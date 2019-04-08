# Edelweiss-Foreclosure-probability
Edelweiss Hackathon-Foreclosure Probability Prediction

3 Datasets are provide
1. Customer Demographics Data
2. Customer Transactions Data
3. List of Foreclosed Customers
4. Email interaction of Customer with Customer Representative

Pre-Processing
Customer Data
1. All values are NA for PROFESSION and OCCUPATION; More than 76% values are NA for POSITION and PRE_JOBYEARS
2. Mode imputation for SEX, MARITAL_STATUS, NO_OF_DEPENDENT, AGE
3. Qualification NA values are imputed using Gross Income for KNN.

Pre-Processing
Agreement Data
1.Checking for null values
2.Mode imputation for City where NA's replaced with Mumbai
3.Mode imputation for DPD with NA's replaced with 0
4.Checking for cases where completed tenor equals 0 and in such cases the previous data column is made equal to current data column
5.Categorical features like City and Product are Label encoded
6.Due to loss of information the final dataset used only Agreement data
7.In-order to deal with the challenge of row multiplicity we decided to convert the agreement data to a single row by using the latest information with regards to MOB feature
8.Finally, to generate more features Interest_start_date, Authorization_date and Last_receipt_date were converted to year, month and day features

Algorithm used:
1. SVM (rbf Kernel)-- 91%
2. Random Forest --98%
3. Finally XGBoost gave highest accuracy--98.84%

GridSearchCV is used for parameter tuning.
Learning Rate 0.01,n_estimators-5000,max_depth-3,min_child_weight-1,gamma-0.3,subsample-0.85,colsample_bytree-0.85,reg_aplha-0.7,nthread-4

Validation Accuracy achieved-99.17%

Secured Rank-13


