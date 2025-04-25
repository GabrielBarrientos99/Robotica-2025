# Servo

![image](https://github.com/user-attachments/assets/43437e21-a99c-4826-a6b7-138c996b1e10)

### Cables de llegada

![image](https://github.com/user-attachments/assets/81ffaa0a-f2aa-4699-b761-57795aaa3af0)

![WhatsApp Image 2025-04-25 at 5 12 34 PM](https://github.com/user-attachments/assets/552ed50f-7c63-4d83-9145-e2e000414e90)

### Estructura general
![WhatsApp Image 2025-04-25 at 5 12 35 PM](https://github.com/user-attachments/assets/344008ec-ce98-41d2-95ed-b73ebab8cb83)

```cpp
este es el 2
/*
 Controlling a servo position using a potentiometer (variable resistor)
 by Michal Rinott <http://people.interaction-ivrea.it/m.rinott>

 modified on 8 Nov 2013
 by Scott Fitzgerald
 http://www.arduino.cc/en/Tutorial/Knob
*/

#include <Servo.h>

Servo myservo;  // create Servo object to control a servo

int potpin = A0;  // analog pin used to connect the potentiometer
int val;    // variable to read the value from the analog pin

void setup() {
  myservo.attach(9);  // attaches the servo on pin 9 to the Servo object
}

void loop() {
  val = analogRead(potpin);            // reads the value of the potentiometer (value between 0 and 1023)
  val = map(val, 0, 1023, 0, 180);     // scale it for use with the servo (value between 0 and 180)
  myservo.write(val);                  // sets the servo position according to the scaled value
  delay(15);                           // waits for the servo to get there
}
```
# Ejercicio 2
Usar el potenciometro para controlar el angulo del servo

# Ejercicio 3
![image](https://github.com/user-attachments/assets/bf6b7cf5-f01b-4fc8-9d8d-5c27e07313b3)

![WhatsApp Image 2025-04-25 at 5 45 26 PM](https://github.com/user-attachments/assets/e3f0c4fc-5000-4ed3-bd06-d4daa518119e)

![WhatsApp Image 2025-04-25 at 5 45 04 PM](https://github.com/user-attachments/assets/fd2a625c-288b-4c59-96a4-56882aa25349)


```cpp
#include <Servo.h>
Servo servo1;
int servopin=3;
int angulo = 0;
int botonPin1=6;
int botonPin2=7;
int estado1=0;
int estado2=0;
void setup() {
  servo1.attach(servopin);
  pinMode(botonPin1,INPUT);
  pinMode(botonPin2,INPUT);
  pinMode(botonPin1,INPUT_PULLUP);
  pinMode(botonPin2,INPUT_PULLUP);
  servo1.write(angulo);

}

void loop() {
  estado1 = digitalRead(botonPin1);
  estado2 = digitalRead(botonPin2);
  if(estado1 == LOW){
    angulo++;
    if(angulo>=180){
      angulo=180;
    }
  } 
  if(estado2 == LOW){
    angulo--;
    if(angulo<=0){
      angulo=0;
    }
  } 
  servo1.write(angulo);
  delay(10);
}
```

# Ejercicio 4

![image](https://github.com/user-attachments/assets/b2a5f514-09ae-4d58-b0bb-17de27f29a3e)

![WhatsApp Image 2025-04-25 at 5 59 15 PM](https://github.com/user-attachments/assets/96da64a9-c939-45e2-8451-8d2ff2a0233b)


```cpp
#include <Servo.h>

Servo myservo;  // create Servo object to control a servo
int buttonPin = 6;//unico boton en pin 6
int estadoBoton=0;
int pos = 0;    // variable to store the servo position
bool invertirBoton = true;
void setup() {
  myservo.attach(3);  // attaches the servo on pin 9 to the Servo object
  pinMode(buttonPin,INPUT);
  pinMode(buttonPin,INPUT_PULLUP);
  myservo.write(pos);
}

void loop() {
  estadoBoton = digitalRead(buttonPin);
  if(estadoBoton==LOW){
    if(invertirBoton){
    for (pos = 0; pos <= 90; pos += 1) { // goes from 0 degrees to 90 degrees
      
      myservo.write(pos);              // tell servo to go to position in variable 'pos'
      delay(15);                       // waits 15 ms for the servo to reach the position
    }
    }
    else{
    for (pos = 90; pos >= 0; pos -= 1) { // goes from 90 degrees to 0 degrees
      myservo.write(pos);              // tell servo to go to position in variable 'pos'
      delay(15);                       // waits 15 ms for the servo to reach the position
    }
    }
  }
  invertirBoton = !invertirBoton;
}
```
