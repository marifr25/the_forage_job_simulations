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
