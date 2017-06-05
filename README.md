# Automagic-Window
Twingo C06 Automagic Power Window Module

**Current status:** This project is something I like to work on intermittently. If and when it reaches a useful state I will upload the source files :)

**Project aim:** A module that can be connected between the window switch and window motor on a Renault Twingo C06 to give the window an automatic up / down feature.

**Requirements:**
- General function: a short press of the switch should result in the window fully opening or closing, but holding the switch should stop the window at the desired position.
- Usable on both driver and passenger side (which requires reversing the polarity in part of the circuit due to how the car is originally wired). Depending on how the circuit design turns out, the module may also be usable for the electric roof.
- Current sensing to determine if the window has reached the end of travel or is obstructed.
- Timeout: if after X seconds the end of travel hasn't been reached, assume a malfunction, cut power to the motor, revert to manual window control.
- Fallback: if the module malfunctions and blows its fuse, revert to manual window control.
- Forced fallback: if the module malfunctions without blowing its fuse, the user should be able to force reverting to manual window control.
- Fused: the module should be fused such that if a malfunction causes the window motor to remain powered for an extended amount of time, the fuse should blow, so the window motor isn't destroyed or set on fire.

**Physical properties:**
- pcb dimensions 50x50mm max if possible
- 4mm mounting holes
- wires soldered directly to the pcb
- connected externally using XT60 connectors
- Arduino Nano connected / soldered onto pcb
- should fit inside car door (inside overhead panel for electric roof)
- main fuse external inline, same type as used in car's fusebox
- user-serviceable glass 5x20mm fuse on pcb for 5V section
- handle high current (stall current for window motor is >10A, operating current around 2.5A (down) to 5A (up))
