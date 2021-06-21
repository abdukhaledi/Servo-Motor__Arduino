# Servo-Motor__Arduino
This is a five servo motors for the robot arm project we're making on Smart Methods company, each servo motor controled by one potentiometer using Arduino UNO microcontroler.
Servo motor is on inital angle 0, and it can rotated for 90 digrees maximum.
The simulation is done using Tinkercad online software.

## circuit link: 
https://www.tinkercad.com/things/fIu9mjbMDmG-servo-motor/editel

## circuit figure:
![servo motor](https://user-images.githubusercontent.com/85647212/122301036-cf53dd80-cf08-11eb-8b56-befc35adb4ab.png)

## circuit video:

https://user-images.githubusercontent.com/85647212/122309547-2791dc00-cf17-11eb-8ce5-4f613c0aef7f.mp4

## Arduino code:
import the servo library:
``` C++
#include <Servo.h> 
```
Create "Servo" object to control the servo motor
``` C++
Servo servoMotor0;
Servo servoMotor1;
Servo servoMotor2;  
Servo servoMotor3; 
Servo servoMotor4;  
```
Analog pin for the potentiometer 
``` C++
int potentiometer0 = A0;
int potentiometer1 = A1;
int potentiometer2 = A2;
int potentiometer3 = A3;
int potentiometer4 = A4;
```
variable to read values from potentiometers
``` C++
int pot_val0;
int pot_val1;
int pot_val2;
int pot_val3;
int pot_val4;
```
inside setup function attache servo objects to its own pins
``` C++
void setup()
{ 
  servoMotor0.attach(3);
  servoMotor1.attach(5);
  servoMotor2.attach(6);
  servoMotor3.attach(9);
  servoMotor4.attach(10);
}
```
inside loop function:
* read values of the potentiometers
* scale values of the potentiometers
* sets position according to its scaled value
``` C++
void loop()
{
  // read values of the potentiometers
  pot_val0 = analogRead(potentiometer0);
  pot_val1 = analogRead(potentiometer1);
  pot_val2 = analogRead(potentiometer2);
  pot_val3 = analogRead(potentiometer3);
  pot_val4 = analogRead(potentiometer4);
  
  // scale values of the potentiometers
  pot_val0 = map(pot_val0, 0, 1023, 0, 90);
  pot_val1 = map(pot_val1, 0, 1023, 0, 90);
  pot_val2 = map(pot_val2, 0, 1023, 0, 90);
  pot_val3 = map(pot_val3, 0, 1023, 0, 90);
  pot_val4 = map(pot_val4, 0, 1023, 0, 90);
  
  // sets position according to its scaled value
  servoMotor0.write(pot_val0);
  servoMotor1.write(pot_val1);
  servoMotor2.write(pot_val2);
  servoMotor3.write(pot_val3);
  servoMotor4.write(pot_val4);
}
```

## Robot Arm
![Screenshot (421)](https://user-images.githubusercontent.com/85647212/122820312-22040f80-d2e4-11eb-8929-1a8e1395995d.png)


