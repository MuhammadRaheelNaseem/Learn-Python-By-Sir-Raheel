# <span style='color:green, font-family; times, serif; font-size:30pt; font-style:italic'>Chapter No # 11 GUI - Graphical User Interface</span>

* What Is Gui - Graphical User Interface?
* Installation Tkinter Library
* Used Of Gui
* Syntax Of Tkinter
* Creating First Gui Window
* Label In Tkinter | Button In Tkinter | Entry In Tkinter | Checkbutton In Tkinter | Radiobutton In Tkinter
* Frame In Tkinter | Listbox In Tkinter | Text In Tkinter | Menubutton In Tkinter | Menu In Tkinter
* Scale In Tkinter | Scrollbar In Tkinter | Panedwindow In Tkinter | Labelframe In Tkinter | Messagebox
* Message In Tkinter | Toplevel In Tkinter | Canvas In Tkinter | Combobox In Tkinter


# <li style='font-size:20pt'>What Is Gui - Graphical User Interface?</li>
A graphical user interface (GUI) is an interface through which a user interacts with electronic devices such as computers and smartphones. GUIs graphically display information and related user controls, unlike text-based interfaces, where data and commands are strictly in text. They are intuitive enough to be operated even by relatively unskilled personnel who have no knowledge of any programming language.

# <li style='font-size:20pt'>History Of Gui</li>
Xerox Palo Alto research laboratory created GUIs, now common in Windows, macOS and many software applications. By using specially designed and labeled images, pictures, shapes and color combinations, objects were depicted on the computer screen that resembled the operation to be performed, or were intuitively recognized by the user. In 1983, Apple introduced the first commercial use of a GUIs in the Lisa computer, followed shortly thereafter by the much more famous Apple Macintosh. Information is presented to the user via visual widgets that can be manipulated without the need for command codes. The same application software or operating system may present different or slightly different GUIs as it is patched and evolves. Many GUIs use standard formats for representing text and graphical elements (such as fonts or scroll bars).

# <li style='font-size:20pt'>Used Of Gui</li>
The graphical user interface (GUI) is a computer program that enables a person to communicate with a computer through the use of symbols, visual metaphors, and pointing devices. Its goal is to present the user with decision points that are easy to find, understand and use. In other words, it lets you control your device with a mouse, pen or even your finger.

# <li style='font-size:20pt'>What is Tkinter</li>
In this lecture we will be using Tkinter, which is a standard library in python used for creating Graphical User Interface (GUI) for Desktop Applications. The primary toolkit for developing desktop applications is Tk - which is Python's default GUI library. We'll access Tk from its Python interface via the 'Tkinter' tab on the left hand side of the page.

# <li style='font-size:20pt'>Installation Tkinter Library</li>
it doesn't need to install tkinter because it's already in our system it's also a built-in library.
### `pip install tkinter`

# <li style='font-size:20pt'>Syntax Of Tkinter</li>
<pre>
from tkinter import *

gui = Tk()

gui.mainloop()
</pre>

# <li style='font-size:20pt'>Creating First Gui Window</li>



```python
# Syntax:

import tkinter
from tkinter import *
# from tkinter import Button
# from tkinter import Label
# from tkinter import messagebox
# from tkinter import Text
# from tkinter import Entry
```


```python
# import GUI library with this method
from tkinter import * 

gui = Tk() # initialize Tk() in tkinter library. It help to create only window
print("First GUI!")

# nothing will be show because we haven't call window | Display
```


```python
# import GUI library with this method
from tkinter import * 

# initialize Tk() in tkinter library. It help us to create only window
gui = Tk()

gui.mainloop() # if we want to view GUI window we only use .mainloop() method to view window
```

![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/441875b9-6275-43f9-a699-c113ec22648b)


```python
# import GUI library with this method
from tkinter import * 

# initialize Tk() in tkinter library. It help us to create only window
gui = Tk()

if __name__=="__main__":
    print(__name__)
    # if we want to view GUI window we only type .mainloop() to view window
    gui.mainloop() 
```

# <li style="font-size:20pt;">Title in Tkinter</li> 


```python
# import tkinter as tk

gui = Tk()

gui.title('Python First GUI') # .title used to give title gui window whatever you can in string form

gui.mainloop()
```

![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/a030a062-0f16-4cd1-8b9d-9396e78c8cfc)


```python
from tkinter import * # it we import all method/functions 

gui = Tk()

gui.title('GUI') # .title used to give title gui window whatever you can in string form

gui.mainloop()
```

![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/33f10b62-64ab-4e39-b8a0-a6b0bd5660de)

# <li style="font-size:20pt;">Geometry in Tkinter </li>


```python
from tkinter import *

gui = Tk()

gui.geometry('545x351') # .geometry take argument for set gui heigth or width in string form

gui.mainloop()
```

![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/0ebf6f6a-9e27-4115-852c-517a47ccd41c)


```python
from tkinter import *

gui = Tk()

gui.title('GUI') # .title used to give title gui window whatever you can in string form
gui.geometry('400x400') # .geometry take argument for set gui heigth or width in string form

gui.mainloop()
```

![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/cff24a72-5a7a-4e46-933c-1808cdaf6d3d)

# <li style='font-size:20pt'>Configuration In Tkinter</li>


```python
from tkinter import *

gui = Tk()

gui.title('GUI ')
gui.geometry('400x400')
gui.configure(background="gold") #change screen background color

gui.mainloop()
```

![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/6df26984-4ae5-4b5d-9d8b-b78c8633957e)


```python
from tkinter import *

gui = Tk()

gui.title('GUI ')
gui.geometry('400x400')
gui.configure(bg='black') #change screen background color

gui.mainloop()
```

![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/607d062b-28f4-4a33-a1d8-9562edacb203)

# <li style='font-size:20pt'>Attributes In Tkinter</li>


```python
from tkinter import *

gui = Tk()

gui.configure(bg='gold') #change screen background color
gui.attributes("-fullscreen",True) # it will show fullscreen
#.attributes take *args 
gui.mainloop()
```

Output;
![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/680fd5c4-8e34-403f-b1f9-df08eb09d2c5)



```python
from tkinter import *

gui = Tk()

gui.title('GUI ')
gui.geometry('400x400')
gui.configure(bg='black') #change screen background color
gui.attributes("-fullscreen",False) # it will show normal screen

gui.mainloop()
```

![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/5de62296-0b02-4888-86f2-4017b7770599)



```python
from tkinter import *

gui = Tk()

gui.title('GUI ')
gui.geometry('400x400')
gui.configure(bg='black') #change screen background color
gui.attributes('-alpha',0.6) # if define opacity/Transparancy of screen
# value of transparancy start from 0.0 to 1 e.g 0.1, 0.2, 0.3, 0.8, 0.006, 0.9, 1

gui.mainloop()
```
![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/1666d466-451e-4b84-98c0-996b274d6fa6)



```python
from tkinter import *

gui = Tk()

gui.configure(bg='blue') #change screen background color
gui.attributes("-fullscreen",True,'-alpha',0.8) # show fullscreen opacity

gui.mainloop()
```

![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/2c64cae2-4142-433a-8a49-76ad048e1bd5)


# Minsize | Maxsize | Resizable


```python
from tkinter import *

gui = Tk()
gui.geometry("400x400+300+200")
# .minsize() will help us to not minimize window, it takes 2 arguments first width second height as you see
gui.minsize(400,400) 

# .maxsize() will help us to not maximize window, it takes 2 arguments first width second height as you see
gui.maxsize(400,400) 

# .resiable() helps to lock maxmize button which locate to before close window button 
gui.resizable(0,0)

gui.mainloop()
```

![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/4c2c58d5-5794-4a2a-8096-aa6601b65f81)



```python
from tkinter import *

gui = Tk()
gui.geometry("400x400+300+200")

gui.resizable(True,True)

gui.mainloop()
```

![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/b26e4634-0e5a-44b8-a962-348c1087957b)



```python
from tkinter import *

gui = Tk()
gui.geometry("400x400+300+200")

gui.resizable(True,0) # only for one side

gui.mainloop()
```
![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/4e3bbdd7-563d-4a62-8d05-79ec60018289)


# <li style='font-size:20pt'>Label In Tkinter</li>
The Label is used to specify the container box where we can place text or images. There are various options which can be specified to configure the text or part of the text shown in the Label. The syntax to use the Label is given below. It provides the information to the user about other widgets used in the application.


```python
from tkinter import *

gui = Tk()

gui.title('GUI ')

# we create button successfully but button will not show because we haven't call button
btn = Label(gui,text="First Python Button") 

gui.mainloop()
```
![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/7fd4965b-05c1-4f04-b4e9-e25792fa171b)



```python
from tkinter import *

root = Tk()

lb = Label(root , text = "ROOT Label")
lb.pack() # .pack() helps us to view button in GUI window

root.mainloop()

```
![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/bfcd46d9-5e89-4b52-91c9-140a9d478b02)



<h2><strong>Geometry:</strong></h2>
<p>The Tkinter geometry specifies the method by using which, the widgets are represented on display. The python Tkinter provides the following geometry methods.</p>
<ol>
<li>The pack() method</li>
<li>The grid() method</li>
<li>The place() method</li>
</ol>
<p><br />Let's discuss each one of them in detail.</p>
<h2><strong>1.) Pack():</strong></h2>
<p>The pack() widget is used to organize widgets in the block. The positions widgets added to the python application using the pack() method can be controlled by using the various options specified in the method call.</p>
<p>However, the controls are fewer, and widgets are generally added in a less organized manner. T<br />The syntax to use the pack() is given below.</p>
<p>Syntax:<br />btn.pack(options)</p>
<p>A list of possible options that can be passed in pack() is given below.</p>
<p><br /><strong>expand:</strong> If the expand is set to true, the widget expands to fill any space.<br /><strong>Fill:</strong> By default, the fill is set to NONE. However, we can set it to X or Y to determine whether the widget contains any extra space.<br /><strong>size:</strong> it represents the side of the parent to which the widget is to be placed on the window.</p>


```python
from tkinter import *

gui = Tk()
gui.geometry("400x400")

lb = Label(gui , text = "This is Label")
lb.pack() # .pack() helps us to view button in GUI window

gui.mainloop()

```

![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/ca686297-f94c-4165-9f47-bb0c79bbd10a)



```python
from tkinter import *

gui = Tk()
gui.geometry("400x400")

lb = Label(gui , text = "This is Label")
lb.pack(side=BOTTOM) # .pack() helps us to view button in GUI window

gui.mainloop()

```
![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/be35cfeb-752d-495b-a5b3-c764c048d354)



```python
from tkinter import *

gui = Tk()
gui.geometry("400x400")

lb = Label(gui , text = "This is Label")
lb.pack(side=LEFT)  # It will show left side
# lb.pack(side=RIGHT) # It will show right side
# lb.pack(side=TOP)   # It will show top side
# lb.pack(side=BOTTOM) # .pack() helps us to view button in GUI window

gui.mainloop()

```
![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/3dcbb0a8-9d29-44b4-8a1c-86106c70525c)



```python
from tkinter import *

gui = Tk()

gui.title('GUI ')
gui.geometry("400x400")

lb1 = Label(gui,text="LEFT Label")
lb1.pack(side=LEFT)  # It will show left side

lb2 = Label(gui,text="RIGHT Label")
lb2.pack(side=RIGHT) # It will show right side

lb3 = Label(gui,text="TOP Label")
lb3.pack(side=TOP)   # It will show top side

lb4 = Label(gui,text="BOTTOM Label")
lb4.pack(side=BOTTOM)  # It will show bottom side

gui.mainloop()
```

![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/63a136db-b3d9-4595-b349-174b3a548f28)



```python
from tkinter import *

gui = Tk()

gui.title('GUI ')
gui.geometry("400x400")

lb1 = Label(text="Label No # 1")
lb1.pack(side=BOTTOM, pady=50) # pady will be downward

gui.mainloop()
```

![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/854b318a-0edc-40cc-88ed-b05ad228b6e8)



```python
from tkinter import *

gui = Tk()

gui.title('GUI ')
gui.geometry("400x400")

button1 = Label(gui,text="Label From Tkinter")
button1.pack(padx=100, pady=160) # pady will be downward, forward

gui.mainloop()
```

![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/60c4a347-cec6-40b7-9bc0-36098eac48be)



```python
from tkinter import *

gui = Tk()

gui.title('GUI ')
gui.geometry("400x400")

lb1 = Label(gui, text = "Have You See me!")
lb1.pack(fill = BOTH, expand = True)

# Button 2
lb2 = Label(gui, text = "I am waiting your answer!")
lb2.pack(fill = BOTH, expand = True)

gui.mainloop()
```

![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/c5560efb-97eb-4699-a114-5380ef9aac74)


<h2>2.) place():</h2>
<p>The place() geometry manager organizes the widgets to the specific x and y coordinates.</p>
<h2>Syntax:</h2>
<p>gui.place(options)</p>
<p>A list of possible options is given below.</p>
<p><strong>Anchor:</strong> It represents the exact position of the widget within the container. The default value (direction) is NW (the upper left corner)<br /><strong>bordermode:</strong> The default value of the border type is INSIDE that refers to ignore the parent's inside the border. The other option is OUTSIDE.<br /><strong>height, width:</strong> It refers to the height and width in pixels. <br /><strong>relheight, relwidth:</strong> It is represented as the float between 0.0 and 1.0 indicating the fraction of the parent's height and width. <br /><strong>relx, rely:</strong> It is represented as the float between 0.0 and 1.0 that is the offset in the horizontal and vertical direction. <br /><strong>x, y:</strong> It refers to the horizontal and vertical offset in the pixels.</p>


```python
from tkinter import *

gui = Tk()

gui.title('GUI ')
gui.geometry("400x400")

lb = Label(gui,text="First Python Label by Place()")
lb.place(x=0 , y=0) # x,y take coordinnate for position of button

gui.mainloop()
```

![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/b9119763-5ff1-4415-b6ec-cd07fb759443)



```python
from tkinter import *

gui = Tk()

gui.title('GUI ')
gui.geometry("400x400")

lb = Label(gui,text="First Python Label by Place()")
# if x value 100 y value 200 it mean it will move downward and forward
lb.place(x=100,y=200)# x,y take coordinnate for position of button

gui.mainloop()
```

![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/8d732d9f-16e9-4033-9bd9-b176fa6bd974)


<h2 style="text-align: justify;">Grid():</h2>
<p style="text-align: justify;">The Grid geometry manager puts the widgets in a 2-dimensional table. The master widget is split into a number of rows and columns, and each "cell" in the resulting table can hold a widget. The grid manager is the most flexible of the geometry managers in Tkinter. If you don't want to learn how and when to use all three managers, you should at least make sure to learn this one. Consider the following <br />example:</p>

![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/653b639b-559d-464e-987b-554afe9a3c5c)



```python
from tkinter import *

gui = Tk()

gui.title('GUI ')
gui.geometry("400x400")

lb = Label(gui,text="First Python Label by Grid()")
lb.grid(row=0,column=0)

gui.mainloop()
```

![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/8bc6e31d-fa21-4d9c-84f7-1e9d1a61c639)



```python
from tkinter import *

gui = Tk()

gui.title('GUI ')
gui.geometry("452x400")

lb1 = Label(gui,text="First Python Label")
lb1.grid(row=0,column=0)

lb2 = Label(gui,text="First Python Label")
lb2.grid(row=0,column=1)


lb3 = Label(gui,text="First Python Label")
lb3.grid(row=0,column=2)

lb7 = Label(gui,text="First Python Label")
lb7.grid(row=3,column=0, sticky = N, padx = 100, pady=0)

lb4 = Label(gui,text="First Python Label")
lb4.grid(row=1,column=0)

lb5 = Label(gui,text="First Python Label")
lb5.grid(row=1,column=1)

lb6 = Label(gui,text="First Python Label")
lb6.grid(row=1,column=2)

gui.mainloop()
```

![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/c140203b-b2c9-4b2d-9511-066cf598c0db)



```python
from tkinter import *

gui = Tk()

gui.title('GUI ')
gui.geometry("400x400")

lb = Label(gui,text="First Python Label 1")
lb.grid(row=0,column=0, sticky = N, padx = 0, pady=100)

lb = Label(gui,text="First Python Label 2")
lb.grid(row=1,column=0, sticky = N, padx = 0, pady=0)

gui.mainloop()
```

![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/4231c5c5-2f93-4317-b40c-aed231266d33)


# Label Propertise 

<pre>
activebackground, activeforeground, anchor,
    background, bitmap, borderwidth, cursor,
    disabledforeground, font, foreground,
    highlightbackground, highlightcolor,
    highlightthickness, image, justify,
    padx, pady, relief, takefocus, text,
    textvariable, underline, wraplength
    </pre>


```python
from tkinter import *

gui = Tk()

gui.title('GUI ')
gui.geometry("400x400")

lab1 = Label(gui,text="First GUI Label Text")
lab1.pack()

gui.mainloop()
```

![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/79e8483d-8b74-4288-8ad0-1cadf3653f59)



```python
from tkinter import *

gui = Tk()

gui.title('GUI ')
gui.geometry("400x400")

lab1 = Label(gui,text="First GUI Label Text", background="black",foreground='white')
lab1.pack()

gui.mainloop()
```

![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/53ecea38-b7ae-4192-b0ce-85c8bc63e606)



```python
from tkinter import *

gui = Tk()

gui.title('GUI ')
gui.geometry("400x400")

lab1 = Label(gui,text="First GUI Label Text", background="sky blue",foreground='white',
             font=("times",15,"underline"))
lab1.pack()

gui.mainloop()
```

![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/57352d8e-9896-4e2d-b426-d7c6349750f3)



```python
from tkinter import *

gui = Tk()

gui.title('GUI ')
gui.geometry("400x400")

lab1 = Label(gui,text="First GUI Label Text", background="sky blue",foreground='white',
             font="Times 20 underline")
lab1.pack()

gui.mainloop()
```

![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/6d60e2e1-7e50-4d27-8afe-2b70596d08eb)



```python
from tkinter import *

gui = Tk()

gui.title('GUI ')
gui.geometry("400x400")

lab1 = Label(gui,text="First GUI Label Text", background="sky blue",foreground='white',
             font="Times 20 underline",borderwidth=25)
lab1.pack()

gui.mainloop()
```

![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/c128bc40-9731-48f4-8812-58426099ad58)



```python
from tkinter import *

gui = Tk()

gui.title('GUI ')
gui.geometry("400x400")

lab1 = Label(gui,text="First GUI Label Text", background="sky blue",foreground='white',
             font="Times 20 underline",borderwidth=25,relief=SUNKEN)
lab1.pack()

gui.mainloop()
```

![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/5c3d63c9-288a-4def-a96f-d4aaeb226d5b)



```python
from tkinter import *

gui = Tk()

gui.title('GUI ')
gui.geometry("400x400")

lab1 = Label(gui,text="First GUI Label Text", background="sky blue",foreground='white',
             font="Times 20 underline",borderwidth=25,relief=GROOVE)
lab1.pack()

gui.mainloop()
```

![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/00881950-678f-473e-9eb5-07ec10c43c15)



```python
from tkinter import *

gui = Tk()

gui.title('GUI ')
gui.geometry("400x400")

lab1 = Label(gui,text="First GUI Label Text", background="sky blue",foreground='white',
             font="Times 20 underline",borderwidth=25,relief=FLAT)
lab1.pack()

gui.mainloop()
```

![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/bc03186a-aa91-41f5-8f63-35c3619ac5b2)



```python
from tkinter import *

gui = Tk()

gui.title("GUI")
gui.geometry("400x400")

for i in range(5):
    lb1 = Label(gui,text=(f"Python{i}"))
    lb1.pack()

gui.mainloop()
```

![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/92cd97e5-2636-42e3-a54c-9f93468e288b)



```python
from tkinter import *

gui = Tk()

gui.title("GUI")
gui.geometry("400x400")

for i in range(5):
    lb1 = Label(gui,text=(f"Python{i}"))
    lb1.grid(row=0,column=i)

gui.mainloop()
```

![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/3521ed95-d11e-487c-954c-b993149f7bfd)



```python
# arrow', 'circle', 'clock', 'cross', 'dotbox',
# 'exchange', 'fleur', 'heart', 'heart', 
# 'man', 'mouse', 'pirate', 'plus', 'shuttle', 
# 'sizing', 'spider', 'spraycan', 'star', 
# 'target', 'tcross', 'trek', 'watch'
```


```python
from tkinter import *

gui = Tk()

gui.title('GUI ')
gui.geometry("400x400")

lab1 = Label(gui,text="First GUI Label Text", background="sky blue",foreground='white',
             font="Times 20 underline",borderwidth=25,relief=FLAT, cursor="dotbox")
lab1.pack()

gui.mainloop()
```

![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/c6f52af5-b53f-419d-830a-aef809f71de8)



```python
from tkinter import *

gui = Tk()

gui.title('GUI ')
gui.geometry("400x400")

lab1 = Label(gui,text="First GUI Label Text", background="sky blue",foreground='white',
             font="Times 20 underline",borderwidth=25,relief=FLAT, cursor="clock")
lab1.pack()

gui.mainloop()
```
![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/45eadb62-bcf7-4a84-a5cb-2f7c4f0ac78d)


# <li style='font-size:20pt'>Button In Tkinter</li>


<p style="text-align: justify;">The button widget is used to add various types of buttons to the python application. Python allows us to configure the look of the button according to our requirements. Various options can be set or reset depending upon the requirements. We can also associate a method or function with a button which is called when the button is pressed. The syntax to use the button widget is given below.</p>
<h2 style="text-align: justify;">Syntax:</h2>
<p style="text-align: justify;">btn = Button(parent, options)<br /><br /></p>


```python
from tkinter import *

gui = Tk()

gui.title('GUI ')

# we create button successfully but button will not show because we haven't call button
btn = Button(gui,text="First Python Button") 

gui.mainloop()
```


```python
from tkinter import *

root = Tk()

btn1 = Button(root , text = "ROOT Button")
btn1.pack() # .pack() helps us to view button in GUI window

root.mainloop()

```

Output;
![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/caf9228b-fa91-41f0-bd83-23acb343e605)



<h2><strong>Geometry:</strong></h2>
<p>The Tkinter geometry specifies the method by using which, the widgets are represented on display. The python Tkinter provides the following geometry methods.</p>
<ol>
<li>The pack() method</li>
<li>The grid() method</li>
<li>The place() method</li>
</ol>
<p><br />Let's discuss each one of them in detail.</p>
<h2><strong>1.) Pack():</strong></h2>
<p>The pack() widget is used to organize widgets in the block. The positions widgets added to the python application using the pack() method can be controlled by using the various options specified in the method call.</p>
<p>However, the controls are fewer, and widgets are generally added in a less organized manner. T<br />The syntax to use the pack() is given below.</p>
<p>Syntax:<br />btn.pack(options)</p>
<p>A list of possible options that can be passed in pack() is given below.</p>
<p><br /><strong>expand:</strong> If the expand is set to true, the widget expands to fill any space.<br /><strong>Fill:</strong> By default, the fill is set to NONE. However, we can set it to X or Y to determine whether the widget contains any extra space.<br /><strong>size:</strong> it represents the side of the parent to which the widget is to be placed on the window.</p>


```python
from tkinter import *

gui = Tk()

gui.title('GUI ')
gui.geometry("400x400")

btn = Button(gui,text="First Python Button")
btn.pack()

gui.mainloop()
```

Output:
![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/8b7b358b-57a1-405f-8fb9-80faaec4292c)



```python
from tkinter import *

gui = Tk()

gui.title('GUI ')
gui.geometry("400x400")

btn = Button(gui,text="First Python Button")
# btn.pack(side=LEFT)  # It will show left side
# btn.pack(side=RIGHT) # It will show right side
# btn.pack(side=TOP)   # It will show top side
btn.pack(side=BOTTOM)  # It will show bottom side

gui.mainloop()
```

Output:
![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/4fc49989-f823-4698-b246-ac4d4c97f9dc)



```python
from tkinter import *

gui = Tk()

gui.title('GUI ')
gui.geometry("400x400")

btn1 = Button(gui,text="LEFT Button")
btn1.pack(side=LEFT)  # It will show left side

btn2 = Button(gui,text="RIGHT Button")
btn2.pack(side=RIGHT) # It will show right side

btn3 = Button(gui,text="TOP Button")
btn3.pack(side=TOP)   # It will show top side

btn4 = Button(gui,text="BOTTOM Button")
btn4.pack(side=BOTTOM)  # It will show bottom side

gui.mainloop()
```

Output:
![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/999fb35a-a2a2-4c1d-aebe-ebc8769ab446)



```python
from tkinter import *

gui = Tk()

gui.title('GUI ')
gui.geometry("400x400")

button1 = Button(text="button1")
button1.pack(side=BOTTOM, pady=50) # pady will be downward

gui.mainloop()
```

output:

![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/332328c9-a273-4895-8161-bc9a26fa4eb9)



```python
from tkinter import *

gui = Tk()

gui.title('GUI ')
gui.geometry("400x400")

button1 = Button(text="button1")
button1.pack(side=LEFT, padx=100) # pady will be forward

gui.mainloop()

```

output:
![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/4db5f57d-0006-4406-8f7b-c3322db72332)



```python
from tkinter import *

gui = Tk()

gui.title('GUI ')
gui.geometry("400x400")

button1 = Button(gui,text="button1")
button1.pack(padx=100, pady=160) # pady will be downward, forward

gui.mainloop()
```

output:
![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/73414b57-445f-49b8-b11a-4028578674d9)



```python
from tkinter import *

gui = Tk()

gui.title('GUI ')
gui.geometry("400x400")

button1 = Button(text="button1")
button1.pack(ipadx=80) # ipadx will be increase button width forwardly

gui.mainloop()
```
+![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/a39baceb-bb71-48a6-a6de-4749c2027af7)



```python
from tkinter import *

gui = Tk()

gui.title('GUI ')
gui.geometry("400x400")

button1 = Button(text="button1")
button1.pack(ipady=80) # pady will be downwardly

gui.mainloop()
```

![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/ec5ce4ec-49a0-44c9-bf93-c384008d5d30)



```python
from tkinter import *

gui = Tk()

gui.title('GUI ')
gui.geometry("400x400")

button1 = Button(gui,text="button1")
button1.pack(ipadx=80,ipady =80) # pady will be downward

gui.mainloop()
```

![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/32c8646a-5bb5-4381-abdb-a200f6fc397f)


```python
from tkinter import *

gui = Tk()

gui.title('GUI ')
gui.geometry("400x400")

b1 = Button(gui, text = "Click me !")
b1.pack(fill = BOTH, expand = True)

# Button 2
b2 = Button(gui, text = "Click me too")
b2.pack(fill = BOTH, expand = True)

gui.mainloop()
```
![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/8b29a963-6b7a-437a-a84f-a08ed1cbd9f2)



```python
from tkinter import *

gui = Tk()

gui.title('GUI ')
gui.geometry("400x400")

b1 = Button(gui, text = "Click me !")
b1.pack(side = TOP, expand = True, fill = BOTH)

# Button 2
b2 = Button(gui, text = "Click me too")
b2.pack(side = TOP, expand = True, fill = BOTH)

gui.mainloop()
```
![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/ec8d6465-fe7e-4d1e-9e95-644e7fbaed9e)



```python
from tkinter import *

gui = Tk()

gui.title('GUI ')
gui.geometry("400x400")

b1 = Button(gui, text = "Click me !")
b1.pack(side = LEFT, expand = True, fill = BOTH)

# Button 2
b2 = Button(gui, text = "Click me too")
b2.pack(side = LEFT, expand = True, fill = BOTH)

# Button 3
b3 = Button(gui, text = "Click me too")
b3.pack(side = LEFT, expand = True, fill = BOTH)

gui.mainloop()
```
![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/6001fe82-e28b-4fa2-b395-55a222233517)



```python
from tkinter import *

gui = Tk()

gui.title('GUI ')
gui.geometry("400x400")

b1 = Button(gui, text = "Click me !")
b1.pack()

gui.mainloop()
```
![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/53d6b37d-39f7-47e7-9494-8f432614624f)


<h2>2.) place():</h2>
<p>The place() geometry manager organizes the widgets to the specific x and y coordinates.</p>
<h2>Syntax:</h2>
<p>gui.place(options)</p>
<p>A list of possible options is given below.</p>
<p><strong>Anchor:</strong> It represents the exact position of the widget within the container. The default value (direction) is NW (the upper left corner)<br /><strong>bordermode:</strong> The default value of the border type is INSIDE that refers to ignore the parent's inside the border. The other option is OUTSIDE.<br /><strong>height, width:</strong> It refers to the height and width in pixels. <br /><strong>relheight, relwidth:</strong> It is represented as the float between 0.0 and 1.0 indicating the fraction of the parent's height and width. <br /><strong>relx, rely:</strong> It is represented as the float between 0.0 and 1.0 that is the offset in the horizontal and vertical direction. <br /><strong>x, y:</strong> It refers to the horizontal and vertical offset in the pixels.</p>


```python
from tkinter import *

gui = Tk()

gui.title('GUI ')
gui.geometry("400x400")

btn = Button(gui,text="First Python Button")
btn.place(x=0 , y=0) # x,y take coordinnate for position of button

gui.mainloop()
```
![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/c34509ad-16f1-4588-bd40-96d7c127b675)



```python
from tkinter import *

gui = Tk()

gui.title('GUI ')
gui.geometry("400x400")

btn = Button(gui,text="First Python Button")
# if x value 20 it mean it will move forward
btn.place(x=20 , y=0) # x,y take coordinnate for position of button
#btn.place(x=380 , y=380)

gui.mainloop()
```
![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/8c282a46-bdcc-4c6e-901a-d59aadfc75e2)



```python
from tkinter import *

gui = Tk()

gui.title('GUI ')
gui.geometry("400x400")

btn = Button(gui,text="First Python Button")
# if y value 20 it mean it will move downward
btn.place(x=0 , y=20) # x,y take coordinnate for position of button

gui.mainloop()
```
![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/d9823fbd-f563-48a4-94b0-0bd90b904f38)



```python
from tkinter import *

gui = Tk()

gui.title('GUI ')
gui.geometry("400x400")

btn0 = Button(gui,text="First Python Button")
btn0.place(x =2, y = 2)
# btn0.place(anchor = CENTER)


gui.mainloop()
```
![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/c931c8a5-bd25-4cf8-a32b-9b54eddaeffb)


<h2 style="text-align: justify;">Grid():</h2>
<p style="text-align: justify;">The Grid geometry manager puts the widgets in a 2-dimensional table. The master widget is split into a number of rows and columns, and each "cell" in the resulting table can hold a widget. The grid manager is the most flexible of the geometry managers in Tkinter. If you don't want to learn how and when to use all three managers, you should at least make sure to learn this one. Consider the following <br />example:</p>

![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/399b3eed-d8c6-405c-b877-1376769e33cf)



```python
from tkinter import *

gui = Tk()

gui.title('GUI ')
gui.geometry("400x400")

btn = Button(gui,text="First Python Button ABCD EFGH")
btn.grid(row=0,column=0)

gui.mainloop()
```
![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/c749888b-371e-4939-a3bd-31d00ade786d)



```python
from tkinter import *

gui = Tk()

gui.title('GUI ')
gui.geometry("452x400")

btn1 = Button(gui,text="First Python Button")
btn1.grid(row=0,column=0)

btn2 = Button(gui,text="First Python Button")
btn2.grid(row=0,column=1)


btn3 = Button(gui,text="First Python Button")
btn3.grid(row=0,column=2)

btn7 = Button(gui,text="First Python Button")
btn7.grid(row=3,column=0, sticky = N, padx = 100, pady=0)

btn4 = Button(gui,text="First Python Button")
btn4.grid(row=1,column=0)

btn5 = Button(gui,text="First Python Button")
btn5.grid(row=1,column=1)

btn6 = Button(gui,text="First Python Button")
btn6.grid(row=1,column=2)

gui.mainloop()
```
![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/c173ba83-9f99-4dd6-b08e-c94d775c3687)



```python
from tkinter import *

gui = Tk()

gui.title('GUI ')
gui.geometry("400x400")

btn = Button(gui,text="First Python Button")
btn.grid(row=0,column=0, sticky = N, padx = 0, pady=100)

btn2 = Button(gui,text="First Python Button")
btn2.grid(row=1,column=0, sticky = N, padx = 0, pady=0)

gui.mainloop()
```
![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/fe9088f7-715e-43eb-9a3a-c33c25062e8a)


# Button Propertise


```python
from tkinter import *

gui = Tk()

gui.title('GUI ')
gui.geometry("600x600")

btn = Button(gui,text="First Python Button",
            activebackground="green",activeforeground="gold",
            background="blue",foreground="white",borderwidth=50,
             font=("times",30,"italic bold underline")
            )
btn.pack()

gui.mainloop()
```
![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/152e3635-4cb4-4f77-8c4d-57019c52b902)



```python
from tkinter import *

gui = Tk()

gui.title('GUI ')
gui.geometry("400x400")

btn = Button(gui,text="First Python Button",
            activebackground="green",activeforeground="gold"
            )
btn.pack()

gui.mainloop()
```
![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/c487aa98-1cf0-49d6-b7e3-8c34904ede1c)



```python
from tkinter import *

gui = Tk()

gui.title('GUI ')
gui.geometry("400x400")

btn = Button(gui,text="First Python Button",
            activebackground="green",activeforeground="gold",
            background="blue",borderwidth=50, font=("arial",12,'underline'),
            foreground="light blue", highlightbackground='black',highlightthickness='10')
btn.pack()

gui.mainloop()
```
![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/e4a0a559-de8b-45b0-8704-ac848bdf405d)



```python
from tkinter import *

gui = Tk()

gui.title('GUI ')
gui.geometry("400x400")

btn = Button(gui,text="First Python Button",
            activebackground="green",activeforeground="gold",
            background="blue",borderwidth=50, font=("arial",12,'underline'),
            foreground="light blue",relief=SUNKEN)
btn.pack()

gui.mainloop()
```
![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/6c470c6a-5d3f-4473-9846-bc1c73ce17ad)



```python
from tkinter import *

gui = Tk()

gui.title('GUI ')
gui.geometry("400x400")

btn = Button(gui,text="First Python Button",
            activebackground="green",activeforeground="gold",
            background="blue",borderwidth=50, font=("arial",12,'underline'),
            foreground="light blue",relief=GROOVE)
btn.pack()

gui.mainloop()
```
![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/8811dc81-16a6-46fc-a3b5-e952178cff13)
![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/da1628b5-b1bc-48c7-8141-db9a84e5f57f)



```python
from tkinter import *

gui = Tk()

gui.title('GUI ')
gui.geometry("400x400")

btn = Button(gui,text="First Python Button",
            activebackground="green",activeforeground="gold",
            background="blue",borderwidth=50, font=("arial",12,'underline'),
            foreground="light blue",relief=FLAT)
btn.pack()

gui.mainloop()
```
![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/f174ac61-4fcd-4b73-b1af-e18c1876f538)



```python
from tkinter import *

gui = Tk()

gui.title('GUI ')
gui.geometry("400x400")

btn1 = Button(gui,text="Python Button SUNKEN",borderwidth=50,
            background="blue", font=("arial",12,'underline'),
            foreground="light blue",relief=SUNKEN)
btn1.pack(side =TOP)

btn2 = Button(gui,text="Python Button GROOVE",borderwidth=50,
            background="red", font=("arial",12,'underline'),
            foreground="light blue",relief=GROOVE)
btn2.pack(side = RIGHT)

btn3 = Button(gui,text="Python Button FLAT",borderwidth=50,
            background="green", font=("arial",12,'underline'),
            foreground="light blue",relief=FLAT)
btn3.pack(side=LEFT)

gui.mainloop()
```
![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/ea8432ec-a15f-458e-8777-945ac80b29ff)



```python
from tkinter import *

gui = Tk()

gui.title('GUI ')
gui.geometry("200x200")

btn=Button(gui,text="Close",command=gui.destroy)
btn.pack()


gui.mainloop()
```
![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/07d90752-9abc-4e8e-8978-c5c21f39913f)



```python
from tkinter import *

gui = Tk()

gui.title('GUI ')
gui.geometry("400x400")

def greet1():
    print("Hello By First Button")

def greet2():
    print("Hello By Second Button")

btn = Button(gui,text="First Python Button",command=greet1)
btn.pack()

btn2 = Button(gui,text="Second Python Button",command=greet2)
btn2.pack()

gui.mainloop()
```

![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/479cfcf7-0c7f-44c9-af0f-9961d1f6ee7c)



```python
from tkinter import *

gui = Tk()

gui.title('GUI ')
gui.geometry("400x400")

def mentor():
    print("Dr. Allama Iqbal Is Our Mentor")

btn = Button(gui,text="First Python Button",command=mentor)
btn.pack()

gui.mainloop()
```
![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/6afe7e3c-acae-4fda-83f2-ef1a4bcf68eb)


# <li style='font-size:20pt'>Entry in Tkinter</li>

<h2><strong>Entry Box:</strong></h2>
<p>The Entry Widget is a Tkinter Widget used to Enter or display a single line of text.</p>
<h3><strong>Syntax:</strong> </h3>
<p>entry = Entry(parent, options)</p>
<p><strong>Parameters:</strong> <br />1) Parent: The Parent window or frame in which the widget to display. <br />2) Options: The various options provided by the entry widget are:</p>
<p><strong>bg:</strong> The normal background color displayed behind the label and indicator. <br /><strong>bd:</strong> The size of the border around the indicator. Default is 2 pixels. <br /><strong>font:</strong> The font used for the text. <br /><strong>fg:</strong> The color used to render the text. <br /><strong>justify:</strong> If the text contains multiple lines, this option controls how the text is justified: CENTER, LEFT, or RIGHT. <br /><strong>relief:</strong> With the default value, relief-FLAT. You may set this option to any of the other styles like SUNKEN, RIGID, RAISED, GROOVE <br /><strong>show:</strong> Normally, the characters that the user types appear in the entry. To make a password. the entry that echoes each character as an asterisk, set show="*".<br /><strong>textvariable:</strong> In order to be able to retrieve the current text from your entry widget, you must set this option to an instance of the StringVar class.</p>
<p><strong>Methods:</strong> The various methods provided by the entry widget are :</p>
<p><strong>get():</strong> Returns the entry's current text as a string. <br /><strong>delete():</strong> Deletes characters from the widget <br /><strong>insert (index, 'name'):</strong> Insert string 'name' before the character at the given index.</p>


```python
from tkinter import *

gui=Tk()

gui.geometry("400x400")
gui.title("GUI")

ent = Entry(gui)
ent.pack()

gui.mainloop()
```

![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/f0fdaa9c-11cb-4f4a-9015-6ef44d778f7d)



```python
from tkinter import *

gui=Tk()

gui.geometry("400x400")
gui.title("GUI")

ent = Entry(gui,show="@")
ent.pack()

gui.mainloop()
```
![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/0d5c36d0-e77b-4bb0-86a6-3c21becece69)



```python
from tkinter import *

gui=Tk()

gui.geometry("400x400")
gui.title("GUI")

ent = Entry(gui)
ent.pack()

btn = Button(gui,text="Click Me!")
btn.pack()

gui.mainloop()
```
![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/73245a91-bb0c-427a-9361-c5c2d8c253d1)



```python
from tkinter import *

gui=Tk()

gui.geometry("400x400")
gui.title("GUI")

name_str_var = StringVar()

def click():
    name = name_str_var.get()
    print(f"You click ==> {name}")

ent = Entry(gui, textvariable=name_str_var)
ent.pack()

btn = Button(gui,text="Click Me!", command=click)
btn.pack()

gui.mainloop()
```
![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/0715560c-0199-4042-9bc8-77ee89f7ed3d)



```python
from tkinter import *

gui=Tk()

gui.geometry("400x400")
gui.title("GUI")

name_str_var = StringVar()

def click():
    name = name_str_var.get()
    print(f"You click ==> {name}")
    name_str_var.set("")

ent = Entry(gui, textvariable=name_str_var)
ent.pack()

btn = Button(gui,text="Click Me!", command=click)
btn.pack()

gui.mainloop()
```
![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/5406e8c1-a4fc-4b47-8c1b-171917a528f1)



```python
from tkinter import *

root = Tk()

e = Entry(root, width=50)
e.pack() 

def myClick():
    hello = "Hello " + e.get() + "!"
    myLabel = Label(root, text=hello)
    myLabel.pack()

# Creating a button
myButton = Button(root, text="Enter You Name", command=myClick)
myButton.pack()

root.mainloop()

```
![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/35b025fd-250d-43ae-bebc-51522f98dc30)



```python
from tkinter import *

gui = Tk()

# setting the windows size
gui.geometry("600x400")

# declaring string variable
# for storing name and password
name_var = StringVar()
passw_var = StringVar()


# defining a function that will
# get the name and password and
# print them on the screen
def submit():

    name=name_var.get()
    password=passw_var.get()
    
    print("The name is : " + name)
    print("The password is : " + password)
    
    name_var.set("")
    passw_var.set("")
    
    
# creating a label for
# name using widget Label
name_label = Label(gui, text = 'Username', font=('calibre',10, 'bold'))

# creating a entry for input
# name using widget Entry
name_entry = Entry(gui,textvariable = name_var, font=('calibre',10,'normal'))

# creating a label for password
passw_label = Label(gui, text = 'Password', font = ('calibre',10,'bold'))

# creating a entry for password
passw_entry = Entry(gui, textvariable = passw_var, font = ('calibre',10,'normal'), show = '*')

# creating a button using the widget
# Button that will call the submit function
sub_btn = Button(gui,text = 'Submit', command = submit)

# placing the label and entry in
# the required position using grid
# method
name_label.grid(row=0,column=0)
name_entry.grid(row=0,column=1)
passw_label.grid(row=1,column=0)
passw_entry.grid(row=1,column=1)
sub_btn.grid(row=2,column=1)

# performing an infinite loop
# for the window to display
gui.mainloop()

```
![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/2bb4f9ae-5fb3-4de4-9ece-68d05279e2f2)


# <li style='font-size:20pt'>CheckButton In Tkinter</li>

<p style="text-align: justify;">The Check button is used to track the user's choices provided to the application. In other words, we can say that the Check button is used to implement the on/off selections. The Check button can contain the text or images. The Check button is mostly used to provide many choices to the user among which, the user needs to choose one. It generally implements many o many selections. The syntax to use the check button is given below.</p>
<h3>Syntax:</h3>
<p>ck_btn = Checkbutton(parent, **kwargs)</p>
<h3>Methods:</h3>
<p>The methods that can be called with the Checkbuttons are described in the following table.</p>
![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/af55299f-4b8c-42dd-a983-8eb683d0e63b)



```python
from tkinter import *

gui = Tk()

ck1_btn = Checkbutton(gui, text="Select Me")
ck1_btn.pack()

gui.mainloop()
```
![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/29ac7e36-08b5-48fa-b3ba-3a88e4f7616e)



```python
from tkinter import *

gui = Tk()

ck1_btn = Checkbutton(gui, text="Java")
ck1_btn.deselect()
ck1_btn.pack()

ck2_btn = Checkbutton(gui, text="C++")
ck2_btn.select()
ck2_btn.pack()

gui.mainloop()
```
![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/6c0226b7-13e8-4e8d-bb2e-2b718b2d580f)



```python
from tkinter import *

gui = Tk()

ck1_btn = Checkbutton(gui, text="Deselect")
ck1_btn.deselect()
ck1_btn.pack()

ck2_btn = Checkbutton(gui, text="Select")
ck2_btn.select()
ck2_btn.pack()

ck3_btn = Checkbutton(gui, text="Invoke")
ck3_btn.invoke()
ck3_btn.pack()

ck4_btn = Checkbutton(gui, text="Flash")
ck4_btn.flash()
ck4_btn.pack()

ck5_btn = Checkbutton(gui, text="Toggle")
ck5_btn.toggle()
ck5_btn.pack()

gui.mainloop()
```
![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/af0daa48-e608-4281-add5-6a552901908d)



```python
from tkinter import *

gui = Tk()
gui.geometry("300x200")

var = IntVar()

def click_me():
#     global Checkbutton1
    print(var.get())

lb = Label(gui, text ='First Check Button', font = "50")
lb.pack()

ck_btn = Checkbutton(gui, text = "Tutorial",
                        variable = var
                     )
ck_btn.pack()

btn = Button(gui,text="Check",command=click_me)
btn.pack()

gui.mainloop()
```
![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/b0072c42-3c71-4cb1-9a12-3f0d2c4e0c43)



```python
from tkinter import *

gui = Tk()
gui.geometry("300x200")

var = StringVar()

def click_me():
    print(var.get())

lb = Label(gui, text ='First Check Button', font = "50")
lb.pack()

ck_btn = Checkbutton(gui, text = "Tutorial",
                    variable = var,
                    offvalue="Uncheck",
                    onvalue="Checked")
ck_btn.deselect()
ck_btn.pack()

btn = Button(gui,text="Check",command=click_me)
btn.pack()

gui.mainloop()
```
![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/7986f4d0-2903-42e5-aa96-ffbf133cb44a)



```python
from tkinter import *
gui = Tk()
gui.geometry("300x200")

var1 = StringVar()
var2 = StringVar()
var3 = StringVar()
def click_me():
    print(var1.get())
    print(var2.get())
    print(var3.get())

lb = Label(gui, text ='First Check Button', font = "50")
lb.pack()
ck_btn = Checkbutton(gui, text = "Python",variable = var1,
                    offvalue="Uncheck",
                    onvalue="Python")
ck_btn.deselect()
ck_btn.pack()
ck_btn2 = Checkbutton(gui, text = "Java",variable = var2,
                    offvalue="Uncheck",
                    onvalue="Java")
ck_btn2.deselect()
ck_btn2.pack()
ck_btn3 = Checkbutton(gui, text = "C++",variable = var3,
                    offvalue="Uncheck",
                    onvalue="C++")
ck_btn3.deselect()
ck_btn3.pack()
btn = Button(gui,text="Check",command=click_me)
btn.pack()
gui.mainloop()
```
![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/10d3fe57-3208-44bb-b6ff-f75d1a72e9cf)


# <li style='font-size:20pt'>RadioButton In Tkinter</li>
<p style="text-align: justify;">The Radiobutton widget is used to implement one-of-many selection in the python application. It shows multiple choices to the user, and the user can select only one of them. We can associate different methods with each of the radio buttons. We can display the multiple-line text or images on the radio buttons. The radio button is associated with a single variable to keep track of the user's selection. Each button displays a single value for that particular variable. The syntax to use the Radiobutton is given below.</p>
<h3 style="text-align: justify;">Syntax:</h3>
<p>rdbtn = Radiobutton(parent, options)</p>


```python
from tkinter import *

gui=Tk()

rbtn = Radiobutton(gui,text="Python")
rbtn.pack()

gui.mainloop()
```
![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/f3307eff-941a-4468-8694-d3df8da67866)



```python
from tkinter import *

gui=Tk()

r1 = IntVar()

rbtn1 = Radiobutton(gui,text="Python",variable=r1,value=1)
rbtn1.deselect()
rbtn1.pack()

rbtn2 = Radiobutton(gui,text="Python",variable=r1 , value=2)
rbtn2.deselect()
rbtn2.pack()

gui.mainloop()
```
![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/2e00aad0-4460-450a-9659-816d768a3bdd)



```python

from tkinter import *  
  
def selection():  
    selection = "You selected the option " + str(radio.get())  
    label.config(text = selection)  

top = Tk()  
top.geometry("300x150")  
radio = IntVar()  

lbl = Label(text = "Favourite programming language:")  
lbl.pack()  
R1 = Radiobutton(top, text="C", variable=radio, value=1,  
                  command=selection)  
R1.pack( anchor = W )  
  
R2 = Radiobutton(top, text="C++", variable=radio, value=2,  
                  command=selection)  
R2.pack( anchor = W )  
  
R3 = Radiobutton(top, text="Java", variable=radio, value=3,  
                  command=selection)  
R3.pack( anchor = W)  
  
label = Label(top)  
label.pack()  
top.mainloop()  
```

![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/46c9d32c-bf57-47ac-98c5-d042a7d2b3de)



```python
from tkinter import *
master = Tk()
master.geometry("175x175")

v = StringVar(master, "1")
values = {"RadioButton 1" : "1",
        "RadioButton 2" : "2",
        "RadioButton 3" : "3",
        "RadioButton 4" : "4",
        "RadioButton 5" : "5"}
def click():
    print(v.get())
for (text, value) in values.items():
    Radiobutton(master, text = text, variable = v,
                value = value, indicator = 0,
                background = "light blue",command=click).pack(fill = X,
                                                              ipady = 5)


mainloop()

```
![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/2ffa3977-7d60-41c5-91ef-1d615ed11f99)


# <li style='font-size:20pt'>Frame In Tkinter</li>
<p style="text-align: justify;">Python Tkinter Frame widget is used to organize the group of widgets. It acts like a container that can be used to hold the other widgets. The rectangular areas of the screen are used to organize the widgets for the python application.</p>
<p style="text-align: justify;">The syntax to use the Frame widget is given below.</p>
<h3 style="text-align: justify;">Syntax:</h3>
<p style="text-align: justify;">frm = Frame(parent, options)</p>
<p style="text-align: justify;">&nbsp;</p>
<h3>Parameter:</h3>
<p><strong>master:</strong> This parameter is used to represent the parent window. <br /><strong>options:</strong> There are many options that are available and they can be used as key-value pairs separated by commas.</p>
<h3>Options:</h3>
<p>The following are commonly used Options that can be used with this widget:-</p>
<p><strong>bg:</strong> This option is used to represent the normal background color displayed behind the label and indicator. <br /><strong>bd:</strong> This option is used to represent the size of the border around the indicator and the default value is 2 pixels.<br /><strong>cursor:</strong> By using this option, the mouse cursor will change to that pattern when it is over the frame.<br /><strong>height:</strong> The vertical dimension of the new frame.<br /><strong>highlight color:</strong> This option is used to represent the color of the focus highlight when the frame has the focus.<br /><strong>highlight thickness:</strong> This option is used to represent the color of the focus highlight when the frame does not have focus.<br /><strong>highlight background:</strong> This option is used to represent the thickness of the focus highlight.<br /><strong>relief:</strong> The type of the border of the frame. Its default value is set to FLAT.<br /><strong>width:</strong> This option is used to represent the width of the frame.</p>


```python
from tkinter import *

gui = Tk()
frame = Frame(gui)
frame.pack()

bottomframe = Frame(gui)
bottomframe.pack( side = BOTTOM )

redbutton = Button(frame, text="Red", fg="red")
redbutton.pack( side = LEFT)


gui.mainloop()
```
![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/1811c62b-cc05-4713-bc10-c496eb90d821)



```python
from tkinter import *

root = Tk()

textLabel = Label(root,
                  text="Label",
                  justify=LEFT,
                  padx=10)
textLabel.pack(side=LEFT)

photo = PhotoImage(file="cat.png")
imgLabel = Label(root, image=photo)
imgLabel.pack(side=RIGHT)

mainloop()
```
![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/ddd8f659-9a28-4f8d-bcdd-58f5101d036e)



```python
from tkinter import *  
root = Tk()  

for fm in ['blue','red','yellow','green','white','black']:  
    Frame(height = 20,width = 640,bg = fm).pack()  
root.mainloop() 
```
![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/6dc7d79e-83ac-43e8-9afc-84b90243b003)



```python
from tkinter import *

gui = Tk()
gui.geometry("400x400")
gui.configure(bg="Gold")

lb = Label(gui,
           text="Label Without Frame",
           font='times 20 bold')
lb.pack()

frm = Frame(gui,bg='blue')
frm.place(x=100,y=100,width=250,height=250)

lb2 = Label(frm,text="Label Inside Frame")
lb2.pack()

frm2= Frame(frm,bg='green')
frm2.place(x=50,y=50,width=150,height=150)

lb3 = Label(frm2,text="Label Inside/Inside  Frame")
lb3.pack()

gui.mainloop()
```
![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/b5360988-289d-49ea-abee-a49770581304)


# <li style='font-size:20pt'>ListBox In Tkinter</li>

<p style="text-align: justify;">A Listbox shows a list of options, you can then click on any of those options. By default, it won't do anything, but you can link that to a callback function or link a button click. To add new items, use the insert() method or a Listbox.</p>
<h2 style="text-align: justify;">Parameters</h2>
<ul class="list" style="text-align: justify;">
<li>
<p><strong>master</strong>&nbsp;&minus; This represents the parent window.</p>
</li>
<li>
<p><strong>options</strong>&nbsp;&minus; Here is the list of most commonly used options for this widget. These options can be used as key-value pairs separated by commas.</p>
</li>
</ul>
<p style="text-align: justify;"><strong>bg:</strong> The normal background color displayed behind the label and indicator.<br /><br /><strong>bd:</strong> The size of the border around the indicator. Default is 2 pixels.</p>
<p style="text-align: justify;"><strong>cursor:</strong> The cursor that appears when the mouse is over the listbox.</p>
<p style="text-align: justify;"><strong>font:</strong> The font used for the text in the listbox.<br /><br /><strong>fg:</strong> The color used for the text in the listbox.</p>
<p style="text-align: justify;"><strong>height:</strong> Number of lines (not pixels!) shown in the Listbox. Default is 10.</p>
<p style="text-align: justify;"><strong>highlightcolor:</strong> The color shown in the focus highlight when the widget has the focus.</p>
<p style="text-align: justify;"><strong>highlightthickness:</strong> Thickness of the focus highlight.</p>
<p style="text-align: justify;"><strong>relief:</strong> Selects three-dimensional border shading effects. The default is SUNKEN.</p>
<p style="text-align: justify;"><strong>selectbackground:</strong> The background color to use displays selected text.</p>
<p style="text-align: justify;"><strong>selectmode:</strong> Determines how many items can be selected, and how mouse drags affect the selection &minus;</p>
<p style="text-align: justify;"><strong>BROWSE &minus;</strong> If you click on an item and then drag it to a different line, the selection will follow the mouse.</p>
<p style="text-align: justify;"><strong>SINGLE &minus;</strong> You can only select one line, and you can't drag the mouse. wherever you click button 1, that line is selected.</p>
<p style="text-align: justify;"><strong>MULTIPLE &minus;</strong> You can select any number of lines at once. Clicking on any line toggles whether or not it is selected.</p>
<p style="text-align: justify;"><strong>EXTENDED &minus;</strong> You can select any adjacent group of lines at once by clicking on the first line and dragging to the last line.</p>
<p style="text-align: justify;"><strong>width:</strong> The width of the widget in characters. The default is 20.</p>
<p style="text-align: justify;"><strong>xscrollcommand:</strong> If you want to allow the user to scroll the Listbox horizontally, you can link your Listbox widget to a horizontal scrollbar.<br /><br /><strong>yscrollcommand:</strong> If you want to allow the user to scroll the Listbox vertically, you can link your Listbox widget to a vertical scrollbar.</p>


```python

from tkinter import *  
  
top = Tk()  
  
top.geometry("200x250")  
  
lbl = Label(top,text = "A list of favourite countries...")  
  
listbox = Listbox(top)  
  
listbox.insert(1,"India")  
  
listbox.insert(2, "USA")  
  
listbox.insert(3, "Japan")  
  
listbox.insert(4, "Austrelia")  
  
lbl.pack()  
listbox.pack()  
  
top.mainloop()  
```


```
![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/8596dece-b480-4e6f-aba1-785df6cc7dc9)

```


# <li style='font-size:20pt'>TextBox In Tkinter</li>

<p>Python Text Widget is used when a user wants to insert multiline text fields. This widget can be used for messaging, sending information or displaying information. We can also insert media files such as images and links also in the Text widget by using the MediaManager tool.</p>
<h2><strong>Optional parameters</strong>&nbsp;<br />&nbsp;</h2>
<ul>
<li><strong>root</strong>&nbsp;&ndash; root window.&nbsp;<br />&nbsp;</li>
<li><strong>bg</strong> &ndash; background color&nbsp;<br />&nbsp;</li>
<li><strong>fg</strong> &ndash; foreground color&nbsp;<br />&nbsp;</li>
<li><strong>bd</strong> &ndash; border of the widget.&nbsp;<br />&nbsp;</li>
<li><strong>height</strong> &ndash; the height of the widget.&nbsp;<br />&nbsp;</li>
<li><strong>width</strong>&nbsp;&ndash; width of the widget.&nbsp;<br />&nbsp;</li>
<li><strong>font</strong>&nbsp;&ndash; Font type of the text.&nbsp;<br />&nbsp;</li>
<li><strong>cursor</strong>&nbsp;&ndash; The type of the cursor to be used.&nbsp;<br />&nbsp;</li>
<li><strong>insetofftime</strong>&nbsp;&ndash; The time in milliseconds for which the cursor blink is off.&nbsp;<br />&nbsp;</li>
<li><strong>insertontime</strong>&nbsp;&ndash; the time in milliseconds for which the cursor blink is on.&nbsp;<br />&nbsp;</li>
<li><strong>padx</strong>&nbsp;&ndash; horizontal padding.&nbsp;&nbsp;</li>
<li><strong>pady</strong>&nbsp;&ndash; vertical padding.&nbsp;<br />&nbsp;</li>
<li><strong>state</strong> &ndash; defines if the widget will be responsive to mouse or keyboard movements.&nbsp;<br />&nbsp;</li>
<li><strong>highlightthickness</strong>&nbsp;&ndash; defines the thickness of the focus highlight.&nbsp;<br />&nbsp;</li>
<li><strong>insertionwidth</strong>&nbsp;&ndash; defines the width of insertion character.&nbsp;<br />&nbsp;</li>
<li><strong>relief</strong> &ndash; the type of the border which can be SUNKEN, RAISED, GROOVE and RIDGE.&nbsp;<br />&nbsp;</li>
<li><strong>yscrollcommand</strong>&nbsp;&ndash; to make the widget vertically scrollable.&nbsp;<br />&nbsp;</li>
<li><strong>xscrollcommand</strong>&nbsp;&ndash; to make the widget horizontally scrollable.&nbsp;</li>
</ul>
<p><strong>Some Common methods</strong><br />&nbsp;</p>
<ul>
<li><strong>index(index)&nbsp;</strong>&ndash; To get the specified index.&nbsp;<br />&nbsp;</li>
<li><strong>insert(index)&nbsp;</strong>&ndash; To insert a string at a specified index.&nbsp;<br />&nbsp;</li>
<li><strong>see(index)&nbsp;</strong>&ndash; Checks if a string is visible or not at a given index.&nbsp;<br />&nbsp;</li>
<li><strong>get(startindex, endindex)</strong>&nbsp;&ndash; to get characters within a given range.&nbsp;<br />&nbsp;</li>
<li><strong>delete(startindex, endindex)</strong>&nbsp;&ndash; deletes characters within specified range.</li>
</ul>
<p><strong>Tag handling methods</strong>&nbsp;<br />&nbsp;</p>
<ul>
<li><strong>tag_delete(tagname)</strong>&nbsp;&ndash; To delete a given tag.&nbsp;<br />&nbsp;</li>
<li><strong>tag_add(tagname, startindex, endindex)</strong>&nbsp;&ndash; to tag the string in the specified range&nbsp;<br />&nbsp;</li>
<li><strong>tag_remove(tagname, startindex, endindex)</strong>&nbsp;&ndash; to remove a tag from specified range&nbsp;<br />&nbsp;</li>
</ul>
<p><strong>Mark handling methods</strong>&nbsp;<br />&nbsp;</p>
<ul>
<li><strong>mark_names()&nbsp;</strong>&ndash; to get all the marks in the given range.&nbsp;<br />&nbsp;</li>
<li><strong>index(mark)&nbsp;</strong>&ndash; to get the index of a mark.&nbsp;<br />&nbsp;</li>
<li><strong>mark_gravity()</strong>&nbsp;&ndash; to get the gravity of a given mark.</li>
</ul>

<h2 style="text-align: justify;">Methods</h2>
<p style="text-align: justify;">Methods on listbox objects include &minus;</p>
<p style="text-align: justify;"><br /><strong>activate(index):</strong> Selects the line specifies by the given index.<br /><strong>curselection():</strong> Returns a tuple containing the line numbers of the selected element or elements, counting from 0. If nothing is selected, returns an empty tuple.<br /><strong>delete(first, last=None):</strong> Deletes the lines whose indices are in the range [first, last]. If the second argument is omitted, the single line with index first is deleted.<br /><strong>get(first, last=None):</strong> Returns a tuple containing the text of the lines with indices from first to last, inclusive. If the second argument is omitted, returns the text of the line closest to first.<br /><strong>index(i):</strong> If possible, positions the visible part of the listbox so that the line containing index i is at the top of the widget.<br /><strong>insert(index, *elements):</strong> Insert one or more new lines into the listbox before the line specified by index. Use END as the first argument if you want to add new lines to the end of the listbox.<br /><strong>nearest(y):</strong> Return the index of the visible line closest to the y-coordinate y relative to the listbox widget.<br /><strong>see(index):</strong> Adjust the position of the listbox so that the line referred to by index is visible.<br /><strong>size():</strong> Returns the number of lines in the listbox.<br /><strong>xview():</strong> To make the listbox horizontally scrollable, set the command option of the associated horizontal scrollbar to this method.<br /><strong>xview_moveto(fraction):</strong> Scroll the listbox so that the leftmost fraction of the width of its longest line is outside the left side of the listbox. Fraction is in the range [0,1].<br /><strong>xview_scroll(number, what):</strong> Scrolls the listbox horizontally. For the what argument, use either UNITS to scroll by characters, or PAGES to scroll by pages, that is, by the width of the listbox. The number argument tells how many to scroll.<br /><strong>yview():</strong> To make the listbox vertically scrollable, set the command option of the associated vertical scrollbar to this method.<br /><strong>yview_moveto(fraction):</strong> Scroll the listbox so that the top fraction of the width of its longest line is outside the left side of the listbox. Fraction is in the range [0,1].<br /><strong>yview_scroll(number, what):</strong> Scrolls the listbox vertically. For the what argument, use either UNITS to scroll by lines, or PAGES to scroll by pages, that is, by the height of the listbox. The number argument tells how many to scroll.</p>


```python
from tkinter import *

gui = Tk()

Lb1 = Listbox(gui)
Lb1.insert(1, "Python")
Lb1.insert(2, "Perl")
Lb1.insert(3, "C")
Lb1.insert(4, "PHP")
Lb1.insert(5, "JSP")
Lb1.insert(6, "Ruby")

Lb1.pack()
gui.mainloop()
```
![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/b12a5b28-8e1e-4611-8be3-c6962bcfc57e)



```python

from tkinter import *  
  
gui = Tk()  
  
gui.geometry("200x250")  
  
lbl = Label(gui,text = "A list of favourite countries...")  
  
listbox = Listbox(gui)  
  
listbox.insert(1,"Pakistan")  
listbox.insert(2, "USA")  
listbox.insert(3, "Russia")
listbox.insert(4, "China")  
listbox.insert(5, "Australia")
listbox.insert(6, "United Kingdom")
listbox.insert(7, "Palestine")
  
lbl.pack()  
listbox.pack()  
gui.mainloop()
```
![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/c5332dfe-92c8-47d6-855b-2ebf060c06c1)



```python

from tkinter import *  
  
gui = Tk()  
  
gui.geometry("200x250")  
  
lbl = Label(gui,text = "A list of favourite countries...")
lbl.pack()  

listbox = Listbox(gui)  
listbox.insert(1,"Pakistan")  
listbox.insert(2, "USA")  
listbox.insert(3, "Russia")
listbox.insert(4, "China")  
listbox.insert(5, "Australia")
listbox.insert(6, "United Kingdom")
listbox.insert(7, "Palestine")

listbox.pack()  


btn = Button(gui, text = "delete", command = lambda listbox=listbox: listbox.delete(ANCHOR))
btn.pack()

gui.mainloop()
```
![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/47a4a6ef-9b00-4f38-97ae-15f821900034)


# <li style='font-size:20pt'>ScrollBar In Tkinter</li>
<p>Tkinter is a built-in standard python library. There are various types of widgets available in Tkinter such as button, frame, label, menu, scrolledtext, canvas and many more. ScrolledText widget is a text widget with a scroll bar. The scrollbar widget is used to scroll down the content. We can also create horizontal scrollbars for the Entry widget.</p>
<p>Syntax:</p>
<pre>sb = Scrollbar(parent, options)<br /><br /></pre>
<p><strong>Parameters:</strong></p>
<ul>
<li><strong>master</strong>: This parameter is used to represent the parent window.</li>
<li><strong>options</strong>: There are many options that are available and they can be used as key-value pairs separated by commas.</li>
</ul>
<p><strong>Options:</strong><br />The following are commonly used Options that can be used with this widget:-</p>
<ul>
<li><strong>activebackground</strong>: This option is used to represent the background color of the widget when it has the focus.</li>
<li><strong>bg</strong>: This option is used to represent the background color of the widget.</li>
<li><strong>bd</strong>: This option is used to represent the border width of the widget.</li>
<li><strong>command</strong>: This option can be set to the procedure associated with the list which can be called each time when the scrollbar is moved.</li>
<li><strong>cursor</strong>: In this option, the mouse pointer is changed to the cursor type set to this option which can be an arrow, dot, etc.</li>
<li><strong>elementborderwidth</strong>: This option is used to represent the border width around the arrowheads and slider. The default value is -1.</li>
<li><strong>Highlightbackground</strong>: This option is used to focus on highlight color when the widget doesn&rsquo;t have the focus.</li>
<li><strong>highlighcolor</strong>: This option is used to focus on highlight color when the widget has the focus.</li>
<li><strong>highlightthickness</strong>: This option is used to represent the thickness of the focus highlight.</li>
<li><strong>jump</strong>: This option is used to control the behavior of the scroll jump. If it is set to 1, then the callback is called when the user releases the mouse button.</li>
<li><strong>orient</strong>: This option can be set to HORIZONTAL or VERTICAL depending upon the orientation of the scrollbar.</li>
<li><strong>repeatdelay</strong>: This option tells the duration up to which the button is to be pressed before the slider starts moving in that direction repeatedly. The default is 300 ms.</li>
<li><strong>repeatinterval</strong>: The default value of the repeat interval is 100.</li>
<li><strong>takefocus</strong>: You can tab the focus through a scrollbar widget</li>
<li><strong>troughcolor</strong>: This option is used to represent the color of the trough.</li>
<li><strong>width</strong>: This option is used to represent the width of the scrollbar.</li>
</ul>
<p><strong>Methods:</strong><br />Methods used in these widgets are as follows:</p>
<ul>
<li><strong>get()</strong>: This method is used to return the two numbers a and b which represent the current position of the scrollbar.</li>
<li><strong>set(first, last)</strong>: This method is used to connect the scrollbar to the other widget w. The yscrollcommand or xscrollcommand of the other widget to this method.</li>
</ul>


```python
from tkinter import *  
  
gui = Tk()
gui.geometry("100x200")
sb = Scrollbar(gui)  
sb.pack(side = RIGHT, fill = Y)

mylist = Listbox(gui, yscrollcommand = sb.set)

for line in range(50):  
    mylist.insert(END, "Number " + str(line))  

mylist.pack( side = LEFT, ipady=17)  
sb.config( command = mylist.yview )  
  
gui.mainloop() 
```
![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/8805589e-7e67-4638-8178-6987f64ad2a6)



```python
from tkinter import *

gui = Tk()
gui.geometry("200x200")

w = Label(gui, text ='Python Tkinter Scrollbar',font = "50")

w.pack()

scroll_bar = Scrollbar(gui)

scroll_bar.pack(side = RIGHT, fill = Y )

mylist = Listbox(gui, yscrollcommand = scroll_bar.set )

for line in range(1, 26):
    mylist.insert(END, "Scrollbar " + str(line))

mylist.pack(side = LEFT, fill = BOTH )

scroll_bar.config(command = mylist.yview )

gui.mainloop()

```
![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/de6b2af1-7f75-4f4a-bcf4-6a60416f852f)



```python
from tkinter import *

gui = tk.Tk()
gui.resizable(False, False)
gui.title("Scrollbar In Text Box")

text = Text(gui, height=8)
text.grid(row=0, column=0, sticky='ew')

scrollbar = Scrollbar(gui, orient='vertical', command=text.yview)
scrollbar.grid(row=0, column=1, sticky='ns')

text['yscrollcommand'] = scrollbar.set

gui.mainloop()
```
[  File Missing] ?????????????

# <li style='font-size:20pt'>LabelFrame In Tkinter</li>
<p>Labelframe is a simple container widget. Its primary purpose is to act as a spacer or container for complex window layouts. It acts like a container that can be used to group the number of interrelated widgets such as Radiobuttons. This widget is a variant of the Frame widget which has all the features of a frame plus the ability to display a label.</p>
<h2>Syntax</h2>
<p>Here is the simple syntax to create this widget:</p>
<pre class="result notranslate">lbfrm = LabelFrame(parent, options)
</pre>
<h2>Parameters</h2>
<ul class="list">
<li>
<p><strong>master</strong>&nbsp;&minus; This represents the parent window.</p>
</li>
<li>
<p><strong>options</strong> &minus; Here is the list of most commonly used options for this widget. These options can be used as key-value pairs separated by commas.</p>
</li>
</ul>
<p><strong>bg:</strong> The background color of the widget.<br /><strong>bd:</strong> It represents the size of the border shown around the indicator. The default is 2 pixels.<br /><strong>Class:</strong> The default value of the class is LabelFrame.<br /><strong>colormap:</strong> This option is used to specify which colormap is to be used for this widget. By colormap, we mean the 256 colors that are used to form the graphics. With this option, we can reuse the colormap of another window on this widget.<br /><strong>container:</strong> If this is set to true, the LabelFrame becomes the container widget. The default value is false.<br /><strong>cursor:</strong> It can be set to a cursor type, i.e. arrow, dot, etc. the mouse pointer is changed to the cursor type when it is over the widget.<br /><strong>fg:</strong> It represents the foreground color of the widget.<br /><strong>font:</strong> It represents the font type of the widget text.<br /><strong>height:</strong> It represents the height of the widget.<br /><strong>labelAnchor:</strong> It represents the exact position of the text within the widget. The default is NW(north-west)<br /><strong>labelwidget:</strong> It represents the widget to be used for the label. The frame uses the text for the label if no value is specified.<br /><strong>highlightbackground:</strong> The color of the focus highlight border when the widget doesn't have the focus.<br /><strong>highlightcolor:</strong> The color of the focus highlight when the widget has the focus.<br /><strong>highlightthickness:</strong> The width of the focus highlight border.<br /><strong>padx:</strong> The horizontal padding of the widget.<br /><strong>pady:</strong> The vertical padding of the widget.<br /><strong>relief:</strong> It represents the border style. The default value is GROOVE.<br /><strong>text:</strong> It represents the string containing the label text.<br /><strong>width:</strong> It represents the width of the frame.</p>


```python
from tkinter import *

gui = Tk()
gui.geometry("200x200")

labelframe = LabelFrame(gui, text="This is a LabelFrame")
labelframe.pack(fill="both", expand="yes")

left = Label(labelframe, text="Inside the LabelFrame")
left.pack()

gui.mainloop()
```



```python
from tkinter import *

gui = Tk()
gui.geometry('300x200')
gui.resizable(False, False)
gui.title('Label Frame')

# label frame
lf = LabelFrame(gui, text='Alignment')
lf.grid(column=0, row=0, padx=20, pady=20)

alignment_var = StringVar()
alignments = ('Left', 'Center', 'Right')

grid_column = 0
for alignment in alignments:
    radio = Radiobutton(lf, text=alignment, value=alignment, variable=alignment_var)
    radio.grid(column=grid_column, row=0, ipadx=10, ipady=10)
    grid_column += 1

gui.mainloop()
```

# ![image.png](attachment:image.png)


```python
from tkinter import *

gui = Tk()
gui.title('LabelFrame Label Anchor')

# label frame
lf = LabelFrame(gui, text='Label Anchor')
lf.grid(column=0, row=0, padx=20, pady=20, sticky=NSEW)

anchor_var = tk.StringVar()
anchors = {
    'nw': {'row': 0, 'column': 1},
    'n': {'row': 0, 'column': 2},
    'ne': {'row': 0, 'column': 3},
    'en': {'row': 1, 'column': 4},
    'e': {'row': 2, 'column': 4},
    'es': {'row': 3, 'column': 4},
    'se': {'row': 4, 'column': 3},
    's': {'row': 4, 'column': 2},
    'sw': {'row': 4, 'column': 1},
    'ws': {'row': 3, 'column': 0},
    'w': {'row': 2, 'column': 0},
    'wn': {'row': 1, 'column': 0}
}


def change_label_anchor():
    lf['labelanchor'] = anchor_var.get()


# create radio buttons and place them on the label frame
for key, value in anchors.items():
    radio = Radiobutton(
        lf,
        text=key.upper(),
        value=key,
        command=change_label_anchor,
        variable=anchor_var
    ).grid(**value, padx=10, pady=10, sticky=tk.NSEW)

# set the radio button selected
anchor_var.set(lf['labelanchor'])

gui.mainloop()
```

# ![image.png](attachment:image.png)


```python
from tkinter import *  
  
gui = Tk()  
gui.geometry("300x200")  
  
labelframe1 = LabelFrame(gui, text="What is Lorem Ipsum?")  
labelframe1.pack(fill="both", expand="yes")  
  
toplabel = Label(labelframe1, text="Lorem Ipsum is simply dummy text.")  
toplabel.pack()  

labelframe2 = LabelFrame(gui, text = "Dummy Text")  
labelframe2.pack(fill="both", expand = "yes")  
  
bottomlabel = Label(labelframe2,text = "Lorem Ipsum is simply dummy text.")  
bottomlabel.pack()  
  
gui.mainloop() 
```

# ![image.png](attachment:image.png)

# <li style='font-size:20pt'>MessageBox In Tkinter</li>
<p>The message box module is used to display the message boxes in the python applications. This module provides a number of functions that you can use to display an appropriate message. Some of these functions are showinfo, showwarning, showerror, askquestion, askokcancel, askyesno, and askretryignore. The syntax to use the message box is given below.</p>
<h2>Syntax:</h2>
<p>box = messagebox.function_name(functionName,message)</p>
<h2>Parameters:</h2>
<p>There are various parameters:</p>
<p><strong>Function_Name:</strong> This parameter is used to represent an appropriate message box function.<br /><strong>title:</strong> This parameter is a string that is shown as a title of a message box. <br /><strong>message:</strong> This parameter is the string to be displayed as a message on the message box. <br /><strong>options:</strong> There are two options that can be used are: <br /><strong>1.) default:</strong> This option is used to specify the default button like ABORT, RETRY, or IGNORE in the message box. <br /><strong>2.) parent:</strong> This option is used to specify the window on top of which the message box is to be displayed.</p>
<h3><strong>Function_Name:</strong></h3>
<p>There are functions or methods available in the messagebox widget.</p>
<p><strong>showinfo():</strong> Show some relevant information to the user. <br /><strong>showwarning():</strong> Display the warning to the user. <br /><strong>showerror():</strong> Display the error message to the user. <br /><strong>askquestion():</strong> Ask a question and the user has to answer yes or no. <br /><strong>askokcancel():</strong> Confirm the user's action regarding some application activity. <br /><strong>askyesno():</strong> The user can answer yes or no for some action. <br /><strong>askretrycancel():</strong> Ask the user about doing a particular task again or not.</p>


```python
from tkinter import *
from tkinter import messagebox

gui = Tk()
gui.title("Message Box")

def btn_msg1():
    messagebox.showinfo("showinfo","Information ")

btn = Button(gui,text="Click here!",command=btn_msg1)
btn.pack()

gui.mainloop()
```

# ![image.png](attachment:image.png)


```python
from tkinter import *
from tkinter import messagebox
gui = Tk()
gui.title("Message Box")

def btn_msg2():
    messagebox.showwarning("showwarning","Warning")

btn2 = Button(gui,text="Show Warning!",command=btn_msg2)
btn2.pack()

gui.mainloop()
```

# ![image.png](attachment:image.png)


```python
from tkinter import *
from tkinter import messagebox
gui = Tk()
gui.title("Message Box")

def btn_msg3():
    messagebox.showerror("showerror","Error")

btn3 = Button(gui,text="Show Error!",command=btn_msg3)
btn3.pack()

gui.mainloop()
```

# ![image.png](attachment:image.png)


```python
from tkinter import *
from tkinter import messagebox
gui = Tk()
gui.title("Message Box")

def btn_msg4():
    messagebox.askquestion("Question","Are you sure?")

btn4 = Button(gui,text="Ask Question!",command=btn_msg4)
btn4.pack()

gui.mainloop()
```

# ![image.png](attachment:image.png)


```python
from tkinter import *
from tkinter import messagebox
gui = Tk()
gui.title("Message Box")

def btn_msg5():
    messagebox.askokcancel("askokcancel", "Want to continue?")

btn5 = Button(gui,text="Ask Ok | Cancel!",command=btn_msg5)
btn5.pack()


gui.mainloop()
```

# ![image.png](attachment:image.png)


```python
from tkinter import *
from tkinter import messagebox
gui = Tk()
gui.title("Message Box")

def btn_msg6():
    messagebox.askyesno("askyesno", "Find the value?")

    
btn6 = Button(gui,text="Ask Yes | No!",command=btn_msg6)
btn6.pack()


gui.mainloop()
```

# ![image.png](attachment:image.png)


```python
from tkinter import *
from tkinter import messagebox
gui = Tk()
gui.title("Message Box")

def btn_msg7():
    messagebox.askretrycancel("askretrycancel", "Try again?")

btn7 = Button(gui,text="Ask Retry | Cancel",command=btn_msg7)
btn7.pack()

gui.mainloop()
```

# ![image.png](attachment:image.png)

# <li style='font-size:20pt'>MenuButton | Main Menu In Tkinter</li>
<p>The Menubutton widget can be defined as the drop-down menu that is shown to the user all the time. It is used to provide the user an option to select the appropriate choice existing within the application. A menu is associated with a menu button that can display the choices of the menu button when clicked by the user.</p>
<h2>Syntax:</h2>
<p>menubtn = Menubutton (parent, options)</p>
<h2>Parameters:</h2>
<p><strong>master:</strong> This parameter is used to represents the parent window.<br /><strong>options: </strong>There are many options which are available and they can be used as key-value pairs separated by commas.</p>
<h2><strong>Options:</strong></h2>
<p>Following are commonly used Option can be used with this widget :-</p>
<p><strong>activebackground:</strong> This option used to represent the background color when the Menubutton is under the cursor.<br /><strong>activeforeground:</strong> This option used to represent the foreground color when the Menubutton is under the cursor.<br /><strong>bg:</strong> This option used to represent the normal background color displayed behind the label and indicator.<br /><strong>bitmap:</strong> This option used to display a monochrome image on a button.<br /><strong>bd:</strong> This option used to represent the size of the border around the indicator and the default value is 2 pixels.<br /><strong>anchor:</strong> This option specifies the exact position of the widget content when the widget is assigned more space than needed.<br /><strong>cursor:</strong> By using this option, the mouse cursor will change to that pattern when it is over the Menubutton.<br /><strong>disabledforeground:</strong> The foreground color used to render the text of a disabled Menubutton. The default is a stippled version of the default foreground color.<br /><strong>direction:</strong> It direction can be specified so that menu can be displayed to the specified direction of the button.<br /><strong>fg:</strong> This option used to represent the color used to render the text.<br /><strong>height:</strong> This option used to represent the number of lines of text on the Menubutton and it&rsquo;s default value is 1.<br /><strong>highlightcolor:</strong> This option used to represent the color of the focus highlight when the Menubutton has the focus.<br /><strong>image:</strong> This option used to display a graphic image on the button.<br /><strong>justify:</strong> This option used to control how the text is justified: CENTER, LEFT, or RIGHT.<br /><strong>menu:</strong> It represents the menu specified with the Menubutton.<br /><strong>padx:</strong> This option used to represent how much space to leave to the left and right of the Menubutton and text. It&rsquo;s default value is 1 pixel.<br /><strong>pady:</strong> This option used to represent how much space to leave above and below the Menubutton and text. It&rsquo;s default value is 1 pixel.<br /><strong>relief:</strong> The type of the border of the Menubutton. It&rsquo;s default value is set to FLAT.<br /><strong>state:</strong> It represents the state of the Menubutton. By default, it is set to normal. We can change it to DISABLED to make the Menubutton unresponsive. The state of the Menubutton is ACTIVE when it is under focus.<br /><strong>text:</strong> This option used use newlines (&ldquo;\n&rdquo;) to display multiple lines of text.<br /><strong>underline:</strong> This option used to represent the index of the character in the text which is to be underlined. The indexing starts with zero in the text.<br /><strong>textvariable:</strong> This option used to represents the associated variable that tracks the state of the Menubutton.<br /><strong>width:</strong> This option used to represents the width of the Menubutton. and also represented in the number of characters that are represented in the form of texts.<br /><strong>wraplength:</strong> This option will be broken text into the number of pieces.</p>


```python
from tkinter import *

gui = Tk()
gui.geometry("150x150")
menubtn = Menubutton(gui, text="Programming", relief=RAISED )
menubtn.grid()
menubtn.menu = Menu(menubtn, tearoff = 0 )
menubtn["menu"] =  menubtn.menu

Var1 = IntVar()
Var2 = IntVar()
Var3 = IntVar()
Var4 = IntVar()
Var5 = IntVar()

menubtn.menu.add_checkbutton (label="Python", variable=Var1)
menubtn.menu.add_checkbutton(label="Java", variable=Var2)
menubtn.menu.add_checkbutton(label="Java Script", variable=Var3)
menubtn.menu.add_checkbutton(label="C++", variable=Var4)
menubtn.menu.add_checkbutton(label="NodeJS", variable=Var5)


menubtn.pack()
gui.mainloop()
```

# ![image.png](attachment:image.png)


```python
from tkinter import *

gui = Tk()
gui.geometry("300x200")

lb = Label(gui, text ='Select Laguages', font = "50")
lb.pack()

menubutton = Menubutton(gui, text = "language")

menubutton.menu = Menu(menubutton, tearoff=0)
menubutton["menu"]= menubutton.menu

var1 = IntVar()
var2 = IntVar()
var3 = IntVar()

menubutton.menu.add_checkbutton(label = "JavaScript", variable = var1)
menubutton.menu.add_checkbutton(label = "Python", variable = var2)
menubutton.menu.add_checkbutton(label = "Darts", variable = var3)

menubutton.pack()
gui.mainloop()

```

# ![image.png](attachment:image.png)


```python
from tkinter import *

gui = Tk()
gui.title('Main Menu')

# create a menubar
menubar = Menu(gui)
gui.config(menu=menubar)

# create a menu
file_menu = Menu(menubar)

# add a menu item to the menu
file_menu.add_command(
    label='Exit',
    command=gui.destroy
)

# add the File menu to the menubar
menubar.add_cascade(
    label="File",
    menu=file_menu
)

gui.mainloop()
```

# ![image.png](attachment:image.png)


```python
from tkinter import *

# Create the default window
gui = Tk()
gui.title("Main Menu")
gui.geometry('150x200')

# Create the list of options
options_list = ["Option 1", "Option 2", "Option 3", "Option 4"]

# Variable to keep track of the option
# selected in OptionMenu
value_inside = StringVar(gui)

# Set the default value of the variable
value_inside.set("Select an Option")

# Create the optionmenu widget and passing
# the options_list and value_inside to it.
question_menu = OptionMenu(gui, value_inside, *options_list)
question_menu.pack()

# Function to print the submitted option-- testing purpose


def print_answers():
    print("Selected Option: {}".format(value_inside.get()))
    return None


# Submit button
# Whenever we click the submit button, our submitted
# option is printed ---Testing purpose
submit_button = Button(gui, text='Submit', command=print_answers)
submit_button.pack()

gui.mainloop()

```

![image.png](attachment:image.png) 

# <li style='font-size:20pt'>Canvas In Tkinter</li>
<p>The canvas widget is used to add structured graphics to the Python application. It can be used to draw simple shapes or complicated graphs. We can also display various kinds of custom widgets according to our needs. The Canvas widget lets us display various graphics on the application.</p>
<h2>Parameters</h2>
<p><strong>master:</strong> This represents the parent window.<br /><strong>options:</strong> Here is the list of most commonly used options for this widget. These options can be used as key-value pairs separated by commas.</p>
<h2>Option</h2>
<p><strong>bd:</strong> Border width in pixels. Default is 2. <br /><strong>bg:</strong> Normal background color.<br /><strong>confine:</strong> If true (the default), the canvas cannot be scrolled outside of the scrollregion.<br /><strong>cursor:</strong> Cursor used in the canvas like arrow, circle, dot etc.<br /><strong>height:</strong> Size of the canvas in the Y dimension.<br /><strong>highlightcolor:</strong> Color shown in the focus highlight.<br /><strong>relief:</strong> Relief specifies the type of the border. Some of the values are SUNKEN, RAISED, GROOVE, and RIDGE.<br /><strong>scrollregion:</strong> A tuple (w, n, e, s) that defines over how large an area the canvas can be scrolled, where w is the left side, n the top, e the right side, and s the bottom.<br /><strong>width:</strong> Size of the canvas in the X dimension.<br /><strong>xscrollincrement:</strong> If you set this option to some positive dimension, the canvas can be positioned only on multiples of that distance, and the value will be used for scrolling by scrolling units, such as when the user clicks on the arrows at the ends of a scrollbar.<br /><strong>xscrollcommand:</strong> If the canvas is scrollable, this attribute should be the .set() method of the horizontal scrollbar.<br /><strong>yscrollincrement:</strong> Works like xscrollincrement, but governs vertical movement.<br /><strong>yscrollcommand:</strong> If the canvas is scrollable, this attribute should be the .set() method of the vertical scrollbar.</p>


```python
from tkinter import *

top = Tk()

C = Canvas(top, bg="blue", height=250, width=300)

coord = 10, 50, 240, 210
arc = C.create_arc(coord, start=0, extent=150, fill="red")

C.pack()
top.mainloop()
```


```python
from tkinter import *


gui = Tk()

C = Canvas(gui, bg="light blue", height=250, width=300)

line = C.create_line(57, 120, 250, 40, fill="green")

C.pack()
gui.mainloop()

```

# ![image.png](attachment:image.png)


```python
from tkinter import *


gui = Tk()

C = Canvas(gui, bg="light blue", height=250, width=300)

arc = C.create_arc(180, 150, 80, 210, start=0, extent=220, fill="red")

C.pack()
gui.mainloop()

```

# ![image.png](attachment:image.png)


```python
from tkinter import *


gui = Tk()

C = Canvas(gui, bg="light blue", height=250, width=300)

oval = C.create_oval(80, 30, 140, 150, fill="gray")

C.pack()
gui.mainloop()

```

# ![image.png](attachment:image.png)


```python
from tkinter import *


gui = Tk()

C = Canvas(gui, bg="light blue", height=250, width=300)

line = C.create_line(57, 120, 490, 40, fill="green")
arc = C.create_arc(180, 150, 80, 210, start=0, extent=220, fill="red")
oval = C.create_oval(80, 30, 140, 150, fill="gray")


C.pack()
gui.mainloop()
```

# ![image.png](attachment:image.png)


```python
from tkinter import *


gui = Tk()

# Create Title
gui.title( "Paint App ")
gui.geometry("500x350")
gui.configure(bg="#deb887")

# define function when
# mouse double click is enabled
def paint( event ):
    # Co-ordinates.
    x1, y1, x2, y2 = ( event.x - 3 ),( event.y - 3 ), ( event.x + 3 ),( event.y + 3 )
    # Colour
    Colour = "black"
    # specify type of display
    w.create_line( x1, y1, x2, y2, fill = Colour )


# create canvas widget.
w = Canvas(gui, width = 400, height = 250)

# call function when double
# click is enabled.
w.bind( "<B1-Motion>", paint )

# create label.
l = Label(gui, text = "Draw Anything With The Help of Drag\nDouble Click and Drag to draw.", bg="#deb887", font="bold")
l.pack()
w.pack()

gui.mainloop()

```

# ![image.png](attachment:image.png)

# <li style='font-size:20pt'>Combobox In Tkinter</li>
<p>Combobox is a combination of an Entry widget and a Listbox widget. A Combobox allows you to select one value in a set of values and enter a custom value. When the user clicks on the drop-down arrow on the entry field, a pop-up of the scrolled Listbox is displayed down the entry field. It is one of the Tkinter widgets containing a down arrow to select from a list of options. Just like CSS is used to style an HTML element, we use Tkinter to style these types of widgets.</p>
<h2>Parameters</h2>
<p><strong>exportselection:</strong> Boolean value. If set, the widget selection is linked to the Window Manager selection<br /><strong>justify:</strong> Specifies how the text is aligned within the widget. One of &ldquo;left&rdquo;, &ldquo;center&rdquo;, or &ldquo;right&rdquo;.<br /><strong>height:</strong> Specifies the height of the pop-down listbox, in rows.<br /><strong>postcommand:</strong> A script that is called immediately before displaying the values. It may specify which values to display.<br /><strong>state:</strong> One of &ldquo;NORMAL, &ldquo;READONLY&rdquo;, or &ldquo;DISABLED&rdquo;. Standard is the default state. Readonly prevents the user from editing any values. disabled shuts down the widgets and greys it out.<br /><strong>textvariable:</strong> Specifies a name whose value is linked to the widget value. Whenever the value associated with that name changes, the widget value is updated, and vice versa. <br /><strong>values:</strong> Specifies the list of values to display in the drop-down listbox.<br /><strong>width:</strong> Specifies an integer value indicating the desired width of the entry window, in average-size characters of the widget&rsquo;s font.</p>


```python
import tkinter as tk
from tkinter import ttk

# Creating tkinter gui
gui = tk.Tk()
gui.title('Combobox')
gui.geometry('500x250')

lb1 = Label(gui, text = "Combobox Drop Down Menu",
            background = 'green', foreground ="white",
            font = ("Times New Roman", 15))
lb1.grid(row = 0, column = 1)

lb2 = Label(gui, text = "Select the Month :",
            font = ("Times New Roman", 10))
lb2.grid(column = 0,row = 5, padx = 10, pady = 25)

n = tk.StringVar()
months = ttk.Combobox(gui, width = 27, textvariable = n)

months['values'] = (' January',
                    ' February',
                    ' March',
                    ' April',
                    ' May',
                    ' June',
                    ' July',
                    ' August',
                    ' September',
                    ' October',
                    ' November',
                    ' December')

months.grid(column = 1, row = 5)
months.current()
gui.mainloop()

```

![image-2.png](attachment:image-2.png)


```python
import tkinter as tk
from tkinter import ttk
from tkinter.messagebox import showinfo
from calendar import month_name

gui = tk.Tk()

gui.geometry('300x200')
gui.resizable(False, False)
gui.title('Combobox Widget')

label = ttk.Label(text="Please select a month:")
label.pack(fill=tk.X, padx=5, pady=5)

selected_month = tk.StringVar()
months = ttk.Combobox(gui, textvariable=selected_month)

months['values'] = [month_name[m][0:9] for m in range(1, 13)]

months['state'] = 'readonly'

months.pack(fill=tk.X, padx=5, pady=5)

def month_changed(event):
    """ handle the month changed event """
    showinfo(
        title='Result',
        message=f'You selected {selected_month.get()}!'
    )

months.bind('<<ComboboxSelected>>', month_changed)

gui.mainloop()
```

# ![image.png](attachment:image.png)


```python
from tkinter import *
from tkinter import ttk

def callback():
    l2.configure(text=cmb.get())
    
gui=Tk()
gui.title('Combobox') 
gui.geometry('300x200')

course=["Pizza","Burger","Noodles"]

l1=Label(gui,text="Choose Your Favorite Food")
l1.grid(column=0, row=0)

cmb=ttk.Combobox(gui,values=course,width=30)
cmb.grid(column=0, row=1)
cmb.current(0)

btn=Button(gui,text="Click Here",command=callback)
btn.grid(column=0, row=2)

l2=Label(gui,text="")
l2.grid(column=0, row=3)
gui.mainloop()
```

# ![image.png](attachment:image.png)

# <li style='font-size:20pt'>TopLevel In Tkinter</li>
<p>Toplevel widgets work as windows that are directly managed by the window manager. They do not necessarily have a parent widget on top of them. The top-level windows have title bars, borders, and other window decorations. This is used when a python application needs to represent some extra information, pop-up, or a group of widgets on the new window.</p>
<h2>Syntax:</h2>
<pre>tlevel = Toplevel(parent, options)</pre>
<h2>Parameters:</h2>
<p><strong>bg:</strong> The background color of the window. <br /><strong>bd:</strong> Border width in pixels; default is 0.<br /><strong>cursor:</strong> The cursor that appears when the mouse is in this window.<br /><strong>class:</strong> Normally, text selected within a text widget is exported to be the selection in the window manager. Set exportselection=0 if you don't want that behavior.<br /><strong>font:</strong> The default font for text inserted into the widget. <br /><strong>fg:</strong> The color used for text (and bitmaps) within the widget. You can change the color for tagged regions; this option is just the default.<br /><strong>height:</strong> Window height.<br /><strong>relief:</strong> Normally, a top-level window will have no 3-d borders around it. To get a shaded border, set the bd option larger that its default value of zero, and set the relief option to one of the constants.<br /><strong>width:</strong> The desired width of the window.</p>
<h2>Methods:</h2>
<p><strong>deiconify():</strong> Displays the window, after using either the iconify or the withdraw methods.<br /><strong>frame():</strong> Returns a system-specific window identifier.<br /><strong>group(window):</strong> Adds the window to the window group administered by the given window.<br /><strong>iconify():</strong> Turns the window into an icon, without destroying it.<br /><strong>protocol(name, function):</strong> Registers a function as a callback which will be called for the given protocol.<br /><strong>iconify():</strong> Turns the window into an icon, without destroying it.<br /><strong>state():</strong> Returns the current state of the window. Possible values are normal, iconic, withdrawn and icon.<br /><strong>transient([master]):</strong> Turns the window into a temporary(transient) window for the given master or to the window's parent, when no argument is given.<br /><strong>withdraw():</strong> Removes the window from the screen, without destroying it.<br /><strong>maxsize(width, height):</strong> Defines the maximum size for this window.<br /><strong>minsize(width, height):</strong> Defines the minimum size for this window.<br /><strong>positionfrom(who):</strong> Defines the position controller.<br /><strong>resizable(width, height):</strong> Defines the resize flags, which control whether the window can be resized.<br /><strong>sizefrom(who):</strong> Defines the size controller.<br /><strong>title(string):</strong> Defines the window title.</p>


```python
from tkinter import *


gui = Tk()
gui.geometry("200x300")
gui.title("main")

l = Label(gui, text = "This is gui window")

top = Toplevel()
top.geometry("180x100")
top.title("toplevel")
l2 = Label(top, text = "This is toplevel window")

l.pack()
l2.pack()

top.mainloop()

```

# ![image.png](attachment:image.png)


```python
from tkinter import *

gui = Tk()
gui.title("Root Window")
gui.geometry("450x300")

# Create label for root window
label1 = Label(gui, text = "This is the gui window")
label1.pack()

def open_Toplevel2():
    top2 = Toplevel()
    top2.title("Toplevel2")
    top2.geometry("200x100")
    label = Label(top2,text = "This is a Toplevel2 window")
    label.pack()
    
    button = Button(top2, text = "Exit",command = top2.destroy)
    button.pack()
    
    top2.mainloop()

def open_Toplevel1():
    top1 = Toplevel(gui)
    top1.title("Toplevel1")
    top1.geometry("200x200")
    label = Label(top1,text = "This is a Toplevel1 window")
    label.pack()
    
    button1 = Button(top1, text = "Exit",command = top1.destroy)
    button1.pack()
    
    button2 = Button(top1, text = "open toplevel2",command = open_Toplevel2)
    button2.pack()
    
    top1.mainloop()

button = Button(gui, text = "open toplevel1",command = open_Toplevel1)
button.place(x = 155, y = 50)

gui.mainloop()
```

# ![image.png](attachment:image.png)

-----------------


# ____________Other Topic______________

# Background Image Load

```python
from tkinter import *
from PIL import Image, ImageTk

# def set_background_image(window, image_path):

# Create the main window
root = Tk()
root.title("Image Background Example")

# Set the window size
root.geometry("600x600")

image = Image.open("img_600x600.jpg")
photo = ImageTk.PhotoImage(image)
label = Label(root, image=photo)
label.image = photo
label.place(x=0, y=0, relwidth=1, relheight=1)

# Run the application
root.mainloop()

```


```python
import tkinter as tk
from PIL import Image, ImageTk

def set_background_image(window, image_path):
    # Load the image
    global photo
    image = Image.open(image_path)
    photo = ImageTk.PhotoImage(image)
    
    # Create a label and set the image as its background
    label = tk.Label(window, image=photo)
    label.image = photo  # Keep a reference to avoid garbage collection
    label.place(x=0, y=0, relwidth=1, relheight=1)  # Stretch the label to cover the whole window

# Create the main window
root = tk.Tk()
root.title("Image Background Example")

# Set the window size
root.geometry("400x300")

# Set the background image
set_background_image(root, "download.jpg")  # Change the image path accordingly

# Run the application
root.mainloop()

```

# Image on Button Example


```python
import tkinter as tk
from PIL import Image, ImageTk

root = tk.Tk()
root.title("Image on Button Example")

image = Image.open("cross.png")
photo = ImageTk.PhotoImage(image)

button = tk.Button(root)
button.config(image=photo, width=300, height=300)
button.image = photo
button.pack()

root.mainloop()

```

# Entry Widget with Image


```python
import tkinter as tk
from PIL import Image, ImageTk

def set_entry_with_image(root, image_path):
    # Create a frame to hold the widgets
    frame = tk.Frame(root)
    frame.pack()

    # Load the image
    image = Image.open(image_path)
    photo = ImageTk.PhotoImage(image)

    # Create a label for the image
    image_label = tk.Label(frame, image=photo)
    image_label.image = photo
    image_label.grid(row=0, column=0)

    # Create an entry widget
    entry = tk.Entry(frame, width=20)
    entry.grid(row=0, column=1)

# Create the main window
root = tk.Tk()
root.title("Entry Widget with Image Example")

# Set the entry with image
set_entry_with_image(root, "download.jpg")

# Run the application
root.mainloop()

```

# Multiple Images in List


```python
import tkinter as tk
from PIL import Image, ImageTk

def display_images(window, image_paths):
    # Create a frame to hold the images
    frame = tk.Frame(window)
    frame.pack()

    # Loop through the image paths and display each image
    for i, image_path in enumerate(image_paths):
        # Load the image
        image = Image.open(image_path)
        photo = ImageTk.PhotoImage(image)

        # Create a label for the image
        label = tk.Label(frame, image=photo)
        label.image = photo
        label.grid(row=0, column=i, padx=5, pady=5)

# Create the main window
root = tk.Tk()
root.title("Multiple Images in List Example")

# List of image paths
image_paths = ["download.jpg","img_600x600.jpg","xyz.jpg"]  # Add more image paths as needed

# Display the images
display_images(root, image_paths)

# Run the application
root.mainloop()

```

# Image Tooltip - Hovering


```python
import tkinter as tk
import tkinter.ttk as ttk
from PIL import Image, ImageTk

class HoverInfo:
    def __init__(self, widget, image_path):
        self.widget = widget
        self.image_path = image_path
        self.tipwindow = None
        self.id = None
        self.x = self.y = 0
        
    def show_image_tooltip(self, event):
        self.x, self.y, _, _ = self.widget.bbox("insert")
        self.x += self.widget.winfo_rootx() + 25
        self.y += self.widget.winfo_rooty() + 25
        
        # Create a toplevel window
        self.tipwindow = tk.Toplevel(self.widget)
        self.tipwindow.overrideredirect(True)
        
        # Load and display the image
        image = Image.open(self.image_path)
        photo = ImageTk.PhotoImage(image)
        label = tk.Label(self.tipwindow, image=photo)
        label.image = photo
        label.pack()
        
        self.tipwindow.wm_geometry("+%d+%d" % (self.x, self.y))

    def hide_image_tooltip(self, event):
        if self.tipwindow:
            self.tipwindow.destroy()

def main():
    root = tk.Tk()
    root.title("Image Tooltip Example")
    
    # Create a label widget
    label = ttk.Label(root, text="Hover Me")
    label.pack(padx=10, pady=10)
    
    # Initialize HoverInfo object with label widget and image path
    hover_info = HoverInfo(label, "img_600x600.jpg")  # Change the image path accordingly
    
    # Bind events to show and hide image tooltip
    label.bind("<Enter>", hover_info.show_image_tooltip)
    label.bind("<Leave>", hover_info.hide_image_tooltip)
    
    root.mainloop()

if __name__ == "__main__":
    main()

```

# Image with opencv


```python
import cv2
import tkinter as tk
from PIL import Image, ImageTk

def convert_image_for_tk(image):
    image = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)  # Convert from BGR to RGB color space
    image = Image.fromarray(image)  # Convert to PIL Image
    photo = ImageTk.PhotoImage(image)  # Convert to PhotoImage
    return photo

def display_image(image_path):
    # Create main window
    root = tk.Tk()
    root.title("Image Display Example")
    
    # Load image using OpenCV
    image = cv2.imread(image_path)
    
    # Convert image for Tkinter
    photo = convert_image_for_tk(image)
    
    # Create label for image
    label = tk.Label(root, image=photo)
    label.photo = photo  # Keep a reference to avoid garbage collection
    label.pack(padx=10, pady=10)

    # Run the application
    root.mainloop()

# Path to the image
image_path = "img_600x600.jpg"  # Replace with your image path
display_image(image_path)

```
