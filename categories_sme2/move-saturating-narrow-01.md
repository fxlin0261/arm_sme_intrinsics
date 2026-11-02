# SME2 / Move / Saturating narrow — Part 1

## svqcvtn_s16[_s32_x2]

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqcvtn_s16%5B_s32_x2%5D

### Signature (source notation)

```c
svint16_t svqcvtn_s16[_s32_x2](svint32x2_t zn);
```

### Description

Signed 32-bit integer saturating extract narrow and interleave to 16-bit integer

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Move / Saturating narrow

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p1)|FEAT_SME2
```

### Return type metadata

```json
{
  "return_base_type": "int16",
  "element_bit_size": "16",
  "value": "svint16_t"
}
```

### Argument preparation and constraints

```json
{
  "zn": {
    "Z multi-vector": "{ Zreg2.S, Zreg3.S }"
  }
}
```

### Result mapping

```json
[
  {
    "Zreg1.H": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
SQCVTN Zreg1.H, { Zreg2.S, Zreg3.S }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQCVTN--Signed-32-bit-integer-saturating-extract-narrow-and-interleave-to-16-bit-integer-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svqcvtn_u16[_s32_x2]

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqcvtn_u16%5B_s32_x2%5D

### Signature (source notation)

```c
svuint16_t svqcvtn_u16[_s32_x2](svint32x2_t zn);
```

### Description

Signed 32-bit integer saturating unsigned extract narrow and interleave to 16-bit integer

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Move / Saturating narrow

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p1)|FEAT_SME2
```

### Return type metadata

```json
{
  "return_base_type": "uint16",
  "element_bit_size": "16",
  "value": "svuint16_t"
}
```

### Argument preparation and constraints

```json
{
  "zn": {
    "Z multi-vector": "{ Zreg2.S, Zreg3.S }"
  }
}
```

### Result mapping

```json
[
  {
    "Zreg1.H": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
SQCVTUN Zreg1.H, { Zreg2.S, Zreg3.S }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQCVTUN--Signed-32-bit-integer-saturating-unsigned-extract-narrow-and-interleave-to-16-bit-integer-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svqcvtn_u16[_u32_x2]

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqcvtn_u16%5B_u32_x2%5D

### Signature (source notation)

```c
svuint16_t svqcvtn_u16[_u32_x2](svuint32x2_t zn);
```

### Description

Unsigned 32-bit integer saturating extract narrow and interleave to 16-bit integer

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Move / Saturating narrow

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p1)|FEAT_SME2
```

### Return type metadata

```json
{
  "return_base_type": "uint16",
  "element_bit_size": "16",
  "value": "svuint16_t"
}
```

### Argument preparation and constraints

```json
{
  "zn": {
    "Z multi-vector": "{ Zreg2.S, Zreg3.S }"
  }
}
```

### Result mapping

```json
[
  {
    "Zreg1.H": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
UQCVTN Zreg1.H, { Zreg2.S, Zreg3.S }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQCVTN--Unsigned-32-bit-integer-saturating-extract-narrow-and-interleave-to-16-bit-integer-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

