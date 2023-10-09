# Project_SRAM
"Unlocking Efficiency: Introducing our 16-byte SRAM in 0.18μm CMOS for Low-Power IoT Applications!

Before diving into the world of SRAM (Static Random-Access Memory), it's essential to understand why we need SRAM when DRAM (Dynamic Random-Access Memory) is already widely used in the world of computer memory. 
 DRAM is a large but slower whiteboard.
 It can store a lot of information, but it needs to refresh the content regularly, like rewriting things on the whiteboard so they don't fade away.
 DRAM is like a bigger storage space that takes a bit more time to find and use information.

SRAM (Static Random-Access Memory) is a type of computer memory that's like a super-fast and easily accessible storage space for data that your computer or electronic devices need right now. 
It helps your devices work quickly and efficiently by storing and retrieving information rapidly. 
It's commonly used in things like your computer's CPU to make it faster, and it's also used in various other electronic gadgets to speed up their operations.


Here's the block diagram for a 16-byte SRAM (Static Random-Access Memory) designed for low-power IoT (Internet of Things) applications in a 0.18μm CMOS (Complementary Metal-Oxide-Semiconductor) technology involves illustrating the major functional blocks and their interconnections. 

# Block diagram
![block_sram](https://github.com/Smrity004/Project_SRAM/assets/102158117/8cb663fd-c1fe-4a52-8d76-fa82e20454a7)

Let's break down the block diagram of your 16-byte SRAM in 0.18μm CMOS for Low-Power IoT Applications into individual blocks, each described in a separate sentence.

**Wordline Decoder:**
Responsible for selecting the specific wordline (row) within the memory array based on the memory address provided for read or write operations.

**Bitline Sense Amplifiers:**
Amplify minute voltage differences on the bitlines during read operations, enhancing the reliability of data retrieval.

**Write Control:**
This block manages write operations, ensuring accurate data is written into the selected memory cell through write drivers.

**Read Control:**
Responsible for overseeing read operations, assisting in the retrieval of data from the selected memory cell.

**Address Decoder:**
Takes the memory address as input and decodes it to select the appropriate row and column in the memory array.

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

Firstly, in  SRAM (Static Random-Access Memory) cells, NMOS (n-channel metal-oxide-semiconductor) transistors are not used for precharge due to their inability to efficiently pull bitlines to the required high voltage level (VDD). 
Instead, PMOS (p-channel metal-oxide-semiconductor) transistors are employed in the precharge circuit to establish a stable voltage reference point, typically at the midpoint between logic high and low. NMOS transistors, known for their fast switching speed, are reserved for read and write access operations, as they excel in rapidly changing the state of the SRAM cell.

![image](https://github.com/Smrity004/Project_SRAM/assets/102158117/b6aab5e7-48f8-4e77-aef3-a7b36bd05724)

In SRAM, the precharge operation is a vital step that readies the memory cell for data storage and retrieval. During precharge, the bitlines are reset to a stable voltage level, typically the midpoint between logic high and low, ensuring a known starting point for subsequent read and write operations. This step equalizes the SRAM cell's nodes, minimizes noise, and optimizes speed, enhancing the reliability and efficiency of data access in this type of memory.

### Sense Amplifier















