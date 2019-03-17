
# Functions and Classes

---------


```python
import numpy as np
```

### Class Circle

Define a function which will take radious as input and provides area as output for a circle.


```python
def area(r):
    A = np.pi*r**2
    return A
```

Claculate the area of a sample circle of radius 10.


```python
area(10)
```




    314.1592653589793



Define a function which will take radious as input and provides circumference as output for a circle.


```python
def circumference(r):
    C = 2*np.pi*r
    return C
```

Claculate the circumference of a sample circle of radius 10.


```python
circumference(10)
```




    62.83185307179586



Lets build a class implementing above constants and functions


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

Test using examples


```python
Circle(5).area()
```




    78.53981633974483




```python
CC = Circle(5)
CC.area(),CC.circumference()
```




    (78.53981633974483, 31.41592653589793)




```python
CC.r
```




    5




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


---------------

### Class Gravity


```python
def gravity(m1,m2,d):
    F = (m1*m2)/d**2
    return F
```


```python
gravity(5,4,10)
```




    0.2



Lets create a class for Gravity calculation


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


```python
N1 = Newton(value_of_G =6.7, value_of_g= 9.8,\
            supplied_info = "great job")
```


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



---------

------------
