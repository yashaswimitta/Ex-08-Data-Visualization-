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
Program
Developed by: Yashaswi Mitta
Register no:212221230062

#Reading the given dataset

import pandas as pd
df=pd.read_csv("Superstore.csv",encoding='unicode_escape')

df.head()

#Data Visualization using Seaborn

import seaborn as sns
from matplotlib import pyplot as plt

#1.Line Plot

plt.figure(figsize=(9,6))
sns.lineplot(x="Segment",y="Region",data=df,marker='o')
plt.xticks(rotation = 90)

sns.lineplot(x='Ship Mode',y='Category', hue ="Segment",data=df)

sns.lineplot(x="Category",y="Sales",data=df,marker='o')

#2.Scatterplot

sns.scatterplot(x='Category',y='Sub-Category',data=df)

sns.scatterplot(x='Category', y='Sub-Category', hue ="Segment",data=df)

plt.figure(figsize=(10,7))
sns.scatterplot(x="Region",y="Sales",data=df)
plt.xticks(rotation = 90)

#3.Boxplot

sns.boxplot(x="Sub-Category",y="Discount",data=df)

sns.boxplot( x="Profit", y="Category",data=df)

#4.Violin Plot

sns.violinplot(x="Profit",data=df)

#5.Barplot

sns.barplot(x="Sub-Category",y="Sales",data=df)
plt.xticks(rotation = 90)

sns.barplot(x="Category",y="Sales",data=df)
plt.xticks(rotation = 90)

#6.Pointplot

sns.pointplot(x=df["Quantity"],y=df["Discount"])

#7.Count plot

sns.countplot(x="Category",data=df)

sns.countplot(x="Sub-Category",data=df)

#8.Histogram

sns.histplot(data=df,x ='Ship Mode',hue='Sub-Category')

#9.KDE Plot

sns.kdeplot(x="Profit", data = df,hue='Category')

#Data Visualization Using MatPlotlib

#1.Plot

plt.plot(df['Category'], df['Sales'])
plt.show()

#2.Heatmap

df.corr()
plt.subplots(figsize=(12,7))
sns.heatmap(df.corr(),annot=True)

#3.Piechart

df1=df.groupby(by=["Ship Mode"]).sum()
labels=[]
for i in df1.index:
    labels.append(i)
colors=sns.color_palette("bright")
plt.pie(df1["Sales"],labels=labels,autopct="%0.0f%%")
plt.show()

df3=df.groupby(by=["Category"]).sum()
labels=[]
for i in df3.index:
    labels.append(i) 
plt.figure(figsize=(8,8))
colors = sns.color_palette('pastel')
plt.pie(df3["Profit"],colors = colors,labels=labels, autopct = '%0.0f%%')
plt.show()

#4.Histogram

plt.hist(df["Sub-Category"],facecolor="peru",edgecolor="blue",bins=10)
plt.show()

#5.Bargraph

plt.bar(df.index,df['Category'])
plt.show()

#6.Scatterplot

plt.scatter(df["Region"],df["Profit"], c ="blue")
plt.show() 

#7.Boxplot

plt.boxplot(x="Sales",data=df)
plt.show()
```
### OUPUT
# Reading the given dataset
![image](https://user-images.githubusercontent.com/94505585/171418057-04d07768-2c22-4ede-a470-3c093b0be289.png)
# Data Visualization Using Seaborn
# 1.Line Plot
![image](https://user-images.githubusercontent.com/94505585/171418228-f6169385-68ad-4dbc-9e7c-f8faec3a0401.png)
![image](https://user-images.githubusercontent.com/94505585/171418280-b5b22a26-0c1d-44f1-8543-1138868c6acf.png)
![image](https://user-images.githubusercontent.com/94505585/171418296-797a391e-861c-479e-b806-e0f649d22816.png)
# 2.Scatterplot
![image](https://user-images.githubusercontent.com/94505585/171418802-84299c6a-8e6c-4351-a6e7-aded4f3f4a1c.png)
![image](https://user-images.githubusercontent.com/94505585/171418825-c214e331-01b4-40ee-af11-fb0be2794bc8.png)
![image](https://user-images.githubusercontent.com/94505585/171418847-551cdc5e-2670-43c7-b056-dd71adb05ffc.png)
# 3.Boxplot
![image](https://user-images.githubusercontent.com/94505585/171418923-1c9879ba-3034-46db-83aa-6eb496ab845d.png)
![image](https://user-images.githubusercontent.com/94505585/171419015-924a77aa-3e63-4c6c-a4d7-daee7e92e808.png)
# 4.Violin Plot
![image](https://user-images.githubusercontent.com/94505585/171419104-871db9e9-0c61-4b92-b58a-e3fc29dfc089.png)
# 5.Barplot
![image](https://user-images.githubusercontent.com/94505585/171419175-631506d6-eb56-406c-a74b-d20064b614e0.png)
![image](https://user-images.githubusercontent.com/94505585/171419263-25941d73-ed42-48a0-bb5d-7fa82cd45a3c.png)
# 6.Pointplot
![image](https://user-images.githubusercontent.com/94505585/171419494-fc6c94f8-8bec-456d-90c1-03b669452b8d.png)
# 7.Count plot
![image](https://user-images.githubusercontent.com/94505585/171419583-9059ea45-e19c-45d3-ad48-a50bdab277c2.png)
![image](https://user-images.githubusercontent.com/94505585/171419618-52dcdcfa-b2f8-4c23-a8f1-e767226c1782.png)
# 8.Histogram
![image](https://user-images.githubusercontent.com/94505585/171419764-8bd8b655-1b08-434d-821a-58451e6c7a0b.png)
# 9.KDE Plot
![image](https://user-images.githubusercontent.com/94505585/171419871-c5fecbe1-bf39-4e64-9c1a-b79f08ad545a.png)
# Data Visualization Using Matplotlib:
# 1.Plot
![image](https://user-images.githubusercontent.com/94505585/171420066-bffc0908-c9ef-4583-b133-c5de0b092c06.png)
# 2.Heatmap
![image](https://user-images.githubusercontent.com/94505585/171420198-8b39c62d-0372-4f14-9ab0-de11a1178a29.png)
# 3.Piechart
![image](https://user-images.githubusercontent.com/94505585/171420306-90f3fb72-dc09-4f33-b058-07a068fdbb87.png)
![image](https://user-images.githubusercontent.com/94505585/171420335-c24bef97-a178-48db-b8a6-dc4d3e303395.png)
# 4.Histogram
![image](https://user-images.githubusercontent.com/94505585/171420415-ecbbdbc1-47bd-4127-a880-9ae14cccdd42.png)
# 5.Bargraph
![image](https://user-images.githubusercontent.com/94505585/171420501-e7704f43-b043-41b7-89e9-55abb9d7fde9.png)
# 6.Scatterplot
![image](https://user-images.githubusercontent.com/94505585/171420572-78651028-2155-4ce3-bcc9-f365913a30a4.png)
# 7.Boxplot
![image](https://user-images.githubusercontent.com/94505585/171421342-17c36957-0632-4288-8a32-9ee65b9b3b39.png)
### RESULT:
Hence, Data Visualization is applied on the complex dataset using libraries like Seaborn and Matplotlib successfully and the data is saved to file.

