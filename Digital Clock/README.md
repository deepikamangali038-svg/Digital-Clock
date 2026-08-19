# Digital Clock Using Verilog

## 1. Project Overview

This project implements a **Digital Clock using Verilog HDL**.

The clock displays:

* Hours: `00–23`
* Minutes: `00–59`
* Seconds: `00–59`

The design uses a clock divider to generate a **1-second timing pulse** from a faster input clock.

## 2. Features

* Written completely in Verilog HDL
* 24-hour clock format
* Seconds, minutes, and hours counters
* Synchronous reset
* Easy-to-understand RTL design
* Includes a Verilog testbench
* Simulation output included

## 3. Inputs

| Signal  | Description                |
| ------- | -------------------------- |
| `clk`   | System clock               |
| `reset` | Resets clock to `00:00:00` |

## 4. Outputs

| Signal    | Description    |
| --------- | -------------- |
| `hours`   | Current hour   |
| `minutes` | Current minute |
| `seconds` | Current second |

## 5. Working Principle

The clock works in three stages:

1. The input clock is divided to generate a 1-second pulse.
2. The seconds counter increments every second.
3. When seconds reach 59, they reset to 00 and minutes increment.
4. When minutes reach 59, they reset to 00 and hours increment.
5. When hours reach 23, they reset to 00.

### Counter Sequence

```text
00:00:00
00:00:01
00:00:02
     ...
00:00:59
00:01:00
     ...
00:59:59
01:00:00
     ...
23:59:59
00:00:00
```

## 6. Tools

The project can be simulated using:

* Icarus Verilog
* ModelSim
* Vivado
* Quartus

## 7. Files

### `digital_clock.v`

Main RTL design of the digital clock.

### `digital_clock_tb.v`

Testbench used to verify the design.

### `output.txt`

Example simulation output.

## 8. Simulation

For Icarus Verilog:

```bash
iverilog -o digital_clock_sim digital_clock.v digital_clock_tb.v
vvp digital_clock_sim
```

The simulation prints the current time whenever the clock advances.

## 9. Expected Result

The clock should correctly count:

```text
Hours   : 00 → 23
Minutes : 00 → 59
Seconds : 00 → 59
```

After `23:59:59`, the clock returns to:

```text
00:00:00
```

## 10. Applications

* Digital clock systems
* FPGA-based clock projects
* Embedded systems
* Digital electronics learning
* Verilog HDL practice
* RTL design practice

## 11. Author

**Verilog Digital Clock Project**

Created for learning and GitHub portfolio purposes.
