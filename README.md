# EXP-9 DATA VISUALIZATION
# AIM
To Perform Data Visualization on a complex dataset and save the data to a file.

# Explanation
Data visualization is the graphical representation of information and data. By using visual elements like charts, graphs, and maps, data visualization tools provide an accessible way to see and understand trends, outliers, and patterns in data.

# ALGORITHM
## STEP 1
Read the given Data

## STEP 2
Clean the Data Set using Data Cleaning Process

## STEP 3
Apply Feature generation and selection techniques to all the features of the data set

## STEP 4
Apply data visualization techniques to identify the patterns of the data.

# CODE
DATA PREPROCESSING
```
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt
df = sns.load_dataset("tips")
df.head()
```
```
df.isnull().sum()
```
FINDING OUTLIERS 
```
plt.figure(figsize=(5,5))
plt.title("Data with Outliers")
df.boxplot()
plt.show()
```
REMOVING OUTLIERS
```
plt.figure(figsize=(5,5))
cols = ['size','tip','total_bill']
Q1 = df[cols].quantile(0.25)
Q3 = df[cols].quantile(0.75)
IQR = Q3 - Q1
df = df[~((df[cols] < (Q1 - 1.5 * IQR)) |(df[cols] > (Q3 + 1.5 * IQR))).any(axis=1)]
plt.title("Dataset after removing outliers")
df.boxplot()
plt.show()
```
Which day of the week has the highest total bill amount?
```
sns.barplot(x=df['day'], y=df['total_bill'])
plt.title("Highest Total Bill Amount by day")
plt.show()
```
What is the average tip amount given by smokers and non-smokers?
```
sns.boxplot(x=df['smoker'], y=df['tip'],hue=df['smoker'])
plt.title("Average Tip Amount given by smokers and non-smokers")
plt.show()
```
How does the tip percentage vary based on the size of the dining party?
```
df["tip_percent"] = df["tip"] / df["total_bill"]
sns.barplot(x=df['size'],y=df['tip_percent'],data=df)
plt.title("Tip Percentage by Dining Party Size")
plt.show()
```
Which gender tends to leave higher tips?
```
sns.barplot(x=df['sex'], y=df['tip'])
plt.title("Highest tips based on gender")
plt.show()
```
Is there any relationship between the total bill amount and the day of the week?
```
sns.barplot(x=df['day'],y=df['total_bill'])
plt.title("Total bill amount by day of the week")
plt.show()
```
How does the distribution of total bill amounts vary across different time periods (lunch vs. dinner)?
```
sns.histplot(data=df, x="total_bill", hue="time", element="step", stat="density")
plt.title("Distribution of Total Bill Amounts by Time of Day")
plt.show()
```
Which dining party size group tends to have the highest average total bill amount?
```
sns.barplot(x="size", y="total_bill", data=df)
plt.title("Average Total Bill Amount by Dining Party Size")
plt.show()
```
What is the distribution of tip amounts for each day of the week?
```
sns.boxplot(x="day", y="tip", data=df)
plt.title("Tip Amount by Day of Week")
plt.show()
```
How does the tip amount vary based on the type of service (lunch vs. dinner)?
```
sns.violinplot(x="time", y="tip", data=df)
plt.title("Tip Amount by Time of Day")
plt.show()
```
Is there any correlation between the total bill amount and the tip amount?
```
sns.scatterplot(x="total_bill", y="tip", data=df)
plt.title("Correlation between Tip Amount and Total Bill Amount")
plt.show()
```
# OUPUT

Data preprocessing

![op1](https://github.com/viswapriyaG/Ex-09-Data-Visualization_/assets/131427787/dafb33a0-0119-4c8b-9369-674d5f4711ac)
![op2](https://github.com/viswapriyaG/Ex-09-Data-Visualization_/assets/131427787/442ac7f4-e880-4e8d-9c32-d364e62e6d6d)
 
 
![op3](https://github.com/viswapriyaG/Ex-09-Data-Visualization_/assets/131427787/1541729e-1825-492e-9ac8-07d6f2279bc2)

![op4](https://github.com/viswapriyaG/Ex-09-Data-Visualization_/assets/131427787/3d54e35d-3656-4e87-9941-8461bc7ac021)

Highest Total Bill Amount by day

![op5](https://github.com/viswapriyaG/Ex-09-Data-Visualization_/assets/131427787/d9c695a4-a87c-4793-a5c9-c48a51667bc9)

Average Tip Amount given by smokers and non-smokers

![op6](https://github.com/viswapriyaG/Ex-09-Data-Visualization_/assets/131427787/b49a2c22-ab0c-48f0-9401-69293947c98d)

Tip Percentage by Dining Party Size

![op7](https://github.com/viswapriyaG/Ex-09-Data-Visualization_/assets/131427787/d3f823a4-77c7-4288-81ec-3d4e79b9410a)

Highest tips based on gender

![op8](https://github.com/viswapriyaG/Ex-09-Data-Visualization_/assets/131427787/9b167390-5359-4c86-8fac-b40dc8e5d283)

Total bill amount by day of the week

![op9](https://github.com/viswapriyaG/Ex-09-Data-Visualization_/assets/131427787/16dbfefb-8f2a-4938-8028-729a6f7d2129)

Distribution of Total Bill Amounts by Time of Day

![op10](https://github.com/viswapriyaG/Ex-09-Data-Visualization_/assets/131427787/086eeaf5-d459-41a0-9120-94a6e163c185)

Average Total Bill Amount by Dining Party Size

![op11](https://github.com/viswapriyaG/Ex-09-Data-Visualization_/assets/131427787/2b5ef04b-d3f3-4829-bf7d-d4a435cd1c26)

Tip Amount by Day of Week

![op12](https://github.com/viswapriyaG/Ex-09-Data-Visualization_/assets/131427787/4e48d2dd-d4a2-4e84-809a-dd2d67ffc1a9)

Tip Amount by Time of Day

![op13](https://github.com/viswapriyaG/Ex-09-Data-Visualization_/assets/131427787/4a765bfe-8580-40f2-aa41-23f1d532b02c)

Correlation between Tip Amount and Total Bill Amount

![op14](https://github.com/viswapriyaG/Ex-09-Data-Visualization_/assets/131427787/c10ee0cc-5c39-4ee7-8c73-0a7539df2b6d)

# RESULT

Thus, Data Visualization is performed on the given dataset and save the data to a file.
