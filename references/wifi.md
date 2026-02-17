# Wifi on the Dev Board

- [ESP32 Wifi Capabilities](#esp32-wifi-capabilities)
- [Wireless AP - Captive Button](#wireless-ap-captive-button)

# ESP32 WiFi Capabilities

The ESP32-S3 has integrated 2.4 GHz Wi-Fi (802.11 b/g/n) and Bluetooth 5 (LE) with mesh support. The wifi can operate in several modes:

1. **Station Mode (STA)**: The ESP32 connects to an existing WiFi network (like your home router), just like your phone or laptop.
2. **Access Point Mode (SoftAP)**: The ESP32 creates its own WiFi network that other devices (phones, laptops) can connect to. 
3. **Station + SoftAP**: It can do both simultaneously!
4. **Promiscuous Mode**: It can monitor WiFi traffic in the air (sniffer).

It supports WPA/WPA2/WPA3 security protocols and has long-range (LR) capabilities. 

# Wireless AP - Captive Button

This program creates a wireless access point (AP) and a captive portal that redirects to a web page. That webpage (served from the ESP32) allows you to control the onboard LED1. 

```cpp
/*
 * ESP32-S3 WiFi Access Point Captive Portal Logic
 *
 * This example:
 * 1. Creates a WiFi Access Point named "ESP32-Control".
 * 2. Starts a DNS Server to redirect all domain requests to the ESP32 IP,
 * acting as a captive portal.
 * 3. Serves a simple web page to control an LED (turn ON/OFF).
 *
 * How to use:
 * 1. Upload the code to your ESP32-S3.
 * 2. Connect your phone or laptop to the WiFi network "ESP32-Control".
 * 3. Most devices will automatically open the captive portal (login page).
 *    If not, open a browser and go to http://1.1.1.1 or any other http://
 * address.
 */

#include <DNSServer.h>
#include <WebServer.h>
#include <WiFi.h>

// Define the LED pin
// If your board has a built-in LED, LED_BUILTIN is usually defined.
// If not, change this to the GPIO pin where your LED is connected.
const byte LED1 = 17;

const byte DNS_PORT = 53;
IPAddress apIP(192, 168, 4, 1);
DNSServer dnsServer;
WebServer server(80);

const char *ssid = "ESP32-Control";
// No password for open network, or add a second argument to softAP for WPA2
// const char* password = "password123";

// HTML content for the control page
String getPage() {
  String html = "<!DOCTYPE html><html><head>";
  html += "<meta name=\"viewport\" content=\"width=device-width, "
          "initial-scale=1\">";
  html += "<style>";
  html +=
      "body { font-family: sans-serif; text-align: center; margin-top: 50px; }";
  html += "h1 { color: #333; }";
  html +=
      ".button { display: inline-block; padding: 15px 25px; font-size: 24px; ";
  html += "cursor: pointer; text-align: center; text-decoration: none; "
          "outline: none; ";
  html += "color: #fff; background-color: #4CAF50; border: none; "
          "border-radius: 15px; ";
  html += "box-shadow: 0 9px #999; margin: 10px; }";
  html += ".button:hover {background-color: #3e8e41}";
  html += ".button:active { background-color: #3e8e41; box-shadow: 0 5px #666; "
          "transform: translateY(4px); }";
  html += ".off { background-color: #f44336; }";
  html += ".off:hover { background-color: #d32f2f; }";
  html += ".off:active { background-color: #d32f2f; }";
  html += "</style></head><body>";
  html += "<h1>ESP32 Control</h1>";
  html += "<p>Turn the LED on or off:</p>";

  if (digitalRead(LED_BUILTIN) == HIGH) {
    html += "<p>Status: <strong>ON</strong></p>";
  } else {
    html += "<p>Status: <strong>OFF</strong></p>";
  }

  html += "<a href=\"/on\"><button class=\"button\">ON</button></a>";
  html += "<a href=\"/off\"><button class=\"button off\">OFF</button></a>";
  html += "</body></html>";
  return html;
}

void handleRoot() { server.send(200, "text/html", getPage()); }

void handleOn() {
  digitalWrite(LED1, HIGH);
  server.send(200, "text/html", getPage()); // Reload page to update status
  Serial.println("LED ON");
}

void handleOff() {
  digitalWrite(LED1, LOW);
  server.send(200, "text/html", getPage()); // Reload page to update status
  Serial.println("LED OFF");
}

void handleNotFound() {
  // Redirect any unknown request to the root page (captive portal behavior)
  server.sendHeader("Location", String("http://") + apIP.toString(), true);
  server.send(302, "text/plain", "");
}

void setup() {
  Serial.begin(115200);

  // Initialize LED pin
  pinMode(LED1, OUTPUT);
  digitalWrite(LED1, LOW); // Start off

  // Configure Access Point
  WiFi.mode(WIFI_AP);
  WiFi.softAPConfig(apIP, apIP, IPAddress(255, 255, 255, 0));
  WiFi.softAP(ssid); // Open network

  // For WPA2 security, use: WiFi.softAP(ssid, "your_password");

  Serial.print("AP Created with IP: ");
  Serial.println(WiFi.softAPIP());

  // Setup DNS Server for Captive Portal
  // Redirect all DNS requests to the AP IP
  dnsServer.start(DNS_PORT, "*", apIP);

  // Setup Web Server Routes
  server.on("/", handleRoot);
  server.on("/on", handleOn);
  server.on("/off", handleOff);

  // Android captive portal check
  server.on("/generate_204", handleRoot);

  // Microsoft captive portal check
  server.on("/ncsi.txt", handleRoot);

  // Apple captive portal check (catch-all is usually enough, but being explicit
  // helps)
  server.on("/hotspot-detect.html", handleRoot);

  server.onNotFound(handleNotFound);

  server.begin();
  Serial.println("HTTP server started");
}

void loop() {
  dnsServer.processNextRequest();
  server.handleClient();
}
```

download: [esp32-wifi-captive-button.ino](assets/esp32-wifi-ap-captive.zip)

__0. Modify the Network Name__

- In the code, change the line that says ```const char *ssid = "ESP32-Control";```, renaming the network from `ESP32-Control` to a readily identifiable name of your choice


__1. Compile and upload the program__

- Select ESP32S3 Dev Module for board type, and select your USB port (as usual)

__2. Reboot the Dev board__

- Open the Serial Monitor (115200 baud)) to view program events as they happen on the server side (ESP32 dev board)

__3. Connect to the Wireless Network__

- Look for the AP name (`ESP32-Control`) in your phone (or laptops) available networks. 
- Connect to the network.
- Ideally, your phone will move you to the captive portal login page, which presents you with LED "ON" and "OFF" buttons. 
- If not, Open a web browser and go to http://1.1.1.1 or any other http:// address.

__4. Control the LED__

- Use the ON and OFF buttons through the web form to control the onboard LED.

__5. Extensions__

- Modify this code to accomplish more advanced tasks, control a servo, trigger some other actuator. 
- Modify this code to display sensor readings (ultrasound) or switch values on the web page. 
- Other ideas? 

# References
- ESP32S3 Wireless Reference: [https://docs.espressif.com/projects/esp-idf/en/v5.5.2/esp32/api-reference/network/esp_wifi.html](https://docs.espressif.com/projects/esp-idf/en/v5.5.2/esp32/api-reference/network/esp_wifi.html)