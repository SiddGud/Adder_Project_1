# 5-Bit Carry Look-Ahead Adder: Design, Implementation, and Analysis

This repository contains the complete design, implementation, and analysis of a **5-bit synchronous Carry Look-Ahead Adder (CLA)**. The project explores the full VLSI design flow, from 180nm CMOS logic gate characterization to post-layout simulation and FPGA hardware verification.

---

## Project Overview

The Carry Look-Ahead Adder addresses the high propagation delay typical of ripple carry adders by using a parallel approach to carry generation. This design is implemented using **180nm CMOS technology** and utilizes **True Single-Phase Clock (TSPC)** master-slave D flip-flops to ensure synchronized operation.

### Key Features
* **Architecture**: 5-bit CLA with Propagate/Generate logic, Carry Look-Ahead logic, and Sum Generation blocks.
* **Logic Style**: Static CMOS logic utilizing NAND-based universal gates for high noise margins and low power consumption.
* **Sequential Elements**: TSPC D-FFs at both input and output stages for stable data sampling and predictable timing.
* **Technology Node**: SCN6M_DEEP.09 (180nm).

---

## Technical Specifications

### Performance Metrics
The system's timing was characterized by comparing ideal schematic results with post-layout simulations that include parasitic effects.



| Parameter | Pre-Layout (Ideal) | Post-Layout (Real) |
| :--- | :--- | :--- |
| **Max Frequency ($F_{max}$)** | 1.232 GHz | 548.5 MHz |
| **Critical Path Delay ($t_{pd,max}$)** | 0.594 ns | 1.503 ns |
| **Setup Time ($t_{su}$)** | 0.11 ns | 0.32 ns |
| **Hold Time ($t_{h}$)** | 0 ns | 0 ns |

### Physical Design
The physical layout was created using the **MAGIC layout editor**.
* **Dimensions**: 273.52 $\mu m$ (Width) x 179.64 $\mu m$ (Height).
* **Total Area**: $\approx 48,000$ sq. microns.



---

## Architecture & Equations
The logic is based on the following iterative relationships:
* **Propagate**: $p_{i}=a_{i}\oplus b_{i}$
* **Generate**: $g_{i}=a_{i}\cdot b_{i}$
* **Carry Out**: $c_{i+1}=g_{i}+(p_{i}\cdot c_{i})$
* **Sum**: $S_i = p_i \oplus c_i$

---

## Project Structure
* `/Schematic`: NGSPICE netlists and simulation results.
* `/Layout`: MAGIC files and post-layout extracted SPICE netlists.
* `/Verilog`: Structural HDL code for synchronous operation.
* `/FPGA`: Implementation files for target hardware.

---

## Author
**Siddhant Gudwani** Electronics and Communication Engineering, IIIT Hyderabad
