# CANARY-NLP
 
Machine Learning framework for the CANARY project. This framework utilizes eye-tracking data and speech data to predict if a participant is a patient or a healthy control. This is an NLP focused fork of the main framework.
[Click here for documentation.](https://docs.google.com/document/d/1GpOHRY3YqOn_rWwBOj5ddYST5MnzThyxnKsRWb9qZiA/edit?usp=sharing)

## Setup
1. (Recommended) Install Anaconda 3 on your system: https://www.anaconda.com/products/individual
2. Download/clone this repository wherever you'd like in your system.
3. Open a terminal **within the repository folder**. In the terminal (Linux)/Command Prompt or Anaconda Prompt (Windows), execute this command: 
   `conda create --name canary python=3.8.5` .
   This will create a virtual environment called "canary", so that it doesn't mess up your normal installation environment.
4. To activate this environment, execute in the same terminal:
   `conda activate canary`. 
5. To install all the dependencies of this framework, execute:
   `pip install -r requirements.txt`
6. (Optional) If you make any changes to the python packages and would like to save them in the requirements.txt file, then execute:
   `pip freeze requirements.txt`
   
## Editing parameters
To use the framework, the file **params/settings.yaml** contains all the parameters to run the experiment. All the parameters defined in **params/settings.yaml** are modifiable, but the ones that would need to be changed the most depending on each experiment are:
1. **seeds**: defines the number of seeds the framework will run for
2. **folds**: defines number of folds for CrossValidation
3. **dataset**: defines the dataset this framework can run on. Current options are _canary_ or _dementia_bank_.
4. **mode**: defines the mode of experiment. Can be _single_tasks_ or can be _fusion_. _ensemble_ will be added soon.
    1. _single_tasks_: runs each of the specified tasks and reports their results separately. 
    2. _fusion_: runs all the specified tasks separately, then combines their results through averaging and reports results.
5. **classifiers**: a list of classifiers that can be run through the framework. 
6. **tasks**: a list of tasks that can be run through the framework. 
7. **output_folder**: name of the folder where the results will be stored at the end of the run. This folder will be kept under the **results** folder.

Within **params/settings.yaml** file, all possible input values for each parameter have been provided in the comments of the file.

## Running the framework
After setting up the parameters, it's time to run the framework. Either use a Python IDE and open **main.py** and run it from there, or using the terminal, execute this line within the repository folder:
`python main.py`
Note: The canary environment has to be activated everytime a new terminal is opened.

The results would be saved at **results/dataset/output_folder** where the dataset and output_folder are the ones specified in **params/settings.yaml**.
A CSV file under the output_folder will appear (having the same name as the output_folder) that will contain results aggregated over all seeds.

