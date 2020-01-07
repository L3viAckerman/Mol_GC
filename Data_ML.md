# Data prepare for ML algorithms
## Generate data
1. Abtracts

Data is given in many xyz data that stored the position information of all atoms in the molecule.

We also are given the train.csv and test.csv that store the value of the pair J coupling we need to compute.

Udsing the information in the xyz file, we need generate the equivalent features and feed it to ML and DL model.

2. Proposed 
 
The ML models require the data in the pair X, y to train and X, to feed to models for predicting.

We choose the pipeline for generating useful feature is: from xyz file , use some helpful library such as RDKit or OpenBabel 

to calculate the mol (representation of molecule that have the xyz file), after that we use this mol to calculate the chemiscal and 
    
physical features of molecule. All of them need to be stored in the format .csv for future processing. We also xyz file to calculate 

some features about the distance and angles of the atoms in the molecule. Using sklearn and networkx to build the graph of molecular. 

This graph againsts the bond propertice between two atoms.

3. Library 

We use some libraries in python for acceleration the computing process. 

List of libraries:

* Networkx
* RDkit
* OpenBabel 
* Sklearn
* Scipy

4. Future works

Some authors proposed the different to generate and store features of molecular, such as using ASE or using cut-of-radius for atoms.

We will review and try to find the better way for genrating and storing them.