
# Loops and conditions

-------


```python
L =['apple','banana','kite','cellphone']

'''Iterate over the items in a list'''

for item in L:
    print(item)
```

    apple
    banana
    kite
    cellphone



```python
L = []
for k in range(10):
    print(k)
    '''Append values to list L'''
    L.append(10*k)
```

    0
    1
    2
    3
    4
    5
    6
    7
    8
    9



```python
L
```




    [0, 10, 20, 30, 40, 50, 60, 70, 80, 90]




```python
D = {}
for i in range(5):
    for j in range(5):
        if i == j :
            
            print(i,"is equal to",j)
            
            '''update dictionary with (i,j) as key and 2*i as value'''
            
            D.update({(i,j) : 10*i+j})
            
        elif i!= j:
            
            '''update dictionary with (i,j) as key and 2*i as value'''
            
            D.update({(i,j) : 101*i+j})
            print(i,"is not equal to",j)
     
        
```

    0 is equal to 0
    0 is not equal to 1
    0 is not equal to 2
    0 is not equal to 3
    0 is not equal to 4
    1 is not equal to 0
    1 is equal to 1
    1 is not equal to 2
    1 is not equal to 3
    1 is not equal to 4
    2 is not equal to 0
    2 is not equal to 1
    2 is equal to 2
    2 is not equal to 3
    2 is not equal to 4
    3 is not equal to 0
    3 is not equal to 1
    3 is not equal to 2
    3 is equal to 3
    3 is not equal to 4
    4 is not equal to 0
    4 is not equal to 1
    4 is not equal to 2
    4 is not equal to 3
    4 is equal to 4



```python
D
```




    {(0, 0): 0,
     (0, 1): 1,
     (0, 2): 2,
     (0, 3): 3,
     (0, 4): 4,
     (1, 0): 101,
     (1, 1): 11,
     (1, 2): 103,
     (1, 3): 104,
     (1, 4): 105,
     (2, 0): 202,
     (2, 1): 203,
     (2, 2): 22,
     (2, 3): 205,
     (2, 4): 206,
     (3, 0): 303,
     (3, 1): 304,
     (3, 2): 305,
     (3, 3): 33,
     (3, 4): 307,
     (4, 0): 404,
     (4, 1): 405,
     (4, 2): 406,
     (4, 3): 407,
     (4, 4): 44}




```python
range(5)
```




    range(0, 5)




```python
for i,j in zip(range(5),range(5)):
    print(i,j)
```

    0 0
    1 1
    2 2
    3 3
    4 4



```python
for item,j in zip(['apple','banana','kite','cellphone','pen'],range(5)):
    print(item,j)
```

    apple 0
    banana 1
    kite 2
    cellphone 3
    pen 4



```python
for i,item in enumerate(['apple','banana','kite','cellphone']):
    print(i, item)
```

    0 apple
    1 banana
    2 kite
    3 cellphone



```python
A = [0 for k in range(10)]
A
```




    [0, 0, 0, 0, 0, 0, 0, 0, 0, 0]




```python
A = [k for k in range(10)]
A
```




    [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]




```python
L = [[1,2,3],[3,4,5],[5,7,9]]

for i in range(len(L)): 
    for j in range(len(L[0])):
        print(L[i][j])
```

    1
    2
    3
    3
    4
    5
    5
    7
    9



```python
LL = [[k+j for k in range(10)]for j in range(10)]
LL
```




    [[0, 1, 2, 3, 4, 5, 6, 7, 8, 9],
     [1, 2, 3, 4, 5, 6, 7, 8, 9, 10],
     [2, 3, 4, 5, 6, 7, 8, 9, 10, 11],
     [3, 4, 5, 6, 7, 8, 9, 10, 11, 12],
     [4, 5, 6, 7, 8, 9, 10, 11, 12, 13],
     [5, 6, 7, 8, 9, 10, 11, 12, 13, 14],
     [6, 7, 8, 9, 10, 11, 12, 13, 14, 15],
     [7, 8, 9, 10, 11, 12, 13, 14, 15, 16],
     [8, 9, 10, 11, 12, 13, 14, 15, 16, 17],
     [9, 10, 11, 12, 13, 14, 15, 16, 17, 18]]




```python
i = 0
while i < 10:
    print( i, "th turn")
    i = i+1
```

    0 th turn
    1 th turn
    2 th turn
    3 th turn
    4 th turn
    5 th turn
    6 th turn
    7 th turn
    8 th turn
    9 th turn



```python
import json 
'''download'''
with open('data/mylist.json', 'w') as f1:
    json.dump(LL,f1)
```

-------


```python
import json 
'''upload'''
with open('data/mydic.json', 'r') as f2:
    AA = json.load(f2)
```


```python
for key,value in AA.items():
    print("key : ", key,"|", "value: ", value)
```

    key :  A | value:  [0.8623300586958146, 0.9817282451404751, 0.918013419185538, 0.7163654763224003, 0.9605939306786828, 0.10535569850024595, 0.11017993829505879, 0.7967874445465515, 0.40100560974033395, 0.6683804538904957]
    key :  B | value:  [0.9108032733225849, 0.5126845596833859, 0.2889475226297349, 0.4361419616905007, 0.9162781988261498, 0.6417420997937421, 0.5703303219382578, 0.8317203028864074, 0.9987773067590386, 0.19901433153401582]
    key :  C | value:  [0.6877286885216957, 0.16565933820204293, 0.25063345210121424, 0.31595887595060124, 0.03522116131022823, 0.5286776181365936, 0.8154337189974739, 0.8202821745739262, 0.0672014040433101, 0.12327287509980445]
    key :  D | value:  [0.4836330819912691, 0.8546497284804153, 0.14752285825255218, 0.5918584543549938, 0.14518319590340412, 0.025762251428333438, 0.016788596008689316, 0.009725555304236244, 0.8177641188673302, 0.5450138847266498]
    key :  E | value:  [0.6456541452062622, 0.7662672636891902, 0.04445215914793821, 0.3159171150800496, 0.9400712936126994, 0.6085210458061509, 0.6029509689621034, 0.34555270993185316, 0.7452915466172698, 0.03229045002223074]



```python
DNA = 'ATGCATGCATATCAAGCTAGCTAGCTAGCTAGCTAGAGCTATTTAATGCTA\
        GCTATATAGCGCTAGCTATAGCTAGCTAGCTAGCTAGCTAGCTAGCTAGCT\
        AGCTAGCTAGCTAGCTAGCTAGCTAGCTAGCTAGCTAGCTAGCGCGCGCTA\
        TATATAGAGAGAGAGAGAGACACACATATATCTCTCTCTCTCGAGATCGAT\
        CGTACTAGCTAGCTAGCTAGCTAGCTAGCT'
```


```python
DNA.count('A'),DNA.count('AT')
```




    (66, 16)




```python
count = 0
for letter in DNA:
    if letter == 'T':
        count = count+1
count
```




    61




```python
'I am ok'.split()
```




    ['I', 'am', 'ok']



#### Q: find sum from 0 to 1000


```python
s = 0
for i in range(1000+1):
    s = s+i
s
```




    500500



#### Q: find sum from 0 to 1000 (only even)


```python
s = 0
LE = []
for i in range(1001):
    if i%2 ==0:
        LE.append(i)
        s = s+i
s, sum(LE)
```




    (250500, 250500)



--------
