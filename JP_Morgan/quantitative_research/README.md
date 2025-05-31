# 📊 Quantitative Research - JPMorgan Chase & Co.
## 🔬 Task 1
### 🧠 Task Overview
- An overview of commodity storage contracts
- How to extrapolate data from external feeds to provide granular insights
- Write code that analyzes data to take a date as input and return a price for past and future estimates
### 🎯 Objectives
- Analyze the data to estimate the purchase price of gas at any date in the past and extrapolate it for one year into the future. 
- Your code should take a date as input and return a price estimate.
- Try to visualize the data to find patterns and consider what factors might cause the price of natural gas to vary.
- This can include looking at months of the year for seasonal trends that affect the prices, but market holidays, weekends, and bank holidays need not be accounted for.
### 📁 Dataset
- This data is available for roughly the next 18 months and is combined with historical prices in a time series database.
- Each point in the data set corresponds to the purchase price of natural gas at the end of a month, from 31st October 2020 to 30th September 2024.
### 🛠️ Methodology
- **Preprocessing Data**:
  - Change `Dates` column to datetime format
  - Check empty data
- **Plot Data**:
  - Use line plot to determine the direction of price movements
- **Modeling**:
  - Choose the ARIMA Model
  - Then for the parameters $p$, $d$, $q$, choose 5, 1, 0 in sequence.
  - In the final stage, plotting to find out what the forecast that has been made looks like.
### 📈 Results
![image](https://github.com/user-attachments/assets/029adeb0-b4db-423c-abbf-2f4e00eace7f)
## 🔬 Task 2
### 🧠 Task Overview
- How to write a function that takes particular inputs and gives back the value of a contract
- Create a prototype pricing model that can go through further validation and testing before being put into production
### 🎯 Objectives
- write a function that is able to use the data that was created previously to price the contract.
- The input parameters that should be taken into account for pricing are:
  - Injection dates. 
  - Withdrawal dates.
  - The prices at which the commodity can be purchased/sold on those dates.
  - The rate at which the gas can be injected/withdrawn.
  - The maximum volume that can be stored.
  - Storage costs.
- Write a function that takes these inputs and gives back the value of the contract.
- Assume there is no transport delay and that interest rates are zero. Market holidays, weekends, and bank holidays need not be accounted for.
- Test your code by selecting a few sample inputs.
### 📁 Dataset
- Same as task 1
### 🛠️ Methodology
- Create a function `price_gas_contract` as mentioned previously in the objectives section 
  - The function takes several parameters include:
    - `nat_gas_data` = dataframe natural gas
    - `injection_dates` = the date when the natural gas was injected
    - `withdrawal_dates` = the date when the natural gas was withdrawn
    - `injection_rate` = the rate at which the gas can be injected
    - `withdrawal_rate` = the rate at which the gas can be withdrawn
    - `max_volume` = the maximum volume that can be stored
    - `storage_cost_per_month` = as the name suggests
    - `injection_cost` = injection cost per injection rate
    - `withdrawal_cost` = withdrawal cost per withdrawal rate
    - `transport_cost` = transport cost per trip
  - Then convert dates in the data to datetime
  - Loop through the `injection_dates` and `withdrawal_dates` to:
    - Check if the dates are within the range of the data
    - Get prices on the injection and withdrawal dates
    - Calculate volume of gas injected and withdrawn
    - Calculate costs
    - Update total costs and value include transport costs
    - Calculate the value of the trade
  - Outside the loop, calculate net value of the contract
  - At the end, return `net_value`
- Then call the function with the sample inputs.
### 📈 Results
- The `price_gas_contract` function returns `net_value` properly
- `net_value` interpretation:
  - Positive value indicates potential net profit.
  - Negative value indicates that expenses exceed revenues.
## 🔬 Task 3
### 🧠 Task Overview
- How to choose appropriate independent variables from a data set that will accurately predict the outcome of a chosen dependent variable 
- The importance of using available data to predict customer trends and actions
- Build a model using Python that will estimate the probability of default for a borrower
### 🎯 Objectives
- Build a model that, given details for any loan, will predict the probability that the borrower will default (also known as PD: the probability of default)
- Use the provided data to train a function that will estimate the probability of default for a borrower
- Assuming a recovery rate of 10%, this can be used to give the expected loss on a loan
- Produce a function that can take in the properties of a loan and output the expected loss.
- You can explore any technique ranging from a simple regression or a decision tree to something more advanced. You can also use multiple methods and provide a comparative analysis.
### 📁 Dataset
- The data is in tabular format, with each row providing details of the borrower, including their income, total loans outstanding, and a few other metrics
- There is also a column indicating if the borrower has previously defaulted on a loan.
### 🛠️ Methodology
- Check for missing values
- Split the data & scale the numeric features
- In this task i use RandomForestClassifier
  - Train a RandomForestClassifier
  - Do testing first before applying it to the function
  - Then evaluate the model
- Define the function to estimate the probability of default and calculate the expected loss
### 📈 Results
- `expected_loss` function which returns the expected loss score
