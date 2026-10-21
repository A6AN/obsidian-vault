---
tags: [computer-architecture, machine-learning, programming]
---

2026-08-06 16:26

Status: #Teen 

Tags: [[Computer Architecture]] [[Processor]] [[CPU]]

# Computer Architecture Intro

#### Components of Computer Architecture
1. CPU :- Consists of ALU, CU and Registers
2. Memory :- Volatile and Non-Volatile Memory

##### Memory
Ram and Rom
Rom consists of OS it has different types :-
1. PROM :- Programmable Rom eg. Music CDs (Cannot change once programmed)
2. EPROM :-  Erasable Programmable Rom 
3. EEPROM :- Electronically Erasable ROM
4. UVEPROM :- Ultraviolet Erasable ROM

##### Input Output Unit

*Insert here*

##### Auxiliary Storage:
Serves as backup storages like SSD, Hard Drive etc.

#### Instructions Cycle
1. Fetch: Fetching of Instructions from Instruction Registers. Sends AC contents to MAR, perform memory read operation and get the instruction
2. Decode: Conversion of Instructions to Binary. Analyze the opcode
3. Fetch/ Operands: Fetching of operands required for instruction execution. Determine operand addresses and Fetch the operands, one by one from memory or from register and supply operands to ALU
4. Execute: Execution of Instruction cycle. Do the required logical operation and store result in memory or register.
![[Pasted image 20260807121735.png]]

#### System Bus Types
1. Data Bus: use when any unit is sending data, instructions or command code to some other units
2. Address Bus: used when one unit is sending an address.
3. Control Bus: responsible for making CPU, memory and I/O devices work together as a functional system, carrying signals.

#### Levels of Cache
1. L1 fastest cache and is usually fixed within the processor chip itself. ranges from 8KB to 64KB and uses the high speed SRAM
2. L2 comes between L1 and L3/Ram in terms of space and size
3. L3 shared between all CPU cores slower than L2 bigger than L2
4. L4 optional 
5. Ram

*Microprocessor programming look into it*
# References
