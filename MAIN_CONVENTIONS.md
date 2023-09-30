# Ontario Tech Racing: Embedded Software - Main Conventions

## Versioning

All versioning follows the [Semantic Versioning 2.0.0 (SemVer)](https://semver.org/) standard.

### Major, Minor and Patches

**MAJOR** version is when you make changes that are incompatible with the current project scope
and/or hardware.
**MINOR** version is when you add functionality in a backward-compatible manner.
**PATCH** version is when you make backward-compatible bug fixes.

### Prerelease

Prerelease (`-alpha`, `-beta`, etc.) denotes general scope validation projects.

For example, suppose you are constructing a reflow oven for the team. To test the feasibility of
creating a professional-level, DIY reflow oven, you try to replicate one from an open-source
project as a point of reference and feasibility assessment. The open-source project might utilize
deprecated parts and premade PID controllers that require improvements. This endeavor is considered
a prerelease, specifically a feasibility testing prerelease project. By completing this project you
can further confirm, deny or adjust the actual project scope.

### Main release

Main release denotes major projects developed by our department, this includes everything from
prototypes.
