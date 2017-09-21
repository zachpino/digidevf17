```
#Python script for digital temperature sensor (pin 4) and RGB LED readout (pins 12,16,20)

#necessary dependencies
import RPi.GPIO as GPIO
import time
from w1thermsensor import W1ThermSensor

#disable needless warnings about GPIO misuse
GPIO.setwarnings(False)

#set a reusable variable to hold the library's utilities
sensor = W1ThermSensor()

#pin layouts for common cathode RGB LED
rPin = 12
gPin = 16
bPin = 20

#set 'one-way streets' to run away from the RasPi for LED and button
GPIO.setmode(GPIO.BCM)
GPIO.setup(rPin, GPIO.OUT)
GPIO.setup(gPin, GPIO.OUT)
GPIO.setup(bPin, GPIO.OUT)
GPIO.setup(21, GPIO.IN, pull_up_down=GPIO.PUD_UP)

#variable for frequency
freq = 100

#set the used GPIO pins to PWM mode at 100hz
red = GPIO.PWM(rPin,freq)
red.start(0)
green = GPIO.PWM(gPin,freq)
green.start(0)
blue = GPIO.PWM(bPin,freq)
blue.start(0)

while True : 
	#reset LEDs
	red.ChangeDutyCycle(0)
	green.ChangeDutyCycle(0)
	blue.ChangeDutyCycle(0)
	
	#button check
	input_state = GPIO.input(21)
	if input_state == False:
		print('Button Pressed')
		
		#get sensor value
		temp_c = sensor.get_temperature()
		
		if temp_c > 30 :
			#set color and intensity for red
			red.ChangeDutyCycle(75)
			green.ChangeDutyCycle(0)
			blue.ChangeDutyCycle(0)
			
			print("The temperature is: " + str(temp_c) + "C")
		elif temp_c >= 27 :
                        #set color and intensity for yellow
                        red.ChangeDutyCycle(75)
                        green.ChangeDutyCycle(75)
                        blue.ChangeDutyCycle()

			print("The temperature is: " + str(temp_c) + "C")
			
		elif temp_c >=24 :
			#set color and intensity for green
                        red.ChangeDutyCycle(0)
                        green.ChangeDutyCycle(75)
                        blue.ChangeDutyCycle(0)
		
			print("The temperature is: " + str(temp_c) + "C")

		elif temp_c >= 21 :
                        #set color and intensity for cyan
                        red.ChangeDutyCycle(0)
                        green.ChangeDutyCycle(75)
                        blue.ChangeDutyCycle(75)

			print("The temperature is: " + str(temp_c) + "C")

		elif temp_c >= 18 : 
			#set color and intensity for blue
                        red.ChangeDutyCycle(0)
                        green.ChangeDutyCycle(0)
                        blue.ChangeDutyCycle(75)
		
			print("The temperature is: " + str(temp_c) + "C")

		else :                        
			#set color and intensity for magenta
			red.ChangeDutyCycle(75)
                        green.ChangeDutyCycle(0)
                        blue.ChangeDutyCycle(75)
			
			print("The temperature is: " + str(temp_c) + "C")

		#delay so we can see the led illuminate
		time.sleep(3)
	#delay between button reads
	time.sleep(.1)
```
