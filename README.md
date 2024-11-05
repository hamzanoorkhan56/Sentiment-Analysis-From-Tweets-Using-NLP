# Sentiment-Analysis-From-Tweets-Using-NLP

This project focuses on building a text classification system designed for sentiment analysis. It includes steps for data input, preprocessing, feature extraction, cross-validation, and error analysis. The primary goal is to train and evaluate a classifier for sentiment detection, analysing its performance across various metrics.

## Table of Contents
- [Project Overview](#project-overview)
- [Features](#features)
  - [Data Parsing and Preprocessing](#data-parsing-and-preprocessing)
  - [Feature Extraction](#feature-extraction)
  - [Cross-Validation](#cross-validation)
  - [Error Analysis](#error-analysis)
- [Results](#results)
- [Acknowledgments](#acknowledgments)

---

## Project Overview

This project is an end-to-end pipeline for sentiment analysis using custom functions to process, vectorise, and evaluate text data. Starting with basic text preprocessing and feature engineering, it progresses to training a classifier with cross-validation and evaluating performance. The analysis includes metrics such as precision, recall, F1-score, and accuracy.

## Features

- **Data Parsing and Preprocessing**: Parses labeled text data and tokenizes it for further processing.
- **Custom Feature Extraction**: Converts tokenised text into feature vectors with customisable weighting schemes.
- **Cross-Validation and Performance Evaluation**: Uses 10-fold cross-validation to assess model performance.
- **Error Analysis**: Includes a confusion matrix to identify and analyse errors in classification.

### Data Parsing and Preprocessing

1. **`parse_data_line()`**  
   This function parses a line of a tab-separated text file, extracting the label and text. It returns a tuple containing the label and the corresponding text.

2. **`pre_process()`**  
   This function tokenizes the input text, transforming it into a list of words (tokens) to facilitate feature extraction. 

### Feature Extraction

1. **`to_feature_vector()`**  
   Given a preprocessed list of tokens, this function generates a feature vector represented as a Python dictionary. The dictionary keys are tokens, and the values are customizable weights (e.g., binary weights, term frequency, or other custom weights). Additionally, a global dictionary of features can be created to keep track of all unique tokens used in the dataset.

### Cross-Validation

1. **`cross_validate()`**  
   This function performs 10-fold cross-validation on the training data, evaluating the model across each fold. The evaluation includes metrics such as precision, recall, F1-score, and accuracy, which are averaged across all folds and stored in `cv_results`. This ensures a robust assessment of model performance.

### Error Analysis

1. **Confusion Matrix**  
   Using the `confusion_matrix_heatmap()` function, the project visualizes false positives and false negatives for each class in a confusion matrix. This step provides insights into where the classifier may struggle, allowing for targeted improvement.

2. **False Positives and False Negatives**  
   For deeper analysis, false positives and negatives for the positive label are printed to a file to facilitate further review of misclassified cases.

## Results

After running the pipeline, the classifier’s performance is reported using precision, recall, F1-score, and accuracy metrics. The confusion matrix provides a visualization of classification errors, highlighting areas for potential improvement. These results serve as a benchmark for analyzing the effectiveness of the preprocessing and feature extraction steps.
