---
title: "FSAE Firmware Monorepo"
description: "Architected a Bazel-based monorepo to unify firmware development, automated CAN code generation, and PCB design for an electric racecar."
pubDate: "January 2026"
heroImage: "/monorepo/big_block.png"
badge: "Embedded Systems"
---

## Overview
As the Electrical Lead for Olin Electric Motorsports, I recognized that siloing our firmware and hardware designs across dozens of separate repositories was creating massive integration bottlenecks. To solve this, I architected and deployed a unified **Monorepo** from the ground up. This system serves as the single source of truth for all vehicle firmware, shared C libraries, custom KiCad PCB footprints, and continuous integration testing.

[Monorepo](https://github.com/olin-electric-motorsports/oem-monorepo)

## My Role & The Tech Stack
* **Role:** Systems Architect & Firmware Lead
* **Build System:** Bazel, OpenOCD, GDB, GNU Make
* **Hardware Target:** STM32G441 Microcontrollers
* **Tooling:** Python (Code Generation), YAML, GitHub Actions, Git LFS, KiCad
* **Skills:** CI/CD Pipelines, Developer Experience (DevEx), Embedded C, Toolchain Architecture

---

## Architectural Pillars & Tooling

### 1. The Bazel Build System & DevEx
Transitioning to a monorepo requires an incredibly fast and scalable build system, which is why I implemented **Bazel**. 

Beyond just compiling code, I wanted to lower the barrier to entry for new team members. I configured the repository to include pre-written linker scripts and integrated **OpenOCD** and **GDB**, allowing developers to compile, flash the STM32 hardware, and launch a live debugging session with a single terminal command. I also wrote extensive example directories and an automated script that injects custom Git Hooks to enforce formatting and linting rules locally before a developer is even allowed to push their code.

![Bazel Building firmware](/monorepo/bazelbuild.png)
*Caption: Bazel succesfully building/compiling all the firmware on the repo*

### 2. Automated CAN Code Generation
A major source of bugs in electric vehicles is mismatched CAN bus configurations between different circuit boards. To eliminate human error, I engineered an automated code-generation pipeline. 

Developers simply fill out a lightweight **YAML** file specifying the CAN messages their specific board needs to send or receive. During the build process, a custom Python script parses these YAML files and automatically generates the C initialization code for the STM32G441. Additionally, it compiles a vehicle-wide master `.dbc` file, allowing us to seamlessly decode live vehicle traffic using a CAN interpreter.

![CAN block diagram](/monorepo/can_pipline.png)
*Caption: Block Digram of how CAN automation works*

![YAML script](/monorepo/yamlfile.png)
*Caption: what the yaml code looks like for developer*

### 3. Unified MCU Abstractions
By standardizing the entire vehicle architecture onto the **STM32G441** microcontroller, I was able to write a single, robust hardware abstraction layer (HAL) for the monorepo. I developed shared helper functions for core communication protocols like SPI, I2C, and UART. Instead of rewriting initialization sequences, every sub-team imports the exact same validated core library, drastically reducing development time.

### 4. Hardware/Firmware CI/CD Pipeline
A monorepo isn't just for software. I integrated our entire KiCad part library into the repo, utilizing **Git LFS (Large File Storage)** to efficiently track bulky `.step` 3D CAD files. 

To maintain strict quality control, I implemented **GitHub Actions**. Before any hardware or firmware pull request can be merged into `main`, the CI pipeline automatically boots up, verifies that all hardware footprints are imported correctly, and ensures that the firmware compiles flawlessly across every single board on the vehicle. 

![GitHub actions](/monorepo/github_actions.png)
*Caption: Checks on a pull request for hardware and software*

---

## Outcomes
Architecting this monorepo completely transformed the team's engineering workflow. By automating the tedious setup processes (like CAN initialization and linker configurations) and enforcing strict PR reviews, our engineers can now focus purely on writing control logic and designing circuits. 
