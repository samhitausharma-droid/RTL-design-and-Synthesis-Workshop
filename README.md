# RTL-design-and-Synthesis-Workshop
RTL Design and Synthesis Workshop
# RTL Design and Synthesis using Verilog, Yosys & SKY130

## 📖 Overview

The semiconductor industry is rapidly transitioning towards open-source Electronic Design Automation (EDA) tools and Process Design Kits (PDKs) for ASIC design and prototyping. This repository documents my learning journey through the **RTL Design and Synthesis Workshop**, where I explore the complete RTL-to-Gate-Level design flow using industry-standard open-source tools.

Throughout this workshop, I learn how digital circuits are described using **Verilog HDL**, verified through **simulation**, synthesized into **logic gates**, and mapped to the **SKY130 Standard Cell Library**. The repository contains my notes, laboratory exercises, Verilog programs, testbenches, synthesis reports, and project implementations completed during the workshop.

The primary goal of this repository is to build a strong foundation in **RTL Design**, **Digital Logic Design**, and the **ASIC Design Flow** using freely available industry tools.

---

## 🎯 Objectives

- Learn the fundamentals of Verilog Hardware Description Language (HDL)
- Understand Register Transfer Level (RTL) design concepts
- Develop and simulate digital circuits
- Write and verify testbenches
- Perform logic synthesis using Yosys
- Explore the SKY130 Standard Cell Library
- Understand the complete RTL-to-Gate-Level design flow
- Gain practical exposure to ASIC design methodologies

---




## 📂 Repository Structure

This repository is organized module-wise, with each section containing detailed notes, source code, laboratory exercises, testbenches, synthesis results, and related resources. Refer to the **Table of Contents** below to navigate through the workshop content.

---

## 📚 References

- Verilog HDL
- Icarus Verilog
- GTKWave
- Yosys Open Synthesis Suite
- SKY130 Open PDK

---

###  L1 Introduction to iverilog design test bench

Simulator

A simulator is a software tool used to verify the functionality of a digital circuit by applying different input signals and observing the corresponding outputs. It helps ensure that the design works correctly before it is implemented on hardware.

Design

The design is the Verilog module that describes the intended digital logic or hardware functionality. It defines how the circuit behaves based on the given inputs.

Testbench

A testbench is a Verilog module used only for simulation. It generates input test cases (stimulus), applies them to the design, and checks whether the outputs match the expected results. It is not synthesized into hardware.

<img width="634" height="251" alt="image" src="https://github.com/user-attachments/assets/31b612bf-cdbb-43a0-a1e3-19a29c6cedf7" />

Iverilog based  simulation flow 

<img width="890" height="428" alt="image" src="https://github.com/user-attachments/assets/989504d2-c392-43f4-bedd-726acbfa16e6" />

### L1 Lab1 introduction to lab &&  L2 Lab2 Introduction iverilog gtkwave part1


<img width="948" height="539" alt="image" src="https://github.com/user-attachments/assets/7a515066-c443-423d-9af4-342bf9096b02" />


Before doing all this we need to first install iverilog and gtkwave 

we can install it using atp install iverilog and atp install gtkwave

after that we can continue to do our simulation 

1) We are simulating MUX
     Here we need to use the command iverilog good_mux_v and we also have a testbench of the same name we need to execute both of that
   and to get the wave form we need to use gtkwave


   <img width="959" height="526" alt="image" src="https://github.com/user-attachments/assets/cb583c19-fba9-49ac-8d3f-833bcbec5176" />

To check the transitions 

<img width="959" height="521" alt="image" src="https://github.com/user-attachments/assets/9f54fdfd-74d7-4462-94ec-28e82d984c8a" />

we need to use the botton highlighted 

<img width="959" height="546" alt="image" src="https://github.com/user-attachments/assets/8dda7958-29d7-40a3-8a94-04ee794d1776" />


### L3 Lab2 Introduction iverilog gtkwave part2

Let us look into the file structure 


<img width="945" height="430" alt="image" src="https://github.com/user-attachments/assets/2fc49d47-8667-477a-9be1-04936e05967f" />


For a 2:1 Multiplexer (MUX):

If sel = 0, the output follows i0.
If sel = 1, the output follows i1

<img width="357" height="116" alt="image" src="https://github.com/user-attachments/assets/2f2bd7b0-2bea-4d98-9eae-578b9a85c47d" />

we know that the testbench instantiates the design 





































