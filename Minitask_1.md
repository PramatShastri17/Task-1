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
[Link to the Project] (https://www.hackster.io/e_s_c/ultrasonic-levitation-machine-using-arduino-9e3989)\
![Acoustic_Levitation](https://user-images.githubusercontent.com/85291394/121806316-f4c4bb00-cc6c-11eb-9ba8-d15a6be44972.gif)


# Project 2 - USB Microphone
Goal -  Creating a USB microphone device.\
Topic - Raspberry Pi\
This project deals with Programming I/O (PIO), Direct Memory Access (DMA), and USB capabilities of the Raspberry Pi Pico RP2040 microcontroller and the Digital Microphone of a  Adafruit PDM MEMS Microphone Breakout board.
Using the Raspberry Pi Pico SDK's TinyUSB library as its USB software stack, and it's built-in USB Audio Class support transforms the board into a USB microphone device.
The RP2040 does not have built-in support for both PDM peripheral interface in software.
The PIO generates a clock signal into the PDM Microphone which captures a digital value from the Microphone once per clock period.The DMA is configured to capture 1 millisecond of audio, with 16 samples (64 x 16 = 1024 bits) generated every millisecond. Received samples will be filtered using the OpenPDM2PCM library and downsampled from 1024-bit raw PDM data into 16 Pulse-code modulation (PCM) 16-bit audio samples and then sent over USB to the PC in real-time!
As USB Audio standard is used for communications between the Raspberry Pi Pico and the PC, no custom software is needed on the PC side.\
Project [Link](https://www.hackster.io/sandeep-mistry/create-a-usb-microphone-with-the-raspberry-pi-pico-cc9bd5)\
![raspberry_pi_audio_logo](https://user-images.githubusercontent.com/85291394/121806487-a532bf00-cc6d-11eb-80b9-ba4c669cc083.png)


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
Project [Link](https://randomnerdtutorials.com/arduino-time-attendance-system-with-rfid/)\
![RFID](https://user-images.githubusercontent.com/85291394/121806687-808b1700-cc6e-11eb-92b5-a2e3777fe811.gif)


# Project 4 - Pulse Oximeter using NodeMCU
Goal - IoT Based Pulse Oximeter Using ESP8266 & Blynk Application\
Topic - NodeMCU and IoT\
**NodeMCU** is a low-cost open-source IoT platform based on firmware which runs on the ESP8266 Wi-Fi SoC and hardware which was based on the ESP-12 module. 
This project uses the MAX30100 *Pulse Oximeter and Heart-Rate sensor* to measure the SpO2 level in the blood. This sensor has two LEDs emitting - red light, infrared light. Infrared light is required for pulse rate but, both lights are required for measuring SpO2 levels in the blood. Oxygenated blood absorbs more infrared light and passes more red light but, deoxygenated blood absorbs red light and passes more infrared light. So, at its core, the MAX30100 sensor reads the absorption levels for both light sources and stores them in a buffer to be read. 
This MAX30100 sensor is interfaced with an OLED Display (to display sensor data) and the NodeMCU ESP8266 module (to allow WiFi access). 
Blynk is an IoT cloud platform with iOS and Android apps to control Arduino, ESP8266, Raspberry Pi , etc. over the Internet. This platform is used to connect the phone to the Oximeter through the NodeMCU module. A simple app (GUI) is created using the Blynk App to display the SpO2 and Heart rate valus on your phone. 
This project can be made more compact be desiging and placing the components in a single module (box).\
Project [Link](https://www.hackster.io/Alfa0420/esp8266-pulse-oximeter-blynk-bpm-76f4a3)\
![Oximeter](https://user-images.githubusercontent.com/85291394/121806723-aca69800-cc6e-11eb-857f-a5e955e152e2.jpg)


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
Project [Link](https://www.hackster.io/taplock/taplock-a-bike-lock-with-machine-learning-85641c)\
![TapLock](https://user-images.githubusercontent.com/85291394/121806801-fabb9b80-cc6e-11eb-9352-242b7b7c8b37.jpg)


# Project 6 - ESP32-CAM Video Surveillance Smart Camera
Goal - A video surveillance pan & tilt camera that can be controlled with an iPhone through Internet.\
Topic - Electronic\
The ESP32-CAM is a full-featured microcontroller that has an integrated video camera and microSD card socket which can perform advanced functions like image tracking and recognition. This project uses the ESP32-CAM to capture video. 
It is powered by the MB102 power supply module through a pair of batteries. 
The ESP32-CAM is mounted on a pair of SG-90 Servos (on there respective platforms), that work together to provide *tilt* and *pan* functionality, enabling the user to change the camera position. 
The microcontroller is programmed on the Arduino IDE with an ESP32 addon installed. The functions of this Smart Camera is completely controlled by custom developed app on the phone.
The program is first run to obtain the IP Address of the ESP32-CAM. This is then inputted on the mobile app to establish connection to the ESP32 board. 
In order to control the camera though the Internet outside the home network, user must configure their router to enable Port Forwarding to effectively communicate to the Camera.\
Project [Link](https://www.instructables.com/ESP32-CAM-Video-Surveillance-Smart-Camera/)\
![security camera](https://user-images.githubusercontent.com/85291394/122076757-c388ee00-ce18-11eb-9bb9-1f8fcbf5174a.gif)


# Project 7 - Interfacing GPS with 8051 Microcontroller
Goal - To determine the location of a vehicle or person.\
Topic - Microcontrollers\
GPS receivers provide reliable navigation, positioning and timing services to the users at anytime or anywhere on the earth. 
The GPS Module uses global positioning system whic uses a system of 24 to 32 satellites to return location data. 
This module calculates the position by reading the signals that are transmitted by these satellites. 
The GPS receiver continuously transmits the data as per the NMEA (National Marine Electronics Association) standards using RS232 protocol. 
This project uses the 8051 Microcontroller along with a MAC232 IC for level conversion (from RS232 to TTL) and LCD to display the data. 
The microcontroller receives data from GPS module serially using UART (Universal Asynchronous Receiver/Transmitter) protocol. 
In NMEA format, the *Latitude* and *Longitude* values of location are available in GPRMC sentence. 
The extracted *Latitude* and *Longitude* values (in NMEA format) is then displayed on the LCD.\
Project [Link](https://www.electronicshub.org/interfacing-gps-8051-microcontroller/)\
![isometric_smartphone_gps](https://user-images.githubusercontent.com/85291394/122076278-5ecd9380-ce18-11eb-9b4d-153e185af3a1.gif)


# Project 8 - Wireless Electronic Notice Board using GSM Technology
Goal - To display data send from the mobile phone on the LCD\
Topic - Electronics\
GSM (Global System for Mobile Communications) is a telecommunication standard allows long range, reliable and secure communication. 
This project uses 8051 Microcontroller (with Dev Board) , GSM Module (SIM 900A GSM Modem) and LCD to display message (used in 8 – bit mode - needs 8 data lines to display the data). 
The GSM Module is directly connected to the microcontroller as the logic levels of both the GSM Modem and Microcontroller are already matched in the GSM Module Board. 
If there is no level converter on the board, then MAX232 level converter is used as a mediator between Controller and GSM to transfer the data. 
In order to communicate with the GSM Modem, AT commands are sent using serial communication (UART protocol). 
When user sends the message from the mobile, GSM modem sends a command serially to indicate that a new message is received. 
The location of the new message is identified and read by the GSM modem and then sends a serial command to the controller with additional information (This information still contains our message). 
From this command, our message is extracted and then displayed on the LCD.\
Project [Link](https://www.electronicshub.org/wireless-electronic-notice-board-using-gsm/)\
![Wireless-Electronic-Notice-Board-using-GSM-Image-5-760x440](https://user-images.githubusercontent.com/85291394/122077387-52960600-ce19-11eb-8c22-51488147a900.jpg)


# Project 9 - Solar Panel Sun Tracker (+ Phone Charger)
Goal -  To build a sun tracking solar array that positions the solar panels to always face the sun.\
Topic - Arduino\
This project consists of two LDRs, a servo motor, two solar panels and an Arduino. 
The components are connected as per the scmenatic and are suitably mounted onto the supporting frame with required mechanical adjustments. 
This project works on the principle that resistance of an LDR is inversely proportional to the intensity of light that falls on its surface.
The LDRs are positioned at the ends of the solar panels. When intensity of light incident on one of the LDR's increases, its resistance decreases,so the panels move towards this side to counter this decrease with the help of the servo. 
The servo and the LDR's output are properly calibrated to ensure optimal functioning. 
Additionally, a 2.5V - 5V DC-DC boost converter can be directly connected to the solar panels to enable phone charging. 
But as the power output of just two solar panels are not sufficient to make the system self-sustaining and reliable to charge a phone, more solar panels can be added to the system with suitable structural modifications.\
Project [Link](https://www.hackster.io/FIELDING/solar-panel-sun-tracker-phone-charger-f669ce)\
![Sun tracker](https://user-images.githubusercontent.com/85291394/122074398-cf73b080-ce16-11eb-9c4b-554dad90959c.jpg)


# Project 10 - Intruder Detection using Ultra Low Powered Thermal Vision
Goal - To build a system which detects intruders in dark with a low resolution thermal camera.\
Topic - Raspberry Pi\
This project uses Raspberry Pi Pico, which is connected to the MLX90640 IR Thermal Camera over I2C. Also a TFT Display is connected to it over SPI. Also, a red LED is connected to the Raspberry Pi. 
The Seeed Wio Terminal is used to collect data for training the system. 
Thermal image data was captured in separate file and then saved on an inbuilt micro SD card on the Wio Terminal. 
This data is uploaded to Edge Impulse to implement Machine Learning. 
The training data is displayed as a time-series of 1 ms interval data but it is used as a single data instance by setting the window size 768 ms which equals to 768 thermal readings. 
Since this is not a time-series data, the Raw Data block is used without preprocessing, which is fed into the Neural Network block. 
When the camera detects a human like thermal signature (as per the training data), it is detected as a person and the red LED glows signifying an intruder. 
This concept can be further integrated with an IoT device which sends a warning to the user.\
Project [Link](https://www.hackster.io/naveenbskumar/intruder-detection-using-ultra-low-powered-thermal-vision-24ed45)\
![intruder_detection](https://user-images.githubusercontent.com/85291394/121711791-9aa2e900-caf8-11eb-8caa-6988bc9511b2.gif)


# Project 11 - Password Protected Door Lock
Goal - To build a door lock that can be controlled from a smartphone using an app.\
Topic - Arduino\
This project uses an Arduino UNO interfaced with a HC-05 Bluetooth Module and a Servo. The Arduino is powered externally through a wall adapter. 
The locking mechanism for this project is 3D printed and assembled accordingly. 
The arduino is programmed to receive commands from a mobile app by establishing bluetooth connection through the HC-05 module. 
The mobile app is designed using MIT App Inventor. 
Its interface includes - Button to connect to the Arduino, Buttons to open or close the door, a Text Box to accept password and a Message Box to display the status or warnings.
The android application is designed to send two command together - the action to be performed (Open or Close) and the password - separated by an '=' character. 
When this command is passed, the action command is first separated from the password with the '=' as referance. 
The password is validated against the preset password, then accordingly the action is carried out or addressed with an appropriate message.\
The project can be improved by providing battery backup to the Arduino incase of any power outages. 
Also, a keypad can be added to enter the password (digits only) incase mobile phone is not available.\
Project [Link](https://www.hackster.io/taifur/arduino-and-android-based-password-protected-door-lock-36887d)\
![door-lock_](https://user-images.githubusercontent.com/85291394/121784325-08224880-cbd1-11eb-895d-cd2cd9e3b32d.jpg)

# Project 12 - Water Level Controller
Goal - To detect and control the water level in an overhead tank and automatically operate the water motor.\
Topic - Microcontrollers\
This project uses the 8051 Microcontroller interfaced with LCD display, Relay Module and Detector Circuit to detect water level. 
This system works on the principle that **Water Conducts electricity**. 
Water sensing is done by using a set of four wires, which are placed at different levels in the tank, the lowest placed being DC supply probe. 
Ther are connected to the microcontroller through a Detector Circuit which comprises of three 2N2222 (NPN) Transistors + Resistors connected in parallel to the remaining three wire probes. 
These four wires indicate the different water levels in the tank. 
Based on the outputs of these wires, the microcontroller displays water level on LCD as well as controls the motor through the relay module. 
Depending on the initial level of water in the tank, LCD will display a message - either LOW, HALF or FULL - as well as the status of the motor - either ON or OFF. 
The motor runs automatically till water level becomes FULL. 
When water level falls again, the LCD displays its current level and runs the motor till the tank is FULL.\
Project [Link](https://www.electronicshub.org/water-level-controller-using-8051-microcontroller/)
![imgonline-com-ua-twotoone-9lLa4YWv7UHgoHZ0](https://user-images.githubusercontent.com/85291394/122075153-78baa680-ce17-11eb-9d32-a2f53031a370.png)


# Project 13 - Controlling Raspberry Pi Using Alexa
Goal - To connect and control Raspberry Pi using Alexa Voice Commands.\  
Topic - Raspberry Pi and IoT\
This project mainly uses the Raspberry Pi and an Amazon Echo Device. 
A simple circuit consisting of an LED and resistor is connected to the raspberry pi. 
For establishing connection between Raspberry Pi and Alexa, *ngrok* tool is used. *Ngrok* establishes a HTTP tunnel from Raspberry Pi to Alexa. 
An Endpoint URL will be generated by *ngrok* and will change every time program is restarted. 
Skills for Alexa will be made using Flask-Ask, which is a Flask extension that helps to build voice user interfaces with the Alexa Skills Kit. 
The Raspberry Pi is coded to control the behavior of LED connected to it. 
This code will be hosted on localhost which will be tunneled to Alexa Skill through *ngrok*. 
Using an Amazon developer account, Alexa Skill console is accessed and a new skill is created and appropriately coded with required commands to control the LED. 
Here, the invocation name 'raspberry' is used to interact with Raspberry Pi. 
In 'Endpoint' on Alexa Skill, the Endpoint URL generated from ngrok is saved in default region, completing the connection between the Raspberry Pi and Alexa. 
A command like "Alexa, ask raspberry to turn on light" will turn on LED light connected to the Raspberry Pi.\
Project [Link](https://www.hackster.io/nishit-patel/controlling-raspberry-pi-using-alexa-33715b)\
![rasp-alexa](https://user-images.githubusercontent.com/85291394/122051098-d3490800-ce01-11eb-9127-10d6a15dd3dd.png)


# Project 14 - Alerting Indoor IoT Air Quality Monitor
Goal - To measure and log indoor air quality and configure alerts when air quality is compromised.\
Topic - IoT\
This project uses Arduino Nano 33 IoT interfaced with a Bosch BME680 Air Quality Sensor and a NeoPixel LED Stick. 
The circuit is assembled inside a box with predrilled holes to allows the flow of air through it. 
The BME680 sensor reports a calculated air quality measurement and the accuracy of its measurement. 
The accuracy of the calibration is displayed through the number of pixels lit on the LED array. 
The accuracy range is from 0 to 3, so two pixels are lit for each of the accuracy categories. 
The color of the pixels corresponds to the air quality measurement - green from 25, yellow from around 200 and red above 400. 
The ThingSpeak IoT analytics platform is used to track the air quality data in real time and is also programmed to sends email alerts to the user when air quality is compromised. 
The data recorded is represented and stored in the form of a live graph (using MatLab Analysis). This gives the user the ability to view and compare historic air quality trends. 
Also, the air quality of the room can be monitored remotely as well using ThinkSpeak.\
Project [Link](https://www.hackster.io/team-matlab-iot/make-your-air-safer-alerting-indoor-iot-air-quality-monitor-5eb90d)\
![Air quality Monitor](https://user-images.githubusercontent.com/85291394/121804305-508a4680-cc63-11eb-8859-2007c23adc27.jpg)


# Project 15 - Persistence of Vision (PoV) Display
Goal - To display any text or image on an LED PoV Display.\
Topics - Arduino\
**PoV** occurs when a visual image seems to persist continuously when a stream of light is repeatedly interrupted for very brief instances and does not enter our eyes during those durations giving us the illusion that the images are in motion. 
This project uses the Arduino Nano powered by a 9V battery. It is connected with an array of 8 LEDs along with an IR sensor. 
The IR sensor in needed to indicate the starting position from where the text or image is to be written/displayed. 
The Holder, consisting of the rotating arm and the steady assembly, are 3D printed. A DC motor is attached to the Holder to rotate the arm. 
The LEDs are connected together along with resistors (for protection) on a GPB and placed in the rotating arm. 
Each LED anode is connected to individual pins on the Arduino and the cathodes (common to all LEDs) are connected to ground. 
A small piece of white paper is attached to the steady assembly, which will be detected by the IR Sensor. 
Varying the placement of the paper leads to a change in the position of the text displayed. 
The Arduino is programmed to display the text with controlled blinking of the LEDs in such a way that the different images overlap each other forming letters causing the effect of PoV. 
When the motor is powered, the IR sensor detects the white paper and the LEDs start to glow, creating the illusion that something is displayed by the LED.\
Project [Link](https://create.arduino.cc/projecthub/theSTEMpedia/persistence-of-vision-pov-display-using-arduino-583d5f)\
![POV_Display](https://user-images.githubusercontent.com/85291394/122073321-f5e51c00-ce15-11eb-987e-6fe2c274cb46.gif)
