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

## Intro to Stateflow

## Calling Simulink Functions

### Single Execution Triggers

To design a trigger in a Stateflow chart that only occurs once, typically during
initialization or based on a unique condition, you can follow these strategies:

#### Using Initialization Events

Stateflow charts can execute specific actions when they start as part of the
model initialization. This is useful for setting up initial conditions or
performing tasks that only need to happen once at the beginning of a simulation.

**Entry Actions in the Initial State:** Create an initial state in your
Stateflow chart. Inside this state, use the entry: action to call the Simulink
function. This action will execute only once when the Stateflow chart enters
this state for the first time, which is at the beginning of the simulation.

```matlab
entry: output = functionName(inputs);
```

#### Using a Conditional Transition

If the function needs to be executed based on a specific condition but only
once, you can use a transition with a condition that changes state to ensure it
does not happen again.

**Set Up a Boolean Flag:** Add a local data variable in Stateflow, e.g.,
hasFunctionRun, initialized to false.

**Conditional Transition:** Create a transition from the initial state to
another state with the condition hasFunctionRun == false && <other_condition>,
where <other_condition> is your specific trigger condition. In the transition
action, call the Simulink function and set hasFunctionRun = true.

```matlab
[hasFunctionRun == false && <other_condition>] {output = functionName(inputs); hasFunctionRun = true;}
```

This ensures the function is called only once because after the first call,
hasFunctionRun becomes true, and the condition for the transition will no longer
be true.

#### Using Event-Based Triggers

If there's an external or internal event that should trigger the function but
only once, you can still use the boolean flag approach to guard the function
call.

**Event Trigger with a Guard:** Suppose an event E should trigger the function.
You can create a transition on this event with a guard condition using the
boolean flag.

```matlab
[E && hasFunctionRun == false] {output = functionName(inputs); hasFunctionRun = true;}
```
