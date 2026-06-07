# conveyor-belt-plc-codesys
Conveyor belt start/stop/sensor control system using IEC 61131-3 Ladder Diagram in CODESYS V3.5, connected to Factory I/O simulation via Modbus TCP/IP protocol.
# Conveyor Belt PLC Control — CODESYS + Factory I/O

## Project Overview
A simulated industrial conveyor belt control system built using 
IEC 61131-3 Ladder Diagram programming in CODESYS V3.5, 
connected to Factory I/O via Modbus TCP/IP protocol.

## System Behaviour
- Press **Start** → conveyor runs and latches
- Press **Stop** → conveyor stops immediately
- Box reaches **end sensor** → conveyor stops automatically
- System must be restarted manually after sensor stop

## Tools & Technologies
- **CODESYS V3.5** — PLC programming (Ladder Diagram)
- **Factory I/O** — 3D industrial simulation environment
- **Modbus TCP/IP** — communication protocol
- **IEC 61131-3** — international PLC programming standard

## I/O Mapping
| Variable | Address | Description |
|---|---|---|
| I0 | %IX0.0 | Start pushbutton |
| I1 | %IX0.1 | Stop pushbutton |
| I2 | %IX0.2 | End-of-line sensor |
| Q0 | %QX0.0 | Conveyor motor |

## Ladder Logic
Rung 1: Start/Stop/Sensor seal-in circuit
- I0 (Start) in series with I1 (Stop) and I2 (Sensor)
- Q0 seal-in contact in parallel with I0
PROGRAM PLC_PRG
VAR
    // STATION INPUTS
    I0 AT %IX0.0:BOOL; // START
    I1 AT %IX0.1:BOOL; // STOP
    I2 AT %IX0.2:BOOL; // SENSOR

    // STATION OUTPUTS
    Q0 AT %QX0.0:BOOL; // CONVEYOR
END_VAR

## Screenshots

### Factory I/O Scene
![Factory IO Scene]




### Ladder Logic (CODESYS)
![Ladder Logic]

### Modbus I/O Mapping
![IO Mapping]

## Author
Dilan — Automation Engineer
