# Bluetooth with the Dev Board

- [What is Bluetooth](#what-is-bluetooth)
- Hands-On  
  - [ESP32 Bluetooth](#esp32s3-bluetooth)
  - [BLE Scanner App](#ble-scanner-app)
  - [BLE LED](#ble-led)
  - [BLE button](#ble-button)

# What is Bluetooth


Talk through what Bluetooth Low Energy (BLE) is, and how it compares/differs from serial, WiFi, and other ways of connecting. 

# ESP32S3 Bluetooth

## BLE Scanner App

nRF Connect is a good one for iOS, Anrdoid, and other OSes.

- search in your app store
- or download for computer [https://www.nordicsemi.com/Products/Development-tools/nRF-Connect-for-Desktop](https://www.nordicsemi.com/Products/Development-tools/nRF-Connect-for-Desktop)

## BLE LED

Control the onboard LED1 or LED2 using a BLE characteristic. 

__1. Compile and upload arduino code__

[ble-led.zip](../assets/ble-led.zip)

You can keep the serial port open to see what is happening.

Be sure to change the device name to be something special to you! (And so you don't conflict with your classmates)

__1. Control with BLE scanner__

- Use nrF Connect or similar to connect to your device. 
- Select the service. 
- Write a value of 0 or 1 to turn the LED on and off.

__2. Control with p5js__

Use a p5js app to connect to and control the LED.

- Open the sketch: [https://editor.p5js.org/robert.twomey/sketches/aXwz43amQ](https://editor.p5js.org/robert.twomey/sketches/aXwz43amQ)
- Reset your ESP32 (RST button on upper right). 
  - (you can follow along in your serial monitor to see what is happening)
- In the p5 sketch click "Connect", select and "Pair" to your device. 
- Write a value of 0 or 1 to turn the LED on and Off.

__3. Activity__
- Wire up and control an external LED instead of the internal LED.
- Setup a number of external LEDs (3) and turn them on by number. i.e. 0 all off, 1 on, 2 on, 3 on.
- Try to control a buzzer or something similar. 

## BLE Button

Use the onboard switch (**SW1**) to control an on-screen sketch. 

__1. Compile and upload arduino code__

[ble-button.zip](../assets/ble-button.zip)

You can keep the serial port open to see what is happening.

Be sure to change the device name to be something special to you! (And so you don't conflict with your classmates)

__1. Debug with BLE scanner__

- Use nrF Connect or similar to connect to your device. 
- Select the service. 
- View the value of 0 or 1 as you press the button.

__2. Control with p5js__

Use a p5js app to connect and read the unboard switch.

- Open the sketch: [https://editor.p5js.org/robert.twomey/sketches/8wQxLraNL](https://editor.p5js.org/robert.twomey/sketches/8wQxLraNL)
- Reset your ESP32 (RST button on upper right). 
  - (you can follow along in your serial monitor to see what is happening)
- In the p5 sketch click "Connect", select and "Pair" to your device. 
- Press the button on board (**SW1**) and watch the sketch change color. 

__3. Activity__
- Change the p5 code to do something more interesting than set the background color. 
- Wire up a potentiometer instead of a button to the ESP32, and change the arduino code to ```analogRead()``` and publish the value.
  - Change the p5 code to change the color of the sketch continously as you turn the knob.
- Rewrite the p5 code to do something more interesting than change a background color (rotate an image, adjust the volume on audio playback, rotate a 3d object, something else)

## Homework

- Reading and Discussion: [1999 A.D.](https://canvas.ucsd.edu/courses/60624/discussion_topics/837644) (DUE 11/6 for discussion)
- [HW 3 Remote Control](../exercises/hw3.md) (DUE 11/6 and in class presentation)

# References
[TK]