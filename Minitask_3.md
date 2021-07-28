# TapLock - Smart Bicycle Lock
## Debugging Steps
As we are working with only a single board with all sensors embedded in it, we need to make sure if all the components and sensors are actually working. 

This project mainly uses the *Bluetooth sensor* and the *IMU sensor*. 

#### 1. Testing Arduino Board
First, we begin by check if the *Power LED* of the arduino board lights up when the board is powered. 
> If **Yes**, then we move on to testing individual sensors. \
> If **No**, this means that the board is faulty and is not able to power up. In this case, the board may need to be replaced.

Next, we make sure that the IC or any specific sensors doesn't heat up during operations.
> If it does, then this is *not good news*. The IC/sensors might have burnt out. But, *shorting an Arduino isn't easy*, they have *inbuilt mechanism* to prevent this. So, this can be tested at the end after all other tests.\
> Even if only one of the sensors is overheating the *entire* board needs to be replaced.

#### 2. Testing Individual sensors
Now, we test if thses individual sensors are working properly.
* **Bluetooth Sensor**
>> First, start by running you project code and connecting to the Arduino thought your mobile's Bluetooth. Try to unlock and lock the TapLock for the app itself. If these operation happen seamlessly then the Bluetooth sensor is working!!\
>> If connection seems to disconnect frequently, first check that your mobile's Bluetooth is functioning correctly. If it is, then the issues is with the Bluetooth sensor of the Arduino. 
>> Now, run a debugger code to check if the Arduino is being powered correctly, i.e., if its working at 3.3 V. If not then the Arduino is faulty and needs to be replaced.
* **IMU Sensor**
>> Now, we check the IMU sensor by running a code that detects the changes orientation of the board and prints the data continuously as you run the code in the Arduino. If there is no output or if it outputs the same data even if you changed its orientation, this means that there the IMU sensor is faulty.\
>> If the outputs change seamlessly with change in orientation of the board, this mean that the IMU sensor is working without a fault. 

#### 3. Testing the software
* **Machine Learning Model** 
>> If we are unable to get our desired results, i.e., the locking/unlocking is not happening when we perform the correct Tapping pattern, then the ML model may have an issue like overfitting or underfitting.\
>> This can be easily resolved looking at plots of the accuracy and loss of the model on Edge and appropriately tweak the model or applying optimisations or just training the model with more diverse data.

# Wireless Electronic Notice Board using GSM
## Debugging Steps
The components work in the following sequence:
> Mobile Device --> GSM Module --> Microcontroller --> LCD Display

The best method to debug is to follow this sequence and evaluate the performance of each of these components. 
### Hardware 
#### 1. Mobile Device
* Check if the mobile phone is connected to the carrier service and ensure the signal is good. If not try to change your location or use another mobile phone.
* Ensure if you have inserted a functioning SIM in your phone. If you have a faulty SIM, get it replaced.
* Ensure your carrier service package has not expired. If it has, then subscribe to a package to use use the SMS service.
* Finally. check if you able to send/receive SMSs for you device. This can be done by sending test messages to anybody you know.

#### 2. GSM Module
* Ensure that you can inserted a functioning SIM in the GSM module.
* Then, power on the board through a 12V DC supply and see if the the LEDs light-up. 
* Notice that if the green LED is blinking at a fast rate then this means that the GSM module is trying to connect to the carrier service of the inserted SIM. If the rate of blinking slows down then the GSM module has established a connection. 
* If you don't notice:
  - The LEDs *don't* lighting up when powered, the GSM module may be faulty and you must get it replaced of check to ensure that the components are properly soldered.
  - If the green LED countinues to blink at a fast rate , then either the SIM is faulty or the signal in your area might be weak. Try changing the location to improve the connection or try using a different SIM.
* If this module is heating up during operation, first check if you are supply only 12V DC power. If you find the you have used a higher watted power supply you may have just *burned out* the module causing permanent damage. The only fix is to replace with a new  module.
#### 3. 8051 Microcontroller
* First, check if the LED on the Dev Board lights up when powered on. If *not*, then the Dev Board might be faulty. You may need to get it check or replaced.
* Next, if the microcontroller *heats up* during operation, this means that it has *shorted*. Here, we have no other alternative than to replace the microcontroller.
#### 4. LCD Display
* First, check if all the reuired connections to the LCD module are correct. 
* Then, check if the LCD backlight turns on when powered. If *not*, then try to adjust the contrast using the potentiometer to improve the lighting. If this too doesn't help then the module may be faulty and needs to be replaced.
* Connnect it to the microcontroller and try to print "Hello World" on the LCD by using appropriate code. After checking if the code is correct, you dont get desired input then,
  - Check if the module is receiving adequate current (below limit). If not the, change external power circuit accrodingly to ensure adequate power.
  - If this doesnt help, mostly there is a faulty in the LCD module, and you need to replace it.

### Code
* First, check if all the connection in the circuit are correct and all the modula have powered on correctly.
* Run the project code on the microcontroller and then send an SMS from your phone to check if the project works as desired.
* If *not* then,
  - Try to have print statements after small chunks of code to check the values held by variables. If inconsistance is noticed, then take appropriate action.
  - If you are having any issues with AT commands, then first go thought the documentation and check if you have implemented the commands correctly. 
