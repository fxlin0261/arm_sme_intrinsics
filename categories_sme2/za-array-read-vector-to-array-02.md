# SME2 / ZA array / Read / Vector to array — Part 2

## svreadz_za8_u8_vg1x2

ISA classification: SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svreadz_za8_u8_vg1x2

### Signature (source notation)

```c
svuint8x2_t svreadz_za8_u8_vg1x2(uint32_t slice)
    __arm_streaming __arm_inout("za");
```

### Description

Move and zero two ZA single-vector groups to Z two-vector operand

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Read / Vector to array

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2p1
```

### Return type metadata

```json
{
  "return_base_type": "uint8",
  "element_bit_size": "8",
  "value": "svuint8x2_t"
}
```

### Argument preparation and constraints

```json
{
  "slice": {
    "register+immediate": "Wreg1 + imm1"
  }
}
```

### Result mapping

```json
[
  {
    "{ Zreg1.D, Zreg2.D }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
MOVAZ { Zreg1.D, Zreg2.D }, ZA.D[Wreg1, imm1, VGX2]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/MOVAZ--array-to-vector--two-registers---Move-and-zero-two-ZA-single-vector-groups-to-Z-two-vector-operand-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svreadz_za8_u8_vg1x4

ISA classification: SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svreadz_za8_u8_vg1x4

### Signature (source notation)

```c
svuint8x4_t svreadz_za8_u8_vg1x4(uint32_t slice)
    __arm_streaming __arm_inout("za");
```

### Description

Move and zero four ZA single-vector groups to Z four-vector operand

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Read / Vector to array

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2p1
```

### Return type metadata

```json
{
  "return_base_type": "uint8",
  "element_bit_size": "8",
  "value": "svuint8x4_t"
}
```

### Argument preparation and constraints

```json
{
  "slice": {
    "register+immediate": "Wreg1 + imm1"
  }
}
```

### Result mapping

```json
[
  {
    "{ Zreg1.D - Zreg2.D }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
MOVAZ { Zreg1.D - Zreg2.D }, ZA.D[Wreg1, imm1, VGX4]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/MOVAZ--array-to-vector--four-registers---Move-and-zero-four-ZA-single-vector-groups-to-Z-four-vector-operand-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

