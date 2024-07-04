# KiCad

---

<details markdown="1">
  <summary>Table of Contents</summary>

- [1 Official Docs & Tutorials](#1-official-docs--tutorials)
- [2 Libraries](#2-libraries)
    - [2.1 Symbols](#21-symbols)
    - [2.2 Footprints](#22-footprints)
    - [2.3 3D Models](#23-3d-models)
- [3 Recommended Beginner Tutorials](#3-recommended-beginner-tutorials)
- [4 SPICE Simulation](#4-spice-simulation)

</details>

---

## 1 Official Docs & Tutorials

All documentation refers to the currently used KiCad version 8.

KiCad official documentation can be found
at [KiCad Docs](https://docs.kicad.org/).

---

## 2 Libraries

### 2.1 Symbols

The standardized symbol libraries are managed as `.kicad_sym` files.

> See KiCad Docs:
> [Symbols and Symbol Libraries](https://docs.kicad.org/8.0/en/eeschema/eeschema_symbols_and_libraries.html)

### 2.2 Footprints

The standardized footprint libraries are managed as `.pretty` directories.

Individual footprints are saved within the directories as `.kicad_mod` files.

> See KiCad Docs:
> [Footprints and footprint libraries](https://docs.kicad.org/7.0/ru/pcbnew/pcbnew_footprints_and_libraries.html)

### 2.3 3D Models

3D models are directly linked to footprints and saved as `.3dshapes` files.

> See KiCad Docs:
> [Linking Symbols, Footprints, and 3D Models](https://docs.kicad.org/8.0/en/getting_started_in_kicad/getting_started_in_kicad.html#linking-symbols-footprints-3d-models).

---

## 3 Recommended Beginner Tutorials

Phil's Lab YouTube:

1. [KiCad 7 STM32 Bluetooth Hardware Design (1/2 Schematic) - Phil's Lab #127](https://youtu.be/nkHFoxe0mrU)
2. [KiCad 7 STM32 Bluetooth Hardware Design (2/2 PCB) - Phil's Lab #128](https://youtu.be/PlXd3lLZ4vc)

---

## 4 SPICE Simulation

KiCAD supports open source spice simulator ngspice, and is documented on the
official docs [SPICE Simulation](https://www.kicad.org/discover/spice/).
