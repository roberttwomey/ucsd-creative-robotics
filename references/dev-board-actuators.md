
# Dev Board Actuators
Making things move. 

## Servo Motor
Rotational motion 0-180 degrees.

Another use of Pulse Width Modulation is driving the position of a servo motor. 

### Servo Sweep

- Install the Servo library: 
  - **Tools** -> **Manage Libraries**: 
    - <img width="300" alt="image" src="https://user-images.githubusercontent.com/1598545/199737681-24316f67-162c-4575-b1e5-931186a644c5.png"> 
  - Search for **Servo**. Click **Install**:
    - <img width="400" alt="image" src="https://user-images.githubusercontent.com/1598545/199737612-735b282d-016f-4162-897a-6d06e2802555.png">
  - Select the "Sweep" example: 
    - <img width="400" alt="image" src="https://user-images.githubusercontent.com/1598545/199741588-8e8a7d49-9f1a-4bff-a5db-9fd8c0d67384.png">

![image](https://user-images.githubusercontent.com/1598545/140386249-6cd37d02-87af-4730-b97e-e04a0f0afb11.png)

![Image](https://www.arduino.cc/wiki/static/dcca996e7af6025b856c4907c3ffa235/01e7c/sweep_schem.png)

[https://www.arduino.cc/en/Tutorial/LibraryExamples/Sweep](https://www.arduino.cc/en/Tutorial/LibraryExamples/Sweep)

- How to read a schematic
- Pulse Width Modulation
  - (`analogWrite()`!)
  - more on PWM [Secrets of Arduino PWM](https://www.arduino.cc/en/Tutorial/SecretsOfArduinoPWM)

### Servo Knob
A knob is a kind of simple "sensor" to drive the servo motion.

- Under **Examples** -> **Servo**, select the **Knob** example: 
  - <img width="300" alt="image" src="https://user-images.githubusercontent.com/1598545/199742032-4d5e6b1f-d340-47ff-93bb-e52343f48ed6.png">

![Image](https://www.arduino.cc/wiki/static/32db11499efe2d9c9ee451f7996e42a2/e85cb/knob_bb.png)

![Image](https://www.arduino.cc/wiki/static/b0be5a84f8d4dd59d63cf0c102102fa6/b06ae/knob_schem.png)

- Reading the schematic.
- Use the servo to control two knobs. 

## DC Motors
Continous forward/backward motion controlled with PWM outputs. Including geared DC motors, which are a special instance of the above with slower rotation rate. 
[TK]

### Geared DC Motor
[TK]

## Solenoid
Push (or pull) linear potion. Digital (on/off).
[TK]

## Stepper Motor
Very precise rotational motion (200 steps/rotation, typically), controlled with digital outputs.
[TK]

## Capacitive Touch Sensing
[TK]

# References
[TK]