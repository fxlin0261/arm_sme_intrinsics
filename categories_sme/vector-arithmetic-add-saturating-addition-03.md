# SME / Vector arithmetic / Add / Saturating addition — Part 3

## svuqadd[_s16]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svuqadd%5B_s16%5D_m

### Signature (source notation)

```c
svint16_t svuqadd[_s16]_m(svbool_t pg, svint16_t op1, svuint16_t op2);
```

### Description

Saturating add with unsigned addend

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
SUQADD Ztied1.H, Pg/M, Ztied1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SUQADD--Signed-saturating-addition-of-unsigned-value-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SUQADD Zresult.H, Pg/M, Zresult.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SUQADD--Signed-saturating-addition-of-unsigned-value-

### Operation

Source operation ID: `SveOperation_svqadd_s16_m`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Add `op1[i]` and `op2[i]` together, without loss of precision.
- Saturate the result to the range of `int16_t`.



Take the inactive elements of the result from the corresponding elements of `op1`.

## svuqadd[_s16]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svuqadd%5B_s16%5D_x

### Signature (source notation)

```c
svint16_t svuqadd[_s16]_x(svbool_t pg, svint16_t op1, svuint16_t op2);
```

### Description

Saturating add with unsigned addend

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
SUQADD Ztied1.H, Pg/M, Ztied1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SUQADD--Signed-saturating-addition-of-unsigned-value-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SUQADD Zresult.H, Pg/M, Zresult.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SUQADD--Signed-saturating-addition-of-unsigned-value-

### Operation

Source operation ID: `SveOperation_svqadd_s16_x`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Add `op1[i]` and `op2[i]` together, without loss of precision.
- Saturate the result to the range of `int16_t`.



The inactive elements of the result have arbitrary, undefined values.

## svuqadd[_s16]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svuqadd%5B_s16%5D_z

### Signature (source notation)

```c
svint16_t svuqadd[_s16]_z(svbool_t pg, svint16_t op1, svuint16_t op2);
```

### Description

Saturating add with unsigned addend

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

This intrinsic compiles to the following instructions, or functionally equivalent instructions:

```asm
MOVPRFX Zresult.H, Pg/Z, Zop1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
SUQADD Zresult.H, Pg/M, Zresult.H, Zop2.H  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SUQADD--Signed-saturating-addition-of-unsigned-value-

### Operation

Source operation ID: `SveOperation_svuqadd_s16_z`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Add `op1[i]` and `op2[i]` together, without loss of precision.
- Saturate the result to the range of `int16_t`.



Set the inactive elements of the result to zero.



**[1]** Note that `result` must be in a different register from `op2`

## svuqadd[_s32]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svuqadd%5B_s32%5D_m

### Signature (source notation)

```c
svint32_t svuqadd[_s32]_m(svbool_t pg, svint32_t op1, svuint32_t op2);
```

### Description

Saturating add with unsigned addend

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
SUQADD Ztied1.S, Pg/M, Ztied1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SUQADD--Signed-saturating-addition-of-unsigned-value-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SUQADD Zresult.S, Pg/M, Zresult.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SUQADD--Signed-saturating-addition-of-unsigned-value-

### Operation

Source operation ID: `SveOperation_svqadd_s32_m`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Add `op1[i]` and `op2[i]` together, without loss of precision.
- Saturate the result to the range of `int32_t`.



Take the inactive elements of the result from the corresponding elements of `op1`.

## svuqadd[_s32]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svuqadd%5B_s32%5D_x

### Signature (source notation)

```c
svint32_t svuqadd[_s32]_x(svbool_t pg, svint32_t op1, svuint32_t op2);
```

### Description

Saturating add with unsigned addend

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
SUQADD Ztied1.S, Pg/M, Ztied1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SUQADD--Signed-saturating-addition-of-unsigned-value-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SUQADD Zresult.S, Pg/M, Zresult.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SUQADD--Signed-saturating-addition-of-unsigned-value-

### Operation

Source operation ID: `SveOperation_svqadd_s32_x`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Add `op1[i]` and `op2[i]` together, without loss of precision.
- Saturate the result to the range of `int32_t`.



The inactive elements of the result have arbitrary, undefined values.

## svuqadd[_s32]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svuqadd%5B_s32%5D_z

### Signature (source notation)

```c
svint32_t svuqadd[_s32]_z(svbool_t pg, svint32_t op1, svuint32_t op2);
```

### Description

Saturating add with unsigned addend

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

This intrinsic compiles to the following instructions, or functionally equivalent instructions:

```asm
MOVPRFX Zresult.S, Pg/Z, Zop1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
SUQADD Zresult.S, Pg/M, Zresult.S, Zop2.S  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SUQADD--Signed-saturating-addition-of-unsigned-value-

### Operation

Source operation ID: `SveOperation_svuqadd_s32_z`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Add `op1[i]` and `op2[i]` together, without loss of precision.
- Saturate the result to the range of `int32_t`.



Set the inactive elements of the result to zero.



**[1]** Note that `result` must be in a different register from `op2`

## svuqadd[_s64]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svuqadd%5B_s64%5D_m

### Signature (source notation)

```c
svint64_t svuqadd[_s64]_m(svbool_t pg, svint64_t op1, svuint64_t op2);
```

### Description

Saturating add with unsigned addend

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
SUQADD Ztied1.D, Pg/M, Ztied1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SUQADD--Signed-saturating-addition-of-unsigned-value-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SUQADD Zresult.D, Pg/M, Zresult.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SUQADD--Signed-saturating-addition-of-unsigned-value-

### Operation

Source operation ID: `SveOperation_svqadd_s64_m`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Add `op1[i]` and `op2[i]` together, without loss of precision.
- Saturate the result to the range of `int64_t`.



Take the inactive elements of the result from the corresponding elements of `op1`.

## svuqadd[_s64]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svuqadd%5B_s64%5D_x

### Signature (source notation)

```c
svint64_t svuqadd[_s64]_x(svbool_t pg, svint64_t op1, svuint64_t op2);
```

### Description

Saturating add with unsigned addend

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
SUQADD Ztied1.D, Pg/M, Ztied1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SUQADD--Signed-saturating-addition-of-unsigned-value-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SUQADD Zresult.D, Pg/M, Zresult.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SUQADD--Signed-saturating-addition-of-unsigned-value-

### Operation

Source operation ID: `SveOperation_svqadd_s64_x`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Add `op1[i]` and `op2[i]` together, without loss of precision.
- Saturate the result to the range of `int64_t`.



The inactive elements of the result have arbitrary, undefined values.

## svuqadd[_s64]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svuqadd%5B_s64%5D_z

### Signature (source notation)

```c
svint64_t svuqadd[_s64]_z(svbool_t pg, svint64_t op1, svuint64_t op2);
```

### Description

Saturating add with unsigned addend

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

This intrinsic compiles to the following instructions, or functionally equivalent instructions:

```asm
MOVPRFX Zresult.D, Pg/Z, Zop1.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
SUQADD Zresult.D, Pg/M, Zresult.D, Zop2.D  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SUQADD--Signed-saturating-addition-of-unsigned-value-

### Operation

Source operation ID: `SveOperation_svuqadd_s64_z`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Add `op1[i]` and `op2[i]` together, without loss of precision.
- Saturate the result to the range of `int64_t`.



Set the inactive elements of the result to zero.



**[1]** Note that `result` must be in a different register from `op2`

## svuqadd[_s8]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svuqadd%5B_s8%5D_m

### Signature (source notation)

```c
svint8_t svuqadd[_s8]_m(svbool_t pg, svint8_t op1, svuint8_t op2);
```

### Description

Saturating add with unsigned addend

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
SUQADD Ztied1.B, Pg/M, Ztied1.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SUQADD--Signed-saturating-addition-of-unsigned-value-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SUQADD Zresult.B, Pg/M, Zresult.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SUQADD--Signed-saturating-addition-of-unsigned-value-

### Operation

Source operation ID: `SveOperation_svqadd_s8_m`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Add `op1[i]` and `op2[i]` together, without loss of precision.
- Saturate the result to the range of `int8_t`.



Take the inactive elements of the result from the corresponding elements of `op1`.

## svuqadd[_s8]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svuqadd%5B_s8%5D_x

### Signature (source notation)

```c
svint8_t svuqadd[_s8]_x(svbool_t pg, svint8_t op1, svuint8_t op2);
```

### Description

Saturating add with unsigned addend

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
SUQADD Ztied1.B, Pg/M, Ztied1.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SUQADD--Signed-saturating-addition-of-unsigned-value-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SUQADD Zresult.B, Pg/M, Zresult.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SUQADD--Signed-saturating-addition-of-unsigned-value-

### Operation

Source operation ID: `SveOperation_svqadd_s8_x`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Add `op1[i]` and `op2[i]` together, without loss of precision.
- Saturate the result to the range of `int8_t`.



The inactive elements of the result have arbitrary, undefined values.

## svuqadd[_s8]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svuqadd%5B_s8%5D_z

### Signature (source notation)

```c
svint8_t svuqadd[_s8]_z(svbool_t pg, svint8_t op1, svuint8_t op2);
```

### Description

Saturating add with unsigned addend

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

This intrinsic compiles to the following instructions, or functionally equivalent instructions:

```asm
MOVPRFX Zresult.B, Pg/Z, Zop1.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
SUQADD Zresult.B, Pg/M, Zresult.B, Zop2.B  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SUQADD--Signed-saturating-addition-of-unsigned-value-

### Operation

Source operation ID: `SveOperation_svuqadd_s8_z`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Add `op1[i]` and `op2[i]` together, without loss of precision.
- Saturate the result to the range of `int8_t`.



Set the inactive elements of the result to zero.



**[1]** Note that `result` must be in a different register from `op2`

