# Fetal Health Dataset Analysis
## About the Dataset
This project aims to classify fetal health as Normal, Suspect, or Pathological using features extracted from Cardiotocogram (CTG) examinations. A neural network was built and trained to perform this multi-class classification task.

## Dataset

The dataset used is from Kaggle and contains 21 features related to fetal heart rate and uterine contractions. The target variable, fetal_health, is divided into three classes:
1. Normal
2. Suspect
3. Pathological

The dataset can be found [here](https://www.kaggle.com/datasets/andrewmvd/fetal-health-classification).

## Project Workflow

The project followed a standard machine learning pipeline:

- Data Cleaning: Removed duplicate entries and corrected messy column names.

- Outlier Handling: Replaced outliers in numerical columns with the mean of the non-outlier data.

- Feature Selection: Dropped redundant histogram-related features to create a more focused feature set.

- Data Normalization: Scaled all numerical features to a common [0, 1] range using min-max scaling. Two constant-value columns were dropped during this process, resulting in a final set of 8 input features.

- Model Building: Constructed a Feedforward Neural Network using PyTorch.

- Training and Evaluation: Trained the model and evaluated its performance on an unseen test set.

## Model Architecture

A Feedforward Neural Network (Multilayer Perceptron) was built with the following structure:

- Input Layer: 8 neurons, one for each input feature.

- Hidden Layer 1: Takes 8 neurons as input and outputs 7 neurons, followed by a ReLU activation function.

- Hidden Layer 2: Takes 7 neurons as input and outputs 12 neurons, followed by a ReLU activation function.

- Output Layer: Takes 12 neurons as input and outputs 3 raw scores (logits), one for each class.

The model was trained using Stochastic Gradient Descent (SGD) as the optimizer and Cross-Entropy Loss as the criterion function, which is ideal for multi-class classification.

## Results

The final model achieved an accuracy of 88.8% on the unseen test data, demonstrating its effectiveness in classifying fetal health based on CTG features.
