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

### REG NO: 212224220019
### NAME: DEEPAK JG
```
import pandas as pd
import numpy as np
import seaborn as sns
import matplotlib.pyplot as plt
dt=pd.read_csv('/content/titanic_dataset (2).csv')
dt
```
![image](https://github.com/user-attachments/assets/aae8ab05-3d37-4427-bde0-8d4a61775d87)
```
dt.info()
```
![image](https://github.com/user-attachments/assets/e13e8529-2dae-4884-91c5-3ac350cfd076)
```
dt.shape
```
![image](https://github.com/user-attachments/assets/406286ec-0c24-45d2-bf0e-db91691f53aa)
```
dt.set_index("PassengerId",inplace=True)
dt
```
![image](https://github.com/user-attachments/assets/d836deea-5647-4530-8a80-36af92dac6b2)
```
dt.describe()
```
![image](https://github.com/user-attachments/assets/9ea20b5c-db06-4e57-8cff-91cf1e242824)
```
dt.nunique()
```
![image](https://github.com/user-attachments/assets/0cd2f50e-d9e0-412c-b049-10d313b990ad)
```
dt["Survived"].value_counts()
```
![image](https://github.com/user-attachments/assets/a1bcbecc-b7f7-4c88-a823-b514b3232738)
```
per=(dt["Survived"].value_counts()/dt.shape[0]*100).round(2)
per
```
![image](https://github.com/user-attachments/assets/9485727f-871f-47db-ac37-0f4d6e3b1eb9)
```
sns.countplot(data=dt,x="Survived")
```
![image](https://github.com/user-attachments/assets/76f1e0e6-c805-4144-8f89-89f709be04bd)
```
dt
```
![image](https://github.com/user-attachments/assets/81b9fd25-6ac6-49fa-a0f6-b3ee3fc07e5e)
```
dt.Pclass.unique()
```
![image](https://github.com/user-attachments/assets/d01c1208-f063-4f14-9dd8-b21879ab69b5)
```
dt.rename(columns={'Sex':'Gender'},inplace=True)
dt
```
![image](https://github.com/user-attachments/assets/6ec6a095-c4df-481d-85d2-556aa9e3abf8)
```
palette_colors = {"male": "blue", "female": "orange"}
sns.catplot(x="Gender",col="Survived",data=dt,kind="count",height=5,aspect=.7,palette=palette_colors)
```
![image](https://github.com/user-attachments/assets/dbbc405a-5370-43fd-84f5-f8ba37fdcee6)
```
sns.catplot(x='Survived',hue="Gender",data=dt,kind="count")
```
![image](https://github.com/user-attachments/assets/65b80ef3-a504-48ff-8120-0fa4c4856c74)
```
dt.boxplot(column='Age',by='Survived')
```
![image](https://github.com/user-attachments/assets/b9d9e7e1-7f05-4e06-9df6-11f320f60d94)
```
sns.scatterplot(x=dt["Age"],y=dt["Fare"])
```
![image](https://github.com/user-attachments/assets/4a933f1e-72a1-4e28-b64f-ce98379638f5)
```
sns.jointplot(x="Age",y="Fare",data=dt)
```
![image](https://github.com/user-attachments/assets/b58ebec9-d9a8-450b-a164-41e4c129312f)
```
import pandas as pd
import numpy as np
import seaborn as sns
import matplotlib.pyplot as plt
dt=pd.read_csv('/content/titanic_dataset (2).csv')
dt
```
![image](https://github.com/user-attachments/assets/676a2bca-5687-4dae-a1eb-42f9f156adb9)
```
fig,ax1=plt.subplots(figsize=(8,5))
pt=sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender",data=dt)
```
![image](https://github.com/user-attachments/assets/2704b699-a3e2-405d-9731-8063d9ebb42b)
```
sns.catplot(data=dt,col="Survived",x="Gender",hue="Pclass",kind="count")
```
![image](https://github.com/user-attachments/assets/3bc78447-6e32-4bf8-80bc-461acec0b255)
```
numerical_features = dt.select_dtypes(include=np.number).columns
corr = dt[numerical_features].corr()

sns.heatmap(corr, annot=True)
```
![image](https://github.com/user-attachments/assets/7a8ef725-3ded-4109-ac54-9decaf36355b)
```
import seaborn as sns
selected_columns = ['Survived', 'Pclass', 'Age']  
sns.pairplot(dt[selected_columns])
```
![image](https://github.com/user-attachments/assets/ab848eba-616c-41d8-b1a6-fe989062dc2c)




# RESULT
            Thus, the Exploratory Data Analysis on the given data set was performed successfully.    Thus, the Exploratory Data Analysis on the given data set was performed successfully.
