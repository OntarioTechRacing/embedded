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

## Diodes

Shockley diode
equation: $`I_{D} = I_{S} \left( e^{\frac{V_{D}}{nV_{T}}} - 1 \right)`$.

- $`I_{D}`$ = Diode current.
- $`I_{S}`$ = Reverse bias saturation current.
- $`V_{D}`$ = Voltage across the diode.
- $`V_{T}`$ = Thermal voltage.
    - Where $`V_{T} = \frac{kT}{q}`$.
        - $`k`$ = [Boltzmann constant](https://en.wikipedia.org/wiki/Boltzmann_constant).
        - $`T`$ = Absolute temperature \[$`K`$].
        - $`q`$ = Magnitude of an electron's charge,
          aka [elementary charge](https://en.wikipedia.org/wiki/Elementary_charge)
          \[$`C`$].
- $`n`$ = [Ideality / quality factor](https://en.wikipedia.org/wiki/Ideality_factor)
  or emission coefficient.

---

## Operational Amplifier (Op Amp)

### Gain

Gain: $`A = \frac{output}{input}`$.

Voltage gain: $`A_{v} = \frac{v_{output}}{v_{input}}`$.

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

### DC Analysis

### Small Signal Analysis (AC)

#### T Model & Hybrid Pi Model

Dependant current: $`i_{D} = g_{m} v_{GS}`$.

### Amplifier Applications

Recall, the MOSFET must operate in saturation mode.

|                                | Common Source | Common Source with Source Resistor | Common Gate | Common Drain |
|--------------------------------|---------------|------------------------------------|-------------|--------------|
| Circuit                        |               |                                    |             |              |
| Model                          |               |                                    |             |              |
| Input                          |               |                                    |             |              |
| Output                         |               |                                    |             |              |
| $`R_{in}`$                     |               |                                    |             |              |
| $`R_{out}`$                    |               |                                    |             |              |
| Gain $`A_{v_{o}}`$ (open load) |               |                                    |             |              |
| Gain $`A_{v}`$ with $`R_{L}`$  |               |                                    |             |              |
| Overall gain $`G_{v}`$         |               |                                    |             |              |
| Effect of $`R_{out}`$          |               |                                    |             |              |

### Negative Feedback Amplifier

---

## Bipolar Junction Transistor (BJT)

### Operating Mode / Response Region

| Operating Mode | EB Junction | CB Junction | Characteristics                         | ~BE Voltage                    | ~BC Voltage                    | Application |
|----------------|-------------|-------------|-----------------------------------------|--------------------------------|--------------------------------|-------------|
| Cutoff         | Reverse     | Reverse     | $`V_{C} > V_{B}`$ and $`V_{E} > V_{B}`$ | $`V_{BE} < 0.5 \; \mathrm{V}`$ | $`V_{BC} < 0.4 \; \mathrm{V}`$ | Digital 0   |
| Active         | Forward     | Reverse     | $`V_{C} > V_{B} > V_{E}`$               | $`V_{BE} = 0.7 \; \mathrm{V}`$ | $`V_{BC} < 0.4 \; \mathrm{V}`$ | Amplifier   |
| Saturation     | Forward     | Forward     | $`v_{B} > V_{C}`$ and $`V_{B} > V_{E}`$ | $`V_{BE} = 0.7 \; \mathrm{V}`$ | $`V_{BC} > 0.4 \; \mathrm{V}`$ | Digital 1   |

### DC Analysis

Important aspects to remember:

1. Signal / AC sources are short.
2. Coupling / decoupling / bypass capacitors are open.

### Small Signal Analysis (AC)

Important aspects to remember:

1. DC sources are short.
2. Coupling / decoupling / bypass capacitors are short.
3. BJT operates as a small signal model.
4. Bias currents are required to find small signal model parameters.

Signal model parameters:

$`g_{m} = \frac{I_{C}}{V_{T}}`$.

#### T Model

Dependant current: $`i_{C} = \alpha i_{E}`$.

BE voltage: $`v_{BE} = i_{E} r_{e}`$.

Resistance: $`r_{e} = \frac{\alpha}{g_m} = \frac{V_{T}}{I_{E}}`$.

#### Pi Model

Dependant current: $`i_{C} = \beta i_{B}`$.

BE voltage: $`v_{BE} = i_{B} r_{\pi}`$.

Resistance: $`r_{\pi} = \frac{\beta}{g_{m}} = \frac{V_{T}}{I_{B}}`$.

### Amplifier Applications

Recall, the BJT must operate in active mode.

|                                   | Common Emitter | Common Emitter with Emitter Resistor | Common Base | Common Collector / Emitter Follower |
|-----------------------------------|----------------|--------------------------------------|-------------|-------------------------------------|
| Circuit                           |                |                                      |             |                                     |
| Model                             |                |                                      |             |                                     |
| Input                             |                |                                      |             |                                     |
| Output                            |                |                                      |             |                                     |
| $`R_{in}`$                        |                |                                      |             |                                     |
| $`R_{out}`$                       |                |                                      |             |                                     |
| Gain $`A_{v_{o}}`$ (no $`R_{L}`$) |                |                                      |             |                                     |
| Gain $`A_{v}`$ with $`R_{L}`$     |                |                                      |             |                                     |
| Overall gain $`G_{v}`$            |                |                                      |             |                                     |
| Effect of $`R_{out}`$             |                |                                      |             |                                     |

> Recommended video:
> - [Feedback Amplifier: How to find DC Bias and AC Gain](https://youtu.be/6dLMxpLNKv4)

### Negative Feedback Amplifier

|                                       | Voltage      | Trans-conductance | Current      | Trans-resistance |
|---------------------------------------|--------------|-------------------|--------------|------------------|
| Input                                 | Voltage      | Voltage           | Current      | Current          |
| Output                                | Voltage      | Current           | Current      | Voltage          |
| Topology                              | Series-Shunt | Series-Series     | Shunt-Series | Shunt-Shunt      |
| Feedback network $`R_{1}`$, $`R_{2}`$ |              |                   |              |                  |
| Feedback factor $`\beta`$             |              |                   |              |                  |
| Open loop gain $`A`$                  |              |                   |              |                  |
| Feedback loop gain $`A_{f}`$          |              |                   |              |                  |

|                                                                            | Series Equation                                                                                                             | Shunt Equation                                                                                                                             |
|----------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------|
| Feedback resistance $`R_{if}`$, $`R_{of}`$                                 | $`= \left( 1 + A \beta \right) R_{\left( i \; \mathrm{or} \; o \right)}`$                                                   | $`= \frac{R_{\left( i \; \mathrm{or} \; o \right)}}{ 1 + A \beta }`$                                                                       | 
| Input output resistance $`R_{i}`$, $`R_{o}`$  (no $`R_{L}`$ & $`R_{sig}`$) | $`R_{i \; \mathrm{or} \; o} = R_{ \left( i \; \mathrm{or} \; o \right) \; f} - R_{\left( sig \; \mathrm{or} \; L \right)}`$ | $`R_{i \; \mathrm{or} \; o}^{-1} = R_{ \left( i \; \mathrm{or} \; o \right) \; f}^{-1} - R_{\left( sig \; \mathrm{or} \; L \right)}^{-1}`$ |

> Recommended video:
> - [Series-shunt Feedback Amplifier Explained: Computing Voltage Gain & Impedances](https://youtu.be/pc221bCojms)

---
