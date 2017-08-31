### Turn on and off an LED on pin 18
```
#import necessary libraries
import RPi.GPIO as GPIO
import time

#make our pins behave as expected
GPIO.setmode(GPIO.BCM)
GPIO.setwarnings(False)

#make sure the pin 'one-way-streets' run the right direction
GPIO.setup(18,GPIO.OUT)

#turn on the led and print a notification
print "LED on"
GPIO.output(18,GPIO.HIGH)
time.sleep(1)

#turn off the led and print a notification
print "LED off"
GPIO.output(18,GPIO.LOW)
```

### Check for button press on pin 21
```
#import necessary libraries
import RPi.GPIO as GPIO
import time

#make our pins behave as expected
GPIO.setmode(GPIO.BCM)

#make sure the pin 'one-way-streets' run the right direction
GPIO.setup(18, GPIO.IN, pull_up_down=GPIO.PUD_UP)

#run forever
while True:
    input_state = GPIO.input(18) #check the state of pin 18
    if input_state == False:
        print('Button Pressed')
        time.sleep(0.5) #delay a bit
```

[electronics]: FullSizeRender.jpg
