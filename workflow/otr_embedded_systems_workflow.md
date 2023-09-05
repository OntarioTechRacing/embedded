# HE + ES Workflow for FSAE Embedded Systems

- By: Mitali G. (HE) + Daniel J. (ES)

![OTR HE and ES Workflow.drawio-Dark.png](pictures/OTR%20HE%20and%20ES%20Workflow.drawio-Dark.png?raw=true "OTR HE and ES Workflow.drawio-Dark.png")

- Diagram made with [https://app.diagrams.net/](https://app.diagrams.net/)

## Hardware Spec Requirements

- Generally speaking, all hardware should be able to tolerate an operating temperatures of `-40°C ~
  60°C`, the most ideal would be `-40°C ~ 85°C`
- No [ball grid array (BGA)](https://en.wikipedia.org/wiki/Ball_grid_array) packages
- All components must have a minimum pitch of `0.65 mm`
- Consider other forms of interference as well (EMI, vibrations, noise, etc)

## Pre-specced Components

1. CAN FD
   Transceiver: [MCP2542FDT-E/SN](https://www.digikey.ca/en/products/detail/microchip-technology/MCP2542FDT-E-SN/5975416)
