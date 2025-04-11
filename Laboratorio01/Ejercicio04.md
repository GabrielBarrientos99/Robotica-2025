## Ejercicio 4: Variar la intensidad de un LED usando PWM

La **modulación por ancho de pulso (PWM)** consiste en alternar rápidamente entre encendido y apagado para controlar la potencia entregada a un componente (como un LED o un motor). La proporción del tiempo que permanece encendido se llama **ciclo de trabajo (duty cycle)** y se expresa en porcentaje.

Por ejemplo:
- Un **ciclo de trabajo del 50%** significa que la señal está encendida la mitad del tiempo y apagada la otra mitad.
- Al variar este ciclo, regulas la potencia o la intensidad del LED.

---

### Conexión del LED al Arduino (pin 9):

Conecta un LED al pin **9** del Arduino con una resistencia de 220Ω aproximadamente.

![image](https://github.com/user-attachments/assets/3ea987a9-6983-4039-98aa-53b76969d7e4)


---

### Código completo y comentado:

Este programa hace variar gradualmente la intensidad del LED conectado al pin 9.

```cpp
const int pinLED = 9; // Pin PWM donde está conectado el LED

void setup() {
  pinMode(pinLED, OUTPUT);  // Configura el pin 9 como salida
}

void loop() {
  // Aumentar gradualmente el brillo del LED
  for (int brillo = 0; brillo <= 255; brillo += 5) {
    analogWrite(pinLED, brillo); // Ajusta brillo del LED (0-255)
    delay(30);                   // Espera para observar el cambio
  }

  // Disminuir gradualmente el brillo del LED
  for (int brillo = 255; brillo >= 0; brillo -= 5) {
    analogWrite(pinLED, brillo); // Ajusta brillo del LED (255-0)
    delay(30);                   // Espera para observar el cambio
  }
}
