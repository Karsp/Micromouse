# Micromouse Pro - Cybertech 2024 🐭🤖

![Status](https://img.shields.io/badge/Status-En%20Desarrollo-yellow)
![Platform](https://img.shields.io/badge/Platform-Arduino/ESP32-blue)

## 📌 Introducción
Este repositorio contiene el sistema de navegación, mapeo y resolución de laberintos para nuestro robot de competición diseñado para la categoría **Cybertech Pro 2024**. 

El desafío consiste en navegar de forma autónoma por un laberinto de 8x8 o de 16x16 casillas, identificar el camino óptimo y alcanzar el centro en el menor tiempo posible. Nuestro enfoque se centra en la eficiencia algorítmica y la robustez del control mediante sensores de proximidad.

## 🎯 Objetivo
Desarrollar un sistema capaz de:
1.  **Explorar** un entorno desconocido en tiempo real.
2.  **Mapear** la estructura del laberinto mediante una matriz de nodos y muros.
3.  **Resolver** el laberinto utilizando el algoritmo de Trémaux para garantizar la llegada a la meta sin bucles infinitos.

## 🛠️ Hardware Actual
* **Movilidad:** 2 Motores DC con ruedas independientes (Tracción diferencial).
* **Sensores:** 3 Sensores de proximidad (Izquierda, Centro, Derecha) para detección de obstáculos y alineación.
* **Estado:** Prototipo en fase de construcción y pruebas de odometría.

## 📂 Documentación Detallada
Para facilitar la comprensión del proyecto, hemos dividido la documentación técnica:
* [Lógica de Navegación y Algoritmos](./docs/algoritmos.md)
* [Estructura de Datos y Mapeo](./docs/mapeo.md)
* [Especificaciones de Hardware](./docs/hardware.md)