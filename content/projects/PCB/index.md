---
title: "custom_PCBs.txt"
date: 2024-10-01
draft: false
---

During my first year on the [Olin's Formula SAE Team](https://www.olinelectricmotorsports.com), I designed and implemented **three custom PCB boards** for our electric vehicle: the **throttle board**, **precharge and discharge board**, and the **battery management system (BMS) board**. I utilized **KiCAD**, an open-source PCB design software, which enabled the use of specialized components and custom footprints.

## Battery Management Systems Board

The first board I developed was our **Battery Management System (BMS) board**. This critical system is responsible for **monitoring the voltage and temperature of each cell** in our battery pack, as well as **balancing the cells** to ensure voltage parity. This is crucial for the safety and longevity of the battery pack and prevents overheating.

My process began with **schematic design**, outlining all board components. I organized the schematic into functional blocks, including:

-   The **Atmega 16m1 microcontroller** and its supporting circuitry
-   The **CAN transceiver** for robust communication
-   **Daisy-Chain IsoSPI interface** for communication with BMS monitoring ICs
-   **BMS Shutdown relay** for safety control
-   Status indicating LEDs
-   A **current sensor trigger** for overcurrent detection
-   **Ground short detection** for fault mitigation

The subsequent step was **PCB layout design**, which involved strategically placing components and routing traces while considering various constraints. This included minimizing the board's physical footprint, shortening trace lengths, mitigating noise susceptibility by component placement, and reducing the number of vias. This iterative process resulted in a production-ready layout.

<div align="center">
    BMS layout
    <img src="/images/pcb/bms.png" alt="layout for bms" width="800" height="350">
</div>

## Precharge and Discharge Board

The second board I designed was the **precharge and discharge board**. This board is essential for **safely precharging components** upon startup and **discharging the system's energy** during shutdown. This prevents damage from sudden power surges and ensures operational safety.

<div align="center">
    Simple block diagram of where it fits in the car
    <img src="/images/pcb/block_prech.png" alt="block diagram" width="500" height="350">
</div>

This board's design was simpler, focusing on:

-   A **precharge relay** to limit inrush current during startup
-   A **discharge relay** to safely dissipate stored energy during shutdown

These relays were controlled by another board within the vehicle.

<div align="center">
    Precharge and Discharge layout
    <img src="/images/pcb/layout_pre.png" alt="layout for Precharge and Discharge" width="500" height="450">
</div>

Both the BMS and Precharge/Discharge boards are located in the car's **Service Section**, the high-voltage area, which I also helped assemble.

<div align="center">
    Service Section, arrow points to BMS Core and circled is the Precharge and Discharge board
    <img src="/images/pcb/service_section.png" alt="layout for Precharge and Discharge" width="600" height="450">
</div>

## Throttle Board

The final PCB I designed that year was the **throttle board**. This board is responsible for **reading the position of two linear potentiometers** on the throttle pedal and **transmitting this data to the motor controller via CAN**. It also incorporates an **inertial switch** for immediate vehicle shutdown in case of rollover.

Key components included:

-   The **Atmega 16m1 microcontroller**
-   A **CAN transceiver** for communication
-   **Two op-amp circuits** to interface with the linear potentiometers
-   An **inertial switch** for safety

The dual potentiometers provide redundancy for safety, ensuring against uncontrolled acceleration. The board also receives **brake pressure sensor data over CAN** from another board to prevent simultaneous acceleration and braking. Ultimately, the throttle board **sends the desired power level to the motor controller via CAN**.

<div align="center">
    Throttle layout, I prioritized the electronics being as small as possible to fit diagram in case a quick fix was needed
    <img src="/images/pcb/layout_throttle.png" alt="layout for throttle" width="900" height="450">
</div>

## Conclusion

Through this project, I gained significant experience in **schematic design, PCB layout, and the PCB manufacturing process**. I also developed my ability to **collaborate within a team** to ensure the boards integrated effectively with the vehicle's other systems. This was a valuable experience, and I am excited to take on the role of the **new electrical lead** for the team next year!