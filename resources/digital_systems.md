# Digital Systems

This guide is meant to quickly get OTR Members trained in Digital Systems.

---

<details markdown="1">
  <summary>Table of Contents</summary>

- [1) Intro to Digital Systems](#1-intro-to-digital-systems)
  - [1.1) Digital Logic](#11-digital-logic)
  - [1.2) Truth Tables](#12-truth-tables)
  - [1.3) Field-Programmable Gate Array (FPGA)](#13-field-programmable-gate-array-fpga)
- [2) Prerequisites](#2-prerequisites)
- [3) Classification of Codes](#3-classification-of-codes)
- [4) Multiplexers](#4-multiplexers)
- [5) Demuxes](#5-demuxes)
- [6) Decoders](#6-decoders)
- [7) Finite State Machines](#7-finite-state-machines)
- [8) External Study Material](#8-external-study-material)
  - [8.1) Difference Between Flip Flops and Latches (LINK)](#81-difference-between-flip-flops-and-latches-link)
  - [8.2) How to Use K-Maps (LINK)](#82-how-to-use-k-maps-link)

</details>

---

## 1) Intro to Digital Systems

Digital Systems is the backbone of modern technology, encompassing the
principles and techniques used to design and
analyze systems that process digital information. These systems are integral to
a vast array of applications, from
simple electronic devices to complex computer networks and advanced
communication systems.

### 1.1) Digital Logic

Digital Logic is the foundation of modern digital systems, involving the
principles and techniques used to design and
analyze circuits that perform logical operations on binary data. It encompasses
the use of logic gates such as AND, OR,
NOT, NAND, NOR, XOR, and XNOR, which combine to form more complex circuits.
These circuits can perform operations like
addition, subtraction, multiplexing, and data storage. Boolean algebra underpins
digital logic, providing a mathematical
framework to simplify and optimize logical expressions. Additionally, tools like
Karnaugh maps help in minimizing logic
functions, ensuring efficient circuit design. Digital logic also includes
combinational and sequential logic, where
combinational logic produces outputs based solely on current inputs, and
sequential logic incorporates memory elements
to consider past inputs as well.

### 1.2) Truth Tables

Truth tables are essential tools in digital logic, used to represent the output
of a logic circuit for all possible
input combinations. They provide a clear and systematic way to visualize how a
logic circuit responds to different
inputs, ensuring accurate design and analysis. Each row of a truth table
corresponds to a unique combination of input
values, and the columns represent the outputs for those inputs.

To create a truth table, list all possible input combinations, typically in
binary form. For example, a truth table for
a simple AND gate with two inputs, A and B, would look like this:

| A | B | Output (A AND B) |
|:-:|:-:|:----------------:|
| 0 | 0 |        0         |
| 0 | 1 |        0         |
| 1 | 0 |        0         |
| 1 | 1 |        1         |

This table shows that the output is 1 only when both inputs are 1. Truth tables
can be used for more complex circuits by
including additional inputs and outputs, helping to identify and troubleshoot
logical errors during the design process.

### 1.3) Field-Programmable Gate Array (FPGA)

Field-Programmable Gate Arrays (FPGAs) are versatile and powerful digital
devices that can be programmed to perform a
wide variety of logical functions. Unlike fixed-function integrated circuits,
FPGAs can be reconfigured after
manufacturing, allowing designers to implement custom logic tailored to specific
applications.

An FPGA consists of an array of configurable logic blocks (CLBs), interconnects,
and input/output blocks. These
components can be programmed using hardware description languages (HDLs) like
VHDL or Verilog to perform complex
computations, signal processing, data routing, and more.

Operating an FPGA involves the following steps:

1. **Design**: Create the desired logic circuit using an HDL. This design
   includes defining how the logic gates, memory
   elements, and interconnects will work together.
2. **Simulation**: Test the design in a simulated environment to ensure it
   functions correctly and meets the required
   specifications.
3. **Synthesis**: Convert the HDL code into a configuration file that the FPGA
   can use.
4. **Programming**: Load the configuration file onto the FPGA, programming the
   CLBs and interconnects to implement the
   desired logic.

FPGAs are used in various applications, including telecommunications, automotive
systems, medical devices, and consumer
electronics. Their reprogrammable nature makes them ideal for prototyping,
custom applications, and systems that require
updates or iterative improvements without changing the hardware.

---

## 2) Prerequisites

- Knowledge of 7 basic logic gates: AND, OR, NAND, NOR, NOT, XOR, XNOR

- Knowledge of Boolean Algebra

- Knowledge on how to read Venn Diagrams

- Knowledge of Number Systems and Conversion between them

---

## 3) Classification of Codes

**Code:** When numbers or letters are represented by a specific group of
symbols, we can see that the numbers or letters
are **encoded**. The group of symbols are called "Code".

```
Codes = Group of Symbols
```

Binary Codes can described as being part of one or more of the following
families:

| Weighted Codes                                                                                    | Non-Weighted Codes                                                                                   | Reflective Codes                                                                                           | Sequential Codes                                                                                                            | Alphanumeric Codes                                                                                                  | Error Detecting & Corrector Codes                                                                                         |
|:--------------------------------------------------------------------------------------------------|:-----------------------------------------------------------------------------------------------------|:-----------------------------------------------------------------------------------------------------------|:----------------------------------------------------------------------------------------------------------------------------|:--------------------------------------------------------------------------------------------------------------------|:--------------------------------------------------------------------------------------------------------------------------|
| There is a weight associated with each digit, dependant on the number's position in the sequence. | Digit Value is independent of a number's position in the sequence. Gray Code is one example of this. | _k-th_ smallest number is the complement of the _K-th_ largest number. Look up the 5211 code or 2421 code. | For every subsequent number, the binary representation only differs by one digit. Excess-3 and 8421 are codes of this type. | The family of binary codes used to represent alphanumeric data. The primordial example would be the ASCII encoding. | The family of binary encoding is meant to detect and or correct failed data transmission. Parity Checking is one example. |

---

## 4) Multiplexers

A multiplexer is a combinational circuit that selects one of many input lines
and directs it to a single output line.
The selection of a particular input line is controlled by a set of selection
lines. Normally, there are $2^𝑛$ input
lines and 𝑛 selection lines whose bit combinations determine which input is
selected.

An example of a 4 to 1 multiplexer is provided below.

![4 to 1 Multiplexer.png](/resources/pictures/4%20to%201%20Multiplexer.png)

---

## 5) Demuxes

> Basic Multiplexer System. Permission allowed since attribution is fulfilled.
> ![Telephony_multiplexer_system.gif](/resources/pictures/Telephony_multiplexer_system.gif)
> Tony R. Kuphaldt, CC BY 1.0 <https://creativecommons.org/licenses/by/1.0>, via
> Wikimedia Commons

Demuxes perform the inverse operation of multiplexers: they direct a single
input line to many output lines. The
selection of a particular output line is controlled by a set of selection lines.
Normally, there are $2^𝑛$ output lines
and 𝑛 selection lines whose bit combinations determine which output is selected.

---

## 6) Decoders

Decoders can be imagined like a demux, where only select lines are present.
Confusingly, these select lines are called
input lines, so keep that in mind. When a partigular output gate is selected, a
high signal (1) is continously
transmitted along said line.

Even more confusing, is that sometimes decoders have an enable input, which
causes them to behave identically to a
demux.

The only real difference lies in how the gates are named.

---

## 7) Finite State Machines

A finite state machine is the next level up in digital design. State Machines
Circuits will produce different outputs
not just from the different combinations of their circuits, but also based on
the output they were sending before, or
just their outputs alone, with no input change at all!

Finite State Machines can be grouped into two types: Mealy or Moore. A block
diagram of each is presented below.

![Mealy vs Moore Machines.png](/resources/pictures/Mealy%20vs%20Moore%20Machines.png)

As you can see above, only in Moore Machines do the inputs asynchronously affect
the output of the machine.

---

## 8) External Study Material

### 8.1) Difference Between Flip Flops and Latches (LINK)

[Difference between Latch and Flip Flop (youtube.com)](https://www.youtube.com/watch?v=m1QBxTeVaNs&list=PLBlnK6fEyqRjMH3mWf6kwqiTbT798eAOm&index=148)

**SUMMARY:** Latches can be turned into a flip-flop, if you add an input that
causes the latch to only listen to its inputs when the additional input is also
active.

### 8.2) How to Use K-Maps (LINK)

[Lecture 6 - Karnaugh Maps And Implicants (youtube.com)](https://www.youtube.com/watch?v=EznCqZ1eh5Q&list=PL803563859BF7ED8C&index=6)

**SUMMARY:** Karnaugh maps and Boolean algebra are the same theory, they are
just different procedures.
The advantages of Karnaugh maps is that it makes you confident you got the best
formula.

---
