# EXPT_4: 4Bit-Up-Down-Asynchronous-Reset-Counter-Synthesis

## Aim:

Synthesize 4Bit-Up-Down-Asynchronous-Reset-Counter design using Constraints and analyse reports, Timing, area and Power.

## Tool Required:

Functional Simulation: Incisive Simulator (ncvlog, ncelab, ncsim)

Synthesis: Genus

### Step 1: Getting Started

Synthesis requires three files as follows,

◦ Liberty Files (.lib)

◦ Verilog/VHDL Files (.v or .vhdl or .vhd)

◦ SDC (Synopsis Design Constraint) File (.sdc)

 ### Step 2 : Creating an SDC File

•	In your terminal type “gedit input_constraints.sdc” to create an SDC File if you do not have one.

•	The SDC File must contain the following commands;

create_clock -name clk -period 2 -waveform {0 1} [get_ports "clk"]

set_clock_transition -rise 0.1 [get_clocks "clk"]

set_clock_transition -fall 0.1 [get_clocks "clk"]

set_clock_uncertainty 0.01 [get_ports "clk"]

set_input_delay -max 0.8 [get_ports "rst"] -clock [get_clocks "clk"]

set_output_delay -max 0.8 [get_ports "count"] -clock [get_clocks "clk"]

i→ Creates a Clock named “clk” with Time Period 2ns and On Time from t=0 to t=1.

ii, iii → Sets Clock Rise and Fall time to 100ps.

iv → Sets Clock Uncertainty to 10ps.

v, vi → Sets the maximum limit for I/O port delay to 1ps.

### Step 3 : Performing Synthesis

The Liberty files are present in the library path,

• The Available technology nodes are 180nm ,90nm and 45nm.

• In the terminal, initialise the tools with the following commands if a new terminal is being
used.

◦ csh

◦ source /cadence/install/cshrc

• The tool used for Synthesis is “Genus”. Hence, type “genus -gui” to open the tool.

• Genus Script file with .tcl file Extension commands are executed one by one to synthesize the netlist.

#### Synthesis RTL Schematic :
![WhatsApp Image 2024-11-21 at 18 41 20_67a478f6](https://github.com/user-attachments/assets/b995f035-a75e-4e96-abde-abeebcadeae6)

#### Area report:
![WhatsApp Image 2024-11-21 at 18 41 26_554216fe](https://github.com/user-attachments/assets/3e906463-c8b2-46e0-8b39-ada12242a4d3)

#### Power Report:
![WhatsApp Image 2024-11-21 at 18 41 18_c19d844c](https://github.com/user-attachments/assets/9be81e9d-6ac4-48d9-9e70-dc5f3cbdeac8)

#### Timing Report:
![WhatsApp Image 2024-11-21 at 18 41 27_e7915a06](https://github.com/user-attachments/assets/c5a08bdc-5a7f-49ff-9e44-0a7d922dbf2e)

#### Result: 

The generic netlist has been created, and area, power, and timing reports have been tabulated and generated using Genus.





