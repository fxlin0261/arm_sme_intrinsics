# SME / Shift / Left / Vector shift left — Part 2

## svlsl_wide[_n_s16]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svlsl_wide%5B_n_s16%5D_z

### Signature (source notation)

```c
svint16_t svlsl_wide[_n_s16]_z(svbool_t pg, svint16_t op1, uint64_t op2);
```

### Description

Logical shift left

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Shift / Left / Vector shift left

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
    "register": "Zop2.D[*]"
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

The general implementation is:

```asm
MOVPRFX Zresult.H, Pg/Z, Zop1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
LSL Zresult.H, Pg/M, Zresult.H, Zop2.D  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSL--wide-elements--predicated---Logical-shift-left-by-64-bit-wide-elements--predicated--

### Operation

Source operation ID: `SveOperation_svlsl_wide_n_s16_z`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Multiply `op1[i]` by two to the power `op2`, without loss of precision.
- Truncate the result to the range of `int16_t`.



All bits of the `op2` value are significant.



Set the inactive elements of the result to zero.



**[1]** Note that `result` must be in a different register from `op2`

## svlsl_wide[_n_s32]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svlsl_wide%5B_n_s32%5D_m

### Signature (source notation)

```c
svint32_t svlsl_wide[_n_s32]_m(svbool_t pg, svint32_t op1, uint64_t op2);
```

### Description

Logical shift left

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Shift / Left / Vector shift left

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
    "register": "Zop2.D[*]"
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

The general implementation is:

```asm
LSL Ztied1.S, Pg/M, Ztied1.S, Zop2.D  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSL--wide-elements--predicated---Logical-shift-left-by-64-bit-wide-elements--predicated--

### Operation

Source operation ID: `SveOperation_svlsl_n_s32_m`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Multiply `op1[i]` by two to the power `op2`, without loss of precision.
- Truncate the result to the range of `int32_t`.



All bits of the `op2` value are significant.



Take the inactive elements of the result from the corresponding elements of `op1`.



**[1]** If instead `result` is in a different register from the inputs, the compiler can add a preceding [MOVPRFX (unpredicated)](https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--) instruction

## svlsl_wide[_n_s32]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svlsl_wide%5B_n_s32%5D_x

### Signature (source notation)

```c
svint32_t svlsl_wide[_n_s32]_x(svbool_t pg, svint32_t op1, uint64_t op2);
```

### Description

Logical shift left

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Shift / Left / Vector shift left

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
    "register": "Zop2.D[*]"
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

When op2 is in the range [0, 31], this intrinsic can use:

```asm
LSL Zresult.S, Zop1.S, #op2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSL--immediate--unpredicated---Logical-shift-left-by-immediate--unpredicated--

When result and op1 are in the same register, this intrinsic can use:

```asm
LSL Ztied1.S, Pg/M, Ztied1.S, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSL--wide-elements--predicated---Logical-shift-left-by-64-bit-wide-elements--predicated--

The general implementation is:

```asm
LSL Zresult.S, Zop1.S, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSL--wide-elements--unpredicated---Logical-shift-left-by-64-bit-wide-elements--unpredicated--

### Operation

Source operation ID: `SveOperation_svlsl_n_s32_x`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Multiply `op1[i]` by two to the power `op2`, without loss of precision.
- Truncate the result to the range of `int32_t`.



All bits of the `op2` value are significant.



The inactive elements of the result have arbitrary, undefined values.

## svlsl_wide[_n_s32]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svlsl_wide%5B_n_s32%5D_z

### Signature (source notation)

```c
svint32_t svlsl_wide[_n_s32]_z(svbool_t pg, svint32_t op1, uint64_t op2);
```

### Description

Logical shift left

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Shift / Left / Vector shift left

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
    "register": "Zop2.D[*]"
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

The general implementation is:

```asm
MOVPRFX Zresult.S, Pg/Z, Zop1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
LSL Zresult.S, Pg/M, Zresult.S, Zop2.D  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSL--wide-elements--predicated---Logical-shift-left-by-64-bit-wide-elements--predicated--

### Operation

Source operation ID: `SveOperation_svlsl_wide_n_s32_z`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Multiply `op1[i]` by two to the power `op2`, without loss of precision.
- Truncate the result to the range of `int32_t`.



All bits of the `op2` value are significant.



Set the inactive elements of the result to zero.



**[1]** Note that `result` must be in a different register from `op2`

## svlsl_wide[_n_s8]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svlsl_wide%5B_n_s8%5D_m

### Signature (source notation)

```c
svint8_t svlsl_wide[_n_s8]_m(svbool_t pg, svint8_t op1, uint64_t op2);
```

### Description

Logical shift left

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Shift / Left / Vector shift left

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
    "register": "Zop2.D[*]"
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

The general implementation is:

```asm
LSL Ztied1.B, Pg/M, Ztied1.B, Zop2.D  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSL--wide-elements--predicated---Logical-shift-left-by-64-bit-wide-elements--predicated--

### Operation

Source operation ID: `SveOperation_svlsl_n_s8_m`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Multiply `op1[i]` by two to the power `op2`, without loss of precision.
- Truncate the result to the range of `int8_t`.



All bits of the `op2` value are significant.



Take the inactive elements of the result from the corresponding elements of `op1`.



**[1]** If instead `result` is in a different register from the inputs, the compiler can add a preceding [MOVPRFX (unpredicated)](https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--) instruction

## svlsl_wide[_n_s8]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svlsl_wide%5B_n_s8%5D_x

### Signature (source notation)

```c
svint8_t svlsl_wide[_n_s8]_x(svbool_t pg, svint8_t op1, uint64_t op2);
```

### Description

Logical shift left

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Shift / Left / Vector shift left

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
    "register": "Zop2.D[*]"
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

When op2 is in the range [0, 7], this intrinsic can use:

```asm
LSL Zresult.B, Zop1.B, #op2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSL--immediate--unpredicated---Logical-shift-left-by-immediate--unpredicated--

When result and op1 are in the same register, this intrinsic can use:

```asm
LSL Ztied1.B, Pg/M, Ztied1.B, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSL--wide-elements--predicated---Logical-shift-left-by-64-bit-wide-elements--predicated--

The general implementation is:

```asm
LSL Zresult.B, Zop1.B, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSL--wide-elements--unpredicated---Logical-shift-left-by-64-bit-wide-elements--unpredicated--

### Operation

Source operation ID: `SveOperation_svlsl_n_s8_x`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Multiply `op1[i]` by two to the power `op2`, without loss of precision.
- Truncate the result to the range of `int8_t`.



All bits of the `op2` value are significant.



The inactive elements of the result have arbitrary, undefined values.

## svlsl_wide[_n_s8]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svlsl_wide%5B_n_s8%5D_z

### Signature (source notation)

```c
svint8_t svlsl_wide[_n_s8]_z(svbool_t pg, svint8_t op1, uint64_t op2);
```

### Description

Logical shift left

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Shift / Left / Vector shift left

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
    "register": "Zop2.D[*]"
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

The general implementation is:

```asm
MOVPRFX Zresult.B, Pg/Z, Zop1.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
LSL Zresult.B, Pg/M, Zresult.B, Zop2.D  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSL--wide-elements--predicated---Logical-shift-left-by-64-bit-wide-elements--predicated--

### Operation

Source operation ID: `SveOperation_svlsl_wide_n_s8_z`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Multiply `op1[i]` by two to the power `op2`, without loss of precision.
- Truncate the result to the range of `int8_t`.



All bits of the `op2` value are significant.



Set the inactive elements of the result to zero.



**[1]** Note that `result` must be in a different register from `op2`

## svlsl_wide[_n_u16]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svlsl_wide%5B_n_u16%5D_m

### Signature (source notation)

```c
svuint16_t svlsl_wide[_n_u16]_m(svbool_t pg, svuint16_t op1, uint64_t op2);
```

### Description

Logical shift left

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Shift / Left / Vector shift left

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
    "register": "Zop2.D[*]"
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

The general implementation is:

```asm
LSL Ztied1.H, Pg/M, Ztied1.H, Zop2.D  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSL--wide-elements--predicated---Logical-shift-left-by-64-bit-wide-elements--predicated--

### Operation

Source operation ID: `SveOperation_svlsl_n_u16_m`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Multiply `op1[i]` by two to the power `op2`, without loss of precision.
- Truncate the result to the range of `uint16_t`.



All bits of the `op2` value are significant.



Take the inactive elements of the result from the corresponding elements of `op1`.



**[1]** If instead `result` is in a different register from the inputs, the compiler can add a preceding [MOVPRFX (unpredicated)](https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--) instruction

## svlsl_wide[_n_u16]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svlsl_wide%5B_n_u16%5D_x

### Signature (source notation)

```c
svuint16_t svlsl_wide[_n_u16]_x(svbool_t pg, svuint16_t op1, uint64_t op2);
```

### Description

Logical shift left

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Shift / Left / Vector shift left

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
    "register": "Zop2.D[*]"
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

When op2 is in the range [0, 15], this intrinsic can use:

```asm
LSL Zresult.H, Zop1.H, #op2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSL--immediate--unpredicated---Logical-shift-left-by-immediate--unpredicated--

When result and op1 are in the same register, this intrinsic can use:

```asm
LSL Ztied1.H, Pg/M, Ztied1.H, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSL--wide-elements--predicated---Logical-shift-left-by-64-bit-wide-elements--predicated--

The general implementation is:

```asm
LSL Zresult.H, Zop1.H, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSL--wide-elements--unpredicated---Logical-shift-left-by-64-bit-wide-elements--unpredicated--

### Operation

Source operation ID: `SveOperation_svlsl_n_u16_x`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Multiply `op1[i]` by two to the power `op2`, without loss of precision.
- Truncate the result to the range of `uint16_t`.



All bits of the `op2` value are significant.



The inactive elements of the result have arbitrary, undefined values.

## svlsl_wide[_n_u16]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svlsl_wide%5B_n_u16%5D_z

### Signature (source notation)

```c
svuint16_t svlsl_wide[_n_u16]_z(svbool_t pg, svuint16_t op1, uint64_t op2);
```

### Description

Logical shift left

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Shift / Left / Vector shift left

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
    "register": "Zop2.D[*]"
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

The general implementation is:

```asm
MOVPRFX Zresult.H, Pg/Z, Zop1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
LSL Zresult.H, Pg/M, Zresult.H, Zop2.D  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSL--wide-elements--predicated---Logical-shift-left-by-64-bit-wide-elements--predicated--

### Operation

Source operation ID: `SveOperation_svlsl_wide_n_u16_z`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Multiply `op1[i]` by two to the power `op2`, without loss of precision.
- Truncate the result to the range of `uint16_t`.



All bits of the `op2` value are significant.



Set the inactive elements of the result to zero.



**[1]** Note that `result` must be in a different register from `op2`

## svlsl_wide[_n_u32]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svlsl_wide%5B_n_u32%5D_m

### Signature (source notation)

```c
svuint32_t svlsl_wide[_n_u32]_m(svbool_t pg, svuint32_t op1, uint64_t op2);
```

### Description

Logical shift left

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Shift / Left / Vector shift left

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
    "register": "Zop2.D[*]"
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

The general implementation is:

```asm
LSL Ztied1.S, Pg/M, Ztied1.S, Zop2.D  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSL--wide-elements--predicated---Logical-shift-left-by-64-bit-wide-elements--predicated--

### Operation

Source operation ID: `SveOperation_svlsl_n_u32_m`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Multiply `op1[i]` by two to the power `op2`, without loss of precision.
- Truncate the result to the range of `uint32_t`.



All bits of the `op2` value are significant.



Take the inactive elements of the result from the corresponding elements of `op1`.



**[1]** If instead `result` is in a different register from the inputs, the compiler can add a preceding [MOVPRFX (unpredicated)](https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--) instruction

## svlsl_wide[_n_u32]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svlsl_wide%5B_n_u32%5D_x

### Signature (source notation)

```c
svuint32_t svlsl_wide[_n_u32]_x(svbool_t pg, svuint32_t op1, uint64_t op2);
```

### Description

Logical shift left

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Shift / Left / Vector shift left

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
    "register": "Zop2.D[*]"
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

When op2 is in the range [0, 31], this intrinsic can use:

```asm
LSL Zresult.S, Zop1.S, #op2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSL--immediate--unpredicated---Logical-shift-left-by-immediate--unpredicated--

When result and op1 are in the same register, this intrinsic can use:

```asm
LSL Ztied1.S, Pg/M, Ztied1.S, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSL--wide-elements--predicated---Logical-shift-left-by-64-bit-wide-elements--predicated--

The general implementation is:

```asm
LSL Zresult.S, Zop1.S, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSL--wide-elements--unpredicated---Logical-shift-left-by-64-bit-wide-elements--unpredicated--

### Operation

Source operation ID: `SveOperation_svlsl_n_u32_x`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Multiply `op1[i]` by two to the power `op2`, without loss of precision.
- Truncate the result to the range of `uint32_t`.



All bits of the `op2` value are significant.



The inactive elements of the result have arbitrary, undefined values.

## svlsl_wide[_n_u32]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svlsl_wide%5B_n_u32%5D_z

### Signature (source notation)

```c
svuint32_t svlsl_wide[_n_u32]_z(svbool_t pg, svuint32_t op1, uint64_t op2);
```

### Description

Logical shift left

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Shift / Left / Vector shift left

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
    "register": "Zop2.D[*]"
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

The general implementation is:

```asm
MOVPRFX Zresult.S, Pg/Z, Zop1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
LSL Zresult.S, Pg/M, Zresult.S, Zop2.D  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSL--wide-elements--predicated---Logical-shift-left-by-64-bit-wide-elements--predicated--

### Operation

Source operation ID: `SveOperation_svlsl_wide_n_u32_z`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Multiply `op1[i]` by two to the power `op2`, without loss of precision.
- Truncate the result to the range of `uint32_t`.



All bits of the `op2` value are significant.



Set the inactive elements of the result to zero.



**[1]** Note that `result` must be in a different register from `op2`

## svlsl_wide[_n_u8]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svlsl_wide%5B_n_u8%5D_m

### Signature (source notation)

```c
svuint8_t svlsl_wide[_n_u8]_m(svbool_t pg, svuint8_t op1, uint64_t op2);
```

### Description

Logical shift left

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Shift / Left / Vector shift left

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
    "register": "Zop2.D[*]"
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

The general implementation is:

```asm
LSL Ztied1.B, Pg/M, Ztied1.B, Zop2.D  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSL--wide-elements--predicated---Logical-shift-left-by-64-bit-wide-elements--predicated--

### Operation

Source operation ID: `SveOperation_svlsl_n_u8_m`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Multiply `op1[i]` by two to the power `op2`, without loss of precision.
- Truncate the result to the range of `uint8_t`.



All bits of the `op2` value are significant.



Take the inactive elements of the result from the corresponding elements of `op1`.



**[1]** If instead `result` is in a different register from the inputs, the compiler can add a preceding [MOVPRFX (unpredicated)](https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--) instruction

## svlsl_wide[_n_u8]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svlsl_wide%5B_n_u8%5D_x

### Signature (source notation)

```c
svuint8_t svlsl_wide[_n_u8]_x(svbool_t pg, svuint8_t op1, uint64_t op2);
```

### Description

Logical shift left

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Shift / Left / Vector shift left

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
    "register": "Zop2.D[*]"
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

When op2 is in the range [0, 7], this intrinsic can use:

```asm
LSL Zresult.B, Zop1.B, #op2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSL--immediate--unpredicated---Logical-shift-left-by-immediate--unpredicated--

When result and op1 are in the same register, this intrinsic can use:

```asm
LSL Ztied1.B, Pg/M, Ztied1.B, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSL--wide-elements--predicated---Logical-shift-left-by-64-bit-wide-elements--predicated--

The general implementation is:

```asm
LSL Zresult.B, Zop1.B, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSL--wide-elements--unpredicated---Logical-shift-left-by-64-bit-wide-elements--unpredicated--

### Operation

Source operation ID: `SveOperation_svlsl_n_u8_x`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Multiply `op1[i]` by two to the power `op2`, without loss of precision.
- Truncate the result to the range of `uint8_t`.



All bits of the `op2` value are significant.



The inactive elements of the result have arbitrary, undefined values.

## svlsl_wide[_n_u8]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svlsl_wide%5B_n_u8%5D_z

### Signature (source notation)

```c
svuint8_t svlsl_wide[_n_u8]_z(svbool_t pg, svuint8_t op1, uint64_t op2);
```

### Description

Logical shift left

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Shift / Left / Vector shift left

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
    "register": "Zop2.D[*]"
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

The general implementation is:

```asm
MOVPRFX Zresult.B, Pg/Z, Zop1.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
LSL Zresult.B, Pg/M, Zresult.B, Zop2.D  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSL--wide-elements--predicated---Logical-shift-left-by-64-bit-wide-elements--predicated--

### Operation

Source operation ID: `SveOperation_svlsl_wide_n_u8_z`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Multiply `op1[i]` by two to the power `op2`, without loss of precision.
- Truncate the result to the range of `uint8_t`.



All bits of the `op2` value are significant.



Set the inactive elements of the result to zero.



**[1]** Note that `result` must be in a different register from `op2`

## svlsl_wide[_s16]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svlsl_wide%5B_s16%5D_m

### Signature (source notation)

```c
svint16_t svlsl_wide[_s16]_m(svbool_t pg, svint16_t op1, svuint64_t op2);
```

### Description

Logical shift left

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Shift / Left / Vector shift left

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
    "register": "Zop2.D"
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
LSL Ztied1.H, Pg/M, Ztied1.H, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSL--wide-elements--predicated---Logical-shift-left-by-64-bit-wide-elements--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
LSL Zresult.H, Pg/M, Zresult.H, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSL--wide-elements--predicated---Logical-shift-left-by-64-bit-wide-elements--predicated--

### Operation

Source operation ID: `SveOperation_svlsl_wide_s16_m`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Multiply `op1[i]` by two to the power `op2[i/4]`, without loss of precision.
- Truncate the result to the range of `int16_t`.



All bits of the `op2` value are significant.



Take the inactive elements of the result from the corresponding elements of `op1`.

## svlsl_wide[_s16]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svlsl_wide%5B_s16%5D_x

### Signature (source notation)

```c
svint16_t svlsl_wide[_s16]_x(svbool_t pg, svint16_t op1, svuint64_t op2);
```

### Description

Logical shift left

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Shift / Left / Vector shift left

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
    "register": "Zop2.D"
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

When result and op1 are in the same register, this intrinsic can use:

```asm
LSL Ztied1.H, Pg/M, Ztied1.H, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSL--wide-elements--predicated---Logical-shift-left-by-64-bit-wide-elements--predicated--

This intrinsic compiles to:

```asm
LSL Zresult.H, Zop1.H, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSL--wide-elements--unpredicated---Logical-shift-left-by-64-bit-wide-elements--unpredicated--

### Operation

Source operation ID: `SveOperation_svlsl_wide_s16_x`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Multiply `op1[i]` by two to the power `op2[i/4]`, without loss of precision.
- Truncate the result to the range of `int16_t`.



All bits of the `op2` value are significant.



The inactive elements of the result have arbitrary, undefined values.

## svlsl_wide[_s16]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svlsl_wide%5B_s16%5D_z

### Signature (source notation)

```c
svint16_t svlsl_wide[_s16]_z(svbool_t pg, svint16_t op1, svuint64_t op2);
```

### Description

Logical shift left

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Shift / Left / Vector shift left

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
    "register": "Zop2.D"
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
LSL Zresult.H, Pg/M, Zresult.H, Zop2.D  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSL--wide-elements--predicated---Logical-shift-left-by-64-bit-wide-elements--predicated--

### Operation

Source operation ID: `SveOperation_svlsl_wide_s16_z`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Multiply `op1[i]` by two to the power `op2[i/4]`, without loss of precision.
- Truncate the result to the range of `int16_t`.



All bits of the `op2` value are significant.



Set the inactive elements of the result to zero.



**[1]** Note that `result` must be in a different register from `op2`

## svlsl_wide[_s32]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svlsl_wide%5B_s32%5D_m

### Signature (source notation)

```c
svint32_t svlsl_wide[_s32]_m(svbool_t pg, svint32_t op1, svuint64_t op2);
```

### Description

Logical shift left

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Shift / Left / Vector shift left

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
    "register": "Zop2.D"
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
LSL Ztied1.S, Pg/M, Ztied1.S, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSL--wide-elements--predicated---Logical-shift-left-by-64-bit-wide-elements--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
LSL Zresult.S, Pg/M, Zresult.S, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSL--wide-elements--predicated---Logical-shift-left-by-64-bit-wide-elements--predicated--

### Operation

Source operation ID: `SveOperation_svlsl_wide_s32_m`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Multiply `op1[i]` by two to the power `op2[i/2]`, without loss of precision.
- Truncate the result to the range of `int32_t`.



All bits of the `op2` value are significant.



Take the inactive elements of the result from the corresponding elements of `op1`.

## svlsl_wide[_s32]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svlsl_wide%5B_s32%5D_x

### Signature (source notation)

```c
svint32_t svlsl_wide[_s32]_x(svbool_t pg, svint32_t op1, svuint64_t op2);
```

### Description

Logical shift left

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Shift / Left / Vector shift left

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
    "register": "Zop2.D"
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

When result and op1 are in the same register, this intrinsic can use:

```asm
LSL Ztied1.S, Pg/M, Ztied1.S, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSL--wide-elements--predicated---Logical-shift-left-by-64-bit-wide-elements--predicated--

This intrinsic compiles to:

```asm
LSL Zresult.S, Zop1.S, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSL--wide-elements--unpredicated---Logical-shift-left-by-64-bit-wide-elements--unpredicated--

### Operation

Source operation ID: `SveOperation_svlsl_wide_s32_x`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Multiply `op1[i]` by two to the power `op2[i/2]`, without loss of precision.
- Truncate the result to the range of `int32_t`.



All bits of the `op2` value are significant.



The inactive elements of the result have arbitrary, undefined values.

## svlsl_wide[_s32]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svlsl_wide%5B_s32%5D_z

### Signature (source notation)

```c
svint32_t svlsl_wide[_s32]_z(svbool_t pg, svint32_t op1, svuint64_t op2);
```

### Description

Logical shift left

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Shift / Left / Vector shift left

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
    "register": "Zop2.D"
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
LSL Zresult.S, Pg/M, Zresult.S, Zop2.D  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSL--wide-elements--predicated---Logical-shift-left-by-64-bit-wide-elements--predicated--

### Operation

Source operation ID: `SveOperation_svlsl_wide_s32_z`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Multiply `op1[i]` by two to the power `op2[i/2]`, without loss of precision.
- Truncate the result to the range of `int32_t`.



All bits of the `op2` value are significant.



Set the inactive elements of the result to zero.



**[1]** Note that `result` must be in a different register from `op2`

## svlsl_wide[_s8]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svlsl_wide%5B_s8%5D_m

### Signature (source notation)

```c
svint8_t svlsl_wide[_s8]_m(svbool_t pg, svint8_t op1, svuint64_t op2);
```

### Description

Logical shift left

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Shift / Left / Vector shift left

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
    "register": "Zop2.D"
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
LSL Ztied1.B, Pg/M, Ztied1.B, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSL--wide-elements--predicated---Logical-shift-left-by-64-bit-wide-elements--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
LSL Zresult.B, Pg/M, Zresult.B, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSL--wide-elements--predicated---Logical-shift-left-by-64-bit-wide-elements--predicated--

### Operation

Source operation ID: `SveOperation_svlsl_wide_s8_m`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Multiply `op1[i]` by two to the power `op2[i/8]`, without loss of precision.
- Truncate the result to the range of `int8_t`.



All bits of the `op2` value are significant.



Take the inactive elements of the result from the corresponding elements of `op1`.

## svlsl_wide[_s8]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svlsl_wide%5B_s8%5D_x

### Signature (source notation)

```c
svint8_t svlsl_wide[_s8]_x(svbool_t pg, svint8_t op1, svuint64_t op2);
```

### Description

Logical shift left

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Shift / Left / Vector shift left

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
    "register": "Zop2.D"
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

When result and op1 are in the same register, this intrinsic can use:

```asm
LSL Ztied1.B, Pg/M, Ztied1.B, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSL--wide-elements--predicated---Logical-shift-left-by-64-bit-wide-elements--predicated--

This intrinsic compiles to:

```asm
LSL Zresult.B, Zop1.B, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSL--wide-elements--unpredicated---Logical-shift-left-by-64-bit-wide-elements--unpredicated--

### Operation

Source operation ID: `SveOperation_svlsl_wide_s8_x`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Multiply `op1[i]` by two to the power `op2[i/8]`, without loss of precision.
- Truncate the result to the range of `int8_t`.



All bits of the `op2` value are significant.



The inactive elements of the result have arbitrary, undefined values.

## svlsl_wide[_s8]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svlsl_wide%5B_s8%5D_z

### Signature (source notation)

```c
svint8_t svlsl_wide[_s8]_z(svbool_t pg, svint8_t op1, svuint64_t op2);
```

### Description

Logical shift left

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Shift / Left / Vector shift left

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
    "register": "Zop2.D"
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
LSL Zresult.B, Pg/M, Zresult.B, Zop2.D  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSL--wide-elements--predicated---Logical-shift-left-by-64-bit-wide-elements--predicated--

### Operation

Source operation ID: `SveOperation_svlsl_wide_s8_z`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Multiply `op1[i]` by two to the power `op2[i/8]`, without loss of precision.
- Truncate the result to the range of `int8_t`.



All bits of the `op2` value are significant.



Set the inactive elements of the result to zero.



**[1]** Note that `result` must be in a different register from `op2`

## svlsl_wide[_u16]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svlsl_wide%5B_u16%5D_m

### Signature (source notation)

```c
svuint16_t svlsl_wide[_u16]_m(svbool_t pg, svuint16_t op1, svuint64_t op2);
```

### Description

Logical shift left

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Shift / Left / Vector shift left

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
    "register": "Zop2.D"
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
LSL Ztied1.H, Pg/M, Ztied1.H, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSL--wide-elements--predicated---Logical-shift-left-by-64-bit-wide-elements--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
LSL Zresult.H, Pg/M, Zresult.H, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSL--wide-elements--predicated---Logical-shift-left-by-64-bit-wide-elements--predicated--

### Operation

Source operation ID: `SveOperation_svlsl_wide_u16_m`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Multiply `op1[i]` by two to the power `op2[i/4]`, without loss of precision.
- Truncate the result to the range of `uint16_t`.



All bits of the `op2` value are significant.



Take the inactive elements of the result from the corresponding elements of `op1`.

## svlsl_wide[_u16]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svlsl_wide%5B_u16%5D_x

### Signature (source notation)

```c
svuint16_t svlsl_wide[_u16]_x(svbool_t pg, svuint16_t op1, svuint64_t op2);
```

### Description

Logical shift left

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Shift / Left / Vector shift left

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
    "register": "Zop2.D"
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

When result and op1 are in the same register, this intrinsic can use:

```asm
LSL Ztied1.H, Pg/M, Ztied1.H, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSL--wide-elements--predicated---Logical-shift-left-by-64-bit-wide-elements--predicated--

This intrinsic compiles to:

```asm
LSL Zresult.H, Zop1.H, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSL--wide-elements--unpredicated---Logical-shift-left-by-64-bit-wide-elements--unpredicated--

### Operation

Source operation ID: `SveOperation_svlsl_wide_u16_x`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Multiply `op1[i]` by two to the power `op2[i/4]`, without loss of precision.
- Truncate the result to the range of `uint16_t`.



All bits of the `op2` value are significant.



The inactive elements of the result have arbitrary, undefined values.

## svlsl_wide[_u16]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svlsl_wide%5B_u16%5D_z

### Signature (source notation)

```c
svuint16_t svlsl_wide[_u16]_z(svbool_t pg, svuint16_t op1, svuint64_t op2);
```

### Description

Logical shift left

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Shift / Left / Vector shift left

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
    "register": "Zop2.D"
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
LSL Zresult.H, Pg/M, Zresult.H, Zop2.D  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSL--wide-elements--predicated---Logical-shift-left-by-64-bit-wide-elements--predicated--

### Operation

Source operation ID: `SveOperation_svlsl_wide_u16_z`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Multiply `op1[i]` by two to the power `op2[i/4]`, without loss of precision.
- Truncate the result to the range of `uint16_t`.



All bits of the `op2` value are significant.



Set the inactive elements of the result to zero.



**[1]** Note that `result` must be in a different register from `op2`

## svlsl_wide[_u32]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svlsl_wide%5B_u32%5D_m

### Signature (source notation)

```c
svuint32_t svlsl_wide[_u32]_m(svbool_t pg, svuint32_t op1, svuint64_t op2);
```

### Description

Logical shift left

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Shift / Left / Vector shift left

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
    "register": "Zop2.D"
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
LSL Ztied1.S, Pg/M, Ztied1.S, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSL--wide-elements--predicated---Logical-shift-left-by-64-bit-wide-elements--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
LSL Zresult.S, Pg/M, Zresult.S, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSL--wide-elements--predicated---Logical-shift-left-by-64-bit-wide-elements--predicated--

### Operation

Source operation ID: `SveOperation_svlsl_wide_u32_m`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Multiply `op1[i]` by two to the power `op2[i/2]`, without loss of precision.
- Truncate the result to the range of `uint32_t`.



All bits of the `op2` value are significant.



Take the inactive elements of the result from the corresponding elements of `op1`.

## svlsl_wide[_u32]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svlsl_wide%5B_u32%5D_x

### Signature (source notation)

```c
svuint32_t svlsl_wide[_u32]_x(svbool_t pg, svuint32_t op1, svuint64_t op2);
```

### Description

Logical shift left

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Shift / Left / Vector shift left

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
    "register": "Zop2.D"
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

When result and op1 are in the same register, this intrinsic can use:

```asm
LSL Ztied1.S, Pg/M, Ztied1.S, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSL--wide-elements--predicated---Logical-shift-left-by-64-bit-wide-elements--predicated--

This intrinsic compiles to:

```asm
LSL Zresult.S, Zop1.S, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSL--wide-elements--unpredicated---Logical-shift-left-by-64-bit-wide-elements--unpredicated--

### Operation

Source operation ID: `SveOperation_svlsl_wide_u32_x`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Multiply `op1[i]` by two to the power `op2[i/2]`, without loss of precision.
- Truncate the result to the range of `uint32_t`.



All bits of the `op2` value are significant.



The inactive elements of the result have arbitrary, undefined values.

## svlsl_wide[_u32]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svlsl_wide%5B_u32%5D_z

### Signature (source notation)

```c
svuint32_t svlsl_wide[_u32]_z(svbool_t pg, svuint32_t op1, svuint64_t op2);
```

### Description

Logical shift left

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Shift / Left / Vector shift left

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
    "register": "Zop2.D"
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
LSL Zresult.S, Pg/M, Zresult.S, Zop2.D  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSL--wide-elements--predicated---Logical-shift-left-by-64-bit-wide-elements--predicated--

### Operation

Source operation ID: `SveOperation_svlsl_wide_u32_z`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Multiply `op1[i]` by two to the power `op2[i/2]`, without loss of precision.
- Truncate the result to the range of `uint32_t`.



All bits of the `op2` value are significant.



Set the inactive elements of the result to zero.



**[1]** Note that `result` must be in a different register from `op2`

## svlsl_wide[_u8]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svlsl_wide%5B_u8%5D_m

### Signature (source notation)

```c
svuint8_t svlsl_wide[_u8]_m(svbool_t pg, svuint8_t op1, svuint64_t op2);
```

### Description

Logical shift left

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Shift / Left / Vector shift left

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
    "register": "Zop2.D"
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
LSL Ztied1.B, Pg/M, Ztied1.B, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSL--wide-elements--predicated---Logical-shift-left-by-64-bit-wide-elements--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
LSL Zresult.B, Pg/M, Zresult.B, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSL--wide-elements--predicated---Logical-shift-left-by-64-bit-wide-elements--predicated--

### Operation

Source operation ID: `SveOperation_svlsl_wide_u8_m`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Multiply `op1[i]` by two to the power `op2[i/8]`, without loss of precision.
- Truncate the result to the range of `uint8_t`.



All bits of the `op2` value are significant.



Take the inactive elements of the result from the corresponding elements of `op1`.

## svlsl_wide[_u8]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svlsl_wide%5B_u8%5D_x

### Signature (source notation)

```c
svuint8_t svlsl_wide[_u8]_x(svbool_t pg, svuint8_t op1, svuint64_t op2);
```

### Description

Logical shift left

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Shift / Left / Vector shift left

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
    "register": "Zop2.D"
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

When result and op1 are in the same register, this intrinsic can use:

```asm
LSL Ztied1.B, Pg/M, Ztied1.B, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSL--wide-elements--predicated---Logical-shift-left-by-64-bit-wide-elements--predicated--

This intrinsic compiles to:

```asm
LSL Zresult.B, Zop1.B, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSL--wide-elements--unpredicated---Logical-shift-left-by-64-bit-wide-elements--unpredicated--

### Operation

Source operation ID: `SveOperation_svlsl_wide_u8_x`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Multiply `op1[i]` by two to the power `op2[i/8]`, without loss of precision.
- Truncate the result to the range of `uint8_t`.



All bits of the `op2` value are significant.



The inactive elements of the result have arbitrary, undefined values.

## svlsl_wide[_u8]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svlsl_wide%5B_u8%5D_z

### Signature (source notation)

```c
svuint8_t svlsl_wide[_u8]_z(svbool_t pg, svuint8_t op1, svuint64_t op2);
```

### Description

Logical shift left

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Shift / Left / Vector shift left

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
    "register": "Zop2.D"
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
LSL Zresult.B, Pg/M, Zresult.B, Zop2.D  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSL--wide-elements--predicated---Logical-shift-left-by-64-bit-wide-elements--predicated--

### Operation

Source operation ID: `SveOperation_svlsl_wide_u8_z`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Multiply `op1[i]` by two to the power `op2[i/8]`, without loss of precision.
- Truncate the result to the range of `uint8_t`.



All bits of the `op2` value are significant.



Set the inactive elements of the result to zero.



**[1]** Note that `result` must be in a different register from `op2`

