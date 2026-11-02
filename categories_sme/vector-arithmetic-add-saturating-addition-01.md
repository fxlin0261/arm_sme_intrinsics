# SME / Vector arithmetic / Add / Saturating addition — Part 1

## svqadd[_n_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqadd%5B_n_s16%5D

### Signature (source notation)

```c
svint16_t svqadd[_n_s16](svint16_t op1, int16_t op2);
```

### Description

Saturating add

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Saturating addition

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
    "register": "Zop2.H[*]"
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

When op2 is in range[1], this intrinsic can use:

```asm
SQADD Ztied1.H, Ztied1.H, #op2  // [3]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQADD--immediate---Signed-saturating-add-immediate--unpredicated--

When -op2 is in range[2], this intrinsic can use:

```asm
SQSUB Ztied1.H, Ztied1.H, #-op2  // [3]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQSUB--immediate---Signed-saturating-subtract-immediate--unpredicated--

The general implementation is:

```asm
SQADD Zresult.H, Zop1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQADD--vectors--unpredicated---Signed-saturating-add--unpredicated--

### Operation

Source operation ID: `SveOperation_svqadd_n_s16`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Add `op1[i]` and `op2` together, without loss of precision.
- Saturate the result to the range of `int16_t`.



**[1]** This is true if the value is in the range [0, 255] or is a multiple of 256 in the range [0, 32767]



**[2]** This is true if the value is in the range [0, 255] or is a multiple of 256 in the range [0, 32768]



**[3]** If instead `result` is in a different register from the inputs, the compiler can add a preceding [MOVPRFX (unpredicated)](https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--) instruction

## svqadd[_n_s16]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqadd%5B_n_s16%5D_m

### Signature (source notation)

```c
svint16_t svqadd[_n_s16]_m(svbool_t pg, svint16_t op1, int16_t op2);
```

### Description

Saturating add

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Saturating addition

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
    "register": "Zop2.H[*]"
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
SQADD Ztied1.H, Pg/M, Ztied1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQADD--vectors--predicated---Signed-saturating-addition--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SQADD Zresult.H, Pg/M, Zresult.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQADD--vectors--predicated---Signed-saturating-addition--predicated--

### Operation

Source operation ID: `SveOperation_svqadd_n_s16_m`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Add `op1[i]` and `op2` together, without loss of precision.
- Saturate the result to the range of `int16_t`.



Take the inactive elements of the result from the corresponding elements of `op1`.

## svqadd[_n_s16]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqadd%5B_n_s16%5D_x

### Signature (source notation)

```c
svint16_t svqadd[_n_s16]_x(svbool_t pg, svint16_t op1, int16_t op2);
```

### Description

Saturating add

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Saturating addition

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

When op2 is in range[1], this intrinsic can use:

```asm
SQADD Ztied1.H, Ztied1.H, #op2  // [3]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQADD--immediate---Signed-saturating-add-immediate--unpredicated--

When -op2 is in range[2], this intrinsic can use:

```asm
SQSUB Ztied1.H, Ztied1.H, #-op2  // [3]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQSUB--immediate---Signed-saturating-subtract-immediate--unpredicated--

When result and op1 are in the same register, this intrinsic can use:

```asm
SQADD Ztied1.H, Pg/M, Ztied1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQADD--vectors--predicated---Signed-saturating-addition--predicated--

When result and op2 are in the same register, this intrinsic can use:

```asm
SQADD Ztied2.H, Pg/M, Ztied2.H, Zop1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQADD--vectors--predicated---Signed-saturating-addition--predicated--

The general implementation is:

```asm
SQADD Zresult.H, Zop1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQADD--vectors--unpredicated---Signed-saturating-add--unpredicated--

### Operation

Source operation ID: `SveOperation_svqadd_n_s16_x`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Add `op1[i]` and `op2` together, without loss of precision.
- Saturate the result to the range of `int16_t`.



The inactive elements of the result have arbitrary, undefined values.



**[1]** This is true if the value is in the range [0, 255] or is a multiple of 256 in the range [0, 32767]



**[2]** This is true if the value is in the range [0, 255] or is a multiple of 256 in the range [0, 32768]



**[3]** If instead `result` is in a different register from the inputs, the compiler can add a preceding [MOVPRFX (unpredicated)](https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--) instruction

## svqadd[_n_s16]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqadd%5B_n_s16%5D_z

### Signature (source notation)

```c
svint16_t svqadd[_n_s16]_z(svbool_t pg, svint16_t op1, int16_t op2);
```

### Description

Saturating add

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Saturating addition

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

When result is in a different register from op2, this intrinsic can use:

```asm
MOVPRFX Zresult.H, Pg/Z, Zop1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
SQADD Zresult.H, Pg/M, Zresult.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQADD--vectors--predicated---Signed-saturating-addition--predicated--

When result is in a different register from op1, this intrinsic can use:

```asm
MOVPRFX Zresult.H, Pg/Z, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
SQADD Zresult.H, Pg/M, Zresult.H, Zop1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQADD--vectors--predicated---Signed-saturating-addition--predicated--

### Operation

Source operation ID: `SveOperation_svqadd_n_s16_z`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Add `op1[i]` and `op2` together, without loss of precision.
- Saturate the result to the range of `int16_t`.



Set the inactive elements of the result to zero.

## svqadd[_n_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqadd%5B_n_s32%5D

### Signature (source notation)

```c
svint32_t svqadd[_n_s32](svint32_t op1, int32_t op2);
```

### Description

Saturating add

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Saturating addition

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
    "register": "Zop2.S[*]"
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

When op2 is in range[1], this intrinsic can use:

```asm
SQADD Ztied1.S, Ztied1.S, #op2  // [2]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQADD--immediate---Signed-saturating-add-immediate--unpredicated--

When -op2 is in range[1], this intrinsic can use:

```asm
SQSUB Ztied1.S, Ztied1.S, #-op2  // [2]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQSUB--immediate---Signed-saturating-subtract-immediate--unpredicated--

The general implementation is:

```asm
SQADD Zresult.S, Zop1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQADD--vectors--unpredicated---Signed-saturating-add--unpredicated--

### Operation

Source operation ID: `SveOperation_svqadd_n_s32`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Add `op1[i]` and `op2` together, without loss of precision.
- Saturate the result to the range of `int32_t`.



**[1]** This is true if the value is in the range [0, 255] or is a multiple of 256 in the range [0, 65280]



**[2]** If instead `result` is in a different register from the inputs, the compiler can add a preceding [MOVPRFX (unpredicated)](https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--) instruction

## svqadd[_n_s32]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqadd%5B_n_s32%5D_m

### Signature (source notation)

```c
svint32_t svqadd[_n_s32]_m(svbool_t pg, svint32_t op1, int32_t op2);
```

### Description

Saturating add

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Saturating addition

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
    "register": "Zop2.S[*]"
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
SQADD Ztied1.S, Pg/M, Ztied1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQADD--vectors--predicated---Signed-saturating-addition--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SQADD Zresult.S, Pg/M, Zresult.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQADD--vectors--predicated---Signed-saturating-addition--predicated--

### Operation

Source operation ID: `SveOperation_svqadd_n_s32_m`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Add `op1[i]` and `op2` together, without loss of precision.
- Saturate the result to the range of `int32_t`.



Take the inactive elements of the result from the corresponding elements of `op1`.

## svqadd[_n_s32]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqadd%5B_n_s32%5D_x

### Signature (source notation)

```c
svint32_t svqadd[_n_s32]_x(svbool_t pg, svint32_t op1, int32_t op2);
```

### Description

Saturating add

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Saturating addition

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

When op2 is in range[1], this intrinsic can use:

```asm
SQADD Ztied1.S, Ztied1.S, #op2  // [2]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQADD--immediate---Signed-saturating-add-immediate--unpredicated--

When -op2 is in range[1], this intrinsic can use:

```asm
SQSUB Ztied1.S, Ztied1.S, #-op2  // [2]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQSUB--immediate---Signed-saturating-subtract-immediate--unpredicated--

When result and op1 are in the same register, this intrinsic can use:

```asm
SQADD Ztied1.S, Pg/M, Ztied1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQADD--vectors--predicated---Signed-saturating-addition--predicated--

When result and op2 are in the same register, this intrinsic can use:

```asm
SQADD Ztied2.S, Pg/M, Ztied2.S, Zop1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQADD--vectors--predicated---Signed-saturating-addition--predicated--

The general implementation is:

```asm
SQADD Zresult.S, Zop1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQADD--vectors--unpredicated---Signed-saturating-add--unpredicated--

### Operation

Source operation ID: `SveOperation_svqadd_n_s32_x`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Add `op1[i]` and `op2` together, without loss of precision.
- Saturate the result to the range of `int32_t`.



The inactive elements of the result have arbitrary, undefined values.



**[1]** This is true if the value is in the range [0, 255] or is a multiple of 256 in the range [0, 65280]



**[2]** If instead `result` is in a different register from the inputs, the compiler can add a preceding [MOVPRFX (unpredicated)](https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--) instruction

## svqadd[_n_s32]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqadd%5B_n_s32%5D_z

### Signature (source notation)

```c
svint32_t svqadd[_n_s32]_z(svbool_t pg, svint32_t op1, int32_t op2);
```

### Description

Saturating add

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Saturating addition

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

When result is in a different register from op2, this intrinsic can use:

```asm
MOVPRFX Zresult.S, Pg/Z, Zop1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
SQADD Zresult.S, Pg/M, Zresult.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQADD--vectors--predicated---Signed-saturating-addition--predicated--

When result is in a different register from op1, this intrinsic can use:

```asm
MOVPRFX Zresult.S, Pg/Z, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
SQADD Zresult.S, Pg/M, Zresult.S, Zop1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQADD--vectors--predicated---Signed-saturating-addition--predicated--

### Operation

Source operation ID: `SveOperation_svqadd_n_s32_z`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Add `op1[i]` and `op2` together, without loss of precision.
- Saturate the result to the range of `int32_t`.



Set the inactive elements of the result to zero.

## svqadd[_n_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqadd%5B_n_s64%5D

### Signature (source notation)

```c
svint64_t svqadd[_n_s64](svint64_t op1, int64_t op2);
```

### Description

Saturating add

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Saturating addition

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
    "register": "Zop2.D[*]"
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

When op2 is in range[1], this intrinsic can use:

```asm
SQADD Ztied1.D, Ztied1.D, #op2  // [2]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQADD--immediate---Signed-saturating-add-immediate--unpredicated--

When -op2 is in range[1], this intrinsic can use:

```asm
SQSUB Ztied1.D, Ztied1.D, #-op2  // [2]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQSUB--immediate---Signed-saturating-subtract-immediate--unpredicated--

The general implementation is:

```asm
SQADD Zresult.D, Zop1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQADD--vectors--unpredicated---Signed-saturating-add--unpredicated--

### Operation

Source operation ID: `SveOperation_svqadd_n_s64`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Add `op1[i]` and `op2` together, without loss of precision.
- Saturate the result to the range of `int64_t`.



**[1]** This is true if the value is in the range [0, 255] or is a multiple of 256 in the range [0, 65280]



**[2]** If instead `result` is in a different register from the inputs, the compiler can add a preceding [MOVPRFX (unpredicated)](https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--) instruction

## svqadd[_n_s64]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqadd%5B_n_s64%5D_m

### Signature (source notation)

```c
svint64_t svqadd[_n_s64]_m(svbool_t pg, svint64_t op1, int64_t op2);
```

### Description

Saturating add

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Saturating addition

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
    "register": "Zop2.D[*]"
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
SQADD Ztied1.D, Pg/M, Ztied1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQADD--vectors--predicated---Signed-saturating-addition--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SQADD Zresult.D, Pg/M, Zresult.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQADD--vectors--predicated---Signed-saturating-addition--predicated--

### Operation

Source operation ID: `SveOperation_svqadd_n_s64_m`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Add `op1[i]` and `op2` together, without loss of precision.
- Saturate the result to the range of `int64_t`.



Take the inactive elements of the result from the corresponding elements of `op1`.

## svqadd[_n_s64]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqadd%5B_n_s64%5D_x

### Signature (source notation)

```c
svint64_t svqadd[_n_s64]_x(svbool_t pg, svint64_t op1, int64_t op2);
```

### Description

Saturating add

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Saturating addition

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

When op2 is in range[1], this intrinsic can use:

```asm
SQADD Ztied1.D, Ztied1.D, #op2  // [2]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQADD--immediate---Signed-saturating-add-immediate--unpredicated--

When -op2 is in range[1], this intrinsic can use:

```asm
SQSUB Ztied1.D, Ztied1.D, #-op2  // [2]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQSUB--immediate---Signed-saturating-subtract-immediate--unpredicated--

When result and op1 are in the same register, this intrinsic can use:

```asm
SQADD Ztied1.D, Pg/M, Ztied1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQADD--vectors--predicated---Signed-saturating-addition--predicated--

When result and op2 are in the same register, this intrinsic can use:

```asm
SQADD Ztied2.D, Pg/M, Ztied2.D, Zop1.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQADD--vectors--predicated---Signed-saturating-addition--predicated--

The general implementation is:

```asm
SQADD Zresult.D, Zop1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQADD--vectors--unpredicated---Signed-saturating-add--unpredicated--

### Operation

Source operation ID: `SveOperation_svqadd_n_s64_x`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Add `op1[i]` and `op2` together, without loss of precision.
- Saturate the result to the range of `int64_t`.



The inactive elements of the result have arbitrary, undefined values.



**[1]** This is true if the value is in the range [0, 255] or is a multiple of 256 in the range [0, 65280]



**[2]** If instead `result` is in a different register from the inputs, the compiler can add a preceding [MOVPRFX (unpredicated)](https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--) instruction

## svqadd[_n_s64]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqadd%5B_n_s64%5D_z

### Signature (source notation)

```c
svint64_t svqadd[_n_s64]_z(svbool_t pg, svint64_t op1, int64_t op2);
```

### Description

Saturating add

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Saturating addition

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

When result is in a different register from op2, this intrinsic can use:

```asm
MOVPRFX Zresult.D, Pg/Z, Zop1.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
SQADD Zresult.D, Pg/M, Zresult.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQADD--vectors--predicated---Signed-saturating-addition--predicated--

When result is in a different register from op1, this intrinsic can use:

```asm
MOVPRFX Zresult.D, Pg/Z, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
SQADD Zresult.D, Pg/M, Zresult.D, Zop1.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQADD--vectors--predicated---Signed-saturating-addition--predicated--

### Operation

Source operation ID: `SveOperation_svqadd_n_s64_z`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Add `op1[i]` and `op2` together, without loss of precision.
- Saturate the result to the range of `int64_t`.



Set the inactive elements of the result to zero.

## svqadd[_n_s8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqadd%5B_n_s8%5D

### Signature (source notation)

```c
svint8_t svqadd[_n_s8](svint8_t op1, int8_t op2);
```

### Description

Saturating add

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Saturating addition

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
    "register": "Zop2.B[*]"
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

When op2 is in the range [0, 127], this intrinsic can use:

```asm
SQADD Ztied1.B, Ztied1.B, #op2  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQADD--immediate---Signed-saturating-add-immediate--unpredicated--

When op2 is in the range [-128, 0], this intrinsic can use:

```asm
SQSUB Ztied1.B, Ztied1.B, #-op2  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQSUB--immediate---Signed-saturating-subtract-immediate--unpredicated--

The general implementation is:

```asm
SQADD Zresult.B, Zop1.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQADD--vectors--unpredicated---Signed-saturating-add--unpredicated--

### Operation

Source operation ID: `SveOperation_svqadd_n_s8`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Add `op1[i]` and `op2` together, without loss of precision.
- Saturate the result to the range of `int8_t`.



**[1]** If instead `result` is in a different register from the inputs, the compiler can add a preceding [MOVPRFX (unpredicated)](https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--) instruction

## svqadd[_n_s8]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqadd%5B_n_s8%5D_m

### Signature (source notation)

```c
svint8_t svqadd[_n_s8]_m(svbool_t pg, svint8_t op1, int8_t op2);
```

### Description

Saturating add

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Saturating addition

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
    "register": "Zop2.B[*]"
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
SQADD Ztied1.B, Pg/M, Ztied1.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQADD--vectors--predicated---Signed-saturating-addition--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SQADD Zresult.B, Pg/M, Zresult.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQADD--vectors--predicated---Signed-saturating-addition--predicated--

### Operation

Source operation ID: `SveOperation_svqadd_n_s8_m`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Add `op1[i]` and `op2` together, without loss of precision.
- Saturate the result to the range of `int8_t`.



Take the inactive elements of the result from the corresponding elements of `op1`.

## svqadd[_n_s8]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqadd%5B_n_s8%5D_x

### Signature (source notation)

```c
svint8_t svqadd[_n_s8]_x(svbool_t pg, svint8_t op1, int8_t op2);
```

### Description

Saturating add

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Saturating addition

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

When op2 is in the range [0, 127], this intrinsic can use:

```asm
SQADD Ztied1.B, Ztied1.B, #op2  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQADD--immediate---Signed-saturating-add-immediate--unpredicated--

When op2 is in the range [-128, 0], this intrinsic can use:

```asm
SQSUB Ztied1.B, Ztied1.B, #-op2  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQSUB--immediate---Signed-saturating-subtract-immediate--unpredicated--

When result and op1 are in the same register, this intrinsic can use:

```asm
SQADD Ztied1.B, Pg/M, Ztied1.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQADD--vectors--predicated---Signed-saturating-addition--predicated--

When result and op2 are in the same register, this intrinsic can use:

```asm
SQADD Ztied2.B, Pg/M, Ztied2.B, Zop1.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQADD--vectors--predicated---Signed-saturating-addition--predicated--

The general implementation is:

```asm
SQADD Zresult.B, Zop1.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQADD--vectors--unpredicated---Signed-saturating-add--unpredicated--

### Operation

Source operation ID: `SveOperation_svqadd_n_s8_x`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Add `op1[i]` and `op2` together, without loss of precision.
- Saturate the result to the range of `int8_t`.



The inactive elements of the result have arbitrary, undefined values.



**[1]** If instead `result` is in a different register from the inputs, the compiler can add a preceding [MOVPRFX (unpredicated)](https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--) instruction

## svqadd[_n_s8]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqadd%5B_n_s8%5D_z

### Signature (source notation)

```c
svint8_t svqadd[_n_s8]_z(svbool_t pg, svint8_t op1, int8_t op2);
```

### Description

Saturating add

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Saturating addition

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

When result is in a different register from op2, this intrinsic can use:

```asm
MOVPRFX Zresult.B, Pg/Z, Zop1.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
SQADD Zresult.B, Pg/M, Zresult.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQADD--vectors--predicated---Signed-saturating-addition--predicated--

When result is in a different register from op1, this intrinsic can use:

```asm
MOVPRFX Zresult.B, Pg/Z, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
SQADD Zresult.B, Pg/M, Zresult.B, Zop1.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQADD--vectors--predicated---Signed-saturating-addition--predicated--

### Operation

Source operation ID: `SveOperation_svqadd_n_s8_z`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Add `op1[i]` and `op2` together, without loss of precision.
- Saturate the result to the range of `int8_t`.



Set the inactive elements of the result to zero.

## svqadd[_n_u16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqadd%5B_n_u16%5D

### Signature (source notation)

```c
svuint16_t svqadd[_n_u16](svuint16_t op1, uint16_t op2);
```

### Description

Saturating add

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Saturating addition

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
    "register": "Zop2.H[*]"
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

When op2 is in range[1], this intrinsic can use:

```asm
UQADD Ztied1.H, Ztied1.H, #op2  // [2]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQADD--immediate---Unsigned-saturating-add-immediate--unpredicated--

The general implementation is:

```asm
UQADD Zresult.H, Zop1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQADD--vectors--unpredicated---Unsigned-saturating-add--unpredicated--

### Operation

Source operation ID: `SveOperation_svqadd_n_u16`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Add `op1[i]` and `op2` together, without loss of precision.
- Saturate the result to the range of `uint16_t`.



**[1]** This is true if the value is in the range [0, 255] or is a multiple of 256 in the range [0, 65280]



**[2]** If instead `result` is in a different register from the inputs, the compiler can add a preceding [MOVPRFX (unpredicated)](https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--) instruction

## svqadd[_n_u16]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqadd%5B_n_u16%5D_m

### Signature (source notation)

```c
svuint16_t svqadd[_n_u16]_m(svbool_t pg, svuint16_t op1, uint16_t op2);
```

### Description

Saturating add

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Saturating addition

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
    "register": "Zop2.H[*]"
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
UQADD Ztied1.H, Pg/M, Ztied1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQADD--vectors--predicated---Unsigned-saturating-addition--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
UQADD Zresult.H, Pg/M, Zresult.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQADD--vectors--predicated---Unsigned-saturating-addition--predicated--

### Operation

Source operation ID: `SveOperation_svqadd_n_u16_m`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Add `op1[i]` and `op2` together, without loss of precision.
- Saturate the result to the range of `uint16_t`.



Take the inactive elements of the result from the corresponding elements of `op1`.

## svqadd[_n_u16]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqadd%5B_n_u16%5D_x

### Signature (source notation)

```c
svuint16_t svqadd[_n_u16]_x(svbool_t pg, svuint16_t op1, uint16_t op2);
```

### Description

Saturating add

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Saturating addition

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

When op2 is in range[1], this intrinsic can use:

```asm
UQADD Ztied1.H, Ztied1.H, #op2  // [2]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQADD--immediate---Unsigned-saturating-add-immediate--unpredicated--

When result and op1 are in the same register, this intrinsic can use:

```asm
UQADD Ztied1.H, Pg/M, Ztied1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQADD--vectors--predicated---Unsigned-saturating-addition--predicated--

When result and op2 are in the same register, this intrinsic can use:

```asm
UQADD Ztied2.H, Pg/M, Ztied2.H, Zop1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQADD--vectors--predicated---Unsigned-saturating-addition--predicated--

The general implementation is:

```asm
UQADD Zresult.H, Zop1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQADD--vectors--unpredicated---Unsigned-saturating-add--unpredicated--

### Operation

Source operation ID: `SveOperation_svqadd_n_u16_x`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Add `op1[i]` and `op2` together, without loss of precision.
- Saturate the result to the range of `uint16_t`.



The inactive elements of the result have arbitrary, undefined values.



**[1]** This is true if the value is in the range [0, 255] or is a multiple of 256 in the range [0, 65280]



**[2]** If instead `result` is in a different register from the inputs, the compiler can add a preceding [MOVPRFX (unpredicated)](https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--) instruction

## svqadd[_n_u16]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqadd%5B_n_u16%5D_z

### Signature (source notation)

```c
svuint16_t svqadd[_n_u16]_z(svbool_t pg, svuint16_t op1, uint16_t op2);
```

### Description

Saturating add

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Saturating addition

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

When result is in a different register from op2, this intrinsic can use:

```asm
MOVPRFX Zresult.H, Pg/Z, Zop1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
UQADD Zresult.H, Pg/M, Zresult.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQADD--vectors--predicated---Unsigned-saturating-addition--predicated--

When result is in a different register from op1, this intrinsic can use:

```asm
MOVPRFX Zresult.H, Pg/Z, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
UQADD Zresult.H, Pg/M, Zresult.H, Zop1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQADD--vectors--predicated---Unsigned-saturating-addition--predicated--

### Operation

Source operation ID: `SveOperation_svqadd_n_u16_z`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Add `op1[i]` and `op2` together, without loss of precision.
- Saturate the result to the range of `uint16_t`.



Set the inactive elements of the result to zero.

## svqadd[_n_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqadd%5B_n_u32%5D

### Signature (source notation)

```c
svuint32_t svqadd[_n_u32](svuint32_t op1, uint32_t op2);
```

### Description

Saturating add

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Saturating addition

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
    "register": "Zop2.S[*]"
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

When op2 is in range[1], this intrinsic can use:

```asm
UQADD Ztied1.S, Ztied1.S, #op2  // [2]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQADD--immediate---Unsigned-saturating-add-immediate--unpredicated--

The general implementation is:

```asm
UQADD Zresult.S, Zop1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQADD--vectors--unpredicated---Unsigned-saturating-add--unpredicated--

### Operation

Source operation ID: `SveOperation_svqadd_n_u32`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Add `op1[i]` and `op2` together, without loss of precision.
- Saturate the result to the range of `uint32_t`.



**[1]** This is true if the value is in the range [0, 255] or is a multiple of 256 in the range [0, 65280]



**[2]** If instead `result` is in a different register from the inputs, the compiler can add a preceding [MOVPRFX (unpredicated)](https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--) instruction

## svqadd[_n_u32]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqadd%5B_n_u32%5D_m

### Signature (source notation)

```c
svuint32_t svqadd[_n_u32]_m(svbool_t pg, svuint32_t op1, uint32_t op2);
```

### Description

Saturating add

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Saturating addition

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
    "register": "Zop2.S[*]"
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
UQADD Ztied1.S, Pg/M, Ztied1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQADD--vectors--predicated---Unsigned-saturating-addition--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
UQADD Zresult.S, Pg/M, Zresult.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQADD--vectors--predicated---Unsigned-saturating-addition--predicated--

### Operation

Source operation ID: `SveOperation_svqadd_n_u32_m`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Add `op1[i]` and `op2` together, without loss of precision.
- Saturate the result to the range of `uint32_t`.



Take the inactive elements of the result from the corresponding elements of `op1`.

## svqadd[_n_u32]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqadd%5B_n_u32%5D_x

### Signature (source notation)

```c
svuint32_t svqadd[_n_u32]_x(svbool_t pg, svuint32_t op1, uint32_t op2);
```

### Description

Saturating add

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Saturating addition

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

When op2 is in range[1], this intrinsic can use:

```asm
UQADD Ztied1.S, Ztied1.S, #op2  // [2]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQADD--immediate---Unsigned-saturating-add-immediate--unpredicated--

When result and op1 are in the same register, this intrinsic can use:

```asm
UQADD Ztied1.S, Pg/M, Ztied1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQADD--vectors--predicated---Unsigned-saturating-addition--predicated--

When result and op2 are in the same register, this intrinsic can use:

```asm
UQADD Ztied2.S, Pg/M, Ztied2.S, Zop1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQADD--vectors--predicated---Unsigned-saturating-addition--predicated--

The general implementation is:

```asm
UQADD Zresult.S, Zop1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQADD--vectors--unpredicated---Unsigned-saturating-add--unpredicated--

### Operation

Source operation ID: `SveOperation_svqadd_n_u32_x`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Add `op1[i]` and `op2` together, without loss of precision.
- Saturate the result to the range of `uint32_t`.



The inactive elements of the result have arbitrary, undefined values.



**[1]** This is true if the value is in the range [0, 255] or is a multiple of 256 in the range [0, 65280]



**[2]** If instead `result` is in a different register from the inputs, the compiler can add a preceding [MOVPRFX (unpredicated)](https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--) instruction

## svqadd[_n_u32]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqadd%5B_n_u32%5D_z

### Signature (source notation)

```c
svuint32_t svqadd[_n_u32]_z(svbool_t pg, svuint32_t op1, uint32_t op2);
```

### Description

Saturating add

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Saturating addition

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

When result is in a different register from op2, this intrinsic can use:

```asm
MOVPRFX Zresult.S, Pg/Z, Zop1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
UQADD Zresult.S, Pg/M, Zresult.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQADD--vectors--predicated---Unsigned-saturating-addition--predicated--

When result is in a different register from op1, this intrinsic can use:

```asm
MOVPRFX Zresult.S, Pg/Z, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
UQADD Zresult.S, Pg/M, Zresult.S, Zop1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQADD--vectors--predicated---Unsigned-saturating-addition--predicated--

### Operation

Source operation ID: `SveOperation_svqadd_n_u32_z`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Add `op1[i]` and `op2` together, without loss of precision.
- Saturate the result to the range of `uint32_t`.



Set the inactive elements of the result to zero.

## svqadd[_n_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqadd%5B_n_u64%5D

### Signature (source notation)

```c
svuint64_t svqadd[_n_u64](svuint64_t op1, uint64_t op2);
```

### Description

Saturating add

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Saturating addition

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
    "register": "Zop2.D[*]"
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

When op2 is in range[1], this intrinsic can use:

```asm
UQADD Ztied1.D, Ztied1.D, #op2  // [2]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQADD--immediate---Unsigned-saturating-add-immediate--unpredicated--

The general implementation is:

```asm
UQADD Zresult.D, Zop1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQADD--vectors--unpredicated---Unsigned-saturating-add--unpredicated--

### Operation

Source operation ID: `SveOperation_svqadd_n_u64`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Add `op1[i]` and `op2` together, without loss of precision.
- Saturate the result to the range of `uint64_t`.



**[1]** This is true if the value is in the range [0, 255] or is a multiple of 256 in the range [0, 65280]



**[2]** If instead `result` is in a different register from the inputs, the compiler can add a preceding [MOVPRFX (unpredicated)](https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--) instruction

## svqadd[_n_u64]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqadd%5B_n_u64%5D_m

### Signature (source notation)

```c
svuint64_t svqadd[_n_u64]_m(svbool_t pg, svuint64_t op1, uint64_t op2);
```

### Description

Saturating add

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Saturating addition

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
    "register": "Zop2.D[*]"
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
UQADD Ztied1.D, Pg/M, Ztied1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQADD--vectors--predicated---Unsigned-saturating-addition--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
UQADD Zresult.D, Pg/M, Zresult.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQADD--vectors--predicated---Unsigned-saturating-addition--predicated--

### Operation

Source operation ID: `SveOperation_svqadd_n_u64_m`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Add `op1[i]` and `op2` together, without loss of precision.
- Saturate the result to the range of `uint64_t`.



Take the inactive elements of the result from the corresponding elements of `op1`.

## svqadd[_n_u64]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqadd%5B_n_u64%5D_x

### Signature (source notation)

```c
svuint64_t svqadd[_n_u64]_x(svbool_t pg, svuint64_t op1, uint64_t op2);
```

### Description

Saturating add

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Saturating addition

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

When op2 is in range[1], this intrinsic can use:

```asm
UQADD Ztied1.D, Ztied1.D, #op2  // [2]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQADD--immediate---Unsigned-saturating-add-immediate--unpredicated--

When result and op1 are in the same register, this intrinsic can use:

```asm
UQADD Ztied1.D, Pg/M, Ztied1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQADD--vectors--predicated---Unsigned-saturating-addition--predicated--

When result and op2 are in the same register, this intrinsic can use:

```asm
UQADD Ztied2.D, Pg/M, Ztied2.D, Zop1.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQADD--vectors--predicated---Unsigned-saturating-addition--predicated--

The general implementation is:

```asm
UQADD Zresult.D, Zop1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQADD--vectors--unpredicated---Unsigned-saturating-add--unpredicated--

### Operation

Source operation ID: `SveOperation_svqadd_n_u64_x`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Add `op1[i]` and `op2` together, without loss of precision.
- Saturate the result to the range of `uint64_t`.



The inactive elements of the result have arbitrary, undefined values.



**[1]** This is true if the value is in the range [0, 255] or is a multiple of 256 in the range [0, 65280]



**[2]** If instead `result` is in a different register from the inputs, the compiler can add a preceding [MOVPRFX (unpredicated)](https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--) instruction

## svqadd[_n_u64]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqadd%5B_n_u64%5D_z

### Signature (source notation)

```c
svuint64_t svqadd[_n_u64]_z(svbool_t pg, svuint64_t op1, uint64_t op2);
```

### Description

Saturating add

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Saturating addition

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

When result is in a different register from op2, this intrinsic can use:

```asm
MOVPRFX Zresult.D, Pg/Z, Zop1.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
UQADD Zresult.D, Pg/M, Zresult.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQADD--vectors--predicated---Unsigned-saturating-addition--predicated--

When result is in a different register from op1, this intrinsic can use:

```asm
MOVPRFX Zresult.D, Pg/Z, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
UQADD Zresult.D, Pg/M, Zresult.D, Zop1.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQADD--vectors--predicated---Unsigned-saturating-addition--predicated--

### Operation

Source operation ID: `SveOperation_svqadd_n_u64_z`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Add `op1[i]` and `op2` together, without loss of precision.
- Saturate the result to the range of `uint64_t`.



Set the inactive elements of the result to zero.

## svqadd[_n_u8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqadd%5B_n_u8%5D

### Signature (source notation)

```c
svuint8_t svqadd[_n_u8](svuint8_t op1, uint8_t op2);
```

### Description

Saturating add

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Saturating addition

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
    "register": "Zop2.B[*]"
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

When op2 is constant, this intrinsic can use:

```asm
UQADD Ztied1.B, Ztied1.B, #op2  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQADD--immediate---Unsigned-saturating-add-immediate--unpredicated--

The general implementation is:

```asm
UQADD Zresult.B, Zop1.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQADD--vectors--unpredicated---Unsigned-saturating-add--unpredicated--

### Operation

Source operation ID: `SveOperation_svqadd_n_u8`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Add `op1[i]` and `op2` together, without loss of precision.
- Saturate the result to the range of `uint8_t`.



**[1]** If instead `result` is in a different register from the inputs, the compiler can add a preceding [MOVPRFX (unpredicated)](https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--) instruction

## svqadd[_n_u8]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqadd%5B_n_u8%5D_m

### Signature (source notation)

```c
svuint8_t svqadd[_n_u8]_m(svbool_t pg, svuint8_t op1, uint8_t op2);
```

### Description

Saturating add

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Saturating addition

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
    "register": "Zop2.B[*]"
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
UQADD Ztied1.B, Pg/M, Ztied1.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQADD--vectors--predicated---Unsigned-saturating-addition--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
UQADD Zresult.B, Pg/M, Zresult.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQADD--vectors--predicated---Unsigned-saturating-addition--predicated--

### Operation

Source operation ID: `SveOperation_svqadd_n_u8_m`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Add `op1[i]` and `op2` together, without loss of precision.
- Saturate the result to the range of `uint8_t`.



Take the inactive elements of the result from the corresponding elements of `op1`.

## svqadd[_n_u8]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqadd%5B_n_u8%5D_x

### Signature (source notation)

```c
svuint8_t svqadd[_n_u8]_x(svbool_t pg, svuint8_t op1, uint8_t op2);
```

### Description

Saturating add

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Saturating addition

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

When op2 is constant, this intrinsic can use:

```asm
UQADD Ztied1.B, Ztied1.B, #op2  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQADD--immediate---Unsigned-saturating-add-immediate--unpredicated--

When result and op1 are in the same register, this intrinsic can use:

```asm
UQADD Ztied1.B, Pg/M, Ztied1.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQADD--vectors--predicated---Unsigned-saturating-addition--predicated--

When result and op2 are in the same register, this intrinsic can use:

```asm
UQADD Ztied2.B, Pg/M, Ztied2.B, Zop1.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQADD--vectors--predicated---Unsigned-saturating-addition--predicated--

The general implementation is:

```asm
UQADD Zresult.B, Zop1.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQADD--vectors--unpredicated---Unsigned-saturating-add--unpredicated--

### Operation

Source operation ID: `SveOperation_svqadd_n_u8_x`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Add `op1[i]` and `op2` together, without loss of precision.
- Saturate the result to the range of `uint8_t`.



The inactive elements of the result have arbitrary, undefined values.



**[1]** If instead `result` is in a different register from the inputs, the compiler can add a preceding [MOVPRFX (unpredicated)](https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--) instruction

## svqadd[_n_u8]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqadd%5B_n_u8%5D_z

### Signature (source notation)

```c
svuint8_t svqadd[_n_u8]_z(svbool_t pg, svuint8_t op1, uint8_t op2);
```

### Description

Saturating add

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Saturating addition

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

When result is in a different register from op2, this intrinsic can use:

```asm
MOVPRFX Zresult.B, Pg/Z, Zop1.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
UQADD Zresult.B, Pg/M, Zresult.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQADD--vectors--predicated---Unsigned-saturating-addition--predicated--

When result is in a different register from op1, this intrinsic can use:

```asm
MOVPRFX Zresult.B, Pg/Z, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
UQADD Zresult.B, Pg/M, Zresult.B, Zop1.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQADD--vectors--predicated---Unsigned-saturating-addition--predicated--

### Operation

Source operation ID: `SveOperation_svqadd_n_u8_z`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Add `op1[i]` and `op2` together, without loss of precision.
- Saturate the result to the range of `uint8_t`.



Set the inactive elements of the result to zero.

## svqadd[_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqadd%5B_s16%5D

### Signature (source notation)

```c
svint16_t svqadd[_s16](svint16_t op1, svint16_t op2);
```

### Description

Saturating add

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Saturating addition

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

This intrinsic compiles to the following instruction:

```asm
SQADD Zresult.H, Zop1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQADD--vectors--unpredicated---Signed-saturating-add--unpredicated--

### Operation

Source operation ID: `SveOperation_svqadd_s16`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Add `op1[i]` and `op2[i]` together, without loss of precision.
- Saturate the result to the range of `int16_t`.

## svqadd[_s16]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqadd%5B_s16%5D_m

### Signature (source notation)

```c
svint16_t svqadd[_s16]_m(svbool_t pg, svint16_t op1, svint16_t op2);
```

### Description

Saturating add

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Saturating addition

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
SQADD Ztied1.H, Pg/M, Ztied1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQADD--vectors--predicated---Signed-saturating-addition--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SQADD Zresult.H, Pg/M, Zresult.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQADD--vectors--predicated---Signed-saturating-addition--predicated--

### Operation

Source operation ID: `SveOperation_svqadd_s16_m`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Add `op1[i]` and `op2[i]` together, without loss of precision.
- Saturate the result to the range of `int16_t`.



Take the inactive elements of the result from the corresponding elements of `op1`.

## svqadd[_s16]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqadd%5B_s16%5D_x

### Signature (source notation)

```c
svint16_t svqadd[_s16]_x(svbool_t pg, svint16_t op1, svint16_t op2);
```

### Description

Saturating add

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Saturating addition

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

When result and op1 are in the same register, this intrinsic can use:

```asm
SQADD Ztied1.H, Pg/M, Ztied1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQADD--vectors--predicated---Signed-saturating-addition--predicated--

When result and op2 are in the same register, this intrinsic can use:

```asm
SQADD Ztied2.H, Pg/M, Ztied2.H, Zop1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQADD--vectors--predicated---Signed-saturating-addition--predicated--

This intrinsic compiles to:

```asm
SQADD Zresult.H, Zop1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQADD--vectors--unpredicated---Signed-saturating-add--unpredicated--

### Operation

Source operation ID: `SveOperation_svqadd_s16_x`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Add `op1[i]` and `op2[i]` together, without loss of precision.
- Saturate the result to the range of `int16_t`.



The inactive elements of the result have arbitrary, undefined values.

## svqadd[_s16]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqadd%5B_s16%5D_z

### Signature (source notation)

```c
svint16_t svqadd[_s16]_z(svbool_t pg, svint16_t op1, svint16_t op2);
```

### Description

Saturating add

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Saturating addition

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
SQADD Zresult.H, Pg/M, Zresult.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQADD--vectors--predicated---Signed-saturating-addition--predicated--

When result is in a different register from op1, this intrinsic can use:

```asm
MOVPRFX Zresult.H, Pg/Z, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
SQADD Zresult.H, Pg/M, Zresult.H, Zop1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQADD--vectors--predicated---Signed-saturating-addition--predicated--

### Operation

Source operation ID: `SveOperation_svqadd_s16_z`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Add `op1[i]` and `op2[i]` together, without loss of precision.
- Saturate the result to the range of `int16_t`.



Set the inactive elements of the result to zero.

## svqadd[_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqadd%5B_s32%5D

### Signature (source notation)

```c
svint32_t svqadd[_s32](svint32_t op1, svint32_t op2);
```

### Description

Saturating add

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Saturating addition

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

This intrinsic compiles to the following instruction:

```asm
SQADD Zresult.S, Zop1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQADD--vectors--unpredicated---Signed-saturating-add--unpredicated--

### Operation

Source operation ID: `SveOperation_svqadd_s32`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Add `op1[i]` and `op2[i]` together, without loss of precision.
- Saturate the result to the range of `int32_t`.

## svqadd[_s32]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqadd%5B_s32%5D_m

### Signature (source notation)

```c
svint32_t svqadd[_s32]_m(svbool_t pg, svint32_t op1, svint32_t op2);
```

### Description

Saturating add

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Saturating addition

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
SQADD Ztied1.S, Pg/M, Ztied1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQADD--vectors--predicated---Signed-saturating-addition--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SQADD Zresult.S, Pg/M, Zresult.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQADD--vectors--predicated---Signed-saturating-addition--predicated--

### Operation

Source operation ID: `SveOperation_svqadd_s32_m`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Add `op1[i]` and `op2[i]` together, without loss of precision.
- Saturate the result to the range of `int32_t`.



Take the inactive elements of the result from the corresponding elements of `op1`.

## svqadd[_s32]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqadd%5B_s32%5D_x

### Signature (source notation)

```c
svint32_t svqadd[_s32]_x(svbool_t pg, svint32_t op1, svint32_t op2);
```

### Description

Saturating add

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Saturating addition

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

When result and op1 are in the same register, this intrinsic can use:

```asm
SQADD Ztied1.S, Pg/M, Ztied1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQADD--vectors--predicated---Signed-saturating-addition--predicated--

When result and op2 are in the same register, this intrinsic can use:

```asm
SQADD Ztied2.S, Pg/M, Ztied2.S, Zop1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQADD--vectors--predicated---Signed-saturating-addition--predicated--

This intrinsic compiles to:

```asm
SQADD Zresult.S, Zop1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQADD--vectors--unpredicated---Signed-saturating-add--unpredicated--

### Operation

Source operation ID: `SveOperation_svqadd_s32_x`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Add `op1[i]` and `op2[i]` together, without loss of precision.
- Saturate the result to the range of `int32_t`.



The inactive elements of the result have arbitrary, undefined values.

## svqadd[_s32]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqadd%5B_s32%5D_z

### Signature (source notation)

```c
svint32_t svqadd[_s32]_z(svbool_t pg, svint32_t op1, svint32_t op2);
```

### Description

Saturating add

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Saturating addition

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
SQADD Zresult.S, Pg/M, Zresult.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQADD--vectors--predicated---Signed-saturating-addition--predicated--

When result is in a different register from op1, this intrinsic can use:

```asm
MOVPRFX Zresult.S, Pg/Z, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
SQADD Zresult.S, Pg/M, Zresult.S, Zop1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQADD--vectors--predicated---Signed-saturating-addition--predicated--

### Operation

Source operation ID: `SveOperation_svqadd_s32_z`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Add `op1[i]` and `op2[i]` together, without loss of precision.
- Saturate the result to the range of `int32_t`.



Set the inactive elements of the result to zero.

## svqadd[_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqadd%5B_s64%5D

### Signature (source notation)

```c
svint64_t svqadd[_s64](svint64_t op1, svint64_t op2);
```

### Description

Saturating add

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Saturating addition

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

This intrinsic compiles to the following instruction:

```asm
SQADD Zresult.D, Zop1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQADD--vectors--unpredicated---Signed-saturating-add--unpredicated--

### Operation

Source operation ID: `SveOperation_svqadd_s64`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Add `op1[i]` and `op2[i]` together, without loss of precision.
- Saturate the result to the range of `int64_t`.

## svqadd[_s64]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqadd%5B_s64%5D_m

### Signature (source notation)

```c
svint64_t svqadd[_s64]_m(svbool_t pg, svint64_t op1, svint64_t op2);
```

### Description

Saturating add

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Saturating addition

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
SQADD Ztied1.D, Pg/M, Ztied1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQADD--vectors--predicated---Signed-saturating-addition--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SQADD Zresult.D, Pg/M, Zresult.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQADD--vectors--predicated---Signed-saturating-addition--predicated--

### Operation

Source operation ID: `SveOperation_svqadd_s64_m`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Add `op1[i]` and `op2[i]` together, without loss of precision.
- Saturate the result to the range of `int64_t`.



Take the inactive elements of the result from the corresponding elements of `op1`.

## svqadd[_s64]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqadd%5B_s64%5D_x

### Signature (source notation)

```c
svint64_t svqadd[_s64]_x(svbool_t pg, svint64_t op1, svint64_t op2);
```

### Description

Saturating add

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Saturating addition

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

When result and op1 are in the same register, this intrinsic can use:

```asm
SQADD Ztied1.D, Pg/M, Ztied1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQADD--vectors--predicated---Signed-saturating-addition--predicated--

When result and op2 are in the same register, this intrinsic can use:

```asm
SQADD Ztied2.D, Pg/M, Ztied2.D, Zop1.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQADD--vectors--predicated---Signed-saturating-addition--predicated--

This intrinsic compiles to:

```asm
SQADD Zresult.D, Zop1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQADD--vectors--unpredicated---Signed-saturating-add--unpredicated--

### Operation

Source operation ID: `SveOperation_svqadd_s64_x`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Add `op1[i]` and `op2[i]` together, without loss of precision.
- Saturate the result to the range of `int64_t`.



The inactive elements of the result have arbitrary, undefined values.

## svqadd[_s64]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqadd%5B_s64%5D_z

### Signature (source notation)

```c
svint64_t svqadd[_s64]_z(svbool_t pg, svint64_t op1, svint64_t op2);
```

### Description

Saturating add

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Saturating addition

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
SQADD Zresult.D, Pg/M, Zresult.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQADD--vectors--predicated---Signed-saturating-addition--predicated--

When result is in a different register from op1, this intrinsic can use:

```asm
MOVPRFX Zresult.D, Pg/Z, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
SQADD Zresult.D, Pg/M, Zresult.D, Zop1.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQADD--vectors--predicated---Signed-saturating-addition--predicated--

### Operation

Source operation ID: `SveOperation_svqadd_s64_z`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Add `op1[i]` and `op2[i]` together, without loss of precision.
- Saturate the result to the range of `int64_t`.



Set the inactive elements of the result to zero.

## svqadd[_s8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqadd%5B_s8%5D

### Signature (source notation)

```c
svint8_t svqadd[_s8](svint8_t op1, svint8_t op2);
```

### Description

Saturating add

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Saturating addition

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

This intrinsic compiles to the following instruction:

```asm
SQADD Zresult.B, Zop1.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQADD--vectors--unpredicated---Signed-saturating-add--unpredicated--

### Operation

Source operation ID: `SveOperation_svqadd_s8`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Add `op1[i]` and `op2[i]` together, without loss of precision.
- Saturate the result to the range of `int8_t`.

## svqadd[_s8]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqadd%5B_s8%5D_m

### Signature (source notation)

```c
svint8_t svqadd[_s8]_m(svbool_t pg, svint8_t op1, svint8_t op2);
```

### Description

Saturating add

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Saturating addition

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
SQADD Ztied1.B, Pg/M, Ztied1.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQADD--vectors--predicated---Signed-saturating-addition--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SQADD Zresult.B, Pg/M, Zresult.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQADD--vectors--predicated---Signed-saturating-addition--predicated--

### Operation

Source operation ID: `SveOperation_svqadd_s8_m`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Add `op1[i]` and `op2[i]` together, without loss of precision.
- Saturate the result to the range of `int8_t`.



Take the inactive elements of the result from the corresponding elements of `op1`.

## svqadd[_s8]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqadd%5B_s8%5D_x

### Signature (source notation)

```c
svint8_t svqadd[_s8]_x(svbool_t pg, svint8_t op1, svint8_t op2);
```

### Description

Saturating add

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Saturating addition

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

When result and op1 are in the same register, this intrinsic can use:

```asm
SQADD Ztied1.B, Pg/M, Ztied1.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQADD--vectors--predicated---Signed-saturating-addition--predicated--

When result and op2 are in the same register, this intrinsic can use:

```asm
SQADD Ztied2.B, Pg/M, Ztied2.B, Zop1.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQADD--vectors--predicated---Signed-saturating-addition--predicated--

This intrinsic compiles to:

```asm
SQADD Zresult.B, Zop1.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQADD--vectors--unpredicated---Signed-saturating-add--unpredicated--

### Operation

Source operation ID: `SveOperation_svqadd_s8_x`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Add `op1[i]` and `op2[i]` together, without loss of precision.
- Saturate the result to the range of `int8_t`.



The inactive elements of the result have arbitrary, undefined values.

## svqadd[_s8]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqadd%5B_s8%5D_z

### Signature (source notation)

```c
svint8_t svqadd[_s8]_z(svbool_t pg, svint8_t op1, svint8_t op2);
```

### Description

Saturating add

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Saturating addition

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
SQADD Zresult.B, Pg/M, Zresult.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQADD--vectors--predicated---Signed-saturating-addition--predicated--

When result is in a different register from op1, this intrinsic can use:

```asm
MOVPRFX Zresult.B, Pg/Z, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
SQADD Zresult.B, Pg/M, Zresult.B, Zop1.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQADD--vectors--predicated---Signed-saturating-addition--predicated--

### Operation

Source operation ID: `SveOperation_svqadd_s8_z`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Add `op1[i]` and `op2[i]` together, without loss of precision.
- Saturate the result to the range of `int8_t`.



Set the inactive elements of the result to zero.

## svqadd[_u16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqadd%5B_u16%5D

### Signature (source notation)

```c
svuint16_t svqadd[_u16](svuint16_t op1, svuint16_t op2);
```

### Description

Saturating add

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Saturating addition

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

This intrinsic compiles to the following instruction:

```asm
UQADD Zresult.H, Zop1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQADD--vectors--unpredicated---Unsigned-saturating-add--unpredicated--

### Operation

Source operation ID: `SveOperation_svqadd_u16`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Add `op1[i]` and `op2[i]` together, without loss of precision.
- Saturate the result to the range of `uint16_t`.

## svqadd[_u16]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqadd%5B_u16%5D_m

### Signature (source notation)

```c
svuint16_t svqadd[_u16]_m(svbool_t pg, svuint16_t op1, svuint16_t op2);
```

### Description

Saturating add

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Saturating addition

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
UQADD Ztied1.H, Pg/M, Ztied1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQADD--vectors--predicated---Unsigned-saturating-addition--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
UQADD Zresult.H, Pg/M, Zresult.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQADD--vectors--predicated---Unsigned-saturating-addition--predicated--

### Operation

Source operation ID: `SveOperation_svqadd_u16_m`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Add `op1[i]` and `op2[i]` together, without loss of precision.
- Saturate the result to the range of `uint16_t`.



Take the inactive elements of the result from the corresponding elements of `op1`.

