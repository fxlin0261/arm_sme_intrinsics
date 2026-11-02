# SME / Logical / Exclusive OR and rotate — Part 1

## svxar[_n_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svxar%5B_n_s16%5D

### Signature (source notation)

```c
svint16_t svxar[_n_s16](svint16_t op1, svint16_t op2, uint64_t imm3);
```

### Description

Bitwise exclusive OR and rotate right

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Logical / Exclusive OR and rotate

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME
```

### Return type metadata

```json
{
  "return_base_type": "int",
  "element_bit_size": "16",
  "value": "svint16_t"
}
```

### Argument preparation and constraints

```json
{
  "op1": {
    "register": "Zop1.H|Ztied1.H"
  },
  "op2": {
    "register": "Zop2.H|Ztied2.H"
  },
  "imm3": {
    "minimum": 1,
    "maximum": 16
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.H|Ztied1.H|Ztied2.H": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
XAR Ztied1.H, Ztied1.H, Zop2.H, #imm3
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/XAR--Bitwise-exclusive-OR-and-rotate-right-by-immediate-

When result and op2 are in the same register, this intrinsic compiles to:

```asm
XAR Ztied2.H, Ztied2.H, Zop1.H, #imm3
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/XAR--Bitwise-exclusive-OR-and-rotate-right-by-immediate-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
XAR Zresult.H, Zresult.H, Zop2.H, #imm3
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/XAR--Bitwise-exclusive-OR-and-rotate-right-by-immediate-

### Operation

Source operation ID: `SveOperation_svxar_n_s8`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Exclusive-OR `op1[i]` and `op2[i]`.
- Rotate the result right by `imm3` bits.

## svxar[_n_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svxar%5B_n_s32%5D

### Signature (source notation)

```c
svint32_t svxar[_n_s32](svint32_t op1, svint32_t op2, uint64_t imm3);
```

### Description

Bitwise exclusive OR and rotate right

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Logical / Exclusive OR and rotate

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME
```

### Return type metadata

```json
{
  "return_base_type": "int",
  "element_bit_size": "32",
  "value": "svint32_t"
}
```

### Argument preparation and constraints

```json
{
  "op1": {
    "register": "Zop1.S|Ztied1.S"
  },
  "op2": {
    "register": "Zop2.S|Ztied2.S"
  },
  "imm3": {
    "minimum": 1,
    "maximum": 32
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.S|Ztied1.S|Ztied2.S": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
XAR Ztied1.S, Ztied1.S, Zop2.S, #imm3
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/XAR--Bitwise-exclusive-OR-and-rotate-right-by-immediate-

When result and op2 are in the same register, this intrinsic compiles to:

```asm
XAR Ztied2.S, Ztied2.S, Zop1.S, #imm3
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/XAR--Bitwise-exclusive-OR-and-rotate-right-by-immediate-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
XAR Zresult.S, Zresult.S, Zop2.S, #imm3
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/XAR--Bitwise-exclusive-OR-and-rotate-right-by-immediate-

### Operation

Source operation ID: `SveOperation_svxar_n_s8`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Exclusive-OR `op1[i]` and `op2[i]`.
- Rotate the result right by `imm3` bits.

## svxar[_n_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svxar%5B_n_s64%5D

### Signature (source notation)

```c
svint64_t svxar[_n_s64](svint64_t op1, svint64_t op2, uint64_t imm3);
```

### Description

Bitwise exclusive OR and rotate right

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Logical / Exclusive OR and rotate

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME
```

### Return type metadata

```json
{
  "return_base_type": "int",
  "element_bit_size": "64",
  "value": "svint64_t"
}
```

### Argument preparation and constraints

```json
{
  "op1": {
    "register": "Zop1.D|Ztied1.D"
  },
  "op2": {
    "register": "Zop2.D|Ztied2.D"
  },
  "imm3": {
    "minimum": 1,
    "maximum": 64
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.D|Ztied1.D|Ztied2.D": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
XAR Ztied1.D, Ztied1.D, Zop2.D, #imm3
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/XAR--Bitwise-exclusive-OR-and-rotate-right-by-immediate-

When result and op2 are in the same register, this intrinsic compiles to:

```asm
XAR Ztied2.D, Ztied2.D, Zop1.D, #imm3
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/XAR--Bitwise-exclusive-OR-and-rotate-right-by-immediate-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
XAR Zresult.D, Zresult.D, Zop2.D, #imm3
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/XAR--Bitwise-exclusive-OR-and-rotate-right-by-immediate-

### Operation

Source operation ID: `SveOperation_svxar_n_s8`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Exclusive-OR `op1[i]` and `op2[i]`.
- Rotate the result right by `imm3` bits.

## svxar[_n_s8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svxar%5B_n_s8%5D

### Signature (source notation)

```c
svint8_t svxar[_n_s8](svint8_t op1, svint8_t op2, uint64_t imm3);
```

### Description

Bitwise exclusive OR and rotate right

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Logical / Exclusive OR and rotate

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME
```

### Return type metadata

```json
{
  "return_base_type": "int",
  "element_bit_size": "8",
  "value": "svint8_t"
}
```

### Argument preparation and constraints

```json
{
  "op1": {
    "register": "Zop1.B|Ztied1.B"
  },
  "op2": {
    "register": "Zop2.B|Ztied2.B"
  },
  "imm3": {
    "minimum": 1,
    "maximum": 8
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.B|Ztied1.B|Ztied2.B": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
XAR Ztied1.B, Ztied1.B, Zop2.B, #imm3
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/XAR--Bitwise-exclusive-OR-and-rotate-right-by-immediate-

When result and op2 are in the same register, this intrinsic compiles to:

```asm
XAR Ztied2.B, Ztied2.B, Zop1.B, #imm3
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/XAR--Bitwise-exclusive-OR-and-rotate-right-by-immediate-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
XAR Zresult.B, Zresult.B, Zop2.B, #imm3
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/XAR--Bitwise-exclusive-OR-and-rotate-right-by-immediate-

### Operation

Source operation ID: `SveOperation_svxar_n_s8`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Exclusive-OR `op1[i]` and `op2[i]`.
- Rotate the result right by `imm3` bits.

## svxar[_n_u16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svxar%5B_n_u16%5D

### Signature (source notation)

```c
svuint16_t svxar[_n_u16](svuint16_t op1, svuint16_t op2, uint64_t imm3);
```

### Description

Bitwise exclusive OR and rotate right

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Logical / Exclusive OR and rotate

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME
```

### Return type metadata

```json
{
  "return_base_type": "uint",
  "element_bit_size": "16",
  "value": "svuint16_t"
}
```

### Argument preparation and constraints

```json
{
  "op1": {
    "register": "Zop1.H|Ztied1.H"
  },
  "op2": {
    "register": "Zop2.H|Ztied2.H"
  },
  "imm3": {
    "minimum": 1,
    "maximum": 16
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.H|Ztied1.H|Ztied2.H": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
XAR Ztied1.H, Ztied1.H, Zop2.H, #imm3
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/XAR--Bitwise-exclusive-OR-and-rotate-right-by-immediate-

When result and op2 are in the same register, this intrinsic compiles to:

```asm
XAR Ztied2.H, Ztied2.H, Zop1.H, #imm3
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/XAR--Bitwise-exclusive-OR-and-rotate-right-by-immediate-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
XAR Zresult.H, Zresult.H, Zop2.H, #imm3
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/XAR--Bitwise-exclusive-OR-and-rotate-right-by-immediate-

### Operation

Source operation ID: `SveOperation_svxar_n_s8`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Exclusive-OR `op1[i]` and `op2[i]`.
- Rotate the result right by `imm3` bits.

## svxar[_n_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svxar%5B_n_u32%5D

### Signature (source notation)

```c
svuint32_t svxar[_n_u32](svuint32_t op1, svuint32_t op2, uint64_t imm3);
```

### Description

Bitwise exclusive OR and rotate right

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Logical / Exclusive OR and rotate

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME
```

### Return type metadata

```json
{
  "return_base_type": "uint",
  "element_bit_size": "32",
  "value": "svuint32_t"
}
```

### Argument preparation and constraints

```json
{
  "op1": {
    "register": "Zop1.S|Ztied1.S"
  },
  "op2": {
    "register": "Zop2.S|Ztied2.S"
  },
  "imm3": {
    "minimum": 1,
    "maximum": 32
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.S|Ztied1.S|Ztied2.S": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
XAR Ztied1.S, Ztied1.S, Zop2.S, #imm3
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/XAR--Bitwise-exclusive-OR-and-rotate-right-by-immediate-

When result and op2 are in the same register, this intrinsic compiles to:

```asm
XAR Ztied2.S, Ztied2.S, Zop1.S, #imm3
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/XAR--Bitwise-exclusive-OR-and-rotate-right-by-immediate-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
XAR Zresult.S, Zresult.S, Zop2.S, #imm3
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/XAR--Bitwise-exclusive-OR-and-rotate-right-by-immediate-

### Operation

Source operation ID: `SveOperation_svxar_n_s8`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Exclusive-OR `op1[i]` and `op2[i]`.
- Rotate the result right by `imm3` bits.

## svxar[_n_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svxar%5B_n_u64%5D

### Signature (source notation)

```c
svuint64_t svxar[_n_u64](svuint64_t op1, svuint64_t op2, uint64_t imm3);
```

### Description

Bitwise exclusive OR and rotate right

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Logical / Exclusive OR and rotate

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME
```

### Return type metadata

```json
{
  "return_base_type": "uint",
  "element_bit_size": "64",
  "value": "svuint64_t"
}
```

### Argument preparation and constraints

```json
{
  "op1": {
    "register": "Zop1.D|Ztied1.D"
  },
  "op2": {
    "register": "Zop2.D|Ztied2.D"
  },
  "imm3": {
    "minimum": 1,
    "maximum": 64
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.D|Ztied1.D|Ztied2.D": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
XAR Ztied1.D, Ztied1.D, Zop2.D, #imm3
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/XAR--Bitwise-exclusive-OR-and-rotate-right-by-immediate-

When result and op2 are in the same register, this intrinsic compiles to:

```asm
XAR Ztied2.D, Ztied2.D, Zop1.D, #imm3
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/XAR--Bitwise-exclusive-OR-and-rotate-right-by-immediate-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
XAR Zresult.D, Zresult.D, Zop2.D, #imm3
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/XAR--Bitwise-exclusive-OR-and-rotate-right-by-immediate-

### Operation

Source operation ID: `SveOperation_svxar_n_s8`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Exclusive-OR `op1[i]` and `op2[i]`.
- Rotate the result right by `imm3` bits.

## svxar[_n_u8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svxar%5B_n_u8%5D

### Signature (source notation)

```c
svuint8_t svxar[_n_u8](svuint8_t op1, svuint8_t op2, uint64_t imm3);
```

### Description

Bitwise exclusive OR and rotate right

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Logical / Exclusive OR and rotate

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME
```

### Return type metadata

```json
{
  "return_base_type": "uint",
  "element_bit_size": "8",
  "value": "svuint8_t"
}
```

### Argument preparation and constraints

```json
{
  "op1": {
    "register": "Zop1.B|Ztied1.B"
  },
  "op2": {
    "register": "Zop2.B|Ztied2.B"
  },
  "imm3": {
    "minimum": 1,
    "maximum": 8
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.B|Ztied1.B|Ztied2.B": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
XAR Ztied1.B, Ztied1.B, Zop2.B, #imm3
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/XAR--Bitwise-exclusive-OR-and-rotate-right-by-immediate-

When result and op2 are in the same register, this intrinsic compiles to:

```asm
XAR Ztied2.B, Ztied2.B, Zop1.B, #imm3
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/XAR--Bitwise-exclusive-OR-and-rotate-right-by-immediate-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
XAR Zresult.B, Zresult.B, Zop2.B, #imm3
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/XAR--Bitwise-exclusive-OR-and-rotate-right-by-immediate-

### Operation

Source operation ID: `SveOperation_svxar_n_s8`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Exclusive-OR `op1[i]` and `op2[i]`.
- Rotate the result right by `imm3` bits.

