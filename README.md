
# Emma Watson, Delvin Marimo, Muhammed Memon

## Advanced Smart Home Security System
## 10 March 2023


## A summary of the behavior of this code in your system

The main function of our software is to provide an advanced security system to a smart home. From the armBookCodeExamples, example 2 already has code for setting off the alarm if there is things like an over Temperature detection or gas detection inside the house. From this code, we added new behaviours to our system. Basically, when an RFID card is scanned, the code will check if it is the correct tag stored in our system. if the tag is correct, the door to our smart home is opened by rotating a servo motor. When the door is unlocked, a green LED is turned on to indicate that the door is open. In the event that the tag scanned is wrong, a red LED stays on and a buzzer is set off for 10 seconds. When it is at night, an antryway LED light is turned on for visibility near the door.  


## A list of the code modules. For each module give a brief description of what the module does. If the code is a) written from scratch, b) based on textbook code or c) based on code found online

### Modules added

**rfid_door**: this module calls a function from ldr_sensor. It checks to see if the ldr sensor connected to the green LED is reading any values greater than the threshold value. If so, it instructs the servo motor to rotate by calling a function from servo motor module. the module also keeps track of the status of the door(open or close). This is written from scratch following examples from class exercises

**servo_motor**:The module has a function to rotate the servo motor to 145 degrees, delay for 10 seconds and then close the door. 

**ldr_sensor**: This module takes in readings from the three Ldr sensors. one ldr sensor to detect correct RFID tags, another to detect incorrect RFID tags and lastly to turn on/off the entryway LED light. 

**entryway**:  This module calls a function inside ldr sensor that reads the ldr sensor value for turning the entryway light ON when it is dark and OFF when it is dalight. 

**outPiezzo**: If there is an incorrect tag scanned, the ldr sensor value is read and this module sets off the piezzo buzzer to indicate that an incorrect tag has just been scanned

**rgb_led**: This module controls the led lights of an RGB LED. The RGB is set to values that turn completly red and complety green in different functions

**Aduino code**: 


## A list of the hardware components connected to the Nucleo board, and the pins for each component



## A description of the tests you performed on the system, and the results.
To test the entryway LED light, we placed a hand over the LDR sensor to provide some darkness. The entryway LED turned on when a hand was used to cover the ldr sensor and the LED turned off when the hand was removed.

To test the door functionaility, we had 6 different RFID tags all assigned with different strings. Only 2 tags were given the correct strings. we randomly scanned all the six tags and when the door only opened twice when the two correct tags were scanned. The other four times, the buzzer went off. 


## Any other details that will help the reader understand your code
