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
Goal -  Creating a USB microphone device using a Raspberry Pi Pico board and an external Digital Microphone.\
Topic - Raspberry Pi\
This project deals with Programming I/O (PIO), Direct Memory Access (DMA), and USB capabilities of the Raspberry Pi Pico RP2040 microcontroller and the Adafruit PDM MEMS Microphone Breakout board.
Using the Raspberry Pi Pico SDK's TinyUSB library as its USB software stack, and it's built-in USB Audio Class support transforms the board into a USB microphone device.
The RP2040 does not have built-in support for both PDM peripheral interface in software.
The PIO generates a clock signal into the PDM Microphone which captures a digital value from the Microphone once per clock period.The DMA is configured to capture 1 millisecond of audio, with 16 samples (64 x 16 = 1024 bits) generated every millisecond. Received samples will be filtered using the OpenPDM2PCM library and downsampled from 1024-bit raw PDM data into 16 Pulse-code modulation (PCM) 16-bit audio samples and then sent over USB to the PC in real-time!
As USB Audio standard is used for communications between the Raspberry Pi Pico and the PC, no custom software is needed on the PC side.\
Project [Link](https://www.hackster.io/sandeep-mistry/create-a-usb-microphone-with-the-raspberry-pi-pico-cc9bd5)

