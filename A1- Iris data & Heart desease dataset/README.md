### 657A Assignment 1 (Spring 2021)

## Dataset 1 - Iris Dataset
It includes different features (attributes) of three Iris flower species (setosa, versicolor, vir- ginica).

## Dataset 2 - Heart Disease Dataset
The dataset contains 14 features (attributes) and 303 instances. The features are multivariate with types - nominal, ordinal, binary, and interval/real ratio data. The classification target is a binary variable (named target) indicating the presence or absence of heart disease using 1 and 0 respectively.

### Question 1: Data Exploration
### CM1 - Data Cleaning and Normalization 
    --> Data cleaning steps used are as follows:
    1) Check for duplicate values
    2) Removing negative values and replacing with NAN 
    3) Checking Outliers (using boxplot and inter quartile range)
Normalization of the data using min-max normalization (MinMaxScaler) and Z-score normalization. The un-normalised data is having different units for different columns which might produce bias while computing. To reduce this, dataset is normalised.                                                          MIn-Max normalization ranges between [0-1] but a presence of outlier might affect the distribution/values. Thus, it is highly recommended to remove outliers before performing min-max normalisation.                                                        
In z-score normalisation, the features are scaled such that they have properties similar to normal distribution where mean is zero and standard deviation is one.
