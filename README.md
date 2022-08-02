# Vehicle-Insurance


This Dataset is a classification dataset and it is for Vehicle Insurance of a company. It is built based on customers information if the customer will be applying for Vehicle insurance or not.

Building a model to predict whether a customer would be interested in Vehicle Insurance is extremely helpful for the company because it can then accordingly plan its communication strategy to reach out to those customers and optimise its business model and revenue.

## Importing Libraries
The libraries imported include:
1. pandas
2. numpy
3. amtplotlib.pyplot and seaborn
4. sklearn


## Loading the Dataset.
The dataset is in two part, train and test set. the train set was found to have 381109 rows and 12 columns ( including the target column. Test set was found to have 127037 rows and 11 columns.

This task is a classification task, a binary classification to be precise.
By exploring the data, the data is found to have no null cell for both the training and testing dataset. The data has both numerical and categorical features.

## Exploratory Data Analysis (EDA)
The analysis results (Data Visualization) of the data is shown below:

#### Gender
![download](https://user-images.githubusercontent.com/104036386/182400347-056711b6-f69d-4950-89ad-9c762c9788b9.png)

#### Vehicle Age
![download](https://user-images.githubusercontent.com/104036386/182400444-f8d4ce7f-f07c-4199-8500-ac972405f575.png)

#### Vehicle Damage
![download](https://user-images.githubusercontent.com/104036386/182400577-2bbb94e9-2a63-483b-b07d-c1c0caf924d1.png)

That of the numerical data is shown below also.

#### Age Distribution
![download](https://user-images.githubusercontent.com/104036386/182400867-afa45c33-1ad8-4b2f-996a-049848ee07e8.png)

#### Distribution of driver license
![download](https://user-images.githubusercontent.com/104036386/182400998-cac6921f-ab3b-48e1-b1a6-02d961e6bfdd.png)

#### Region Code 
![download](https://user-images.githubusercontent.com/104036386/182401095-22b5f44b-c44b-4db3-81c0-6cf21f4d8253.png)

#### Previously Insured
![download](https://user-images.githubusercontent.com/104036386/182401193-65e8d722-b8ea-4d6f-a7a2-054f5a76c714.png)

#### Annual_ premium
![download](https://user-images.githubusercontent.com/104036386/182401315-2f1c72d7-bb63-4a7a-828a-a9ac49bdc88f.png)

#### Policy sales channel
![download](https://user-images.githubusercontent.com/104036386/182401590-f9a1459c-0f9e-461a-8c11-64dc7220425f.png)

#### Vintage
![download](https://user-images.githubusercontent.com/104036386/182401664-5a3aae93-78ff-4441-9c06-15e435ec149a.png)

#### Response (target feature)
![download](https://user-images.githubusercontent.com/104036386/182401797-4a5e94f9-84d8-4211-bc18-855e3be87c79.png)


### Performing some multivariate analsis

#### Gender and Response
![download](https://user-images.githubusercontent.com/104036386/182401998-9edaed2f-2d14-4996-8d8d-f5bb81161236.png)
With this, it is seen that more male responded to making vehicle insurance

#### Previously Insured
![download](https://user-images.githubusercontent.com/104036386/182402437-c811a6bf-4c36-4e6a-834f-48ac719f7875.png)

The number of males that haven't insured their vehicle are more than that of male. I guess that is why more men are responding to the vehicle insurance than females.

## Data Cleaning
Data cleaning has to do with removing outliers from the data and making it more distributed. 
Boxplots from seaborn were used to do this (note that only numerical features are considered here).
The resut is shown below.
![download](https://user-images.githubusercontent.com/104036386/182403450-268d47b9-161c-4f28-a805-8a4a7b6cfd4d.png)
from the plot, Annual Pemium is found to be skewed and contain lots of outliers.
The outliers in this feature are removed using the quantile range of the feature.

The result of the data after removing the outlier is shown below.
![download](https://user-images.githubusercontent.com/104036386/182404099-880b4f25-37b1-4788-9e46-e637fb54044b.png)

Looking at the result, there are less outliers in the data. 
Hence the data can be said to be cleaned.

### Correlation 
The plot below shows the correlation matrix of the features to the target variable.
![download](https://user-images.githubusercontent.com/104036386/182404552-46f96333-b02f-4711-8862-7114aaf77992.png)

## Preprocessing
Looking at the correlation plot, there are two features that aren't correlating with the response (target feature), then they can be removed from the data (both train and test data).

A validation set was created from the train data to test the model performance. The validation data have 60198 rows.

The categorical features were transformed using OneHotEncoder from sklearn into seperate features.
The numerical features were standardized with standardscaler from sklearn also.

## Modeling
The metrics for the model used are Accuracy_Score and roc_auc_score
#### Random Forest Classifier
This is the first model used. 
The model achieved an accuracy of 87.5% 
The roc_auc_score of the model is 83.7%

#### Decision Tree Classifier 
The model achieved an accuracy of 87.9% 
The roc_auc_score of the model is 84.5%

#### XGBoost Classifier
The model achieved an accuracy of 88.1% 
The roc_auc_score of the model is 85.0%

#### LGBM Classifier
The model achieved an accuracy of 88.1% 
The roc_auc_score of the model is 85.4%

#### Gradient Boosting Classifier
The model achieved an accuracy of 88.1% 
The roc_auc_score of the model is 85.3%

Looking at the model performance, Gradient Boosting is selected as the preferred model.
The prediction of the test set was made and stored in a dataframe for submission.
