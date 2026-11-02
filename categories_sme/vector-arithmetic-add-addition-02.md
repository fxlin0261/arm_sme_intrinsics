# SME / Vector arithmetic / Add / Addition — Part 2

## svadd[_s64]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svadd%5B_s64%5D_z

### Signature (source notation)

```c
svint64_t svadd[_s64]_z(svbool_t pg, svint64_t op1, svint64_t op2);
```

### Description

Add

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Addition

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
ADD Zresult.D, Pg/M, Zresult.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ADD--vectors--predicated---Add-vectors--predicated--

When result is in a different register from op1, this intrinsic can use:

```asm
MOVPRFX Zresult.D, Pg/Z, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
ADD Zresult.D, Pg/M, Zresult.D, Zop1.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ADD--vectors--predicated---Add-vectors--predicated--

### Operation

Source operation ID: `SveOperation_svadd_s8_z`

**Operation**



Return a vector in which each active element *i* contains `op1[i] + op2[i]`. Set the inactive elements of the result to zero.



The operation uses modulo arithmetic.  The behavior is therefore defined for all inputs; unlike C, there is no undefined behavior for signed overflow.

## svadd[_s8]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svadd%5B_s8%5D_m

### Signature (source notation)

```c
svint8_t svadd[_s8]_m(svbool_t pg, svint8_t op1, svint8_t op2);
```

### Description

Add

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Addition

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
ADD Ztied1.B, Pg/M, Ztied1.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ADD--vectors--predicated---Add-vectors--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
ADD Zresult.B, Pg/M, Zresult.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ADD--vectors--predicated---Add-vectors--predicated--

### Operation

Source operation ID: `SveOperation_svadd_s8_m`

**Operation**



Return a vector in which each active element *i* contains `op1[i] + op2[i]`. Take the inactive elements of the result from the corresponding elements of `op1`.



The operation uses modulo arithmetic.  The behavior is therefore defined for all inputs; unlike C, there is no undefined behavior for signed overflow.

## svadd[_s8]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svadd%5B_s8%5D_x

### Signature (source notation)

```c
svint8_t svadd[_s8]_x(svbool_t pg, svint8_t op1, svint8_t op2);
```

### Description

Add

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Addition

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
ADD Ztied1.B, Pg/M, Ztied1.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ADD--vectors--predicated---Add-vectors--predicated--

When result and op2 are in the same register, this intrinsic can use:

```asm
ADD Ztied2.B, Pg/M, Ztied2.B, Zop1.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ADD--vectors--predicated---Add-vectors--predicated--

This intrinsic compiles to:

```asm
ADD Zresult.B, Zop1.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ADD--vectors--unpredicated---Add--unpredicated--

### Operation

Source operation ID: `SveOperation_svadd_s8_x`

**Operation**



Return a vector in which each active element *i* contains `op1[i] + op2[i]`. The inactive elements of the result have arbitrary, undefined values.



The operation uses modulo arithmetic.  The behavior is therefore defined for all inputs; unlike C, there is no undefined behavior for signed overflow.

## svadd[_s8]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svadd%5B_s8%5D_z

### Signature (source notation)

```c
svint8_t svadd[_s8]_z(svbool_t pg, svint8_t op1, svint8_t op2);
```

### Description

Add

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Addition

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
ADD Zresult.B, Pg/M, Zresult.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ADD--vectors--predicated---Add-vectors--predicated--

When result is in a different register from op1, this intrinsic can use:

```asm
MOVPRFX Zresult.B, Pg/Z, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
ADD Zresult.B, Pg/M, Zresult.B, Zop1.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ADD--vectors--predicated---Add-vectors--predicated--

### Operation

Source operation ID: `SveOperation_svadd_s8_z`

**Operation**



Return a vector in which each active element *i* contains `op1[i] + op2[i]`. Set the inactive elements of the result to zero.



The operation uses modulo arithmetic.  The behavior is therefore defined for all inputs; unlike C, there is no undefined behavior for signed overflow.

## svadd[_u16]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svadd%5B_u16%5D_m

### Signature (source notation)

```c
svuint16_t svadd[_u16]_m(svbool_t pg, svuint16_t op1, svuint16_t op2);
```

### Description

Add

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Addition

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
ADD Ztied1.H, Pg/M, Ztied1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ADD--vectors--predicated---Add-vectors--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
ADD Zresult.H, Pg/M, Zresult.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ADD--vectors--predicated---Add-vectors--predicated--

### Operation

Source operation ID: `SveOperation_svadd_u8_m`

**Operation**



Return a vector in which each active element *i* contains `op1[i] + op2[i]`. Take the inactive elements of the result from the corresponding elements of `op1`.

## svadd[_u16]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svadd%5B_u16%5D_x

### Signature (source notation)

```c
svuint16_t svadd[_u16]_x(svbool_t pg, svuint16_t op1, svuint16_t op2);
```

### Description

Add

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Addition

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
ADD Ztied1.H, Pg/M, Ztied1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ADD--vectors--predicated---Add-vectors--predicated--

When result and op2 are in the same register, this intrinsic can use:

```asm
ADD Ztied2.H, Pg/M, Ztied2.H, Zop1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ADD--vectors--predicated---Add-vectors--predicated--

This intrinsic compiles to:

```asm
ADD Zresult.H, Zop1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ADD--vectors--unpredicated---Add--unpredicated--

### Operation

Source operation ID: `SveOperation_svadd_u8_x`

**Operation**



Return a vector in which each active element *i* contains `op1[i] + op2[i]`. The inactive elements of the result have arbitrary, undefined values.

## svadd[_u16]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svadd%5B_u16%5D_z

### Signature (source notation)

```c
svuint16_t svadd[_u16]_z(svbool_t pg, svuint16_t op1, svuint16_t op2);
```

### Description

Add

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Addition

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
ADD Zresult.H, Pg/M, Zresult.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ADD--vectors--predicated---Add-vectors--predicated--

When result is in a different register from op1, this intrinsic can use:

```asm
MOVPRFX Zresult.H, Pg/Z, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
ADD Zresult.H, Pg/M, Zresult.H, Zop1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ADD--vectors--predicated---Add-vectors--predicated--

### Operation

Source operation ID: `SveOperation_svadd_u8_z`

**Operation**



Return a vector in which each active element *i* contains `op1[i] + op2[i]`. Set the inactive elements of the result to zero.

## svadd[_u32]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svadd%5B_u32%5D_m

### Signature (source notation)

```c
svuint32_t svadd[_u32]_m(svbool_t pg, svuint32_t op1, svuint32_t op2);
```

### Description

Add

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Addition

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
ADD Ztied1.S, Pg/M, Ztied1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ADD--vectors--predicated---Add-vectors--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
ADD Zresult.S, Pg/M, Zresult.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ADD--vectors--predicated---Add-vectors--predicated--

### Operation

Source operation ID: `SveOperation_svadd_u8_m`

**Operation**



Return a vector in which each active element *i* contains `op1[i] + op2[i]`. Take the inactive elements of the result from the corresponding elements of `op1`.

## svadd[_u32]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svadd%5B_u32%5D_x

### Signature (source notation)

```c
svuint32_t svadd[_u32]_x(svbool_t pg, svuint32_t op1, svuint32_t op2);
```

### Description

Add

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Addition

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
ADD Ztied1.S, Pg/M, Ztied1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ADD--vectors--predicated---Add-vectors--predicated--

When result and op2 are in the same register, this intrinsic can use:

```asm
ADD Ztied2.S, Pg/M, Ztied2.S, Zop1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ADD--vectors--predicated---Add-vectors--predicated--

This intrinsic compiles to:

```asm
ADD Zresult.S, Zop1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ADD--vectors--unpredicated---Add--unpredicated--

### Operation

Source operation ID: `SveOperation_svadd_u8_x`

**Operation**



Return a vector in which each active element *i* contains `op1[i] + op2[i]`. The inactive elements of the result have arbitrary, undefined values.

## svadd[_u32]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svadd%5B_u32%5D_z

### Signature (source notation)

```c
svuint32_t svadd[_u32]_z(svbool_t pg, svuint32_t op1, svuint32_t op2);
```

### Description

Add

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Addition

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
ADD Zresult.S, Pg/M, Zresult.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ADD--vectors--predicated---Add-vectors--predicated--

When result is in a different register from op1, this intrinsic can use:

```asm
MOVPRFX Zresult.S, Pg/Z, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
ADD Zresult.S, Pg/M, Zresult.S, Zop1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ADD--vectors--predicated---Add-vectors--predicated--

### Operation

Source operation ID: `SveOperation_svadd_u8_z`

**Operation**



Return a vector in which each active element *i* contains `op1[i] + op2[i]`. Set the inactive elements of the result to zero.

## svadd[_u64]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svadd%5B_u64%5D_m

### Signature (source notation)

```c
svuint64_t svadd[_u64]_m(svbool_t pg, svuint64_t op1, svuint64_t op2);
```

### Description

Add

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Addition

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
ADD Ztied1.D, Pg/M, Ztied1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ADD--vectors--predicated---Add-vectors--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
ADD Zresult.D, Pg/M, Zresult.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ADD--vectors--predicated---Add-vectors--predicated--

### Operation

Source operation ID: `SveOperation_svadd_u8_m`

**Operation**



Return a vector in which each active element *i* contains `op1[i] + op2[i]`. Take the inactive elements of the result from the corresponding elements of `op1`.

## svadd[_u64]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svadd%5B_u64%5D_x

### Signature (source notation)

```c
svuint64_t svadd[_u64]_x(svbool_t pg, svuint64_t op1, svuint64_t op2);
```

### Description

Add

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Addition

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
ADD Ztied1.D, Pg/M, Ztied1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ADD--vectors--predicated---Add-vectors--predicated--

When result and op2 are in the same register, this intrinsic can use:

```asm
ADD Ztied2.D, Pg/M, Ztied2.D, Zop1.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ADD--vectors--predicated---Add-vectors--predicated--

This intrinsic compiles to:

```asm
ADD Zresult.D, Zop1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ADD--vectors--unpredicated---Add--unpredicated--

### Operation

Source operation ID: `SveOperation_svadd_u8_x`

**Operation**



Return a vector in which each active element *i* contains `op1[i] + op2[i]`. The inactive elements of the result have arbitrary, undefined values.

## svadd[_u64]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svadd%5B_u64%5D_z

### Signature (source notation)

```c
svuint64_t svadd[_u64]_z(svbool_t pg, svuint64_t op1, svuint64_t op2);
```

### Description

Add

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Addition

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
ADD Zresult.D, Pg/M, Zresult.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ADD--vectors--predicated---Add-vectors--predicated--

When result is in a different register from op1, this intrinsic can use:

```asm
MOVPRFX Zresult.D, Pg/Z, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
ADD Zresult.D, Pg/M, Zresult.D, Zop1.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ADD--vectors--predicated---Add-vectors--predicated--

### Operation

Source operation ID: `SveOperation_svadd_u8_z`

**Operation**



Return a vector in which each active element *i* contains `op1[i] + op2[i]`. Set the inactive elements of the result to zero.

## svadd[_u8]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svadd%5B_u8%5D_m

### Signature (source notation)

```c
svuint8_t svadd[_u8]_m(svbool_t pg, svuint8_t op1, svuint8_t op2);
```

### Description

Add

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Addition

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
ADD Ztied1.B, Pg/M, Ztied1.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ADD--vectors--predicated---Add-vectors--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
ADD Zresult.B, Pg/M, Zresult.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ADD--vectors--predicated---Add-vectors--predicated--

### Operation

Source operation ID: `SveOperation_svadd_u8_m`

**Operation**



Return a vector in which each active element *i* contains `op1[i] + op2[i]`. Take the inactive elements of the result from the corresponding elements of `op1`.

## svadd[_u8]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svadd%5B_u8%5D_x

### Signature (source notation)

```c
svuint8_t svadd[_u8]_x(svbool_t pg, svuint8_t op1, svuint8_t op2);
```

### Description

Add

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Addition

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
ADD Ztied1.B, Pg/M, Ztied1.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ADD--vectors--predicated---Add-vectors--predicated--

When result and op2 are in the same register, this intrinsic can use:

```asm
ADD Ztied2.B, Pg/M, Ztied2.B, Zop1.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ADD--vectors--predicated---Add-vectors--predicated--

This intrinsic compiles to:

```asm
ADD Zresult.B, Zop1.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ADD--vectors--unpredicated---Add--unpredicated--

### Operation

Source operation ID: `SveOperation_svadd_u8_x`

**Operation**



Return a vector in which each active element *i* contains `op1[i] + op2[i]`. The inactive elements of the result have arbitrary, undefined values.

## svadd[_u8]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svadd%5B_u8%5D_z

### Signature (source notation)

```c
svuint8_t svadd[_u8]_z(svbool_t pg, svuint8_t op1, svuint8_t op2);
```

### Description

Add

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Addition

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
ADD Zresult.B, Pg/M, Zresult.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ADD--vectors--predicated---Add-vectors--predicated--

When result is in a different register from op1, this intrinsic can use:

```asm
MOVPRFX Zresult.B, Pg/Z, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
ADD Zresult.B, Pg/M, Zresult.B, Zop1.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ADD--vectors--predicated---Add-vectors--predicated--

### Operation

Source operation ID: `SveOperation_svadd_u8_z`

**Operation**



Return a vector in which each active element *i* contains `op1[i] + op2[i]`. Set the inactive elements of the result to zero.

## svhadd[_n_s16]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svhadd%5B_n_s16%5D_m

### Signature (source notation)

```c
svint16_t svhadd[_n_s16]_m(svbool_t pg, svint16_t op1, int16_t op2);
```

### Description

Halving add

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Addition

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
SHADD Ztied1.H, Pg/M, Ztied1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SHADD--Signed-halving-addition-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SHADD Zresult.H, Pg/M, Zresult.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SHADD--Signed-halving-addition-

### Operation

Source operation ID: `SveOperation_svhadd_n_s8_m`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Add `op2` to `op1[i]` without loss of precision.
- Divide the result by 2, rounding towards -∞.



Take the inactive elements of the result from the corresponding elements of `op1`.

## svhadd[_n_s16]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svhadd%5B_n_s16%5D_x

### Signature (source notation)

```c
svint16_t svhadd[_n_s16]_x(svbool_t pg, svint16_t op1, int16_t op2);
```

### Description

Halving add

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Addition

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

When result and op1 are in the same register, this intrinsic compiles to:

```asm
SHADD Ztied1.H, Pg/M, Ztied1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SHADD--Signed-halving-addition-

When result and op2 are in the same register, this intrinsic compiles to:

```asm
SHADD Ztied2.H, Pg/M, Ztied2.H, Zop1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SHADD--Signed-halving-addition-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SHADD Zresult.H, Pg/M, Zresult.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SHADD--Signed-halving-addition-

### Operation

Source operation ID: `SveOperation_svhadd_n_s8_x`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Add `op2` to `op1[i]` without loss of precision.
- Divide the result by 2, rounding towards -∞.



The inactive elements of the result have arbitrary, undefined values.

## svhadd[_n_s16]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svhadd%5B_n_s16%5D_z

### Signature (source notation)

```c
svint16_t svhadd[_n_s16]_z(svbool_t pg, svint16_t op1, int16_t op2);
```

### Description

Halving add

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Addition

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
SHADD Zresult.H, Pg/M, Zresult.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SHADD--Signed-halving-addition-

When result is in a different register from op1, this intrinsic can use:

```asm
MOVPRFX Zresult.H, Pg/Z, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
SHADD Zresult.H, Pg/M, Zresult.H, Zop1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SHADD--Signed-halving-addition-

### Operation

Source operation ID: `SveOperation_svhadd_n_s8_z`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Add `op2` to `op1[i]` without loss of precision.
- Divide the result by 2, rounding towards -∞.



Set the inactive elements of the result to zero.

## svhadd[_n_s32]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svhadd%5B_n_s32%5D_m

### Signature (source notation)

```c
svint32_t svhadd[_n_s32]_m(svbool_t pg, svint32_t op1, int32_t op2);
```

### Description

Halving add

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Addition

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
SHADD Ztied1.S, Pg/M, Ztied1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SHADD--Signed-halving-addition-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SHADD Zresult.S, Pg/M, Zresult.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SHADD--Signed-halving-addition-

### Operation

Source operation ID: `SveOperation_svhadd_n_s8_m`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Add `op2` to `op1[i]` without loss of precision.
- Divide the result by 2, rounding towards -∞.



Take the inactive elements of the result from the corresponding elements of `op1`.

## svhadd[_n_s32]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svhadd%5B_n_s32%5D_x

### Signature (source notation)

```c
svint32_t svhadd[_n_s32]_x(svbool_t pg, svint32_t op1, int32_t op2);
```

### Description

Halving add

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Addition

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

When result and op1 are in the same register, this intrinsic compiles to:

```asm
SHADD Ztied1.S, Pg/M, Ztied1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SHADD--Signed-halving-addition-

When result and op2 are in the same register, this intrinsic compiles to:

```asm
SHADD Ztied2.S, Pg/M, Ztied2.S, Zop1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SHADD--Signed-halving-addition-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SHADD Zresult.S, Pg/M, Zresult.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SHADD--Signed-halving-addition-

### Operation

Source operation ID: `SveOperation_svhadd_n_s8_x`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Add `op2` to `op1[i]` without loss of precision.
- Divide the result by 2, rounding towards -∞.



The inactive elements of the result have arbitrary, undefined values.

## svhadd[_n_s32]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svhadd%5B_n_s32%5D_z

### Signature (source notation)

```c
svint32_t svhadd[_n_s32]_z(svbool_t pg, svint32_t op1, int32_t op2);
```

### Description

Halving add

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Addition

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
SHADD Zresult.S, Pg/M, Zresult.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SHADD--Signed-halving-addition-

When result is in a different register from op1, this intrinsic can use:

```asm
MOVPRFX Zresult.S, Pg/Z, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
SHADD Zresult.S, Pg/M, Zresult.S, Zop1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SHADD--Signed-halving-addition-

### Operation

Source operation ID: `SveOperation_svhadd_n_s8_z`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Add `op2` to `op1[i]` without loss of precision.
- Divide the result by 2, rounding towards -∞.



Set the inactive elements of the result to zero.

## svhadd[_n_s64]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svhadd%5B_n_s64%5D_m

### Signature (source notation)

```c
svint64_t svhadd[_n_s64]_m(svbool_t pg, svint64_t op1, int64_t op2);
```

### Description

Halving add

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Addition

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
SHADD Ztied1.D, Pg/M, Ztied1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SHADD--Signed-halving-addition-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SHADD Zresult.D, Pg/M, Zresult.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SHADD--Signed-halving-addition-

### Operation

Source operation ID: `SveOperation_svhadd_n_s8_m`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Add `op2` to `op1[i]` without loss of precision.
- Divide the result by 2, rounding towards -∞.



Take the inactive elements of the result from the corresponding elements of `op1`.

## svhadd[_n_s64]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svhadd%5B_n_s64%5D_x

### Signature (source notation)

```c
svint64_t svhadd[_n_s64]_x(svbool_t pg, svint64_t op1, int64_t op2);
```

### Description

Halving add

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Addition

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

When result and op1 are in the same register, this intrinsic compiles to:

```asm
SHADD Ztied1.D, Pg/M, Ztied1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SHADD--Signed-halving-addition-

When result and op2 are in the same register, this intrinsic compiles to:

```asm
SHADD Ztied2.D, Pg/M, Ztied2.D, Zop1.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SHADD--Signed-halving-addition-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SHADD Zresult.D, Pg/M, Zresult.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SHADD--Signed-halving-addition-

### Operation

Source operation ID: `SveOperation_svhadd_n_s8_x`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Add `op2` to `op1[i]` without loss of precision.
- Divide the result by 2, rounding towards -∞.



The inactive elements of the result have arbitrary, undefined values.

## svhadd[_n_s64]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svhadd%5B_n_s64%5D_z

### Signature (source notation)

```c
svint64_t svhadd[_n_s64]_z(svbool_t pg, svint64_t op1, int64_t op2);
```

### Description

Halving add

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Addition

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
SHADD Zresult.D, Pg/M, Zresult.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SHADD--Signed-halving-addition-

When result is in a different register from op1, this intrinsic can use:

```asm
MOVPRFX Zresult.D, Pg/Z, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
SHADD Zresult.D, Pg/M, Zresult.D, Zop1.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SHADD--Signed-halving-addition-

### Operation

Source operation ID: `SveOperation_svhadd_n_s8_z`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Add `op2` to `op1[i]` without loss of precision.
- Divide the result by 2, rounding towards -∞.



Set the inactive elements of the result to zero.

## svhadd[_n_s8]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svhadd%5B_n_s8%5D_m

### Signature (source notation)

```c
svint8_t svhadd[_n_s8]_m(svbool_t pg, svint8_t op1, int8_t op2);
```

### Description

Halving add

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Addition

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
SHADD Ztied1.B, Pg/M, Ztied1.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SHADD--Signed-halving-addition-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SHADD Zresult.B, Pg/M, Zresult.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SHADD--Signed-halving-addition-

### Operation

Source operation ID: `SveOperation_svhadd_n_s8_m`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Add `op2` to `op1[i]` without loss of precision.
- Divide the result by 2, rounding towards -∞.



Take the inactive elements of the result from the corresponding elements of `op1`.

## svhadd[_n_s8]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svhadd%5B_n_s8%5D_x

### Signature (source notation)

```c
svint8_t svhadd[_n_s8]_x(svbool_t pg, svint8_t op1, int8_t op2);
```

### Description

Halving add

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Addition

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

When result and op1 are in the same register, this intrinsic compiles to:

```asm
SHADD Ztied1.B, Pg/M, Ztied1.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SHADD--Signed-halving-addition-

When result and op2 are in the same register, this intrinsic compiles to:

```asm
SHADD Ztied2.B, Pg/M, Ztied2.B, Zop1.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SHADD--Signed-halving-addition-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SHADD Zresult.B, Pg/M, Zresult.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SHADD--Signed-halving-addition-

### Operation

Source operation ID: `SveOperation_svhadd_n_s8_x`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Add `op2` to `op1[i]` without loss of precision.
- Divide the result by 2, rounding towards -∞.



The inactive elements of the result have arbitrary, undefined values.

## svhadd[_n_s8]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svhadd%5B_n_s8%5D_z

### Signature (source notation)

```c
svint8_t svhadd[_n_s8]_z(svbool_t pg, svint8_t op1, int8_t op2);
```

### Description

Halving add

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Addition

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
SHADD Zresult.B, Pg/M, Zresult.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SHADD--Signed-halving-addition-

When result is in a different register from op1, this intrinsic can use:

```asm
MOVPRFX Zresult.B, Pg/Z, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
SHADD Zresult.B, Pg/M, Zresult.B, Zop1.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SHADD--Signed-halving-addition-

### Operation

Source operation ID: `SveOperation_svhadd_n_s8_z`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Add `op2` to `op1[i]` without loss of precision.
- Divide the result by 2, rounding towards -∞.



Set the inactive elements of the result to zero.

## svhadd[_n_u16]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svhadd%5B_n_u16%5D_m

### Signature (source notation)

```c
svuint16_t svhadd[_n_u16]_m(svbool_t pg, svuint16_t op1, uint16_t op2);
```

### Description

Halving add

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Addition

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
UHADD Ztied1.H, Pg/M, Ztied1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UHADD--Unsigned-halving-addition-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
UHADD Zresult.H, Pg/M, Zresult.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UHADD--Unsigned-halving-addition-

### Operation

Source operation ID: `SveOperation_svhadd_n_s8_m`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Add `op2` to `op1[i]` without loss of precision.
- Divide the result by 2, rounding towards -∞.



Take the inactive elements of the result from the corresponding elements of `op1`.

## svhadd[_n_u16]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svhadd%5B_n_u16%5D_x

### Signature (source notation)

```c
svuint16_t svhadd[_n_u16]_x(svbool_t pg, svuint16_t op1, uint16_t op2);
```

### Description

Halving add

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Addition

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

When result and op1 are in the same register, this intrinsic compiles to:

```asm
UHADD Ztied1.H, Pg/M, Ztied1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UHADD--Unsigned-halving-addition-

When result and op2 are in the same register, this intrinsic compiles to:

```asm
UHADD Ztied2.H, Pg/M, Ztied2.H, Zop1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UHADD--Unsigned-halving-addition-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
UHADD Zresult.H, Pg/M, Zresult.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UHADD--Unsigned-halving-addition-

### Operation

Source operation ID: `SveOperation_svhadd_n_s8_x`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Add `op2` to `op1[i]` without loss of precision.
- Divide the result by 2, rounding towards -∞.



The inactive elements of the result have arbitrary, undefined values.

## svhadd[_n_u16]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svhadd%5B_n_u16%5D_z

### Signature (source notation)

```c
svuint16_t svhadd[_n_u16]_z(svbool_t pg, svuint16_t op1, uint16_t op2);
```

### Description

Halving add

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Addition

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
UHADD Zresult.H, Pg/M, Zresult.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UHADD--Unsigned-halving-addition-

When result is in a different register from op1, this intrinsic can use:

```asm
MOVPRFX Zresult.H, Pg/Z, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
UHADD Zresult.H, Pg/M, Zresult.H, Zop1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UHADD--Unsigned-halving-addition-

### Operation

Source operation ID: `SveOperation_svhadd_n_s8_z`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Add `op2` to `op1[i]` without loss of precision.
- Divide the result by 2, rounding towards -∞.



Set the inactive elements of the result to zero.

## svhadd[_n_u32]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svhadd%5B_n_u32%5D_m

### Signature (source notation)

```c
svuint32_t svhadd[_n_u32]_m(svbool_t pg, svuint32_t op1, uint32_t op2);
```

### Description

Halving add

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Addition

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
UHADD Ztied1.S, Pg/M, Ztied1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UHADD--Unsigned-halving-addition-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
UHADD Zresult.S, Pg/M, Zresult.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UHADD--Unsigned-halving-addition-

### Operation

Source operation ID: `SveOperation_svhadd_n_s8_m`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Add `op2` to `op1[i]` without loss of precision.
- Divide the result by 2, rounding towards -∞.



Take the inactive elements of the result from the corresponding elements of `op1`.

## svhadd[_n_u32]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svhadd%5B_n_u32%5D_x

### Signature (source notation)

```c
svuint32_t svhadd[_n_u32]_x(svbool_t pg, svuint32_t op1, uint32_t op2);
```

### Description

Halving add

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Addition

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

When result and op1 are in the same register, this intrinsic compiles to:

```asm
UHADD Ztied1.S, Pg/M, Ztied1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UHADD--Unsigned-halving-addition-

When result and op2 are in the same register, this intrinsic compiles to:

```asm
UHADD Ztied2.S, Pg/M, Ztied2.S, Zop1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UHADD--Unsigned-halving-addition-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
UHADD Zresult.S, Pg/M, Zresult.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UHADD--Unsigned-halving-addition-

### Operation

Source operation ID: `SveOperation_svhadd_n_s8_x`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Add `op2` to `op1[i]` without loss of precision.
- Divide the result by 2, rounding towards -∞.



The inactive elements of the result have arbitrary, undefined values.

## svhadd[_n_u32]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svhadd%5B_n_u32%5D_z

### Signature (source notation)

```c
svuint32_t svhadd[_n_u32]_z(svbool_t pg, svuint32_t op1, uint32_t op2);
```

### Description

Halving add

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Addition

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
UHADD Zresult.S, Pg/M, Zresult.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UHADD--Unsigned-halving-addition-

When result is in a different register from op1, this intrinsic can use:

```asm
MOVPRFX Zresult.S, Pg/Z, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
UHADD Zresult.S, Pg/M, Zresult.S, Zop1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UHADD--Unsigned-halving-addition-

### Operation

Source operation ID: `SveOperation_svhadd_n_s8_z`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Add `op2` to `op1[i]` without loss of precision.
- Divide the result by 2, rounding towards -∞.



Set the inactive elements of the result to zero.

## svhadd[_n_u64]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svhadd%5B_n_u64%5D_m

### Signature (source notation)

```c
svuint64_t svhadd[_n_u64]_m(svbool_t pg, svuint64_t op1, uint64_t op2);
```

### Description

Halving add

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Addition

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
UHADD Ztied1.D, Pg/M, Ztied1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UHADD--Unsigned-halving-addition-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
UHADD Zresult.D, Pg/M, Zresult.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UHADD--Unsigned-halving-addition-

### Operation

Source operation ID: `SveOperation_svhadd_n_s8_m`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Add `op2` to `op1[i]` without loss of precision.
- Divide the result by 2, rounding towards -∞.



Take the inactive elements of the result from the corresponding elements of `op1`.

## svhadd[_n_u64]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svhadd%5B_n_u64%5D_x

### Signature (source notation)

```c
svuint64_t svhadd[_n_u64]_x(svbool_t pg, svuint64_t op1, uint64_t op2);
```

### Description

Halving add

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Addition

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

When result and op1 are in the same register, this intrinsic compiles to:

```asm
UHADD Ztied1.D, Pg/M, Ztied1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UHADD--Unsigned-halving-addition-

When result and op2 are in the same register, this intrinsic compiles to:

```asm
UHADD Ztied2.D, Pg/M, Ztied2.D, Zop1.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UHADD--Unsigned-halving-addition-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
UHADD Zresult.D, Pg/M, Zresult.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UHADD--Unsigned-halving-addition-

### Operation

Source operation ID: `SveOperation_svhadd_n_s8_x`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Add `op2` to `op1[i]` without loss of precision.
- Divide the result by 2, rounding towards -∞.



The inactive elements of the result have arbitrary, undefined values.

## svhadd[_n_u64]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svhadd%5B_n_u64%5D_z

### Signature (source notation)

```c
svuint64_t svhadd[_n_u64]_z(svbool_t pg, svuint64_t op1, uint64_t op2);
```

### Description

Halving add

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Addition

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
UHADD Zresult.D, Pg/M, Zresult.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UHADD--Unsigned-halving-addition-

When result is in a different register from op1, this intrinsic can use:

```asm
MOVPRFX Zresult.D, Pg/Z, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
UHADD Zresult.D, Pg/M, Zresult.D, Zop1.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UHADD--Unsigned-halving-addition-

### Operation

Source operation ID: `SveOperation_svhadd_n_s8_z`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Add `op2` to `op1[i]` without loss of precision.
- Divide the result by 2, rounding towards -∞.



Set the inactive elements of the result to zero.

## svhadd[_n_u8]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svhadd%5B_n_u8%5D_m

### Signature (source notation)

```c
svuint8_t svhadd[_n_u8]_m(svbool_t pg, svuint8_t op1, uint8_t op2);
```

### Description

Halving add

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Addition

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
UHADD Ztied1.B, Pg/M, Ztied1.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UHADD--Unsigned-halving-addition-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
UHADD Zresult.B, Pg/M, Zresult.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UHADD--Unsigned-halving-addition-

### Operation

Source operation ID: `SveOperation_svhadd_n_s8_m`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Add `op2` to `op1[i]` without loss of precision.
- Divide the result by 2, rounding towards -∞.



Take the inactive elements of the result from the corresponding elements of `op1`.

## svhadd[_n_u8]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svhadd%5B_n_u8%5D_x

### Signature (source notation)

```c
svuint8_t svhadd[_n_u8]_x(svbool_t pg, svuint8_t op1, uint8_t op2);
```

### Description

Halving add

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Addition

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

When result and op1 are in the same register, this intrinsic compiles to:

```asm
UHADD Ztied1.B, Pg/M, Ztied1.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UHADD--Unsigned-halving-addition-

When result and op2 are in the same register, this intrinsic compiles to:

```asm
UHADD Ztied2.B, Pg/M, Ztied2.B, Zop1.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UHADD--Unsigned-halving-addition-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
UHADD Zresult.B, Pg/M, Zresult.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UHADD--Unsigned-halving-addition-

### Operation

Source operation ID: `SveOperation_svhadd_n_s8_x`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Add `op2` to `op1[i]` without loss of precision.
- Divide the result by 2, rounding towards -∞.



The inactive elements of the result have arbitrary, undefined values.

## svhadd[_n_u8]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svhadd%5B_n_u8%5D_z

### Signature (source notation)

```c
svuint8_t svhadd[_n_u8]_z(svbool_t pg, svuint8_t op1, uint8_t op2);
```

### Description

Halving add

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Addition

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
UHADD Zresult.B, Pg/M, Zresult.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UHADD--Unsigned-halving-addition-

When result is in a different register from op1, this intrinsic can use:

```asm
MOVPRFX Zresult.B, Pg/Z, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
UHADD Zresult.B, Pg/M, Zresult.B, Zop1.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UHADD--Unsigned-halving-addition-

### Operation

Source operation ID: `SveOperation_svhadd_n_s8_z`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Add `op2` to `op1[i]` without loss of precision.
- Divide the result by 2, rounding towards -∞.



Set the inactive elements of the result to zero.

## svhadd[_s16]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svhadd%5B_s16%5D_m

### Signature (source notation)

```c
svint16_t svhadd[_s16]_m(svbool_t pg, svint16_t op1, svint16_t op2);
```

### Description

Halving add

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Addition

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
SHADD Ztied1.H, Pg/M, Ztied1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SHADD--Signed-halving-addition-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SHADD Zresult.H, Pg/M, Zresult.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SHADD--Signed-halving-addition-

### Operation

Source operation ID: `SveOperation_svhadd_s8_m`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Add `op2[i]` to `op1[i]` without loss of precision.
- Divide the result by 2, rounding towards -∞.



Take the inactive elements of the result from the corresponding elements of `op1`.

## svhadd[_s16]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svhadd%5B_s16%5D_x

### Signature (source notation)

```c
svint16_t svhadd[_s16]_x(svbool_t pg, svint16_t op1, svint16_t op2);
```

### Description

Halving add

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Addition

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
SHADD Ztied1.H, Pg/M, Ztied1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SHADD--Signed-halving-addition-

When result and op2 are in the same register, this intrinsic compiles to:

```asm
SHADD Ztied2.H, Pg/M, Ztied2.H, Zop1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SHADD--Signed-halving-addition-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SHADD Zresult.H, Pg/M, Zresult.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SHADD--Signed-halving-addition-

### Operation

Source operation ID: `SveOperation_svhadd_s8_x`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Add `op2[i]` to `op1[i]` without loss of precision.
- Divide the result by 2, rounding towards -∞.



The inactive elements of the result have arbitrary, undefined values.

## svhadd[_s16]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svhadd%5B_s16%5D_z

### Signature (source notation)

```c
svint16_t svhadd[_s16]_z(svbool_t pg, svint16_t op1, svint16_t op2);
```

### Description

Halving add

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Addition

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
SHADD Zresult.H, Pg/M, Zresult.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SHADD--Signed-halving-addition-

When result is in a different register from op1, this intrinsic can use:

```asm
MOVPRFX Zresult.H, Pg/Z, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
SHADD Zresult.H, Pg/M, Zresult.H, Zop1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SHADD--Signed-halving-addition-

### Operation

Source operation ID: `SveOperation_svhadd_s8_z`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Add `op2[i]` to `op1[i]` without loss of precision.
- Divide the result by 2, rounding towards -∞.



Set the inactive elements of the result to zero.

## svhadd[_s32]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svhadd%5B_s32%5D_m

### Signature (source notation)

```c
svint32_t svhadd[_s32]_m(svbool_t pg, svint32_t op1, svint32_t op2);
```

### Description

Halving add

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Addition

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
SHADD Ztied1.S, Pg/M, Ztied1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SHADD--Signed-halving-addition-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SHADD Zresult.S, Pg/M, Zresult.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SHADD--Signed-halving-addition-

### Operation

Source operation ID: `SveOperation_svhadd_s8_m`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Add `op2[i]` to `op1[i]` without loss of precision.
- Divide the result by 2, rounding towards -∞.



Take the inactive elements of the result from the corresponding elements of `op1`.

## svhadd[_s32]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svhadd%5B_s32%5D_x

### Signature (source notation)

```c
svint32_t svhadd[_s32]_x(svbool_t pg, svint32_t op1, svint32_t op2);
```

### Description

Halving add

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Addition

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
SHADD Ztied1.S, Pg/M, Ztied1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SHADD--Signed-halving-addition-

When result and op2 are in the same register, this intrinsic compiles to:

```asm
SHADD Ztied2.S, Pg/M, Ztied2.S, Zop1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SHADD--Signed-halving-addition-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SHADD Zresult.S, Pg/M, Zresult.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SHADD--Signed-halving-addition-

### Operation

Source operation ID: `SveOperation_svhadd_s8_x`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Add `op2[i]` to `op1[i]` without loss of precision.
- Divide the result by 2, rounding towards -∞.



The inactive elements of the result have arbitrary, undefined values.

## svhadd[_s32]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svhadd%5B_s32%5D_z

### Signature (source notation)

```c
svint32_t svhadd[_s32]_z(svbool_t pg, svint32_t op1, svint32_t op2);
```

### Description

Halving add

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Addition

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
SHADD Zresult.S, Pg/M, Zresult.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SHADD--Signed-halving-addition-

When result is in a different register from op1, this intrinsic can use:

```asm
MOVPRFX Zresult.S, Pg/Z, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
SHADD Zresult.S, Pg/M, Zresult.S, Zop1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SHADD--Signed-halving-addition-

### Operation

Source operation ID: `SveOperation_svhadd_s8_z`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Add `op2[i]` to `op1[i]` without loss of precision.
- Divide the result by 2, rounding towards -∞.



Set the inactive elements of the result to zero.

## svhadd[_s64]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svhadd%5B_s64%5D_m

### Signature (source notation)

```c
svint64_t svhadd[_s64]_m(svbool_t pg, svint64_t op1, svint64_t op2);
```

### Description

Halving add

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Addition

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
SHADD Ztied1.D, Pg/M, Ztied1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SHADD--Signed-halving-addition-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SHADD Zresult.D, Pg/M, Zresult.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SHADD--Signed-halving-addition-

### Operation

Source operation ID: `SveOperation_svhadd_s8_m`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Add `op2[i]` to `op1[i]` without loss of precision.
- Divide the result by 2, rounding towards -∞.



Take the inactive elements of the result from the corresponding elements of `op1`.

## svhadd[_s64]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svhadd%5B_s64%5D_x

### Signature (source notation)

```c
svint64_t svhadd[_s64]_x(svbool_t pg, svint64_t op1, svint64_t op2);
```

### Description

Halving add

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Addition

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
SHADD Ztied1.D, Pg/M, Ztied1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SHADD--Signed-halving-addition-

When result and op2 are in the same register, this intrinsic compiles to:

```asm
SHADD Ztied2.D, Pg/M, Ztied2.D, Zop1.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SHADD--Signed-halving-addition-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SHADD Zresult.D, Pg/M, Zresult.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SHADD--Signed-halving-addition-

### Operation

Source operation ID: `SveOperation_svhadd_s8_x`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Add `op2[i]` to `op1[i]` without loss of precision.
- Divide the result by 2, rounding towards -∞.



The inactive elements of the result have arbitrary, undefined values.

## svhadd[_s64]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svhadd%5B_s64%5D_z

### Signature (source notation)

```c
svint64_t svhadd[_s64]_z(svbool_t pg, svint64_t op1, svint64_t op2);
```

### Description

Halving add

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Addition

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
SHADD Zresult.D, Pg/M, Zresult.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SHADD--Signed-halving-addition-

When result is in a different register from op1, this intrinsic can use:

```asm
MOVPRFX Zresult.D, Pg/Z, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
SHADD Zresult.D, Pg/M, Zresult.D, Zop1.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SHADD--Signed-halving-addition-

### Operation

Source operation ID: `SveOperation_svhadd_s8_z`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Add `op2[i]` to `op1[i]` without loss of precision.
- Divide the result by 2, rounding towards -∞.



Set the inactive elements of the result to zero.

## svhadd[_s8]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svhadd%5B_s8%5D_m

### Signature (source notation)

```c
svint8_t svhadd[_s8]_m(svbool_t pg, svint8_t op1, svint8_t op2);
```

### Description

Halving add

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Addition

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
SHADD Ztied1.B, Pg/M, Ztied1.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SHADD--Signed-halving-addition-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SHADD Zresult.B, Pg/M, Zresult.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SHADD--Signed-halving-addition-

### Operation

Source operation ID: `SveOperation_svhadd_s8_m`

**Operation**



Return a vector in which each active element *i* contains the result of the following procedure:




- Add `op2[i]` to `op1[i]` without loss of precision.
- Divide the result by 2, rounding towards -∞.



Take the inactive elements of the result from the corresponding elements of `op1`.

