# neuro-cim-tile: Architectural Specification

This is a proposed interface/dataflow specification. RTL and executable validation are not yet implemented in this repository.

## 1. Top-Level Hierarchy
1. `cim_row_driver`: Bit-serial activation sequencer and wordline pulse generator.
2. `cim_crossbar_macro`: $M \times N$ array with parameter `DEVICE_TECH` (SRAM, RRAM, FeFET, PCM).
3. `cim_column_accum`: Column-wise bitline summation and optional ADC quantization.
4. `cim_activation_unit`: Shift-and-add accumulation across bit-planes + bias addition + ReLU / Linear bypass.

## 2. Pinout & Interface
| Signal | Direction | Width | Description |
| :--- | :---: | :---: | :--- |
| `clk` | In | 1 | Clock |
| `rst_n` | In | 1 | Active-low reset |
| `act_in` | In | ROWS*4 | Packed 4-bit activations for all rows |
| `act_valid` | In | 1 | Activations valid strobe |
| `mode_linear` | In | 1 | 0: ReLU activation, 1: Linear pass-through (TransCIM) |
| `bias_in` | In | COLS*16| Optional bias per column |
| `result_out` | Out | COLS*8 | Quantized output activations |
| `result_valid` | Out | 1 | Output valid strobe |
