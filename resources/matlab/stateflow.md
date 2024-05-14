# Stateflow

---

<details markdown="1">
  <summary>Table of Contents</summary>



</details>

---

## 1 Overview

These docs were written based on internal learnings and online documentation.

> See MathWorks Stateflow
> documentation: [Stateflow](https://www.mathworks.com/help/stateflow/).

## 2 Introduction to Stateflow

Stateflow is a graphical tool within MATLAB and Simulink for designing and
implementing finite state machines and control logic. It specializes in modeling
reactive systems, where the system's response to events depends on its current
state. Stateflow includes a state chart editor that aids in the construction of
state machines and flow diagrams.

**State Machines:** Stateflow facilitates the design of state machines that
visually represent the system's states and transitions. States may denote modes
of operation, while transitions indicate how the system transitions between
these states based on events or conditions.

**Hierarchical State Machines:** Stateflow supports hierarchical state machines,
enabling the inclusion of nested states. This functionality allows for the
creation of complex behaviors in a structured manner.

**Parallel States:** The tool also supports modeling concurrent states,
representing multiple operations or tasks occurring simultaneously within the
system.

**Event Handling:** Stateflow is capable of managing events that trigger
transitions between states. These events may be time-based, signal-based, or
custom-defined.

**Integration with Simulink:** Stateflow integrates smoothly with Simulink,
facilitating the integration of state machines into Simulink models and aiding
in the simulation of control logic alongside dynamic systems.

## 3 Basic Components

**States:** Depicted as rectangles, states represent various conditions or modes
of the system.

**Transitions:** Illustrated by arrows connecting states, transitions depict how
the system moves from one state to another based on defined conditions.

**Events:** Events are triggers that initiate state transitions, which can be
due to external inputs or generated internally within the Stateflow chart.

**Conditions:** These are logical expressions that need to be true for a
transition to take place.

## 4 Calling Simulink Functions

### 4.1 Single Execution Triggers

To design a trigger in a Stateflow chart that operates only once, typically
during initialization or under a unique condition, the following strategies can
be used:

#### 4.2 Using Initialization Events

Stateflow charts can perform specific actions at startup as part of the model
initialization, useful for setting initial conditions or conducting tasks only
necessary at the simulation's start.

**Entry Actions in the Initial State:** Introduce an initial state with an entry
action to call the Simulink function. This action executes solely when the
Stateflow chart first enters this state at the simulation's commencement.

```matlab
entry: output = functionName(inputs);
```

#### 4.3 Using a Conditional Transition

If a function must execute based on a specific condition but only once, a
transition with a condition to alter the state can prevent repeated execution.

**Set Up a Boolean Flag:** Include a local data variable in Stateflow, e.g.,
hasFunctionRun, initialized to false.

**Conditional Transition:** Form a transition from the initial state to another
with the condition hasFunctionRun == false && <other_condition>. In the
transition action, call the Simulink function and set hasFunctionRun = true.

```matlab
[hasFunctionRun == false && <other_condition>] {output = functionName(inputs); hasFunctionRun = true;}
```

This configuration guarantees the function is called only once because the
boolean flag, once set to true, prevents the condition for the transition from
being met again.

#### 4.4 Using Event-Based Triggers

For scenarios where an external or internal event should trigger the function
execution but only once, the boolean flag strategy can be applied.

Event Trigger with a Guard: Suppose an event, E, should activate the function. A
transition can be established on this event with a guard condition utilizing the
boolean flag.

```matlab
[E && hasFunctionRun == false] {output = functionName(inputs); hasFunctionRun = true;}
```
