<!---

This file is used to generate your project datasheet. Please fill in the information below and delete any unused
sections.

You can also include images in this folder and reference them in the markdown. Each image must be less than
512 kb in size, and the combined size of all images must be less than 1 MB.
-->

# 1-bit Full Adder

A simple 1-bit full adder circuit built using basic logic gates (XOR, AND, OR).

## How it works

A full adder adds three binary inputs (A, B, and Carry-in) to produce two outputs: Sum and Carry-out.

**Logic formulas:**
- Sum = A XOR B XOR Cin
- Carry-out = (A AND B) OR (Cin AND (A XOR B))

**Circuit components:**
- 2 XOR gates (for Sum calculation)
- 2 AND gates (for Carry-out calculation)
- 1 OR gate (combines the AND outputs)

The circuit takes three 1-bit inputs and outputs the result of binary addition.

## How to test

**Inputs (using 8-position DIP switch in Wokwi):**
- Switch 1 → Input A
- Switch 2 → Input B  
- Switch 4 → Input Cin (Carry in)

**Outputs (using LEDs):**
- Red LED → Sum output (lights when Sum = 1)
- Blue LED → Carry output (lights when Cout = 1)

**Truth table (test all 8 combinations):**

| A | B | Cin | Sum | Cout |
|---|---|-----|-----|------|
| 0 | 0 | 0 | 0 | 0 |
| 0 | 0 | 1 | 1 | 0 |
| 0 | 1 | 0 | 1 | 0 |
| 0 | 1 | 1 | 0 | 1 |
| 1 | 0 | 0 | 1 | 0 |
| 1 | 0 | 1 | 0 | 1 |
| 1 | 1 | 0 | 0 | 1 |
| 1 | 1 | 1 | 1 | 1 |

**To test the physical chip (when received):**
1. Apply 3.3V or 5V to VCC pin and GND to ground
2. Set inputs on ui[0] (A), ui[1] (B), ui[2] (Cin)
3. Read outputs from uo[0] (Sum), uo[1] (Cout)
4. Verify against truth table above

## External hardware

For Wokwi simulation:
- None required - all components simulated

For physical chip testing (when received):
- 3.3V or 5V power supply
- Breadboard
- 3x push buttons (for inputs A, B, Cin)
- 3x 1kΩ resistors (pull-down for buttons)
- 2x LEDs (for Sum and Cout outputs)
- 2x 220Ω resistors (current limiting for LEDs)
- Jumper wires

For Lab 4 breadboard implementation (7400-series ICs):
- 74LS86 (Quad 2-input XOR gate)
- 74LS08 (Quad 2-input AND gate)
- 74LS32 (Quad 2-input OR gate)
- Same button/LED/resistor setup as above
- 5V power from Arduino or power supply

## How the chip was submitted

This design was submitted to Tiny Tapeout for fabrication. The project files include:
- `info.yaml` - Project configuration and pin mapping
- `wokwi/diagram.json` - Circuit schematic in Wokwi format

## Pin mapping (for physical chip)

| Pin | Signal | Direction |
|-----|--------|-----------|
| ui[0] | A | Input |
| ui[1] | B | Input |
| ui[2] | Cin | Input |
| uo[0] | Sum | Output |
| uo[1] | Cout | Output |
