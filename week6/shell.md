### Shell Scripts 

We have already made a text file containing Python code and run it through the command line.

```
mkdir ~/Desktop/pillow
cd ~/Desktop/pillow/
touch hello.py
echo "print('hello')" > hello.py
python hello.py
```
This will return the word `hello` in your terminal. But, what if we wanted user input instead -- for instance, what if we wanted to greet a user by name?

```
#!/usr/bin/python
# Hello world python program

import sys
name = sys.argv[1]

print("hello " + name)
```

Press 'control+o' to save, hitting 'enter' to confirm, and then 'control+x' to exit.

The first "shebang" line of the script tells the terminal application what program should run the program. Here, the python binary is chosen. The second line is a comment for humans, letting everyone know what the program does.

`import sys` adds the 'system' module, allowing the python code to access information coming at it from low-level software stacks, like the standard input/output that the terminal application uses.

We associate the variable `name` with the second element of a Python list (lists start at [0], so [1] is the second item) produced by the system module called `argv`. `argv` returns the command that launched this python application, and its arguments and options, as a list. The [0] item is the name of the command, and the rest of the list are the arguments entered in order.

We can run the application like so.

```
python hello.py zach
```

Python will return...

```
Hello zach
```

We can edit the program to include more information...
```
nano hello.py
```
... to include time and date information.

```
#!/usr/bin/python
# Hello world python program

#import dependencies
import sys
import time

#get user arguments
name = sys.argv[1]

#get current time and convert to string
now = str(time.ctime())

print("hello " + name + ", it is now " + now)
```
