# KLH-AI&DS-2026-2030--15--ALU-8-bit
This project presents the Design and Simulation of an 8-Bit Arithmetic Logic Unit (ALU). It covers the ALU architecture, objectives, arithmetic and logical operations, control signals, simulation, and verification, along with GitHub guidelines, commit requirements, folder structure, README details, access rules, and final submission.
# ALU-8-bit

### 8-Bit Arithmetic Logic Unit

A complete design and implementation of an **8-bit Arithmetic Logic Unit (ALU)** — the core computational component of a processor responsible for performing arithmetic and logical operations on binary data.

---

## 📌 Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Supported Operations](#supported-operations)
- [Architecture](#architecture)
- [Block Diagram](#block-diagram)
- [Inputs & Outputs](#inputs--outputs)
- [Truth Table / Opcode Mapping](#truth-table--opcode-mapping)
- [Project Structure](#project-structure)
- [Technologies Used](#technologies-used)
- [How to Run / Simulation](#how-to-run--simulation)
- [Results & Waveforms](#results--waveforms)
- [Design Methodology](#design-methodology)
- [Future Improvements](#future-improvements)
- [License](#license)
- [Author](#author)

---

## 📖 Overview

The **Arithmetic Logic Unit (ALU)** is one of the most fundamental building blocks of any Central Processing Unit (CPU). It is responsible for executing arithmetic operations (addition, subtraction, increment, decrement, etc.) and logical operations (AND, OR, XOR, NOT, shifts, etc.) on binary numbers.

This project implements a fully functional **8-bit ALU** capable of processing two 8-bit operands and producing an 8-bit (or 16-bit in some cases) result based on a control/select signal (opcode). The design also includes status flags such as **Carry**, **Zero**, **Overflow**, and **Sign** for better integration into larger processor designs.

The ALU can be used as a standalone module or integrated into a larger 8-bit processor/CPU project.

---

## ✨ Features

- Fully synthesizable 8-bit ALU design
- Supports a wide range of arithmetic and logical operations
- Configurable through a multi-bit opcode/select line
- Status flags generation:
  - **Carry Flag (C)**
  - **Zero Flag (Z)**
  - **Overflow Flag (V)**
  - **Sign Flag (S)** / Negative Flag
- Modular and hierarchical design (easy to understand and modify)
- Includes comprehensive testbench for verification
- Suitable for FPGA implementation or simulation
- Clean and well-commented code

---

## 🧮 Supported Operations

| Opcode | Operation          | Description                          | Result Width |
|--------|--------------------|--------------------------------------|--------------|
| 0000   | ADD                | A + B                                | 8-bit + Carry |
| 0001   | SUB                | A - B (using 2's complement)         | 8-bit + Carry |
| 0010   | AND                | Bitwise AND of A and B               | 8-bit        |
| 0011   | OR                 | Bitwise OR of A and B                | 8-bit        |
| 0100   | XOR                | Bitwise XOR of A and B               | 8-bit        |
| 0101   | NOT A              | Bitwise complement of A              | 8-bit        |
| 0110   | Left Shift (LSL)   | Logical Left Shift of A              | 8-bit        |
| 0111   | Right Shift (LSR)  | Logical Right Shift of A             | 8-bit        |
| 1000   | Increment          | A + 1                                | 8-bit        |
| 1001   | Decrement          | A - 1                                | 8-bit        |
| 1010   | NAND               | Bitwise NAND                         | 8-bit        |
| 1011   | NOR                | Bitwise NOR                          | 8-bit        |
| 1100   | XNOR               | Bitwise XNOR                         | 8-bit        |
| 1101   | Compare (SLT)      | Set Less Than (A < B)                | 1-bit        |
| 1110   | Multiply (optional)| A × B                                | 16-bit       |
| 1111   | Reserved / NOP     | No Operation                         | -            |

> **Note:** You can modify the opcode mapping according to your design.

---

## 🏗 Architecture

The ALU is designed using a modular hierarchical approach:

1. **Arithmetic Unit**
   - 8-bit Ripple Carry Adder / Carry Look-Ahead Adder
   - 2's Complement Subtractor
   - Incrementer / Decrementer

2. **Logic Unit**
   - Bitwise AND, OR, XOR, NAND, NOR, XNOR, NOT

3. **Shifter Unit**
   - Logical Left Shift
   - Logical Right Shift
   - (Optional) Arithmetic Right Shift / Rotate

4. **Multiplexer / Control Logic**
   - Selects the final output based on the Opcode

5. **Flag Generation Logic**
   - Zero Flag: Result is all zeros
   - Carry Flag: From the adder/subtractor
   - Overflow Flag: Detected using XOR of carry bits
   - Sign Flag: MSB of the result

---


