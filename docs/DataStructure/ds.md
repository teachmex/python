# Fundamental Data Structure :

The fundamental data structure in python includes 

- **Primitive type** ( ***Integer, Float, String***, and ***Boolean***) and 
- **Non-Primitive type** ( ***Array, List, Tuples, Dictionary, Set***, and ***File***) 

In this tutorial, we are going to discudd about List, Tuples, Set and Dictionary. 



### List

List is built in data structure in python. It is 
- Mutable i.e., we can change or edite the size of the list by appending, inserting and deleting the elements.
- List can hold heterogeneous objects (e.g., integer, string, boolean)

Lets try to understand the List:

- To initiate a blank List.


```python
l = []
```

- To find the type of the object.


```python
type(l)
```




    list



- To create a list from scratch.


```python
L = [1,2,3,4,5,6]
```

- Indexing of list.


```python
L[0],L[1],L[5]
```




    (1, 2, 6)



- Revers indexing is also possible.


```python
L[-1],L[-2],L[-3]
```




    (6, 5, 4)



- To find the length of list.


```python
len(L)
```




    6



- To add the element from last.


```python
L.append(12)
L
```




    [1, 2, 3, 4, 5, 6, 12]



- To find the sum of the elements (if they are of same types like int. double etc)


```python
sum(L)
```




    33



- To find maximum and minimum of the list


```python
max(L), min(L)
```




    (12, 1)



- To create a list of heterogeneous element types.


```python
L = [1,2.0,3,4,5,"Apple",True]
```

- To find the type of elements of a list.


```python
type(L[1]),type(L[5])
```




    (float, str)



- To create a list of list.


```python
L = [[1,2,3],[3,4,5],[5,7,9]]
```

- To find list inside a list.


```python
L[0]
```




    [1, 2, 3]




```python
L[0][1]
```




    2



- To add two list. It is not as ususal addition. The elements are accumulated.


```python
L1 = [1,2,3] ; L2 = [2,4,6]
L1+L2, set(L1+L2)
```




    ([1, 2, 3, 2, 4, 6], {1, 2, 3, 4, 6})



- To add element from end of the list


```python
L = [1,4,2,3,5,6,7]
L.append(100)
L
```




    [1, 4, 2, 3, 5, 6, 7, 100]



- To insert element (100) at specific index (1)


```python
L = [1,4,2,3,5,6,7]
L.insert(1,100)
L
```




    [1, 100, 4, 2, 3, 5, 6, 7]



- To remove specific element form list. It will remove the first occurance.


```python
L = [1,4,2,3,5,6,7,4]
L.remove(4)
L
```




    [1, 2, 3, 5, 6, 7, 4]



- To remove the element from specific index


```python
L = [1,4,2,3,5,6,7]
L.pop(-1)
L
```




    [1, 4, 2, 3, 5, 6]



- To sort the list


```python
L = [1,10,2,30,5,60,7]
L.sort()
L
```




    [1, 2, 5, 7, 10, 30, 60]



- To reverse the list


```python
L = [1,4,2,3,5,6,7]
L.reverse()
L
```




    [7, 6, 5, 3, 2, 4, 1]



- To create a List of List


```python
LL = [[1,2,3],[4,5,6],[5,6,7]]
LL
```




    [[1, 2, 3], [4, 5, 6], [5, 6, 7]]



### Tuples

Tuples are non-mutable, which means we can ot add or remove elements once tuple is defind.

- To define a tuples from scratch


```python
t = (2,3,4,5)
```

- Find type


```python
type(t)
```




    tuple



- Indexing


```python
t[1]
```




    3



- Create a list of tuples


```python
L = [(1,2),("a","b"),(True, False)]
L
```




    [(1, 2), ('a', 'b'), (True, False)]



### Dictionary

Dictionary organizes the data with key-value pair. Dictionary can be nested with other data types.

- To initiate a dictionary


```python
D = dict()
DD = {}
```

- Create a dictionary from scratch


```python
D = {"fruit":'apple',
    "vegetable" : 'carrot',
    "rice": 2.0,
    'milk': 10,}
```

- What are keys?


```python
D.keys()
```




    dict_keys(['fruit', 'vegetable', 'rice', 'milk'])



- What are values?


```python
D.values()
```




    dict_values(['apple', 'carrot', 2.0, 10])



- Indexing


```python
D['fruit'], D["rice"]
```




    ('apple', 2.0)



- Iteration over key and values


```python
for key,value in D.items():
    print(key,value)
```

    fruit apple
    vegetable carrot
    rice 2.0
    milk 10


- To update a dictionary


```python
D.update({"salt": 2.0})
D
```




    {'fruit': 'apple', 'vegetable': 'carrot',
    'rice': 2.0, 'milk': 10, 'salt': 2.0}



- To create a list form a Dictionary. Only keys are collected.


```python
list(D)
```




    ['fruit', 'vegetable', 'rice', 'milk']



- To create a list of keys only


```python
list(D.keys())
```




    ['fruit', 'vegetable', 'rice', 'milk']



- To create a list of values


```python
list(D.values())
```




    ['apple', 'carrot', 2.0, 10, 2.0]



- To create Dictionary of with list, tuples and dictionary


```python
DD = {"names":["John","Harry", "Brat"],\
      "roll no": (1,2,3),\
      "plan":{"first":[12,34,56],"second":[1,3,5]}}

DD
```




    {'names': ['John', 'Harry', 'Brat'],
     'roll no': (1, 2, 3),
     'plan': {'first': [12, 34, 56], 'second': [1, 3, 5]}}


