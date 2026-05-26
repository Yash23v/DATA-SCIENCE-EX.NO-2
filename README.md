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
<img width="1220" height="420" alt="image" src="https://github.com/user-attachments/assets/7216785e-99af-4e46-b353-054d01ea3615" />

```
print(df.info())
print()
print(df.dtypes)
```
<img width="394" height="682" alt="Screenshot 2026-05-26 093041" src="https://github.com/user-attachments/assets/65eb4af5-12f1-49bf-a2d9-8275375302fd" />

```
df.value_counts()
```
<img width="1148" height="499" alt="image" src="https://github.com/user-attachments/assets/0514f900-2be6-4302-9b6b-169d23892cd4" />

```
df['Age'].value_counts()
```
<img width="627" height="479" alt="image" src="https://github.com/user-attachments/assets/dd91a7d8-3a89-4d3d-84da-130ee5fb6d97" />

```
df.set_index("PassengerId",inplace=True)
print(df.describe(),'\n',df.shape)
```
<img width="699" height="204" alt="image" src="https://github.com/user-attachments/assets/785c1ed6-5f96-44ed-9b06-f98124d9e5bb" />

```
df.nunique()
```
<img width="153" height="254" alt="image" src="https://github.com/user-attachments/assets/22ee3c5d-4e36-4035-b0e1-6704cd6acd86" />

```
sns.countplot(data=df,x='Survived')
df.Pclass.unique()
```
<img width="688" height="536" alt="image" src="https://github.com/user-attachments/assets/21a099c9-902b-40bc-b1c6-4c6b5f5e19a7" />

```
df.rename(columns={'Sex':'Gender'},inplace=True)
df
```
<img width="1110" height="442" alt="image" src="https://github.com/user-attachments/assets/355ef8fc-c733-4985-b34f-6d6b8a50ce72" />

```
sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=7,aspect=.7)
```
<img width="752" height="549" alt="image" src="https://github.com/user-attachments/assets/85fde7bd-b56b-402d-8689-307d7d69fc38" />

```
df.boxplot(column="Age",by="Survived")
```
<img width="678" height="563" alt="Screenshot 2026-05-26 094046" src="https://github.com/user-attachments/assets/67411858-c099-4859-8de6-78e985ee0008" />

```
sns.scatterplot(x=df["Age"],y=df["Fare"])
```
<img width="694" height="541" alt="image" src="https://github.com/user-attachments/assets/f5c61d09-cdbb-4bf2-8786-bc47ee8fe095" />

```
fig,ax1=plt.subplots(figsize=(8,5))
plt = sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=df)
```
<img width="808" height="519" alt="image" src="https://github.com/user-attachments/assets/0f0d31de-4ef8-4039-b370-a179baa20a9a" />

```
plt = sns.boxplot(x='Pclass',y='Age',hue='Gender',data=df)
```
<img width="653" height="494" alt="image" src="https://github.com/user-attachments/assets/ae3161a8-b45b-4e04-9ce1-4905e99d23a0" />

```
sns.catplot(data=df,col="Survived",x="Gender",hue="Pclass",kind="count")
```
<img width="1147" height="572" alt="image" src="https://github.com/user-attachments/assets/265bba57-9c48-424d-876c-204a9903ab7f" />

```
sns.pairplot(data=df)
```
<img width="512" height="522" alt="image" src="https://github.com/user-attachments/assets/109b57a2-de7d-4ef3-bdf7-ba2fe26b5ef6" />

```
corr1 = df.select_dtypes(include=['number']).corr()
sns.heatmap(corr1, annot=True)
```
<img width="616" height="528" alt="image" src="https://github.com/user-attachments/assets/d60bda27-07f4-4507-8f8c-c311202d39a8" />

# RESULT
Thus, Exploratory Data Analysis on the given data set is implemented successfully.
