# Implementation-of-SVM-For-Spam-Mail-Detection

## AIM:
To write a program to implement the SVM For Spam Mail Detection.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Detect File Encoding: Use chardet to determine the dataset's encoding.
2. Load Data: Read the dataset with pandas.read_csv using the detected encoding.
3. Inspect Data: Check dataset structure with .info() and missing values with .isnull().sum().
4. Split Data: Extract text (x) and labels (y) and split into training and test sets using train_test_split.
5. Convert Text to Numerical Data: Use CountVectorizer to transform text into a sparse matrix.
6. Train SVM Model: Fit an SVC model on the training data.
7. Predict Labels: Predict test labels using the trained SVM model.
8. Evaluate Model: Calculate and display accuracy with metrics.accuracy_score.

## Program:
Program to implement the SVM For Spam Mail Detection..
Developed by: ADITHYA M
RegisterNumber:  212224230008
```
import chardet
file='spam.csv'
with open(file, 'rb') as rawdata:
    result = chardet.detect (rawdata.read(100000))
result
```
```
import pandas as pd
data=pd.read_csv('spam.csv', encoding='Windows-1252')
data.info()
```
```
data.isnull().sum()
```
```
x=data["v1"].values
y=data["v2"].values
```
```
from sklearn.model_selection import train_test_split
x_train, x_test, y_train,y_test=train_test_split(x,y,test_size=0.2, random_state=0)
from sklearn.feature_extraction.text import CountVectorizer
cv = CountVectorizer()
x_train=cv.fit_transform(x_train)
x_test=cv.transform(x_test)
```
```
from sklearn.svm import SVC
svc=SVC()
svc.fit(x_train, y_train)
y_pred=svc.predict(x_test)
y_pred
```
```
from sklearn import metrics
accuracy=metrics.accuracy_score(y_test,y_pred)
accuracy
```

## Output:
<img width="886" height="44" alt="image" src="https://github.com/user-attachments/assets/3e0cbe62-5681-4e57-926a-1bd9a9eaedab" />

<img width="548" height="275" alt="image" src="https://github.com/user-attachments/assets/b6934344-11fe-4430-8783-776a785ee766" />

<img width="426" height="295" alt="image" src="https://github.com/user-attachments/assets/04279297-06c6-4d44-8248-2746776e79e8" />

<img width="775" height="40" alt="image" src="https://github.com/user-attachments/assets/4d5d21ae-70d0-4d59-b562-6251cc55092e" />

<img width="344" height="28" alt="image" src="https://github.com/user-attachments/assets/030e6202-e902-418a-ad47-f2cd3329ebf6" />



## Result:
Thus the program to implement the SVM For Spam Mail Detection is written and verified using python programming.
