# Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee

## AIM:
To write a program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
### 1. Initialize the dataset using the pandas library
### 2. Have a look at the dataset using df.head() and df.info() to make any changes
### 3. Convert the string columns to numerical values to fit in to the regressor 
### 4. Split the dataset to train and test and then fit that data to the DecisionTreeRegressor
### 5. Evaluate the model on metrics like mse and r2 score
### 6. Predict values of Salary using the trained model

## Program:
```
/*
Program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee.
Developed by: Arikatla Hari Veera Prasad
RegisterNumber:  212223240014
*/
```
```
import pandas as pd
data=pd.read_csv('Salary.csv')
data.head()
```

## Output:
![image](https://github.com/Hariveeraprasad-2006/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/145049988/3095f90f-3a28-4730-91df-d8be5c3d4cbe)
```
data.info()
```
## Output:
![image](https://github.com/Hariveeraprasad-2006/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/145049988/09068145-0f7e-4fc2-9f68-29e6bde76be6)
```
data.isnull().sum()
```
## Output:
![image](https://github.com/Hariveeraprasad-2006/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/145049988/a9c77355-3f46-4ab8-992f-9e9cfbecc00f)
```
from sklearn.preprocessing import LabelEncoder
le=LabelEncoder()
data['Position']=le.fit_transform(data['Position'])
data.head()
```
## Output:
![image](https://github.com/Hariveeraprasad-2006/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/145049988/59e69b0c-b371-442e-b029-9104eee3411d)
```
x=data[["Position","Level"]]
y=data["Salary"]
from sklearn.model_selection import train_test_split
x_train,x_test,y_train,y_test=train_test_split(x,y,test_size=0.2,random_state=2)

from sklearn.tree import DecisionTreeRegressor
dt=DecisionTreeRegressor()
dt.fit(x_train,y_train)
y_pred=dt.predict(x_test)
from sklearn import metrics
mse=metrics.mean_squared_error(y_test,y_pred)
mse
```
## Output:
![image](https://github.com/Hariveeraprasad-2006/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/145049988/a2d02000-6471-4510-bb59-416695a95897)
```
r2=metrics.r2_score(y_test,y_pred)
r2
```
## Output:
![image](https://github.com/Hariveeraprasad-2006/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/145049988/846b03a7-21fe-4b03-b151-d1a2cf4d424f)
```
dt.predict([[5,6]])
```
## Output:
![image](https://github.com/Hariveeraprasad-2006/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/145049988/b4405c14-f881-4716-8786-ab7a07967306)

## Result:
Thus the program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee is written and verified using python programming.
