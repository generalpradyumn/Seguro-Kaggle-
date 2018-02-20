# Seguro-Kaggle-
## Problem Statement 

Seguro has been struggling to price their premiums which effects the good drivers by increasing their premiums due to bad drivers. Seguro intends to use predictive modelling to make their premium pricing fair and prevent penalizing good drivers due to the behavior of bad ones. Thus, problem statement is to predict which drivers will file for insurance claim next year.

## Data Description 
In this competition, you will predict the probability that an auto insurance policy holder files a claim.

In the train and test data, features that belong to similar groupings are tagged as such in the feature names (e.g., ind, reg, car, calc). In addition, feature names include the postfix bin to indicate binary features and cat to indicate categorical features. Features without these designations are either continuous or ordinal. Values of -1 indicate that the feature was missing from the observation. The target columns signifies whether or not a claim was filed for that policy holder.

The above data description is taken from Kaggle. This is the only description available and thus it will affect the decision making for preprocessing. 


## Preprocessing 

Following are the data preprocessing techniques that are needed based on the data vizualization :            
    1) Missing value imputation for the rest of the variables.        
    2) Dimensional reduction of variables specially after one hot encoding of categorical variables.       
    3) Outlier treatement of interval level variables.       
    4) Undersampling the dataset to adjust the imbalance in the dataset.   
    
    
    
    
## Modelling 

The missing value imputations were done using mean , median and model based approach using MICE algorithm. 
Both of these imputations techniques are tested together.Parameter tuning is done on select few parameters with grid search and a CV of 5. Model selection criteria was negative log loss due to the data beind imbalanced. The performance of the models on the validation set is given below:


|      Data     |     Model     |    Accuracy |
| ------------- | ------------- |   --------- | 
| Mean and Mode | XG Boost      |     71.94   |
| MICE          | ANN           |     70.45   |


Further Ensemble models were made via stacking by combining ANN and XG boost on both dataset with different techniques of missing value imputations.The results are given below. 


| Data          |    Accuracy |
| ------------- |  -----------| 
| Mean and Mode |     79.15   |
| MICE          |     79.93   |
