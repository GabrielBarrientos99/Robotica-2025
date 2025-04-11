## Ejercicio 3: Display de 7 segmentos - Contador de 0 a 9

Este ejercicio consiste en crear un contador del **0 al 9** usando un display de **7 segmentos** controlado por Arduino.

---

### Diagrama de conexión del circuito:

Conecta el display de 7 segmentos como se muestra en la siguiente imagen:

![image](https://github.com/user-attachments/assets/6e7e7101-73bf-4e54-a789-591307602ccf)


---

### Código completo y comentado:

Este código realiza un conteo repetitivo del número 0 al 9, mostrando cada número durante un segundo.

```cpp
// Pines conectados al display de 7 segmentos (a, b, c, d, e, f, g)
int segmentos[7] = {2, 3, 4, 5, 6, 7, 8};

// Tabla con valores para números del 0 al 9
byte numeros[10][7] = {
  {1,1,1,1,1,1,0}, // 0
  {0,1,1,0,0,0,0}, // 1
  {1,1,0,1,1,0,1}, // 2
  {1,1,1,1,0,0,1}, // 3
  {0,1,1,0,0,1,1}, // 4
  {1,0,1,1,0,1,1}, // 5
  {1,0,1,1,1,1,1}, // 6
  {1,1,1,0,0,0,0}, // 7
  {1,1,1,1,1,1,1}, // 8
  {1,1,1,1,0,1,1}  // 9
};

void setup() {
  // Inicializa todos los segmentos como salida
  for (int i = 0; i < 7; i++) {
    pinMode(segmentos[i], OUTPUT);
  }
}

void loop() {
  // Ciclo que muestra números del 0 al 9
  for (int num = 0; num <= 9; num++) {
    mostrarNumero(num); // Muestra el número actual
    delay(1000);        // Espera 1 segundo antes de cambiar
  }
}

// Función que activa los segmentos necesarios para mostrar el número
void mostrarNumero(int num) {
  for (int seg = 0; seg < 7; seg++) {
    digitalWrite(segmentos[seg], numeros[num][seg]);
  }
}
