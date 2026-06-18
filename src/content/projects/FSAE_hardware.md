---
title: "FSAE Hardware Architecture"
description: "Designed and integrated custom KiCad PCBs for critical electric vehicle subsystems, including the BMS, throttle, and precharge circuits."
pubDate: "May 2025"
heroImage: "/pcb/bms.png"
badge: "PCB Design"
---

## Overview
During my first year on [Olin Electric Motorsports](https://www.olinelectricmotorsports.com) (Formula SAE), I was tasked with engineering the critical hardware required to safely operate our electric vehicle. I designed, routed, and integrated three custom PCBs from scratch using **KiCad**: the Battery Management System (BMS) core, the Throttle Board, and the Precharge/Discharge board. 

## My Role & The Tech Stack
* **Role:** Hardware Engineer (Progressed to Electrical Lead)
* **Hardware:** KiCad, Custom PCBs, Atmega 16m1 microcontrollers, CAN Transceivers
* **Protocols:** IsoSPI, CAN Bus Communication
* **Skills:** Schematic Architecture, High-Voltage Layout, Fault Mitigation, Safety Redundancy

---

## Core Hardware Subsystems

### 1. Battery Management System (BMS) Board
The BMS board is the most critical safety component of the tractive system. It is responsible for monitoring the voltage and temperature of every individual cell in our accumulator and balancing them to ensure voltage parity and prevent thermal runaway.

I organized the schematic into distinct functional blocks before moving to layout. The core architecture relies on an **Atmega 16m1 microcontroller** and a **Daisy-Chain IsoSPI interface** to communicate with the specialized BMS monitoring ICs. To ensure strict rules compliance and driver safety, I integrated hardware-level ground short detection, an overcurrent sensor trigger, and a dedicated BMS shutdown relay that can sever tractive power instantly.

![BMS Board](/pcb/bms.png)
*Caption: The completed Battery Management System board.*

### 2. Throttle Control & Safety Redundancy
The Throttle Board reads the driver's physical input and translates it into digital torque commands. To prevent uncontrolled acceleration, this board requires strict redundancy.

I designed two distinct op-amp circuits to interface with dual linear potentiometers on the physical pedal. An Atmega 16m1 processes these analog signals and broadcasts the desired power level to the motor controller via **CAN bus**. For safety, the board continuously checks for brake plausibility (receiving brake pressure sensor data over CAN) to ensure the driver isn't pressing both pedals simultaneously. I also integrated an inertial switch directly onto the board to trigger an immediate vehicle shutdown in the event of a rollover.

![Throttle PCB Layout](/pcb/layout_throttle.png)
*Caption: The KiCad layout for the Throttle Board. I heavily prioritized minimizing the footprint to fit within tight mechanical constraints.*

### 3. Precharge & Discharge Circuitry
*(Note: I will update this section with specific schematic details for the high-voltage precharge system, which safely limits inrush current to the motor controller capacitors before closing the main contactors).*

![Precharge Schematic](/pcb/schematic_pre.png)
*Caption: The logical block schematic for the Precharge and Discharge system.*

![Precharge Layout](/pcb/layout_pre.png)
*Caption: The physical board layout routing the high-voltage precharge lines.*

---

## Outcomes & Leadership Progression
Navigating the full lifecycle of these three boards—from raw schematic design to strict layout routing and final manufacturing—solidified my hardware engineering foundation. The success of these sub-systems and my ability to collaborate across mechanical and firmware boundaries directly contributed to my selection as the **Electrical Lead** for the following season.