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
