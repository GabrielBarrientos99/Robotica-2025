## Ejercicio 3 (Combina el ejercicio 1 + 2)

**Encender/Apagar Led con un botón + imprimir un contador serial:** Realizar un programa que haga prender/apagar un LED conectado en el pin 13 (el Arduino UNO ya tiene un LED integrado en este pin) mediante un botón conectado al pin 2.

### 📌 Diagrama de conexión:

[![imagen.png](https://i.postimg.cc/d1RtYbcz/imagen.png)](https://postimg.cc/9RMjPNMp)


### Código completo:


```cpp
int buttonPin = 5 ;
int ledPin = 13;
int counter = 0;
bool isLighting = false;
void setup() {
 
  // put your setup code here, to run once:
  pinMode(buttonPin,INPUT);
  pinMode(ledPin,OUTPUT);
  Serial.begin(9600);
  pinMode(buttonPin,INPUT_PULLUP);
}
 
void loop() {
  // put your main code here, to run repeatedly:
  if(digitalRead(buttonPin)== LOW){
    delay(10);
    if(digitalRead(buttonPin)== LOW){
    counter++;
    Serial.println(counter);
    reverseLed();
    while(digitalRead(buttonPin)== LOW);
      delay(10);
    }
  }
}
void reverseLed(){
  if(isLighting){
    digitalWrite(ledPin, LOW);
    isLighting = false;
  }
  else{
    digitalWrite(ledPin,HIGH);
    isLighting=true;
  }
}
```