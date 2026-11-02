# SME / Shift / Left / Vector shift left and insert — Part 1

## svsli[_n_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsli%5B_n_s16%5D

### Signature (source notation)

```c
svint16_t svsli[_n_s16](svint16_t op1, svint16_t op2, uint64_t imm3);
```

### Description

Shift left and insert

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Shift / Left / Vector shift left and insert

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
    "register": "Ztied1.H"
  },
  "op2": {
    "register": "Zop2.H"
  },
  "imm3": {
    "minimum": 0,
    "maximum": 15
  }
}
```

### Result mapping

```json
[
  {
    "Ztied1.H": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
SLI Ztied1.H, Zop2.H, #imm3
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SLI--Shift-left-and-insert--immediate--

### Operation

Source operation ID: `SveOperation_svsli_n_s8`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Shift `op2[i]` left by `imm3` bits.
- OR the result with the low `imm3` bits of `op1[i]`.

## svsli[_n_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsli%5B_n_s32%5D

### Signature (source notation)

```c
svint32_t svsli[_n_s32](svint32_t op1, svint32_t op2, uint64_t imm3);
```

### Description

Shift left and insert

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Shift / Left / Vector shift left and insert

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
    "register": "Ztied1.S"
  },
  "op2": {
    "register": "Zop2.S"
  },
  "imm3": {
    "minimum": 0,
    "maximum": 31
  }
}
```

### Result mapping

```json
[
  {
    "Ztied1.S": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
SLI Ztied1.S, Zop2.S, #imm3
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SLI--Shift-left-and-insert--immediate--

### Operation

Source operation ID: `SveOperation_svsli_n_s8`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Shift `op2[i]` left by `imm3` bits.
- OR the result with the low `imm3` bits of `op1[i]`.

## svsli[_n_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsli%5B_n_s64%5D

### Signature (source notation)

```c
svint64_t svsli[_n_s64](svint64_t op1, svint64_t op2, uint64_t imm3);
```

### Description

Shift left and insert

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Shift / Left / Vector shift left and insert

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
    "register": "Ztied1.D"
  },
  "op2": {
    "register": "Zop2.D"
  },
  "imm3": {
    "minimum": 0,
    "maximum": 63
  }
}
```

### Result mapping

```json
[
  {
    "Ztied1.D": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
SLI Ztied1.D, Zop2.D, #imm3
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SLI--Shift-left-and-insert--immediate--

### Operation

Source operation ID: `SveOperation_svsli_n_s8`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Shift `op2[i]` left by `imm3` bits.
- OR the result with the low `imm3` bits of `op1[i]`.

## svsli[_n_s8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsli%5B_n_s8%5D

### Signature (source notation)

```c
svint8_t svsli[_n_s8](svint8_t op1, svint8_t op2, uint64_t imm3);
```

### Description

Shift left and insert

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Shift / Left / Vector shift left and insert

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
    "register": "Ztied1.B"
  },
  "op2": {
    "register": "Zop2.B"
  },
  "imm3": {
    "minimum": 0,
    "maximum": 7
  }
}
```

### Result mapping

```json
[
  {
    "Ztied1.B": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
SLI Ztied1.B, Zop2.B, #imm3
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SLI--Shift-left-and-insert--immediate--

### Operation

Source operation ID: `SveOperation_svsli_n_s8`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Shift `op2[i]` left by `imm3` bits.
- OR the result with the low `imm3` bits of `op1[i]`.

## svsli[_n_u16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsli%5B_n_u16%5D

### Signature (source notation)

```c
svuint16_t svsli[_n_u16](svuint16_t op1, svuint16_t op2, uint64_t imm3);
```

### Description

Shift left and insert

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Shift / Left / Vector shift left and insert

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
    "register": "Ztied1.H"
  },
  "op2": {
    "register": "Zop2.H"
  },
  "imm3": {
    "minimum": 0,
    "maximum": 15
  }
}
```

### Result mapping

```json
[
  {
    "Ztied1.H": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
SLI Ztied1.H, Zop2.H, #imm3
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SLI--Shift-left-and-insert--immediate--

### Operation

Source operation ID: `SveOperation_svsli_n_s8`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Shift `op2[i]` left by `imm3` bits.
- OR the result with the low `imm3` bits of `op1[i]`.

## svsli[_n_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsli%5B_n_u32%5D

### Signature (source notation)

```c
svuint32_t svsli[_n_u32](svuint32_t op1, svuint32_t op2, uint64_t imm3);
```

### Description

Shift left and insert

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Shift / Left / Vector shift left and insert

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
    "register": "Ztied1.S"
  },
  "op2": {
    "register": "Zop2.S"
  },
  "imm3": {
    "minimum": 0,
    "maximum": 31
  }
}
```

### Result mapping

```json
[
  {
    "Ztied1.S": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
SLI Ztied1.S, Zop2.S, #imm3
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SLI--Shift-left-and-insert--immediate--

### Operation

Source operation ID: `SveOperation_svsli_n_s8`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Shift `op2[i]` left by `imm3` bits.
- OR the result with the low `imm3` bits of `op1[i]`.

## svsli[_n_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsli%5B_n_u64%5D

### Signature (source notation)

```c
svuint64_t svsli[_n_u64](svuint64_t op1, svuint64_t op2, uint64_t imm3);
```

### Description

Shift left and insert

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Shift / Left / Vector shift left and insert

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
    "register": "Ztied1.D"
  },
  "op2": {
    "register": "Zop2.D"
  },
  "imm3": {
    "minimum": 0,
    "maximum": 63
  }
}
```

### Result mapping

```json
[
  {
    "Ztied1.D": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
SLI Ztied1.D, Zop2.D, #imm3
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SLI--Shift-left-and-insert--immediate--

### Operation

Source operation ID: `SveOperation_svsli_n_s8`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Shift `op2[i]` left by `imm3` bits.
- OR the result with the low `imm3` bits of `op1[i]`.

## svsli[_n_u8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsli%5B_n_u8%5D

### Signature (source notation)

```c
svuint8_t svsli[_n_u8](svuint8_t op1, svuint8_t op2, uint64_t imm3);
```

### Description

Shift left and insert

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Shift / Left / Vector shift left and insert

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
    "register": "Ztied1.B"
  },
  "op2": {
    "register": "Zop2.B"
  },
  "imm3": {
    "minimum": 0,
    "maximum": 7
  }
}
```

### Result mapping

```json
[
  {
    "Ztied1.B": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
SLI Ztied1.B, Zop2.B, #imm3
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SLI--Shift-left-and-insert--immediate--

### Operation

Source operation ID: `SveOperation_svsli_n_s8`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Shift `op2[i]` left by `imm3` bits.
- OR the result with the low `imm3` bits of `op1[i]`.

