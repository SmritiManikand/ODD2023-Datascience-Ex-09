# Ex-09-Data-Visualization

## AIM
To Perform Data Visualization on a complex dataset and save the data to a file. 

# EXPLANATION
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
import seaborn as sns
import pandas as pd
import matplotlib.pyplot as plt
df=sns.load_dataset("tips")
df

df.isnull().sum()

plt.figure(figsize=(5,5))
plt.title("Data with Outliers")
df.boxplot()

plt.figure(figsize=(5,5))
cols=['size','tip','total_bill']
Q1=df[cols].quantile(0.25)
Q3=df[cols].quantile(0.75)
IQR=Q3-Q1
df=df[~((df[cols]<(Q1-1.5*IQR))|(df[cols]>(Q3+1.5*IQR))).any(axis=1)]
plt.title("Dataset after removing outliers")
df.boxplot()

sns.barplot(x=df['day'],y=df['total_bill'],hue=df['day'])
plt.legend(loc='center')
plt.title("Highest Total Bill Amount by day of the week")

sns.boxplot(x=df['smoker'],y=df['tip'],hue=df['smoker'])
plt.title("Average Tip Amount given by smokers and non-smokers")

df['tip_percent']=df['tip']/df['total_bill']
sns.scatterplot(x=df['size'],y=df['tip_percent'],data=df)
plt.title("Tip Percentage by Dining Party Size")

sns.boxplot(x=df['sex'],y=df['tip'],hue=df['sex'])
plt.title("Tips based on Gender")

sns.scatterplot(x=df['day'],y=df['total_bill'],hue=df['day'])
plt.legend(loc='best')
plt.title("Total bill amount by day of the week")

sns.histplot(data=df,x='total_bill',hue='time',element='step',stat='density')
plt.title("Distribution of Total Bill Amounts by Time of Day")

sns.barplot(x=df['size'],y=df['total_bill'],hue=df['size'])
plt.title("Average Total Bill Amount by Dining Party Size")

sns.boxplot(x='day',y='tip',data=df)
plt.title("Tip Amount by Day of Week")

sns.violinplot(x='time',y='tip',data=df)
plt.title("Tip Amount by Time of Day")

sns.scatterplot(x='total_bill',y='tip',data=df)
plt.title("Correlation between Tip Amount and Total Bill Amount")
```

# OUTPUT

### Tips Dataset
<img width="324" alt="s1" src="https://github.com/SmritiManikand/ODD2023-Datascience-Ex-09/assets/113674204/2db3fc05-62cb-4eec-8db4-f29baac7183a">

### Missing Values
<img width="154" alt="s2" src="https://github.com/SmritiManikand/ODD2023-Datascience-Ex-09/assets/113674204/c6deb567-48ac-4ae7-8408-6226a7118d1e">

### Data with Outliers
<img width="277" alt="s3" src="https://github.com/SmritiManikand/ODD2023-Datascience-Ex-09/assets/113674204/ae70c8a2-bdb0-4f3a-a1f0-8285482540cd">

### Dataset after removing outliers
<img width="289" alt="s4" src="https://github.com/SmritiManikand/ODD2023-Datascience-Ex-09/assets/113674204/6d3bafb9-e980-4fff-9ea3-357eb4f88473">

### Highest Total Bill Amount by day of the week
<img width="370" alt="s5" src="https://github.com/SmritiManikand/ODD2023-Datascience-Ex-09/assets/113674204/28645a45-2c11-4e85-8ce5-c3c3d3a00dc9">

### Average Tip Amount given by smokers and non-smokers
<img width="365" alt="s6" src="https://github.com/SmritiManikand/ODD2023-Datascience-Ex-09/assets/113674204/6a465eba-2a69-4d87-81f1-c37e09e60216">

### Tip Percentage by Dining Party Size
<img width="385" alt="s7" src="https://github.com/SmritiManikand/ODD2023-Datascience-Ex-09/assets/113674204/260d33fc-8617-445b-916e-de5a24d0a5e4">

### Tips based on Gender
<img width="360" alt="s8" src="https://github.com/SmritiManikand/ODD2023-Datascience-Ex-09/assets/113674204/17f224bb-4d13-4bad-9427-07e586308a15">

### Total bill amount by day of the week
<img width="384" alt="s9" src="https://github.com/SmritiManikand/ODD2023-Datascience-Ex-09/assets/113674204/6c0b8b7a-674e-4cc5-ace3-31d2f668c294">

### Distribution of Total Bill Amounts by Time of Day
<img width="377" alt="s10" src="https://github.com/SmritiManikand/ODD2023-Datascience-Ex-09/assets/113674204/a1b89a5c-0f31-42a3-b44f-76c57bc31369">

### Average Total Bill Amount by Dining Party Size
<img width="355" alt="s11" src="https://github.com/SmritiManikand/ODD2023-Datascience-Ex-09/assets/113674204/593a4e3c-4ed2-41df-96ca-fd2dc05717b6">

### Tip Amount by Day of Week
<img width="370" alt="s12" src="https://github.com/SmritiManikand/ODD2023-Datascience-Ex-09/assets/113674204/a7c760bf-ed93-4f40-a155-f9a174c3053c">

### Tip Amount by Time of Day
<img width="359" alt="s13" src="https://github.com/SmritiManikand/ODD2023-Datascience-Ex-09/assets/113674204/e1ef9e60-66b3-4e43-99c4-6e65a14b0924">

### Correlation between Tip Amount and Total Bill Amount
<img width="367" alt="s14" src="https://github.com/SmritiManikand/ODD2023-Datascience-Ex-09/assets/113674204/f871dafd-4380-461e-b81f-ce5d2c7b92ea">

# RESULT
Thus, Data Visualization on a complex dataset and save the data to a file has been performed successfully.
