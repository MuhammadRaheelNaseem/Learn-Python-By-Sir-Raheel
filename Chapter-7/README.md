# <span style='color:green, font-family; times, serif; font-size:30pt; font-style:italic'>Chapter No # 7 <u>Functions</u></span>

* What is function
* Syntax Of Function,
* Writing And Calling Functions
* One Parameter & One Argument Function,
* Two Parameter & Two Argument Function,
* Three Parameter & Three Argument Function,
* Four Parameter & Four Argument Function,
* Multiple Parameter & Multiple Arguments,
* **Args Functions,
* **Kwargs Functions,
* Local And Global Variable
* Nested Functions,
* Making Library With Functions,
* Built-In Function,
* Mudules,
* Annonymous Function
* Map, Filter & Reduce Function
* Decorators

# <li style="font-size:20pt;">What is Functions</li>

Functions in Python provide organized, reusable and modular code to perform a set of specific actions. Functions
simplify the coding process, prevent redundant logic, and make the code easier to follow. This topic describes the
declaration and utilization of functions in Python.

Python has many built-in functions like <span style="color: orange;"><b>print()</b></span>.,<span style="color: green;"><b>input()</b></span>, <span style="color: blue;"><b>len()</b></span>. Besides built-ins you can also create your own
functions to do more specific jobs—these are called user-defined functions.


# <li style="font-size:20pt;">Syntax Of Function</li>
<pre>
def function_name(parameter):
    """doc string"""
    expression
    statement(s)

</pre>

# <li style="font-size:20pt;">Writing And Calling Functions</li>


```python
def square(): #function to find square of a number
    """This function is used for only square"""  # """doc string"""
    x = 2**2  # epression
    print(x)  # statement

square()
```

    4
    


```python
def myfunc(): # function with no parameter
    print("Hello, I'm from function") # statement
    
myfunc() # calling the function | function with no argument
```

    Hello, I'm from function
    


```python
def greet():
    print("Hello")
    
greet()
```

    Hello
    


```python
def greeting():
    print("This is the 1st program of function")
    print("It is building block")
greeting() # Calling function
```

    This is the 1st program of function
    It is building block
    


```python
def myfunc(): # function with no parameters
    print("Hello Python programmers")
myfunc() # function with no arguments
```

    Hello Python programmers
    


```python
def myfunc(): # function with no parameters
    x = 5
    y = 20
    z = x + y # expression
    print("Total of z is: ",z)
myfunc() # function with no arguments
```

    Total of z is:  25
    


```python
def myfunc(): # function with no parameters
    name = "Python"
    call = "Hello "+ name
    print(call)
myfunc() # function with no arguments
```

    Hello Python
    

# <li style="font-size:20pt;">One Parameter & One Argument Function</li>



```python
def myfunc(fname): # function with one paramenter
    print("First Name "+ fname)

myfunc("Asad") # function with one argument
```

    First Name Asad
    


```python
def myfunc(fname): # function with one paramenter
    print("First Name "+ fname)

myfunc() # function with one argument
```


    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    Cell In[1], line 4
          1 def myfunc(fname): # function with one paramenter
          2     print("First Name "+ fname)
    ----> 4 myfunc()
    

    TypeError: myfunc() missing 1 required positional argument: 'fname'



```python
def square (n): #function to find square of a number
    """This function is used for only square"""
    n= n*n
    print(n)

square(20)
```

    400
    


```python
def even_odd (num): #Even odd test
    """ This function will check whether a number is even or odd"""
    if num % 2 ==0:
        print (num, ' is even number')
    else:
        print (num, ' is odd number')
even_odd(40)
```

    40  is even number
    


```python
def get(name):
    print("Name: ",name)
    
a=input("Enter Name: ")

get(a)
```

    Enter Name: Raheel
    Name:  Raheel
    


```python
def greet_two(greeting="Howdy"):
    print(greeting)
greet_two()
```

    Howdy
    


```python
def factorial(num): # Calculate factorial of a number using recursive function c 4x3x2x1=24
    if num <=1 :
        return 1
    else:
        return num * factorial(num-1)

factorial(4)
```




    24



# <li style="font-size:20pt;">Two Parameter & Two Argument Function</li>



```python
def details(name,userid): # Function to print User details
    print('Name :- ', name)
    print('User ID is :- ', userid)
    
details('Raheel',12312313123)

```

    Name :-  Raheel
    User ID is :-  12312313123
    


```python
def addition(a,b):
    print("The first value is: ",a)
    print("The second value is: ",b)
    print("The result is: ",a+b)
addition(10,20) # Calling function
```

    The first value is:  10
    The second value is:  20
    The result is:  30
    


```python
def info(fname, lname):
    print("First Name: ",fname)
    print("Last Name: ",lname)
    
info("Raheel","Naseem")
```

    First Name:  Raheel
    Last Name:  Naseem
    


```python
def add_numbers(first_number, second_number):
    total = first_number + second_number
    print(total)
add_numbers(2,8)
```

    10
    


```python
def AreaPerameter(a,b):
    a = int(a)
    b = int(b)
    print("Length is: ",a)
    print("Breadth is: ",b)
    Area = a * b
    Perameter = 2*a + 2*b
    print("The result of area is: ",Area)
    print("The result of perameter is: ",Perameter)
    return

h = input("Enter length ")
w = input("Enter width ")
AreaPerameter(h,w)
```

    Enter length 12
    Enter width 32
    Length is:  12
    Breadth is:  32
    The result of area is:  384
    The result of perameter is:  88
    


```python
print("-----Addition-----")
def addition(x,y):
    print("The first value is: ",x)
    print("The second value is: ",y)
    print("The result is: ",x+y)
addition(100,20) # Calling function
print()
# for subtraction
print("-----Subtraction-----")
def subtraction(x,y):
    print("The first value is: ",x)
    print("The second value is: ",y)
    print("The result is: ",x-y)
subtraction(50,20) # Calling function
print()
# for multiplacation
print("-----Multiplacation-----")
def multiplacation(x,y):
    print("The first value is: ",x)
    print("The second value is: ",y)
    print("The result is: ",x*y)
multiplacation(5,10) # Calling function
print()
# for division
print("-----Division-----")
def division(x,y):
    print("The first value is: ",x)
    print("The second value is: ",y)
    print("The result is: ",x/y)
division(36,4) # Calling function
print()
# for reminder
print("-----Reminder-----")
def reminder(x,y):
    print("The first value is: ",x)
    print("The second value is: ",y)
    print("The result is: ",x%y)
reminder(50,20) # Calling function
```

    -----Addition-----
    The first value is:  100
    The second value is:  20
    The result is:  120
    
    -----Subtraction-----
    The first value is:  50
    The second value is:  20
    The result is:  30
    
    -----Multiplacation-----
    The first value is:  5
    The second value is:  10
    The result is:  50
    
    -----Division-----
    The first value is:  36
    The second value is:  4
    The result is:  9.0
    
    -----Reminder-----
    The first value is:  50
    The second value is:  20
    The result is:  10
    

# <li style="font-size:20pt;">Three Parameter & Three Argument Function</li>



```python
def fullname (firstname , middlename ,lastname): #Concatenate Strings
    fullname = "{} {} {}".format(firstname,middlename,lastname)
    print (fullname)
fullname('Muhammad' , 'Raheel' , 'Naseem')
```

    Muhammad Raheel Naseem
    


```python
def fullname (firstname , middlename ,lastname): #Concatenate Strings
    fullname = "{} {} {}".format(firstname,middlename,lastname)
    print (fullname)
fullname(lastname = 'Bhat' , middlename='Ali' , firstname='Asif') 
```

    Asif Ali Bhat
    

# <li style="font-size:20pt;">Multiple Parameter & Multiple Arguments Using "**args"</li>
`**args`

*args allows us to pass a variable number of non-keyword arguments to a Python function. In the function, we should use an asterisk (*) before the parameter name to specify how many arguments we want to pass to the function.


```python
def func1(*args):
    print(args)
func1(1,2,3,4,5,6,7,8,9,10)

```

    (1, 2, 3, 4, 5, 6, 7, 8, 9, 10)
    


```python
def func1(*args):
    for i in args:
        print(i)
func1(1,2,3,4,5,6,7,8,9,10)

```

    1
    2
    3
    4
    5
    6
    7
    8
    9
    10
    


```python
def UserDetails(*args):
    print(args)  
    
UserDetails("Raheel",23424,"sdfsdfsdf",123123)

```

    ('Raheel', 23424, 'sdfsdfsdf', 123123)
    


```python
def my_function(*prog):
    print("The youngest programming is " + prog[0])

my_function("Typescript", "C++", "Java")
```

    The youngest programming is Typescript
    


```python
def func(*args):
    # args will be a tuple containing all values that are passed in
    for i in args:
        print(i)
func(1, 2, 3) # Calling it with 3 arguments
```

    1
    2
    3
    

# <li style="font-size:20pt;">Multiple Parameter & Multiple Arguments Using "**kwargs"</li>
Python uses a special syntax called kwargs in function definitions. It is used to pass through a keyworded, variable-length argument list. The double star in the name allows us to pass any number of arguments, or keywords, through a function's definition.


```python
def UserDetails(**kwargs): # **kwards use only dictionary
    print(kwargs)
        
UserDetails(Name='Raheel' , ID=7412 , Pincode=41102 , Age= 33)
```

    {'Name': 'Raheel', 'ID': 7412, 'Pincode': 41102, 'Age': 33}
    


```python
def UserDetails(**kwargs):
    for key,val in kwargs.items():
        print("{} :- {}".format(key,val))
UserDetails(Name='Raheel' , ID=7412 , Pincode=41102 , Age= 300 , Country= 'Pakistan',language='Urdu')
```

    Name :- Raheel
    ID :- 7412
    Pincode :- 41102
    Age :- 300
    Country :- Pakistan
    language :- Urdu
    


```python
mydict = {'Name': 'Asif', 'ID': 7412, 'Pincode': 41102, 'Age': 33, 'Country': "Pakistan","language":"Urdu"}
UserDetails(**mydict)
```

    Name :- Asif
    ID :- 7412
    Pincode :- 41102
    Age :- 33
    Country :- Pakistan
    language :- Urdu
    


```python
def intro(**data):
    print("\nData type of argument:",type(data))

    for key, value in data.items():
        print("{} is {}".format(key,value))

intro(Firstname="Ali", Lastname="Imran", Age=22, Phone=1234567890)
intro(Firstname="John", Lastname="Malton", Email="johnmalton@nomail.com", Country="Wakanda", Age=25, Phone=9876543210)
```

    
    Data type of argument: <class 'dict'>
    Firstname is Ali
    Lastname is Imran
    Age is 22
    Phone is 1234567890
    
    Data type of argument: <class 'dict'>
    Firstname is John
    Lastname is Malton
    Email is johnmalton@nomail.com
    Country is Wakanda
    Age is 25
    Phone is 9876543210
    

# <li style="font-size:20pt;">Local And Global Variable</li>

## `Local Variable`
In Python or any other programming languages, the definition of local variables remains the same, which is "A variable declared inside the function is called local function". We can access a local variable inside but not outside the function.

## `Global Variable`
Python allows you to access global variables in a program both inside and outside of a function. A global variable in Python is often declared as the top of the program, or the beginning of a program.


```python
def f():
    # local variable
    s = "I love Python"
    print(s)

f()

```

    I love Python
    


```python
def add():
    c = 2
    print(c)
add() 
```

    2
    


```python
def calling():
    y="Hello: ","Python"
    print(y)
calling()
```

    ('Hello: ', 'Python')
    


```python
c = 1
def add():
    c=c+2
    print(c)
add() # Raise Error its global scop 
```


    ---------------------------------------------------------------------------

    UnboundLocalError                         Traceback (most recent call last)

    ~\AppData\Local\Temp\ipykernel_11484\3093420356.py in <module>
          3     c=c+2
          4     print(c)
    ----> 5 add() # Raise Error its global scop
    

    ~\AppData\Local\Temp\ipykernel_11484\3093420356.py in add()
          1 c = 1
          2 def add():
    ----> 3     c=c+2
          4     print(c)
          5 add() # Raise Error its global scop
    

    UnboundLocalError: local variable 'c' referenced before assignment



```python
y = "Python"
def calling():
    y="Hello: ",y
    print(y)
calling()
```


    ---------------------------------------------------------------------------

    UnboundLocalError                         Traceback (most recent call last)

    <ipython-input-5-e7acc4035cce> in <module>
          3     y="Hello: ",y
          4     print(y)
    ----> 5 calling()
    

    <ipython-input-5-e7acc4035cce> in calling()
          1 y = "Python"
          2 def calling():
    ----> 3     y="Hello: ",y
          4     print(y)
          5 calling()
    

    UnboundLocalError: local variable 'y' referenced before assignment



```python
def foo():
    z = "local"


foo()
print(z)
```


    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    <ipython-input-6-903d3f57d2bf> in <module>
          4 
          5 foo()
    ----> 6 print(z)
    

    NameError: name 'z' is not defined



```python
c=0
def add():
    global c
    c+=10
    print("Inside add function: ",c)
add()
# print("Outside add function: ",c)
```

    Inside add function:  10
    


```python
x = "global "

def foo():
    global x
    y = "local"
    x = x * 2
    print(x)
    print(y)

foo()
```

    global global 
    local
    

# <li style="font-size:20pt;">Nested Functions</li>



```python
# Python program to illustrate
# nested functions
def outerFunction(text):
    text = text
    
    def innerFunction():
        print(text)

    innerFunction()

outerFunction('Hey !')

```

    Hey !
    


```python
def function1(): # outer function
    print ("Hello from outer function")
    def function2(): # inner function
        print ("Hello from inner function")
    function2()
    
function1()
```

    Hello from outer function
    Hello from inner function
    


```python
def num1(x):
    def num2(y):
        return x * y
    return num2

res = num1(10)

print(res(5))
```

    50
    


```python
def function1(): # outer function
    x = 2 # A variable defined within the outer function
    def function2(a): # inner function
       # Let's define a new variable within the inner function
       # rather than changing the value of x of the outer function
        x = 6
        print (a+x)
    print (x) # to display the value of x of the outer function
    function2(3)

function1()
```

    2
    9
    


```python
def function1(name):
    def function2():
        print('Hello ' + name)
    return function2

func = function1('Nichola Tesla')
func()
```

    Hello Nichola Tesla
    

# <li style="font-size:20pt;">Making Library With Functions</li>

### Save this code with this name 
## `calculator.py`
<pre>
# for addition
def addition(x,y):
    return x+y

# for subtraction
def subtraction(x,y):
    return x-y

# for multiplacation
def multiplacation(x,y):
    return x*y

# for division
def division(x,y):
    return x/y

# for reminder
def reminder(x,y):
    return x%y
    
</pre>

### Then import like blow code


```python
import calculator

calculator.addition(2,25)
```




    27




```python
from calculator import subtraction

subtraction(50,6)
```




    44




```python
from calculator import *

division(20,2)
```




    10.0



# <li style="font-size:20pt;">Built-In Function</li>



```python
number = 9

# eval performs the multiplication passed as argument
square_number = eval('number * number')
print(square_number)

```

    81
    


```python
name = input("Enter your name: ")
print(name)

```

    Enter your name: Raheel
    Raheel
    


```python
numbers = [9, 34, 11, -4, 27]

# find the smallest number
min_number = min(numbers)
print(min_number)
```

    -4
    


```python
seq_string = 'Python'

# reverse of a string
print(list(reversed(seq_string)))
```

    ['n', 'o', 'h', 't', 'y', 'P']
    


```python
numbers = [4, 2, 12, 8]

sorted_numbers = sorted(numbers)
print(sorted_numbers)
```

    [2, 4, 8, 12]
    


```python
languages = ['Java', 'Python', 'JavaScript']
versions = [14, 3, 6]

result = zip(languages, versions)
print(dict(result))
```

    {'Java': 14, 'Python': 3, 'JavaScript': 6}
    


```python
languages = ['Java', 'Python', 'JavaScript']
versions = [14, 3, 6]

result = zip(languages, versions)
print(list(result))
```

    [('Java', 14), ('Python', 3), ('JavaScript', 6)]
    

# <li style="font-size:20pt;">Annonymous Function</li>

Lambda functions are used when you need a function for a short period of time. This is commonly when you want to pass a function as an argument to higher-order functions. A Lambda function can take any number of arguments, but can only have one expression.

Lambda function is also a annonymous function (function without a name).
![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/be17d43a-7c4e-4990-8146-9ffcfefd4de2)
![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/08256b44-3525-4927-99ee-80c0fdbf21ea)


```python
addition = lambda a : a + 10 # This lambda function adds value 10 to an argument
print(addition(50))
```

    60
    


```python
product = lambda a, b : a * b #This lambda function takes two arguments (a,b) and
print(product(5, 56))
```

    280
    


```python
addition = lambda a, b, c : a + b + c #This lambda function takes three argument
print(addition(5, 6, 2))

```

    13
    


```python
res = (lambda *args: sum(args))
# res(10,20)
# res(10,20,30,40)
res(10,20,30,40,50,60,70)

```




    280




```python
res1 = (lambda **kwargs: sum(kwargs.values())) # This lambda function can take an
res1(a = 10 , b= 20 , c = 30)

# res1(a = 10 , b= 20 , c = 30, d = 40)
```




    60




```python
dic = (lambda **kwargs: kwargs)
dic(Name="raheel",ID=65456)
```




    {'Name': 'raheel', 'ID': 65456}



# <li style="font-size:20pt;">Map, Filter & Reduce Function</li>
Three new functions have been introduced in the latest version of Python that provide a more elegant and short-hand approach to some problems. The map() and filter() and reduce() functions bring a bit of functional programming to Python. All three of these are convenience functions that can be replaced with List Comprehensions or loops, but provide a cleaner way of working with data.

## The map() Function
The map() function iterates through all items in the given iterable and executes the function we passed as an argument on each of them.

The syntax is:

map(function, iterable(s))


```python
# Without using lambdas
def starts_with_A(s):
    return s[0] == "A"

fruit = ["Apple", "Banana", "Pear", "Apricot", "Orange"]
map_object = map(starts_with_A, fruit)

print(list(map_object))
```

    [True, False, False, True, False]
    


```python
fruit = ["Apple", "Banana", "Pear", "Apricot", "Orange"]
map_object = map(lambda s: s[0] == "A", fruit)

print(list(map_object))
```

    [True, False, False, True, False]
    

## The filter() Function
Similar to map(), filter() takes a function object and an iterable and creates a new list.

As the name suggests, filter() forms a new list that contains only elements that satisfy a certain condition, i.e. the function we passed returns True.

The syntax is:

filter(function, iterable(s))


```python
def starts_with_A(s):
    return s[0] == "A"

fruit = ["Apple", "Banana", "Pear", "Apricot", "Orange"]
filter_object = filter(starts_with_A, fruit)

print(list(filter_object))
```

    ['Apple', 'Apricot']
    


```python
fruit = ["Apple", "Banana", "Pear", "Apricot", "Orange"]
filter_object = filter(lambda s: s[0] == "A", fruit)

print(list(filter_object))
```

    ['Apple', 'Apricot']
    

## The reduce() Function
reduce() works differently than map() and filter(). It does not return a new list based on the function and iterable we've passed. Instead, it returns a single value.

Also, in Python 3 reduce() isn't a built-in function anymore, and it can be found in the functools module.

The syntax is:

reduce(function, sequence[, initial])


```python
from functools import reduce

def add(x, y):
    return x + y

list = [2, 4, 7, 3]
print(reduce(add, list))
```

    16
    


```python
from functools import reduce

list = [2, 4, 7, 3]
print(reduce(lambda x, y: x + y, list))
print("With an initial value: " + str(reduce(lambda x, y: x + y, list, 10)))
```

    16
    With an initial value: 26
    

# <li style="font-size:20pt;">Decorators</li>
Decorators are a design pattern in Python that allows a user to add new functionality to an existing object without modifying its structure. A few good examples are when you want to add logging, test performance, perform caching, verify permissions, and so on. You can also use one when you need to run the same code on multiple functions.


```python
def decorator(func):
    def inner_deco():
        print("I'm inside decorator function")
        func()
        print("I'm inner_deco function")
    return inner_deco

def num():
    print()
    print("We will us this 'num' function")
    print("I'll use as the decorator!")
    print()
    
new = decorator(num)
new()
```

    I'm inside decorator function
    
    We will us this 'num' function
    I'll use as the decorator!
    
    I'm inner_deco function
    


```python
def decorator(func):
    def inner_deco():
        print("I'm inside decorator function")
        func()
        print("I'm inner_deco function")
    return inner_deco

def num():
    print()
    print("We will us this 'num' function")
    print("I'll use as the decorator!")
    print()
    
new = decorator(num)
new()
```

    I'm inside decorator function
    
    We will us this 'num' function
    I'll use as the decorator!
    
    I'm inner_deco function
    


```python
def decorator(num):
    def inner_deco():
        print("I'm inside decorator function")
        num()
        print("I'm inner_deco function")
    return inner_deco

@decorator
def num():
    print()
    print("We will us this 'num' function")
    print("I'll use as the decorator!")
    print()
    
num()
```

    I'm inside decorator function
    
    We will us this 'num' function
    I'll use as the decorator!
    
    I'm inner_deco function
    


```python
def decorat(fun):
    def inner():
        a = fun()
        add = a + 10
        print(add)
    return inner

def num():
    return 10

main = decorat(num)
main()
```

    20
    


```python
def decorat(num):
    def inner():
        a = num()
        add = a + a
        return add
    return inner

@decorat
def num():
    return 10

num()
```




    20




```python
def hello_decorator(func):
    def inner1():
        print("Hello, this is before function execution")
        func()
        print("This is after function execution")
    return inner1

def function_to_be_used():
    print("This is inside the function !!")

function_to_be_used = hello_decorator(function_to_be_used)
function_to_be_used()

```

    Hello, this is before function execution
    This is inside the function !!
    This is after function execution
    


```python
def hello_decorator(func):
    def inner1():
        print("Hello, this is before function execution")
        func()
        print("This is after function execution")
    return inner1
@hello_decorator
def function_to_be_used():
    print("This is inside the function !!")

function_to_be_used()
# function_to_be_used = hello_decorator(function_to_be_used)
# function_to_be_used()

```

    Hello, this is before function execution
    This is inside the function !!
    This is after function execution
    


```python
def smart_divide(func):
    print("func parameter: ",func)
    def inner(a, b):
        print("inner ",a,"\n Inner ",b)
        print("I am going to divide", a, "and", b)
        if b == 0:
            print("Whoops! cannot divide")
            return
        return func(a, b)
    return inner

@smart_divide
def divide(a, b):
    print(a/b)
    
divide(8,0)
```

    func parameter:  <function divide at 0x000001C771062708>
    inner  8 
     Inner  0
    I am going to divide 8 and 0
    Whoops! cannot divide
    

-----------------------
