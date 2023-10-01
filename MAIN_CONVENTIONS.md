# Ontario Tech Racing: Embedded Software - Main Conventions

---

# Versioning

All versioning follows the [Semantic Versioning 2.0.0 (SemVer)](https://semver.org/) standard.

## `MAJOR.MINOR.PATCH` in the Context of OTR FSAE

### MAJOR

- Incompatible with the previous project scope and/or hardware
- **Changing MCU IC hardware**
- **PCB and/or Embedded Hardware changes required**

### MINOR

- Maintaining same project scope and functionality in a backward-compatible manner
- Allows for hardware changes provided **no PCB and/or Embedded Hardware changes required**

### PATCH

- Completely backwards compatible in both software and exact hardware

## Prerelease (`-alpha`, `-beta`, etc) 

Prerelease denotes general scope validation projects.

For example, suppose you are constructing a reflow oven for the team. To test the feasibility of
creating a professional-level, DIY reflow oven, you try to replicate one from an open-source
project as a point of reference and feasibility assessment. The open-source project might utilize
deprecated parts and premade PID controllers that require improvements. This endeavor is considered
a prerelease, specifically a feasibility testing prerelease project. By completing this project you
can further confirm, deny or adjust the actual project scope.

## Main release

Main release denotes major projects developed by our department, this includes everything from
prototypes.

---
