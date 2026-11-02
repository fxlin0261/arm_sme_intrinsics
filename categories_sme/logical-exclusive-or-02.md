# SME / Logical / Exclusive OR — Part 2

## sveor[_s8]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/sveor%5B_s8%5D_m

### Signature (source notation)

```c
svint8_t sveor[_s8]_m(svbool_t pg, svint8_t op1, svint8_t op2);
```

### Description

Bitwise exclusive OR

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / Exclusive OR

- SME attributes: Not specified by source.

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
EOR Ztied1.B, Pg/M, Ztied1.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/EOR--vectors--predicated---Bitwise-exclusive-OR--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
EOR Zresult.B, Pg/M, Zresult.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/EOR--vectors--predicated---Bitwise-exclusive-OR--predicated--

### Operation

Source operation ID: `SveOperation_sveor_s8_m`

**Operation**



Return a vector in which each active element *i* contains `op1[i] ^ op2[i]`. Take the inactive elements of the result from the corresponding elements of `op1`.

## sveor[_s8]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/sveor%5B_s8%5D_x

### Signature (source notation)

```c
svint8_t sveor[_s8]_x(svbool_t pg, svint8_t op1, svint8_t op2);
```

### Description

Bitwise exclusive OR

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / Exclusive OR

- SME attributes: Not specified by source.

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
EOR Ztied1.B, Pg/M, Ztied1.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/EOR--vectors--predicated---Bitwise-exclusive-OR--predicated--

When result and op2 are in the same register, this intrinsic can use:

```asm
EOR Ztied2.B, Pg/M, Ztied2.B, Zop1.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/EOR--vectors--predicated---Bitwise-exclusive-OR--predicated--

This intrinsic compiles to:

```asm
EOR Zresult.D, Zop1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/EOR--vectors--unpredicated---Bitwise-exclusive-OR--unpredicated--

### Operation

Source operation ID: `SveOperation_sveor_s8_x`

**Operation**



Return a vector in which each active element *i* contains `op1[i] ^ op2[i]`. The inactive elements of the result have arbitrary, undefined values.

## sveor[_s8]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/sveor%5B_s8%5D_z

### Signature (source notation)

```c
svint8_t sveor[_s8]_z(svbool_t pg, svint8_t op1, svint8_t op2);
```

### Description

Bitwise exclusive OR

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / Exclusive OR

- SME attributes: Not specified by source.

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
EOR Zresult.B, Pg/M, Zresult.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/EOR--vectors--predicated---Bitwise-exclusive-OR--predicated--

When result is in a different register from op1, this intrinsic can use:

```asm
MOVPRFX Zresult.B, Pg/Z, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
EOR Zresult.B, Pg/M, Zresult.B, Zop1.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/EOR--vectors--predicated---Bitwise-exclusive-OR--predicated--

### Operation

Source operation ID: `SveOperation_sveor_s8_z`

**Operation**



Return a vector in which each active element *i* contains `op1[i] ^ op2[i]`. Set the inactive elements of the result to zero.

## sveor[_u16]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/sveor%5B_u16%5D_m

### Signature (source notation)

```c
svuint16_t sveor[_u16]_m(svbool_t pg, svuint16_t op1, svuint16_t op2);
```

### Description

Bitwise exclusive OR

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / Exclusive OR

- SME attributes: Not specified by source.

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
EOR Ztied1.H, Pg/M, Ztied1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/EOR--vectors--predicated---Bitwise-exclusive-OR--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
EOR Zresult.H, Pg/M, Zresult.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/EOR--vectors--predicated---Bitwise-exclusive-OR--predicated--

### Operation

Source operation ID: `SveOperation_sveor_s8_m`

**Operation**



Return a vector in which each active element *i* contains `op1[i] ^ op2[i]`. Take the inactive elements of the result from the corresponding elements of `op1`.

## sveor[_u16]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/sveor%5B_u16%5D_x

### Signature (source notation)

```c
svuint16_t sveor[_u16]_x(svbool_t pg, svuint16_t op1, svuint16_t op2);
```

### Description

Bitwise exclusive OR

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / Exclusive OR

- SME attributes: Not specified by source.

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
EOR Ztied1.H, Pg/M, Ztied1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/EOR--vectors--predicated---Bitwise-exclusive-OR--predicated--

When result and op2 are in the same register, this intrinsic can use:

```asm
EOR Ztied2.H, Pg/M, Ztied2.H, Zop1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/EOR--vectors--predicated---Bitwise-exclusive-OR--predicated--

This intrinsic compiles to:

```asm
EOR Zresult.D, Zop1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/EOR--vectors--unpredicated---Bitwise-exclusive-OR--unpredicated--

### Operation

Source operation ID: `SveOperation_sveor_s8_x`

**Operation**



Return a vector in which each active element *i* contains `op1[i] ^ op2[i]`. The inactive elements of the result have arbitrary, undefined values.

## sveor[_u16]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/sveor%5B_u16%5D_z

### Signature (source notation)

```c
svuint16_t sveor[_u16]_z(svbool_t pg, svuint16_t op1, svuint16_t op2);
```

### Description

Bitwise exclusive OR

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / Exclusive OR

- SME attributes: Not specified by source.

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
EOR Zresult.H, Pg/M, Zresult.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/EOR--vectors--predicated---Bitwise-exclusive-OR--predicated--

When result is in a different register from op1, this intrinsic can use:

```asm
MOVPRFX Zresult.H, Pg/Z, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
EOR Zresult.H, Pg/M, Zresult.H, Zop1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/EOR--vectors--predicated---Bitwise-exclusive-OR--predicated--

### Operation

Source operation ID: `SveOperation_sveor_s8_z`

**Operation**



Return a vector in which each active element *i* contains `op1[i] ^ op2[i]`. Set the inactive elements of the result to zero.

## sveor[_u32]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/sveor%5B_u32%5D_m

### Signature (source notation)

```c
svuint32_t sveor[_u32]_m(svbool_t pg, svuint32_t op1, svuint32_t op2);
```

### Description

Bitwise exclusive OR

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / Exclusive OR

- SME attributes: Not specified by source.

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
EOR Ztied1.S, Pg/M, Ztied1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/EOR--vectors--predicated---Bitwise-exclusive-OR--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
EOR Zresult.S, Pg/M, Zresult.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/EOR--vectors--predicated---Bitwise-exclusive-OR--predicated--

### Operation

Source operation ID: `SveOperation_sveor_s8_m`

**Operation**



Return a vector in which each active element *i* contains `op1[i] ^ op2[i]`. Take the inactive elements of the result from the corresponding elements of `op1`.

## sveor[_u32]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/sveor%5B_u32%5D_x

### Signature (source notation)

```c
svuint32_t sveor[_u32]_x(svbool_t pg, svuint32_t op1, svuint32_t op2);
```

### Description

Bitwise exclusive OR

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / Exclusive OR

- SME attributes: Not specified by source.

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
EOR Ztied1.S, Pg/M, Ztied1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/EOR--vectors--predicated---Bitwise-exclusive-OR--predicated--

When result and op2 are in the same register, this intrinsic can use:

```asm
EOR Ztied2.S, Pg/M, Ztied2.S, Zop1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/EOR--vectors--predicated---Bitwise-exclusive-OR--predicated--

This intrinsic compiles to:

```asm
EOR Zresult.D, Zop1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/EOR--vectors--unpredicated---Bitwise-exclusive-OR--unpredicated--

### Operation

Source operation ID: `SveOperation_sveor_s8_x`

**Operation**



Return a vector in which each active element *i* contains `op1[i] ^ op2[i]`. The inactive elements of the result have arbitrary, undefined values.

## sveor[_u32]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/sveor%5B_u32%5D_z

### Signature (source notation)

```c
svuint32_t sveor[_u32]_z(svbool_t pg, svuint32_t op1, svuint32_t op2);
```

### Description

Bitwise exclusive OR

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / Exclusive OR

- SME attributes: Not specified by source.

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
EOR Zresult.S, Pg/M, Zresult.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/EOR--vectors--predicated---Bitwise-exclusive-OR--predicated--

When result is in a different register from op1, this intrinsic can use:

```asm
MOVPRFX Zresult.S, Pg/Z, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
EOR Zresult.S, Pg/M, Zresult.S, Zop1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/EOR--vectors--predicated---Bitwise-exclusive-OR--predicated--

### Operation

Source operation ID: `SveOperation_sveor_s8_z`

**Operation**



Return a vector in which each active element *i* contains `op1[i] ^ op2[i]`. Set the inactive elements of the result to zero.

## sveor[_u64]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/sveor%5B_u64%5D_m

### Signature (source notation)

```c
svuint64_t sveor[_u64]_m(svbool_t pg, svuint64_t op1, svuint64_t op2);
```

### Description

Bitwise exclusive OR

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / Exclusive OR

- SME attributes: Not specified by source.

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
EOR Ztied1.D, Pg/M, Ztied1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/EOR--vectors--predicated---Bitwise-exclusive-OR--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
EOR Zresult.D, Pg/M, Zresult.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/EOR--vectors--predicated---Bitwise-exclusive-OR--predicated--

### Operation

Source operation ID: `SveOperation_sveor_s8_m`

**Operation**



Return a vector in which each active element *i* contains `op1[i] ^ op2[i]`. Take the inactive elements of the result from the corresponding elements of `op1`.

## sveor[_u64]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/sveor%5B_u64%5D_x

### Signature (source notation)

```c
svuint64_t sveor[_u64]_x(svbool_t pg, svuint64_t op1, svuint64_t op2);
```

### Description

Bitwise exclusive OR

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / Exclusive OR

- SME attributes: Not specified by source.

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
EOR Ztied1.D, Pg/M, Ztied1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/EOR--vectors--predicated---Bitwise-exclusive-OR--predicated--

When result and op2 are in the same register, this intrinsic can use:

```asm
EOR Ztied2.D, Pg/M, Ztied2.D, Zop1.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/EOR--vectors--predicated---Bitwise-exclusive-OR--predicated--

This intrinsic compiles to:

```asm
EOR Zresult.D, Zop1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/EOR--vectors--unpredicated---Bitwise-exclusive-OR--unpredicated--

### Operation

Source operation ID: `SveOperation_sveor_s8_x`

**Operation**



Return a vector in which each active element *i* contains `op1[i] ^ op2[i]`. The inactive elements of the result have arbitrary, undefined values.

## sveor[_u64]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/sveor%5B_u64%5D_z

### Signature (source notation)

```c
svuint64_t sveor[_u64]_z(svbool_t pg, svuint64_t op1, svuint64_t op2);
```

### Description

Bitwise exclusive OR

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / Exclusive OR

- SME attributes: Not specified by source.

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
EOR Zresult.D, Pg/M, Zresult.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/EOR--vectors--predicated---Bitwise-exclusive-OR--predicated--

When result is in a different register from op1, this intrinsic can use:

```asm
MOVPRFX Zresult.D, Pg/Z, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
EOR Zresult.D, Pg/M, Zresult.D, Zop1.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/EOR--vectors--predicated---Bitwise-exclusive-OR--predicated--

### Operation

Source operation ID: `SveOperation_sveor_s8_z`

**Operation**



Return a vector in which each active element *i* contains `op1[i] ^ op2[i]`. Set the inactive elements of the result to zero.

## sveor[_u8]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/sveor%5B_u8%5D_m

### Signature (source notation)

```c
svuint8_t sveor[_u8]_m(svbool_t pg, svuint8_t op1, svuint8_t op2);
```

### Description

Bitwise exclusive OR

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / Exclusive OR

- SME attributes: Not specified by source.

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
EOR Ztied1.B, Pg/M, Ztied1.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/EOR--vectors--predicated---Bitwise-exclusive-OR--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
EOR Zresult.B, Pg/M, Zresult.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/EOR--vectors--predicated---Bitwise-exclusive-OR--predicated--

### Operation

Source operation ID: `SveOperation_sveor_s8_m`

**Operation**



Return a vector in which each active element *i* contains `op1[i] ^ op2[i]`. Take the inactive elements of the result from the corresponding elements of `op1`.

## sveor[_u8]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/sveor%5B_u8%5D_x

### Signature (source notation)

```c
svuint8_t sveor[_u8]_x(svbool_t pg, svuint8_t op1, svuint8_t op2);
```

### Description

Bitwise exclusive OR

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / Exclusive OR

- SME attributes: Not specified by source.

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
EOR Ztied1.B, Pg/M, Ztied1.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/EOR--vectors--predicated---Bitwise-exclusive-OR--predicated--

When result and op2 are in the same register, this intrinsic can use:

```asm
EOR Ztied2.B, Pg/M, Ztied2.B, Zop1.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/EOR--vectors--predicated---Bitwise-exclusive-OR--predicated--

This intrinsic compiles to:

```asm
EOR Zresult.D, Zop1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/EOR--vectors--unpredicated---Bitwise-exclusive-OR--unpredicated--

### Operation

Source operation ID: `SveOperation_sveor_s8_x`

**Operation**



Return a vector in which each active element *i* contains `op1[i] ^ op2[i]`. The inactive elements of the result have arbitrary, undefined values.

## sveor[_u8]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/sveor%5B_u8%5D_z

### Signature (source notation)

```c
svuint8_t sveor[_u8]_z(svbool_t pg, svuint8_t op1, svuint8_t op2);
```

### Description

Bitwise exclusive OR

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / Exclusive OR

- SME attributes: Not specified by source.

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
EOR Zresult.B, Pg/M, Zresult.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/EOR--vectors--predicated---Bitwise-exclusive-OR--predicated--

When result is in a different register from op1, this intrinsic can use:

```asm
MOVPRFX Zresult.B, Pg/Z, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
EOR Zresult.B, Pg/M, Zresult.B, Zop1.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/EOR--vectors--predicated---Bitwise-exclusive-OR--predicated--

### Operation

Source operation ID: `SveOperation_sveor_s8_z`

**Operation**



Return a vector in which each active element *i* contains `op1[i] ^ op2[i]`. Set the inactive elements of the result to zero.

## sveorbt[_n_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/sveorbt%5B_n_s16%5D

### Signature (source notation)

```c
svint16_t sveorbt[_n_s16](svint16_t odd, svint16_t op1, int16_t op2);
```

### Description

Interleaving exclusive OR (bottom, top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Logical / Exclusive OR

- SME attributes: Not specified by source.

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
  "odd": {
    "register": "Zodd.H|Ztied.H"
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
    "Zresult.H|Ztied.H": "result"
  }
]
```

### Instruction mapping

When result and odd are in the same register, this intrinsic compiles to:

```asm
EORBT Ztied.H, Zop1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/EORBT--Interleaving-exclusive-OR--bottom--top--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zodd
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
EORBT Zresult.H, Zop1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/EORBT--Interleaving-exclusive-OR--bottom--top--

### Operation

Source operation ID: `SveOperation_sveorbt_n_s8`

**Operation**



Return a vector in which, for each even element index *i*:




- element *i* contains `op1[i] ^ op2`
- element *i* + 1 contains `odd[i + 1]`

## sveorbt[_n_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/sveorbt%5B_n_s32%5D

### Signature (source notation)

```c
svint32_t sveorbt[_n_s32](svint32_t odd, svint32_t op1, int32_t op2);
```

### Description

Interleaving exclusive OR (bottom, top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Logical / Exclusive OR

- SME attributes: Not specified by source.

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
  "odd": {
    "register": "Zodd.S|Ztied.S"
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
    "Zresult.S|Ztied.S": "result"
  }
]
```

### Instruction mapping

When result and odd are in the same register, this intrinsic compiles to:

```asm
EORBT Ztied.S, Zop1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/EORBT--Interleaving-exclusive-OR--bottom--top--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zodd
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
EORBT Zresult.S, Zop1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/EORBT--Interleaving-exclusive-OR--bottom--top--

### Operation

Source operation ID: `SveOperation_sveorbt_n_s8`

**Operation**



Return a vector in which, for each even element index *i*:




- element *i* contains `op1[i] ^ op2`
- element *i* + 1 contains `odd[i + 1]`

## sveorbt[_n_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/sveorbt%5B_n_s64%5D

### Signature (source notation)

```c
svint64_t sveorbt[_n_s64](svint64_t odd, svint64_t op1, int64_t op2);
```

### Description

Interleaving exclusive OR (bottom, top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Logical / Exclusive OR

- SME attributes: Not specified by source.

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
  "odd": {
    "register": "Zodd.D|Ztied.D"
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
    "Zresult.D|Ztied.D": "result"
  }
]
```

### Instruction mapping

When result and odd are in the same register, this intrinsic compiles to:

```asm
EORBT Ztied.D, Zop1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/EORBT--Interleaving-exclusive-OR--bottom--top--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zodd
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
EORBT Zresult.D, Zop1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/EORBT--Interleaving-exclusive-OR--bottom--top--

### Operation

Source operation ID: `SveOperation_sveorbt_n_s8`

**Operation**



Return a vector in which, for each even element index *i*:




- element *i* contains `op1[i] ^ op2`
- element *i* + 1 contains `odd[i + 1]`

## sveorbt[_n_s8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/sveorbt%5B_n_s8%5D

### Signature (source notation)

```c
svint8_t sveorbt[_n_s8](svint8_t odd, svint8_t op1, int8_t op2);
```

### Description

Interleaving exclusive OR (bottom, top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Logical / Exclusive OR

- SME attributes: Not specified by source.

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
  "odd": {
    "register": "Zodd.B|Ztied.B"
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
    "Zresult.B|Ztied.B": "result"
  }
]
```

### Instruction mapping

When result and odd are in the same register, this intrinsic compiles to:

```asm
EORBT Ztied.B, Zop1.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/EORBT--Interleaving-exclusive-OR--bottom--top--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zodd
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
EORBT Zresult.B, Zop1.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/EORBT--Interleaving-exclusive-OR--bottom--top--

### Operation

Source operation ID: `SveOperation_sveorbt_n_s8`

**Operation**



Return a vector in which, for each even element index *i*:




- element *i* contains `op1[i] ^ op2`
- element *i* + 1 contains `odd[i + 1]`

## sveorbt[_n_u16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/sveorbt%5B_n_u16%5D

### Signature (source notation)

```c
svuint16_t sveorbt[_n_u16](svuint16_t odd, svuint16_t op1, uint16_t op2);
```

### Description

Interleaving exclusive OR (bottom, top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Logical / Exclusive OR

- SME attributes: Not specified by source.

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
  "odd": {
    "register": "Zodd.H|Ztied.H"
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
    "Zresult.H|Ztied.H": "result"
  }
]
```

### Instruction mapping

When result and odd are in the same register, this intrinsic compiles to:

```asm
EORBT Ztied.H, Zop1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/EORBT--Interleaving-exclusive-OR--bottom--top--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zodd
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
EORBT Zresult.H, Zop1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/EORBT--Interleaving-exclusive-OR--bottom--top--

### Operation

Source operation ID: `SveOperation_sveorbt_n_s8`

**Operation**



Return a vector in which, for each even element index *i*:




- element *i* contains `op1[i] ^ op2`
- element *i* + 1 contains `odd[i + 1]`

## sveorbt[_n_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/sveorbt%5B_n_u32%5D

### Signature (source notation)

```c
svuint32_t sveorbt[_n_u32](svuint32_t odd, svuint32_t op1, uint32_t op2);
```

### Description

Interleaving exclusive OR (bottom, top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Logical / Exclusive OR

- SME attributes: Not specified by source.

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
  "odd": {
    "register": "Zodd.S|Ztied.S"
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
    "Zresult.S|Ztied.S": "result"
  }
]
```

### Instruction mapping

When result and odd are in the same register, this intrinsic compiles to:

```asm
EORBT Ztied.S, Zop1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/EORBT--Interleaving-exclusive-OR--bottom--top--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zodd
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
EORBT Zresult.S, Zop1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/EORBT--Interleaving-exclusive-OR--bottom--top--

### Operation

Source operation ID: `SveOperation_sveorbt_n_s8`

**Operation**



Return a vector in which, for each even element index *i*:




- element *i* contains `op1[i] ^ op2`
- element *i* + 1 contains `odd[i + 1]`

## sveorbt[_n_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/sveorbt%5B_n_u64%5D

### Signature (source notation)

```c
svuint64_t sveorbt[_n_u64](svuint64_t odd, svuint64_t op1, uint64_t op2);
```

### Description

Interleaving exclusive OR (bottom, top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Logical / Exclusive OR

- SME attributes: Not specified by source.

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
  "odd": {
    "register": "Zodd.D|Ztied.D"
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
    "Zresult.D|Ztied.D": "result"
  }
]
```

### Instruction mapping

When result and odd are in the same register, this intrinsic compiles to:

```asm
EORBT Ztied.D, Zop1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/EORBT--Interleaving-exclusive-OR--bottom--top--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zodd
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
EORBT Zresult.D, Zop1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/EORBT--Interleaving-exclusive-OR--bottom--top--

### Operation

Source operation ID: `SveOperation_sveorbt_n_s8`

**Operation**



Return a vector in which, for each even element index *i*:




- element *i* contains `op1[i] ^ op2`
- element *i* + 1 contains `odd[i + 1]`

## sveorbt[_n_u8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/sveorbt%5B_n_u8%5D

### Signature (source notation)

```c
svuint8_t sveorbt[_n_u8](svuint8_t odd, svuint8_t op1, uint8_t op2);
```

### Description

Interleaving exclusive OR (bottom, top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Logical / Exclusive OR

- SME attributes: Not specified by source.

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
  "odd": {
    "register": "Zodd.B|Ztied.B"
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
    "Zresult.B|Ztied.B": "result"
  }
]
```

### Instruction mapping

When result and odd are in the same register, this intrinsic compiles to:

```asm
EORBT Ztied.B, Zop1.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/EORBT--Interleaving-exclusive-OR--bottom--top--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zodd
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
EORBT Zresult.B, Zop1.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/EORBT--Interleaving-exclusive-OR--bottom--top--

### Operation

Source operation ID: `SveOperation_sveorbt_n_s8`

**Operation**



Return a vector in which, for each even element index *i*:




- element *i* contains `op1[i] ^ op2`
- element *i* + 1 contains `odd[i + 1]`

## sveorbt[_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/sveorbt%5B_s16%5D

### Signature (source notation)

```c
svint16_t sveorbt[_s16](svint16_t odd, svint16_t op1, svint16_t op2);
```

### Description

Interleaving exclusive OR (bottom, top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Logical / Exclusive OR

- SME attributes: Not specified by source.

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
  "odd": {
    "register": "Zodd.H|Ztied.H"
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
    "Zresult.H|Ztied.H": "result"
  }
]
```

### Instruction mapping

When result and odd are in the same register, this intrinsic compiles to:

```asm
EORBT Ztied.H, Zop1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/EORBT--Interleaving-exclusive-OR--bottom--top--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zodd
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
EORBT Zresult.H, Zop1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/EORBT--Interleaving-exclusive-OR--bottom--top--

### Operation

Source operation ID: `SveOperation_sveorbt_s8`

**Operation**



Return a vector in which, for each even element index *i*:




- element *i* contains `op1[i] ^ op2[i + 1]`
- element *i* + 1 contains `odd[i + 1]`

## sveorbt[_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/sveorbt%5B_s32%5D

### Signature (source notation)

```c
svint32_t sveorbt[_s32](svint32_t odd, svint32_t op1, svint32_t op2);
```

### Description

Interleaving exclusive OR (bottom, top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Logical / Exclusive OR

- SME attributes: Not specified by source.

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
  "odd": {
    "register": "Zodd.S|Ztied.S"
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
    "Zresult.S|Ztied.S": "result"
  }
]
```

### Instruction mapping

When result and odd are in the same register, this intrinsic compiles to:

```asm
EORBT Ztied.S, Zop1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/EORBT--Interleaving-exclusive-OR--bottom--top--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zodd
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
EORBT Zresult.S, Zop1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/EORBT--Interleaving-exclusive-OR--bottom--top--

### Operation

Source operation ID: `SveOperation_sveorbt_s8`

**Operation**



Return a vector in which, for each even element index *i*:




- element *i* contains `op1[i] ^ op2[i + 1]`
- element *i* + 1 contains `odd[i + 1]`

## sveorbt[_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/sveorbt%5B_s64%5D

### Signature (source notation)

```c
svint64_t sveorbt[_s64](svint64_t odd, svint64_t op1, svint64_t op2);
```

### Description

Interleaving exclusive OR (bottom, top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Logical / Exclusive OR

- SME attributes: Not specified by source.

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
  "odd": {
    "register": "Zodd.D|Ztied.D"
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
    "Zresult.D|Ztied.D": "result"
  }
]
```

### Instruction mapping

When result and odd are in the same register, this intrinsic compiles to:

```asm
EORBT Ztied.D, Zop1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/EORBT--Interleaving-exclusive-OR--bottom--top--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zodd
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
EORBT Zresult.D, Zop1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/EORBT--Interleaving-exclusive-OR--bottom--top--

### Operation

Source operation ID: `SveOperation_sveorbt_s8`

**Operation**



Return a vector in which, for each even element index *i*:




- element *i* contains `op1[i] ^ op2[i + 1]`
- element *i* + 1 contains `odd[i + 1]`

## sveorbt[_s8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/sveorbt%5B_s8%5D

### Signature (source notation)

```c
svint8_t sveorbt[_s8](svint8_t odd, svint8_t op1, svint8_t op2);
```

### Description

Interleaving exclusive OR (bottom, top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Logical / Exclusive OR

- SME attributes: Not specified by source.

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
  "odd": {
    "register": "Zodd.B|Ztied.B"
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
    "Zresult.B|Ztied.B": "result"
  }
]
```

### Instruction mapping

When result and odd are in the same register, this intrinsic compiles to:

```asm
EORBT Ztied.B, Zop1.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/EORBT--Interleaving-exclusive-OR--bottom--top--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zodd
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
EORBT Zresult.B, Zop1.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/EORBT--Interleaving-exclusive-OR--bottom--top--

### Operation

Source operation ID: `SveOperation_sveorbt_s8`

**Operation**



Return a vector in which, for each even element index *i*:




- element *i* contains `op1[i] ^ op2[i + 1]`
- element *i* + 1 contains `odd[i + 1]`

## sveorbt[_u16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/sveorbt%5B_u16%5D

### Signature (source notation)

```c
svuint16_t sveorbt[_u16](svuint16_t odd, svuint16_t op1, svuint16_t op2);
```

### Description

Interleaving exclusive OR (bottom, top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Logical / Exclusive OR

- SME attributes: Not specified by source.

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
  "odd": {
    "register": "Zodd.H|Ztied.H"
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
    "Zresult.H|Ztied.H": "result"
  }
]
```

### Instruction mapping

When result and odd are in the same register, this intrinsic compiles to:

```asm
EORBT Ztied.H, Zop1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/EORBT--Interleaving-exclusive-OR--bottom--top--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zodd
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
EORBT Zresult.H, Zop1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/EORBT--Interleaving-exclusive-OR--bottom--top--

### Operation

Source operation ID: `SveOperation_sveorbt_s8`

**Operation**



Return a vector in which, for each even element index *i*:




- element *i* contains `op1[i] ^ op2[i + 1]`
- element *i* + 1 contains `odd[i + 1]`

## sveorbt[_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/sveorbt%5B_u32%5D

### Signature (source notation)

```c
svuint32_t sveorbt[_u32](svuint32_t odd, svuint32_t op1, svuint32_t op2);
```

### Description

Interleaving exclusive OR (bottom, top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Logical / Exclusive OR

- SME attributes: Not specified by source.

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
  "odd": {
    "register": "Zodd.S|Ztied.S"
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
    "Zresult.S|Ztied.S": "result"
  }
]
```

### Instruction mapping

When result and odd are in the same register, this intrinsic compiles to:

```asm
EORBT Ztied.S, Zop1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/EORBT--Interleaving-exclusive-OR--bottom--top--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zodd
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
EORBT Zresult.S, Zop1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/EORBT--Interleaving-exclusive-OR--bottom--top--

### Operation

Source operation ID: `SveOperation_sveorbt_s8`

**Operation**



Return a vector in which, for each even element index *i*:




- element *i* contains `op1[i] ^ op2[i + 1]`
- element *i* + 1 contains `odd[i + 1]`

## sveorbt[_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/sveorbt%5B_u64%5D

### Signature (source notation)

```c
svuint64_t sveorbt[_u64](svuint64_t odd, svuint64_t op1, svuint64_t op2);
```

### Description

Interleaving exclusive OR (bottom, top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Logical / Exclusive OR

- SME attributes: Not specified by source.

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
  "odd": {
    "register": "Zodd.D|Ztied.D"
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
    "Zresult.D|Ztied.D": "result"
  }
]
```

### Instruction mapping

When result and odd are in the same register, this intrinsic compiles to:

```asm
EORBT Ztied.D, Zop1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/EORBT--Interleaving-exclusive-OR--bottom--top--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zodd
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
EORBT Zresult.D, Zop1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/EORBT--Interleaving-exclusive-OR--bottom--top--

### Operation

Source operation ID: `SveOperation_sveorbt_s8`

**Operation**



Return a vector in which, for each even element index *i*:




- element *i* contains `op1[i] ^ op2[i + 1]`
- element *i* + 1 contains `odd[i + 1]`

## sveorbt[_u8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/sveorbt%5B_u8%5D

### Signature (source notation)

```c
svuint8_t sveorbt[_u8](svuint8_t odd, svuint8_t op1, svuint8_t op2);
```

### Description

Interleaving exclusive OR (bottom, top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Logical / Exclusive OR

- SME attributes: Not specified by source.

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
  "odd": {
    "register": "Zodd.B|Ztied.B"
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
    "Zresult.B|Ztied.B": "result"
  }
]
```

### Instruction mapping

When result and odd are in the same register, this intrinsic compiles to:

```asm
EORBT Ztied.B, Zop1.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/EORBT--Interleaving-exclusive-OR--bottom--top--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zodd
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
EORBT Zresult.B, Zop1.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/EORBT--Interleaving-exclusive-OR--bottom--top--

### Operation

Source operation ID: `SveOperation_sveorbt_s8`

**Operation**



Return a vector in which, for each even element index *i*:




- element *i* contains `op1[i] ^ op2[i + 1]`
- element *i* + 1 contains `odd[i + 1]`

## sveorqv[_s16]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/sveorqv%5B_s16%5D

### Signature (source notation)

```c
int16x8_t sveorqv[_s16](svbool_t pg, svint16_t zn);
```

### Description

Bitwise exclusive-OR reduction of quadword vector segments

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Logical / Exclusive OR

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p1)|FEAT_SME2p1
```

### Return type metadata

```json
{
  "return_base_type": "int16x8_t",
  "element_bit_size": "16",
  "value": "int16x8_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Preg1"
  },
  "zn": {
    "register": "Zreg1.H"
  }
}
```

### Result mapping

```json
[
  {
    "Vreg1.8H": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
EORQV Vreg1.8H, Preg1, Zreg1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/EORQV--Bitwise-exclusive-OR-reduction-of-quadword-vector-segments-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## sveorqv[_s32]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/sveorqv%5B_s32%5D

### Signature (source notation)

```c
int32x4_t sveorqv[_s32](svbool_t pg, svint32_t zn);
```

### Description

Bitwise exclusive-OR reduction of quadword vector segments

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Logical / Exclusive OR

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p1)|FEAT_SME2p1
```

### Return type metadata

```json
{
  "return_base_type": "int32x4_t",
  "element_bit_size": "32",
  "value": "int32x4_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Preg1"
  },
  "zn": {
    "register": "Zreg1.S"
  }
}
```

### Result mapping

```json
[
  {
    "Vreg1.4S": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
EORQV Vreg1.4S, Preg1, Zreg1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/EORQV--Bitwise-exclusive-OR-reduction-of-quadword-vector-segments-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## sveorqv[_s64]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/sveorqv%5B_s64%5D

### Signature (source notation)

```c
int64x2_t sveorqv[_s64](svbool_t pg, svint64_t zn);
```

### Description

Bitwise exclusive-OR reduction of quadword vector segments

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Logical / Exclusive OR

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p1)|FEAT_SME2p1
```

### Return type metadata

```json
{
  "return_base_type": "int64x2_t",
  "element_bit_size": "64",
  "value": "int64x2_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Preg1"
  },
  "zn": {
    "register": "Zreg1.D"
  }
}
```

### Result mapping

```json
[
  {
    "Vreg1.2D": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
EORQV Vreg1.2D, Preg1, Zreg1.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/EORQV--Bitwise-exclusive-OR-reduction-of-quadword-vector-segments-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## sveorqv[_s8]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/sveorqv%5B_s8%5D

### Signature (source notation)

```c
int8x16_t sveorqv[_s8](svbool_t pg, svint8_t zn);
```

### Description

Bitwise exclusive-OR reduction of quadword vector segments

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Logical / Exclusive OR

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p1)|FEAT_SME2p1
```

### Return type metadata

```json
{
  "return_base_type": "int8x16_t",
  "element_bit_size": "8",
  "value": "int8x16_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Preg1"
  },
  "zn": {
    "register": "Zreg1.B"
  }
}
```

### Result mapping

```json
[
  {
    "Vreg1.16B": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
EORQV Vreg1.16B, Preg1, Zreg1.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/EORQV--Bitwise-exclusive-OR-reduction-of-quadword-vector-segments-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## sveorqv[_u16]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/sveorqv%5B_u16%5D

### Signature (source notation)

```c
uint16x8_t sveorqv[_u16](svbool_t pg, svuint16_t zn);
```

### Description

Bitwise exclusive-OR reduction of quadword vector segments

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Logical / Exclusive OR

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p1)|FEAT_SME2p1
```

### Return type metadata

```json
{
  "return_base_type": "uint16x8_t",
  "element_bit_size": "16",
  "value": "uint16x8_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Preg1"
  },
  "zn": {
    "register": "Zreg1.H"
  }
}
```

### Result mapping

```json
[
  {
    "Vreg1.8H": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
EORQV Vreg1.8H, Preg1, Zreg1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/EORQV--Bitwise-exclusive-OR-reduction-of-quadword-vector-segments-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## sveorqv[_u32]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/sveorqv%5B_u32%5D

### Signature (source notation)

```c
uint32x4_t sveorqv[_u32](svbool_t pg, svuint32_t zn);
```

### Description

Bitwise exclusive-OR reduction of quadword vector segments

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Logical / Exclusive OR

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p1)|FEAT_SME2p1
```

### Return type metadata

```json
{
  "return_base_type": "uint32x4_t",
  "element_bit_size": "32",
  "value": "uint32x4_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Preg1"
  },
  "zn": {
    "register": "Zreg1.S"
  }
}
```

### Result mapping

```json
[
  {
    "Vreg1.4S": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
EORQV Vreg1.4S, Preg1, Zreg1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/EORQV--Bitwise-exclusive-OR-reduction-of-quadword-vector-segments-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## sveorqv[_u64]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/sveorqv%5B_u64%5D

### Signature (source notation)

```c
uint64x2_t sveorqv[_u64](svbool_t pg, svuint64_t zn);
```

### Description

Bitwise exclusive-OR reduction of quadword vector segments

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Logical / Exclusive OR

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p1)|FEAT_SME2p1
```

### Return type metadata

```json
{
  "return_base_type": "uint64x2_t",
  "element_bit_size": "64",
  "value": "uint64x2_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Preg1"
  },
  "zn": {
    "register": "Zreg1.D"
  }
}
```

### Result mapping

```json
[
  {
    "Vreg1.2D": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
EORQV Vreg1.2D, Preg1, Zreg1.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/EORQV--Bitwise-exclusive-OR-reduction-of-quadword-vector-segments-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## sveorqv[_u8]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/sveorqv%5B_u8%5D

### Signature (source notation)

```c
uint8x16_t sveorqv[_u8](svbool_t pg, svuint8_t zn);
```

### Description

Bitwise exclusive-OR reduction of quadword vector segments

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Logical / Exclusive OR

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p1)|FEAT_SME2p1
```

### Return type metadata

```json
{
  "return_base_type": "uint8x16_t",
  "element_bit_size": "8",
  "value": "uint8x16_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Preg1"
  },
  "zn": {
    "register": "Zreg1.B"
  }
}
```

### Result mapping

```json
[
  {
    "Vreg1.16B": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
EORQV Vreg1.16B, Preg1, Zreg1.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/EORQV--Bitwise-exclusive-OR-reduction-of-quadword-vector-segments-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## sveortb[_n_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/sveortb%5B_n_s16%5D

### Signature (source notation)

```c
svint16_t sveortb[_n_s16](svint16_t even, svint16_t op1, int16_t op2);
```

### Description

Interleaving exclusive OR (top, bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Logical / Exclusive OR

- SME attributes: Not specified by source.

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
  "even": {
    "register": "Zeven.H|Ztied.H"
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
    "Zresult.H|Ztied.H": "result"
  }
]
```

### Instruction mapping

When result and even are in the same register, this intrinsic compiles to:

```asm
EORTB Ztied.H, Zop1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/EORTB--Interleaving-exclusive-OR--top--bottom--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zeven
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
EORTB Zresult.H, Zop1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/EORTB--Interleaving-exclusive-OR--top--bottom--

### Operation

Source operation ID: `SveOperation_sveortb_n_s8`

**Operation**



Return a vector in which, for each even element index *i*:




- element *i* contains `even[i]`
- element *i* + 1 contains `op1[i + 1] ^ op2`

## sveortb[_n_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/sveortb%5B_n_s32%5D

### Signature (source notation)

```c
svint32_t sveortb[_n_s32](svint32_t even, svint32_t op1, int32_t op2);
```

### Description

Interleaving exclusive OR (top, bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Logical / Exclusive OR

- SME attributes: Not specified by source.

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
  "even": {
    "register": "Zeven.S|Ztied.S"
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
    "Zresult.S|Ztied.S": "result"
  }
]
```

### Instruction mapping

When result and even are in the same register, this intrinsic compiles to:

```asm
EORTB Ztied.S, Zop1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/EORTB--Interleaving-exclusive-OR--top--bottom--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zeven
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
EORTB Zresult.S, Zop1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/EORTB--Interleaving-exclusive-OR--top--bottom--

### Operation

Source operation ID: `SveOperation_sveortb_n_s8`

**Operation**



Return a vector in which, for each even element index *i*:




- element *i* contains `even[i]`
- element *i* + 1 contains `op1[i + 1] ^ op2`

## sveortb[_n_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/sveortb%5B_n_s64%5D

### Signature (source notation)

```c
svint64_t sveortb[_n_s64](svint64_t even, svint64_t op1, int64_t op2);
```

### Description

Interleaving exclusive OR (top, bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Logical / Exclusive OR

- SME attributes: Not specified by source.

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
  "even": {
    "register": "Zeven.D|Ztied.D"
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
    "Zresult.D|Ztied.D": "result"
  }
]
```

### Instruction mapping

When result and even are in the same register, this intrinsic compiles to:

```asm
EORTB Ztied.D, Zop1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/EORTB--Interleaving-exclusive-OR--top--bottom--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zeven
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
EORTB Zresult.D, Zop1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/EORTB--Interleaving-exclusive-OR--top--bottom--

### Operation

Source operation ID: `SveOperation_sveortb_n_s8`

**Operation**



Return a vector in which, for each even element index *i*:




- element *i* contains `even[i]`
- element *i* + 1 contains `op1[i + 1] ^ op2`

## sveortb[_n_s8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/sveortb%5B_n_s8%5D

### Signature (source notation)

```c
svint8_t sveortb[_n_s8](svint8_t even, svint8_t op1, int8_t op2);
```

### Description

Interleaving exclusive OR (top, bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Logical / Exclusive OR

- SME attributes: Not specified by source.

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
  "even": {
    "register": "Zeven.B|Ztied.B"
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
    "Zresult.B|Ztied.B": "result"
  }
]
```

### Instruction mapping

When result and even are in the same register, this intrinsic compiles to:

```asm
EORTB Ztied.B, Zop1.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/EORTB--Interleaving-exclusive-OR--top--bottom--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zeven
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
EORTB Zresult.B, Zop1.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/EORTB--Interleaving-exclusive-OR--top--bottom--

### Operation

Source operation ID: `SveOperation_sveortb_n_s8`

**Operation**



Return a vector in which, for each even element index *i*:




- element *i* contains `even[i]`
- element *i* + 1 contains `op1[i + 1] ^ op2`

## sveortb[_n_u16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/sveortb%5B_n_u16%5D

### Signature (source notation)

```c
svuint16_t sveortb[_n_u16](svuint16_t even, svuint16_t op1, uint16_t op2);
```

### Description

Interleaving exclusive OR (top, bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Logical / Exclusive OR

- SME attributes: Not specified by source.

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
  "even": {
    "register": "Zeven.H|Ztied.H"
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
    "Zresult.H|Ztied.H": "result"
  }
]
```

### Instruction mapping

When result and even are in the same register, this intrinsic compiles to:

```asm
EORTB Ztied.H, Zop1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/EORTB--Interleaving-exclusive-OR--top--bottom--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zeven
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
EORTB Zresult.H, Zop1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/EORTB--Interleaving-exclusive-OR--top--bottom--

### Operation

Source operation ID: `SveOperation_sveortb_n_s8`

**Operation**



Return a vector in which, for each even element index *i*:




- element *i* contains `even[i]`
- element *i* + 1 contains `op1[i + 1] ^ op2`

## sveortb[_n_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/sveortb%5B_n_u32%5D

### Signature (source notation)

```c
svuint32_t sveortb[_n_u32](svuint32_t even, svuint32_t op1, uint32_t op2);
```

### Description

Interleaving exclusive OR (top, bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Logical / Exclusive OR

- SME attributes: Not specified by source.

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
  "even": {
    "register": "Zeven.S|Ztied.S"
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
    "Zresult.S|Ztied.S": "result"
  }
]
```

### Instruction mapping

When result and even are in the same register, this intrinsic compiles to:

```asm
EORTB Ztied.S, Zop1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/EORTB--Interleaving-exclusive-OR--top--bottom--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zeven
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
EORTB Zresult.S, Zop1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/EORTB--Interleaving-exclusive-OR--top--bottom--

### Operation

Source operation ID: `SveOperation_sveortb_n_s8`

**Operation**



Return a vector in which, for each even element index *i*:




- element *i* contains `even[i]`
- element *i* + 1 contains `op1[i + 1] ^ op2`

## sveortb[_n_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/sveortb%5B_n_u64%5D

### Signature (source notation)

```c
svuint64_t sveortb[_n_u64](svuint64_t even, svuint64_t op1, uint64_t op2);
```

### Description

Interleaving exclusive OR (top, bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Logical / Exclusive OR

- SME attributes: Not specified by source.

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
  "even": {
    "register": "Zeven.D|Ztied.D"
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
    "Zresult.D|Ztied.D": "result"
  }
]
```

### Instruction mapping

When result and even are in the same register, this intrinsic compiles to:

```asm
EORTB Ztied.D, Zop1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/EORTB--Interleaving-exclusive-OR--top--bottom--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zeven
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
EORTB Zresult.D, Zop1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/EORTB--Interleaving-exclusive-OR--top--bottom--

### Operation

Source operation ID: `SveOperation_sveortb_n_s8`

**Operation**



Return a vector in which, for each even element index *i*:




- element *i* contains `even[i]`
- element *i* + 1 contains `op1[i + 1] ^ op2`

## sveortb[_n_u8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/sveortb%5B_n_u8%5D

### Signature (source notation)

```c
svuint8_t sveortb[_n_u8](svuint8_t even, svuint8_t op1, uint8_t op2);
```

### Description

Interleaving exclusive OR (top, bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Logical / Exclusive OR

- SME attributes: Not specified by source.

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
  "even": {
    "register": "Zeven.B|Ztied.B"
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
    "Zresult.B|Ztied.B": "result"
  }
]
```

### Instruction mapping

When result and even are in the same register, this intrinsic compiles to:

```asm
EORTB Ztied.B, Zop1.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/EORTB--Interleaving-exclusive-OR--top--bottom--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zeven
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
EORTB Zresult.B, Zop1.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/EORTB--Interleaving-exclusive-OR--top--bottom--

### Operation

Source operation ID: `SveOperation_sveortb_n_s8`

**Operation**



Return a vector in which, for each even element index *i*:




- element *i* contains `even[i]`
- element *i* + 1 contains `op1[i + 1] ^ op2`

## sveortb[_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/sveortb%5B_s16%5D

### Signature (source notation)

```c
svint16_t sveortb[_s16](svint16_t even, svint16_t op1, svint16_t op2);
```

### Description

Interleaving exclusive OR (top, bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Logical / Exclusive OR

- SME attributes: Not specified by source.

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
  "even": {
    "register": "Zeven.H|Ztied.H"
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
    "Zresult.H|Ztied.H": "result"
  }
]
```

### Instruction mapping

When result and even are in the same register, this intrinsic compiles to:

```asm
EORTB Ztied.H, Zop1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/EORTB--Interleaving-exclusive-OR--top--bottom--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zeven
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
EORTB Zresult.H, Zop1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/EORTB--Interleaving-exclusive-OR--top--bottom--

### Operation

Source operation ID: `SveOperation_sveortb_s8`

**Operation**



Return a vector in which, for each even element index *i*:




- element *i* contains `even[i]`
- element *i* + 1 contains `op1[i + 1] ^ op2[i]`

## sveortb[_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/sveortb%5B_s32%5D

### Signature (source notation)

```c
svint32_t sveortb[_s32](svint32_t even, svint32_t op1, svint32_t op2);
```

### Description

Interleaving exclusive OR (top, bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Logical / Exclusive OR

- SME attributes: Not specified by source.

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
  "even": {
    "register": "Zeven.S|Ztied.S"
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
    "Zresult.S|Ztied.S": "result"
  }
]
```

### Instruction mapping

When result and even are in the same register, this intrinsic compiles to:

```asm
EORTB Ztied.S, Zop1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/EORTB--Interleaving-exclusive-OR--top--bottom--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zeven
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
EORTB Zresult.S, Zop1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/EORTB--Interleaving-exclusive-OR--top--bottom--

### Operation

Source operation ID: `SveOperation_sveortb_s8`

**Operation**



Return a vector in which, for each even element index *i*:




- element *i* contains `even[i]`
- element *i* + 1 contains `op1[i + 1] ^ op2[i]`

## sveortb[_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/sveortb%5B_s64%5D

### Signature (source notation)

```c
svint64_t sveortb[_s64](svint64_t even, svint64_t op1, svint64_t op2);
```

### Description

Interleaving exclusive OR (top, bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Logical / Exclusive OR

- SME attributes: Not specified by source.

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
  "even": {
    "register": "Zeven.D|Ztied.D"
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
    "Zresult.D|Ztied.D": "result"
  }
]
```

### Instruction mapping

When result and even are in the same register, this intrinsic compiles to:

```asm
EORTB Ztied.D, Zop1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/EORTB--Interleaving-exclusive-OR--top--bottom--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zeven
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
EORTB Zresult.D, Zop1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/EORTB--Interleaving-exclusive-OR--top--bottom--

### Operation

Source operation ID: `SveOperation_sveortb_s8`

**Operation**



Return a vector in which, for each even element index *i*:




- element *i* contains `even[i]`
- element *i* + 1 contains `op1[i + 1] ^ op2[i]`

