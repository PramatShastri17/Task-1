# Project 1 - Ultrasonic Levitation Machine using Arduino:
Goal - To explore levitation of objects using Interference of Ultrasonic Waves\
Topic - Arduino\
This project deals with building an ultrasonic levitator, capable of levitating small objects, by implementing the concept of standing wave interference using ultrasonic sensors. 
The Arduino is programmed to generate a 40KHz high-frequency oscillation signal for the ultrasonic transducer and this pulse is applied to the input of duel motor driver IC L293D to drive the ultrasonic transducers. 
The pair of ultrasonic transducers (collected from HCSR04 module) are positioned opposite to each other along the same line at a suitable distance apart, to produce standing waves inbetween them. 
Standing sound waves have defined _nodes_(areas of minimum pressure) and _antinodes_(areas of maximum pressure). 
When the orientation of the wave is parallel to the pull of gravity, portions of the standing wave have a constant downward pressure and others have constant upward pressure. 
When a small object is carefully positioned inbetween the transducers, it appears to float free of any support.\
This machine is very sensitive as variation is subtle parameters (like positioning of or distance between the sensors) can tamper with the results. Also, it is limited to levitating only small (lighter) objects. 
Designing the transducer with a concave geometry to fit more pairs of ultrasonic sensors (suitably positioning them on the surface) may allow it to lift havier objects. 
Project Link: [https://www.hackster.io/e_s_c/ultrasonic-levitation-machine-using-arduino-9e3989](https://www.hackster.io/e_s_c/ultrasonic-levitation-machine-using-arduino-9e3989)
