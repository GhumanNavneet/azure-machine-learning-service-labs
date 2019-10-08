# Lab 4 - Model Training with AutoML

In this lab you will us the automated machine learning (Auto ML) capabilities within the Azure Machine Learning service to automatically train multiple models with varying algorithms and hyperparameters, select the best performing model and register that model.

## Exercise 1 - Get oriented to the lab files
1. On your local computer expand the folder `C:\LabFiles\azure-machine-learning-service-labs-master\starter-artifacts\visual-studio-code`.<br/>
2. Expand the `data` folder. This folder contains the CSV file `UsedCars_Affordability.csv` which contains the complete data set with labels (Affordable is 1 for affordable, 0 for not affordable).<br/>
   <img src="images/data1.jpg"/><br/>
3. To run a lab, start Visual Studio Code and open the folder: `04-automl` and click the starting python file: `04_automl.py`.<br/>
4. For setting `azure_automl` as your interpreter select **Python Interpreter**. This will take 2 minutes to setup<br/
    <img src="images/select.jpg"/><br/>
5. Once you select the python interpreter, select `azure_automl`
    <img src="images/python.jpg"/><br/>
6. `04_automl.py` is the Python file you will step thru executing in this lab.<br/>
7.  You need to `Run Cell` just above the step for each steps as show below.<br/>
   <img src="images/lab04.jpg"/><br/>

## Exercise 2 - Train a model using AutoML
This lab builds upon the lessons learned in the previous lab, but is self contained so you work thru this lab without having to run a previous lab.  
1. Begin with **Step 1**. In this step you are loading the data prepared in previous labs and acquiring (or creating) an instance of your Azure Machine Learning Workspace. In this step, Get the values for `subscription_id`, `resource_group` from your **Environment Detail Page** and set them as below<br/>
 * Set the workspace_region as `eastus`<br/>
   <img src="images/cred2.jpg"/><br/>
   <img src="images/eastus.jpg"/><br/>
2. Execute **Step 1**. You will be prompted to log in to your Azure. Use the **Azure credentials** that are given in your **Environment Detali Page**<br/>
   <img src="images/cred.jpg"/><br/>
``
If in case prompted did not appare, Check the Microsoft edge Browser in virtual machine
``
   <img src="images/lab21.jpg"/><br/>
3. To train a model using **AutoML** you need only provide a configuration for AutoML that defines items such as the type of model (classification or regression), the performance metric to optimize, exit criteria in terms of max training time and iterations and desired performance, any algorithms that should not be used, and the path into which to output the results. This configuration is specified using the `AutomMLConfig` class, which is then used to drive the submission of an experiment via `experiment.submit`.  When AutoML finishes the parent run, you can easily get the best performing run and model from the returned run object by using `run.get_output()`. **Execute** Step 2 to define the helper function that wraps the AutoML job submission.<br/>
   <img src="images/lab22.jpg"/><br/>
4. In **Step 3**, you invoke the AutoML job. **Execute** Step 3.<br/>
   <img src="images/lab23.jpg"/><br/>
5. Try out the best model by using Step 4.<br/>
   <img src="images/lab24.jpg"/><br/>

## Exercise 3 - Register an AutoML created model
1. You can register models created by **AutoML** with Azure Machine Learning just as you would any other model. **Execute** Step 5 to register this model.<br/>
   <img src="images/lab25.jpg"/><br/>
