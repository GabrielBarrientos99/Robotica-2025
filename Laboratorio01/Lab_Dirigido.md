## Estructura del Arduino UNO

![Arduino UNO](https://github.com/user-attachments/assets/4dc8e957-8513-4d27-ba32-e722bb53429a)

---

### 🔄 Botón de Reinicio (Reset button)

Este botón permite reiniciar el programa que está ejecutando tu Arduino.
- Equivale a apagar y volver a encender la placa rápidamente sin desconectar cables.

**Ejemplo práctico:**  
> Si tienes un programa que hace parpadear un LED, al presionar el botón de reset, el LED comenzará nuevamente su ciclo desde el principio.

---

### 🔌 Puerto USB (USB Interface)

Permite conectar el Arduino a tu computadora. Tiene dos funciones clave:

1. 📂 **Cargar programas (sketches)** escritos desde tu computadora.
2. 📡 **Comunicación Serial:** Enviar y recibir datos entre el Arduino y la computadora.

**Ejemplo de comunicación serial:**

```cpp
void setup() {
  Serial.begin(9600);              // Iniciar comunicación serial
  Serial.println("Hola Arduino!"); // Enviar mensaje a la computadora
}

void loop() {
  // Tu código aquí
}
```

---

### 💡 LEDs Indicadores

Arduino tiene varios LEDs incorporados que indican diferentes estados:

- **LED L:** Conectado internamente al pin 13. Muy útil para pruebas rápidas sin necesidad de usar componentes adicionales.
- **LED TX (Transmit):** Parpadea cuando Arduino envía datos a la computadora.
- **LED RX (Receive):** Parpadea cuando Arduino recibe datos desde la computadora.

**Ejemplo práctico:**  
> Al subir un programa al Arduino desde el IDE, los LEDs TX y RX parpadearán indicando que hay transmisión de datos.

---

### 🔋 Puerto de Energía (DC Interface)

Permite alimentar el Arduino sin necesidad del cable USB.

- Útil para proyectos autónomos o portátiles.
- Recomendado usar una fuente externa (por ejemplo, una batería de 9V).

**Ejemplo práctico:**
> Si estás construyendo un robot móvil o un dispositivo portátil, utiliza una batería conectada a este puerto para darle energía al Arduino.

---

### ⚡ Sección de Energía (Power)

Aquí encontrarás varios pines esenciales para alimentar sensores y otros dispositivos externos:

| Pin   | Función                                            | Ejemplo de uso                                |
|-------|----------------------------------------------------|-----------------------------------------------|
| `GND` | Tierra, necesaria para cualquier circuito externo. | Siempre conecta el pin GND con sensores y LEDs |
| `5V`  | Proporciona voltaje estable de 5 voltios.          | Conectar sensores que operen a 5V             |
| `3.3V`| Proporciona voltaje estable de 3.3 voltios.        | Para sensores o módulos que usen 3.3V         |
| `Vin` | Entrada para voltaje externo (entre 7 y 12 voltios)| Usar baterías externas o fuentes adicionales  |

**Ejemplo práctico:**
> Si tu sensor necesita 5 voltios, conecta su pin positivo a `5V` y el pin negativo al pin `GND` del Arduino.

---

### Pines Digitales (Digital I/O)

Numerados del 0 al 13 (14 pines totales)

**Funcionalidades:**

- Entrada digital (digitalRead())

- Salida digital (digitalWrite())

- PWM (~) en pines 3,5,6,9,10,11 (analogWrite())


### Pines Analógicos (Analog Inputs)

Numerados del A0 al A5 (6 pines)

**Funcionalidades:**

- Lectura analógica de 10-bit (0-1023) con analogRead()

- Voltaje de referencia: 0-5V (por defecto)




