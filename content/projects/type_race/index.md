---
title: "type_race.txt" 
date: 2024-10-01 
draft: false
---

Type-Race is an exciting typing game that my partner and I built. Played very similarly to the classic game "Type Racer", it is built in Python using the `pygame` library and is designed to help users improve their typing speed and accuracy in a fun, competitive way.

## The Game

When the game starts, you have 60 seconds to copy as much of the prompt on your screen as you can. As you type, the prompt will scroll. If you make a mistake, no worries! Mistakes are underlined in red and can be fixed with the backspace key. In the top left, view the time remaining, your current words per minute, and your opponent's words per minute (if playing multiplayer).

## Video Overview

{{< youtube DYhtCqgXzgE >}}

## Peeking Inside

Majority of the game is built using the `pygame` library. The structure of the code is based on the Model-View-Controller (MVC) framework to help keep the code organized and easily expandable.

The model contains the game logic, such as the current prompt, the timer, player's WPM, and decides if the player put in the correct character. The view is responsible for rendering the game state to the screen, including the prompt, the player's input, both correct and incorrect characters, both players' WPM, and the timer. The controller handles user input on the keyboard.

In the multiplayer mode, we create a host and client network utilizing a TCP socket connection that runs on a local network.

1. The host runs a server that listens for an incoming connection from a client.
2. The client connects to the server and sends an all good signal to start the game.
3. The game then starts on both ends and the only information that is sent over the network is both players' WPM as to not have a delay in information being sent over the network.
4. Once the game ends at 60 seconds, the model on both ends compares the corrected WPM of both players and shows either displays a winner prompt or loser prompt depending on who has the higher WPM.

Few key notes about the socket connection:

- Both the host and client run their own game loop
- We implemented threads to handle the network communication so that it does not block the game loop.
- The host and client can run on different machines as long as they are on the same local network.

## Project Links
- [GitHub Repository](https://github.com/olincollege/type-race)
- [Game Website](https://olincollege.github.io/type-race/)