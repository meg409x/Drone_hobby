# ADR-TaskPhase
STRUCTURE OF TASK 


Write code to implement MPU readings on the serial monitor >use complimentary filter on the MPU readings to combine the accelerometer and gyroscope readings >use the values obtained from the filter in the PID loop code >Obtain PWM Left and Right values using the PID balancing code >Compare the left and right values in order to confirm attitude stabilization >these signals are then eventually sent to the ESC
MICROCONTROLLERS


Microcontrollers are integrated circuits that are basically tiny computers. They can run small, simple software programs. They are low powered enough that they can be powered by a battery for days, but they are fast enough to process data much faster than any human being can think.

ARDUINO


Arduino is a company in Italy that designs and sells circuit boards that make microcontrollers easy to use.
NOTE*
often Arduinos are called microcontrollers, and that's technically incorrect.
Arduinos are circuit boards that not only have  microcontroller chips on them, but also a lot of other stuff on it.
There are a lot of different types of Arduinos, Here, I will be using the Arduino Nano for the task.
![image](https://user-images.githubusercontent.com/96991020/157723268-a7108f48-666a-40cb-b762-b6d16c555c06.png)

 



INTEGRATING THE ARDUINO AND THE MPU 6050


 ![image](https://user-images.githubusercontent.com/96991020/157723186-d604cdac-4233-45cf-9701-f3a91329ce96.png)
 ![image](https://user-images.githubusercontent.com/96991020/157723214-1e26dfe6-9198-4cf4-ad48-892c1bd7a06e.png)




ARDUINO PROGRAMMING



Every Arduino program will have two main areas,
The setup and The loop.
The setup area is where you configure your Arduino to do certain things for the duration of your program.
It could be information on which pins are inputs, and which are outputs, but in this case we are telling it to send serial data to our computer at 9600 bits per second(baud rate), which is a pretty standard data rate for most projects
The loop is the area of code that repeats over and over again for as long as the Arduino has power to it.


INTEGRATED CIRCUIT



 ![image](https://user-images.githubusercontent.com/96991020/157722848-03a89da3-930f-4675-be72-484a843102a9.png)
 ![image](https://user-images.githubusercontent.com/96991020/157722985-cbfb0d67-0a9f-43a0-b2e5-af83715fa5cb.png)

USB connection 
![image](https://user-images.githubusercontent.com/96991020/157723036-49839be2-183b-4c7e-8823-9179381f92b8.png)
 
FILTER

Please note that I have used complimentary filter only in my task 


COMPLIMENTARY FILTER 



It takes slow moving signals from the the accelerometer and fast moving signals from the gyroscope to combine them and eliminate the integration error and gyro drift respectively for which it uses a low pass filter on the accelerometer and a high pass filter on the gyroscope.
Filter formulae has been implemented on code (Please refer to the code uploaded in the repository)


KALMAN FILTER



Kalman filter tries to estimate a continuously changing (w.r.t to time) state variable based on some noisy observation. It does so iteratively, i.e, it relies on the last estimate to predict the present one.
To estimate the position using a Kalman filter.
1.	Obtain the prior information of the position from the GPS receiver.
2.	Have an estimate of the noises from the various sensors; speedometer, intertial sensor and GPS receiver from their datasheets. The noises can be approximated by white Gaussian noises, with zero mean and the variances in the measurements.
3.	Construct the motion and measurements models with the states latitude longitude and heading in the global coordinates
PID 
The term PID stands for proportional integral derivative and it is one kind of device used to control different process variables like pressure, flow, temperature, and speed in industrial applications. In this controller, a control loop feedback device is used to regulate all the process variables.


TUNING 


PID tuning is the process of finding the values of proportional, integral, and derivative gains of a PID controller to achieve desired performance and meet design requirements.

ZEIGLER NICHOLS METHOD OF PID TUNING 


The Ziegler-Nichols rule is a heuristic PID tuning rule that attempts to produce good values for the three PID gain parameters:


A.	Kp - the controller path gain
B.	Ti - the controller's integrator time constant
C.	Td - the controller's derivative time constant


feedback loop parameters required to be derived from measurements:
1.	the period Tu of the oscillation frequency at the stability limit
2.	the gain margin Ku for loop stability
with the goal of achieving good regulation (disturbance rejection)


>Tuning rules
 ![image](https://user-images.githubusercontent.com/96991020/157723404-2c052388-1fdd-4b1a-a372-bf672c53dab0.png)







































REFERENCES


•	i2c - What does this notation stands for? Wire.read() <<8 | Wire.read() - Arduino Stack Exchange


•	(2) How can I implement a Kalman filter on Arduino to eliminate noise on a triaxial accelerometer? - Quora


•	Complementary filter with the MPU6050 - Using Arduino / Project Guidance - Arduino Forum


•	You can learn Arduino in 15 minutes. - YouTube



•	Arduino and MPU6050 Accelerometer and Gyroscope Tutorial (howtomechatronics.com)



•	Arduino Nano Every — Arduino Online Shop



•	Gyroscopes, Accelerometers and the Complementary Filter | Bayesian Adventures (wordpress.com)



•	sensors-11-05931.pdf



•	c++ - Difference between errors "does not name a type" and "has not been declared" - Stack Overflow



•	C variable with examples (fresh2refresh.com)



•	MPU 6050 Tutorial | How to Program MPU 6050 With Arduino - Arduino Project Hub



•	MPU-6000 and MPU-6050 Product Specification Revision 3.4 (Data sheet)



•	Incorrect Accelerometer Sensitivity with MPU-6050 - Using Arduino / Sensors - Arduino Forum



•	 <img width="383" alt="image" src="https://user-images.githubusercontent.com/96991020/157723758-296d99d4-ea87-41d1-9f0e-2650168f5790.png">

                   (sensitivity )
                   
                   
                   
                
