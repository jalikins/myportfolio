---
title: "RISC32I Processor FPGA Implementation"
description: "Designed and implemented a custom multicycle RISC-V processor architecture in SystemVerilog, deployed to an FPGA to execute custom assembly logic."
pubDate: "December 2025"
heroImage: "/post_img.webp"
badge: "Computer Architecture"
---

## Overview
Designed an unpipelined, multicycle 32-bit RISC-V integer microprocessor. Working on a three person team, we mapped the processor's datapath, wrote the hardware logic in SystemVerilog, and deployed the architecture to an iceBlinkPico FPGA board to run Assembly code.

## My Role & The Tech Stack
* **Team Division:** A 3 person team to handle RTL design, testbench simulation, and hardware-software integration.
* **Hardware:** iceBlinkPico FPGA Board
* **Software:** SystemVerilog, RISC-V Assembly, OSS CAD Suite, Icarus Verilog
* **Skills:** Multicycle Datapath Design, State Machine Logic, Memory Mapping, Hardware Simulation

---

## The Process

### 1. Processor Architecture 
Designed the processor using **Harvard architecture**, creating a 32-bit address space with separate 4kB instruction and 4kB data memories. The core logic required us to implement the base RV32I instruction set. Because this was a multicycle processor, we created a finite state machine to control the flow of data through the Fetch, Decode, Execute, Memory, and Writeback stages.

![Block diagram of architecture](/risc/neorv32_cpu.png)
*Caption: Block diagram of architecture (did not create diagram).*

### 2. RTL Simulation 
Before dealing with hardware, we designed the software then validated it. We used the OSS CAD Suite and **Icarus Verilog (iverilog)** to build testbenches. By simulating examples for each class of RV32I instructions, we saw signal waveforms and verified the proper operation of the arithmetic logic unit (ALU) and control structures in software.

![simulation data](/risc/simulation.png)
*Caption: Checking the PC timing and actions.*

### 3. Hardware 
To show the processor was functional, we used **RISC-V Assembly code**. The assembly program used our memory mapped addresses and hardware timers to interact with the board's RGB LEDs, verifying that our custom hardware could accurately fetch, decode, and execute software instructions in the real world.

<video controls class="max-w-full mx-auto mb-6 rounded-lg shadow-sm">
  <source src="/risc/final_demo.mp4" type="video/mp4">
  Your browser does not support the video tag.
</video>
*Caption: Hardware blinking LED colot depending on which stage it is on.*

---

## Technical Growth
Building a CPU from the ground up demystifies the barrier between software and physical circuitry. Taking this design from theoretical state diagrams to simulated SystemVerilog, and finally to physical hardware running our own assembly code, was an test of digital logic design and computer architecture principles.

## Project Links
* **[View the Source Code on GitHub](https://github.com/jalikins/RISC5_Processor)**

