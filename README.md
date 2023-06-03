# EXP-9 DATA VISUALIZATION-
# AIM
To Perform Data Visualization on a complex dataset and save the data to a file.

# DATE:
GITHUB LINK:
COLAB LINK:

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
DEVELOPED BY : VISWA PRIYA G
REGISTER NUMBER: 212221220061

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
![1](https://github.com/viswapriyaG/Ex-09-Data-Visualization_/assets/131427787/8de365c6-08e9-4695-98c7-167151f37a3b)

![2](https://github.com/viswapriyaG/Ex-09-Data-Visualization_/assets/131427787/ad1caf98-070f-46fe-a5f1-7bead2e8b3ff)

![3](https://github.com/viswapriyaG/Ex-09-Data-Visualization_/assets/131427787/730c0554-eadc-4ef5-a1ac-f80fcace3a27)

![4](https://github.com/viswapriyaG/Ex-09-Data-Visualization_/assets/131427787/0a830937-7895-4330-a4a6-d8dbe1c27d84)

![5](https://github.com/viswapriyaG/Ex-09-Data-Visualization_/assets/131427787/eee7621d-bf2c-459c-a55f-8438dbc00138)

![6](https://github.com/viswapriyaG/Ex-09-Data-Visualization_/assets/131427787/537a0c74-2ea2-4e04-8f7e-14db7fd02c69)

![7](https://github.com/viswapriyaG/Ex-09-Data-Visualization_/assets/131427787/45ce75c4-fa81-4d49-af98-074560f95689)

![8](https://github.com/viswapriyaG/Ex-09-Data-Visualization_/assets/131427787/500c10b3-3b2a-42f3-a73e-1b1ced94d1c3)

![9](https://github.com/viswapriyaG/Ex-09-Data-Visualization_/assets/131427787/25ac68f5-0ab7-4ec8-9f7c-09c9a15ee7d1)

![10](https://github.com/viswapriyaG/Ex-09-Data-Visualization_/assets/131427787/02035e35-fd87-43f4-a4e9-2f2ca2621ae6)


![11](https://github.com/viswapriyaG/Ex-09-Data-Visualization_/assets/131427787/e4922a86-0852-45b9-8a1d-66e8213ffc1e)

![12](https://github.com/viswapriyaG/Ex-09-Data-Visualization_/assets/131427787/4b0cb253-e71b-4a5e-b3f0-3f450277560b)

![13](https://github.com/viswapriyaG/Ex-09-Data-Visualization_/assets/131427787/dcfb90f3-3906-4fc8-9507-6b0bf548c930)

![14](https://github.com/viswapriyaG/Ex-09-Data-Visualization_/assets/131427787/79a2ea49-58cf-4a59-bfe0-3c302d1bc046)


# RESULT

Thus, Data Visualization is performed on the given dataset and save the data to a file.
