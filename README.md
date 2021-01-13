# CP-SPP: Constraint-based model for Service Placement Problem in Fog Computing

## Reference
--------------
[1] F. Ait Salaht, F. Desprez, A. Lebre, C. Prud'homme and M. Abderrahim, "Service Placement in Fog Computing Using Constraint Programming," 2019 IEEE International Conference on Services Computing (SCC), Milan, Italy, 2019, pp. 19-27, doi: 10.1109/SCC.2019.00017.

## Summary
--------------

This repository contains the source code of the CP-SPP model provided in [1] that achieves a service placement in a given infrastructure network based on [Choco Solver](https://github.com/chocoteam/choco-solver) which is a Constraint programming solver. 


An example is provided to run and quickly apprehend the model.

Inputs: property files with the descriptions of :
        - Network infrastructure 
        and
        - The services to deploy

Output: The infrastructure nodes on which to place each component of each service.

## Requirements
--------------
<u>Tools</u>:

- JDK8+
- Maven 3+

- You should be able to run it within the IDE (IntelliJ IDEA).

<u>Libraries</u>:

- [Choco Solver](https://github.com/chocoteam/choco-solver)


## Installation 
--------------
(You can refer to https://github.com/chocoteam/choco-solver/tree/master/examples for more details)

- Create a repository in which to clone the project and move in it:  
        ```mkdir SPP_code && cd SPP_codeSPP_code```
- Clone this repository:  
        ```git clone https://github.com/BeyondTheClouds/PLACEMENTS/SPP_code.git```
        
- Build (install dependencies):  
    * From command line : Move to the "java" directory ```cd java``` and run ```mvn clean install```
    * From JetBrains IntelliJ : Right click on ```pom.xml``` file and select ```Add as Maven project```. All the dependencies is provided on this repository (pom.xml). 

## Run the code
--------------
You can run the project from inside an IDE, by running the main method in ```src/main/java/io/cprudhom/saica/Placement.java```

### Parameters

This repository comes with an example properties files, at "reources" folder (```"./src/main/resources/Infra_Ye_Small.properties"``` and ``` "./src/main/resources/Appli_Ye.properties"```).  These files contain respectively the infrastructure and services descriptions (topologie(s), nodes/edges capacities/requirements, ...)

Follow the same conventions while writing your own ```.properties``` file.  
And if you wrote your own ```.properties``` file, please change the argument of the variables "Infra_src" and "Appli"  in the main function of ```java/src/Placement.java``` accordingly.

### Run the project

You can run the project from inside an IDE, by running the main method in ```java/src/Placement.java```

an output would look like this:

```
Model[CP-SPP], 551 variables, 427 constraints, building time: 0,152s, w/o user-defined search strategy, w/o complementary search strategy

C0 ----> 3;C1 ----> 3;C2 ----> 1;C3 ----> 2;C4 ----> 2;C5 ----> 7;C6 ----> 1;C7 ----> 2;C8 ----> 8;C9 ----> 2;C10 ----> 11;C11 ----> 12;C12 ----> 13;C13 ----> 14;C14 ----> 15;C15 ----> 16;
Model[CP-SPP], 1 Solutions, MINIMIZE nb distinct Hosts = 11, Resolution time 0,239s, 441 Nodes (1 841,5 n/s), 837 Backtracks, 0 Backjumps, 426 Fails, 0 Restarts

```
