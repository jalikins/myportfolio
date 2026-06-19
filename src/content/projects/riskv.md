---
title: "RISC32I Processor FPGA Implementation"
description: "Designed and implemented a custom multicycle RISC-V processor architecture in SystemVerilog, deployed to an FPGA to execute custom assembly logic."
pubDate: "December 2025"
heroImage: "/post_img.webp"
badge: "Computer Architecture"
---

## Overview
This project involved the complete, scratch-built design of an unpipelined, multicycle 32-bit RISC-V integer microprocessor (RV32I). Working on a three-person engineering team, we mapped the processor's datapath, wrote the hardware logic in SystemVerilog, and successfully deployed the architecture to an iceBlinkPico FPGA board to execute custom software.

## My Role & The Tech Stack
* **Team Division:** Collaborated on a 3-person team to handle RTL design, testbench simulation, and hardware-software integration.
* **Hardware:** iceBlinkPico FPGA Board
* **Software:** SystemVerilog, RISC-V Assembly, OSS CAD Suite, Icarus Verilog
* **Skills:** Multicycle Datapath Design, State Machine Logic, Memory Mapping, Hardware Simulation

---

## The Engineering Process

### 1. Processor Architecture & Datapath Design
We designed the processor utilizing a strict **Harvard architecture**, establishing a unified 32-bit address space but maintaining separate 4kB instruction and 4kB data memories. The core logic required us to implement the base RV32I instruction set. Because this was a multicycle processor, we engineered a complex finite state machine to precisely control the flow of data through the Fetch, Decode, Execute, Memory, and Writeback stages without structural hazards.

### 2. RTL Simulation & Verification
Before ever touching physical hardware, the design had to be meticulously verified. We utilized the OSS CAD Suite and **Icarus Verilog (iverilog)** to build comprehensive testbenches. By simulating representative examples of each class of RV32I instructions, we were able to observe signal waveforms and verify the proper operation of the arithmetic logic unit (ALU) and control structures in software.

### 3. Hardware Deployment & Assembly Execution
Once the SystemVerilog passed simulation, we synthesized the design and flashed it to the iceBlinkPico FPGA. To interface with the physical world, we implemented memory-mapped hardware peripherals at the top of the data memory space, including 8-bit PWM generators and 32-bit millisecond/microsecond hardware timers. 

To prove the processor was fully functional, we wrote custom **RISC-V Assembly code**. The assembly program successfully utilized our memory-mapped addresses and hardware timers to interact with the board's RGB LEDs, verifying that our custom hardware could accurately fetch, decode, and execute software instructions in the real world.

---

## Outcomes & Technical Growth
Building a CPU from the ground up completely demystified the barrier between software and physical circuitry. Successfully taking this design from theoretical state diagrams to simulated SystemVerilog, and finally to physical hardware running our own assembly code, was an incredibly rigorous test of digital logic design and computer architecture principles.

## Project Links
* **[View the Source Code on GitHub](https://github.com/jalikins/RISC5_Processor)**

## Image Gallery
*(Add screenshots of your Icarus Verilog waveform simulations, a block diagram of your datapath, and a photo/video of the iceBlinkPico board running your assembly code here)*

![Processor Datapath](/post_img.webp)
*Caption: The block diagram mapping our multicycle RISC-V datapath and control signals.*