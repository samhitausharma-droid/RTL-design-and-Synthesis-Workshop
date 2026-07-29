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


###  L5 Interesting optimisations part1

Multiplying by the powers of two is just **SHIFTING**
We do not require any hardware for this 


<img width="693" height="394" alt="image" src="https://github.com/user-attachments/assets/17ec07c7-9c07-4329-800c-cf9a46714fc2" />


Its basically appending **TWO ZEROS** in this example



This is the Mul2 and Mul8

<img width="953" height="452" alt="image" src="https://github.com/user-attachments/assets/5afae933-ae59-4dfa-af5c-63aa47041962" />


<img width="498" height="170" alt="image" src="https://github.com/user-attachments/assets/83d4071e-7387-4513-918b-ca24eb9acbbf" />


Since we do not require any hardware the number of memory,memory bits,processors and cells are **0**


<img width="960" height="530" alt="image" src="https://github.com/user-attachments/assets/6d432b39-a2b9-4969-8601-70b2f73c1e56" />

OUTPUT


<img width="959" height="443" alt="image" src="https://github.com/user-attachments/assets/dcb7d9a8-7512-420f-9e61-e81c27fd082b" />



### L6 Interesting optimisations part2


<img width="485" height="263" alt="image" src="https://github.com/user-attachments/assets/02d9b247-669e-4d7a-85fd-6eff1b59f0ca" />

THIS IS HOW IT WILL LOOK LIKE 


<img width="493" height="278" alt="image" src="https://github.com/user-attachments/assets/631103dc-c30b-44e2-928e-262f03ac1939" />


For Mult 8


<img width="959" height="535" alt="image" src="https://github.com/user-attachments/assets/550cb4f4-9def-4eb6-8be5-fe8e130b2dcb" />


<img width="959" height="526" alt="image" src="https://github.com/user-attachments/assets/4d129e33-a164-4266-8ee2-e410f6825f6a" />

Here also the number of standard cells is **0**

OUTPUT 


<img width="959" height="254" alt="image" src="https://github.com/user-attachments/assets/23280022-64af-49b3-81fa-8bde39bda9bd" />

###  L1 Introduction to optimisations part1



<img width="959" height="553" alt="image" src="https://github.com/user-attachments/assets/8d983e63-e8be-430b-89be-e294b5bbd3c7" />



<img width="959" height="527" alt="image" src="https://github.com/user-attachments/assets/a81f0743-cf91-4f32-94c0-b9f45d2aafb6" />



<img width="959" height="532" alt="image" src="https://github.com/user-attachments/assets/2b49bc96-9e68-410d-bb3b-253ab7275832" />


###  L2 Introduction to optimisations part2



<img width="956" height="527" alt="image" src="https://github.com/user-attachments/assets/af5c520b-5ccd-4911-aaa8-06d06e83d0e9" />



<img width="959" height="536" alt="image" src="https://github.com/user-attachments/assets/f4d91839-14f4-4975-8c20-45741527d5aa" />

###  L3 Introduction to optimisations part3


<img width="951" height="568" alt="image" src="https://github.com/user-attachments/assets/e40c294f-ec68-4bf4-bc00-7fe50716d1ba" />



### L1 Lab06 Combinational Logic Optimisations part1



<img width="446" height="250" alt="image" src="https://github.com/user-attachments/assets/e07f28ea-456a-4fc8-9ba1-bd202c3841e1" />



Optcheck1 


<img width="955" height="530" alt="image" src="https://github.com/user-attachments/assets/68b446f2-a1c1-4a22-9d2c-be110b92a885" />


Optcheck2


<img width="573" height="205" alt="image" src="https://github.com/user-attachments/assets/2eb46125-2755-43ae-b715-87866452b1ae" />



### L2 Lab06 Combinational Logic Optimisations part2


<img width="452" height="265" alt="image" src="https://github.com/user-attachments/assets/79bea3de-7191-4a45-b95b-4fbd52110dab" />


Opt check 3


<img width="748" height="280" alt="image" src="https://github.com/user-attachments/assets/ef22ace4-07d0-4ce8-a836-46b80dccda74" />


Opt check 4


<img width="753" height="257" alt="image" src="https://github.com/user-attachments/assets/cc738c7e-3ea2-41a2-924b-466a1559b4f4" />


###  L1 Lab07 Sequential Logic Optimisations part1


dff_const1

This D flip-flop has an asynchronous active-high reset. When reset = 1, the output q is immediately reset to 0, independent of the clock. When reset = 0, the flip-flop loads a constant logic 1 on the next positive edge of the clock, so q becomes 1.

dff_const2

This D flip-flop continuously assigns a constant logic 1 to the output. Since both the if and else conditions assign q = 1, the reset signal has no effect, and the output remains permanently high (1) regardless of the clock or reset.


<img width="514" height="253" alt="image" src="https://github.com/user-attachments/assets/5473759a-eb42-480a-a2cc-5a51a348e31d" />



<img width="957" height="540" alt="image" src="https://github.com/user-attachments/assets/c16c89ce-8548-49a3-8420-4e45c0df5b2c" />



<img width="621" height="395" alt="image" src="https://github.com/user-attachments/assets/1e15557c-7893-482f-84a9-1e71b8d9bb28" />



<img width="915" height="304" alt="image" src="https://github.com/user-attachments/assets/b862c5da-a970-4fc5-8a28-00837eabea92" />


 ### L2 Lab07 Sequential Logic Optimisations part2



<img width="970" height="482" alt="image" src="https://github.com/user-attachments/assets/21e5f0a0-1ce6-4960-b277-3a23cff0894d" />


in dff_const1 it has inferred a dff 
but in dff_const2 it has not inferred anything 


<img width="959" height="538" alt="image" src="https://github.com/user-attachments/assets/8c75f5d8-eb2f-4597-b47a-b98c300cb0c9" />


<img width="959" height="463" alt="image" src="https://github.com/user-attachments/assets/a60dd2c7-7b62-4779-8cd9-85e8d847969f" />

### L3 Lab07 Sequential Logic Optimisations part3



<img width="925" height="447" alt="image" src="https://github.com/user-attachments/assets/a54b9226-3e03-4e25-8506-e672a8f3167d" />



<img width="472" height="256" alt="image" src="https://github.com/user-attachments/assets/914a4da9-f56f-4d2d-bd93-cc5a0221fb8c" />


<img width="925" height="294" alt="image" src="https://github.com/user-attachments/assets/4a146009-cd3b-46c9-81c4-47ad78753806" />



### L1 Seq optimisation unused outputs part1


<img width="959" height="497" alt="image" src="https://github.com/user-attachments/assets/6e38ef4f-cba6-4ff5-86af-7ee751d0b925" />


<img width="944" height="409" alt="image" src="https://github.com/user-attachments/assets/bc6cc76b-f0c7-4cb4-8055-759cf5310d0e" />


actual explanation 



<img width="921" height="227" alt="image" src="https://github.com/user-attachments/assets/e53ab5c4-5a19-476b-bf5a-6273073a889b" />


OUTPUT 

### L2 Seq optimisation unused outputs part2



<img width="554" height="467" alt="image" src="https://github.com/user-attachments/assets/042a0240-8649-471a-9c3b-dbed8df475c3" />


<img width="350" height="186" alt="image" src="https://github.com/user-attachments/assets/88bcb9cc-c92e-4897-bdbd-f94d283d2661" />

WE HAD INFERRED 3FF AND WE ALSO GOT 3FF



<img width="911" height="393" alt="image" src="https://github.com/user-attachments/assets/6f46151b-425d-43f4-bab7-f795077986bf" />



IF WE LOOK AT Q LOGIC ALONE::



<img width="959" height="416" alt="image" src="https://github.com/user-attachments/assets/48ae0501-91f2-4e67-bccf-8538d2812d53" />


### DAY 4  GLS, blocking vs non-blocking and Synthesis-Simulation mismatch

### L1 GLSConceptsAndFlowUsingIverilog


GLS---> stands for GATE LEVEL SIMULATION


**WHAT IS GLS?? AND WHY DO WE NEED GLS???**


<img width="950" height="488" alt="image" src="https://github.com/user-attachments/assets/c54c4d0e-c2ab-45c8-89c8-5cea56b98d53" />

What is GLS (Gate-Level Simulation)?
Gate-Level Simulation (GLS) is the process of simulating the synthesized gate-level netlist using the same testbench that was used for RTL simulation.
In GLS, the netlist acts as the Design Under Test (DUT) instead of the RTL code.
The synthesized netlist is functionally equivalent to the RTL design, so the same testbench can be reused without any modifications.
GLS is performed to verify that the synthesized netlist behaves exactly like the original RTL design.


Why is GLS?
To verify the functional correctness of the synthesized design after synthesis.
To ensure that the synthesized netlist produces the same output as the RTL design.
To identify synthesis-related errors such as logic optimization issues, incorrect connections, or functional mismatches.
To verify that the design satisfies the required timing constraints.
For timing verification, GLS is performed with delay annotation (back-annotated delays) to detect setup violations, hold violations, race conditions, and other timing-related issues before hardware implementation.
GLS increases confidence that the synthesized hardware will function correctly when implemented on the target device.




<img width="959" height="518" alt="image" src="https://github.com/user-attachments/assets/21d1fdc7-1757-41e5-a696-9ad8e177abe0" />


***Sythesis Simulation Mismatch***

The RTL design assign y = (a & b) | c is synthesized into a gate-level netlist consisting of an AND gate followed by an OR gate, while preserving the same logical functionality.
During Gate-Level Simulation (GLS), the synthesized netlist is simulated using the same testbench to verify that its behavior matches the original RTL design.
If the RTL simulation and gate-level simulation produce different outputs, it indicates a synthesis simulation mismatch, which may be caused by synthesis optimizations, missing sensitivity lists, or timing-related issues


<img width="926" height="426" alt="image" src="https://github.com/user-attachments/assets/00c7a720-b4d2-4193-89da-c5dd1d109bc4" />



### L2 SynthesisSimulationMismatch

**but why is it happening??**



<img width="784" height="362" alt="image" src="https://github.com/user-attachments/assets/3a9c0604-dc56-48f9-85ef-9836c83350ee" />








<img width="959" height="536" alt="image" src="https://github.com/user-attachments/assets/6e2f5055-43c9-437e-a29f-988784029cf7" />


In the first code, the always @(sel) block is triggered only when the select (sel) signal changes. If i0 or i1 changes while sel remains constant, the output y is not updated, causing a simulation mismatch.
In the second code, always @(*) automatically includes all input signals in the sensitivity list. Therefore, the block is re-evaluated whenever i0, i1, or sel changes, ensuring the output is always correct.
Hence, always @(*) should be used for combinational logic to avoid missing sensitivity list issues and prevent RTL-to-GLS simulation mismatches.



###  L3 BlockingAndNonBlockingStatementsInVerilog


**Blocking and Non-Blocking statements in verilog**



<img width="956" height="465" alt="image" src="https://github.com/user-attachments/assets/390a7878-27fb-4414-a928-2fd1ce9b7ba6" />





<img width="954" height="518" alt="image" src="https://github.com/user-attachments/assets/2d8d26fb-5e71-49ad-b181-867c4b02a9a2" />

In sequential circuits, using blocking (=) assignments inside a clocked always block can produce incorrect simulation results because statements execute sequentially, allowing updated values to be used immediately.
In the first example, q = q0; is executed before q0 = d;, so q receives the previous value of q0, correctly modeling two cascaded D flip-flops.
In the second example, q0 = d; is executed before q = q0;, causing q to receive the new value of d in the same clock cycle. This removes the intended one-clock delay, resulting in simulation-synthesis mismatch.


### L4 CaveatsWithBlockingStatements



**ALWAYS USE NON-BLOCKING STATEMENTS FOR SEQUENTIAL CRICUITS**



<img width="959" height="545" alt="image" src="https://github.com/user-attachments/assets/4d01c522-f225-4b50-bacf-384cd3795a26" />



### L1 Lab GLS Synth Sim Mismatch part1




<img width="959" height="538" alt="image" src="https://github.com/user-attachments/assets/abc3cea0-7bfb-4d9e-8666-129eae5a8fc8" />



<img width="751" height="341" alt="image" src="https://github.com/user-attachments/assets/10af76e2-5b99-40d1-b77f-1af5e8af3d95" />



<img width="677" height="196" alt="image" src="https://github.com/user-attachments/assets/1496eda0-c9f6-4206-827a-dc27204dd8a4" />




<img width="462" height="251" alt="image" src="https://github.com/user-attachments/assets/01acd398-03cb-4ef6-9c20-0de90d1a25b9" />


### L2 Lab GLS Synth Sim Mismatch part2


For Bad_MUX


<img width="758" height="332" alt="image" src="https://github.com/user-attachments/assets/cb0db31d-e30a-4d70-8d66-f1192ed7d832" />


**But what is the issue???**

Issues:

Incomplete sensitivity list: The sensitivity list should include all input signals (i0, i1, and sel). Otherwise, the output may not update whenever an input changes, leading to incorrect RTL simulation results.
Use of non-blocking assignment in combinational logic: Combinational circuits should use blocking assignments (=) instead of non-blocking assignments (<=). Using non-blocking assignments in combinational logic may result in simulation-synthesis mismatche


The output y remains incorrect until sel changes because the sensitivity list is incomplete. This results in an RTL simulation error, whereas the synthesized hardware updates immediately whenever any input changes, causing a **simulation-synthesis mismatch.**



### L1 Lab Synth sim mismatch blocking statement part1



<img width="959" height="494" alt="image" src="https://github.com/user-attachments/assets/950c16a0-728f-4c66-b506-92667eb80845" />




<img width="455" height="237" alt="image" src="https://github.com/user-attachments/assets/6f5270af-645c-43f1-b95d-c1e2321765f3" />


If we do the RTL simulation 
we get



<img width="928" height="409" alt="image" src="https://github.com/user-attachments/assets/46ff843a-16f1-459e-b083-f32f35f6f870" />

our point of interset 


<img width="781" height="134" alt="image" src="https://github.com/user-attachments/assets/cb15ae04-f800-4fe9-98cc-a88e24c34708" />


### L2 Lab Synth sim mismatch blocking statement part2


When we synthesize it we get 


<img width="923" height="333" alt="image" src="https://github.com/user-attachments/assets/1c32cec2-bf3b-4c1f-b2b2-db7d585b232b" />

**Waveform**


<img width="923" height="406" alt="image" src="https://github.com/user-attachments/assets/4c9bd443-5b8b-4714-b963-0c502bd5006e" />



<img width="933" height="200" alt="image" src="https://github.com/user-attachments/assets/396fc77a-3593-4edd-aa56-461f8d4757e6" />


**HERE WE CAN SEE THE SYNTEHSIS SIMULATION MISMATCH**


### Day 5 - Optimization in synthesis

### L1 IF CASE Constructs part1






