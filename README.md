# DIY-ESP32C3-Mini

Developing a DIY simple ESP32C3 using KiCad. Below I will outline my development journey as I develop the board. All the files will be provided at a later date once I complete this project.

Below is a detailed description of the componets used.

## Components used

1. USB C receptable 2.0 16p

- I personally choosed this board as this is a mini evaluation board then we don't require high speed data tranfers.

### Pins of this USB C connector

1. VBUS
    - This is the main power pin. In a standard USB connection it provides 5V.
    - This is the pin that will power our entire board.
2. CC1 & CC2
    - These are the configuration channel pins.
    - They are used for cable orientation detection and to negotiate power roles between devices.
    - Since USB C is reversible only one of the CC pins will be active depending on how the cable is inserted.
    - In this project we will use pull down resistors on these pins to indicate that our board is a power sync, meaning it wants to recieve power.
3. D- & D+
    - These are the USB 2.0 data lines.
    - They are used for communication between the host and the device.
    - If we implement USB data functionality these lines will connect to the microcontroller or to a USB to UR converter.
4. SBU1 & SBU2
    - They are sidebands use pins.
    - In simple USB C 2.0 designs like this they are usually not used and can be left unconnnected. They are more relevant in advanced USB C applications.
5. GND
    - These are the ground pins, they provide the return path for current and are critical for stable operation. All power and signal references rely on solid ground connection.
6. Shield
    - This connects to the metal shell of the USB connector.
    - It is typically tied to a ground either direct or through a resistor or capacitor network to improve electromagnetic compactibilty and reduce noise.
