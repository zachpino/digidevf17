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

We associate the variable `name` with the second element of a Python list (lists start at [0], so [1] is the second item) produced by the system module called `argv`. `argv` returns the command that launched this python application as a list. The [0] item is the name of the application, and the rest of the list are the arguments entered.

We can run the application like so.

```
python hello.py zach
```

Python will return

```
Hello zach
```

The combination of python code and shell arguments is incredibly powerful, with many obvious applications. For instance, we can produce a simple command line image resizer with the [Pillow](https://python-pillow.org) Python image processing library.

```
touch resize.py
nano resize.py
```

Enter the following text to create the resizing logic.

```
import os, sys
import Image

width = sys.argv[1]
height = sys.argv[2]

for infile in sys.argv[3:]:
    outfile = os.path.splitext(infile)[0] + ".thumbnail"
    if infile != outfile:
        try:
            im = Image.open(infile)
            im.thumbnail(width, height, Image.ANTIALIAS)
            im.save(outfile, "JPEG")
        except IOError:
            print "cannot create thumbnail for '%s'" % infile
```

Run the program like so...

```
python resize.py 200 100 ~/Desktop/someimage.jpg
```
