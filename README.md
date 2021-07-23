# Tanzinia_Water_Wells
## Overview
For this project, I used multiple modeling techniques to predict the functionality of water wells in Tanzania. 

## Business Problem:
4 million people in Tanzania lack access to an improved source of safe water, and 30 million don't have access to improved sanitation. With the data that I was given, I was able to help this problem by predicting whether or not a well was functional, functional needs repair, or non-functional. A good understanding of these water wells can help to improve the maintenance of the wells and help to ensure clean water is available across Tanzania.

## Data:
I used data from the "Pump It Up" competition on the DataDriven website. I combined the training_set_lables.csv and the training_set_values.csv to create my training dataframe. The data frame contains the following information:
-	amount_tsh - Total static head (amount water available to waterpoint)
-	date_recorded - The date the row was entered
-	funder - Who funded the well
-	gps_height - Altitude of the well
-	installer - Organization that installed the well
-	longitude - GPS coordinate
-	latitude - GPS coordinate
-	wpt_name - Name of the waterpoint if there is one
-	num_private –
-	basin - Geographic water basin
-	subvillage - Geographic location
-	region - Geographic location
-	region_code - Geographic location (coded)
-	district_code - Geographic location (coded)
-	lga - Geographic location
-	ward - Geographic location
-	population - Population around the well
-	public_meeting - True/False
-	recorded_by - Group entering this row of data
-	scheme_management - Who operates the waterpoint
-	scheme_name - Who operates the waterpoint
-	permit - If the waterpoint is permitted
-	construction_year - Year the waterpoint was constructed
-	extraction_type - The kind of extraction the waterpoint uses
-	extraction_type_group - The kind of extraction the waterpoint uses
-	extraction_type_class - The kind of extraction the waterpoint uses
-	management - How the waterpoint is managed
-	management_group - How the waterpoint is managed
-	payment - What the water costs
-	payment_type - What the water costs
-	water_quality - The quality of the water
-	quality_group - The quality of the water
-	quantity - The quantity of water
-	quantity_group - The quantity of water
-	source - The source of the water
-	source_type - The source of the water
-	source_class - The source of the water
-	waterpoint_type - The kind of waterpoint
-	waterpoint_type_group - The kind of waterpoint

## Process:
I screened the data and looked at the target, status_group closely. I looked at all of the features that had any impact on the target. No outliers were dropped but null values were replaced with zeros.  I created my baseline model with only seven features. I believed that without any deep data diving, these seven features were the most impactful features. 
I then used an iterative process to create more predictive models to come up with the best accuracy score.
https://github.com/EmmaChoate/Phase_3_Project/blob/main/images/functionality_barchart.png
## Methods and Results:
First, I cleaned the data and made a new data frame called training. This data frame contained 21 columns and 27,813 rows. I started with a baseline model with only 7 features as I explained above. I scaled the numerical data and one hot encoded the categorical columns to increase the predictabilty of my models. I merged the data together to then run through a logistic regression model. The baseline model gave me a training accuracy of 0.6888. 
Once I had my baseline model built I was able to run multiple models from a function that I created. My first, second, and third models were logistic regression models. The first model, the best model, ran as just a logistic regression with no parameters and had a validation accuracy score of 0.785. For the second model, I used SMOTE to fix the class imbalance. Once I fixed the class imbalance my validation accuracy went down from 0.785 to 0.703. For the third model, I used a modeling score function instead of just a modeling function. My model ran produced validation score of 0.702. Model four and five were both run with a random forest classifier to help with the possibility of overfitting. I used a grid search on both models to find the best parameters to use to maximize the accuracy of the model. Model four ran a validation accuracy score of 0.828, but was very overfit therefore even though the score was better, the model was not running well. Model five ran with a validation accuracy of 0.763. 
https://github.com/EmmaChoate/Phase_3_Project/blob/main/images/confusion_matrix.png
## Conclusions:
-	I was able to create a model that can predict the functionality of a well with 78.5% accuracy
-	My model can be used to help the water problem that is effecting millions of people in Tanzania and in other parts of the world that are having similar issues
-	Breaking down the wide range of information given in the dataset, using many different modeling techniques, and being able to relay my findings to help the water crisis 

## For More Information:
Please review my full analysis in my Jupyter Notebook or my presentation 
https://github.com/EmmaChoate/Phase_3_Project/blob/main/water_data.ipynb

For any additional questions, please contact me at emmachoate11@gmail.com
