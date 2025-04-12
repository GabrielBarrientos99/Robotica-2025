## Ejercicio 1

**Encender/Apagar Led con un botón:** Realizar un programa que haga prender/apagar un LED conectado en el pin 13 (el Arduino UNO ya tiene un LED integrado en este pin) mediante un botón conectado al pin 2.

### 📌 Diagrama de conexión:

[![imagen.png](https://i.postimg.cc/d1RtYbcz/imagen.png)](https://postimg.cc/9RMjPNMp)


### Código completo:

```cpp
int buttonPin = 2; // es el numero de pin donde se encuentra conectado el boton
int ledPin = 13; // es el numero de pin donde se encuentra conectado el led
bool isLighting = false; //defino esta variable para guardar el estado del led
// Función de configuración, se ejecuta una sola vez al iniciar
void setup() {
  pinMode(buttonPin, INPUT); //seteo el pin del boton en modo entrada
  pinMode(ledPin, OUTPUT); //seteo el pin del LED en modo salida
  pinMode(buttonPin, INPUT_PULLUP); //seteo el pin del boton como una resistencia a alta
}
// Función loop, se ejecuta continuamente
void loop() {
  if(digitalRead(buttonPin) == LOW){ // si el boton ha sido presionado
    delay(10); // retardo usado para evitar el rebote
    if(digitalRead(buttonPin) == LOW){ // confirmo otra vez si el boton ha sido presionado
      reverseLED(); //Encender o apagar el led
      while(digitalRead(buttonPin) == LOW); //Espera que suelte
      delay(10);
    }
  }
}

void reverseLED(){
  if(isLighting){
    digitalWrite(ledPin, LOW);// apago el LED
    isLighting = false; //almacena el estado del led
  }else{
    digitalWrite(ledPin, HIGH); // enciendo el LED
    isLighting = true; //almacena el estado del led
  }
}
```
