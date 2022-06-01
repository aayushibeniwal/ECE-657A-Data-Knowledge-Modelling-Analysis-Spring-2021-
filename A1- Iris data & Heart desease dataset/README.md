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
### CM4 - KNN Classifier
Using KNN classifier on Iris Data, we trained the model using (80%, 20%) sci-kit learn train test split function to get the same split every time we run the program.

By using K-fold Cross Validation (k = 5) avg accuracy for Iris data came as <b> 96.2 % </b>

By using (90%, 10%) split for Heart disease dataset fitted the KNN classifier for a range of k values (1 to 25) and stored accuracy scores across all the k values for comparison. Highest <b> 78% </b> accuracy was achieved at k = 9 for Heart Disease data.

### CM5 - Plotting and Visualizing results
Accuracy vs K plotting for Iris Dataset


Accuracy vs K plotting for Heart Disease dataset


### CM6 - accuracy, AUC, f-score of kNN classifier

In the Iris dataset,the accuracy increases with the increasing value of k and reaches its highest value at k=5. It remains stable between k = [5,10] after which it starts decreasing. The increasing value of K reduces the accuracy since the model is unable to differentiate between the classes. Thus, based on these observations k=5 is selected as the best fitting parameter.

In Heart disease dataset, the accuracy increases with the increasing value of K and achieves max value at k=11. However, this is the case of overfitting due to limited values of validation set and cannot be considered. Thus, K=14 is selected after testing the data.

### CM7 - Improved model using Weighted KNN
Used Weighted KNN with (default, manhatten, euclidean) to see their effects on improving accuracy.
