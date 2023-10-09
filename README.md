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


### 6T-SRAM Read Operation
file:///home/nfs2/vlab17/Downloads/new.jpg![image](https://github.com/Smrity004/Project_SRAM/assets/102158117/0062879a-769d-4151-82b7-bde10c05fc71)

The above circuit show the read circuit of SRAM 


![image](https://github.com/Smrity004/Project_SRAM/assets/102158117/26a29df6-1278-4fb6-a7d9-921a637a5b30)


#Schematic of Write Operation
file:///home/nfs2/vlab17/Pictures/write.png![image](https://github.com/Smrity004/Project_SRAM/assets/102158117/859feb46-b901-41d5-9aee-8226124ca97f)


#Graphically
![image](https://github.com/Smrity004/Project_SRAM/assets/102158117/71c4403f-6d80-4ff1-8cfb-2a964c1677aa)











