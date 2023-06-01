# <span style='color:green, font-family; times, serif; font-size:30pt; font-style:italic'>Chapter No # 9 Classes</span>

* What Is Classes?
* Uses Of Classes
* Syntax Of Classes
* First Program Of Classes
* Istance Attribute In Class
* Initializer In Class
* Method In Class
* Special Methods & Regular Method
* Creating Objects With Instance Data
* Inheritance In Class
* Constructors In Class
* Polymorphism In Class
* Abstraction In Class
* Encapsulation In Class


# <li style="font-size:20pt;">What Is Classes?</li>
A class is a code template for creating objects. Objects have member variables and have behavior associated with them. In Python, a class is created by the keyword class. An object is created using the constructor of the class. This object will then be called the instance of this class.
<ul>
    <li>A Class is an object constructor or a "blueprint" for creating objects. </li>
    <li>Objects are nothing but an encapsulation of variables and functions into a single entity. </li>
    <li>Objects get their variables and functions from classes.</li>
    <li>To create a class we use the keyword class. </li>
    <li>The first string inside the class is called docstring which gives the brief description about the class.</li>
    <li>All classes have a function called "__init__()" which is always executed when the class is being initiated.</li>
    <li>We can use init "__init__()" function to assign values to object properties or other operations that are necessary         to perform when the object is being created.</li>
    <li>The self parameter is a reference to the current instance of the class and is used to access class variables.</li>
    <li>self must be the first parameter of any function in the class.</li>
    <li>The super() built-in function returns a temporary object of the superclass that allows us to access methods of the         base class. </li>
    <li>super() allows us to avoid using the base class name explicitly and to enable multiple inheritance.</li>
</ul>

# <li style="font-size:20pt;">Uses Of Classes</li>
Object-Oriented Programming (OO) is a programming paradigm in which the data members and methods of a program are kept in one place, called a class. Using classes also provides another functionality of this object-oriented programming paradigm, that is, inheritance.

# <li style="font-size:20pt;">Syntax Of Classes</li>
<pre>
class myclass: 
	"""DocString""" 
	def __init__(self, var1, var2): 
		self.var1 = var1 
		self.var2 = var2 
	def myfunc1(self):
		print(self.var1) 
		print(self.var2)
</pre>
![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/6a546f3e-2265-4b9a-a114-e7f487f3d9ab)
<br><hr>
![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/bf68f678-0788-43db-91b4-612bd488cfb0)
<br><hr>
![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/3de91359-31b4-41d5-9122-cdccbbcb61cc)
<br><hr>
![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/9c86e6d0-3261-4d56-9599-e2dd0836ccb2)


# <li style="font-size:20pt;">First Program Of Classes</li>



```python
class Person:
    """This is a person class"""
    age = 10

print(Person.age)
```

    10
    


```python
class program:
    language = "Python"
    
p = program()
print(p.language)
```

    Python
    


```python
class detail:
    FirstName = "Muhammad"
    LastName = "Raheel"
    emailID = FirstName+LastName+"123@gmail.com"
    
p1 = detail()
print(p1.FirstName)
print(p1.LastName)
print(p1.emailID)
```

    Muhammad
    Raheel
    MuhammadRaheel123@gmail.com
    


```python
class square:
    num = 45
    sq = num*num
    
s1 = square()
print(s1.sq)
```

    2025
    


```python
class Dog:
    attr1 = "mammal"
    attr2 = "dog"

Rodger = Dog()
print("Name: ",Rodger.attr2)
print("Class: ",Rodger.attr1)
```

    Name:  dog
    Class:  mammal
    

# <li style="font-size:20pt;">Initializer | Constructors | Istance Attribute In Class</li>



```python
class person:
    # Special Method
    #initializer
    # 1.) They are always define inside the "initializer"
    # 2.) They are recommended inside the "initializer"
    # 3.) Whenever you creat new instance of a class, the call for initializer is must
    def __init__(self,name,age): # self is reference parameter into the current instance of class
        self.name=name # instance attribute
        self.age=age
        
p1 = person("Raheel",10)
print(p1.name)
print(p1.age)
```

    Raheel
    10
    


```python
class person:
    #initializer
    def __init__(self,name,age): # self is reference parameter into the current instance of class
        self.name=name # instance attribute
        self.age=age
        self.email=name+str(age)+"@gmail.com"
p1 = person("Raheel",10)
print(p1.name)
print(p1.age)
print(p1.email)
```

    Raheel
    10
    Raheel10@gmail.com
    


```python
class Employee:
    def __init__(self, first, last, pay):
        self.first = first
        self.last = last
        self.pay = pay
        self.email = first + '.' + last +'@mail.com'


emp1 = Employee("Ali", "Usman", 50000)
emp2 = Employee("Furqan", "Azhar", 20000)

print(emp1.email)
print(emp1.pay)
print(emp2.email)
print(emp2.pay)
```

    Ali.Usman@mail.com
    50000
    Furqan.Azhar@mail.com
    20000
    


```python
# Create an employee class
class Employee:
    def __init__(self, name, empid): # __init__() function is used to assign values
        self.name = name
        self.empid = empid

emp1 = Employee("Imran", 34163) # Create an employee object
print('Name :- ',emp1.name)
print('Employee ID :- ',emp1.empid)

```

    Name :-  Imran
    Employee ID :-  34163
    

# <li style="font-size:20pt;">Method In Class</li>


```python
class Person:
    def __init__(self, name, age):
        self.name = name
        self.age = age

    def myfunc(self):
        print("Hello my name is " + self.name)

p1 = Person("John", 36)
p1.myfunc()
```

    Hello my name is John
    


```python
# Create an employee class
class Employee:
    def __init__(self, name, empid): # __init__() function is used to assign values
        self.name = name
        self.empid = empid
    def greet(self): # Class Method
        print("Thanks for joining ABC Company {}!!".format(self.name))

emp1 = Employee("Imran", 34163) # Create an employee object
print('Name :- ',emp1.name)
print('Employee ID :- ',emp1.empid)
emp1.greet()
```

    Name :-  Imran
    Employee ID :-  34163
    Thanks for joining ABC Company Imran!!
    


```python
class Employee:
    def __init__(self, first, last, pay):
        self.first = first
        self.last = last
        self.pay = pay
        self.email = first + '.' + last +'@1992.com'

    def fullname(self):
        return '{} {}'.format(self.first, self.last)


emp1 = Employee("Ali", "Usman", 50000)
emp2 = Employee("Furqan", "Azhar", 20000)


print(emp1.fullname())
print(emp2.fullname())
```

    Ali Usman
    Furqan Azhar
    


```python
class Polygon:
    def __init__(self, sides, name):
        self.sides = sides
        self.name = name

    def work(self):
        print("Hello the work is goin on: ", self.name)

square = Polygon(4, "Square")
square.work()
```

    Hello the work is goin on:  Square
    


```python
class Person:
    def __init__(self, name, age):
        self.name = name
        self.age = age

    def myfunc(self,name2):
        print("Hello my name is " + name2)

p1 = Person("John", 36)
p1.myfunc("Raheel")
```

    Hello my name is Raheel
    


```python
class Person:
    "This is a person class"
    age = 10

    def greet(self):
        print('Hello')

harry = Person()
print(Person.greet)
print(harry.greet())
harry.greet()
```

    <function Person.greet at 0x0000019B752CF0D0>
    Hello
    None
    Hello
    

# <li style="font-size:20pt;">Special Methods & Regular Method</li>

Python's special methods give us complete control over the interfaces that we use to interact with objects. Special methods can also be referred to as "dunder" (double-underscore) methods. Learning to leverage special methods will enable us to design elegant and powerful classes of objects.


```python

```


```python

```

# <li style="font-size:20pt;">Inheritance In Class</li>
<ul>
    <li>Inheritance is a powerful feature in object oriented programming.</li>
    <li>Inheritance provides code reusability in the program because we can use an existing class (Super Class/Parent Class /       Base Class) to create a new class (Sub Class / Child Class / Derived Class) instead of creating it from scratch.</li>
    <li>The child class inherits data definitions and methods from the parent class which facilitates the reuse of features         already available. The child class can add few more definitions or redefine a base class method.</li>
    <li>Inheritance comes into picture when a new class possesses the 'IS A' relationship with an existing class. E.g Student       is a person. Hence person is the base class and student is derived class.</li>
</ul>

![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/84703aae-7fcb-47fa-bff4-a5819cad2144)
![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/20cf6eff-d0e5-4b9b-a2f1-df67ed5c403e)


```python
class Person:
    def __init__(self, fname, lname):
        self.firstname = fname
        self.lastname = lname

    def printname(self):
        print(self.firstname, self.lastname)

class Student(Person):
    pass

x = Student("Mike", "Olsen")
x.printname()

```

    Mike Olsen
    


```python
class person: # Parent Class
    def __init__(self, name , age , gender):
        self.name = name
        self.age = age
        self.gender = gender

    def PersonInfo(self):
        print('Name :- {}'.format(self.name))
        print('Age :- {}'.format(self.age))
        print('Gender :- {}'.format(self.gender))



class student(person): # Child Class
    def __init__(self,name,age,gender,studentid,fees):
        person.__init__(self,name,age,gender)
        self.studentid = studentid
        self.fees = fees

    def StudentInfo(self):
        print('Student ID :- {}'.format(self.studentid))
        print('Fees :- {}'.format(self.fees))


class teacher(person): # Child Class
    def __init__(self,name,age,gender,empid,salary):
        person.__init__(self,name,age,gender)
        self.empid = empid
        self.salary = salary

    def TeacherInfo(self):
        print('Employee ID :- {}'.format(self.empid))
        print('Salary :- {}'.format(self.salary))

stud1 = student('Asif' , 24 , 'Male' , 123 , 1200)
print('Student Details')
print('---------------')
stud1.PersonInfo() # PersonInfo() method presnt in Parent Class will be access
stud1.StudentInfo()
print()
teacher1 = teacher('Basit' , 36 , 'Male' , 456 , 80000)
print('Employee Details')
print('---------------')
teacher1.PersonInfo() # PersonInfo() method presnt in Parent Class will be acc
teacher1.TeacherInfo()
```

    Student Details
    ---------------
    Name :- Asif
    Age :- 24
    Gender :- Male
    Student ID :- 123
    Fees :- 1200
    
    Employee Details
    ---------------
    Name :- Basit
    Age :- 36
    Gender :- Male
    Employee ID :- 456
    Salary :- 80000
    


```python
class person: # Parent Class
    def __init__(self, name , age , gender):
        self.name = name
        self.age = age
        self.gender = gender
    def PersonInfo(self):
        print('Name :- {}'.format(self.name))
        print('Age :- {}'.format(self.age))
        print('Gender :- {}'.format(self.gender))



class student(person): # Child Class
    def __init__(self,name,age,gender,studentid,fees):
        person.__init__(self,name,age,gender)
        self.studentid = studentid
        self.fees = fees

    def StudentInfo(self):
        print('Student ID :- {}'.format(self.studentid))
        print('Fees :- {}'.format(self.fees))


stud1 = student('Asif' , 24 , 'Male' , 123 , 1200)
print('Student Details')
print('---------------')
stud1.PersonInfo() # PersonInfo() method presnt in Parent Class will be access
stud1.StudentInfo()
print()
```

    Student Details
    ---------------
    Name :- Asif
    Age :- 24
    Gender :- Male
    Student ID :- 123
    Fees :- 1200
    
    


```python
# Super Class
class Father:
    def __init__(self):
        self.fathername = str()

# Super Class
class Mother:
    def __init__(self):
        self.mothername = str()


# Sub Class
class Son(Father, Mother):
    name = str()
    def show(self):
        print('My Name :- ',self.name)
        print("Father :", self.fathername)
        print("Mother :", self.mothername)
s1 = Son()
s1.name = 'Bill'
s1.fathername = "John"
s1.mothername = "Kristen"
s1.show()

```

    My Name :-  Bill
    Father : John
    Mother : Kristen
    


```python
import datetime
class Date:
    def __init__(self,date):
        self.date = date

class Time:
    def __init__(self,time):
        self.time = time
class timestamp(Date,Time):
    def __init__(self,date,time):
        Date.__init__(self,date)
        Time.__init__(self,time)
        DateTime = self.date + ' ' + self.time
        print(DateTime)
        
datetime1 = timestamp( '2020-08-09', '23:48:55')
```

    2020-08-09 23:48:55
    

# <li style="font-size:20pt;">Polymorphism In Class</li>
The word polymorphism means having many forms. In programming, polymorphism means the same function name (but different signatures) being used for different types.


```python
class Pakistan():
    def capital(self):
        print("Islamabad is the capital of Pakistan.")

    def language(self):
        print("Urdu is the most widely spoken language of Pakistan.")

    def type(self):
        print("Pakistan is a developing country.")

class USA():
    def capital(self):
        print("Washington, D.C. is the capital of USA.")

    def language(self):
        print("English is the primary language of USA.")

    def type(self):
        print("USA is a developed country.")

obj_pak = Pakistan()
obj_usa = USA()
for country in (obj_pak, obj_usa):
    country.capital()
    country.language()
    country.type()

```

    Islamabad is the capital of Pakistan.
    Urdu is the most widely spoken language of Pakistan.
    Pakistan is a developing country.
    Washington, D.C. is the capital of USA.
    English is the primary language of USA.
    USA is a developed country.
    


```python
class Bird:
    def intro(self):
        print("There are many types of birds.")

    def flight(self):
        print("Most of the birds can fly but some cannot.")

class sparrow(Bird):
    def flight(self):
        print("Sparrows can fly.")
    
class ostrich(Bird):
    def flight(self):
        print("Ostriches cannot fly.")

obj_bird = Bird()
obj_spr = sparrow()
obj_ost = ostrich()

obj_bird.intro()
obj_bird.flight()

obj_spr.intro()
obj_spr.flight()

obj_ost.intro()
obj_ost.flight()

```

    There are many types of birds.
    Most of the birds can fly but some cannot.
    There are many types of birds.
    Sparrows can fly.
    There are many types of birds.
    Ostriches cannot fly.
    


```python
class Pakistan():
    def capital(self):
        print("Islamabad is the capital of Pakistan.")

    def language(self):
        print("Urdu is the most widely spoken language of Pakistan.")

    def type(self):
        print("Pakistan is a developing country.")

class USA():
    def capital(self):
        print("Washington, D.C. is the capital of USA.")

    def language(self):
        print("English is the primary language of USA.")

    def type(self):
        print("USA is a developed country.")

        
def func(obj):
    obj.capital()
    obj.language()
    obj.type()

    
obj_pak = Pakistan()
obj_usa = USA()
  
func(obj_pak)
func(obj_usa)
```

    Islamabad is the capital of Pakistan.
    Urdu is the most widely spoken language of Pakistan.
    Pakistan is a developing country.
    Washington, D.C. is the capital of USA.
    English is the primary language of USA.
    USA is a developed country.
    

# <li style="font-size:20pt;">Encapsulation In Class</li>

Encapsulation is one of the four fundamental concepts in object-oriented programming including abstraction, encapsulation, inheritance, and polymorphism. It describes the idea of wrapping data and the methods that work on it within one unit. A class is an example of encapsulation as it encapsulates all the data that is member functions, variables, etc.


```python
class Counter:
    def __init__(self):
        self.current = 0

    def increment(self):
        self.current += 1

    def value(self):
        return self.current

    def reset(self):
        self.current = 0

counter = Counter()


counter.increment()
counter.increment()
counter.increment()

print(counter.value())



```

    3
    


```python
class Parrot:

    # class attribute
    species = "bird"

    # instance attribute
    def __init__(self, name, age):
        self.name = name
        self.age = age

# instantiate the Parrot class
blu = Parrot("Blu", 10)
woo = Parrot("Woo", 15)

# access the class attributes
print("Blu is a {}".format(blu.__class__.species))
print("Woo is also a {}".format(woo.__class__.species))

# access the instance attributes
print("{} is {} years old".format( blu.name, blu.age))
print("{} is {} years old".format( woo.name, woo.age))
```

    Blu is a bird
    Woo is also a bird
    Blu is 10 years old
    Woo is 15 years old
    


```python
class Parrot:
    
    # instance attributes
    def __init__(self, name, age):
        self.name = name
        self.age = age
    
    # instance method
    def sing(self, song):
        return "{} sings {}".format(self.name, song)

    def dance(self):
        return "{} is now dancing".format(self.name)

# instantiate the object
blu = Parrot("Blu", 10)

# call our instance methods
print(blu.sing("'Happy'"))
print(blu.dance())
```

    Blu sings 'Happy'
    Blu is now dancing
    


```python
# parent class
class Bird:
    
    def __init__(self):
        print("Bird is ready")

    def whoisThis(self):
        print("Bird")

    def swim(self):
        print("Swim faster")

# child class
class Penguin(Bird):

    def __init__(self):
        # call super() function
        super().__init__()
        print("Penguin is ready")

    def whoisThis(self):
        print("Penguin")

    def run(self):
        print("Run faster")

peggy = Penguin()
peggy.whoisThis()
peggy.swim()
peggy.run()
```

    Bird is ready
    Penguin is ready
    Penguin
    Swim faster
    Run faster
    


```python
class Computer:

    def __init__(self):
        self.__maxprice = 900

    def sell(self):
        print("Selling Price: {}".format(self.__maxprice))

    def setMaxPrice(self, price):
        self.__maxprice = price

c = Computer()
c.sell()

# change the price
c.__maxprice = 1000
c.sell()

# using setter function
c.setMaxPrice(1000)
c.sell()
```

    Selling Price: 900
    Selling Price: 900
    Selling Price: 1000
    


```python
class Parrot:

    def fly(self):
        print("Parrot can fly")
    
    def swim(self):
        print("Parrot can't swim")

class Penguin:

    def fly(self):
        print("Penguin can't fly")
    
    def swim(self):
        print("Penguin can swim")

# common interface
def flying_test(bird):
    bird.fly()

#instantiate objects
blu = Parrot()
peggy = Penguin()

# passing the object
flying_test(blu)
flying_test(peggy)
```

    Parrot can fly
    Penguin can't fly
    

-------------- 
