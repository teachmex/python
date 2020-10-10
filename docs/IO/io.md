## Input and Output


```python
import json as json
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import random as random
%matplotlib inline
```


```python
#mkdir newfolder
```

### Txt file

- ```with open ()``` method


```python
mkdir data
```

    A subdirectory or file data already exists.



```python
with open('data/test.txt', 'w')as file:
    for k in range(100):
        file.write("it is your "+ str(k) + "th turn! \n")
```

- ```open()``` and ```close()``` method


```python
txtfile = open("data/textdata.txt",'w')
```


```python
for i in range (1000):
    '''check even or odd'''
    if i%2 ==0:
        txtfile.write(str(i) + "|It is even \n")
        
        '''check above or below 500'''
        if i<500:
            txtfile.write(str(i) + "|It is below 500 \n")
        else:
            txtfile.write(str(i) + "|It is above 500 \n")
            
    else:
        txtfile.write(str(i) + "|It is odd \n")
        
        '''check above or below 500'''
        if i<500:
            txtfile.write(str(i) + "|It is below 500 \n")
        else:
            txtfile.write(str(i) + "|It is above 500 \n")
            
txtfile.close()
```

- uploading/reading text file


```python
with open('data/textdata.txt','r') as f:
    i = 0
    for line in f:
        print(line)
        if i >10:
            break
        i = i+1
```

    0|It is even 
    
    0|It is below 500 
    
    1|It is odd 
    
    1|It is below 500 
    
    2|It is even 
    
    2|It is below 500 
    
    3|It is odd 
    
    3|It is below 500 
    
    4|It is even 
    
    4|It is below 500 
    
    5|It is odd 
    
    5|It is below 500 
    


### JSON file


```python
Data = []
for k in range(1000):
    Data.append({"x": np.random.uniform(0,10),\
        "y": np.random.uniform(0,20),\
        "z" : np.random.uniform(0,10)})
```


```python
Data[101:105]
```




    [{'x': 6.1054636810164595, 'y': 3.2863675264349634, 'z': 8.384891787980322},
     {'x': 7.069985836956237, 'y': 0.17988344698211423, 'z': 9.975981385348762},
     {'x': 2.7021265268361416, 'y': 9.729258889243164, 'z': 9.894201832125768},
     {'x': 6.418458045982539, 'y': 12.858408084598345, 'z': 5.91904399119246}]



- Save data to a JSON file


```python
mkdir data
```

    A subdirectory or file data already exists.



```python
with open("data/sample_data.json", 'w')as f:
    json.dump(Data,f)
```

- Upload data from JSON file


```python
with open("data/sample_data.json","r")as f:
    uploaded_data = json.load(f)
```


```python
uploaded_data[0:2]
```




    [{'x': 0.6982478944780635, 'y': 1.126719593276797, 'z': 0.4844149246453111},
     {'x': 9.508377504777027, 'y': 15.488536320226022, 'z': 2.7307796829523037}]



### CSV file


```python
DF = pd.DataFrame(Data)
DF.head()
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
      <th>x</th>
      <th>y</th>
      <th>z</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>0.698248</td>
      <td>1.126720</td>
      <td>0.484415</td>
    </tr>
    <tr>
      <th>1</th>
      <td>9.508378</td>
      <td>15.488536</td>
      <td>2.730780</td>
    </tr>
    <tr>
      <th>2</th>
      <td>7.248392</td>
      <td>1.646036</td>
      <td>5.782741</td>
    </tr>
    <tr>
      <th>3</th>
      <td>5.829758</td>
      <td>4.888937</td>
      <td>7.824382</td>
    </tr>
    <tr>
      <th>4</th>
      <td>3.174409</td>
      <td>19.844952</td>
      <td>4.117781</td>
    </tr>
  </tbody>
</table>
</div>



- Save data to a CSV file


```python
DF.to_csv("data/sampledata.csv")
```

- Upload data from a CSV file


```python
uploaded_data = pd.read_csv("data/sampledata.csv")
```


```python
uploaded_data.head()
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
      <th>Unnamed: 0</th>
      <th>x</th>
      <th>y</th>
      <th>z</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>0</td>
      <td>0.698248</td>
      <td>1.126720</td>
      <td>0.484415</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1</td>
      <td>9.508378</td>
      <td>15.488536</td>
      <td>2.730780</td>
    </tr>
    <tr>
      <th>2</th>
      <td>2</td>
      <td>7.248392</td>
      <td>1.646036</td>
      <td>5.782741</td>
    </tr>
    <tr>
      <th>3</th>
      <td>3</td>
      <td>5.829758</td>
      <td>4.888937</td>
      <td>7.824382</td>
    </tr>
    <tr>
      <th>4</th>
      <td>4</td>
      <td>3.174409</td>
      <td>19.844952</td>
      <td>4.117781</td>
    </tr>
  </tbody>
</table>
</div>




```python

```


```python

```
