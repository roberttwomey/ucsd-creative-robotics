# Bluetooth with the Dev Board

- [What is Bluetooth](#what-is-bluetooth)
- Hands-On  
  - [ESP32 Bluetooth](#esp32s3-bluetooth)
  - [BLE Scanner App](#ble-scanner-app)
    - detect if user is nearby (RSSI and MAC/identifier)
  - [BLE LED](#ble-led)
  - [BLE button](#ble-button)

# What is Bluetooth?

Talk through what Bluetooth Low Energy (BLE) is, and how it compares/differs from serial, WiFi, and other ways of connecting. 

# ESP32S3 Bluetooth

## BLE Scanner App

nRF Connect is a good one for iOS, Anrdoid, and other OSes.

- search in your app store
- or download for computer [https://www.nordicsemi.com/Products/Development-tools/nRF-Connect-for-Desktop](https://www.nordicsemi.com/Products/Development-tools/nRF-Connect-for-Desktop)

## BLE LED

Control the onboard LED1 or LED2 using a BLE characteristic. 

__1. Compile and upload arduino code__

```C++
/* 
Electronic Technologies for Art II
et4a.roberttwomey.com | rtwomey@ucsd.edu

ble-led

Controls LED1 with BLE service. 
Use a BLE scanner (such as nRF Connect) or
this p5js sketch: https://editor.p5js.org/robert.twomey/sketches/aXwz43amQ

Adapted from ESP32 Examples -> BLE -> Write
And NYU ITP https://itpnyu.github.io/p5ble-website/docs/write-one-char-callback

*/

#include <BLEDevice.h>
#include <BLEUtils.h>
#include <BLEServer.h>

// See the following for generating UUIDs:
// https://www.uuidgenerator.net/

#define SERVICE_UUID        "4fafc201-1fb5-459e-8fcc-c5c9c331914b"
#define CHARACTERISTIC_UUID "beb5483e-36e1-4688-b7f5-ea07361b26a8"

const int ledPin = 17;

class MyCallbacks : public BLECharacteristicCallbacks {
  void onWrite(BLECharacteristic *pCharacteristic) {
    String value = pCharacteristic->getValue();

    if (value.length() > 0) {
      Serial.println("*********");
      Serial.print("New value: ");
      for (int i = 0; i < value.length(); i++) {
        Serial.print(value[i]);
      }

        if (value != 0) {   // any value other than 0
          Serial.println("\nLED on\n");
          digitalWrite(ledPin, HIGH);         // will turn the LED on
        } else {                              // a 0 value
          Serial.println("\nLED off\n");
          digitalWrite(ledPin, LOW);          // will turn the LED off
        }

      Serial.println();
      Serial.println("*********");
    }
  }
};

void setup() {
  pinMode(ledPin, OUTPUT);

  Serial.begin(115200);

  Serial.println("1- Download and install an BLE scanner app in your phone (nRF)");
  Serial.println("2- Scan for BLE devices in the app");
  Serial.println("3- Connect to MyESP32");
  Serial.println("4- Go to CUSTOM CHARACTERISTIC in CUSTOM SERVICE and write something");
  Serial.println("5- See the magic =)");

  BLEDevice::init("MyESP32"); // change this name
  BLEServer *pServer = BLEDevice::createServer();

  BLEService *pService = pServer->createService(SERVICE_UUID);

  BLECharacteristic *pCharacteristic =
    pService->createCharacteristic(CHARACTERISTIC_UUID, BLECharacteristic::PROPERTY_READ | BLECharacteristic::PROPERTY_WRITE);

  pCharacteristic->setCallbacks(new MyCallbacks());

  pCharacteristic->setValue("Hello World");
  pService->start();

  BLEAdvertising *pAdvertising = pServer->getAdvertising();
  pAdvertising->addServiceUUID(SERVICE_UUID);
  pAdvertising->setScanResponse(true);
  pAdvertising->setMinPreferred(0x06);  // functions that help with iPhone connections issue
  pAdvertising->setMinPreferred(0x12);
  pAdvertising->start();
}

void loop() {
  // put your main code here, to run repeatedly:
  delay(2000);
}
```
[ble-led.zip](../assets/ble-led.zip)

### Instructions

1. Be sure to change the device name (`BLEDevice::init("MyESP32");`)to be something special to you! (And so you don't conflict with your classmates)

2. Compile and upload the program. 

3. You can keep the serial port open to see what is happening from the dev board side. (Make sure **Tools->USB CDC on Boot** is set to **Enabled**)

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
- Write a value of 0 or 1 to turn the LED `ON` and `OFF`. (technically any non-zero value will turn the LED on)

__3. Activity__
- Wire up and control an external LED instead of the internal LED.
- Setup a number of external LEDs (3) and turn them on by number. i.e. 0 all off, 1 on, 2 on, 3 on.
- Try to control a buzzer or something similar. 

__4. Extension__
- Try to control a servo motor or different device (buzzer, DC motor) instead of the LED output. 
- Try for more complicated messaging on the p5 and arduino side—i.e. more than sending single characters ("0" and "1") to control behaviors. 
- Establish bidirectional control. 

## BLE Button

Use the onboard switch (**SW1**) to control an on-screen sketch. 

__1. Compile and upload arduino code__

```C++
/* 
Electronic Technologies for Art II
et4a.roberttwomey.com | rtwomey@ucsd.edu

ble-button

Reads from builting SW1 (IO12) and publishes to service.
Use a BLE scanner (such as nRF Connect) or
this p5js sketch: https://editor.p5js.org/robert.twomey/sketches/8wQxLraNL

NOTE: change your BLEDevice name from "MyESP32" to something of your own.

Adapted from ESP32 Examples -> BLE -> Server
And NYU ITP https://itpnyu.github.io/p5ble-website/docs/read-one-char-callback

*/

#include <BLEDevice.h>
#include <BLEUtils.h>
#include <BLEServer.h>

// See the following for generating UUIDs:
// https://www.uuidgenerator.net/

#define SERVICE_UUID        "4fafc201-1fb5-459e-8fcc-c5c9c331914b"
#define BUTTON_CHARACTERISTIC_UUID "19B10012-E8F2-537E-4F6C-D104768A1214"

const int ledPin = 18; // set ledPin to on-board LED2
const int buttonPin = 12; // set buttonPin to BTN1
int sensorPin = A0;    // select the input pin for the potentiometer

// create switch characteristic and allow remote device to read and write
//BLEByteCharacteristic ledCharacteristic("19B10011-E8F2-537E-4F6C-D104768A1214", BLERead | BLEWrite);
// create button characteristic and allow remote device to get notifications
// BLEIntCharacteristic buttonCharacteristic("19B10012-E8F2-537E-4F6C-D104768A1214", BLERead | BLENotify);

BLECharacteristic *pCharacteristic;

void setup() {
  pinMode(ledPin, OUTPUT); // use the LED as an output
  pinMode(buttonPin, INPUT); // use button pin as an input

  Serial.begin(115200);
  Serial.println("Starting BLE work!");

  BLEDevice::init("MyESP32"); // change this name to a custom name
  BLEServer *pServer = BLEDevice::createServer();
  BLEService *pService = pServer->createService(SERVICE_UUID);
  pCharacteristic =
    pService->createCharacteristic(BUTTON_CHARACTERISTIC_UUID, BLECharacteristic::PROPERTY_READ | BLECharacteristic::PROPERTY_NOTIFY);
    // pService->createCharacteristic(CHARACTERISTIC_UUID, BLECharacteristic::PROPERTY_READ | BLECharacteristic::PROPERTY_WRITE);

  char txString[8];
  dtostrf(0, 1, 2, txString);

  pCharacteristic->setValue(txString); // set value to 0
  pService->start();
  // BLEAdvertising *pAdvertising = pServer->getAdvertising();  // this still is working for backward compatibility
  BLEAdvertising *pAdvertising = BLEDevice::getAdvertising();
  pAdvertising->addServiceUUID(SERVICE_UUID);
  pAdvertising->setScanResponse(true);
  pAdvertising->setMinPreferred(0x06);  // functions that help with iPhone connections issue
  pAdvertising->setMinPreferred(0x12);
  BLEDevice::startAdvertising();
  Serial.println("Characteristic defined! Now you can read it in your phone!");
}

void loop() {
  // put your main code here, to run repeatedly:
  delay(2000);

  // read the value from an analog sensor:
  // int sensorValue = analogRead(sensorPin);
  // char txString[8];
  // dtostrf(sensorValue/4, 1, 2, txString);

  // read value from digital button
  // char txString[8];
  // dtostrf(digitalRead(buttonPin), 1, 2, txString);
  // Serial.println(txString);
  // publish to characteristic
  // pCharacteristic->setValue(txString);

  int btn = digitalRead(buttonPin);

  Serial.println(btn);
  pCharacteristic->setValue(btn);

}
```

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

__4. Extension__
- Read more complicated sensor input (ultrasound, PIR, thermistor) rather than switch or potentiometer.
- Establish bidirectional communication and control. 

# References
- p5ble: [https://itpnyu.github.io/p5ble-website/docs/](https://itpnyu.github.io/p5ble-website/docs/)