### Python Program : Image Resizing with Pillow

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
            originalImage = Image.open(infile)
      
            #resize to specified size
            newImage = originalImage.resize(size, Image.ANTIALIAS)
      
            #save as jpeg
            newImage.save(outfile, "JPEG")
     
        except IOError:
            #let user know in event of error
            print("cannot create thumbnail for " + str(infile))
```

The program will resize any image and produce the resized jpg. Run the program like so...

```
python resize.py 200 100 ~/Desktop/someimage.jpg
```
