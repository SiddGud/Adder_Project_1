# 5-Bit Carry Look-Ahead Adder: Design, Implementation, and Analysis

This repository contains the complete design, implementation, and analysis of a **5-bit synchronous Carry Look-Ahead Adder (CLA)**[cite: 1, 8]. [cite_start]The project explores the full VLSI design flow, from 180nm CMOS logic gate characterization to post-layout simulation and FPGA hardware verification[cite: 8, 253, 470].

---

## ## Project Overview

[cite_start]The Carry Look-Ahead Adder addresses the high propagation delay typical of ripple carry adders by using a parallel approach to carry generation[cite: 7]. [cite_start]This design is implemented using **180nm CMOS technology** and utilizes **True Single-Phase Clock (TSPC)** master-slave D flip-flops to ensure synchronized operation[cite: 8, 75].

### ### Key Features
* [cite_start]**Architecture**: 5-bit CLA with Propagate/Generate logic, Carry Look-Ahead logic, and Sum Generation blocks[cite: 13, 14, 15, 16].
* [cite_start]**Logic Style**: Static CMOS logic utilizing NAND-based universal gates for high noise margins and low power consumption[cite: 34, 35, 36, 37].
* [cite_start]**Sequential Elements**: TSPC D-FFs at both input and output stages for stable data sampling and predictable timing[cite: 75, 77, 78].
* [cite_start]**Technology Node**: SCN6M_DEEP.09 (180nm)[cite: 253].

---

## ## Technical Specifications

### ### Performance Metrics
[cite_start]The system's timing was characterized by comparing ideal schematic results with post-layout simulations that include parasitic effects[cite: 258, 259, 320, 398].



| Parameter | Pre-Layout (Ideal) | Post-Layout (Real) |
| :--- | :--- | :--- |
| **Max Frequency ($F_{max}$)** | [cite_start]1.232 GHz [cite: 384] | [cite_start]548.5 MHz [cite: 399] |
| **Critical Path Delay ($t_{pd,max}$)** | [cite_start]0.594 ns [cite: 384] | [cite_start]1.503 ns [cite: 399] |
| **Setup Time ($t_{su}$)** | [cite_start]0.11 ns [cite: 399] | [cite_start]0.32 ns [cite: 399] |
| **Hold Time ($t_{h}$)** | [cite_start]0 ns [cite: 399] | [cite_start]0 ns [cite: 399] |

### ### Physical Design
[cite_start]The physical layout was created using the **MAGIC layout editor**[cite: 253].
* [cite_start]**Dimensions**: 273.52 $\mu m$ (Width) x 179.64 $\mu m$ (Height)[cite: 433, 435].
* [cite_start]**Total Area**: $\approx 48,000$ sq. microns[cite: 437].



---

## ## Architecture & Equations
[cite_start]The logic is based on the following iterative relationships[cite: 18, 22]:
* [cite_start]**Propagate**: $p_{i}=a_{i}\oplus b_{i}$ [cite: 20]
* [cite_start]**Generate**: $g_{i}=a_{i}\cdot b_{i}$ [cite: 20]
* [cite_start]**Carry Out**: $c_{i+1}=g_{i}+(p_{i}\cdot c_{i})$ [cite: 22]
* [cite_start]**Sum**: $S_i = p_i \oplus c_i$ [cite: 72]

---

## ## Project Structure
* [cite_start]`/Schematic`: NGSPICE netlists and simulation results[cite: 84].
* [cite_start]`/Layout`: MAGIC files and post-layout extracted SPICE netlists[cite: 253, 258].
* [cite_start]`/Verilog`: Structural HDL code for synchronous operation[cite: 440].
* [cite_start]`/FPGA`: Implementation files for target hardware[cite: 470].

---

## ## Author
[cite_start]**Siddhant Gudwani** [cite: 2]
[cite_start]Electronics and Communication Engineering, IIIT Hyderabad [cite: 3, 4]
