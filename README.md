<img width="760" height="353" alt="image" src="https://github.com/user-attachments/assets/58ba544f-480e-4ffe-9a04-fde7642cb5bf" /># RTL-design-and-Synthesis-Workshop
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



<img width="670" height="458" alt="image" src="https://github.com/user-attachments/assets/1d8d76b9-4b51-4603-918b-3328128227e6" />]

if we are not getting the file name then we can find it by the command highlighted


<img width="380" height="421" alt="image" src="https://github.com/user-attachments/assets/a34ed455-7c57-455c-890e-747f662bed3a" />


To convert our rtl file into a gate and what gate it should link to is specified through the command

**abc -liberty**


<img width="234" height="58" alt="image" src="https://github.com/user-attachments/assets/3f23b7e4-6d7c-4fb2-9399-7da3aa5beeb3" />

<img width="283" height="106" alt="image" src="https://github.com/user-attachments/assets/ca803ea9-1cff-41e3-9aa4-23c1a510a19d" />

In order to see the logic 

type show 

<img width="959" height="530" alt="image" src="https://github.com/user-attachments/assets/fc943358-5fd6-407c-90ce-b462f1bf2225" />

This schematic represents a 2:1 multiplexer where i0 and i1 are the data inputs, sel is the select line, and y is the output. If sel = 0, the output follows i0; if sel = 1, the output follows i1.

 ### L3 Lab3 Yosys 1 good mux Part3

<img width="802" height="397" alt="image" src="https://github.com/user-attachments/assets/f615c0ff-6d0a-47e6-9bfb-92991b9b86a9" />




here we get the netlist 

The above code is the gate-level netlist generated by Yosys after synthesizing the RTL description of the good_mux module. Instead of using behavioral Verilog, the design is represented using Sky130 standard cells such as clkinv, nand2, and o21ai, which are available in the Sky130 standard cell library.

The intermediate wires (_0_, _1_, _2_, etc.) are automatically generated by the synthesis tool to connect the outputs of one standard cell to the inputs of another. These internal signals help implement the required logic while maintaining proper connectivity between gates.

The assign statements map the module inputs (i0, i1, and sel) to the internal wires and connect the final internal signal to the output (y). This synthesized netlist represents the actual hardware implementation of the 2:1 multiplexer that can be used for ASIC design and further physical implementation.


sky130_fd_sc_hd__clkinv_1 – Inverter (NOT gate)
sky130_fd_sc_hd__nand2_1 – 2-input NAND gate
sky130_fd_sc_hd__o21ai_0 – OR-AND-Invert standard cell used to optimize the multiplexer logic.

### L1 Lab4 Introduction to dot Lib part1

tt- stands for typical
025c-temperature

**Three Important things**
Process,Variation,Temperature


<img width="960" height="530" alt="image" src="https://github.com/user-attachments/assets/8a09bd06-f692-48fc-bc26-5cca3c4ff3bf" />


### L2 Lab4 Introduction to dot Lib part2


<img width="959" height="538" alt="image" src="https://github.com/user-attachments/assets/8d437b23-5e9f-49cd-95e9-9957cb127fd7" />


<img width="350" height="238" alt="image" src="https://github.com/user-attachments/assets/74ed9142-5694-406f-b0f0-173ccd2fa7ef" />




  

### L3 Lab4 Introduction to dot Lib part3

<img width="266" height="263" alt="image" src="https://github.com/user-attachments/assets/4a47deb2-e670-4f8c-a68e-76adf19a2a94" />





<img width="245" height="247" alt="image" src="https://github.com/user-attachments/assets/9b00b6a0-89df-4b43-8431-c49340c7def1" />


all 4 possible conditions are analysed


<img width="860" height="313" alt="image" src="https://github.com/user-attachments/assets/f64026fd-09ce-4bb5-b6b0-2ad65f67c268" />


we are comparing the 3 and gates of different types 

in terms of delay--->  and2_4 >and2_2 >and2_0
in terms of power--->  and2_0 >and2_2 >and2_4


## L1 Lab05 Hier synthesis flat synthesis part1


we will be using the file multiple_modules

<img width="959" height="518" alt="image" src="https://github.com/user-attachments/assets/a0406ab6-d8dc-4577-8e0a-bc74b665eb00" />


here we have two submodules and *&* or gate

<img width="592" height="270" alt="image" src="https://github.com/user-attachments/assets/33acdd23-2a9c-4196-a8b2-bdd96f3a4f03" />

this is how the logic works 



<img width="959" height="532" alt="image" src="https://github.com/user-attachments/assets/7fdef678-a79a-4335-83b3-3c744a03dd46" />




Ideally we will expect to see and gate and or gate but thats not the case we will see U1 and U2 instead 


<img width="959" height="524" alt="image" src="https://github.com/user-attachments/assets/ff215655-6be4-49ed-a633-ce0ba641a8cf" />

the hierarchy is preserved 

if we try to see the netlist 

<img width="599" height="352" alt="image" src="https://github.com/user-attachments/assets/d24d1366-d4ab-43e1-85bc-542d0cae202d" />



we expected a or gate we have nand and two invertors 


<img width="424" height="243" alt="image" src="https://github.com/user-attachments/assets/96947089-cebd-48cc-8514-515a2e3f47ee" />



**Why has it choesn a NAND implementation??**

<img width="449" height="262" alt="image" src="https://github.com/user-attachments/assets/e1dd6610-c1f2-4c44-af81-9e8b0f7b5593" />


### L2 Lab05 Hier synthesis flat synthesis part2

now we will flatten the netlist 


in the flatten list we wont see any hierarchy 

<img width="247" height="335" alt="image" src="https://github.com/user-attachments/assets/2b91ac7e-4d63-4df3-a602-f2d42efb4c59" />


We are not seeing U1 and U2 as we have flattened 

<img width="686" height="104" alt="image" src="https://github.com/user-attachments/assets/7bde5381-d3ca-4936-8124-12230b6b2f08" />


if we create only submodule 1


<img width="251" height="80" alt="image" src="https://github.com/user-attachments/assets/57d58536-88a9-4f3b-b5c0-b6dcdfbfc39d" />


But why did we do it ????

<img width="473" height="266" alt="image" src="https://github.com/user-attachments/assets/687c84fe-8354-473a-b95b-3b0bd6aa48a0" />


### L1 Why Flops and Flop coding styles part1


<img width="946" height="533" alt="image" src="https://github.com/user-attachments/assets/ed3b80b6-d8d1-4d9d-af03-a6be63906fb3" />


 ### L2 Why Flops and Flop coding styles part2

**D Flip-Flop with Asynchronous Reset**


**Code**

<img width="694" height="258" alt="image" src="https://github.com/user-attachments/assets/f6599242-caff-4cf0-879a-a25466e922c1" />

<img width="497" height="185" alt="image" src="https://github.com/user-attachments/assets/654267ac-6d18-4ca0-8758-20b1a8365061" />


The following diagram highlights the distinction between synchronous reset and 
asynchronous reset in D flip-flops, showing how the reset signal is implemented in each case.

<img width="797" height="389" alt="image" src="https://github.com/user-attachments/assets/524fabb3-e6a8-4d9a-9669-4ff234d506f9" />

### L3 Lab flop synthesis simulations part1

iverilog dff_asyncres.v tb_dff_asyncres.v
./a.out
gtkwave tb_dff_asyncres.vcd


type these commands 


<img width="760" height="353" alt="image" src="https://github.com/user-attachments/assets/20550e85-c3bd-442c-a2d6-23dab888f035" />


### L4 Lab flop synthesis simulations part2

When we synthesize with YOSYS 



<img width="914" height="242" alt="image" src="https://github.com/user-attachments/assets/e503f3f6-3509-4df1-8d37-e03b74d805dd" />

There is no set and reset pin 

<img width="959" height="388" alt="image" src="https://github.com/user-attachments/assets/d38424d8-010b-4fcd-9a09-b6d36c413a61" />

Explanation 




