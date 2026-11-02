# SME / Shift / Left / Vector rounding shift left — Part 1

## svrshl[_n_s16]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrshl%5B_n_s16%5D_m

### Signature (source notation)

```c
svint16_t svrshl[_n_s16]_m(svbool_t pg, svint16_t op1, int16_t op2);
```

### Description

Rounding shift left

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Shift / Left / Vector rounding shift left

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
    "register": "Ztied1.H"
  },
  "op2": {
    "register": "Zop2.H[*]"
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

When op2 is in the range [0, 15], this intrinsic can use:

```asm
LSL Ztied1.H, Pg/M, Ztied1.H, #op2  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSL--immediate--predicated---Logical-shift-left-by-immediate--predicated--

When op2 is in the range [-16, -1], this intrinsic can use:

```asm
SRSHR Ztied1.H, Pg/M, Ztied1.H, #-op2  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SRSHR--Signed-rounding-shift-right-by-immediate-

The general implementation is:

```asm
SRSHL Ztied1.H, Pg/M, Ztied1.H, Zop2.H  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SRSHL--Signed-rounding-shift-left--predicated--

### Operation

Source operation ID: `SveOperation_svrshl_n_s16_m`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Multiply `op1[i]` by 2 to the power `op2`, without loss of precision.
- Round the result to nearest with ties towards +∞.
- Truncate the result to the range of `int16_t`.



Take the inactive elements of the result from the corresponding elements of `op1`.



**[1]** If instead `result` is in a different register from the inputs, the compiler can add a preceding [MOVPRFX (unpredicated)](https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--) instruction

## svrshl[_n_s16]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrshl%5B_n_s16%5D_x

### Signature (source notation)

```c
svint16_t svrshl[_n_s16]_x(svbool_t pg, svint16_t op1, int16_t op2);
```

### Description

Rounding shift left

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Shift / Left / Vector rounding shift left

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
  "op2": {
    "register": "Zop2.H[*]|Ztied2.H[*]"
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

When op2 is in the range [0, 15], this intrinsic can use:

```asm
LSL Zresult.H, Zop1.H, #op2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSL--immediate--unpredicated---Logical-shift-left-by-immediate--unpredicated--

When op2 is in the range [-16, -1], this intrinsic can use:

```asm
SRSHR Ztied1.H, Pg/M, Ztied1.H, #-op2  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SRSHR--Signed-rounding-shift-right-by-immediate-

When result and op1 are in the same register, this intrinsic can use:

```asm
SRSHL Ztied1.H, Pg/M, Ztied1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SRSHL--Signed-rounding-shift-left--predicated--

When result and op2 are in the same register, this intrinsic can use:

```asm
SRSHLR Ztied2.H, Pg/M, Ztied2.H, Zop1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SRSHLR--Signed-rounding-shift-left-reversed--predicated--

When result is in a different register from the inputs, the general implementation is:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SRSHL Zresult.H, Pg/M, Zresult.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SRSHL--Signed-rounding-shift-left--predicated--

### Operation

Source operation ID: `SveOperation_svrshl_n_s16_x`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Multiply `op1[i]` by 2 to the power `op2`, without loss of precision.
- Round the result to nearest with ties towards +∞.
- Truncate the result to the range of `int16_t`.



The inactive elements of the result have arbitrary, undefined values.



**[1]** If instead `result` is in a different register from the inputs, the compiler can add a preceding [MOVPRFX (unpredicated)](https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--) instruction

## svrshl[_n_s16]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrshl%5B_n_s16%5D_z

### Signature (source notation)

```c
svint16_t svrshl[_n_s16]_z(svbool_t pg, svint16_t op1, int16_t op2);
```

### Description

Rounding shift left

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Shift / Left / Vector rounding shift left

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
  "op2": {
    "register": "Zop2.H[*]"
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

When op2 is in the range [0, 15], this intrinsic can use:

```asm
MOVPRFX Zresult.H, Pg/Z, Zop1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
LSL Zresult.H, Pg/M, Zresult.H, #op2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSL--immediate--predicated---Logical-shift-left-by-immediate--predicated--

When op2 is in the range [-16, -1], this intrinsic can use:

```asm
MOVPRFX Zresult.H, Pg/Z, Zop1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
SRSHR Zresult.H, Pg/M, Zresult.H, #-op2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SRSHR--Signed-rounding-shift-right-by-immediate-

When result is in a different register from op2, this intrinsic can use:

```asm
MOVPRFX Zresult.H, Pg/Z, Zop1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
SRSHL Zresult.H, Pg/M, Zresult.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SRSHL--Signed-rounding-shift-left--predicated--

When result is in a different register from op1, this intrinsic can use:

```asm
MOVPRFX Zresult.H, Pg/Z, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
SRSHLR Zresult.H, Pg/M, Zresult.H, Zop1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SRSHLR--Signed-rounding-shift-left-reversed--predicated--

### Operation

Source operation ID: `SveOperation_svrshl_n_s16_z`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Multiply `op1[i]` by 2 to the power `op2`, without loss of precision.
- Round the result to nearest with ties towards +∞.
- Truncate the result to the range of `int16_t`.



Set the inactive elements of the result to zero.

## svrshl[_n_s32]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrshl%5B_n_s32%5D_m

### Signature (source notation)

```c
svint32_t svrshl[_n_s32]_m(svbool_t pg, svint32_t op1, int32_t op2);
```

### Description

Rounding shift left

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Shift / Left / Vector rounding shift left

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
    "register": "Ztied1.S"
  },
  "op2": {
    "register": "Zop2.S[*]"
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

When op2 is in the range [0, 31], this intrinsic can use:

```asm
LSL Ztied1.S, Pg/M, Ztied1.S, #op2  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSL--immediate--predicated---Logical-shift-left-by-immediate--predicated--

When op2 is in the range [-32, -1], this intrinsic can use:

```asm
SRSHR Ztied1.S, Pg/M, Ztied1.S, #-op2  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SRSHR--Signed-rounding-shift-right-by-immediate-

The general implementation is:

```asm
SRSHL Ztied1.S, Pg/M, Ztied1.S, Zop2.S  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SRSHL--Signed-rounding-shift-left--predicated--

### Operation

Source operation ID: `SveOperation_svrshl_n_s32_m`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Multiply `op1[i]` by 2 to the power `op2`, without loss of precision.
- Round the result to nearest with ties towards +∞.
- Truncate the result to the range of `int32_t`.



Take the inactive elements of the result from the corresponding elements of `op1`.



**[1]** If instead `result` is in a different register from the inputs, the compiler can add a preceding [MOVPRFX (unpredicated)](https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--) instruction

## svrshl[_n_s32]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrshl%5B_n_s32%5D_x

### Signature (source notation)

```c
svint32_t svrshl[_n_s32]_x(svbool_t pg, svint32_t op1, int32_t op2);
```

### Description

Rounding shift left

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Shift / Left / Vector rounding shift left

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
  "op2": {
    "register": "Zop2.S[*]|Ztied2.S[*]"
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

When op2 is in the range [0, 31], this intrinsic can use:

```asm
LSL Zresult.S, Zop1.S, #op2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSL--immediate--unpredicated---Logical-shift-left-by-immediate--unpredicated--

When op2 is in the range [-32, -1], this intrinsic can use:

```asm
SRSHR Ztied1.S, Pg/M, Ztied1.S, #-op2  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SRSHR--Signed-rounding-shift-right-by-immediate-

When result and op1 are in the same register, this intrinsic can use:

```asm
SRSHL Ztied1.S, Pg/M, Ztied1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SRSHL--Signed-rounding-shift-left--predicated--

When result and op2 are in the same register, this intrinsic can use:

```asm
SRSHLR Ztied2.S, Pg/M, Ztied2.S, Zop1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SRSHLR--Signed-rounding-shift-left-reversed--predicated--

When result is in a different register from the inputs, the general implementation is:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SRSHL Zresult.S, Pg/M, Zresult.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SRSHL--Signed-rounding-shift-left--predicated--

### Operation

Source operation ID: `SveOperation_svrshl_n_s32_x`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Multiply `op1[i]` by 2 to the power `op2`, without loss of precision.
- Round the result to nearest with ties towards +∞.
- Truncate the result to the range of `int32_t`.



The inactive elements of the result have arbitrary, undefined values.



**[1]** If instead `result` is in a different register from the inputs, the compiler can add a preceding [MOVPRFX (unpredicated)](https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--) instruction

## svrshl[_n_s32]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrshl%5B_n_s32%5D_z

### Signature (source notation)

```c
svint32_t svrshl[_n_s32]_z(svbool_t pg, svint32_t op1, int32_t op2);
```

### Description

Rounding shift left

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Shift / Left / Vector rounding shift left

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
  "op2": {
    "register": "Zop2.S[*]"
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

When op2 is in the range [0, 31], this intrinsic can use:

```asm
MOVPRFX Zresult.S, Pg/Z, Zop1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
LSL Zresult.S, Pg/M, Zresult.S, #op2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSL--immediate--predicated---Logical-shift-left-by-immediate--predicated--

When op2 is in the range [-32, -1], this intrinsic can use:

```asm
MOVPRFX Zresult.S, Pg/Z, Zop1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
SRSHR Zresult.S, Pg/M, Zresult.S, #-op2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SRSHR--Signed-rounding-shift-right-by-immediate-

When result is in a different register from op2, this intrinsic can use:

```asm
MOVPRFX Zresult.S, Pg/Z, Zop1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
SRSHL Zresult.S, Pg/M, Zresult.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SRSHL--Signed-rounding-shift-left--predicated--

When result is in a different register from op1, this intrinsic can use:

```asm
MOVPRFX Zresult.S, Pg/Z, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
SRSHLR Zresult.S, Pg/M, Zresult.S, Zop1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SRSHLR--Signed-rounding-shift-left-reversed--predicated--

### Operation

Source operation ID: `SveOperation_svrshl_n_s32_z`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Multiply `op1[i]` by 2 to the power `op2`, without loss of precision.
- Round the result to nearest with ties towards +∞.
- Truncate the result to the range of `int32_t`.



Set the inactive elements of the result to zero.

## svrshl[_n_s64]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrshl%5B_n_s64%5D_m

### Signature (source notation)

```c
svint64_t svrshl[_n_s64]_m(svbool_t pg, svint64_t op1, int64_t op2);
```

### Description

Rounding shift left

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Shift / Left / Vector rounding shift left

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
    "register": "Ztied1.D"
  },
  "op2": {
    "register": "Zop2.D[*]"
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

When op2 is in the range [0, 63], this intrinsic can use:

```asm
LSL Ztied1.D, Pg/M, Ztied1.D, #op2  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSL--immediate--predicated---Logical-shift-left-by-immediate--predicated--

When op2 is in the range [-64, -1], this intrinsic can use:

```asm
SRSHR Ztied1.D, Pg/M, Ztied1.D, #-op2  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SRSHR--Signed-rounding-shift-right-by-immediate-

The general implementation is:

```asm
SRSHL Ztied1.D, Pg/M, Ztied1.D, Zop2.D  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SRSHL--Signed-rounding-shift-left--predicated--

### Operation

Source operation ID: `SveOperation_svrshl_n_s64_m`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Multiply `op1[i]` by 2 to the power `op2`, without loss of precision.
- Round the result to nearest with ties towards +∞.
- Truncate the result to the range of `int64_t`.



Take the inactive elements of the result from the corresponding elements of `op1`.



**[1]** If instead `result` is in a different register from the inputs, the compiler can add a preceding [MOVPRFX (unpredicated)](https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--) instruction

## svrshl[_n_s64]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrshl%5B_n_s64%5D_x

### Signature (source notation)

```c
svint64_t svrshl[_n_s64]_x(svbool_t pg, svint64_t op1, int64_t op2);
```

### Description

Rounding shift left

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Shift / Left / Vector rounding shift left

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
  "op2": {
    "register": "Zop2.D[*]|Ztied2.D[*]"
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

When op2 is in the range [0, 63], this intrinsic can use:

```asm
LSL Zresult.D, Zop1.D, #op2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSL--immediate--unpredicated---Logical-shift-left-by-immediate--unpredicated--

When op2 is in the range [-64, -1], this intrinsic can use:

```asm
SRSHR Ztied1.D, Pg/M, Ztied1.D, #-op2  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SRSHR--Signed-rounding-shift-right-by-immediate-

When result and op1 are in the same register, this intrinsic can use:

```asm
SRSHL Ztied1.D, Pg/M, Ztied1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SRSHL--Signed-rounding-shift-left--predicated--

When result and op2 are in the same register, this intrinsic can use:

```asm
SRSHLR Ztied2.D, Pg/M, Ztied2.D, Zop1.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SRSHLR--Signed-rounding-shift-left-reversed--predicated--

When result is in a different register from the inputs, the general implementation is:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SRSHL Zresult.D, Pg/M, Zresult.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SRSHL--Signed-rounding-shift-left--predicated--

### Operation

Source operation ID: `SveOperation_svrshl_n_s64_x`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Multiply `op1[i]` by 2 to the power `op2`, without loss of precision.
- Round the result to nearest with ties towards +∞.
- Truncate the result to the range of `int64_t`.



The inactive elements of the result have arbitrary, undefined values.



**[1]** If instead `result` is in a different register from the inputs, the compiler can add a preceding [MOVPRFX (unpredicated)](https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--) instruction

## svrshl[_n_s64]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrshl%5B_n_s64%5D_z

### Signature (source notation)

```c
svint64_t svrshl[_n_s64]_z(svbool_t pg, svint64_t op1, int64_t op2);
```

### Description

Rounding shift left

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Shift / Left / Vector rounding shift left

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
  "op2": {
    "register": "Zop2.D[*]"
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

When op2 is in the range [0, 63], this intrinsic can use:

```asm
MOVPRFX Zresult.D, Pg/Z, Zop1.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
LSL Zresult.D, Pg/M, Zresult.D, #op2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSL--immediate--predicated---Logical-shift-left-by-immediate--predicated--

When op2 is in the range [-64, -1], this intrinsic can use:

```asm
MOVPRFX Zresult.D, Pg/Z, Zop1.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
SRSHR Zresult.D, Pg/M, Zresult.D, #-op2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SRSHR--Signed-rounding-shift-right-by-immediate-

When result is in a different register from op2, this intrinsic can use:

```asm
MOVPRFX Zresult.D, Pg/Z, Zop1.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
SRSHL Zresult.D, Pg/M, Zresult.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SRSHL--Signed-rounding-shift-left--predicated--

When result is in a different register from op1, this intrinsic can use:

```asm
MOVPRFX Zresult.D, Pg/Z, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
SRSHLR Zresult.D, Pg/M, Zresult.D, Zop1.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SRSHLR--Signed-rounding-shift-left-reversed--predicated--

### Operation

Source operation ID: `SveOperation_svrshl_n_s64_z`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Multiply `op1[i]` by 2 to the power `op2`, without loss of precision.
- Round the result to nearest with ties towards +∞.
- Truncate the result to the range of `int64_t`.



Set the inactive elements of the result to zero.

## svrshl[_n_s8]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrshl%5B_n_s8%5D_m

### Signature (source notation)

```c
svint8_t svrshl[_n_s8]_m(svbool_t pg, svint8_t op1, int8_t op2);
```

### Description

Rounding shift left

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Shift / Left / Vector rounding shift left

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
    "register": "Ztied1.B"
  },
  "op2": {
    "register": "Zop2.B[*]"
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

When op2 is in the range [0, 7], this intrinsic can use:

```asm
LSL Ztied1.B, Pg/M, Ztied1.B, #op2  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSL--immediate--predicated---Logical-shift-left-by-immediate--predicated--

When op2 is in the range [-8, -1], this intrinsic can use:

```asm
SRSHR Ztied1.B, Pg/M, Ztied1.B, #-op2  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SRSHR--Signed-rounding-shift-right-by-immediate-

The general implementation is:

```asm
SRSHL Ztied1.B, Pg/M, Ztied1.B, Zop2.B  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SRSHL--Signed-rounding-shift-left--predicated--

### Operation

Source operation ID: `SveOperation_svrshl_n_s8_m`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Multiply `op1[i]` by 2 to the power `op2`, without loss of precision.
- Round the result to nearest with ties towards +∞.
- Truncate the result to the range of `int8_t`.



Take the inactive elements of the result from the corresponding elements of `op1`.



**[1]** If instead `result` is in a different register from the inputs, the compiler can add a preceding [MOVPRFX (unpredicated)](https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--) instruction

## svrshl[_n_s8]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrshl%5B_n_s8%5D_x

### Signature (source notation)

```c
svint8_t svrshl[_n_s8]_x(svbool_t pg, svint8_t op1, int8_t op2);
```

### Description

Rounding shift left

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Shift / Left / Vector rounding shift left

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
  "op2": {
    "register": "Zop2.B[*]|Ztied2.B[*]"
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

When op2 is in the range [0, 7], this intrinsic can use:

```asm
LSL Zresult.B, Zop1.B, #op2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSL--immediate--unpredicated---Logical-shift-left-by-immediate--unpredicated--

When op2 is in the range [-8, -1], this intrinsic can use:

```asm
SRSHR Ztied1.B, Pg/M, Ztied1.B, #-op2  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SRSHR--Signed-rounding-shift-right-by-immediate-

When result and op1 are in the same register, this intrinsic can use:

```asm
SRSHL Ztied1.B, Pg/M, Ztied1.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SRSHL--Signed-rounding-shift-left--predicated--

When result and op2 are in the same register, this intrinsic can use:

```asm
SRSHLR Ztied2.B, Pg/M, Ztied2.B, Zop1.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SRSHLR--Signed-rounding-shift-left-reversed--predicated--

When result is in a different register from the inputs, the general implementation is:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SRSHL Zresult.B, Pg/M, Zresult.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SRSHL--Signed-rounding-shift-left--predicated--

### Operation

Source operation ID: `SveOperation_svrshl_n_s8_x`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Multiply `op1[i]` by 2 to the power `op2`, without loss of precision.
- Round the result to nearest with ties towards +∞.
- Truncate the result to the range of `int8_t`.



The inactive elements of the result have arbitrary, undefined values.



**[1]** If instead `result` is in a different register from the inputs, the compiler can add a preceding [MOVPRFX (unpredicated)](https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--) instruction

## svrshl[_n_s8]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrshl%5B_n_s8%5D_z

### Signature (source notation)

```c
svint8_t svrshl[_n_s8]_z(svbool_t pg, svint8_t op1, int8_t op2);
```

### Description

Rounding shift left

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Shift / Left / Vector rounding shift left

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
  "op2": {
    "register": "Zop2.B[*]"
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

When op2 is in the range [0, 7], this intrinsic can use:

```asm
MOVPRFX Zresult.B, Pg/Z, Zop1.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
LSL Zresult.B, Pg/M, Zresult.B, #op2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSL--immediate--predicated---Logical-shift-left-by-immediate--predicated--

When op2 is in the range [-8, -1], this intrinsic can use:

```asm
MOVPRFX Zresult.B, Pg/Z, Zop1.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
SRSHR Zresult.B, Pg/M, Zresult.B, #-op2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SRSHR--Signed-rounding-shift-right-by-immediate-

When result is in a different register from op2, this intrinsic can use:

```asm
MOVPRFX Zresult.B, Pg/Z, Zop1.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
SRSHL Zresult.B, Pg/M, Zresult.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SRSHL--Signed-rounding-shift-left--predicated--

When result is in a different register from op1, this intrinsic can use:

```asm
MOVPRFX Zresult.B, Pg/Z, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
SRSHLR Zresult.B, Pg/M, Zresult.B, Zop1.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SRSHLR--Signed-rounding-shift-left-reversed--predicated--

### Operation

Source operation ID: `SveOperation_svrshl_n_s8_z`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Multiply `op1[i]` by 2 to the power `op2`, without loss of precision.
- Round the result to nearest with ties towards +∞.
- Truncate the result to the range of `int8_t`.



Set the inactive elements of the result to zero.

## svrshl[_n_u16]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrshl%5B_n_u16%5D_m

### Signature (source notation)

```c
svuint16_t svrshl[_n_u16]_m(svbool_t pg, svuint16_t op1, int16_t op2);
```

### Description

Rounding shift left

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Shift / Left / Vector rounding shift left

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
    "register": "Ztied1.H"
  },
  "op2": {
    "register": "Zop2.H[*]"
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

When op2 is in the range [0, 15], this intrinsic can use:

```asm
LSL Ztied1.H, Pg/M, Ztied1.H, #op2  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSL--immediate--predicated---Logical-shift-left-by-immediate--predicated--

When op2 is in the range [-16, -1], this intrinsic can use:

```asm
URSHR Ztied1.H, Pg/M, Ztied1.H, #-op2  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/URSHR--Unsigned-rounding-shift-right-by-immediate-

The general implementation is:

```asm
URSHL Ztied1.H, Pg/M, Ztied1.H, Zop2.H  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/URSHL--Unsigned-rounding-shift-left--predicated--

### Operation

Source operation ID: `SveOperation_svrshl_n_u16_m`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Multiply `op1[i]` by 2 to the power `op2`, without loss of precision.
- Round the result to nearest with ties towards +∞.
- Truncate the result to the range of `uint16_t`.



Take the inactive elements of the result from the corresponding elements of `op1`.



**[1]** If instead `result` is in a different register from the inputs, the compiler can add a preceding [MOVPRFX (unpredicated)](https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--) instruction

## svrshl[_n_u16]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrshl%5B_n_u16%5D_x

### Signature (source notation)

```c
svuint16_t svrshl[_n_u16]_x(svbool_t pg, svuint16_t op1, int16_t op2);
```

### Description

Rounding shift left

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Shift / Left / Vector rounding shift left

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
  "op2": {
    "register": "Zop2.H[*]|Ztied2.H[*]"
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

When op2 is in the range [0, 15], this intrinsic can use:

```asm
LSL Zresult.H, Zop1.H, #op2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSL--immediate--unpredicated---Logical-shift-left-by-immediate--unpredicated--

When op2 is in the range [-16, -1], this intrinsic can use:

```asm
URSHR Ztied1.H, Pg/M, Ztied1.H, #-op2  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/URSHR--Unsigned-rounding-shift-right-by-immediate-

When result and op1 are in the same register, this intrinsic can use:

```asm
URSHL Ztied1.H, Pg/M, Ztied1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/URSHL--Unsigned-rounding-shift-left--predicated--

When result and op2 are in the same register, this intrinsic can use:

```asm
URSHLR Ztied2.H, Pg/M, Ztied2.H, Zop1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/URSHR--Unsigned-rounding-shift-right-by-immediate-

When result is in a different register from the inputs, the general implementation is:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
URSHL Zresult.H, Pg/M, Zresult.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/URSHL--Unsigned-rounding-shift-left--predicated--

### Operation

Source operation ID: `SveOperation_svrshl_n_u16_x`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Multiply `op1[i]` by 2 to the power `op2`, without loss of precision.
- Round the result to nearest with ties towards +∞.
- Truncate the result to the range of `uint16_t`.



The inactive elements of the result have arbitrary, undefined values.



**[1]** If instead `result` is in a different register from the inputs, the compiler can add a preceding [MOVPRFX (unpredicated)](https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--) instruction

## svrshl[_n_u16]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrshl%5B_n_u16%5D_z

### Signature (source notation)

```c
svuint16_t svrshl[_n_u16]_z(svbool_t pg, svuint16_t op1, int16_t op2);
```

### Description

Rounding shift left

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Shift / Left / Vector rounding shift left

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
  "op2": {
    "register": "Zop2.H[*]"
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

When op2 is in the range [0, 15], this intrinsic can use:

```asm
MOVPRFX Zresult.H, Pg/Z, Zop1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
LSL Zresult.H, Pg/M, Zresult.H, #op2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSL--immediate--predicated---Logical-shift-left-by-immediate--predicated--

When op2 is in the range [-16, -1], this intrinsic can use:

```asm
MOVPRFX Zresult.H, Pg/Z, Zop1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
URSHR Zresult.H, Pg/M, Zresult.H, #-op2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/URSHR--Unsigned-rounding-shift-right-by-immediate-

When result is in a different register from op2, this intrinsic can use:

```asm
MOVPRFX Zresult.H, Pg/Z, Zop1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
URSHL Zresult.H, Pg/M, Zresult.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/URSHL--Unsigned-rounding-shift-left--predicated--

When result is in a different register from op1, this intrinsic can use:

```asm
MOVPRFX Zresult.H, Pg/Z, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
URSHLR Zresult.H, Pg/M, Zresult.H, Zop1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/URSHR--Unsigned-rounding-shift-right-by-immediate-

### Operation

Source operation ID: `SveOperation_svrshl_n_u16_z`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Multiply `op1[i]` by 2 to the power `op2`, without loss of precision.
- Round the result to nearest with ties towards +∞.
- Truncate the result to the range of `uint16_t`.



Set the inactive elements of the result to zero.

## svrshl[_n_u32]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrshl%5B_n_u32%5D_m

### Signature (source notation)

```c
svuint32_t svrshl[_n_u32]_m(svbool_t pg, svuint32_t op1, int32_t op2);
```

### Description

Rounding shift left

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Shift / Left / Vector rounding shift left

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
    "register": "Ztied1.S"
  },
  "op2": {
    "register": "Zop2.S[*]"
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

When op2 is in the range [0, 31], this intrinsic can use:

```asm
LSL Ztied1.S, Pg/M, Ztied1.S, #op2  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSL--immediate--predicated---Logical-shift-left-by-immediate--predicated--

When op2 is in the range [-32, -1], this intrinsic can use:

```asm
URSHR Ztied1.S, Pg/M, Ztied1.S, #-op2  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/URSHR--Unsigned-rounding-shift-right-by-immediate-

The general implementation is:

```asm
URSHL Ztied1.S, Pg/M, Ztied1.S, Zop2.S  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/URSHL--Unsigned-rounding-shift-left--predicated--

### Operation

Source operation ID: `SveOperation_svrshl_n_u32_m`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Multiply `op1[i]` by 2 to the power `op2`, without loss of precision.
- Round the result to nearest with ties towards +∞.
- Truncate the result to the range of `uint32_t`.



Take the inactive elements of the result from the corresponding elements of `op1`.



**[1]** If instead `result` is in a different register from the inputs, the compiler can add a preceding [MOVPRFX (unpredicated)](https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--) instruction

## svrshl[_n_u32]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrshl%5B_n_u32%5D_x

### Signature (source notation)

```c
svuint32_t svrshl[_n_u32]_x(svbool_t pg, svuint32_t op1, int32_t op2);
```

### Description

Rounding shift left

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Shift / Left / Vector rounding shift left

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
  "op2": {
    "register": "Zop2.S[*]|Ztied2.S[*]"
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

When op2 is in the range [0, 31], this intrinsic can use:

```asm
LSL Zresult.S, Zop1.S, #op2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSL--immediate--unpredicated---Logical-shift-left-by-immediate--unpredicated--

When op2 is in the range [-32, -1], this intrinsic can use:

```asm
URSHR Ztied1.S, Pg/M, Ztied1.S, #-op2  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/URSHR--Unsigned-rounding-shift-right-by-immediate-

When result and op1 are in the same register, this intrinsic can use:

```asm
URSHL Ztied1.S, Pg/M, Ztied1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/URSHL--Unsigned-rounding-shift-left--predicated--

When result and op2 are in the same register, this intrinsic can use:

```asm
URSHLR Ztied2.S, Pg/M, Ztied2.S, Zop1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/URSHR--Unsigned-rounding-shift-right-by-immediate-

When result is in a different register from the inputs, the general implementation is:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
URSHL Zresult.S, Pg/M, Zresult.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/URSHL--Unsigned-rounding-shift-left--predicated--

### Operation

Source operation ID: `SveOperation_svrshl_n_u32_x`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Multiply `op1[i]` by 2 to the power `op2`, without loss of precision.
- Round the result to nearest with ties towards +∞.
- Truncate the result to the range of `uint32_t`.



The inactive elements of the result have arbitrary, undefined values.



**[1]** If instead `result` is in a different register from the inputs, the compiler can add a preceding [MOVPRFX (unpredicated)](https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--) instruction

## svrshl[_n_u32]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrshl%5B_n_u32%5D_z

### Signature (source notation)

```c
svuint32_t svrshl[_n_u32]_z(svbool_t pg, svuint32_t op1, int32_t op2);
```

### Description

Rounding shift left

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Shift / Left / Vector rounding shift left

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
  "op2": {
    "register": "Zop2.S[*]"
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

When op2 is in the range [0, 31], this intrinsic can use:

```asm
MOVPRFX Zresult.S, Pg/Z, Zop1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
LSL Zresult.S, Pg/M, Zresult.S, #op2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSL--immediate--predicated---Logical-shift-left-by-immediate--predicated--

When op2 is in the range [-32, -1], this intrinsic can use:

```asm
MOVPRFX Zresult.S, Pg/Z, Zop1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
URSHR Zresult.S, Pg/M, Zresult.S, #-op2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/URSHR--Unsigned-rounding-shift-right-by-immediate-

When result is in a different register from op2, this intrinsic can use:

```asm
MOVPRFX Zresult.S, Pg/Z, Zop1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
URSHL Zresult.S, Pg/M, Zresult.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/URSHL--Unsigned-rounding-shift-left--predicated--

When result is in a different register from op1, this intrinsic can use:

```asm
MOVPRFX Zresult.S, Pg/Z, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
URSHLR Zresult.S, Pg/M, Zresult.S, Zop1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/URSHR--Unsigned-rounding-shift-right-by-immediate-

### Operation

Source operation ID: `SveOperation_svrshl_n_u32_z`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Multiply `op1[i]` by 2 to the power `op2`, without loss of precision.
- Round the result to nearest with ties towards +∞.
- Truncate the result to the range of `uint32_t`.



Set the inactive elements of the result to zero.

## svrshl[_n_u64]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrshl%5B_n_u64%5D_m

### Signature (source notation)

```c
svuint64_t svrshl[_n_u64]_m(svbool_t pg, svuint64_t op1, int64_t op2);
```

### Description

Rounding shift left

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Shift / Left / Vector rounding shift left

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
    "register": "Ztied1.D"
  },
  "op2": {
    "register": "Zop2.D[*]"
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

When op2 is in the range [0, 63], this intrinsic can use:

```asm
LSL Ztied1.D, Pg/M, Ztied1.D, #op2  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSL--immediate--predicated---Logical-shift-left-by-immediate--predicated--

When op2 is in the range [-64, -1], this intrinsic can use:

```asm
URSHR Ztied1.D, Pg/M, Ztied1.D, #-op2  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/URSHR--Unsigned-rounding-shift-right-by-immediate-

The general implementation is:

```asm
URSHL Ztied1.D, Pg/M, Ztied1.D, Zop2.D  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/URSHL--Unsigned-rounding-shift-left--predicated--

### Operation

Source operation ID: `SveOperation_svrshl_n_u64_m`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Multiply `op1[i]` by 2 to the power `op2`, without loss of precision.
- Round the result to nearest with ties towards +∞.
- Truncate the result to the range of `uint64_t`.



Take the inactive elements of the result from the corresponding elements of `op1`.



**[1]** If instead `result` is in a different register from the inputs, the compiler can add a preceding [MOVPRFX (unpredicated)](https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--) instruction

## svrshl[_n_u64]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrshl%5B_n_u64%5D_x

### Signature (source notation)

```c
svuint64_t svrshl[_n_u64]_x(svbool_t pg, svuint64_t op1, int64_t op2);
```

### Description

Rounding shift left

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Shift / Left / Vector rounding shift left

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
  "op2": {
    "register": "Zop2.D[*]|Ztied2.D[*]"
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

When op2 is in the range [0, 63], this intrinsic can use:

```asm
LSL Zresult.D, Zop1.D, #op2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSL--immediate--unpredicated---Logical-shift-left-by-immediate--unpredicated--

When op2 is in the range [-64, -1], this intrinsic can use:

```asm
URSHR Ztied1.D, Pg/M, Ztied1.D, #-op2  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/URSHR--Unsigned-rounding-shift-right-by-immediate-

When result and op1 are in the same register, this intrinsic can use:

```asm
URSHL Ztied1.D, Pg/M, Ztied1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/URSHL--Unsigned-rounding-shift-left--predicated--

When result and op2 are in the same register, this intrinsic can use:

```asm
URSHLR Ztied2.D, Pg/M, Ztied2.D, Zop1.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/URSHR--Unsigned-rounding-shift-right-by-immediate-

When result is in a different register from the inputs, the general implementation is:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
URSHL Zresult.D, Pg/M, Zresult.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/URSHL--Unsigned-rounding-shift-left--predicated--

### Operation

Source operation ID: `SveOperation_svrshl_n_u64_x`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Multiply `op1[i]` by 2 to the power `op2`, without loss of precision.
- Round the result to nearest with ties towards +∞.
- Truncate the result to the range of `uint64_t`.



The inactive elements of the result have arbitrary, undefined values.



**[1]** If instead `result` is in a different register from the inputs, the compiler can add a preceding [MOVPRFX (unpredicated)](https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--) instruction

## svrshl[_n_u64]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrshl%5B_n_u64%5D_z

### Signature (source notation)

```c
svuint64_t svrshl[_n_u64]_z(svbool_t pg, svuint64_t op1, int64_t op2);
```

### Description

Rounding shift left

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Shift / Left / Vector rounding shift left

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
  "op2": {
    "register": "Zop2.D[*]"
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

When op2 is in the range [0, 63], this intrinsic can use:

```asm
MOVPRFX Zresult.D, Pg/Z, Zop1.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
LSL Zresult.D, Pg/M, Zresult.D, #op2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSL--immediate--predicated---Logical-shift-left-by-immediate--predicated--

When op2 is in the range [-64, -1], this intrinsic can use:

```asm
MOVPRFX Zresult.D, Pg/Z, Zop1.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
URSHR Zresult.D, Pg/M, Zresult.D, #-op2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/URSHR--Unsigned-rounding-shift-right-by-immediate-

When result is in a different register from op2, this intrinsic can use:

```asm
MOVPRFX Zresult.D, Pg/Z, Zop1.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
URSHL Zresult.D, Pg/M, Zresult.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/URSHL--Unsigned-rounding-shift-left--predicated--

When result is in a different register from op1, this intrinsic can use:

```asm
MOVPRFX Zresult.D, Pg/Z, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
URSHLR Zresult.D, Pg/M, Zresult.D, Zop1.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/URSHR--Unsigned-rounding-shift-right-by-immediate-

### Operation

Source operation ID: `SveOperation_svrshl_n_u64_z`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Multiply `op1[i]` by 2 to the power `op2`, without loss of precision.
- Round the result to nearest with ties towards +∞.
- Truncate the result to the range of `uint64_t`.



Set the inactive elements of the result to zero.

## svrshl[_n_u8]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrshl%5B_n_u8%5D_m

### Signature (source notation)

```c
svuint8_t svrshl[_n_u8]_m(svbool_t pg, svuint8_t op1, int8_t op2);
```

### Description

Rounding shift left

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Shift / Left / Vector rounding shift left

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
    "register": "Ztied1.B"
  },
  "op2": {
    "register": "Zop2.B[*]"
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

When op2 is in the range [0, 7], this intrinsic can use:

```asm
LSL Ztied1.B, Pg/M, Ztied1.B, #op2  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSL--immediate--predicated---Logical-shift-left-by-immediate--predicated--

When op2 is in the range [-8, -1], this intrinsic can use:

```asm
URSHR Ztied1.B, Pg/M, Ztied1.B, #-op2  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/URSHR--Unsigned-rounding-shift-right-by-immediate-

The general implementation is:

```asm
URSHL Ztied1.B, Pg/M, Ztied1.B, Zop2.B  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/URSHL--Unsigned-rounding-shift-left--predicated--

### Operation

Source operation ID: `SveOperation_svrshl_n_u8_m`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Multiply `op1[i]` by 2 to the power `op2`, without loss of precision.
- Round the result to nearest with ties towards +∞.
- Truncate the result to the range of `uint8_t`.



Take the inactive elements of the result from the corresponding elements of `op1`.



**[1]** If instead `result` is in a different register from the inputs, the compiler can add a preceding [MOVPRFX (unpredicated)](https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--) instruction

## svrshl[_n_u8]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrshl%5B_n_u8%5D_x

### Signature (source notation)

```c
svuint8_t svrshl[_n_u8]_x(svbool_t pg, svuint8_t op1, int8_t op2);
```

### Description

Rounding shift left

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Shift / Left / Vector rounding shift left

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
  "op2": {
    "register": "Zop2.B[*]|Ztied2.B[*]"
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

When op2 is in the range [0, 7], this intrinsic can use:

```asm
LSL Zresult.B, Zop1.B, #op2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSL--immediate--unpredicated---Logical-shift-left-by-immediate--unpredicated--

When op2 is in the range [-8, -1], this intrinsic can use:

```asm
URSHR Ztied1.B, Pg/M, Ztied1.B, #-op2  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/URSHR--Unsigned-rounding-shift-right-by-immediate-

When result and op1 are in the same register, this intrinsic can use:

```asm
URSHL Ztied1.B, Pg/M, Ztied1.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/URSHL--Unsigned-rounding-shift-left--predicated--

When result and op2 are in the same register, this intrinsic can use:

```asm
URSHLR Ztied2.B, Pg/M, Ztied2.B, Zop1.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/URSHR--Unsigned-rounding-shift-right-by-immediate-

When result is in a different register from the inputs, the general implementation is:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
URSHL Zresult.B, Pg/M, Zresult.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/URSHL--Unsigned-rounding-shift-left--predicated--

### Operation

Source operation ID: `SveOperation_svrshl_n_u8_x`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Multiply `op1[i]` by 2 to the power `op2`, without loss of precision.
- Round the result to nearest with ties towards +∞.
- Truncate the result to the range of `uint8_t`.



The inactive elements of the result have arbitrary, undefined values.



**[1]** If instead `result` is in a different register from the inputs, the compiler can add a preceding [MOVPRFX (unpredicated)](https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--) instruction

## svrshl[_n_u8]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrshl%5B_n_u8%5D_z

### Signature (source notation)

```c
svuint8_t svrshl[_n_u8]_z(svbool_t pg, svuint8_t op1, int8_t op2);
```

### Description

Rounding shift left

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Shift / Left / Vector rounding shift left

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
  "op2": {
    "register": "Zop2.B[*]"
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

When op2 is in the range [0, 7], this intrinsic can use:

```asm
MOVPRFX Zresult.B, Pg/Z, Zop1.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
LSL Zresult.B, Pg/M, Zresult.B, #op2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSL--immediate--predicated---Logical-shift-left-by-immediate--predicated--

When op2 is in the range [-8, -1], this intrinsic can use:

```asm
MOVPRFX Zresult.B, Pg/Z, Zop1.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
URSHR Zresult.B, Pg/M, Zresult.B, #-op2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/URSHR--Unsigned-rounding-shift-right-by-immediate-

When result is in a different register from op2, this intrinsic can use:

```asm
MOVPRFX Zresult.B, Pg/Z, Zop1.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
URSHL Zresult.B, Pg/M, Zresult.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/URSHL--Unsigned-rounding-shift-left--predicated--

When result is in a different register from op1, this intrinsic can use:

```asm
MOVPRFX Zresult.B, Pg/Z, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
URSHLR Zresult.B, Pg/M, Zresult.B, Zop1.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/URSHR--Unsigned-rounding-shift-right-by-immediate-

### Operation

Source operation ID: `SveOperation_svrshl_n_u8_z`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Multiply `op1[i]` by 2 to the power `op2`, without loss of precision.
- Round the result to nearest with ties towards +∞.
- Truncate the result to the range of `uint8_t`.



Set the inactive elements of the result to zero.

## svrshl[_s16]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrshl%5B_s16%5D_m

### Signature (source notation)

```c
svint16_t svrshl[_s16]_m(svbool_t pg, svint16_t op1, svint16_t op2);
```

### Description

Rounding shift left

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Shift / Left / Vector rounding shift left

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
  "op2": {
    "register": "Zop2.H"
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
SRSHL Ztied1.H, Pg/M, Ztied1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SRSHL--Signed-rounding-shift-left--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SRSHL Zresult.H, Pg/M, Zresult.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SRSHL--Signed-rounding-shift-left--predicated--

### Operation

Source operation ID: `SveOperation_svrshl_s16_m`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Multiply `op1[i]` by 2 to the power `op2[i]`, without loss of precision.
- Round the result to nearest with ties towards +∞.
- Truncate the result to the range of `int16_t`.



Take the inactive elements of the result from the corresponding elements of `op1`.

## svrshl[_s16]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrshl%5B_s16%5D_x

### Signature (source notation)

```c
svint16_t svrshl[_s16]_x(svbool_t pg, svint16_t op1, svint16_t op2);
```

### Description

Rounding shift left

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Shift / Left / Vector rounding shift left

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
  "op2": {
    "register": "Zop2.H|Ztied2.H"
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
SRSHL Ztied1.H, Pg/M, Ztied1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SRSHL--Signed-rounding-shift-left--predicated--

When result and op2 are in the same register, this intrinsic compiles to:

```asm
SRSHLR Ztied2.H, Pg/M, Ztied2.H, Zop1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SRSHLR--Signed-rounding-shift-left-reversed--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SRSHL Zresult.H, Pg/M, Zresult.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SRSHL--Signed-rounding-shift-left--predicated--

### Operation

Source operation ID: `SveOperation_svrshl_s16_x`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Multiply `op1[i]` by 2 to the power `op2[i]`, without loss of precision.
- Round the result to nearest with ties towards +∞.
- Truncate the result to the range of `int16_t`.



The inactive elements of the result have arbitrary, undefined values.

## svrshl[_s16]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrshl%5B_s16%5D_z

### Signature (source notation)

```c
svint16_t svrshl[_s16]_z(svbool_t pg, svint16_t op1, svint16_t op2);
```

### Description

Rounding shift left

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Shift / Left / Vector rounding shift left

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
  "op2": {
    "register": "Zop2.H"
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

When result is in a different register from op2, this intrinsic can use:

```asm
MOVPRFX Zresult.H, Pg/Z, Zop1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
SRSHL Zresult.H, Pg/M, Zresult.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SRSHL--Signed-rounding-shift-left--predicated--

When result is in a different register from op1, this intrinsic can use:

```asm
MOVPRFX Zresult.H, Pg/Z, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
SRSHLR Zresult.H, Pg/M, Zresult.H, Zop1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SRSHLR--Signed-rounding-shift-left-reversed--predicated--

### Operation

Source operation ID: `SveOperation_svrshl_s16_z`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Multiply `op1[i]` by 2 to the power `op2[i]`, without loss of precision.
- Round the result to nearest with ties towards +∞.
- Truncate the result to the range of `int16_t`.



Set the inactive elements of the result to zero.

## svrshl[_s32]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrshl%5B_s32%5D_m

### Signature (source notation)

```c
svint32_t svrshl[_s32]_m(svbool_t pg, svint32_t op1, svint32_t op2);
```

### Description

Rounding shift left

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Shift / Left / Vector rounding shift left

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
  "op2": {
    "register": "Zop2.S"
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
SRSHL Ztied1.S, Pg/M, Ztied1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SRSHL--Signed-rounding-shift-left--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SRSHL Zresult.S, Pg/M, Zresult.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SRSHL--Signed-rounding-shift-left--predicated--

### Operation

Source operation ID: `SveOperation_svrshl_s32_m`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Multiply `op1[i]` by 2 to the power `op2[i]`, without loss of precision.
- Round the result to nearest with ties towards +∞.
- Truncate the result to the range of `int32_t`.



Take the inactive elements of the result from the corresponding elements of `op1`.

## svrshl[_s32]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrshl%5B_s32%5D_x

### Signature (source notation)

```c
svint32_t svrshl[_s32]_x(svbool_t pg, svint32_t op1, svint32_t op2);
```

### Description

Rounding shift left

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Shift / Left / Vector rounding shift left

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
  "op2": {
    "register": "Zop2.S|Ztied2.S"
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
SRSHL Ztied1.S, Pg/M, Ztied1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SRSHL--Signed-rounding-shift-left--predicated--

When result and op2 are in the same register, this intrinsic compiles to:

```asm
SRSHLR Ztied2.S, Pg/M, Ztied2.S, Zop1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SRSHLR--Signed-rounding-shift-left-reversed--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SRSHL Zresult.S, Pg/M, Zresult.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SRSHL--Signed-rounding-shift-left--predicated--

### Operation

Source operation ID: `SveOperation_svrshl_s32_x`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Multiply `op1[i]` by 2 to the power `op2[i]`, without loss of precision.
- Round the result to nearest with ties towards +∞.
- Truncate the result to the range of `int32_t`.



The inactive elements of the result have arbitrary, undefined values.

## svrshl[_s32]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrshl%5B_s32%5D_z

### Signature (source notation)

```c
svint32_t svrshl[_s32]_z(svbool_t pg, svint32_t op1, svint32_t op2);
```

### Description

Rounding shift left

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Shift / Left / Vector rounding shift left

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
  "op2": {
    "register": "Zop2.S"
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

When result is in a different register from op2, this intrinsic can use:

```asm
MOVPRFX Zresult.S, Pg/Z, Zop1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
SRSHL Zresult.S, Pg/M, Zresult.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SRSHL--Signed-rounding-shift-left--predicated--

When result is in a different register from op1, this intrinsic can use:

```asm
MOVPRFX Zresult.S, Pg/Z, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
SRSHLR Zresult.S, Pg/M, Zresult.S, Zop1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SRSHLR--Signed-rounding-shift-left-reversed--predicated--

### Operation

Source operation ID: `SveOperation_svrshl_s32_z`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Multiply `op1[i]` by 2 to the power `op2[i]`, without loss of precision.
- Round the result to nearest with ties towards +∞.
- Truncate the result to the range of `int32_t`.



Set the inactive elements of the result to zero.

## svrshl[_s64]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrshl%5B_s64%5D_m

### Signature (source notation)

```c
svint64_t svrshl[_s64]_m(svbool_t pg, svint64_t op1, svint64_t op2);
```

### Description

Rounding shift left

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Shift / Left / Vector rounding shift left

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
  "op2": {
    "register": "Zop2.D"
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
SRSHL Ztied1.D, Pg/M, Ztied1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SRSHL--Signed-rounding-shift-left--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SRSHL Zresult.D, Pg/M, Zresult.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SRSHL--Signed-rounding-shift-left--predicated--

### Operation

Source operation ID: `SveOperation_svrshl_s64_m`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Multiply `op1[i]` by 2 to the power `op2[i]`, without loss of precision.
- Round the result to nearest with ties towards +∞.
- Truncate the result to the range of `int64_t`.



Take the inactive elements of the result from the corresponding elements of `op1`.

## svrshl[_s64]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrshl%5B_s64%5D_x

### Signature (source notation)

```c
svint64_t svrshl[_s64]_x(svbool_t pg, svint64_t op1, svint64_t op2);
```

### Description

Rounding shift left

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Shift / Left / Vector rounding shift left

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
  "op2": {
    "register": "Zop2.D|Ztied2.D"
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
SRSHL Ztied1.D, Pg/M, Ztied1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SRSHL--Signed-rounding-shift-left--predicated--

When result and op2 are in the same register, this intrinsic compiles to:

```asm
SRSHLR Ztied2.D, Pg/M, Ztied2.D, Zop1.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SRSHLR--Signed-rounding-shift-left-reversed--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SRSHL Zresult.D, Pg/M, Zresult.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SRSHL--Signed-rounding-shift-left--predicated--

### Operation

Source operation ID: `SveOperation_svrshl_s64_x`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Multiply `op1[i]` by 2 to the power `op2[i]`, without loss of precision.
- Round the result to nearest with ties towards +∞.
- Truncate the result to the range of `int64_t`.



The inactive elements of the result have arbitrary, undefined values.

## svrshl[_s64]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrshl%5B_s64%5D_z

### Signature (source notation)

```c
svint64_t svrshl[_s64]_z(svbool_t pg, svint64_t op1, svint64_t op2);
```

### Description

Rounding shift left

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Shift / Left / Vector rounding shift left

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
  "op2": {
    "register": "Zop2.D"
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

When result is in a different register from op2, this intrinsic can use:

```asm
MOVPRFX Zresult.D, Pg/Z, Zop1.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
SRSHL Zresult.D, Pg/M, Zresult.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SRSHL--Signed-rounding-shift-left--predicated--

When result is in a different register from op1, this intrinsic can use:

```asm
MOVPRFX Zresult.D, Pg/Z, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
SRSHLR Zresult.D, Pg/M, Zresult.D, Zop1.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SRSHLR--Signed-rounding-shift-left-reversed--predicated--

### Operation

Source operation ID: `SveOperation_svrshl_s64_z`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Multiply `op1[i]` by 2 to the power `op2[i]`, without loss of precision.
- Round the result to nearest with ties towards +∞.
- Truncate the result to the range of `int64_t`.



Set the inactive elements of the result to zero.

## svrshl[_s8]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrshl%5B_s8%5D_m

### Signature (source notation)

```c
svint8_t svrshl[_s8]_m(svbool_t pg, svint8_t op1, svint8_t op2);
```

### Description

Rounding shift left

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Shift / Left / Vector rounding shift left

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
  "op2": {
    "register": "Zop2.B"
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
SRSHL Ztied1.B, Pg/M, Ztied1.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SRSHL--Signed-rounding-shift-left--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SRSHL Zresult.B, Pg/M, Zresult.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SRSHL--Signed-rounding-shift-left--predicated--

### Operation

Source operation ID: `SveOperation_svrshl_s8_m`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Multiply `op1[i]` by 2 to the power `op2[i]`, without loss of precision.
- Round the result to nearest with ties towards +∞.
- Truncate the result to the range of `int8_t`.



Take the inactive elements of the result from the corresponding elements of `op1`.

## svrshl[_s8]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrshl%5B_s8%5D_x

### Signature (source notation)

```c
svint8_t svrshl[_s8]_x(svbool_t pg, svint8_t op1, svint8_t op2);
```

### Description

Rounding shift left

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Shift / Left / Vector rounding shift left

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
  "op2": {
    "register": "Zop2.B|Ztied2.B"
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
SRSHL Ztied1.B, Pg/M, Ztied1.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SRSHL--Signed-rounding-shift-left--predicated--

When result and op2 are in the same register, this intrinsic compiles to:

```asm
SRSHLR Ztied2.B, Pg/M, Ztied2.B, Zop1.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SRSHLR--Signed-rounding-shift-left-reversed--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SRSHL Zresult.B, Pg/M, Zresult.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SRSHL--Signed-rounding-shift-left--predicated--

### Operation

Source operation ID: `SveOperation_svrshl_s8_x`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Multiply `op1[i]` by 2 to the power `op2[i]`, without loss of precision.
- Round the result to nearest with ties towards +∞.
- Truncate the result to the range of `int8_t`.



The inactive elements of the result have arbitrary, undefined values.

## svrshl[_s8]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrshl%5B_s8%5D_z

### Signature (source notation)

```c
svint8_t svrshl[_s8]_z(svbool_t pg, svint8_t op1, svint8_t op2);
```

### Description

Rounding shift left

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Shift / Left / Vector rounding shift left

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
  "op2": {
    "register": "Zop2.B"
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

When result is in a different register from op2, this intrinsic can use:

```asm
MOVPRFX Zresult.B, Pg/Z, Zop1.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
SRSHL Zresult.B, Pg/M, Zresult.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SRSHL--Signed-rounding-shift-left--predicated--

When result is in a different register from op1, this intrinsic can use:

```asm
MOVPRFX Zresult.B, Pg/Z, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
SRSHLR Zresult.B, Pg/M, Zresult.B, Zop1.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SRSHLR--Signed-rounding-shift-left-reversed--predicated--

### Operation

Source operation ID: `SveOperation_svrshl_s8_z`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Multiply `op1[i]` by 2 to the power `op2[i]`, without loss of precision.
- Round the result to nearest with ties towards +∞.
- Truncate the result to the range of `int8_t`.



Set the inactive elements of the result to zero.

## svrshl[_u16]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrshl%5B_u16%5D_m

### Signature (source notation)

```c
svuint16_t svrshl[_u16]_m(svbool_t pg, svuint16_t op1, svint16_t op2);
```

### Description

Rounding shift left

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Shift / Left / Vector rounding shift left

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
  "op2": {
    "register": "Zop2.H"
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
URSHL Ztied1.H, Pg/M, Ztied1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/URSHL--Unsigned-rounding-shift-left--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
URSHL Zresult.H, Pg/M, Zresult.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/URSHL--Unsigned-rounding-shift-left--predicated--

### Operation

Source operation ID: `SveOperation_svrshl_u16_m`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Multiply `op1[i]` by 2 to the power `op2[i]`, without loss of precision.
- Round the result to nearest with ties towards +∞.
- Truncate the result to the range of `uint16_t`.



Take the inactive elements of the result from the corresponding elements of `op1`.

## svrshl[_u16]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrshl%5B_u16%5D_x

### Signature (source notation)

```c
svuint16_t svrshl[_u16]_x(svbool_t pg, svuint16_t op1, svint16_t op2);
```

### Description

Rounding shift left

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Shift / Left / Vector rounding shift left

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
  "op2": {
    "register": "Zop2.H|Ztied2.H"
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
URSHL Ztied1.H, Pg/M, Ztied1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/URSHL--Unsigned-rounding-shift-left--predicated--

When result and op2 are in the same register, this intrinsic compiles to:

```asm
URSHLR Ztied2.H, Pg/M, Ztied2.H, Zop1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/URSHR--Unsigned-rounding-shift-right-by-immediate-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
URSHL Zresult.H, Pg/M, Zresult.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/URSHL--Unsigned-rounding-shift-left--predicated--

### Operation

Source operation ID: `SveOperation_svrshl_u16_x`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Multiply `op1[i]` by 2 to the power `op2[i]`, without loss of precision.
- Round the result to nearest with ties towards +∞.
- Truncate the result to the range of `uint16_t`.



The inactive elements of the result have arbitrary, undefined values.

## svrshl[_u16]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrshl%5B_u16%5D_z

### Signature (source notation)

```c
svuint16_t svrshl[_u16]_z(svbool_t pg, svuint16_t op1, svint16_t op2);
```

### Description

Rounding shift left

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Shift / Left / Vector rounding shift left

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
  "op2": {
    "register": "Zop2.H"
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

When result is in a different register from op2, this intrinsic can use:

```asm
MOVPRFX Zresult.H, Pg/Z, Zop1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
URSHL Zresult.H, Pg/M, Zresult.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/URSHL--Unsigned-rounding-shift-left--predicated--

When result is in a different register from op1, this intrinsic can use:

```asm
MOVPRFX Zresult.H, Pg/Z, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
URSHLR Zresult.H, Pg/M, Zresult.H, Zop1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/URSHR--Unsigned-rounding-shift-right-by-immediate-

### Operation

Source operation ID: `SveOperation_svrshl_u16_z`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Multiply `op1[i]` by 2 to the power `op2[i]`, without loss of precision.
- Round the result to nearest with ties towards +∞.
- Truncate the result to the range of `uint16_t`.



Set the inactive elements of the result to zero.

## svrshl[_u32]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrshl%5B_u32%5D_m

### Signature (source notation)

```c
svuint32_t svrshl[_u32]_m(svbool_t pg, svuint32_t op1, svint32_t op2);
```

### Description

Rounding shift left

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Shift / Left / Vector rounding shift left

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
  "op2": {
    "register": "Zop2.S"
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
URSHL Ztied1.S, Pg/M, Ztied1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/URSHL--Unsigned-rounding-shift-left--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
URSHL Zresult.S, Pg/M, Zresult.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/URSHL--Unsigned-rounding-shift-left--predicated--

### Operation

Source operation ID: `SveOperation_svrshl_u32_m`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Multiply `op1[i]` by 2 to the power `op2[i]`, without loss of precision.
- Round the result to nearest with ties towards +∞.
- Truncate the result to the range of `uint32_t`.



Take the inactive elements of the result from the corresponding elements of `op1`.

## svrshl[_u32]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrshl%5B_u32%5D_x

### Signature (source notation)

```c
svuint32_t svrshl[_u32]_x(svbool_t pg, svuint32_t op1, svint32_t op2);
```

### Description

Rounding shift left

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Shift / Left / Vector rounding shift left

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
  "op2": {
    "register": "Zop2.S|Ztied2.S"
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
URSHL Ztied1.S, Pg/M, Ztied1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/URSHL--Unsigned-rounding-shift-left--predicated--

When result and op2 are in the same register, this intrinsic compiles to:

```asm
URSHLR Ztied2.S, Pg/M, Ztied2.S, Zop1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/URSHR--Unsigned-rounding-shift-right-by-immediate-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
URSHL Zresult.S, Pg/M, Zresult.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/URSHL--Unsigned-rounding-shift-left--predicated--

### Operation

Source operation ID: `SveOperation_svrshl_u32_x`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Multiply `op1[i]` by 2 to the power `op2[i]`, without loss of precision.
- Round the result to nearest with ties towards +∞.
- Truncate the result to the range of `uint32_t`.



The inactive elements of the result have arbitrary, undefined values.

## svrshl[_u32]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrshl%5B_u32%5D_z

### Signature (source notation)

```c
svuint32_t svrshl[_u32]_z(svbool_t pg, svuint32_t op1, svint32_t op2);
```

### Description

Rounding shift left

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Shift / Left / Vector rounding shift left

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
  "op2": {
    "register": "Zop2.S"
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

When result is in a different register from op2, this intrinsic can use:

```asm
MOVPRFX Zresult.S, Pg/Z, Zop1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
URSHL Zresult.S, Pg/M, Zresult.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/URSHL--Unsigned-rounding-shift-left--predicated--

When result is in a different register from op1, this intrinsic can use:

```asm
MOVPRFX Zresult.S, Pg/Z, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
URSHLR Zresult.S, Pg/M, Zresult.S, Zop1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/URSHR--Unsigned-rounding-shift-right-by-immediate-

### Operation

Source operation ID: `SveOperation_svrshl_u32_z`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Multiply `op1[i]` by 2 to the power `op2[i]`, without loss of precision.
- Round the result to nearest with ties towards +∞.
- Truncate the result to the range of `uint32_t`.



Set the inactive elements of the result to zero.

## svrshl[_u64]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrshl%5B_u64%5D_m

### Signature (source notation)

```c
svuint64_t svrshl[_u64]_m(svbool_t pg, svuint64_t op1, svint64_t op2);
```

### Description

Rounding shift left

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Shift / Left / Vector rounding shift left

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
  "op2": {
    "register": "Zop2.D"
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
URSHL Ztied1.D, Pg/M, Ztied1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/URSHL--Unsigned-rounding-shift-left--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
URSHL Zresult.D, Pg/M, Zresult.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/URSHL--Unsigned-rounding-shift-left--predicated--

### Operation

Source operation ID: `SveOperation_svrshl_u64_m`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Multiply `op1[i]` by 2 to the power `op2[i]`, without loss of precision.
- Round the result to nearest with ties towards +∞.
- Truncate the result to the range of `uint64_t`.



Take the inactive elements of the result from the corresponding elements of `op1`.

## svrshl[_u64]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrshl%5B_u64%5D_x

### Signature (source notation)

```c
svuint64_t svrshl[_u64]_x(svbool_t pg, svuint64_t op1, svint64_t op2);
```

### Description

Rounding shift left

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Shift / Left / Vector rounding shift left

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
  "op2": {
    "register": "Zop2.D|Ztied2.D"
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
URSHL Ztied1.D, Pg/M, Ztied1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/URSHL--Unsigned-rounding-shift-left--predicated--

When result and op2 are in the same register, this intrinsic compiles to:

```asm
URSHLR Ztied2.D, Pg/M, Ztied2.D, Zop1.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/URSHR--Unsigned-rounding-shift-right-by-immediate-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
URSHL Zresult.D, Pg/M, Zresult.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/URSHL--Unsigned-rounding-shift-left--predicated--

### Operation

Source operation ID: `SveOperation_svrshl_u64_x`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Multiply `op1[i]` by 2 to the power `op2[i]`, without loss of precision.
- Round the result to nearest with ties towards +∞.
- Truncate the result to the range of `uint64_t`.



The inactive elements of the result have arbitrary, undefined values.

## svrshl[_u64]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrshl%5B_u64%5D_z

### Signature (source notation)

```c
svuint64_t svrshl[_u64]_z(svbool_t pg, svuint64_t op1, svint64_t op2);
```

### Description

Rounding shift left

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Shift / Left / Vector rounding shift left

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
  "op2": {
    "register": "Zop2.D"
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

When result is in a different register from op2, this intrinsic can use:

```asm
MOVPRFX Zresult.D, Pg/Z, Zop1.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
URSHL Zresult.D, Pg/M, Zresult.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/URSHL--Unsigned-rounding-shift-left--predicated--

When result is in a different register from op1, this intrinsic can use:

```asm
MOVPRFX Zresult.D, Pg/Z, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
URSHLR Zresult.D, Pg/M, Zresult.D, Zop1.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/URSHR--Unsigned-rounding-shift-right-by-immediate-

### Operation

Source operation ID: `SveOperation_svrshl_u64_z`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Multiply `op1[i]` by 2 to the power `op2[i]`, without loss of precision.
- Round the result to nearest with ties towards +∞.
- Truncate the result to the range of `uint64_t`.



Set the inactive elements of the result to zero.

## svrshl[_u8]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrshl%5B_u8%5D_m

### Signature (source notation)

```c
svuint8_t svrshl[_u8]_m(svbool_t pg, svuint8_t op1, svint8_t op2);
```

### Description

Rounding shift left

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Shift / Left / Vector rounding shift left

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
  "op2": {
    "register": "Zop2.B"
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
URSHL Ztied1.B, Pg/M, Ztied1.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/URSHL--Unsigned-rounding-shift-left--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
URSHL Zresult.B, Pg/M, Zresult.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/URSHL--Unsigned-rounding-shift-left--predicated--

### Operation

Source operation ID: `SveOperation_svrshl_u8_m`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Multiply `op1[i]` by 2 to the power `op2[i]`, without loss of precision.
- Round the result to nearest with ties towards +∞.
- Truncate the result to the range of `uint8_t`.



Take the inactive elements of the result from the corresponding elements of `op1`.

## svrshl[_u8]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrshl%5B_u8%5D_x

### Signature (source notation)

```c
svuint8_t svrshl[_u8]_x(svbool_t pg, svuint8_t op1, svint8_t op2);
```

### Description

Rounding shift left

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Shift / Left / Vector rounding shift left

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
  "op2": {
    "register": "Zop2.B|Ztied2.B"
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
URSHL Ztied1.B, Pg/M, Ztied1.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/URSHL--Unsigned-rounding-shift-left--predicated--

When result and op2 are in the same register, this intrinsic compiles to:

```asm
URSHLR Ztied2.B, Pg/M, Ztied2.B, Zop1.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/URSHR--Unsigned-rounding-shift-right-by-immediate-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
URSHL Zresult.B, Pg/M, Zresult.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/URSHL--Unsigned-rounding-shift-left--predicated--

### Operation

Source operation ID: `SveOperation_svrshl_u8_x`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Multiply `op1[i]` by 2 to the power `op2[i]`, without loss of precision.
- Round the result to nearest with ties towards +∞.
- Truncate the result to the range of `uint8_t`.



The inactive elements of the result have arbitrary, undefined values.

## svrshl[_u8]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrshl%5B_u8%5D_z

### Signature (source notation)

```c
svuint8_t svrshl[_u8]_z(svbool_t pg, svuint8_t op1, svint8_t op2);
```

### Description

Rounding shift left

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Shift / Left / Vector rounding shift left

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
  "op2": {
    "register": "Zop2.B"
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

When result is in a different register from op2, this intrinsic can use:

```asm
MOVPRFX Zresult.B, Pg/Z, Zop1.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
URSHL Zresult.B, Pg/M, Zresult.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/URSHL--Unsigned-rounding-shift-left--predicated--

When result is in a different register from op1, this intrinsic can use:

```asm
MOVPRFX Zresult.B, Pg/Z, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
URSHLR Zresult.B, Pg/M, Zresult.B, Zop1.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/URSHR--Unsigned-rounding-shift-right-by-immediate-

### Operation

Source operation ID: `SveOperation_svrshl_u8_z`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Multiply `op1[i]` by 2 to the power `op2[i]`, without loss of precision.
- Round the result to nearest with ties towards +∞.
- Truncate the result to the range of `uint8_t`.



Set the inactive elements of the result to zero.

