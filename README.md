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
  ![image](
