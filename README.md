# IoT-Intrusion-Detection

## Plamen Dzhelepov
[Linkedin](https://www.linkedin.com/in/pdzhelepov) | [Github](https://github.com/plamengj)

## Table of Contents

* [Overview and Motivation](#overview-and-motivation)
* [Data](#data)
  * [Data Preprocessing](#data-preprocessing)
  * [EDA](#eda)
<!-- * [Exploration](#exploration) -->
* [Modeling](#modeling)
  * [Attack type classfication](#attack-type-classfication)
  * [Attack or normal classfication](#attack-or-normal-classfication)
* [Conclusion](#conclusion)


## Overview and Motivation
IoT networks have become an increasingly valuable target of malicious attacks due to the increased amount of valuable user data they contain. In response, network intrusion detection systems have been developed to detect suspicious network activity.
Moreover, IoT traditional network security solutions may not be directly applicable due to the differences in IoT structure and behavior. IoT devices offer low operating energy and minimal computational capabilities. Therefore security mechanism such as encryption protocols and authentication can not be directly applied. Last but not least, The lack of a single standard for IoT architecture. IoT systems may have different policies, and connectivity domains.


## Data
### Description
UNSW-NB15 is an IoT-based network traffic data set with different categories for normal activities and malicious attack behaviors. 

The data contains 400,000+ rows and two columns (an URL & whether it’s malicious or not) that translates to 400,000+ observations and 1 feature (the URL itself). The ratio of benign to malicious URLs is 3:1 in the dataset. I have used pandas and dataframes to examine, plot and analyze this data.

## Data Preprocessing
CSV processed with Pandas, NumPy, skitLearn, then NaN`s were removed. The data was split into training and testing set. And then finally I did some Encoding Transformation.

Then I decided to look into attack or not classification and attack type classification, and select the best model for each.

<!-- ## Exploration
This section contains plots that demonstrate the types of information that can be gleaned from this data set.

This is a heatmap of the correlation matrix and it shows how the features are correlated with each other and with the target.
<div align='left'>
<img src="figures/heatmap.png">
</div> -->

## EDA
<div align='left'>
<img src='figures/attack_or_not.png'>
</div>

<div align='left'>
<img src='figures/attack_types.png'>
</div>


## Modeling
Determine which model should be used to classify category attacks and intrusions detection on IoT networks. Also discover relevant features for model inspection.

<div align='left'>
<img src='figures/attack_or_not_CV.png'>
</div>

<div align='left'>
<img src='figures/attack_type_CV.png'>
</div>


Based on the f1 cross-validation score of both classifications, I chose as my model the Random forest and scored it on the testing set. 

These are the feature importances for attack or not classification:
<div align='left'>
<img src='figures/fi_attack_or_not.png'>
</div>

And these are the feature importances for the attack type classification:
<div align='left'>
<img src='figures/fi_attack_type.png'>
</div>

<!-- And the confusion matrix:
<div align='left'>
<img src='figures/confusion-matrix.png'>
</div> -->

## Attack Type Classification
This dataset has nine types of attacks: Fuzzers, Analysis, Backdoors, DoS, Exploits, Generic, Reconnaissance, Shellcode and Worms. 

## Attack or Normal Classification


F1 score (weighted average of the precision and recall) is the primary evaluation metric on testing data to show the performance of the trained model. The Random Forest model marginally outperformed the other model in both classificati9ons. 


## Conclusion
UNSW-NB15 botnet datasets with IoT sensors' data are used to obtain results that show that the proposed features have the potential characteristics of identifying and classifying normal and malicious activity. The eole of the ML algorithms is for developing a network forensic system based on network flow identifiers and features that can track suspicious activities of botnets is possible. Furthermore, Random Forest model provides a higher detection rate, accuracy and a lower false positive rate compared with both classification responses. The ML model metrics using the UNSW-NB15 dataset revealed that ML techniques with flow identifiers can effectively and efficiently detect botnets’ attacks and their tracks.