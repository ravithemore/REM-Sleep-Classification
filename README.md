# REM Sleep Disorder prediction using EDF dataset and Score level fusion

## Table of Contents

- [Abstract](#abstract)

- [Introduction](#introduction)

- [Objective](#objective)

## Abstract

Rapid eye Movement (REM) sleep behavior disorder belong to the family of sleep
disorders occurring worldwide. Several existing studies demonstrate EEG images and EMG metrics for classifying RBD & non-RBD patients. However, merely few researchers have used EDF data available into the existing algorithms. This paper builds an ensemble method combing the metrics and results of different models trained on the EDF dataset to analyze the difference between REM and non-REM patients. The EDF's numerical data is also integrated for further results. The different algorithms and models which were trained included Naive Bayes Classification, Random Forest, Logistic Regression and Gradient Boosted trees. However, the final prediction is attained by their score-level fusion, where each model is assigned with some weight based on its individual recall score.

## Introduction

Sleep is a significant determinant of mental wellbeing and happiness. Sleep disorders are conditions that impair our sleep or prevent us from getting restful sleep and, as a result, can cause daytime sleepiness and other symptoms. Troubled sleep is a common complaint all over the world. According to the American Sleep Association (AMA), sleep disorders affect 50 to 70 million adults in the United States of America  Not getting the proper amount or quality of sleep leads to more than just feeling tired. Sleepiness interferes with cognitive function, which can lead to learning disabilities in children, memory impairment in people of all ages, personality changes and depression. People who are deprived of sleep have trouble making decisions, irritability, have problems with performance, and slower reaction times, placing them at risk for automobile and work-related accidents. Sleep loss can also adversely affect life by contributing to the development of obesity, diabetes and heart disease. Insomnia, Bruxism, Narcolepsy, Nocturnal frontal lobe epilepsy, Periodic leg movements, REM behavior disorder, Sleep-disordered breathing are the widely known forms of sleep disorders. The most predominant manners of sleep are Rapid Eye movement (REM), sleep and non-REM sleep. REM sleep first begins about one and a half hours after falling asleep. The eyes switch rapidly behind shut eyelids from side to side. The respiration is quicker; the pulse and heart rate rise to waking levels. Most of the dreams take place during REM sleep, while some could occur in non-REM too. The body passes through all stages of non-REM sleep before entering the REM. Each of the stage lasts for 5-15 minutes.


## Objective

The objective of work was to study the EDF data and process it in such a way that we can use it for visualization and to train model. Also, after visualizing the EDF data, we had used different type of classification algorithms to build a model, which can classify the REM and Non-REM type of sleep disorder. So that, it can help people manage their sleep time accordingly and easily understand their REM sleep disorder.

<img src="https://github.com/Vishesht27/REM-Sleep-Classification/blob/main/visuals/tech_stack_achitecture.jpg">

## Dataset Description

The Cyclic Alternating Pattern (CAP) is a periodic EEG activity occurring during NREM sleep. It is characterized by cyclic sequences of cerebral activation (phase A) followed by periods of deactivation (phase B) which separate two successive phase A periods with an interval <1 min. A phase A period and the following phase B period define a CAP cycle, and at least two CAP cycles are required to form a CAP sequence. The CAP sleep database a collection of 108 polysomnographic recordings registered at the Sleep Disorders Center of the Ospedale Maggiore of Parma, Italy. The waveforms (contained in the .edf files of the database) include at least 3 EEG channels (F3 or F4, C3 or C4 and O1 or O2, referred to A1 or A2), EOG (2 channels), EMG of the submental is muscle, bilateral anterior tibial EMG, respiration signals (airflow, abdominal and thoracic effort and SaO2) and EKG. Additional traces include EEG bipolar traces, according to the 10-20 international system (Fp1-F3, F3-C3, C3-P3, P3-O1 and/or Fp2-F4, F4-C4, C4-P4, P4-O2).

The 16 healthy subjects included in the study did not present any neurological disorders and were free of drugs affecting the central nervous system. The 92 pathological recordings include 40 recordings of patients diagnosed with NFLE, 22 affected by RBD, 10 with PLM, 9 insomniac, 5 narcoleptic, 4 affected by SDB and 2 by bruxism. The age and gender of the subjects are reported in a spreadsheet.


## Working principle

The data was in image format so first step was to extract features from the data and then combine it with .txt file where the details of the patient are present. We followed this by creating separate visualization functions and then merged both the kinds using a merger function. We preprocessed the data while visualizing the different aspects of the features and which plot and sub-features are more important for the model. Then after preprocessing we applied classification algorithm on the model. 

## Feature Extraction

We used libraries like Independent Component Analysis and minmax scalar for getting the sub-features of the model. The components were separately visualized and analyzed for better result and then columns of time and sleep-stages were modified accordingly.

### Matplotlib

For plotting graph, we are using matplotlib library that allows us visual access to huge amounts of data in easily digestible visuals. Matplotlib consists of several plots like line, bar, scatter, histogram etc.

### TensorFlow Decision Forests

TensorFlow Decision Forests (TF-DF) is a collection of state-of-the-art algorithms for the training, serving and interpretation of Decision Forest models. The library is a collection of Keras models and supports classification, regression, and ranking. TF-DF is a wrapper around the Yggdrasil Decision Forest C++ libraries. Models trained with TF-DF are compatible with Yggdrasil Decision Forests' models, and vice versa.

### Random Forest

A Random Forest is a collection of deep CART decision trees trained independently and without pruning. Each tree is trained on a random subset of the original training dataset (sampled with replacement). The algorithm is unique in that it is robust to overfitting, even in extreme cases e.g., when there are more features than training examples. It is probably the most well-known of the Decision Forest training algorithms.

<img src="https://github.com/Vishesht27/REM-Sleep-Classification/blob/main/visuals/random_forest.jpg">

### Gradient Boosted Trees

A GBT (Gradient Boosted [Decision] Tree) Is a set of shallow decision trees trained sequentially. Each tree is trained to predict and then "correct" for the errors of the previously trained trees (more precisely each tree predict the gradient of the loss relative to the model output).

<img src="https://github.com/Vishesht27/REM-Sleep-Classification/blob/main/visuals/gradient_boosted_trees.jpg">

## Summary

To summarize, we extracted the data from the source. Merging the two types of data and files was the first steps towards building a model. We merged the data file and
annotation file for the same. We preprocessed the data and applied Minmax Scalar for scaling the features and visualized the data. After visualization, we filtered the data we needed for training the model. After selecting the data required preciously, we decided to train a simple model and got a poor accuracy. Hence, we decided to go with ensemble learning. Ensemble learning is the process by which multiple models, such as classifiers or experts, are strategically generated and combined to solve a particular computational intelligence problem. We then trained and separate models including Naïve Bayes, Gradient Boosted trees, Logistic Regression and Random Forest. TensorFlow and Scikit-learn libraries were used for the same. After that we tried to combine to the metrics of all models to put in comparison and visualization. After carefully observing the results and visualization of the comparison, we did a score level fusion for the same.

We intend to add another feature that will advise the patient on how to avoid REM sleep disorder. The model will make recommendations based on the patient's condition; if the patient does not have REM sleep disorder, the model will make recommendations based on the sleep disorder.

<img src = "https://github.com/Vishesht27/REM-Sleep-Classification/blob/main/visuals/accuracy.jpg">

