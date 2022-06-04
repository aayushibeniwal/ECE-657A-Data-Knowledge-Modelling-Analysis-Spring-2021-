
## Dataset - DKMA-Covid19-Jan-States
This dataset uses statistics on COVID-19 cases in US states in January of 2021.

The datapoints describe various information about the population and Covid pandemic situation in 50 US States and over each day of the month of January 2021. Each record gives Covid information for that day and demographic data for the whole state as well. Note the demographic data is duplicated for each state since for all days since it doesn’t change that quickly and is based on data from the last census. 

### File Descriptions:
• dkmacovid train.csv - main training data with input features and three binary labels.
• dkmacovid kaggletest features.csv - feature for a test set, with ”Id” column for Kaggle competition.

### Fields Descriptions:
• Day: Date in January 2021 ranging from Jan 2 to Jan 31.
• State ID: Arbitrary ID number for each state, based on alphabetical order. Note there are 51 states since the District of Columbia is also included.
• State: Name of the US State.
• Lat: Latitude for the geographic centre of the state.
• Long : Longitude for the geographic centre of the state.
• Active: Number of active, tracked COVID-19 cases that day in that state.
• Incident Rate: see original data source
• Total Test Results: see original data source
• Case Fatality Ratio: see original data source
• Testing Rate: see original data source
• Resident Population 2021 Census: see original data source • Population Density 2021 Census: see original data source • Density Rank 2021 Census: see original data source
• SexRatio: see original data source


### Label Description:
Each row of this data dataset represents a particular day in January, 2021 in a
particular US State and has three binary labels which are:
• True if is the corresponding count went up from the previous day.
• False if is the corresponding count went down from the previous day.
The three binary labels are:
• Confirmed: Was there a daily increase in the confirmed total cases of COVID-19 in that state on that day?
• Deaths: Was there a daily increase in the number of deaths from COVID-19 in that state on that day?
• Recovered: Was there a daily increase in the number of people recov- ered from COVID-19 in that state on that day?
Note that the labels are fairly unbalanced, so there are quite a few more True cases than there are False cases. Recovered is the most balanced, so it should be easier to train. Deaths is next and Confirmed is the least balanced.

### [CM1] Data Pre-processing and Preparation

#### 1) The dataset that is imported goes though a series of preprocessing steps. It is initially checked for NAN and negative values, there were no NAN values in the dataset. 
#### 2) The 'Resident Population 2020 Census' and 'Population Density 2020 Census' were of type object because there were commas between numbers and thus the data was stored as string type. The commas were removed and these columns were converted to numerical datatype. 
#### 3) The datset is then checked for outliers. The outliers were to be considered based on grouping the dataset by 'State'. This resulted in 25 outliers which were replaced by their upper and lower limit values. 
#### 4) The state and stateId represented the same information so the 'State' column was dropped. We have kept the 'Day' and 'State ID' so that the data may be grouped according to state for any future reference in the following CM's. However, these values will not be used for calculation purposes.
#### 5) We used z-score normalization since the columns would be normally distributed with a specified range of values and most of the classifiers calculate the distance between points for classification. Min Max scaler is not used as presence of outlier might affect its values and since the data is generated over a specific population, there might be chances of outliers.

### [CM2] Representation Learning (Applying PCA LDA)

### [CM3] Decision Tree Classifier

Classified the data using Decision Tree and tuned the hyper-parameters of the classifier using k-fold cross validation and sklearn functions. Evaluated the best value for the number of trees and maximum depth of trees. For decision trees we tried a range of parameters including the following:
• max depth: {3, 5, 10, None}
• None: (grow until leaf contains 2 datapoints)
and plotted the mean accuracy versus the maximum depth. 

### [CM4] Random Forest Classifier

For random forest we tried a range of parameters including the following: 
• number of trees: {5, 10, 50, 150, 200}
• max depth: {3, 5, 10, None}
We also plotted a heat plot. We got (5 * 4) mean accuracies for different values of number of trees and maximum depth.

### [CM5] Gradient Tree Boosting

For Gradient Tree Boosting (on sklearn it is GradientBoostingClassifier):
• number of estimators: {5, 10, 50, 150, 200}
For this, we plotted the mean accuracy versus the number of estimators.
Note: the number of ‘trees’ grown by GBT is n classes × n estimators but this is handled automatically. 

### [CM6] 

