SmartRelayRemote
===========

This project used one project "RelayRemote" from Shane Tully (shane@shanetully.com)

An Arduino relay control server and Android client and OpenWrt client for control from your OpenWRT Router.
It is nice basis for your OpenSource SmartHome project. 

We use for our project only OpenSource Projects :

* Arduino
* Android
* OpenWrt

## About
RelayRemote is an Arduino-based server for turing off and on electrical relays, which turn on/off devices run from a standard 220V AC circuit. The project inclues 3 clients, an Android application and a C client for control from Linux systems and OpenWrt client for control from your OpenWRT Router.

The Android app supports multiple relay servers, relay groups, homescreen widgets, and NFC (near field communication) tags.

A demo video and brief description of how it works is available at: http://shanetully.com/2012/12/controlling-a-relay-via-an-arduino-from-an-android-client-with-nfc/


## Hardware
RelayRemote was built and tested on an Arduino Uno with the Arduino Ethernet Shield for networking capabilities. A PowerSwitch Tail II is the recommended relay.

* Arduino Uno: http://www.arduino.cc/en/Main/arduinoBoardUno
* Arduino Ethernet Shield: http://www.arduino.cc/en/Main/ArduinoEthernetShield
* Arduino Relais Shield:
* TP-Link TL-WR1043N: http://wiki.openwrt.org/toh/tp-link/tl-wr1043nd


## Usage
### Setting up the hardware
1. Connect the Arduino ethernet shield to the Arduino by placing the ethernet shield on top of the Arduino
2. Connect a wire from the postivive terminal of the relay to a pin between 2 and 9 (inclusive) on the Arduino. Keep note of the pin you choose. Multiple relays can be connected to the same Arduino by connecting them to different pins.
3. Connect a wire from the negative terminal of the relay to a ground pin on the Arduino
4. Connect the Arduino to your network

### Installing the software
1. Change the network settings (IP, MAC, netmask, and gateway) for the Arduino by editing the server sketch (relay.pde) in the arduino folder of this repo. The lines needing changes are near the top of the file and are marked by a comment.
2. Use the Arduino software (http://arduino.cc/en/main/software) to compile and load the server sketch (relay.pde) in the arduino folder of this repo to the Arduino.
3. Repeat steps 1 and 2 for each Arduino you're setting up
4. Install the Android SDK (http://developer.android.com/sdk/index.html).
5. Either install (using the Android SDK) the pre-built APK in the android folder of this repo or import the Eclipse project in the android folder of this repo into Eclipse and use Eclipse to build and install the application to an Android device.
6. If desired, build the C client in the c_client folder of this repo on a Linux system by running `make` in a terminal.

### Using the Android app
1. After opening the Android app, relays must be added.
2. After adding relays, they can be added to a group, a widget can be placed on the homescreen, or an NFC tag can be created to turn the relays on/off (if the device supports NFC)

### Using the C client
1. The C client is fairly straightforward. Run it with `--help` for more info.

### Note
The default port is 2424. Don't forget to add rules to allow communcation on this port on any firewalls or gateways between the client and the server.

## License
Copyright (C) 2012 Shane Tully , 2014 Key Night

This program is free software: you can redistribute it and/or modify
it under the terms of the GNU Lesser General Public License as published by
the Free Software Foundation, either version 3 of the License, or
(at your option) any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU Lesser General Public License for more details.

You should have received a copy of the GNU Lesser General Public License
along with this program.  If not, see <http://www.gnu.org/licenses/>.
