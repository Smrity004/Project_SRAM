# 16 byte SRAM in 0.18um CMOS for Low-Power IoT Applications

## Specifications of SRAM

Supply Voltage | Time Period   | Frequency     |
| -------------| ------------- | ------------- |
| 1.8V         |   60 ns       | 16.66 MHz     |


## Tool Used: Cadence

Schematic       | Simulation    | 
| ------------- | ------------- | 
| Virtuoso      | Spectre       |              
  

## Table of Content
- [Introduction](#introduction)
- [Block Diagram](#block-diagram)
- [Design Description](#design-discription)
- [Result Analysis](result-analysis)
- [Conclusion](#conclusion)
- [Bibliography](#bibliography)


## Introduction

Introducing our 16-byte SRAM in 0.18μm CMOS for Low-Power IoT Applications!

 Before diving into the world of SRAM (Static Random-Access Memory), it's essential to understand why we need SRAM when DRAM (Dynamic Random-Access Memory) is already widely used in the world of computer memory. 
 
 DRAM is a smaller but slower whiteboard( this is because to read the data, the charge in the capacitor needs to be sensed, which is a relatively slow process), it consists of a single transistor and a capacitor so,results in lower power consumption. It can store a lot of information, but it needs to refresh the content regularly, like rewriting things on the whiteboard so they don't fade away. It's a volatile memory, which means it loses its data when the power is turned off. DRAM is like a bigger storage space that takes a bit more time to find and use information.


SRAM (Static Random-Access Memory) is a type of computer memory that's like a super-fast and easily accessible storage space for data that our computer or electronic devices need right now. 
It helps your devices work quickly and efficiently by storing and retrieving information rapidly. Each SRAM cell typically uses multiple transistors (usually six) to store a single bit of data. The data is stored **as a flip-flop circuit**, which allows for very fast access times. Since SRAM cells don't rely on capacitors and charge, there's no need for refreshing, and data can be read quickly.
It's commonly used in things like our computer's CPU to make it faster, and it's also used in various other electronic gadgets to speed up their operations.


### Block Diagram
Here's the block diagram for a 16-byte SRAM designed for low-power IoT applications in a 0.18μm CMOS technology involves illustrating the major functional blocks and their interconnections. 

![image](https://github.com/Smrity004/Project_SRAM/assets/102158117/472ecf1d-814a-43af-92d9-ae978928e937)


<p align="center">
  Fig.1: Block diagram of SRAM
</p>




The above figure shows the 16x8 SRAM architecture refers to a specific organization of SRAM cells in an array. 

**16 Rows**: This part of the architecture indicates that there are 16 rows of SRAM cells in the memory array. Each row consists of a set of SRAM cells that store data. Rows are often referred to as wordlines (WLs) in SRAM design.

**8 Columns**: The "8" in the architecture tells us that there are 8 columns of SRAM cells in the array. Each column is associated with a pair of bitlines: a bitline (BL) and its complement (BLB). These bitlines are used for reading and writing data to and from the SRAM cells.

So, in a 16x8 SRAM architecture, you have a grid-like structure with 16 rows and 8 columns of SRAM cells. Each SRAM cell is at the intersection of a row and a column, and they collectively make up the memory array. This organization allows for the storage and retrieval of data in a structured and addressable manner.

Now,
Let's break down the block diagram of your 16-byte SRAM in 0.18μm CMOS for Low-Power IoT Applications into individual blocks, each described in a separate sentence.


**Short description of each block in a typical SRAM**

**1. Wordline Decoder:**
Responsible for selecting the specific wordline (row) within the memory array based on the memory address provided for read or write operations.

**2. Sense Amplifiers:**
Amplify minute voltage differences on the bitlines during read operations, enhancing the reliability of data retrieval.

**3. Write Control(WR):**
This block manages write operations, ensuring accurate data is written into the selected memory cell through write drivers.

**4. Read Control:**
Responsible for overseeing read operations, assisting in the retrieval of data from the selected memory cell.

**5. Address Decoder:**
Takes the memory address as input and decodes it to select the appropriate row and column in the memory array.



### DESIGN DISCRIPTION

**Let's delve into the detailed study of the different blocks involved in your 16-byte SRAM designed for low-power IoT applications in a 0.18μm CMOS technology.**

The Read Control block is crucial for balancing performance and power efficiency in SRAM memory, ensuring that read operations are both fast and energy-efficient, which is particularly important for IoT devices that need to conserve power while maintaining responsive data access.


### 6T-SRAM
![image](https://github.com/Smrity004/Project_SRAM/assets/102158117/6eb63480-4436-4701-b81d-f2636d98bf22)

The above circuit show the read circuit of SRAM.


### Transister Sizing in SRAM

The below expression show how I have dicided the sizing of SRAM,

![image](https://github.com/Smrity004/Project_SRAM/assets/102158117/04cda667-fa25-46d8-b14b-070da1c5bc95)


Let voltage at node C1=0.3 (0.3 is the stable voltage so that tr T2 not grt ON)
Then
T1= ON(**Saturation**)
and T5(**Liner region**)

 **I4(sat)=I1(lin)**

![image](https://github.com/Smrity004/Project_SRAM/assets/102158117/7f965590-628f-4ace-9445-25ed4e5ebfdd)


Sizing of Transister T3 and T5
**I3(sat)=I5(lin)**

![image](https://github.com/Smrity004/Project_SRAM/assets/102158117/e359ac41-51b7-4d1a-aac5-7b0cbeda43f0)


### Read Operation
   During the read phase:

a. A specific wordline is activated, which enables access to a particular SRAM cell in the array.

b. When you read a "1," it means that one of the transistors (e.g., T4 or T6) in the SRAM cell is turned on, which connects one of the bitlines to the cell. This, in turn, causes the voltage on the bitline to drop slightly.

c. The data-read circuitry detects this small voltage difference and amplifies it, effectively converting it into a logic "1" data output.

d. Conversely, if you were reading a "0," , T1 and T5 is on and the bitline voltage would stay at the precharged level, and bitline bar is showly discharged indicating a logic "0."
This voltage difference detection and amplification process is what allows SRAM to rapidly and accurately read data without the need for refreshing, making it well-suited for applications that require fast and reliable data retrieval.


The Fig.3 graph shows the read operation ie.,
1. During the read phase, the Q node (the output) is connected to one of the bitlines (either BL or BLB).
2. The Q node starts to discharge toward GND (low) through the connected bitline.
3. When the Q node voltage drops below a certain threshold, it's detected and amplified as a logic "0" data output.

<p align="center">
  Fig.3: Read operation of SRAM
</p>

![image](https://github.com/Smrity004/Project_SRAM/assets/102158117/26a29df6-1278-4fb6-a7d9-921a637a5b30)


### Write Operation

![image](https://github.com/Smrity004/Project_SRAM/assets/102158117/9de521a3-b568-4722-8e71-6565dd5c256d)


<p align="center">
  Fig.4: Write operation of SRAM
</p>


When we want to 'write' data into SRAM (a type of computer memory) , we need to make sure that the memory cells store a 'logic-low' value, which is typically represented by 0. To do this, we need a way to connect the memory cells to the ground (0 V) selectively when we want to write. This is where a special circuit comes into play.

In the circuit, we use nMOS transistors, specifically T1 and T2, to bring down the voltage in the memory cells. There's also another transistor, T3, which completes the connection to the ground. Importantly, T3 only turns on when we want to write data to a specific location in the memory, determined by the 'column address.'

The transistors that bring down the voltage in the memory cells (T1 and T2) need to be big enough (meaning they have a sufficiently large size) to ensure the voltage gets very close to 0 V during a 'write' operation.

The 'write' operation is controlled by signals. One signal, called 'write-enable,' tells the circuit when it's time to write data. The actual data we want to write is called 'DATA.' Together, these signals create the control signals that determine when and where the write operation happens.

The input circuitry, which processes the data to be written, can be shared among multiple memory cells, as long as only one cell is active or selected at any given moment. This ensures that we write the correct data to the intended location in memory."

The Fig.4 graph shows how write operation in performed:

1. The Q node is connected to the high bitline (BL or BLB).
2. The Q node starts to charge toward VDD.
3. When the Q node voltage reaches a certain threshold (VTH), the given data (let data=1) is confirmed and stored as a logic "1" in the SRAM cell.

The graph below shows the write operation.

![image](https://github.com/Smrity004/Project_SRAM/assets/102158117/54bf4897-9b05-4cf7-9a43-f42f55ec547a)


### Precharge circuit of SRAM block

**Firstly**, the question arrises why we precharge why not predischarge.
Predischarge in digital circuits, especially in memory elements like SRAM, is rarely used due to the disadvantages it introduces, such as the area increases as we have to use PMOS ,slower operation(PMOS is used-> Area increases -> Capacitance increases), higher power consumption(As area increases).

Here, is the table which show why I did Precharging,

 Transister    | PMOS(Precharge)  | NMOS(Predischarge)  |
| -------------| -------------    | -------------       |
| T5           | 0.25u/0.18u      |  2.5u/0.18u         |
| T3           | 0.568u/0.18u     |  2.5u/0.18u         |
| T1           | 0.294u/0.18u     |  0.25u/0.18u        |
| Total Area( in sq.units)        | 0.945     |  0.2          |

Therefore we can see the area of PMOS is **4.47** times more than PMOS which is approximately **5 times** more than NMOS.
So, we go more Precharging ,it is the preferred method in SRAM because it provides a stable starting point for memory cells, ensuring data integrity, reliable write and read operations, noise immunity, and overall robust performance.

**Secondly**, in  SRAM (Static Random-Access Memory) cells, NMOS (n-channel metal-oxide-semiconductor) transistors are not used for precharge due to their inability to efficiently pull bitlines to the required high voltage level (VDD). 
Instead, PMOS (p-channel metal-oxide-semiconductor) transistors are employed in the precharge circuit to establish a stable voltage reference point, typically at the midpoint between logic high and low. NMOS transistors, known for their fast switching speed, are reserved for read and write access operations, as they excel in rapidly changing the state of the SRAM cell.

![image](https://github.com/Smrity004/Project_SRAM/assets/102158117/ee813d2c-9c10-426b-8ad3-79588f6dd4e0)


<p align="center">
  Fig.5: Block diagram of Precharge block
</p>



In SRAM, the precharge operation is a vital step that readies the memory cell for data storage and retrieval. During precharge, the bitlines are reset to a stable voltage level, typically the midpoint between logic high and low, ensuring a known starting point for subsequent read and write operations. This step equalizes the SRAM cell's nodes, minimizes noise, and optimizes speed, enhancing the reliability and efficiency of data access in this type of memory.

### Sense Amplifier

![image](https://github.com/Smrity004/Project_SRAM/assets/102158117/40251edb-a0e5-4c16-8bef-1ea968cad683)


<p align="center">
  Fig.6: Block diagram of Precharge block
</p>

![image](https://github.com/Smrity004/Project_SRAM/assets/102158117/abc61968-14ce-47ab-ad96-8b650f1cbcf0)
 

### Write Driver

Since in my SRAM architecture Sense Amplifier is always ON, here a am trying to elaborate the role of write enable in sram block.
In SRAM architecture, the sense amplifier is indeed a crucial component. It's used for reading the stored data in the SRAM cells. However, to write data into SRAM, we typically need a separate circuit of write driver control.
The Write Driver signal is an external control signal that plays a crucial role in the write operation, it is used to give a data to the sram,  what we need to write. When it is set to a logic high, one is written to SRAM and when zero in given than 0 is given to the SRAM. Here, I have used a switch in which when RD is 1 and RW is 0 then data is passed to BL and datab is passed to BLB.

Here's a simplified circuit diagram for a basic SRAM cell with a write enable control. 

<p align="center">
  Fig.7:Driver block of SRAM
</p>

![image](https://github.com/Smrity004/Project_SRAM/assets/102158117/9be6b268-20e2-47c0-b3e2-5de570b2bf73)


### Decoder block

In a 16x8 SRAM memory, the decoder acts like a "traffic cop." When you want to find or change information stored in a specific part of the memory, you provide an address. The decoder takes that address and figures out exactly which spot in the memory grid you're talking about – which row and which column. It then turns on the right "roads" (wordlines and bitlines) to reach that spot.
Once there, you can either read what's already there or put new information in. 
The decoder makes sure you get to the right place in the memory every time you want to work with data. Simply, it's like your GPS for the memory grid, guiding you to the right location to find or store data.

<p align="center">
  Fig.8:Decoder block of SRAM
</p>

![image](https://github.com/Smrity004/Project_SRAM/assets/102158117/254446ef-b7d9-446a-a0fe-e23c30d7c570)


## Cadence Simulations

Let's provide a brief description of each block in SRAM architecture in more simplified terms, as if you were designing it by hand:
When working on a bottom-to-top design approach for an SRAM circuit in Cadence, it means starting with the smallest and most fundamental building blocks and progressively integrating them into a complete system. Here's how you can approach this process:
Starting from scratch, designing an SRAM block involves a systematic approach to create a reliable and efficient memory unit. Here's a step-by-step explanation of how you might begin and why each step is necessary:

### Precharge circuit: 

The precharge circuit in an SRAM cell is responsible for ensuring that the bitlines (BL and BLB) are precharged to a certain voltage level before a read or write operation. Precharging is essential to establish a known starting point and to facilitate the accurate reading and writing of data. Let's explore how the precharge circuit precharges an 16x8 SRAM cell array.

<p align="center">
  Fig.9:Precharge circuit
</p>

![image](https://github.com/Smrity004/Project_SRAM/assets/102158117/798266af-adcd-4353-b1a5-6356fa9af1b0)

### Sense Amplifier: 

A sense amplifier in a 16x8 SRAM cell array is crucial for accurately detecting and amplifying the voltage differences on the bitlines (BL and BLB) during a read operation. In a 16x8 SRAM cell array, there are 16 rows and 8 columns of SRAM cells. Each SRAM cell has its own bitlines (BL and BLB), and the sense amplifier is used to read the data stored in a specific cell by sensing the voltage difference between these bitlines.
The sense amplifier in a 16x8 SRAM cell array plays a critical role in reading the data stored in SRAM cells accurately. It detects small voltage differences on the bitlines, amplifies them, and provides a clear and stable output that represents the stored logic state. This operation ensures reliable data access in the SRAM memory array.

<p align="center">
  Fig.10:Sense Amplifier
</p>

![image](https://github.com/Smrity004/Project_SRAM/assets/102158117/74c22f23-b053-46b8-8f40-506d7a0cb0db)

Fig.10 shows sense amplifier graph, designers can optimize the sense amplifier's performance, reducing power consumption and improving the overall reliability of the memory cell.Transister with signal **sae** and **saen** is used so that only when saen=1 the circuit works and when saen=0 when the amplifier stores the previous data. So, it is only on in case of read operation. Therefore it is a valuable for the efficient circuit operation.

### Write Driver:

Fig.11 shows the Write driver circuit in which when RD is 1 and RW is 0 then **data** is passed to **BL** and **datab** is passed to **BLB.**


<p align="center">
  Fig.11: Write Driver
</p>

![image](https://github.com/Smrity004/Project_SRAM/assets/102158117/a743c3a6-9c44-4d10-9277-c2935238a808)

### Decoder block

The 4-bit address is given as input to the SRAM. The address decoder takes the 4-bit address(A,B,C,D) and generates control signals. The number of control signals depends on the number of address lines in the SRAM
In this case, you would have 16 possible memory locations, so you'd need 4 address lines (2^4 = 16).The control signals generated by the address decoder help to select the specific memory cell in the SRAM that corresponds to the provided address. Each memory cell in the SRAM is associated with a unique binary address (e.g., 0000, 0001, 0010, etc.).

The decoder translates the 4-bit input address into the corresponding address for the memory cell that needs to be accessed. Once the correct memory cell is selected, data can be read from or written to that cell based on the memory operation (read or write) and the timing signals.


<p align="center">
  Fig.12:Decoder block
</p>

![image](https://github.com/Smrity004/Project_SRAM/assets/102158117/0ee13df4-bc78-4143-ad9a-78b83bbbf0f9)


### Sense Amplifier

<p align="center">
  Fig.13:Sense Amplifier
</p>

![image](https://github.com/Smrity004/Project_SRAM/assets/102158117/3a01ed73-df22-4cd9-a0ac-e527e40ef4da)

## Complete SRAM Schematic 

<p align="center">
  Fig.14:SRAM Schematic
</p>

![image](https://github.com/Smrity004/Project_SRAM/assets/102158117/a2907d0b-c15c-4ba2-bca8-2df955775a7b)

## TOP Testbench

Here, is the core of the SRAM which consists of 16 memory cells, each capable of storing 8 bits of data, 4 address input lines that provide the 4-bit address to select one of the 16 memory cells. This address is used by the address decoder to choose the specific cell that needs to be accessed.
 
<p align="center">
  Fig.15:Testbench
</p>

![image](https://github.com/Smrity004/Project_SRAM/assets/102158117/3d3b4684-c21b-4739-9a0b-1170c6878278)


Before any read or write operation, SRAM cells are typically precharged to a known state to ensure that they are ready for access. A control signal(ctrl) ,is used to indicate whether a read or write operation will be performed. When the Ctrl signal is set to 1, it indicates that a read or write operation is requested, and when it's set to 0, it means the circuit will be in a hold state. The address lines (typically 4 bits in your case) are used to specify the location (memory cell) from which data should be read or to which data should be written. Data lines (8 bits in your description) are used to input data for write operations and output data for read operations. After the read or write operation is executed, the output of the SRAM can be observed. If it's a read operation, the data from the addressed memory cell will appear on the data output lines. If it's a write operation, the data will be stored in the addressed memory cell.

![image](https://github.com/Smrity004/Project_SRAM/assets/102158117/0ee448e3-b9ad-4ce3-bb6e-41e55cb49eee)


## Corner Analysis

The given address
add1=15
add2=15

The given data,
data1= 0
data2= 6

The below graph show the write, delay and precharge delay which I got durning my analysis:

![image](https://github.com/Smrity004/Project_SRAM/assets/102158117/24653116-6356-41c4-8a25-500914c07aa6)

Given below are the results of the corner analysis which i have checked ie(tm, wp, ws): 

The corner analysis results provide critical insights into how a design or circuit performs under different operating conditions, allowing designers to optimize for a range of real-world scenarios and variations. These analyses help the designers to ensure that the final product functions reliably across the specified temperature ranges, manufacturing process variations, and supply voltage(vdd=1.8V) conditions.
   
    
    TM (Temperature): Represents a range of temperatures from -40°C to 85°C.

    WP (Process): Analyzes the design under varying manufacturing process conditions.

    WS (Supply Voltage): Assesses performance under different supply voltage levels.
    
![image](https://github.com/Smrity004/Project_SRAM/assets/102158117/c621db45-a755-49d1-b85b-ba83cd254500)

The below graph show the final max and mini delay of the block:

![image](https://github.com/Smrity004/Project_SRAM/assets/102158117/1ebe102f-ecfe-43d5-883d-188a0fac2fde)



## Conclusion

To conclude your SRAM project effectively, start by summarizing the key points and achievements of your project.
In our 16x8 SRAM project, the inclusion of the sense amplifier greatly improved the efficiency of read operations, ensuring accurate data detection. 

We consciously chose not to implement a column decoder due to the small size of our SRAM array, making it more practical to directly address and access the columns. 

With a frequency of operation set at 16MHz. The symphony of our efforts is best illustrated by our achievement of 367.92 micro-watts of balanced power. 
This project is not just a technical feat but a testament to our dedication to excellence.


## Bibliography

   1. Kang, Sung Mo (by Yusuf Leblebici).
   2. Google.com


























