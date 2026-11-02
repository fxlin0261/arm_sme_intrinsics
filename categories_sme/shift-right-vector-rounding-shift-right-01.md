# SME / Shift / Right / Vector rounding shift right — Part 1

## svrshr[_n_s16]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrshr%5B_n_s16%5D_m

### Signature (source notation)

```c
svint16_t svrshr[_n_s16]_m(svbool_t pg, svint16_t op1, uint64_t imm2);
```

### Description

Rounding shift right

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Shift / Right / Vector rounding shift right

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
  "pg": {
    "register": "Pg"
  },
  "op1": {
    "register": "Zop1.H|Ztied1.H"
  },
  "imm2": {
    "minimum": 1,
    "maximum": 16
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.H|Ztied1.H": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
SRSHR Ztied1.H, Pg/M, Ztied1.H, #imm2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SRSHR--Signed-rounding-shift-right-by-immediate-

When result and op1 are in different registers, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SRSHR Zresult.H, Pg/M, Zresult.H, #imm2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SRSHR--Signed-rounding-shift-right-by-immediate-

### Operation

Source operation ID: `SveOperation_svrshr_n_s8_m`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Divide `op1[i]` by 2 to the power `imm2`.
- Round the result to nearest with ties towards +∞.



Take the inactive elements of the result from the corresponding elements of `op1`.

## svrshr[_n_s16]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrshr%5B_n_s16%5D_x

### Signature (source notation)

```c
svint16_t svrshr[_n_s16]_x(svbool_t pg, svint16_t op1, uint64_t imm2);
```

### Description

Rounding shift right

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Shift / Right / Vector rounding shift right

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
  "pg": {
    "register": "Pg"
  },
  "op1": {
    "register": "Zop1.H|Ztied1.H"
  },
  "imm2": {
    "minimum": 1,
    "maximum": 16
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.H|Ztied1.H": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
SRSHR Ztied1.H, Pg/M, Ztied1.H, #imm2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SRSHR--Signed-rounding-shift-right-by-immediate-

When result and op1 are in different registers, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SRSHR Zresult.H, Pg/M, Zresult.H, #imm2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SRSHR--Signed-rounding-shift-right-by-immediate-

### Operation

Source operation ID: `SveOperation_svrshr_n_s8_x`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Divide `op1[i]` by 2 to the power `imm2`.
- Round the result to nearest with ties towards +∞.



The inactive elements of the result have arbitrary, undefined values.

## svrshr[_n_s16]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrshr%5B_n_s16%5D_z

### Signature (source notation)

```c
svint16_t svrshr[_n_s16]_z(svbool_t pg, svint16_t op1, uint64_t imm2);
```

### Description

Rounding shift right

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Shift / Right / Vector rounding shift right

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
  "pg": {
    "register": "Pg"
  },
  "op1": {
    "register": "Zop1.H"
  },
  "imm2": {
    "minimum": 1,
    "maximum": 16
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
SRSHR Zresult.H, Pg/M, Zresult.H, #imm2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SRSHR--Signed-rounding-shift-right-by-immediate-

### Operation

Source operation ID: `SveOperation_svrshr_n_s8_z`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Divide `op1[i]` by 2 to the power `imm2`.
- Round the result to nearest with ties towards +∞.



Set the inactive elements of the result to zero.

## svrshr[_n_s32]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrshr%5B_n_s32%5D_m

### Signature (source notation)

```c
svint32_t svrshr[_n_s32]_m(svbool_t pg, svint32_t op1, uint64_t imm2);
```

### Description

Rounding shift right

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Shift / Right / Vector rounding shift right

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
  "pg": {
    "register": "Pg"
  },
  "op1": {
    "register": "Zop1.S|Ztied1.S"
  },
  "imm2": {
    "minimum": 1,
    "maximum": 32
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
SRSHR Ztied1.S, Pg/M, Ztied1.S, #imm2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SRSHR--Signed-rounding-shift-right-by-immediate-

When result and op1 are in different registers, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SRSHR Zresult.S, Pg/M, Zresult.S, #imm2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SRSHR--Signed-rounding-shift-right-by-immediate-

### Operation

Source operation ID: `SveOperation_svrshr_n_s8_m`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Divide `op1[i]` by 2 to the power `imm2`.
- Round the result to nearest with ties towards +∞.



Take the inactive elements of the result from the corresponding elements of `op1`.

## svrshr[_n_s32]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrshr%5B_n_s32%5D_x

### Signature (source notation)

```c
svint32_t svrshr[_n_s32]_x(svbool_t pg, svint32_t op1, uint64_t imm2);
```

### Description

Rounding shift right

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Shift / Right / Vector rounding shift right

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
  "pg": {
    "register": "Pg"
  },
  "op1": {
    "register": "Zop1.S|Ztied1.S"
  },
  "imm2": {
    "minimum": 1,
    "maximum": 32
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
SRSHR Ztied1.S, Pg/M, Ztied1.S, #imm2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SRSHR--Signed-rounding-shift-right-by-immediate-

When result and op1 are in different registers, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SRSHR Zresult.S, Pg/M, Zresult.S, #imm2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SRSHR--Signed-rounding-shift-right-by-immediate-

### Operation

Source operation ID: `SveOperation_svrshr_n_s8_x`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Divide `op1[i]` by 2 to the power `imm2`.
- Round the result to nearest with ties towards +∞.



The inactive elements of the result have arbitrary, undefined values.

## svrshr[_n_s32]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrshr%5B_n_s32%5D_z

### Signature (source notation)

```c
svint32_t svrshr[_n_s32]_z(svbool_t pg, svint32_t op1, uint64_t imm2);
```

### Description

Rounding shift right

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Shift / Right / Vector rounding shift right

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
  "pg": {
    "register": "Pg"
  },
  "op1": {
    "register": "Zop1.S"
  },
  "imm2": {
    "minimum": 1,
    "maximum": 32
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
SRSHR Zresult.S, Pg/M, Zresult.S, #imm2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SRSHR--Signed-rounding-shift-right-by-immediate-

### Operation

Source operation ID: `SveOperation_svrshr_n_s8_z`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Divide `op1[i]` by 2 to the power `imm2`.
- Round the result to nearest with ties towards +∞.



Set the inactive elements of the result to zero.

## svrshr[_n_s64]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrshr%5B_n_s64%5D_m

### Signature (source notation)

```c
svint64_t svrshr[_n_s64]_m(svbool_t pg, svint64_t op1, uint64_t imm2);
```

### Description

Rounding shift right

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Shift / Right / Vector rounding shift right

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
  "pg": {
    "register": "Pg"
  },
  "op1": {
    "register": "Zop1.D|Ztied1.D"
  },
  "imm2": {
    "minimum": 1,
    "maximum": 64
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
SRSHR Ztied1.D, Pg/M, Ztied1.D, #imm2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SRSHR--Signed-rounding-shift-right-by-immediate-

When result and op1 are in different registers, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SRSHR Zresult.D, Pg/M, Zresult.D, #imm2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SRSHR--Signed-rounding-shift-right-by-immediate-

### Operation

Source operation ID: `SveOperation_svrshr_n_s8_m`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Divide `op1[i]` by 2 to the power `imm2`.
- Round the result to nearest with ties towards +∞.



Take the inactive elements of the result from the corresponding elements of `op1`.

## svrshr[_n_s64]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrshr%5B_n_s64%5D_x

### Signature (source notation)

```c
svint64_t svrshr[_n_s64]_x(svbool_t pg, svint64_t op1, uint64_t imm2);
```

### Description

Rounding shift right

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Shift / Right / Vector rounding shift right

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
  "pg": {
    "register": "Pg"
  },
  "op1": {
    "register": "Zop1.D|Ztied1.D"
  },
  "imm2": {
    "minimum": 1,
    "maximum": 64
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
SRSHR Ztied1.D, Pg/M, Ztied1.D, #imm2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SRSHR--Signed-rounding-shift-right-by-immediate-

When result and op1 are in different registers, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SRSHR Zresult.D, Pg/M, Zresult.D, #imm2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SRSHR--Signed-rounding-shift-right-by-immediate-

### Operation

Source operation ID: `SveOperation_svrshr_n_s8_x`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Divide `op1[i]` by 2 to the power `imm2`.
- Round the result to nearest with ties towards +∞.



The inactive elements of the result have arbitrary, undefined values.

## svrshr[_n_s64]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrshr%5B_n_s64%5D_z

### Signature (source notation)

```c
svint64_t svrshr[_n_s64]_z(svbool_t pg, svint64_t op1, uint64_t imm2);
```

### Description

Rounding shift right

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Shift / Right / Vector rounding shift right

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
  "pg": {
    "register": "Pg"
  },
  "op1": {
    "register": "Zop1.D"
  },
  "imm2": {
    "minimum": 1,
    "maximum": 64
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
SRSHR Zresult.D, Pg/M, Zresult.D, #imm2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SRSHR--Signed-rounding-shift-right-by-immediate-

### Operation

Source operation ID: `SveOperation_svrshr_n_s8_z`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Divide `op1[i]` by 2 to the power `imm2`.
- Round the result to nearest with ties towards +∞.



Set the inactive elements of the result to zero.

## svrshr[_n_s8]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrshr%5B_n_s8%5D_m

### Signature (source notation)

```c
svint8_t svrshr[_n_s8]_m(svbool_t pg, svint8_t op1, uint64_t imm2);
```

### Description

Rounding shift right

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Shift / Right / Vector rounding shift right

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
  "pg": {
    "register": "Pg"
  },
  "op1": {
    "register": "Zop1.B|Ztied1.B"
  },
  "imm2": {
    "minimum": 1,
    "maximum": 8
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
SRSHR Ztied1.B, Pg/M, Ztied1.B, #imm2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SRSHR--Signed-rounding-shift-right-by-immediate-

When result and op1 are in different registers, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SRSHR Zresult.B, Pg/M, Zresult.B, #imm2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SRSHR--Signed-rounding-shift-right-by-immediate-

### Operation

Source operation ID: `SveOperation_svrshr_n_s8_m`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Divide `op1[i]` by 2 to the power `imm2`.
- Round the result to nearest with ties towards +∞.



Take the inactive elements of the result from the corresponding elements of `op1`.

## svrshr[_n_s8]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrshr%5B_n_s8%5D_x

### Signature (source notation)

```c
svint8_t svrshr[_n_s8]_x(svbool_t pg, svint8_t op1, uint64_t imm2);
```

### Description

Rounding shift right

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Shift / Right / Vector rounding shift right

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
  "pg": {
    "register": "Pg"
  },
  "op1": {
    "register": "Zop1.B|Ztied1.B"
  },
  "imm2": {
    "minimum": 1,
    "maximum": 8
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
SRSHR Ztied1.B, Pg/M, Ztied1.B, #imm2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SRSHR--Signed-rounding-shift-right-by-immediate-

When result and op1 are in different registers, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SRSHR Zresult.B, Pg/M, Zresult.B, #imm2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SRSHR--Signed-rounding-shift-right-by-immediate-

### Operation

Source operation ID: `SveOperation_svrshr_n_s8_x`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Divide `op1[i]` by 2 to the power `imm2`.
- Round the result to nearest with ties towards +∞.



The inactive elements of the result have arbitrary, undefined values.

## svrshr[_n_s8]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrshr%5B_n_s8%5D_z

### Signature (source notation)

```c
svint8_t svrshr[_n_s8]_z(svbool_t pg, svint8_t op1, uint64_t imm2);
```

### Description

Rounding shift right

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Shift / Right / Vector rounding shift right

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
  "pg": {
    "register": "Pg"
  },
  "op1": {
    "register": "Zop1.B"
  },
  "imm2": {
    "minimum": 1,
    "maximum": 8
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
SRSHR Zresult.B, Pg/M, Zresult.B, #imm2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SRSHR--Signed-rounding-shift-right-by-immediate-

### Operation

Source operation ID: `SveOperation_svrshr_n_s8_z`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Divide `op1[i]` by 2 to the power `imm2`.
- Round the result to nearest with ties towards +∞.



Set the inactive elements of the result to zero.

## svrshr[_n_u16]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrshr%5B_n_u16%5D_m

### Signature (source notation)

```c
svuint16_t svrshr[_n_u16]_m(svbool_t pg, svuint16_t op1, uint64_t imm2);
```

### Description

Rounding shift right

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Shift / Right / Vector rounding shift right

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
    "register": "Zop1.H|Ztied1.H"
  },
  "imm2": {
    "minimum": 1,
    "maximum": 16
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.H|Ztied1.H": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
URSHR Ztied1.H, Pg/M, Ztied1.H, #imm2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/URSHR--Unsigned-rounding-shift-right-by-immediate-

When result and op1 are in different registers, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
URSHR Zresult.H, Pg/M, Zresult.H, #imm2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/URSHR--Unsigned-rounding-shift-right-by-immediate-

### Operation

Source operation ID: `SveOperation_svrshr_n_s8_m`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Divide `op1[i]` by 2 to the power `imm2`.
- Round the result to nearest with ties towards +∞.



Take the inactive elements of the result from the corresponding elements of `op1`.

## svrshr[_n_u16]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrshr%5B_n_u16%5D_x

### Signature (source notation)

```c
svuint16_t svrshr[_n_u16]_x(svbool_t pg, svuint16_t op1, uint64_t imm2);
```

### Description

Rounding shift right

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Shift / Right / Vector rounding shift right

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
    "register": "Zop1.H|Ztied1.H"
  },
  "imm2": {
    "minimum": 1,
    "maximum": 16
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.H|Ztied1.H": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
URSHR Ztied1.H, Pg/M, Ztied1.H, #imm2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/URSHR--Unsigned-rounding-shift-right-by-immediate-

When result and op1 are in different registers, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
URSHR Zresult.H, Pg/M, Zresult.H, #imm2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/URSHR--Unsigned-rounding-shift-right-by-immediate-

### Operation

Source operation ID: `SveOperation_svrshr_n_s8_x`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Divide `op1[i]` by 2 to the power `imm2`.
- Round the result to nearest with ties towards +∞.



The inactive elements of the result have arbitrary, undefined values.

## svrshr[_n_u16]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrshr%5B_n_u16%5D_z

### Signature (source notation)

```c
svuint16_t svrshr[_n_u16]_z(svbool_t pg, svuint16_t op1, uint64_t imm2);
```

### Description

Rounding shift right

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Shift / Right / Vector rounding shift right

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
    "minimum": 1,
    "maximum": 16
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
URSHR Zresult.H, Pg/M, Zresult.H, #imm2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/URSHR--Unsigned-rounding-shift-right-by-immediate-

### Operation

Source operation ID: `SveOperation_svrshr_n_s8_z`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Divide `op1[i]` by 2 to the power `imm2`.
- Round the result to nearest with ties towards +∞.



Set the inactive elements of the result to zero.

## svrshr[_n_u32]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrshr%5B_n_u32%5D_m

### Signature (source notation)

```c
svuint32_t svrshr[_n_u32]_m(svbool_t pg, svuint32_t op1, uint64_t imm2);
```

### Description

Rounding shift right

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Shift / Right / Vector rounding shift right

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
    "minimum": 1,
    "maximum": 32
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
URSHR Ztied1.S, Pg/M, Ztied1.S, #imm2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/URSHR--Unsigned-rounding-shift-right-by-immediate-

When result and op1 are in different registers, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
URSHR Zresult.S, Pg/M, Zresult.S, #imm2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/URSHR--Unsigned-rounding-shift-right-by-immediate-

### Operation

Source operation ID: `SveOperation_svrshr_n_s8_m`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Divide `op1[i]` by 2 to the power `imm2`.
- Round the result to nearest with ties towards +∞.



Take the inactive elements of the result from the corresponding elements of `op1`.

## svrshr[_n_u32]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrshr%5B_n_u32%5D_x

### Signature (source notation)

```c
svuint32_t svrshr[_n_u32]_x(svbool_t pg, svuint32_t op1, uint64_t imm2);
```

### Description

Rounding shift right

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Shift / Right / Vector rounding shift right

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
    "minimum": 1,
    "maximum": 32
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
URSHR Ztied1.S, Pg/M, Ztied1.S, #imm2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/URSHR--Unsigned-rounding-shift-right-by-immediate-

When result and op1 are in different registers, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
URSHR Zresult.S, Pg/M, Zresult.S, #imm2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/URSHR--Unsigned-rounding-shift-right-by-immediate-

### Operation

Source operation ID: `SveOperation_svrshr_n_s8_x`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Divide `op1[i]` by 2 to the power `imm2`.
- Round the result to nearest with ties towards +∞.



The inactive elements of the result have arbitrary, undefined values.

## svrshr[_n_u32]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrshr%5B_n_u32%5D_z

### Signature (source notation)

```c
svuint32_t svrshr[_n_u32]_z(svbool_t pg, svuint32_t op1, uint64_t imm2);
```

### Description

Rounding shift right

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Shift / Right / Vector rounding shift right

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
    "minimum": 1,
    "maximum": 32
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
URSHR Zresult.S, Pg/M, Zresult.S, #imm2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/URSHR--Unsigned-rounding-shift-right-by-immediate-

### Operation

Source operation ID: `SveOperation_svrshr_n_s8_z`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Divide `op1[i]` by 2 to the power `imm2`.
- Round the result to nearest with ties towards +∞.



Set the inactive elements of the result to zero.

## svrshr[_n_u64]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrshr%5B_n_u64%5D_m

### Signature (source notation)

```c
svuint64_t svrshr[_n_u64]_m(svbool_t pg, svuint64_t op1, uint64_t imm2);
```

### Description

Rounding shift right

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Shift / Right / Vector rounding shift right

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
    "minimum": 1,
    "maximum": 64
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
URSHR Ztied1.D, Pg/M, Ztied1.D, #imm2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/URSHR--Unsigned-rounding-shift-right-by-immediate-

When result and op1 are in different registers, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
URSHR Zresult.D, Pg/M, Zresult.D, #imm2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/URSHR--Unsigned-rounding-shift-right-by-immediate-

### Operation

Source operation ID: `SveOperation_svrshr_n_s8_m`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Divide `op1[i]` by 2 to the power `imm2`.
- Round the result to nearest with ties towards +∞.



Take the inactive elements of the result from the corresponding elements of `op1`.

## svrshr[_n_u64]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrshr%5B_n_u64%5D_x

### Signature (source notation)

```c
svuint64_t svrshr[_n_u64]_x(svbool_t pg, svuint64_t op1, uint64_t imm2);
```

### Description

Rounding shift right

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Shift / Right / Vector rounding shift right

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
    "minimum": 1,
    "maximum": 64
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
URSHR Ztied1.D, Pg/M, Ztied1.D, #imm2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/URSHR--Unsigned-rounding-shift-right-by-immediate-

When result and op1 are in different registers, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
URSHR Zresult.D, Pg/M, Zresult.D, #imm2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/URSHR--Unsigned-rounding-shift-right-by-immediate-

### Operation

Source operation ID: `SveOperation_svrshr_n_s8_x`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Divide `op1[i]` by 2 to the power `imm2`.
- Round the result to nearest with ties towards +∞.



The inactive elements of the result have arbitrary, undefined values.

## svrshr[_n_u64]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrshr%5B_n_u64%5D_z

### Signature (source notation)

```c
svuint64_t svrshr[_n_u64]_z(svbool_t pg, svuint64_t op1, uint64_t imm2);
```

### Description

Rounding shift right

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Shift / Right / Vector rounding shift right

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
    "minimum": 1,
    "maximum": 64
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
URSHR Zresult.D, Pg/M, Zresult.D, #imm2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/URSHR--Unsigned-rounding-shift-right-by-immediate-

### Operation

Source operation ID: `SveOperation_svrshr_n_s8_z`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Divide `op1[i]` by 2 to the power `imm2`.
- Round the result to nearest with ties towards +∞.



Set the inactive elements of the result to zero.

## svrshr[_n_u8]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrshr%5B_n_u8%5D_m

### Signature (source notation)

```c
svuint8_t svrshr[_n_u8]_m(svbool_t pg, svuint8_t op1, uint64_t imm2);
```

### Description

Rounding shift right

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Shift / Right / Vector rounding shift right

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
    "minimum": 1,
    "maximum": 8
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
URSHR Ztied1.B, Pg/M, Ztied1.B, #imm2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/URSHR--Unsigned-rounding-shift-right-by-immediate-

When result and op1 are in different registers, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
URSHR Zresult.B, Pg/M, Zresult.B, #imm2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/URSHR--Unsigned-rounding-shift-right-by-immediate-

### Operation

Source operation ID: `SveOperation_svrshr_n_s8_m`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Divide `op1[i]` by 2 to the power `imm2`.
- Round the result to nearest with ties towards +∞.



Take the inactive elements of the result from the corresponding elements of `op1`.

## svrshr[_n_u8]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrshr%5B_n_u8%5D_x

### Signature (source notation)

```c
svuint8_t svrshr[_n_u8]_x(svbool_t pg, svuint8_t op1, uint64_t imm2);
```

### Description

Rounding shift right

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Shift / Right / Vector rounding shift right

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
    "minimum": 1,
    "maximum": 8
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
URSHR Ztied1.B, Pg/M, Ztied1.B, #imm2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/URSHR--Unsigned-rounding-shift-right-by-immediate-

When result and op1 are in different registers, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
URSHR Zresult.B, Pg/M, Zresult.B, #imm2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/URSHR--Unsigned-rounding-shift-right-by-immediate-

### Operation

Source operation ID: `SveOperation_svrshr_n_s8_x`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Divide `op1[i]` by 2 to the power `imm2`.
- Round the result to nearest with ties towards +∞.



The inactive elements of the result have arbitrary, undefined values.

## svrshr[_n_u8]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrshr%5B_n_u8%5D_z

### Signature (source notation)

```c
svuint8_t svrshr[_n_u8]_z(svbool_t pg, svuint8_t op1, uint64_t imm2);
```

### Description

Rounding shift right

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Shift / Right / Vector rounding shift right

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
    "minimum": 1,
    "maximum": 8
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
URSHR Zresult.B, Pg/M, Zresult.B, #imm2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/URSHR--Unsigned-rounding-shift-right-by-immediate-

### Operation

Source operation ID: `SveOperation_svrshr_n_s8_z`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Divide `op1[i]` by 2 to the power `imm2`.
- Round the result to nearest with ties towards +∞.



Set the inactive elements of the result to zero.

