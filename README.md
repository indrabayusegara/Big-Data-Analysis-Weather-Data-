# Data-Analysis-(Weather-Data)

###### This project i'm using Python, jupyter Notebook, Anaconda
---

| 1. importing the pandas and DataSet (CSV)
```
import pandas as pd 
data = pd.read_csv("E:\Data Analtys\Weather Data\DataSet_Weather.csv")
```

| 2. Perform data verification first.
### A. Check if the data has been imported correctly
```
data
```
---
![check data head](https://github.com/indrabayusegara/Data-Analysis--Weather-Data-/assets/75928437/f60b064e-958f-43a6-b4fc-2c95777c2e73)
---

### B. First, check the shape of the data
```
data.shape
```
---
![shape](https://github.com/indrabayusegara/Data-Analysis--Weather-Data-/assets/75928437/502c9988-b035-43a5-a02c-761fd935bc1c)
---

### C. columns data 
```
data.columns
```
---
![columns](https://github.com/indrabayusegara/Data-Analysis--Weather-Data-/assets/75928437/cefe0cb5-6fb7-409f-96f8-d252bc0eff93)
---

### D. data.dtypes
```
data.dtypes
```
---
![types data](https://github.com/indrabayusegara/Data-Analysis--Weather-Data-/assets/75928437/fec89908-cd56-4196-92dd-7e22ab3563a3)
---

### E. check values unique in weather columns
```
data['Weather'].unique()
```
---
![unique values in columns](https://github.com/indrabayusegara/Data-Analysis--Weather-Data-/assets/75928437/27e28d28-510e-4951-95cf-71afe89d3f10)
---

### F. checking values in columns 
```
data.nunique()
```
---
![check data unique](https://github.com/indrabayusegara/Data-Analysis--Weather-Data-/assets/75928437/1a3b78ab-b44f-4119-8903-705350152953)
---

### G. Count data in each column
```
data.count()
```
---
![counting data values](https://github.com/indrabayusegara/Data-Analysis--Weather-Data-/assets/75928437/b6aa5ffa-aa3c-4fab-9e9e-96ec47aa31b8)
---

### H. Perform calculations on each value in the 'weather' column.
```
data['Weather'].value_counts()
```
---
![values count in weather](https://github.com/indrabayusegara/Data-Analysis--Weather-Data-/assets/75928437/04730489-37ea-4514-a9bd-277524ff0bf5)
---

# | 3. insight 
## 1. Find all the unique 'Wind Speed' values in data.
```
data['Wind Speed_km/h'].nunique()
```
```
data['Wind Speed_km/h'].unique()
```
---
![1](https://github.com/indrabayusegara/Data-Analysis--Weather-Data-/assets/75928437/31f1e36c-448f-418f-8507-710d69e9e202)
---

## 2. Find the number of times when the 'Weather is exactly Clear'
```
#filtering data
data[data.Weather == 'Clear']
```
---
![2](https://github.com/indrabayusegara/Data-Analysis--Weather-Data-/assets/75928437/047e2fbd-ae12-413e-bfd1-7b90a5726343)
---

## 3. Find the number of times when the 'Wind Speed was exactly 4 Km/h'.
```
data[data['Wind Speed_km/h'] == 4]
```
---
![3](https://github.com/indrabayusegara/Data-Analysis--Weather-Data-/assets/75928437/21f0cf02-007b-4e2a-b562-087dec422236)
---

## 4. Find out all the Null Values in the data.
```
# check data is null or not
data.isnull().sum()
```
```
# check data again to make sure data is not null
data.notnull().sum()
```
---
![4](https://github.com/indrabayusegara/Data-Analysis--Weather-Data-/assets/75928437/e88e4546-2c57-4342-b8eb-6bb8e14803f1)
---
## 5. Rename the column name 'Weather' of the dataframe to 'Weather Condition'
```
## if you dont want the dataframe pop up just use inplace = True  
data.rename(columns = {'Weather':'Weather Condition'})
```
---
![5](https://github.com/indrabayusegara/Data-Analysis--Weather-Data-/assets/75928437/781cd766-579a-40ee-acf8-c1e7ffbfa929)
---

## 6. What is the mean 'Visibility'?
```
data['Visibility_km'].mean()
```
---
![6](https://github.com/indrabayusegara/Data-Analysis--Weather-Data-/assets/75928437/5eaf59e5-b3c0-4ffd-9533-804edda88cff)
---

## 7. What is the standard Deviation of 'Pressure' in this data?
```
data.Press_kPa.std()
```
---
![7](https://github.com/indrabayusegara/Data-Analysis--Weather-Data-/assets/75928437/eb956772-b024-44a7-a443-6900ef5c7b28)
---

## 8. What is the Variance of 'Relative Humidity' in this data?
```
data['Rel Hum_%'].var()
```
---
![8](https://github.com/indrabayusegara/Data-Analysis--Weather-Data-/assets/75928437/527a1c89-f9da-4d35-8ad6-91984bafc7f2)
---

## 9. Find all instances when 'Snow' was recorded.
```
# if you use this ways, not all the values that contains snow will include in the dataset
data[data['Weather Condition'] == 'Snow']
```
---
![9 A](https://github.com/indrabayusegara/Data-Analysis--Weather-Data-/assets/75928437/1cf65e1c-ed01-46df-a9bc-800d02b69a67)
---
```
# so i will use this instead cause it will include all values that have snow in the dataset
data[data['Weather Condition'].str.contains('Snow')]
```
---
![9 B](https://github.com/indrabayusegara/Data-Analysis--Weather-Data-/assets/75928437/f08fedaf-cfac-4968-a3b0-54278a86b56a)
---

## 10. Find all instances when 'Wind Speed is Above 24' and 'Visibility is 25'
```
data[(data['Wind Speed_km/h'] > 24) & (data['Visibility_km'] == 25)]
```
---
![10](https://github.com/indrabayusegara/Data-Analysis--Weather-Data-/assets/75928437/6b3b5e35-c8c1-423b-9e67-3aa80dc3d286)
---

## 11. What is the Mean value of each Column against each 'Weather Condition'?
```
data.groupby('Weather Condition').mean()
```
---
![11 A](https://github.com/indrabayusegara/Data-Analysis--Weather-Data-/assets/75928437/a94218dd-ce9f-4223-a5e2-015b0de240db)
![11 B](https://github.com/indrabayusegara/Data-Analysis--Weather-Data-/assets/75928437/45c16827-ee4a-4bd6-af68-2ad79aff4df2)
![11 C](https://github.com/indrabayusegara/Data-Analysis--Weather-Data-/assets/75928437/3af90ed9-2431-4f9c-bfea-eeb9984c3f96)
---

## 12. What is the minimum & Maximum value of each column against each 'Weather Condition'?
```
data.groupby('Weather Condition').min()
```
---
![12 A](https://github.com/indrabayusegara/Data-Analysis--Weather-Data-/assets/75928437/8860dd7e-9e7b-4210-bb2e-a316551c384f)
![12 B](https://github.com/indrabayusegara/Data-Analysis--Weather-Data-/assets/75928437/327abe26-2e61-45f9-a78a-401024dc6c55)
---

```
data.groupby('Weather Condition').max()
```
---
![12 A1](https://github.com/indrabayusegara/Data-Analysis--Weather-Data-/assets/75928437/9b909497-103d-492e-af5c-b1729cd0e7da)
![12 B1](https://github.com/indrabayusegara/Data-Analysis--Weather-Data-/assets/75928437/9cc04d55-eabe-44b9-bb51-9d94b15111e5)
---

## 13. Show all the records where weather Condition is fog.
```
data[data['Weather Condition'].str.contains('Fog')]
```
---
![13](https://github.com/indrabayusegara/Data-Analysis--Weather-Data-/assets/75928437/ebe66074-8e1f-4b70-97b8-669c617803d8)
---

## 14. Find all Instances when 'Weather is Clear ' or 'Visibility is above 40'.
```
data[(data['Weather Condition'].str.contains('Clear')) | (data['Visibility_km'] > 40)]
```
---
![14](https://github.com/indrabayusegara/Data-Analysis--Weather-Data-/assets/75928437/75e9be45-17ea-4f18-a395-b1d0d8bef3e6)
---

## 15. Find all Instances when : A. 'Weather is clear' and 'Realtive Humidity is Greater than 50' or B. 'Visibility is above 40'
```
data[(data['Weather Condition'].str.contains('Clear')) & (data['Rel Hum_%'] > 50) | (data['Visibility_km'] > 40)]
```
---
![15](https://github.com/indrabayusegara/Data-Analysis--Weather-Data-/assets/75928437/2da03352-0dbf-4f43-9652-69f803f7b41a)
---

## 16. Perform visualization of the processed data.
```
import matplotlib.pyplot as plt
```
> 1. Weather Top 5 Condition Distribution (Bar Chart)
```
bc = data['Weather Condition'].value_counts()
data_chart = bc.head(5)

plt.figure(figsize=(10,7))
plt.bar(data_chart.index, data_chart.values, width=0.5)
plt.title('Weather Top 5 Condition Distribution')
plt.xlabel('Weather Condition')
plt.ylabel('Values')
plt.xticks(rotation=45)  # Rotate label agar lebih mudah dibaca
plt.show()
```
---
![Top 5 Bar chart](https://github.com/indrabayusegara/Data-Analysis--Weather-Data-/assets/75928437/f8227ada-daed-474f-9b97-de3884c39871)
---

> 2.  Weather Top 5 Condition Distribution (Line Chart)
```
plt.figure(figsize=(10,7))
plt.plot(data_chart.index, data_chart.values, marker='o')
plt.title('Weather Top 5 Condition Distribution')
plt.xlabel('Weather Condition')
plt.ylabel('Values')
plt.xticks(rotation=45)  # Rotate label agar lebih mudah dibaca
plt.show()
```
---
![Top 5 line Chart](https://github.com/indrabayusegara/Data-Analysis--Weather-Data-/assets/75928437/7adbef5d-4884-4737-934f-e79e41ecd609)
---

> 3. Weather Top 5 Condition Distribution (Donut Chart)
```
# Menghitung persentase dari setiap nilai dalam data_chart
percentages = data_chart / data_chart.sum() * 100

# Membuat donut chart
plt.figure(figsize=(10, 7))
plt.pie(percentages, labels=data_chart.index, autopct='%1.1f%%', startangle=140, wedgeprops=dict(width=0.4, edgecolor='w'))

# Menambahkan lingkaran di tengah untuk membuatnya menjadi donut chart
centre_circle = plt.Circle((0,0),0.30,fc='white')
fig = plt.gcf()
fig.gca().add_artist(centre_circle)

# Mengatur aspek ratio agar pie chart berbentuk lingkaran
plt.axis('equal')

plt.title('Weather Top 5 Condition Distribution')
plt.show()
```
---
![Top 5 donut chart](https://github.com/indrabayusegara/Data-Analysis--Weather-Data-/assets/75928437/6fd34820-a99d-4a2b-b4af-b197949d6bb8)
---

> 4. Weather Bottom 5 Condition Distribution (Bar Chart)
```
plt.figure(figsize=(10,7))
plt.bar(data_chart2.index, data_chart2.values, width=0.5)
plt.title('Weather Bottom 5 Condition Distribution')
plt.xlabel('Weather Condition')
plt.ylabel('Values')
plt.xticks(rotation=45)  # Rotate label agar lebih mudah dibaca
plt.show()
```
---
![Bottom 5 Bar chart](https://github.com/indrabayusegara/Data-Analysis--Weather-Data-/assets/75928437/142e0050-2b13-47f1-bbbe-e2c4e93d5aeb)
---
