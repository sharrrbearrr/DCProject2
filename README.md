# DCProject2
This project provides a Mathworks Simulink library that controls a Roomba2, and includes a failsafe that is triggered when there may be potential overheating.

In the attached files you may find the library .slx file. Below is a description of how to utilize this Library


# Wifi Initialization

https://user-images.githubusercontent.com/31410952/32416495-f161c70e-c217-11e7-8684-5ffa5b2e109a.png

This block activates the function that initializes the wifi, allowing the user/Simulink to communicate with the serially communicate with the Roomba.

All blocks following this function require the output from this block as in input, in order to function properly.

# IR Sensors

https://user-images.githubusercontent.com/31410952/32416494-f1584f26-c217-11e7-961c-6b86f4c35fa4.png

This block uses the wifi connection to pull readings from the Roomba's 6 onboard IR sensors. A value of one indicates and obstacle and a value of zero indicates no obstacle.

The output from this block is taken as an input into the Wheel Control block. Following the block logic, the Roomba avoids obstacles if IR sensors detect an obstacle (logic value 1).

# Temperature Block
The temperature block is the final input for the Wheel Control Block, acting as the parameter for the temperature failsafe programmed into the Wheel Control Logic.

# NOTE
1. IR Sensors may not detect darker color obstacles (black) but does detect lighter obstacles (white) very well. This is because black absorbs light and White reflects it.

2. The temperature failsafe is set to 15 degrees Celcius. This temperature is adjustable in the Wheel Control block
