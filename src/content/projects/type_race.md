---
title: "Type Race Application"
description: "Developed a real-time multiplayer typing speed application focusing on asynchronous socket networking and MVC architecture."
pubDate: "October 2024"
heroImage: "/projects/type_race/main.png"
badge: "Software"
---

## Overview
Type-Race is a competitive, multiplayer typing application built entirely in Python using the `pygame` library. Designed to help users improve their typing speed and accuracy, the game challenges players to accurately type a dynamically scrolling prompt within a strict 60-second timeframe, either solo or head-to-head against another player over a local network.

## My Role & The Tech Stack
* **Role:** Software Developer (Co-developed with a peer)
* **Languages & Libraries:** Python, Pygame, TCP Sockets, Threading
* **Architecture:** Model-View-Controller (MVC), Client-Server Model
* **Skills:** Asynchronous Networking, State Management, Input Validation

---

## The Engineering Process

### 1. Software Architecture (MVC)
To ensure a well-organized and highly scalable codebase, we built the game using a strict Model-View-Controller (MVC) framework:
* **The Model:** Encapsulates the core game logic, managing the text prompts, calculating the live Words Per Minute (WPM), and validating typed characters against the target string.
* **The View:** Renders the game state to the user interface at a high frame rate, dynamically rendering scrolling text, highlighting incorrect characters in red, and displaying live timer updates.
* **The Controller:** Captures and routes asynchronous keyboard inputs to the model without interrupting the visual rendering loop.

### 2. Real-Time Input & UI Feedback
Creating a smooth typing experience required precise input handling. The prompt dynamically scrolls as the user types, and the system instantly flags errors with a visual red underline. Users cannot proceed until the error is corrected using the backspace key, enforcing accuracy over sheer speed. 

![Type Race Gameplay](/projects/type_race/gameplay.png)
*Caption: The primary user interface displaying the scrolling prompt, timer, and live WPM tracking.*

### 3. Multiplayer TCP Socket Networking
The most complex engineering challenge was facilitating real-time competition between two separate machines over a local network. We implemented a robust Client-Server architecture utilizing TCP sockets:
1. **Connection Protocol:** One instance initiates a server (Host) listening for incoming connections, while the second instance (Client) connects and signals a ready state.
2. **Asynchronous Threading:** To prevent network latency from lagging or blocking the high-speed `pygame` rendering loop, we implemented threading. The network communication runs asynchronously, transmitting only essential data (the player's live WPM) to keep packet sizes incredibly small.
3. **Resolution:** At the 60-second mark, the models on both machines independently compare the final corrected WPMs to determine and display the winner.

---

## Outcomes & Project Links
The project successfully demonstrated the ability to build a highly responsive desktop application with complex background networking. By isolating the game logic from the rendering and networking layers, the codebase remains clean and easily extensible for future features, such as online matchmaking or database-backed leaderboards.

* **[View the Live Game Website](https://olincollege.github.io/type-race/)**
* **[View the GitHub Repository](https://github.com/olincollege/type-race)**
* **[Watch the Video Overview (YouTube)](https://www.youtube.com/watch?v=DYhtCqgXzgE)**