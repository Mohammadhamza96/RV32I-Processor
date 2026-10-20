# RV32I Processor | Verilog Implementation

A 32-bit RISC-V processor project featuring a processor RTL implementation, digital circuit designs, and a simulation testbench for Fibonacci and factorial programs.

## 📌 Project Overview

This project focuses on the design and implementation of an RV32I-style processor using Verilog/SystemVerilog. It includes the processor's major hardware components, instruction execution logic, memory interfaces, register operations, and program counter control.

The repository organizes the project into three main sections: circuit designs, Verilog/SystemVerilog source code, and testcases.

## 📂 Repository Structure

```text
RV32I-Processor/
│
├── circuits/
│   └── Processor circuit designs
│
├── verilog-code/
│   └── design.sv
│
├── testcases/
│   └── testbench.sv
│
└── README.md
```

## ⚙️ Processor Architecture

The processor design contains the following modules:

| Module | Description |
|---|---|
| `RV32I_Processor` | Top-level module connecting the processor components |
| `Program_Counter` | Maintains and updates the program counter |
| `Instruction_Memory` | Stores and provides instructions to the processor |
| `Data_Memory` | Handles data memory read and write operations |
| `Register_File` | Contains 32 general-purpose 32-bit registers |
| `Immediate_Generator` | Generates immediate values from instruction fields |
| `Control_Unit` | Generates control signals according to instruction opcodes |
| `ALU_Control` | Determines the ALU operation |
| `ALU` | Performs arithmetic and logical operations |

## 🧠 Key Features

- 32-bit processor datapath.
- Modular processor design.
- Program counter and instruction-fetch logic.
- Register file with 32 registers.
- Instruction and data memory modules.
- Immediate generation for supported instruction formats.
- Arithmetic and logical operations through the ALU.
- Branch and jump control logic.
- Load and store control signals.
- Testbench for executing sample programs and observing processor signals.

## 🧪 Verification and Testbench

The `testcases/` directory contains a SystemVerilog testbench that instantiates the processor and loads machine instructions directly into instruction memory.

### 1. Fibonacci Test

The testbench loads a Fibonacci-related instruction sequence, runs the processor for a specified number of clock cycles, and checks whether data memory location `0` contains the expected result of `55`.

**Expected result:** `55`

### 2. Factorial Test

The testbench loads a factorial-related instruction sequence, resets the processor, and checks whether data memory location `1` contains the expected result of `120`.

**Expected result:** `120`

The testbench also displays the program counter, current instruction, ALU result, and selected register values to help inspect processor execution.

*Note: Expected values are the testbench's intended results. Successful verification should be confirmed by running the simulation.*

## 🛠️ Tools and Technologies

- **HDL:** Verilog/SystemVerilog
- **Design:** Digital circuit design and processor RTL
- **Verification:** SystemVerilog testbench and simulation
- **Version Control:** Git and GitHub

Use a simulator that supports the SystemVerilog constructs used in the source code.

## ▶️ Running the Simulation

If Icarus Verilog is installed, open a terminal at the repository root and run:

```bash
iverilog -g2012 -s testbench -o sim.out \
  verilog-code/design.sv \
  testcases/testbench.sv
```

Run the compiled simulation:

```bash
vvp sim.out
```

Review the simulation output for the Fibonacci and factorial test results.

## 🎯 Project Objectives

- Understand processor datapath organization.
- Explore the interaction between the control unit, register file, ALU, and memory.
- Study instruction execution and program counter updates.
- Practice modular hardware design using Verilog/SystemVerilog.
- Develop testbench-based verification skills.
- Maintain a structured and version-controlled hardware design project.

## 🚀 Future Improvements

- Expand instruction support and verification coverage.
- Add individual testcases for arithmetic, logical, branch, jump, load, and store instructions.
- Improve automated verification with assertions and self-checking tests.
- Add waveform-based debugging and timing analysis.
- Document the processor datapath and control flow with architecture diagrams.

## 👨‍💻 Author

**Muhammad Hamza**

Interested in processor design, computer architecture, digital systems, embedded systems, and hardware description languages.

## 📄 License

A license has not yet been specified. Please add an appropriate license before allowing others to reuse or redistribute this project.
