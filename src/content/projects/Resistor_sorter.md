---
title: "Automated Resistor Sorter"
description: "Designed the custom PCB and electromechanical control systems for an automated resistor sorting machine, focusing on analog measurement and rapid hardware iteration."
pubDate: "May 2025"
heroImage: "/post_img.webp"
badge: "PCB Design"
---

## Overview
As part of Olin College's Principles of Integrated Engineering (PIE) course, I collaborated on a 6-person multidisciplinary team to build "The Resistance"—an electromechanical system designed to automatically singulate, measure, and sort bulk resistors into specific bins based on their ohm values. 

## My Role & The Tech Stack
* **Role:** Electrical & Systems Engineer
* **Hardware:** KiCad, Custom PCB, [Arduino / ESP32], [A4988 Stepper Drivers / Servos]
* **Software:** C++, Serial Debugging
* **Skills:** Analog-to-Digital Conversion (ADC), Hardware Debugging, Multidisciplinary Integration

---

## The Engineering Process

### 1. Measurement Logic & Circuit Design
The core electrical challenge was accurately reading the resistance values on the fly. I designed a measurement circuit utilizing a voltage divider network connected to the microcontroller's Analog-to-Digital Converter (ADC). By applying a known voltage and measuring the drop across the unknown sorted resistor, the software could calculate its exact ohmic value and trigger the mechanical sorting routine.

### 2. Custom PCB Architecture
To ensure reliable operation and avoid the notorious "rat's nest" of breadboard wiring, I designed a custom PCB in **KiCad**. This board served as the central nervous system for the project, consolidating the microcontroller, the analog measurement circuitry, and the motor drivers needed to control the singulation and sorting mechanisms. 

![PCB Layout](/post_img.webp)
*Caption: The custom PCB layout designed in KiCad, routing power and logic for the motor drivers and measurement circuits.*

### 3. Integration & Hardware Debugging
While the isolated electrical systems performed well, integrating them with the mechanical hopper and sorting mechanisms introduced significant challenges. We encountered issues with [mechanical jamming / ADC sensor noise from the motors / power draw drops], which occasionally caused the system to misread or misplace a resistor. 

I led the electrical debugging process, utilizing oscilloscopes and multimeters to trace voltage drops and isolate signal noise. This rapid iteration and troubleshooting process was the most intensive and educational phase of the project.

---

## Outcomes & Lessons Learned
Ultimately, while the final integrated machine did not achieve a 100% perfect sorting success rate, the project was a massive success in terms of hardware education. 

If we had another iteration to improve the system, I would implement **hardware-level low-pass filtering** on the PCB to clean up the ADC readings, and I would add optical limit switches to the mechanical track to give the microcontroller strict physical confirmation before attempting a measurement. Learning how to design a PCB that survives the chaos of moving mechanical parts profoundly changed my approach to systems engineering.

## Image Gallery
*(Add photos of the bare PCB, the fully wired electronics box, and the complete physical machine here)*

![Complete Machine](/post_img.webp)
*Caption: The fully integrated electromechanical resistor sorter.*