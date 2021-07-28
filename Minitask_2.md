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
*As per the project doc*, it doesn't implement the locking mechanism yet. It's just a proof of concept.

### Choosing a Pipeline:
#### Bluetooth:
I felt that having a bluetooth only device will limit the functionality of the project. Bluetooth has a low ranges and is usually used for PANs. 
This means that if we park our cycle, say at a metro station, and travel out of range of the bluetooth, we will not be able to track the cycle's status.

**Solution:**
We can use a **Nb-IoT** (Narrowband IoT) module with an embedded SIM for *real-time tracking*. 
* It is more secure and reliable.
* It has longer range than BLE and has more penetration.
* It is power efficient.
* It enables more accurate mobility tracking (GPS features).

### Prototyping:
A holder for the board along with a attachment bracket including a custom locking mechanism must we fabricated to properly deploy the project. 
Also, providing the casing/holder with water resistance will be great to ensure that we can use this lock even in the rains.


# Wireless Electronic Notice Board using GSM
## Problem Statement: 
Designing a Wireless Electronic Notice Board that displays the data sent from the mobile as SMS on the LCD using GSM technology. 
## Ideation:
Message sent (via SMS) --> Mobile Device --> GSM Module --> Microcontroller --> LCD Display
### Project Pipeline Breakdown:
|Part of the Pipeline | Feasibility | Advantages | Disadvantages |
| --- | --- | --- | --- |
|Microcontroller|Slightly difficult to handle. Prior knowledge is a must.|Very Cheap. Compact and power efficient. Makes project portable|Have to learn C and assembly languages.  3rd Part IDE and programmer need to compile and load the code. |
|GSM Module|Not very easy to use. Must learn from the basics | Long range, reliable and secure communication| Need to have prior knowledge of AT commands. Needs a  SIM card|
|LCD Display|Difficult for a beginner to code|It is energy efficient. In the long-term, cost effective.|Requires frequent adjustments throughout usage. Limited viewing angles.|
|Mobile Device|Easy to obtain and use|Nowadays, everybody has one, so no need to buy special hardware.|Limited usability. Highly dependent on the schemes of a service provider|

### Choosing a Pipeline:
> **GSM Module**: From the above table it is clear that this module has it short comings. So, we can instead convert this into an IoT project by interfacing the 8051 microcontroller with a NodeMCU ESP8266 Module. This will make it more dynamic and flexible stil maintaining the long range communication advantage of a GSM Module.\
> Even thought we find that GSM communication can be secure, anyone who get access to the SIM number in the module can take control. If implemented on a large scale this can be an issue. So, by making it IoT-based, it can also help address the security issues with GSM communication.\
> Also, implementing as IoT can enable us to modify the messages by adding elements like emojis or displaying tabulated data, etc.

### Prototyping:
In this phase, the project is implemented on a larger scale with a large LCD notice board panel. Some of our initial assumptions can breakdown here. So, to fix such problems we may need to go back to the ideation phase and workout a better implementation.
