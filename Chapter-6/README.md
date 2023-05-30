# <span style='color:green, font-family; times, serif; font-size:30pt; font-style:italic'>Chapter No # 6 Data Types:-Lists-Tuples-Dictionaries</span>

* What is List
* Syntax Of List
* Create Python Lists,
* Lists - Collections Of Data
* Sorting Simple Lists - The Bubble Sort Algorithm
* Update Python Lists,
* Copy Python Lists,
* Delete Elements From Python Lists,
* Nested Lists & Code Style
* Processing Nested Lists
* Split Method
* Python Tuples,
* Mutable Vs Imutable
* Access Tuples,
* Update Tuples,
* Unpack Tuples,
* Loop Tuples,
* Join Tuples,
* Tuple Methods,
* Python Sets,
* Access Set Items,
* Add Set Items,
* Remove Set Items,
* Loop Sets,
* Join Sets,
* Set Methods,
* Access Items,
* Change Items,
* Add Items,
* Remove Items,
* Loop Dictionaries,
* Copy Dictionaries,
* Nested Dictionaries,
* Dictionary Methods,




# <span style='font-family; times, serif; font-size:20pt;'>What is List | Syntax Of List</span>
Lists are one of the built-in data types in Python. They are used to store collections of data. Lists are created using square brackets, rather than curly brackets as in other data types such as tuples or dictates for organization and structure.

### Syntax:
lst = [] # here you can add items\Element

# <li style="font-size:20pt;">Create Python Lists | Lists - Collections Of Data | Indexing</li>


```python
lst = [] # Empty List
```


```python
print(type(lst))
```

    <class 'list'>
    


```python
list2 = [10,30,60] # List of integers numbers
print(list2)
```

    [10, 30, 60]
    


```python
list3 = [10.77,30.66,60.89] # List of float numbers
print(list3)
```

    [10.77, 30.66, 60.89]
    


```python
list4 = ['one','two' , "three"] # List of strings
print(list4)
```

    ['one', 'two', 'three']
    


```python
list5 = ['Asif', 25 ,[50, 100],[150, 90]] # Nested Lists
print(list5)
```

    ['Asif', 25, [50, 100], [150, 90]]
    


```python
list6 = [100, 'Asif', 17.765] # List of mixed data types
print(list6)
```

    [100, 'Asif', 17.765]
    


```python
list7 = ['Asif', 25 ,[50, 100],[150, 90] , {'John' , 'David'},("Raheel","Asad")]
# print(list7)
print(list7)
```

    ['Asif', 25, [50, 100], [150, 90], {'David', 'John'}, ('Raheel', 'Asad')]
    


```python
x=[1,2,2,5,4,5,47,8,7]
a = len(x) #Length of list
print(a)
```

    9
    

![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/dd14b0fc-11d6-4e1f-8421-7e7ca3c6471d)


```python
th = ["apple", "banana", "cherry"]
print(th)
```

    ['apple', 'banana', 'cherry']
    


```python
thislist = ["apple", "banana", "cherry", "apple", "cherry"]
print(thislist)
print(thislist[2])
print(thislist[-1])
```

    ['apple', 'banana', 'cherry', 'apple', 'cherry']
    cherry
    cherry
    


```python
lst = [1,2,3,4,5,6,7,8]
```


```python
lst[0] # Retreive first element of the list
```




    1




```python
lst[4:6]
```




    [5, 6]




```python
lst[6]
```




    7




```python
abc = ['john',"Wick","Albert",[1,2,5,3.42,3+6j,["Hello","Python"]]]
```


```python
abc[3]
```




    [1, 2, 5, 3.42, (3+6j), ['Hello', 'Python']]




```python
abc[2]
```




    'Albert'




```python
abc[3][3]
```




    3.42




```python
abc[3][2]
```




    5




```python
abc[3][5][0]
```




    'Hello'




```python
abc[3][5][1]
```




    'Python'




```python
emp = ["John", 102, "USA"]     
Dep1 = ["CS",10]  
Dep2 = ["IT",11]    
HOD_CS = [10,"Mr. Holding"]    
HOD_IT = [11, "Mr. Bewon"]    
print("printing employee data...")    
print("Name : %s, ID: %d, Country: %s"%(emp[0],emp[1],emp[2]))    
print("printing departments...")   
print("Department 1:\nName: %s, ID: %d\nDepartment 2:\nName: %s, ID: %s"
      %(Dep1[0],Dep1[1],Dep2[0],Dep2[1]))    
print("HOD Details ....")    
print("CS HOD Name: %s, Id: %d"%(HOD_CS[1],HOD_CS[0]))    
print("IT HOD Name: %s, Id: %d"%(HOD_IT[1],HOD_IT[0]))    
# print(type(emp),type(Dep1),type(Dep2),type(HOD_CS),type(HOD_IT))  
```

    printing employee data...
    Name : John, ID: 102, Country: USA
    printing departments...
    Department 1:
    Name: CS, ID: 10
    Department 2:
    Name: IT, ID: 11
    HOD Details ....
    CS HOD Name: Mr. Holding, Id: 10
    IT HOD Name: Mr. Bewon, Id: 11
    

# <li style="font-size:20pt;">Slicing List | Update Lists | Copy Lists | Delete Elements From Lists</li>


```python
mylist = ['one' , 'two' , 'three' , 'four' , 'five' , 'six' , 'seven' , 'eight']
```


```python
mylist[0:3] # Return all items from 0th to 3rd index location excluding the item 
```




    ['one', 'two', 'three']




```python
mylist[2:5] 
```




    ['three', 'four', 'five']




```python
mylist[-3:] 
```




    ['six', 'seven', 'eight']




```python
mylist = ['one', 'two', 'three', 'four', 'five', 'six', 'seven', 'eight'] # Updating
```


```python
mylist.append('nine') # Add an item to the end of the list
print(mylist)
```

    ['one', 'two', 'three', 'four', 'five', 'six', 'seven', 'eight', 'nine']
    


```python
mylist.insert(0,'ten') # Add item at index location 9
print(mylist)
```

    ['ten', 'one', 'two', 'three', 'four', 'five', 'six', 'seven', 'eight', 'nine']
    


```python
mylist.insert(1,'ONE') # Add item at index location 1
print(mylist)

```

    ['ten', 'ONE', 'one', 'two', 'three', 'four', 'five', 'six', 'seven', 'eight', 'nine']
    


```python
mylist.remove('ONE') # Remove item "ONE"
print(mylist)
```

    ['ten', 'one', 'two', 'three', 'four', 'five', 'six', 'seven', 'eight', 'nine']
    


```python
mylist.remove('nine')
mylist
```




    ['ten', 'one', 'two', 'three', 'four', 'five', 'six', 'seven', 'eight']




```python
lst = [1,1,1,3,3,4,5,6,6]
lst.remove(1)
lst
```




    [1, 1, 3, 3, 4, 5, 6, 6]




```python
mylist.pop(5) # Remove item at index location 8
mylist

```




    ['ten', 'one', 'two', 'three', 'four', 'six', 'seven', 'eight']




```python
mylist.pop() # Remove last item of the list
mylist
```




    ['ten', 'one', 'two', 'three', 'four', 'six', 'seven']




```python
mylist = ['one', 'two', 'three', 'four', 'five', 'six', 'seven', 'eight', 'nine','ten'] # copying
```


```python
mylist2 = mylist.copy() # Create a copy of the list
```


```python
mylist2 # Copy of list won't be impacted due to changes made on the original list
```




    ['one', 'two', 'three', 'four', 'five', 'six', 'seven', 'eight', 'nine', 'ten']




```python
import random

card = ["AD","KD","QD","JD","AH","KH","QH","JH",
       "AC","KC","QC","JC","AS","KS","QS","JS"]

print("without shuffle ",card)

random.shuffle(card)

print("With shuffle ",card)

```

    without shuffle  ['AD', 'KD', 'QD', 'JD', 'AH', 'KH', 'QH', 'JH', 'AC', 'KC', 'QC', 'JC', 'AS', 'KS', 'QS', 'JS']
    With shuffle  ['KC', 'JS', 'AH', 'QD', 'QH', 'JD', 'QS', 'JH', 'AS', 'JC', 'QC', 'KH', 'KD', 'AC', 'KS', 'AD']
    


```python
import random

card = ["AD","KD","QD","JD","AH","KH","QH","JH",
       "AC","KC","QC","JC","AS","KS","QS","JS"]
random.shuffle(card)

p1 = []
p2 = []
p3 = []
p4 = []
p5=[]

for i in range(0,4):
    p1.append(card[i])

for j in range(4,8):
    p2.append(card[j])

for k in range(8,12):
    p3.append(card[k])

for l in range(12,16):
    p4.append(card[l])
    
print("Player 1: ",p1)
print("Player 2: ",p2)
print("Player 3: ",p3)
print("Player 4: ",p4)

```

    Player 1:  ['QH', 'QD', 'KH', 'JH']
    Player 2:  ['AD', 'KD', 'JD', 'QS']
    Player 3:  ['AC', 'AH', 'AS', 'KC']
    Player 4:  ['KS', 'QC', 'JS', 'JC']
    

# <li style="font-size:20pt;">list() Constructor | Nested Lists</li> 


```python
thislist = list(("apple", "banana", "cherry")) # note the double round-brackets
print(thislist)
```

    ['apple', 'banana', 'cherry']
    


```python
text = 'Python'
text_list = list(text)
print(text_list)
print(type(text_list))
```

    ['P', 'y', 't', 'h', 'o', 'n']
    <class 'list'>
    


```python
print(list())
vowel_string = 'aeiou'
print(list(vowel_string))

vowel_tuple = ('a', 'e', 'i', 'o', 'u')
print(list(vowel_tuple))

vowel_list = ['a', 'e', 'i', 'o', 'u']
print(list(vowel_list))
```

    []
    ['a', 'e', 'i', 'o', 'u']
    ['a', 'e', 'i', 'o', 'u']
    ['a', 'e', 'i', 'o', 'u']
    

# <li style="fontsize:20pt;">List Comprehensions</li>
List Comprehensions provide an elegant way to create new lists.
It consists of brackets containing an expression followed by a for clause, then zero or more for
or if clauses.
![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/50cf9ace-fd3b-41ec-a85e-2dde83cc1046)


```python
mystring = "WELCOME"
mylist = [ i for i in mystring ] # Iterating through a string Using List Comprehension
mylist

```




    ['W', 'E', 'L', 'C', 'O', 'M', 'E']




```python
mylist1 = [ i for i in range(40) if i % 2 == 0] # Display all even numbers
mylist1

```




    [0, 2, 4, 6, 8, 10, 12, 14, 16, 18, 20, 22, 24, 26, 28, 30, 32, 34, 36, 38]




```python
mylist3 = [num**2 for num in range(10)] 
mylist3
```




    [0, 1, 4, 9, 16, 25, 36, 49, 64, 81]




```python
list1 = [2,3,4,5,6,7,8]
list1 = [i*10 for i in list1]
list1
```




    [20, 30, 40, 50, 60, 70, 80]




```python
mystr = "One 1 two 2 three 3 four 4 five 5 six 6789"
numbers = [i for i in mystr if i.isdigit()]
print(numbers)

```

    ['1', '2', '3', '4', '5', '6', '7', '8', '9']
    

# <li style="font-size:20pt;">What is Python Tuples</li>
Python has a built-in data type called a Tuple. Tuples are used to store multiple items in a single variable. They are the same as a List, Set, and Dictionary but are ordered and unchangeable.

# <li style="font-size:20pt;">Mutable Vs Imutable </li>
![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/d9188054-698b-4283-bfe7-c65cc644c37e)
![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/5a82e065-9819-4342-b425-e36d2a1d5072)

# <li style="font-size:20pt;">Syntax of Tuple</li>
<pre>
tp = tuple()
</pre>

# <li style="font-size:20pt;">Simple Program Of Tuple</li>



```python
thistuple = ("apple", "banana", "cherry")
print(thistuple)
print(type(thistuple))
```

    ('apple', 'banana', 'cherry')
    <class 'tuple'>
    


```python
tup = ('a','b','c',[1,2,3,4],{"key":"value"},True,3.25)
print(tup)
```

    ('a', 'b', 'c', [1, 2, 3, 4], {'key': 'value'}, True, 3.25)
    


```python
tuple1 = (0, 1, 2, 3)
print(tuple1)

```

    (0, 1, 2, 3)
    

# <li style="font-size:20pt;">Tuple Constructor | Indexing | Update  | Delete Elements From Tuples</li>


```python
x = tuple("Hello")
print(x)
```

    ('H', 'e', 'l', 'l', 'o')
    


```python
# b = (1,2,3,4,"5","6")
a = tuple((1,2,3,4,"5","6"))
print(a)
print(type(a))
print(len(a))
```

    (1, 2, 3, 4, '5', '6')
    <class 'tuple'>
    6
    


```python
tup = tuple(("hello","python",'Programmers'))
print(tup)
```

    ('hello', 'python', 'Programmers')
    


```python
x = tuple(('a','b','c',[1,2,3,4],{"key":"value"},True,3.25))
print(x)
```

    ('a', 'b', 'c', [1, 2, 3, 4], {'key': 'value'}, True, 3.25)
    


```python
a = ('a', 'b', 'c', [1, 2, 3, 4], {'key': 'value'}, True, 3.25)
print(a)
print(a[0])
```

    ('a', 'b', 'c', [1, 2, 3, 4], {'key': 'value'}, True, 3.25)
    a
    


```python
a = ('a', 'b', 'c', [1, 2, 3, 4], {'key': 'value'}, True, 3.25)
print(a)
print(a[2])
```

    ('a', 'b', 'c', [1, 2, 3, 4], {'key': 'value'}, True, 3.25)
    c
    


```python
a = ('a', 'b', 'c', [1, 2, 3, 4], {'key': 'value'}, True, 3.25)
print(a)
print(a[3])
```

    ('a', 'b', 'c', [1, 2, 3, 4], {'key': 'value'}, True, 3.25)
    [1, 2, 3, 4]
    


```python
a = ('a', 'b', 'c', [1, 2, 3, 4], {'key': 'value'}, True, 3.25)
print(a)
print(a[3][0])
```

    ('a', 'b', 'c', [1, 2, 3, 4], {'key': 'value'}, True, 3.25)
    1
    


```python
a = ('a', 'b', 'c', [1, 2, 3, 4], {'key': 'value'}, True, 3.25)
print(a)
print(a[3][2])
```

    ('a', 'b', 'c', [1, 2, 3, 4], {'key': 'value'}, True, 3.25)
    3
    


```python
a = ('a', 'b', 'c', [1, 2, 3, 4], {'key': 'value'}, True, 3.25)
print(a)
print(a[4])
```

    ('a', 'b', 'c', [1, 2, 3, 4], {'key': 'value'}, True, 3.25)
    {'key': 'value'}
    


```python
a = ('a', 'b', 'c', [1, 2, 3, 4], {'key': 'value',"Hello":"World!"}, True, 3.25)
print(a)
print(a[4]['key'])
```

    ('a', 'b', 'c', [1, 2, 3, 4], {'key': 'value', 'Hello': 'World!'}, True, 3.25)
    value
    


```python
a = ('a', 'b', 'c', [1, 2, 3, 4], {'key': 'value',"Hello":"World!"}, True, 3.25)
print(a)
print(a[4]["Hello"])
```

    ('a', 'b', 'c', [1, 2, 3, 4], {'key': 'value', 'Hello': 'World!'}, True, 3.25)
    World!
    


```python
a = ('a', 'b', 'c', [1, 2, 3, 4], {'key': 'value',"Hello":"World!"}, True, 3.25)
a[0] = "Apple"
```


    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    ~\AppData\Local\Temp\ipykernel_11484\905779835.py in <module>
          1 a = ('a', 'b', 'c', [1, 2, 3, 4], {'key': 'value',"Hello":"World!"}, True, 3.25)
    ----> 2 a[0] = "Apple"
    

    TypeError: 'tuple' object does not support item assignment



```python
a = ('a', 'b', 'c', [1, 2, 3, 4], {'key': 'value',"Hello":"World!"}, True, 3.25)
a = list(a)
a[1] = "Apple"
a = tuple(a)
print(a)
```


```python
a = ('a', 'b', 'c', [1, 2, 3, 4], {'key': 'value',"Hello":"World!"}, True, 3.25)
del a[1]
```


```python
del a
```

# <li style="font-size:20pt;">What is Python Sets</li>
Set is one of the built-in data types in Python used to store collections of data, the other 3 are List, Tuple, and Dictionary, all with different qualities and usage. A set is a collection which is unordered, unchangeable*, and unindexed, it is also called a set because it holds multiple items in a single variable.

# <li style="font-size:20pt;">Syntax of Set</li>

### set = { data types }

# <li style="font-size:20pt;">Simple Program Of Sets | Access Set Items | Remove Set Items</li>



```python
Set = {}
```


```python
myset = {1,2,3,4,5,1,2,3,4,5} # Set of numbers
print(myset)
```


```python
myset = {1,2,3,4,5,6}
len(myset) #Length of the set
```


```python
my_set = {1,1,2,2,3,4,5,5}
print(my_set) # Duplicate elements are not allowed.
```


```python
thisset = {"apple", "banana", "cherry", "apple"}
print(thisset)
```


```python
myset1 = {1.79,2.08,3.99,4.56,5.45} # Set of float numbers
print(myset1)
```


```python
myset3 = {10,20, "Hola", (11, 22, 32)} # Mixed datprintatypes
print(myset3)
```

# <li style="font-size:20pt;">Access Set Items</li>
You can access items in a set by referring to an index or key, but you can loop through the set items using a for loop, or ask if a specified value is present, by using the in keyword.


```python
x = {1, 2, 3, 4, 5,'cherry', 'banana', 'apple',(11, 22, 32), 10, 20, 'Hola'}
print("banana" in x)
```


```python
x = {1, 2, 3, 4, 5,'cherry', 'banana', 'apple',(11, 22, 32), 10, 20, 'Hola'}
print("Hola" in x)
```


```python
x = {1, 2, 3, 4, 5,'cherry', 'banana', 'apple',(11, 22, 32), 10, 20, 'Hola'}
print("Apple" in x)
```

# <li style="font-size:20pt;">Remove Set Items</li>


```python
x = {1, 2, 3, 4, 5,'cherry', 'banana', 'apple',(11, 22, 32), 10, 20, 'Hola'}
x.remove(1)
print(x)
```


```python
x = {1, 2, 3, 4, 5,'cherry', 'banana', 'apple',(11, 22, 32), 10, 20, 'Hola'}
x.remove("Hola")
print(x)
```

    {1, 2, 3, 4, 5, 'cherry', 'banana', (11, 22, 32), 10, 20, 'apple'}
    


```python
x = {1, 2, 3, 4, 5,'cherry', 'banana', 'apple',(11, 22, 32), 10, 20, 'Hola'}
x.remove("banana")
print(x)
```

    {1, 2, 3, 4, 5, 'cherry', (11, 22, 32), 10, 'Hola', 20, 'apple'}
    


```python
x = {1, 2, 3, 4, 5,'cherry', 'banana', 'apple',(11, 22, 32), 10, 20, 'Hola'}
x.remove(4)
print(x)
```

    {1, 2, 3, 5, 'cherry', 'banana', (11, 22, 32), 10, 'Hola', 20, 'apple'}
    

# <li style="font-size:20pt;">Add Set Items</li>


```python
x = {1, 2, 3, 5, 'cherry', 'apple', 'Hola', 10, 20, (11, 22, 32), 'banana'}
x.add("Mango")
print(x)
```

    {1, 2, 3, 'cherry', 5, (11, 22, 32), 'banana', 10, 'Hola', 'Mango', 20, 'apple'}
    


```python
x = {1, 2, 3, 5, 'cherry', 'apple', 'Hola', 10, 20, (11, 22, 32), 'banana'}
x.add("Apple")
print(x)
```

    {1, 2, 3, 'cherry', 5, (11, 22, 32), 'banana', 10, 'Apple', 'Hola', 20, 'apple'}
    


```python
x = {1, 2, 3, 5, 'cherry', 'apple', 'Hola', 10, 20, (11, 22, 32), 'banana'}
x.add("Python")
print(x)
```

    {1, 2, 3, 'cherry', 5, (11, 22, 32), 'banana', 'Python', 10, 'Hola', 20, 'apple'}
    

# <li style="font-size:20pt;">What is Dictionary</li>
![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/1a25a1f2-46a0-43ad-9d4d-e75d1fc6bf53)
Dictionaries are now sorted in Python version 3.7; before, they were unordered in Python versions 3.6 and prior. Data values are kept as key-value pairs in dictionaries. A dictionary is an organized collection that may be changed and does not permit duplications.
# <li style="font-size:20pt;">Syntax of Dictionary</li>
![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/c7064f63-4af0-494f-902a-a65f8df7597d)

# <li style="font-size:20pt;">Simple Program Of Dictionarie</li>


```python
dic = {"Key":"Value"}
print(dic)
print(type(dic))
```

    {'Key': 'Value'}
    <class 'dict'>
    


```python
mydict = {1:'one' , 2:'two' , 3:'three'} # dictionary with integer keys
mydict
```




    {1: 'one', 2: 'two', 3: 'three'}




```python
dic = {"brand": "BMW","model": "E30 M3","year": 1986}
print(dic)
```

    {'brand': 'BMW', 'model': 'E30 M3', 'year': 1986}
    


```python
dicc = {"list":[1,2,3,4],"Tuple":(1,2,3,4,5),"Set":{1,2,3,4,5}}
print(dicc)
```

    {'list': [1, 2, 3, 4], 'Tuple': (1, 2, 3, 4, 5), 'Set': {1, 2, 3, 4, 5}}
    


```python
dic = {1:'one' , 'A':'two' , 3:'three',3:'five',"jack":"Ace","Ace":"Jack"} 
print(dic)
```

    {1: 'one', 'A': 'two', 3: 'five', 'jack': 'Ace', 'Ace': 'Jack'}
    


# <li style="font-size:20pt;">Access Items </li>



```python
dic = {1:'one' , 'A':'two' , 3:'three',3:'five',"jack":"Ace","Ace":"Jack"} 
print(dic[1])
```

    one
    


```python
dic = {1:'one' , 'A':'two' , 3:'three',3:'five',"jack":"Ace","Ace":"Jack"} 
print(dic["A"])
```

    two
    


```python
dic = {1:'one' , 'A':'two' , 3:'three',3:'five',"jack":"Ace","Ace":"Jack"} 
print(dic["jack"])
```

    Ace
    


```python
dic = {1:'one' , 'A':'two' , 3:'three',3:'five',"jack":"Ace","Ace":"Jack"} 
print(dic["Ace"])
```

    Jack
    


```python
dicc = {"list":[1,2,3,4],"Tuple":(1,2,3,4,5),"Set":{1,2,3,4,5}}
print(dicc["list"])
```

    [1, 2, 3, 4]
    


```python
dicc = {"list":[1,2,3,4],"Tuple":(1,2,3,4,5),"Set":{1,2,3,4,5}}
print(dicc["list"][2])
```

    3
    


```python
dicc = {"list":[1,2,3,4],"Tuple":(1,2,3,4,5),"Set":{1,2,3,4,5}}
print(dicc["Tuple"][2])
```

    3
    


```python
dicc = {"list":[1,2,3,4],"Tuple":(1,2,3,4,5),"Set":{1,2,3,4,5}}
print(dicc["list"][3])
```

    4
    

# <li style="font-size:20pt;">Change Items</li>


```python
dic = {1:'one' , 'A':'two' , 3:'three',3:'five',"jack":"Ace","Ace":"Jack"}
dic["Ace"] = "card"
print(dic)
```

    {1: 'one', 'A': 'two', 3: 'five', 'jack': 'Ace', 'Ace': 'card'}
    


```python
dic = {1:'one' , 'A':'two' , 3:'three',3:'five',"jack":"Ace","Ace":"Jack"}
dic["jack"] = "Joker"
print(dic)
```

    {1: 'one', 'A': 'two', 3: 'five', 'jack': 'Joker', 'Ace': 'Jack'}
    


```python
dic = {"list":[1,2,3,4],"Tuple":(1,2,3,4,5),"Set":{1,2,3,4,5}}
dic["Tuple"] = ("A","B","C","D")
print(dic)
```

    {'list': [1, 2, 3, 4], 'Tuple': ('A', 'B', 'C', 'D'), 'Set': {1, 2, 3, 4, 5}}
    


```python
dic = {"list":[1,2,3,4],"Tuple":(1,2,3,4,5),"Set":{1,2,3,4,5}}
dic["Set"] = "Value"
print(dic)
```

    {'list': [1, 2, 3, 4], 'Tuple': (1, 2, 3, 4, 5), 'Set': 'Value'}
    

# <li style="font-size:20pt;">Add Items</li>



```python
dic = {"list":[1,2,3,4],"Tuple":(1,2,3,4,5),"Set":{1,2,3,4,5}}
dic["Operator"] = "Addition"
print(dic)
```

    {'list': [1, 2, 3, 4], 'Tuple': (1, 2, 3, 4, 5), 'Set': {1, 2, 3, 4, 5}, 'Operator': 'Addition'}
    


```python
dic = {"list":[1,2,3,4],"Tuple":(1,2,3,4,5),"Set":{1,2,3,4,5}}
dic["Programming"] = "Python"
print(dic)
```

    {'list': [1, 2, 3, 4], 'Tuple': (1, 2, 3, 4, 5), 'Set': {1, 2, 3, 4, 5}, 'Programming': 'Python'}
    


```python
dic = {"list":[1,2,3,4],"Tuple":(1,2,3,4,5),"Set":{1,2,3,4,5}}
dic["IoT"] = "With Python Programming"
print(dic)
```

    {'list': [1, 2, 3, 4], 'Tuple': (1, 2, 3, 4, 5), 'Set': {1, 2, 3, 4, 5}, 'IoT': 'With Python Programming'}
    

# <li style="font-size:20pt;">Remove Items</li>



```python
x = {'list': [1, 2, 3, 4], 'Tuple': (1, 2, 3, 4, 5),'Set': {1, 2, 3, 4, 5}, 
     'IoT': 'With Python Programming','Programming': 'Python','Operator': 'Addition'}
x.pop("list")
print(x)
```

    {'Tuple': (1, 2, 3, 4, 5), 'Set': {1, 2, 3, 4, 5}, 'IoT': 'With Python Programming', 'Programming': 'Python', 'Operator': 'Addition'}
    


```python
x = {'list': [1, 2, 3, 4], 'Tuple': (1, 2, 3, 4, 5),'Set': {1, 2, 3, 4, 5}, 
     'IoT': 'With Python Programming','Programming': 'Python','Operator': 'Addition'}
x.pop("IoT")
print(x)
```

    {'list': [1, 2, 3, 4], 'Tuple': (1, 2, 3, 4, 5), 'Set': {1, 2, 3, 4, 5}, 'Programming': 'Python', 'Operator': 'Addition'}
    


```python
x = {'list': [1, 2, 3, 4], 'Tuple': (1, 2, 3, 4, 5),'Set': {1, 2, 3, 4, 5}, 
     'IoT': 'With Python Programming','Programming': 'Python','Operator': 'Addition'}
x.pop("Tuple")
print(x)
```

    {'list': [1, 2, 3, 4], 'Set': {1, 2, 3, 4, 5}, 'IoT': 'With Python Programming', 'Programming': 'Python', 'Operator': 'Addition'}
    


```python
x = {'list': [1, 2, 3, 4], 'Tuple': (1, 2, 3, 4, 5),'Set': {1, 2, 3, 4, 5}, 
     'IoT': 'With Python Programming','Programming': 'Python','Operator': 'Addition'}
print(x)
x.popitem()
print(x)
```

    {'list': [1, 2, 3, 4], 'Tuple': (1, 2, 3, 4, 5), 'Set': {1, 2, 3, 4, 5}, 'IoT': 'With Python Programming', 'Programming': 'Python', 'Operator': 'Addition'}
    {'list': [1, 2, 3, 4], 'Tuple': (1, 2, 3, 4, 5), 'Set': {1, 2, 3, 4, 5}, 'IoT': 'With Python Programming', 'Programming': 'Python'}
    


```python
x = {'list': [1, 2, 3, 4], 'Tuple': (1, 2, 3, 4, 5),'Set': {1, 2, 3, 4, 5}, 
     'IoT': 'With Python Programming','Programming': 'Python','Operator': 'Addition'}
del x
print(x)
```


    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    ~\AppData\Local\Temp\ipykernel_11484\926779698.py in <module>
          2      'IoT': 'With Python Programming','Programming': 'Python','Operator': 'Addition'}
          3 del x
    ----> 4 print(x)
    

    NameError: name 'x' is not defined



```python
x = {'list': [1, 2, 3, 4], 'Tuple': (1, 2, 3, 4, 5),'Set': {1, 2, 3, 4, 5}, 
     'IoT': 'With Python Programming','Programming': 'Python','Operator': 'Addition'}
print(x)
x.clear()
print(x)
```

    {'list': [1, 2, 3, 4], 'Tuple': (1, 2, 3, 4, 5), 'Set': {1, 2, 3, 4, 5}, 'IoT': 'With Python Programming', 'Programming': 'Python', 'Operator': 'Addition'}
    {}
    

# <li style="font-size:20pt;">Copy Dictionaries</li>



```python
x = {'list': [1, 2, 3, 4], 'Tuple': (1, 2, 3, 4, 5),'Set': {1, 2, 3, 4, 5}, 
     'IoT': 'With Python Programming','Programming': 'Python','Operator': 'Addition'}
after_copy = x.copy()

print(after_copy)
```

    {'list': [1, 2, 3, 4], 'Tuple': (1, 2, 3, 4, 5), 'Set': {1, 2, 3, 4, 5}, 'IoT': 'With Python Programming', 'Programming': 'Python', 'Operator': 'Addition'}
    


```python
dic = {1:'one' , 'A':'two' , 3:'three',3:'five',"jack":"Ace","Ace":"Jack"}
dic_copy = dic.copy()
print(dic)
```

    {1: 'one', 'A': 'two', 3: 'five', 'jack': 'Ace', 'Ace': 'Jack'}
    


```python
student_data = {"Ali":12345,"Faran":45678,"Taha":234234,"Zeeshan":234234,"Kaleem":234525,"Asif":234234,"Faizan":34234}
data = student_data.copy()
print(data)
```

    {'Ali': 12345, 'Faran': 45678, 'Taha': 234234, 'Zeeshan': 234234, 'Kaleem': 234525, 'Asif': 234234, 'Faizan': 34234}
    

# <li style="font-size:20pt;">Dictionary Constructor</li>
The dict() python function is a constructor that is used to create dictionaries. A dictionary is a data structure in Python that contains elements in the form of a value and its respective key. It is a collection of data that is unordered, indexed, and can be changed.


```python
x = dict(name = "John", age = 36, country = "Norway")
print(x)
```

    {'name': 'John', 'age': 36, 'country': 'Norway'}
    


```python
dic = dict({1:'one' , 2:'two' , 3:'three'}) 
print(dic)
```

    {1: 'one', 2: 'two', 3: 'three'}
    


```python
my_dict = dict([(1,'apple'), (2,'ball')])
print(my_dict)
```

    {1: 'apple', 2: 'ball'}
    


```python
const = dict({1: 'one', 'A': 'two', 3: 'five', 'jack': 'Ace', 'Ace': 'Jack'})
print(const)
```

    {1: 'one', 'A': 'two', 3: 'five', 'jack': 'Ace', 'Ace': 'Jack'}
    

# <li style="font-size:20pt;">.fromkeys()</li>


```python
keys = {'a' , 'b' , 'c' , 'd'} # set
value = "value"
newdict = dict.fromkeys(keys,value)
print(newdict)
```

    {'c': 'value', 'a': 'value', 'b': 'value', 'd': 'value'}
    


```python
keys = {'a' , 'b' , 'c' , 'd'}
value = [10,'values']
newdict = dict.fromkeys(keys,value)
print(newdict)
```

    {'c': [10, 'values'], 'a': [10, 'values'], 'b': [10, 'values'], 'd': [10, 'values']}
    


```python
keys = {'a' , 'b' , 'c' , 'd'}
value = [10,'values']
value.append('items')
newdict = dict.fromkeys(keys,value)
print(newdict)
```

    {'c': [10, 'values', 'items'], 'a': [10, 'values', 'items'], 'b': [10, 'values', 'items'], 'd': [10, 'values', 'items']}
    


```python
ids = {"id_1":
      {
          "name":"Ali",
          "fname":"Imran",
          "age":24,
          "Class":[14,"BS-Depart","Software Eng"]
      },
      "id_2":
      {
          "name":"Faran",
          "fname":"Iran",
          "age":55,
          "Class":[140,"BS-Departs","Software Eng"]
      },
      "id_3":
      {
          "name":"Aliza",
          "fname":"abc",
          "age":240,
          "Class":[14,"BS-Depart","Software Eng"]
      },
      "id_4":
      {
          "name":"Gul",
          "fname":"Faraz",
          "age":24,
          "Class":[14,"BS-Depart","Software Eng"]
      }}
print(ids)
```

    {'id_1': {'name': 'Ali', 'fname': 'Imran', 'age': 24, 'Class': [14, 'BS-Depart', 'Software Eng']}, 'id_2': {'name': 'Faran', 'fname': 'Iran', 'age': 55, 'Class': [140, 'BS-Departs', 'Software Eng']}, 'id_3': {'name': 'Aliza', 'fname': 'abc', 'age': 240, 'Class': [14, 'BS-Depart', 'Software Eng']}, 'id_4': {'name': 'Gul', 'fname': 'Faraz', 'age': 24, 'Class': [14, 'BS-Depart', 'Software Eng']}}
    


```python
from pprint import pprint
ids = {"id_1":
      {
          "name":"Ali",
          "fname":"Imran",
          "age":24,
          "Class":[14,"BS-Depart","Software Eng"]
      },
      "id_2":
      {
          "name":"Faran",
          "fname":"Iran",
          "age":55,
          "Class":[140,"BS-Departs","Software Eng"]
      },
      "id_3":
      {
          "name":"Aliza",
          "fname":"abc",
          "age":240,
          "Class":[14,"BS-Depart","Software Eng"]
      },
      "id_4":
      {
          "name":"Gul",
          "fname":"Faraz",
          "age":24,
          "Class":[14,"BS-Depart","Software Eng"]
      }}
pprint(ids)
```

    {'id_1': {'Class': [14, 'BS-Depart', 'Software Eng'],
              'age': 24,
              'fname': 'Imran',
              'name': 'Ali'},
     'id_2': {'Class': [140, 'BS-Departs', 'Software Eng'],
              'age': 55,
              'fname': 'Iran',
              'name': 'Faran'},
     'id_3': {'Class': [14, 'BS-Depart', 'Software Eng'],
              'age': 240,
              'fname': 'abc',
              'name': 'Aliza'},
     'id_4': {'Class': [14, 'BS-Depart', 'Software Eng'],
              'age': 24,
              'fname': 'Faraz',
              'name': 'Gul'}}
    

----------------
