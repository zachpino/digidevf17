### L293D and Single DC Motor

![l293d and 1 motor](l293d_singlemotor_bb.png)

```
import RPi.GPIO as GPIO
from time import sleep
 
GPIO.setmode(GPIO.BCM)

Motor1A = 27
Motor1B = 22
Motor1E = 17
 
GPIO.setup(Motor1A,GPIO.OUT)
GPIO.setup(Motor1B,GPIO.OUT)
GPIO.setup(Motor1E,GPIO.OUT)

freq = 100

motor = GPIO.PWM(Motor1E, freq)
motor.start(0)

print "Going forwards, fast"
GPIO.output(Motor1A,GPIO.HIGH)
GPIO.output(Motor1B,GPIO.LOW)
motor.ChangeDutyCycle(90)
 
sleep(2)
 
print "Going backwards, slow"
GPIO.output(Motor1A,GPIO.LOW)
GPIO.output(Motor1B,GPIO.HIGH)
motor.ChangeDutyCycle(50)

 
sleep(2)
 
print "Now stop"
GPIO.output(Motor1E,GPIO.LOW)
 
GPIO.cleanup()
```

### L293D and Dual DC Motors

![l293d and 1 motor](l293d_singlemotor_bb.png)
