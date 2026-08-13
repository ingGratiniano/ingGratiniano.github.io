---
title: "Órgano Digital Profesional"
collection: portfolio
permalink: /portfolio/organo-digital
excerpt: "Desarrollo integral de un órgano digital profesional: motor de audio en C sobre Linux, sistemas de escaneo MIDI con reed switches, registros, pedalera y pedales de expresión con sensores HAL, y sistema de audio Hi-Fi 2.1 de diseño propio."
image: /images/organo_sin_fondo.png
date: 2025-08-01
---

**Proyecto integral en solitario (2025 – Actualidad)**

El órgano digital profesional es el proyecto más grande y completo de mi carrera. Abarca todas las áreas de la ingeniería electrónica: hardware, firmware, software, diseño de PCBs, acústica y mecánica. Cada componente fue diseñado, fabricado y programado por mí, desde el concepto hasta el producto funcional.

---
### ⚡ Sistema Inteligente de Encendido / Apagado Secuencial

**Descripción:** Desarrollo de un sistema de control basado en un microcontrolador dedicado que monitorea un pulsador de encendido/apagado (normalmente abierto). Dependiendo de la pulsación, el sistema activa de forma **secuencial y temporizada** cada uno de los subsistemas del órgano en el orden correcto:

1. **Iluminación** 
2. **SBC (Orange Pi)** con un retraso suficiente para que el sistema operativo arranque de forma estable y con este microcontroladores, LEDs RGB.
3. **Amplificadores de audio**, evitando picos de corriente y protegiendo los altavoces.

El mismo proceso se invierte al apagar, asegurando que cada componente se desconecte de forma segura y ordenada. Este sistema previene daños por encendidos bruscos o cortes inesperados de energía, prolongando la vida útil de todos los componentes del órgano, tal como lo haría un operador humano experimentado.

**Tecnologías:** Microcontrolador dedicado, electrónica de potencia, secuenciación por firmware.

![Sistema inteligente de encendido/apagado](/images/od4.jpg)

---

### 🧠 Motor de Audio (Software)

**Descripción:** Desarrollo de un motor de audio en C sobre Linux embebido (Orange Pi 5 Max / RK3588, Debian). El motor procesa las señales MIDI y genera audio en tiempo real con polifonía robusta y baja latencia.

**Tecnologías:** C, Linux embebido, ALSA, SCHED_FIFO (scheduling en tiempo real).

---

### ⌨️ Sistema de escaneo de teclados con Reed Switches

**Descripción:** Diseño y fabricación de PCBs para el escaneo de los dos teclados manuales. Cada tecla utiliza un **reed switch** (interruptor de lengüeta) en lugar de contactos físicos directos. Esta tecnología, superior a los contactos tradicionales, elimina el desgaste mecánico, previene la oxidación y suprime los rebotes de contacto, garantizando una detección de pulsación extremadamente fiable, duradera y con una respuesta digital limpia. El sistema envía la información al motor de audio a través de MIDI-USB.

**Tecnologías:** Reed switches, microcontroladores, MIDI, diseño de PCB (KiCad).

![Sistema de escaneo de teclados con reed switches](/images/od1.jpg)

---

### 🎛️ Sistema de registros y pistones

**Descripción:** Diseño y fabricación de la electrónica para los 16 registros y los pistones (3 fijos + 10 programables). Incluye el sistema de encendido secuencial inteligente e iluminación LED integrada.

**Tecnologías:** Microcontroladores, MIDI, diseño de PCB (KiCad), iluminación LED.

![Sistema de registros y pistones](/images/od3.jpg)

---

### 🦶 Pedalera MIDI con Reed Switches

**Descripción:** Diseño y fabricación de la electrónica para la pedalera, que permite a los organistas ejecutar las notas graves del instrumento. Siguiendo la misma filosofía que los teclados manuales, cada pedal utiliza un **reed switch**, ofreciendo las mismas ventajas de durabilidad, precisión y fiabilidad a largo plazo, sin los problemas de mantenimiento típicos de los contactos mecánicos convencionales.

**Tecnologías:** Reed switches, microcontroladores, MIDI, diseño de PCB.

---

### 🎚️ Pedales Expresivo y Crescendo con Sensores HAL

**Descripción:** Diseño e implementación de los pedales de expresión y crescendo utilizando tecnología de **sensores HAL (Efecto Hall)**. Esta tecnología, superior a los potenciómetros tradicionales, elimina el desgaste mecánico y ofrece una respuesta de posición mucho más precisa, suave y duradera, mejorando significativamente la experiencia interpretativa del organista.

**Tecnologías:** Sensores HAL (lineales), microcontroladores, MIDI.

---
### 🧩 Controladores de Teclados y Registros (PIC / MIDI-USB)

**Descripción:** El sistema cuenta con una red de microcontroladores PIC dedicados que funcionan como el sistema nervioso periférico del órgano.

- **Escaneo de Teclados y Pedalera:** Cada teclado manual (2) y la pedalera son escaneados mediante matrices de **reed switches**. Los microcontroladores PIC se encargan de leer estas matrices a alta velocidad, detectando cada pulsación y soltura de tecla con precisión.
- **Gestión de Registros y Pistones:** Un controlador PIC adicional se encarga del escaneo de los 16 registros (drawbars) y los pistones. No solo lee el estado de cada registro, sino que **controla la iluminación LED** para indicar qué registros y combinaciones de pistones están activos en todo momento.
- **Comunicación MIDI-USB:** Toda la información procesada por estos controladores (notas tocadas, cambios de registros, activación de pistones) es empaquetada en mensajes **MIDI** y enviada a la SBC (Orange Pi) a través de **USB**. Esto asegura una comunicación estandarizada, de baja latencia y fácilmente integrable con el motor de audio.
- **Firmware Propio:** Todo el firmware que gestiona el escaneo, el debounce de los reed switches, el control de LEDs y la comunicación MIDI-USB fue desarrollado por mí en C para la familia de microcontroladores PIC.

**Tecnologías:** Microcontroladores PIC, C, matrices de escaneo, USB-MIDI.

![Controladores PIC y sistema de registros](/images/od2.jpg)

---

### 🔊 Sistema de audio Hi-Fi 2.1

**Descripción:** Diseño y construcción del sistema de audio completo, incluyendo la amplificación y los altavoces (woofer y satélites), diseñados y fabricados a medida para garantizar una reproducción de sonido de alta fidelidad.

**Tecnologías:** Electrónica de audio, amplificadores, diseño acústico, altavoces.

---

### 🎵 Especificaciones generales

- **2 manuales** (teclados) con reed switches.
- **Pedalera** completa (teclado de pies) con reed switches.
- **16 registros**.
- **3 memorias fijas + 10 programables**.
- **Pedal expresivo y crescendo** con sensores HAL.
- **Motor de audio** con polifonía optimizada.

---

**Resultado final:** Un órgano digital profesional que integra tecnologías de detección de vanguardia (reed switches y sensores HAL) para garantizar una fiabilidad y durabilidad excepcionales, desarrollado de forma integral desde el concepto hasta el prototipo funcional. Todo el sistema, desde el motor de audio hasta los altavoces, es diseño y fabricación 100% propia.

[← Volver al Portafolio](/portfolio/)
