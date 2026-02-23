from machine import Pin,PWM
import time
import neopixel

myneo = neopixel.NeoPixel(Pin(23),16)
ir = Pin(15,Pin.IN,Pin.PULL_UP)
motor = PWM(4,Pin.OUT)
buzzer = PWM(Pin(14))
buzzer.duty(256)
motor.freq(50)
notes = [4000,400,600,2000,1000]

while True:
    ir_val = ir.value()
    if ir_val < 1:
        for x in notes:
            buzzer.freq(x)
            time.sleep(0.3)
        print(ir_val)
        for i in range(0,16,1):
            myneo[i] = (0,0,255)
            time.sleep(0.09)
            myneo.write()
        for x in range(35,100):
            motor.duty(x)
            time.sleep(0.1)
            motor.duty(35)
        buzzer.duty(0)
    else:
        ir_val == 0
        for r in range(0,16,1):
            myneo[r] = (255,0,0)
            time.sleep(0.001)
            myneo.write()
            
