# Strain Gauges

---

<details markdown="1">
  <summary>Table of Contents</summary>

- [1 Intro to Strain Gauges](#1-intro-to-strain-gauges)
- [2 Important Characteristics](#2-important-characteristics)
- [3 Mechanical and Electrical Considerations](#3-mechanical-and-electrical-considerations)
    - [3.1 Bridge Configurations](#31-bridge-configurations)
        - [3.1.2 Quarter-Bridge Configuration](#312-quarter-bridge-configuration)
        - [3.1.3 Half-Bridge Configuration](#313-half-bridge-configuration)
        - [3.1.4 Full-Bridge Configuration](#314-full-bridge-configuration)
- [4 Software / Embedded Systems Considerations](#4-software--embedded-systems-considerations)
- [5 Calculating Strain / Stress via ADC](#5-calculating-strain--stress-via-adc)
    - [5.1 Calculation of Strain](#51-calculation-of-strain)
    - [5.2 Calculating Stress (Hooke's Law)](#52-calculating-stress-hookes-law)
- [6 Mechanical Integration](#6-mechanical-integration)
- [6.1 Installation (Surface Preparation)](#61-installation-surface-preparation)

</details>

---

## 1 Intro to Strain Gauges

A strain gauge is a sensor whose resistance varies with applied force; it
essentially measures strain on an object. When an object deforms, the strain
gauge deforms with it, causing its electrical resistance to change. This change
in resistance is proportional to the strain experienced.

Strain gauges are used in various applications to measure forces, loads, or
stresses impacting different materials or structures.

---

## 2 Important Characteristics

**Grid Resistance:** This refers to the electrical resistance of the metallic
grid in the strain gauge, typically measured in ohms. It influences how much the
signal can be amplified without noise interference.

**Gauge Factor:** The ratio of relative change in electrical resistance to the
mechanical strain. The gauge factor is critical for calibrating the strain gauge
and interpreting its output.

**Transverse Sensitivity:** This measures the sensitivity of the strain gauge to
strain perpendicular to the direction of the main strain. It’s important for
applications where multi-directional strain occurs.

**Thermal Output Coefficients:** These are coefficients that describe how the
gauge's output changes with temperature. Different materials have different
coefficients, affecting the accuracy in varying thermal conditions.

**Stability and Drift:** Over time and under varying environmental conditions,
the properties of a strain gauge can drift, affecting accuracy. Stability is
crucial for long-term measurements.

**Hysteresis:** The degree to which the strain gauge output is affected by
previous load cycles. Lower hysteresis is preferable for repeatable and reliable
measurements.

**Fatigue Life:** Refers to how well a strain gauge can withstand repeated
loading and unloading cycles without failure. Important in dynamic applications
where the material undergoes frequent or cyclical stress.

> Recommended calculator:
> [Micro-Measurements Calculators](https://www.micro-measurements.com/calculators#/)

---

## 3 Mechanical and Electrical Considerations

**Surface Preparation:** The surface where the gauge will be attached must be
clean, smooth, and free of any grease or dirt.

**Attaching the Gauge:** Adhesive is used to stick the gauge onto the surface.
Care must be taken to avoid any air bubbles or wrinkles.

**Wiring and Calibration:** Connect the gauge to a measuring instrument. The
gauge must be calibrated to ensure accurate measurements, adjusting for factors
like temperature and material properties.

**Measurement:** Strain readings are taken as the material undergoes stress,
with the changes in resistance measured through an electrical circuit.

**Voltage Regulation:** Consistent voltage levels must be maintained to ensure
that the strain gauge's output remains accurate and stable. Using voltage
regulators can prevent fluctuations that might come from battery depletion or
other power supply issues.

### 3.1 Bridge Configurations

Strain gauges are often used in bridge configurations to maximize sensitivity
and compensate for external factors like temperature changes. The most common
configurations are as follows.

#### 3.1.2 Quarter-Bridge Configuration

Uses one active strain gauge, best for simple, cost-effective measurements where
moderate accuracy is acceptable. Good for general applications where the strain
is uniform.

#### 3.1.3 Half-Bridge Configuration

Utilizes two gauges; one active gauge measuring strain and another placed
perpendicular or at a neutral point to compensate for temperature.

Suitable for bending measurements where temperature compensation is needed
without using a full bridge.

#### 3.1.4 Full-Bridge Configuration

Consists of four strain gauges in a Wheatstone bridge arrangement. This
configuration provides the highest sensitivity and accuracy. It's ideal for
precise measurements and can effectively compensate for temperature and other
external influences.

Best for complex applications requiring high accuracy, such aerospace component
testing where all factors including temperature and multidimensional
strains are critical.

> Recommended calculator:
> [Micro-Measurements Calculators](https://www.micro-measurements.com/calculators#/)

---

## 4 Software / Embedded Systems Considerations

**Signal Conditioning:** The resistance change due to strain is typically small,
so signal conditioning, like amplification and filtering, is necessary before
digitization. Amplification increases the voltage change for better resolution
and sensitivity in the ADC phase.

**Analog to Digital Conversion (ADC):** The conditioned analog voltage signal is
converted into a digital signal by the ADC. The quality and resolution of an ADC
affect how finely the changes can be detected and quantified.

**Microcontroller Selection:** Choose a microcontroller (MCU) that can handle
the necessary computation and has sufficient analog inputs if direct connection
is required. The MCU should have a high-resolution ADC or support an external
ADC for accurate data collection.

**Data Acquisition Speed:** Ensure that the ADC and microcontroller can handle
the sampling rate required for your application. High-speed changes require
faster data acquisition to capture transient events accurately.

**Noise Reduction:** Implementing hardware and software filtering techniques to
minimize noise is crucial. This includes using low-pass filters to eliminate
high-frequency noise and designing proper shielding and grounding in the circuit
layout.

---

## 5 Calculating Strain / Stress via ADC

To calculate strain or stress from the ADC signal output of a strain gauge,
follow these steps:

### 5.1 Calculation of Strain

Determine Change in Resistance: First, calculate the change in resistance from
the digital output, considering the initial resistance and the characteristics
of the amplification. Use the gauge factor (GF) to convert the relative change
in resistance (ΔR/R) to strain (ε):

$\epsilon = \frac{\Delta R}{R} \times GF$

- $\epsilon$ = strain.
- $GF$ = Gauge factor.
- $\frac{\Delta R}{R}$ = Relative change in resistance.
    - $\Delta R$ = Change in resistance.
    - $R$ = Original resistance.

### 5.2 Calculating Stress (Hooke's Law)

If the modulus of elasticity (E) of the material is known, stress (σ) can be
calculated using Hooke's Law:

$\sigma = E \times \epsilon$

- Note recall Hooke's law assumes the material behaves elastically with no
  plastic deformation.

## 6 Mechanical Integration

### 6.1 Installation (Surface Preparation)

> Recommended Video:
> [Tutorial: Strain Gage Installation Procedure](https://youtu.be/tTax9pEO8CQ)
