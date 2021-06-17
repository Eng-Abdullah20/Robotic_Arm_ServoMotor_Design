# Robotic_Arm_ServoMotor_Design
//Robotic Arm Servo Motors Technical Description 
//1.	Hardware Description
//In this task, the circuit has been designed to be composed of a 5V DC voltage source and a microcontroller (Arduino Uno) with five servo motors. Each motor is controlled by a //separate 10KΩ potentiometer to allow each part of the robotic arm to move apart from the other parts. The five motors were connected to the digital pins from one to five, //respectively. Furthermore, the potentiometers were connected to the analog pins A5 to A1. 


//2.	Programing Description
//In order to have each servo motor to be controlled separately by one potentiometer the microcontroller had to be programmed to take the input from the potentiometer and move //the servo motor accordingly. First the connected servo motors and potentiometers have to be defined as follows. 
#include <Servo.h>
//Define the servos
Servo servo1;
Servo servo2;
Servo servo3;
Servo servo4;
Servo servo5;

int R1= A1;
int R2= A2;
int R3= A3;
int R4= A4;
int R5= A5;

//then, define a new variable for each potentiometer to save the value of the resistance once changed by the user. 


int valR1;
int valR2;
int valR3;
int valR4;
int valR5;

//Set every servo motor to its connected pin 
void setup()
{
servo1.attach(5);
servo2.attach(4);
servo3.attach(3);
servo4.attach(2);
servo5.attach(1);
  
}
/In a Void loop, assign the defined new variables for the potentiometers to the connected pin using the function “Analogread” to read the change resistance once changed by the //user. Then, using the function “map” assign the movement of the servo in degrees. Since all potentiometers are 10KΩ, 0Ω will be 0 degrees and 10KΩ will be 90 degrees.  //Finally, using “write” function for each servo motor will move according to the value of the assigned variable of the potentiometer. 
void loop()
{
 valR1=analogRead(R1);
 valR1= map (valR1, 0, 1023, 0, 90);
 servo1.write(valR1);
 delay(10);
 
 valR2=analogRead(R2);
 valR2= map (valR2, 0, 1023, 0, 90);
 servo2.write(valR2);
 delay(10);
 
 valR3=analogRead(R3);
 valR3= map (valR3, 0, 1023, 0, 90);
 servo3.write(valR3);
 delay(10);

 
 valR4=analogRead(R4);
 valR4= map (valR4, 0, 1023, 0, 90);
 servo4.write(valR4);
 delay(10);
 
 valR5=analogRead(R5);

 valR5= map (valR5, 0, 1023, 0, 90);
 servo5.write(valR5);
 delay(10);
}
