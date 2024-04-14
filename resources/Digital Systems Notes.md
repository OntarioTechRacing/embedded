# Digital Systems Notes

This guide is meant to quickly get OTR Members trained in Digital Systems.

## Prerequisites

- Knowledge of 7 basic logic gates: AND, OR, NAND, NOR, NOT, XOR, XNOR

- Knowledge of Boolean Algebra

- Knowledge on how to read Venn Diagrams

- Knowledge of Number Systems and Conversion between them

## Classification of Codes

**Code:** When numbers or letters are represesented by a specific group of symbols, we can see that the numbers or letters are **encoded**. The group of symbols are called "Code". 

```
Codes = Group of Symbols
```

Binary Codes can described as being part of one or more of the following families:

| Weigthed Codes                                                                                    | Non-Weighted Codes                                                                                   | Reflective Codes                                                                                            | Sequential Codes                                                                                                             | Alphanumeric Codes                                                                                                  | Error Detecting  & Corrector Codes                                                                                         |
| ------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------- |
| There is a weight associated with each digit, dependant on the number's position in the sequence. | Digit Value is independent of a number's position in the sequence. Gray Code is one example of this. | _k-th_ smallest number is the complement of  the _K-th_ largest number. Look up the 5211 code or 2421 code. | For every  subsequent number, the binary representation only differs by one digit. Excess-3 and 8421 are codes of this type. | The family of binary codes used to represent alphanumeric data. The primordial example would be the ASCII encoding. | The family of binary encoding is meant to detect and or correct failed data transmission.  Parity Checking is one example. |

## Multiplexer

A multiplexer is a combinational circuit that selects one of many input lines and directs it to a single output line. The selection of a particular input line is controlled by a set of selection lines. Normally, there are $2^𝑛$ input lines and 𝑛 selection lines whose bit combinations determine which input is selected.

An example of a 4 to 1 multiplexer is provided below.

![4 to 1 Multiplexer.png](C:\Users\Julian\embedded\resources\pictures\4%20to%201%20Multiplexer.png)

## Demuxes

![Telephony_multiplexer_system.gif](C:\Users\Julian\embedded\resources\pictures\Telephony_multiplexer_system.gif)

Demuxes perform the inverse operation of multiplexers: they direct a single input line to many output lines. The selection of a particular output line is controlled by a set of selection lines. Normally, there are $2^𝑛$ output lines and 𝑛 selection lines whose bit combinations determine which output is selected.

## Decoders

Decoders can be imagined like a demux, where only select lines are present. Confusingly, these select lines are called input lines, so keep that in mind. When a partigular output gate is selected, a high signal (1) is continously transmitted along said line.

Even more confusing, is that sometimes decoders have an enable input, which causes them to behave identically to a demux.

The only real difference lies in how the gates are named.

## Finite State Machines

 finite state machine is the next level up in digital design. State Machines Circuits will produce different outputs not just from the different combinations of their circuits, but also based on the output they were sending before, or just their outputs alone, with no input change at all!

 Finite State Machines can be grouped into two types: Mealy or Moore. A block diagram of each is presented below.

![Mealy vs Moore Machines.png](C:\Users\Julian\embedded\resources\pictures\Mealy%20vs%20Moore%20Machines.png)

As you can see above, only in Moore Machines do the inputs asynchronously affect the output of the machine. 

## External Study Material

### Difference Between Flip Flops and Latches (LINK)

[Difference between Latch and Flip Flop (youtube.com)](https://www.youtube.com/watch?v=m1QBxTeVaNs&list=PLBlnK6fEyqRjMH3mWf6kwqiTbT798eAOm&index=148)

**SUMMARY:** Latches can be turned into a flip flop, if you add an additional input that causes the latch to only listen to its inputs when the additional input is also active.

### How to Use K-Maps (LINK)

[Lecture 6 - Karnaugh Maps And Implicants (youtube.com)](https://www.youtube.com/watch?v=EznCqZ1eh5Q&list=PL803563859BF7ED8C&index=6)

**SUMMARY:** Karnaugh maps and Boolean algebra are the same theory, they are just different procedures.
The advantages of Karnaugh maps is that it makes you confident you got the best formula.
