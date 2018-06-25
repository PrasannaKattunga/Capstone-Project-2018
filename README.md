# Capstone-Project-2018
# Project: Using Single Proton Emission Computed Tomography (SPECT) data and Machine Learning to create a diagnostic tool

# Problem: 
Diagnosing of myocardial perfusion condition by analyzing “single proton emission computed tomography (SPECT" images.

# The Target Client/Audience: 
This project aims to develop a Machine Learning (ML) algorithm that could be used by cardiologists as a second-opinion computer-based diagnostic tool. SPECT imaging is frequently used to diagnose patients with myocardial perfusion. From the medical point of view, the main benefit of using an algorithm is to semi-automate cardiac SPECT diagnostic process in order to assist physicians in diagnosing cardiac SPECT images, thereby making this procedure easier, more consistent, and efficient.

# Approach of solving the problem:

We will develop a prediction model for distinguishing normal and abnormal patients using two SPECT datasets: a training set and a testing set. The accuracy of the classification model developed in the training set will be assessed using the testing set.

Training dataset has been binarized by using the following heuristic approach. For each
feature, (2 X 22= 44 Attributes: one for rest, and one for
stress) apply the rule 1+ rule2+ rule 3 for partial diagnosis. Apply rule 4 for
finalized decision. 

Rule 1:    IF [feature stressi - feature resti] < threshold THEN Regioni ABN, where i is the number of ROI

Rule 2:    IF [featureresti < 50 AND feature streesi < 50] THEN Regioni ABN

Rule 3:    IF [featurei < meanj - threshold] THEN Regioni ABN, where i is the number of features, j the number of heart cross-section, mean j the mean value of features along entire cross-section (entire image)

Rule 4:    IF [feature stressi - feature resti] < threshold THEN Regioni ABN, where i is the number of ROIs from the specific part of the LV

After creating a binarized training dataset, using a classification algorithm identify abnormal and normal classifications.

# Data Details: 
The source of the SPECT dataset is UCI repository: https://archive.ics.uci.edu/ml/datasets/SPECT+Heart. The SPECT dataset contains data on 267 patients. Each patient is classified into two categories: normal and abnormal. The SPECT image of each patient was processed to extract 44 continuous features that summarize the image. Thus, the dataset contains 267 rows (patients) and 45 attributes. 

# Deliverables: 
The project deliverables are R code, a final paper, and a slide deck will be posted in GitHub.
