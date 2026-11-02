# SME / Vector arithmetic / Maximum — Part 2

## svmax[_s64]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmax%5B_s64%5D_z

### Signature (source notation)

```c
svint64_t svmax[_s64]_z(svbool_t pg, svint64_t op1, svint64_t op2);
```

### Description

Maximum

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Maximum

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
SMAX Zresult.D, Pg/M, Zresult.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SMAX--vectors---Signed-maximum--predicated--

When result is in a different register from op1, this intrinsic can use:

```asm
MOVPRFX Zresult.D, Pg/Z, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
SMAX Zresult.D, Pg/M, Zresult.D, Zop1.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SMAX--vectors---Signed-maximum--predicated--

### Operation

Source operation ID: `SveOperation_svmax_s8_z`

**Operation**



Return a vector in which each active element *i* contains the maximum of `op1[i]` and `op2[i]`. Set the inactive elements of the result to zero.

## svmax[_s8]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmax%5B_s8%5D_m

### Signature (source notation)

```c
svint8_t svmax[_s8]_m(svbool_t pg, svint8_t op1, svint8_t op2);
```

### Description

Maximum

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Maximum

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
SMAX Ztied1.B, Pg/M, Ztied1.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SMAX--vectors---Signed-maximum--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SMAX Zresult.B, Pg/M, Zresult.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SMAX--vectors---Signed-maximum--predicated--

### Operation

Source operation ID: `SveOperation_svmax_s8_m`

**Operation**



Return a vector in which each active element *i* contains the maximum of `op1[i]` and `op2[i]`. Take the inactive elements of the result from the corresponding elements of `op1`.

## svmax[_s8]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmax%5B_s8%5D_x

### Signature (source notation)

```c
svint8_t svmax[_s8]_x(svbool_t pg, svint8_t op1, svint8_t op2);
```

### Description

Maximum

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Maximum

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
SMAX Ztied1.B, Pg/M, Ztied1.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SMAX--vectors---Signed-maximum--predicated--

When result and op2 are in the same register, this intrinsic compiles to:

```asm
SMAX Ztied2.B, Pg/M, Ztied2.B, Zop1.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SMAX--vectors---Signed-maximum--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SMAX Zresult.B, Pg/M, Zresult.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SMAX--vectors---Signed-maximum--predicated--

### Operation

Source operation ID: `SveOperation_svmax_s8_x`

**Operation**



Return a vector in which each active element *i* contains the maximum of `op1[i]` and `op2[i]`. The inactive elements of the result have arbitrary, undefined values.

## svmax[_s8]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmax%5B_s8%5D_z

### Signature (source notation)

```c
svint8_t svmax[_s8]_z(svbool_t pg, svint8_t op1, svint8_t op2);
```

### Description

Maximum

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Maximum

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
SMAX Zresult.B, Pg/M, Zresult.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SMAX--vectors---Signed-maximum--predicated--

When result is in a different register from op1, this intrinsic can use:

```asm
MOVPRFX Zresult.B, Pg/Z, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
SMAX Zresult.B, Pg/M, Zresult.B, Zop1.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SMAX--vectors---Signed-maximum--predicated--

### Operation

Source operation ID: `SveOperation_svmax_s8_z`

**Operation**



Return a vector in which each active element *i* contains the maximum of `op1[i]` and `op2[i]`. Set the inactive elements of the result to zero.

## svmax[_u16]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmax%5B_u16%5D_m

### Signature (source notation)

```c
svuint16_t svmax[_u16]_m(svbool_t pg, svuint16_t op1, svuint16_t op2);
```

### Description

Maximum

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Maximum

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
UMAX Ztied1.H, Pg/M, Ztied1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UMAX--vectors---Unsigned-maximum--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
UMAX Zresult.H, Pg/M, Zresult.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UMAX--vectors---Unsigned-maximum--predicated--

### Operation

Source operation ID: `SveOperation_svmax_s8_m`

**Operation**



Return a vector in which each active element *i* contains the maximum of `op1[i]` and `op2[i]`. Take the inactive elements of the result from the corresponding elements of `op1`.

## svmax[_u16]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmax%5B_u16%5D_x

### Signature (source notation)

```c
svuint16_t svmax[_u16]_x(svbool_t pg, svuint16_t op1, svuint16_t op2);
```

### Description

Maximum

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Maximum

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
UMAX Ztied1.H, Pg/M, Ztied1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UMAX--vectors---Unsigned-maximum--predicated--

When result and op2 are in the same register, this intrinsic compiles to:

```asm
UMAX Ztied2.H, Pg/M, Ztied2.H, Zop1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UMAX--vectors---Unsigned-maximum--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
UMAX Zresult.H, Pg/M, Zresult.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UMAX--vectors---Unsigned-maximum--predicated--

### Operation

Source operation ID: `SveOperation_svmax_s8_x`

**Operation**



Return a vector in which each active element *i* contains the maximum of `op1[i]` and `op2[i]`. The inactive elements of the result have arbitrary, undefined values.

## svmax[_u16]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmax%5B_u16%5D_z

### Signature (source notation)

```c
svuint16_t svmax[_u16]_z(svbool_t pg, svuint16_t op1, svuint16_t op2);
```

### Description

Maximum

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Maximum

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
UMAX Zresult.H, Pg/M, Zresult.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UMAX--vectors---Unsigned-maximum--predicated--

When result is in a different register from op1, this intrinsic can use:

```asm
MOVPRFX Zresult.H, Pg/Z, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
UMAX Zresult.H, Pg/M, Zresult.H, Zop1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UMAX--vectors---Unsigned-maximum--predicated--

### Operation

Source operation ID: `SveOperation_svmax_s8_z`

**Operation**



Return a vector in which each active element *i* contains the maximum of `op1[i]` and `op2[i]`. Set the inactive elements of the result to zero.

## svmax[_u32]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmax%5B_u32%5D_m

### Signature (source notation)

```c
svuint32_t svmax[_u32]_m(svbool_t pg, svuint32_t op1, svuint32_t op2);
```

### Description

Maximum

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Maximum

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
UMAX Ztied1.S, Pg/M, Ztied1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UMAX--vectors---Unsigned-maximum--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
UMAX Zresult.S, Pg/M, Zresult.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UMAX--vectors---Unsigned-maximum--predicated--

### Operation

Source operation ID: `SveOperation_svmax_s8_m`

**Operation**



Return a vector in which each active element *i* contains the maximum of `op1[i]` and `op2[i]`. Take the inactive elements of the result from the corresponding elements of `op1`.

## svmax[_u32]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmax%5B_u32%5D_x

### Signature (source notation)

```c
svuint32_t svmax[_u32]_x(svbool_t pg, svuint32_t op1, svuint32_t op2);
```

### Description

Maximum

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Maximum

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
UMAX Ztied1.S, Pg/M, Ztied1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UMAX--vectors---Unsigned-maximum--predicated--

When result and op2 are in the same register, this intrinsic compiles to:

```asm
UMAX Ztied2.S, Pg/M, Ztied2.S, Zop1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UMAX--vectors---Unsigned-maximum--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
UMAX Zresult.S, Pg/M, Zresult.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UMAX--vectors---Unsigned-maximum--predicated--

### Operation

Source operation ID: `SveOperation_svmax_s8_x`

**Operation**



Return a vector in which each active element *i* contains the maximum of `op1[i]` and `op2[i]`. The inactive elements of the result have arbitrary, undefined values.

## svmax[_u32]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmax%5B_u32%5D_z

### Signature (source notation)

```c
svuint32_t svmax[_u32]_z(svbool_t pg, svuint32_t op1, svuint32_t op2);
```

### Description

Maximum

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Maximum

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
UMAX Zresult.S, Pg/M, Zresult.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UMAX--vectors---Unsigned-maximum--predicated--

When result is in a different register from op1, this intrinsic can use:

```asm
MOVPRFX Zresult.S, Pg/Z, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
UMAX Zresult.S, Pg/M, Zresult.S, Zop1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UMAX--vectors---Unsigned-maximum--predicated--

### Operation

Source operation ID: `SveOperation_svmax_s8_z`

**Operation**



Return a vector in which each active element *i* contains the maximum of `op1[i]` and `op2[i]`. Set the inactive elements of the result to zero.

## svmax[_u64]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmax%5B_u64%5D_m

### Signature (source notation)

```c
svuint64_t svmax[_u64]_m(svbool_t pg, svuint64_t op1, svuint64_t op2);
```

### Description

Maximum

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Maximum

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
UMAX Ztied1.D, Pg/M, Ztied1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UMAX--vectors---Unsigned-maximum--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
UMAX Zresult.D, Pg/M, Zresult.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UMAX--vectors---Unsigned-maximum--predicated--

### Operation

Source operation ID: `SveOperation_svmax_s8_m`

**Operation**



Return a vector in which each active element *i* contains the maximum of `op1[i]` and `op2[i]`. Take the inactive elements of the result from the corresponding elements of `op1`.

## svmax[_u64]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmax%5B_u64%5D_x

### Signature (source notation)

```c
svuint64_t svmax[_u64]_x(svbool_t pg, svuint64_t op1, svuint64_t op2);
```

### Description

Maximum

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Maximum

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
UMAX Ztied1.D, Pg/M, Ztied1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UMAX--vectors---Unsigned-maximum--predicated--

When result and op2 are in the same register, this intrinsic compiles to:

```asm
UMAX Ztied2.D, Pg/M, Ztied2.D, Zop1.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UMAX--vectors---Unsigned-maximum--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
UMAX Zresult.D, Pg/M, Zresult.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UMAX--vectors---Unsigned-maximum--predicated--

### Operation

Source operation ID: `SveOperation_svmax_s8_x`

**Operation**



Return a vector in which each active element *i* contains the maximum of `op1[i]` and `op2[i]`. The inactive elements of the result have arbitrary, undefined values.

## svmax[_u64]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmax%5B_u64%5D_z

### Signature (source notation)

```c
svuint64_t svmax[_u64]_z(svbool_t pg, svuint64_t op1, svuint64_t op2);
```

### Description

Maximum

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Maximum

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
UMAX Zresult.D, Pg/M, Zresult.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UMAX--vectors---Unsigned-maximum--predicated--

When result is in a different register from op1, this intrinsic can use:

```asm
MOVPRFX Zresult.D, Pg/Z, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
UMAX Zresult.D, Pg/M, Zresult.D, Zop1.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UMAX--vectors---Unsigned-maximum--predicated--

### Operation

Source operation ID: `SveOperation_svmax_s8_z`

**Operation**



Return a vector in which each active element *i* contains the maximum of `op1[i]` and `op2[i]`. Set the inactive elements of the result to zero.

## svmax[_u8]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmax%5B_u8%5D_m

### Signature (source notation)

```c
svuint8_t svmax[_u8]_m(svbool_t pg, svuint8_t op1, svuint8_t op2);
```

### Description

Maximum

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Maximum

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
UMAX Ztied1.B, Pg/M, Ztied1.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UMAX--vectors---Unsigned-maximum--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
UMAX Zresult.B, Pg/M, Zresult.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UMAX--vectors---Unsigned-maximum--predicated--

### Operation

Source operation ID: `SveOperation_svmax_s8_m`

**Operation**



Return a vector in which each active element *i* contains the maximum of `op1[i]` and `op2[i]`. Take the inactive elements of the result from the corresponding elements of `op1`.

## svmax[_u8]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmax%5B_u8%5D_x

### Signature (source notation)

```c
svuint8_t svmax[_u8]_x(svbool_t pg, svuint8_t op1, svuint8_t op2);
```

### Description

Maximum

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Maximum

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
UMAX Ztied1.B, Pg/M, Ztied1.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UMAX--vectors---Unsigned-maximum--predicated--

When result and op2 are in the same register, this intrinsic compiles to:

```asm
UMAX Ztied2.B, Pg/M, Ztied2.B, Zop1.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UMAX--vectors---Unsigned-maximum--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
UMAX Zresult.B, Pg/M, Zresult.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UMAX--vectors---Unsigned-maximum--predicated--

### Operation

Source operation ID: `SveOperation_svmax_s8_x`

**Operation**



Return a vector in which each active element *i* contains the maximum of `op1[i]` and `op2[i]`. The inactive elements of the result have arbitrary, undefined values.

## svmax[_u8]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmax%5B_u8%5D_z

### Signature (source notation)

```c
svuint8_t svmax[_u8]_z(svbool_t pg, svuint8_t op1, svuint8_t op2);
```

### Description

Maximum

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Maximum

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
UMAX Zresult.B, Pg/M, Zresult.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UMAX--vectors---Unsigned-maximum--predicated--

When result is in a different register from op1, this intrinsic can use:

```asm
MOVPRFX Zresult.B, Pg/Z, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
UMAX Zresult.B, Pg/M, Zresult.B, Zop1.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UMAX--vectors---Unsigned-maximum--predicated--

### Operation

Source operation ID: `SveOperation_svmax_s8_z`

**Operation**



Return a vector in which each active element *i* contains the maximum of `op1[i]` and `op2[i]`. Set the inactive elements of the result to zero.

## svmaxnm[_f16]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmaxnm%5B_f16%5D_m

### Signature (source notation)

```c
svfloat16_t svmaxnm[_f16]_m(svbool_t pg, svfloat16_t op1, svfloat16_t op2);
```

### Description

Maximum number

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Maximum

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
  "return_base_type": "float",
  "element_bit_size": "16",
  "value": "svfloat16_t"
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
FMAXNM Ztied1.H, Pg/M, Ztied1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMAXNM--vectors---Floating-point-maximum-number--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FMAXNM Zresult.H, Pg/M, Zresult.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMAXNM--vectors---Floating-point-maximum-number--predicated--

### Operation

Source operation ID: `SveOperation_svmaxnm_f16_m`

**Operation**



Return a vector in which each active element *i* contains the maximum of `op1[i]` and `op2[i]`. Take the inactive elements of the result from the corresponding elements of `op1`.



This maximum operation works as follows:




- The maximum of a signaling NaN and anything else is a signaling NaN.
- The maximum of two quiet NaNs is a quiet NaN.
- Otherwise, the maximum of a quiet NaN and another value is the other value.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.

## svmaxnm[_f16]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmaxnm%5B_f16%5D_x

### Signature (source notation)

```c
svfloat16_t svmaxnm[_f16]_x(svbool_t pg, svfloat16_t op1, svfloat16_t op2);
```

### Description

Maximum number

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Maximum

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
  "return_base_type": "float",
  "element_bit_size": "16",
  "value": "svfloat16_t"
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
FMAXNM Ztied1.H, Pg/M, Ztied1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMAXNM--vectors---Floating-point-maximum-number--predicated--

When result and op2 are in the same register, this intrinsic compiles to:

```asm
FMAXNM Ztied2.H, Pg/M, Ztied2.H, Zop1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMAXNM--vectors---Floating-point-maximum-number--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FMAXNM Zresult.H, Pg/M, Zresult.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMAXNM--vectors---Floating-point-maximum-number--predicated--

### Operation

Source operation ID: `SveOperation_svmaxnm_f16_x`

**Operation**



Return a vector in which each active element *i* contains the maximum of `op1[i]` and `op2[i]`. The inactive elements of the result have arbitrary, undefined values.



This maximum operation works as follows:




- The maximum of a signaling NaN and anything else is a signaling NaN.
- The maximum of two quiet NaNs is a quiet NaN.
- Otherwise, the maximum of a quiet NaN and another value is the other value.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.

## svmaxnm[_f16]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmaxnm%5B_f16%5D_z

### Signature (source notation)

```c
svfloat16_t svmaxnm[_f16]_z(svbool_t pg, svfloat16_t op1, svfloat16_t op2);
```

### Description

Maximum number

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Maximum

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
  "return_base_type": "float",
  "element_bit_size": "16",
  "value": "svfloat16_t"
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
FMAXNM Zresult.H, Pg/M, Zresult.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMAXNM--vectors---Floating-point-maximum-number--predicated--

When result is in a different register from op1, this intrinsic can use:

```asm
MOVPRFX Zresult.H, Pg/Z, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
FMAXNM Zresult.H, Pg/M, Zresult.H, Zop1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMAXNM--vectors---Floating-point-maximum-number--predicated--

### Operation

Source operation ID: `SveOperation_svmaxnm_f16_z`

**Operation**



Return a vector in which each active element *i* contains the maximum of `op1[i]` and `op2[i]`. Set the inactive elements of the result to zero.



This maximum operation works as follows:




- The maximum of a signaling NaN and anything else is a signaling NaN.
- The maximum of two quiet NaNs is a quiet NaN.
- Otherwise, the maximum of a quiet NaN and another value is the other value.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.

## svmaxnm[_f32]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmaxnm%5B_f32%5D_m

### Signature (source notation)

```c
svfloat32_t svmaxnm[_f32]_m(svbool_t pg, svfloat32_t op1, svfloat32_t op2);
```

### Description

Maximum number

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Maximum

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
  "return_base_type": "float",
  "element_bit_size": "32",
  "value": "svfloat32_t"
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
FMAXNM Ztied1.S, Pg/M, Ztied1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMAXNM--vectors---Floating-point-maximum-number--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FMAXNM Zresult.S, Pg/M, Zresult.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMAXNM--vectors---Floating-point-maximum-number--predicated--

### Operation

Source operation ID: `SveOperation_svmaxnm_f16_m`

**Operation**



Return a vector in which each active element *i* contains the maximum of `op1[i]` and `op2[i]`. Take the inactive elements of the result from the corresponding elements of `op1`.



This maximum operation works as follows:




- The maximum of a signaling NaN and anything else is a signaling NaN.
- The maximum of two quiet NaNs is a quiet NaN.
- Otherwise, the maximum of a quiet NaN and another value is the other value.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.

## svmaxnm[_f32]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmaxnm%5B_f32%5D_x

### Signature (source notation)

```c
svfloat32_t svmaxnm[_f32]_x(svbool_t pg, svfloat32_t op1, svfloat32_t op2);
```

### Description

Maximum number

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Maximum

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
  "return_base_type": "float",
  "element_bit_size": "32",
  "value": "svfloat32_t"
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
FMAXNM Ztied1.S, Pg/M, Ztied1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMAXNM--vectors---Floating-point-maximum-number--predicated--

When result and op2 are in the same register, this intrinsic compiles to:

```asm
FMAXNM Ztied2.S, Pg/M, Ztied2.S, Zop1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMAXNM--vectors---Floating-point-maximum-number--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FMAXNM Zresult.S, Pg/M, Zresult.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMAXNM--vectors---Floating-point-maximum-number--predicated--

### Operation

Source operation ID: `SveOperation_svmaxnm_f16_x`

**Operation**



Return a vector in which each active element *i* contains the maximum of `op1[i]` and `op2[i]`. The inactive elements of the result have arbitrary, undefined values.



This maximum operation works as follows:




- The maximum of a signaling NaN and anything else is a signaling NaN.
- The maximum of two quiet NaNs is a quiet NaN.
- Otherwise, the maximum of a quiet NaN and another value is the other value.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.

## svmaxnm[_f32]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmaxnm%5B_f32%5D_z

### Signature (source notation)

```c
svfloat32_t svmaxnm[_f32]_z(svbool_t pg, svfloat32_t op1, svfloat32_t op2);
```

### Description

Maximum number

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Maximum

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
  "return_base_type": "float",
  "element_bit_size": "32",
  "value": "svfloat32_t"
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
FMAXNM Zresult.S, Pg/M, Zresult.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMAXNM--vectors---Floating-point-maximum-number--predicated--

When result is in a different register from op1, this intrinsic can use:

```asm
MOVPRFX Zresult.S, Pg/Z, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
FMAXNM Zresult.S, Pg/M, Zresult.S, Zop1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMAXNM--vectors---Floating-point-maximum-number--predicated--

### Operation

Source operation ID: `SveOperation_svmaxnm_f16_z`

**Operation**



Return a vector in which each active element *i* contains the maximum of `op1[i]` and `op2[i]`. Set the inactive elements of the result to zero.



This maximum operation works as follows:




- The maximum of a signaling NaN and anything else is a signaling NaN.
- The maximum of two quiet NaNs is a quiet NaN.
- Otherwise, the maximum of a quiet NaN and another value is the other value.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.

## svmaxnm[_f64]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmaxnm%5B_f64%5D_m

### Signature (source notation)

```c
svfloat64_t svmaxnm[_f64]_m(svbool_t pg, svfloat64_t op1, svfloat64_t op2);
```

### Description

Maximum number

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Maximum

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
  "return_base_type": "float",
  "element_bit_size": "64",
  "value": "svfloat64_t"
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
FMAXNM Ztied1.D, Pg/M, Ztied1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMAXNM--vectors---Floating-point-maximum-number--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FMAXNM Zresult.D, Pg/M, Zresult.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMAXNM--vectors---Floating-point-maximum-number--predicated--

### Operation

Source operation ID: `SveOperation_svmaxnm_f16_m`

**Operation**



Return a vector in which each active element *i* contains the maximum of `op1[i]` and `op2[i]`. Take the inactive elements of the result from the corresponding elements of `op1`.



This maximum operation works as follows:




- The maximum of a signaling NaN and anything else is a signaling NaN.
- The maximum of two quiet NaNs is a quiet NaN.
- Otherwise, the maximum of a quiet NaN and another value is the other value.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.

## svmaxnm[_f64]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmaxnm%5B_f64%5D_x

### Signature (source notation)

```c
svfloat64_t svmaxnm[_f64]_x(svbool_t pg, svfloat64_t op1, svfloat64_t op2);
```

### Description

Maximum number

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Maximum

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
  "return_base_type": "float",
  "element_bit_size": "64",
  "value": "svfloat64_t"
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
FMAXNM Ztied1.D, Pg/M, Ztied1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMAXNM--vectors---Floating-point-maximum-number--predicated--

When result and op2 are in the same register, this intrinsic compiles to:

```asm
FMAXNM Ztied2.D, Pg/M, Ztied2.D, Zop1.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMAXNM--vectors---Floating-point-maximum-number--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FMAXNM Zresult.D, Pg/M, Zresult.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMAXNM--vectors---Floating-point-maximum-number--predicated--

### Operation

Source operation ID: `SveOperation_svmaxnm_f16_x`

**Operation**



Return a vector in which each active element *i* contains the maximum of `op1[i]` and `op2[i]`. The inactive elements of the result have arbitrary, undefined values.



This maximum operation works as follows:




- The maximum of a signaling NaN and anything else is a signaling NaN.
- The maximum of two quiet NaNs is a quiet NaN.
- Otherwise, the maximum of a quiet NaN and another value is the other value.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.

## svmaxnm[_f64]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmaxnm%5B_f64%5D_z

### Signature (source notation)

```c
svfloat64_t svmaxnm[_f64]_z(svbool_t pg, svfloat64_t op1, svfloat64_t op2);
```

### Description

Maximum number

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Maximum

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
  "return_base_type": "float",
  "element_bit_size": "64",
  "value": "svfloat64_t"
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
FMAXNM Zresult.D, Pg/M, Zresult.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMAXNM--vectors---Floating-point-maximum-number--predicated--

When result is in a different register from op1, this intrinsic can use:

```asm
MOVPRFX Zresult.D, Pg/Z, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
FMAXNM Zresult.D, Pg/M, Zresult.D, Zop1.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMAXNM--vectors---Floating-point-maximum-number--predicated--

### Operation

Source operation ID: `SveOperation_svmaxnm_f16_z`

**Operation**



Return a vector in which each active element *i* contains the maximum of `op1[i]` and `op2[i]`. Set the inactive elements of the result to zero.



This maximum operation works as follows:




- The maximum of a signaling NaN and anything else is a signaling NaN.
- The maximum of two quiet NaNs is a quiet NaN.
- Otherwise, the maximum of a quiet NaN and another value is the other value.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.

## svmaxnm[_n_f16]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmaxnm%5B_n_f16%5D_m

### Signature (source notation)

```c
svfloat16_t svmaxnm[_n_f16]_m(svbool_t pg, svfloat16_t op1, float16_t op2);
```

### Description

Maximum number

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Maximum

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
  "return_base_type": "float",
  "element_bit_size": "16",
  "value": "svfloat16_t"
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

When op2 is 0.0 or 1.0, this intrinsic can use:

```asm
FMAXNM Ztied1.H, Pg/M, Ztied1.H, #op2  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMAXNM--immediate---Floating-point-maximum-number-with-immediate--predicated--

The general implementation is:

```asm
FMAXNM Ztied1.H, Pg/M, Ztied1.H, Zop2.H  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMAXNM--vectors---Floating-point-maximum-number--predicated--

### Operation

Source operation ID: `SveOperation_svmaxnm_n_f16_m`

**Operation**



Return a vector in which each active element *i* contains the maximum of `op1[i]` and `op2`. Take the inactive elements of the result from the corresponding elements of `op1`.



This maximum operation works as follows:




- The maximum of a signaling NaN and anything else is a signaling NaN.
- The maximum of two quiet NaNs is a quiet NaN.
- Otherwise, the maximum of a quiet NaN and another value is the other value.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.



**[1]** If instead `result` is in a different register from the inputs, the compiler can add a preceding [MOVPRFX (unpredicated)](https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--) instruction

## svmaxnm[_n_f16]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmaxnm%5B_n_f16%5D_x

### Signature (source notation)

```c
svfloat16_t svmaxnm[_n_f16]_x(svbool_t pg, svfloat16_t op1, float16_t op2);
```

### Description

Maximum number

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Maximum

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
  "return_base_type": "float",
  "element_bit_size": "16",
  "value": "svfloat16_t"
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

When op2 is 0.0 or 1.0, this intrinsic can use:

```asm
FMAXNM Ztied1.H, Pg/M, Ztied1.H, #op2  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMAXNM--immediate---Floating-point-maximum-number-with-immediate--predicated--

When result and op1 are in the same register, the general implementation is:

```asm
FMAXNM Ztied1.H, Pg/M, Ztied1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMAXNM--vectors---Floating-point-maximum-number--predicated--

When result and op2 are in the same register, the general implementation is:

```asm
FMAXNM Ztied2.H, Pg/M, Ztied2.H, Zop1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMAXNM--vectors---Floating-point-maximum-number--predicated--

When result is in a different register from the inputs, the general implementation is:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FMAXNM Zresult.H, Pg/M, Zresult.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMAXNM--vectors---Floating-point-maximum-number--predicated--

### Operation

Source operation ID: `SveOperation_svmaxnm_n_f16_x`

**Operation**



Return a vector in which each active element *i* contains the maximum of `op1[i]` and `op2`. The inactive elements of the result have arbitrary, undefined values.



This maximum operation works as follows:




- The maximum of a signaling NaN and anything else is a signaling NaN.
- The maximum of two quiet NaNs is a quiet NaN.
- Otherwise, the maximum of a quiet NaN and another value is the other value.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.



**[1]** If instead `result` is in a different register from the inputs, the compiler can add a preceding [MOVPRFX (unpredicated)](https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--) instruction

## svmaxnm[_n_f16]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmaxnm%5B_n_f16%5D_z

### Signature (source notation)

```c
svfloat16_t svmaxnm[_n_f16]_z(svbool_t pg, svfloat16_t op1, float16_t op2);
```

### Description

Maximum number

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Maximum

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
  "return_base_type": "float",
  "element_bit_size": "16",
  "value": "svfloat16_t"
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

When op2 is 0.0 or 1.0, this intrinsic can use:

```asm
MOVPRFX Zresult.H, Pg/Z, Zop1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
FMAXNM Zresult.H, Pg/M, Zresult.H, #op2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMAXNM--immediate---Floating-point-maximum-number-with-immediate--predicated--

When result is in a different register from op2, this intrinsic can use:

```asm
MOVPRFX Zresult.H, Pg/Z, Zop1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
FMAXNM Zresult.H, Pg/M, Zresult.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMAXNM--vectors---Floating-point-maximum-number--predicated--

When result is in a different register from op1, this intrinsic can use:

```asm
MOVPRFX Zresult.H, Pg/Z, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
FMAXNM Zresult.H, Pg/M, Zresult.H, Zop1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMAXNM--vectors---Floating-point-maximum-number--predicated--

### Operation

Source operation ID: `SveOperation_svmaxnm_n_f16_z`

**Operation**



Return a vector in which each active element *i* contains the maximum of `op1[i]` and `op2`. Set the inactive elements of the result to zero.



This maximum operation works as follows:




- The maximum of a signaling NaN and anything else is a signaling NaN.
- The maximum of two quiet NaNs is a quiet NaN.
- Otherwise, the maximum of a quiet NaN and another value is the other value.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.

## svmaxnm[_n_f32]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmaxnm%5B_n_f32%5D_m

### Signature (source notation)

```c
svfloat32_t svmaxnm[_n_f32]_m(svbool_t pg, svfloat32_t op1, float32_t op2);
```

### Description

Maximum number

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Maximum

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
  "return_base_type": "float",
  "element_bit_size": "32",
  "value": "svfloat32_t"
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

When op2 is 0.0 or 1.0, this intrinsic can use:

```asm
FMAXNM Ztied1.S, Pg/M, Ztied1.S, #op2  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMAXNM--immediate---Floating-point-maximum-number-with-immediate--predicated--

The general implementation is:

```asm
FMAXNM Ztied1.S, Pg/M, Ztied1.S, Zop2.S  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMAXNM--vectors---Floating-point-maximum-number--predicated--

### Operation

Source operation ID: `SveOperation_svmaxnm_n_f16_m`

**Operation**



Return a vector in which each active element *i* contains the maximum of `op1[i]` and `op2`. Take the inactive elements of the result from the corresponding elements of `op1`.



This maximum operation works as follows:




- The maximum of a signaling NaN and anything else is a signaling NaN.
- The maximum of two quiet NaNs is a quiet NaN.
- Otherwise, the maximum of a quiet NaN and another value is the other value.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.



**[1]** If instead `result` is in a different register from the inputs, the compiler can add a preceding [MOVPRFX (unpredicated)](https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--) instruction

## svmaxnm[_n_f32]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmaxnm%5B_n_f32%5D_x

### Signature (source notation)

```c
svfloat32_t svmaxnm[_n_f32]_x(svbool_t pg, svfloat32_t op1, float32_t op2);
```

### Description

Maximum number

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Maximum

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
  "return_base_type": "float",
  "element_bit_size": "32",
  "value": "svfloat32_t"
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

When op2 is 0.0 or 1.0, this intrinsic can use:

```asm
FMAXNM Ztied1.S, Pg/M, Ztied1.S, #op2  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMAXNM--immediate---Floating-point-maximum-number-with-immediate--predicated--

When result and op1 are in the same register, the general implementation is:

```asm
FMAXNM Ztied1.S, Pg/M, Ztied1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMAXNM--vectors---Floating-point-maximum-number--predicated--

When result and op2 are in the same register, the general implementation is:

```asm
FMAXNM Ztied2.S, Pg/M, Ztied2.S, Zop1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMAXNM--vectors---Floating-point-maximum-number--predicated--

When result is in a different register from the inputs, the general implementation is:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FMAXNM Zresult.S, Pg/M, Zresult.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMAXNM--vectors---Floating-point-maximum-number--predicated--

### Operation

Source operation ID: `SveOperation_svmaxnm_n_f16_x`

**Operation**



Return a vector in which each active element *i* contains the maximum of `op1[i]` and `op2`. The inactive elements of the result have arbitrary, undefined values.



This maximum operation works as follows:




- The maximum of a signaling NaN and anything else is a signaling NaN.
- The maximum of two quiet NaNs is a quiet NaN.
- Otherwise, the maximum of a quiet NaN and another value is the other value.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.



**[1]** If instead `result` is in a different register from the inputs, the compiler can add a preceding [MOVPRFX (unpredicated)](https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--) instruction

## svmaxnm[_n_f32]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmaxnm%5B_n_f32%5D_z

### Signature (source notation)

```c
svfloat32_t svmaxnm[_n_f32]_z(svbool_t pg, svfloat32_t op1, float32_t op2);
```

### Description

Maximum number

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Maximum

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
  "return_base_type": "float",
  "element_bit_size": "32",
  "value": "svfloat32_t"
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

When op2 is 0.0 or 1.0, this intrinsic can use:

```asm
MOVPRFX Zresult.S, Pg/Z, Zop1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
FMAXNM Zresult.S, Pg/M, Zresult.S, #op2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMAXNM--immediate---Floating-point-maximum-number-with-immediate--predicated--

When result is in a different register from op2, this intrinsic can use:

```asm
MOVPRFX Zresult.S, Pg/Z, Zop1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
FMAXNM Zresult.S, Pg/M, Zresult.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMAXNM--vectors---Floating-point-maximum-number--predicated--

When result is in a different register from op1, this intrinsic can use:

```asm
MOVPRFX Zresult.S, Pg/Z, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
FMAXNM Zresult.S, Pg/M, Zresult.S, Zop1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMAXNM--vectors---Floating-point-maximum-number--predicated--

### Operation

Source operation ID: `SveOperation_svmaxnm_n_f16_z`

**Operation**



Return a vector in which each active element *i* contains the maximum of `op1[i]` and `op2`. Set the inactive elements of the result to zero.



This maximum operation works as follows:




- The maximum of a signaling NaN and anything else is a signaling NaN.
- The maximum of two quiet NaNs is a quiet NaN.
- Otherwise, the maximum of a quiet NaN and another value is the other value.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.

## svmaxnm[_n_f64]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmaxnm%5B_n_f64%5D_m

### Signature (source notation)

```c
svfloat64_t svmaxnm[_n_f64]_m(svbool_t pg, svfloat64_t op1, float64_t op2);
```

### Description

Maximum number

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Maximum

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
  "return_base_type": "float",
  "element_bit_size": "64",
  "value": "svfloat64_t"
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

When op2 is 0.0 or 1.0, this intrinsic can use:

```asm
FMAXNM Ztied1.D, Pg/M, Ztied1.D, #op2  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMAXNM--immediate---Floating-point-maximum-number-with-immediate--predicated--

The general implementation is:

```asm
FMAXNM Ztied1.D, Pg/M, Ztied1.D, Zop2.D  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMAXNM--vectors---Floating-point-maximum-number--predicated--

### Operation

Source operation ID: `SveOperation_svmaxnm_n_f16_m`

**Operation**



Return a vector in which each active element *i* contains the maximum of `op1[i]` and `op2`. Take the inactive elements of the result from the corresponding elements of `op1`.



This maximum operation works as follows:




- The maximum of a signaling NaN and anything else is a signaling NaN.
- The maximum of two quiet NaNs is a quiet NaN.
- Otherwise, the maximum of a quiet NaN and another value is the other value.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.



**[1]** If instead `result` is in a different register from the inputs, the compiler can add a preceding [MOVPRFX (unpredicated)](https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--) instruction

## svmaxnm[_n_f64]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmaxnm%5B_n_f64%5D_x

### Signature (source notation)

```c
svfloat64_t svmaxnm[_n_f64]_x(svbool_t pg, svfloat64_t op1, float64_t op2);
```

### Description

Maximum number

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Maximum

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
  "return_base_type": "float",
  "element_bit_size": "64",
  "value": "svfloat64_t"
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

When op2 is 0.0 or 1.0, this intrinsic can use:

```asm
FMAXNM Ztied1.D, Pg/M, Ztied1.D, #op2  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMAXNM--immediate---Floating-point-maximum-number-with-immediate--predicated--

When result and op1 are in the same register, the general implementation is:

```asm
FMAXNM Ztied1.D, Pg/M, Ztied1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMAXNM--vectors---Floating-point-maximum-number--predicated--

When result and op2 are in the same register, the general implementation is:

```asm
FMAXNM Ztied2.D, Pg/M, Ztied2.D, Zop1.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMAXNM--vectors---Floating-point-maximum-number--predicated--

When result is in a different register from the inputs, the general implementation is:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FMAXNM Zresult.D, Pg/M, Zresult.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMAXNM--vectors---Floating-point-maximum-number--predicated--

### Operation

Source operation ID: `SveOperation_svmaxnm_n_f16_x`

**Operation**



Return a vector in which each active element *i* contains the maximum of `op1[i]` and `op2`. The inactive elements of the result have arbitrary, undefined values.



This maximum operation works as follows:




- The maximum of a signaling NaN and anything else is a signaling NaN.
- The maximum of two quiet NaNs is a quiet NaN.
- Otherwise, the maximum of a quiet NaN and another value is the other value.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.



**[1]** If instead `result` is in a different register from the inputs, the compiler can add a preceding [MOVPRFX (unpredicated)](https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--) instruction

## svmaxnm[_n_f64]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmaxnm%5B_n_f64%5D_z

### Signature (source notation)

```c
svfloat64_t svmaxnm[_n_f64]_z(svbool_t pg, svfloat64_t op1, float64_t op2);
```

### Description

Maximum number

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Maximum

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
  "return_base_type": "float",
  "element_bit_size": "64",
  "value": "svfloat64_t"
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

When op2 is 0.0 or 1.0, this intrinsic can use:

```asm
MOVPRFX Zresult.D, Pg/Z, Zop1.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
FMAXNM Zresult.D, Pg/M, Zresult.D, #op2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMAXNM--immediate---Floating-point-maximum-number-with-immediate--predicated--

When result is in a different register from op2, this intrinsic can use:

```asm
MOVPRFX Zresult.D, Pg/Z, Zop1.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
FMAXNM Zresult.D, Pg/M, Zresult.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMAXNM--vectors---Floating-point-maximum-number--predicated--

When result is in a different register from op1, this intrinsic can use:

```asm
MOVPRFX Zresult.D, Pg/Z, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
FMAXNM Zresult.D, Pg/M, Zresult.D, Zop1.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMAXNM--vectors---Floating-point-maximum-number--predicated--

### Operation

Source operation ID: `SveOperation_svmaxnm_n_f16_z`

**Operation**



Return a vector in which each active element *i* contains the maximum of `op1[i]` and `op2`. Set the inactive elements of the result to zero.



This maximum operation works as follows:




- The maximum of a signaling NaN and anything else is a signaling NaN.
- The maximum of two quiet NaNs is a quiet NaN.
- Otherwise, the maximum of a quiet NaN and another value is the other value.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.

