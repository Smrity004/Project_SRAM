# Project_SRAM
# Table of Content
- [Introduction](#introduction)
- [Block Diagram](#block-diagram)
- [Design Description](#design-discription)
- [Conclusion](#conclusion)
- [Result Analysis](result-analysis)


# Introduction

"Unlocking Efficiency: Introducing our 16-byte SRAM in 0.18μm CMOS for Low-Power IoT Applications!

Before diving into the world of SRAM (Static Random-Access Memory), it's essential to understand why we need SRAM when DRAM (Dynamic Random-Access Memory) is already widely used in the world of computer memory. 
 DRAM is a large but slower whiteboard.
 It can store a lot of information, but it needs to refresh the content regularly, like rewriting things on the whiteboard so they don't fade away.
 DRAM is like a bigger storage space that takes a bit more time to find and use information.

SRAM (Static Random-Access Memory) is a type of computer memory that's like a super-fast and easily accessible storage space for data that your computer or electronic devices need right now. 
It helps your devices work quickly and efficiently by storing and retrieving information rapidly. 
It's commonly used in things like your computer's CPU to make it faster, and it's also used in various other electronic gadgets to speed up their operations.


## Block Diagram
Here's the block diagram for a 16-byte SRAM (Static Random-Access Memory) designed for low-power IoT (Internet of Things) applications in a 0.18μm CMOS (Complementary Metal-Oxide-Semiconductor) technology involves illustrating the major functional blocks and their interconnections. 

![block_sram](https://github.com/Smrity004/Project_SRAM/assets/102158117/8cb663fd-c1fe-4a52-8d76-fa82e20454a7)

Let's break down the block diagram of your 16-byte SRAM in 0.18μm CMOS for Low-Power IoT Applications into individual blocks, each described in a separate sentence.
**Short description of each block in a typical SRAM**

**1. Wordline Decoder:**
Responsible for selecting the specific wordline (row) within the memory array based on the memory address provided for read or write operations.

**2. Bitline Sense Amplifiers:**
Amplify minute voltage differences on the bitlines during read operations, enhancing the reliability of data retrieval.

**3. Write Control(WR):**
This block manages write operations, ensuring accurate data is written into the selected memory cell through write drivers.

**4. Read Control:**
Responsible for overseeing read operations, assisting in the retrieval of data from the selected memory cell.

**5. Address Decoder:**
Takes the memory address as input and decodes it to select the appropriate row and column in the memory array.

Here, the block of my SRAM Project.

![image](https://github.com/Smrity004/Project_SRAM/assets/102158117/a5fc4363-b678-40bb-9201-3967325e63ab)


## DESIGN DISCRIPTION

**Let's delve into the detailed study of the different blocks involved in your 16-byte SRAM designed for low-power IoT applications in a 0.18μm CMOS technology.**

The Read Control block is crucial for balancing performance and power efficiency in SRAM memory, ensuring that read operations are both fast and energy-efficient, which is particularly important for IoT devices that need to conserve power while maintaining responsive data access.

### DC response of invertor
![image](https://github.com/Smrity004/Project_SRAM/assets/102158117/35d5b121-85e9-47e0-871a-dd1e40a98413)

The above graph shows DC response of invertor.
The DC response of an inverter involves the conversion of direct current (DC) power from sources like batteries or solar panels into alternating current (AC) electricity. This process relies on electronic components to rapidly switch the DC voltage, creating a clean and stable AC waveform suitable for powering household appliances and devices. Inverters can be adjusted to provide specific AC voltage and frequency outputs and aim for high efficiency while maintaining the quality of the AC power generated. This transformation is crucial for making DC power sources compatible with the electrical grid and various consumer electronics.
The graph of an inverter's DC response typically shows a horizontal line representing the constant input DC voltage. When the inverter is active, there will be a corresponding AC waveform with varying voltage and frequency, typically represented as a sine wave on the graph. The key aspect is the conversion from a steady DC input to an oscillating AC output, which can vary in terms of voltage and frequency based on the inverter's design


### 6T-SRAM Read Operation
![image](https://github.com/Smrity004/Project_SRAM/assets/102158117/0062879a-769d-4151-82b7-bde10c05fc71)

The above circuit show the read circuit of SRAM

![image](https://github.com/Smrity004/Project_SRAM/assets/102158117/26a29df6-1278-4fb6-a7d9-921a637a5b30)


### Write Operation
![image](https://github.com/Smrity004/Project_SRAM/assets/102158117/fc09d792-e085-49cd-b1ce-6a7094918dff)

### Precharge circuit of SRAM block
**Firstly**, the question arrises why we predischarge why not predischarge.
Predischarge in digital circuits, especially in memory elements like SRAM, is rarely used due to the disadvantages it introduces, such as data instability, reduced noise immunity, increased complexity, slower operation, higher power consumption, and incompatibility with established circuit designs.
On the otherhand precharging is the preferred method in SRAM because it provides a stable starting point for memory cells, ensuring data integrity, reliable write and read operations, noise immunity, and overall robust performance.

**Secondly**, in  SRAM (Static Random-Access Memory) cells, NMOS (n-channel metal-oxide-semiconductor) transistors are not used for precharge due to their inability to efficiently pull bitlines to the required high voltage level (VDD). 
Instead, PMOS (p-channel metal-oxide-semiconductor) transistors are employed in the precharge circuit to establish a stable voltage reference point, typically at the midpoint between logic high and low. NMOS transistors, known for their fast switching speed, are reserved for read and write access operations, as they excel in rapidly changing the state of the SRAM cell.

![image](https://github.com/Smrity004/Project_SRAM/assets/102158117/b6aab5e7-48f8-4e77-aef3-a7b36bd05724)

In SRAM, the precharge operation is a vital step that readies the memory cell for data storage and retrieval. During precharge, the bitlines are reset to a stable voltage level, typically the midpoint between logic high and low, ensuring a known starting point for subsequent read and write operations. This step equalizes the SRAM cell's nodes, minimizes noise, and optimizes speed, enhancing the reliability and efficiency of data access in this type of memory.

### Sense Amplifier

![image](https://github.com/Smrity004/Project_SRAM/assets/102158117/2bc39496-04bc-4dc1-98d7-3e48246a34be)


**Write enable(WR)**

Since in my SRAM architecture Sense Amplifier is always ON, here a am trying to elaborate the role of write enable in sram block.
In SRAM architecture, the sense amplifier is indeed a crucial component. It's used for reading the stored data in the SRAM cells. However, to write data into SRAM, you typically need a separate circuit for write enable (WE) control.
The Write Enable (WE) signal is an external control signal that plays a crucial role in the write operation. It determines whether data can be written into the SRAM cell or not. When the WE signal is set to a logic high (usually 1), it enables the write operation. Conversely, when the WE signal is set to a logic low (usually 0), it disables the write operation, ensuring that data remains unchanged within the SRAM cell.

Here's a simplified circuit diagram for a basic SRAM cell with a write enable (WE) control. 

![image](https://github.com/Smrity004/Project_SRAM/assets/102158117/659c78c4-3deb-4aa0-b4a7-e3fb8642ce9f)


#### Hand to hand design in Cadence

Let's provide a brief description of each block in SRAM architecture in more simplified terms, as if you were designing it by hand:
When working on a bottom-to-top design approach for an SRAM circuit in Cadence, it means starting with the smallest and most fundamental building blocks and progressively integrating them into a complete system. Here's how you can approach this process:
Starting from scratch, designing an SRAM block involves a systematic approach to create a reliable and efficient memory unit. Here's a step-by-step explanation of how you might begin and why each step is necessary:

###### Precharge circuit: 

The precharge circuit in an SRAM cell is responsible for ensuring that the bitlines (BL and BLB) are precharged to a certain voltage level before a read or write operation. Precharging is essential to establish a known starting point and to facilitate the accurate reading and writing of data. Let's explore how the precharge circuit precharges an 16x8 SRAM cell array.

file:///home/nfs2/vlab17/Pictures/pc%3C7:0%3E.png![image](https://github.com/Smrity004/Project_SRAM/assets/102158117/798266af-adcd-4353-b1a5-6356fa9af1b0)

###### Sense Amplifier: 

A sense amplifier in a 16x8 SRAM cell array is crucial for accurately detecting and amplifying the voltage differences on the bitlines (BL and BLB) during a read operation. In a 16x8 SRAM cell array, there are 16 rows and 8 columns of SRAM cells. Each SRAM cell has its own bitlines (BL and BLB), and the sense amplifier is used to read the data stored in a specific cell by sensing the voltage difference between these bitlines.
The sense amplifier in a 16x8 SRAM cell array plays a critical role in reading the data stored in SRAM cells accurately. It detects small voltage differences on the bitlines, amplifies them, and provides a clear and stable output that represents the stored logic state. This operation ensures reliable data access in the SRAM memory array.

![image](https://github.com/Smrity004/Project_SRAM/assets/102158117/74c22f23-b053-46b8-8f40-506d7a0cb0db)

###### Write enable(wr):

In SRAM (Static Random-Access Memory) design, the sense amplifier is like the "reader" that helps us figure out what's stored in the memory cells. But when we want to put new information into these cells, we need a special signal called Write Enable (WE).

Think of Write Enable like a "lock" or a "switch." When this lock is in the "open" position (like a 1 in digital terms), it allows us to write new data into the memory cell. However, when we switch the lock to the "closed" position (like a 0 in digital terms), it prevents us from changing the data stored in the memory cell. This way, we make sure we don't accidentally overwrite or mess up the information already there.

So, the sense amplifier helps us "read" the data, and the Write Enable signal acts like a "lock" to control whether we can "write" new data into the memory. Together, they ensure that data is stored and retrieved correctly in SRAM.


![image](https://github.com/Smrity004/Project_SRAM/assets/102158117/a743c3a6-9c44-4d10-9277-c2935238a808)


###### Decoder block

In a 16x8 SRAM memory, the decoder acts like a "traffic cop." When you want to find or change information stored in a specific part of the memory, you provide an address. The decoder takes that address and figures out exactly which spot in the memory grid you're talking about – which row and which column. It then turns on the right "roads" (wordlines and bitlines) to reach that spot.
Once there, you can either read what's already there or put new information in. 
The decoder makes sure you get to the right place in the memory every time you want to work with data. Simply, it's like your GPS for the memory grid, guiding you to the right location to find or store data.


![image](https://github.com/Smrity004/Project_SRAM/assets/102158117/0ee13df4-bc78-4143-ad9a-78b83bbbf0f9)


###### Sense Amplifier

![image](https://github.com/Smrity004/Project_SRAM/assets/102158117/3a01ed73-df22-4cd9-a0ac-e527e40ef4da)

###### Systematic 

![image](https://github.com/Smrity004/Project_SRAM/assets/102158117/a2907d0b-c15c-4ba2-bca8-2df955775a7b)

###### TOP Testbench

![image](https://github.com/Smrity004/Project_SRAM/assets/102158117/3d3b4684-c21b-4739-9a0b-1170c6878278)

## Conclusion

![image](https://github.com/Smrity004/Project_SRAM/assets/102158117/e164d1d0-088f-4de1-9917-c158eba53246)

#### Corner Analysis

![image](https://github.com/Smrity004/Project_SRAM/assets/102158117/cf82f577-da32-414d-a281-aae4e7ce18db)



























