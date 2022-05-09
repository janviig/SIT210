import time
import smbus

BH1750_sensor = 0x23
lightOn = 0x01 #turn on = 1
lightOff = 0x00 #turn off = 0
received_address = 0x20

bus = smbus.SMBus(1)

def lightIntensity():
    data = bus.read_i2c_block_data(BH1750_sensor, received_address)
    return lightSensor(data)

def lightSensor(data):
    result = ((data[1] + (256 * data[0])) / 1.2)
    return result

def main():
    while True:
        intensity = lightIntensity()
        print(lightIntensity())
        if(intensity>=200):
            print("too bright")
        elif(intensity>100):
            print("bright")
        elif(intensity>50):
            print("medium")
        elif(intensity<50):
            print("dark")
        elif(intensity<10):
            print("too dark")
        
        time.sleep(1)
main()
