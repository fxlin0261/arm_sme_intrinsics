# SME / Logical / OR — Part 2

## svorr[_u32]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svorr%5B_u32%5D_z

### Signature (source notation)

```c
svuint32_t svorr[_u32]_z(svbool_t pg, svuint32_t op1, svuint32_t op2);
```

### Description

Bitwise inclusive OR

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / OR

- SME attributes: Not specified by source.

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
ORR Zresult.S, Pg/M, Zresult.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ORR--vectors--predicated---Bitwise-inclusive-OR--predicated--

When result is in a different register from op1, this intrinsic can use:

```asm
MOVPRFX Zresult.S, Pg/Z, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
ORR Zresult.S, Pg/M, Zresult.S, Zop1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ORR--vectors--predicated---Bitwise-inclusive-OR--predicated--

### Operation

Source operation ID: `SveOperation_svorr_s8_z`

**Operation**



Return a vector in which each active element *i* contains `op1[i] | op2[i]`. Set the inactive elements of the result to zero.

## svorr[_u64]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svorr%5B_u64%5D_m

### Signature (source notation)

```c
svuint64_t svorr[_u64]_m(svbool_t pg, svuint64_t op1, svuint64_t op2);
```

### Description

Bitwise inclusive OR

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / OR

- SME attributes: Not specified by source.

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
ORR Ztied1.D, Pg/M, Ztied1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ORR--vectors--predicated---Bitwise-inclusive-OR--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
ORR Zresult.D, Pg/M, Zresult.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ORR--vectors--predicated---Bitwise-inclusive-OR--predicated--

### Operation

Source operation ID: `SveOperation_svorr_s8_m`

**Operation**



Return a vector in which each active element *i* contains `op1[i] | op2[i]`. Take the inactive elements of the result from the corresponding elements of `op1`.

## svorr[_u64]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svorr%5B_u64%5D_x

### Signature (source notation)

```c
svuint64_t svorr[_u64]_x(svbool_t pg, svuint64_t op1, svuint64_t op2);
```

### Description

Bitwise inclusive OR

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / OR

- SME attributes: Not specified by source.

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
ORR Ztied1.D, Pg/M, Ztied1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ORR--vectors--predicated---Bitwise-inclusive-OR--predicated--

When result and op2 are in the same register, this intrinsic can use:

```asm
ORR Ztied2.D, Pg/M, Ztied2.D, Zop1.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ORR--vectors--predicated---Bitwise-inclusive-OR--predicated--

This intrinsic compiles to:

```asm
ORR Zresult.D, Zop1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ORR--vectors--unpredicated---Bitwise-inclusive-OR--unpredicated--

### Operation

Source operation ID: `SveOperation_svorr_s8_x`

**Operation**



Return a vector in which each active element *i* contains `op1[i] | op2[i]`. The inactive elements of the result have arbitrary, undefined values.

## svorr[_u64]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svorr%5B_u64%5D_z

### Signature (source notation)

```c
svuint64_t svorr[_u64]_z(svbool_t pg, svuint64_t op1, svuint64_t op2);
```

### Description

Bitwise inclusive OR

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / OR

- SME attributes: Not specified by source.

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
ORR Zresult.D, Pg/M, Zresult.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ORR--vectors--predicated---Bitwise-inclusive-OR--predicated--

When result is in a different register from op1, this intrinsic can use:

```asm
MOVPRFX Zresult.D, Pg/Z, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
ORR Zresult.D, Pg/M, Zresult.D, Zop1.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ORR--vectors--predicated---Bitwise-inclusive-OR--predicated--

### Operation

Source operation ID: `SveOperation_svorr_s8_z`

**Operation**



Return a vector in which each active element *i* contains `op1[i] | op2[i]`. Set the inactive elements of the result to zero.

## svorr[_u8]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svorr%5B_u8%5D_m

### Signature (source notation)

```c
svuint8_t svorr[_u8]_m(svbool_t pg, svuint8_t op1, svuint8_t op2);
```

### Description

Bitwise inclusive OR

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / OR

- SME attributes: Not specified by source.

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
ORR Ztied1.B, Pg/M, Ztied1.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ORR--vectors--predicated---Bitwise-inclusive-OR--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
ORR Zresult.B, Pg/M, Zresult.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ORR--vectors--predicated---Bitwise-inclusive-OR--predicated--

### Operation

Source operation ID: `SveOperation_svorr_s8_m`

**Operation**



Return a vector in which each active element *i* contains `op1[i] | op2[i]`. Take the inactive elements of the result from the corresponding elements of `op1`.

## svorr[_u8]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svorr%5B_u8%5D_x

### Signature (source notation)

```c
svuint8_t svorr[_u8]_x(svbool_t pg, svuint8_t op1, svuint8_t op2);
```

### Description

Bitwise inclusive OR

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / OR

- SME attributes: Not specified by source.

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
ORR Ztied1.B, Pg/M, Ztied1.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ORR--vectors--predicated---Bitwise-inclusive-OR--predicated--

When result and op2 are in the same register, this intrinsic can use:

```asm
ORR Ztied2.B, Pg/M, Ztied2.B, Zop1.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ORR--vectors--predicated---Bitwise-inclusive-OR--predicated--

This intrinsic compiles to:

```asm
ORR Zresult.D, Zop1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ORR--vectors--unpredicated---Bitwise-inclusive-OR--unpredicated--

### Operation

Source operation ID: `SveOperation_svorr_s8_x`

**Operation**



Return a vector in which each active element *i* contains `op1[i] | op2[i]`. The inactive elements of the result have arbitrary, undefined values.

## svorr[_u8]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svorr%5B_u8%5D_z

### Signature (source notation)

```c
svuint8_t svorr[_u8]_z(svbool_t pg, svuint8_t op1, svuint8_t op2);
```

### Description

Bitwise inclusive OR

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / OR

- SME attributes: Not specified by source.

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
ORR Zresult.B, Pg/M, Zresult.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ORR--vectors--predicated---Bitwise-inclusive-OR--predicated--

When result is in a different register from op1, this intrinsic can use:

```asm
MOVPRFX Zresult.B, Pg/Z, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
ORR Zresult.B, Pg/M, Zresult.B, Zop1.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ORR--vectors--predicated---Bitwise-inclusive-OR--predicated--

### Operation

Source operation ID: `SveOperation_svorr_s8_z`

**Operation**



Return a vector in which each active element *i* contains `op1[i] | op2[i]`. Set the inactive elements of the result to zero.

## svorv[_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svorv%5B_s16%5D

### Signature (source notation)

```c
int16_t svorv[_s16](svbool_t pg, svint16_t op);
```

### Description

Bitwise inclusive OR reduction to scalar

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / OR

- SME attributes: Not specified by source.

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
  "value": "int16_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Pg"
  },
  "op": {
    "register": "Zop.H"
  }
}
```

### Result mapping

```json
[
  {
    "Hresult": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
ORV Hresult, Pg, Zop.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ORV--Bitwise-inclusive-OR-reduction-to-scalar-

### Operation

Source operation ID: `SveOperation_svorv_s8`

**Operation**



Return the bitwise inclusive OR of all active elements of `op`.  Return zero if no elements are active.

## svorv[_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svorv%5B_s32%5D

### Signature (source notation)

```c
int32_t svorv[_s32](svbool_t pg, svint32_t op);
```

### Description

Bitwise inclusive OR reduction to scalar

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / OR

- SME attributes: Not specified by source.

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
  "value": "int32_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Pg"
  },
  "op": {
    "register": "Zop.S"
  }
}
```

### Result mapping

```json
[
  {
    "Sresult": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
ORV Sresult, Pg, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ORV--Bitwise-inclusive-OR-reduction-to-scalar-

### Operation

Source operation ID: `SveOperation_svorv_s8`

**Operation**



Return the bitwise inclusive OR of all active elements of `op`.  Return zero if no elements are active.

## svorv[_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svorv%5B_s64%5D

### Signature (source notation)

```c
int64_t svorv[_s64](svbool_t pg, svint64_t op);
```

### Description

Bitwise inclusive OR reduction to scalar

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / OR

- SME attributes: Not specified by source.

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
  "value": "int64_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Pg"
  },
  "op": {
    "register": "Zop.D"
  }
}
```

### Result mapping

```json
[
  {
    "Dresult": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
ORV Dresult, Pg, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ORV--Bitwise-inclusive-OR-reduction-to-scalar-

### Operation

Source operation ID: `SveOperation_svorv_s8`

**Operation**



Return the bitwise inclusive OR of all active elements of `op`.  Return zero if no elements are active.

## svorv[_s8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svorv%5B_s8%5D

### Signature (source notation)

```c
int8_t svorv[_s8](svbool_t pg, svint8_t op);
```

### Description

Bitwise inclusive OR reduction to scalar

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / OR

- SME attributes: Not specified by source.

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
  "value": "int8_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Pg"
  },
  "op": {
    "register": "Zop.B"
  }
}
```

### Result mapping

```json
[
  {
    "Bresult": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
ORV Bresult, Pg, Zop.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ORV--Bitwise-inclusive-OR-reduction-to-scalar-

### Operation

Source operation ID: `SveOperation_svorv_s8`

**Operation**



Return the bitwise inclusive OR of all active elements of `op`.  Return zero if no elements are active.

## svorv[_u16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svorv%5B_u16%5D

### Signature (source notation)

```c
uint16_t svorv[_u16](svbool_t pg, svuint16_t op);
```

### Description

Bitwise inclusive OR reduction to scalar

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / OR

- SME attributes: Not specified by source.

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
  "value": "uint16_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Pg"
  },
  "op": {
    "register": "Zop.H"
  }
}
```

### Result mapping

```json
[
  {
    "Hresult": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
ORV Hresult, Pg, Zop.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ORV--Bitwise-inclusive-OR-reduction-to-scalar-

### Operation

Source operation ID: `SveOperation_svorv_s8`

**Operation**



Return the bitwise inclusive OR of all active elements of `op`.  Return zero if no elements are active.

## svorv[_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svorv%5B_u32%5D

### Signature (source notation)

```c
uint32_t svorv[_u32](svbool_t pg, svuint32_t op);
```

### Description

Bitwise inclusive OR reduction to scalar

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / OR

- SME attributes: Not specified by source.

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
  "value": "uint32_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Pg"
  },
  "op": {
    "register": "Zop.S"
  }
}
```

### Result mapping

```json
[
  {
    "Sresult": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
ORV Sresult, Pg, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ORV--Bitwise-inclusive-OR-reduction-to-scalar-

### Operation

Source operation ID: `SveOperation_svorv_s8`

**Operation**



Return the bitwise inclusive OR of all active elements of `op`.  Return zero if no elements are active.

## svorv[_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svorv%5B_u64%5D

### Signature (source notation)

```c
uint64_t svorv[_u64](svbool_t pg, svuint64_t op);
```

### Description

Bitwise inclusive OR reduction to scalar

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / OR

- SME attributes: Not specified by source.

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
  "value": "uint64_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Pg"
  },
  "op": {
    "register": "Zop.D"
  }
}
```

### Result mapping

```json
[
  {
    "Dresult": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
ORV Dresult, Pg, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ORV--Bitwise-inclusive-OR-reduction-to-scalar-

### Operation

Source operation ID: `SveOperation_svorv_s8`

**Operation**



Return the bitwise inclusive OR of all active elements of `op`.  Return zero if no elements are active.

## svorv[_u8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svorv%5B_u8%5D

### Signature (source notation)

```c
uint8_t svorv[_u8](svbool_t pg, svuint8_t op);
```

### Description

Bitwise inclusive OR reduction to scalar

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / OR

- SME attributes: Not specified by source.

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
  "value": "uint8_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Pg"
  },
  "op": {
    "register": "Zop.B"
  }
}
```

### Result mapping

```json
[
  {
    "Bresult": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
ORV Bresult, Pg, Zop.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ORV--Bitwise-inclusive-OR-reduction-to-scalar-

### Operation

Source operation ID: `SveOperation_svorv_s8`

**Operation**



Return the bitwise inclusive OR of all active elements of `op`.  Return zero if no elements are active.

