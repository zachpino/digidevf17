### Homework for 9/28/17

##### Motion Challenge | Chilly Robot
Using any means available to you, create an object that has a temperature sensor and RGB LED onboard, as well as means for controlled rolling motion (1-4 DC motors with up to 2 L293D drivers). The object should...

- ...take the average of several temperature reading with short time gaps in between. The object should indicate visually that it is "thinking."
 - The object should roll forward and do the same sensing routine...
 - If that averaged temperature reading is higher than the previous reading, the object stay forwards and display warm colors...
 - otherwise, if the number is lower than the initial reading, the object should move backwards and display cool colors.
 
The net result is that the object should, given a linear region, continually seek out the warmest spot autonomously while providing understandable feedback to an audience. The delay between temperature readings and the amount of distance traveled at each evaluation should be experimentally fine-tuned for best results. 
