## [The Python Standard Library](https://docs.python.org/3/library/index.html)

Python’s standard library is very extensive, offering a wide range of facilities as indicated by the long table of contents listed below. The library contains built-in modules (written in C) that provide access to system functionality such as file I/O that would otherwise be inaccessible to Python programmers, as well as modules written in Python that provide standardized solutions for many problems that occur in everyday programming. Some of these modules are explicitly designed to encourage and enhance the portability of Python programs by abstracting away platform-specifics into platform-neutral APIs.

### ```string```


```python
for i in range(5):
    for j in range(2):
        print("this is  ({},{}) integer".format(i,j))
```

    this is (0,0) integer
    this is (0,1) integer
    this is (1,0) integer
    this is (1,1) integer
    this is (2,0) integer
    this is (2,1) integer
    this is (3,0) integer
    this is (3,1) integer
    this is (4,0) integer
    this is (4,1) integer



```python
import re  
  
s = 'Hello from shubhamg199630@gmail.com to priya@yahoo.com about\
    the meeting @2PM. Can we meet today for an important decision?\
    Based on previous meeting minute we had decided to write an emailto\
    abc@example.com. In case we do not get reply.\
    Hello from shubhamg@gmail.com to priya2@yahoo.com about\
    the meeting @2PM. Can we meet today for an important decision?\
    Based on previous meeting minute we had decided to write an emailto\
    abcd@example.com. In case we do not get reply\
    Hello from shubhamg19@gmail.com to priya5@yahoo.com about\
    the meeting @2PM. Can we meet today for an important decision?\
    Based on previous meeting minute we had decided to write an emailto\
    abct@example.com. In case we do not get reply'
   
lst = re.findall('\S+@\S+', s)     
print(lst)
```

    ['shubhamg199630@gmail.com', 'priya@yahoo.com', 'abc@example.com.', 'shubhamg@gmail.com', 'priya2@yahoo.com', 'abcd@example.com.', 'shubhamg19@gmail.com', 'priya5@yahoo.com', 'abct@example.com.']


### ```collections```


```python
from collections import namedtuple
```


```python
point = namedtuple('Point', ['x', 'y'])
```


```python
point(11,12)
```




    Point(x=11, y=12)




```python
point(2,3)
```




    Point(x=2, y=3)




```python
from collections import Counter
```


```python
A = [ 1,3,5,6,8,6,5,4,5,6,5,4,3,2]
Counter(A)
```




    Counter({1: 1, 3: 2, 5: 4, 6: 3, 8: 1, 4: 2, 2: 1})



### ```itertools```


```python
from itertools import permutations
L = ["a","b","c","d","e"]
for item in permutations(L,2):
    print(item)
```

    ('a', 'b')
    ('a', 'c')
    ('a', 'd')
    ('b', 'a')
    ('b', 'c')
    ('b', 'd')
    ('c', 'a')
    ('c', 'b')
    ('c', 'd')
    ('d', 'a')
    ('d', 'b')
    ('d', 'c')



```python
for item in permutations(L,3):
    print(item)
```

    ('a', 'b', 'c')
    ('a', 'b', 'd')
    ('a', 'c', 'b')
    ('a', 'c', 'd')
    ('a', 'd', 'b')
    ('a', 'd', 'c')
    ('b', 'a', 'c')
    ('b', 'a', 'd')
    ('b', 'c', 'a')
    ('b', 'c', 'd')
    ('b', 'd', 'a')
    ('b', 'd', 'c')
    ('c', 'a', 'b')
    ('c', 'a', 'd')
    ('c', 'b', 'a')
    ('c', 'b', 'd')
    ('c', 'd', 'a')
    ('c', 'd', 'b')
    ('d', 'a', 'b')
    ('d', 'a', 'c')
    ('d', 'b', 'a')
    ('d', 'b', 'c')
    ('d', 'c', 'a')
    ('d', 'c', 'b')


### ```os```


```python
import os
path = "plot"
os.path.isdir(path)
```




    True




```python
path = "1. DataStructure.ipynb"
os.path.isfile(path)
```




    True




```python
os.listdir()
```




    ['.git',
     '.gitignore',
     '.ipynb_checkpoints',
     '1. DataStructure.ipynb',
     '1.1-MiniAssignment-DNAcount.ipynb',
     '2. LoopAndCondition.ipynb',
     '3. Input and Output.ipynb',
     '4. FunctionAndClass.ipynb',
     '5. Learning from Errors.ipynb',
     '6. The Python Standard Library.ipynb',
     'data',
     'Learning to read error.ipynb',
     'plot',
     'Project1-Fern-I.ipynb',
     'Project2-Rwalk.ipynb',
     'Project3-Ncharges.ipynb',
     'Project4-Diffusion.ipynb',
     'Project5-Fern-II.ipynb',
     'README.md']




```python
import os 

# Running the aforementioned command and saving its output 
output = os.popen('wmic process get description, processid').read() 

# Displaying the output 
print(output[0:1000]) 

```

    Description                       ProcessId  
    
    System Idle Process               0          
    
    System                            4          
    
    Registry                          96         
    
    smss.exe                          416        
    
    csrss.exe                         640        
    
    csrss.exe                         744        
    
    wininit.exe                       772        
    
    services.exe                      820        
    
    lsass.exe                         868        
    
    winlogon.exe                      940        
    
    svchost.exe                       392        
    
    svchost.exe                       576        
    
    fontdrvhost.exe                   592        
    
    fontdrvhost.exe                   588        
    
    WUDFHost.exe                      564        
    
    svchost.exe                       1068       
    
    svchost.exe                       1120       
    
    dwm.exe                           1208       
    
    svchost.exe                       1344       
    
    svchost.exe                       1352       
    
    svchost.exe  


### ```glob```


```python
import glob
glob.glob('*.ipynb')
```




    ['1. DataStructure.ipynb',
     '1.1-MiniAssignment-DNAcount.ipynb',
     '2. LoopAndCondition.ipynb',
     '3. Input and Output.ipynb',
     '4. FunctionAndClass.ipynb',
     '5. Learning from Errors.ipynb',
     '6. The Python Standard Library.ipynb',
     'Learning to read error.ipynb',
     'Project1-Fern-I.ipynb',
     'Project2-Rwalk.ipynb',
     'Project3-Ncharges.ipynb',
     'Project4-Diffusion.ipynb',
     'Project5-Fern-II.ipynb']



### ```time```


```python
import time

t1 = time.time()
for i in range(1000001):
    if i==1000000:
        print("done!")

t2 = time.time()
t2-t1
```

    done!





    0.09277701377868652



### ```urllib```


```python
ff = open('data/web.txt','w')
```


```python
import urllib.request
import urllib.parse
params = urllib.parse.urlencode({'spam': 1, 'eggs': 2, 'bacon': 0})
url = "http://www.python.org"
with urllib.request.urlopen(url) as f:
     ff.write(f.read().decode('utf-8'))
        
ff.close()
```

### ```tqdm```


```python
import time
from tqdm import tqdm

mylist = [i for i in range(100)]

for i in tqdm(mylist):
    time.sleep(0.5)
```

    100%|██████████| 100/100 [00:50<00:00,  1.99it/s]



```python

```
