---
author: CVRA
title: Sisyphus,<br>a Landmine Mapping Rover
date: 27.11.2018
---

#

## Motivation

According to ["Landmine Monitor 2018"](http://www.the-monitor.org/media/2918780/Landmine-Monitor-2018_final.pdf)

- 7'239 casualties in 2017:
    * 2'793 deaths
    * 4'431 injuries
    * 15 unknown survival status
- 60 states contaminated with antipersonnel mines

##

<img src="images/mine_casualties.png" alt="" title="" width="90%" />

##

<img src="images/mine_contamination.png" alt="" title="" width="90%" />

#

## Minesweepers competition

<img src="images/minesweepers.jpg" alt="" title="" width="90%" />

## When/Where?

<img src="images/iros2018.jpg" alt="" title="" width="80%" />

## Rules

- One or multiple robots
- Autonomous or teleoperated
- 20 minutes to map 400m² outdoor looking for
    * Surface landmines
    * Underground landmines
- Not allowed to touch the mines

#

## Who are we?

<img src="images/cvra.jpg" alt="" title="" width="70%" />

## How many?

<img src="images/team.jpg" alt="" title="" width="80%" />

## Where?

Lausanne, Switzerland
<img src="images/lausanne.jpg" alt="" title="" width="75%" />

## Goal

Build a rover for the competition in 3 months,<br>with 4 persons, and 500$ + parts

#

## Enter Sisyphus

<img src="images/sisyphus.jpg" alt="" title="" width="70%" />

#

## Mechanical design

<img src="images/mechanical-design.jpg" alt="" title="" width="65%" />

## Rocker-bogie

<img src="images/rocker-bogie.gif" alt="" title="" width="65%" />

## Rocker-bogie

<img src="images/rocker-bogie.jpg" alt="" title="" width="90%" />

## Driving electronics

- Driving wheels
    * powered by DC motors
    * controlled by Motor boards
- Steering servos
    * controlled by PWM outputs on the Master board

#

## Detecting buried mines

<img src="images/coil.jpg" alt="" title="" width="65%" />

## Detecting buried mines

- Pulse-induction metal detector
- 3 coils on the front of the rover
- Total span of 1m covered

## Detecting surface mines

<img src="images/rgbd.jpg" alt="" title="" width="55%" />

## Detecting surface mines

- Realsense D435
- RGB + Depth converted to Point cloud
- Point cloud segmented based on geometry
    * Remove the planar background
    * Cluster remaining points
    * Find cluster matching mine size range

#

## Positioning system

Requirements

- Drift-free ➡ 🚫 INS or SLAM
- High-accuracy (<10cm) ➡ 🚫 GPS
- Cheap (<500$) ➡ 🚫 RTK GPS

## Ultra-Wide Band beacons

:::::::::::::: {.columns}
::: {.column width="35%"}
![](images/uwb-beacon.jpg)
:::
::: {.column width="60%"}
- Custom design
- cm-level range measurement
- High update rate (>100Hz)
- 50$ per board
- Open source
:::
::::::::::::::

## UWB positioning system

<img src="images/uwb-positioning.png" alt="" title="" width="80%" />

## UWB positioning system

- Drift: None ✔
- Positioning accuracy: 5cm ✔
- Total cost: 250$ ✔
- Bonus: works indoor and outdoor

#

## System design

<img src="images/system.png" alt="" title="" width="90%" />

## CVRA CAN stack

Reusing our CAN boards

- UWB boards
- Motor boards
- IO board
- CAN/USB adapter

## UWB board

:::::::::::::: {.columns}
::: {.column width="35%"}
![](images/uwb-beacon.jpg)
:::
::: {.column width="60%"}
- Used for positioning
- STM32F4 + ChibiOS + UAVCAN
- 50$ per board
:::
::::::::::::::

## Motor board

:::::::::::::: {.columns}
::: {.column width="40%"}
![](images/motor-board.jpg)
:::
::: {.column width="60%"}
- Used for motor control
- Hacked for metal detection
- STM32F3 + ChibiOS + UAVCAN
- 35$ per board
:::
::::::::::::::

## IO board

:::::::::::::: {.columns}
::: {.column width="40%"}
![](images/io-board.jpg)
:::
::: {.column width="60%"}
- Used as RC receiver
- STM32F3 + ChibiOS + UAVCAN
- 10$ per board
:::
::::::::::::::

## CAN/USB adapter

:::::::::::::: {.columns}
::: {.column width="40%"}
![](images/can-adapter.jpg)
:::
::: {.column width="60%"}
- Used as PC - CAN interface
- STM32F3 + ChibiOS + UAVCAN
- 20$ per board
:::
::::::::::::::

#

## Sisyphus flies to Madrid

<img src="images/sisyphus.jpg" alt="" title="" width="70%" />

## Madrid

![](images/madrid.jpg)

## Working at the Airbnb

<img src="images/airbnb.jpg" alt="" title="" width="80%" />

## On the field

![](images/trial.jpg)

## Best Design Award

<img src="images/award.jpg" alt="" title="" width="60%" />

## IROS

:::::::::::::: {.columns}
::: {.column width="36%"}
![](images/iros-1.jpg)
:::
::: {.column width="64%"}
![](images/iros-2.jpg)
:::
::::::::::::::

## La conquista de Madrid

<img src="images/cvra-madrid.jpg" alt="" title="" width="65%" />

#

## Conclusion

:::::::::::::: {.columns}
::: {.column width="30%"}
**Good**

- Modular Design
- CAN bus
- 3D Printing
- RGBD Camera
:::
::: {.column width="30%"}
**Bad**

- Coil detector
- Mechanical issues
- Late integration
- Lack of testing
:::
::::::::::::::

#

## We ❤ open-source!

- Software & Electronics    [github.com/cvra](https://github.com/cvra)
- Mechanical design         [grabcad.com/cvra-1](https://grabcad.com/cvra-1)
- CVRA CAN stack            [cvra.ch/robot-software](https://www.cvra.ch/robot-software)

#

## Questions? {data-background-image="images/rgbd.jpg" data-background-opacity=0.8 data-background-size=60%}
