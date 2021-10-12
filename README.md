# Credit Card Fraud Detection with Python

## About
Created as a showcase project from Bootcamp Data Science Dibimbing. Simulated credit card transaction dataset containing legitimate and fraud transactions, the goal of this project was to build the best predictive model to predict the fraud transaction in order to help prevent fraud transactions in the future.

## Business Understanding
* Created several models that we're able to predict credit card fraud and chose the best model.

## Data Understanding
* This is a simulated credit card transaction dataset containing legitimate and fraud transactions from the duration 1st Jan 2019 - 31st Dec 2020. It covers credit cards of 1000   customers doing transactions with a pool of 800 merchants.
* Source Data: https://www.kaggle.com/kartik2112/fraud-detection
* Data Related to Customer Account Information
	* First name : customer's first name
	* Last name : customer's last name
	* Date of birth : customer's date of birth
	* Trans date trans time : customer's trans date trans time
	* CC number : customer's credit card number
	* Amount : amount of transaction
	* Trans number : transaction number
	* Unix time : unique time number 
* Data Related to Customer Demographic Information
	* Gender : customer's gender 
	* Street : customer's street 
	* Ciy : customer's city
	* State : customer's state
	* Zip : customer's zip
	* Lat : customer's latitude address
	* Long : customer's longitude address
	* City pop : customer's city population
	* Job : customer's job
* Data Related to Merchant Information
	* Merchant : merchant name
	* Category : merchant's category
	* Merchant latitude : merchant's latitude address
	* Merchant longitude : merchant's longitude address
Data Related to Fraud Information
	* Is fraud : transaction clasification wether fraud or not

## Data preparation
* Code Used:
* Python Version: 3.9.7
* Packages: Pandas, Numpy, Matplotlib, Seaborn, Sklearn, and Feature Engine

## Data Cleansing
* Check for each column and find if any column is redundant or useless.
* Check for missing values.
* Check if the data format is already suitable for algorithm.
* Check for value that are not consistent with general common sense.

## Exploratory Data Analysis
### Imbalance of Fraud Transaction Observation 

![image](https://user-images.githubusercontent.com/85482667/136994871-7e08d730-a7cd-4f65-9027-352367684f58.png)

### Gender vs Amount Transaction

![image](https://user-images.githubusercontent.com/85482667/136995431-cb9e1b9c-e50c-4740-b70f-aed2f7cccb08.png)

### Transaction Day of Week

![image](https://user-images.githubusercontent.com/85482667/136995491-44000244-3a4b-477f-a208-f8b70199e90a.png)

### Age Group

![image](https://user-images.githubusercontent.com/85482667/136995641-56554f23-8526-4889-9f52-be4b1544aeca.png)

### Fraud Transaction (% Group) by Category

![image](https://user-images.githubusercontent.com/85482667/136995846-44c04489-ef0d-4efe-98f2-dbd20ea4789a.png)

### Amount Distribution

![image](https://user-images.githubusercontent.com/85482667/136995961-ab935ccf-08b2-46bb-b118-de0785efd438.png)

### Transaction Distribution

![transaction distribution](https://user-images.githubusercontent.com/85482667/136996167-5bde524a-db29-4302-8105-91a9014a6c99.png)

## Modelling
### Preparation
* Drop 20 unused columns, used 500.000 rows only, and create dummy variables.
* Normalize by Robust Scaler which scales the data according to the quantile range.
* Train data size is 80% of observation and Test data size is 20% of observation.
* Oversampling the observation of fraud transaction.
  
  ![image](https://user-images.githubusercontent.com/85482667/136617100-8b1995ee-c119-4388-871b-fc88bd3bf0bf.png)

* Check the correlation matrix.
 
  ![image](https://user-images.githubusercontent.com/85482667/136616839-c3c6fea1-f865-4987-ad6c-4614ce96516c.png)
  
### Training and Evaluation

* Supervised machine learning used that are Ada Boost, Decision Tree, Gaussian Naive Bayes, XGBoost, K Neighbor, Logistic Regression, and Random Forest.

  ![Supervised machine learning](https://user-images.githubusercontent.com/85482667/136396056-ac6ce4d9-427c-423b-b7be-7927e4b620e2.png)
  
#### Best Modelling

* Random Forest is the best supervised machine learning model in this project.
  * Precision = 86%
  * Recall = 74%
  * F1 Score = 79%
  * AUC score = 99%
  * Confussion Matrix;
  
    ![Confussion Matrix](https://user-images.githubusercontent.com/85482667/136394809-0371c7b4-dd4b-4503-9e4b-5c75e53d53bc.png)
* Hyperparameter Tuning in the Random Forest does not affect to increase the F1 score.

  ![Hyperparameter Tuning](https://user-images.githubusercontent.com/85482667/136393750-6842d277-90e9-4111-b802-17d7bcf60c68.png)
* Feature Important in Random Forest.

  ![Feature Important](https://user-images.githubusercontent.com/85482667/136394953-6d01b3b8-5003-4b9f-b1b6-ad4f20f8a44f.png)

## Summary
* The recommended machine learning model for detecting fraudulent transactions is the random forest because it has the best F1 score, RMSE, MAE, and ROC curve analysis.
* Hyperparameter tuning in the random forest does not affect to increase the F1 score.
* The 2 highest feature importances from random forest are amount transaction and transation hour.
