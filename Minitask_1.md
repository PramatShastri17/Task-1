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
RFID (**R**adio-**F**requency **ID**entification) uses electromagnetic fields to automatically identify and track tags attached to objects by assigning a **Un**ique **ID**entification (UID) to each tag. This projects uses the MFRC522 RFID Reader which sends a signal to the tag and reads its response and communicates with the Arduino using SPI com protocol. It uses a SD Card module to store the UID of the tags on an SD card. It also uses a DS1307 RTS (**R**eal-**T**ime **C**lock) Module to keep track of time. Furthermore, this RTC module has an inbuilt backup battery installed which allows the module to retain the time, even when it’s not being powered up.
