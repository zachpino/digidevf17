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

print("Hello World!")
```

##### Indentation
Some languages use curly braces { and } to wrap around lines of code which belong together, and leave it to the writer to indent these lines to appear visually nested. However, Python does not use curly braces but instead requires indentation for nesting. For example a for loop in Python:
for i in range(10):
    print("Hello")
The indentation is necessary here. A second line indented would be a part of the loop, and a second line not indented would be outside of the loop. For example:
for i in range(2):
    print("A")
    print("B")
would print:
A
B
A
B
whereas the following:
for i in range(2):
    print("A")
print("B")
would print:
A
A
B
Variables
To save a value to a variable, assign it like so:
name = "Bob"
age = 15
Note here I did not assign types to these variables, as types are inferred, and can be changed (it's dynamic).
age = 15
age += 1  # increment age by 1
print(age)
This time I used comments beside the increment command.

print("Hello")
Lists
Python also has lists (called arrays in some languages) which are collections of data of any type:
numbers = [1, 2, 3]
Lists are denoted by the use of square brackets [] and each item is separated by a comma.
Iteration
Some data types are iterable, which means you can loop over the values they contain. For example a list:
numbers = [1, 2, 3]

for number in numbers:
    print(number)
This takes each item in the list numbers and prints out the item:
1
2
3
Note I used the word number to denote each item. This is merely the word I chose for this - it's recommended you choose descriptive words for variables - using plurals for lists, and singular for each item makes sense. It makes it easier to understand when reading.
Other data types are iterable, for example the string:
dog_name = "BINGO"

for char in dog_name:
    print(char)
This loops over each character and prints them out:
B
I
N
G
O
Range
The integer data type is not iterable and trying to iterate over it will produce an error. For example:
for i in 3:
    print(i)
will produce:
TypeError: 'int' object is not iterable

However you can make an iterable object using the range function:
for i in range(3):
    print(i)
range(5) contains the numbers 0, 1, 2, 3 and 4 (five numbers in total). To get the numbers 1 to 5 use range(1, 6).
Length
You can use functions like len to find the length of a string or a list:
name = "Jamie"
print(len(name))  # 5

names = ["Bob", "Jane", "James", "Alice"]
print(len(names))  # 4
If statements
You can use if statements for control flow:
name = "Joe"

if len(name) > 3:
    print("Nice name,")
    print(name)
else:
    print("That's a short name,")
    print(name)
Python files in IDLE
To create a Python file in IDLE, click File > New File and you'll be given a blank window. This is an empty file, not a Python prompt. You write a Python file in this window, save it, then run it and you'll see the output in the other window.
For example, in the new window, type:
n = 0

for i in range(1, 101):
    n += i

print("The sum of the numbers 1 to 100 is:")
print(n)
Then save this file (File > Save or Ctrl + S) and run (Run > Run Module or hit F5) and you'll see the output in your original Python window.
Executing Python files from the command line
You can write a Python file in a standard editor like Vim, Nano or LeafPad, and run it as a Python script from the command line. Just navigate to the directory the file is saved (use cd and ls for guidance) and run with python, e.g. python hello.py.
