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
  * Accuracy of KNN Classifier is 79.63%, Decision tree Classifier is 73.62% and Random Forest Classifier is 78.84% on the Test data.
  * Accuracy from the KNN Classifier is slightly higher than that of Random Forest but much higher than the Decision tree.
  * The computational complexity for KNN is comparatively more as it doesn't built a generalised model during the training phase hence it requires more time in testing phase,     also we can say that it computes distances of each query instance to all training samples but as KNN performs instance-based learning, a well-tuned K can model complex       decision spaces having arbitrarily complicated decision boundarie which are not modeled by other 'eager' Classifiers like Decision tree.
  * KNN naturally supports incremental learning.
  * Random Forest overfitts the model as it is showing less bias and high variance, thus making it less compatible for this data.
    But KNN is showing less bias and less variance as compared to other Classifiers.
  * KNN classifier gives test error rates closer to that of Bayesian classier (the gold standard)
  * KNN classifier works better in large number of samples like this data.
       

