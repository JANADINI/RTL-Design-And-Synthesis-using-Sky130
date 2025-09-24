# RTL Design And Synthesis Using Sky130

A day-wise hands-on series on Verilog **RTL** design, simulation, synthesis, and digital circuit optimization with labs, code, and explanations.

 - - -
 # Day 1 – Verilog RTL & Synthesis

Open source simulator **Icarus verilog** – intro

**Icarus Verilog** + **GTKWave** – labs

**Yosys** + Logic Synthesis – intro

**Sky130 PDK** – hands-on labs

---
# Simulator

A simulator is a tool used in RTL design flow to run Verilog/VHDL code and observe its behavior before hardware implementation.

- It models how the circuit reacts to inputs over time.
- <mark>Output changes only when inputs or internal states (flip-flops, registers) change.</mark>
- Helps to debug design and verify logic correctness.
- Examples-: **Icarus Verilog (iverilog).**
- Purpose-: Catch functional errors early, long before synthesis and fabrication.
  
  ![image](https://github.com/JANADINI/RTL-Design-And-Synthesis-using-Sky130/blob/main/Week_1/Day-1/Icarus%20verilog%20design%20flow.png)

  ---
 # Design

- **Definition**: Describes the functionality of a digital circuit using HDL at the RTL level.

- **What it does**: Defines logic and data flow between inputs and outputs.

- **Examples:** Verilog code for MUX, Flip-Flop, ALU.

- **Purpose**: Provide a clear model of circuit behavior for simulation and synthesis.

  ---
 # Testbench

- **Definition**: A verification environment written in HDL to test the functionality of the design.

- **What it does**: Provides stimulus (inputs), observes outputs, and checks if the design behaves as expected.

- **Examples**: Verilog testbench for MUX, Flip-Flop, ALU.

- **Purpose**: Validate and debug the design before synthesis and hardware implementation.

  
