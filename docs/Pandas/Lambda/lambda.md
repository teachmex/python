
# Lambda Transformation

-------------


```python
import pandas as pd
import numpy as np
import seaborn as sns
import matplotlib.pyplot as plt
%matplotlib inline
```

####  Load data


```python
titanic = pd.read_csv('data/titanic.csv')
```

### Setting Name column as index


```python
df1 = titanic.copy(deep =True)
```


```python
df1 = titanic.set_index('Name')
df1.head(2)
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



-----------

### Lambda Transformation


```python
df1['Fare'].apply(lambda x: (10*x**2 + 2*x +4)/10)
```




    Name
    Braund, Mr. Owen Harris                                       0.72500
    Cumings, Mrs. John Bradley (Florence Briggs Thayer)           7.12833
    Heikkinen, Miss. Laina                                        0.79250
    Futrelle, Mrs. Jacques Heath (Lily May Peel)                  5.31000
    Allen, Mr. William Henry                                      0.80500
    Moran, Mr. James                                              0.84583
    McCarthy, Mr. Timothy J                                       5.18625
    Palsson, Master. Gosta Leonard                                2.10750
    Johnson, Mrs. Oscar W (Elisabeth Vilhelmina Berg)             1.11333
    Nasser, Mrs. Nicholas (Adele Achem)                           3.00708
    Sandstrom, Miss. Marguerite Rut                               1.67000
    Bonnell, Miss. Elizabeth                                      2.65500
    Saundercock, Mr. William Henry                                0.80500
    Andersson, Mr. Anders Johan                                   3.12750
    Vestrom, Miss. Hulda Amanda Adolfina                          0.78542
    Hewlett, Mrs. (Mary D Kingcome)                               1.60000
    Rice, Master. Eugene                                          2.91250
    Williams, Mr. Charles Eugene                                  1.30000
    Vander Planke, Mrs. Julius (Emelia Maria Vandemoortele)       1.80000
    Masselmani, Mrs. Fatima                                       0.72250
    Fynney, Mr. Joseph J                                          2.60000
    Beesley, Mr. Lawrence                                         1.30000
    McGowan, Miss. Anna "Annie"                                   0.80292
    Sloper, Mr. William Thompson                                  3.55000
    Palsson, Miss. Torborg Danira                                 2.10750
    Asplund, Mrs. Carl Oscar (Selma Augusta Emilia Johansson)     3.13875
    Emir, Mr. Farred Chehab                                       0.72250
    Fortune, Mr. Charles Alexander                               26.30000
    O'Dwyer, Miss. Ellen "Nellie"                                 0.78792
    Todoroff, Mr. Lalio                                           0.78958
                                                                   ...   
    Giles, Mr. Frederick Edward                                   1.15000
    Swift, Mrs. Frederick Joel (Margaret Welles Barron)           2.59292
    Sage, Miss. Dorothy Edith "Dolly"                             6.95500
    Gill, Mr. John William                                        1.30000
    Bystrom, Mrs. (Karolina)                                      1.30000
    Duran y More, Miss. Asuncion                                  1.38583
    Roebling, Mr. Washington Augustus II                          5.04958
    van Melkebeke, Mr. Philemon                                   0.95000
    Johnson, Master. Harold Theodor                               1.11333
    Balkic, Mr. Cerin                                             0.78958
    Beckwith, Mrs. Richard Leonard (Sallie Monypeny)              5.25542
    Carlsson, Mr. Frans Olof                                      0.50000
    Vander Cruyssen, Mr. Victor                                   0.90000
    Abelson, Mrs. Samuel (Hannah Wizosky)                         2.40000
    Najib, Miss. Adele Kiamie "Jane"                              0.72250
    Gustafsson, Mr. Alfred Ossian                                 0.98458
    Petroff, Mr. Nedelio                                          0.78958
    Laleff, Mr. Kristo                                            0.78958
    Potter, Mrs. Thomas Jr (Lily Alexenia Wilson)                 8.31583
    Shelley, Mrs. William (Imanita Parrish Hall)                  2.60000
    Markun, Mr. Johann                                            0.78958
    Dahlberg, Miss. Gerda Ulrika                                  1.05167
    Banfield, Mr. Frederick James                                 1.05000
    Sutehall, Mr. Henry Jr                                        0.70500
    Rice, Mrs. William (Margaret Norton)                          2.91250
    Montvila, Rev. Juozas                                         1.30000
    Graham, Miss. Margaret Edith                                  3.00000
    Johnston, Miss. Catherine Helen "Carrie"                      2.34500
    Behr, Mr. Karl Howell                                         3.00000
    Dooley, Mr. Patrick                                           0.77500
    Name: Fare, Length: 891, dtype: float64




```python
def newfeature(x):
    return 10 + x/3 + x**2
```


```python
df1['Fare'].apply(newfeature)
```




    Name
    Braund, Mr. Owen Harris                                         64.979167
    Cumings, Mrs. John Bradley (Florence Briggs Thayer)           5115.069959
    Heikkinen, Miss. Laina                                          75.447292
    Futrelle, Mrs. Jacques Heath (Lily May Peel)                  2847.310000
    Allen, Mr. William Henry                                        77.485833
    Moran, Mr. James                                                84.362272
    McCarthy, Mr. Timothy J                                       2717.006406
    Palsson, Master. Gosta Leonard                                 461.180625
    Johnson, Mrs. Oscar W (Elisabeth Vilhelmina Berg)              137.661469
    Nasser, Mrs. Nicholas (Adele Achem)                            924.276613
    Sandstrom, Miss. Marguerite Rut                                294.456667
    Bonnell, Miss. Elizabeth                                       723.752500
    Saundercock, Mr. William Henry                                  77.485833
    Andersson, Mr. Anders Johan                                    998.550625
    Vestrom, Miss. Hulda Amanda Adolfina                            74.306524
    Hewlett, Mrs. (Mary D Kingcome)                                271.333333
    Rice, Master. Eugene                                           867.973958
    Williams, Mr. Charles Eugene                                   183.333333
    Vander Planke, Mrs. Julius (Emelia Maria Vandemoortele)        340.000000
    Masselmani, Mrs. Fatima                                         64.608958
    Fynney, Mr. Joseph J                                           694.666667
    Beesley, Mr. Lawrence                                          183.333333
    McGowan, Miss. Anna "Annie"                                     77.144453
    Sloper, Mr. William Thompson                                  1282.083333
    Palsson, Miss. Torborg Danira                                  461.180625
    Asplund, Mrs. Carl Oscar (Selma Augusta Emilia Johansson)     1005.637656
    Emir, Mr. Farred Chehab                                         64.608958
    Fortune, Mr. Charles Alexander                               69266.666667
    O'Dwyer, Miss. Ellen "Nellie"                                   74.708193
    Todoroff, Mr. Lalio                                             74.975591
                                                                     ...     
    Giles, Mr. Frederick Edward                                    146.083333
    Swift, Mrs. Frederick Joel (Margaret Welles Barron)            690.966479
    Sage, Miss. Dorothy Edith "Dolly"                             4870.385833
    Gill, Mr. John William                                         183.333333
    Bystrom, Mrs. (Karolina)                                       183.333333
    Duran y More, Miss. Asuncion                                   206.671912
    Roebling, Mr. Washington Augustus II                          2576.657751
    van Melkebeke, Mr. Philemon                                    103.416667
    Johnson, Master. Harold Theodor                                137.661469
    Balkic, Mr. Cerin                                               74.975591
    Beckwith, Mrs. Richard Leonard (Sallie Monypeny)              2789.462004
    Carlsson, Mr. Frans Olof                                        36.666667
    Vander Cruyssen, Mr. Victor                                     94.000000
    Abelson, Mrs. Samuel (Hannah Wizosky)                          594.000000
    Najib, Miss. Adele Kiamie "Jane"                                64.608958
    Gustafsson, Mr. Alfred Ossian                                  110.221711
    Petroff, Mr. Nedelio                                            74.975591
    Laleff, Mr. Kristo                                              74.975591
    Potter, Mrs. Thomas Jr (Lily Alexenia Wilson)                 6953.022292
    Shelley, Mrs. William (Imanita Parrish Hall)                   694.666667
    Markun, Mr. Johann                                              74.975591
    Dahlberg, Miss. Gerda Ulrika                                   124.106546
    Banfield, Mr. Frederick James                                  123.750000
    Sutehall, Mr. Henry Jr                                          62.052500
    Rice, Mrs. William (Margaret Norton)                           867.973958
    Montvila, Rev. Juozas                                          183.333333
    Graham, Miss. Margaret Edith                                   920.000000
    Johnston, Miss. Catherine Helen "Carrie"                       567.719167
    Behr, Mr. Karl Howell                                          920.000000
    Dooley, Mr. Patrick                                             72.645833
    Name: Fare, Length: 891, dtype: float64


