# DSK - MLC Tool

## Table of Contents
--------------------
<!--ts-->
* [config](#config)
    * [```instances.json```](#```instances.json```)
    * [```mappings.json```](#```mappings.json```)
* [instances](#instances)
    * [YYYYMMDD](#YYYYMMDD)
        * [raw_input](#raw_input)
        * [steps](#steps)
            * [coll_alloc](#coll_alloc)
                * [interm](#interm)
                * [output](#output)
* [logs](#logs)
    * [YYYYMMDD_logs](#YYYYMMDD_logs)
        * [collateral_allocation](#collateral_allocation)
* [src](#src)
    * [modules](#modules)
    * [```EngineMngr.py```](#```EngineMngr.py```)
    * [```InstanceMngr.py```](#```InstanceMngr.py```)
    * [```Admin.py```](#```Admin.py```)
* [```__init.py__```](#```__init.py__```)
<!--te-->
---------

## config
This folder includes the files to configure the variables and keep the valuable information about the backup of the system. 
### ```instances.json```
The file will keep the data in JSON format as the checkpoint of the system.  Under the  ```instances{}``` json, there will be the <b>ID</b>, <b>date & time </b> and <b> steps</b> of the instance that is created once the button is clicked.  

In the ```steps{}```, there is the status and iteration of each step. This will be used to sustain the dependency of every step from one another. So that, once the step is launched, the <b>iteration</b> will be increased and it will benchmark the logic of the system. For example, as long as the iteration of a step is more than the previous steps, it cannot be launched.

Additionally, the <b>status </b> indicates whether the step succeeded or not. 1 stands for <i> success </i>, 0 stands for <i> not launched </i>, 2 stands for <i> failure </i>. 

This file can be modified and expanded when there are updates in the further levels.

### ```mappings.json```
The json file will hold the mapping of the variables, such as naming. (to be continued)

## instances
Once the button is clicked, the instance object will be created in this folder and it will include several sub-folders systematically.

### YYYYMMDD
The date of the creation is assigned as the name of the instance. 

#### raw_input

It includes the raw input of the instance to initiate. The input data is entered by the user will be updated in the next steps, if necessary.

#### steps
<b> steps </b> folder can consist of the 5 predefined steps. The folder of each step is created once the step is launched. 

#### coll_alloc
Once the step is launched, the [interm](#interm) and [output](#output) folders are created automatically.

##### interm

The folder holds the intermediary data that are either obtained directly from the [raw_input](#raw_input) or  data that are modified in the previous steps. 

##### output

It contains the the output data of the step which can be downloaded by the user, when it is required.

## logs

The folder consists of the logs of each step. Once the steps are created, the [YYYYMMDD_logs](#YYYYMMDD_logs) directory of them will be automatically assigned in this folder. 

### YYYYMMDD_logs
Each step has its seperate log file to found an isolated and integrated environment.

#### collateral_allocation
This folder has only a file which is the logs of the activity applied on the step. 

## src

In this section, there will be all the source codes that are developed throughout the project.
Further files and folders can be uploaded depending on the procedure.

### modules
The folder includes built-in or user-defined modules to contribute to the functionality of the project. Each module has only one purpose to serve and it is independent from the others in the directory.

### ```EngineMngr.py```

This .py runs the engine functions, such as the logger, call of the steps, backup of the logs etc. 

### ```InstanceMngr.py```

Once the project is run, Instance Manager will be triggered before the compilation of the [```EngineMngr.py```](#```EngineMngr.py```). It will create the instance with the parameter of ID and get the raw input. 

### ```Admin.py```
(to be decided)

## ```__init.py__```

When the <b> run </b> button is clicked by the user, ```__init.py__``` is triggered, as default. This code is the initiative of all the project
