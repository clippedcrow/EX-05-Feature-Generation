# EX-05-Feature-Generation


## AIM
To read the given data and perform Feature Generation process and save the data to a file. 

# Explanation
Feature Generation (also known as feature construction, feature extraction or feature engineering) is the process of transforming features into new features that better relate to the target.
 

# ALGORITHM
### STEP 1
Read the given Data
### STEP 2
Clean the Data Set using Data Cleaning Process
### STEP 3
Apply Feature Generation techniques to all the feature of the data set
### STEP 4
Save the data to the file


# CODE
```python
import pandas as pd
df = pd.read_csv("Encoding Data.csv")
df

```
```python
from sklearn.preprocessing import LabelEncoder, OrdinalEncoder
data = ["Red","Green","Blue"]
set = OrdinalEncoder(categories = [data])
set.fit_transform(df[["nom_0"]])
df["nom_1"] = set.fit_transform(df[["nom_0"]])
df
```
```python
data = ["Cold","Warm","Hot"]
st = OrdinalEncoder(categories = [data])
st.fit_transform(df[["ord_2"]])
df["ord_1"] = st.fit_transform(df[["ord_2"]])
df
```
```python
le = LabelEncoder()
df["sty"]=le.fit_transform(df[["ord_2"]])
df
```
```python
pd.get_dummies(df,columns=["nom_0"])
```
```python
df = pd.read_csv("data.csv")
from sklearn.preprocessing import LabelEncoder, OrdinalEncoder
data = ["Cold","Warm","Hot","Very Hot"]
set = OrdinalEncoder(categories = [data])
set.fit_transform(df[["Ord_1"]])
df["nom_1"] = set.fit_transform(df[["Ord_1"]])
df
```
```python
pd.get_dummies(df,columns=["Ord_1"])
```
# OUPUT
![image](./Screenshot%20from%202023-04-25%2015-38-32.png)
![image](./Screenshot%20from%202023-04-25%2015-38-48.png)
![image](./Screenshot%20from%202023-04-25%2015-39-04.png)
![image](./Screenshot%20from%202023-04-25%2015-39-16.png)

# RESULT
Thus, the given data is read and Feature Generation process is successfully performed and the data is successfully saved to a file.