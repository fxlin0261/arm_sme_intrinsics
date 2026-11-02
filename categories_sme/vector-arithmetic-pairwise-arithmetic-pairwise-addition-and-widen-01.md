# SME / Vector arithmetic / Pairwise arithmetic / Pairwise addition and widen — Part 1

## svadalp[_s16]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svadalp%5B_s16%5D_m

### Signature (source notation)

```c
svint16_t svadalp[_s16]_m(svbool_t pg, svint16_t op1, svint8_t op2);
```

### Description

Add and accumulate long pairwise

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Pairwise arithmetic / Pairwise addition and widen

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
    "register": "Zop2.B"
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
SADALP Ztied1.H, Pg/M, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SADALP--Signed-add-and-accumulate-long-pairwise-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SADALP Zresult.H, Pg/M, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SADALP--Signed-add-and-accumulate-long-pairwise-

### Operation

Source operation ID: `SveOperation_svadalp_s16_m`

**Operation**



Return a vector in which each active element *i* contains the value:



```text
op1[i] + (int16_t)op2[i * 2] + (int16_t)op2[i * 2 + 1]
```



Take the inactive elements of the result from the corresponding elements of `op1`.



The operation uses modulo arithmetic.  The behavior is therefore defined for all inputs; unlike C, there is no undefined behavior for signed overflow.

## svadalp[_s16]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svadalp%5B_s16%5D_x

### Signature (source notation)

```c
svint16_t svadalp[_s16]_x(svbool_t pg, svint16_t op1, svint8_t op2);
```

### Description

Add and accumulate long pairwise

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Pairwise arithmetic / Pairwise addition and widen

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
    "register": "Zop2.B"
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
SADALP Ztied1.H, Pg/M, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SADALP--Signed-add-and-accumulate-long-pairwise-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SADALP Zresult.H, Pg/M, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SADALP--Signed-add-and-accumulate-long-pairwise-

### Operation

Source operation ID: `SveOperation_svadalp_s16_x`

**Operation**



Return a vector in which each active element *i* contains the value:



```text
op1[i] + (int16_t)op2[i * 2] + (int16_t)op2[i * 2 + 1]
```



The inactive elements of the result have arbitrary, undefined values.



The operation uses modulo arithmetic.  The behavior is therefore defined for all inputs; unlike C, there is no undefined behavior for signed overflow.

## svadalp[_s16]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svadalp%5B_s16%5D_z

### Signature (source notation)

```c
svint16_t svadalp[_s16]_z(svbool_t pg, svint16_t op1, svint8_t op2);
```

### Description

Add and accumulate long pairwise

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Pairwise arithmetic / Pairwise addition and widen

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
    "register": "Zop2.B"
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
SADALP Zresult.H, Pg/M, Zop2.B  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SADALP--Signed-add-and-accumulate-long-pairwise-

### Operation

Source operation ID: `SveOperation_svadalp_s16_z`

**Operation**



Return a vector in which each active element *i* contains the value:



```text
op1[i] + (int16_t)op2[i * 2] + (int16_t)op2[i * 2 + 1]
```



Set the inactive elements of the result to zero.



The operation uses modulo arithmetic.  The behavior is therefore defined for all inputs; unlike C, there is no undefined behavior for signed overflow.



**[1]** Note that `result` must be in a different register from `op2`

## svadalp[_s32]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svadalp%5B_s32%5D_m

### Signature (source notation)

```c
svint32_t svadalp[_s32]_m(svbool_t pg, svint32_t op1, svint16_t op2);
```

### Description

Add and accumulate long pairwise

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Pairwise arithmetic / Pairwise addition and widen

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
    "register": "Zop2.H"
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
SADALP Ztied1.S, Pg/M, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SADALP--Signed-add-and-accumulate-long-pairwise-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SADALP Zresult.S, Pg/M, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SADALP--Signed-add-and-accumulate-long-pairwise-

### Operation

Source operation ID: `SveOperation_svadalp_s32_m`

**Operation**



Return a vector in which each active element *i* contains the value:



```text
op1[i] + (int32_t)op2[i * 2] + (int32_t)op2[i * 2 + 1]
```



Take the inactive elements of the result from the corresponding elements of `op1`.



The operation uses modulo arithmetic.  The behavior is therefore defined for all inputs; unlike C, there is no undefined behavior for signed overflow.

## svadalp[_s32]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svadalp%5B_s32%5D_x

### Signature (source notation)

```c
svint32_t svadalp[_s32]_x(svbool_t pg, svint32_t op1, svint16_t op2);
```

### Description

Add and accumulate long pairwise

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Pairwise arithmetic / Pairwise addition and widen

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
    "register": "Zop2.H"
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
SADALP Ztied1.S, Pg/M, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SADALP--Signed-add-and-accumulate-long-pairwise-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SADALP Zresult.S, Pg/M, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SADALP--Signed-add-and-accumulate-long-pairwise-

### Operation

Source operation ID: `SveOperation_svadalp_s32_x`

**Operation**



Return a vector in which each active element *i* contains the value:



```text
op1[i] + (int32_t)op2[i * 2] + (int32_t)op2[i * 2 + 1]
```



The inactive elements of the result have arbitrary, undefined values.



The operation uses modulo arithmetic.  The behavior is therefore defined for all inputs; unlike C, there is no undefined behavior for signed overflow.

## svadalp[_s32]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svadalp%5B_s32%5D_z

### Signature (source notation)

```c
svint32_t svadalp[_s32]_z(svbool_t pg, svint32_t op1, svint16_t op2);
```

### Description

Add and accumulate long pairwise

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Pairwise arithmetic / Pairwise addition and widen

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
    "register": "Zop2.H"
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
SADALP Zresult.S, Pg/M, Zop2.H  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SADALP--Signed-add-and-accumulate-long-pairwise-

### Operation

Source operation ID: `SveOperation_svadalp_s32_z`

**Operation**



Return a vector in which each active element *i* contains the value:



```text
op1[i] + (int32_t)op2[i * 2] + (int32_t)op2[i * 2 + 1]
```



Set the inactive elements of the result to zero.



The operation uses modulo arithmetic.  The behavior is therefore defined for all inputs; unlike C, there is no undefined behavior for signed overflow.



**[1]** Note that `result` must be in a different register from `op2`

## svadalp[_s64]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svadalp%5B_s64%5D_m

### Signature (source notation)

```c
svint64_t svadalp[_s64]_m(svbool_t pg, svint64_t op1, svint32_t op2);
```

### Description

Add and accumulate long pairwise

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Pairwise arithmetic / Pairwise addition and widen

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
    "register": "Zop2.S"
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
SADALP Ztied1.D, Pg/M, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SADALP--Signed-add-and-accumulate-long-pairwise-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SADALP Zresult.D, Pg/M, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SADALP--Signed-add-and-accumulate-long-pairwise-

### Operation

Source operation ID: `SveOperation_svadalp_s64_m`

**Operation**



Return a vector in which each active element *i* contains the value:



```text
op1[i] + (int64_t)op2[i * 2] + (int64_t)op2[i * 2 + 1]
```



Take the inactive elements of the result from the corresponding elements of `op1`.



The operation uses modulo arithmetic.  The behavior is therefore defined for all inputs; unlike C, there is no undefined behavior for signed overflow.

## svadalp[_s64]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svadalp%5B_s64%5D_x

### Signature (source notation)

```c
svint64_t svadalp[_s64]_x(svbool_t pg, svint64_t op1, svint32_t op2);
```

### Description

Add and accumulate long pairwise

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Pairwise arithmetic / Pairwise addition and widen

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
    "register": "Zop2.S"
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
SADALP Ztied1.D, Pg/M, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SADALP--Signed-add-and-accumulate-long-pairwise-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SADALP Zresult.D, Pg/M, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SADALP--Signed-add-and-accumulate-long-pairwise-

### Operation

Source operation ID: `SveOperation_svadalp_s64_x`

**Operation**



Return a vector in which each active element *i* contains the value:



```text
op1[i] + (int64_t)op2[i * 2] + (int64_t)op2[i * 2 + 1]
```



The inactive elements of the result have arbitrary, undefined values.



The operation uses modulo arithmetic.  The behavior is therefore defined for all inputs; unlike C, there is no undefined behavior for signed overflow.

## svadalp[_s64]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svadalp%5B_s64%5D_z

### Signature (source notation)

```c
svint64_t svadalp[_s64]_z(svbool_t pg, svint64_t op1, svint32_t op2);
```

### Description

Add and accumulate long pairwise

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Pairwise arithmetic / Pairwise addition and widen

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
    "register": "Zop2.S"
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
SADALP Zresult.D, Pg/M, Zop2.S  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SADALP--Signed-add-and-accumulate-long-pairwise-

### Operation

Source operation ID: `SveOperation_svadalp_s64_z`

**Operation**



Return a vector in which each active element *i* contains the value:



```text
op1[i] + (int64_t)op2[i * 2] + (int64_t)op2[i * 2 + 1]
```



Set the inactive elements of the result to zero.



The operation uses modulo arithmetic.  The behavior is therefore defined for all inputs; unlike C, there is no undefined behavior for signed overflow.



**[1]** Note that `result` must be in a different register from `op2`

## svadalp[_u16]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svadalp%5B_u16%5D_m

### Signature (source notation)

```c
svuint16_t svadalp[_u16]_m(svbool_t pg, svuint16_t op1, svuint8_t op2);
```

### Description

Add and accumulate long pairwise

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Pairwise arithmetic / Pairwise addition and widen

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
    "register": "Zop2.B"
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
UADALP Ztied1.H, Pg/M, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UADALP--Unsigned-add-and-accumulate-long-pairwise-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
UADALP Zresult.H, Pg/M, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UADALP--Unsigned-add-and-accumulate-long-pairwise-

### Operation

Source operation ID: `SveOperation_svadalp_u16_m`

**Operation**



Return a vector in which each active element *i* contains the value:



```text
op1[i] + (uint16_t)op2[i * 2] + (uint16_t)op2[i * 2 + 1]
```



Take the inactive elements of the result from the corresponding elements of `op1`.

## svadalp[_u16]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svadalp%5B_u16%5D_x

### Signature (source notation)

```c
svuint16_t svadalp[_u16]_x(svbool_t pg, svuint16_t op1, svuint8_t op2);
```

### Description

Add and accumulate long pairwise

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Pairwise arithmetic / Pairwise addition and widen

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
    "register": "Zop2.B"
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
UADALP Ztied1.H, Pg/M, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UADALP--Unsigned-add-and-accumulate-long-pairwise-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
UADALP Zresult.H, Pg/M, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UADALP--Unsigned-add-and-accumulate-long-pairwise-

### Operation

Source operation ID: `SveOperation_svadalp_u16_x`

**Operation**



Return a vector in which each active element *i* contains the value:



```text
op1[i] + (uint16_t)op2[i * 2] + (uint16_t)op2[i * 2 + 1]
```



The inactive elements of the result have arbitrary, undefined values.

## svadalp[_u16]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svadalp%5B_u16%5D_z

### Signature (source notation)

```c
svuint16_t svadalp[_u16]_z(svbool_t pg, svuint16_t op1, svuint8_t op2);
```

### Description

Add and accumulate long pairwise

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Pairwise arithmetic / Pairwise addition and widen

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
    "register": "Zop2.B"
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
UADALP Zresult.H, Pg/M, Zop2.B  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UADALP--Unsigned-add-and-accumulate-long-pairwise-

### Operation

Source operation ID: `SveOperation_svadalp_u16_z`

**Operation**



Return a vector in which each active element *i* contains the value:



```text
op1[i] + (uint16_t)op2[i * 2] + (uint16_t)op2[i * 2 + 1]
```



Set the inactive elements of the result to zero.



**[1]** Note that `result` must be in a different register from `op2`

## svadalp[_u32]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svadalp%5B_u32%5D_m

### Signature (source notation)

```c
svuint32_t svadalp[_u32]_m(svbool_t pg, svuint32_t op1, svuint16_t op2);
```

### Description

Add and accumulate long pairwise

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Pairwise arithmetic / Pairwise addition and widen

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
    "register": "Zop2.H"
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
UADALP Ztied1.S, Pg/M, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UADALP--Unsigned-add-and-accumulate-long-pairwise-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
UADALP Zresult.S, Pg/M, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UADALP--Unsigned-add-and-accumulate-long-pairwise-

### Operation

Source operation ID: `SveOperation_svadalp_u32_m`

**Operation**



Return a vector in which each active element *i* contains the value:



```text
op1[i] + (uint32_t)op2[i * 2] + (uint32_t)op2[i * 2 + 1]
```



Take the inactive elements of the result from the corresponding elements of `op1`.

## svadalp[_u32]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svadalp%5B_u32%5D_x

### Signature (source notation)

```c
svuint32_t svadalp[_u32]_x(svbool_t pg, svuint32_t op1, svuint16_t op2);
```

### Description

Add and accumulate long pairwise

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Pairwise arithmetic / Pairwise addition and widen

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
    "register": "Zop2.H"
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
UADALP Ztied1.S, Pg/M, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UADALP--Unsigned-add-and-accumulate-long-pairwise-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
UADALP Zresult.S, Pg/M, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UADALP--Unsigned-add-and-accumulate-long-pairwise-

### Operation

Source operation ID: `SveOperation_svadalp_u32_x`

**Operation**



Return a vector in which each active element *i* contains the value:



```text
op1[i] + (uint32_t)op2[i * 2] + (uint32_t)op2[i * 2 + 1]
```



The inactive elements of the result have arbitrary, undefined values.

## svadalp[_u32]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svadalp%5B_u32%5D_z

### Signature (source notation)

```c
svuint32_t svadalp[_u32]_z(svbool_t pg, svuint32_t op1, svuint16_t op2);
```

### Description

Add and accumulate long pairwise

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Pairwise arithmetic / Pairwise addition and widen

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
    "register": "Zop2.H"
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
UADALP Zresult.S, Pg/M, Zop2.H  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UADALP--Unsigned-add-and-accumulate-long-pairwise-

### Operation

Source operation ID: `SveOperation_svadalp_u32_z`

**Operation**



Return a vector in which each active element *i* contains the value:



```text
op1[i] + (uint32_t)op2[i * 2] + (uint32_t)op2[i * 2 + 1]
```



Set the inactive elements of the result to zero.



**[1]** Note that `result` must be in a different register from `op2`

## svadalp[_u64]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svadalp%5B_u64%5D_m

### Signature (source notation)

```c
svuint64_t svadalp[_u64]_m(svbool_t pg, svuint64_t op1, svuint32_t op2);
```

### Description

Add and accumulate long pairwise

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Pairwise arithmetic / Pairwise addition and widen

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
    "register": "Zop2.S"
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
UADALP Ztied1.D, Pg/M, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UADALP--Unsigned-add-and-accumulate-long-pairwise-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
UADALP Zresult.D, Pg/M, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UADALP--Unsigned-add-and-accumulate-long-pairwise-

### Operation

Source operation ID: `SveOperation_svadalp_u64_m`

**Operation**



Return a vector in which each active element *i* contains the value:



```text
op1[i] + (uint64_t)op2[i * 2] + (uint64_t)op2[i * 2 + 1]
```



Take the inactive elements of the result from the corresponding elements of `op1`.

## svadalp[_u64]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svadalp%5B_u64%5D_x

### Signature (source notation)

```c
svuint64_t svadalp[_u64]_x(svbool_t pg, svuint64_t op1, svuint32_t op2);
```

### Description

Add and accumulate long pairwise

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Pairwise arithmetic / Pairwise addition and widen

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
    "register": "Zop2.S"
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
UADALP Ztied1.D, Pg/M, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UADALP--Unsigned-add-and-accumulate-long-pairwise-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
UADALP Zresult.D, Pg/M, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UADALP--Unsigned-add-and-accumulate-long-pairwise-

### Operation

Source operation ID: `SveOperation_svadalp_u64_x`

**Operation**



Return a vector in which each active element *i* contains the value:



```text
op1[i] + (uint64_t)op2[i * 2] + (uint64_t)op2[i * 2 + 1]
```



The inactive elements of the result have arbitrary, undefined values.

## svadalp[_u64]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svadalp%5B_u64%5D_z

### Signature (source notation)

```c
svuint64_t svadalp[_u64]_z(svbool_t pg, svuint64_t op1, svuint32_t op2);
```

### Description

Add and accumulate long pairwise

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Pairwise arithmetic / Pairwise addition and widen

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
    "register": "Zop2.S"
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
UADALP Zresult.D, Pg/M, Zop2.S  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UADALP--Unsigned-add-and-accumulate-long-pairwise-

### Operation

Source operation ID: `SveOperation_svadalp_u64_z`

**Operation**



Return a vector in which each active element *i* contains the value:



```text
op1[i] + (uint64_t)op2[i * 2] + (uint64_t)op2[i * 2 + 1]
```



Set the inactive elements of the result to zero.



**[1]** Note that `result` must be in a different register from `op2`

