# SME / Vector arithmetic / Subtract / Saturating subtract — Part 3

## svqsubr[_u16]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqsubr%5B_u16%5D_m

### Signature (source notation)

```c
svuint16_t svqsubr[_u16]_m(svbool_t pg, svuint16_t op1, svuint16_t op2);
```

### Description

Saturating subtract reversed

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Subtract / Saturating subtract

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
UQSUBR Ztied1.H, Pg/M, Ztied1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQSUBR--Unsigned-saturating-subtraction-reversed--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
UQSUBR Zresult.H, Pg/M, Zresult.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQSUBR--Unsigned-saturating-subtraction-reversed--predicated--

### Operation

Source operation ID: `SveOperation_svqsubr_u16_m`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Subtract `op1[i]` from `op2[i]`.
- Saturate the result to the range of `uint16_t`.



Take the inactive elements of the result from the corresponding elements of `op1`.

## svqsubr[_u16]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqsubr%5B_u16%5D_x

### Signature (source notation)

```c
svuint16_t svqsubr[_u16]_x(svbool_t pg, svuint16_t op1, svuint16_t op2);
```

### Description

Saturating subtract reversed

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Subtract / Saturating subtract

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

When result and op1 are in the same register, this intrinsic can use:

```asm
UQSUBR Ztied1.H, Pg/M, Ztied1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQSUBR--Unsigned-saturating-subtraction-reversed--predicated--

When result and op2 are in the same register, this intrinsic can use:

```asm
UQSUB Ztied2.H, Pg/M, Ztied2.H, Zop1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQSUB--vectors--predicated---Unsigned-saturating-subtraction--predicated--

This intrinsic compiles to:

```asm
UQSUB Zresult.H, Zop2.H, Zop1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQSUB--vectors--unpredicated---Unsigned-saturating-subtract--unpredicated--

### Operation

Source operation ID: `SveOperation_svqsubr_u16_x`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Subtract `op1[i]` from `op2[i]`.
- Saturate the result to the range of `uint16_t`.



The inactive elements of the result have arbitrary, undefined values.

## svqsubr[_u16]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqsubr%5B_u16%5D_z

### Signature (source notation)

```c
svuint16_t svqsubr[_u16]_z(svbool_t pg, svuint16_t op1, svuint16_t op2);
```

### Description

Saturating subtract reversed

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Subtract / Saturating subtract

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
UQSUBR Zresult.H, Pg/M, Zresult.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQSUBR--Unsigned-saturating-subtraction-reversed--predicated--

When result is in a different register from op1, this intrinsic can use:

```asm
MOVPRFX Zresult.H, Pg/Z, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
UQSUB Zresult.H, Pg/M, Zresult.H, Zop1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQSUB--vectors--predicated---Unsigned-saturating-subtraction--predicated--

### Operation

Source operation ID: `SveOperation_svqsubr_u16_z`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Subtract `op1[i]` from `op2[i]`.
- Saturate the result to the range of `uint16_t`.



Set the inactive elements of the result to zero.

## svqsubr[_u32]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqsubr%5B_u32%5D_m

### Signature (source notation)

```c
svuint32_t svqsubr[_u32]_m(svbool_t pg, svuint32_t op1, svuint32_t op2);
```

### Description

Saturating subtract reversed

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Subtract / Saturating subtract

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
UQSUBR Ztied1.S, Pg/M, Ztied1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQSUBR--Unsigned-saturating-subtraction-reversed--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
UQSUBR Zresult.S, Pg/M, Zresult.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQSUBR--Unsigned-saturating-subtraction-reversed--predicated--

### Operation

Source operation ID: `SveOperation_svqsubr_u32_m`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Subtract `op1[i]` from `op2[i]`.
- Saturate the result to the range of `uint32_t`.



Take the inactive elements of the result from the corresponding elements of `op1`.

## svqsubr[_u32]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqsubr%5B_u32%5D_x

### Signature (source notation)

```c
svuint32_t svqsubr[_u32]_x(svbool_t pg, svuint32_t op1, svuint32_t op2);
```

### Description

Saturating subtract reversed

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Subtract / Saturating subtract

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

When result and op1 are in the same register, this intrinsic can use:

```asm
UQSUBR Ztied1.S, Pg/M, Ztied1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQSUBR--Unsigned-saturating-subtraction-reversed--predicated--

When result and op2 are in the same register, this intrinsic can use:

```asm
UQSUB Ztied2.S, Pg/M, Ztied2.S, Zop1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQSUB--vectors--predicated---Unsigned-saturating-subtraction--predicated--

This intrinsic compiles to:

```asm
UQSUB Zresult.S, Zop2.S, Zop1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQSUB--vectors--unpredicated---Unsigned-saturating-subtract--unpredicated--

### Operation

Source operation ID: `SveOperation_svqsubr_u32_x`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Subtract `op1[i]` from `op2[i]`.
- Saturate the result to the range of `uint32_t`.



The inactive elements of the result have arbitrary, undefined values.

## svqsubr[_u32]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqsubr%5B_u32%5D_z

### Signature (source notation)

```c
svuint32_t svqsubr[_u32]_z(svbool_t pg, svuint32_t op1, svuint32_t op2);
```

### Description

Saturating subtract reversed

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Subtract / Saturating subtract

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
UQSUBR Zresult.S, Pg/M, Zresult.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQSUBR--Unsigned-saturating-subtraction-reversed--predicated--

When result is in a different register from op1, this intrinsic can use:

```asm
MOVPRFX Zresult.S, Pg/Z, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
UQSUB Zresult.S, Pg/M, Zresult.S, Zop1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQSUB--vectors--predicated---Unsigned-saturating-subtraction--predicated--

### Operation

Source operation ID: `SveOperation_svqsubr_u32_z`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Subtract `op1[i]` from `op2[i]`.
- Saturate the result to the range of `uint32_t`.



Set the inactive elements of the result to zero.

## svqsubr[_u64]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqsubr%5B_u64%5D_m

### Signature (source notation)

```c
svuint64_t svqsubr[_u64]_m(svbool_t pg, svuint64_t op1, svuint64_t op2);
```

### Description

Saturating subtract reversed

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Subtract / Saturating subtract

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
UQSUBR Ztied1.D, Pg/M, Ztied1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQSUBR--Unsigned-saturating-subtraction-reversed--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
UQSUBR Zresult.D, Pg/M, Zresult.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQSUBR--Unsigned-saturating-subtraction-reversed--predicated--

### Operation

Source operation ID: `SveOperation_svqsubr_u64_m`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Subtract `op1[i]` from `op2[i]`.
- Saturate the result to the range of `uint64_t`.



Take the inactive elements of the result from the corresponding elements of `op1`.

## svqsubr[_u64]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqsubr%5B_u64%5D_x

### Signature (source notation)

```c
svuint64_t svqsubr[_u64]_x(svbool_t pg, svuint64_t op1, svuint64_t op2);
```

### Description

Saturating subtract reversed

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Subtract / Saturating subtract

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

When result and op1 are in the same register, this intrinsic can use:

```asm
UQSUBR Ztied1.D, Pg/M, Ztied1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQSUBR--Unsigned-saturating-subtraction-reversed--predicated--

When result and op2 are in the same register, this intrinsic can use:

```asm
UQSUB Ztied2.D, Pg/M, Ztied2.D, Zop1.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQSUB--vectors--predicated---Unsigned-saturating-subtraction--predicated--

This intrinsic compiles to:

```asm
UQSUB Zresult.D, Zop2.D, Zop1.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQSUB--vectors--unpredicated---Unsigned-saturating-subtract--unpredicated--

### Operation

Source operation ID: `SveOperation_svqsubr_u64_x`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Subtract `op1[i]` from `op2[i]`.
- Saturate the result to the range of `uint64_t`.



The inactive elements of the result have arbitrary, undefined values.

## svqsubr[_u64]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqsubr%5B_u64%5D_z

### Signature (source notation)

```c
svuint64_t svqsubr[_u64]_z(svbool_t pg, svuint64_t op1, svuint64_t op2);
```

### Description

Saturating subtract reversed

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Subtract / Saturating subtract

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
UQSUBR Zresult.D, Pg/M, Zresult.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQSUBR--Unsigned-saturating-subtraction-reversed--predicated--

When result is in a different register from op1, this intrinsic can use:

```asm
MOVPRFX Zresult.D, Pg/Z, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
UQSUB Zresult.D, Pg/M, Zresult.D, Zop1.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQSUB--vectors--predicated---Unsigned-saturating-subtraction--predicated--

### Operation

Source operation ID: `SveOperation_svqsubr_u64_z`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Subtract `op1[i]` from `op2[i]`.
- Saturate the result to the range of `uint64_t`.



Set the inactive elements of the result to zero.

## svqsubr[_u8]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqsubr%5B_u8%5D_m

### Signature (source notation)

```c
svuint8_t svqsubr[_u8]_m(svbool_t pg, svuint8_t op1, svuint8_t op2);
```

### Description

Saturating subtract reversed

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Subtract / Saturating subtract

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
UQSUBR Ztied1.B, Pg/M, Ztied1.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQSUBR--Unsigned-saturating-subtraction-reversed--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
UQSUBR Zresult.B, Pg/M, Zresult.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQSUBR--Unsigned-saturating-subtraction-reversed--predicated--

### Operation

Source operation ID: `SveOperation_svqsubr_u8_m`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Subtract `op1[i]` from `op2[i]`.
- Saturate the result to the range of `uint8_t`.



Take the inactive elements of the result from the corresponding elements of `op1`.

## svqsubr[_u8]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqsubr%5B_u8%5D_x

### Signature (source notation)

```c
svuint8_t svqsubr[_u8]_x(svbool_t pg, svuint8_t op1, svuint8_t op2);
```

### Description

Saturating subtract reversed

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Subtract / Saturating subtract

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

When result and op1 are in the same register, this intrinsic can use:

```asm
UQSUBR Ztied1.B, Pg/M, Ztied1.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQSUBR--Unsigned-saturating-subtraction-reversed--predicated--

When result and op2 are in the same register, this intrinsic can use:

```asm
UQSUB Ztied2.B, Pg/M, Ztied2.B, Zop1.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQSUB--vectors--predicated---Unsigned-saturating-subtraction--predicated--

This intrinsic compiles to:

```asm
UQSUB Zresult.B, Zop2.B, Zop1.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQSUB--vectors--unpredicated---Unsigned-saturating-subtract--unpredicated--

### Operation

Source operation ID: `SveOperation_svqsubr_u8_x`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Subtract `op1[i]` from `op2[i]`.
- Saturate the result to the range of `uint8_t`.



The inactive elements of the result have arbitrary, undefined values.

## svqsubr[_u8]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqsubr%5B_u8%5D_z

### Signature (source notation)

```c
svuint8_t svqsubr[_u8]_z(svbool_t pg, svuint8_t op1, svuint8_t op2);
```

### Description

Saturating subtract reversed

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Subtract / Saturating subtract

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
UQSUBR Zresult.B, Pg/M, Zresult.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQSUBR--Unsigned-saturating-subtraction-reversed--predicated--

When result is in a different register from op1, this intrinsic can use:

```asm
MOVPRFX Zresult.B, Pg/Z, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
UQSUB Zresult.B, Pg/M, Zresult.B, Zop1.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQSUB--vectors--predicated---Unsigned-saturating-subtraction--predicated--

### Operation

Source operation ID: `SveOperation_svqsubr_u8_z`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Subtract `op1[i]` from `op2[i]`.
- Saturate the result to the range of `uint8_t`.



Set the inactive elements of the result to zero.

