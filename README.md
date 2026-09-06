# neuro-cim-tile

> Multi-Technology Compute-in-Memory (CIM) Core with D-CIM CMOS & NVM Macro Modeling (NeuroSim & TransCIM Inspired).

[![License: Apache-2.0](https://img.shields.io/badge/License-Apache_2.0-blue.svg)](./LICENSE)
[![Framework: NeuroSim & TransCIM](https://img.shields.io/badge/inspired%20by-NeuroSim%20v1.5%20%7C%20TransCIM-purple)](#)
[![Devices: SRAM | RRAM | FeFET | PCM](https://img.shields.io/badge/devices-SRAM%20%7C%20RRAM%20%7C%20FeFET%20%7C%20PCM-orange)](#)

## Overview
`neuro-cim-tile` is a device-configurable Compute-in-Memory (CIM) macro core inspired by **NeuroSim v1.5** and **TransCIM**. It couples a synthesizable digital periphery (row decoders, shift-and-add accumulators, activation/quantization units) with a pluggable synaptic crossbar supporting both standard D-CIM CMOS (SRAM) and behavioral NVM macros (RRAM, FeFET, PCM).

## Key Features
- **Pluggable Cell Technology (`DEVICE_TECH`)**:
  - `0`: Pure synthesizable D-CIM CMOS (SRAM logic).
  - `1`: Behavioral RRAM (1T1R non-linear filament conductance).
  - `2`: Behavioral FeFET (multi-level remnant polarization & threshold voltage shifts).
  - `3`: Behavioral PCM (amorphous/crystalline resistance states).
- **Shift-and-Add Accumulation**: Collects bitline partial sums across bit-serial cycles into a 16-bit result.
- **Configurable Activation**: ReLU (standard CNNs/MLPs) and Linear Pass-Through (TransCIM attention projections).
