
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
```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
df=pd.read_csv("/content/titanic_dataset.csv")
df
```
![image](https://github.com/23008859/EXNO2DS/assets/139117979/c2077c3e-3774-4ffc-abe9-3939a5afe5b5)
```
df.info()
```
![image](https://github.com/23008859/EXNO2DS/assets/139117979/8be94def-613f-4fc3-b4a5-660cdc3e03bb)
```
df.shape
```
![Screenshot 2024-03-09 112050](https://github.com/23008859/EXNO2DS/assets/139117979/d1721974-6202-4b42-81d5-440ef33070a3)
```
import pandas as pd
df=pd.read_csv("/content/titanic_dataset.csv")
df.set_index("PassengerId",inplace=True)
print(df.set_index)
```
![image](https://github.com/23008859/EXNO2DS/assets/139117979/f7ac11fc-b7f5-4c31-b2a4-1fcceb5f0e50)
```
df.describe()
```
![image](https://github.com/23008859/EXNO2DS/assets/139117979/6d034efb-449f-446d-b54f-a0768e9d46b2)
```
df.nunique()
```
![image](https://github.com/23008859/EXNO2DS/assets/139117979/b3a42231-fee5-4e90-aa4b-c05b9fe2cb2c)
```
df["Survived"].value_counts()
```
![image](https://github.com/23008859/EXNO2DS/assets/139117979/a49c37e3-3233-482d-ae36-ae6a27994793)
```
per=(df["Survived"].value_counts()/df.shape[0]*100).round(2)
per
```
![image](https://github.com/23008859/EXNO2DS/assets/139117979/a9b90b96-0568-42e3-8875-2365a856253a)
```
sns.countplot(data=df,x="Survived")
```
![image](https://github.com/23008859/EXNO2DS/assets/139117979/5ebe484d-1594-48d3-8992-81b24de88a1f)
```
df
```
![image](https://github.com/23008859/EXNO2DS/assets/139117979/55625cf5-dfc1-446a-87b8-ae20ea9f21e5)
```
df.Pclass.unique()
```
![image](https://github.com/23008859/EXNO2DS/assets/139117979/7748dad4-5d07-4943-8498-0a70f6742d5e)
```

df.rename(columns={'sex':'Gender'},inplace=True)
df
```
![image](https://github.com/23008859/EXNO2DS/assets/139117979/ff5a1f17-b436-43b9-b0bf-996523aed43e)
```
import seaborn as sns
df=pd.read_csv("/content/titanic_dataset.csv")
sns.catplot(x="Sex",col='Survived',kind="count",data=df,height=5, aspect=.7)
```
![Screenshot 2024-03-09 113220](https://github.com/23008859/EXNO2DS/assets/139117979/7ed3a5dc-57f6-439a-955a-6e09d86240eb)
```
sns.catplot(x='Survived',hue='Sex',data=df,kind='count')
```
![Screenshot 2024-03-09 113331](https://github.com/23008859/EXNO2DS/assets/139117979/7db95063-8453-40ec-b76e-97647f9bfac5)
```
df.boxplot(column='Age',by="Survived")
```

![Screenshot 2024-03-09 113509](https://github.com/23008859/EXNO2DS/assets/139117979/22858c6a-7b0f-4228-b91d-82c99580fe80)
```
sns.scatterplot(x=df['Age'],y=df["Fare"])
```

![Screenshot 2024-03-09 113603](https://github.com/23008859/EXNO2DS/assets/139117979/d425461d-1d6e-49e1-8199-cf7b3ebb4800)
```
import matplotlib.pyplot as plt
fig,ax1=plt.subplots(figsize=(8,5))
pt=sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Sex',data=df)
```

![Screenshot 2024-03-09 113711](https://github.com/23008859/EXNO2DS/assets/139117979/eec75898-0a1b-4314-aa1b-efce61cd39bb)

```
sns.catplot(data=df,col='Survived',x='Sex',hue='Pclass',kind='count')
```

![Screenshot 2024-03-09 113842](https://github.com/23008859/EXNO2DS/assets/139117979/3ca298cf-a932-42b0-8060-18d8169311e9)
```
import seaborn as sns
corr=df.corr()
sns.heatmap(corr,annot=True)
```

![Screenshot 2024-03-09 113948](https://github.com/23008859/EXNO2DS/assets/139117979/5d711030-0018-47d6-a66a-33bd465adad9)
```
sns.pairplot(df)
```

![Screenshot 2024-03-09 114123](https://github.com/23008859/EXNO2DS/assets/139117979/7d58bbd8-c86a-40c6-b2f8-da498592b7cf)

# RESULT
                Code are sucessfully executed.
