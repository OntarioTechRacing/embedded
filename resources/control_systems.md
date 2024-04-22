# Control Systems

---

<details markdown="1">
  <summary>Table of Contents</summary>

- [1 Intro to Control Systems](#1-intro-to-control-systems)
- [2 Open Loop-and Closed Loop Control](#2-open-loop-and-closed-loop-control)
    - [2.1 Open Loop Control](#21-open-loop-control)
    - [2.2 Closed Loop Control](#22-closed-loop-control)
- [3 Feedback](#3-feedback)
    - [3.1 Positive Feedback](#31-positive-feedback)
    - [3.2 Negative Feedback](#32-negative-feedback)
- [4 Block Diagrams](#4-block-diagrams)
    - [4.1 Block Diagram Basics](#41-block-diagram-basics)
        - [4.1.1 Block](#411-block)
        - [4.1.2 Summing Point](#412-summing-point)
        - [4.1.3 Taking off Point](#413-taking-off-point)
    - [4.2 Block Diagram Algebra](#42-block-diagram-algebra)
    - [4.3 Block Diagram Reduction](#43-block-diagram-reduction)
- [5 Transfer Functions](#5-transfer-functions)
    - [5.1 Poles and Zeros of Transfer Functions](#51-poles-and-zeros-of-transfer-functions)
    - [5.2 The s-plane](#52-the-s-plane)
    - [5.3 Obtaining Transfer Function from a Block Diagram](#53-obtaining-transfer-function-from-a-block-diagram)
    - [5.4 Matlab Implementation](#54-matlab-implementation)
- [6 Time Response Analysis](#6-time-response-analysis)
    - [6.1 Transient State Response](#61-transient-state-response)
    - [6.2 Steady State Response](#62-steady-state-response)
    - [6.3 Standard Test Signal](#63-standard-test-signal)
        - [6.3.1 Unit Impulse Signal](#631-unit-impulse-signal)
        - [6.3.2 Unit Step Signal](#632-unit-step-signal)
        - [6.3.3 Unit Ramp Signal](#633-unit-ramp-signal)
- [7 Response of a First Order System](#7-response-of-a-first-order-system)
- [8 Response of a Second Order System](#8-response-of-a-second-order-system)
- [9 Time Domain Specifications of a 2nd Order System](#9-time-domain-specifications-of-a-2nd-order-system)
    - [9.1 Delay Time](#91-delay-time)
    - [9.2 Rise Time](#92-rise-time)
    - [9.3 Peak Time](#93-peak-time)
    - [9.4 Peak Overshoot](#94-peak-overshoot)
    - [9.5 Settling Time](#95-settling-time)
- [10 Steady State Error](#10-steady-state-error)
- [11 Stability](#11-stability)
    - [11.1 Types of Stability](#111-types-of-stability)
- [12 Frequency Response](#12-frequency-response)
- [13 Frequency Domain Specifications](#13-frequency-domain-specifications)
    - [13.1 Resonant Frequency](#131-resonant-frequency)
    - [13.2 Peak Resonance](#132-peak-resonance)
    - [13.3 Bandwidth](#133-bandwidth)
- [14 Control System Plots](#14-control-system-plots)
    - [14.1 Bode Plot](#141-bode-plot)
        - [14.1.1 Stability Analysis with Bode Plots](#1411-stability-analysis-with-bode-plots)
            - [14.1.1.1 Cross Over Frequency](#14111-cross-over-frequency)
            - [14.1.1.2 Gain and Phase Margin](#14112-gain-and-phase-margin)
        - [14.1.2 Matlab Implementation](#1412-matlab-implementation)
    - [14.2 Nyquist Plot](#142-nyquist-plot)
        - [14.2.1 Nyquist Stability Criterion](#1421-nyquist-stability-criterion)
        - [14.2.2 Stability Analysis with Nyquist Plots](#1422-stability-analysis-with-nyquist-plots)
            - [14.2.1.1 Cross Over Frequency](#14211-cross-over-frequency)
            - [14.2.1.2 Gain and Phase Margin](#14212-gain-and-phase-margin)
        - [14.2.3 Matlab Implementation](#1423-matlab-implementation)
- [15 State Space](#15-state-space)
    - [15.1 State Transition Matrix](#151-state-transition-matrix)
    - [15.2 Controllability and Observability](#152-controllability-and-observability)
- [16 Code Implementation](#16-code-implementations)

</details>

---

## 1 Intro to Control Systems

Control systems constitute a system, device or set of devices, that utilizes the principle of output control via input,
to command the activities of other systems or devices.  
Control systems are utilized in electronic, automation and engineering systems.

**Recommended video:**

> [Everything You Need to Know About Control Theory](https://youtu.be/lBC1nEq0_nk)

## 2 Open Loop and Closed Loop Control

### 2.1 Open Loop Control

In this control system type, the systems output is dependent on the system input, but the output has no influence on the
systems control action.
This system utilizes no feedback system.

**Recommended video:**
> [Open-Loop Control Systems | Understanding Control Systems, Part 1](https://youtu.be/FurC2unHeXI?si=deoKwaBSaMM_wqQV)

### 2.2 Closed Loop Control

This control system consists of an open loop forward path, along with one or more feedback loops. In this system the
output is utilized in a feedback loop to influence the systems
control actions,to ensure the output matches a desired input.

**Recommended video:**
> [What is a Closed Loop System? | Basics of Control System](https://youtu.be/maQyGdgvS4M?si=Mzu-kVqzEHeM_Nku)

## 3 Feedback

Feedback involves feeding a systems output or part of the output back to the systems input side to be used as part
of the systems input.

### 3.1 Positive Feedback

Here the feedback output is added to the desired input.

![Positive feedback loop](https://www.tutorialspoint.com/control_systems/images/positive_feedback.jpg)

### 3.2 Negative Feedback

Here the feedback output is subtracted from the desired input. Negative feedback is used
to reduce the error between the input and output.

![Negative feedback loop](https://www.tutorialspoint.com/control_systems/images/negative_feedback.jpg)

## 4 Block Diagrams

### 4.1 Block Diagram Basics

#### 4.1.1 Block

Blocks represent the transfer function of a component, with a single input
and output.

The diagram below shows a block with input _X(s)_, output _Y(s)_ and transfer
function _G(s)_.

![](https://www.tutorialspoint.com/control_systems/images/block.jpg)

$$G(s) = \frac{Y(s)}{X(s)}$$

The output is obtained by multiplying the transfer function and input.

#### 4.1.2 Summing Point

Represented by a circle, it receives 2 or more inputs and a single output. It is used
to perform algebraic operation (summation and/or subtraction) on inputs to produce the operations result as an output.
The operations on the inputs depend on their polarity.

The figures below shows a summing point and operations on inputs.

![](https://www.tutorialspoint.com/control_systems/images/negative_sign.jpg)

**Recommended video:**
> [Basics of Block DIagrams](https://youtu.be/6YRjc8LgXmc?si=4OKShzdOeDTaX3N4)

#### 4.1.3 Taking-off point

This is a point on a branch from which an input/output can be passed to a
summing point or one or more blocks.

![](https://www.tutorialspoint.com/control_systems/images/take_off_point.jpg)

### 4.2 Block Diagram Algebra

The multiple rules of block diagram algebra are shown below.

![](https://th.bing.com/th/id/OIP.QuF-v7Lo78EYJTWSIzjdzwAAAA?w=470&h=618&rs=1&pid=ImgDetMain)

**Recommended video:**
> [Block Diagram Algebra Rules](https://youtu.be/NUUGOgkOd1A?si=7n90fl0JNNfrVbVz)

### 4.3 Block Diagram Reduction

The video provides an example on block diagram reduction.

**Recommended video:**
> [Block Diagram Reduction Example](https://youtu.be/7a2pyG1JkHQ?si=WuTTXtrO5CoSqGgn)

## 5 Transfer Functions

A transfer function represents the ratio of the laplace transform of a systems output signal and
laplace transform of the systems input signal. Transfer functions can be obtained through reduction of a systems block
diagram.

![](https://www.tutorialspoint.com/control_systems/images/block.jpg)

$$G(s) = \frac{Y(s)}{X(s)}$$

### 5.1 Poles and Zeros of Transfer Functions

A transfer function can be represented as

$$G(s) = \frac{Y(s)}{X(s)} = K\frac{(s-z_1)(s-z_2)(s-z_n)}
{(s-p_1)(s-p_2)(s-p_n)}$$

K is the gain factor of the transfer function.

From the equation if, s = $z_1$ or s = $z_2$ or s = $z_n$, the transfer function would become zero.
Therefore, $z_1$, $z_2$ and $z_n$ are the zeros of the transfer function.

Now if, s = $p_1$ or s = $p_2$ or s = $p_n$, the transfer function would become infinite.
Therefore, $p_1$, $p_2$ and $p_n$ are the roots of the transfer function.

### 5.2 The S-Plane

The s-plane is a complex plane with a real and imaginary axis. The position on the complex
plane is defined by $re^{j\theta}$ and the angle from the positive real axis, $\theta$.
Poles are mapped on the s-plane as an _x_, while zeros are mapped as a _o_.

![](https://www.jobilize.com/ocw/mirror/col10064_1.15_complete/m34855/splane.png)

![](https://vru.vibrationresearch.com/wp-content/uploads/2021/06/zdomain-poles-zeros.png)

**Recommended video:**
> [Introduction to Transfer Functions](https://youtu.be/2Xl7--Df3g8?si=JuJpT5uI-rB9WjrR)

### 5.3 Obtaining Transfer Function from a Block Diagram

**Recommended video:**
> [Transfer Function from Block Diagram Reduction Example](https://youtu.be/7a2pyG1JkHQ?si=WuTTXtrO5CoSqGgn)

### 5.4 MATLAB Implementation

**Recommended video:**
> [Transfer function model](https://www.mathworks.com/help/control/ref/tf.html)

## 6 Time Response Analysis

The output response of a system varying with time is the time response of the system.
The time response of a system consists of a transient state and steady state. Below is
a generic time response of a system with the 2 states.

![](https://www.tutorialspoint.com/control_systems/images/time_response.jpg)

Mathematically a systems response c(t) is written as

$$c(t) = c_{tr}(t) + c_{ss}(t)$$

### 6.1 Transient State Response

This state encompasses a systems output response until it reaches a steady state. For
large values of time _t_, the transient response will be zero.

### 6.2 Steady State Response

This state refers to the steady section of a systems response where the transient
response reaches a zero value, as _t_ approaches infinity.

### 6.3 Standard Test Signal

#### 6.3.1 Unit Impulse Signal

Mathematically a unit impulse, $\delta$ is defined as

$$\delta = 0;~t\neq0$$

![](https://www.tutorialspoint.com/control_systems/images/unit_impulse.jpg)

#### 6.3.2 Unit Step Signal

Mathematically a unit step signal, _u(t)_ is defined as

$$u(t) = 1;~t\geq0$$

$$~~~~~= 0;~t<0$$

![](https://www.tutorialspoint.com/control_systems/images/unit_step.jpg)

#### 6.3.3 Unit Ramp Signal

Mathematically a unit step signal, _r(t)_ is defined as

$$r(t) = t;~t\geq0$$

$$~~~~~= 0;~t<0$$

![](https://www.tutorialspoint.com/control_systems/images/unit_ramp.jpg)

## 7 Response of A First Order System

![](https://www.tutorialspoint.com/control_systems/images/unity_negative_feedback.jpg)

From the first order system above, the transfer function is

$$\frac{C(s)}{R(s)} = \frac{G(s)}{1 + G(s)}$$

Substituting the value of _G(s)_

$${C(s)} = \frac{1}{sT + 1}{R(s)}$$

- ***_C(s)_*** is the laplace transform of output signal c(t)
- ***_R(s)_*** is the laplace transform of input signal R(t)
- ***_T_*** is the time constant

For the time response of the output, the inverse laplace transform of the transfer function is performed.

The table below shows the time domain responses to various signals. The constant values
of the responses are the steady state components, while the transient components posses exponents.

| Signal       | Response, _c(t)_                           |
|--------------|--------------------------------------------|
| Unit impulse | $$c(t) = \frac{1}{T}e^{\frac{-1}{T}}u(t)$$ |
| Unit Step    | $$c(t) = (1-e^{\frac{-1}{T}})u(t)$$        |
| Unit Ramp    | $$c(t) = (t-T-Te^{\frac{-1}{T}})u(t)$$     |


**Unit Impulse Response**

![](https://www.tutorialspoint.com/control_systems/images/unit_impulse_response.jpg)

**Unit Step Response**

![](https://www.tutorialspoint.com/control_systems/images/step_response.jpg)

**Unit Ramp Response**

![](https://www.tutorialspoint.com/control_systems/images/ramp_response.jpg)

## 8 Response of A Second Order System

![](https://www.tutorialspoint.com/control_systems/images/second_order_response.jpg)

From the second order system above, the transfer function is

$$C(s) = (\frac{w_n^2}{s^2+2\zeta w_n s+w_n^2})R(s)$$

- ***_C(s)_*** is the laplace transform of output signal c(t)
- ***_R(s)_*** is the laplace transform of input signal R(t)
- $w_n$ is the natural frequency: The oscillation frequency of a system which is disturbed and
then allowed to oscillate freely
- $\zeta$ is the damping ratio: Quantity that describes the damping level in a system

For the time response of the output, the inverse laplace transform of the transfer function is performed.

The table below shows the time domain responses to a unit step signal, under different ranges of $\zeta$.

| Damping ratio, $\zeta$ | Response, _c(t)_                                                                                                    | Response Type     |
|------------------------|---------------------------------------------------------------------------------------------------------------------|-------------------|
| $\zeta = 0$            | $$c(t) = (1-\cos{w_n t})u(t)$$                                                                                      | Undamped          |
| $\zeta = 1$            | $$c(t) = (1-e^{-w_n t}-w_n te^{-w_n t})u(t)$$                                                                       | Critically Damped |
| $0<\zeta<1$            | $$c(t) = (1- (\frac{e^{-\zeta w_n t}}{\sqrt{1-\zeta^2}})(\sin{w_d t + \theta})u(t)$$                                | Underdamped       |
| $\zeta > 1$            | $$c(t) = (1+(\frac{1}{2(\zeta+\zeta^2-1)})e^-(\zeta w_n+ w_d)t-(\frac{1}{2(\zeta-\zeta^2+1)})e^-(\zeta w_n-w_d)t)$$ | Overdamped        |

-$w_d$ is the damping frequency: This quantity is mathematically defined as

$$w_d = w_n \sqrt{1 - \zeta^2}$$

## 9 Time Domain Specifications of a 2nd Order System

Response of a 2nd order underdamped system

![](https://www.tutorialspoint.com/control_systems/images/time_domain.jpg)

### 9.1 Delay Time

Delay time $t_d$, is the required time for an underdamped system response to reach half of its final
value, from it zero instance.

### 9.2 Rise Time

This is the time $t_r$, taken for an underdamped system response to rise from 0% to 100% of its final value.
For a overdamped system response, it is the time to rise from 0% to 100% of its final value.

The quantity is defined mathematically below

$$t_r = \frac{\pi - \tan^{-1}(\frac{\sqrt{1-\zeta^2}}{\zeta})}{w_n \sqrt{1-\zeta^2}}$$

### 9.3 Peak Time

Peak time $t_p$ is the time taken for a response to reach its maximum value for the first time.

The quantity is defined mathematically below

$$t_P = \frac{\pi}{w_d}$$

### 9.4 Peak Overshoot

Overshoot $M_p$ is the deviation of the systems response from the final steady state response at peak time.

The quantity is defined mathematically below

$$M_p = (e^-(\frac{\zeta \pi}{\sqrt{1-\zeta^2}}))$$

The percentage of peak overshoot can be foud from the above equation.

### 9.5 Settling Time

This is the time $t_s$ taken for a response to reach its steady state final value and remain within
a specific tolerance range of the value.

For a 2% tolerance range, the quantity is defined mathematically below as

$$t_s = \frac{4}{\zeta w_n} = 4\tau$$

- $\tau$ is the time constant: This is the time taken for a response to reach 63.2% of its
  final steady state value from the initial state.

**Recommended video:**
> [Time Domain Specifications](https://youtu.be/MzrgBc4s-jk?si=SSw2xam1qhFWr2St)

## 10 Steady State Error

This refers to the discrepancy between a control systems output from the
desired steady state response.

![](https://dwma4bz18k1bd.cloudfront.net/tutorials/Steady-State-Error-1.jpg)

The quantity is defined mathematically below as

$$e_{ss} = \lim_{x\to\infty} e(t) = \lim_{s\to 0} sE(s)$$

- **E(s)** is the laplace transform of signal, e(t).

**Recommended video:**
> [Steady State Error](https://youtu.be/gR5nDxw5lds?si=892S8V75aUxjNRfX)

## 11 Stability

For a stable system produces a bounded output for a given bounded input.

### 11.1 Types of Stability

The classification of systems based on stability is given below.

- **Absolutely Stable System**: This system provides bounded output for all variations
  in the system. If all the poles of the open loop and closed loop transfer function is on the left half of the
  s-plane, then the open and closed loop control system is absolutely stable.

![](https://media.geeksforgeeks.org/wp-content/uploads/20240122140154/CS--Stability.webp)

- **Conditionally Stable System**: Here the system provides bounded output for only a
  range of variations in the system.

![](https://media.geeksforgeeks.org/wp-content/uploads/20240122140251/CS--Stability2.webp)

- **Marginally Stable System**: This system produces bounded output when the bounded input
  possess constant amplitude and frequency. If any 2 poles of the open loop and closed
  loop transfer function is on the imaginary of the s-plane, then the open and closed
  loop control system is marginally stable.

![](https://media.geeksforgeeks.org/wp-content/uploads/20240122173811/stability.webp)

- **Unstable Stable System**: This system provides unbounded output for all variations
  in the system. If all the poles of the open loop and closed loop transfer function is on the right half of the
  s-plane, then the open and closed loop control system is absolutely stable.

![](https://media.geeksforgeeks.org/wp-content/uploads/20240122140239/CS--Stability3.webp)

**Recommended video:**
> [Introduction to Stability](https://youtu.be/t1BrHAYhvog?si=TMgU2nFZuiZBwXw_)

## 12 Frequency Response

Frequency response is the response of a system for a given sinusoidal input.

For an input signal $r(t) = A\sin(\omega_0 t)$ and open loop transfer function $G(s) = G(j\omega)$, with
magnitude and phase $G(j\omega_0)|\angle G(j\omega_0)|$
the output signal is

$$c(t) = A|G(j\omega_0)|\sin(\omega_0 t+\angle G(j\omega_0))$$

- A is the amplitude of the input signal
- $\omega_0$ is the angular frequency of the input signal, mathematically described as

$$\omega_0 = 2\pi f_0$$

- $f_0$ is the frequency of the input signal

## 13 Frequency Domain Specifications

For the 2nd order transfer function

$$T(S) = \frac{C(s)}{R(s)} = (\frac{w_n^2}{s^2+2\zeta w_n s+
w_n^2})$$

The magnitude of _T(s)_, with $s = j\omega$,

$$M = |T(j\omega)| = \frac{1}{\sqrt{(1-(\frac{\omega}{\omega_n})^2)
^2+(2\zeta \frac{\omega}{\omega_n})^2}}$$

The phase of _T(s)_, with $s = j\omega$,

$$\angle T(j\omega) = -\tan^{-1}(\frac{\frac{2\zeta\omega}{\omega_n}}
{1 - (\frac{\omega}{\omega_n})^2})$$

### 13.1 Resonant Frequency

Resonant frequency, $\omega_r$, is the frequency when the magnitude of the frequency response
reaches its peak value for the first time.

It is mathematically defined as

$$\omega_r = \omega_n\sqrt{1-2\zeta^2}$$

### 13.2 Peak Resonance

Peak resonance, $M_r$ is the maximum magnitude of $T(j\omega$).

It is mathematically defined as

$$M_r = \frac{1}{2\zeta\sqrt{1-\zeta^2}}$$

### 13.3 Bandwidth

Bandwidth, $\omega_b$, is the frequency range over which, the magnitude of $T(j\omega$) drops to 70.7%
of its zero frequency value.

$$\omega_b = \omega_n\sqrt{1-2\zeta^2+
\sqrt{2-4\zeta^2+4\zeta^4}}$$

## 14 Control System Plots

### 14.1 Bode Plot

Bode Plots describe the change in magnitude and phase as a function of frequency.

The magnitude of an open loop transfer function in dB is

$$M = 20\log(|G(j\omega)H(j\omega)|)$$

The phase angle of an open loop transfer function in degrees is

$$\phi = \angle G(j\omega)H(j\omega)$$

**Recommended video:**
> [Introduction to Bode Plots](https://www.youtube.com/watch?reload=9&v=gZhRvrGSZdQ)

**Recommended video:**
> [Bode Plot Solved Example](https://www.youtube.com/watch?v=JLWJTdK0Q0w)

#### 14.1.1 Stability Analysis with Bode Plots

##### 14.1.1.1 Cross Over Frequency

- **Phase Cross Over Frequency**, $\omega_pc$: This is the frequency at which the bode phase plot has a phase of
  $-180^\circ$. Its unit is **rad/sec**.
- **Gain Cross Over Frequency**, $\omega_gc$: This is the frequency at which the bode magnitude
  plot has a magnitude of zero dB. Its unit is **rad/sec**.

| Stability Criteria      | Stability                |
|-------------------------|--------------------------|
| $\omega_pc > \omega_gc$ | Stable system            |
| $\omega_pc = \omega_gc$ | Marginally Stable system |
| $\omega_pc < \omega_gc$ | Unstable system          |

##### 14.1.1.2 Gain and Phase Margin

-**Gain Margin**, GM: This is the negative value of magnitude in dB at the phase cross over frequency, $M_pc$.

It is mathematically defined as

$$GM = 20\log(\frac{1}{M_pc}) = 10\log(M_pc)$$

- **Phase Margin**, PM: It is mathematically defined as

$$PM = 180^\circ + \phi_gc$$

where $\phi_gc$, is the phase angle at the gain cross over frequency.

| Stability Criteria            | Stability                |
|-------------------------------|--------------------------|
| $GM > 0$<br/> and $PM > 0$    | Stable system            |
| $GM = 0$<br/> and $PM = 0$    | Marginally Stable system |
| $GM < 0$<br/> and/or $PM < 0$ | Unstable system          |

**Recommended video:**
> [How to find cross over frequencies, Gain and Phase Margin from Bode Plot](https://www.youtube.com/watch?v=iB10Hk0BCAs)

#### 14.1.2 MATLAB Implementation

**Recommended video:**
> [Bode plot of frequency response, or magnitude and phase data](https://www.mathworks.com/help/ident/ref/dynamicsystem.bode.html)

### 14.2 Nyquist Plot

#### 14.2.1 Nyquist Stability Criterion

The criterion states that if _P_ poles and _Z_ zeros are encircled by an enclosed path in the _s_ plane,
the corresponding _G(s)H(s)_ plane must encircle the origin _P-Z_ times. The encirclement number, _N_,
is given by

$$N = P - Z$$

- If only poles exist in the encircled _s_ plane closed path, the encirclement in the _G(s)H(s)_ is
  opposite in direction to the path in the _s_ plane.
- If only zeros exist in the encircled _s_ plane closed path, the encirclement in the _G(s)H(s)_ is
  in the same direction as the path in the _s_ plane.

The **Nyquist Stability Criterion** states that _N_ of the point (-1,0) must equal _P-Z_ of the close loop
transfer function.

**Recommended video:**
> [Nyquist plot intro 1](https://www.youtube.com/watch?v=sof3meN96MA)

**Recommended video:**
> [Nyquist plot intro 2](https://www.youtube.com/watch?v=tsgOstfoNhk)

#### 14.2.2 Stability Analysis with Nyquist Plots

##### 14.2.1.1 Cross Over Frequency

- **Phase Cross Over Frequency**, $\omega_pc$: This is the frequency at which the Nyquist plot
  intersects the negative real axis (phase of $-180^\circ$). Its unit is **rad/sec**.
- **Gain Cross Over Frequency**, $\omega_gc$: This is the frequency at which the Nyquist
  plot has a magnitude of 1. Its unit is **rad/sec**.

| Stability Criteria      | Stability                |
|-------------------------|--------------------------|
| $\omega_pc > \omega_gc$ | Stable system            |
| $\omega_pc = \omega_gc$ | Marginally Stable system |
| $\omega_pc < \omega_gc$ | Unstable system          |

##### 14.2.1.2 Gain and Phase Margin

-**Gain Margin**, GM: This is the reciprocal value of magnitude at the phase cross over frequency, $M_pc$.

It is mathematically defined as

$$GM = \frac{1}{M_pc}$$

- **Phase Margin**, PM: It is mathematically defined as

$$PM = 180^\circ + \phi_{gc}$$

where $\phi_gc$, is the phase angle at the gain cross over frequency.

| Stability Criteria           | Stability                |
|------------------------------|--------------------------|
| $GM > 1$<br/> and $PM > 0$   | Stable system            |
| $GM = 1$<br/> and $PM = 0$   | Marginally Stable system |
| $GM < 1$<br/> and/or $PM < 0$ | Unstable system          |

**Recommended video:**
> [How to find cross over frequencies, Gain and Phase Margin from Nyquist Plot](https://www.youtube.com/watch?v=84o_rcCXOBw)

#### 14.2.3 MATLAB Implementation

**Recommended video:**
> [Nyquist plot of frequency response](https://www.mathworks.com/help/control/ref/dynamicsystem.nyquist.html)

## 15 State Space

- **State**: A group of variables which summarize the systems history, utilized to predict
future outputs.
- **State Variables**: They possess the dynamic information of a system.

The state space model of a linear time invariant system is represented as

State~Equation

$$\dot {X} = AX + BU$$

Output~Equation

$$Y = CX + DU$$

- _X_ and $\dot {X}$, are the state vector and differential state vector.
- Y and U, are the output and input vectors.
- A is the system matrix.
- B and C are the input and output matrices.
- D is the feed forward matrix.

Applying laplace transform to the state space model defined above, the transfer function of a system in state space
is defined as

$$\frac{Y(s)}{U(s)} = C(sI-A)^{-1}$$

- I is an identity matrix.

### 15.1 State Transition Matrix

If the matrix satisfies the following linear homogenous equation

$$\dot x(t) = \frac{dx(t)}{dt} = Ax(t)$$

The state transition matrix $\phi (t)$ is

$$\frac{d\phi (t)}{dt} = A\phi (t)$$

The condition following will be met

$$x(t) = \phi (t)x(0)$$

Taking laplace of the linear homogenous equation

$$x(t) = \phi (t)x(0) = L^{-1}[(sI - A)^{-1} x(0)]$$

- Properties of State Transition Matrix
- $\phi (t) = I$
- $\phi (t) = e^{At} = (e^{-At})^{-1} = (\phi (-t))^{-1}$
- $\phi (t_2 - t_0) = \phi (t_2 - t_1)\phi(t_1 - t_0)$
- $\phi (t - t_0) = \phi (t)\phi^{-1} (t_0)$
- $\phi (t+t_0) = \phi (t)\phi(t_0)$

### 15.2 Controllability and Observability

- **Controllability**: A system is controllable when a desired output is obtained from a specified
and controlled input. The criteria is given below, using the matrix $Q_0$.

$$Q_0 = [B AB A^2B .... A^{n-1}B]$$

If the determinant of $Q_0$, $|Q_0|$ is unequal to 0, then the system is controllable.

- **Observability**: If input and output signals are used to determine the internal state of a system
within a finite interval of time, the system is observable. The criteria is given below, using the matrix $Q_0$.

$$Q_0 = [C^T A^T C^T .... (A^T)^{n-1}C^T]$$

If the determinant of $Q_0$, $|Q_0|$ is unequal to 0, then the system is observable.

> **Recommended videos:**
> 1. [Introduction to State-Space Equations | State Space, Part 1 ](https://youtu.be/hpeKrMG-WP0)
> 2. [What is Pole Placement (Full State Feedback) | State Space, Part 2](https://youtu.be/FXSpHy8LvmY)
> 3. [A Conceptual Approach to Controllability and Observability | State Space, Part 3](https://youtu.be/BYvTEfNAi38)
> 4. [What Is Linear Quadratic Regulator (LQR) Optimal Control? | State Space, Part 4](https://youtu.be/E_RDCFOlJx4)
> 5. [State Space Models, Part 1: Creation and Analysis](https://youtu.be/wXzlhUzhqao)
> 6. [State Space Models, Part 2: Control Design](https://youtu.be/RC7_nRZKGgE)

## 16 code implementations

**Recommended video:**
> [4 Ways to Implement a Transfer Function in Code | Control Systems in Practice](https://youtu.be/nkq4WkX7CFU)
