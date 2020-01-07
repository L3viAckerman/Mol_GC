# Data preparation for ML algorithms
## Generate data
1. **Abtracts**

    Data is given in many xyz files that stored the position information of all atoms in the molecule.
    We are also given the train.csv and test.csv that store the value of the pair J coupling we need to predict.
    Using the information in the xyz files, we need to generate the equivalent features and feed them to ML and DL model.

2. **Proposed**
 
    The ML models require the data in the pair X, y to train and X, to feed to models for predicting.
    We choose the pipeline for generating useful feature, which is: from xyz files , use some helpful libraries such as RDKit or OpenBabel 
    to calculate the mol (representation of molecule that have the xyz file), after that we use this mol to calculate the chemiscal and 
    physical features of molecule. All of them need to be stored in the format .csv for future processing. We also use xyz files to calculate some features about the distance and angles of the atoms in the molecule. Using sklearn and networkx to build the graph of molecular. This graph againsts the bond propertice between two atoms.

3. **Features**
    We care about the local and global features of the molecule. The local feature take the information of the neighborhood atoms and the global features take the system information of all molecular. 

    In local feature, we divide it into two groups like the representation of graph, node features and edges feature.

    In this work, we describle the node features are:
    * The numbers of atoms type around the atoms in pair (we use the graph of bond for calculate this)
    * Type of the atoms 
    * Total number of atom in the neiborhood 
    * The information about the ring (atoms is in the ring)
    * Hyb of atoms 
    * Chiral of atoms 
    * Atomic number of atom

    And edge features is:
    * Bond type
    * Bond length if chemical bond is exist, if non-exist, it will be set to zero
    * Shortest path between them
    * Distance between them
    * Coulomb's matrix between 2 atom
    * Angle betwen 2 atom (if between them has one atoms, if not set to zeros). This feature is speciality of 2J coupling 
    * Cos and Cos2T (calculate when has torsion between 2 atom)
    * Diherial between them if between them has 2 atoms. It is speciality of 3J coupling
    * Torsion
    * If 2 atoms has a bond, some features adding for more information. They are aromatic and ring information.
    * We add information of the atom between the pair 


3. **Library**

    We use some libraries in python for acceleration the computing process. 
    List of libraries:
    * Networkx
    * RDkit
    * OpenBabel 
    * Sklearn
    * Scipy

4. **Future works**

    Some authors proposed the different to generate and store features of molecular, such as using ASE or using cut-of-radius for atoms.
    We will review and try to find the better way for genrating and storing them.