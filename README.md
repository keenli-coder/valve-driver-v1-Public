# Valve Driver V1

This repository contains the KiCad project and supporting files for the Valve Driver V1 power/driver board (separate MCU board).

Overview

- Target: drive 12V electromagnetic valve up to 1A using PWM (up to 5 kHz) with fast turn-off clamping, current sensing, and closed-loop control.
- Topology: low-side N-MOSFET switch, TC4427 gate driver, TVS clamp (33V), Schottky (SS34) recovery, Rsh = 50 mΩ, INA240 differential current sense to MCU ADC (3.3V reference).
- Board: SMD design, 2 oz copper, footprint supports SO-8 and DPAK MOSFET variants.

Files included in later release/ZIP

- KiCad project files (.sch, .kicad_pcb, libraries)
- Gerber/Drill files
- valve-driver_v1_kicad.zip (full KiCad project and Gerbers)
- BOM.csv (in repository root)

How to use

1. Clone the repository.
2. Review KiCad source in the kicad/ directory (once uploaded).
3. Produce Gerbers and order PCBs; recommended 2 oz copper.
4. Populate with parts from BOM.csv; candidate MOSFETs are listed in BOM notes.

Notes

- INA240 output is scaled for 3.3V MCU ADC (target Vout ≈ 2.0V at 1A with Rsh=50 mΩ and G≈40). Calibrate with a known current source or resistor.
- Default gate-driver supply is VIN (12V). Ensure MCU PWM level (3.3V) is compatible (TC4427 inputs accept 3.3V logic).

Repository contact: keenli-coder