# SME / Shift / Right / Vector shift right — Part 2

## svasrd[_n_s64]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svasrd%5B_n_s64%5D_z

### Signature (source notation)

```c
svint64_t svasrd[_n_s64]_z(svbool_t pg, svint64_t op1, uint64_t imm2);
```

### Description

Arithmetic shift right for divide by immediate

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Shift / Right / Vector shift right

- SME attributes: Not specified by source.

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
  "imm2": {
    "minimum": 1,
    "maximum": 64
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
ASRD Zresult.D, Pg/M, Zresult.D, #imm2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ASRD--Arithmetic-shift-right-for-divide-by-immediate--predicated--

### Operation

Source operation ID: `SveOperation_svasrd_n_s8_z`

**Operation**



Return a vector in which each active element *i* contains `op1[i]` divided by 2 to the power `imm2`, with the result rounded towards zero (as for integer division in C).



Set the inactive elements of the result to zero.

## svasrd[_n_s8]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svasrd%5B_n_s8%5D_m

### Signature (source notation)

```c
svint8_t svasrd[_n_s8]_m(svbool_t pg, svint8_t op1, uint64_t imm2);
```

### Description

Arithmetic shift right for divide by immediate

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Shift / Right / Vector shift right

- SME attributes: Not specified by source.

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
  "imm2": {
    "minimum": 1,
    "maximum": 8
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
ASRD Ztied1.B, Pg/M, Ztied1.B, #imm2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ASRD--Arithmetic-shift-right-for-divide-by-immediate--predicated--

When result and op1 are in different registers, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
ASRD Zresult.B, Pg/M, Zresult.B, #imm2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ASRD--Arithmetic-shift-right-for-divide-by-immediate--predicated--

### Operation

Source operation ID: `SveOperation_svasrd_n_s8_m`

**Operation**



Return a vector in which each active element *i* contains `op1[i]` divided by 2 to the power `imm2`, with the result rounded towards zero (as for integer division in C).



Take the inactive elements of the result from the corresponding elements of `op1`.

## svasrd[_n_s8]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svasrd%5B_n_s8%5D_x

### Signature (source notation)

```c
svint8_t svasrd[_n_s8]_x(svbool_t pg, svint8_t op1, uint64_t imm2);
```

### Description

Arithmetic shift right for divide by immediate

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Shift / Right / Vector shift right

- SME attributes: Not specified by source.

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
  "imm2": {
    "minimum": 1,
    "maximum": 8
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
ASRD Ztied1.B, Pg/M, Ztied1.B, #imm2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ASRD--Arithmetic-shift-right-for-divide-by-immediate--predicated--

When result and op1 are in different registers, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
ASRD Zresult.B, Pg/M, Zresult.B, #imm2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ASRD--Arithmetic-shift-right-for-divide-by-immediate--predicated--

### Operation

Source operation ID: `SveOperation_svasrd_n_s8_x`

**Operation**



Return a vector in which each active element *i* contains `op1[i]` divided by 2 to the power `imm2`, with the result rounded towards zero (as for integer division in C).



The inactive elements of the result have arbitrary, undefined values.

## svasrd[_n_s8]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svasrd%5B_n_s8%5D_z

### Signature (source notation)

```c
svint8_t svasrd[_n_s8]_z(svbool_t pg, svint8_t op1, uint64_t imm2);
```

### Description

Arithmetic shift right for divide by immediate

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Shift / Right / Vector shift right

- SME attributes: Not specified by source.

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
  "imm2": {
    "minimum": 1,
    "maximum": 8
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
ASRD Zresult.B, Pg/M, Zresult.B, #imm2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ASRD--Arithmetic-shift-right-for-divide-by-immediate--predicated--

### Operation

Source operation ID: `SveOperation_svasrd_n_s8_z`

**Operation**



Return a vector in which each active element *i* contains `op1[i]` divided by 2 to the power `imm2`, with the result rounded towards zero (as for integer division in C).



Set the inactive elements of the result to zero.

## svlsr[_n_u16]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svlsr%5B_n_u16%5D_m

### Signature (source notation)

```c
svuint16_t svlsr[_n_u16]_m(svbool_t pg, svuint16_t op1, uint16_t op2);
```

### Description

Logical shift right

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Shift / Right / Vector shift right

- SME attributes: Not specified by source.

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

When op2 is in the range [1, 16], this intrinsic can use:

```asm
LSR Ztied1.H, Pg/M, Ztied1.H, #op2  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSR--immediate--predicated---Logical-shift-right-by-immediate--predicated--

The general implementation is:

```asm
LSR Ztied1.H, Pg/M, Ztied1.H, Zop2.H  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSR--vectors---Logical-shift-right-by-vector--predicated--

### Operation

Source operation ID: `SveOperation_svlsr_n_u8_m`

**Operation**



Return a vector in which each active element *i* contains `op1[i]` divided by 2 to the power `op2`, with the result rounded towards zero  (or, equivalently, towards -∞).  All bits of the `op2` value are significant.



Take the inactive elements of the result from the corresponding elements of `op1`.



**[1]** If instead `result` is in a different register from the inputs, the compiler can add a preceding [MOVPRFX (unpredicated)](https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--) instruction

## svlsr[_n_u16]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svlsr%5B_n_u16%5D_x

### Signature (source notation)

```c
svuint16_t svlsr[_n_u16]_x(svbool_t pg, svuint16_t op1, uint16_t op2);
```

### Description

Logical shift right

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Shift / Right / Vector shift right

- SME attributes: Not specified by source.

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

When op2 is in the range [1, 16], this intrinsic can use:

```asm
LSR Zresult.H, Zop1.H, #op2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSR--immediate--unpredicated---Logical-shift-right-by-immediate--unpredicated--

When result and op1 are in the same register, this intrinsic can use:

```asm
LSR Ztied1.H, Pg/M, Ztied1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSR--vectors---Logical-shift-right-by-vector--predicated--

When result and op2 are in the same register, this intrinsic can use:

```asm
LSRR Ztied2.H, Pg/M, Ztied2.H, Zop1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSRR--Reversed-logical-shift-right-by-vector--predicated--

When result is in a different register from the inputs, the general implementation is:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
LSR Zresult.H, Pg/M, Zresult.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSR--vectors---Logical-shift-right-by-vector--predicated--

### Operation

Source operation ID: `SveOperation_svlsr_n_u8_x`

**Operation**



Return a vector in which each active element *i* contains `op1[i]` divided by 2 to the power `op2`, with the result rounded towards zero  (or, equivalently, towards -∞).  All bits of the `op2` value are significant.



The inactive elements of the result have arbitrary, undefined values.

## svlsr[_n_u16]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svlsr%5B_n_u16%5D_z

### Signature (source notation)

```c
svuint16_t svlsr[_n_u16]_z(svbool_t pg, svuint16_t op1, uint16_t op2);
```

### Description

Logical shift right

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Shift / Right / Vector shift right

- SME attributes: Not specified by source.

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

When op2 is in the range [1, 16], this intrinsic can use:

```asm
MOVPRFX Zresult.H, Pg/Z, Zop1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
LSR Zresult.H, Pg/M, Zresult.H, #op2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSR--immediate--predicated---Logical-shift-right-by-immediate--predicated--

When result is in a different register from op2, this intrinsic can use:

```asm
MOVPRFX Zresult.H, Pg/Z, Zop1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
LSR Zresult.H, Pg/M, Zresult.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSR--vectors---Logical-shift-right-by-vector--predicated--

When result is in a different register from op1, this intrinsic can use:

```asm
MOVPRFX Zresult.H, Pg/Z, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
LSRR Zresult.H, Pg/M, Zresult.H, Zop1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSRR--Reversed-logical-shift-right-by-vector--predicated--

### Operation

Source operation ID: `SveOperation_svlsr_n_u8_z`

**Operation**



Return a vector in which each active element *i* contains `op1[i]` divided by 2 to the power `op2`, with the result rounded towards zero  (or, equivalently, towards -∞).  All bits of the `op2` value are significant.



Set the inactive elements of the result to zero.

## svlsr[_n_u32]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svlsr%5B_n_u32%5D_m

### Signature (source notation)

```c
svuint32_t svlsr[_n_u32]_m(svbool_t pg, svuint32_t op1, uint32_t op2);
```

### Description

Logical shift right

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Shift / Right / Vector shift right

- SME attributes: Not specified by source.

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

When op2 is in the range [1, 32], this intrinsic can use:

```asm
LSR Ztied1.S, Pg/M, Ztied1.S, #op2  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSR--immediate--predicated---Logical-shift-right-by-immediate--predicated--

The general implementation is:

```asm
LSR Ztied1.S, Pg/M, Ztied1.S, Zop2.S  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSR--vectors---Logical-shift-right-by-vector--predicated--

### Operation

Source operation ID: `SveOperation_svlsr_n_u8_m`

**Operation**



Return a vector in which each active element *i* contains `op1[i]` divided by 2 to the power `op2`, with the result rounded towards zero  (or, equivalently, towards -∞).  All bits of the `op2` value are significant.



Take the inactive elements of the result from the corresponding elements of `op1`.



**[1]** If instead `result` is in a different register from the inputs, the compiler can add a preceding [MOVPRFX (unpredicated)](https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--) instruction

## svlsr[_n_u32]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svlsr%5B_n_u32%5D_x

### Signature (source notation)

```c
svuint32_t svlsr[_n_u32]_x(svbool_t pg, svuint32_t op1, uint32_t op2);
```

### Description

Logical shift right

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Shift / Right / Vector shift right

- SME attributes: Not specified by source.

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

When op2 is in the range [1, 32], this intrinsic can use:

```asm
LSR Zresult.S, Zop1.S, #op2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSR--immediate--unpredicated---Logical-shift-right-by-immediate--unpredicated--

When result and op1 are in the same register, this intrinsic can use:

```asm
LSR Ztied1.S, Pg/M, Ztied1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSR--vectors---Logical-shift-right-by-vector--predicated--

When result and op2 are in the same register, this intrinsic can use:

```asm
LSRR Ztied2.S, Pg/M, Ztied2.S, Zop1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSRR--Reversed-logical-shift-right-by-vector--predicated--

When result is in a different register from the inputs, the general implementation is:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
LSR Zresult.S, Pg/M, Zresult.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSR--vectors---Logical-shift-right-by-vector--predicated--

### Operation

Source operation ID: `SveOperation_svlsr_n_u8_x`

**Operation**



Return a vector in which each active element *i* contains `op1[i]` divided by 2 to the power `op2`, with the result rounded towards zero  (or, equivalently, towards -∞).  All bits of the `op2` value are significant.



The inactive elements of the result have arbitrary, undefined values.

## svlsr[_n_u32]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svlsr%5B_n_u32%5D_z

### Signature (source notation)

```c
svuint32_t svlsr[_n_u32]_z(svbool_t pg, svuint32_t op1, uint32_t op2);
```

### Description

Logical shift right

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Shift / Right / Vector shift right

- SME attributes: Not specified by source.

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

When op2 is in the range [1, 32], this intrinsic can use:

```asm
MOVPRFX Zresult.S, Pg/Z, Zop1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
LSR Zresult.S, Pg/M, Zresult.S, #op2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSR--immediate--predicated---Logical-shift-right-by-immediate--predicated--

When result is in a different register from op2, this intrinsic can use:

```asm
MOVPRFX Zresult.S, Pg/Z, Zop1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
LSR Zresult.S, Pg/M, Zresult.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSR--vectors---Logical-shift-right-by-vector--predicated--

When result is in a different register from op1, this intrinsic can use:

```asm
MOVPRFX Zresult.S, Pg/Z, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
LSRR Zresult.S, Pg/M, Zresult.S, Zop1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSRR--Reversed-logical-shift-right-by-vector--predicated--

### Operation

Source operation ID: `SveOperation_svlsr_n_u8_z`

**Operation**



Return a vector in which each active element *i* contains `op1[i]` divided by 2 to the power `op2`, with the result rounded towards zero  (or, equivalently, towards -∞).  All bits of the `op2` value are significant.



Set the inactive elements of the result to zero.

## svlsr[_n_u64]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svlsr%5B_n_u64%5D_m

### Signature (source notation)

```c
svuint64_t svlsr[_n_u64]_m(svbool_t pg, svuint64_t op1, uint64_t op2);
```

### Description

Logical shift right

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Shift / Right / Vector shift right

- SME attributes: Not specified by source.

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

When op2 is in the range [1, 64], this intrinsic can use:

```asm
LSR Ztied1.D, Pg/M, Ztied1.D, #op2  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSR--immediate--predicated---Logical-shift-right-by-immediate--predicated--

The general implementation is:

```asm
LSR Ztied1.D, Pg/M, Ztied1.D, Zop2.D  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSR--vectors---Logical-shift-right-by-vector--predicated--

### Operation

Source operation ID: `SveOperation_svlsr_n_u8_m`

**Operation**



Return a vector in which each active element *i* contains `op1[i]` divided by 2 to the power `op2`, with the result rounded towards zero  (or, equivalently, towards -∞).  All bits of the `op2` value are significant.



Take the inactive elements of the result from the corresponding elements of `op1`.



**[1]** If instead `result` is in a different register from the inputs, the compiler can add a preceding [MOVPRFX (unpredicated)](https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--) instruction

## svlsr[_n_u64]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svlsr%5B_n_u64%5D_x

### Signature (source notation)

```c
svuint64_t svlsr[_n_u64]_x(svbool_t pg, svuint64_t op1, uint64_t op2);
```

### Description

Logical shift right

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Shift / Right / Vector shift right

- SME attributes: Not specified by source.

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

When op2 is in the range [1, 64], this intrinsic can use:

```asm
LSR Zresult.D, Zop1.D, #op2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSR--immediate--unpredicated---Logical-shift-right-by-immediate--unpredicated--

When result and op1 are in the same register, this intrinsic can use:

```asm
LSR Ztied1.D, Pg/M, Ztied1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSR--vectors---Logical-shift-right-by-vector--predicated--

When result and op2 are in the same register, this intrinsic can use:

```asm
LSRR Ztied2.D, Pg/M, Ztied2.D, Zop1.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSRR--Reversed-logical-shift-right-by-vector--predicated--

When result is in a different register from the inputs, the general implementation is:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
LSR Zresult.D, Pg/M, Zresult.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSR--vectors---Logical-shift-right-by-vector--predicated--

### Operation

Source operation ID: `SveOperation_svlsr_n_u8_x`

**Operation**



Return a vector in which each active element *i* contains `op1[i]` divided by 2 to the power `op2`, with the result rounded towards zero  (or, equivalently, towards -∞).  All bits of the `op2` value are significant.



The inactive elements of the result have arbitrary, undefined values.

## svlsr[_n_u64]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svlsr%5B_n_u64%5D_z

### Signature (source notation)

```c
svuint64_t svlsr[_n_u64]_z(svbool_t pg, svuint64_t op1, uint64_t op2);
```

### Description

Logical shift right

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Shift / Right / Vector shift right

- SME attributes: Not specified by source.

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

When op2 is in the range [1, 64], this intrinsic can use:

```asm
MOVPRFX Zresult.D, Pg/Z, Zop1.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
LSR Zresult.D, Pg/M, Zresult.D, #op2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSR--immediate--predicated---Logical-shift-right-by-immediate--predicated--

When result is in a different register from op2, this intrinsic can use:

```asm
MOVPRFX Zresult.D, Pg/Z, Zop1.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
LSR Zresult.D, Pg/M, Zresult.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSR--vectors---Logical-shift-right-by-vector--predicated--

When result is in a different register from op1, this intrinsic can use:

```asm
MOVPRFX Zresult.D, Pg/Z, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
LSRR Zresult.D, Pg/M, Zresult.D, Zop1.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSRR--Reversed-logical-shift-right-by-vector--predicated--

### Operation

Source operation ID: `SveOperation_svlsr_n_u8_z`

**Operation**



Return a vector in which each active element *i* contains `op1[i]` divided by 2 to the power `op2`, with the result rounded towards zero  (or, equivalently, towards -∞).  All bits of the `op2` value are significant.



Set the inactive elements of the result to zero.

## svlsr[_n_u8]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svlsr%5B_n_u8%5D_m

### Signature (source notation)

```c
svuint8_t svlsr[_n_u8]_m(svbool_t pg, svuint8_t op1, uint8_t op2);
```

### Description

Logical shift right

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Shift / Right / Vector shift right

- SME attributes: Not specified by source.

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

When op2 is in the range [1, 8], this intrinsic can use:

```asm
LSR Ztied1.B, Pg/M, Ztied1.B, #op2  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSR--immediate--predicated---Logical-shift-right-by-immediate--predicated--

The general implementation is:

```asm
LSR Ztied1.B, Pg/M, Ztied1.B, Zop2.B  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSR--vectors---Logical-shift-right-by-vector--predicated--

### Operation

Source operation ID: `SveOperation_svlsr_n_u8_m`

**Operation**



Return a vector in which each active element *i* contains `op1[i]` divided by 2 to the power `op2`, with the result rounded towards zero  (or, equivalently, towards -∞).  All bits of the `op2` value are significant.



Take the inactive elements of the result from the corresponding elements of `op1`.



**[1]** If instead `result` is in a different register from the inputs, the compiler can add a preceding [MOVPRFX (unpredicated)](https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--) instruction

## svlsr[_n_u8]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svlsr%5B_n_u8%5D_x

### Signature (source notation)

```c
svuint8_t svlsr[_n_u8]_x(svbool_t pg, svuint8_t op1, uint8_t op2);
```

### Description

Logical shift right

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Shift / Right / Vector shift right

- SME attributes: Not specified by source.

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

When op2 is in the range [1, 8], this intrinsic can use:

```asm
LSR Zresult.B, Zop1.B, #op2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSR--immediate--unpredicated---Logical-shift-right-by-immediate--unpredicated--

When result and op1 are in the same register, this intrinsic can use:

```asm
LSR Ztied1.B, Pg/M, Ztied1.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSR--vectors---Logical-shift-right-by-vector--predicated--

When result and op2 are in the same register, this intrinsic can use:

```asm
LSRR Ztied2.B, Pg/M, Ztied2.B, Zop1.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSRR--Reversed-logical-shift-right-by-vector--predicated--

When result is in a different register from the inputs, the general implementation is:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
LSR Zresult.B, Pg/M, Zresult.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSR--vectors---Logical-shift-right-by-vector--predicated--

### Operation

Source operation ID: `SveOperation_svlsr_n_u8_x`

**Operation**



Return a vector in which each active element *i* contains `op1[i]` divided by 2 to the power `op2`, with the result rounded towards zero  (or, equivalently, towards -∞).  All bits of the `op2` value are significant.



The inactive elements of the result have arbitrary, undefined values.

## svlsr[_n_u8]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svlsr%5B_n_u8%5D_z

### Signature (source notation)

```c
svuint8_t svlsr[_n_u8]_z(svbool_t pg, svuint8_t op1, uint8_t op2);
```

### Description

Logical shift right

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Shift / Right / Vector shift right

- SME attributes: Not specified by source.

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

When op2 is in the range [1, 8], this intrinsic can use:

```asm
MOVPRFX Zresult.B, Pg/Z, Zop1.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
LSR Zresult.B, Pg/M, Zresult.B, #op2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSR--immediate--predicated---Logical-shift-right-by-immediate--predicated--

When result is in a different register from op2, this intrinsic can use:

```asm
MOVPRFX Zresult.B, Pg/Z, Zop1.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
LSR Zresult.B, Pg/M, Zresult.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSR--vectors---Logical-shift-right-by-vector--predicated--

When result is in a different register from op1, this intrinsic can use:

```asm
MOVPRFX Zresult.B, Pg/Z, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
LSRR Zresult.B, Pg/M, Zresult.B, Zop1.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSRR--Reversed-logical-shift-right-by-vector--predicated--

### Operation

Source operation ID: `SveOperation_svlsr_n_u8_z`

**Operation**



Return a vector in which each active element *i* contains `op1[i]` divided by 2 to the power `op2`, with the result rounded towards zero  (or, equivalently, towards -∞).  All bits of the `op2` value are significant.



Set the inactive elements of the result to zero.

## svlsr[_u16]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svlsr%5B_u16%5D_m

### Signature (source notation)

```c
svuint16_t svlsr[_u16]_m(svbool_t pg, svuint16_t op1, svuint16_t op2);
```

### Description

Logical shift right

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Shift / Right / Vector shift right

- SME attributes: Not specified by source.

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
LSR Ztied1.H, Pg/M, Ztied1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSR--vectors---Logical-shift-right-by-vector--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
LSR Zresult.H, Pg/M, Zresult.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSR--vectors---Logical-shift-right-by-vector--predicated--

### Operation

Source operation ID: `SveOperation_svlsr_u8_m`

**Operation**



Return a vector in which each active element *i* contains `op1[i]` divided by 2 to the power `op2[i]`, with the result rounded towards zero  (or, equivalently, towards -∞).  All bits of the `op2` value are significant.



Take the inactive elements of the result from the corresponding elements of `op1`.

## svlsr[_u16]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svlsr%5B_u16%5D_x

### Signature (source notation)

```c
svuint16_t svlsr[_u16]_x(svbool_t pg, svuint16_t op1, svuint16_t op2);
```

### Description

Logical shift right

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Shift / Right / Vector shift right

- SME attributes: Not specified by source.

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
LSR Ztied1.H, Pg/M, Ztied1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSR--vectors---Logical-shift-right-by-vector--predicated--

When result and op2 are in the same register, this intrinsic compiles to:

```asm
LSRR Ztied2.H, Pg/M, Ztied2.H, Zop1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSRR--Reversed-logical-shift-right-by-vector--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
LSR Zresult.H, Pg/M, Zresult.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSR--vectors---Logical-shift-right-by-vector--predicated--

### Operation

Source operation ID: `SveOperation_svlsr_u8_x`

**Operation**



Return a vector in which each active element *i* contains `op1[i]` divided by 2 to the power `op2[i]`, with the result rounded towards zero  (or, equivalently, towards -∞).  All bits of the `op2` value are significant.



The inactive elements of the result have arbitrary, undefined values.

## svlsr[_u16]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svlsr%5B_u16%5D_z

### Signature (source notation)

```c
svuint16_t svlsr[_u16]_z(svbool_t pg, svuint16_t op1, svuint16_t op2);
```

### Description

Logical shift right

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Shift / Right / Vector shift right

- SME attributes: Not specified by source.

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
LSR Zresult.H, Pg/M, Zresult.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSR--vectors---Logical-shift-right-by-vector--predicated--

When result is in a different register from op1, this intrinsic can use:

```asm
MOVPRFX Zresult.H, Pg/Z, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
LSRR Zresult.H, Pg/M, Zresult.H, Zop1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSRR--Reversed-logical-shift-right-by-vector--predicated--

### Operation

Source operation ID: `SveOperation_svlsr_u8_z`

**Operation**



Return a vector in which each active element *i* contains `op1[i]` divided by 2 to the power `op2[i]`, with the result rounded towards zero  (or, equivalently, towards -∞).  All bits of the `op2` value are significant.



Set the inactive elements of the result to zero.

## svlsr[_u32]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svlsr%5B_u32%5D_m

### Signature (source notation)

```c
svuint32_t svlsr[_u32]_m(svbool_t pg, svuint32_t op1, svuint32_t op2);
```

### Description

Logical shift right

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Shift / Right / Vector shift right

- SME attributes: Not specified by source.

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
LSR Ztied1.S, Pg/M, Ztied1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSR--vectors---Logical-shift-right-by-vector--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
LSR Zresult.S, Pg/M, Zresult.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSR--vectors---Logical-shift-right-by-vector--predicated--

### Operation

Source operation ID: `SveOperation_svlsr_u8_m`

**Operation**



Return a vector in which each active element *i* contains `op1[i]` divided by 2 to the power `op2[i]`, with the result rounded towards zero  (or, equivalently, towards -∞).  All bits of the `op2` value are significant.



Take the inactive elements of the result from the corresponding elements of `op1`.

## svlsr[_u32]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svlsr%5B_u32%5D_x

### Signature (source notation)

```c
svuint32_t svlsr[_u32]_x(svbool_t pg, svuint32_t op1, svuint32_t op2);
```

### Description

Logical shift right

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Shift / Right / Vector shift right

- SME attributes: Not specified by source.

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
LSR Ztied1.S, Pg/M, Ztied1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSR--vectors---Logical-shift-right-by-vector--predicated--

When result and op2 are in the same register, this intrinsic compiles to:

```asm
LSRR Ztied2.S, Pg/M, Ztied2.S, Zop1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSRR--Reversed-logical-shift-right-by-vector--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
LSR Zresult.S, Pg/M, Zresult.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSR--vectors---Logical-shift-right-by-vector--predicated--

### Operation

Source operation ID: `SveOperation_svlsr_u8_x`

**Operation**



Return a vector in which each active element *i* contains `op1[i]` divided by 2 to the power `op2[i]`, with the result rounded towards zero  (or, equivalently, towards -∞).  All bits of the `op2` value are significant.



The inactive elements of the result have arbitrary, undefined values.

## svlsr[_u32]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svlsr%5B_u32%5D_z

### Signature (source notation)

```c
svuint32_t svlsr[_u32]_z(svbool_t pg, svuint32_t op1, svuint32_t op2);
```

### Description

Logical shift right

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Shift / Right / Vector shift right

- SME attributes: Not specified by source.

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
LSR Zresult.S, Pg/M, Zresult.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSR--vectors---Logical-shift-right-by-vector--predicated--

When result is in a different register from op1, this intrinsic can use:

```asm
MOVPRFX Zresult.S, Pg/Z, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
LSRR Zresult.S, Pg/M, Zresult.S, Zop1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSRR--Reversed-logical-shift-right-by-vector--predicated--

### Operation

Source operation ID: `SveOperation_svlsr_u8_z`

**Operation**



Return a vector in which each active element *i* contains `op1[i]` divided by 2 to the power `op2[i]`, with the result rounded towards zero  (or, equivalently, towards -∞).  All bits of the `op2` value are significant.



Set the inactive elements of the result to zero.

## svlsr[_u64]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svlsr%5B_u64%5D_m

### Signature (source notation)

```c
svuint64_t svlsr[_u64]_m(svbool_t pg, svuint64_t op1, svuint64_t op2);
```

### Description

Logical shift right

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Shift / Right / Vector shift right

- SME attributes: Not specified by source.

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
LSR Ztied1.D, Pg/M, Ztied1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSR--vectors---Logical-shift-right-by-vector--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
LSR Zresult.D, Pg/M, Zresult.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSR--vectors---Logical-shift-right-by-vector--predicated--

### Operation

Source operation ID: `SveOperation_svlsr_u8_m`

**Operation**



Return a vector in which each active element *i* contains `op1[i]` divided by 2 to the power `op2[i]`, with the result rounded towards zero  (or, equivalently, towards -∞).  All bits of the `op2` value are significant.



Take the inactive elements of the result from the corresponding elements of `op1`.

## svlsr[_u64]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svlsr%5B_u64%5D_x

### Signature (source notation)

```c
svuint64_t svlsr[_u64]_x(svbool_t pg, svuint64_t op1, svuint64_t op2);
```

### Description

Logical shift right

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Shift / Right / Vector shift right

- SME attributes: Not specified by source.

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
LSR Ztied1.D, Pg/M, Ztied1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSR--vectors---Logical-shift-right-by-vector--predicated--

When result and op2 are in the same register, this intrinsic compiles to:

```asm
LSRR Ztied2.D, Pg/M, Ztied2.D, Zop1.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSRR--Reversed-logical-shift-right-by-vector--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
LSR Zresult.D, Pg/M, Zresult.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSR--vectors---Logical-shift-right-by-vector--predicated--

### Operation

Source operation ID: `SveOperation_svlsr_u8_x`

**Operation**



Return a vector in which each active element *i* contains `op1[i]` divided by 2 to the power `op2[i]`, with the result rounded towards zero  (or, equivalently, towards -∞).  All bits of the `op2` value are significant.



The inactive elements of the result have arbitrary, undefined values.

## svlsr[_u64]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svlsr%5B_u64%5D_z

### Signature (source notation)

```c
svuint64_t svlsr[_u64]_z(svbool_t pg, svuint64_t op1, svuint64_t op2);
```

### Description

Logical shift right

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Shift / Right / Vector shift right

- SME attributes: Not specified by source.

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
LSR Zresult.D, Pg/M, Zresult.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSR--vectors---Logical-shift-right-by-vector--predicated--

When result is in a different register from op1, this intrinsic can use:

```asm
MOVPRFX Zresult.D, Pg/Z, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
LSRR Zresult.D, Pg/M, Zresult.D, Zop1.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSRR--Reversed-logical-shift-right-by-vector--predicated--

### Operation

Source operation ID: `SveOperation_svlsr_u8_z`

**Operation**



Return a vector in which each active element *i* contains `op1[i]` divided by 2 to the power `op2[i]`, with the result rounded towards zero  (or, equivalently, towards -∞).  All bits of the `op2` value are significant.



Set the inactive elements of the result to zero.

## svlsr[_u8]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svlsr%5B_u8%5D_m

### Signature (source notation)

```c
svuint8_t svlsr[_u8]_m(svbool_t pg, svuint8_t op1, svuint8_t op2);
```

### Description

Logical shift right

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Shift / Right / Vector shift right

- SME attributes: Not specified by source.

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
LSR Ztied1.B, Pg/M, Ztied1.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSR--vectors---Logical-shift-right-by-vector--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
LSR Zresult.B, Pg/M, Zresult.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSR--vectors---Logical-shift-right-by-vector--predicated--

### Operation

Source operation ID: `SveOperation_svlsr_u8_m`

**Operation**



Return a vector in which each active element *i* contains `op1[i]` divided by 2 to the power `op2[i]`, with the result rounded towards zero  (or, equivalently, towards -∞).  All bits of the `op2` value are significant.



Take the inactive elements of the result from the corresponding elements of `op1`.

## svlsr[_u8]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svlsr%5B_u8%5D_x

### Signature (source notation)

```c
svuint8_t svlsr[_u8]_x(svbool_t pg, svuint8_t op1, svuint8_t op2);
```

### Description

Logical shift right

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Shift / Right / Vector shift right

- SME attributes: Not specified by source.

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
LSR Ztied1.B, Pg/M, Ztied1.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSR--vectors---Logical-shift-right-by-vector--predicated--

When result and op2 are in the same register, this intrinsic compiles to:

```asm
LSRR Ztied2.B, Pg/M, Ztied2.B, Zop1.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSRR--Reversed-logical-shift-right-by-vector--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
LSR Zresult.B, Pg/M, Zresult.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSR--vectors---Logical-shift-right-by-vector--predicated--

### Operation

Source operation ID: `SveOperation_svlsr_u8_x`

**Operation**



Return a vector in which each active element *i* contains `op1[i]` divided by 2 to the power `op2[i]`, with the result rounded towards zero  (or, equivalently, towards -∞).  All bits of the `op2` value are significant.



The inactive elements of the result have arbitrary, undefined values.

## svlsr[_u8]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svlsr%5B_u8%5D_z

### Signature (source notation)

```c
svuint8_t svlsr[_u8]_z(svbool_t pg, svuint8_t op1, svuint8_t op2);
```

### Description

Logical shift right

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Shift / Right / Vector shift right

- SME attributes: Not specified by source.

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
LSR Zresult.B, Pg/M, Zresult.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSR--vectors---Logical-shift-right-by-vector--predicated--

When result is in a different register from op1, this intrinsic can use:

```asm
MOVPRFX Zresult.B, Pg/Z, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
LSRR Zresult.B, Pg/M, Zresult.B, Zop1.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSRR--Reversed-logical-shift-right-by-vector--predicated--

### Operation

Source operation ID: `SveOperation_svlsr_u8_z`

**Operation**



Return a vector in which each active element *i* contains `op1[i]` divided by 2 to the power `op2[i]`, with the result rounded towards zero  (or, equivalently, towards -∞).  All bits of the `op2` value are significant.



Set the inactive elements of the result to zero.

## svlsr_wide[_n_u16]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svlsr_wide%5B_n_u16%5D_m

### Signature (source notation)

```c
svuint16_t svlsr_wide[_n_u16]_m(svbool_t pg, svuint16_t op1, uint64_t op2);
```

### Description

Logical shift right

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Shift / Right / Vector shift right

- SME attributes: Not specified by source.

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

When op2 is in the range [1, 16], this intrinsic can use:

```asm
LSR Ztied1.H, Pg/M, Ztied1.H, #op2  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSR--immediate--predicated---Logical-shift-right-by-immediate--predicated--

The general implementation is:

```asm
LSR Ztied1.H, Pg/M, Ztied1.H, Zop2.D  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSR--wide-elements--predicated---Logical-shift-right-by-64-bit-wide-elements--predicated--

### Operation

Source operation ID: `SveOperation_svlsr_n_u8_m`

**Operation**



Return a vector in which each active element *i* contains `op1[i]` divided by 2 to the power `op2`, with the result rounded towards zero  (or, equivalently, towards -∞).  All bits of the `op2` value are significant.



Take the inactive elements of the result from the corresponding elements of `op1`.



**[1]** If instead `result` is in a different register from the inputs, the compiler can add a preceding [MOVPRFX (unpredicated)](https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--) instruction

## svlsr_wide[_n_u16]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svlsr_wide%5B_n_u16%5D_x

### Signature (source notation)

```c
svuint16_t svlsr_wide[_n_u16]_x(svbool_t pg, svuint16_t op1, uint64_t op2);
```

### Description

Logical shift right

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Shift / Right / Vector shift right

- SME attributes: Not specified by source.

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

When op2 is in the range [1, 16], this intrinsic can use:

```asm
LSR Zresult.H, Zop1.H, #op2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSR--immediate--unpredicated---Logical-shift-right-by-immediate--unpredicated--

When result and op1 are in the same register, this intrinsic can use:

```asm
LSR Ztied1.H, Pg/M, Ztied1.H, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSR--wide-elements--predicated---Logical-shift-right-by-64-bit-wide-elements--predicated--

The general implementation is:

```asm
LSR Zresult.H, Zop1.H, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSR--wide-elements--unpredicated---Logical-shift-right-by-64-bit-wide-elements--unpredicated--

### Operation

Source operation ID: `SveOperation_svlsr_n_u8_x`

**Operation**



Return a vector in which each active element *i* contains `op1[i]` divided by 2 to the power `op2`, with the result rounded towards zero  (or, equivalently, towards -∞).  All bits of the `op2` value are significant.



The inactive elements of the result have arbitrary, undefined values.

## svlsr_wide[_n_u16]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svlsr_wide%5B_n_u16%5D_z

### Signature (source notation)

```c
svuint16_t svlsr_wide[_n_u16]_z(svbool_t pg, svuint16_t op1, uint64_t op2);
```

### Description

Logical shift right

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Shift / Right / Vector shift right

- SME attributes: Not specified by source.

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

When op2 is in the range [1, 16], this intrinsic can use:

```asm
MOVPRFX Zresult.H, Pg/Z, Zop1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
LSR Zresult.H, Pg/M, Zresult.H, #op2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSR--immediate--predicated---Logical-shift-right-by-immediate--predicated--

The general implementation is:

```asm
MOVPRFX Zresult.H, Pg/Z, Zop1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
LSR Zresult.H, Pg/M, Zresult.H, Zop2.D  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSR--wide-elements--predicated---Logical-shift-right-by-64-bit-wide-elements--predicated--

### Operation

Source operation ID: `SveOperation_svlsr_wide_n_u8_z`

**Operation**



Return a vector in which each active element *i* contains `op1[i]` divided by 2 to the power `op2`, with the result rounded towards zero  (or, equivalently, towards -∞).  All bits of the `op2` value are significant.



Set the inactive elements of the result to zero.



**[1]** Note that `result` must be in a different register from `op2`

## svlsr_wide[_n_u32]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svlsr_wide%5B_n_u32%5D_m

### Signature (source notation)

```c
svuint32_t svlsr_wide[_n_u32]_m(svbool_t pg, svuint32_t op1, uint64_t op2);
```

### Description

Logical shift right

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Shift / Right / Vector shift right

- SME attributes: Not specified by source.

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

When op2 is in the range [1, 32], this intrinsic can use:

```asm
LSR Ztied1.S, Pg/M, Ztied1.S, #op2  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSR--immediate--predicated---Logical-shift-right-by-immediate--predicated--

The general implementation is:

```asm
LSR Ztied1.S, Pg/M, Ztied1.S, Zop2.D  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSR--wide-elements--predicated---Logical-shift-right-by-64-bit-wide-elements--predicated--

### Operation

Source operation ID: `SveOperation_svlsr_n_u8_m`

**Operation**



Return a vector in which each active element *i* contains `op1[i]` divided by 2 to the power `op2`, with the result rounded towards zero  (or, equivalently, towards -∞).  All bits of the `op2` value are significant.



Take the inactive elements of the result from the corresponding elements of `op1`.



**[1]** If instead `result` is in a different register from the inputs, the compiler can add a preceding [MOVPRFX (unpredicated)](https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--) instruction

## svlsr_wide[_n_u32]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svlsr_wide%5B_n_u32%5D_x

### Signature (source notation)

```c
svuint32_t svlsr_wide[_n_u32]_x(svbool_t pg, svuint32_t op1, uint64_t op2);
```

### Description

Logical shift right

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Shift / Right / Vector shift right

- SME attributes: Not specified by source.

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

When op2 is in the range [1, 32], this intrinsic can use:

```asm
LSR Zresult.S, Zop1.S, #op2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSR--immediate--unpredicated---Logical-shift-right-by-immediate--unpredicated--

When result and op1 are in the same register, this intrinsic can use:

```asm
LSR Ztied1.S, Pg/M, Ztied1.S, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSR--wide-elements--predicated---Logical-shift-right-by-64-bit-wide-elements--predicated--

The general implementation is:

```asm
LSR Zresult.S, Zop1.S, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSR--wide-elements--unpredicated---Logical-shift-right-by-64-bit-wide-elements--unpredicated--

### Operation

Source operation ID: `SveOperation_svlsr_n_u8_x`

**Operation**



Return a vector in which each active element *i* contains `op1[i]` divided by 2 to the power `op2`, with the result rounded towards zero  (or, equivalently, towards -∞).  All bits of the `op2` value are significant.



The inactive elements of the result have arbitrary, undefined values.

## svlsr_wide[_n_u32]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svlsr_wide%5B_n_u32%5D_z

### Signature (source notation)

```c
svuint32_t svlsr_wide[_n_u32]_z(svbool_t pg, svuint32_t op1, uint64_t op2);
```

### Description

Logical shift right

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Shift / Right / Vector shift right

- SME attributes: Not specified by source.

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

When op2 is in the range [1, 32], this intrinsic can use:

```asm
MOVPRFX Zresult.S, Pg/Z, Zop1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
LSR Zresult.S, Pg/M, Zresult.S, #op2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSR--immediate--predicated---Logical-shift-right-by-immediate--predicated--

The general implementation is:

```asm
MOVPRFX Zresult.S, Pg/Z, Zop1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
LSR Zresult.S, Pg/M, Zresult.S, Zop2.D  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSR--wide-elements--predicated---Logical-shift-right-by-64-bit-wide-elements--predicated--

### Operation

Source operation ID: `SveOperation_svlsr_wide_n_u8_z`

**Operation**



Return a vector in which each active element *i* contains `op1[i]` divided by 2 to the power `op2`, with the result rounded towards zero  (or, equivalently, towards -∞).  All bits of the `op2` value are significant.



Set the inactive elements of the result to zero.



**[1]** Note that `result` must be in a different register from `op2`

## svlsr_wide[_n_u8]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svlsr_wide%5B_n_u8%5D_m

### Signature (source notation)

```c
svuint8_t svlsr_wide[_n_u8]_m(svbool_t pg, svuint8_t op1, uint64_t op2);
```

### Description

Logical shift right

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Shift / Right / Vector shift right

- SME attributes: Not specified by source.

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

When op2 is in the range [1, 8], this intrinsic can use:

```asm
LSR Ztied1.B, Pg/M, Ztied1.B, #op2  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSR--immediate--predicated---Logical-shift-right-by-immediate--predicated--

The general implementation is:

```asm
LSR Ztied1.B, Pg/M, Ztied1.B, Zop2.D  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSR--wide-elements--predicated---Logical-shift-right-by-64-bit-wide-elements--predicated--

### Operation

Source operation ID: `SveOperation_svlsr_n_u8_m`

**Operation**



Return a vector in which each active element *i* contains `op1[i]` divided by 2 to the power `op2`, with the result rounded towards zero  (or, equivalently, towards -∞).  All bits of the `op2` value are significant.



Take the inactive elements of the result from the corresponding elements of `op1`.



**[1]** If instead `result` is in a different register from the inputs, the compiler can add a preceding [MOVPRFX (unpredicated)](https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--) instruction

## svlsr_wide[_n_u8]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svlsr_wide%5B_n_u8%5D_x

### Signature (source notation)

```c
svuint8_t svlsr_wide[_n_u8]_x(svbool_t pg, svuint8_t op1, uint64_t op2);
```

### Description

Logical shift right

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Shift / Right / Vector shift right

- SME attributes: Not specified by source.

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

When op2 is in the range [1, 8], this intrinsic can use:

```asm
LSR Zresult.B, Zop1.B, #op2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSR--immediate--unpredicated---Logical-shift-right-by-immediate--unpredicated--

When result and op1 are in the same register, this intrinsic can use:

```asm
LSR Ztied1.B, Pg/M, Ztied1.B, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSR--wide-elements--predicated---Logical-shift-right-by-64-bit-wide-elements--predicated--

The general implementation is:

```asm
LSR Zresult.B, Zop1.B, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSR--wide-elements--unpredicated---Logical-shift-right-by-64-bit-wide-elements--unpredicated--

### Operation

Source operation ID: `SveOperation_svlsr_n_u8_x`

**Operation**



Return a vector in which each active element *i* contains `op1[i]` divided by 2 to the power `op2`, with the result rounded towards zero  (or, equivalently, towards -∞).  All bits of the `op2` value are significant.



The inactive elements of the result have arbitrary, undefined values.

## svlsr_wide[_n_u8]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svlsr_wide%5B_n_u8%5D_z

### Signature (source notation)

```c
svuint8_t svlsr_wide[_n_u8]_z(svbool_t pg, svuint8_t op1, uint64_t op2);
```

### Description

Logical shift right

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Shift / Right / Vector shift right

- SME attributes: Not specified by source.

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

When op2 is in the range [1, 8], this intrinsic can use:

```asm
MOVPRFX Zresult.B, Pg/Z, Zop1.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
LSR Zresult.B, Pg/M, Zresult.B, #op2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSR--immediate--predicated---Logical-shift-right-by-immediate--predicated--

The general implementation is:

```asm
MOVPRFX Zresult.B, Pg/Z, Zop1.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
LSR Zresult.B, Pg/M, Zresult.B, Zop2.D  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSR--wide-elements--predicated---Logical-shift-right-by-64-bit-wide-elements--predicated--

### Operation

Source operation ID: `SveOperation_svlsr_wide_n_u8_z`

**Operation**



Return a vector in which each active element *i* contains `op1[i]` divided by 2 to the power `op2`, with the result rounded towards zero  (or, equivalently, towards -∞).  All bits of the `op2` value are significant.



Set the inactive elements of the result to zero.



**[1]** Note that `result` must be in a different register from `op2`

## svlsr_wide[_u16]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svlsr_wide%5B_u16%5D_m

### Signature (source notation)

```c
svuint16_t svlsr_wide[_u16]_m(svbool_t pg, svuint16_t op1, svuint64_t op2);
```

### Description

Logical shift right

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Shift / Right / Vector shift right

- SME attributes: Not specified by source.

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
LSR Ztied1.H, Pg/M, Ztied1.H, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSR--wide-elements--predicated---Logical-shift-right-by-64-bit-wide-elements--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
LSR Zresult.H, Pg/M, Zresult.H, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSR--wide-elements--predicated---Logical-shift-right-by-64-bit-wide-elements--predicated--

### Operation

Source operation ID: `SveOperation_svlsr_wide_u16_m`

**Operation**



Return a vector in which each active element *i* contains `op1[i]` divided by 2 to the power `op2[i/4]`, with the result rounded towards zero  (or, equivalently, towards -∞).  All bits of the `op2` value are significant.



Take the inactive elements of the result from the corresponding elements of `op1`.

## svlsr_wide[_u16]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svlsr_wide%5B_u16%5D_x

### Signature (source notation)

```c
svuint16_t svlsr_wide[_u16]_x(svbool_t pg, svuint16_t op1, svuint64_t op2);
```

### Description

Logical shift right

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Shift / Right / Vector shift right

- SME attributes: Not specified by source.

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
LSR Ztied1.H, Pg/M, Ztied1.H, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSR--wide-elements--predicated---Logical-shift-right-by-64-bit-wide-elements--predicated--

This intrinsic compiles to:

```asm
LSR Zresult.H, Zop1.H, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSR--wide-elements--unpredicated---Logical-shift-right-by-64-bit-wide-elements--unpredicated--

### Operation

Source operation ID: `SveOperation_svlsr_wide_u16_x`

**Operation**



Return a vector in which each active element *i* contains `op1[i]` divided by 2 to the power `op2[i/4]`, with the result rounded towards zero  (or, equivalently, towards -∞).  All bits of the `op2` value are significant.



The inactive elements of the result have arbitrary, undefined values.

## svlsr_wide[_u16]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svlsr_wide%5B_u16%5D_z

### Signature (source notation)

```c
svuint16_t svlsr_wide[_u16]_z(svbool_t pg, svuint16_t op1, svuint64_t op2);
```

### Description

Logical shift right

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Shift / Right / Vector shift right

- SME attributes: Not specified by source.

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
LSR Zresult.H, Pg/M, Zresult.H, Zop2.D  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSR--wide-elements--predicated---Logical-shift-right-by-64-bit-wide-elements--predicated--

### Operation

Source operation ID: `SveOperation_svlsr_wide_u16_z`

**Operation**



Return a vector in which each active element *i* contains `op1[i]` divided by 2 to the power `op2[i/4]`, with the result rounded towards zero  (or, equivalently, towards -∞).  All bits of the `op2` value are significant.



Set the inactive elements of the result to zero.



**[1]** Note that `result` must be in a different register from `op2`

## svlsr_wide[_u32]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svlsr_wide%5B_u32%5D_m

### Signature (source notation)

```c
svuint32_t svlsr_wide[_u32]_m(svbool_t pg, svuint32_t op1, svuint64_t op2);
```

### Description

Logical shift right

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Shift / Right / Vector shift right

- SME attributes: Not specified by source.

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
LSR Ztied1.S, Pg/M, Ztied1.S, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSR--wide-elements--predicated---Logical-shift-right-by-64-bit-wide-elements--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
LSR Zresult.S, Pg/M, Zresult.S, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSR--wide-elements--predicated---Logical-shift-right-by-64-bit-wide-elements--predicated--

### Operation

Source operation ID: `SveOperation_svlsr_wide_u32_m`

**Operation**



Return a vector in which each active element *i* contains `op1[i]` divided by 2 to the power `op2[i/2]`, with the result rounded towards zero  (or, equivalently, towards -∞).  All bits of the `op2` value are significant.



Take the inactive elements of the result from the corresponding elements of `op1`.

## svlsr_wide[_u32]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svlsr_wide%5B_u32%5D_x

### Signature (source notation)

```c
svuint32_t svlsr_wide[_u32]_x(svbool_t pg, svuint32_t op1, svuint64_t op2);
```

### Description

Logical shift right

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Shift / Right / Vector shift right

- SME attributes: Not specified by source.

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
LSR Ztied1.S, Pg/M, Ztied1.S, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSR--wide-elements--predicated---Logical-shift-right-by-64-bit-wide-elements--predicated--

This intrinsic compiles to:

```asm
LSR Zresult.S, Zop1.S, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSR--wide-elements--unpredicated---Logical-shift-right-by-64-bit-wide-elements--unpredicated--

### Operation

Source operation ID: `SveOperation_svlsr_wide_u32_x`

**Operation**



Return a vector in which each active element *i* contains `op1[i]` divided by 2 to the power `op2[i/2]`, with the result rounded towards zero  (or, equivalently, towards -∞).  All bits of the `op2` value are significant.



The inactive elements of the result have arbitrary, undefined values.

## svlsr_wide[_u32]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svlsr_wide%5B_u32%5D_z

### Signature (source notation)

```c
svuint32_t svlsr_wide[_u32]_z(svbool_t pg, svuint32_t op1, svuint64_t op2);
```

### Description

Logical shift right

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Shift / Right / Vector shift right

- SME attributes: Not specified by source.

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
LSR Zresult.S, Pg/M, Zresult.S, Zop2.D  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSR--wide-elements--predicated---Logical-shift-right-by-64-bit-wide-elements--predicated--

### Operation

Source operation ID: `SveOperation_svlsr_wide_u32_z`

**Operation**



Return a vector in which each active element *i* contains `op1[i]` divided by 2 to the power `op2[i/2]`, with the result rounded towards zero  (or, equivalently, towards -∞).  All bits of the `op2` value are significant.



Set the inactive elements of the result to zero.



**[1]** Note that `result` must be in a different register from `op2`

## svlsr_wide[_u8]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svlsr_wide%5B_u8%5D_m

### Signature (source notation)

```c
svuint8_t svlsr_wide[_u8]_m(svbool_t pg, svuint8_t op1, svuint64_t op2);
```

### Description

Logical shift right

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Shift / Right / Vector shift right

- SME attributes: Not specified by source.

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
LSR Ztied1.B, Pg/M, Ztied1.B, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSR--wide-elements--predicated---Logical-shift-right-by-64-bit-wide-elements--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
LSR Zresult.B, Pg/M, Zresult.B, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSR--wide-elements--predicated---Logical-shift-right-by-64-bit-wide-elements--predicated--

### Operation

Source operation ID: `SveOperation_svlsr_wide_u8_m`

**Operation**



Return a vector in which each active element *i* contains `op1[i]` divided by 2 to the power `op2[i/8]`, with the result rounded towards zero  (or, equivalently, towards -∞).  All bits of the `op2` value are significant.



Take the inactive elements of the result from the corresponding elements of `op1`.

## svlsr_wide[_u8]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svlsr_wide%5B_u8%5D_x

### Signature (source notation)

```c
svuint8_t svlsr_wide[_u8]_x(svbool_t pg, svuint8_t op1, svuint64_t op2);
```

### Description

Logical shift right

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Shift / Right / Vector shift right

- SME attributes: Not specified by source.

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
LSR Ztied1.B, Pg/M, Ztied1.B, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSR--wide-elements--predicated---Logical-shift-right-by-64-bit-wide-elements--predicated--

This intrinsic compiles to:

```asm
LSR Zresult.B, Zop1.B, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSR--wide-elements--unpredicated---Logical-shift-right-by-64-bit-wide-elements--unpredicated--

### Operation

Source operation ID: `SveOperation_svlsr_wide_u8_x`

**Operation**



Return a vector in which each active element *i* contains `op1[i]` divided by 2 to the power `op2[i/8]`, with the result rounded towards zero  (or, equivalently, towards -∞).  All bits of the `op2` value are significant.



The inactive elements of the result have arbitrary, undefined values.

## svlsr_wide[_u8]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svlsr_wide%5B_u8%5D_z

### Signature (source notation)

```c
svuint8_t svlsr_wide[_u8]_z(svbool_t pg, svuint8_t op1, svuint64_t op2);
```

### Description

Logical shift right

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Shift / Right / Vector shift right

- SME attributes: Not specified by source.

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
LSR Zresult.B, Pg/M, Zresult.B, Zop2.D  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LSR--wide-elements--predicated---Logical-shift-right-by-64-bit-wide-elements--predicated--

### Operation

Source operation ID: `SveOperation_svlsr_wide_u8_z`

**Operation**



Return a vector in which each active element *i* contains `op1[i]` divided by 2 to the power `op2[i/8]`, with the result rounded towards zero  (or, equivalently, towards -∞).  All bits of the `op2` value are significant.



Set the inactive elements of the result to zero.



**[1]** Note that `result` must be in a different register from `op2`

