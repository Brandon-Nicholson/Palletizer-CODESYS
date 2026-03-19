# Palletizer — Multi-POU Industrial Control System

CODESYS + Factory I/O simulation of a two-story palletizer that sequences conveyors, sensors, and actuators to place boxes onto a pallet.

## Architecture
- 4 modular POUs with correct task execution order: SAFETY_LOGIC, PREDICTIVE_MAINTENANCE, LIGHTS_LOGIC, MAIN
- GVL for all shared variables across programs

## Key Features
- Watchdog fault detection monitoring elevator state transitions and box feed rates — stall beyond timeout triggers automatic shutdown
- E-stop, reset guard, pre-start operator warning, and clean stop logic using fail-safe principles
- OPC UA server running in CODESYS with Factory I/O connected as client
- Race condition diagnosed and fixed using dedicated INT elevator_state variable

## Demo
[YouTube Demo](https://youtu.be/uOj7-TnxfHA?si=FeeYypzgNRzz0JOq)

## Tools
- CODESYS 3.5
- Factory I/O
