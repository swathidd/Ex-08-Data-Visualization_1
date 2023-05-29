# Ex-09-Data-Visualization-

## AIM
To Perform Data Visualization on a complex dataset and save the data to a file. 

# Explanation
Data visualization is the graphical representation of information and data. By using visual elements like charts, graphs, and maps, data visualization tools provide an accessible way to see and understand trends, outliers, and patterns in data.

# ALGORITHM
### STEP 1
Read the given Data
### STEP 2
Clean the Data Set using Data Cleaning Process
### STEP 3
Apply Feature generation and selection techniques to all the features of the data set
### STEP 4
Apply data visualization techniques to identify the patterns of the data.


# CODE
```
Data Preprocessing

import seaborn as sns
import pandas as pd
import matplotlib.pyplot as plt
df = sns.load_dataset("tips")
print(df)

df.isnull().sum()

Handling Outliers
plt.figure(figsize=(8,8))
plt.title("Data with Outliers")
df.boxplot()
plt.show()

Removing Outliers
plt.figure(figsize=(8,8))
cols = ['size','tip','total_bill']
Q1 = df[cols].quantile(0.25)
Q3 = df[cols].quantile(0.75)
IQR = Q3 - Q1
df = df[~((df[cols] < (Q1 - 1.5 * IQR)) |(df[cols] > (Q3 + 1.5 * IQR))).any(axis=1)]
plt.title("Dataset after removing outliers")
df.boxplot()
plt.show()

1) Which day of the week has the highest total bill amount?
sns.barplot(x=df['day'], y=df['total_bill'], hue=df['day'])
plt.legend(loc="center")
plt.title("Highest Total Bill Amount by day of the week")
plt.show()

2) What is the average tip amount given by smokers and non-smokers?
sns.boxplot(x=df['smoker'], y=df['tip'], hue=df['smoker'])
plt.title("Average Tip Amount given by smokers and non-smokers")

3) How does the tip percentage vary based on the size of the dining party?
df["tip_percent"] = df["tip"] / df["total_bill"]
sns.scatterplot(x=df['size'],y=df['tip_percent'],data=df)
plt.title("Tip Percentage by Dining Party Size")

4) Which gender tends to leave higher tips?
sns.boxplot(x=df['sex'], y=df['tip'],hue=df['sex'])
plt.title("Tips based on gender")

5) Is there any relationship between the total bill amount and the day of the week?
sns.scatterplot(x=df['day'],y=df['total_bill'],hue=df['day'])
plt.legend(loc="best")
plt.title("Total bill amount by day of the week")

6) How does the distribution of total bill amounts vary across different time periods (lunch vs. dinner)?
sns.histplot(data=df, x="total_bill", hue="time", element="step", stat="density")
plt.title("Distribution of Total Bill Amounts by Time of Day")
plt.show()

7) Which dining party size group tends to have the highest average total bill amount?
sns.barplot(x=df['size'],y=df['total_bill'],hue=df['size'])
plt.title("Average Total Bill Amount by Dining Party Size")
plt.show()

8) What is the distribution of tip amounts for each day of the week?
sns.boxplot(x="day", y="tip", data=df)
plt.title("Tip Amount by Day of Week")
plt.show()

9) How does the tip amount vary based on the type of service (lunch vs. dinner)?
sns.violinplot(x="time", y="tip", data=df)
plt.title("Tip Amount by Time of Day")
plt.show()

10) Is there any correlation between the total bill amount and the tip amount?
sns.scatterplot(x="total_bill", y="tip", data=df)
plt.title("Correlation between Tip Amount and Total Bill Amount")
plt.show()
```

# OUPUT
Data preprocessing

![image](https://github.com/swathidd/Ex-08-Data-Visualization_1/assets/121300272/7391e6f9-1cab-4842-b22c-eba5deffca4f)

![image](https://github.com/swathidd/Ex-08-Data-Visualization_1/assets/121300272/16fae79e-2bd6-4a85-9563-a185d9890b7a)

Handling outliers

![image](https://github.com/swathidd/Ex-08-Data-Visualization_1/assets/121300272/074b0419-ddcf-424a-941f-2c39f7feb693)

Removing outliers

![image](https://github.com/swathidd/Ex-08-Data-Visualization_1/assets/121300272/961e4d92-2e0c-4d00-8f0b-6f9a81dfc483)

1) Which day of the week has the highest total bill amount?

![image](https://github.com/swathidd/Ex-08-Data-Visualization_1/assets/121300272/4866a4e1-86a8-4ce3-bacf-25a14bcf204d)

2) What is the average tip amount given by smokers and non-smokers?

![image](https://github.com/swathidd/Ex-08-Data-Visualization_1/assets/121300272/9ad7eeac-5d10-4dc3-a39f-87f34b6c6b85)

3) How does the tip percentage vary based on the size of the dining party?

![image](https://github.com/swathidd/Ex-08-Data-Visualization_1/assets/121300272/5b07bd25-3480-4f2d-ba03-dc6bd0522fb8)

4) Which gender tends to leave higher tips?

![image](https://github.com/swathidd/Ex-08-Data-Visualization_1/assets/121300272/c389f0d9-ee42-44d1-9cae-1a4970b44222)

5) Is there any relationship between the total bill amount and the day of the week?

 ![image](https://github.com/swathidd/Ex-08-Data-Visualization_1/assets/121300272/815621a1-0f33-4bb9-847d-7604d8187b0a)
 
 6) How does the distribution of total bill amounts vary across different time periods (lunch vs. dinner)?
 
 ![image](https://github.com/swathidd/Ex-08-Data-Visualization_1/assets/121300272/5e1273a4-fad6-4e60-b0ff-d35919833d5e)
 
 7) Which dining party size group tends to have the highest average total bill amount?
 
 ![image](https://github.com/swathidd/Ex-08-Data-Visualization_1/assets/121300272/32e6b2cf-9b5a-4149-9e71-a5a4960456d8)
 
 
8) What is the distribution of tip amounts for each day of the week?

![image](https://github.com/swathidd/Ex-08-Data-Visualization_1/assets/121300272/d4723c11-2614-4477-8aa5-3468e915c31a)

9) How does the tip amount vary based on the type of service (lunch vs. dinner)?

![image](https://github.com/swathidd/Ex-08-Data-Visualization_1/assets/121300272/1587873e-02d0-4abd-91b6-6766d9e65f4d)

10) Is there any correlation between the total bill amount and the tip amount?

![image](https://github.com/swathidd/Ex-08-Data-Visualization_1/assets/121300272/ccfcb302-88e2-4765-9636-3a88b90a5dc3)

# RESULT
Thus the Data Visualization method is performed to the given data and to predict the outcome for the given questions.







