## Estructura del Arduino UNO

![Arduino UNO](https://github.com/user-attachments/assets/4dc8e957-8513-4d27-ba32-e722bb53429a)

---

### Botón de Reinicio (Reset button)

| Función | Imagen |
|---------|--------|
| <ul><li>Este botón permite reiniciar el programa que está ejecutando tu Arduino.</li><li>Equivale a apagar y volver a encender la placa rápidamente sin desconectar cables.</li></ul> | ![Botón Reset](https://github.com/user-attachments/assets/6e1e0944-0fbf-4211-8c76-61095b17706b) |


**Ejemplo práctico:**  
> Si tienes un programa que hace parpadear un LED, al presionar el botón de reset, el LED comenzará nuevamente su ciclo desde el principio.

---

### Puerto USB (USB Interface)

| Función | Imagen |
|---------|--------|
| <ul><li>**Cargar programas (sketches)** escritos desde tu computadora.</li><li>**Comunicación Serial:** Enviar y recibir datos entre el Arduino y la computadora.</li></ul> | ![image](https://github.com/user-attachments/assets/86bfe15f-ab3a-4239-8fd9-91ed826d8f84) |

 
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

### LEDs Indicadores

Arduino tiene varios LEDs incorporados que indican diferentes estados:

| Función | Imagen |
|---------|--------|
| <ul><li>**LED L:** Conectado internamente al pin 13. Muy útil para pruebas rápidas sin necesidad de usar componentes adicionales.</li><li>**LED TX (Transmit):** Parpadea cuando Arduino envía datos a la computadora.</li><li>**LED RX (Receive):** Parpadea cuando Arduino recibe datos desde la computadora.</li></ul> | ![image](https://github.com/user-attachments/assets/d9b73693-16a1-4a07-8313-7dd4e932c987) |

**Ejemplo práctico:**  
> Al subir un programa al Arduino desde el IDE, los LEDs TX y RX parpadearán indicando que hay transmisión de datos.

---

### Puerto de Energía (DC Interface)

| Función | Imagen |
|---------|--------|
| <ul><li>Permite alimentar el Arduino sin necesidad del cable USB.</li></ul> | ![image](https://github.com/user-attachments/assets/3df23306-9a58-4d0e-b395-f6c1f3b5851f)|

- Útil para proyectos autónomos o portátiles.
- Recomendado usar una fuente externa (por ejemplo, una batería de 9V).

**Ejemplo práctico:**
> Si estás construyendo un robot móvil o un dispositivo portátil, utiliza una batería conectada a este puerto para darle energía al Arduino.

---

### Sección de Energía (Power)

| Función | Imagen |
|---------|--------|
| <ul><li>Aquí encontrarás varios pines esenciales para alimentar sensores y otros dispositivos externos</li></ul> | ![image](https://github.com/user-attachments/assets/79131d25-c216-4c2b-884c-2b70141a3e80) |

Caracteristicas especificas:

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

| Función | Imagen |
|---------|--------|
| <ul><li>Numerados del 0 al 13 (14 pines totales)</li><li>Entrada digital (digitalRead())</li><li>Salida digital (digitalWrite())</li></ul> | ![image](https://github.com/user-attachments/assets/42d66f35-baf7-469a-ada4-5b0e4202b1a4)|

**Ejemplo práctico:**

 ```cpp
pinMode(8, OUTPUT);           // Pin 8 como salida digital
digitalWrite(8, HIGH);        // Encender LED conectado al pin 8
 ```


### Pines Analógicos (Analog Inputs)

| Función | Imagen |
|---------|--------|
| <ul><li>Numerados del A0 al A5 (6 pines)</li><li>Lectura analógica de 10-bit (0-1023) con analogRead()</li><li>Voltaje de referencia: 0-5V (por defecto)</li></ul> | ![image](https://github.com/user-attachments/assets/35fa84ef-ff1e-4d10-ada6-787390e69a3a)|


**Ejemplo práctico:**

 ```cpp
int sensorValue = analogRead(A0);  // Leer sensor conectado al pin A0
Serial.println(sensorValue);       // Mostrar valor leído en monitor serial
 ```






