# <span style='color:green, font-family; times, serif; font-size:30pt; font-style:italic'>Chapter No # 8 File & Exception Handling</span>

* What is File Handling
* Why do we need this?
* Types of File Handling
* Python Read Files,
* Python Write/Create Files,
* Python Delete Files,
* What Is Json?,
* Json Load & Json Loads,
* Json Dump & Json Dumps,
* What Is Regex - Regular Expression?
* Use Of Regex- Regular Expression.
* Python Try,
* Python Except,
* Python Else,
* Python Finally,


# <li style="font-size:20pt;">What is File Handling</li>
Python provides us with an important feature for reading data from a file and writing data into a file. File handling in Python is simplified with built-in methods, which include creating, opening, and closing files. While files are open, Python allows performing various file operations, such as reading, writing, and appending information.

# <li style="font-size:20pt;">Why do we need this?</li>
Files are used to store data in a storage device permanently. File handling provides a mechanism to store the output of a program in a file and to perform various operations on it. A stream is an abstraction that represents a device on which operations of input and output are performed.

# <li style="font-size:20pt;">Types of File Handling</li>
![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/3276e061-db4b-4876-9914-2747bb188868)

# Modes
![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/3da4d42f-974a-4e0d-9399-22ad23326138)

<pre style="font-size: 20px;">

  Modes   Description
    r      Open a file for reading. <br>
    w      Opens a file for writing only. Overwrites the file if the file exists.
           If the file does not exist, creates a new file for writing. <br>
    r+     opens for reading and writing (cannot truncate a file).<br>
    w+     For writing and reading (can truncate a file).<br>
    a      Open for appending at the end of the file without truncating it. 
           Creates a new file if it does not exist.<br>
    t      Open in text mode.<br>
    b      Open in binary mode. <br>
    x      Open for exclusive creation, failing if the file already.<br>

</pre>

# <li style="font-size:20pt;">Python Read Files | Open file</li>

## `1st Method`


```python
fileobj = open('test.txt') # Open file 
```


```python
fileobj = open('test.txt') # Open file 
```


```python
fileobj = open('test.txt','r') # Open file in read mode
```


```python
fileobj = open('test.txt', 'w') # Open file in write mode
```


```python
fileobj = open('test1.txt', 'a') # Open file in append mode
```

# `read method` 


```python
fileobj = open('test.txt', "r") # "r" for read mode
x = fileobj.read()
print(x)
```

    
    What is Lorem Ipsum?
    Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.
    
    Why do we use it?
    It is a long established fact that a reader will be distracted by the readable content of a page when looking at its layout. The point of using Lorem Ipsum is that it has a more-or-less normal distribution of letters, as opposed to using 'Content here, content here', making it look like readable English. Many desktop publishing packages and web page editors now use Lorem Ipsum as their default model text, and a search for 'lorem ipsum' will uncover many web sites still in their infancy. Various versions have evolved over the years, sometimes by accident, sometimes on purpose (injected humour and the like).
    
    
    


```python
fileobj = open('test.txt', "r") 
x = fileobj.read(10) # for number of character "fileobj.read(size=-1, /)""
print(x)
```

    
    What is L
    


```python
fileobj = open('test.txt', "r") 
x = fileobj.read(100) # for number of character "fileobj.read(size=-1, /)""
print(x)
```

    
    What is Lorem Ipsum?
    Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lor
    


```python
fileobj = open('test.txt', "r") 
x = fileobj.readline()
print(x)
```

    What is Lorem Ipsum?
    
    


```python
fileobj = open('test1.txt', "r") 
x = fileobj.readline()
print(x)
```

    What is Lorem Ipsum?
    
    


```python
fileobj = open('test.txt', "r") 
fileobj.readlines()
```




    ['What is Lorem Ipsum?\n',
     "Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.\n",
     '\n',
     'Why do we use it?\n',
     "It is a long established fact that a reader will be distracted by the readable content of a page when looking at its layout. The point of using Lorem Ipsum is that it has a more-or-less normal distribution of letters, as opposed to using 'Content here, content here', making it look like readable English. Many desktop publishing packages and web page editors now use Lorem Ipsum as their default model text, and a search for 'lorem ipsum' will uncover many web sites still in their infancy. Various versions have evolved over the years, sometimes by accident, sometimes on purpose (injected humour and the like).\n",
     '\n']




```python
fileobj = open('test.txt', "r") 
x = fileobj.readlines()
print(x)
```

    ['What is Lorem Ipsum?\n', "Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.\n", '\n', 'Why do we use it?\n', "It is a long established fact that a reader will be distracted by the readable content of a page when looking at its layout. The point of using Lorem Ipsum is that it has a more-or-less normal distribution of letters, as opposed to using 'Content here, content here', making it look like readable English. Many desktop publishing packages and web page editors now use Lorem Ipsum as their default model text, and a search for 'lorem ipsum' will uncover many web sites still in their infancy. Various versions have evolved over the years, sometimes by accident, sometimes on purpose (injected humour and the like).\n", '\n']
    


```python
fileobj = open('test1.txt', "r") 
x = fileobj.readlines()
print(x)
```

    ['What is Lorem Ipsum?\n', "Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.\n", '\n', 'Why do we use it?\n', "It is a long established fact that a reader will be distracted by the readable content of a page when looking at its layout. The point of using Lorem Ipsum is that it has a more-or-less normal distribution of letters, as opposed to using 'Content here, content here', making it look like readable English. Many desktop publishing packages and web page editors now use Lorem Ipsum as their default model text, and a search for 'lorem ipsum' will uncover many web sites still in their infancy. Various versions have evolved over the years, sometimes by accident, sometimes on purpose (injected humour and the like).\n", '\n']
    


```python
file = open("test.txt","r")
for i in file:
    print(i)
```

    What is Lorem Ipsum?
    
    Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.
    
    
    
    Why do we use it?
    
    It is a long established fact that a reader will be distracted by the readable content of a page when looking at its layout. The point of using Lorem Ipsum is that it has a more-or-less normal distribution of letters, as opposed to using 'Content here, content here', making it look like readable English. Many desktop publishing packages and web page editors now use Lorem Ipsum as their default model text, and a search for 'lorem ipsum' will uncover many web sites still in their infancy. Various versions have evolved over the years, sometimes by accident, sometimes on purpose (injected humour and the like).
    
    
    
    

# `close() method`


```python
fileobj = open('test.txt', "r") 
x = fileobj.readlines()
print(x)
fileobj.close()
```

    ['What is Lorem Ipsum?\n', "Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.\n", '\n', 'Why do we use it?\n', "It is a long established fact that a reader will be distracted by the readable content of a page when looking at its layout. The point of using Lorem Ipsum is that it has a more-or-less normal distribution of letters, as opposed to using 'Content here, content here', making it look like readable English. Many desktop publishing packages and web page editors now use Lorem Ipsum as their default model text, and a search for 'lorem ipsum' will uncover many web sites still in their infancy. Various versions have evolved over the years, sometimes by accident, sometimes on purpose (injected humour and the like).\n", '\n']
    


```python
fileobj = open('test.txt', "r") 
fileobj.close()
fileobj.readlines()
```


    ---------------------------------------------------------------------------

    ValueError                                Traceback (most recent call last)

    <ipython-input-74-633d6f0522e9> in <module>
          1 fileobj = open('test.txt', "r")
          2 fileobj.close()
    ----> 3 fileobj.readlines()
    

    ValueError: I/O operation on closed file.


# <li style="font-size:20pt;">Python Write/Create Files</li>



```python
fileobj = open("test2.txt", "w") # "w" for write mode
fileobj.write("NEW CONTENT ADDED IN THE FILE.")
fileobj.close()
```


```python
fileobj = open('test2.txt','r') # lets check is this write?
fileobj.read()
```




    'NEW CONTENT ADDED IN THE FILE.'




```python
fileobj = open("test2.txt", "w") # Create a new file
fileobj.write("First Line\n")
fileobj.write("Second Line\n")
fileobj.write("Third Line\n")
fileobj.write("Fourth Line\n")
fileobj.write("Fifth Line\n")
fileobj.close()
```


```python
fileobj = open('test2.txt','r') # lets check is this write?
print(fileobj.read())
```

    First Line
    Second Line
    Third Line
    Fourth Line
    Fifth Line
    
    

# `append method` 


```python
fileobj = open("test2.txt", "a") # append into previous file
fileobj.write("\n six Line\n")
fileobj.write("Seven Line\n")
fileobj.write("eight Line\n")
fileobj.write("nine Line\n")
fileobj.write("ten Line\n")
fileobj.close()
```


```python
fileobj = open('test2.txt','r') # lets check is this write?
print(fileobj.read())
```

    First Line
    Second Line
    Third Line
    Fourth Line
    Fifth Line
    
     six Line
    Seven Line
    eight Line
    nine Line
    ten Line
    
    

# `File handling for 2nd Method`
# `read method`


```python
# Python code to illustrate with()
with open("test1.txt") as file:
    data = file.read()
# do something with data
print(data)
# data
```

    What is Lorem Ipsum?
    Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.
    
    Why do we use it?
    It is a long established fact that a reader will be distracted by the readable content of a page when looking at its layout. The point of using Lorem Ipsum is that it has a more-or-less normal distribution of letters, as opposed to using 'Content here, content here', making it look like readable English. Many desktop publishing packages and web page editors now use Lorem Ipsum as their default model text, and a search for 'lorem ipsum' will uncover many web sites still in their infancy. Various versions have evolved over the years, sometimes by accident, sometimes on purpose (injected humour and the like).
    
    
    


```python
# Python code to illustrate split() function
with open("test1.txt", "r") as file:
    data = file.readlines()
    for line in data:
        word = line.split()
        print (word)

```

    ['What', 'is', 'Lorem', 'Ipsum?']
    ['Lorem', 'Ipsum', 'is', 'simply', 'dummy', 'text', 'of', 'the', 'printing', 'and', 'typesetting', 'industry.', 'Lorem', 'Ipsum', 'has', 'been', 'the', "industry's", 'standard', 'dummy', 'text', 'ever', 'since', 'the', '1500s,', 'when', 'an', 'unknown', 'printer', 'took', 'a', 'galley', 'of', 'type', 'and', 'scrambled', 'it', 'to', 'make', 'a', 'type', 'specimen', 'book.', 'It', 'has', 'survived', 'not', 'only', 'five', 'centuries,', 'but', 'also', 'the', 'leap', 'into', 'electronic', 'typesetting,', 'remaining', 'essentially', 'unchanged.', 'It', 'was', 'popularised', 'in', 'the', '1960s', 'with', 'the', 'release', 'of', 'Letraset', 'sheets', 'containing', 'Lorem', 'Ipsum', 'passages,', 'and', 'more', 'recently', 'with', 'desktop', 'publishing', 'software', 'like', 'Aldus', 'PageMaker', 'including', 'versions', 'of', 'Lorem', 'Ipsum.']
    []
    ['Why', 'do', 'we', 'use', 'it?']
    ['It', 'is', 'a', 'long', 'established', 'fact', 'that', 'a', 'reader', 'will', 'be', 'distracted', 'by', 'the', 'readable', 'content', 'of', 'a', 'page', 'when', 'looking', 'at', 'its', 'layout.', 'The', 'point', 'of', 'using', 'Lorem', 'Ipsum', 'is', 'that', 'it', 'has', 'a', 'more-or-less', 'normal', 'distribution', 'of', 'letters,', 'as', 'opposed', 'to', 'using', "'Content", 'here,', 'content', "here',", 'making', 'it', 'look', 'like', 'readable', 'English.', 'Many', 'desktop', 'publishing', 'packages', 'and', 'web', 'page', 'editors', 'now', 'use', 'Lorem', 'Ipsum', 'as', 'their', 'default', 'model', 'text,', 'and', 'a', 'search', 'for', "'lorem", "ipsum'", 'will', 'uncover', 'many', 'web', 'sites', 'still', 'in', 'their', 'infancy.', 'Various', 'versions', 'have', 'evolved', 'over', 'the', 'years,', 'sometimes', 'by', 'accident,', 'sometimes', 'on', 'purpose', '(injected', 'humour', 'and', 'the', 'like).']
    []
    


```python
with open("test2.txt",'r') as x:
    y = x.readlines()
print(y)
```

    ['First Line\n', 'Second Line\n', 'Third Line\n', 'Fourth Line\n', 'Fifth Line\n', '\n', ' six Line\n', 'Seven Line\n', 'eight Line\n', 'nine Line\n', 'ten Line\n']
    


```python
with open("test2.txt",'r') as x:
    y = x.readlines()
# print(y)
y
```




    ['First Line\n',
     'Second Line\n',
     'Third Line\n',
     'Fourth Line\n',
     'Fifth Line\n',
     '\n',
     ' six Line\n',
     'Seven Line\n',
     'eight Line\n',
     'nine Line\n',
     'ten Line\n']



# `write method`


```python
with open("test2.txt",'w') as x:
    x.write("First Line\n")
    x.write("Second Line\n")
    x.write("Third Line\n")
    x.write("Fourth Line\n")
    x.write("Fifth Line\n")
```


```python
with open("test3.txt","w") as file:
    file.write("Why do we use it?\n")
    file.write("""It is a long established fact that a reader will be distracted by the readable content of a page 
    when looking at its layout. The point of using Lorem Ipsum is that it has a more-or-less normal distribution of 
    letters, as opposed to using 'Content here, content here', making it look like readable English. Many desktop 
    publishing packages and web page editors now use Lorem Ipsum as their default model text, and a search for 
    'lorem ipsum' will uncover many web sites still in their infancy. Various versions have evolved over the years, 
    sometimes by accident, sometimes on purpose (injected humour and the like).""")
```


```python
with open("test3.txt","r") as rd:
    readd = rd.read()
    
print(readd)
```

    Why do we use it?
    It is a long established fact that a reader will be distracted by the readable content of a page 
        when looking at its layout. The point of using Lorem Ipsum is that it has a more-or-less normal distribution of 
        letters, as opposed to using 'Content here, content here', making it look like readable English. Many desktop 
        publishing packages and web page editors now use Lorem Ipsum as their default model text, and a search for 
        'lorem ipsum' will uncover many web sites still in their infancy. Various versions have evolved over the years, 
        sometimes by accident, sometimes on purpose (injected humour and the like).
    


```python
with open('test2.txt','a') as file:
    file.write("\n six Line\n")
    file.write("Seven Line\n")
    file.write("eight Line\n")
    file.write("nine Line\n")
    file.write("ten Line\n")
```


```python
with open("test.txt","r") as rd:
    readd = rd.read()
    
print(readd)
```

    What is Lorem Ipsum?
    Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.
    
    Why do we use it?
    It is a long established fact that a reader will be distracted by the readable content of a page when looking at its layout. The point of using Lorem Ipsum is that it has a more-or-less normal distribution of letters, as opposed to using 'Content here, content here', making it look like readable English. Many desktop publishing packages and web page editors now use Lorem Ipsum as their default model text, and a search for 'lorem ipsum' will uncover many web sites still in their infancy. Various versions have evolved over the years, sometimes by accident, sometimes on purpose (injected humour and the like).
    
    
    


```python
with open('test1.txt','a') as file:
    file.write("\n six Line\n")
    file.write("Seven Line\n")
    file.write("eight Line\n")
    file.write("nine Line\n")
    file.write("ten Line\n")
```


```python
with open("test1.txt","r") as rd:
    readd = rd.read()
    
print(readd)
```

    What is Lorem Ipsum?
    Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.
    
    Why do we use it?
    It is a long established fact that a reader will be distracted by the readable content of a page when looking at its layout. The point of using Lorem Ipsum is that it has a more-or-less normal distribution of letters, as opposed to using 'Content here, content here', making it look like readable English. Many desktop publishing packages and web page editors now use Lorem Ipsum as their default model text, and a search for 'lorem ipsum' will uncover many web sites still in their infancy. Various versions have evolved over the years, sometimes by accident, sometimes on purpose (injected humour and the like).
    
    
     six Line
    Seven Line
    eight Line
    nine Line
    ten Line
    
    

# `Read and write a file with r+`
In r+ mode, we can read and write the file, but the file pointer position is at the beginning of the file; if we write the file directly, it will overwrite the beginning content.

See the below example: 


```python
with open('file.txt', 'r+') as f:
    f.write("new line \n hello")
    x = f.readlines()
    
print(x)
```

    []
    


```python
with open('file.txt', 'r+') as f:
    f.read()                # move file position to the end of the file.
    f.write("new line \n")
    

```

# <li style="font-size:20pt;">Python Delete Files</li>



```python
import os
os.remove("test.txt")
```


```python
import os
os.remove("test1.txt")
```


```python
import os
os.remove("test3.txt")
```


```python
import os
os.remove("file.txt")
```

# <li style="font-size:20pt;">What Is Json?</li>
JSON (JavaScript Object Notation) is a popular data format used for representing structured data. It's common to transmit and receive data between a server and web application in this format. In Python, JSON exists as a string; in other languages it's written as a series of characters.

# <li style="font-size:20pt;">What is JSON and why it is used? | Is JSON a database?</li>
A nonrelational database is designed to store and query data as JSON documents, rather than normalizing data across multiple tables, as in a relational database. It is often used for serializing structured data and exchanging it over a network, typically between a server and web applications. The language is relatively easy to read and write, while also easy for software to parse and generate.

# <li style="font-size:20pt;">JSON Objects</li>
<pre style="font-size: 20px;">
Python Object       JSON Object
    Dict 	      Object
 List, Tuple 	      Array
   String 	      String
  Int, Float          Numbers
    Boolean           True/False
    None              Null
</pre>
            

# <li style="font-size:20pt;">Json Loads</li>


```python
import json

# some JSON:
x =  '{ "name":"John", "age":30, "city":"New York"}'

# parse x:
y = json.loads(x)

# the result is a Python dictionary:
print(y)
print(type(y))
print(type(x))
```

    {'name': 'John', 'age': 30, 'city': 'New York'}
    <class 'dict'>
    <class 'str'>
    


```python
import json

# JSON string:
# Multi-line string
x = """{
    "Name": "Jennifer Smith",
    "Contact Number": 7867567898,
    "Email": "jen123@gmail.com",
    "Hobbies":["Reading", "Sketching", "Horse Riding"]
    }"""

# parse x:
y = json.loads(x)

# the result is a Python dictionary:
print(y)

```

    {'Name': 'Jennifer Smith', 'Contact Number': 7867567898, 'Email': 'jen123@gmail.com', 'Hobbies': ['Reading', 'Sketching', 'Horse Riding']}
    


```python
import json

# JSON string
employee ='{"id":"4201", "name": "Nitin", "department":"Finance"}'

# Convert string to Python dict
employee_dict = json.loads(employee)
print(employee_dict)

print(employee_dict['name'])

```

    {'id': '4201', 'name': 'Nitin', 'department': 'Finance'}
    Nitin
    

# <li style="font-size:20pt;">Json Dumps</li>


```python
import json

# a Python object (dict):
x = {
  "name": "John",
  "age": 30,
  "city": "New York"
}

# convert into JSON:
# conversion to JSON done by dumps() function
y = json.dumps(x)

# the result is a JSON string:
print("Result of x: ",x)
print("Result of y: ",y)
print("X ",type(x))
print("Y ",type(y))
```

    Result of x:  {'name': 'John', 'age': 30, 'city': 'New York'}
    Result of y:  {"name": "John", "age": 30, "city": "New York"}
    X  <class 'dict'>
    Y  <class 'str'>
    


```python
import json

print(json.dumps({"name": "John", "age": 30}))
print(json.dumps(["apple", "bananas"]))
print(json.dumps(("apple", "bananas")))
print(json.dumps("hello"))
print(json.dumps(42))
print(json.dumps(31.76))
print(json.dumps(True))
print(json.dumps(False))
print(json.dumps(None))
```

    {"name": "John", "age": 30}
    ["apple", "bananas"]
    ["apple", "bananas"]
    "hello"
    42
    31.76
    true
    false
    null
    


```python
import json
# list conversion to Array
print(json.dumps(['Welcome', "to", "Python","World"]))
# tuple conversion to Array
print(json.dumps(("Welcome", "to", "Programming","World")))
# string conversion to String
print(json.dumps("Hi"))
# int conversion to Number
print(json.dumps(123))
# float conversion to Number
print(json.dumps(23.572))
# Boolean conversion to their respective values
print(json.dumps(True))
print(json.dumps(False))
# None value to null
print(json.dumps(None))
```

    ["Welcome", "to", "Python", "World"]
    ["Welcome", "to", "Programming", "World"]
    "Hi"
    123
    23.572
    true
    false
    null
    


```python
import json

# Creating a dictionary
Dictionary ={1:'Welcome', 2:'to',
            3:'Python', 4:'for',
            5:'Programming'}

# Converts input dictionary into
# string and stores it in json_string
json_string = json.dumps(Dictionary)
print('Equivalent json string of input dictionary:',json_string)
print(" ")

# Checking type of object
# returned by json.dumps
print(type(json_string))

```

    Equivalent json string of input dictionary: {"1": "Welcome", "2": "to", "3": "Python", "4": "for", "5": "Programming"}
     
    <class 'str'>
    

# <li style="font-size:20pt;">Json Dump</li>


```python
import json

# python object(dictionary) to be dumped
dict1 ={
    "emp1": {
        "name": "Raheel",
        "designation": "programmer",
        "age": "34",
        "salary": "54000"
    },
    "emp2": {
        "name": "Ali",
        "designation": "Trainee",
        "age": "24",
        "salary": "40000"
    },
}

# the json file where the output must be stored
out_file = open("myfile.json", "w")

json.dump(dict1, out_file, indent = 6)

out_file.close()

```


```python
import json


# dictionary to be dumped
d ={'lang':'??? ????'}

with open('myfile.json', 'w', encoding ='utf8') as json_file:
    json.dump(d, json_file, ensure_ascii = True)

```


```python
with open("myfile.json","r") as file:
    x = file.readlines()
    
print(x)
```

    ['{"lang": "??? ????"}']
    


```python
import json


# dictionary to be dumped
d ={
    'a':1,
    'x':float('nan')
}

with open('myfile.json', 'w', encoding ='utf8') as json_file:
    json.dump(d, json_file, allow_nan=True)

```


```python
with open("myfile.json","r") as file:
    x = file.readlines()
    
print(x)
```

    ['{"a": 1, "x": NaN}']
    


```python
import json

x = {
  "name": "John",
  "age": 30,
  "married": True,
  "divorced": False,
  "children": ("Ann","Billy"),
  "pets": None,
  "cars": [
    {"model": "BMW 230", "mpg": 27.5},
    {"model": "Ford Edge", "mpg": 24.1}
  ]
}
with open("make.json",'w') as y:
    json.dump(x,y)
with open("make.json",'r') as file:
    a=json.load(file)
print(a)
```

    {'name': 'John', 'age': 30, 'married': True, 'divorced': False, 'children': ['Ann', 'Billy'], 'pets': None, 'cars': [{'model': 'BMW 230', 'mpg': 27.5}, {'model': 'Ford Edge', 'mpg': 24.1}]}
    

# <li style="font-size:20pt;">Json Load</li>


```python
# Python program to read
# json file


import json

# Opening JSON file
f = open('myfile.json')

# returns JSON object as
# a dictionary
data = json.load(f)
print(data)

# Iterating through the json
# list
for x,y in data.items():
    print(x,y)

# Closing file
f.close()

```

    {'a': 1, 'x': nan}
    a 1
    x nan
    


```python
with open("myfile.json", "r") as read_it:
    data = json.load(read_it)
print(data)
```

    {'a': 1, 'x': nan}
    

### **RegEx**

---

### **1. Introduction to Regular Expressions**

**What is RegEx?**
- A RegEx (Regular Expression) is a sequence of characters that forms a search pattern. It is used for searching and manipulating strings based on specific patterns.
  
- It’s primarily used for:
  - Searching text for patterns.
  - Replacing patterns.
  - Splitting strings based on patterns.
  - Validating input strings.


#### **Metacharacters**
Metacharacters are special characters that represent patterns in RegEx:

| **Character** | **Description**                            | **Example**           |
|---------------|--------------------------------------------|-----------------------|
| `.`           | Matches any character except newline.      | `a.c` (matches `abc`, `acc`, etc.) |
| `^`           | Anchors a match at the beginning of the string. | `^abc` (matches "abc" at the start of a string) |
| `$`           | Anchors a match at the end of the string.  | `abc$` (matches "abc" at the end of the string) |
| `*`           | Matches zero or more occurrences.         | `a*` (matches "", `a`, `aa`, `aaa`, etc.) |
| `+`           | Matches one or more occurrences.          | `a+` (matches `a`, `aa`, `aaa`, etc.) |
| `?`           | Matches zero or one occurrence.           | `a?` (matches "", `a`) |
| `{n}`         | Matches exactly `n` occurrences.          | `a{3}` (matches `aaa`) |
| `{n,}`        | Matches `n` or more occurrences.          | `a{2,}` (matches `aa`, `aaa`, `aaaa`, etc.) |
| `{n,m}`       | Matches between `n` and `m` occurrences.  | `a{2,4}` (matches `aa`, `aaa`, `aaaa`) |
| `|`           | Matches either of two patterns.            | `a|b` (matches `a` or `b`) |
| `()`          | Groups a pattern.                          | `(abc)+` (matches `abc`, `abcabc`) |


### **Special Sequences**

Special sequences represent a set of characters that match specific conditions:

| **Character** | **Description** | **Example** |
|---------------|-----------------|-------------|
| `\d`          | Matches any digit (0-9) | `\d{2,4}` (matches `12`, `1234`, etc.) |
| `\D`          | Matches any non-digit | `\D+` (matches any non-digit string) |
| `\s`          | Matches any whitespace character | `\s+` (matches spaces, tabs, newlines) |
| `\S`          | Matches any non-whitespace character | `\S+` (matches non-whitespace characters) |
| `\w`          | Matches any alphanumeric character | `\w+` (matches any word) |
| `\W`          | Matches any non-alphanumeric character | `\W+` (matches non-alphanumeric characters) |
| `\b`          | Matches a word boundary | `r"\bcat\b"` (matches "cat" at word boundaries) |
| `\B`          | Matches a non-word boundary | `r"\Bcat\B"` (matches "cat" not at word boundaries) |


### **Sets and Ranges**

A set is a collection of characters enclosed within `[]`.

| **Set Description**         | **Example**     |
|-----------------------------|-----------------|
| `[abc]`                     | Matches `a`, `b`, or `c` |
| `[a-z]`                     | Matches any lowercase letter |
| `[0-9]`                     | Matches any digit |
| `[^abc]`                    | Matches any character except `a`, `b`, or `c` |
| `[a-zA-Z]`                  | Matches any letter (lower or uppercase) |
| `[+]`                       | Matches the literal `+` character |


### **Flags in RegEx**

Flags change the behavior of the RegEx pattern matching. Some common flags include:

| **Flag**         | **Shorthand** | **Description**                           |
|------------------|---------------|-------------------------------------------|
| `re.ASCII`       | `re.A`        | Matches only ASCII characters             |
| `re.DOTALL`      | `re.S`        | Makes `.` match all characters, including newline |
| `re.IGNORECASE`  | `re.I`        | Case-insensitive matching                 |
| `re.MULTILINE`   | `re.M`        | Matches the beginning and end of each line |
| `re.VERBOSE`     | `re.X`        | Allows you to write more readable RegEx (with comments) |



```python
import re

txt = "The rain in Spain"
x = re.search("Spain$", txt)

if x:
    print(True)
else:
    print(False)
```

    True
    


```python
import re

txt = "The rain in Spain"
x = re.search("\s", txt)

print("The first white-space character is located in position:", x)
```

    The first white-space character is located in position: <re.Match object; span=(3, 4), match=' '>
    


```python
import re

s = 'GeeksforGeeks: A computer science portal for geeks'
# print(len(s))

match = re.search(r'geeks$', s)

# print('Start Index:', match.start())
print('End Index:', match)
if match:
    print(True)
else:
    print(False)
```

    End Index: <re.Match object; span=(45, 50), match='geeks'>
    True
    


```python
import re

txt = "Today is Saturday"

#Find all lower case characters alphabetically between "a" and "m":

x = re.findall("[a-x]", txt)
print(x)

```

    ['o', 'd', 'a', 'i', 's', 'a', 't', 'u', 'r', 'd', 'a']
    


```python
import re

txt = "The rain in Spain l"

#Find all lower case characters alphabetically between "a" and "m":

x = re.findall("[n-z]", txt)
print(x)

```


```python
import re

txt = "That will be 59 dollars"

#Find all digit characters:
x = re.findall("\d", txt)
y = re.findall("\d+", txt)
z = re.findall("\D", txt)

print("output of \d: ",x)
print("output of \d+: ",y)
print("Output of \D: ",z)
```

    output of \d:  ['5', '9']
    output of \d+:  ['59']
    Output of \D:  ['T', 'h', 'a', 't', ' ', 'w', 'i', 'l', 'l', ' ', 'b', 'e', ' ', ' ', 'd', 'o', 'l', 'l', 'a', 'r', 's']
    


```python
import re

txt = "I am 15 years old and my brother is 13 years old"

x = re.findall("\d+", txt)
print(x)
```

    ['15', '13']
    


```python
import re

txt = "That will be 59 90 98 dollars"

#Find all digit characters:

x = re.findall("\d", txt)
print(x)

```


```python
import re

txt = "hello planet help"

#Search for a sequence that starts with "he", followed by two (any) characters, and an "o":

x = re.findall(".l.n.t", txt)
print(x)

```

    ['planet']
    


```python
import re

txt = "hello helps planet"

#Check if the string starts with 'hello':

x = re.findall("^he...", txt)
print(x)
if x:
    print("Yes, the string starts with 'hello'")
else:
    print("No match")

```


```python
import re

txt = "hello planet"

#Check if the string ends with 'planet':

x = re.findall("planet$", txt)
print(x)
if x:
    print("Yes, the string ends with 'planet'")
else:
    print("No match")

```


```python
import re

txt = "hello planet"

#Search for a sequence that starts with "he", followed by 0 or more  (any) characters, and an "o":

x = re.findall("he.*o", txt)

print(x)

```

    ['hello']
    


```python
import re

txt = "hello planet"

#Search for a sequence that starts with "he", followed by 0 or more  (any) characters, and an "o":

x = re.findall("he.*o", txt)

print(x)

```


```python
import re

txt = "heo"
txt1 = 'hello'
txt2 = 'helo'
txt3 = 'he'

#Search for a sequence that starts with "he", followed by 0 or 1  (any) character, and an "o":

x = re.findall("he?o", txt)
y = re.findall("he.?o", txt1)
z = re.findall("he.?o", txt2)
v = re.findall("he.?o", txt3)

print(x)
print(y)
print(z)
print(v)

#This time we got no match, because there were not zero, not one, but two characters between "he" and the "o"

```


```python
ILovePakistan 
ILovePakistn ? wrong forgot
```


```python
import re

txt = "hello planet"
var = "Introduction"
print(len(var))

#Search for a sequence that starts with "he", followed excactly 2 (any) characters, and an "o":

# x = re.findall("he.{2}o", txt)
x = re.findall("In.{9}n", var)
# y = re.findall("pl...t", txt)


print(x)
# print(y)
```

    12
    ['Introduction']
    


```python
import re

txt = "hello planet"

#Search for a sequence that starts with "he", followed excactly 2 (any) characters, and an "o":

x = re.findall("he.{2}o", txt)

print(x)

```


```python
import re

txt = "ain in Spain"

#Check if "ain" is present at the beginning of a WORD:

x = re.findall(r"\bains", txt)

print(x)

if x:
    print("Yes, there is at least one match!")
else:
    print("No match")

```

    []
    No match
    


```python
import re

txt = "The rain in Spain"

#Check if "ain" is present at the beginning of a WORD:
# (pick only starting characters)

x = re.findall(r"\brains", txt)

print(x)

if x:
    print("Yes, there is at least one match!")
else:
    print("No match")

```


```python
import re

txt = "The rain pain Spain bin"

#Check if "ain" is present, but NOT at the beginning of a word
# (pick only last characters / seperate characters)

x = re.findall(r"\Bin", txt)

print(x)

if x:
    print("Yes, there is at least one match!")
else:
    print("No match")

```

    ['in', 'in', 'in', 'in']
    Yes, there is at least one match!
    


```python
import re

txt = "The rain in Spain"

#Check if "ain" is present, but NOT at the end of a word:

# x = re.findall(r"\Bain", txt)
y = re.findall(r"a\B", txt)

# print(x)
print(y)

if y:
    print("Yes, there is at least one match!")
else:
    print("No match")

```

    ['a', 'a']
    Yes, there is at least one match!
    


```python
import re

txt = "The rain in Spain 78"

#Check if the string contains any digits (numbers from 0-9):

x = re.findall("\d+", txt)

print(x)

if x:
    print("Yes, there is at least one match!")
else:
    print("No match")

```

    ['78']
    Yes, there is at least one match!
    


```python
import re

txt = "The rain in Spain 78 79 80"

#Return a match at every no-digit character:

x = re.findall("\D", txt)

print(x)

if x:
    print("Yes, there is at least one match!")
else:
    print("No match")

```

    ['T', 'h', 'e', ' ', 'r', 'a', 'i', 'n', ' ', 'i', 'n', ' ', 'S', 'p', 'a', 'i', 'n', ' ', ' ', ' ']
    Yes, there is at least one match!
    


```python
import re

txt = "The rain in Spain"

#Return a match at every white-space character:

x = re.findall("\s", txt)

print(x)

if x:
    print("Yes, there is at least one match!")
else:
    print("No match")

```

    [' ', ' ', ' ']
    Yes, there is at least one match!
    


```python
import re

txt = "The rain in Spain"

#Return a match at every NON white-space character:

x = re.findall("\S", txt)

print(x)

if x:
    print("Yes, there is at least one match!")
else:
    print("No match")

```

    ['T', 'h', 'e', 'r', 'a', 'i', 'n', 'i', 'n', 'S', 'p', 'a', 'i', 'n']
    Yes, there is at least one match!
    


```python
import re

txt = "The 59 _ $ @ # $ % & -"

#Return a match at every word character (characters from a to Z, digits from 0-9, and the underscore _ character):
# not to pick @ # $ % & -
x = re.findall("\w", txt)

print(x)

if x:
    print("Yes, there is at least one match!")
else:
    print("No match")

```

    ['T', 'h', 'e', '5', '9', '_']
    Yes, there is at least one match!
    


```python
import re

txt = "The rain in Spain 89 ? @ ! . $ @ # $ % & -"

#Return a match at every NON word character (characters NOT between a and Z. Like "!", "?" white-space etc.):

x = re.findall("\W", txt)

print(x)

if x:
    print("Yes, there is at least one match!")
else:
    print("No match")

```

    [' ', ' ', ' ', ' ', ' ', '?', ' ', '@', ' ', '!', ' ', '.', ' ', '$', ' ', '@', ' ', '#', ' ', '$', ' ', '%', ' ', '&', ' ', '-']
    Yes, there is at least one match!
    


```python
import re

txt = "The rain in Spain"

#Check if the string ends with "Spain":

x = re.findall("ain\Z", txt)

print(x)

if x:
    print("Yes, there is a match!")
else:
    print("No match")

```

    ['ain']
    Yes, there is a match!
    

    <>:7: SyntaxWarning: invalid escape sequence '\Z'
    <>:7: SyntaxWarning: invalid escape sequence '\Z'
    C:\Users\mrahe\AppData\Local\Temp\ipykernel_17796\1756666343.py:7: SyntaxWarning: invalid escape sequence '\Z'
      x = re.findall("ain\Z", txt)
    


```python
import re

txt = "The rain in Spain"

#Check if the string starts with "The":

x = re.findall("\AThe", txt)

print(x)

if x:
    print("Yes, there is a match!")
else:
    print("No match")

```

    ['The']
    Yes, there is a match!
    

    <>:7: SyntaxWarning: invalid escape sequence '\A'
    <>:7: SyntaxWarning: invalid escape sequence '\A'
    C:\Users\mrahe\AppData\Local\Temp\ipykernel_17796\1027700818.py:7: SyntaxWarning: invalid escape sequence '\A'
      x = re.findall("\AThe", txt)
    


```python
# A Python program to demonstrate working of
# findall()
import re

# A sample text string where regular expression
# is searched.
string = """Hello my Number is 123456789 and my friend's number is 987654321"""

# A sample regular expression to find digits.
regex = '\d+'

match = re.findall(regex, string)
print(match)

```

    ['123456789', '987654321']
    

    <>:10: SyntaxWarning: invalid escape sequence '\d'
    <>:10: SyntaxWarning: invalid escape sequence '\d'
    C:\Users\mrahe\AppData\Local\Temp\ipykernel_17796\1767463906.py:10: SyntaxWarning: invalid escape sequence '\d'
      regex = '\d+'
    


```python
import re

test_string = 'abyss'
pattern = '^a...s'

result = re.match(pattern, test_string)
print(result)

if result:
    print("Search successful.")
else:
    print("Search unsuccessful.")

```

    <re.Match object; span=(0, 5), match='abyss'>
    Search successful.
    


```python
import re

txt = "The rain in Spain"
x = re.search("^The.*Spain$", txt)
print(x)

if x:
    print("Match")
else:
    print("Not Match")
```

    <re.Match object; span=(0, 17), match='The rain in Spain'>
    Match
    


```python
# import re module
import re

Substring ='ALI'


String1 ='''We are learning regex with abc institute 
		regex is very useful for string matching.
		It is fast too. ALI'''
String2 ='''string We are learning regex with abc institute 
		regex is very useful for string matching.
		It is fast too. alI'''

# Use of re.search() Method
# x = re.search(Substring, String2, re.IGNORECASE) # found from anywhere else
x = re.match('$alI', String1) # found from starting 
if x:
    print('Founded.....')
else:
    print("Not Founded.....")
# Use of re.match() Method
# print(re.match(Substring, String1))

# # Use of re.search() Method
# print(re.search(Substring, String2))
# # Use of re.match() Method
# print(re.match(Substring, String2))

```

    Not Founded.....
    


```python
import re

Substring = 'ALI'

String1 = '''We are learning regex with abc institute 
        regex is very useful for string matching.
        It is fast too. ALI'''
String2 = '''ALI We are learning regex with abc institute 
        regex is very useful for string matching.
        It is fast too. alI'''

# Match 'ALI' at the start of the string (case-insensitive)
start_match = re.match(r'^' + Substring, String2, re.IGNORECASE)
if start_match:
    print("Found at the start of the string.")
else:
    print("Not Found at the start of the string.")

# Match 'ALI' at the end of the string (case-insensitive)
end_match = re.search(r'ALI$', String1, re.IGNORECASE)
if end_match:
    print("Found at the end of the string.")
else:
    print("Not Found at the end of the string.")

# Match any occurrence of 'ALI' ignoring case
any_match = re.search(r'ALI', String1, re.IGNORECASE)
if any_match:
    print("Found anywhere in the string.")
else:
    print("Not Found anywhere in the string.")

```

    Found at the start of the string.
    Found at the end of the string.
    Found anywhere in the string.
    


```python
import re

# Keyword to search for
keyword = 'ALI'

# Sample user comments (real-world scenario)
comments = [
    "I had a great experience with ALI's service!",
    "The product quality is excellent. alI would recommend it to everyone.",
    "Not satisfied with the service provided by Ali.",
    "I think ALI could improve their customer support.",
    "This is a random comment without the keyword."
]

# Function to search for the keyword in comments
def search_keyword_in_comments(keyword, comments):
    for index, comment in enumerate(comments):
        # Match 'keyword' at the start of the comment (case-insensitive)
        start_match = re.match(r'^' + re.escape(keyword), comment, re.IGNORECASE)
        if start_match:
            print(f"Comment {index + 1}: Found at the start of the comment.")

        # Match 'keyword' at the end of the comment (case-insensitive)
        end_match = re.search(re.escape(keyword) + r'$', comment, re.IGNORECASE)
        if end_match:
            print(f"Comment {index + 1}: Found at the end of the comment.")

        # Match any occurrence of 'keyword' ignoring case
        any_match = re.search(re.escape(keyword), comment, re.IGNORECASE)
        if any_match:
            print(f"Comment {index + 1}: Found anywhere in the comment.")

# Execute the search
search_keyword_in_comments(keyword, comments)
```

    Comment 1: Found anywhere in the comment.
    Comment 2: Found anywhere in the comment.
    Comment 3: Found anywhere in the comment.
    Comment 4: Found anywhere in the comment.
    


```python
# Email Validation System
import re

def validate_email(email):
    # RegEx pattern for a valid email
    pattern = r"^[a-zA-Z0-9_.+-]+@[a-zA-Z0-9-]+\.[a-zA-Z0-9-.]+$"
    
    # Search for a match
    if re.match(pattern, email):
        return "Valid Email"
    else:
        return "Invalid Email"

# Test the function
email = "test@example.com"
print(validate_email(email))

email = "invalid-email"
print(validate_email(email))

```

    Valid Email
    Invalid Email
    


```python
# Phone Number Validator
import re

def validate_phone_number(phone):
    # RegEx pattern for phone number format XXX-XXX-XXXX
    pattern = r"^\d{3}-\d{3}-\d{4}$"
    
    if re.match(pattern, phone):
        return "Valid Phone Number"
    else:
        return "Invalid Phone Number"

# Test the function
phone = "123-456-7890"
print(validate_phone_number(phone))

phone = "12345-67890"
print(validate_phone_number(phone)) 

```

    Valid Phone Number
    Invalid Phone Number
    


```python
# URL Extractor
import re

def extract_urls(text):
    # RegEx pattern to match both HTTP and HTTPS URLs
    pattern = r"https?://[a-zA-Z0-9.-]+(?:\.[a-zA-Z]{2,})+"
    
    urls = re.findall(pattern, text)
    return urls

# Test the function
text = "Visit us at https://www.example.com or check out our old site at http://oldsite.org"
urls = extract_urls(text)
print("URLs found:", urls) 

```

    URLs found: ['https://www.example.com', 'http://oldsite.org']
    


```python
# Date Extractor

import re

def extract_dates(text):
    # RegEx pattern to match dates in dd-mm-yyyy format
    pattern = r"\b\d{2}-\d{2}-\d{4}\b"
    
    dates = re.findall(pattern, text)
    return dates

# Test the function
text = "The event is on 12-05-2023 and the next event is on 15-06-2023."
dates = extract_dates(text)
print("Dates found:", dates)

```

    Dates found: ['12-05-2023', '15-06-2023']
    


```python
# Password Strength Checker

import re

def check_password_strength(password):
    # RegEx patterns to check different requirements
    if len(password) < 8:
        return "Password too short. Must be at least 8 characters."
    
    if not re.search(r"[A-Z]", password):
        return "Password must contain at least one uppercase letter."
    
    if not re.search(r"[a-z]", password):
        return "Password must contain at least one lowercase letter."
    
    if not re.search(r"[0-9]", password):
        return "Password must contain at least one digit."
    
    return "Password is strong."

# Test the function
password = "Password123"
print(check_password_strength(password)) 

password = "pass123"
print(check_password_strength(password)) 

```

    Password is strong.
    Password too short. Must be at least 8 characters.
    


```python
 # Log File Analyzer
import re

def extract_errors(log_text):
    # RegEx pattern to match 'ERROR' and 'WARNING' messages in log
    pattern = r"(ERROR|WARNING):\s.+"
    
    errors = re.findall(pattern, log_text)
    return errors

# Test the function
log_text = """INFO: System boot successful.
ERROR: File not found.
WARNING: Low disk space.
ERROR: Network timeout."""
errors = extract_errors(log_text)
print("Errors and Warnings:", errors)

```

    Errors and Warnings: ['ERROR', 'WARNING', 'ERROR']
    


```python
# Phone Number Formatting
import re

def format_phone_number(phone):
    # Remove all non-digit characters
    clean_phone = re.sub(r"\D", "", phone)
    
    # Format to XXX-XXX-XXXX
    formatted_phone = f"{clean_phone[:3]}-{clean_phone[3:6]}-{clean_phone[6:]}"
    
    return formatted_phone

# Test the function
phone = "123.456.7890"
formatted = format_phone_number(phone)
print("Formatted Phone:", formatted)  # Output: 123-456-7890

phone = "(123) 456-7890"
formatted = format_phone_number(phone)
print("Formatted Phone:", formatted)  # Output: 123-456-7890

```

    Formatted Phone: 123-456-7890
    Formatted Phone: 123-456-7890
    
    

# <li style="font-size:20pt;">Python Try/Except</li>
Code is executed in a series of blocks, starting with the try- and except blocks. The finally block lets you execute code, regardless of the result of the first two blocks. Code can only be executed once if there is an exception or when there is no error.

# <li style="font-size:20pt;">What is the purpose of a try except statement?</li>
The try-except statement is a Microsoft extension to the C language that enables applications to gain control of a program when events that normally terminate execution occur. Such events are called exceptions, and the mechanism that deals with them is called structured exception handling (TEW).

# `Syntax`
<pre>
try:
    # Some Code
except:
    # Executed if error in the
    # try block
else:
    # execute if no exception
finally:
    # Some code .....(always executed)    
</pre>


```python
try:
    a=2
    print(a)
except:
    print("variable is not defined!")
```

    2
    


```python
try:
    a=2
    print(x) # x is not define
except:
    print("variable is not defined!")
```

    ['ai', 'ai']
    


```python
if y==y:
    print(y)
else:
    print("Else")
```

    Else
    


```python
try:
    print("The value of y: ",y)
except:
    print("Error")
```

    The value of y:  nan
    


```python
try:
    print(20/2)
except:
    print('Exception occured') # This statement will be execu

```

    10.0
    


```python
a = [1, 2, 3]
try:
    print ("Second element = %d" %(a[1]))
    # Throws error since there are only 3 elements in array
    print ("Fourth element = %d" %(a[4]))

except:
    print ("An error occurred")   
```

    Second element = 2
    An error occurred
    


```python
try:
    a=2
    print(a)
except:
    print("variable is not defined!")
else: # this will have to execute
    print("hey!")
```

    2
    hey!
    


```python
try:    
    a = int(input("Enter a:"))    
    b = int(input("Enter b:"))    
    c = a/b  
    print("a/b = %d"%c)  
    print(c)
# Using Exception with except statement. If we print(Exception) it will return exception class  
except:    
    print("can't divide by zero")    
#     print(Exception)  
else:    
    print("Hi I am else block")    
```

    Enter a:45
    Enter b:46
    a/b = 0
    0.9782608695652174
    Hi I am else block
    


```python
try:
    print("Hello")
except:
    print("Something went wrong")
else:
    print("Nothing went wrong")
```

    Hello
    Nothing went wrong
    


```python
# program to print the reciprocal of even numbers

try:
    num = int(input("Enter a number: "))
    assert num % 2 == 0
except:
    print("Not an even number!")
else:
    reciprocal = 1/num
    print(reciprocal)
```

    Enter a number: 
    Not an even number!
    


```python
try:    
    a = int(input("Enter a:"))    
    b = int(input("Enter b:"))    
    c = a/b  
    print("a/b = %d"%c)  
    print(c)
# Using Exception with except statement. If we print(Exception) it will return exception class  
except:    
    print("can't divide by zero")    
#     print(Exception)  
finally:
    print("Hi I am finally block")    
```

    Enter a:467
    Enter b:8
    a/b = 58
    58.375
    Hi I am finally block
    


```python
try:
    k = 5//0 # raises divide by zero exception.
    print(k)
    
# handles zerodivision exception	
except:
    print("Can't divide by zero")
        
finally:
    # this block is always executed
    # regardless of exception generation.
    print('This is always executed')

```

    Can't divide by zero
    This is always executed
    

 -------------------
