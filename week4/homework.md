### Homework for 9/21/17

##### Software
Install [Fritzing](http://fritzing.org) on your main machine for circuit layout diagramming.

Also install it onto your Raspberry Pi

```
sudo apt-get install fritzing
```

##### Electronics
Create a circuit that, when a user presses and holds a button, an RGB LED illuminates and displays a color dependent on a reading from the DS18B20 sensor.

##### Programming
1. Make a python shell script `worldlyhello.py` that takes a language as input, and outputs "hello world" in that language, or returns an understandable error.

```
python worldlyhello.py spanish
buenos dias, el mundo
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

Make good use of `if` and `elif`!

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

##### Motion Challenge

Using *any means available to you*, excluding prefabricated parts, create a propulsion system that...

- holds wheeled vehicles from last week in place until launch
- has a controllable trigger to launch the vehicles
- can accelerate both team member's wheeled vehicle from last week's homework in a *straight* line...
- ...to repeatable, controllable distances: 6ft, 10ft, and 20ft in reliably consistent times
- with a minimum of parts and a maximum of styling

The goal this week is accuracy. How repeatable in time and position can sequential launches be? 

The deliverable should be an mp4 or gif recording a set of 3 launches that demonstrate the most similar attainable distance and time. Do not disassemble the propulsion system, we will reuse it. 

Materials in the shop to explore include elastic, rubber bands, springs, balloons, controlled inclines or drops, flame-induced vacuum, sails and electric fans... what else could be used?
