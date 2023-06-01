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
    

# <li style="font-size:20pt;">What Is Regex - Regular Expression?</li>
Regular Expressions are used to match strings of text such as particular characters, words, or patterns of characters. RegEx can be used to check if a string contains the specified search pattern. It means that we can match and extract any string pattern from the text with the help of regular expressions.

# <li style="font-size:20pt;">Use Of Regex- Regular Expression.</li>

### `MetaCharacters`
Metacharacters are characters that are interpreted in a special way by a RegEx engine. Here's a list of metacharacters:

[] . ^ $ * + ? {} () \ |


```python
import re

txt = "The rain in Spain"
x = re.search("^The.*Spain$", txt)
print(x)
```

    <re.Match object; span=(0, 17), match='The rain in Spain'>
    


```python
import re

pattern = '^a...s$'
test_string = 'abyss'
result = re.match(pattern, test_string)

if result:
    print("Search successful.")
else:
    print("Search unsuccessful.")

```

    Search successful.
    


```python
import re

txt = "The rain in Spain"
x = re.findall("ai", txt)
print(x)
```

    ['ai', 'ai']
    


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
    


```python
import re

# \d is equivalent to [0-9].
p = re.compile('\d')
print(p.findall("I went to him at 11 A.M. on 4th July 1886"))

# \d+ will match a group on [0-9], group
# of one or greater size
p = re.compile('\d+')
print(p.findall("I went to him at 11 A.M. on 4th July 1886"))

```

    ['1', '1', '4', '1', '8', '8', '6']
    ['11', '4', '1886']
    

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
