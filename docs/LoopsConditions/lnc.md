# Loops and conditions

Loops provide the method of iteration while condition allows or blocks the code execution  when specified condition is meet.

### For llop and While Loop

- To iterate over the List. Lets prin the items in the list


```python
L =['apple','banana','kite','cellphone']
for item in L:
    print(item)
```

    apple
    banana
    kite
    cellphone


- What is range?


```python
range(5), range(1,100), sum(range(100))
```




    (range(0, 5), range(1, 100), 4950)



- To iterate with ```for``` loop and adding the iterating index (the value of ```10*k```) to a blank List ```L```.


```python
L = []
for k in range(10):
    L.append(10*k)
L
```




    [0, 10, 20, 30, 40, 50, 60, 70, 80, 90]



- To create a double loop also called ***nested for loop***. Lets create double for loop with ```i``` and ```j``` with range ```5``` and also populate the dictionary with ```key``` as ```(i,j)```and ```value``` as ```10*i+j``` when ```i=j``` and ```100*1+j``` when ```i!=j```.


```python
D = {}
for i in range(5):
    for j in range(5):
        if i == j :
            D.update({(i,j) : 10*i+j})
        elif i!= j:
            D.update({(i,j) : 100*i+j})
            
print(D)
```

    {(0, 0): 0, (0, 1): 1, (0, 2): 2, (0, 3): 3, (0, 4): 4, (1, 0): 100, (1, 1): 11, (1, 2): 102, (1, 3): 103, (1, 4): 104, (2, 0): 200, (2, 1): 201, (2, 2): 22, (2, 3): 203, (2, 4): 204, (3, 0): 300, (3, 1): 301, (3, 2): 302, (3, 3): 33, (3, 4): 304, (4, 0): 400, (4, 1): 401, (4, 2): 402, (4, 3): 403, (4, 4): 44}


- To iterate two elements from two seperate Lists. It is not like nested for loop.


```python
for item,j,k in zip(['apple','banana','kite','cellphone','pen'],\
                    range(5),[12,45,45,67,34]):
    print(item,"|",j,"|",k)
```

    apple | 0 | 12
    banana | 1 | 45
    kite | 2 | 45
    cellphone | 3 | 67
    pen | 4 | 34


- To iterate and ```ennumerate``` both together.


```python
for i,item in enumerate(['apple','banana','kite','cellphone']):
    print("The",i,"th element is: ", item)
```

    The 0 th element is:  apple
    The 1 th element is:  banana
    The 2 th element is:  kite
    The 3 th element is:  cellphone


- To create a list with ```for``` loop


```python
A = [10*k**2+5*k+1 for k in range(10)]
print(A)
```

    [1, 16, 51, 106, 181, 276, 391, 526, 681, 856]



```python
AA = [[10*x**2+5*y+1 for x in range(3)] for y in range(3)]
print(AA)
```

    [[1, 11, 41], [6, 16, 46], [11, 21, 51]]


- To iterate over List of List


```python
for i in range(3): 
    for j in range(3):
        print("The","(",i,",",j,")","th element is: ",AA[i][j])
```

    The ( 0 , 0 ) th element is:  1
    The ( 0 , 1 ) th element is:  11
    The ( 0 , 2 ) th element is:  41
    The ( 1 , 0 ) th element is:  6
    The ( 1 , 1 ) th element is:  16
    The ( 1 , 2 ) th element is:  46
    The ( 2 , 0 ) th element is:  11
    The ( 2 , 1 ) th element is:  21
    The ( 2 , 2 ) th element is:  51


- To use ```while``` loop.


```python
i = 0
while i <5:
    print( i, "th turn")
    i = i+1
```

    0 th turn
    1 th turn
    2 th turn
    3 th turn
    4 th turn


- To break for loop implementing ```if``` condition


```python
for i in range(10):
    print(i)
    if i ==3:
        break
```

    0
    1
    2
    3


- To test the if conditions:


```python
import random as random

for i in range(10):
    r = random.uniform(1,10)
    if r<2 and r>0:
        print("It is samaller then 2 and greater then 1","|", r)
    elif r<4 and r>2:
        print("It is samaller then 4 and greater then 2","|", r)
    elif r<6 and r>4:
        print("It is samaller then 6 and greater then 4","|", r)
    elif r<8 and r>6:
        print("It is samaller then 8 and greater then 6","|", r)
    elif r<10 and r>8:
        print("It is samaller then 10 and greater then 8","|", r)
```

    It is samaller then 10 and greater then 8 | 8.910435750481426
    It is samaller then 8 and greater then 6 | 6.616669779231224
    It is samaller then 4 and greater then 2 | 3.8009645328925896
    It is samaller then 4 and greater then 2 | 3.3039198434839117
    It is samaller then 4 and greater then 2 | 3.2192327041596696
    It is samaller then 10 and greater then 8 | 8.658302824387317
    It is samaller then 10 and greater then 8 | 9.048987906482312
    It is samaller then 10 and greater then 8 | 8.061577985253708
    It is samaller then 8 and greater then 6 | 6.301327115111054
    It is samaller then 6 and greater then 4 | 5.316492901781898


- To find sum from 0 to 1000


```python
s = 0
for i in range(1000+1):
    s = s+i
s
```




    500500



- To find sum from 0 to 1000 (only even)


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



### References:
1. https://docs.python.org/3/tutorial/index.html

--------
