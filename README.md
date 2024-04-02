# Implementation-of-Decision-Tree-Classifier-Model-for-Predicting-Employee-Churn

## AIM:
To write a program to implement the Decision Tree Classifier Model for Predicting Employee Churn.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm:
1. import pandas module and import the required data set.
2. Find the null values and count them.
3. Count number of left values.
4. From sklearn import LabelEncoder to convert string values to numerical values.
5. From sklearn.model_selection import train_test_split.
6. Assign the train dataset and test dataset.
7. From sklearn.tree import DecisionTreeClassifier.
8. Use criteria as entropy.
9. From sklearn import metrics.
10.Find the accuracy of our model and predict the require values.

## Program:
```
/*
Program to implement the Decision Tree Classifier Model for Predicting Employee Churn.
Developed by: PRAJAN P
RegisterNumber: 212223240121
*/
import pandas as pd
data = pd.read_csv("Employee.csv")
data.head()
data.info()

data.isnull().sum()

data["left"].value_counts

from sklearn.preprocessing import LabelEncoder
le= LabelEncoder()
data["salary"]=le.fit_transform(data["salary"])
data.head()

x= data[["satisfaction_level","last_evaluation","number_project","average_montly_hours","time_spend_company","Work_accident","promotion_last_5years","salary"]]

x.head()
y=data["left"]

from sklearn.model_selection import train_test_split
x_train,x_test,y_train,y_test = train_test_split(x,y,test_size=0.2,random_state = 100)

from sklearn.tree import DecisionTreeClassifier
dt = DecisionTreeClassifier(criterion="entropy")
dt.fit(x_train,y_train)

y_pred = dt.predict(x_test)
from sklearn import metrics

accuracy = metrics.accuracy_score(y_test,y_pred)
accuracy

dt.predict([[0.5,0.8,9,260,6,0,1,2]])
```

## Output:

Data.head():


![238635663-fe7e2a52-b584-4686-8027-b1cb8ec0c136](https://github.com/PRAJAN-23013995/Implementation-of-Decision-Tree-Classifier-Model-for-Predicting-Employee-Churn/assets/150313345/39bc96d3-7849-43cf-9b3a-b335732c4945)

Data.info():


![238635901-e91f5083-b124-4bde-a531-a3a8f8f469cb](https://github.com/PRAJAN-23013995/Implementation-of-Decision-Tree-Classifier-Model-for-Predicting-Employee-Churn/assets/150313345/0099abc2-b7d7-43c4-8882-c1712e3f8db9)

isnull() and sum():

![238636120-13765c70-5817-4e4a-875b-191ff0b3a687](https://github.com/PRAJAN-23013995/Implementation-of-Decision-Tree-Classifier-Model-for-Predicting-Employee-Churn/assets/150313345/a00790ae-1912-4cc7-bfa2-8db2f84de4bb)

Data value coounts():

![238637334-01560d37-b412-446d-8648-705b39e7a7ea](https://github.com/PRAJAN-23013995/Implementation-of-Decision-Tree-Classifier-Model-for-Predicting-Employee-Churn/assets/150313345/2f34571f-8df7-481c-a673-33882ff47448)


Data.head() for salary:

![238637043-459eba34-9924-4f09-a9fe-c3db2cb4b230](https://github.com/PRAJAN-23013995/Implementation-of-Decision-Tree-Classifier-Model-for-Predicting-Employee-Churn/assets/150313345/a4061a5f-74cd-4e27-9db6-676faff2e479)


X.head():

![238637477-9c7e8ea2-4992-464f-9c3e-8ade02113569](https://github.com/PRAJAN-23013995/Implementation-of-Decision-Tree-Classifier-Model-for-Predicting-Employee-Churn/assets/150313345/8af4f144-4c71-4a1d-9062-fc00bdc9d92d)

Accuracy value:

![238637597-7dd3fc29-5591-415e-b43c-bb3d9bcb392c](https://github.com/PRAJAN-23013995/Implementation-of-Decision-Tree-Classifier-Model-for-Predicting-Employee-Churn/assets/150313345/c19d39e5-03a2-4061-b857-0a4ad49e3dfb)

Data prediction:

![238637742-9a5343bc-3a31-4ab6-9e9d-96bad64d5909](https://github.com/PRAJAN-23013995/Implementation-of-Decision-Tree-Classifier-Model-for-Predicting-Employee-Churn/assets/150313345/d8abcbd7-60be-49a6-a21c-bdde1770a9ed)


## Result:
Thus the program to implement the  Decision Tree Classifier Model for Predicting Employee Churn is written and verified using python programming.
