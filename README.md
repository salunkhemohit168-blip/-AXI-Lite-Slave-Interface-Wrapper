\# AXI4-Lite Slave Interface Wrapper



\## Project Overview

A parameterized AXI4-Lite Slave Interface Wrapper implemented using Verilog HDL. It provides a memory-mapped interface for reading and writing four internal registers.



\## Features

\- Parameterized data and address widths.

\- Independent AXI4-Lite read and write channels.

\- Separate read and write FSMs.

\- Independent write address and data handling.

\- Byte-level write control using WSTRB.

\- Four 32-bit memory-mapped registers.

\- Concurrent read and write operations.

\- Active-low asynchronous reset.



\## Architecture

1\. \*\*Write FSM:\*\* Manages write address, write data, and write response.

2\. \*\*Read FSM:\*\* Manages read address and read data response.

3\. \*\*Register Bank:\*\* Contains four memory-mapped registers.

4\. \*\*Write Buffering:\*\* Handles independent AW and W channel arrival.



\## Register Map



| Register | Address Offset |

|---|---|

| slv\_reg0 | 0x00 |

| slv\_reg1 | 0x04 |

| slv\_reg2 | 0x08 |

| slv\_reg3 | 0x0C |



\## Verification

The testbench covers:

\- Writes and reads to all four registers.

\- AW channel arriving before W channel.

\- W channel arriving before AW channel.

\- Byte-strobe masking using WSTRB.

\- Concurrent read and write operations.

\- Read-data comparison and error counting.



\## Project Structure

```text

AXI-Lite-Slave-Interface-Wrapper/

├── rtl/

│   └── axi\_lite\_slave.v

├── tb/

│   └── tb.v

├── waveforms/

│   ├── waveform.png

│   └── dump.vcd

├── out.vvp

└── README.md

```



\## Simulation



Using Icarus Verilog:



```bash

iverilog -o out.vvp rtl/axi\_lite\_slave.v tb/tb.v

vvp out.vvp

gtkwave dump.vcd

```



\## Tools

\- Verilog HDL

\- Icarus Verilog

\- GTKWave



\## Source Attribution

Based on Day 078 of the 100DaysOfRTL repository:



https://github.com/Praful-Kesavadas/100DaysOfRTL



Source commit: `9614aa7b207ff11aa089b0f3277c6a4ee1ef34d6`



The implementation is based on the referenced source. Review the original repository's licensing terms before redistribution.

