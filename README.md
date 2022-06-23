# Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee

## AIM:
To write a program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
1. Import pandas as pd and import the required dataset.
2. Calculate the null values in the dataset.
3. Import the LabelEncoder from sklearn.preprocessing
4. Convert the string values to numeric values.
5. Import train_test_split from sklearn.model_selection.
6. Assign the train and test dataset.
7. Import DecisionTreeRegressor from sklearn.tree.
8. Import metrics from sklearn.metrics.
9. Calculate the MeanSquareError.
10. Apply the metrics to the dataset.
11. Predict the output for the required values.

## Program:
/*
Program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee.
Developed by: varunkumar k
RegisterNumber: 21221940173
*/
import pandas as pd

data=pd.read_csv("Salary.csv")

data.head()

data.info()

data.isnull().sum()

from sklearn.preprocessing import LabelEncoder

le=LabelEncoder()

data["Position"]=le.fit_transform(data["Position"])


data.head()

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

r2=metrics.r2_score(y_test,y_pred)

r2

dt.predict([[5,6]])


## Output:
HEAD:


![image](https://user-images.githubusercontent.com/88264052/175308229-67252c4c-07cd-4ed0-8d43-bde5125cd0ce.png)

INFO:

![image](https://user-images.githubusercontent.com/88264052/175308333-768d3410-4c99-4705-8984-329d14944c9d.png)

ISNULL:

![image](https://user-images.githubusercontent.com/88264052/175308436-dc68224e-d3cc-4d5c-b040-a70c6878e54d.png)

LEFT:

![image](https://user-images.githubusercontent.com/88264052/175308554-35ade2da-cdf2-43a5-b858-70ad430f04d9.png)

HEAD USING LABELENCODER:

![image](https://user-images.githubusercontent.com/88264052/175308694-9445d02e-31d0-4677-8c44-283c7b77eb44.png)

ACCURACY:

![image](https://user-images.githubusercontent.com/88264052/175308811-2c619e59-a89a-4532-95a0-0f3cd6ce4ac9.png)

PREDICT:

![image](https://user-images.githubusercontent.com/88264052/175308863-cdf94e15-4f30-4f37-ab21-70065b7d8e73.png)


## Result:
Thus the program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee is written and verified using python programming.
