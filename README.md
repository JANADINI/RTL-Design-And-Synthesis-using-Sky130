
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
# Flow from Simulation(RTL.v) to Synthesis(Netlist.v):
  
 ### Step 1: Start from your home
 ```bash
cd /home/vboxuser/vsd/VLSI
ls
```
Once if you list it , you will see
```bash
(no sky130 folder yet)
```
### Step 2: Clone the GitHub repository  ![link](https://github.com/kunalg123/sky130RTLDesignAndSynthesisWorkshop.git)
```bash
git clone https://github.com/kunalg123/sky130RTLDesignAndSynthesisWorkshop.git
ls
```
You will see
```bash
sky130RTLDesignAndSynthesisWorkshop
```
Repository cloned successfully. All project files are inside this folder.
### Step 3: Go inside project folder
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

![image](https://github.com/JANADINI/RTL-Design-And-Synthesis-using-Sky130/blob/main/Week_1/Day-1/Photos/code%20dumped%20in%20iverilog(a.out).png)

### Step 4: Next dump th <mark>RTL code</mark> in <mark>iverilog</mark> 
```bash
iverilog good_mux.v  tb_good_mux.v
```
After dumping into the simulator the code will be in a executable file`a.out`
### Step 5: Execute the <mark>a.out</mark> executable file
```bash
./a.out
```
### Step 6: View the <mark>.vcd</mark> file in <mark>GTKwave</mark>

![image](https://github.com/JANADINI/RTL-Design-And-Synthesis-using-Sky130/blob/main/Week_1/Day-1/Photos/Mux%20in%20GTKwave.png)

> [!Tip]
> ```bash
> gvim tb_good_mux.v -o good_mux.v
> ```
>  Opens tb_good_mux.v(![code](https://github.com/JANADINI/RTL-Design-And-Synthesis-using-Sky130/blob/main/Week_1/Day-1/Visualization/))tb_good_mux.v and good_mux.v(![code](https://github.com/JANADINI/RTL-Design-And-Synthesis-using-Sky130/blob/main/Week_1/Day-1/Visualization/RTL%20code%20for%20good_mux.v)) together in GVim. The -o option makes them appear in a split window (side by side). You can compare, view, and edit both files in the same editor, and save changes normally with :w or exit with :q.

---
# Synthesizer

- A synthesizer transforms **high-level RTL** descriptions into a **low-level gate-level** representation that hardware can implement.

- It is a **translation engine** that maps Verilog/VHDL code onto standard cells of a technology library.

- A synthesizer performs **RTL-to-gate conversion**, applying optimizations for **timing, area, and power**.

- In VLSI flow, the synthesizer is the **bridge** between functional design **(RTL)** and hardware realization **(netlist).**

- Tool used here: **Yosys.**
  
  ![image](https://github.com/JANADINI/RTL-Design-And-Synthesis-using-Sky130/blob/main/Week_1/Day-1/Photos/Synthesizer(yosys).png)

# Verification of <mark>Netlitst.v</mark> by Icarus verilog

Verification of the synthesized netlist ensures the gate-level design matches the RTL functionality and meets required specifications.The flow will be like

![image](https://github.com/JANADINI/RTL-Design-And-Synthesis-using-Sky130/blob/main/Week_1/Day-1/Photos/verification%20of%20netlist.png)
>[!Note]
> The number of **primary inputs and outputs** remains the same for both RTL and synthesized netlist.  
> Therefore, the **same testbench (TB)** can be used to verify both designs.
---
# Flow for RTL code to Netlist
![###What is RTL code?]()






