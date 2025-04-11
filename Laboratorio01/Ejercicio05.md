## Ejercicio 5: Medir distancia con un sensor ultrasónico

Este ejercicio permite medir la distancia a un objeto usando el sensor ultrasónico **HC-SR04**, el cual funciona enviando una señal de sonido (no audible) y midiendo el tiempo que tarda en rebotar. Arduino calcula la distancia a partir de ese tiempo.

---


![image](https://github.com/user-attachments/assets/7f5ed7c8-d486-4e55-9e49-df1e85c33fad)


### Conexiones del sensor al Arduino

| Pin del HC-SR04 | Pin del Arduino |
|------------------|------------------|
| VCC              | 5V               |
| GND              | GND              |
| TRIG             | 2                |
| ECHO             | 3                |

> Asegúrate de conectar el pin **TRIG** a 2 y el pin **ECHO** a 3.

---

### Código completo para medir distancia:

```cpp
#define TRIG 2  // Pin de disparo
#define ECHO 3  // Pin de recepción

void setup() {
  Serial.begin(9600);        // Inicia la comunicación serial
  pinMode(TRIG, OUTPUT);     // TRIG como salida
  pinMode(ECHO, INPUT);      // ECHO como entrada
}

void loop() {
  long duracion, distancia;

  // Enviar un pulso de 10 microsegundos
  digitalWrite(TRIG, LOW);
  delayMicroseconds(2);
  digitalWrite(TRIG, HIGH);
  delayMicroseconds(10);
  digitalWrite(TRIG, LOW);

  // Leer el tiempo que tarda en recibir el eco
  duracion = pulseIn(ECHO, HIGH);

  // Calcular la distancia en centímetros
  distancia = duracion * 0.034 / 2;

  // Mostrar en el monitor serial
  Serial.print(\"Distancia: \");
  Serial.print(distancia);
  Serial.println(\" cm\");

  delay(500);  // Esperar medio segundo antes de la siguiente lectura
}
