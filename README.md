// Servo-with-Potentiometer
//Servo Control using Potentiometer


#include <ESP32Servo.h>
#define VCC2 26 // define pin 5 or any other digial pin here as VCC2
#define GND2 33 // define pin 2 or any other digital pin as Ground 2

Servo servo1;

void setup(){
 servo1.attach(19);
 pinMode(VCC2,OUTPUT);//define a digital pin as output
 digitalWrite(VCC2, HIGH);// set the above pin as HIGH so it acts as 5V

 pinMode(GND2,OUTPUT);//define a digital pin as output
 digitalWrite(GND2, LOW);// set the above pin as LOW so it acts as Ground
}
void loop(){
  int p = analogRead(35);
 p = map(p,0,4095,0,180);
 servo1.write(p);
 for(int i=0;i<=180;i++){
 servo1.write(p); 
 delay(15);
 }
 for(int i=180;i>=0;i--){
 servo1.write(p); 
 delay(15);
 }
}
