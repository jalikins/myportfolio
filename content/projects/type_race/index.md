---
title: "type_race.txt"
date: 2024-10-01
draft: false
---

Type-Race is an engaging typing game **built in Python using the `pygame` library** by my partner and me. Inspired by "Type Racer," it's designed to **help users improve their typing speed and accuracy** through a fun, competitive experience.

## The Game

The game challenges players to **copy as much of the on-screen prompt as possible within a 60-second timeframe**. The prompt dynamically scrolls as the player types. Mistakes are visually underlined in red for easy correction using the backspace key. The top-left display provides real-time feedback on the **remaining time**, the player's **current words per minute (WPM)**, and, in multiplayer mode, the **opponent's WPM**.

## Video Overview

{{< youtube DYhtCqgXzgE >}}

## Peeking Inside

The game's architecture is primarily built using the **`pygame` library**. To ensure a well-organized and scalable codebase, we adopted the **Model-View-Controller (MVC) framework**.

The **model** encapsulates the core **game logic**, managing aspects such as the current prompt, the game timer, the calculation of the player's WPM, and the validation of typed characters. The **view** is responsible for **rendering the game state** to the user interface, displaying the prompt, player input (with distinctions between correct and incorrect characters), both players' WPM (in multiplayer), and the timer. The **controller** handles **user input from the keyboard**.

The **multiplayer mode** leverages a **TCP socket connection** over a local network to facilitate real-time competition between a host and a client.

1.  The **host initiates a server** that listens for incoming client connections.
2.  A **client connects to the server** and signals readiness to start the game.
3.  Once both sides are ready, the game commences simultaneously. To minimize latency, only the **players' WPM is transmitted over the network** during gameplay.
4.  Upon the 60-second mark, the **model on both ends compares the corrected WPM** of the players, displaying a "winner" or "loser" prompt accordingly.

Key aspects of the socket connection include:

-   Both the host and the client operate with their **own independent game loop**.
-   **Threads were implemented to manage network communication asynchronously**, preventing blocking of the main game loop.
-   The host and client can run on **different machines connected to the same local network**.

## Project Links

-   [GitHub Repository](https://github.com/olincollege/type-race)
-   [Game Website](https://olincollege.github.io/type-race/)