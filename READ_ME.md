# Anomaly-Detection-in-Traffic-Data

## Code
Contains all the jupyter notebook codes and their datasets (csv)

### STFdata_2min 
This is the basic data analysis to visualize the data. (not the data I have used for further analysis) I havent used any figures or datasets from this code, its purely just for EDA.

### cross_detector
This file contains analysis based on comparison with other detector, using correlation coefficient. We use location dataset to form triplets of detectors (& duets) and use those to find correlation between them. Then we do some analysis on them and plot timeseries graph for visualization. Lastly we have the code here used to generate the dataset that I will use ( in data folder)

### data_preparation
This file contains code to create dataset for training the profile model. We use triplets and correlations to obtain a training dataset and remove some detectors.

### profile_model
This file contains code to train profile model. First we visualize our training data and then use Ml model to train it. In analysis section we create a correltion matrix and try to compare the accuracy of model with correlation values for each day. Aslo plot different accuracy values for different correlation intervals.

### profile_model_analysis
Here for further analysis, we first create a labelled training data using mask and test data. Then we test on test data, using best model obtained before. Here we know exactly which data was used for testing hence we can plot scatter plots and heatmaps to compare the correlation values, and also avg rank histograms.

### classification
Here we first find those detectors which are present in triplets. Then get their correlation matrix. Remove those whose data is not present . Then we label the data for supervised training, and similarly construct the input output tensors. Here also we label the training and testing data to so that we can directly analyse only test data. Then we find the best model fit for classifying anomalies and normal data. Similarly we plot the heatmap and histogram of probability of data being good vs the correlation.

### model_profile
Contains profile models' saved ML models.

### model_classification
Contains supervised models' saved ML models.

### Prediction Model
Has the prediction model code a its separate dataset. We dont use this code finally, as we dont get satisfactory results. This model is borrowed from XieXin

### result_csv
Contains intermediate csv files used for analysis. 

### data
Contains the data used for my project.

## Papers
Contains research papers for references, and also includes my ppt and drafts.

## Plots
Contains Resultant plots

## Extra Information

1) Cross Detector Analysis:

   Errors in detector_info dataset: The spelling of Northbound and Souhtbound was wrong, and AID07117 doesnt mention the bound, should
   be Westbound

   AID05126    Kwai Chung Road near Lai King MTR Station - Nouthbound 

   AID05129    Tsuen Wan Road near Wing Kin Industrial Building - Nouthbound 

   AID05204    Tsuen Wan Road near Tsuen Wan Sports Centre - Sorthbound 

   AID07117    Lung Cheung Road near Diamond Hill MTR Station 

   TDS/TPR/10002    Tai Po Road - Tai Po Kau near Tai Po Kau Fresh Water Pumping Station - Souhtbound 

   +more

2) Cross detector analysis :
    It removes the rows during corr calc. if there is NaN in any one of the values.

    AID04201 : Found 0.28 low correlation : There is a tree blocking the view.

    AID01213 : Found 0.49 correlation : Big junction 

    AID07102 : Found 0.33 low correlation : There is tree blocking the view.

    AID08203 : Found 0.1/0.25/-ve low correlation : There is tree blocking the view.

    AID09120 : No service most of time.

    TDS90023 : 0.1 coree : Dont know

    AID07226 : 0.5/0.6 coorelation : Is there dirt on the detector? Or bcz of junction 

    AID01130 : 0.6 corr : Camera not woking properly?

    AID05223 : Is some structure blocking?

    TDS10006 : Not in order

    AID05114-5115 : Diff lane but 90+ corr

    AID09204-9208 : Same no of lanes, but bad correlation 0.5/0.6

    AID09101-9108 : Same no of lanes, but bad correlation 0.7/0.6
    
    AID09118 & AID09119 : Corr 0.83, but for a particular time, the data is different.
 