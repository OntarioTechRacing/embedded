# Circuits and Electronics

---

<details markdown="1">
  <summary>Table of Contents</summary>

-

</details>

---

## Introduction

Recommended resources:

Online public
textbooks: [All About Circuits](https://www.allaboutcircuits.com/textbook/)

(Paid)
Textbook: [Sedra Smith Microelectronic Circuits](https://learninglink.oup.com/search/Sedra%20Smith%20Microelectronic%20Circuits?discipline=Engineering)

---

## Intro to Circuits and Electronics

---

## Ohms Law

---

## KVL KCL

---

## Voltage Divider

---

## Node and Mesh Analysis

---

## Thevenin and Norton

Conversions:

- $`R_{Th} = R_{N}`$.
- $`V_{Th} = I_{N} \times R_{N}`$.
- $`I_{N} = \frac{V_{Th}}{R_{Th}}`$.

### Thevenin

Voltage source series to resistor.

### Norton

Current source parallel to resistor.

---

## Source transform

---

## Superposition

---

## Operational Amplifier (Op Amp)

---

## Metal Oxide Field Effect Transistor (MOSFET)

For an ideal MOSFET, the gate current is essentially zero. The gate is insulated
from the channel by a thin layer of oxide, and no direct current flows through
the gate. This insulation makes the MOSFET a voltage-controlled device.

Therefore, the current relationship in an NMOS under normal operation, assuming
no substrate (body) current, is $`I_{D} = I_{S}`$, since $`I_{G} = 0`$.

### Operating Mode / Response Region

Also known as Insulated-Gate Field-Effect Transistor (IGFET).

| Operating Mode | Characteristics                                 | Application |
|----------------|-------------------------------------------------|-------------|
| Cutoff         | $`v_{GS} < V_{t}`$                              | Digital 0   |
| Triode         | $`v_{GD} > V_{t}`$ or $`v_{OV} > V_{DS}`$       | Digital 1   |
| Saturation     | $`v_{GD} \leq V_{t}`$ or $`v_{OV} \leq V_{DS}`$ | Amplifier   |

- $`V_{t}`$ = Threshold voltage.
- $`V_{OV}`$ = Over voltage, $`V_{OV} = v_{GS} - V_{t}`$.

### I-V Relationship

| Operating Mode | I-V relationship                                                                                            |
|----------------|-------------------------------------------------------------------------------------------------------------|
| Cutoff         | $`i_{D} = 0`$                                                                                               |
| Triode         | $`i_{D} = k_{n}' \frac{W}{L} \left( \left( v_{GS} - V_{t} \right) v_{DS} - \frac{1}{2} v^{2}_{DS} \right)`$ |
| Saturation     | $`i_{D} = \frac{1}{2} k_{n}' \frac{W}{L} \left( v_{GS} - V_{t} \right)^{2}`$                                |

- Where $`k_{n}' = \mu_{n} C_{ox}`$ and $`k_{n} = k_{n}' \frac{W}{L}`$.
- $`\mu_{n}`$ = Electronic mobility of N-type [$`Cm^2 / Vs`$].
- $`C_{ox}`$ = Oxide capacitance [$`fF / \mu m^{2}`$].
- $`W`$ = Channel width.
- $`L`$ = Channel length.

### Signal Model

---

## Bipolar Junction Transistor (BJT)

### Operating Mode / Response Region

| Operating Mode | EB Junction | CB Junction | Characteristics                         | ~BE Voltage                    | ~BC Voltage                    | Application |
|----------------|-------------|-------------|-----------------------------------------|--------------------------------|--------------------------------|-------------|
| Cutoff         | Reverse     | Reverse     | $`V_{C} > V_{B}`$ and $`V_{E} > V_{B}`$ | $`V_{BE} < 0.5 \; \mathrm{V}`$ | $`V_{BC} < 0.4 \; \mathrm{V}`$ | Digital 0   |
| Active         | Forward     | Reverse     | $`V_{C} > V_{B} > V_{E}`$               | $`V_{BE} = 0.7 \; \mathrm{V}`$ | $`V_{BC} < 0.4 \; \mathrm{V}`$ | Amplifier   |
| Saturation     | Forward     | Forward     | $`v_{B} > V_{C}`$ and $`V_{B} > V_{E}`$ | $`V_{BE} = 0.7 \; \mathrm{V}`$ | $`V_{BC} > 0.4 \; \mathrm{V}`$ | Digital 1   |

---
