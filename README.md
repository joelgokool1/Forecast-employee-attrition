Introduction 
Predicting employee turnover. Employee churn or turnover is the voluntary or involuntary separation of employees within an organization. The benefit of predicting employee turnover is it is less expensive to engage and keep existing employees then attract and train new ones. 
The goal is to identify the employees that may leave and create a system that assist in staff retention. 
Data Gathering 
The data collected for this analysis comprises both active and inactive NYCT employees in operating titles at the end of each year from 2012 to 2017. 
Describing the Dataset 
The dataset contains the following fields: 
-	Age
-	Gender
-	Ethnic Group 
-	Years of Service
-	Job Title
-	Employee Status

The data provides a snapshot of active and terminated employees at year end. Moreover, each record will have a corresponding employee status of “Active” or “Terminated”. The employee status field will be the dependent variable to be predicted. The others are independent variables which are predictors. 

Cleaning and wrangling data 
The pay statuses for employees are displayed as a single letter. For example, Pay Status “A” translates to “Active” and “T” translates to “Terminated”. Terminations for the purposes of this analysis includes all separations (Dismissals, resignations, etc.).  A column titled “Status” was added to the data to change letter values to either “Active” or “Terminated”.  For coding purposes, column names were separated by “.” and changed to”_”.  Status was changed to “0” for employees that separated from NYCT and “1” for employees that didn’t.  Moreover, gender and ethnic group were converted to numeric values. The date field was modified to a date type, which allows easy segregation of training and testing data.  

Exploratory Data Analysis (EDA)
What proportion of separations are voluntary and involuntary? 
What are the different reasons and proportion of employee separation?

Build the Models for Predicting Separations
The models used to predict employee attrition: 
•	Logistic Regression Model
•	Random Forest 
•	Support Vector Machine
Tuning Parameter 
The model accuracy result is good but it can be improved. To increase the accuracy result, more data could be included. Instead, a model hyper parameter tuning code will be added to the Random Forest Model to improve accuracy result. 
The hyperparameter tuning is setting the algorithm to optimize performance. The hyperparameter include the number of decision trees in the forest and number of features considered by each tree when splitting a node. 

Build the best model 
The accuracy estimate for the models as follows: 
•	Logistic Regression Model is 67%
•	Random Forest with tuning parameter is 87%
•	Support Vector Machine 77%
Radom forest was the most accurate model that was tested. 
Confusion Matrix for Random Forest Model 
The confusion matrix for a Random Forest consists of two tables and rows that reflect the number of false positives, false negatives, true positives and true negatives. In the “Left” row the matrix illustrates the true positive for TA Bus Operators that left the authority.   It appears that the algorithm in the Random Forest classified that 2887 employees accurately left and incorrectly classified that 540 employees would leave but they stayed. In the “Stayed” row the matrix classified 347 employees as staying but they left the Authority and correctly classified 3122 employees as staying. 
Receiver Operating Characteristic (ROC curve) 
The ROC curve is a plot used with binary classifiers of the true positive rate against the false positive rate using various threshold settings. The best possible prediction method would yield a point toward the top left corner of the ROC space. The true positive rate reflects the probability of terminations the predictive models classified correctly. The false positive is the probability of terminations that the model classified as leaving NYCT but really stayed. The best possible predictive method would yield a point in the upper left corner of the ROC space. The point (0, 1) would reflect a perfect classification. The Random Forest model, again, displays the best predictive power (87%) among the other models to predict TA Bus Operator separations. Therefore, the random forest will be used to predict separations. 
