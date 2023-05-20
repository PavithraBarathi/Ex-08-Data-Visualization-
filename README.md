# Ex-07-Data-Visualization-

## AIM
To Perform Data Visualization on the given dataset and save the data to a file. 

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
OUPUT
Reading the given dataset
## Data Visualization Using Seaborn: ### 1.Line Plot
plt.scatter(df["Region"],df["Profit"], c ="blue")
plt.show()
#7.Boxplot
plt.boxplot(x="Sales",data=df)
plt.show()
Reading the given dataset
![image](https://github.com/PavithraBarathi/Ex-08-Data-Visualization-/assets/96919035/d5154159-0527-48bb-bdcb-901d5e76cd41)

Data Visualization Using Seaborn
1.Line Plot
![image](https://github.com/PavithraBarathi/Ex-08-Data-Visualization-/assets/96919035/3132c3cd-3ba6-4fdf-b726-9500a8d6356c)
![image](https://github.com/PavithraBarathi/Ex-08-Data-Visualization-/assets/96919035/41c53dbb-c274-49e6-9efe-ef4239dd9037)

2.Scatterplot
![image](https://github.com/PavithraBarathi/Ex-08-Data-Visualization-/assets/96919035/3739bb5a-b5f9-4780-8c5b-0b60b83e7f88)
![image](https://github.com/PavithraBarathi/Ex-08-Data-Visualization-/assets/96919035/0d117f17-fa60-4fb3-b11a-8500a34a52f8)

![image](https://github.com/PavithraBarathi/Ex-08-Data-Visualization-/assets/96919035/56640413-06b9-4112-99da-71ace123ba74)

3.Boxplot
![image](https://github.com/PavithraBarathi/Ex-08-Data-Visualization-/assets/96919035/3ab9f561-4adf-4022-ac63-5583fd1e1053)

![image](https://github.com/PavithraBarathi/Ex-08-Data-Visualization-/assets/96919035/0f897220-e9c9-4bcc-9203-dccb66fcf9f8)

Violin Plot
![image](https://github.com/PavithraBarathi/Ex-08-Data-Visualization-/assets/96919035/1efa4e43-2dce-4b94-b128-760f6fd7b274)

5.Barplot
![image](https://github.com/PavithraBarathi/Ex-08-Data-Visualization-/assets/96919035/b9f57675-2211-4236-9cf6-5c372e1f0526)
![image](https://github.com/PavithraBarathi/Ex-08-Data-Visualization-/assets/96919035/f193c2d2-b8f0-426e-b304-f70569bf3441)

pointplot
![image](https://github.com/PavithraBarathi/Ex-08-Data-Visualization-/assets/96919035/6ee0d6e3-0185-45b9-9f24-71878278571e)

Count plot
![image](https://github.com/PavithraBarathi/Ex-08-Data-Visualization-/assets/96919035/cc10b934-15f0-45fd-9154-c524311f982a)

![image](https://github.com/PavithraBarathi/Ex-08-Data-Visualization-/assets/96919035/d55b4f26-63ca-488c-8d78-76827d9e439a)

Histogram
![image](https://github.com/PavithraBarathi/Ex-08-Data-Visualization-/assets/96919035/809aa107-39cb-4d48-9778-460701f0ae88)

DE Plot
![image](https://github.com/PavithraBarathi/Ex-08-Data-Visualization-/assets/96919035/69315522-da77-4f5d-8ef8-bb5e621ee155)

Data Visualization Using Matplotlib:
Plot
![image](https://github.com/PavithraBarathi/Ex-08-Data-Visualization-/assets/96919035/40e2a2c9-8efd-49d6-bcb5-b886f692938e)

Heatmap
![image](https://github.com/PavithraBarathi/Ex-08-Data-Visualization-/assets/96919035/0ed4c3eb-01a5-4d6a-a822-a4f2e2330600)

Piechart
![image](https://github.com/PavithraBarathi/Ex-08-Data-Visualization-/assets/96919035/be18b67d-7a0e-4b84-bf80-e3bb8ae1b19d)

![image](https://github.com/PavithraBarathi/Ex-08-Data-Visualization-/assets/96919035/c3c4d53f-5774-4c48-832d-baef0b7fc140)

Histogram
![image](https://github.com/PavithraBarathi/Ex-08-Data-Visualization-/assets/96919035/489f0b61-46d7-44fa-a774-3642bb3ca005)

Bargraph
![image](https://github.com/PavithraBarathi/Ex-08-Data-Visualization-/assets/96919035/e8b1f1e3-4e0a-4113-992c-0f2b513bf494)

Scatterplot
![image](https://github.com/PavithraBarathi/Ex-08-Data-Visualization-/assets/96919035/29e79e8a-5b55-485e-a3ef-f934635ac4c9)

Boxplot
![image](https://github.com/PavithraBarathi/Ex-08-Data-Visualization-/assets/96919035/f819c9ea-da78-4770-bc23-e9336cf16e5e)

RESULT
Hence,Data Visualization is applied on the complex dataset using libraries like Seaborn and Matplotlib successfully and the data is saved to file
****

