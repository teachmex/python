# Functions and Classes

Function and Class are required for object oriented programming. Functions, once created, can be implemented multiple times while Class is more useful for both data encaptulation and functions.


```python
import numpy as np
import random as random
```

### Class Circle

- Define a function which will take radious as input and provides area as output for a circle.


```python
def area(r):
    A = np.pi*r**2
    return A
```

- Claculate the area of a sample circle of radius 10.


```python
area(10)
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
    def __init__(self, r):
        self.r = r
          
    def area(self):
        A = np.pi*self.r**2
        return A
    
    def circumference(self):
        C = 2*np.pi*self.r
        return C
```

- Test using examples. Circle object can be created by calling ```Circle(5)``` and function ```area()``` can be applied later ot together.


```python
Circle(5).area()
```




    78.53981633974483




```python
CC = Circle(5)
CC.area(),CC.circumference()
```




    (78.53981633974483, 31.41592653589793)



- Sililar to the functions, a data can be called from class object.


```python
CC.r
```




    5



- To use class and function object multiple time.


```python
for r in [2,3,6,24,25,46,567]:
    CC = Circle(r)
    print("radius: " , r,\
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


