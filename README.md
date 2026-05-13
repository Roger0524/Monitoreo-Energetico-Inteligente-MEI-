# Monitoreo Energetico Inteligente (MEI)

![TRL](https://img.shields.io/badge/TRL-5-blue)
![Arduino](https://img.shields.io/badge/Arduino-Uno-blue)
![License](https://img.shields.io/badge/License-MIT-green)

## 📋 Descripción
Sistema inteligente de monitoreo y control del consumo energético desarrollado como proyecto de grado para la Universidad Nacional Abierta y a Distancia (UNAD). El sistema permite medir variables eléctricas en tiempo real, identificar patrones de consumo y ejecutar acciones de control automatizado.

## 👤 Autor
- Roger Andrés Sauméth Visbál

## 🎯 Objetivos

### Objetivo General
Diseñar un sistema inteligente de monitoreo y control del consumo energético para mejorar la eficiencia en el uso de la energía eléctrica en contextos residenciales, institucionales y comerciales.

### Objetivos Específicos
1. Analizar la situación actual del consumo energético
2. Diseñar la arquitectura técnica del sistema
3. Desarrollar criterios de control automatizado
4. Estimar el impacto potencial del sistema

## 🔧 Componentes del Hardware

| Componente | Cantidad | Especificación |
|------------|----------|----------------|
| Arduino Uno R3 | 1 | Microcontrolador ATmega328P |
| LCD 16x2 | 1 | Display con interfaz 4 bits |
| Sensor LDR | 1 | Fotoresistencia para luminosidad |
| Sensor TMP36 | 1 | Sensor de temperatura analógico |
| HC-SR04 | 1 | Sensor ultrasónico de distancia |
| LEDs | 3 | Indicadores visuales (D9, D5, D8) |
| Resistencias 220Ω | 3 | Para protección de LEDs |
| Protoboard | 1 | Para interconexión |

## 📊 Funcionalidades

### Monitoreo en Tiempo Real
- **Voltaje (V):** 5.0V (alimentación del sistema)
- **Corriente (I):** Estimada según estados de carga (0.09A base + 0.02A por LED activo)
- **Potencia (W):** Calculada mediante P = V × I

### Control Automatizado
El sistema activa LEDs indicadores según umbrales predefinidos:
- **Luminosidad (L):** LED D9 se activa cuando L ≥ 5
- **Temperatura (T):** LED D5 se activa cuando Temp > 30°C
- **Distancia (D):** LED D8 se activa cuando Dist < 20 cm

### Interfaz de Usuario
- Display LCD 16x2 con caracteres personalizados
- Secuencia de inicio animada ("MEI" + barra de carga)
- Indicadores circulares (vacío/lleno) para estados de sensores

## 🏗️ Arquitectura del Sistema

### Capa de Adquisición
Sensores LDR (A2), TMP36 (A3) y HC-SR04 (D6/D10) capturan variables ambientales.

### Capa de Procesamiento
Arduino Uno ejecuta el firmware que:
- Lee y procesa señales de sensores
- Evalúa umbrales de activación
- Calcula parámetros eléctricos
- Controla actuadores (LEDs)

### Capa de Visualización
LCD 16x2 muestra dashboard en tiempo real con:
- Variables eléctricas (V, I, W)
- Estados de sensores (T, D, L)

## 💻 Firmware

### Librerías Utilizadas
- `LiquidCrystal.h` - Control del display LCD

### Estructura del Código
```cpp
void setup() {
  // Inicialización de LCD
  // Creación de caracteres personalizados
  // Configuración de pines
  // Secuencia de inicio "MEI"
}

void loop() {
  // Lectura de sensores
  // Procesamiento y conversión
  // Evaluación de umbrales
  // Cálculo de consumo
  // Actualización de LCD
  delay(100); // 10 Hz
}
