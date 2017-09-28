### Shell Scripts and Python Library: Pillow and Image Manipulation

It is straightforward to make a text file containing Python code run through the command line.

```
mkdir ~/Desktop/pillow
cd ~/Desktop/pillow/
touch hello.py
nano hello.py
```

We can type in python code into the `nano` text editor to create programs to run via the command line.

In `nano` enter the following.

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

Python will return

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

The combination of python code and shell arguments is incredibly powerful, with many obvious applications. For instance, we can produce a simple command line image resizer with the [Pillow](https://python-pillow.org) Python image processing library.

```
touch resize.py
nano resize.py
```

Enter the following text to create the resizing logic.

```python
#import necessary dependencies
import os, sys
from PIL import Image

#access what user entered for overall size and convert to integers
width = int(sys.argv[1])
height = int(sys.argv[2])

#create tuple
size = (width, height)

#access all image files user entered
for infile in sys.argv[3:]:
    #subtract extension from filename and add .thumbnail
    outfile = os.path.splitext(infile)[0] + ".thumbnail"
    #make sure the above line worked...
    if infile != outfile:
        try:
            #open file for editing
            im = Image.open(infile)
            #resize to specified size
            im.thumbnail(size)
            #save as jpeg
            im.save(outfile, "JPEG")
        except IOError:
            #let user know in event of error
            print("cannot create thumbnail for", infile)

```

The program will only resize *down*. Run the program like so...

```
python resize.py 200 100 ~/Desktop/someimage.jpg
```

