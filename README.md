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

## NAME:ANISH ADAN THIVAKARAN
## REF.NO:25017997
```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns

df=pd.read_csv("titanic_dataset.csv")
df
```
<img width="1295" height="515" alt="Screenshot 2025-10-16 134522" src="https://github.com/user-attachments/assets/0c018aaf-dad9-4ad1-bfdd-856f5327c1a8" />

```
df.info()
```

<img width="414" height="418" alt="Screenshot 2025-10-16 134542" src="https://github.com/user-attachments/assets/17357c44-1600-4737-a103-79870ed51fec" />

```
df.describe()
```

<img width="773" height="369" alt="Screenshot 2025-10-16 134735" src="https://github.com/user-attachments/assets/58498843-0595-4f6d-95eb-6abd6cf31cca" />

```
df.shape
```

<img width="102" height="49" alt="Screenshot 2025-10-16 134747" src="https://github.com/user-attachments/assets/f194e7c2-83a2-406e-9388-9468a8f05814" />

```
df.nunique()
```

<img width="221" height="299" alt="Screenshot 2025-10-16 135402" src="https://github.com/user-attachments/assets/e0041cf5-8e44-41ee-8389-bd00082c01a9" />

```
df["Survived"].value_counts()
```

<img width="252" height="105" alt="Screenshot 2025-10-16 135410" src="https://github.com/user-attachments/assets/f4f930ec-adcd-45ec-9474-361fdca79e3d" />

```
per=(df["Survived"].value_counts()/df.shape[0]*100).round(2)
per
```

<img width="273" height="108" alt="Screenshot 2025-10-16 135419" src="https://github.com/user-attachments/assets/1d2ea093-f9a5-486f-a6c3-b71a407c29bd" />

```
sns.countplot(data=df,x="Survived")
```

<img width="778" height="592" alt="Screenshot 2025-10-16 135439" src="https://github.com/user-attachments/assets/9ce7f279-52b4-4a5b-82a4-48c8207c76d0" />

```
df.Pclass.unique()
```

<img width="172" height="52" alt="Screenshot 2025-10-16 135450" src="https://github.com/user-attachments/assets/10f72ddf-7f32-4df5-b127-1183b9e27e74" />

```
df.rename(columns={"Sex":"Gender"},inplace = True)
df
```

<img width="1310" height="524" alt="Screenshot 2025-10-16 135536" src="https://github.com/user-attachments/assets/8c859ef3-7373-4a8b-a6e9-a44a40ef2706" />

```
sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=5,aspect=.7)
```

<img width="962" height="667" alt="Screenshot 2025-10-16 135611" src="https://github.com/user-attachments/assets/aa7a078f-c6eb-4146-84fb-9f4e9ae5b265" />

```
sns.catplot(x='Survived',hue="Gender",data=df,kind="count")
```

<img width="789" height="665" alt="Screenshot 2025-10-16 135625" src="https://github.com/user-attachments/assets/b9eb4774-2e0f-4df0-a55f-e8aa8d997256" />

```
df.boxplot(column="Age",by="Survived")
```

<img width="746" height="633" alt="Screenshot 2025-10-16 135643" src="https://github.com/user-attachments/assets/74ca39a9-4efb-4af8-aa1f-6a6b3d24e4c3" />

```
sns.scatterplot(x=df["Age"],y=df["Fare"])
```

<img width="792" height="599" alt="Screenshot 2025-10-16 135654" src="https://github.com/user-attachments/assets/05400f84-1878-45e3-9933-133ca9d28642" />

```
sns.jointplot(x="Age",y="Fare",data=df)
```

<img width="773" height="788" alt="Screenshot 2025-10-16 135711" src="https://github.com/user-attachments/assets/8660c2a5-17bc-404f-a92d-31712e3e41d6" />

```
fig,ax1=plt.subplots(figsize=(8,5))
pt=sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=df)
```

<img width="923" height="581" alt="Screenshot 2025-10-16 135733" src="https://github.com/user-attachments/assets/df4ef289-879a-47f9-8f29-8143fa9862bc" />

```
sns.catplot(data=df,col="Survived",x="Gender",hue="Pclass",kind="count")
```

<img width="1367" height="660" alt="Screenshot 2025-10-16 135754" src="https://github.com/user-attachments/assets/b2fdaf71-7c69-40e7-b69c-dd3c3abc86d3" />

```
numeric_df=df.select_dtypes(exclude=[object])
corr=numeric_df.corr()
sns.heatmap(corr,annot=True)
```

<img width="822" height="661" alt="Screenshot 2025-10-16 135808" src="https://github.com/user-attachments/assets/539ae217-4d75-4d36-874d-4871fb49c309" />

```
sns.pairplot(df)
```

<img width="685" height="697" alt="Screenshot 2025-10-16 135859" src="https://github.com/user-attachments/assets/1c9b2aec-d575-468d-a573-aea3c3dc8814" />


# RESULT
Thus the program to implement the data analysis has been successfully completed.
