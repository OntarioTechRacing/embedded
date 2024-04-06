# Coding Practices

---

<details markdown="1">
  <summary>Table of Contents</summary>

- [1 Introduction to Coding Practices](#1-introduction-to-coding-practices)
- [2 Practices for Embedded System Software for High-Reliability Needs](#2-practices-for-embedded-system-software-for-high-reliability-needs)
- [3 MISRA C](#3-misra-c)
- [4 NASA's Rule of 10](#4-nasas-rule-of-10)

</details>

---

## 1 Introduction to Coding Practices

Unlike other internal conventions, this coding practices documentation involve
theory and general knowledge, less of a rule set. While this could be seen as a
internal resource documentation item, due to the nature of its importance and
fundamental importance to shaping all other coding standards it is considered
an internal convention documentation item.

---

## 2 Practices for Embedded System Software for High-Reliability Needs

Resource Management: Due to the constrained resources (memory, processing power)
in embedded systems, efficient management is crucial. This includes careful
allocation, use, and deallocation of memory, as well as optimization of CPU
usage.

Error Handling and Recovery: Systems must be designed to handle errors
gracefully, often through the use of watchdog timers and safe states to recover
from failures.

Deterministic Behavior: Ensuring the system behaves predictably under all
conditions is vital, especially for real-time operations. This involves avoiding
features that can introduce non-determinism, such as dynamic memory allocation
and recursion.

Code Portability and Reusability: Writing modular, portable code not only
enhances maintainability but also facilitates reuse across projects, reducing
development time and costs.

Use of Coding Standards: Adopting coding standards is pivotal for improving code
quality, readability, and maintainability. Two prominent standards in
high-reliability fields are MISRA C and NASA's Rule of 10.

---

## 3 MISRA C

[MISRA C](https://en.wikipedia.org/wiki/MISRA_C) is a set of programming
guidelines developed for the C language to facilitate the safety, security,
portability, and reliability of software for embedded systems. Originally used
for the automotive industry, the principles are widely applicable across other
high-reliability sectors. MISRA C covers rules and recommendations across
various aspects of C programming, including language usage, error handling, and
code structure, to prevent errors and undefined behaviors that could compromise
system safety.

---

## 4 NASA's Rule of 10

"[The Power of 10: Rules for Developing Safety-Critical Code](https://en.wikipedia.org/wiki/The_Power_of_10:_Rules_for_Developing_Safety-Critical_Code)"
was created by Gerard J. Holzmann of the NASA / JPL Laboratory for Reliable
Software in 2006.

The "Rule of 10" is an approach to software development designed to minimize
risks in mission-critical applications.

It emphasizes:

- Rigorous code inspections to detect and correct errors early, specifically the
  use
  of [static code analysers](https://www.jetbrains.com/help/clion/code-inspection.html).
- Unit testing with comprehensive coverage to validate individual software
  components.
- Integration testing to ensure components work together correctly.
- Limitation of code complexity to enhance readability and maintainability.

The 10 rules (simplified) are as follows:

1. All code must follow very simple control flow constructs. Do not use goto
   statements, setjmp, longjmp
   or [recursion](https://en.wikipedia.org/wiki/Recursion_(computer_science)).
2. All loops must have fixed upper bounds to prevent runaway. It a static
   analyser must be able to prove the loop will not exceed the preset upper
   bound.
3. Do not
   use [dynamic / heap memory allocation](https://en.wikipedia.org/wiki/Memory_management#DYNAMIC)
   after initialization.
4. No function should be longer than a single sheet of paper (~60 lines of code)
   with standard styling.
5. Code assertions should average at least
   two [assertions](https://en.wikipedia.org/wiki/Assertion_(software_development)#Assertions_for_run-time_checking)
   per function. Assertions must check for conditions that should never happen
   in real-life. Assertions must be a Boolean test. Upon assertion fail, a
   recovery action is required such as returning an error condition to the
   original function caller. All assertions must not be provable by static
   analysers.
6. Declare all data at the smallest possible scope level.
7. Check all non-void function returns, each called function must validate all
   parameters provided.
8. The [preprocessor](https://en.wikipedia.org/wiki/Preprocessor) must be
   restricted in use, it should only be used for the inclusion of header files
   and simple macro definitions.
9. Pointer use must be restricted, never exceed one level of pointer
   [dereference](https://en.wikipedia.org/wiki/Dereference_operator), and do not
   use [function pointers](https://en.wikipedia.org/wiki/Function_pointer).
10. Compile and account for all possible warnings; all warnings must be
    addressed before any software release.

---
