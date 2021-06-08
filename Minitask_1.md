# Project 1 - Ultrasonic Levitation Machine using Arduino:
Goal - To explore levitation of objects using Interference of Ultrasonic Waves\
Topic - Arduino\
This project deals with building an ultrasonic levitator, capable of levitating small objects, by implementing the concept of standing wave interference using ultrasonic sensors. 
The Arduino is programmed to generate a 40KHz high-frequency oscillation signal for the ultrasonic transducer and this pulse is applied to the input of duel motor driver IC L293D to drive the ultrasonic transducers. 
The pair of ultrasonic transducers (collected from HCSR04 module) are positioned opposite to each other along the same line at a suitable distance apart, to produce standing waves inbetween them. 
When the orientation of the wave is parallel to the pull of gravity, portions of the standing wave have a constant downward pressure and others have constant upward pressure. 
When a small object is carefully positioned inbetween the transducers, it appears to float free of any support.\
This machine is very sensitive as variation is subtle parameters (like positioning of or distance between the sensors) can tamper with the results. Also, it is limited to levitating only small (lighter) objects. 
Designing the transducer with a concave geometry to fit more pairs of ultrasonic sensors (suitably positioning them on the surface) may allow it to lift heavier objects.\
Project [Link](https://www.hackster.io/e_s_c/ultrasonic-levitation-machine-using-arduino-9e3989)

# Project 2 - USB Microphone
Goal -  Creating a USB microphone device.\
Topic - Raspberry Pi\
This project deals with Programming I/O (PIO), Direct Memory Access (DMA), and USB capabilities of the Raspberry Pi Pico RP2040 microcontroller and the Digital Microphone of a  Adafruit PDM MEMS Microphone Breakout board.
Using the Raspberry Pi Pico SDK's TinyUSB library as its USB software stack, and it's built-in USB Audio Class support transforms the board into a USB microphone device.
The RP2040 does not have built-in support for both PDM peripheral interface in software.
The PIO generates a clock signal into the PDM Microphone which captures a digital value from the Microphone once per clock period.The DMA is configured to capture 1 millisecond of audio, with 16 samples (64 x 16 = 1024 bits) generated every millisecond. Received samples will be filtered using the OpenPDM2PCM library and downsampled from 1024-bit raw PDM data into 16 Pulse-code modulation (PCM) 16-bit audio samples and then sent over USB to the PC in real-time!
As USB Audio standard is used for communications between the Raspberry Pi Pico and the PC, no custom software is needed on the PC side.\
Project [Link](https://www.hackster.io/sandeep-mistry/create-a-usb-microphone-with-the-raspberry-pi-pico-cc9bd5)

# Project 3 - Time Attendance System with RFID
Goal - To build a time attendance system which shows if you are late or in time according to a preset time.\
Topic - Arduino\
RFID (**R**adio-**F**requency **ID**entification) uses electromagnetic fields to automatically identify and track tags attached to objects by assigning a **Un**ique **ID**entification (UID) to each tag. 
This projects uses the MFRC522 RFID Reader which sends a signal to the tag and reads its response and communicates with the Arduino using SPI protocol. It uses a SD Card module to store the UID of the tags on an SD card. The Arduino communicates with the SD card using an SD card module with the same SPI protocol. 
It also uses a DS1307 RTS (**R**eal-**T**ime **C**lock) Module to keep track of time. Furthermore, this RTC module has an inbuilt backup battery installed which allows the module to retain the time, even when it’s not being powered up. 
Functions of each of the modules are implements by including the required libraries respectively in the code. 
When the RFID reader reads an RFID tag, a buzzer beeps, and it saves the current time and the UID of the tag in an SD card. 
According to the check-in time set by the user, it detects if you are on-time and lights up the green led, else if you are late, a red LED lights up. 
This project can be expanded by linking data received from the RFID reader directly into a database which can identify the person by the UID an record the attendence.\
Project [Link](https://randomnerdtutorials.com/arduino-time-attendance-system-with-rfid/)

# Project 4 - Pulse Oximeter using NodeMCU
Goal - IoT Based Pulse Oximeter Using ESP8266 & Blynk Application\
Topic - NodeMCU and IoT\
**NodeMCU** is a low-cost open-source IoT platform based on firmware which runs on the ESP8266 Wi-Fi SoC and hardware which was based on the ESP-12 module. 
This project uses the MAX30100 *Pulse Oximeter and Heart-Rate sensor* to measure the SpO2 level in the blood. This sensor has two LEDs emitting - red light, infrared light. Infrared light is required for pulse rate but, both lights are required for measuring SpO2 levels in the blood. Oxygenated blood absorbs more infrared light and passes more red light but, deoxygenated blood absorbs red light and passes more infrared light. So, at its core, the MAX30100 sensor reads the absorption levels for both light sources and stores them in a buffer to be read. 
This MAX30100 sensor is interfaced with an OLED Display (to display sensor data) and the NodeMCU ESP8266 module (to allow WiFi access). 
Blynk is an IoT cloud platform with iOS and Android apps to control Arduino, ESP8266, Raspberry Pi , etc. over the Internet. This platform is used to connect the phone to the Oximeter through the NodeMCU module. A simple app (GUI) is created using the Blynk App to display the SpO2 and Heart rate valus on your phone. 
This project can be made more compact be desiging and placing the components in a single module (box).\
Project [Link](https://www.hackster.io/Alfa0420/esp8266-pulse-oximeter-blynk-bpm-76f4a3)

# Project 5 - TapLock : Bike/Bicycle lock
Goal - Using the power of Machine Learning (ML) to read tapping pattern to keep your bike safe.\
Topic - Arduino\
This project uses the Arduino Nano 33 BLE sense along with a power bank to power the board. For tap detection, the accelerometer found on the Arduino Nano board is used. 
ML is implement through the is Edge impulse platform. It records the tapping and presents it as a graph of axial acceleration based on time. 
The accelerometer output was preprocessed on the board by averaging the acceleration over all three axes so that minute variations (without changing the base tapping pattern) in tapping is also recognised. 
The raw data processing block from Edge impulse along with Keras neural network learning block was used to train the system to learn the tapping pattern to a high accuracy. 
The functions of Taplock is controlled via an application on the mobile phone, that connects to the board via Bluetooth. This app is integrated with a map client. 
When the bike is locked, it updates the lock atatue to the app and also creates a pin is on the map to indicate the location of the bike. 
The user can also manually lock or unlock the bike via the app. 
The mounting bracket on the bike for the board was 3D printed.\
Project [Link](https://www.hackster.io/taplock/taplock-a-bike-lock-with-machine-learning-85641c)
