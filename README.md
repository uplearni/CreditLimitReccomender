# Credit Card Limit Reccomender
A machine learning project aimed to  predict an individual credit limit based on various features



# About Dataset
| Column Name      | Description                        |
|------------------|------------------------------------|
| `CLIENTNUM` | Client ID (not for analysing!) |
| `Attrition_Flag` | Whether or not the customer has left the bank in the last 12 months(**yes or no**) |
| `Customer_Age` | Age of customer in years |
| `Gender` | Gender of customer (**male or female**) |
| `Dependent_count` | Number of dependents (**children**) of the customer |
| `Education_Level` | Education level attained by the customer(**primary, secondary or third level**)|
| `Marital_Status` | **divorced, married/living with partner or single**  |
| `Income_Category` | Yearly income in Euro (to nearest 1k, grouped **<30k, 31-50k,51-70k,71-110k or 111k+**)|
| `Card_Category` | Type of credit card (**Blue or Gold**) |
| `Months_on_book` | Number of months as credit card customer |
| `Credit_Limit` | Credit card limit (Target Variable)|
| `Avg_Utilization_Ratio` | A measure of how often the credit card is used |
| `Pay_on_time` | Whether or not the monthly balance on the credit card paid off( **yes or no**) |
|`Random_numbers`| Random Numbers |

The final Dataset has **7,297** Rows and **11** Columns now


# ML Workflow
## 1. Data Cleaning
- replace the null value `"NULL!"` with the numpy `nan`
- dropped all rows with missing values
- dropped columns which does not add any value like CLIENTNUM ,   Attrition_Flag and the Random_Numbers
-  1 duplicate row was found which was then dropped

## EDA
