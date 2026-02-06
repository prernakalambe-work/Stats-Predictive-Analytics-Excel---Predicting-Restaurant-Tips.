# Predicting-Restaurant-Tips (Stats, Predictive-Analytics, Excel)
### Submitted By: Prerna M. Kalambe

<br> <br>

> This image shows the final Linear Regression output generated using Excel’s Analysis ToolPak, including coefficients, intercept, and statistical significance.

<img width="1919" height="779" alt="Linear regression output in Excel showing coefficients, intercept, and model statistics
" src="https://github.com/user-attachments/assets/a9853c5e-1cfd-4b6e-bc7f-426854acbb09" />

<br> <br>

> This image demonstrates how the regression coefficients were used to calculate predicted tip values using a mathematical formula in Excel.

<img width="1754" height="731" alt="Excel formula used to calculate predicted restaurant tip values using regression coefficients
" src="https://github.com/user-attachments/assets/2799283b-238a-464e-9d1a-da467e05920e" />

<br> <br>

> This image shows the calculation of Root Mean Square Error (RMSE) used to evaluate the accuracy of the predictive model.

<img width="1919" height="763" alt="RMSE calculation in Excel using squared error and average formula
" src="https://github.com/user-attachments/assets/0c1ae704-45d1-4785-92b1-0a8bfe1d8312" />

<br> <br> 

## 1. Objective

The objective of this project is to build a predictive analytics model in Microsoft Excel that estimates restaurant tip amounts based on customer and billing attributes.

### The project aims to:
• Clean and prepare the dataset
<br> • Identify independent and dependent variables
<br> • Encode categorical variables for analysis
<br> • Perform correlation analysis
<br> • Build a Linear Regression model using Excel
<br> • Predict tip values
<br> • Evaluate model performance using RMSE
<br> • Generate a final mathematical prediction model

<br> <br> 

## 2. Dataset Description

The [restaurant tips dataset](https://github.com/prernakalambe-work/Stats-Predictive-Analytics-Excel---Predicting-Restaurant-Tips./blob/630862ea481bd23ba4b0bd719997f75210ec22ed/1715854881_restaurant_tips_dataset.xlsx) contains records of restaurant customers and their tipping behavior.

### Variables included:

• sex – Gender of the customer
<br> • smoker – Whether the customer is a smoker
<br> • day – Day of restaurant visit
<br> • time – Lunch or Dinner
<br> • size – Number of people dining
<br> • total_bill – Total bill amount (USD)
<br> • tip – Tip amount (USD)

<br> The dataset was used to analyze relationships between customer behavior and tipping patterns.

<br> <br> 

## 3. Data Cleaning

### 3.1 Missing Values

<br> Checked for missing values using:
<br> Go To Special → Blanks
 
<br> • No missing values were found in the dataset
<br>

> This screenshot verifies that the dataset was checked for missing values using Excel’s Go To Special feature.

<img width="927" height="719" alt="Excel sheet showing missing value check using Go To Special blanks
" src="https://github.com/user-attachments/assets/4d0012f5-896c-4e09-87c7-30108fdafbfa" />

<br>

### 3.2 Duplicate Removal
<br> Duplicates were checked using:
<br> Data → Remove Duplicates

<br> • No critical duplicates were present after cleaning
<br>

> This image shows the process of identifying and removing duplicate records from the dataset.

<img width="925" height="725" alt="Removing duplicate records in Excel using Remove Duplicates tool
" src="https://github.com/user-attachments/assets/2bdd042e-edc4-4e80-b078-760e33c5b1c2" />

<br> <br> 

## 4. Identifying Independent & Dependent Variables

### Dependent Variable (Y):
• Tip (numeric output variable)
<br> 

### Independent Variables (X):

• sex
<br> • smoker
<br> • day
<br> • time
<br> • size
<br> • total_bill

<br> These variables represent customer attributes and billing information influencing tip behavior.

<br> <br> 

## 5. Predictive Problem Identification

### Since the target variable (tip) is a continuous numeric value, this project is classified as:

Regression Problem (Linear Regression)

<br> <br> 

## 6. Encoding Categorical Variables

### Categorical variables were converted into numeric format using IF conditions in Excel:

<br> • sex_enc
<br> `=IF(A2="Male",1,0)`
<br> 
<br> • smoker_enc
<br> `=IF(C2="Yes",1,0)`
<br> 
<br> • time_enc
<br> `=IF(E2="Dinner",1,0)`
<br> 
<br> • day_enc
<br> `=IF(D2="Thur",1,IF(D2="Fri",2,IF(D2="Sat",3,4)))`
<br> 
<br> Encoded variables were placed alongside original columns.
<br> Numeric variables (size, total_bill) were used directly.

<br> <br> 

## 7. Correlation Analysis

Correlation between independent variables and tip was calculated using:
<br> `=CORREL(variable_range, tip_range)`

<br> This helped identify variables with stronger linear relationships to the target variable.
<br>

> This screenshot displays the correlation calculation between independent variables and the tip amount to identify influential predictors.

<img width="905" height="784" alt="Correlation analysis in Excel between independent variables and tip amount
" src="https://github.com/user-attachments/assets/d24b5fd8-4e32-47b6-9526-494444bf1b34" />

<br> <br> 

## 8. Building the Regression Model (Using Analysis ToolPak)

### Steps followed:
• Enabled Analysis ToolPak
<br> • Data → Data Analysis → Regression
<br> 
### Regression Inputs:

• Y Input Range: Tip
<br> • X Input Range:
<br> sex_enc, smoker_enc, day_enc, time_enc, size, total_bill
<br> 
### Options selected:
- Labels
<br> - Residuals
<br> 
Excel generated coefficients, intercept, residuals, and statistical significance.

<br> <br> 

## 9. Mathematical Prediction Model

### The final regression equation follows this structure:

**Predicted Tip = Intercept
<br> 
<br> (Coef_sex × sex_enc)
<br> 
<br> (Coef_smoker × smoker_enc)
<br> 
<br> (Coef_day × day_enc)
<br> 
<br> (Coef_time × time_enc)
<br> 
<br> (Coef_size × size)
<br> 
<br> (Coef_total_bill × total_bill)**
<br> 
<br> Actual coefficient values were taken directly from Excel’s regression output.
<br> <br> 
## 10. Predicted Tip Calculation

A new column (predicted_tip) was created using the regression formula.
<br> 
<br> Example Excel formula:
<br>  
`=Intercept + coef1*sex_enc + coef2*smoker_enc + coef3*day_enc + 
 coef4*time_enc + coef5*size + coef6*total_bill`

<br> 
<br> The formula was applied across all rows to generate predictions.
<br> <br> 

## 11. RMSE Calculation

<br> Model performance was evaluated using Root Mean Square Error (RMSE).
<br> 
### Steps:
• Error - `= Actual Tip – Predicted Tip`
<br> • Squared Error - `= Error²`
<br> • RMSE - `=SQRT(AVERAGE(Squared Error Range))`
<br> 
Lower RMSE indicates better prediction accuracy.
<br><br>  
## 12. Project Outcome

### This project resulted in:
**• A cleaned and structured dataset
<br> • Encoded categorical variables
<br> • A complete linear regression model
<br> • A mathematical equation for tip prediction
<br> • Actual vs Predicted tip comparison
<br> • RMSE-based model evaluation**
<br>
The model can now be used to predict restaurant tip amounts based on customer and billing inputs.

<br><br>  

## 13. Tools Used

• Microsoft Excel
<br> • IF conditions
<br> • CORREL function
<br> • Analysis ToolPak – Regression
<br> • Data Cleaning tools
<br> • Statistical evaluation (RMSE)
<br> 
<br> 

### Portfolio Note
This project demonstrates statistical thinking, predictive modeling, and Excel-based analytics, making it suitable for data analyst and business analyst portfolios.





