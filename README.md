# Custom CMOS IC & ASIC Design Portfolio

This public repository presents my VLSI/ASIC design work completed as part of the ECE425 course, in course-milestone order: a custom CMOS standard-cell library, a bit-sliced processor datapath, and ASIC physical design.

## Project Flow

```text
Custom standard cells
  -> ALU and register file
  -> bit-sliced datapath
  -> datapath with shifter (extra credit)
  -> synthesis and place-and-route
```

## Milestones at a Glance

| Order | Directory | My work |
|---:|---|---|
| 1 | [`01_mp_stdcell`](01_mp_stdcell/) | Custom CMOS standard-cell library, including layout artifacts and public-safe Sim/DRC/LVS results |
| 2 | [`02_mp_datapath`](02_mp_datapath/) | ALU, register file, integrated bit-sliced datapath, and a **datapath-with-shifter extra-credit implementation** |
| 3 | [`03_mp_pnr`](03_mp_pnr/) | Custom `stdcells.lef/.lib` and `regfile.lef/.lib` abstractions, synthesis/PnR scripts, and final physical-design renders |

## 01 — Custom Standard-Cell Library

The standard-cell milestone builds the physical implementation foundation used by the later datapath and PnR work.

- Designed transistor-level CMOS schematics and layouts for combinational logic, storage elements, and multiplexing primitives.
- Created cells with consistent placement conventions, power rails, well structures, and accessible routing pins so they can be used as a library rather than as isolated layouts.
- Verified the evaluated cells with functional simulation, DRC, and LVS.
- Exported the library as `stdcells.lef` and `stdcells.lib` for downstream automated physical design.

See [`01_mp_stdcell`](01_mp_stdcell/) for the cell artifacts, screenshots, and public-safe verification summary.

## 02 — Bit-Sliced RISC-V Datapath

The datapath milestone applies the custom cells to a 32-bit, single-cycle, bit-sliced processor datapath.

- Implemented and verified core datapath blocks, including the ALU and register file.
- Built the processor datapath from repeated bit-slice structures, preserving the regularity needed for custom layout.
- Completed checkpoint 1 with ALU and register-file schematic/layout validation plus integrated datapath functional simulation.
- Completed checkpoint 2 with an integrated datapath layout that passed simulation, DRC, and LVS.
- Implemented `datapath_s`, a **datapath-with-shifter extra-credit variant** that adds shift functionality beyond the required baseline datapath. Its schematic and layout screenshots are included in `checkpoint2_results/`.

See [`02_mp_datapath`](02_mp_datapath/) for the checkpoint summaries and design views.

## 03 — ASIC Synthesis and Physical Design

The PnR milestone takes the custom IP into an automated ASIC implementation flow.

- Packaged the custom standard-cell library as LEF and Liberty models for physical-design tools.
- Performed automated place-and-route for the controller and a full CPU implementation using the standard-cell flow.
- Exported the custom register file as a hard-macro LEF/Liberty model and integrated it into a second full-CPU PnR implementation.
- Preserved selected Innovus TCL scripts and final controller, CPU, macro-integrated CPU, and integration renders.

See [`03_mp_pnr`](03_mp_pnr/) for the PnR artifacts and final images.

## Validation Highlights

- Standard-cell milestone: all evaluated cells passed simulation, DRC, and LVS.
- Datapath checkpoint 1: ALU and register file passed simulation, DRC, and LVS; integrated datapath functional simulation passed.
- Datapath checkpoint 2: the integrated datapath passed simulation, DRC, and LVS.
- Extra credit: a datapath variant with shift functionality is documented by the schematic and layout artifacts in checkpoint 2.

## Scope and Public-Release Policy

Completed as part of ECE425. Course-provided RTL and verification infrastructure were used for system integration but are not redistributed. Raw autograder logs, private course records, tool-generated databases, and non-redistributable materials are excluded.

## Academic Integrity and Disclaimer

This repository is a retrospective portfolio of completed work, shared for documentation and learning only. **Use it at your own risk.** It is not an answer key, tutorial substitute, or source of materials to submit for credit.

Do not copy, adapt, or submit any part of this repository for a course assignment, assessment, or other work that is expected to be your own. The author does not support, endorse, or assist academic dishonesty.
