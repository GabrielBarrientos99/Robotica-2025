## Estructura del Arduino

![image](https://github.com/user-attachments/assets/4dc8e957-8513-4d27-ba32-e722bb53429a)

### Botón de Reset (Reset button)

- Reinicia el programa cargado, empezando desde el principio
```
Ejemplo:
    Si tu codigo enciende o apaga un LED, presionar este botón volverá a ejecutar este ciclo desde el inicio
```

### Puerto USB (USB interface)

- Se conecta a la computadora para:

  1. Cargar programas (código).
  2. Enviar/recibir datos (comunicación serial).

```
Ejemplo:
    Serial.println("Hola desde Arduino!");
```

### LEDs indicadores

**LED L:** Es una luz incorporada en el Arduino, conectada al pin 13 (no necesitas cables para probarla).

**LED TX** y **RX**:

- TX = Transmitir.

- RX = Recibir.

 ```
Ejemplo:
    Estas luces parpadean cuando el Arduino se está comunicando con la computadora.
```

### Puerto de energía

- Sirve para alimentar el Arduino si no lo tienes conectado por USB.

 ```
Ejemplo:
    Puedes usar una batería de 9 voltios si quieres que tu proyecto sea portátil (como un robot que camine sin estar conectado a la compu).
```



