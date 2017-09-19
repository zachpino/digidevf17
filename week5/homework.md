### Homework for 9/28/17

##### Programming
1. Make a python shell script `worldlyhello.py` that takes a language as input, and outputs "hello world" in that language, or returns an understandable error.

```
python worldlyhello.py spanish
buenos dias, a todo el mundo
```

```
python worldlyhello.py somali
salaam dunida oa dhan
```

Support at least five languages, and if a user enters an unincluded language, offer help.

```
python worldlyhello.py burmese
Sorry, worldlyhello only supports arabic, quechua, somali, vietnamese, sardinian, and inuktitut.
```

Make good use of `if` and `elif`! Try to use a list to hold all of the possible strings like this pseudo-code.

```
helloWorldList = ["Hello world", "Buon giorno, a tutto il mondo", "Marhabaan liljamie"]

if sys.argv[1] == "italian"
 print(helloWorldList[1])
```

2. Make a python shell script `color.py` that takes a color as input, and outputs that color to an rgb led attached to the GPIO pins and provides feedback to the user of success or failure. The script should support at least red, green, blue, magenta, yellow, cyan, orange, [millenialpink](https://www.theguardian.com/artanddesign/shortcuts/2017/mar/22/millennial-pink-is-the-colour-of-now-but-what-exactly-is-it), white, and black.

```
python color.py cyan
The LED is glowing cyan

python color.py purple
This LED does not support purple. Try colors like red, cyan, or white.
```

Could you create functionality in the same script that, in the event of 3 numerical inputs, uses those values to set the color of an RGB led directly? You can use `len()` to check how many arguments the user has entered.

```
if len(sys.argv) == 3
 ...
else
 ...
```

##### Motion Challenge | Chilly Robot
Using any means available to you, create an object that has a temperature sensor and RGB LED onboard, as well as means for rolling motion. The object should...

- ...take the average of several temperature reading with short time gaps in between. The object should indicate visually that it is "thinking."
 - if that averaged temperature reading is higher than the previous reading, the object should move forward and display warm colors.
 - otherwise, if the number is lower than the previous reading, the object should move backwards and display cool colors.
 
 The net result is that the object should, given a linear region, continually seek out the warmest spot autonomously.
