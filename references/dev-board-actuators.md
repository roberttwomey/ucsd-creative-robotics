# Dev Board Actuators
Making things move. 

- [Servo Sweep](#servo-sweep)
- [Servo Knob](#servo-knob)
- more [TK].

## Servo Motor
Rotational motion 0-180 degrees.

Another use of Pulse Width Modulation is driving the position of a servo motor. 

### Servo Sweep

1. Install the **ESP32Servo** library: 
   - **Tools** -> **Manage Libraries**: 
     - <img width="300" alt="image" src="https://user-images.githubusercontent.com/1598545/199737681-24316f67-162c-4575-b1e5-931186a644c5.png"> 
   - Search for **ESP32Servo**. Click **Install**:
    - <img width="400" alt="image" src="assets/esp32-servo.png">
2. Under **Examples** -> **ESP32Servo**, select the **Sweep** example: 
   - <img width="400" alt="image" src="assets/esp32-servo-sweep.png">
   - Make sure that your servo is connected to the pins used in the example code. Or change the pins in the code to match your setup.
   - ![alt text](assets/esp32-servo-pwm-pins.png)
4. Wire up the servo:
   - BLACK/BROWN -> Ground
   - RED/YELLOW -> +5V
   - ORANGE -> your `servoPin`.
3. Compile and run the example.

### Servo Knob

We are going to use the potentiometer knob as an input device. You can think of a knob as a kind of simple "sensor" to drive the servo motion.

- Under **Examples** -> **ESP32Servo**, select the **Knob** example: 
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

# References
[TK]

### ESP32-ESP32S Analog Write

#### Easing
![gifs of easing](https://user-images.githubusercontent.com/63488701/227943891-87cb7555-fe56-4064-a83a-38b99ad58e1d.gif)

[Servo Easing](https://github.com/Dlloydev/ESP32-ESP32S2-AnalogWrite?tab=readme-ov-file#servo-easing)


