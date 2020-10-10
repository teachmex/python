# Functions and Classes

Function and Class are required for object oriented programming. Functions, once created, can be implemented multiple times while Class is more useful for both data encaptulation and functions.


```python
import numpy as np
import random as random
```

### Function


```python
sum([2,3])
```




    5




```python
def printer(message):
    print("your message is:",message)
    return 
```


```python
printer("How are you?")
```

    your message is: How are you?



```python
for i in range(10):
    printer(i)
```

    your message is: 0
    your message is: 1
    your message is: 2
    your message is: 3
    your message is: 4
    your message is: 5
    your message is: 6
    your message is: 7
    your message is: 8
    your message is: 9



```python
def list2dict(L):
    D = {}
    for e in L:
        D.update({e:L.index(e)})
    return D
```


```python
mylist = [34,45,67,89,90,36,12,57]
x2 = list2dict(mylist)
```


```python
def dice(N):
    roll = []
    for r in range(N):
        s = random.choice([1,2,3,4,5,6])
        roll.append(s)
    return roll
```


```python
print(dice(100))
```

    [4, 5, 5, 4, 2, 1, 6, 2, 6, 3, 6, 5, 5, 4, 4, 6, 3, 1, 3, 5, 5, 5, 4, 3, 1, 2, 2, 4, 4, 5, 1, 2, 3, 6, 4, 6, 5, 1, 3, 1, 4, 2, 6, 1, 3, 5, 2, 3, 4, 6, 1, 5, 5, 6, 1, 3, 1, 2, 6, 5, 5, 3, 1, 1, 3, 1, 6, 2, 2, 3, 2, 2, 6, 6, 4, 5, 1, 6, 4, 4, 4, 2, 3, 1, 4, 1, 5, 3, 5, 3, 2, 2, 2, 3, 6, 1, 3, 6, 5, 6]



```python
def grader(g):
    if g >80:
        return "A"
    elif g<80 and g>60:
        return "B"
    else:
        return "C"
```


```python
grader(95),grader(50)
```




    ('A', 'C')




```python
def plo(x):
    A = 2.9
    B = 8.7
    C = 8.1
    
    y = A*x**2 + B*x + C + np.pi
    
    return y
```


```python
plo(1.2)
```




    25.857592653589794



### Class Circle

- Define a function which will take radious as input and provides area as output for a circle.


```python
def f(r):
    A = np.pi*r**2 
    return A
```


```python
f(3)
```




    28.274333882308138




```python
def area(r):
    A = np.pi*r**2 
    return A
```


```python
area(4)
```




    50.26548245743669



- Claculate the area of a sample circle of radius 10.


```python
a1 = area(10)
```


```python
print(a1)
```

    314.1592653589793


- Define a function which will take radious as input and provides circumference as output for a circle.


```python
def circumference(r):
    C = 2*np.pi*r
    return C
```

- Claculate the circumference of a sample circle of radius 10.


```python
circumference(10)
```




    62.83185307179586



- Lets build a class implementing above constants and functions


```python
class Circle():
    
    def __init__(self, supplied_r):
        self.r = supplied_r
          
    def area(self):
        A = np.pi*self.r**2
        return A
    
    def circumference(self):
        C = 2*np.pi*self.r
        return C
```

- Test using examples. Circle object can be created by calling ```Circle(5)``` and function ```area()``` can be applied later ot together.


```python
C = Circle(5)
C.area()
```




    78.53981633974483




```python
type(C)
```




    __main__.Circle




```python
C.r
```




    5




```python
C.circumference()
```




    31.41592653589793




```python
Circle(5).area()
```




    78.53981633974483




```python
CC = Circle(10)
CC.area(),CC.circumference(),CC.r
```




    (314.1592653589793, 62.83185307179586, 10)



- To use class and function object multiple time.


```python
for r in [2,3,6,24,25,46,567]:
    CC = Circle(r)
    print("radius: " , CC.r,\
          "area : " , CC.area(),\
          "circumf : " , CC.circumference())
```

    radius:  2 area :  12.566370614359172 circumf :  12.566370614359172
    radius:  3 area :  28.274333882308138 circumf :  18.84955592153876
    radius:  6 area :  113.09733552923255 circumf :  37.69911184307752
    radius:  24 area :  1809.5573684677208 circumf :  150.79644737231007
    radius:  25 area :  1963.4954084936207 circumf :  157.07963267948966
    radius:  46 area :  6647.610054996002 circumf :  289.02652413026095
    radius:  567 area :  1009987.480609929 circumf :  3562.5660691708254


### Class Gravity

- To create a function Gravity


```python
def gravity(m1,m2,d):
    F = (m1*m2)/d**2
    return F
```


```python
gravity(5,4,10)
```




    0.2



- Lets create a class ```Newton``` for Gravity calculation


```python
class Newton():
    
    def __init__(self,value_of_G, value_of_g, supplied_info):
        self.G = value_of_G
        self.info = supplied_info
        self.g = value_of_g
        
    def gravity(self,m1,m2,d):
        F = self.G*(m1*m2)/d**2
        print(self.info)
        return F  
    
    def gravity_pot(self,m1):
        F = m1*self.g
        return F      
```

- To create a object by calling a class with define inputs.


```python
N1 = Newton(value_of_G =6.7, value_of_g= 9.8,\
            supplied_info = "great job")
```

- To find constants and output of functions


```python
N1.G, N1.g,N1.gravity(2,3,13),N1.gravity_pot(12)
```

    great job





    (6.7, 9.8, 0.2378698224852071, 117.60000000000001)




```python
N1.gravity(m1=11,m2=12,d=3)
```

    great job





    98.26666666666667



### Class Dice

- Lets create a Class called ```Dice``` for fun


```python
class Dice(object):
    
    def __init__(self,A_value,B_value,C_value):
        self.pi = 3.14
        self.A = A_value
        self.B = B_value
        self.C = C_value 
    
    def find_sum(self,n1,n2):
        S = n1+n2
        return S
    
    def find_product(self,n1,n2):
        P = n1*n2
        return P
    
    def poly(self,x):
        pl = self.A*self.find_product(x,x) + self.B*x + self.C
        return pl
    
    def roll_dice(self):
        side = random.choice([1,2,3,4,5,6])
        return side
    
    def roll_two_dices(self):
        d1 = self.roll_dice()
        d2 = self.roll_dice()
        p = self.find_product(d1,d2)
        s = self.find_sum(d1,d2)
        return d1,d2,p,s
```

- To implement object created by class with predefined input


```python
A = 2.3; B=4.5; C =8.9
D = Dice(A,B,C)
```

- Can I ask this object for value of A, B and C?


```python
D.A, D.B, D.C
```




    (2.3, 4.5, 8.9)



- To roll a dice to get randum side


```python
D.roll_dice()
```




    4



- To roll two dice for two randum side. The ```roll_two_dices``` function implements ```find_sum()``` and ```find_product``` functions inside it.


```python
D.roll_two_dices()
```




    (2, 4, 8, 6)



- To roll a single dice and supply the output of single roll of dice to calculate polynomial function  by implementing ```poly``` function


```python
d = D.roll_dice()
D.poly(d)
```




    43.1



### References:
1. https://docs.python.org/3/tutorial/index.html
