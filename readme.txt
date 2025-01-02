# Humboldt Individual Recognition.

The provided code contains all the scripts and data necessary to reproduce the content of our manuscript. The scripts are written as Python notebooks and were executed in a Google Colab environment (a `requirements.txt` file is provided).

This is not a standalone application, but research-oriented code used to train the models and perform the analyses presented in our manuscript.

### File Structure
This repository consists of the following elements:

-requirements.txt: Requirements file for the Python environment.
- readme.md: This file.
- Humboldt_train_CLEAN_FINAL.ipynb: Main script 1. This script contains the training procedure for the Neural Network models.
- DATA_HUMBOLDT_FINALS: Data folder. It contains the raw data in NumPy .npy format, used (read) by Main Script 1.
- FINAL_PASSES: Main models folder. It contains the trained models from the Main Script.
- saved_models: Secondary models folder. It stores non-final models, useful for model exploration.
- DATA_ANALYSIS_FINALS: Analysis folder. It contains the scripts with the results.
    - ANALYSIS_Humboldt.ipynb: Script for the analysis of Humboldt recognition.
    - ANALYSIS_Turtles.ipynb: Script for the analysis of Hermann's tortoise recognition.
    - Results: Data folder used for the Humboldt analysis script.
    - Results_Turtles: Data folder used for the tortoise analysis script.
      

### Overview
This project performs data analysis and image classification using deep learning models such as InceptionV3, ResNet, and others for chest recognition on the Humboldt dataset and the shell on Hermann's Tortoise. The models are implemented using TensorFlow and Keras, and the notebook is primarily designed to run on Google Colab but can also be set up on a local machine.

## 1. System Requirements

**Software Requirements:**
Python 3.10.12 was used in our system
Dependencies : see requierements.txt file for full list of dependencies

**Hardware Requirements:**
This code has been tested on Google Colab environment, on a Tesla T4.


## 2. Installation Guide

Option 1. Running on Google Colab (recommended)
No installation needed. Simply upload the notebook to Google Colab with the same structure as in this repository.

You must change the **path** variable (at the beginning of the code) to point to your Google Drive path in the following files: 
- Humboldt_train_CLEAN_FINAL.ipynb
- ANALYSIS_Humboldt.ipynb
- ANALYSIS_Turtles.ipynb
   


Option 2: Running Locally
Ensure Python 3.8+ and all dependencies are installed.
If you do not have a GPU, training can be very very slow, if functional at all. 

Install dependencies by running:

`!pip install -r requirements.txt`

Mount or download the dataset to a local directory. Modify the paths in the notebook accordingly.


## 3. Demo
(Running the sowfware with our data.)

Open the notebook in Google Colab.

Ensure that the Google Drive is properly mounted by running the corresponding cell:
Ensure that the main `path` variable has been set to your own directory.
Run the notebooks.

**Expected Runtime:**

On Google Colab with a GPU (e.g., Tesla T4), the training process should take approximately 30-45 minutes, depending on the dataset size and the complexity of the model.
On a local machine without a GPU, the runtime may be significantly longer (several hours for large datasets).


### 4. Instructions for Use

**Running the Software on Your Data**

Update the paths in the notebook to point to your dataset locations. For example:



**Train Models:**

The notebook offers multiple deep learning models such as InceptionV3, ResNet, etc. You can train a model by executing the corresponding cell.

Customize the model as necessary for your data.

**Evaluate Model:**

After training, evaluate the model using the built-in metrics:

Reproduction Instructions (Optional)
To reproduce the exact results in the notebook:

**Dataset**
The provided dataset should be in .npy format with the images and associated metadata with the labels. The notebook already contains preprocessing steps to normalize images and prepare the data for model training.

Inside the the npy file there should a array version of all the pictures, with domensions (N, l, w, k) where
- **N** is the number of images
- **(l,w)** is the size of the images.
-  **k** is the number of channels (3 for color images, 1 for grey images).
There should also be a dataframe with metadata, in particular the labels of the known images.

Both the array and the metadata, are encapsulated in a dictionary, which is saved as the `.npy` file. 


**License**
This software is licensed under the MIT License.

**Authors**
Victor Planas-Bielsa & Miguel Rodriguez_Olmos
