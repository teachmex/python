## Learning from Errors

- 1. What is wrong here?


```python
# This is title

This is paragraph
```


    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    <ipython-input-1-9784fba40ee2> in <module>
          1 # This is title
          2 
    ----> 3 This is paragraph
    

    NameError: name 'This' is not defined


Note: [Learn more about Jupyter notebook functionalities](https://jupyter-notebook.readthedocs.io/en/stable/index.html)

- 2. What is wrong here?


```python
print "Hello world"
```


      File "<ipython-input-3-9fb80848b1b7>", line 1
        print "Hello world"
                          ^
    SyntaxError: Missing parentheses in call to 'print'. Did you mean print("Hello world")?



- 3. What is wrong here?


```python
for i in range(4):
print(i)
```


      File "<ipython-input-5-8ee9e742a8b8>", line 2
        print(i)
            ^
    IndentationError: expected an indented block



- 4. What is wrong here?


```python
L = [3,5,7]
L[3]
```


    ---------------------------------------------------------------------------

    IndexError                                Traceback (most recent call last)

    <ipython-input-13-e5031a802bc6> in <module>
          1 L = [3,5,7]
    ----> 2 L[3]
    

    IndexError: list index out of range


- 5. What is wrong here?


```python
A = npp.array([2,5,7])
```


    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    <ipython-input-8-c9813575a7f9> in <module>
    ----> 1 A = npp.array([2,5,7])
    

    NameError: name 'npp' is not defined



```python
def myfunction():
    x = random.randint()
    return x+10
```


```python
myfunction()
```


    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    <ipython-input-16-7b999452a26c> in <module>
    ----> 1 myfunction()
    

    <ipython-input-15-6920121cfd0d> in myfunction()
          1 def myfunction():
    ----> 2     x = random.randint()
          3     return x+10


    NameError: name 'random' is not defined



```python
def myfunction(x):
    return x+y
```


```python
myfunction(5)
```


    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    <ipython-input-18-8afb436c6a81> in <module>
    ----> 1 myfunction(5)
    

    <ipython-input-17-29ec7037f18c> in myfunction(x)
          1 def myfunction(x):
    ----> 2     return x+y
    

    NameError: name 'y' is not defined



```python
def myfunction(x):
    y=6
    return x+y
```


```python
myfunction(5)
```




    11




```python
y
```


    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    <ipython-input-22-9063a9f0e032> in <module>
    ----> 1 y
    

    NameError: name 'y' is not defined


6. What is wrong here?


```python
for i in range(5):
    print(5/i)

```


    ---------------------------------------------------------------------------

    ZeroDivisionError                         Traceback (most recent call last)

    <ipython-input-29-7f38f68db52f> in <module>
          1 for i in range(5):
    ----> 2     print(5/i)
    

    ZeroDivisionError: division by zero



```python

```


```python
open("imaginary.txt")
```


    ---------------------------------------------------------------------------

    FileNotFoundError                         Traceback (most recent call last)

    <ipython-input-30-2bedf9c67314> in <module>
    ----> 1 open("imaginary.txt")
    

    FileNotFoundError: [Errno 2] No such file or directory: 'imaginary.txt'



```python
L = [1,2,3,4]
type(L)
```




    list




```python
for k,v in L.items():
    print(k,v)
```


    ---------------------------------------------------------------------------

    AttributeError                            Traceback (most recent call last)

    <ipython-input-22-1284dd3b8bca> in <module>
    ----> 1 for k,v in L.items():
          2     print(k,v)


    AttributeError: 'list' object has no attribute 'items'


### Types of Error: 
[Learn more about Python errors](https://www.programiz.com/python-programming/exceptions)


|**Exception**|Cause of Error|
|--|--|
|**AssertionError**|Raised when an assert statement fails.|
|**AttributeError**|	Raised when attribute assignment or reference fails.|
| **EOFError**	|Raised when the input() function hits end-of-file condition.|
| **FloatingPointError**	|Raised when a floating point operation fails.|
| **GeneratorExit**	|Raise when a generator's close() method is called.|
| **ImportError**	|Raised when the imported module is not found.|
| **IndexError**	|Raised when the index of a sequence is out of range.|
| **KeyError**	|Raised when a key is not found in a dictionary.|
| **KeyboardInterrupt**	|Raised when the user hits the interrupt key (Ctrl+C or Delete).|
| **MemoryError**	|Raised when an operation runs out of memory.|
| **NameError**	|Raised when a variable is not found in local or global scope.|
| **NotImplementedError**	|Raised by abstract methods.|
| **OSError**	|Raised when system operation causes system related error.|
| **OverflowError**	|Raised when the result of an arithmetic operation is too large to be represented.|
| **ReferenceError**	|Raised when a weak reference proxy is used to access a garbage collected referent.|
| **RuntimeError**	|Raised when an error does not fall under any other category.|
| **StopIteration**	|Raised by next() function to indicate that there is no further item to be returned by iterator.|
| **SyntaxError**	|Raised by parser when syntax error is encountered.|
| **IndentationError**	|Raised when there is incorrect indentation.|
| **TabError**	|Raised when indentation consists of inconsistent tabs and spaces.|
| **SystemError**	|Raised when interpreter detects internal error.|
| **SystemExit**	|Raised by sys.exit() function.|
| **TypeError**	|Raised when a function or operation is applied to an object of incorrect type.|
| **UnboundLocalError**	|Raised when a reference is made to a local variable in a function or method, but no value has been bound to that variable.|
| **UnicodeError**	|Raised when a Unicode-related encoding or decoding error occurs.|
| **UnicodeEncodeError**	|Raised when a Unicode-related error occurs during encoding.|
| **UnicodeDecodeError**	|Raised when a Unicode-related error occurs during decoding.|
| **UnicodeTranslateError**	|Raised when a Unicode-related error occurs during translating.
| **ValueError**	|Raised when a function gets an argument of correct type but improper value.|
| **ZeroDivisionError**	|Raised when the second operand of division or modulo operation is zero.|

### Exception Handeling

[Learn more in builtin exceptions](https://docs.python.org/3/library/exceptions.html)


```python
D = {"1344":234.98,"2564":345.97,"3345":367.95,"#":358.63,"*":283.54}
```


```python
for k,v in D.items():
        k = int(k)
```


    ---------------------------------------------------------------------------

    ValueError                                Traceback (most recent call last)

    <ipython-input-2-6fae1746f8e5> in <module>
          1 for k,v in D.items():
    ----> 2         k = int(k)
    

    ValueError: invalid literal for int() with base 10: '#'



```python
int_dict = {}
non_int_dict = {}
for k,v in D.items():
    try:
        int_dict.update({int(k):v})
        print("this is integer", k)
    except:
        non_int_dict.update({k:v})
        print('this is not integer',k)
```

    this is integer 1344
    this is integer 2564
    this is integer 3345
    this is not integer #
    this is not integer *



```python
int_dict
```




    {1344: 234.98, 2564: 345.97, 3345: 367.95}




```python
non_int_dict
```




    {'#': 358.63, '*': 283.54}




```python

```
