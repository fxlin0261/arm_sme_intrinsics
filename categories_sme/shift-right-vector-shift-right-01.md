# SME / Shift / Right / Vector shift right — Part 1

## svasr[_n_s16]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svasr%5B_n_s16%5D_m

### Signature (source notation)

```c
svint16_t svasr[_n_s16]_m(svbool_t pg, svint16_t op1, uint16_t op2);
```

### Description

Arithmetic shift right

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
ASR Ztied1.H, Pg/M, Ztied1.H, #op2  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ASR--immediate--predicated---Arithmetic-shift-right-by-immediate--predicated--

The general implementation is:

```asm
ASR Ztied1.H, Pg/M, Ztied1.H, Zop2.H  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ASR--vectors---Arithmetic-shift-right-by-vector--predicated--

### Operation

Source operation ID: `SveOperation_svasr_n_s8_m`

**Operation**



Return a vector in which each active element *i* contains `op1[i]` divided by 2 to the power `op2`, with the result rounded towards -∞.  All bits of the `op2` value are significant.



Take the inactive elements of the result from the corresponding elements of `op1`.



**[1]** If instead `result` is in a different register from the inputs, the compiler can add a preceding [MOVPRFX (unpredicated)](https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--) instruction

## svasr[_n_s16]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svasr%5B_n_s16%5D_x

### Signature (source notation)

```c
svint16_t svasr[_n_s16]_x(svbool_t pg, svint16_t op1, uint16_t op2);
```

### Description

Arithmetic shift right

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

When op2 is in the range [1, 16], this intrinsic can use:

```asm
ASR Zresult.H, Zop1.H, #op2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ASR--immediate--unpredicated---Arithmetic-shift-right-by-immediate--unpredicated--

When result and op1 are in the same register, this intrinsic can use:

```asm
ASR Ztied1.H, Pg/M, Ztied1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ASR--vectors---Arithmetic-shift-right-by-vector--predicated--

When result and op2 are in the same register, this intrinsic can use:

```asm
ASRR Ztied2.H, Pg/M, Ztied2.H, Zop1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ASRR--Reversed-arithmetic-shift-right-by-vector--predicated--

When result is in a different register from the inputs, the general implementation is:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
ASR Zresult.H, Pg/M, Zresult.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ASR--vectors---Arithmetic-shift-right-by-vector--predicated--

### Operation

Source operation ID: `SveOperation_svasr_n_s8_x`

**Operation**



Return a vector in which each active element *i* contains `op1[i]` divided by 2 to the power `op2`, with the result rounded towards -∞.  All bits of the `op2` value are significant.



The inactive elements of the result have arbitrary, undefined values.

## svasr[_n_s16]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svasr%5B_n_s16%5D_z

### Signature (source notation)

```c
svint16_t svasr[_n_s16]_z(svbool_t pg, svint16_t op1, uint16_t op2);
```

### Description

Arithmetic shift right

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

When op2 is in the range [1, 16], this intrinsic can use:

```asm
MOVPRFX Zresult.H, Pg/Z, Zop1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
ASR Zresult.H, Pg/M, Zresult.H, #op2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ASR--immediate--predicated---Arithmetic-shift-right-by-immediate--predicated--

When result is in a different register from op2, this intrinsic can use:

```asm
MOVPRFX Zresult.H, Pg/Z, Zop1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
ASR Zresult.H, Pg/M, Zresult.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ASR--vectors---Arithmetic-shift-right-by-vector--predicated--

When result is in a different register from op1, this intrinsic can use:

```asm
MOVPRFX Zresult.H, Pg/Z, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
ASRR Zresult.H, Pg/M, Zresult.H, Zop1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ASRR--Reversed-arithmetic-shift-right-by-vector--predicated--

### Operation

Source operation ID: `SveOperation_svasr_n_s8_z`

**Operation**



Return a vector in which each active element *i* contains `op1[i]` divided by 2 to the power `op2`, with the result rounded towards -∞.  All bits of the `op2` value are significant.



Set the inactive elements of the result to zero.

## svasr[_n_s32]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svasr%5B_n_s32%5D_m

### Signature (source notation)

```c
svint32_t svasr[_n_s32]_m(svbool_t pg, svint32_t op1, uint32_t op2);
```

### Description

Arithmetic shift right

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
ASR Ztied1.S, Pg/M, Ztied1.S, #op2  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ASR--immediate--predicated---Arithmetic-shift-right-by-immediate--predicated--

The general implementation is:

```asm
ASR Ztied1.S, Pg/M, Ztied1.S, Zop2.S  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ASR--vectors---Arithmetic-shift-right-by-vector--predicated--

### Operation

Source operation ID: `SveOperation_svasr_n_s8_m`

**Operation**



Return a vector in which each active element *i* contains `op1[i]` divided by 2 to the power `op2`, with the result rounded towards -∞.  All bits of the `op2` value are significant.



Take the inactive elements of the result from the corresponding elements of `op1`.



**[1]** If instead `result` is in a different register from the inputs, the compiler can add a preceding [MOVPRFX (unpredicated)](https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--) instruction

## svasr[_n_s32]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svasr%5B_n_s32%5D_x

### Signature (source notation)

```c
svint32_t svasr[_n_s32]_x(svbool_t pg, svint32_t op1, uint32_t op2);
```

### Description

Arithmetic shift right

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

When op2 is in the range [1, 32], this intrinsic can use:

```asm
ASR Zresult.S, Zop1.S, #op2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ASR--immediate--unpredicated---Arithmetic-shift-right-by-immediate--unpredicated--

When result and op1 are in the same register, this intrinsic can use:

```asm
ASR Ztied1.S, Pg/M, Ztied1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ASR--vectors---Arithmetic-shift-right-by-vector--predicated--

When result and op2 are in the same register, this intrinsic can use:

```asm
ASRR Ztied2.S, Pg/M, Ztied2.S, Zop1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ASRR--Reversed-arithmetic-shift-right-by-vector--predicated--

When result is in a different register from the inputs, the general implementation is:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
ASR Zresult.S, Pg/M, Zresult.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ASR--vectors---Arithmetic-shift-right-by-vector--predicated--

### Operation

Source operation ID: `SveOperation_svasr_n_s8_x`

**Operation**



Return a vector in which each active element *i* contains `op1[i]` divided by 2 to the power `op2`, with the result rounded towards -∞.  All bits of the `op2` value are significant.



The inactive elements of the result have arbitrary, undefined values.

## svasr[_n_s32]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svasr%5B_n_s32%5D_z

### Signature (source notation)

```c
svint32_t svasr[_n_s32]_z(svbool_t pg, svint32_t op1, uint32_t op2);
```

### Description

Arithmetic shift right

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

When op2 is in the range [1, 32], this intrinsic can use:

```asm
MOVPRFX Zresult.S, Pg/Z, Zop1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
ASR Zresult.S, Pg/M, Zresult.S, #op2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ASR--immediate--predicated---Arithmetic-shift-right-by-immediate--predicated--

When result is in a different register from op2, this intrinsic can use:

```asm
MOVPRFX Zresult.S, Pg/Z, Zop1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
ASR Zresult.S, Pg/M, Zresult.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ASR--vectors---Arithmetic-shift-right-by-vector--predicated--

When result is in a different register from op1, this intrinsic can use:

```asm
MOVPRFX Zresult.S, Pg/Z, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
ASRR Zresult.S, Pg/M, Zresult.S, Zop1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ASRR--Reversed-arithmetic-shift-right-by-vector--predicated--

### Operation

Source operation ID: `SveOperation_svasr_n_s8_z`

**Operation**



Return a vector in which each active element *i* contains `op1[i]` divided by 2 to the power `op2`, with the result rounded towards -∞.  All bits of the `op2` value are significant.



Set the inactive elements of the result to zero.

## svasr[_n_s64]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svasr%5B_n_s64%5D_m

### Signature (source notation)

```c
svint64_t svasr[_n_s64]_m(svbool_t pg, svint64_t op1, uint64_t op2);
```

### Description

Arithmetic shift right

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
ASR Ztied1.D, Pg/M, Ztied1.D, #op2  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ASR--immediate--predicated---Arithmetic-shift-right-by-immediate--predicated--

The general implementation is:

```asm
ASR Ztied1.D, Pg/M, Ztied1.D, Zop2.D  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ASR--vectors---Arithmetic-shift-right-by-vector--predicated--

### Operation

Source operation ID: `SveOperation_svasr_n_s8_m`

**Operation**



Return a vector in which each active element *i* contains `op1[i]` divided by 2 to the power `op2`, with the result rounded towards -∞.  All bits of the `op2` value are significant.



Take the inactive elements of the result from the corresponding elements of `op1`.



**[1]** If instead `result` is in a different register from the inputs, the compiler can add a preceding [MOVPRFX (unpredicated)](https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--) instruction

## svasr[_n_s64]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svasr%5B_n_s64%5D_x

### Signature (source notation)

```c
svint64_t svasr[_n_s64]_x(svbool_t pg, svint64_t op1, uint64_t op2);
```

### Description

Arithmetic shift right

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
ASR Zresult.D, Zop1.D, #op2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ASR--immediate--unpredicated---Arithmetic-shift-right-by-immediate--unpredicated--

When result and op1 are in the same register, this intrinsic can use:

```asm
ASR Ztied1.D, Pg/M, Ztied1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ASR--vectors---Arithmetic-shift-right-by-vector--predicated--

When result and op2 are in the same register, this intrinsic can use:

```asm
ASRR Ztied2.D, Pg/M, Ztied2.D, Zop1.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ASRR--Reversed-arithmetic-shift-right-by-vector--predicated--

When result is in a different register from the inputs, the general implementation is:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
ASR Zresult.D, Pg/M, Zresult.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ASR--vectors---Arithmetic-shift-right-by-vector--predicated--

### Operation

Source operation ID: `SveOperation_svasr_n_s8_x`

**Operation**



Return a vector in which each active element *i* contains `op1[i]` divided by 2 to the power `op2`, with the result rounded towards -∞.  All bits of the `op2` value are significant.



The inactive elements of the result have arbitrary, undefined values.

## svasr[_n_s64]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svasr%5B_n_s64%5D_z

### Signature (source notation)

```c
svint64_t svasr[_n_s64]_z(svbool_t pg, svint64_t op1, uint64_t op2);
```

### Description

Arithmetic shift right

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
ASR Zresult.D, Pg/M, Zresult.D, #op2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ASR--immediate--predicated---Arithmetic-shift-right-by-immediate--predicated--

When result is in a different register from op2, this intrinsic can use:

```asm
MOVPRFX Zresult.D, Pg/Z, Zop1.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
ASR Zresult.D, Pg/M, Zresult.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ASR--vectors---Arithmetic-shift-right-by-vector--predicated--

When result is in a different register from op1, this intrinsic can use:

```asm
MOVPRFX Zresult.D, Pg/Z, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
ASRR Zresult.D, Pg/M, Zresult.D, Zop1.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ASRR--Reversed-arithmetic-shift-right-by-vector--predicated--

### Operation

Source operation ID: `SveOperation_svasr_n_s8_z`

**Operation**



Return a vector in which each active element *i* contains `op1[i]` divided by 2 to the power `op2`, with the result rounded towards -∞.  All bits of the `op2` value are significant.



Set the inactive elements of the result to zero.

## svasr[_n_s8]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svasr%5B_n_s8%5D_m

### Signature (source notation)

```c
svint8_t svasr[_n_s8]_m(svbool_t pg, svint8_t op1, uint8_t op2);
```

### Description

Arithmetic shift right

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
ASR Ztied1.B, Pg/M, Ztied1.B, #op2  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ASR--immediate--predicated---Arithmetic-shift-right-by-immediate--predicated--

The general implementation is:

```asm
ASR Ztied1.B, Pg/M, Ztied1.B, Zop2.B  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ASR--vectors---Arithmetic-shift-right-by-vector--predicated--

### Operation

Source operation ID: `SveOperation_svasr_n_s8_m`

**Operation**



Return a vector in which each active element *i* contains `op1[i]` divided by 2 to the power `op2`, with the result rounded towards -∞.  All bits of the `op2` value are significant.



Take the inactive elements of the result from the corresponding elements of `op1`.



**[1]** If instead `result` is in a different register from the inputs, the compiler can add a preceding [MOVPRFX (unpredicated)](https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--) instruction

## svasr[_n_s8]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svasr%5B_n_s8%5D_x

### Signature (source notation)

```c
svint8_t svasr[_n_s8]_x(svbool_t pg, svint8_t op1, uint8_t op2);
```

### Description

Arithmetic shift right

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
ASR Zresult.B, Zop1.B, #op2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ASR--immediate--unpredicated---Arithmetic-shift-right-by-immediate--unpredicated--

When result and op1 are in the same register, this intrinsic can use:

```asm
ASR Ztied1.B, Pg/M, Ztied1.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ASR--vectors---Arithmetic-shift-right-by-vector--predicated--

When result and op2 are in the same register, this intrinsic can use:

```asm
ASRR Ztied2.B, Pg/M, Ztied2.B, Zop1.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ASRR--Reversed-arithmetic-shift-right-by-vector--predicated--

When result is in a different register from the inputs, the general implementation is:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
ASR Zresult.B, Pg/M, Zresult.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ASR--vectors---Arithmetic-shift-right-by-vector--predicated--

### Operation

Source operation ID: `SveOperation_svasr_n_s8_x`

**Operation**



Return a vector in which each active element *i* contains `op1[i]` divided by 2 to the power `op2`, with the result rounded towards -∞.  All bits of the `op2` value are significant.



The inactive elements of the result have arbitrary, undefined values.

## svasr[_n_s8]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svasr%5B_n_s8%5D_z

### Signature (source notation)

```c
svint8_t svasr[_n_s8]_z(svbool_t pg, svint8_t op1, uint8_t op2);
```

### Description

Arithmetic shift right

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
ASR Zresult.B, Pg/M, Zresult.B, #op2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ASR--immediate--predicated---Arithmetic-shift-right-by-immediate--predicated--

When result is in a different register from op2, this intrinsic can use:

```asm
MOVPRFX Zresult.B, Pg/Z, Zop1.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
ASR Zresult.B, Pg/M, Zresult.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ASR--vectors---Arithmetic-shift-right-by-vector--predicated--

When result is in a different register from op1, this intrinsic can use:

```asm
MOVPRFX Zresult.B, Pg/Z, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
ASRR Zresult.B, Pg/M, Zresult.B, Zop1.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ASRR--Reversed-arithmetic-shift-right-by-vector--predicated--

### Operation

Source operation ID: `SveOperation_svasr_n_s8_z`

**Operation**



Return a vector in which each active element *i* contains `op1[i]` divided by 2 to the power `op2`, with the result rounded towards -∞.  All bits of the `op2` value are significant.



Set the inactive elements of the result to zero.

## svasr[_s16]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svasr%5B_s16%5D_m

### Signature (source notation)

```c
svint16_t svasr[_s16]_m(svbool_t pg, svint16_t op1, svuint16_t op2);
```

### Description

Arithmetic shift right

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
ASR Ztied1.H, Pg/M, Ztied1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ASR--vectors---Arithmetic-shift-right-by-vector--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
ASR Zresult.H, Pg/M, Zresult.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ASR--vectors---Arithmetic-shift-right-by-vector--predicated--

### Operation

Source operation ID: `SveOperation_svasr_s8_m`

**Operation**



Return a vector in which each active element *i* contains `op1[i]` divided by 2 to the power `op2[i]`, with the result rounded towards -∞.  All bits of the `op2` value are significant.



Take the inactive elements of the result from the corresponding elements of `op1`.

## svasr[_s16]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svasr%5B_s16%5D_x

### Signature (source notation)

```c
svint16_t svasr[_s16]_x(svbool_t pg, svint16_t op1, svuint16_t op2);
```

### Description

Arithmetic shift right

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
ASR Ztied1.H, Pg/M, Ztied1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ASR--vectors---Arithmetic-shift-right-by-vector--predicated--

When result and op2 are in the same register, this intrinsic compiles to:

```asm
ASRR Ztied2.H, Pg/M, Ztied2.H, Zop1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ASRR--Reversed-arithmetic-shift-right-by-vector--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
ASR Zresult.H, Pg/M, Zresult.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ASR--vectors---Arithmetic-shift-right-by-vector--predicated--

### Operation

Source operation ID: `SveOperation_svasr_s8_x`

**Operation**



Return a vector in which each active element *i* contains `op1[i]` divided by 2 to the power `op2[i]`, with the result rounded towards -∞.  All bits of the `op2` value are significant.



The inactive elements of the result have arbitrary, undefined values.

## svasr[_s16]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svasr%5B_s16%5D_z

### Signature (source notation)

```c
svint16_t svasr[_s16]_z(svbool_t pg, svint16_t op1, svuint16_t op2);
```

### Description

Arithmetic shift right

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
ASR Zresult.H, Pg/M, Zresult.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ASR--vectors---Arithmetic-shift-right-by-vector--predicated--

When result is in a different register from op1, this intrinsic can use:

```asm
MOVPRFX Zresult.H, Pg/Z, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
ASRR Zresult.H, Pg/M, Zresult.H, Zop1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ASRR--Reversed-arithmetic-shift-right-by-vector--predicated--

### Operation

Source operation ID: `SveOperation_svasr_s8_z`

**Operation**



Return a vector in which each active element *i* contains `op1[i]` divided by 2 to the power `op2[i]`, with the result rounded towards -∞.  All bits of the `op2` value are significant.



Set the inactive elements of the result to zero.

## svasr[_s32]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svasr%5B_s32%5D_m

### Signature (source notation)

```c
svint32_t svasr[_s32]_m(svbool_t pg, svint32_t op1, svuint32_t op2);
```

### Description

Arithmetic shift right

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
ASR Ztied1.S, Pg/M, Ztied1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ASR--vectors---Arithmetic-shift-right-by-vector--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
ASR Zresult.S, Pg/M, Zresult.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ASR--vectors---Arithmetic-shift-right-by-vector--predicated--

### Operation

Source operation ID: `SveOperation_svasr_s8_m`

**Operation**



Return a vector in which each active element *i* contains `op1[i]` divided by 2 to the power `op2[i]`, with the result rounded towards -∞.  All bits of the `op2` value are significant.



Take the inactive elements of the result from the corresponding elements of `op1`.

## svasr[_s32]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svasr%5B_s32%5D_x

### Signature (source notation)

```c
svint32_t svasr[_s32]_x(svbool_t pg, svint32_t op1, svuint32_t op2);
```

### Description

Arithmetic shift right

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
ASR Ztied1.S, Pg/M, Ztied1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ASR--vectors---Arithmetic-shift-right-by-vector--predicated--

When result and op2 are in the same register, this intrinsic compiles to:

```asm
ASRR Ztied2.S, Pg/M, Ztied2.S, Zop1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ASRR--Reversed-arithmetic-shift-right-by-vector--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
ASR Zresult.S, Pg/M, Zresult.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ASR--vectors---Arithmetic-shift-right-by-vector--predicated--

### Operation

Source operation ID: `SveOperation_svasr_s8_x`

**Operation**



Return a vector in which each active element *i* contains `op1[i]` divided by 2 to the power `op2[i]`, with the result rounded towards -∞.  All bits of the `op2` value are significant.



The inactive elements of the result have arbitrary, undefined values.

## svasr[_s32]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svasr%5B_s32%5D_z

### Signature (source notation)

```c
svint32_t svasr[_s32]_z(svbool_t pg, svint32_t op1, svuint32_t op2);
```

### Description

Arithmetic shift right

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
ASR Zresult.S, Pg/M, Zresult.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ASR--vectors---Arithmetic-shift-right-by-vector--predicated--

When result is in a different register from op1, this intrinsic can use:

```asm
MOVPRFX Zresult.S, Pg/Z, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
ASRR Zresult.S, Pg/M, Zresult.S, Zop1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ASRR--Reversed-arithmetic-shift-right-by-vector--predicated--

### Operation

Source operation ID: `SveOperation_svasr_s8_z`

**Operation**



Return a vector in which each active element *i* contains `op1[i]` divided by 2 to the power `op2[i]`, with the result rounded towards -∞.  All bits of the `op2` value are significant.



Set the inactive elements of the result to zero.

## svasr[_s64]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svasr%5B_s64%5D_m

### Signature (source notation)

```c
svint64_t svasr[_s64]_m(svbool_t pg, svint64_t op1, svuint64_t op2);
```

### Description

Arithmetic shift right

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
ASR Ztied1.D, Pg/M, Ztied1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ASR--vectors---Arithmetic-shift-right-by-vector--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
ASR Zresult.D, Pg/M, Zresult.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ASR--vectors---Arithmetic-shift-right-by-vector--predicated--

### Operation

Source operation ID: `SveOperation_svasr_s8_m`

**Operation**



Return a vector in which each active element *i* contains `op1[i]` divided by 2 to the power `op2[i]`, with the result rounded towards -∞.  All bits of the `op2` value are significant.



Take the inactive elements of the result from the corresponding elements of `op1`.

## svasr[_s64]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svasr%5B_s64%5D_x

### Signature (source notation)

```c
svint64_t svasr[_s64]_x(svbool_t pg, svint64_t op1, svuint64_t op2);
```

### Description

Arithmetic shift right

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
ASR Ztied1.D, Pg/M, Ztied1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ASR--vectors---Arithmetic-shift-right-by-vector--predicated--

When result and op2 are in the same register, this intrinsic compiles to:

```asm
ASRR Ztied2.D, Pg/M, Ztied2.D, Zop1.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ASRR--Reversed-arithmetic-shift-right-by-vector--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
ASR Zresult.D, Pg/M, Zresult.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ASR--vectors---Arithmetic-shift-right-by-vector--predicated--

### Operation

Source operation ID: `SveOperation_svasr_s8_x`

**Operation**



Return a vector in which each active element *i* contains `op1[i]` divided by 2 to the power `op2[i]`, with the result rounded towards -∞.  All bits of the `op2` value are significant.



The inactive elements of the result have arbitrary, undefined values.

## svasr[_s64]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svasr%5B_s64%5D_z

### Signature (source notation)

```c
svint64_t svasr[_s64]_z(svbool_t pg, svint64_t op1, svuint64_t op2);
```

### Description

Arithmetic shift right

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
ASR Zresult.D, Pg/M, Zresult.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ASR--vectors---Arithmetic-shift-right-by-vector--predicated--

When result is in a different register from op1, this intrinsic can use:

```asm
MOVPRFX Zresult.D, Pg/Z, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
ASRR Zresult.D, Pg/M, Zresult.D, Zop1.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ASRR--Reversed-arithmetic-shift-right-by-vector--predicated--

### Operation

Source operation ID: `SveOperation_svasr_s8_z`

**Operation**



Return a vector in which each active element *i* contains `op1[i]` divided by 2 to the power `op2[i]`, with the result rounded towards -∞.  All bits of the `op2` value are significant.



Set the inactive elements of the result to zero.

## svasr[_s8]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svasr%5B_s8%5D_m

### Signature (source notation)

```c
svint8_t svasr[_s8]_m(svbool_t pg, svint8_t op1, svuint8_t op2);
```

### Description

Arithmetic shift right

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
ASR Ztied1.B, Pg/M, Ztied1.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ASR--vectors---Arithmetic-shift-right-by-vector--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
ASR Zresult.B, Pg/M, Zresult.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ASR--vectors---Arithmetic-shift-right-by-vector--predicated--

### Operation

Source operation ID: `SveOperation_svasr_s8_m`

**Operation**



Return a vector in which each active element *i* contains `op1[i]` divided by 2 to the power `op2[i]`, with the result rounded towards -∞.  All bits of the `op2` value are significant.



Take the inactive elements of the result from the corresponding elements of `op1`.

## svasr[_s8]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svasr%5B_s8%5D_x

### Signature (source notation)

```c
svint8_t svasr[_s8]_x(svbool_t pg, svint8_t op1, svuint8_t op2);
```

### Description

Arithmetic shift right

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
ASR Ztied1.B, Pg/M, Ztied1.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ASR--vectors---Arithmetic-shift-right-by-vector--predicated--

When result and op2 are in the same register, this intrinsic compiles to:

```asm
ASRR Ztied2.B, Pg/M, Ztied2.B, Zop1.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ASRR--Reversed-arithmetic-shift-right-by-vector--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
ASR Zresult.B, Pg/M, Zresult.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ASR--vectors---Arithmetic-shift-right-by-vector--predicated--

### Operation

Source operation ID: `SveOperation_svasr_s8_x`

**Operation**



Return a vector in which each active element *i* contains `op1[i]` divided by 2 to the power `op2[i]`, with the result rounded towards -∞.  All bits of the `op2` value are significant.



The inactive elements of the result have arbitrary, undefined values.

## svasr[_s8]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svasr%5B_s8%5D_z

### Signature (source notation)

```c
svint8_t svasr[_s8]_z(svbool_t pg, svint8_t op1, svuint8_t op2);
```

### Description

Arithmetic shift right

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
ASR Zresult.B, Pg/M, Zresult.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ASR--vectors---Arithmetic-shift-right-by-vector--predicated--

When result is in a different register from op1, this intrinsic can use:

```asm
MOVPRFX Zresult.B, Pg/Z, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
ASRR Zresult.B, Pg/M, Zresult.B, Zop1.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ASRR--Reversed-arithmetic-shift-right-by-vector--predicated--

### Operation

Source operation ID: `SveOperation_svasr_s8_z`

**Operation**



Return a vector in which each active element *i* contains `op1[i]` divided by 2 to the power `op2[i]`, with the result rounded towards -∞.  All bits of the `op2` value are significant.



Set the inactive elements of the result to zero.

## svasr_wide[_n_s16]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svasr_wide%5B_n_s16%5D_m

### Signature (source notation)

```c
svint16_t svasr_wide[_n_s16]_m(svbool_t pg, svint16_t op1, uint64_t op2);
```

### Description

Arithmetic shift right

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
ASR Ztied1.H, Pg/M, Ztied1.H, #op2  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ASR--immediate--predicated---Arithmetic-shift-right-by-immediate--predicated--

The general implementation is:

```asm
ASR Ztied1.H, Pg/M, Ztied1.H, Zop2.D  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ASR--wide-elements--predicated---Arithmetic-shift-right-by-64-bit-wide-elements--predicated--

### Operation

Source operation ID: `SveOperation_svasr_n_s8_m`

**Operation**



Return a vector in which each active element *i* contains `op1[i]` divided by 2 to the power `op2`, with the result rounded towards -∞.  All bits of the `op2` value are significant.



Take the inactive elements of the result from the corresponding elements of `op1`.



**[1]** If instead `result` is in a different register from the inputs, the compiler can add a preceding [MOVPRFX (unpredicated)](https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--) instruction

## svasr_wide[_n_s16]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svasr_wide%5B_n_s16%5D_x

### Signature (source notation)

```c
svint16_t svasr_wide[_n_s16]_x(svbool_t pg, svint16_t op1, uint64_t op2);
```

### Description

Arithmetic shift right

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
ASR Zresult.H, Zop1.H, #op2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ASR--immediate--unpredicated---Arithmetic-shift-right-by-immediate--unpredicated--

When result and op1 are in the same register, this intrinsic can use:

```asm
ASR Ztied1.H, Pg/M, Ztied1.H, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ASR--wide-elements--predicated---Arithmetic-shift-right-by-64-bit-wide-elements--predicated--

The general implementation is:

```asm
ASR Zresult.H, Zop1.H, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ASR--wide-elements--unpredicated---Arithmetic-shift-right-by-64-bit-wide-elements--unpredicated--

### Operation

Source operation ID: `SveOperation_svasr_n_s8_x`

**Operation**



Return a vector in which each active element *i* contains `op1[i]` divided by 2 to the power `op2`, with the result rounded towards -∞.  All bits of the `op2` value are significant.



The inactive elements of the result have arbitrary, undefined values.

## svasr_wide[_n_s16]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svasr_wide%5B_n_s16%5D_z

### Signature (source notation)

```c
svint16_t svasr_wide[_n_s16]_z(svbool_t pg, svint16_t op1, uint64_t op2);
```

### Description

Arithmetic shift right

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

When op2 is in the range [1, 16], this intrinsic can use:

```asm
MOVPRFX Zresult.H, Pg/Z, Zop1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
ASR Zresult.H, Pg/M, Zresult.H, #op2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ASR--immediate--predicated---Arithmetic-shift-right-by-immediate--predicated--

The general implementation is:

```asm
MOVPRFX Zresult.H, Pg/Z, Zop1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
ASR Zresult.H, Pg/M, Zresult.H, Zop2.D  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ASR--wide-elements--predicated---Arithmetic-shift-right-by-64-bit-wide-elements--predicated--

### Operation

Source operation ID: `SveOperation_svasr_wide_n_s8_z`

**Operation**



Return a vector in which each active element *i* contains `op1[i]` divided by 2 to the power `op2`, with the result rounded towards -∞.  All bits of the `op2` value are significant.



Set the inactive elements of the result to zero.



**[1]** Note that `result` must be in a different register from `op2`

## svasr_wide[_n_s32]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svasr_wide%5B_n_s32%5D_m

### Signature (source notation)

```c
svint32_t svasr_wide[_n_s32]_m(svbool_t pg, svint32_t op1, uint64_t op2);
```

### Description

Arithmetic shift right

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

When op2 is in the range [1, 32], this intrinsic can use:

```asm
ASR Ztied1.S, Pg/M, Ztied1.S, #op2  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ASR--immediate--predicated---Arithmetic-shift-right-by-immediate--predicated--

The general implementation is:

```asm
ASR Ztied1.S, Pg/M, Ztied1.S, Zop2.D  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ASR--wide-elements--predicated---Arithmetic-shift-right-by-64-bit-wide-elements--predicated--

### Operation

Source operation ID: `SveOperation_svasr_n_s8_m`

**Operation**



Return a vector in which each active element *i* contains `op1[i]` divided by 2 to the power `op2`, with the result rounded towards -∞.  All bits of the `op2` value are significant.



Take the inactive elements of the result from the corresponding elements of `op1`.



**[1]** If instead `result` is in a different register from the inputs, the compiler can add a preceding [MOVPRFX (unpredicated)](https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--) instruction

## svasr_wide[_n_s32]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svasr_wide%5B_n_s32%5D_x

### Signature (source notation)

```c
svint32_t svasr_wide[_n_s32]_x(svbool_t pg, svint32_t op1, uint64_t op2);
```

### Description

Arithmetic shift right

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

When op2 is in the range [1, 32], this intrinsic can use:

```asm
ASR Zresult.S, Zop1.S, #op2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ASR--immediate--unpredicated---Arithmetic-shift-right-by-immediate--unpredicated--

When result and op1 are in the same register, this intrinsic can use:

```asm
ASR Ztied1.S, Pg/M, Ztied1.S, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ASR--wide-elements--predicated---Arithmetic-shift-right-by-64-bit-wide-elements--predicated--

The general implementation is:

```asm
ASR Zresult.S, Zop1.S, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ASR--wide-elements--unpredicated---Arithmetic-shift-right-by-64-bit-wide-elements--unpredicated--

### Operation

Source operation ID: `SveOperation_svasr_n_s8_x`

**Operation**



Return a vector in which each active element *i* contains `op1[i]` divided by 2 to the power `op2`, with the result rounded towards -∞.  All bits of the `op2` value are significant.



The inactive elements of the result have arbitrary, undefined values.

## svasr_wide[_n_s32]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svasr_wide%5B_n_s32%5D_z

### Signature (source notation)

```c
svint32_t svasr_wide[_n_s32]_z(svbool_t pg, svint32_t op1, uint64_t op2);
```

### Description

Arithmetic shift right

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

When op2 is in the range [1, 32], this intrinsic can use:

```asm
MOVPRFX Zresult.S, Pg/Z, Zop1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
ASR Zresult.S, Pg/M, Zresult.S, #op2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ASR--immediate--predicated---Arithmetic-shift-right-by-immediate--predicated--

The general implementation is:

```asm
MOVPRFX Zresult.S, Pg/Z, Zop1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
ASR Zresult.S, Pg/M, Zresult.S, Zop2.D  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ASR--wide-elements--predicated---Arithmetic-shift-right-by-64-bit-wide-elements--predicated--

### Operation

Source operation ID: `SveOperation_svasr_wide_n_s8_z`

**Operation**



Return a vector in which each active element *i* contains `op1[i]` divided by 2 to the power `op2`, with the result rounded towards -∞.  All bits of the `op2` value are significant.



Set the inactive elements of the result to zero.



**[1]** Note that `result` must be in a different register from `op2`

## svasr_wide[_n_s8]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svasr_wide%5B_n_s8%5D_m

### Signature (source notation)

```c
svint8_t svasr_wide[_n_s8]_m(svbool_t pg, svint8_t op1, uint64_t op2);
```

### Description

Arithmetic shift right

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
ASR Ztied1.B, Pg/M, Ztied1.B, #op2  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ASR--immediate--predicated---Arithmetic-shift-right-by-immediate--predicated--

The general implementation is:

```asm
ASR Ztied1.B, Pg/M, Ztied1.B, Zop2.D  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ASR--wide-elements--predicated---Arithmetic-shift-right-by-64-bit-wide-elements--predicated--

### Operation

Source operation ID: `SveOperation_svasr_n_s8_m`

**Operation**



Return a vector in which each active element *i* contains `op1[i]` divided by 2 to the power `op2`, with the result rounded towards -∞.  All bits of the `op2` value are significant.



Take the inactive elements of the result from the corresponding elements of `op1`.



**[1]** If instead `result` is in a different register from the inputs, the compiler can add a preceding [MOVPRFX (unpredicated)](https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--) instruction

## svasr_wide[_n_s8]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svasr_wide%5B_n_s8%5D_x

### Signature (source notation)

```c
svint8_t svasr_wide[_n_s8]_x(svbool_t pg, svint8_t op1, uint64_t op2);
```

### Description

Arithmetic shift right

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
ASR Zresult.B, Zop1.B, #op2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ASR--immediate--unpredicated---Arithmetic-shift-right-by-immediate--unpredicated--

When result and op1 are in the same register, this intrinsic can use:

```asm
ASR Ztied1.B, Pg/M, Ztied1.B, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ASR--wide-elements--predicated---Arithmetic-shift-right-by-64-bit-wide-elements--predicated--

The general implementation is:

```asm
ASR Zresult.B, Zop1.B, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ASR--wide-elements--unpredicated---Arithmetic-shift-right-by-64-bit-wide-elements--unpredicated--

### Operation

Source operation ID: `SveOperation_svasr_n_s8_x`

**Operation**



Return a vector in which each active element *i* contains `op1[i]` divided by 2 to the power `op2`, with the result rounded towards -∞.  All bits of the `op2` value are significant.



The inactive elements of the result have arbitrary, undefined values.

## svasr_wide[_n_s8]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svasr_wide%5B_n_s8%5D_z

### Signature (source notation)

```c
svint8_t svasr_wide[_n_s8]_z(svbool_t pg, svint8_t op1, uint64_t op2);
```

### Description

Arithmetic shift right

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
ASR Zresult.B, Pg/M, Zresult.B, #op2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ASR--immediate--predicated---Arithmetic-shift-right-by-immediate--predicated--

The general implementation is:

```asm
MOVPRFX Zresult.B, Pg/Z, Zop1.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
ASR Zresult.B, Pg/M, Zresult.B, Zop2.D  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ASR--wide-elements--predicated---Arithmetic-shift-right-by-64-bit-wide-elements--predicated--

### Operation

Source operation ID: `SveOperation_svasr_wide_n_s8_z`

**Operation**



Return a vector in which each active element *i* contains `op1[i]` divided by 2 to the power `op2`, with the result rounded towards -∞.  All bits of the `op2` value are significant.



Set the inactive elements of the result to zero.



**[1]** Note that `result` must be in a different register from `op2`

## svasr_wide[_s16]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svasr_wide%5B_s16%5D_m

### Signature (source notation)

```c
svint16_t svasr_wide[_s16]_m(svbool_t pg, svint16_t op1, svuint64_t op2);
```

### Description

Arithmetic shift right

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
ASR Ztied1.H, Pg/M, Ztied1.H, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ASR--wide-elements--predicated---Arithmetic-shift-right-by-64-bit-wide-elements--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
ASR Zresult.H, Pg/M, Zresult.H, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ASR--wide-elements--predicated---Arithmetic-shift-right-by-64-bit-wide-elements--predicated--

### Operation

Source operation ID: `SveOperation_svasr_wide_s16_m`

**Operation**



Return a vector in which each active element *i* contains `op1[i]` divided by 2 to the power `op2[i/4]`, with the result rounded towards -∞.  All bits of the `op2` value are significant.



Take the inactive elements of the result from the corresponding elements of `op1`.

## svasr_wide[_s16]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svasr_wide%5B_s16%5D_x

### Signature (source notation)

```c
svint16_t svasr_wide[_s16]_x(svbool_t pg, svint16_t op1, svuint64_t op2);
```

### Description

Arithmetic shift right

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
ASR Ztied1.H, Pg/M, Ztied1.H, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ASR--wide-elements--predicated---Arithmetic-shift-right-by-64-bit-wide-elements--predicated--

This intrinsic compiles to:

```asm
ASR Zresult.H, Zop1.H, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ASR--wide-elements--unpredicated---Arithmetic-shift-right-by-64-bit-wide-elements--unpredicated--

### Operation

Source operation ID: `SveOperation_svasr_wide_s16_x`

**Operation**



Return a vector in which each active element *i* contains `op1[i]` divided by 2 to the power `op2[i/4]`, with the result rounded towards -∞.  All bits of the `op2` value are significant.



The inactive elements of the result have arbitrary, undefined values.

## svasr_wide[_s16]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svasr_wide%5B_s16%5D_z

### Signature (source notation)

```c
svint16_t svasr_wide[_s16]_z(svbool_t pg, svint16_t op1, svuint64_t op2);
```

### Description

Arithmetic shift right

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
ASR Zresult.H, Pg/M, Zresult.H, Zop2.D  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ASR--wide-elements--predicated---Arithmetic-shift-right-by-64-bit-wide-elements--predicated--

### Operation

Source operation ID: `SveOperation_svasr_wide_s16_z`

**Operation**



Return a vector in which each active element *i* contains `op1[i]` divided by 2 to the power `op2[i/4]`, with the result rounded towards -∞.  All bits of the `op2` value are significant.



Set the inactive elements of the result to zero.



**[1]** Note that `result` must be in a different register from `op2`

## svasr_wide[_s32]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svasr_wide%5B_s32%5D_m

### Signature (source notation)

```c
svint32_t svasr_wide[_s32]_m(svbool_t pg, svint32_t op1, svuint64_t op2);
```

### Description

Arithmetic shift right

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
ASR Ztied1.S, Pg/M, Ztied1.S, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ASR--wide-elements--predicated---Arithmetic-shift-right-by-64-bit-wide-elements--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
ASR Zresult.S, Pg/M, Zresult.S, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ASR--wide-elements--predicated---Arithmetic-shift-right-by-64-bit-wide-elements--predicated--

### Operation

Source operation ID: `SveOperation_svasr_wide_s32_m`

**Operation**



Return a vector in which each active element *i* contains `op1[i]` divided by 2 to the power `op2[i/2]`, with the result rounded towards -∞.  All bits of the `op2` value are significant.



Take the inactive elements of the result from the corresponding elements of `op1`.

## svasr_wide[_s32]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svasr_wide%5B_s32%5D_x

### Signature (source notation)

```c
svint32_t svasr_wide[_s32]_x(svbool_t pg, svint32_t op1, svuint64_t op2);
```

### Description

Arithmetic shift right

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
ASR Ztied1.S, Pg/M, Ztied1.S, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ASR--wide-elements--predicated---Arithmetic-shift-right-by-64-bit-wide-elements--predicated--

This intrinsic compiles to:

```asm
ASR Zresult.S, Zop1.S, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ASR--wide-elements--unpredicated---Arithmetic-shift-right-by-64-bit-wide-elements--unpredicated--

### Operation

Source operation ID: `SveOperation_svasr_wide_s32_x`

**Operation**



Return a vector in which each active element *i* contains `op1[i]` divided by 2 to the power `op2[i/2]`, with the result rounded towards -∞.  All bits of the `op2` value are significant.



The inactive elements of the result have arbitrary, undefined values.

## svasr_wide[_s32]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svasr_wide%5B_s32%5D_z

### Signature (source notation)

```c
svint32_t svasr_wide[_s32]_z(svbool_t pg, svint32_t op1, svuint64_t op2);
```

### Description

Arithmetic shift right

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
ASR Zresult.S, Pg/M, Zresult.S, Zop2.D  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ASR--wide-elements--predicated---Arithmetic-shift-right-by-64-bit-wide-elements--predicated--

### Operation

Source operation ID: `SveOperation_svasr_wide_s32_z`

**Operation**



Return a vector in which each active element *i* contains `op1[i]` divided by 2 to the power `op2[i/2]`, with the result rounded towards -∞.  All bits of the `op2` value are significant.



Set the inactive elements of the result to zero.



**[1]** Note that `result` must be in a different register from `op2`

## svasr_wide[_s8]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svasr_wide%5B_s8%5D_m

### Signature (source notation)

```c
svint8_t svasr_wide[_s8]_m(svbool_t pg, svint8_t op1, svuint64_t op2);
```

### Description

Arithmetic shift right

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
ASR Ztied1.B, Pg/M, Ztied1.B, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ASR--wide-elements--predicated---Arithmetic-shift-right-by-64-bit-wide-elements--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
ASR Zresult.B, Pg/M, Zresult.B, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ASR--wide-elements--predicated---Arithmetic-shift-right-by-64-bit-wide-elements--predicated--

### Operation

Source operation ID: `SveOperation_svasr_wide_s8_m`

**Operation**



Return a vector in which each active element *i* contains `op1[i]` divided by 2 to the power `op2[i/8]`, with the result rounded towards -∞.  All bits of the `op2` value are significant.



Take the inactive elements of the result from the corresponding elements of `op1`.

## svasr_wide[_s8]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svasr_wide%5B_s8%5D_x

### Signature (source notation)

```c
svint8_t svasr_wide[_s8]_x(svbool_t pg, svint8_t op1, svuint64_t op2);
```

### Description

Arithmetic shift right

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
ASR Ztied1.B, Pg/M, Ztied1.B, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ASR--wide-elements--predicated---Arithmetic-shift-right-by-64-bit-wide-elements--predicated--

This intrinsic compiles to:

```asm
ASR Zresult.B, Zop1.B, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ASR--wide-elements--unpredicated---Arithmetic-shift-right-by-64-bit-wide-elements--unpredicated--

### Operation

Source operation ID: `SveOperation_svasr_wide_s8_x`

**Operation**



Return a vector in which each active element *i* contains `op1[i]` divided by 2 to the power `op2[i/8]`, with the result rounded towards -∞.  All bits of the `op2` value are significant.



The inactive elements of the result have arbitrary, undefined values.

## svasr_wide[_s8]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svasr_wide%5B_s8%5D_z

### Signature (source notation)

```c
svint8_t svasr_wide[_s8]_z(svbool_t pg, svint8_t op1, svuint64_t op2);
```

### Description

Arithmetic shift right

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
ASR Zresult.B, Pg/M, Zresult.B, Zop2.D  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ASR--wide-elements--predicated---Arithmetic-shift-right-by-64-bit-wide-elements--predicated--

### Operation

Source operation ID: `SveOperation_svasr_wide_s8_z`

**Operation**



Return a vector in which each active element *i* contains `op1[i]` divided by 2 to the power `op2[i/8]`, with the result rounded towards -∞.  All bits of the `op2` value are significant.



Set the inactive elements of the result to zero.



**[1]** Note that `result` must be in a different register from `op2`

## svasrd[_n_s16]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svasrd%5B_n_s16%5D_m

### Signature (source notation)

```c
svint16_t svasrd[_n_s16]_m(svbool_t pg, svint16_t op1, uint64_t imm2);
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
  "imm2": {
    "minimum": 1,
    "maximum": 16
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
ASRD Ztied1.H, Pg/M, Ztied1.H, #imm2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ASRD--Arithmetic-shift-right-for-divide-by-immediate--predicated--

When result and op1 are in different registers, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
ASRD Zresult.H, Pg/M, Zresult.H, #imm2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ASRD--Arithmetic-shift-right-for-divide-by-immediate--predicated--

### Operation

Source operation ID: `SveOperation_svasrd_n_s8_m`

**Operation**



Return a vector in which each active element *i* contains `op1[i]` divided by 2 to the power `imm2`, with the result rounded towards zero (as for integer division in C).



Take the inactive elements of the result from the corresponding elements of `op1`.

## svasrd[_n_s16]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svasrd%5B_n_s16%5D_x

### Signature (source notation)

```c
svint16_t svasrd[_n_s16]_x(svbool_t pg, svint16_t op1, uint64_t imm2);
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
  "imm2": {
    "minimum": 1,
    "maximum": 16
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
ASRD Ztied1.H, Pg/M, Ztied1.H, #imm2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ASRD--Arithmetic-shift-right-for-divide-by-immediate--predicated--

When result and op1 are in different registers, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
ASRD Zresult.H, Pg/M, Zresult.H, #imm2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ASRD--Arithmetic-shift-right-for-divide-by-immediate--predicated--

### Operation

Source operation ID: `SveOperation_svasrd_n_s8_x`

**Operation**



Return a vector in which each active element *i* contains `op1[i]` divided by 2 to the power `imm2`, with the result rounded towards zero (as for integer division in C).



The inactive elements of the result have arbitrary, undefined values.

## svasrd[_n_s16]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svasrd%5B_n_s16%5D_z

### Signature (source notation)

```c
svint16_t svasrd[_n_s16]_z(svbool_t pg, svint16_t op1, uint64_t imm2);
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
  "imm2": {
    "minimum": 1,
    "maximum": 16
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
ASRD Zresult.H, Pg/M, Zresult.H, #imm2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ASRD--Arithmetic-shift-right-for-divide-by-immediate--predicated--

### Operation

Source operation ID: `SveOperation_svasrd_n_s8_z`

**Operation**



Return a vector in which each active element *i* contains `op1[i]` divided by 2 to the power `imm2`, with the result rounded towards zero (as for integer division in C).



Set the inactive elements of the result to zero.

## svasrd[_n_s32]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svasrd%5B_n_s32%5D_m

### Signature (source notation)

```c
svint32_t svasrd[_n_s32]_m(svbool_t pg, svint32_t op1, uint64_t imm2);
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
  "imm2": {
    "minimum": 1,
    "maximum": 32
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
ASRD Ztied1.S, Pg/M, Ztied1.S, #imm2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ASRD--Arithmetic-shift-right-for-divide-by-immediate--predicated--

When result and op1 are in different registers, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
ASRD Zresult.S, Pg/M, Zresult.S, #imm2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ASRD--Arithmetic-shift-right-for-divide-by-immediate--predicated--

### Operation

Source operation ID: `SveOperation_svasrd_n_s8_m`

**Operation**



Return a vector in which each active element *i* contains `op1[i]` divided by 2 to the power `imm2`, with the result rounded towards zero (as for integer division in C).



Take the inactive elements of the result from the corresponding elements of `op1`.

## svasrd[_n_s32]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svasrd%5B_n_s32%5D_x

### Signature (source notation)

```c
svint32_t svasrd[_n_s32]_x(svbool_t pg, svint32_t op1, uint64_t imm2);
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
  "imm2": {
    "minimum": 1,
    "maximum": 32
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
ASRD Ztied1.S, Pg/M, Ztied1.S, #imm2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ASRD--Arithmetic-shift-right-for-divide-by-immediate--predicated--

When result and op1 are in different registers, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
ASRD Zresult.S, Pg/M, Zresult.S, #imm2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ASRD--Arithmetic-shift-right-for-divide-by-immediate--predicated--

### Operation

Source operation ID: `SveOperation_svasrd_n_s8_x`

**Operation**



Return a vector in which each active element *i* contains `op1[i]` divided by 2 to the power `imm2`, with the result rounded towards zero (as for integer division in C).



The inactive elements of the result have arbitrary, undefined values.

## svasrd[_n_s32]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svasrd%5B_n_s32%5D_z

### Signature (source notation)

```c
svint32_t svasrd[_n_s32]_z(svbool_t pg, svint32_t op1, uint64_t imm2);
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
  "imm2": {
    "minimum": 1,
    "maximum": 32
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
ASRD Zresult.S, Pg/M, Zresult.S, #imm2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ASRD--Arithmetic-shift-right-for-divide-by-immediate--predicated--

### Operation

Source operation ID: `SveOperation_svasrd_n_s8_z`

**Operation**



Return a vector in which each active element *i* contains `op1[i]` divided by 2 to the power `imm2`, with the result rounded towards zero (as for integer division in C).



Set the inactive elements of the result to zero.

## svasrd[_n_s64]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svasrd%5B_n_s64%5D_m

### Signature (source notation)

```c
svint64_t svasrd[_n_s64]_m(svbool_t pg, svint64_t op1, uint64_t imm2);
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
    "register": "Zop1.D|Ztied1.D"
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
    "Zresult.D|Ztied1.D": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
ASRD Ztied1.D, Pg/M, Ztied1.D, #imm2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ASRD--Arithmetic-shift-right-for-divide-by-immediate--predicated--

When result and op1 are in different registers, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
ASRD Zresult.D, Pg/M, Zresult.D, #imm2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ASRD--Arithmetic-shift-right-for-divide-by-immediate--predicated--

### Operation

Source operation ID: `SveOperation_svasrd_n_s8_m`

**Operation**



Return a vector in which each active element *i* contains `op1[i]` divided by 2 to the power `imm2`, with the result rounded towards zero (as for integer division in C).



Take the inactive elements of the result from the corresponding elements of `op1`.

## svasrd[_n_s64]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svasrd%5B_n_s64%5D_x

### Signature (source notation)

```c
svint64_t svasrd[_n_s64]_x(svbool_t pg, svint64_t op1, uint64_t imm2);
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
    "register": "Zop1.D|Ztied1.D"
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
    "Zresult.D|Ztied1.D": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
ASRD Ztied1.D, Pg/M, Ztied1.D, #imm2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ASRD--Arithmetic-shift-right-for-divide-by-immediate--predicated--

When result and op1 are in different registers, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
ASRD Zresult.D, Pg/M, Zresult.D, #imm2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ASRD--Arithmetic-shift-right-for-divide-by-immediate--predicated--

### Operation

Source operation ID: `SveOperation_svasrd_n_s8_x`

**Operation**



Return a vector in which each active element *i* contains `op1[i]` divided by 2 to the power `imm2`, with the result rounded towards zero (as for integer division in C).



The inactive elements of the result have arbitrary, undefined values.

