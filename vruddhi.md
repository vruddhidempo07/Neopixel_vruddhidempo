from machine import Pin
import time
import neopixel

ir_sensor = Pin(25,Pin.IN,Pin.PULL_UP)
haha = neopixel.NeoPixel(Pin(15),16)

while True:
    haha_val = ir_sensor.value()
    print(haha_val)
    if haha_val==0:
        for i in range(0,16,1):
            haha[i]=(0,0,255)
            haha.write()
            time.sleep(0.1)
    
    else:
        for i in range(0,16,1):
            haha[i]=(0,0,0)
            haha.write()
    time.sleep(0.1)
