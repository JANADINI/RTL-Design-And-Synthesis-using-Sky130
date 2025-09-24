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
  
  ![image](https://github.com/JANADINI/RTL-Design-And-Synthesis-using-Sky130/blob/main/Week_1/Day-1/Photos/Icarus%20verilog%20design%20flow.png)

  ---
# Design

- **Definition**: Describes the functionality of a digital circuit at the RTL level using HDL, defining its logic and data flow.

- **What it does**: Processes one or more primary inputs to produce outputs according to the intended behavior.

- **Examples**: Verilog code for MUX, Flip-Flop, ALU,...

- **Purpose**: Creates a clear, testable model of the circuit that can be simulated and synthesized for hardware implementation
  
  ---
# Testbench

- **Definition**: A verification environment written in HDL to test and validate the design.

- **What it does**: Applies stimulus to the design, observes outputs, and checks if the behavior matches the specification. <mark>It does not have any primary inputs or outputs of its own.</mark>

- **Examples**: Verilog testbench for MUX, Flip-Flop, ALU,..

- **Purpose**: Helps debug and verify the design before synthesis and hardware implementation.

  ![image](https://github.com/JANADINI/RTL-Design-And-Synthesis-using-Sky130/blob/main/Week_1/Day-1/Photos/Testbench.png)

  ---
 # Step 0: Start from your home
 ```bash
cd /home/vboxuser/vsd/VLSI
ls
```
Once if you list it , you will see
```bash
(no sky130 folder yet)
```
# Step 1: Clone the GitHub repository  ![link](https://github.com/kunalg123/sky130RTLDesignAndSynthesisWorkshop.git)
```bash
git clone https://github.com/kunalg123/sky130RTLDesignAndSynthesisWorkshop.git
ls
```
You will see
```bash
sky130RTLDesignAndSynthesisWorkshop
```
Repository cloned successfully. All project files are inside this folder.
# Step 2: Go inside project folder
```bash
cd sky130RTLDesignAndSynthesisWorkshop
ls
```
Inside this folder you will see all the Standard cells / library files for RTL & synthesis.The Directory Flow from /home will be like:
```bash
/home
└── vboxuser
    └── vsd
        └── VLSI
            └── sky130RTLDesignAndSynthesisWorkshop/
                ├── my_lib/
                │   └── verilog_model/       # Prebuilt verilog library (cells, primitives)
                ├── verilog_files/           # RTL design examples + testbenches
                ├── DC_WORKSHOP/             # Digital Compiler related labs
                ├── lib/                     # Library support files
                ├── README.md                # Project info
                └── yosys_run.sh             # Script to run synthesis using Yosys
```
# Step 3:Then go to verilog_files and check whether all librarires are cloned properly


