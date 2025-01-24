### OLA_Ensemble-Learning
#### Objective:
The objective of this business case study is to predict whether a driver will be leaving the company or not based on their attributes like demographics, tenure, and historical data based on the past performance. 

#### Steps performed
1. Loading the dataset of OLA drivers.<br><br>
2. After analyzing the dataset, here are the major key takeaways.<br>
   a. Each driver must report on the first of every month. Each entry in the dataset reflects the basic details about the             driver's performance from the previous month.<br>
   b. Driver_ID is the unique key assigned to each driver.<br>
   c.	The dataset contains the data collected between ‘2019-01-01’ and ‘2020-12-01’.<br><br>
3. Converting all date-related columns to their respective datatypes.<br><br>
4. Deriving new columns from the existing columns.<br>
      a.	**Negative Total Business Value(Negative TBV)**: Indicates whether the driver generated negative business value for              that month.<br> 
              1: Generated negative business value for that month.<br>
              0: Negative business value was not generated for that month.<br>
      b.  **Zero Total Business Value(Zero TBV):** Indicates whether the driver generated zero business value for that month. <br>
1: Generated zero business value for that month.<br>
0: Zero business value was not generated for that month.<br><br>
5. Deriving dataset from the original dataset by aggregating data to remove multiple occurrences of the same driver data.<br><br>
6. Deriving new columns from the derived dataset.<br>
   **Target:** Deriving the Target Variable from the LastWorkingDate Column. <br>
**Joining year:** Extracting year from the Date of Joining column. Maybe it contributes to the likelihood of driver churn.<br>
**Quarterly Rating Increased:** Represented by 1 if the recent quarterly rating has been increased else 0. If the quarterly rating is increased, the likelihood of the driver staying in the company is higher.<br>
**Quarterly Rating Decreased:** Represented by 1 if the recent quarterly rating has been decreased else 0. If the quarterly rating is decreased, the likelihood of the driver leaving the company is higher.<br>
**Income Increased:** Represented by 1 if the monthly income has been increased at least once during his tenure in this company else 0. If the monthly income is increased, the driver gets Job satisfaction which increases the likelihood of the driver staying in the company is higher.<br>
**Grade Increased:** Represented by 1 if the Grade has been increased at least once during his tenure in this company else 0. If the grade is increased, the driver gets Job satisfaction which increases the likelihood of the driver staying in the company is higher.<br>
**Observations:** <br>
Income and Grade are positively correlated. As the grade spikes up, the income boosts.<br><br>
7. Performing univariate Analysis of Categorical Columns.<br>
Segregating Categorical columns and numerical columns and performing univariate analysis.<br>
After visualizing count plots of the categorical variables and analyzing the statistical summary, it is evident that a few columns are not contributing to the Target Variable. Those are<br>
      a. City<br>
      b. Gender<br>
      c. Education<br>
      d. Negative TBV<br>
These columns are dropped off from the derived dataset.<br><br>
8. Performing uniivariate Analysis of Numerical Columns.<br>
   Plotted histograms for numerical features. The numerical features are right-skewed. Quantile transformation is used to mitigate the skewness. 
   Hypothesis tests like Mann-Whitney U are used to determine the association between each numerical feature and Target variable. <br>
   **Observations:** <br>
      a.	Drivers with high monthly incomes tend to remain with the company.<br>
      b.	Most of the drivers generating substantial business value are also not leaving the company.<br>
      c.	The second point applies to the TBV/income feature as well.<br>
      d.	There are no significant findings related to the Age feature. Although the precision is low, we can suggest that younger drivers may be more prone to attrition.<br><br>
9. **Outliers treatment**<br>
      Boxplot is used to detect the outliers in the data. Since outliers are not so extreme, they are not removed from the data. However, the numerical features are                transformed to reduce the impact of outliers on the model performance. <br><br>
10. **Class Imbalance treatment**<br>
      The imbalance in the dataset can lead to biased models that perform poorly on the minority class, which is often the class of interest. Given that the dataset is             imbalanced, it is preferable to use appropriate techniques for oversampling or undersampling. In this case, since we have very little data, we will use the                   oversampling technique.<br>
      Before applying oversampling, we will remove irrelevant columns, specifically Driver_ID, MMM-YY, LastWorkingDate, and DateofJoining. We will then evaluate the                performance of the model both before and after using the oversampling technique. It was observed that the model performed well without oversampling, as the majority          class is the primary focus in this case study.<br><br>
#### Data Preprocessing: 
1. Splitting the data into train and test data sets.<br>
2. Standardization of features <br><br>
**Model Implementation:** <br>
Following the same sequence for all the models built<br>
   a. Model implementation<br>
   b. Predicting for test data and obtaining scores for both train and test data.<br>
   c. Hyperparameter tuning for best parameters<br>
   d. Training the model with the best parameters.<br>
   e. Repeat step-2<br>
   f. Classification Report and confusion matrix for test data.<br>
   g. ROC AUC implementation.<br>
   f. Feature Importance.<br><br>
**Models built**:<br>
      a. Decision tree classifier<br>
      b. Random forest tree<br>
      c. Gradient boosting decision tree<br>
      d. XGBoost<br>
      e. LightGBM<br><br>
Lastly, providing insights and recommendations after analyzing the performance of the models.
 








   


             

