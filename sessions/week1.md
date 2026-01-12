# Week 1 - Introduction, Overview, Hands-On

<!--<img src="https://github.com/user-attachments/assets/59ed6228-bea4-4194-8df9-15d4fdd3acbd" width=100%>

Robert Twomey, [Rover on VROOM](https://roberttwomey.com/rover-on-vroom/) (2019)-->

## Agenda
- Introductions
- Review Syllabus
  - (basics/outcomes, assignments, policies, schedule, tools/platforms)
- My approach to Electronic Technologies for Art
- Arduino Review Activities
  - Digital Input/Output; Analog Input/Output; Meaningful Signal, Meaningful Interaction.
  - Sign up for discord ([see canvas Week 1](https://canvas.ucsd.edu/courses/60624/discussion_topics/823519))
- ~ break ~
- Review and Hands-On: electronics assessment/what do you remember from 147a?
- Assign Homework

## Arduino Assessment / Review
Arduino 1: Intro and Digital Input/Output. ([slides](https://docs.google.com/presentation/d/1TOZF61UpWHaOlSmP1OJVyTXk8dMxqG71KRXWlUs-ZCo/edit?usp=drive_link))

### Code Basics
- `setup()` - runs once, like `setup()` in processing. [reference](https://www.arduino.cc/reference/en/language/structure/sketch/setup/)
- `loop()` - runs repeatedly, like `draw()` in processing. [reference](https://www.arduino.cc/reference/en/language/structure/sketch/loop/)
- `pinMode()` - tell the arduino whether to use a pin as an input, an output, or the other things it can do (more later on that). [reference](https://www.arduino.cc/reference/en/language/functions/digital-io/pinmode/)
- `digitalRead()` - reads the input on a digital pin. [reference](https://www.arduino.cc/reference/en/language/functions/digital-io/digitalread/)
- `digitalWrite()` - sets the output on a digital pin. [reference](https://www.arduino.cc/reference/en/language/functions/digital-io/digitalwrite/)

### Blink

The hello world of arduino. By default, the arduino will blink a built-in LED ("L"), next to the RX, TX, and POW lights.
- Schematic:
  - (no schematic needed, we will use the built in LED on the Arduino nano)
  - The built-in LED is attached internally to pin 13 on the arduino `LED_BUILTIN`. (see [constants](https://www.arduino.cc/reference/en/language/variables/constants/constants) in reference)
- Code: 
  - **File->Examples->01.Basics->Blink.ino**
- Behavior:
  - we will see the LED blinkin on for 1000 milliseconds, and then off for 1000 milliseconds.

### Digital Output

![Image](https://www.arduino.cc/wiki/static/52c238dba09c2e40b69e0612ff02ef0f/29007/circuit.png)

[https://www.arduino.cc/en/Tutorial/BuiltInExamples/Blink](https://www.arduino.cc/en/Tutorial/BuiltInExamples/Blink)

Let's wire up our own LED attached to a different pin.
- Schematic
  - wire up an LED and resistor to a different pin on the arduino, say `D2`. 
  - we need one resistor (10k)
  - one LED (red?)
- Code
  - Make a copy of your Blink code from above. 
  - we need to change the line in `setup()` where the `pinMode()` is declared. Change `LED_BUILTIN` to the 

TODO: 
- Change the `delay()`. Experiment with how the delays change the blinking rate and duration.
- Add more blinks. Can you spell out morse code?

### Digital Input

![Image](https://www.arduino.cc/wiki/static/73702ee121860fa04c7f6db5bc77183b/29007/circuit.png)

[https://www.arduino.cc/en/Tutorial/BuiltInExamples/Button](https://www.arduino.cc/en/Tutorial/BuiltInExamples/Button)

- TODO
  - modify to be a toggle (add a variable that keeps track of on/off)
  - use the button input to call a function

## Homework

- Fill out the week 1 survey: (check canvas) (DUE End of day today Oct 2)
  - (basic info, some questions about interest/enthusiasms, choosing office hours, anything else you wish to share)
- [Create a Digital Sketchbook](https://canvas.ucsd.edu/courses/60624/assignments/863853) (DUE Oct 9)
- Discussion: [Reading: Minds and Brains](https://canvas.ucsd.edu/courses/60624/assignments/863868) (DUE Oct 9)
- Exercise 1: [Meaningful Signal](../exercises/hw1) (DUE Oct 9)

## References

### Arduino Reference

<img src="https://user-images.githubusercontent.com/1598545/137305695-2d5a0bbc-37c9-43ad-9d26-435b2782f24b.png" width=400>

__Breadboard__

<img src="https://user-images.githubusercontent.com/1598545/137305908-31ef631b-e085-44bf-b058-f9cb3bc7a368.png" width=400>

__LED__

![image](https://user-images.githubusercontent.com/1598545/137358952-3ea6684c-6ea3-4efb-8c69-6b9a4b2427d2.png)

__Resistor__

![image](https://user-images.githubusercontent.com/1598545/139250236-3dfac097-bcbe-4dad-920f-a23bd82b32a9.png)

![image](https://user-images.githubusercontent.com/1598545/139250292-c751c276-03f8-4714-a918-3b29955106b5.png)

from Sparkfun ([link](https://learn.sparkfun.com/tutorials/voltage-current-resistance-and-ohms-law/resistance))
