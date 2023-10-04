# ODD2023-Datascience-Ex-04
# Aim
To read the given data and perform the univariate analysis with different types of plots.

# Explanation
Univariate analysis is basically the simplest form to analyze data. Uni means one and this means that the data has only one kind of variable. The major reason for univariate analysis is to use the data to describe. The analysis will take data, summarise it, and then find some pattern in the data.

# Algorithm :
Step1
Read the given data.

Step2
Get the information about the data.

Step3
Remove the null values from the data.

Step4
Mention the datatypes from the data.

Step5
Count the values from the data.

Step6
Do plots like boxplots,countplot,distribution plot,histogram plot.

# Program:
```
import pandas as pd
from scipy import stats
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
```

```
from google.colab import files
uploaded = files.upload()
```
![image](https://github.com/Vaish-1011/ODD2023-Datascience-Ex-04/assets/135130074/6139b26b-0b17-44b1-8d29-a12eb134d26e)

```
df = pd.read_csv('diabetes.csv')
df
```
![image](https://github.com/Vaish-1011/ODD2023-Datascience-Ex-04/assets/135130074/91a4e2a7-59f1-4cd9-a447-78e1d82bcb6d)

```
df.isnull().sum()
```
![image](https://github.com/Vaish-1011/ODD2023-Datascience-Ex-04/assets/135130074/2c4f5cca-cba4-4bb4-b431-17c09bbd0b7e)

```
q1 = df.quantile(0.25)
q3 = df.quantile(0.75)
iqr = q3 - q1
iqr
```
![image](https://github.com/Vaish-1011/ODD2023-Datascience-Ex-04/assets/135130074/05b2323e-0bbf-4d87-b4d0-de642ed5603e)

```
sns.boxplot(df)
```
![image](https://github.com/Vaish-1011/ODD2023-Datascience-Ex-04/assets/135130074/32d2ee2e-1260-4cea-9082-a067b492b0ee)

```
plt.figure(figsize = (14,6))
sns.scatterplot(x = 'Glucose',y='BloodPressure',data = df)
```
![image](https://github.com/Vaish-1011/ODD2023-Datascience-Ex-04/assets/135130074/d260b052-5e60-44ca-837c-15f8baa1d202)

```
sns.scatterplot(x = 'Glucose',y='Insulin',data = df)
```
![image](https://github.com/Vaish-1011/ODD2023-Datascience-Ex-04/assets/135130074/96998dbe-2632-4ba2-a72f-87bda8b8e276)

```
sns.scatterplot(x = 'Glucose',y='DiabetesPedigreeFunction',data = df)
```
![image](https://github.com/Vaish-1011/ODD2023-Datascience-Ex-04/assets/135130074/581d2b36-684d-4705-9833-e51bcba72c83)

```
sns.scatterplot(x = 'Glucose',y='Age',data = df)
```
![image](https://github.com/Vaish-1011/ODD2023-Datascience-Ex-04/assets/135130074/c8db7dbc-85eb-4835-99cc-b282f249f4ee)

```
sns.heatmap(df.corr(),annot = True)
```
![image](https://github.com/Vaish-1011/ODD2023-Datascience-Ex-04/assets/135130074/bf593e69-c06e-485e-b3c6-692059a72ed3)

```
from google.colab import files
uploaded = files.upload()
```
![image](https://github.com/Vaish-1011/ODD2023-Datascience-Ex-04/assets/135130074/2880fc29-ce10-453c-b9f3-329b09c71c20)

```
df = pd.read_csv('employeesal.csv')
df
```
![image](https://github.com/Vaish-1011/ODD2023-Datascience-Ex-04/assets/135130074/8bf617ed-58e0-45d6-9938-79756fbeba78)

```
df.isnull().sum()
```
![image](https://github.com/Vaish-1011/ODD2023-Datascience-Ex-04/assets/135130074/59c4b545-12f3-4387-b80e-c220924f80f7)

```
numeric_cols = df.select_dtypes(include=[int, float])
q1 = numeric_cols.quantile(0.25);
q3 = numeric_cols.quantile(0.75);
iqr = q3 - q1
iqr
```
![image](https://github.com/Vaish-1011/ODD2023-Datascience-Ex-04/assets/135130074/46adb4d3-129c-4dbb-9881-17a9e1153bea)

```
low = q1 - 1.5*iqr
high = q1 + 1.5*iqr
numeric_cols = numeric_cols[(numeric_cols >= low) & (numeric_cols <= high)]
numeric_cols.dropna()
```
![image](https://github.com/Vaish-1011/ODD2023-Datascience-Ex-04/assets/135130074/c07bb422-e0e0-428e-a2b0-f914c678a521)

```
sns.boxplot(numeric_cols)
```
![image](https://github.com/Vaish-1011/ODD2023-Datascience-Ex-04/assets/135130074/ce75095d-4f3d-4904-b46f-d453583bd386)

```
sns.scatterplot(x = 'Salary',y='Age',data = numeric_cols)
```
![image](https://github.com/Vaish-1011/ODD2023-Datascience-Ex-04/assets/135130074/64bacbc5-db78-41d8-92d7-13291ef4e84e)

```
sns.scatterplot(x = 'Experience_Years',y='Salary',data = numeric_cols)
```
![image](https://github.com/Vaish-1011/ODD2023-Datascience-Ex-04/assets/135130074/c48ed4e9-c694-48e8-9d7a-3c229c6bac19)

```
sns.scatterplot(x = 'Experience_Years',y='Age',data = numeric_cols)
```
![image](https://github.com/Vaish-1011/ODD2023-Datascience-Ex-04/assets/135130074/143a2b8e-f961-4264-893b-e924865e6e54)

```
sns.heatmap(numeric_cols.corr(),annot = True)
```
![image](https://github.com/Vaish-1011/ODD2023-Datascience-Ex-04/assets/135130074/b1098c01-57dd-4305-af99-0fb088126539)

```
from google.colab import files
uploaded = files.upload()
```
![image](https://github.com/Vaish-1011/ODD2023-Datascience-Ex-04/assets/135130074/71136f65-5139-438a-966c-58dfdd274801)

```
df = pd.read_csv('SuperStore.csv')
df
```
![image](https://github.com/Vaish-1011/ODD2023-Datascience-Ex-04/assets/135130074/a69b33ef-377a-4161-8952-30b60ed31f21)

```
df.isnull().sum()
```
![image](https://github.com/Vaish-1011/ODD2023-Datascience-Ex-04/assets/135130074/2e117a97-c529-47c7-876d-b14947c0f1d1)

```
df.dropna()
```
![image](https://github.com/Vaish-1011/ODD2023-Datascience-Ex-04/assets/135130074/579a9aeb-623b-4193-afb2-339f73ad14c2)


```
df.dtypes
```
![image](https://github.com/Vaish-1011/ODD2023-Datascience-Ex-04/assets/135130074/dc898982-cf9a-494d-94b5-84359824774d)

```
numeric_cols = df.select_dtypes(include=[int,float])
q1 = numeric_cols.quantile(0.25);
q3 = numeric_cols.quantile(0.75);
iqr = q3 - q1
iqr
```
![image](https://github.com/Vaish-1011/ODD2023-Datascience-Ex-04/assets/135130074/3cd56a79-58fe-442d-9a76-e9cab138f7b2)

```
low = q1 - 1.5*iqr
high = q1 + 1.5*iqr
numeric_cols = numeric_cols[(numeric_cols >= low) & (numeric_cols <= high)]
```

```
sns.boxplot(numeric_cols)
```
![image](https://github.com/Vaish-1011/ODD2023-Datascience-Ex-04/assets/135130074/3d1e51a9-1d7b-4722-a11a-be68e9b020ba)

```
sns.heatmap(numeric_cols.corr(),annot = True)
```
![image](https://github.com/Vaish-1011/ODD2023-Datascience-Ex-04/assets/135130074/a82e88bc-70d2-4b91-b091-e2c41f9e13f6)

# RESULT:
Thus we have read the given data and performed the univariate analysis with different types of plots.



