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
       

       

