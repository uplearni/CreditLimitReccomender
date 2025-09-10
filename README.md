# Credit Card Limit Reccomender
A machine learning project aimed to  predict an individual credit limit based on various features



## About Dataset
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


## ML Workflow
### 1. Data Cleaning
- the dataset has represented the null values with the #NULL! , replaced was replaced  with nan so we can work with it
- Total 217 null values were found and those rows were dropped
- dropped columns which did not add any value like CLIENTNUM, Attrition_Flag and the Random_Numbers
-  1 duplicate row was found which was then dropped

### 2. EDA (Exploratory Data Analysis) 
#### Univariate Analysis
1)  All the categorical variable like Martial Status , Card Category and payment on time were found unbalanced except the Gender variable as there is only a slight difference
    
2)  Most(39%) of the Customers were found to be earning less than 30k and there are only 8% were found to be earning 111k+.
3)  Average of the Customers were found to be 46 years approximately.
4)  The histogram shows the distribution of credit limit that is positively skewed indicating higher number of customers have lower income and tells the direction of outlier towards the left.
but theres a spike on the right end of the distribution which on further investigations shows that customers with higher income , is male cover the most part of the gold card holders

#### Multivariate Analysis
1) Correlation Matrix for numerial values shows a positive high correlation (0.79)     between Customer_Age and Months_on_book(Number of months as credit card             customer) . the months_on_book increases as the customer_age increase so            multicollineraity present between both variable . hence , will use only one from    both.

   Moreover, a negative moderate correlation (-0.48)  exist between                    Avg_utilization and Credit Limit which shows that with the increase in              avg_utilization ratio the Credit Limit for that customer decreases moderatly        and vice versa.(Inclusion of avg_utilization ratio variable will dpend on it's      significance added to the model)

2) Categorical vs Numerical Values
   - Gender vs Credit Limit : Male customers have higher median credit limit as          compared to females.
   - Martial Status vs Credit Limit : median difference between different martial
     is not huge
   - Income Category vs Credit Limit : the income and credit limit is found to be        directly proportional to each other
   - Card Category vs Credit Limit : median credit limit for gold card is much           higher than the blue card category
   - Pay on time vs Credit Limit : no significant difference between the median
     credit limit for both

### Feature Engineering 

