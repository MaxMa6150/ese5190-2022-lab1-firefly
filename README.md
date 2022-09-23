University of Pennsylvania, ESE 5190: Intro to Embedded Systems, Lab 1

    Sizhe Ma
        masizhe@seas.upenn.edu
    Tested on:  
    Partner: Sudong Wang
    
# Overview
In this lab, we mainly did several tasks list below:
1) get familiar with microcontroller Adafruit QT Py RP2040 and sensor board APDS9960
2) set up Adafruit QT Py RP2040 and connect it to APDS9960
3) get familiar with the sensor brightness perception, color recognition and gesture perception function 
4) track the brightness reading from APDS9960's color sensor and simultaneously display on RP2040's LED via neopixel (Q.3.2)
5) track the gesture and brightness reading and display on PC with RP2040's keyboard function

### code setup
```python
import board
import busio
import time
import adafruit_apds9960.apds9960
import neopixel


#i2c = board.STEMMA_I2C()
i2c = busio.I2C(board.SCL1, board.SDA1)
sensor = adafruit_apds9960.apds9960.APDS9960(i2c)
sensor.enable_proximity = True                         # for brightness sensor
sensor.enable_color = True                             # for color sensor
sensor.enable_gesture = True                           # for gesture sensor
sensor.color_integration_time = 10                     # for a much faster source of data

pixels = neopixel.NeoPixel(board.NEOPIXEL, 1)          # for RP2040's LED display
```

# Q.3.2: Firefly Visualization
In this section, we used APDS9960 color sensor to track the brightness reading of firefly flashing, and then use RP2040's LED to simutaneously display the flashing. when the firefly goes bright, the LED should get bright, and the LED should get dim when the firefly goes dim. Then the board would flash in sync with the firefly in the video.

### Basic Logic

### Result
![]()

# Q.4.4 Keyboard Visualization
### result
![]()
