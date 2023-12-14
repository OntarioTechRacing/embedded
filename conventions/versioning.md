# Ontario Tech Racing: Embedded Software - Versioning Conventions

Versioning in software development is the practice of assigning unique version numbers to distinct
states of computer software, providing a clear historical record of code changes and development
progress. It is essential for tracking modifications, facilitating collaboration among multiple
developers, and ensuring that users can access stable and well-documented software releases.

---

## Version Nomenclature

- **Active**: This indicates that the version is currently being maintained. It receives updates,
  bug fixes, and possibly new features. It's safe to use in production environments.
- **Deprecated**: This means the version is still functional but is no longer recommended for use.
  It may no longer receive updates or support, and users are encouraged to transition to newer
  versions.
- **Obsolete**: This term implies that the version is out of date and no longer useful. It's often
  no longer supported or maintained, and using it could pose security or compatibility risks.
- **Discontinued**: This indicates that the version is no longer being developed or supported at
  all. It's essentially an end-of-life status for that particular version.
- **Stable**: This term is often used to describe a version that has been thoroughly tested and is
  considered reliable for production use.
- **Beta**: This is a pre-release version that is made available for testing purposes. It's not yet
  considered stable and may have bugs or unfinished features.
- **Alpha**: Even earlier than beta, this is a very preliminary version, often with incomplete
  features and numerous bugs. It's typically used for internal testing and not recommended for
  general use.
- **Release** Candidate (RC): This is a version that is potentially the final product, pending final
  tests. It's more stable than beta versions but might still have some minor issues.
- **Snapshot**: This is a version that is automatically compiled from the latest source code. It
  represents the most current development status but can be very unstable.
- **Legacy**: This often refers to older versions that are still in use but are no longer actively
  developed or supported. They may still receive critical security updates in some cases.
- **Long-term Support (LTS)**: This designation is often given to versions that will receive
  extended support and updates, usually for several years, even as newer versions are released.
- **End of Life (EOL)**: This indicates that the version will no longer receive any updates or
  support, including security patches. It's a clear signal to users that they should upgrade to a
  newer version.

---

## Semantic Versioning `MAJOR.MINOR.PATCH`

All versioning follows the [Semantic Versioning 2.0.0 (SemVer)](https://semver.org/) standard.

### MAJOR

- Incompatible with the previous project scope and/or hardware
- **Changing MCU IC hardware**
- **PCB and/or Embedded Hardware changes required**

### MINOR

- Maintaining same project scope and functionality in a backward-compatible manner
- Allows for hardware changes provided **no PCB and/or Embedded Hardware changes required**

### PATCH

- Completely backwards compatible in both software and exact hardware

### Prerelease (`-alpha`, `-beta`, etc)

Prerelease denotes general scope validation projects.

For example, suppose you are constructing a reflow oven for the team. To test the feasibility of
creating a professional-level, DIY reflow oven, you try to replicate one from an open-source
project as a point of reference and feasibility assessment. The open-source project might utilize
deprecated parts and premade PID controllers that require improvements. This endeavor is considered
a prerelease, specifically a feasibility testing prerelease project. By completing this project you
can further confirm, deny or adjust the actual project scope.

### Main release

Main release denotes major projects developed by our department, this includes everything from
prototypes.

---
