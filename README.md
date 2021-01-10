Activity-Recognition-from-a-Single-Chest-Mounted-Accelerometer
==============================================================
Steps :- 
========
## Data Collection

* !wget "https://archive.ics.uci.edu/ml/machine-learning-databases/00287/Activity%20Recognition%20from%20Single%20Chest-Mounted%20Accelerometer.zip"
* !unzip "/content/Activity Recognition from Single Chest-Mounted Accelerometer.zip"

## Data Preperation

* Used glob module to retrieve files as it is used to retrieve files/pathnames matching a specified pattern
  
      glob(r"path\classification\Activity Recognition from Single Chest-Mounted Accelerometer/*.csv")
       
* Adding some extra attributes like magnitude of acceleration (A_m)       
* Anomaly Detection by using zscore and EllipticEnvelope as the data is normally distributed and multimodal.
  
  Percentage of outliers in the whole data= 10%
       
## EDA (Exploratory Data Analysis)

* Exploring each feature
* Exploring the relationship between participants and their activities

## Data Modelling

* Data Spliting
* Feature Scaling 
* Building Pipeline & Model Training
  * Finding the optimal value of k in KNN (K-Nearest Neighbors)
  * Classification Report
  * Confusion Matrix
* Cross- Validation
* Comparison between KNN , Decision tree and Random Forest Classifier
### Reasons for selecting KNN Classifier
* Accuracy of KNN Classifier is 79.63%, Decision tree Classifier is 73.62% and Random Forest Classifier is 78.84% on the Test data.
* Accuracy from the KNN Classifier is slightly higher than that of Random Forest but much higher than the Decision tree.
* The computational complexity for KNN is comparatively more as it doesn't built a generalised model during the training phase hence it requires more time in testing phase,     also we can say that it computes distances of each query instance to all training samples but as KNN performs instance-based learning, a well-tuned K can model complex       decision spaces having arbitrarily complicated decision boundarie which are not modeled by other 'eager' Classifiers like Decision tree.
* KNN naturally supports incremental learning.
* Random Forest overfitts the model as it is showing less bias and high variance, thus making it less compatible for this data.
  But KNN is showing less bias and less variance as compared to other Classifiers.
* KNN classifier gives test error rates closer to that of Bayesian classier (the gold standard).
* KNN classifier works better in large number of samples like this data.
       

Dataset
=======

1. Abstract: The dataset collects data from a wearable accelerometer mounted on the chest. Uncalibrated Accelerometer Data are collected from 15 participants performing 7 activities. The dataset is intended for Activity Recognition research purposes. It provides challenges for identification and authentication of people using motion patterns.

2. Relevant Information:
   * The dataset collects data from a wearable accelerometer mounted on the chest
   * Sampling frequency of the accelerometer: 52 Hz
   * Accelerometer Data are Uncalibrated
   * Number of Participants: 15
   * Number of Activities: 7
   * Data Format: CSV

3. Dataset Information
   * Data are separated by participant
   * Each file contains the following information
      * sequential number, x acceleration, y acceleration, z acceleration, label 
   * Labels are codified by numbers
       * 1: Working at Computer
       * 2: Standing Up, Walking and Going up\down stairs
       * 3: Standing
       * 4: Walking
       * 5: Going Up\Down Stairs
       * 6: Walking and Talking with Someone
       * 7: Talking while Standing
