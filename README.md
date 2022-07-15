# wafaa-almadhoun-servo_motor_with_PCA9685_module_using_Arduino_UNO_R3_
electronic path week 2 task


## Table of contents
* [Introduction](#Introduction)
* [Technologies](#technologies)
* [Components required](#Components-required)
* [Connections](#Connections)
* [Block diagram & simulation ](#Block-diagram-&-simulation)



## Introduction
This project is to control servo motors using Arduino UNO R3 simulated with TINKERCAD circuit , The servo motor is used in robotics to activate movements, giving the arm to its precise angle , so we used it with several projects like robot arm , spider robot and humanoid robot  ,We will cover several topics : 👍 


 1. servo motor rotate from 0 to 90 degrees and back simulated with TINKERCAD circuit  .
 2. servo motor Controlled by using Potentiometer simulated with TINKERCAD circuit .
 3. servo motor with PCA9685 module rotate from 0 to 90 degrees and back . 
 4. servo motor with PCA9685 module  Controlled by using Potentiometer. 


## Technologies
Project is created with:
* Arduino IDE 1.8.19 [To Downloud](https://www.arduino.cc/en/software)
* AUTODESK TINKERCAD [Open](https://www.tinkercad.com/)
	
## Components required
1. Arduino UNO
2. 1 servo motors MG995
3. jumper wirs
4. 1 potentiometer 10 K ohm 
5. bettrey  5 volt 
6. breadboard
7. PCA9685 module 

## Connections
Connection pins:
 1. servo motor rotate from 0 to 90 degrees and back simulated with TINKERCAD circuit  .
  
     5V: Power (red) to servo 
     
     Gnd: Ground (black) to servo
     
     we attach the servo object to pin 9 in arduino 
   
 2. servo motor Controlled by using Potentiometer simulated with TINKERCAD circuit .
     5V: Power (red) to servo 
     
     Gnd: Ground (black) to servo
     
     we attach the servo object to pin 9 in arduino 
       
     5v: power from Arduino to breadboard to Potentiometer
     
     signal of Potentiometer attach to pin A0 in arduino 

 
## Block diagram & simulation
### 1.servo motor rotate from 0 to 90 degrees and back simulated with TINKERCAD circuit . [see here](https://www.tinkercad.com/things/9Hd8sj9JjSr-servo-motor-rotate-from-0-to-90-degrees/editel)
![Cool Bigery-Uusam (3)](https://user-images.githubusercontent.com/64277741/179117203-9ee32234-7d2c-4f77-b2a4-db39a51de82f.png)
Figure (1): Servo Motor at initial value (0 degree

After 30 ms
![Cool Bigery-Uusam (2)](https://user-images.githubusercontent.com/64277741/179117381-296e4d7b-d3bb-45ee-b0f0-a619268678ff.png)
Figure (2): Servo Motor at 90 degrees 

#### The Code 
#include <Servo.h>

Servo myservo;  // create servo object to control a servo


int pos = 0;    // variable to store the servo position

void setup() {

  myservo.attach(9);  // attaches the servo on pin 9 to the servo object
}

void loop() {

  for (pos = 0; pos <= 90; pos += 1) { // goes from 0 degrees to 90 degrees
  
    // in steps of 1 degree
    
    myservo.write(pos);              // tell servo to go to position in variable 'pos'
    
    delay(30);                       // waits 30ms for the servo to reach the position
    
  }
  
  for (pos = 90; pos >= 0; pos -= 1) { // goes from 90 degrees to 0 degrees
  
    myservo.write(pos);              // tell servo to go to position in variable 'pos'
    
    delay(30);                       // waits 30ms for the servo to reach the position
    
  }
  
}

### 2. servo motor Controlled by using Potentiometer simulated with TINKERCAD circuit .[see here ](https://www.tinkercad.com/things/bbagRhCJEr8-servo-motor-controlled-by-using-potentiometer/editel)

![servo motor Controlled by using Potentiometer](https://user-images.githubusercontent.com/64277741/179123789-863c1598-059b-42cd-8c3f-d3abc94e5751.png)
Figure (3): Servo Motor at initial value (0 degree)

After changing the value of Potentiometer 
![servo motor Controlled by using Potentiometer (1)](https://user-images.githubusercontent.com/64277741/179124038-f83b191b-ad75-4a50-9389-99e6ef5e4fe5.png)
Figure (4): Servo Motor at 180 degrees

After changing the value of Potentiometer 

![servo motor Controlled by using Potentiometer (2)](https://user-images.githubusercontent.com/64277741/179124144-9b929f91-288c-4dbe-83be-e01724491ac1.png)
Figure (5): Servo Motor at 60 degree 
#### The code 

#include <Servo.h>

Servo myservo;  // create servo object to control a servo

int potpin = 0;  // analog pin used to connect the potentiometer

int val;    // variable to read the value from the analog pin

void setup() {
  myservo.attach(9);  // attaches the servo on pin 9 to the servo object
}

void loop() {

  val = analogRead(potpin);            // reads the value of the potentiometer (value between 0 and 1023)
  
  val = map(val, 0, 1023, 0, 180);     // scale it to use it with the servo (value between 0 and 180)
  
  myservo.write(val);                  // sets the servo position according to the scaled value
  
  delay(15);                           // waits for the servo to get 
  
}


### servo motor with PCA9685 module rotate from 0 to 180 degrees and back  [see here](https://www.tinkercad.com/things/jBKW8pofJhZ-task-3-control-servo-motor-using-potentiometer/editel?sharecode=FqY5TjQ9On_IY1DgVje0gg_ci8Gl3PQnv6i9iKbzVOA)
At begin
![3](https://user-images.githubusercontent.com/64277741/122786908-75169c00-d2bd-11eb-9624-60cee51a1ea6.PNG)
Figure (6): Five Servo Motor with Five Potentiometers

After start simulation ![4](https://user-images.githubusercontent.com/64277741/122787141-b3ac5680-d2bd-11eb-97f9-08a8c668f9b1.PNG)
Figure (7): Changing the angles of Servo Motors according to change the angles of Potentiometers

#### The Code 

