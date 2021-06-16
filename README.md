# servoMotorCircuit-robotArm
This is a five servo motors circuit controlled by potentiometers, each potentiometer controls one servo motor using Arduino UNO microcontroler.
Servo motor is on inital angle 0, and it can rotate for 90 digrees maximum.
The simulation is done using Tinkercad online software.

## circuit link: 
https://www.tinkercad.com/things/fIu9mjbMDmG-servo-motor/editel

## circuit figure:
![servo motor](https://user-images.githubusercontent.com/85647212/122301036-cf53dd80-cf08-11eb-8b56-befc35adb4ab.png)

Arduino code:
#include <Servo.h> //servo motor library

// Crate "Servo" object to control the servo motor
Servo servoMotor0;
Servo servoMotor1;
Servo servoMotor2;  
Servo servoMotor3; 
Servo servoMotor4;  

// Analog pin for the potentiometer 
int potentiometer0 = A0;
int potentiometer1 = A1;
int potentiometer2 = A2;
int potentiometer3 = A3;
int potentiometer4 = A4;

// variable to read values from potentiometers
int pot_val0;
int pot_val1;
int pot_val2;
int pot_val3;
int pot_val4;
  
void setup()
{
  // attaches servo objects to its own pins 
  servoMotor0.attach(3);
  servoMotor1.attach(5);
  servoMotor2.attach(6);
  servoMotor3.attach(9);
  servoMotor4.attach(10);
}

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

