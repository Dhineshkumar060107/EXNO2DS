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

```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
df=pd.read_csv("titanic_dataset.csv")
df
```
<img width="1812" height="755" alt="Screenshot 2025-09-13 224146" src="https://github.com/user-attachments/assets/158a52ce-e20b-48c9-90b3-abd7e7b216c5" />

```
df.info()
```

<img width="1776" height="491" alt="Screenshot 2025-09-13 224650" src="https://github.com/user-attachments/assets/29177ba3-31ea-4dc6-852f-b31013f79919" />

```
df.describe()
```

<img width="1745" height="427" alt="Screenshot 2025-09-13 224808" src="https://github.com/user-attachments/assets/e12626b6-b3e6-4fe8-b2ee-8e50918f238e" />

```
df.dtypes

```

<img width="1782" height="617" alt="Screenshot 2025-09-13 225224" src="https://github.com/user-attachments/assets/06979bfa-4ce3-4af2-b0bd-c40d87598b2d" />

```
df.value_counts()

```
<img width="1779" height="649" alt="Screenshot 2025-09-13 225346" src="https://github.com/user-attachments/assets/adf426ed-1ea8-487f-bc30-4f78fd8629b8" />

```

df['Age'].value_counts()

```

<img width="1733" height="649" alt="Screenshot 2025-09-13 225528" src="https://github.com/user-attachments/assets/9744d344-ec53-4442-b955-b50aa814286d" />

```

df.set_index("PassengerId",inplace=True)
df.describe()

```

<img width="1784" height="440" alt="image" src="https://github.com/user-attachments/assets/93fc3840-f727-4693-a4db-1751e3a66a6a" />

```

df.shape

```

<img width="1822" height="121" alt="Screenshot 2025-09-13 225901" src="https://github.com/user-attachments/assets/ae6270be-b2b9-4cc0-a410-b79bf7defb93" />

```

df.nunique()

```

<img width="553" height="587" alt="Screenshot 2025-09-13 225957" src="https://github.com/user-attachments/assets/a548f32d-214b-4bd5-86a2-f6d6047d33b0" />


```

sns.countplot(data=df,x='Survived')

```

<img width="1140" height="630" alt="Screenshot 2025-09-13 230037" src="https://github.com/user-attachments/assets/f54abbed-94b2-4f25-9183-bc05c02fb262" />


```

df.Pclass.unique()


```

<img width="1757" height="90" alt="Screenshot 2025-09-13 230133" src="https://github.com/user-attachments/assets/c029a77c-d92a-4212-aabf-a7e0563d8f3a" />


```

df.rename(columns={'Sex':'Gender'},inplace=True)
df


```

<img width="1737" height="640" alt="Screenshot 2025-09-13 230227" src="https://github.com/user-attachments/assets/3a6bd929-c24a-4109-8f60-cf36471819ba" />


```

sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=7,aspect=.7)


```

<img width="1374" height="834" alt="Screenshot 2025-09-13 230951" src="https://github.com/user-attachments/assets/79b60520-7c47-4790-97b9-2d490b5c415a" />

```

df.boxplot(column="Age",by="Survived")

```

<img width="1371" height="661" alt="Screenshot 2025-09-13 231108" src="https://github.com/user-attachments/assets/d71a055c-e9f4-499a-bbd9-d4db28fc62c1" />


```

sns.scatterplot(x=df["Age"],y=df["Fare"])


```

<img width="1378" height="612" alt="Screenshot 2025-09-13 231151" src="https://github.com/user-attachments/assets/e18e8af0-040f-401b-b4a9-b16c38436017" />


```

fig,ax1=plt.subplots(figsize=(8,5))
plt = sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=df)

```


<img width="1407" height="668" alt="Screenshot 2025-09-13 231242" src="https://github.com/user-attachments/assets/679ea4d4-ea96-433f-9540-247c95b409cf" />


```

plt = sns.boxplot(x='Pclass',y='Age',hue='Gender',data=df)

```


<img width="1390" height="606" alt="Screenshot 2025-09-13 231449" src="https://github.com/user-attachments/assets/c66fa8ab-f3f7-4f11-8774-67c16b548449" />


```

sns.catplot(data=df,col="Survived",x="Gender",hue="Pclass",kind="count")


```

<img width="1396" height="713" alt="Screenshot 2025-09-13 231542" src="https://github.com/user-attachments/assets/fd65db28-69ad-4771-97eb-b8d2ab27d662" />


```

corr=df.select_dtypes(include=np.number).corr()
sns.heatmap(corr,annot=True)


```

<img width="1390" height="620" alt="Screenshot 2025-09-13 231701" src="https://github.com/user-attachments/assets/097daff9-9066-488a-b350-0f9407580326" />























# RESULT
Thus exploratory data analysis on the given data set has been executed successfully
