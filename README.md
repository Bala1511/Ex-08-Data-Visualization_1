# Ex-08-Data-Visualization-

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
import pandas as pd

import seaborn as sns

import matplotlib.pyplot as plt

df = sns.load_dataset("tips")

df.head()

df.isnull().sum()

plt.figure(figsize=(5,5))

plt.title("Data with Outliers")

df.boxplot()

plt.show()

plt.figure(figsize=(5,5))

cols = ['size','tip','total_bill']

Q1 = df[cols].quantile(0.25)

Q3 = df[cols].quantile(0.75)

IQR = Q3 - Q1

df = df[~((df[cols] < (Q1 - 1.5 * IQR)) |(df[cols] > (Q3 + 1.5 * IQR))).any(axis=1)]

plt.title("Dataset after removing outliers")

df.boxplot()


sns.barplot(x=df['day'], y=df['total_bill'])

plt.title("Highest Total Bill Amount by day")

plt.show()

sns.boxplot(x=df['smoker'], y=df['tip'],hue=df['smoker'])

plt.title("Average Tip Amount given by smokers and non-smokers")

plt.show()

sns.barplot(x=df['sex'], y=df['tip'])

plt.title("Highest tips based on gender")

plt.show()

sns.barplot(x=df['day'],y=df['total_bill'])

plt.title("Total bill amount by day of the week")

plt.show()

sns.histplot(data=df, x="total_bill", hue="time", element="step", stat="density")

plt.title("Distribution of Total Bill Amounts by Time of Day")

plt.show()

sns.violinplot(x="day", y="tip", data=df)

plt.title("Tip Amount by Day of Week")

plt.show()

sns.barplot(x="time", y="tip", data=df)

plt.title("Tip Amount by Time of Day")

plt.show()

sns.scatterplot(x="total_bill", y="tip", data=df)

plt.title("Correlation between Tip Amount and Total Bill Amount")

plt.show()
```

# OUPUT

![ex9 4](https://github.com/Bala1511/Ex-08-Data-Visualization_1/assets/118680410/cc1a8697-f979-43d4-8da9-9ea843cc005f)
![ex9 3](https://github.com/Bala1511/Ex-08-Data-Visualization_1/assets/118680410/bf83840c-2589-4492-9fe1-038274090d5e)
![ex9 2](https://github.com/Bala1511/Ex-08-Data-Visualization_1/assets/118680410/aa7d66ce-1fe5-4fd0-933a-11b885b3de6e)
![ex9 1](https://github.com/Bala1511/Ex-08-Data-Visualization_1/assets/118680410/fcdeaeae-05c0-4445-bac7-2fc289f86803)
![ex9 12](https://github.com/Bala1511/Ex-08-Data-Visualization_1/assets/118680410/f8d52090-012b-40bf-923e-392501522994)
![ex9 11](https://github.com/Bala1511/Ex-08-Data-Visualization_1/assets/118680410/c724b537-7ab2-487e-b4ad-1add570b9556)
![ex9 10](https://github.com/Bala1511/Ex-08-Data-Visualization_1/assets/118680410/4621ff49-1b78-4c83-909c-8f57d39440b9)
![ex9 9](https://github.com/Bala1511/Ex-08-Data-Visualization_1/assets/118680410/b2f50bc1-ccbd-4a4e-8709-9eaa5680671e)
![ex9 8](https://github.com/Bala1511/Ex-08-Data-Visualization_1/assets/118680410/11725490-b39a-47a6-971d-ecb9c14b2eae)
![ex9 7](https://github.com/Bala1511/Ex-08-Data-Visualization_1/assets/118680410/7ef20982-bc61-4c60-9b9e-ec261fab66b8)
![ex9 6](https://github.com/Bala1511/Ex-08-Data-Visualization_1/assets/118680410/dbe885b6-e8e9-4679-80d5-8516751e15d4)

![ex9 5](https://github.com/Bala1511/Ex-08-Data-Visualization_1/assets/118680410/acab0288-f336-4afc-8b3f-dbc5e9e53fbd)

