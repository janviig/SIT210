#pwm 

from time import sleep
import gpiozero
from gpiozero import DistanceSensor, PWMLED

redLed = PWMLED(14)

sensor = DistanceSensor(echo=17, trigger=4)

def furtherDistance():
    sensor.value
#     print("distance is: " + furtherDistance)
    furtherDistance = sensor.distance * 100
    return(furtherDistance)
    
while True:
#     furtherDistance = sensor.distance * 100
    distance = furtherDistance()
    print("distance is: ", furtherDistance())
    sleep(1)
    
    if(distance<30.0 and distance>25.0):
        redLed.value = 0.1
        sleep(0.5)
    elif(distance<25.0 and distance>15.0):
        redLed.value = 0.4
        sleep(0.5)
    elif(distance<15.0 and distance>5.0):
        redLed.value = 1
    else:
        redLed.value = 0
        sleep(0.5)
