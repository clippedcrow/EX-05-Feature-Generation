# Feature Generation Workshop


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
df=pd.read_excel("/content/Workshop_feature Engg.csv (1).xlsx")
df

```
```python
from sklearn.preprocessing import LabelEncoder, OrdinalEncoder
data = ["convertible","sedan","wagon","hatchback","hardtop"]
set = OrdinalEncoder(categories = [data])
set.fit_transform(df[["carbody"]])
df["car-body"] = set.fit_transform(df[["carbody"]])
df
```
```python
pd.get_dummies(df,columns=["carbody"])
```
```python
le = LabelEncoder()
df3=df.copy()
df3['car-body']=le.fit_transform(df3['carbody'])
df3
```
```python
from sklearn.preprocessing import OneHotEncoder
ohe = OneHotEncoder(sparse =False)
df6=df.copy()
enc=pd.DataFrame(ohe.fit_transform(df6[['carbody']]))
df6= pd.concat([df6,enc],axis=1)
```
```python
df7=df.copy()
pd.get_dummies(df7,columns=['carbody'])
```
```python
from category_encoders import BinaryEncoder
be=BinaryEncoder()
newdata=be.fit_transform(df['carbody'])
df1=pd.concat([df,newdata],axis=1)
df2=df.copy()
df1
```
```python
from category_encoders import TargetEncoder
te=TargetEncoder()
df4=df.copy()
new=te.fit_transform(X=df4['carbody'],y=df4['wheelbase'])
df4=pd.concat([df4,new],axis=1)
df4
```

# OUPUT
![image](./Screenshot%20from%202023-04-25%2015-38-32.png)
![image](./Screenshot%20from%202023-04-25%2015-38-48.png)
![image](./Screenshot%20from%202023-04-25%2015-39-04.png)
![image](./Screenshot%20from%202023-04-25%2015-39-16.png)

# RESULT
Thus, the given data is read and Feature Generation process is successfully performed and the data is successfully saved to a file.
