# Automagic-Window
Twingo C06 Automagic Power Window Module

**Current status:** I have abandoned this project due to no longer owning this car.

**Project aim:** A module that can be connected between the window switch and window motor on a Renault Twingo C06 to give the window an automatic up / down feature.

**Requirements:**
- General function: an activation of the window switch that is nearly immediately followed by the release of the switch should result in the window fully opening or closing, while holding the switch for a predetermined amount of time should stop the window the moment the switch is released.
- A single design usable on either driver or passenger side: due to the original wiring of the car, on one side, the window motor at rest has both poles connected to +12V, the other side has both poles connected to Ground. Assuming the design uses two SPDT relays to control the motor, there needs to be a solder or wire jumper to connect the relays' common connection to either +12V or Ground when building the module.
- Current sensing: cut power to the motor if the window is obstructed or has reached the end of travel.
- Timeout: if after a predetermined amount of time the end of travel hasn't been reached, assume a malfunction, cut power to the motor, revert to manual window control.
- Fallback: if the module malfunctions and blows its fuse, revert to manual window control.
- Forced fallback: if the module malfunctions without blowing its fuse, the user should be able to force reverting to manual window control. For example by turning off the ignition, pressing and holding the window switch in its down position, then turning on the ignition. The module should then remain in this state (also through power cycles) until a similar operation indicates the user's express intent to reactivate the module.
- Fused: the module should be fused such that if a malfunction causes the window motor to remain powered for an extended amount of time, the fuse should blow, so the window motor isn't destroyed or set on fire.
- Back EMF: even though in the original design the control switches directly power the motor (which may or may not include protection circuitry), I feel it would make for a good design to include a TVS between the relay outputs to the motor, if for no other reason than to extend the life of the relays.

**Physical properties:**
- pcb dimensions as small as possible, but no larger than 100x100mm
- 3 or 4mm mounting holes
- wires soldered directly to the pcb
- connected externally using XT30 connectors in such a way that the module can be taken out and the window switch wires XT30 connector can be plugged straight into the motor wires XT30 connector, restoring the window operation to factory conditions
- Arduino Nano as the controller
- main fuse external inline, same type as used in car's fusebox
- user-serviceable glass 5x20mm fuse on pcb for 5V section
- handle high current (stall current for window motor is >10A, operating current around 2.5A (down) to 5A (up))
