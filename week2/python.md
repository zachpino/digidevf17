 ### Python Basics

On the Raspberry Pi, Python is an easy to learn programming language with many different interfaces. It is powerful, expressive, and easy to debug.

##### IDLE
The easiest way to play with Python is to open IDLE, an interface for rapid code prototyping. Access the `Raspberry Menu`, navigate to `Programming` and select `Python 3 (Idle)`. A window will popup that permits interactive python code.

##### Printing to the Console
The standard `Hello world` example, in Python:

```
print("Hello world")
```
##### Comments
Comments are text that are humand-readable, and ignored by the compiler. Take notes by using comments directly in code!

You can write comments in Python by typing the `#` character and following it up with text on a single line.

```
print("Hello world") #this prints text to the console
```

Multi-line comments use three quotation characters to begin and end the comment.

```
"""
This says hello
to everyone
all over the planet
"""

print("Hello " + "World") #we can glue text together with the addition sign, just like numbers
```

##### Variables
It is easy to make a container for information, called a `variable` in Python -- and you don't even need to know what kind of information it will store (unlike many other programming languages). The technical term for this behavior is that Python is a *dynamically-typed* language.

```
name = "Zach"
siblingCount = "1"

print(name + " has " + str(siblingCount) + "sibling")
```

Note that, in order to print `siblingCount`, we must convert it to a String (text) format. Variables can hold whatever data, but in Python it is often necessary to force a data type when the information is used.

##### Indentation and Simple Loops
Some languages use curly braces ({ and }) or other formatting characters to determine which code is subordinated to other code. Often, programmers use indentation to show these relationships, as these formatting characters can be easily missed. Python does not use curly braces, and instead just makes use of indentation.

```
for i in range(10):
    print("Hello " + str(i) + " times")
```

##### Conditions

Conditions work the same way as loops.

```
#Zach's fashion rules
temp = 82

if temp > 100:
    print("Wear short-sleeves!")
else:
    print("Wear long-sleeves but roll them up!")
```
