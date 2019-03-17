
# Data Iteration and Indexing

-------------


```python
import pandas as pd
import numpy as np
import seaborn as sns
import matplotlib.pyplot as plt
%matplotlib inline
```


```python
titanic = pd.read_csv('data/titanic.csv')
```


```python
titanic.head()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>PassengerId</th>
      <th>Survived</th>
      <th>Pclass</th>
      <th>Name</th>
      <th>Sex</th>
      <th>Age</th>
      <th>SibSp</th>
      <th>Parch</th>
      <th>Ticket</th>
      <th>Fare</th>
      <th>Cabin</th>
      <th>Embarked</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1</td>
      <td>0</td>
      <td>3</td>
      <td>Braund, Mr. Owen Harris</td>
      <td>male</td>
      <td>22.0</td>
      <td>1</td>
      <td>0</td>
      <td>A/5 21171</td>
      <td>7.2500</td>
      <td>NaN</td>
      <td>S</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2</td>
      <td>1</td>
      <td>1</td>
      <td>Cumings, Mrs. John Bradley (Florence Briggs Th...</td>
      <td>female</td>
      <td>38.0</td>
      <td>1</td>
      <td>0</td>
      <td>PC 17599</td>
      <td>71.2833</td>
      <td>C85</td>
      <td>C</td>
    </tr>
    <tr>
      <th>2</th>
      <td>3</td>
      <td>1</td>
      <td>3</td>
      <td>Heikkinen, Miss. Laina</td>
      <td>female</td>
      <td>26.0</td>
      <td>0</td>
      <td>0</td>
      <td>STON/O2. 3101282</td>
      <td>7.9250</td>
      <td>NaN</td>
      <td>S</td>
    </tr>
    <tr>
      <th>3</th>
      <td>4</td>
      <td>1</td>
      <td>1</td>
      <td>Futrelle, Mrs. Jacques Heath (Lily May Peel)</td>
      <td>female</td>
      <td>35.0</td>
      <td>1</td>
      <td>0</td>
      <td>113803</td>
      <td>53.1000</td>
      <td>C123</td>
      <td>S</td>
    </tr>
    <tr>
      <th>4</th>
      <td>5</td>
      <td>0</td>
      <td>3</td>
      <td>Allen, Mr. William Henry</td>
      <td>male</td>
      <td>35.0</td>
      <td>0</td>
      <td>0</td>
      <td>373450</td>
      <td>8.0500</td>
      <td>NaN</td>
      <td>S</td>
    </tr>
  </tbody>
</table>
</div>



-----------------

### Setting Name column as index


```python
titanic_df1 = titanic.copy(deep =True)
```


```python
titanic_df1 = titanic.set_index('Name')
titanic_df1.head(5)
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>PassengerId</th>
      <th>Survived</th>
      <th>Pclass</th>
      <th>Sex</th>
      <th>Age</th>
      <th>SibSp</th>
      <th>Parch</th>
      <th>Ticket</th>
      <th>Fare</th>
      <th>Cabin</th>
      <th>Embarked</th>
    </tr>
    <tr>
      <th>Name</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Braund, Mr. Owen Harris</th>
      <td>1</td>
      <td>0</td>
      <td>3</td>
      <td>male</td>
      <td>22.0</td>
      <td>1</td>
      <td>0</td>
      <td>A/5 21171</td>
      <td>7.2500</td>
      <td>NaN</td>
      <td>S</td>
    </tr>
    <tr>
      <th>Cumings, Mrs. John Bradley (Florence Briggs Thayer)</th>
      <td>2</td>
      <td>1</td>
      <td>1</td>
      <td>female</td>
      <td>38.0</td>
      <td>1</td>
      <td>0</td>
      <td>PC 17599</td>
      <td>71.2833</td>
      <td>C85</td>
      <td>C</td>
    </tr>
    <tr>
      <th>Heikkinen, Miss. Laina</th>
      <td>3</td>
      <td>1</td>
      <td>3</td>
      <td>female</td>
      <td>26.0</td>
      <td>0</td>
      <td>0</td>
      <td>STON/O2. 3101282</td>
      <td>7.9250</td>
      <td>NaN</td>
      <td>S</td>
    </tr>
    <tr>
      <th>Futrelle, Mrs. Jacques Heath (Lily May Peel)</th>
      <td>4</td>
      <td>1</td>
      <td>1</td>
      <td>female</td>
      <td>35.0</td>
      <td>1</td>
      <td>0</td>
      <td>113803</td>
      <td>53.1000</td>
      <td>C123</td>
      <td>S</td>
    </tr>
    <tr>
      <th>Allen, Mr. William Henry</th>
      <td>5</td>
      <td>0</td>
      <td>3</td>
      <td>male</td>
      <td>35.0</td>
      <td>0</td>
      <td>0</td>
      <td>373450</td>
      <td>8.0500</td>
      <td>NaN</td>
      <td>S</td>
    </tr>
  </tbody>
</table>
</div>



-----------

##   Data Frame item iteration

------------


```python
sample = titanic_df1[0:5]
```

##### ```iterrows```


```python
for index,row in sample.iterrows():
    print(index,list(row))
```

    Braund, Mr. Owen Harris [1, 0, 3, 'male', 22.0, 1, 0, 'A/5 21171', 7.25, nan, 'S']
    Cumings, Mrs. John Bradley (Florence Briggs Thayer) [2, 1, 1, 'female', 38.0, 1, 0, 'PC 17599', 71.2833, 'C85', 'C']
    Heikkinen, Miss. Laina [3, 1, 3, 'female', 26.0, 0, 0, 'STON/O2. 3101282', 7.925, nan, 'S']
    Futrelle, Mrs. Jacques Heath (Lily May Peel) [4, 1, 1, 'female', 35.0, 1, 0, '113803', 53.1, 'C123', 'S']
    Allen, Mr. William Henry [5, 0, 3, 'male', 35.0, 0, 0, '373450', 8.05, nan, 'S']



```python
for index,row in sample.iterrows():
    print(index,row['Sex'],row['Age'])
```

    Braund, Mr. Owen Harris male 22.0
    Cumings, Mrs. John Bradley (Florence Briggs Thayer) female 38.0
    Heikkinen, Miss. Laina female 26.0
    Futrelle, Mrs. Jacques Heath (Lily May Peel) female 35.0
    Allen, Mr. William Henry male 35.0


####  ```iteritems```


```python
for index,row in sample.T.iteritems():
    print(index,list(row))
```

    Braund, Mr. Owen Harris [1, 0, 3, 'male', 22.0, 1, 0, 'A/5 21171', 7.25, nan, 'S']
    Cumings, Mrs. John Bradley (Florence Briggs Thayer) [2, 1, 1, 'female', 38.0, 1, 0, 'PC 17599', 71.2833, 'C85', 'C']
    Heikkinen, Miss. Laina [3, 1, 3, 'female', 26.0, 0, 0, 'STON/O2. 3101282', 7.925, nan, 'S']
    Futrelle, Mrs. Jacques Heath (Lily May Peel) [4, 1, 1, 'female', 35.0, 1, 0, '113803', 53.1, 'C123', 'S']
    Allen, Mr. William Henry [5, 0, 3, 'male', 35.0, 0, 0, '373450', 8.05, nan, 'S']



```python
for index,row in sample.iteritems():
    print(index,row[0],row[1],row[2])
```

    PassengerId 1 2 3
    Survived 0 1 1
    Pclass 3 1 3
    Sex male female female
    Age 22.0 38.0 26.0
    SibSp 1 1 0
    Parch 0 0 0
    Ticket A/5 21171 PC 17599 STON/O2. 3101282
    Fare 7.25 71.2833 7.925
    Cabin nan C85 nan
    Embarked S C S


-------------

##  Indexing Data

Source: [Using iloc, loc, & ix to select rows and columns in Pandas DataFrames](https://www.shanelynn.ie/select-pandas-dataframe-rows-and-columns-using-iloc-loc-and-ix/)

### ```loc``` and ```iloc``` :

The iloc indexer for Pandas Dataframe is used for integer-location based indexing / selection by position.

The Pandas loc indexer can be used with DataFrames for two different use cases:

  - a.) Selecting rows by label/index
  - b.) Selecting rows with a boolean / conditional lookup


```python
sample.iloc[0:2,:]
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>PassengerId</th>
      <th>Survived</th>
      <th>Pclass</th>
      <th>Sex</th>
      <th>Age</th>
      <th>SibSp</th>
      <th>Parch</th>
      <th>Ticket</th>
      <th>Fare</th>
      <th>Cabin</th>
      <th>Embarked</th>
    </tr>
    <tr>
      <th>Name</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Braund, Mr. Owen Harris</th>
      <td>1</td>
      <td>0</td>
      <td>3</td>
      <td>male</td>
      <td>22.0</td>
      <td>1</td>
      <td>0</td>
      <td>A/5 21171</td>
      <td>7.2500</td>
      <td>NaN</td>
      <td>S</td>
    </tr>
    <tr>
      <th>Cumings, Mrs. John Bradley (Florence Briggs Thayer)</th>
      <td>2</td>
      <td>1</td>
      <td>1</td>
      <td>female</td>
      <td>38.0</td>
      <td>1</td>
      <td>0</td>
      <td>PC 17599</td>
      <td>71.2833</td>
      <td>C85</td>
      <td>C</td>
    </tr>
  </tbody>
</table>
</div>




```python
sample.iloc[1,0:3]
```




    PassengerId    2
    Survived       1
    Pclass         1
    Name: Cumings, Mrs. John Bradley (Florence Briggs Thayer), dtype: object




```python
sample.loc[:,'Survived': 'Ticket']
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Survived</th>
      <th>Pclass</th>
      <th>Sex</th>
      <th>Age</th>
      <th>SibSp</th>
      <th>Parch</th>
      <th>Ticket</th>
    </tr>
    <tr>
      <th>Name</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Braund, Mr. Owen Harris</th>
      <td>0</td>
      <td>3</td>
      <td>male</td>
      <td>22.0</td>
      <td>1</td>
      <td>0</td>
      <td>A/5 21171</td>
    </tr>
    <tr>
      <th>Cumings, Mrs. John Bradley (Florence Briggs Thayer)</th>
      <td>1</td>
      <td>1</td>
      <td>female</td>
      <td>38.0</td>
      <td>1</td>
      <td>0</td>
      <td>PC 17599</td>
    </tr>
    <tr>
      <th>Heikkinen, Miss. Laina</th>
      <td>1</td>
      <td>3</td>
      <td>female</td>
      <td>26.0</td>
      <td>0</td>
      <td>0</td>
      <td>STON/O2. 3101282</td>
    </tr>
    <tr>
      <th>Futrelle, Mrs. Jacques Heath (Lily May Peel)</th>
      <td>1</td>
      <td>1</td>
      <td>female</td>
      <td>35.0</td>
      <td>1</td>
      <td>0</td>
      <td>113803</td>
    </tr>
    <tr>
      <th>Allen, Mr. William Henry</th>
      <td>0</td>
      <td>3</td>
      <td>male</td>
      <td>35.0</td>
      <td>0</td>
      <td>0</td>
      <td>373450</td>
    </tr>
  </tbody>
</table>
</div>




```python
sample.loc['Braund, Mr. Owen Harris',:]
```




    PassengerId            1
    Survived               0
    Pclass                 3
    Sex                 male
    Age                   22
    SibSp                  1
    Parch                  0
    Ticket         A/5 21171
    Fare                7.25
    Cabin                NaN
    Embarked               S
    Name: Braund, Mr. Owen Harris, dtype: object



------------

### Data Filters

--------------

#### Dictionary to DataFrame


```python
data = {'country': ['Belgium', 'France', 'Germany', 'Netherlands', 'United Kingdom'],
        'population': [11.3, 64.3, 81.3, 16.9, 64.9],
        'area': [30510, 671308, 357050, 41526, 244820],
        'capital': ['Brussels', 'Paris', 'Berlin', 'Amsterdam', 'London']}



countries = pd.DataFrame(data)
countries
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>country</th>
      <th>population</th>
      <th>area</th>
      <th>capital</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Belgium</td>
      <td>11.3</td>
      <td>30510</td>
      <td>Brussels</td>
    </tr>
    <tr>
      <th>1</th>
      <td>France</td>
      <td>64.3</td>
      <td>671308</td>
      <td>Paris</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Germany</td>
      <td>81.3</td>
      <td>357050</td>
      <td>Berlin</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Netherlands</td>
      <td>16.9</td>
      <td>41526</td>
      <td>Amsterdam</td>
    </tr>
    <tr>
      <th>4</th>
      <td>United Kingdom</td>
      <td>64.9</td>
      <td>244820</td>
      <td>London</td>
    </tr>
  </tbody>
</table>
</div>




```python
countries = countries.set_index('country')
countries
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>population</th>
      <th>area</th>
      <th>capital</th>
    </tr>
    <tr>
      <th>country</th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Belgium</th>
      <td>11.3</td>
      <td>30510</td>
      <td>Brussels</td>
    </tr>
    <tr>
      <th>France</th>
      <td>64.3</td>
      <td>671308</td>
      <td>Paris</td>
    </tr>
    <tr>
      <th>Germany</th>
      <td>81.3</td>
      <td>357050</td>
      <td>Berlin</td>
    </tr>
    <tr>
      <th>Netherlands</th>
      <td>16.9</td>
      <td>41526</td>
      <td>Amsterdam</td>
    </tr>
    <tr>
      <th>United Kingdom</th>
      <td>64.9</td>
      <td>244820</td>
      <td>London</td>
    </tr>
  </tbody>
</table>
</div>




```python
countries['area']
```




    country
    Belgium            30510
    France            671308
    Germany           357050
    Netherlands        41526
    United Kingdom    244820
    Name: area, dtype: int64




```python
countries[['area', 'population']]
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>area</th>
      <th>population</th>
    </tr>
    <tr>
      <th>country</th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Belgium</th>
      <td>30510</td>
      <td>11.3</td>
    </tr>
    <tr>
      <th>France</th>
      <td>671308</td>
      <td>64.3</td>
    </tr>
    <tr>
      <th>Germany</th>
      <td>357050</td>
      <td>81.3</td>
    </tr>
    <tr>
      <th>Netherlands</th>
      <td>41526</td>
      <td>16.9</td>
    </tr>
    <tr>
      <th>United Kingdom</th>
      <td>244820</td>
      <td>64.9</td>
    </tr>
  </tbody>
</table>
</div>




```python
countries['France':'Netherlands']
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>population</th>
      <th>area</th>
      <th>capital</th>
    </tr>
    <tr>
      <th>country</th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>France</th>
      <td>64.3</td>
      <td>671308</td>
      <td>Paris</td>
    </tr>
    <tr>
      <th>Germany</th>
      <td>81.3</td>
      <td>357050</td>
      <td>Berlin</td>
    </tr>
    <tr>
      <th>Netherlands</th>
      <td>16.9</td>
      <td>41526</td>
      <td>Amsterdam</td>
    </tr>
  </tbody>
</table>
</div>




```python
countries.loc['Germany', 'area']
```




    357050




```python
countries.loc['France':'Germany', ['area', 'population']]
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>area</th>
      <th>population</th>
    </tr>
    <tr>
      <th>country</th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>France</th>
      <td>671308</td>
      <td>64.3</td>
    </tr>
    <tr>
      <th>Germany</th>
      <td>357050</td>
      <td>81.3</td>
    </tr>
  </tbody>
</table>
</div>




```python
countries.iloc[0:2,1:3]
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>area</th>
      <th>capital</th>
    </tr>
    <tr>
      <th>country</th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Belgium</th>
      <td>30510</td>
      <td>Brussels</td>
    </tr>
    <tr>
      <th>France</th>
      <td>671308</td>
      <td>Paris</td>
    </tr>
  </tbody>
</table>
</div>




```python
countries2 = countries.copy()
countries2.loc['Belgium':'Germany', 'population'] = 10
```


```python
countries2
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>population</th>
      <th>area</th>
      <th>capital</th>
    </tr>
    <tr>
      <th>country</th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Belgium</th>
      <td>10.0</td>
      <td>30510</td>
      <td>Brussels</td>
    </tr>
    <tr>
      <th>France</th>
      <td>10.0</td>
      <td>671308</td>
      <td>Paris</td>
    </tr>
    <tr>
      <th>Germany</th>
      <td>10.0</td>
      <td>357050</td>
      <td>Berlin</td>
    </tr>
    <tr>
      <th>Netherlands</th>
      <td>16.9</td>
      <td>41526</td>
      <td>Amsterdam</td>
    </tr>
    <tr>
      <th>United Kingdom</th>
      <td>64.9</td>
      <td>244820</td>
      <td>London</td>
    </tr>
  </tbody>
</table>
</div>




```python
countries['area'] > 100000
```




    country
    Belgium           False
    France             True
    Germany            True
    Netherlands       False
    United Kingdom     True
    Name: area, dtype: bool




```python
countries[countries['area'] > 100000]
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>population</th>
      <th>area</th>
      <th>capital</th>
    </tr>
    <tr>
      <th>country</th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>France</th>
      <td>64.3</td>
      <td>671308</td>
      <td>Paris</td>
    </tr>
    <tr>
      <th>Germany</th>
      <td>81.3</td>
      <td>357050</td>
      <td>Berlin</td>
    </tr>
    <tr>
      <th>United Kingdom</th>
      <td>64.9</td>
      <td>244820</td>
      <td>London</td>
    </tr>
  </tbody>
</table>
</div>



---

<div class="alert alert-success">
    <b>EXERCISE</b>: Add a column `density` with the population density (note: population column is expressed in millions)
</div>


```python
countries['density'] = countries['population']*1000000 / countries['area']
countries
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>population</th>
      <th>area</th>
      <th>capital</th>
      <th>density</th>
    </tr>
    <tr>
      <th>country</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Belgium</th>
      <td>11.3</td>
      <td>30510</td>
      <td>Brussels</td>
      <td>370.370370</td>
    </tr>
    <tr>
      <th>France</th>
      <td>64.3</td>
      <td>671308</td>
      <td>Paris</td>
      <td>95.783158</td>
    </tr>
    <tr>
      <th>Germany</th>
      <td>81.3</td>
      <td>357050</td>
      <td>Berlin</td>
      <td>227.699202</td>
    </tr>
    <tr>
      <th>Netherlands</th>
      <td>16.9</td>
      <td>41526</td>
      <td>Amsterdam</td>
      <td>406.973944</td>
    </tr>
    <tr>
      <th>United Kingdom</th>
      <td>64.9</td>
      <td>244820</td>
      <td>London</td>
      <td>265.092721</td>
    </tr>
  </tbody>
</table>
</div>



<div class="alert alert-success">
    <b>EXERCISE</b>: Select the capital and the population column of those countries where the density is larger than 300
</div>


```python
countries.loc[countries['density'] > 300, ['capital', 'population']]
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>capital</th>
      <th>population</th>
    </tr>
    <tr>
      <th>country</th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Belgium</th>
      <td>Brussels</td>
      <td>11.3</td>
    </tr>
    <tr>
      <th>Netherlands</th>
      <td>Amsterdam</td>
      <td>16.9</td>
    </tr>
  </tbody>
</table>
</div>



<div class="alert alert-success">
    <b>EXERCISE</b>: Add a column 'density_ratio' with the ratio of the density to the mean density
</div>


```python
countries['density_ratio'] = countries['density'] / countries['density'].mean()
countries
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>population</th>
      <th>area</th>
      <th>capital</th>
      <th>density</th>
      <th>density_ratio</th>
    </tr>
    <tr>
      <th>country</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Belgium</th>
      <td>11.3</td>
      <td>30510</td>
      <td>Brussels</td>
      <td>370.370370</td>
      <td>1.355755</td>
    </tr>
    <tr>
      <th>France</th>
      <td>64.3</td>
      <td>671308</td>
      <td>Paris</td>
      <td>95.783158</td>
      <td>0.350618</td>
    </tr>
    <tr>
      <th>Germany</th>
      <td>81.3</td>
      <td>357050</td>
      <td>Berlin</td>
      <td>227.699202</td>
      <td>0.833502</td>
    </tr>
    <tr>
      <th>Netherlands</th>
      <td>16.9</td>
      <td>41526</td>
      <td>Amsterdam</td>
      <td>406.973944</td>
      <td>1.489744</td>
    </tr>
    <tr>
      <th>United Kingdom</th>
      <td>64.9</td>
      <td>244820</td>
      <td>London</td>
      <td>265.092721</td>
      <td>0.970382</td>
    </tr>
  </tbody>
</table>
</div>



<div class="alert alert-success">
    <b>EXERCISE</b>: Change the capital of the UK to Cambridge
</div>


```python
countries.loc['United Kingdom', 'capital'] = 'Cambridge'
countries
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>population</th>
      <th>area</th>
      <th>capital</th>
      <th>density</th>
      <th>density_ratio</th>
    </tr>
    <tr>
      <th>country</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Belgium</th>
      <td>11.3</td>
      <td>30510</td>
      <td>Brussels</td>
      <td>370.370370</td>
      <td>1.355755</td>
    </tr>
    <tr>
      <th>France</th>
      <td>64.3</td>
      <td>671308</td>
      <td>Paris</td>
      <td>95.783158</td>
      <td>0.350618</td>
    </tr>
    <tr>
      <th>Germany</th>
      <td>81.3</td>
      <td>357050</td>
      <td>Berlin</td>
      <td>227.699202</td>
      <td>0.833502</td>
    </tr>
    <tr>
      <th>Netherlands</th>
      <td>16.9</td>
      <td>41526</td>
      <td>Amsterdam</td>
      <td>406.973944</td>
      <td>1.489744</td>
    </tr>
    <tr>
      <th>United Kingdom</th>
      <td>64.9</td>
      <td>244820</td>
      <td>Cambridge</td>
      <td>265.092721</td>
      <td>0.970382</td>
    </tr>
  </tbody>
</table>
</div>



<div class="alert alert-success">
    <b>EXERCISE</b>: Select all countries whose population density is between 100 and 300 people/km²
</div>


```python
countries[(countries['density'] > 100) & (countries['density'] < 300)]
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>population</th>
      <th>area</th>
      <th>capital</th>
      <th>density</th>
      <th>density_ratio</th>
    </tr>
    <tr>
      <th>country</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Germany</th>
      <td>81.3</td>
      <td>357050</td>
      <td>Berlin</td>
      <td>227.699202</td>
      <td>0.833502</td>
    </tr>
    <tr>
      <th>United Kingdom</th>
      <td>64.9</td>
      <td>244820</td>
      <td>Cambridge</td>
      <td>265.092721</td>
      <td>0.970382</td>
    </tr>
  </tbody>
</table>
</div>


