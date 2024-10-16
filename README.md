# Implementation-of-Decision-Tree-Classifier-Model-for-Predicting-Employee-Churn

## AIM:
To write a program to implement the Decision Tree Classifier Model for Predicting Employee Churn.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1.import pandas module and import the required data set.

2.Find the null values and count them.

3.Count number of left values.

4.From sklearn import LabelEncoder to convert string values to numerical values.

5.From sklearn.model_selection import train_test_split.

6.Assign the train dataset and test dataset.

7.From sklearn.tree import DecisionTreeClassifier.

8.Use criteria as entropy.

9.From sklearn import metrics.

10.Find the accuracy of our model and predict the require values.

## Program:
```
/*
Program to implement the Decision Tree Classifier Model for Predicting Employee Churn.
Developed by: DURGA V
RegisterNumber:  212223230052
*/
```
```
import pandas as pd data=pd.read_csv("Employee.csv") data.head()
```

## Output:
![image](https://github.com/user-attachments/assets/405ca5f2-2405-44bd-a944-086a3a754e99)

```
data.info()
```
## OUTPUT:
![image](https://github.com/user-attachments/assets/d01fa150-501a-4dce-8553-7fa9995d4541)

```
data.isnull().sum()
```

## OUTPUT:
![image](https://github.com/user-attachments/assets/abc43f44-aacd-4970-a8d1-8c964a90b0f1)

```
data["left"].value_counts()
```
## OUTPUT:
![image](https://github.com/user-attachments/assets/08c1cfcb-a3ff-46ef-b9b0-17c692877b4a)

```
from sklearn.preprocessing import LabelEncoder 
le=LabelEncoder()
data["salary"]=le.fit_transform(data["salary"])
data.head()
```

## OUTPUT:
![image](https://github.com/user-attachments/assets/c58c9a80-928c-4ffe-b2a8-21d46f77b1fb)

```
x=data[["satisfaction_level", "last_evaluation", "number_project","average_montly_hours", "time_spend_company", "Work_accident", "promotion_last_5years", "salary"]]

x.head()
```
## OUTPUT:
![image](https://github.com/user-attachments/assets/cd7a6f4d-e88d-4318-a73f-0178c80e872a)

```
y=data["left"]
from sklearn.model_selection import train_test_split
x_train, x_test,y_train,y_test=train_test_split(x, y, test_size=0.2, random_state=100)
from sklearn.tree import DecisionTreeClassifier 
dt=DecisionTreeClassifier (criterion="entropy") 
dt.fit(x_train, y_train) 
y_pred=dt.predict(x_test)
from sklearn import metrics
accuracy=metrics.accuracy_score(y_test,y_pred)
accuracy
```
## OUTPUT:
![image](https://github.com/user-attachments/assets/97ea5386-a586-4234-8d94-c17cc83db3e7)

```
dt.predict([[0.5,0.8,9,260,6,0,1,]])
```
## OUTPUT:
![image](https://github.com/user-attachments/assets/9c15209d-afd2-4265-bd91-75f7c4c15861)

## Result:
Thus the program to implement the  Decision Tree Classifier Model for Predicting Employee Churn is written and verified using python programming.
