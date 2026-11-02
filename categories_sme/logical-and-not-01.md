# SME / Logical / AND-NOT — Part 1

## svbic[_b]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svbic%5B_b%5D_z

### Signature (source notation)

```c
svbool_t svbic[_b]_z(svbool_t pg, svbool_t op1, svbool_t op2);
```

### Description

Bitwise clear

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / AND-NOT

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME
```

### Return type metadata

```json
{
  "return_base_type": "bool",
  "element_bit_size": "8",
  "value": "svbool_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Pg"
  },
  "op1": {
    "register": "Pop1.B"
  },
  "op2": {
    "register": "Pop2.B"
  }
}
```

### Result mapping

```json
[
  {
    "Presult.B": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
BIC Presult.B, Pg/Z, Pop1.B, Pop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BIC--predicates---Bitwise-clear-predicates-

### Operation

Source operation ID: `SveOperation_svbic_b_z`

**Operation**



Return a predicate in which each active element *i* contains `op1[i] & ~op2[i]`. Set the inactive elements of the result to zero.

## svbic[_n_s16]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svbic%5B_n_s16%5D_m

### Signature (source notation)

```c
svint16_t svbic[_n_s16]_m(svbool_t pg, svint16_t op1, int16_t op2);
```

### Description

Bitwise clear

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / AND-NOT

- SME attributes: Not specified by source.

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
BIC Ztied1.H, Pg/M, Ztied1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BIC--vectors--predicated---Bitwise-clear--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
BIC Zresult.H, Pg/M, Zresult.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BIC--vectors--predicated---Bitwise-clear--predicated--

### Operation

Source operation ID: `SveOperation_svbic_n_s8_m`

**Operation**



Return a vector in which each active element *i* contains `op1[i] & ~op2`. Take the inactive elements of the result from the corresponding elements of `op1`.

## svbic[_n_s16]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svbic%5B_n_s16%5D_x

### Signature (source notation)

```c
svint16_t svbic[_n_s16]_x(svbool_t pg, svint16_t op1, int16_t op2);
```

### Description

Bitwise clear

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / AND-NOT

- SME attributes: Not specified by source.

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

When ~op2 is a logical immediate[1], this intrinsic can use:

```asm
AND Ztied1.H, Ztied1.H, #~op2  // [2]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/AND--immediate---Bitwise-AND-with-immediate--unpredicated--

When result and op1 are in the same register, this intrinsic can use:

```asm
BIC Ztied1.H, Pg/M, Ztied1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BIC--vectors--predicated---Bitwise-clear--predicated--

The general implementation is:

```asm
BIC Zresult.D, Zop1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BIC--vectors--unpredicated---Bitwise-clear--unpredicated--

### Operation

Source operation ID: `SveOperation_svbic_n_s8_x`

**Operation**



Return a vector in which each active element *i* contains `op1[i] & ~op2`. The inactive elements of the result have arbitrary, undefined values.



**[1]** This is true if ~op2 is filled by some replicated bitmask *b* for which either all 0s in *b* are consecutive or all 1s in *b* are consecutive.



**[2]** If instead `result` is in a different register from the inputs, the compiler can add a preceding [MOVPRFX (unpredicated)](https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--) instruction

## svbic[_n_s16]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svbic%5B_n_s16%5D_z

### Signature (source notation)

```c
svint16_t svbic[_n_s16]_z(svbool_t pg, svint16_t op1, int16_t op2);
```

### Description

Bitwise clear

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / AND-NOT

- SME attributes: Not specified by source.

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

This intrinsic compiles to the following instructions, or functionally equivalent instructions:

```asm
MOVPRFX Zresult.H, Pg/Z, Zop1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
BIC Zresult.H, Pg/M, Zresult.H, Zop2.H  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BIC--vectors--predicated---Bitwise-clear--predicated--

### Operation

Source operation ID: `SveOperation_svbic_n_s8_z`

**Operation**



Return a vector in which each active element *i* contains `op1[i] & ~op2`. Set the inactive elements of the result to zero.



**[1]** Note that `result` must be in a different register from `op2`

## svbic[_n_s32]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svbic%5B_n_s32%5D_m

### Signature (source notation)

```c
svint32_t svbic[_n_s32]_m(svbool_t pg, svint32_t op1, int32_t op2);
```

### Description

Bitwise clear

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / AND-NOT

- SME attributes: Not specified by source.

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
BIC Ztied1.S, Pg/M, Ztied1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BIC--vectors--predicated---Bitwise-clear--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
BIC Zresult.S, Pg/M, Zresult.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BIC--vectors--predicated---Bitwise-clear--predicated--

### Operation

Source operation ID: `SveOperation_svbic_n_s8_m`

**Operation**



Return a vector in which each active element *i* contains `op1[i] & ~op2`. Take the inactive elements of the result from the corresponding elements of `op1`.

## svbic[_n_s32]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svbic%5B_n_s32%5D_x

### Signature (source notation)

```c
svint32_t svbic[_n_s32]_x(svbool_t pg, svint32_t op1, int32_t op2);
```

### Description

Bitwise clear

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / AND-NOT

- SME attributes: Not specified by source.

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

When ~op2 is a logical immediate[1], this intrinsic can use:

```asm
AND Ztied1.S, Ztied1.S, #~op2  // [2]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/AND--immediate---Bitwise-AND-with-immediate--unpredicated--

When result and op1 are in the same register, this intrinsic can use:

```asm
BIC Ztied1.S, Pg/M, Ztied1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BIC--vectors--predicated---Bitwise-clear--predicated--

The general implementation is:

```asm
BIC Zresult.D, Zop1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BIC--vectors--unpredicated---Bitwise-clear--unpredicated--

### Operation

Source operation ID: `SveOperation_svbic_n_s8_x`

**Operation**



Return a vector in which each active element *i* contains `op1[i] & ~op2`. The inactive elements of the result have arbitrary, undefined values.



**[1]** This is true if ~op2 is filled by some replicated bitmask *b* for which either all 0s in *b* are consecutive or all 1s in *b* are consecutive.



**[2]** If instead `result` is in a different register from the inputs, the compiler can add a preceding [MOVPRFX (unpredicated)](https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--) instruction

## svbic[_n_s32]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svbic%5B_n_s32%5D_z

### Signature (source notation)

```c
svint32_t svbic[_n_s32]_z(svbool_t pg, svint32_t op1, int32_t op2);
```

### Description

Bitwise clear

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / AND-NOT

- SME attributes: Not specified by source.

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

This intrinsic compiles to the following instructions, or functionally equivalent instructions:

```asm
MOVPRFX Zresult.S, Pg/Z, Zop1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
BIC Zresult.S, Pg/M, Zresult.S, Zop2.S  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BIC--vectors--predicated---Bitwise-clear--predicated--

### Operation

Source operation ID: `SveOperation_svbic_n_s8_z`

**Operation**



Return a vector in which each active element *i* contains `op1[i] & ~op2`. Set the inactive elements of the result to zero.



**[1]** Note that `result` must be in a different register from `op2`

## svbic[_n_s64]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svbic%5B_n_s64%5D_m

### Signature (source notation)

```c
svint64_t svbic[_n_s64]_m(svbool_t pg, svint64_t op1, int64_t op2);
```

### Description

Bitwise clear

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / AND-NOT

- SME attributes: Not specified by source.

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
BIC Ztied1.D, Pg/M, Ztied1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BIC--vectors--predicated---Bitwise-clear--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
BIC Zresult.D, Pg/M, Zresult.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BIC--vectors--predicated---Bitwise-clear--predicated--

### Operation

Source operation ID: `SveOperation_svbic_n_s8_m`

**Operation**



Return a vector in which each active element *i* contains `op1[i] & ~op2`. Take the inactive elements of the result from the corresponding elements of `op1`.

## svbic[_n_s64]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svbic%5B_n_s64%5D_x

### Signature (source notation)

```c
svint64_t svbic[_n_s64]_x(svbool_t pg, svint64_t op1, int64_t op2);
```

### Description

Bitwise clear

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / AND-NOT

- SME attributes: Not specified by source.

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

When ~op2 is a logical immediate[1], this intrinsic can use:

```asm
AND Ztied1.D, Ztied1.D, #~op2  // [2]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/AND--immediate---Bitwise-AND-with-immediate--unpredicated--

When result and op1 are in the same register, this intrinsic can use:

```asm
BIC Ztied1.D, Pg/M, Ztied1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BIC--vectors--predicated---Bitwise-clear--predicated--

The general implementation is:

```asm
BIC Zresult.D, Zop1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BIC--vectors--unpredicated---Bitwise-clear--unpredicated--

### Operation

Source operation ID: `SveOperation_svbic_n_s8_x`

**Operation**



Return a vector in which each active element *i* contains `op1[i] & ~op2`. The inactive elements of the result have arbitrary, undefined values.



**[1]** This is true if ~op2 is filled by some replicated bitmask *b* for which either all 0s in *b* are consecutive or all 1s in *b* are consecutive.



**[2]** If instead `result` is in a different register from the inputs, the compiler can add a preceding [MOVPRFX (unpredicated)](https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--) instruction

## svbic[_n_s64]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svbic%5B_n_s64%5D_z

### Signature (source notation)

```c
svint64_t svbic[_n_s64]_z(svbool_t pg, svint64_t op1, int64_t op2);
```

### Description

Bitwise clear

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / AND-NOT

- SME attributes: Not specified by source.

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

This intrinsic compiles to the following instructions, or functionally equivalent instructions:

```asm
MOVPRFX Zresult.D, Pg/Z, Zop1.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
BIC Zresult.D, Pg/M, Zresult.D, Zop2.D  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BIC--vectors--predicated---Bitwise-clear--predicated--

### Operation

Source operation ID: `SveOperation_svbic_n_s8_z`

**Operation**



Return a vector in which each active element *i* contains `op1[i] & ~op2`. Set the inactive elements of the result to zero.



**[1]** Note that `result` must be in a different register from `op2`

## svbic[_n_s8]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svbic%5B_n_s8%5D_m

### Signature (source notation)

```c
svint8_t svbic[_n_s8]_m(svbool_t pg, svint8_t op1, int8_t op2);
```

### Description

Bitwise clear

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / AND-NOT

- SME attributes: Not specified by source.

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
BIC Ztied1.B, Pg/M, Ztied1.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BIC--vectors--predicated---Bitwise-clear--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
BIC Zresult.B, Pg/M, Zresult.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BIC--vectors--predicated---Bitwise-clear--predicated--

### Operation

Source operation ID: `SveOperation_svbic_n_s8_m`

**Operation**



Return a vector in which each active element *i* contains `op1[i] & ~op2`. Take the inactive elements of the result from the corresponding elements of `op1`.

## svbic[_n_s8]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svbic%5B_n_s8%5D_x

### Signature (source notation)

```c
svint8_t svbic[_n_s8]_x(svbool_t pg, svint8_t op1, int8_t op2);
```

### Description

Bitwise clear

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / AND-NOT

- SME attributes: Not specified by source.

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

When ~op2 is a logical immediate[1], this intrinsic can use:

```asm
AND Ztied1.B, Ztied1.B, #~op2  // [2]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/AND--immediate---Bitwise-AND-with-immediate--unpredicated--

When result and op1 are in the same register, this intrinsic can use:

```asm
BIC Ztied1.B, Pg/M, Ztied1.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BIC--vectors--predicated---Bitwise-clear--predicated--

The general implementation is:

```asm
BIC Zresult.D, Zop1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BIC--vectors--unpredicated---Bitwise-clear--unpredicated--

### Operation

Source operation ID: `SveOperation_svbic_n_s8_x`

**Operation**



Return a vector in which each active element *i* contains `op1[i] & ~op2`. The inactive elements of the result have arbitrary, undefined values.



**[1]** This is true if ~op2 is filled by some replicated bitmask *b* for which either all 0s in *b* are consecutive or all 1s in *b* are consecutive.



**[2]** If instead `result` is in a different register from the inputs, the compiler can add a preceding [MOVPRFX (unpredicated)](https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--) instruction

## svbic[_n_s8]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svbic%5B_n_s8%5D_z

### Signature (source notation)

```c
svint8_t svbic[_n_s8]_z(svbool_t pg, svint8_t op1, int8_t op2);
```

### Description

Bitwise clear

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / AND-NOT

- SME attributes: Not specified by source.

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

This intrinsic compiles to the following instructions, or functionally equivalent instructions:

```asm
MOVPRFX Zresult.B, Pg/Z, Zop1.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
BIC Zresult.B, Pg/M, Zresult.B, Zop2.B  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BIC--vectors--predicated---Bitwise-clear--predicated--

### Operation

Source operation ID: `SveOperation_svbic_n_s8_z`

**Operation**



Return a vector in which each active element *i* contains `op1[i] & ~op2`. Set the inactive elements of the result to zero.



**[1]** Note that `result` must be in a different register from `op2`

## svbic[_n_u16]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svbic%5B_n_u16%5D_m

### Signature (source notation)

```c
svuint16_t svbic[_n_u16]_m(svbool_t pg, svuint16_t op1, uint16_t op2);
```

### Description

Bitwise clear

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / AND-NOT

- SME attributes: Not specified by source.

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
BIC Ztied1.H, Pg/M, Ztied1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BIC--vectors--predicated---Bitwise-clear--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
BIC Zresult.H, Pg/M, Zresult.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BIC--vectors--predicated---Bitwise-clear--predicated--

### Operation

Source operation ID: `SveOperation_svbic_n_s8_m`

**Operation**



Return a vector in which each active element *i* contains `op1[i] & ~op2`. Take the inactive elements of the result from the corresponding elements of `op1`.

## svbic[_n_u16]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svbic%5B_n_u16%5D_x

### Signature (source notation)

```c
svuint16_t svbic[_n_u16]_x(svbool_t pg, svuint16_t op1, uint16_t op2);
```

### Description

Bitwise clear

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / AND-NOT

- SME attributes: Not specified by source.

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

When ~op2 is a logical immediate[1], this intrinsic can use:

```asm
AND Ztied1.H, Ztied1.H, #~op2  // [2]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/AND--immediate---Bitwise-AND-with-immediate--unpredicated--

When result and op1 are in the same register, this intrinsic can use:

```asm
BIC Ztied1.H, Pg/M, Ztied1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BIC--vectors--predicated---Bitwise-clear--predicated--

The general implementation is:

```asm
BIC Zresult.D, Zop1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BIC--vectors--unpredicated---Bitwise-clear--unpredicated--

### Operation

Source operation ID: `SveOperation_svbic_n_s8_x`

**Operation**



Return a vector in which each active element *i* contains `op1[i] & ~op2`. The inactive elements of the result have arbitrary, undefined values.



**[1]** This is true if ~op2 is filled by some replicated bitmask *b* for which either all 0s in *b* are consecutive or all 1s in *b* are consecutive.



**[2]** If instead `result` is in a different register from the inputs, the compiler can add a preceding [MOVPRFX (unpredicated)](https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--) instruction

## svbic[_n_u16]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svbic%5B_n_u16%5D_z

### Signature (source notation)

```c
svuint16_t svbic[_n_u16]_z(svbool_t pg, svuint16_t op1, uint16_t op2);
```

### Description

Bitwise clear

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / AND-NOT

- SME attributes: Not specified by source.

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

This intrinsic compiles to the following instructions, or functionally equivalent instructions:

```asm
MOVPRFX Zresult.H, Pg/Z, Zop1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
BIC Zresult.H, Pg/M, Zresult.H, Zop2.H  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BIC--vectors--predicated---Bitwise-clear--predicated--

### Operation

Source operation ID: `SveOperation_svbic_n_s8_z`

**Operation**



Return a vector in which each active element *i* contains `op1[i] & ~op2`. Set the inactive elements of the result to zero.



**[1]** Note that `result` must be in a different register from `op2`

## svbic[_n_u32]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svbic%5B_n_u32%5D_m

### Signature (source notation)

```c
svuint32_t svbic[_n_u32]_m(svbool_t pg, svuint32_t op1, uint32_t op2);
```

### Description

Bitwise clear

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / AND-NOT

- SME attributes: Not specified by source.

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
BIC Ztied1.S, Pg/M, Ztied1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BIC--vectors--predicated---Bitwise-clear--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
BIC Zresult.S, Pg/M, Zresult.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BIC--vectors--predicated---Bitwise-clear--predicated--

### Operation

Source operation ID: `SveOperation_svbic_n_s8_m`

**Operation**



Return a vector in which each active element *i* contains `op1[i] & ~op2`. Take the inactive elements of the result from the corresponding elements of `op1`.

## svbic[_n_u32]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svbic%5B_n_u32%5D_x

### Signature (source notation)

```c
svuint32_t svbic[_n_u32]_x(svbool_t pg, svuint32_t op1, uint32_t op2);
```

### Description

Bitwise clear

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / AND-NOT

- SME attributes: Not specified by source.

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

When ~op2 is a logical immediate[1], this intrinsic can use:

```asm
AND Ztied1.S, Ztied1.S, #~op2  // [2]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/AND--immediate---Bitwise-AND-with-immediate--unpredicated--

When result and op1 are in the same register, this intrinsic can use:

```asm
BIC Ztied1.S, Pg/M, Ztied1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BIC--vectors--predicated---Bitwise-clear--predicated--

The general implementation is:

```asm
BIC Zresult.D, Zop1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BIC--vectors--unpredicated---Bitwise-clear--unpredicated--

### Operation

Source operation ID: `SveOperation_svbic_n_s8_x`

**Operation**



Return a vector in which each active element *i* contains `op1[i] & ~op2`. The inactive elements of the result have arbitrary, undefined values.



**[1]** This is true if ~op2 is filled by some replicated bitmask *b* for which either all 0s in *b* are consecutive or all 1s in *b* are consecutive.



**[2]** If instead `result` is in a different register from the inputs, the compiler can add a preceding [MOVPRFX (unpredicated)](https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--) instruction

## svbic[_n_u32]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svbic%5B_n_u32%5D_z

### Signature (source notation)

```c
svuint32_t svbic[_n_u32]_z(svbool_t pg, svuint32_t op1, uint32_t op2);
```

### Description

Bitwise clear

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / AND-NOT

- SME attributes: Not specified by source.

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

This intrinsic compiles to the following instructions, or functionally equivalent instructions:

```asm
MOVPRFX Zresult.S, Pg/Z, Zop1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
BIC Zresult.S, Pg/M, Zresult.S, Zop2.S  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BIC--vectors--predicated---Bitwise-clear--predicated--

### Operation

Source operation ID: `SveOperation_svbic_n_s8_z`

**Operation**



Return a vector in which each active element *i* contains `op1[i] & ~op2`. Set the inactive elements of the result to zero.



**[1]** Note that `result` must be in a different register from `op2`

## svbic[_n_u64]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svbic%5B_n_u64%5D_m

### Signature (source notation)

```c
svuint64_t svbic[_n_u64]_m(svbool_t pg, svuint64_t op1, uint64_t op2);
```

### Description

Bitwise clear

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / AND-NOT

- SME attributes: Not specified by source.

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
BIC Ztied1.D, Pg/M, Ztied1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BIC--vectors--predicated---Bitwise-clear--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
BIC Zresult.D, Pg/M, Zresult.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BIC--vectors--predicated---Bitwise-clear--predicated--

### Operation

Source operation ID: `SveOperation_svbic_n_s8_m`

**Operation**



Return a vector in which each active element *i* contains `op1[i] & ~op2`. Take the inactive elements of the result from the corresponding elements of `op1`.

## svbic[_n_u64]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svbic%5B_n_u64%5D_x

### Signature (source notation)

```c
svuint64_t svbic[_n_u64]_x(svbool_t pg, svuint64_t op1, uint64_t op2);
```

### Description

Bitwise clear

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / AND-NOT

- SME attributes: Not specified by source.

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

When ~op2 is a logical immediate[1], this intrinsic can use:

```asm
AND Ztied1.D, Ztied1.D, #~op2  // [2]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/AND--immediate---Bitwise-AND-with-immediate--unpredicated--

When result and op1 are in the same register, this intrinsic can use:

```asm
BIC Ztied1.D, Pg/M, Ztied1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BIC--vectors--predicated---Bitwise-clear--predicated--

The general implementation is:

```asm
BIC Zresult.D, Zop1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BIC--vectors--unpredicated---Bitwise-clear--unpredicated--

### Operation

Source operation ID: `SveOperation_svbic_n_s8_x`

**Operation**



Return a vector in which each active element *i* contains `op1[i] & ~op2`. The inactive elements of the result have arbitrary, undefined values.



**[1]** This is true if ~op2 is filled by some replicated bitmask *b* for which either all 0s in *b* are consecutive or all 1s in *b* are consecutive.



**[2]** If instead `result` is in a different register from the inputs, the compiler can add a preceding [MOVPRFX (unpredicated)](https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--) instruction

## svbic[_n_u64]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svbic%5B_n_u64%5D_z

### Signature (source notation)

```c
svuint64_t svbic[_n_u64]_z(svbool_t pg, svuint64_t op1, uint64_t op2);
```

### Description

Bitwise clear

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / AND-NOT

- SME attributes: Not specified by source.

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

This intrinsic compiles to the following instructions, or functionally equivalent instructions:

```asm
MOVPRFX Zresult.D, Pg/Z, Zop1.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
BIC Zresult.D, Pg/M, Zresult.D, Zop2.D  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BIC--vectors--predicated---Bitwise-clear--predicated--

### Operation

Source operation ID: `SveOperation_svbic_n_s8_z`

**Operation**



Return a vector in which each active element *i* contains `op1[i] & ~op2`. Set the inactive elements of the result to zero.



**[1]** Note that `result` must be in a different register from `op2`

## svbic[_n_u8]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svbic%5B_n_u8%5D_m

### Signature (source notation)

```c
svuint8_t svbic[_n_u8]_m(svbool_t pg, svuint8_t op1, uint8_t op2);
```

### Description

Bitwise clear

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / AND-NOT

- SME attributes: Not specified by source.

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
BIC Ztied1.B, Pg/M, Ztied1.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BIC--vectors--predicated---Bitwise-clear--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
BIC Zresult.B, Pg/M, Zresult.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BIC--vectors--predicated---Bitwise-clear--predicated--

### Operation

Source operation ID: `SveOperation_svbic_n_s8_m`

**Operation**



Return a vector in which each active element *i* contains `op1[i] & ~op2`. Take the inactive elements of the result from the corresponding elements of `op1`.

## svbic[_n_u8]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svbic%5B_n_u8%5D_x

### Signature (source notation)

```c
svuint8_t svbic[_n_u8]_x(svbool_t pg, svuint8_t op1, uint8_t op2);
```

### Description

Bitwise clear

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / AND-NOT

- SME attributes: Not specified by source.

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

When ~op2 is a logical immediate[1], this intrinsic can use:

```asm
AND Ztied1.B, Ztied1.B, #~op2  // [2]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/AND--immediate---Bitwise-AND-with-immediate--unpredicated--

When result and op1 are in the same register, this intrinsic can use:

```asm
BIC Ztied1.B, Pg/M, Ztied1.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BIC--vectors--predicated---Bitwise-clear--predicated--

The general implementation is:

```asm
BIC Zresult.D, Zop1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BIC--vectors--unpredicated---Bitwise-clear--unpredicated--

### Operation

Source operation ID: `SveOperation_svbic_n_s8_x`

**Operation**



Return a vector in which each active element *i* contains `op1[i] & ~op2`. The inactive elements of the result have arbitrary, undefined values.



**[1]** This is true if ~op2 is filled by some replicated bitmask *b* for which either all 0s in *b* are consecutive or all 1s in *b* are consecutive.



**[2]** If instead `result` is in a different register from the inputs, the compiler can add a preceding [MOVPRFX (unpredicated)](https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--) instruction

## svbic[_n_u8]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svbic%5B_n_u8%5D_z

### Signature (source notation)

```c
svuint8_t svbic[_n_u8]_z(svbool_t pg, svuint8_t op1, uint8_t op2);
```

### Description

Bitwise clear

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / AND-NOT

- SME attributes: Not specified by source.

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

This intrinsic compiles to the following instructions, or functionally equivalent instructions:

```asm
MOVPRFX Zresult.B, Pg/Z, Zop1.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
BIC Zresult.B, Pg/M, Zresult.B, Zop2.B  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BIC--vectors--predicated---Bitwise-clear--predicated--

### Operation

Source operation ID: `SveOperation_svbic_n_s8_z`

**Operation**



Return a vector in which each active element *i* contains `op1[i] & ~op2`. Set the inactive elements of the result to zero.



**[1]** Note that `result` must be in a different register from `op2`

## svbic[_s16]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svbic%5B_s16%5D_m

### Signature (source notation)

```c
svint16_t svbic[_s16]_m(svbool_t pg, svint16_t op1, svint16_t op2);
```

### Description

Bitwise clear

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / AND-NOT

- SME attributes: Not specified by source.

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
BIC Ztied1.H, Pg/M, Ztied1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BIC--vectors--predicated---Bitwise-clear--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
BIC Zresult.H, Pg/M, Zresult.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BIC--vectors--predicated---Bitwise-clear--predicated--

### Operation

Source operation ID: `SveOperation_svbic_s8_m`

**Operation**



Return a vector in which each active element *i* contains `op1[i] & ~op2[i]`. Take the inactive elements of the result from the corresponding elements of `op1`.

## svbic[_s16]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svbic%5B_s16%5D_x

### Signature (source notation)

```c
svint16_t svbic[_s16]_x(svbool_t pg, svint16_t op1, svint16_t op2);
```

### Description

Bitwise clear

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / AND-NOT

- SME attributes: Not specified by source.

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

When result and op1 are in the same register, this intrinsic can use:

```asm
BIC Ztied1.H, Pg/M, Ztied1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BIC--vectors--predicated---Bitwise-clear--predicated--

This intrinsic compiles to:

```asm
BIC Zresult.D, Zop1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BIC--vectors--unpredicated---Bitwise-clear--unpredicated--

### Operation

Source operation ID: `SveOperation_svbic_s8_x`

**Operation**



Return a vector in which each active element *i* contains `op1[i] & ~op2[i]`. The inactive elements of the result have arbitrary, undefined values.

## svbic[_s16]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svbic%5B_s16%5D_z

### Signature (source notation)

```c
svint16_t svbic[_s16]_z(svbool_t pg, svint16_t op1, svint16_t op2);
```

### Description

Bitwise clear

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / AND-NOT

- SME attributes: Not specified by source.

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
BIC Zresult.H, Pg/M, Zresult.H, Zop2.H  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BIC--vectors--predicated---Bitwise-clear--predicated--

### Operation

Source operation ID: `SveOperation_svbic_s8_z`

**Operation**



Return a vector in which each active element *i* contains `op1[i] & ~op2[i]`. Set the inactive elements of the result to zero.



**[1]** Note that `result` must be in a different register from `op2`

## svbic[_s32]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svbic%5B_s32%5D_m

### Signature (source notation)

```c
svint32_t svbic[_s32]_m(svbool_t pg, svint32_t op1, svint32_t op2);
```

### Description

Bitwise clear

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / AND-NOT

- SME attributes: Not specified by source.

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
BIC Ztied1.S, Pg/M, Ztied1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BIC--vectors--predicated---Bitwise-clear--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
BIC Zresult.S, Pg/M, Zresult.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BIC--vectors--predicated---Bitwise-clear--predicated--

### Operation

Source operation ID: `SveOperation_svbic_s8_m`

**Operation**



Return a vector in which each active element *i* contains `op1[i] & ~op2[i]`. Take the inactive elements of the result from the corresponding elements of `op1`.

## svbic[_s32]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svbic%5B_s32%5D_x

### Signature (source notation)

```c
svint32_t svbic[_s32]_x(svbool_t pg, svint32_t op1, svint32_t op2);
```

### Description

Bitwise clear

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / AND-NOT

- SME attributes: Not specified by source.

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

When result and op1 are in the same register, this intrinsic can use:

```asm
BIC Ztied1.S, Pg/M, Ztied1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BIC--vectors--predicated---Bitwise-clear--predicated--

This intrinsic compiles to:

```asm
BIC Zresult.D, Zop1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BIC--vectors--unpredicated---Bitwise-clear--unpredicated--

### Operation

Source operation ID: `SveOperation_svbic_s8_x`

**Operation**



Return a vector in which each active element *i* contains `op1[i] & ~op2[i]`. The inactive elements of the result have arbitrary, undefined values.

## svbic[_s32]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svbic%5B_s32%5D_z

### Signature (source notation)

```c
svint32_t svbic[_s32]_z(svbool_t pg, svint32_t op1, svint32_t op2);
```

### Description

Bitwise clear

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / AND-NOT

- SME attributes: Not specified by source.

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
BIC Zresult.S, Pg/M, Zresult.S, Zop2.S  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BIC--vectors--predicated---Bitwise-clear--predicated--

### Operation

Source operation ID: `SveOperation_svbic_s8_z`

**Operation**



Return a vector in which each active element *i* contains `op1[i] & ~op2[i]`. Set the inactive elements of the result to zero.



**[1]** Note that `result` must be in a different register from `op2`

## svbic[_s64]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svbic%5B_s64%5D_m

### Signature (source notation)

```c
svint64_t svbic[_s64]_m(svbool_t pg, svint64_t op1, svint64_t op2);
```

### Description

Bitwise clear

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / AND-NOT

- SME attributes: Not specified by source.

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
BIC Ztied1.D, Pg/M, Ztied1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BIC--vectors--predicated---Bitwise-clear--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
BIC Zresult.D, Pg/M, Zresult.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BIC--vectors--predicated---Bitwise-clear--predicated--

### Operation

Source operation ID: `SveOperation_svbic_s8_m`

**Operation**



Return a vector in which each active element *i* contains `op1[i] & ~op2[i]`. Take the inactive elements of the result from the corresponding elements of `op1`.

## svbic[_s64]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svbic%5B_s64%5D_x

### Signature (source notation)

```c
svint64_t svbic[_s64]_x(svbool_t pg, svint64_t op1, svint64_t op2);
```

### Description

Bitwise clear

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / AND-NOT

- SME attributes: Not specified by source.

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

When result and op1 are in the same register, this intrinsic can use:

```asm
BIC Ztied1.D, Pg/M, Ztied1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BIC--vectors--predicated---Bitwise-clear--predicated--

This intrinsic compiles to:

```asm
BIC Zresult.D, Zop1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BIC--vectors--unpredicated---Bitwise-clear--unpredicated--

### Operation

Source operation ID: `SveOperation_svbic_s8_x`

**Operation**



Return a vector in which each active element *i* contains `op1[i] & ~op2[i]`. The inactive elements of the result have arbitrary, undefined values.

## svbic[_s64]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svbic%5B_s64%5D_z

### Signature (source notation)

```c
svint64_t svbic[_s64]_z(svbool_t pg, svint64_t op1, svint64_t op2);
```

### Description

Bitwise clear

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / AND-NOT

- SME attributes: Not specified by source.

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
BIC Zresult.D, Pg/M, Zresult.D, Zop2.D  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BIC--vectors--predicated---Bitwise-clear--predicated--

### Operation

Source operation ID: `SveOperation_svbic_s8_z`

**Operation**



Return a vector in which each active element *i* contains `op1[i] & ~op2[i]`. Set the inactive elements of the result to zero.



**[1]** Note that `result` must be in a different register from `op2`

## svbic[_s8]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svbic%5B_s8%5D_m

### Signature (source notation)

```c
svint8_t svbic[_s8]_m(svbool_t pg, svint8_t op1, svint8_t op2);
```

### Description

Bitwise clear

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / AND-NOT

- SME attributes: Not specified by source.

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
BIC Ztied1.B, Pg/M, Ztied1.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BIC--vectors--predicated---Bitwise-clear--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
BIC Zresult.B, Pg/M, Zresult.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BIC--vectors--predicated---Bitwise-clear--predicated--

### Operation

Source operation ID: `SveOperation_svbic_s8_m`

**Operation**



Return a vector in which each active element *i* contains `op1[i] & ~op2[i]`. Take the inactive elements of the result from the corresponding elements of `op1`.

## svbic[_s8]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svbic%5B_s8%5D_x

### Signature (source notation)

```c
svint8_t svbic[_s8]_x(svbool_t pg, svint8_t op1, svint8_t op2);
```

### Description

Bitwise clear

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / AND-NOT

- SME attributes: Not specified by source.

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

When result and op1 are in the same register, this intrinsic can use:

```asm
BIC Ztied1.B, Pg/M, Ztied1.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BIC--vectors--predicated---Bitwise-clear--predicated--

This intrinsic compiles to:

```asm
BIC Zresult.D, Zop1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BIC--vectors--unpredicated---Bitwise-clear--unpredicated--

### Operation

Source operation ID: `SveOperation_svbic_s8_x`

**Operation**



Return a vector in which each active element *i* contains `op1[i] & ~op2[i]`. The inactive elements of the result have arbitrary, undefined values.

## svbic[_s8]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svbic%5B_s8%5D_z

### Signature (source notation)

```c
svint8_t svbic[_s8]_z(svbool_t pg, svint8_t op1, svint8_t op2);
```

### Description

Bitwise clear

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / AND-NOT

- SME attributes: Not specified by source.

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
BIC Zresult.B, Pg/M, Zresult.B, Zop2.B  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BIC--vectors--predicated---Bitwise-clear--predicated--

### Operation

Source operation ID: `SveOperation_svbic_s8_z`

**Operation**



Return a vector in which each active element *i* contains `op1[i] & ~op2[i]`. Set the inactive elements of the result to zero.



**[1]** Note that `result` must be in a different register from `op2`

## svbic[_u16]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svbic%5B_u16%5D_m

### Signature (source notation)

```c
svuint16_t svbic[_u16]_m(svbool_t pg, svuint16_t op1, svuint16_t op2);
```

### Description

Bitwise clear

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / AND-NOT

- SME attributes: Not specified by source.

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
BIC Ztied1.H, Pg/M, Ztied1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BIC--vectors--predicated---Bitwise-clear--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
BIC Zresult.H, Pg/M, Zresult.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BIC--vectors--predicated---Bitwise-clear--predicated--

### Operation

Source operation ID: `SveOperation_svbic_s8_m`

**Operation**



Return a vector in which each active element *i* contains `op1[i] & ~op2[i]`. Take the inactive elements of the result from the corresponding elements of `op1`.

## svbic[_u16]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svbic%5B_u16%5D_x

### Signature (source notation)

```c
svuint16_t svbic[_u16]_x(svbool_t pg, svuint16_t op1, svuint16_t op2);
```

### Description

Bitwise clear

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / AND-NOT

- SME attributes: Not specified by source.

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

When result and op1 are in the same register, this intrinsic can use:

```asm
BIC Ztied1.H, Pg/M, Ztied1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BIC--vectors--predicated---Bitwise-clear--predicated--

This intrinsic compiles to:

```asm
BIC Zresult.D, Zop1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BIC--vectors--unpredicated---Bitwise-clear--unpredicated--

### Operation

Source operation ID: `SveOperation_svbic_s8_x`

**Operation**



Return a vector in which each active element *i* contains `op1[i] & ~op2[i]`. The inactive elements of the result have arbitrary, undefined values.

## svbic[_u16]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svbic%5B_u16%5D_z

### Signature (source notation)

```c
svuint16_t svbic[_u16]_z(svbool_t pg, svuint16_t op1, svuint16_t op2);
```

### Description

Bitwise clear

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / AND-NOT

- SME attributes: Not specified by source.

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

This intrinsic compiles to the following instructions, or functionally equivalent instructions:

```asm
MOVPRFX Zresult.H, Pg/Z, Zop1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
BIC Zresult.H, Pg/M, Zresult.H, Zop2.H  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BIC--vectors--predicated---Bitwise-clear--predicated--

### Operation

Source operation ID: `SveOperation_svbic_s8_z`

**Operation**



Return a vector in which each active element *i* contains `op1[i] & ~op2[i]`. Set the inactive elements of the result to zero.



**[1]** Note that `result` must be in a different register from `op2`

## svbic[_u32]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svbic%5B_u32%5D_m

### Signature (source notation)

```c
svuint32_t svbic[_u32]_m(svbool_t pg, svuint32_t op1, svuint32_t op2);
```

### Description

Bitwise clear

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / AND-NOT

- SME attributes: Not specified by source.

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
BIC Ztied1.S, Pg/M, Ztied1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BIC--vectors--predicated---Bitwise-clear--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
BIC Zresult.S, Pg/M, Zresult.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BIC--vectors--predicated---Bitwise-clear--predicated--

### Operation

Source operation ID: `SveOperation_svbic_s8_m`

**Operation**



Return a vector in which each active element *i* contains `op1[i] & ~op2[i]`. Take the inactive elements of the result from the corresponding elements of `op1`.

## svbic[_u32]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svbic%5B_u32%5D_x

### Signature (source notation)

```c
svuint32_t svbic[_u32]_x(svbool_t pg, svuint32_t op1, svuint32_t op2);
```

### Description

Bitwise clear

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / AND-NOT

- SME attributes: Not specified by source.

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

When result and op1 are in the same register, this intrinsic can use:

```asm
BIC Ztied1.S, Pg/M, Ztied1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BIC--vectors--predicated---Bitwise-clear--predicated--

This intrinsic compiles to:

```asm
BIC Zresult.D, Zop1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BIC--vectors--unpredicated---Bitwise-clear--unpredicated--

### Operation

Source operation ID: `SveOperation_svbic_s8_x`

**Operation**



Return a vector in which each active element *i* contains `op1[i] & ~op2[i]`. The inactive elements of the result have arbitrary, undefined values.

## svbic[_u32]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svbic%5B_u32%5D_z

### Signature (source notation)

```c
svuint32_t svbic[_u32]_z(svbool_t pg, svuint32_t op1, svuint32_t op2);
```

### Description

Bitwise clear

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / AND-NOT

- SME attributes: Not specified by source.

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

This intrinsic compiles to the following instructions, or functionally equivalent instructions:

```asm
MOVPRFX Zresult.S, Pg/Z, Zop1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
BIC Zresult.S, Pg/M, Zresult.S, Zop2.S  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BIC--vectors--predicated---Bitwise-clear--predicated--

### Operation

Source operation ID: `SveOperation_svbic_s8_z`

**Operation**



Return a vector in which each active element *i* contains `op1[i] & ~op2[i]`. Set the inactive elements of the result to zero.



**[1]** Note that `result` must be in a different register from `op2`

## svbic[_u64]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svbic%5B_u64%5D_m

### Signature (source notation)

```c
svuint64_t svbic[_u64]_m(svbool_t pg, svuint64_t op1, svuint64_t op2);
```

### Description

Bitwise clear

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / AND-NOT

- SME attributes: Not specified by source.

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
BIC Ztied1.D, Pg/M, Ztied1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BIC--vectors--predicated---Bitwise-clear--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
BIC Zresult.D, Pg/M, Zresult.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BIC--vectors--predicated---Bitwise-clear--predicated--

### Operation

Source operation ID: `SveOperation_svbic_s8_m`

**Operation**



Return a vector in which each active element *i* contains `op1[i] & ~op2[i]`. Take the inactive elements of the result from the corresponding elements of `op1`.

## svbic[_u64]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svbic%5B_u64%5D_x

### Signature (source notation)

```c
svuint64_t svbic[_u64]_x(svbool_t pg, svuint64_t op1, svuint64_t op2);
```

### Description

Bitwise clear

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / AND-NOT

- SME attributes: Not specified by source.

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

When result and op1 are in the same register, this intrinsic can use:

```asm
BIC Ztied1.D, Pg/M, Ztied1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BIC--vectors--predicated---Bitwise-clear--predicated--

This intrinsic compiles to:

```asm
BIC Zresult.D, Zop1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BIC--vectors--unpredicated---Bitwise-clear--unpredicated--

### Operation

Source operation ID: `SveOperation_svbic_s8_x`

**Operation**



Return a vector in which each active element *i* contains `op1[i] & ~op2[i]`. The inactive elements of the result have arbitrary, undefined values.

## svbic[_u64]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svbic%5B_u64%5D_z

### Signature (source notation)

```c
svuint64_t svbic[_u64]_z(svbool_t pg, svuint64_t op1, svuint64_t op2);
```

### Description

Bitwise clear

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / AND-NOT

- SME attributes: Not specified by source.

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

This intrinsic compiles to the following instructions, or functionally equivalent instructions:

```asm
MOVPRFX Zresult.D, Pg/Z, Zop1.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
BIC Zresult.D, Pg/M, Zresult.D, Zop2.D  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BIC--vectors--predicated---Bitwise-clear--predicated--

### Operation

Source operation ID: `SveOperation_svbic_s8_z`

**Operation**



Return a vector in which each active element *i* contains `op1[i] & ~op2[i]`. Set the inactive elements of the result to zero.



**[1]** Note that `result` must be in a different register from `op2`

## svbic[_u8]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svbic%5B_u8%5D_m

### Signature (source notation)

```c
svuint8_t svbic[_u8]_m(svbool_t pg, svuint8_t op1, svuint8_t op2);
```

### Description

Bitwise clear

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / AND-NOT

- SME attributes: Not specified by source.

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
BIC Ztied1.B, Pg/M, Ztied1.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BIC--vectors--predicated---Bitwise-clear--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
BIC Zresult.B, Pg/M, Zresult.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BIC--vectors--predicated---Bitwise-clear--predicated--

### Operation

Source operation ID: `SveOperation_svbic_s8_m`

**Operation**



Return a vector in which each active element *i* contains `op1[i] & ~op2[i]`. Take the inactive elements of the result from the corresponding elements of `op1`.

## svbic[_u8]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svbic%5B_u8%5D_x

### Signature (source notation)

```c
svuint8_t svbic[_u8]_x(svbool_t pg, svuint8_t op1, svuint8_t op2);
```

### Description

Bitwise clear

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / AND-NOT

- SME attributes: Not specified by source.

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

When result and op1 are in the same register, this intrinsic can use:

```asm
BIC Ztied1.B, Pg/M, Ztied1.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BIC--vectors--predicated---Bitwise-clear--predicated--

This intrinsic compiles to:

```asm
BIC Zresult.D, Zop1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BIC--vectors--unpredicated---Bitwise-clear--unpredicated--

### Operation

Source operation ID: `SveOperation_svbic_s8_x`

**Operation**



Return a vector in which each active element *i* contains `op1[i] & ~op2[i]`. The inactive elements of the result have arbitrary, undefined values.

## svbic[_u8]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svbic%5B_u8%5D_z

### Signature (source notation)

```c
svuint8_t svbic[_u8]_z(svbool_t pg, svuint8_t op1, svuint8_t op2);
```

### Description

Bitwise clear

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / AND-NOT

- SME attributes: Not specified by source.

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

This intrinsic compiles to the following instructions, or functionally equivalent instructions:

```asm
MOVPRFX Zresult.B, Pg/Z, Zop1.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
BIC Zresult.B, Pg/M, Zresult.B, Zop2.B  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BIC--vectors--predicated---Bitwise-clear--predicated--

### Operation

Source operation ID: `SveOperation_svbic_s8_z`

**Operation**



Return a vector in which each active element *i* contains `op1[i] & ~op2[i]`. Set the inactive elements of the result to zero.



**[1]** Note that `result` must be in a different register from `op2`

