### OLA_Ensemble-Learning
#### Objective:
The objective of this business case study is to predict whether a driver will be leaving the company or not based on their attributes like demographics, tenure, and historical data based on the past performance. 

#### Steps performed
1. Loading the dataset of OLA drivers.<br><br>
2. After analyzing the dataset, here are the major key takeaways.<br>
   a. Each driver must report on the first of every month. Each entry in the dataset reflects the basic details about the             driver's performance from the previous month.<br>
   b. Driver_ID is the unique key assigned to each driver.<br>
   c.	The dataset contains the data collected between ‘2019-01-01’ and ‘2020-12-01’.<br><br>
3. Converting all date-related columns to their respective datatypes.
4. Deriving new columns from the existing columns.<br>
      a.	**Negative Total Business Value(Negative TBV)**: Indicates whether the driver generated negative business value for              that month.<br> 
              1: Generated negative business value for that month.<br>
              0: Negative business value was not generated for that month.<br>
      b.  **Zero Total Business Value(Zero TBV):** Indicates whether the driver generated zero business value for that month. <br>
1: Generated zero business value for that month.<br>
0: Zero business value was not generated for that month.<br>
5. Deriving dataset from the original dataset by aggregating data to remove multiple occurrences of the same driver data.
6. Deriving new columns from the derived dataset.<br>
   **Target:** Deriving the Target Variable from the LastWorkingDate Column. <br>
**Joining year:** Extracting year from the Date of Joining column. Maybe it contributes to the likelihood of driver churn.<br>
**Quarterly Rating Increased:** Represented by 1 if the recent quarterly rating has been increased else 0. If the quarterly rating is increased, the likelihood of the driver staying in the company is higher.<br>
**Quarterly Rating Decreased:** Represented by 1 if the recent quarterly rating has been decreased else 0. If the quarterly rating is decreased, the likelihood of the driver leaving the company is higher.<br>
**Income Increased:** Represented by 1 if the monthly income has been increased at least once during his tenure in this company else 0. If the monthly income is increased, the driver gets Job satisfaction which increases the likelihood of the driver staying in the company is higher.<br>
**Grade Increased:** Represented by 1 if the Grade has been increased at least once during his tenure in this company else 0. If the grade is increased, the driver gets Job satisfaction which increases the likelihood of the driver staying in the company is higher.<br>

   


             

