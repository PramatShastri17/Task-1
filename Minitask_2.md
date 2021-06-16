# TapLock - Smart Bicycle Lock
## Problem Statement: 
Building a device that uses the power of machine learning to read tapping pattern (gestures) to lock/unlock a bicycle.
## Ideation:
### Main Path:
Tap Pattern detection --> Accelerometer Output -->  Microcontroller --> Edge Impulse --> Tap Recognision -->
- **First Path:** *Microcontroller --> Bluetooth Module --> Android Mobile Device*
- **Second Path:** *Microcontroller --> Trigger Locking Mechanism*
### Project Pipeline Breakdown:
|Part of the Pipeline | Feasibility | Advantages | Disadvantages |
| --- | --- | --- | --- |
|Arduino/Microcontroller|Hard to handle. Prior Experience and Skills Required. Sligthly Expensive| Has Embedded sensors & AI. Compact Design. Built-in Libraries. Power efficient | Difficult for Beginners to understand and code|
|Tap Detection: IMU|Embedded sensor. Capable of magnetic, accelerometer and gyroscope sensing | Access functions through built-in library. Reliable and Accurate| Challenging to code|
|Bluetooth Transreceiver|Com chipset on microcontroller can be both a BLE and Bluetooth® client and host device| No External module/attachment required. Access functions through built-in library| Short range communication. Connection not very secure |
|Smart Phone App|Hard to design and code an app|Easy to operate. Very versatile and can have many features| Not secure - can be Hacked. Not very easy to modify or update|
|Edge Impulse - ML|Microcontroller Built-in support; Leading development platform for embedded machine learning| User-Friendly Platform; Multiple Features - Data Training, Data Accuracy; Embedded TinyML|ML concepts are difficult to master. Challenging to code without prior knowledge or training|  

The problem solution is elegant and compact. But, improments can be made to tackle the issues. \
The  Arduino Nano 33 BLE Sense used is very powerful and versatile due to is many embedded sensors, which eleminated the need to separately attach required modules to the board externally. Also, it is capable of handle AI and ML codes with easy.\
*As per the project doc*, it doesn't implement the locking mechanism yet. It's just a proof of concept.\


# Wireless Electronic Notice Board using GSM
## Problem Statement: 
Designing a Wireless Electronic Notice Board that displays the data sent from the mobile as SMS on the LCD using GSM technology. 
## Ideation:
Message sent (via SMS) --> Mobile Device --> GSM Module --> Microcontroller --> LCD Display
### Project Pipeline Breakdown:
