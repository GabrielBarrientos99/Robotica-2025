## Ejercicio 1

**Parpadeo de un LED:** Realizar un programa que haga parpadear un LED conectado en el pin 13 (el Arduino UNO ya tiene un LED integrado en este pin).

### 📌 Diagrama de conexión:

![image](https://github.com/user-attachments/assets/b8f4ce7b-4f3e-4694-acc4-5bc831f2d477)


### Código completo:

```cpp
// Función de configuración, se ejecuta una sola vez al iniciar
void setup() {
  pinMode(13, OUTPUT); // Configura el pin 13 como salida para el LED
}

// Función loop, se ejecuta continuamente
void loop() {
  digitalWrite(13, HIGH); // Enciende el LED (envía voltaje alto)
  delay(1000);            // Espera 1 segundo (1000 milisegundos)

  digitalWrite(13, LOW);  // Apaga el LED (envía voltaje bajo)
  delay(1000);            // Espera otro segundo
}
