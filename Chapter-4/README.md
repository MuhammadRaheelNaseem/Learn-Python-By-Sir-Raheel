# <span style='color:green, font-family; times, serif; font-size:30pt; font-style:italic'>Chapter No # 4 Variables & Operators</span>

* What Is Variable?,
* Declaration Of Variables, 
* Assign Values To Variables, 
* Types Of Python Variables.
* Legal Or Ill Legal Variable
* What Is Data Type?,
* Arithmetic Operators,
* Assignment Operators,
* Comparison Operators,
* Logical Operators,
* Identity Operators,
* Membership Operators,
* Bitwise Operators,
* Python Numbers,
* Python Strings,
* String - Single Quotes Or In Double Quotes Or In Three Double Quotes,
* Finding String Length,
* Concatenating Strings, 
* Cases Type,

# <li style="font-size:20pt">What Is Variable?</li>
A Python variable is a reserved memory location to store values. In other words, a variable in a python program gives data to the computer for processing. Once an object is assigned to a variable, you can refer to the object by that name. But the data itself is still contained within the object.

# <li style="font-size:20pt">Declaration Of Variables | Assign Values To Variables</li>


```python
var = "first variable"
print(var)
print(type(var))
```

    first variable
    <class 'str'>
    


```python
a = 100 
print (a)
print(type(a))
```

    100
    <class 'int'>
    


```python
x = True 
print(x)
print(type(x))
```

    True
    <class 'bool'>
    


```python
y = 3+5j
print(y)
```

    (3+5j)
    


```python
firstvariable = "Hello world"
print(firstvariable)
```

    Hello world
    

# <li style="font-size:20pt">Types Of Python Variables</li>

Python allows you to get the type of a variable by inspecting its type. In Python, everything is an object - so when you use the type() function to print out a value, it returns the class type of the object.

![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/2b6fd6f5-d4d4-4898-9cc3-53696810dcc1)


```python
string = "Hello"

print(string)
```

    Hello
    


```python
integer = 12
print(integer)
```

    12
    


```python
floatt = 12.3
print(floatt)
```

    12.3
    


```python
boolean = True       # ture = 1 | False = 0 | 1, 0 is also know bool
print(boolean)
```

    True
    


```python
complexx = 5+9j      # complex only support j
print(complexx)
```

    (5+9j)
    

# <li style="font-size:20pt">Legal Or Ill Legal Variable</li>
A variable name must start with a letter or the underscore character. A variable name can only contain alpha-numeric characters and underscores (A-z, 0-9, and _). Variable names are case-sensitive (age, Age and AGE are three different variables).

![image.png](attachment:image.png)

`1. Variable name should start with letter(a-zA-Z) or underscore (_).`

`Legal:`age, _age, Age.

`Illegal:`1age, 4plus5.

`2.In variable name, no special characters allowed other than underscore (_).`

`Legal:`_age, age_.

`Illegal:`age_*, +age.

`3.Variables are case sensitive.`

age and Age are different, since variable names are case sensitive.

`4.Variable name can have numbers but not at the beginning.`

`Legal:`Age1, Age2



```python
xyz = "Raheel"

print(xyz)
```

    Raheel
    


```python
# Legal Variable Names

age = 15
Age = 16
AGE = 17
_age = 18
aGe = 19
age_number = 20
ageNumber = 21

```


```python
# Illegal Variable Names

1age = 10
a.g.e = 11
$age = 12
```


      File "<ipython-input-54-fedfc811b5e8>", line 3
        1age = 10
         ^
    SyntaxError: invalid syntax
    


# <li style="font-size:20pt">What Is Data Type?</li>

Data types are the classification or categorization of data items. It represents the kind of value that tells what operations can be performed on a particular data. Numeric value can be integer, floating number or even complex numbers. These values are defined as int, float and complex class in Python.


```python
print(type(5))
```

    <class 'int'>
    


```python
type("hello")
```




    str




```python
a = 5
print("Type of a: ", type(a))
```

    Type of a:  <class 'int'>
    


```python
b = 5.0
print("Type of b: ", type(b))
```

    Type of b:  <class 'float'>
    


```python
c = 2 + 4j
print("Type of c: ", type(c))
```

    Type of c:  <class 'complex'>
    


```python
String1 = 'Welcome to the Python Programmer'
print(String1) 
print(type(String1))
```

    Welcome to the Python Programmer
    <class 'str'>
    


```python
boolean = True
print(type(boolean))
```

    <class 'bool'>
    


```python
x = [1,2,3,4]
print(type(x))
```

    <class 'list'>
    


```python
y = {"a":1,"b":2}
print(type(y))
```

    <class 'dict'>
    


```python
z = (1,2,3,4)
print(type(z))
```

    <class 'tuple'>
    


```python
abc = {1,2,3,4}

print(type(abc))
```

    <class 'set'>
    

# <li style="font-size:20pt">Arithmetic Operators</li>

![image.png](attachment:image.png)


```python
x = 4
y = 5
z = x+y
print(z)
```

    9
    


```python
x = 15
y = 5
z = x-y
print(z)
```

    10
    


```python
x = 4
y = 5
z = x*y
print(z)
```

    20
    


```python
x = 40
y = 5
z = x/y
print(z)
```

    8.0
    


```python
x = 40
y = 5
z = x%y
print(z)
```

    0
    


```python
x = 4
y = 5
z = x**y
print(z)
```

    1024
    


```python
x = 40
y = 5
z = x//y
print(z)
```

    8
    

# <li style="font-size:20pt">Assignment Operators</li>

![image-5.png](attachment:image-5.png)


```python
x = 5
y = 5
print(x)
print(y)
```

    5
    5
    


```python
x = 5
x += 5 # increament
print(x)
```

    10
    


```python
x = 5
x = x+50
print(x)
```

    55
    


```python
x = 10 
x -= 2 # decreament
print(x)
```

    8
    


```python
x = 10 
x = x-2
print(x)
```

    8
    


```python
x = 10 
x *= 2
print(x)
```

    20
    


```python
x = 10 
x = x*2
print(x)
```

    20
    


```python
x = 100 
x /= 2
print(x)
```

    50.0
    


```python
x = 100 
x = x/2
print(x)
```

    50.0
    


```python
x = 11
x %= 3
print(x)
```

    2
    


```python
x = 11
x = x%3
print(x)
```

    2
    

# <li style="font-size:20pt">Comparison Operators</li>
![image.png](attachment:image.png)


```python
x = 10
y = 10
z = x == y # == show equal to
print(z)
```

    True
    


```python
x = 10
y = 11
z = x == y # show equal to
print(z)
```

    False
    


```python
x = 10
y = 10
z = x != y # != show not equal to
print(z)
```

    False
    


```python
x = 10
y = 100
z = x != y # != show not equal to
print(z)
```

    True
    


```python
x = 10
y = 100
z = x < y # < show less than
print(z)
```

    True
    


```python
x = 100
y = 10
z = x < y # < show less than
print(z)
```

    False
    


```python
x = 100
y = 10
z = x > y # > show greater than
print(z)
```

    True
    


```python
x = 100
y = 1000
z = x > y # > show greater than
print(z)
```

    False
    


```python
x = 10
y = 10
z = x <= y # <= show less than equal to
print(z)
```

    True
    


```python
x = 46
y = 46
z = x <= y # <= show less than
print(z)
```

    True
    


```python
x = 100
y = 100
z = x >= y # >= show greater than
print(z)
```

    True
    

# <li style="font-size:20pt">Logical Operators</li>
![image.png](attachment:image.png)


```python
a = 5
b = 10
c = a < b
print("Ouput Of C: ",c)
x = 15
y = 2
z = x > y
print("Ouput Of Z: ",z)
print("Ouput Of and operator: ",c and z) # using "and" operator
```

    Ouput Of C:  True
    Ouput Of Z:  True
    Ouput Of and operator:  True
    


```python
a = 50
b = 100
c = a < b
print("Ouput Of C: ",c)
x = 155
y = 20
z = x > y
print("Ouput Of Z: ",z)
print("Ouput Of and operator: ",c and z) # using "and" operator
```

    Ouput Of C:  True
    Ouput Of Z:  True
    Ouput Of and operator:  True
    


```python
a = 5
b = 10
c = a < b
print("Ouput Of C: ",c)
x = 15
y = 20
z = x > y
print("Ouput Of Z: ",z)
print("Ouput Of or operator: ",c or z) # using "or" operator
```

    Ouput Of C:  True
    Ouput Of Z:  False
    Ouput Of or operator:  True
    


```python
a = 50
b = 10
c = a < b
print("Ouput Of C: ",c)
x = 155
y = 20
z = x > y
print("Ouput Of Z: ",z)
print("Ouput Of or operator: ",c or z) # using "or" operator
```

    Ouput Of C:  False
    Ouput Of Z:  True
    Ouput Of or operator:  True
    


```python
a = 50
b = 10
c = a < b
print("Ouput Of C: ",c)
x = 15
y = 20
z = x > y
print("Ouput Of Z: ",z)
print("Ouput Of or operator: ",c or z) # using "or" operator
```

    Ouput Of C:  False
    Ouput Of Z:  False
    Ouput Of or operator:  False
    


```python
a = "Python"

print("t" not in a)
```

    False
    


```python
a = 50
b = 10
c = a < b
print("Ouput Of C: ",c)
print("Ouput Of not operator: ",not c) # using "not" operator
```

    Ouput Of C:  False
    Ouput Of not operator:  True
    


```python
a = 5
b = 10
c = a < b
print("Ouput Of C: ",c)
print("Ouput Of not operator: ",not c) # using "not" operator
```

    Ouput Of C:  True
    Ouput Of not operator:  False
    

# <li style="font-size:20pt">Identity Operators</li>
![image.png](attachment:image.png)


```python
x = "Python"
z = "Python"

print(x is z)
```

    True
    


```python
x = "Python"
z = "python"

print(x is z)
```

    False
    


```python
x = "apple"
z = "apple"
print(x is not z)
```

    False
    


```python
x = "apple"
z = "Apple"
print(x is not z)
```

    True
    

# <li style="font-size:20pt">Membership Operators</li>
![image-2.png](attachment:image-2.png)


```python
x = "Hello Python!"

print("Hello" in x)
```

    True
    


```python
x = "Hello Python!"

print("H" in x)
```

    True
    


```python
x = "Hello Python!"

print("python" in x)
```

    False
    


```python
x = "Hello Python!"

print("Python!" in x)
```

    True
    


```python
x = "Hello Python!"

print("hello" not in x)
```

    True
    


```python
x = "Hello Python!"

print("python" not in x)
```

    True
    


```python
x = "Hello Python!"

print("Hello" not in x)
```

    False
    

# <li style="font-size:20pt">Bitwise Operators</li>
![image.png](attachment:image.png)
![image-2.png](attachment:image-2.png)


# <li style="font-size:20pt">Python Numbers (Integers, Floating-Point Numbers, And Complex Numbers)</li>


```python
integer = 123
floating = 3.142
complexx = 3+6j

print(integer)
print(floating)
print(complexx)
```

    123
    3.142
    (3+6j)
    

# <li style="font-size:20pt">Python Numbers | Python Strings </li>
# <li style="font-size:20pt">String - Single Quotes Or In Double Quotes Or In Three Double Quotes</li>

# `Already Discuss`


```python
# Single quote
print('single quote used for single line print ')

print('Hello World')

print('Hey! This message from python jupyter notebook')

# Double quote
print("single quote used for single word print")

print("I love Pakistan")

print("Pakistan has self development country")

# Triple quote
print("""Triple quote
used for
multiple lines
in python
programming""")

print('''Hello
python
programmers''')

print("""Twinkle, twinkle, little star
How I wonder what you are
Up above the world so high
Like a diamond in the sky
Twinkle, twinkle, little star
How I wonder what you are""")
```

    single quote used for single line print 
    Hello World
    Hey! This message from python jupyter notebook
    single quote used for single word print
    I love Pakistan
    Pakistan has self development country
    Triple quote
    used for
    multiple lines
    in python
    programming
    Hello
    python
    programmers
    Twinkle, twinkle, little star
    How I wonder what you are
    Up above the world so high
    Like a diamond in the sky
    Twinkle, twinkle, little star
    How I wonder what you are
    

# <li style="font-size:20pt">Finding String Length</li>
The length of a Python string is calculated using the built-in len() method. It takes a string as a parameter and returns an integer as the length of that string. For example, len("educative") will return 9 because there are 9 characters in "educative".


```python
x = "Hello World!"
print(x)
print(len(x))
```

    Hello World!
    12
    


```python
len("python")
```




    6




```python
y = "Python is highly programming language"
print("Length of y: ",len(y))
```

    Length of y:  37
    

# <li style="font-size:20pt">Concatenating Strings</li>


```python
x = "Hello "
y = "Python"

print(x+y)
```

    Hello Python
    


```python
print("we "+"are "+"learning "+"python "+"programming!")
```

    we are learning python programming!
    


```python
s1 = "Hello "
s2 = "Programmers"
s3 = s1 + s2
print(s3)
```

    Hello Programmers
    


```python
s1 = "Hello"
s2 = "Programmers"
s3 = s1 + " " + s2
print(s3)
```

    Hello Programmers
    

# <li style="font-size:20pt">Cases Type</li>

### `Camel Case`
This case combines words by capitalizing the first letter of each word (except the first one) and removing the space between them:

#### Camel Case: `firstName`

This case is very used in many languages for a variety of purposes and in Python is not much used because Pascal Case is the default approach.

### `Pascal Case`
This case is also called Upper Camel Case, because combines words by capitalizing all words (even the first word) and removing the space between them:

#### Pascal Case: `FirstName`

This type is very used in Python for class names: OverflowError or ValueError (Exceptions are classes).

### `Snake Case`
This one is the most used in Python. It combines words by replacing spaces between words with an underscore:

#### Snake Case: `first_name`

Sometimes, it is better to use this type all capitalized, also known as Constant Case (used in constants in Python, of course):

#### Constant Case (Capitalized Snake Case): `FIRST_NAME`

### `Kebab Case`

This one is like Snake Case but instead of underscore, the dash is used to replace the spaces between words:

#### Kebab Case: `first-name`

------------------------
