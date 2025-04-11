## Ejercicio 2: LED controlado con un botón

Programa que permite encender el LED conectado en el pin 13 cuando se presiona un botón.

### 📌 Diagrama de conexión:

![image](https://github.com/user-attachments/assets/7e4f4d84-921f-4ab9-a8bd-f8e7a88b6be0)


### 🔧 Código completo y comentado:

```cpp
// Declaración de variables para los pines
const int pinBoton = 2;  // Pin donde se conecta el botón
const int pinLed = 13;   // Pin del LED incorporado en Arduino

void setup() {
  pinMode(pinBoton, INPUT);   // Configura el pin del botón como entrada
  pinMode(pinLed, OUTPUT);    // Configura el pin del LED como salida
}

void loop() {
  // Lee el estado del botón (HIGH cuando se presiona)
  int estadoBoton = digitalRead(pinBoton);

  // Si el botón está presionado, enciende el LED
  if (estadoBoton == HIGH) {
    digitalWrite(pinLed, HIGH);  // Encender LED
  } else {
    digitalWrite(pinLed, LOW);   // Apagar LED
  }
}
