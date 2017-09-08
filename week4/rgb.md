RGB Common Cathode LED on Pins 12, 16, 21

```
import RPi.GPIO as GPIO
import time

rPin = 12
gPin = 16
bPin = 20
 
GPIO.setmode(GPIO.BCM)
GPIO.setup(rPin, GPIO.OUT)
GPIO.setup(gPin, GPIO.OUT)
GPIO.setup(bPin, GPIO.OUT)

freq = 100

red = GPIO.PWM(rPin,freq)
red.start(0)
green = GPIO.PWM(gPin,freq)
green.start(0)
blue = GPIO.PWM(bPin,freq)
blue.start(0)

count = "up"

while True :
 if count == "up" :
  print("ascending")
  for i in range(1,100):
   red.ChangeDutyCycle(i)
   time.sleep(.1)
  count = "down"

 elif count == "down" :
  print("descending")
  for i in range(1,100):
   red.ChangeDutyCycle(100 - i)
   time.sleep(.1)
  count = "up"
```
