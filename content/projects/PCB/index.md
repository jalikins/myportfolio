---
title: "custom_PCBs.txt" 
date: 2024-10-01 
draft: false
---

On my first year on [Olin's Formula SAE Team](https://www.olinelectricmotorsports.com) I made three custom PCB boards for our electric car! I made our throttle board, precharge and discharge board, and our battery management system board.

## Battery Management Systems Board

The first board I made was our battery management system (BMS) board. This board is responsible for monitoring the voltage and temperature of each cell in our battery pack, as well as balancing the cells to ensure they are all at the same voltage. This is important for the safety and longevity of our battery pack as well as ensuring that our battery does not overheat.

I started with the schematic design, which is sort of like a blueprint that shows what all of the components on the board are without having to worry about how they'll be laid out on an actual board. I broke up my schematic into a few different functional blocks:

- The Atmega 16m1, the microcontroller we use on our team, and its accompanying crystal and circuitry
- The CAN transceiver used to send and receive CAN messages
- Daisy-Chain IsoSPI interface to communicate with the battery management system chips that track voltage and temperature.
- BMS Shutdown relay to decide whether car should be shut off or not
- LEDs to indicate status of the board
- Current sensor trigger which is used to detect if there is to much power running though the board
- Ground short detection which shuts off the car if short is detected

The next step was designing the board's layout. This was by far the trickiest step, as now I had to take that list of components and lay them out on a circuit board. The reason I found it difficult is because I had to keep in mind a varying list of constraints that were sometimes didn't have a straightforward solution.

For example, I wanted to make the physical footprint of the board no larger than it needed to be, and also have all of the traces (connections on the circuit board) be as short as possible. But certain signals are also susceptible to noise, so I had to make changes to move those farther away from components that had a tendency to produce noise. Minimizing the number of vias (a small hole that's used to make a connection to another layer of the board, which is useful when two traces need to intersect to get to their destinations) was also important.

Ultimately, it took a few revisions, but I ended up with a layout I was happy with and was ready to ship for production.

<div align="center">
    BMS layout
    <img src="/images/pcb/bms.png" alt="layout for bms" width="800" height="350">
</div>


## Precharge and Discharge Board

The next board I made was our precharge and discharge board. This board is responsible for precharging components before suddenly giving the entire voltage directly when the car is turned on, as well as discharging the all the energy in the system when the car is turned off. This is important for the safety of the car, as it prevents the components being damaged by a sudden surge of power.

<div align="center">
    Simple block diagram of where it fits in the car
    <img src="/images/pcb/block_prech.png" alt="block diagram" width="500" height="350">
</div>

This board was a bit simpler than the BMS board, as it only had a few components. The main components were:

- precharge relay, which is used to precharge the components before the car is turned on
- discharge relay, which is used to discharge the components when the car is turned off

Both of the relays were controlled by a different board on the car, so I only had to have either of these relays on or off on the car.
<div align="center">
    Precharge and Discharge layout
    <img src="/images/pcb/layout_pre.png" alt="layout for Precharge and Discharge" width="500" height="450">
</div>

Both of the boards are on the same part of the car, which we call the Service Section. This part of the car is where all the high voltage of the car is located and I helped put together the service section as well.

<div align="center">
    Service Section, arrow points to BMS Core and circled is the Precharge and Discharge board
    <img src="/images/pcb/service_section.png" alt="layout for Precharge and Discharge" width="600" height="450">
</div>

## Throttle Board

The last board I made my first year was the throttle board. This board is responsible for reading the position of the two linear potentiometers that are attached to the throttle pedal, and sending that information to the motor controller over CAN. Also, it had an inertial switch that would turn off the car if it detected that the car was upside down.

Main components of the board were:

- Atmega 16m1, the microcontroller we use on our team, and its accompanying crystal and circuitry
- CAN transceiver used to send and receive CAN messages
- two op-amps circuits to read the position of the two linear potentiometers
- Inertial switch to turn off the car if it detects that the car is upside down

The reason we have two linear potentiometers is to ensure that the throttle pedal is not stuck in a position that would cause the car to accelerate uncontrollably. If one of the potentiometers reads a different value than the other, the car will be turned off. Also, a different board on the car will read a break pressure sensor sends that information over CAN to the throttle board, to make sure that both the accelerator and brake are not pressed at the same time. Also, the throttle board will send a message over CAN to the motor controller to tell it how much power to send to the motor.

<div align="center">
    Throttle layout, I prioritized the electronics being as small as possible to fit diagram in case a quick fix was needed
    <img src="/images/pcb/layout_throttle.png" alt="layout for throttle" width="900" height="450">
</div>

## Conclusion

Overall, I learned a lot from making these boards. I learned how to design a schematic, how to layout a board, and how to work with the manufacturing process. I also learned how to work with the team to make sure that the boards fit in the car and worked with the other components. It was a great experience and I look forward to working next year as the new electrical lead on the team?