# SME / Shift / Left / Vector saturating shift left — Part 2

## svqshlu[_n_s16]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqshlu%5B_n_s16%5D_z

### Signature (source notation)

```c
svuint16_t svqshlu[_n_s16]_z(svbool_t pg, svint16_t op1, uint64_t imm2);
```

### Description

Saturating shift left unsigned

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Shift / Left / Vector saturating shift left

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
  "pg": {
    "register": "Pg"
  },
  "op1": {
    "register": "Zop1.H"
  },
  "imm2": {
    "minimum": 0,
    "maximum": 15
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.H": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instructions, or functionally equivalent instructions:

```asm
MOVPRFX Zresult.H, Pg/Z, Zop1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
SQSHLU Zresult.H, Pg/M, Zresult.H, #imm2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQSHLU--Signed-saturating-shift-left-unsigned-by-immediate-

### Operation

Source operation ID: `SveOperation_svqshlu_n_s16_z`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Multiply `op1[i]` by 2 to the power `imm2`, without loss of precision.
- Round the result towards -∞.
- Saturate the result to the range of `uint16_t`.



Set the inactive elements of the result to zero.

## svqshlu[_n_s32]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqshlu%5B_n_s32%5D_m

### Signature (source notation)

```c
svuint32_t svqshlu[_n_s32]_m(svbool_t pg, svint32_t op1, uint64_t imm2);
```

### Description

Saturating shift left unsigned

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Shift / Left / Vector saturating shift left

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
  "pg": {
    "register": "Pg"
  },
  "op1": {
    "register": "Zop1.S|Ztied1.S"
  },
  "imm2": {
    "minimum": 0,
    "maximum": 31
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.S|Ztied1.S": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
SQSHLU Ztied1.S, Pg/M, Ztied1.S, #imm2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQSHLU--Signed-saturating-shift-left-unsigned-by-immediate-

When result and op1 are in different registers, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SQSHLU Zresult.S, Pg/M, Zresult.S, #imm2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQSHLU--Signed-saturating-shift-left-unsigned-by-immediate-

### Operation

Source operation ID: `SveOperation_svqshlu_n_s32_m`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Multiply `op1[i]` by 2 to the power `imm2`, without loss of precision.
- Round the result towards -∞.
- Saturate the result to the range of `uint32_t`.



Take the inactive elements of the result from the corresponding elements of `op1`.

## svqshlu[_n_s32]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqshlu%5B_n_s32%5D_x

### Signature (source notation)

```c
svuint32_t svqshlu[_n_s32]_x(svbool_t pg, svint32_t op1, uint64_t imm2);
```

### Description

Saturating shift left unsigned

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Shift / Left / Vector saturating shift left

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
  "pg": {
    "register": "Pg"
  },
  "op1": {
    "register": "Zop1.S|Ztied1.S"
  },
  "imm2": {
    "minimum": 0,
    "maximum": 31
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.S|Ztied1.S": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
SQSHLU Ztied1.S, Pg/M, Ztied1.S, #imm2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQSHLU--Signed-saturating-shift-left-unsigned-by-immediate-

When result and op1 are in different registers, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SQSHLU Zresult.S, Pg/M, Zresult.S, #imm2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQSHLU--Signed-saturating-shift-left-unsigned-by-immediate-

### Operation

Source operation ID: `SveOperation_svqshlu_n_s32_x`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Multiply `op1[i]` by 2 to the power `imm2`, without loss of precision.
- Round the result towards -∞.
- Saturate the result to the range of `uint32_t`.



The inactive elements of the result have arbitrary, undefined values.

## svqshlu[_n_s32]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqshlu%5B_n_s32%5D_z

### Signature (source notation)

```c
svuint32_t svqshlu[_n_s32]_z(svbool_t pg, svint32_t op1, uint64_t imm2);
```

### Description

Saturating shift left unsigned

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Shift / Left / Vector saturating shift left

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
  "pg": {
    "register": "Pg"
  },
  "op1": {
    "register": "Zop1.S"
  },
  "imm2": {
    "minimum": 0,
    "maximum": 31
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.S": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instructions, or functionally equivalent instructions:

```asm
MOVPRFX Zresult.S, Pg/Z, Zop1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
SQSHLU Zresult.S, Pg/M, Zresult.S, #imm2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQSHLU--Signed-saturating-shift-left-unsigned-by-immediate-

### Operation

Source operation ID: `SveOperation_svqshlu_n_s32_z`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Multiply `op1[i]` by 2 to the power `imm2`, without loss of precision.
- Round the result towards -∞.
- Saturate the result to the range of `uint32_t`.



Set the inactive elements of the result to zero.

## svqshlu[_n_s64]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqshlu%5B_n_s64%5D_m

### Signature (source notation)

```c
svuint64_t svqshlu[_n_s64]_m(svbool_t pg, svint64_t op1, uint64_t imm2);
```

### Description

Saturating shift left unsigned

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Shift / Left / Vector saturating shift left

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
  "pg": {
    "register": "Pg"
  },
  "op1": {
    "register": "Zop1.D|Ztied1.D"
  },
  "imm2": {
    "minimum": 0,
    "maximum": 63
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.D|Ztied1.D": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
SQSHLU Ztied1.D, Pg/M, Ztied1.D, #imm2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQSHLU--Signed-saturating-shift-left-unsigned-by-immediate-

When result and op1 are in different registers, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SQSHLU Zresult.D, Pg/M, Zresult.D, #imm2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQSHLU--Signed-saturating-shift-left-unsigned-by-immediate-

### Operation

Source operation ID: `SveOperation_svqshlu_n_s64_m`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Multiply `op1[i]` by 2 to the power `imm2`, without loss of precision.
- Round the result towards -∞.
- Saturate the result to the range of `uint64_t`.



Take the inactive elements of the result from the corresponding elements of `op1`.

## svqshlu[_n_s64]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqshlu%5B_n_s64%5D_x

### Signature (source notation)

```c
svuint64_t svqshlu[_n_s64]_x(svbool_t pg, svint64_t op1, uint64_t imm2);
```

### Description

Saturating shift left unsigned

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Shift / Left / Vector saturating shift left

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
  "pg": {
    "register": "Pg"
  },
  "op1": {
    "register": "Zop1.D|Ztied1.D"
  },
  "imm2": {
    "minimum": 0,
    "maximum": 63
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.D|Ztied1.D": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
SQSHLU Ztied1.D, Pg/M, Ztied1.D, #imm2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQSHLU--Signed-saturating-shift-left-unsigned-by-immediate-

When result and op1 are in different registers, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SQSHLU Zresult.D, Pg/M, Zresult.D, #imm2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQSHLU--Signed-saturating-shift-left-unsigned-by-immediate-

### Operation

Source operation ID: `SveOperation_svqshlu_n_s64_x`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Multiply `op1[i]` by 2 to the power `imm2`, without loss of precision.
- Round the result towards -∞.
- Saturate the result to the range of `uint64_t`.



The inactive elements of the result have arbitrary, undefined values.

## svqshlu[_n_s64]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqshlu%5B_n_s64%5D_z

### Signature (source notation)

```c
svuint64_t svqshlu[_n_s64]_z(svbool_t pg, svint64_t op1, uint64_t imm2);
```

### Description

Saturating shift left unsigned

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Shift / Left / Vector saturating shift left

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
  "pg": {
    "register": "Pg"
  },
  "op1": {
    "register": "Zop1.D"
  },
  "imm2": {
    "minimum": 0,
    "maximum": 63
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.D": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instructions, or functionally equivalent instructions:

```asm
MOVPRFX Zresult.D, Pg/Z, Zop1.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
SQSHLU Zresult.D, Pg/M, Zresult.D, #imm2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQSHLU--Signed-saturating-shift-left-unsigned-by-immediate-

### Operation

Source operation ID: `SveOperation_svqshlu_n_s64_z`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Multiply `op1[i]` by 2 to the power `imm2`, without loss of precision.
- Round the result towards -∞.
- Saturate the result to the range of `uint64_t`.



Set the inactive elements of the result to zero.

## svqshlu[_n_s8]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqshlu%5B_n_s8%5D_m

### Signature (source notation)

```c
svuint8_t svqshlu[_n_s8]_m(svbool_t pg, svint8_t op1, uint64_t imm2);
```

### Description

Saturating shift left unsigned

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Shift / Left / Vector saturating shift left

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
  "pg": {
    "register": "Pg"
  },
  "op1": {
    "register": "Zop1.B|Ztied1.B"
  },
  "imm2": {
    "minimum": 0,
    "maximum": 7
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.B|Ztied1.B": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
SQSHLU Ztied1.B, Pg/M, Ztied1.B, #imm2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQSHLU--Signed-saturating-shift-left-unsigned-by-immediate-

When result and op1 are in different registers, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SQSHLU Zresult.B, Pg/M, Zresult.B, #imm2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQSHLU--Signed-saturating-shift-left-unsigned-by-immediate-

### Operation

Source operation ID: `SveOperation_svqshlu_n_s8_m`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Multiply `op1[i]` by 2 to the power `imm2`, without loss of precision.
- Round the result towards -∞.
- Saturate the result to the range of `uint8_t`.



Take the inactive elements of the result from the corresponding elements of `op1`.

## svqshlu[_n_s8]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqshlu%5B_n_s8%5D_x

### Signature (source notation)

```c
svuint8_t svqshlu[_n_s8]_x(svbool_t pg, svint8_t op1, uint64_t imm2);
```

### Description

Saturating shift left unsigned

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Shift / Left / Vector saturating shift left

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
  "pg": {
    "register": "Pg"
  },
  "op1": {
    "register": "Zop1.B|Ztied1.B"
  },
  "imm2": {
    "minimum": 0,
    "maximum": 7
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.B|Ztied1.B": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
SQSHLU Ztied1.B, Pg/M, Ztied1.B, #imm2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQSHLU--Signed-saturating-shift-left-unsigned-by-immediate-

When result and op1 are in different registers, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SQSHLU Zresult.B, Pg/M, Zresult.B, #imm2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQSHLU--Signed-saturating-shift-left-unsigned-by-immediate-

### Operation

Source operation ID: `SveOperation_svqshlu_n_s8_x`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Multiply `op1[i]` by 2 to the power `imm2`, without loss of precision.
- Round the result towards -∞.
- Saturate the result to the range of `uint8_t`.



The inactive elements of the result have arbitrary, undefined values.

## svqshlu[_n_s8]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqshlu%5B_n_s8%5D_z

### Signature (source notation)

```c
svuint8_t svqshlu[_n_s8]_z(svbool_t pg, svint8_t op1, uint64_t imm2);
```

### Description

Saturating shift left unsigned

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Shift / Left / Vector saturating shift left

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
  "pg": {
    "register": "Pg"
  },
  "op1": {
    "register": "Zop1.B"
  },
  "imm2": {
    "minimum": 0,
    "maximum": 7
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.B": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instructions, or functionally equivalent instructions:

```asm
MOVPRFX Zresult.B, Pg/Z, Zop1.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
SQSHLU Zresult.B, Pg/M, Zresult.B, #imm2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQSHLU--Signed-saturating-shift-left-unsigned-by-immediate-

### Operation

Source operation ID: `SveOperation_svqshlu_n_s8_z`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Multiply `op1[i]` by 2 to the power `imm2`, without loss of precision.
- Round the result towards -∞.
- Saturate the result to the range of `uint8_t`.



Set the inactive elements of the result to zero.

