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
    
Normalization of the data using min-max normalization (MinMaxScaler) and Z-score normalization. The un-normalised data is having different units for different columns which might produce bias while computing. To reduce this, dataset is normalised.                                                        

Min-Max normalization ranges between [0-1] but a presence of outlier might affect the distribution/values. Thus, it is highly recommended to remove outliers before performing min-max normalization.                                                        
In z-score normalization, the features are scaled such that they have properties similar to normal distribution where mean is zero and standard deviation is one.

### CM2 - Pair Plot/ Scatter Plot / Heat Map

From the correlation graphs we can observe various correlation coefficients amongst the dataset features in the form of scatter plots. Same with the heat map with a particular representing positive correlation and other color showing negative correlation.
Correlation comparison with targets can help us figure out the main features. These features playes major role in figuring out our target variable over the testing dataset.

### CM3 - Data Exploration - Correlation Coefficient (Heat Map), Mean, Variance, Skew, and Kurtosis
We know that <b> variance </b> is a measure of how spread out a data set is. It is calculated as the average squared deviation of each number from the mean of a data set. 

skewness is a measure of the asymmetry of the probability distribution of a real-valued random variable about its mean. The skewness value can be positive, zero, negative, or undefined. Negative skew commonly indicates that the tail is on the left side of the distribution, and positive skew indicates that the tail is on the right.

Kurtosis is a statistical measure that defines how heavily the tails of a distribution differ from the tails of a normal distribution. It identifies whether the tails of a given distribution contain extreme values. The kurtosis of a normal distribution equals 3. Therefore, the excess kurtosis is found using the formula: Excess Kurtosis = Kurtosis – 3. The kurtosis for normal data distrubtion has a value of 3.
The kurtosis is highly tailed for value > 3 and  low tailed for value < 3.

### Question 2: KNN
### CM4 - 
Using KNN classifier, we trained the model using (80%, 20%) sci-kit learn train test split function to get the same split every time we run the program.

By using K-fold Cross Validation (k = 5) avg accuacy for Iris data came as 96.2 %
