# <span style='color:green, font-family; times, serif; font-size:30pt; font-style:italic'>Chapter No # 5 Condition & Loops</span>

* How To Take Input From User,
* What Is Decision Making,
* Python Control Flow Statements,
* Syntax Of Conditional Statements In Python,
* Simple If Structure,
* If-Else Structure, 
* If Elif Structure,
* Nested If Structure,
* Using And, Or, In Conditions,
* In And Not In,
* Python Loop Statements,
* Syntax Of Wile Loop,
* Python While Loop,
* Syntax Of For Loop,
* Python For Loop, 
* Python Range(), 
* Stepping Through A For Loop,
* More About Ranges,
* Python Nested Loop Structures,
* Inserting Conditions In Loops And Vice Versa,
* Python Branching Statements – Break, Continue, Pass,
* The Random Module And Import,
* Flag In Python,
* Use Of Flag In Python,


# <li style='font-family; times, serif; font-size:20pt;'>How To Take Input From User</li>

In Python, we use input() function to take input from the user. Whatever you enter as input, the input function converts it into a string. If you enter an integer value still input() function convert it into a string. 

`Syntax: input(prompt)`

Parameter:

Prompt: (optional) The string that is written to standard output(usually screen) without newline.
Return: String object


```python
input()
```


```python
x = input()
print(x)
```


```python
x = input("Enter Your Name: ")
print(x)
```


```python
first_name = input("Enter your first name: ")
lastName = input("Enter your last name: ")
print("First Name: "+first_name+"\n"+"Last Name: "+lastName)
```


```python
name = input("Enter your name")
print("Hello", name)
print(type(name))
```


```python
num = int(input())
print(num)
print(type(num))
```


```python
num = int(input())
print(num)
print(type(num))
```


```python
num = int(input("Enter a number:"))
add = num + 1
print(add)
```


```python
first_name = input("Enter your first name: ")
lastName = input("Enter your last name: ")
Age = int(input("Enter your age: "))
print("#------------------------------------------3")
print("First Name: "+first_name+"\n"+"Last Name: "+lastName+"\n"+"Age: ",Age)
```


```python
floats = float(input())
print(floats)
```


```python
num =float(input("Enter number "))
add = num + 1
print(add)
```

# <li style='font-family; times, serif; font-size:20pt;'>What Is Decision Making | Python Control Flow Statements</li>
 
Python's Decision making structures require that the programmer specify one or more conditions to be evaluated or tested by the program. A selection statement allows a program to test several conditions and execute instructions based on which condition is true. In Python, the selection statements are also known as Decision control statements or branching statements.

![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/c5d764fd-1990-45fb-92cd-ae9f2a622d2b)
![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/825bd32e-410e-4e11-b102-1dbd77357745)

# <li style='font-family; times, serif; font-size:20pt;'>Syntax Of Conditional Statements In Python</li>

### `Syntax of Condition:`
<pre>
if expression:
    """doc string"""
    expression
    statement
elif expression:
    """doc string"""
    expression
    statement
else:
    """doc string"""
    statement
</pre>

# <li style='font-family; times, serif; font-size:20pt;'>Simple If Structure | If-Else Structure | If Elif Structure</li>


```python
a = 33
b = 200
if a<b:
    """From doc string: this is condition"""
    print("a is less than b")
```

    a is less than b
    


```python
aa = 330
bb = 20
if bb > aa:
    """From doc string: this is condition"""
    print("b is greater than a")
```


```python
num = 50
if ( num >= 10):
    print("num is greater than 10")
```

    num is greater than 10
    


```python
number1 = 20
number2 = 30
if number1 >= number2:
    print("number 1 is greater than number 2")
else:
    print("number 2 is greater than number 1")
```

    number 2 is greater than number 1
    


```python
if (5>10):
    print(5)
else:
    print(10)

```

    10
    


```python
a = 33
b = 33
if b > a:
    """From doc string: this is condition"""
    print("b is greater than a")
elif a == b:
    """From doc string: this is condition"""
    print("a and b are equal")
```

    a and b are equal
    


```python
a = 200
b = 33
if b > a:
    print("b is greater than a")
elif a == b:
    print("a and b are equal")
else:
    print("a is greater than b")
```

    a is greater than b
    


```python
print("Select your ride:")
print("1. Bike")
print("2. Car")
print("3. SUV")

choice = int( input() )

if ( choice == 1 ):
    print( "You have selected Bike" )
elif ( choice == 2 ):
    print( "You have selected Car" )
elif ( choice == 3 ):
    print( "You have selected SUV")
else:
    print("Wrong choice!")
```

    Select your ride:
    1. Bike
    2. Car
    3. SUV
    one
    


    ---------------------------------------------------------------------------

    ValueError                                Traceback (most recent call last)

    Cell In[9], line 6
          3 print("2. Car")
          4 print("3. SUV")
    ----> 6 choice = int( input() )
          8 if ( choice == 1 ):
          9     print( "You have selected Bike" )
    

    ValueError: invalid literal for int() with base 10: 'one'



```python
num = int(input("Enter number: "))
if num > 0:
    print(num, "is a positive number.")
elif num < 0:
    print(num, "is a Negative number.")
else:
    print("Sleep............")
```

    Enter number: 5
    5 is a positive number.
    

# <li style='font-family; times, serif; font-size:20pt;'>And | Or | In | Not In</li>




```python
a = 200
b = 33
c = 500
if a > b and c > a:
    print("Both conditions are True")
```

    Both conditions are True
    


```python
a = 200
b = 33
c = 500
if a > b or a > c:
    print("At least one of the conditions is True")
```

    At least one of the conditions is True
    


```python
x = "Hello"
if "e" in x:
    print("e in "+x)
else:
    print("Not Found!")
```

    e in Hello
    


```python
exampleStr = "Python is a general-purpose programming language."

# Look for substring in source string
if 'gene' in exampleStr:
    print("Found! The string contains the phrase 'gene'.")
else:
    print("Didn't find the substring.")
```

    Found! The string contains the phrase 'gene'.
    


```python
x = "Hello"
if "e" not in x:
    print("a not in "+x)
else:
    print("Not Found!")
```

# <li style='font-family; times, serif; font-size:20pt;'>Nested If Structure</li>


### Syntax:
<pre>
if expression1:
   statement(s)
   if expression2:
      statement(s)
   elif expression3:
      statement(s)
   else
      statement(s)
   elif expression4:
      statement(s)
   else:
      statement(s)
</pre>



```python
x = 41

if x > 10:
    print("Above ten,")
    if x > 20:
        print("and also above 20!")
    else:
        print("but not above 20.")
```

    Above ten,
    and also above 20!
    


```python
num = 8
if num >= 0:
    if num == 0:
        print("zero")
    else:
        print("Positive number")
else:
    print("Negative number")
```

    Positive number
    


```python
price=100
quantity=10
amount = price*quantity
if amount > 200:
    if amount >1000:
        print("The amount is greater than 1000")
    else:
        if amount == 800:
            print("The amount is between 800 and 1000")
        elif amount == 600:
            print("The amount is between 600 and 1000")
        else:
            print("The amount is between 400 and 1000")
elif amount == 200:
    print("Amount is 200")
else:
    print("Amount is less than 200")

```

    The amount is between 400 and 1000
    


```python
num = int(input("enter number"))
if num%2 == 0:
    if num%3 == 0:
        print ("Divisible by 3 and 2")
    else:
        print ("divisible by 2 not divisible by 3")
else:
    if num%3 == 0:
        print ("divisible by 3 not divisible by 2")
    else:
        print  ("not Divisible by 2 not divisible by 3")
```

    enter number5
    not Divisible by 2 not divisible by 3
    


```python
num = float(input("Enter a number: "))
if num >= 0:
    if num == 0:
        print("Zero")
    else:
        print("Positive number")
else:
    print("Negative number")
```

    Enter a number: 2
    Positive number
    

# <li style='font-family; times, serif; font-size:20pt;'>Python While Loop Statements</li>
 
The while loop in Python is used to iterate over a block of code as long as the test expression (condition) is true. We generally use this loop when we don't know the number of times to repeat a particular section of code, such as a function statement.

# <li style='font-family; times, serif; font-size:20pt;'>Syntax Of While Loop</li>
![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/c5ba2db1-eb1d-4e16-8213-1b2b82d7938f)
![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/da026fde-273f-41c5-8744-d0bf491decfd)

# <li style='font-family; times, serif; font-size:20pt;'>Python While Loop</li>


```python
while True:
    print("Hey")
```

    Hey
    Hey
    Hey
    Hey
    Hey
    Hey
    Hey
    
    
    
    
    
    it is keep runnning it will not stop
    


```python
while 1:
    print("hello")
```

    hello
    hello
    hello
    hello
    hello
    hello
    hello
    hello
    hello
    hello
    
    
    
    
    
    it is keep runnning it will not stop
    


```python
while False:
    print("hello")
```


```python
counter = 0

while True:
    counter += 1
    print(counter)
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
    11
    12
    13
    14
    15
    
    
    
    
    
    it is keep runnning it will not stop
    


```python
count = 1
while 1:
    usr = input("Press Enter To Continue.....")
    if usr == "":
        name = input("enter name ")
        fname=input("enter father name ")
        age=int(input("Enter age "))
        gender =input("Enter gender")
        print("_________Patient No_________",count)
        print("Name ",name)
        print("Father Name ",fname)
        print("Age ",age)
        print("Gender ",gender)
        print("_________closed______________")
        count+=1
    else:
        break
    
```

    Press Enter To Continue.....
    enter name Muhammad Raheel
    enter father name Naseem
    Enter age 12
    Enter genderMale
    _________Patient No_________ 1
    Name  Muhammad Raheel
    Father Name  Naseem
    Age  12
    Gender  Male
    _________closed______________
    Press Enter To Continue.....
    enter name Ali
    enter father name Farhan
    Enter age 11
    Enter genderMale
    _________Patient No_________ 2
    Name  Ali
    Father Name  Farhan
    Age  11
    Gender  Male
    _________closed______________
    Press Enter To Continue.....stop
    


```python
counter = 0

while counter < 3:
    print("Inside loop" , counter)
    counter = counter + 1
else:
    print("Stop While")
```

    Inside loop 0
    Inside loop 1
    Inside loop 2
    Stop While
    


```python
i = 1
while i < 6:
    print(i)
    i += 1
```

    1
    2
    3
    4
    5
    


```python
count = 0
while (count < 9):
    print ('The count is:', count)
    count = count + 1

print ("Good bye!")
```

    The count is: 0
    The count is: 1
    The count is: 2
    The count is: 3
    The count is: 4
    The count is: 5
    The count is: 6
    The count is: 7
    The count is: 8
    Good bye!
    


```python
while True :  # This constructs an infinite loop
    num = int(input("Enter a number  :"))
    print ("You entered: ", num)
    
print ("Good bye!")
```

    Enter a number  :2
    You entered:  2
    Enter a number  :3
    You entered:  3
    Enter a number  :4
    You entered:  4
    Enter a number  :five
    


    ---------------------------------------------------------------------------

    ValueError                                Traceback (most recent call last)

    Cell In[20], line 2
          1 while True :  # This constructs an infinite loop
    ----> 2     num = int(input("Enter a number  :"))
          3     print ("You entered: ", num)
          5 print ("Good bye!")
    

    ValueError: invalid literal for int() with base 10: 'five'


# <li style='font-family; times, serif; font-size:20pt;'>What is for loop?</li>
Python For Loops A for loop is used for iterating over a sequence (that is either a list, a tuple, a dictionary, a set, or a string).

This is less like the for keyword in other programming languages, and works more like an iterator method as found in other object-orientated programming languages.

With the for loop we can execute a set of statements, once for each item in a list, tuple, set etc.
![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/c4cf6726-7cfc-4dc6-846f-1f712bc18fd1)

# <li style='font-family; times, serif; font-size:20pt;'>Syntax Of For Loop</li>
![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/58bb0e13-bdf0-4cc0-a2c3-836ebc6e5e4a)

# <li style='font-family; times, serif; font-size:20pt;'>Python For Loop</li>


```python
for i in range(10):
    print(i)
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
for i in range(5):
    print(i)
```

    0
    1
    2
    3
    4
    


```python
for i in range(1, 11):
    print(i)
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
for i in range(1, 25, 2):
    print(i)
```

    1
    3
    5
    7
    9
    11
    13
    15
    17
    19
    21
    23
    


```python
iterate = "Python Programmers"

for i in iterate:
    print(i)
```

    P
    y
    t
    h
    o
    n
     
    P
    r
    o
    g
    r
    a
    m
    m
    e
    r
    s
    

# <li style='font-family; times, serif; font-size:20pt;'>Python Range() | Stepping Through A For Loop</li>


```python
for variable in range(10): # range(starting)
    print(variable)
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
for i in range(10):
    print("No of time iterate   ----> " + str(i))
    
```

    No of time iterate   ----> 0
    No of time iterate   ----> 1
    No of time iterate   ----> 2
    No of time iterate   ----> 3
    No of time iterate   ----> 4
    No of time iterate   ----> 5
    No of time iterate   ----> 6
    No of time iterate   ----> 7
    No of time iterate   ----> 8
    No of time iterate   ----> 9
    


```python
for var in range(1,11): # range(starting, ending)
    print(var)
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
for i in range(10,31):
    print(i)
```

    10
    11
    12
    13
    14
    15
    16
    17
    18
    19
    20
    21
    22
    23
    24
    25
    26
    27
    28
    29
    30
    


```python
for i in range(1,20,2): # range(starting, ending, steps)
    print(i)
```

    1
    3
    5
    7
    9
    11
    13
    15
    17
    19
    


```python
for i in range(1,50,5):
    print(i)
```

    1
    6
    11
    16
    21
    26
    31
    36
    41
    46
    


```python
for i in range(10,0,-1):
    print(i)
```

    10
    9
    8
    7
    6
    5
    4
    3
    2
    1
    


```python
for i in range(1,11):
    print("5  X ", i, " = ", i*5)
```

    5  X  1  =  5
    5  X  2  =  10
    5  X  3  =  15
    5  X  4  =  20
    5  X  5  =  25
    5  X  6  =  30
    5  X  7  =  35
    5  X  8  =  40
    5  X  9  =  45
    5  X  10  =  50
    


```python
table = int(input("enter table number:"))

for var in range(1,11):
    print(table ," x ", var, " = " ,var*table)
```

    enter table number:23
    23  x  1  =  23
    23  x  2  =  46
    23  x  3  =  69
    23  x  4  =  92
    23  x  5  =  115
    23  x  6  =  138
    23  x  7  =  161
    23  x  8  =  184
    23  x  9  =  207
    23  x  10  =  230
    


```python
print(range(10))
```

    range(0, 10)
    

# <li style='font-family; times, serif; font-size:20pt;'>Python Nested Loop Structures</li>
![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/4bca1713-e720-4f59-a26f-ac13826b6f45)


```python
for i in range(1,11):
    for j in range(1,11):
        print(i*j,end="\t")
    print("")
```

    1	2	3	4	5	6	7	8	9	10	
    2	4	6	8	10	12	14	16	18	20	
    3	6	9	12	15	18	21	24	27	30	
    4	8	12	16	20	24	28	32	36	40	
    5	10	15	20	25	30	35	40	45	50	
    6	12	18	24	30	36	42	48	54	60	
    7	14	21	28	35	42	49	56	63	70	
    8	16	24	32	40	48	56	64	72	80	
    9	18	27	36	45	54	63	72	81	90	
    10	20	30	40	50	60	70	80	90	100	
    


```python
x = "Python"
y = "Programmers"
for i in x:
    for j in y:
        print(i,j)
    print()
```

    P P
    P r
    P o
    P g
    P r
    P a
    P m
    P m
    P e
    P r
    P s
    
    y P
    y r
    y o
    y g
    y r
    y a
    y m
    y m
    y e
    y r
    y s
    
    t P
    t r
    t o
    t g
    t r
    t a
    t m
    t m
    t e
    t r
    t s
    
    h P
    h r
    h o
    h g
    h r
    h a
    h m
    h m
    h e
    h r
    h s
    
    o P
    o r
    o o
    o g
    o r
    o a
    o m
    o m
    o e
    o r
    o s
    
    n P
    n r
    n o
    n g
    n r
    n a
    n m
    n m
    n e
    n r
    n s
    
    


```python
for i in range(0,5):
    for j in range(0,i+1):
        print("x", end="\t")
    print()
```

    x	
    x	x	
    x	x	x	
    x	x	x	x	
    x	x	x	x	x	
    


```python
rows = 5
# outer loop
for i in range(1, rows + 1):
    # inner loop
    for j in range(1, i + 1):
        print("*", end="\t")
    print('')
```

    *	
    *	*	
    *	*	*	
    *	*	*	*	
    *	*	*	*	*	
    


```python
rows = int(input("Enter the rows:"))  
# Outer loop will print number of rows  
for i in range(0,rows+1):  
# Inner loop will print number of Astrisk  
    for j in range(i):  
        print("*",end = '')  
    print()  
```

    Enter the rows:4
    
    *
    **
    ***
    ****
    

# <li style='font-family; times, serif; font-size:20pt;'>Inserting Conditions In Loops | For Loop – Break, Continue, Pass</li>



```python
for i in range(1, 4):
    print(i)
else: # Executed because no break in for
    print("No Break")

```

    1
    2
    3
    No Break
    


```python
for i in range(1, 4):
    print(i)
    break
    print("not show")
else: # Not executed as there is a break
    print("No Break")

    
```

    1
    


```python
for i in range(1,10):
    print(i)
    if i == 5:
        break
```

    1
    2
    3
    4
    5
    


```python
x = "Hello Python Programmers"
for i in x:
    print(i)
    if i == "t":
        break
```

    H
    e
    l
    l
    o
     
    P
    y
    t
    


```python
for i in range(15):
    if i == 8:
        continue
    print(i)
```

    0
    1
    2
    3
    4
    5
    6
    7
    9
    10
    11
    12
    13
    14
    


```python
x = "Hello Python Programmers"
for i in x:
    if i == "t":
        continue
    print(i)
```

    H
    e
    l
    l
    o
     
    P
    y
    h
    o
    n
     
    P
    r
    o
    g
    r
    a
    m
    m
    e
    r
    s
    


```python
var = 0                    # Second Example
while var < 10:              
    var = var +1
    if var == 5 or var == 7 or var == 9:
        continue
    print('Current variable value :', var)
print("Good bye!")
```

    Current variable value : 1
    Current variable value : 2
    Current variable value : 3
    Current variable value : 4
    Current variable value : 6
    Current variable value : 8
    Current variable value : 10
    Good bye!
    


```python
for i in range(5):
    if i>3:
        continue
    print(i)
```

    0
    1
    2
    3
    


```python
for i in range(5):
    if i<3:
        continue
    print(i)
```

    3
    4
    


```python
for i in range(5):
    if i > 2:
        pass
    print(i)
```

    0
    1
    2
    3
    4
    

# <li style='font-family; times, serif; font-size:20pt;'>The Random Module And Import</li>
Python Random is an in-built module used to generate random numbers. These are pseudo-random numbers so they are not truly random. It can be used to perform random actions such as generating random numbers, print random a value for a list or string, etc.


```python
import random

print(random.randint(1,10))
```

    6
    


```python
import random

print(random.randrange(1,20))
```

    14
    


```python
import random

print(random.random())
```

    0.11480371185056482
    

# <li style='font-family; times, serif; font-size:20pt;'>Flag In Python | Use Of Flag In Python</li>
Flag variables are the same for all languages, whether it's RUBY, Python, Javascript or C++. A flag variable is usually given one value, 0 or 1 , True or False. It's used as a Boolean where the result toggles between 0 (False) and 1 (True).


```python
x = 0 # flag

for i in range(5):
    if x==0:
        print("I am inside of if condition which is x==0")
        x = 1
    elif x==1:
        print("I am inside of elif condition which is x==1")
        x = 0
```

    I am inside of if condition which is x==0
    I am inside of elif condition which is x==1
    I am inside of if condition which is x==0
    I am inside of elif condition which is x==1
    I am inside of if condition which is x==0
    


```python
x = 1

while x:
    if x == 1: 
        print("its one")
        x = 0

    if x == 0:
        print("its zero")
        x = 1
```

    its one
    its zero
    its one
    its zero
    its one
    its zero
    its one
    its zero
    its one
    its zero
    its one
    its zero
    its one
    its zero
    its one
    its zero
    its one
    its zero
    its one
    its zero
    
    
    
    
    
    it is keep runnning it will not stop
    


```python
prompt = "Tell me something cool: "
prompt += "\nEnter 'quit' to end the program \t"

active = True
while active:
    message = input(prompt)

    if message == 'quit':
        active = False
    else: 
        print(message)
```

    Tell me something cool: 
    Enter 'quit' to end the program 	Pakistan Zindabad
    Pakistan Zindabad
    Tell me something cool: 
    Enter 'quit' to end the program 	IoT is new emerging technology
    IoT is new emerging technology
    Tell me something cool: 
    Enter 'quit' to end the program 	quite
    quite
    Tell me something cool: 
    Enter 'quit' to end the program 	quit
    

# <li style="font-size:20pt;">String Formating</li> 
The format() method formats the specified value(s) and insert them inside the string's placeholder.

The placeholder is defined using curly brackets: {}. Read more about the placeholders in the Placeholder section below.

The format() method returns the formatted string.

`There are 3 type of string formating`
1. Modulus - %s, %d, %f (s=string, d=integer, f=float) (Old Method)
2. f-string - {}
3. Dot formating - .format{}

### 1. Python String Formatting Using % Operator
Python allows us to use the format specifiers used in C's printf statement. The format specifiers in Python are treated in the same way as they are treated in C. However, Python provides an additional operator %, which is used as an interface between the format specifiers and their values. In other words, we can say that it binds the format specifiers to the values.



```python
Integer = 10  
print("Hi I am Integer ... My value is %d "%(Integer))  
```

    Hi I am Integer ... My value is 10 
    


```python
# Old Methon %
Integer = 10  
Float = 1.290    
String = "Programming"    
print("Hi I am Integer ... My value is %d \nHi I am float ... My value is %f \nHi I am string ... My value is %s "%(Integer,Float,String))  
```

    Hi I am Integer ... My value is 10 
    Hi I am float ... My value is 1.290000 
    Hi I am string ... My value is Programming 
    


```python
a=3
b="Pi"
c=3.142
print("A= %d , B=%s ,C=%f"%(a,b,c))
```

    A= 3 , B=Pi ,C=3.142000
    


```python
a="Python"
b="everyone"

print("%s for %s"%(a,b))
```

    Python for everyone
    


```python
fName = input()
lName = input()
print("First Name: %s \nLast Name: %s"%(fName,lName))
```

    Muhammad
    Raheel
    First Name: Muhammad 
    Last Name: Raheel
    

### 2. String Interpolation / f-Strings (Python 3.6+)
Python 3.6 added a new string formatting approach called formatted string literals or “f-strings”. This new way of formatting strings lets you use embedded Python expressions inside string constants. Here’s a simple example to give you a feel for the feature:


```python
a = 5
b = 10
c= f'Five plus ten is {a + b} and not {2 * (a + b)}.'
print(c)
```

    Five plus ten is 15 and not 30.
    


```python
fName = input("Enter Name: ")
lName = input("Enter Last Name: ")
# print("First Name: {} \nLast Name: {}".format(fName,lName))
combine = f"First Name: {fName} \nLast Name: {lName}"
print(combine)
```

    Enter Name: Muhammad
    Enter Last Name: Raheel
    First Name: Muhammad 
    Last Name: Raheel
    


```python
for i in range(1,11):
    print(f"2 x {i} = {i*2}")
#     print("2 x ", i ," = ",i*2)
```

    2 x 1 = 2
    2 x 2 = 4
    2 x 3 = 6
    2 x 4 = 8
    2 x 5 = 10
    2 x 6 = 12
    2 x 7 = 14
    2 x 8 = 16
    2 x 9 = 18
    2 x 10 = 20
    

### 3. String Formatting - .format

The format() method formats the specified value(s) and insert them inside the string's placeholder.

The placeholder is defined using curly brackets: {}. Read more about the placeholders in the Placeholder section below.

The format() method returns the formatted string. 


```python
a = "hello"
b = 'sunday'
print(" {} this is {} we will enjoy ".format(a,b))
```

     hello this is sunday we will enjoy 
    


```python
# Using Curly braces  
print("{} and {} both are the best friend".format("Ali","Imran"))  
```

    Ali and Imran both are the best friend
    


```python
#Positional Argument 
print("{1} and {0} best players ".format("Ali","Imran"))  
```

    Imran and Ali best players 
    


```python
#Keyword Argument  
print("{b},{c},{a}".format(a = "James", b = "Peter", c = "Ricky"))  
```

    Peter,Ricky,James
    


```python
fName = input()
lName = input()
print("First Name: {} \nLast Name: {}".format(fName,lName))
```

    xyz
    abc
    First Name: xyz 
    Last Name: abc
    

--------------
