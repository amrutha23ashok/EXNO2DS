# EXNO2DS
# AIM:
      To perform Exploratory Data Analysis on the given data set.
      
# EXPLANATION:
  The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.
  
# ALGORITHM:
STEP 1: Import the required packages to perform Data Cleansing,Removing Outliers and Exploratory Data Analysis.

STEP 2: Replace the null value using any one of the method from mode,median and mean based on the dataset available.

STEP 3: Use boxplot method to analyze the outliers of the given dataset.

STEP 4: Remove the outliers using Inter Quantile Range method.

STEP 5: Use Countplot method to analyze in a graphical method for categorical data.

STEP 6: Use displot method to represent the univariate distribution of data.

STEP 7: Use cross tabulation method to quantitatively analyze the relationship between multiple variables.

STEP 8: Use heatmap method of representation to show relationships between two variables, one plotted on each axis.

## CODING AND OUTPUT
NAME: AMRUTHA SA
REG NO: 212222110004

       import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
dt=pd.read_csv("/content/titanic.csv")dt
![image](https://github.com/user-attachments/assets/cfe7c9f5-44c4-4d86-bc48-7b9f5529758b)
dt.info()
![image](https://github.com/user-attachments/assets/a0bf5103-5dfd-4ffb-8f9c-0d9834d4cc87)

dt.set_index('PassengerId',inplace=True)
dt.describe()
![image](https://github.com/user-attachments/assets/c994712e-93f2-4d23-8f92-fd94d603d1c8)
dt.shape
![image](https://github.com/user-attachments/assets/9b62cb24-318a-486c-b2ac-1d8447a837bc)
dt.nunique()

![image](https://github.com/user-attachments/assets/bf7d2e7d-2e62-4ff9-8344-068d3ab95a30)

dt["Survived"].value_counts()

![image](https://github.com/user-attachments/assets/6f66409d-1df4-4e42-b55c-605d8c241f44)
per=(dt["Survived"].value_counts()/dt.shape[0]*100).round(2)
per

![image](https://github.com/user-attachments/assets/a9a25c8d-9c88-441f-8104-bc3ccc900bfd)
sns.countplot(data=dt,x="Survived")

![image](https://github.com/user-attachments/assets/8afe6e04-9a79-4a8f-9680-0ee3b74b1d50)
dt.Pclass.unique()

![image](https://github.com/user-attachments/assets/91874c42-3a3d-4c91-ae79-3dd857d98516)
dt.rename(columns={'Sex':'Gender'},inplace=True)
dt

![image](https://github.com/user-attachments/assets/fbe30f4a-613c-441f-979f-314b3553fb3c)
sns.catplot(x="Gender",col="Survived",kind="count",data=dt,height=5,aspect=.7)


![image](https://github.com/user-attachments/assets/54e6c68c-2969-4df1-8fa9-f746f012e21e)
sns.catplot(x='Survived',hue="Gender",data=dt,kind="count")

![image](https://github.com/user-attachments/assets/1534321a-f756-4665-9dbb-b19dfa76ab24)
dt.boxplot(column="Age",by="Survived")

![image](https://github.com/user-attachments/assets/dc96628c-0c17-4bc4-ae30-9a54f9bb8420)
sns.scatterplot(x=dt["Age"],y=dt["Fare"])

![image](https://github.com/user-attachments/assets/33ec2b22-e26b-4556-a197-2f8a598bbe01)
sns.jointplot(x=dt["Age"],y=dt["Fare"],data=dt)

![image](https://github.com/user-attachments/assets/504b4858-9c8c-484a-ac9e-a400c08b3795)

fig,ax1=plt.subplots(figsize=(8,5))
pt=sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=dt)

![image](https://github.com/user-attachments/assets/bb6e7324-aca3-4118-8cc7-1c9672aff62f

sns.catplot(data=dt,col="Survived",x="Gender",hue="Pclass",kind="count")

![image](https://github.com/user-attachments/assets/c7af5d28-ab81-4e70-b806-368e225e02dd)
corr=dt.corr()
sns.heatmap(corr,annot=True)

![image](https://github.com/user-attachments/assets/0923195f-34df-4b1f-b01c-1b0a06e58abd)

sns.pairplot(dt)

![Uploading image.png…]()

# RESULT
        <<INCLUDE YOUR RESULT HERE>>
