# neuro-cim-tile

<!-- BEGIN GENERATED PROJECT GUIDE -->

## Purpose and first steps

Specify a proposed compute-in-memory tile and its digital/device-model boundaries.

**Who it is for:** Researchers planning the boundaries between digital accumulation and CIM device models.

**First task:** Trace the proposed row-driver, crossbar, accumulator, and activation interfaces.

**What to expect:** A hierarchy/interface proposal for a future tile model and digital implementation.

**Current scope:** Architecture draft only. RTL, behavioral device models, calibration data, and verification are future work.

**Start here:** [Tile hierarchy proposal](ARCHITECTURE.md).

**Related projects:** [cim-bit-serial-pe](https://github.com/zesun33/cim-bit-serial-pe), [lif-spiking-core](https://github.com/zesun33/lif-spiking-core).

[Choose another project](https://github.com/zesun33/personal-projects/blob/main/GETTING_STARTED.md).
<!-- END GENERATED PROJECT GUIDE -->

Architecture proposal for a compute-in-memory tile combining digital control/accumulation with a future device-model interface.

## Current implementation

This repository currently contains this README and [ARCHITECTURE.md](ARCHITECTURE.md). The tile hierarchy is specified as a proposal; RTL, device models, calibration data, and executable tests are not present.

## Why study this design?

A tile needs a clear boundary between digital arithmetic and the behavior of its weight storage. Separating row sequencing, crossbar output, column accumulation, and activation makes those assumptions visible before implementation.

## Proposed features

- Bit-serial row sequencing and column accumulation.
- A device selector for SRAM, RRAM, FeFET, or PCM studies.
- Shift-and-add accumulation, quantization, bias, and ReLU or linear output modes.

These are design goals. Mentioning a device technology does not establish a calibrated device model or measured physical behavior. NeuroSim and TransCIM are conceptual references; no integration is implemented here.

## Next concrete milestone

Implement and check the digital periphery against a software reference first. Add behavioral device models only with explicit assumptions, calibration evidence, and separate validation.
