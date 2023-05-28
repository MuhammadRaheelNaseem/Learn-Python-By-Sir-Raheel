# <span style='color:green, font-family; times, serif; font-size:30pt; font-style:italic'>Chapter No # 3 Python Language Syntax</span>
* Syntax Of Python,
* Interpreter Vs Compiler,
* Python Identifiers | * Python Keywords,
* Purpose/Use Of Comments In Computer Programming
* Python Comment Syntax,
* Comments In Python,
* Python Single Line Comment, 
* Multiline Comment In Python, 

# <li style='font-size:25pt'>Syntax Of Python</li>
<font style='font-size:20pt'>print(value,  sep=' ', end='\n' , "\n" , "\t")</font>

* Optional keyword arguments:
* sep:   string inserted between values, default a space.
* end:   string appended after the last value, default a newline.



```python
print("""Optional keyword argumentsOptional keyword arguments Optional keyword arguments Optional keyword arguments Optional keyword arguments 
Optional keyword arguments Optional keyword arguments Optional keyword arguments
 Optional keyword arguments Optional keyword arguments Optional keyword arguments 
  Optional keyword arguments Optional keyword arguments""") # String form
```

    Optional keyword argumentsOptional keyword arguments Optional keyword arguments Optional keyword arguments Optional keyword arguments 
    Optional keyword arguments Optional keyword arguments Optional keyword arguments
     Optional keyword arguments Optional keyword arguments Optional keyword arguments 
      Optional keyword arguments Optional keyword arguments
    


```python
print("Hello", "World") # String form
```

    Hello World
    


```python
print("Hello") # String form
print("world") # String form
```

    Hello
    world
    


```python
print("Hello World By Python Programming!") # String form
```

    Hello World By Python Programming!
    


```python
print("Twinkle, twinkle, little star How I wonder what you are") # String form
```

    Twinkle, twinkle, little star How I wonder what you are
    


```python
print(200) # integer
```

    200
    


```python
print(15 + 15) # addition
```

    30
    


```python
print(30 - 10) # subtraction
```

    20
    


```python
print(36 * 2) # multiplacation
```

    72
    


```python
print(36 / 6) # division
```

    6.0
    


```python
print(8 ** 2) # power
```

    64
    


```python
print("Hello","World", sep=" ")
```

    Hello World
    


```python
print("Hello", "", sep=" world")
```

    Hello world
    


```python
print("Rs. 100,000","PKR", sep="\-")
```

    Rs. 100,000\-PKR
    


```python
print("Rs. 100,000", "PKR = $400", "", sep="\-")
```

    Rs. 100,000\-PKR = $400\-
    


```python
print("Rs. 100,000", end="\-")
```

    Rs. 100,000\-


```python
print('single quote used for single line print ')
```

    single quote used for single line print 
    


```python
print('Hello World')
```

    Hello World
    


```python
print('Hey! This message from python jupyter notebook')
```

    Hey! This message from python jupyter notebook
    


```python
print("single quote used for single word print")
```

    single quote used for single word print
    


```python
print("I love Pakistan")
```

    I love Pakistan
    


```python
print("Pakistan has self development country")
```

    Pakistan has self development country
    


```python
print(""" hello 
this message
from
python
programming!""")
```

     hello 
    this message
    from
    python
    programming!
    


```python
print("""Triple quote
used for
multiple lines
in python
programming""")
```

    Triple quote
    used for
    multiple lines
    in python
    programming
    


```python
print('''Hello
python
programmers''')
```

    Hello
    python
    programmers
    


```python
print("""Twinkle, twinkle, little star
How I wonder what you are
Up above the world so high
Like a diamond in the sky
Twinkle, twinkle, little star
How I wonder what you are""")
```

    Twinkle, twinkle, little star
    How I wonder what you are
    Up above the world so high
    Like a diamond in the sky
    Twinkle, twinkle, little star
    How I wonder what you are
    


```python
print("hello","world")
```

    hello world
    


```python
print("Hello","\t","world") # \t used for tab or 1 tab == 4 space
```

    Hello 	 world
    


```python
print("Hello","\t\t\t","world")
```

    Hello 			 world
    


```python
print("Hello\tworld")
```

    Hello	world
    


```python
print("Hello" , '\n', "world") # \n used for new line
```

    Hello 
     world
    


```python
print("Hello", "\n\n\n", "Python")
```

    Hello 
    
    
     Python
    


```python
print("Hello\nPython")
```

    Hello
    Python
    

# <li style="font-size:20pt">Interpreter Vs Compiler</li>

![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/64d8b231-918d-47fb-b857-287646cc87ec)

# <li style="font-size:15pt">Interpreter</li>

![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/270830a8-5464-4168-ba53-15f7c87751d3)

# <li style="font-size:15pt">Compiler</li>

![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/296afa49-be9a-4d75-9fd4-de08a178c8f3)

# <li style="font-size:20pt">Python Identifiers | Python Keywords</li>

Keywords are the reserved words in Python. They are used to define the syntax and structure of the Python language. There are 33 keywords in Python 3.7. The list of all the keywords is given below. All the keywords except True, False and None are in lowercase and must be written as they are.
![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/669d6eb4-bbcd-49a1-a1be-91047f0c5eb2)

```python
import keyword
print(keyword.kwlist)
```

    ['False', 'None', 'True', 'and', 'as', 'assert', 'async', 'await', 'break', 'class', 'continue', 'def', 'del', 'elif', 'else', 'except', 'finally', 'for', 'from', 'global', 'if', 'import', 'in', 'is', 'lambda', 'nonlocal', 'not', 'or', 'pass', 'raise', 'return', 'try', 'while', 'with', 'yield']
    

# <li style="font-size:20pt">Use Of Comments In Computer Programming</li>


In addition to programming language codes, we programmers may want to write statements that need not be executed, such as simple human-readable English. These additional statements that are not executed as codes but remain in the program are known as comments. The comment play no role in building the logic of the program, but helps other programmers to understand what does the code intend to do.

# <li style="font-size:20pt">Python Comment Syntax</li>
Comments in Python begin with a hash mark ( # ) and whitespace character and continue to the end of the line.



```python
# This is comment syntax
```


```python
# this message will not show when its print
print("hello world")
```

    hello world
    


```python
print("We are Programmers")   # This is an inline comment also know as single line comment
```

    We are Programmers
    


```python
#This is the first line
#This is the second line
print("We are learning Python programming.")
```

    We are learning Python programming.
    


```python
'''
This is a string literal,
we should not use it for writing comments.
'''
print("Sharing is Caring")
```

    Sharing is Caring
    


```python
'''
This is multi line comment.
User will not get this message.
I hope you Understand very well.
'''

print("Sharing is Caring")
```

    Sharing is Caring
    


```python
"""
This is multi line comment.
User will not get this message.
I hope you Understand very well.
"""

print("Sharing is Caring")
```

    Sharing is Caring
    

-----------------------
