### Homework for 9/21/17

##### Raspberry Pi Improvements
Install [Fritzing](http://fritzing.org) on your main machine for circuit layout diagramming.

Also install it onto your Raspberry Pi

```
sudo apt-get install fritzing
```

Change your background desktop image as well, have your Raspberry Pi reflect your personality a bit! Use your Raspberry Pi to browse the internet, and check out its built-in software.

##### Electronics and Programming
Create a circuit that, *when a user presses a button*, an RGB LED illuminates for a set amount of time to display an encoded but legible version of the reading from the DS18B20 sensor. 

Have the RGB illuminate to the following colors at these Celsius temperatures. Feel free to adjust these numbers to the readings of your sensor in the studio so you can see the full RGB rainbow.

```
30 >  Red
27 >  Yellow  <= 30
24 >  Green   <= 27
21 >  Cyan    <= 24
18 >  Blue    <= 21
      Magenta <= 18 
```

You will need compound conditions to make this happen. Take a look at the [grade.py example halfway down this page](https://www.digitalocean.com/community/tutorials/how-to-write-conditional-statements-in-python-3-2) in this tutorial on conditions in Python for a hint.

Come to class next week with the completed circuit, code, and any questions.

##### Motion Challenge

Using *any means available to you*, excluding prefabricated parts, create a propulsion system that...

- holds wheeled vehicles from last week in place until launch
- has a controllable trigger to launch the vehicles
- can accelerate both team member's wheeled vehicle from last week's homework in a *straight* line...
- ...to repeatable, controllable distances: 6ft, 10ft, and 20ft in reliably consistent times
- with a minimum of parts and a maximum of styling

The goal this week is accuracy, not speed or durability. How repeatable in time and position can sequential launches be? 

The deliverable should be an mp4 or gif recording a set of 3 launches that demonstrate the most similar attainable distance and time. For example, a video showing a launch of the same vehicle to 6ft each time, with a marking placed to show each launch's result for comparison. Do not disassemble the propulsion system, we will reuse it. 

Materials in the shop to explore include elastic, rubber bands, springs, balloons, controlled inclines or drops, flame-induced vacuum, sails and electric fans... what else could be used?
