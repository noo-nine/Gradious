# Steps taken for data cleaning operation.
- Data Importing:
   1) Importing the required libraries
   2) Creating a pandas Dataframe as 'health' after importing the dataset
  (Note: "None" condition in dataset are imported as NaN values)
- Handling Duplicates:
   1) Removing 20 duplicates present in the entire DataFrame
- Handling Missing Values: 
   1) Dropping the features that are not useful -- 'Patient_ID'
   2) Replacing the 'None' values in 'Condition' column with 'No Condition' to avoid considering them as missing values
   3) We have some missing values labeled as 'NAN'. hence we replace them by 'NaN'
   4) We got 11 missing values in the whole Dataframe
   5) Instead of dropping those rows, we try to impute them to avoid losing data
- Data Splitting:
   1) Since imputations should be performed seperately on train and test data, we do the 'train_test_split'
   2) Use 'median' to impute numerical columns, 'mode' to impute categorical columns
   3) Checking if the imputations have resulted in any Null values (No Null values)
- Handling Outliers:
   1) Finding the upper and lower bounds using 'IQR method'
   2) Capping the outliers in train and test data using the bounds calculated from train data
- Data Transformation:
   1) Checking the skewness of data, to know whether to transform the data or not
   2) Skweness is close to 0, there is no need to transform
- Data Scaling:
   1) Using 'StandardScaler' to scale data
   2) Fit and transform the train data first, then transform the test data
- Encoding:
   1) Using 'One-Hot Encoding' to encode categorical features, and dropping one of the new features produced from encoding (since it implies the same as rest of the encoded features)
   2) Performing 'One-Hot Encoding' on train and test data seperately