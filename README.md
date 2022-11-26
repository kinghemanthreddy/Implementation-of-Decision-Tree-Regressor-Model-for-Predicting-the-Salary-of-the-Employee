# Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee

## AIM:
To write a program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Import the required libraries.

2. Upload the csv file and read the dataset.

3. Check for any null values using the isnull() function.

4. From sklearn.tree inport DecisionTreeRegressor.

5. Import metrics and calculate the Mean squared error.

6. Apply metrics to the dataset, and predict the output.

## Program:
```
/*
Program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee.
Developed by: HEMANTH KUMAR B
RegisterNumber: 21222044047 
*/
import pandas as pd
data=pd.read_csv("/content/Salary.csv")
data.head()
data.info()
data.isnull().sum()
from sklearn.preprocessing import LabelEncoder
le = LabelEncoder()
data["Position"] = le.fit_transform(data["Position"])
data.head()
x = data[["Position","Level"]]
y = data["Salary"]
from sklearn.model_selection import train_test_split
x_train,x_test,y_train,y_test = train_test_split(x,y,test_size=0.2,random_state=2)
from sklearn.tree import DecisionTreeRegressor
dt = DecisionTreeRegressor()
dt.fit(x_train,y_train)
y_pred = dt.predict(x_test)
from sklearn import metrics
mse = metrics.mean_squared_error(y_test,y_pred)
mse
r2 = metrics.r2_score(y_test,y_pred)
r2
dt.predict([[5,6]])

```

## Output:

![image](https://user-images.githubusercontent.com/116530537/204097628-962d1928-fa1d-4da2-adc7-99b82f0022ea.png)

![image](https://user-images.githubusercontent.com/116530537/204097655-7a987c9e-5e0e-4543-adcc-591c85af181f.png)

![image](https://user-images.githubusercontent.com/116530537/204097688-70ff2a94-1a71-471c-be96-1e764b6be244.png)

![image](https://user-images.githubusercontent.com/116530537/204097718-f7b61f16-f5b2-453e-bdba-d1346327e730.png)

![image](https://user-images.githubusercontent.com/116530537/204097735-948663a3-0c59-46e6-8d95-703a5ba754fb.png)

![image](https://user-images.githubusercontent.com/116530537/204097750-5ea324a2-1c63-45b5-8123-1cef5b7fc817.png)

![image](https://user-images.githubusercontent.com/116530537/204097776-08f5d1e2-9ebf-48ee-9722-d2afea175671.png)


## Result:
Thus the program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee is written and verified using python programming.
