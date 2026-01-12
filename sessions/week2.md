# Week 2 - Making Things Move

## Agenda
- Review/Discuss HW1 + Reading
- [Artist(s) of the Day](#artists-of-the-day)
- Tutorial: PWM and Analog Output
  - [Analog output](#analog-output)
- Tutorial: Making things Move
  - [Servo sweep](#servo-sweep)
  - [Servo knob](#servo-knob)
  - [Photoresistor Part 2](#photoresistor-part-2) light responsive motion
- [Homework](#homework)
  - Making Things Move (DUE next Tuesday 10/20)
  - Assign Project 1 - Augmentation (DUE Week 5)

## Artist(s) of the Day

<img width="800" alt="image" src="https://user-images.githubusercontent.com/1598545/199234670-4492adcd-ad5b-4dc7-959e-af737f84db18.png">

Daniel Rozin

- [Wooden Mirror](http://www.smoothware.com/danny/woodenmirror.html)
  - Thousands of servo motors
- Longer video from Wired (2019): [https://www.youtube.com/watch?v=kV8v2GKC8WA](https://www.youtube.com/watch?v=kV8v2GKC8WA)
- Wooden Mirror (2000) in SIGGRAPH Archives: [https://digitalartarchive.siggraph.org/artwork/daniel-rozin-wooden-mirror/](https://digitalartarchive.siggraph.org/artwork/daniel-rozin-wooden-mirror/)
- Danny Rozin [portfolio](https://www.smoothware.com/danny/index.html)

## Analog Input and Output

### Analog Output

Commonly called PWM ([Pulse Width Modulation](https://en.wikipedia.org/wiki/Pulse-width_modulation)).

![Image](https://www.arduino.cc/wiki/static/079b1bab3758603a56c5d98e1f59a88e/29007/circuit.png)

[https://www.arduino.cc/en/Tutorial/BuiltInExamples/Fade](https://www.arduino.cc/en/Tutorial/BuiltInExamples/Fade)

- NOTE: this is a very similar circuit and wiring as [Digital Output](#digital-output) above.
  - the difference is that here we are using `analogWrite()` (reference)
  - and a different pin (one of the PWM capable pins)
- Demo:
  - Show the "duty cycle" on the oscilloscope.
  - Show how a different analog output corresponds to (1) a waveform and (2) a different measured voltage.

- TODO: 
  - modify the speed at which it fades. (hint: change the `delay()`. see [the delay reference](https://www.arduino.cc/reference/en/language/functions/time/delay/))

## Making Things Move

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

https://www.arduino.cc/en/Tutorial/LibraryExamples/Sweep

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

### Photoresistor Part 2
With the photoresistor setup and arduino code from [part 1](#photoresistor-part-1) above:

1. Use [`map()`](https://www.arduino.cc/reference/en/language/functions/math/map/) to scale those analog values to 0 -> 180 degrees (the full range of the servo)
2. Interact with the photoresistor and see the motor move. 
3. Extension: Instead of directly mapping sensor values to servo position, use the sensor values to trigger specific motions. For instance, have if statements that move it to different positions depending on how much light it sees.


## Homework
- Exercise 2: [Making Things Move](../exercises/hw2.md) DUE next wednesday 10/16
- Start ideating for [Project 1](../projects/project1.md)

## References

- Sparkfun Tutorial on [Pulse Width Modulation](https://learn.sparkfun.com/tutorials/pulse-width-modulation/all)