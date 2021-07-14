# TapLock - Smart Bicycle Lock
## Debugging Steps
As we are working with only a single board with all sensors embedded in it, we need to make sure if all the components and sensors are actually working. 

This project mainly uses the *Bluetooth sensor* and the *IMU sensor*. 

#### 1. Testing Arduino Board
First, we begin by check if the *Power LED* of the arduino board lights up when the board is powered. 
> If **Yes**, then we move on to testing individual sensors. \
> If **No**, this means that the board is faulty and is not able to power up. In this case, the board may need to be replaced.

Next, we make sure that the IC or any specific sensors doesn't heat up during operations.
> If it does, then this is *not good news*. The IC/sensors might have burnt out. \
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
