

# BLENDED_LEARNING
# Implementation of Decision Tree Model for Tumor Classification

## AIM:
To implement and evaluate a Decision Tree model to classify tumors as benign or malignant using a dataset of lab test results.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
```
Import the dataset and preprocess the data (handle missing values and encode labels).
Split the dataset into training and testing sets.
Train the Decision Tree model using the training data.
Test the model and evaluate its accuracy for tumor classification.
``` 

## Program:
```
/*
Program to  implement a Decision Tree model for tumor classification.
Developed by: roopika m
RegisterNumber: 212225040348
import pandas as pd
import matplotlib.pyplot as plt
from sklearn.model_selection import train_test_split
from sklearn.tree import DecisionTreeClassifier
from sklearn.metrics import accuracy_score, classification_report,confusion_matrix
import seaborn as sns

data = pd.read_csv('tumor.csv')
print(data.head())
print(data.columns)
  Clump  UnifSize  UnifShape  MargAdh  SingEpiSize  BareNuc  BlandChrom  \
0      5         1          1        1            2        1           3   
1      5         4          4        5            7       10           3   
2      3         1          1        1            2        2           3   
3      6         8          8        1            3        4           3   
4      4         1          1        3            2        1           3   

   NormNucl  Mit  Class  
0         1    1      0  
1         2    1      0  
2         1    1      0  
3         7    1      0  
4         1    1      0  
Index(['Clump', 'UnifSize', 'UnifShape', 'MargAdh', 'SingEpiSize', 'BareNuc',
       'BlandChrom', 'NormNucl', 'Mit', 'Class'],
      dtype='object')
#assigning
X=data.drop(columns=['Class'])
y=data['Class']
​
​
​
#splitting datas
X_test,X_train,y_test,y_train=train_test_split(X,y,test_size=0.3,random_state=42)
​
​
model=DecisionTreeClassifier()
​
​
model.fit(X_train,y_train)
​
​

DecisionTreeClassifier
DecisionTreeClassifier()
​
​
y_pred=model.predict(X_test)
​
accuracy=accuracy_score(y_test,y_pred)
print("Name: roopika m")
print("Register Number: 212225040348")
print("Accuracy:",accuracy)
print("Classification Report:\n",classification_report(y_test,y_pred))
​
Name: roopika m
Register Number: 212225040348
Accuracy: 0.9079497907949791
Classification Report:
               precision    recall  f1-score   support

           0       0.93      0.93      0.93       317
           1       0.86      0.86      0.86       161

    accuracy                           0.91       478
   macro avg       0.90      0.90      0.90       478
weighted avg       0.91      0.91      0.91       478

conf_matrix=confusion_matrix(y_test,y_pred)
sns.heatmap(conf_matrix,annot=True,fmt="d",cmap="Blues")
plt.xlabel=("Predicted")
plt.ylabel=("Actual")
plt.title("Confussion Matrix")
plt.show()
 
*/
```

## Output:
![simple linear regression model for predicting the marks scored](sam.png)

<img width="520" height="433" alt="image" src="https://github.com/user-attachments/assets/f81d099f-5f37-45ac-8e8c-e2d5f0b36c71" />

## Result:
Thus, the Decision Tree model was successfully implemented to classify tumors as benign or malignant, and the model’s performance was evaluated.
