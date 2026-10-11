# IEEE-754-Floating-Point-Adder
# IEEE 754 Single-Precision Floating-Point Adder

A modular Verilog RTL implementation of a 32-bit IEEE 754 single-precision floating-point adder, developed as an educational digital logic design project.

## Overview

The project demonstrates how two 32-bit floating-point operands can be processed through separate hardware stages to produce a floating-point result.

## IEEE 754 Single-Precision Format

A 32-bit floating-point number consists of:

- **Sign:** 1 bit
- **Exponent:** 8 bits, with a bias of 127
- **Fraction:** 23 bits

## Architecture

The design is organized into the following stages:

1. Unpack the input operands into sign, exponent and fraction fields.
2. Align the exponents.
3. Add or subtract the significands according to the operand signs.
4. Normalize the intermediate result.
5. Round the significand.
6. Pack the fields into a 32-bit output.

## Technologies Used

- Verilog HDL / RTL
- AMD Xilinx Vivado
- Digital Logic Design
- Behavioral Simulation

## Project Structure

```text
ieee754-floating-point-adder/
├── rtl/
│   ├── 01_fp_unpack.v
│   ├── 02_exp_align.v
│   ├── 03_significand_add.v
│   ├── 04_normalize.v
│   ├── 05_round_mantissa.v
│   ├── 06_fp_pack.v
│   └── 07_fp_adder_top.v
├── testbench/
│   └── 08_tb_fp_adder.v
├── docs/
│   ├── project-report.pdf
│   └── simulation-waveform.png
├── README.md
└── .gitignore
```

*The structure above is a suggested layout. Include only files that are actually available in the project.*

## Simulation

1. Open AMD Xilinx Vivado.
2. Create a new RTL project.
3. Add the Verilog design files as Design Sources.
4. Add the testbench as a Simulation Source.
5. Set `fp_adder_top` as the design top module.
6. Set `tb_fp_adder` as the simulation top module.
7. Run Behavioral Simulation and inspect the output and waveform.

## Suggested Test Cases

- Positive floating-point addition: 1.5 + 2.25 = 3.75
- Negative operands
- Mixed-sign addition and subtraction
- Large exponent differences
- Addition carry-out and normalization

These are suggested test cases; verify the actual outputs before reporting successful results.

## Limitations

This project is an educational prototype and is not yet fully IEEE 754-compliant. Special-value handling, subnormal numbers, rounding and some edge cases may be incomplete.

## Future Improvements

- Implement complete guard, round and sticky bit handling.
- Improve normalization after subtraction.
- Handle signed zero, subnormal numbers, infinity, NaN, overflow and underflow.
- Add automated PASS/FAIL test cases.
- Compare results against a trusted IEEE 754 reference.

## Disclaimer

This repository documents an educational hardware design project. Full IEEE 754 compliance should not be claimed without comprehensive verification.
