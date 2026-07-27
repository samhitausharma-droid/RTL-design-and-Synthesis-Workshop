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


###  L1 Introduction to yosys

**What is a SYNTHESIZER**

  It is a tool used for converting RTL into Netlist 
    Yosys is the synthesizer used here 

  **But what is a netlist?**
  
  Design (Verilog code) → Tells what the circuit should do.
  Netlist → Tells how the circuit is built using logic gates and how they're connected.

  In other words the netlist is the representation of the design in the form of the cells present in the .lib

  **Yosys setup**

  <img width="959" height="539" alt="image" src="https://github.com/user-attachments/assets/6fa915fa-5d4e-48e0-97d7-bc649e071cf9" />


  **Verify the synthesis**

  
<img width="712" height="392" alt="image" src="https://github.com/user-attachments/assets/5efaa011-ed3d-4d3b-824d-51ecaa66b039" />


### L2 introduction to logic synthesis part1


 <img width="724" height="535" alt="image" src="https://github.com/user-attachments/assets/e27ddb69-a327-4fdf-95ab-dbebfd5d86e9" />

 How do we map the rtl code and the design logic circuit

 Ans::<img width="725" height="536" alt="image" src="https://github.com/user-attachments/assets/e3435334-0d14-4cdb-9204-a38e7a11dbcc" />


 **What is .lib**

 # What is .lib

• .lib
  - Collection of logical modules.
  - Includes basic logic gates like And, Or, Not, etc...
  - Different flavors of same gate
      • 2 input And gate
          - Slow
          - Medium
          - Fast

      • 3 input And gate
          - Slow
          - Medium
          - Fast

      • 4 input And gate
          - Slow
          - Medium
          - Fast

      • ..................

Inside the .lib:

- AND GATE
- NOT GATE
- OR GATE
- ................

<img width="531" height="371" alt="image" src="https://github.com/user-attachments/assets/e26d314c-1854-498c-ad3b-bfa6afbc0eda" />


<img width="715" height="491" alt="image" src="https://github.com/user-attachments/assets/848a9a1b-62f5-46cf-b3a0-12ccdf17ec95" />


###  L3 introduction to logic synthesis part2


Why do we need slow cells ???

<img width="719" height="538" alt="image" src="https://github.com/user-attachments/assets/ef2f596a-47f5-4c58-990d-f51e4a998c94" />

**Faster VS Slower Cells**

<img width="727" height="538" alt="image" src="https://github.com/user-attachments/assets/792ea597-381c-48ab-87ff-bb3b1f876075" />


**Selection of cells**

<img width="717" height="518" alt="image" src="https://github.com/user-attachments/assets/a2f525a0-c5d0-4daa-afec-a7a1557848f4" />


**Synthesis Illustration**

<img width="723" height="550" alt="image" src="https://github.com/user-attachments/assets/15cdb89e-d3ab-41f4-a599-9508a049dfe2" />


### L1 Lab3 Yosys 1 good mux Part1

To invoke the YOSYS type yosys 













  



  




































