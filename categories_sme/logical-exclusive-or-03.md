# SME / Logical / Exclusive OR — Part 3

## sveortb[_s8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/sveortb%5B_s8%5D

### Signature (source notation)

```c
svint8_t sveortb[_s8](svint8_t even, svint8_t op1, svint8_t op2);
```

### Description

Interleaving exclusive OR (top, bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Logical / Exclusive OR

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
  "even": {
    "register": "Zeven.B|Ztied.B"
  },
  "op1": {
    "register": "Zop1.B"
  },
  "op2": {
    "register": "Zop2.B"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.B|Ztied.B": "result"
  }
]
```

### Instruction mapping

When result and even are in the same register, this intrinsic compiles to:

```asm
EORTB Ztied.B, Zop1.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/EORTB--Interleaving-exclusive-OR--top--bottom--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zeven
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
EORTB Zresult.B, Zop1.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/EORTB--Interleaving-exclusive-OR--top--bottom--

### Operation

Source operation ID: `SveOperation_sveortb_s8`

**Operation**



Return a vector in which, for each even element index *i*:




- element *i* contains `even[i]`
- element *i* + 1 contains `op1[i + 1] ^ op2[i]`

## sveortb[_u16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/sveortb%5B_u16%5D

### Signature (source notation)

```c
svuint16_t sveortb[_u16](svuint16_t even, svuint16_t op1, svuint16_t op2);
```

### Description

Interleaving exclusive OR (top, bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Logical / Exclusive OR

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
  "even": {
    "register": "Zeven.H|Ztied.H"
  },
  "op1": {
    "register": "Zop1.H"
  },
  "op2": {
    "register": "Zop2.H"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.H|Ztied.H": "result"
  }
]
```

### Instruction mapping

When result and even are in the same register, this intrinsic compiles to:

```asm
EORTB Ztied.H, Zop1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/EORTB--Interleaving-exclusive-OR--top--bottom--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zeven
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
EORTB Zresult.H, Zop1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/EORTB--Interleaving-exclusive-OR--top--bottom--

### Operation

Source operation ID: `SveOperation_sveortb_s8`

**Operation**



Return a vector in which, for each even element index *i*:




- element *i* contains `even[i]`
- element *i* + 1 contains `op1[i + 1] ^ op2[i]`

## sveortb[_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/sveortb%5B_u32%5D

### Signature (source notation)

```c
svuint32_t sveortb[_u32](svuint32_t even, svuint32_t op1, svuint32_t op2);
```

### Description

Interleaving exclusive OR (top, bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Logical / Exclusive OR

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
  "even": {
    "register": "Zeven.S|Ztied.S"
  },
  "op1": {
    "register": "Zop1.S"
  },
  "op2": {
    "register": "Zop2.S"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.S|Ztied.S": "result"
  }
]
```

### Instruction mapping

When result and even are in the same register, this intrinsic compiles to:

```asm
EORTB Ztied.S, Zop1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/EORTB--Interleaving-exclusive-OR--top--bottom--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zeven
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
EORTB Zresult.S, Zop1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/EORTB--Interleaving-exclusive-OR--top--bottom--

### Operation

Source operation ID: `SveOperation_sveortb_s8`

**Operation**



Return a vector in which, for each even element index *i*:




- element *i* contains `even[i]`
- element *i* + 1 contains `op1[i + 1] ^ op2[i]`

## sveortb[_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/sveortb%5B_u64%5D

### Signature (source notation)

```c
svuint64_t sveortb[_u64](svuint64_t even, svuint64_t op1, svuint64_t op2);
```

### Description

Interleaving exclusive OR (top, bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Logical / Exclusive OR

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
  "even": {
    "register": "Zeven.D|Ztied.D"
  },
  "op1": {
    "register": "Zop1.D"
  },
  "op2": {
    "register": "Zop2.D"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.D|Ztied.D": "result"
  }
]
```

### Instruction mapping

When result and even are in the same register, this intrinsic compiles to:

```asm
EORTB Ztied.D, Zop1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/EORTB--Interleaving-exclusive-OR--top--bottom--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zeven
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
EORTB Zresult.D, Zop1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/EORTB--Interleaving-exclusive-OR--top--bottom--

### Operation

Source operation ID: `SveOperation_sveortb_s8`

**Operation**



Return a vector in which, for each even element index *i*:




- element *i* contains `even[i]`
- element *i* + 1 contains `op1[i + 1] ^ op2[i]`

## sveortb[_u8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/sveortb%5B_u8%5D

### Signature (source notation)

```c
svuint8_t sveortb[_u8](svuint8_t even, svuint8_t op1, svuint8_t op2);
```

### Description

Interleaving exclusive OR (top, bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Logical / Exclusive OR

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
  "even": {
    "register": "Zeven.B|Ztied.B"
  },
  "op1": {
    "register": "Zop1.B"
  },
  "op2": {
    "register": "Zop2.B"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.B|Ztied.B": "result"
  }
]
```

### Instruction mapping

When result and even are in the same register, this intrinsic compiles to:

```asm
EORTB Ztied.B, Zop1.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/EORTB--Interleaving-exclusive-OR--top--bottom--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zeven
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
EORTB Zresult.B, Zop1.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/EORTB--Interleaving-exclusive-OR--top--bottom--

### Operation

Source operation ID: `SveOperation_sveortb_s8`

**Operation**



Return a vector in which, for each even element index *i*:




- element *i* contains `even[i]`
- element *i* + 1 contains `op1[i + 1] ^ op2[i]`

## sveorv[_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/sveorv%5B_s16%5D

### Signature (source notation)

```c
int16_t sveorv[_s16](svbool_t pg, svint16_t op);
```

### Description

Bitwise exclusive OR reduction to scalar

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / Exclusive OR

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
  "value": "int16_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Pg"
  },
  "op": {
    "register": "Zop.H"
  }
}
```

### Result mapping

```json
[
  {
    "Hresult": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
EORV Hresult, Pg, Zop.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/EORV--Bitwise-exclusive-OR-reduction-to-scalar-

### Operation

Source operation ID: `SveOperation_sveorv_s8`

**Operation**



Return the bitwise exclusive OR of all active elements of `op`.  Return zero if no elements are active.

## sveorv[_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/sveorv%5B_s32%5D

### Signature (source notation)

```c
int32_t sveorv[_s32](svbool_t pg, svint32_t op);
```

### Description

Bitwise exclusive OR reduction to scalar

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / Exclusive OR

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
  "value": "int32_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Pg"
  },
  "op": {
    "register": "Zop.S"
  }
}
```

### Result mapping

```json
[
  {
    "Sresult": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
EORV Sresult, Pg, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/EORV--Bitwise-exclusive-OR-reduction-to-scalar-

### Operation

Source operation ID: `SveOperation_sveorv_s8`

**Operation**



Return the bitwise exclusive OR of all active elements of `op`.  Return zero if no elements are active.

## sveorv[_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/sveorv%5B_s64%5D

### Signature (source notation)

```c
int64_t sveorv[_s64](svbool_t pg, svint64_t op);
```

### Description

Bitwise exclusive OR reduction to scalar

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / Exclusive OR

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
  "value": "int64_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Pg"
  },
  "op": {
    "register": "Zop.D"
  }
}
```

### Result mapping

```json
[
  {
    "Dresult": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
EORV Dresult, Pg, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/EORV--Bitwise-exclusive-OR-reduction-to-scalar-

### Operation

Source operation ID: `SveOperation_sveorv_s8`

**Operation**



Return the bitwise exclusive OR of all active elements of `op`.  Return zero if no elements are active.

## sveorv[_s8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/sveorv%5B_s8%5D

### Signature (source notation)

```c
int8_t sveorv[_s8](svbool_t pg, svint8_t op);
```

### Description

Bitwise exclusive OR reduction to scalar

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / Exclusive OR

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
  "value": "int8_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Pg"
  },
  "op": {
    "register": "Zop.B"
  }
}
```

### Result mapping

```json
[
  {
    "Bresult": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
EORV Bresult, Pg, Zop.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/EORV--Bitwise-exclusive-OR-reduction-to-scalar-

### Operation

Source operation ID: `SveOperation_sveorv_s8`

**Operation**



Return the bitwise exclusive OR of all active elements of `op`.  Return zero if no elements are active.

## sveorv[_u16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/sveorv%5B_u16%5D

### Signature (source notation)

```c
uint16_t sveorv[_u16](svbool_t pg, svuint16_t op);
```

### Description

Bitwise exclusive OR reduction to scalar

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / Exclusive OR

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
  "value": "uint16_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Pg"
  },
  "op": {
    "register": "Zop.H"
  }
}
```

### Result mapping

```json
[
  {
    "Hresult": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
EORV Hresult, Pg, Zop.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/EORV--Bitwise-exclusive-OR-reduction-to-scalar-

### Operation

Source operation ID: `SveOperation_sveorv_s8`

**Operation**



Return the bitwise exclusive OR of all active elements of `op`.  Return zero if no elements are active.

## sveorv[_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/sveorv%5B_u32%5D

### Signature (source notation)

```c
uint32_t sveorv[_u32](svbool_t pg, svuint32_t op);
```

### Description

Bitwise exclusive OR reduction to scalar

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / Exclusive OR

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
  "value": "uint32_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Pg"
  },
  "op": {
    "register": "Zop.S"
  }
}
```

### Result mapping

```json
[
  {
    "Sresult": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
EORV Sresult, Pg, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/EORV--Bitwise-exclusive-OR-reduction-to-scalar-

### Operation

Source operation ID: `SveOperation_sveorv_s8`

**Operation**



Return the bitwise exclusive OR of all active elements of `op`.  Return zero if no elements are active.

## sveorv[_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/sveorv%5B_u64%5D

### Signature (source notation)

```c
uint64_t sveorv[_u64](svbool_t pg, svuint64_t op);
```

### Description

Bitwise exclusive OR reduction to scalar

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / Exclusive OR

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
  "value": "uint64_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Pg"
  },
  "op": {
    "register": "Zop.D"
  }
}
```

### Result mapping

```json
[
  {
    "Dresult": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
EORV Dresult, Pg, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/EORV--Bitwise-exclusive-OR-reduction-to-scalar-

### Operation

Source operation ID: `SveOperation_sveorv_s8`

**Operation**



Return the bitwise exclusive OR of all active elements of `op`.  Return zero if no elements are active.

## sveorv[_u8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/sveorv%5B_u8%5D

### Signature (source notation)

```c
uint8_t sveorv[_u8](svbool_t pg, svuint8_t op);
```

### Description

Bitwise exclusive OR reduction to scalar

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / Exclusive OR

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
  "value": "uint8_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Pg"
  },
  "op": {
    "register": "Zop.B"
  }
}
```

### Result mapping

```json
[
  {
    "Bresult": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
EORV Bresult, Pg, Zop.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/EORV--Bitwise-exclusive-OR-reduction-to-scalar-

### Operation

Source operation ID: `SveOperation_sveorv_s8`

**Operation**



Return the bitwise exclusive OR of all active elements of `op`.  Return zero if no elements are active.

