# Chemical-Images-to-Molecular-Structure-texts

## Introduction
This repository contains extensive analysis of Bristol-Myers Squibb Molecular Translation. As part of a competition conducted on Kaggle, Bristol Myers Squibb wanted a solution to convert millions of images containing chemical compounds to their respective International Chemical Identifier formula (InChI).

## Background and Problem
In this experimental world, technology has provided various innovative tools; however, for organic chemists, the most accessible tools are still notebook and pen. They draw sub-atomic or molecular work with the structural notation used for an extended period. Several years of scanned documents can’t be searched for compound depictions by the scientist. The main goal of the Bristol-Myers Squibb Molecular Translation competition was to accelerate the research and development efforts and elevate organic chemist access to chemical research through image recognition of optical chemical structures using a machine learning algorithm. 
In this project, we’ll convert chemical images to the molecular structure annotated by InChI text.

## Results
This section will discuss the Exploratory data analysis, optimization, pre-processing, and training models.
1)	Exploratory Data Analysis- 
•	The dataset used in this project is from Bristol-Meyers Squibb’s bms molecular translation. There are 242418f labels in the training dataset.
•	String length of labels in the sample set of training labels are: [130,173,156,141,68]
•	The mean, median, and maximum character length of labels in the training dataset are 120, 115, and 397, respectively.
•	The Dataset comprises 100 features that are depicted by Image Pixels.

2)	Model and Pre-processing
•	Build a model to predict the chirality of each chemical compound
•	In our dataset of 2.4 million compounds, nearly 2 million compounds are not chiral, whereas 0.4 million are chiral with the chirality flag as 1
•	Preprocessed training images by resizing them and bringing them to the same color gradient
•	Build a Neural Network model using EfficientNet, which predicts the chirality of chemical compounds, achieving a validation accuracy of 92% with a log loss of 0.43. 
•	Performed Batch Normalization after every layer of the training model
•	Build 2 models, among them one model is 3 layered network, calculating the Levenshtein distance of validation data as 7.73. Our model predicts the same chemical structure with an average error of 7 characters
•	The other model is 5 layered network, calculating the Levenshtein distance of validation data as 8.95. Our model predicts the same chemical structure with an average of 8 characters

## Requirements
This project requires the below libraries:
numpy
pandas
opencv-python
matplotlib
tqdm
sklearn
tensorflow
keras
albumentations
Levenshtein

You can simply install them by using:
pip install <package_name>

## Usage

This repository contains 2 folders. Input folder is the data folder. Raw data can be downloaded from "https://www.kaggle.com/competitions/bms-molecular-translation/data", which is of 8 GB. After unzipping data it can be placed in the input folder for further analysis. Another study of this project which included arranging the training data based on their InChI characters, which can be downloaded from "https://www.kaggle.com/code/wineplanetary/understanding-inchi-format-and-arrange-train-label/data" and placed in input/bms-molecular-translation.

The code folder contains following:
1. EDA.ipynb contains Exploratory Data Analysis of the molecular data. Various visualizations of the images, height-width distributions, analysis of InChI formulae and the length of target variables.
2. Model.ipynb contains the first analysis of the molecular data, which is based on predicting the chemical compound's chirality. 
3. Model 2.ipynb contains the second analysis of the molecular data which is predicting the InChI structure of the chemical compound.
