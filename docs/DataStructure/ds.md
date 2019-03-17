
# Fundamental Data Structure :
-------------------
### List, Tuple and Dictionary

### List
-----------

To initiate a blank List.


```python
l = []
```

To find the type of the object.


```python
type(l)
```




    list



To create a list from scratch.


```python
L = [1,2,3,4,5,6]
```

Indexing of list.


```python
L[0],L[1],L[5]
```




    (1, 2, 6)



Revers indexing is also possible.


```python
L[-1],L[-2],L[-3]
```




    (6, 5, 4)



To find the length of list.


```python
len(L)
```




    6



To add the element from last.


```python
L.append(12)
L
```




    [1, 2, 3, 4, 5, 6, 12]



To find the sum of the elements (if they are of same types like int. double etc)


```python
sum(L)
```




    33



To find maximum and minimum of the list


```python
max(L), min(L)
```




    (12, 1)



To create a list of heterogeneous element types.


```python
L = [1,2.0,3,4,5,"Apple"]
```

To find the type of elements of a list.


```python
type(L[1]),type(L[5])
```




    (float, str)



To create a list of list.


```python
L = [[1,2,3],[3,4,5],[5,7,9]]
```

To find list inside a list.


```python
L[0]
```




    [1, 2, 3]




```python
L[0][1]
```




    2



To add list


```python
L1 = [1,2,3] ; L2 = [2,4,6]
L1+L2, set(L1+L2)
```




    ([1, 2, 3, 2, 4, 6], {1, 2, 3, 4, 6})



To create array for algebraic operations


```python
import numpy as np
L1 = np.array([1,2,3]); L2 = np.array([2,4,6])
L1 + L2
```




    array([3, 6, 9])



To iterate over the element of list


```python
L = [i for i in range(10)]
L
```




    [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]



To create a random List


```python
import random as random
L = [random.uniform(0,1) for k in  range(10)]
L
```




    [0.43053490647858217,
     0.4042754547551368,
     0.4825961844418639,
     0.07969436319497114,
     0.5359042493237792,
     0.521045536638314,
     0.9657067090287339,
     0.11515389590934644,
     0.20310645682803774,
     0.3875919385817722]



To create a random list of lists


```python
LL = [[random.uniform(0,1) for k in  range(3)]for l in range(3)]
LL
```




    [[0.27628847122005273, 0.8897450734835115, 0.18989122408874082],
     [0.13835865058469599, 0.7262672634594681, 0.10898554004253247],
     [0.42276719493338266, 0.11377775037902738, 0.4901096855852801]]



To save the data to json file


```python
import json
with open ('data/mylist.json', 'w')as f1:
    json.dump(LL,f1)
```

### Tuples
----------

To define a tuples from scratch


```python
t = (2,3,4,5)
```

Find type


```python
type(t)
```




    tuple



Indexing


```python
t[1]
```




    3



### Dictionary
---------

To initiate a dictionary


```python
D = dict()
DD = {}
```

Create a dictionary from scratch


```python
D = {"fruit":'apple',
    "vegetable" : 'carrot',
    "rice": 2.0,
    'milk': 10,}
```

What are keys?


```python
D.keys()
```




    dict_keys(['fruit', 'vegetable', 'rice', 'milk'])



What are values?


```python
D.values()
```




    dict_values(['apple', 'carrot', 2.0, 10])



Indexing


```python
D['fruit']
```




    'apple'



Iteration over key and values


```python
for key,value in D.items():
    print(key,value)
```

    fruit apple
    vegetable carrot
    rice 2.0
    milk 10


Update a dictionary


```python
D.update({"salt": 2.0})
D
```




    {'fruit': 'apple', 'vegetable': 'carrot', 'rice': 2.0, 'milk': 10, 'salt': 2.0}



Create a list form a Dictionary


```python
list(D)
```




    ['fruit', 'vegetable', 'rice', 'milk', 'salt']



Create a list of keys


```python
list(D.keys())
```




    ['fruit', 'vegetable', 'rice', 'milk', 'salt']



Create a list of values


```python
list(D.values())
```




    ['apple', 'carrot', 2.0, 10, 2.0]



Create a random Dictionary


```python
DD = {}
for item in ['A','B','C','D','E']:
    DD.update({item:[random.uniform(0,1) for k in  range(10)]})
```


```python
DD
```




    {'A': [0.8623300586958146,
      0.9817282451404751,
      0.918013419185538,
      0.7163654763224003,
      0.9605939306786828,
      0.10535569850024595,
      0.11017993829505879,
      0.7967874445465515,
      0.40100560974033395,
      0.6683804538904957],
     'B': [0.9108032733225849,
      0.5126845596833859,
      0.2889475226297349,
      0.4361419616905007,
      0.9162781988261498,
      0.6417420997937421,
      0.5703303219382578,
      0.8317203028864074,
      0.9987773067590386,
      0.19901433153401582],
     'C': [0.6877286885216957,
      0.16565933820204293,
      0.25063345210121424,
      0.31595887595060124,
      0.03522116131022823,
      0.5286776181365936,
      0.8154337189974739,
      0.8202821745739262,
      0.0672014040433101,
      0.12327287509980445],
     'D': [0.4836330819912691,
      0.8546497284804153,
      0.14752285825255218,
      0.5918584543549938,
      0.14518319590340412,
      0.025762251428333438,
      0.016788596008689316,
      0.009725555304236244,
      0.8177641188673302,
      0.5450138847266498],
     'E': [0.6456541452062622,
      0.7662672636891902,
      0.04445215914793821,
      0.3159171150800496,
      0.9400712936126994,
      0.6085210458061509,
      0.6029509689621034,
      0.34555270993185316,
      0.7452915466172698,
      0.03229045002223074]}



Save a dictionary to a json file


```python
import json
with open ('data/mydic.json', 'w')as f2:
    json.dump(DD,f2)
```


