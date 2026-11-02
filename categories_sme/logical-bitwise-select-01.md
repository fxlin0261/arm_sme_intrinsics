# SME / Logical / Bitwise select — Part 1

## svbsl1n[_n_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svbsl1n%5B_n_s16%5D

### Signature (source notation)

```c
svint16_t svbsl1n[_n_s16](svint16_t op1, svint16_t op2, int16_t op3);
```

### Description

Bitwise select with first input inverted

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Logical / Bitwise select

- SME attributes: Not specified by source.

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
  "op1": {
    "register": "Zop1.H|Ztied1.H"
  },
  "op2": {
    "register": "Zop2.H"
  },
  "op3": {
    "register": "Zop3.H[*]"
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
BSL1N Ztied1.D, Ztied1.D, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BSL1N--Bitwise-select-with-first-input-inverted-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
BSL1N Zresult.D, Zresult.D, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BSL1N--Bitwise-select-with-first-input-inverted-

### Operation

Source operation ID: `SveOperation_svbsl1n_n_s8`

**Operation**



Return a vector in which each element *i* contains:



```text
(op3 & ~op1[i]) | (~op3 & op2[i])
```



This is, `op3` selects between bits of `~op1[i]` (for true `op3` bits) and bits of `op2[i]` (for false `op3` bits).

## svbsl1n[_n_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svbsl1n%5B_n_s32%5D

### Signature (source notation)

```c
svint32_t svbsl1n[_n_s32](svint32_t op1, svint32_t op2, int32_t op3);
```

### Description

Bitwise select with first input inverted

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Logical / Bitwise select

- SME attributes: Not specified by source.

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
  "op1": {
    "register": "Zop1.S|Ztied1.S"
  },
  "op2": {
    "register": "Zop2.S"
  },
  "op3": {
    "register": "Zop3.S[*]"
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
BSL1N Ztied1.D, Ztied1.D, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BSL1N--Bitwise-select-with-first-input-inverted-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
BSL1N Zresult.D, Zresult.D, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BSL1N--Bitwise-select-with-first-input-inverted-

### Operation

Source operation ID: `SveOperation_svbsl1n_n_s8`

**Operation**



Return a vector in which each element *i* contains:



```text
(op3 & ~op1[i]) | (~op3 & op2[i])
```



This is, `op3` selects between bits of `~op1[i]` (for true `op3` bits) and bits of `op2[i]` (for false `op3` bits).

## svbsl1n[_n_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svbsl1n%5B_n_s64%5D

### Signature (source notation)

```c
svint64_t svbsl1n[_n_s64](svint64_t op1, svint64_t op2, int64_t op3);
```

### Description

Bitwise select with first input inverted

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Logical / Bitwise select

- SME attributes: Not specified by source.

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
  "op1": {
    "register": "Zop1.D|Ztied1.D"
  },
  "op2": {
    "register": "Zop2.D"
  },
  "op3": {
    "register": "Zop3.D[*]"
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
BSL1N Ztied1.D, Ztied1.D, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BSL1N--Bitwise-select-with-first-input-inverted-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
BSL1N Zresult.D, Zresult.D, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BSL1N--Bitwise-select-with-first-input-inverted-

### Operation

Source operation ID: `SveOperation_svbsl1n_n_s8`

**Operation**



Return a vector in which each element *i* contains:



```text
(op3 & ~op1[i]) | (~op3 & op2[i])
```



This is, `op3` selects between bits of `~op1[i]` (for true `op3` bits) and bits of `op2[i]` (for false `op3` bits).

## svbsl1n[_n_s8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svbsl1n%5B_n_s8%5D

### Signature (source notation)

```c
svint8_t svbsl1n[_n_s8](svint8_t op1, svint8_t op2, int8_t op3);
```

### Description

Bitwise select with first input inverted

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Logical / Bitwise select

- SME attributes: Not specified by source.

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
  "op1": {
    "register": "Zop1.B|Ztied1.B"
  },
  "op2": {
    "register": "Zop2.B"
  },
  "op3": {
    "register": "Zop3.B[*]"
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
BSL1N Ztied1.D, Ztied1.D, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BSL1N--Bitwise-select-with-first-input-inverted-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
BSL1N Zresult.D, Zresult.D, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BSL1N--Bitwise-select-with-first-input-inverted-

### Operation

Source operation ID: `SveOperation_svbsl1n_n_s8`

**Operation**



Return a vector in which each element *i* contains:



```text
(op3 & ~op1[i]) | (~op3 & op2[i])
```



This is, `op3` selects between bits of `~op1[i]` (for true `op3` bits) and bits of `op2[i]` (for false `op3` bits).

## svbsl1n[_n_u16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svbsl1n%5B_n_u16%5D

### Signature (source notation)

```c
svuint16_t svbsl1n[_n_u16](svuint16_t op1, svuint16_t op2, uint16_t op3);
```

### Description

Bitwise select with first input inverted

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Logical / Bitwise select

- SME attributes: Not specified by source.

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
  "op1": {
    "register": "Zop1.H|Ztied1.H"
  },
  "op2": {
    "register": "Zop2.H"
  },
  "op3": {
    "register": "Zop3.H[*]"
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
BSL1N Ztied1.D, Ztied1.D, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BSL1N--Bitwise-select-with-first-input-inverted-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
BSL1N Zresult.D, Zresult.D, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BSL1N--Bitwise-select-with-first-input-inverted-

### Operation

Source operation ID: `SveOperation_svbsl1n_n_s8`

**Operation**



Return a vector in which each element *i* contains:



```text
(op3 & ~op1[i]) | (~op3 & op2[i])
```



This is, `op3` selects between bits of `~op1[i]` (for true `op3` bits) and bits of `op2[i]` (for false `op3` bits).

## svbsl1n[_n_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svbsl1n%5B_n_u32%5D

### Signature (source notation)

```c
svuint32_t svbsl1n[_n_u32](svuint32_t op1, svuint32_t op2, uint32_t op3);
```

### Description

Bitwise select with first input inverted

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Logical / Bitwise select

- SME attributes: Not specified by source.

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
  "op1": {
    "register": "Zop1.S|Ztied1.S"
  },
  "op2": {
    "register": "Zop2.S"
  },
  "op3": {
    "register": "Zop3.S[*]"
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
BSL1N Ztied1.D, Ztied1.D, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BSL1N--Bitwise-select-with-first-input-inverted-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
BSL1N Zresult.D, Zresult.D, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BSL1N--Bitwise-select-with-first-input-inverted-

### Operation

Source operation ID: `SveOperation_svbsl1n_n_s8`

**Operation**



Return a vector in which each element *i* contains:



```text
(op3 & ~op1[i]) | (~op3 & op2[i])
```



This is, `op3` selects between bits of `~op1[i]` (for true `op3` bits) and bits of `op2[i]` (for false `op3` bits).

## svbsl1n[_n_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svbsl1n%5B_n_u64%5D

### Signature (source notation)

```c
svuint64_t svbsl1n[_n_u64](svuint64_t op1, svuint64_t op2, uint64_t op3);
```

### Description

Bitwise select with first input inverted

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Logical / Bitwise select

- SME attributes: Not specified by source.

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
  "op1": {
    "register": "Zop1.D|Ztied1.D"
  },
  "op2": {
    "register": "Zop2.D"
  },
  "op3": {
    "register": "Zop3.D[*]"
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
BSL1N Ztied1.D, Ztied1.D, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BSL1N--Bitwise-select-with-first-input-inverted-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
BSL1N Zresult.D, Zresult.D, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BSL1N--Bitwise-select-with-first-input-inverted-

### Operation

Source operation ID: `SveOperation_svbsl1n_n_s8`

**Operation**



Return a vector in which each element *i* contains:



```text
(op3 & ~op1[i]) | (~op3 & op2[i])
```



This is, `op3` selects between bits of `~op1[i]` (for true `op3` bits) and bits of `op2[i]` (for false `op3` bits).

## svbsl1n[_n_u8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svbsl1n%5B_n_u8%5D

### Signature (source notation)

```c
svuint8_t svbsl1n[_n_u8](svuint8_t op1, svuint8_t op2, uint8_t op3);
```

### Description

Bitwise select with first input inverted

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Logical / Bitwise select

- SME attributes: Not specified by source.

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
  "op1": {
    "register": "Zop1.B|Ztied1.B"
  },
  "op2": {
    "register": "Zop2.B"
  },
  "op3": {
    "register": "Zop3.B[*]"
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
BSL1N Ztied1.D, Ztied1.D, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BSL1N--Bitwise-select-with-first-input-inverted-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
BSL1N Zresult.D, Zresult.D, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BSL1N--Bitwise-select-with-first-input-inverted-

### Operation

Source operation ID: `SveOperation_svbsl1n_n_s8`

**Operation**



Return a vector in which each element *i* contains:



```text
(op3 & ~op1[i]) | (~op3 & op2[i])
```



This is, `op3` selects between bits of `~op1[i]` (for true `op3` bits) and bits of `op2[i]` (for false `op3` bits).

## svbsl1n[_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svbsl1n%5B_s16%5D

### Signature (source notation)

```c
svint16_t svbsl1n[_s16](svint16_t op1, svint16_t op2, svint16_t op3);
```

### Description

Bitwise select with first input inverted

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Logical / Bitwise select

- SME attributes: Not specified by source.

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
  "op1": {
    "register": "Zop1.H|Ztied1.H"
  },
  "op2": {
    "register": "Zop2.H"
  },
  "op3": {
    "register": "Zop3.H"
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
BSL1N Ztied1.D, Ztied1.D, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BSL1N--Bitwise-select-with-first-input-inverted-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
BSL1N Zresult.D, Zresult.D, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BSL1N--Bitwise-select-with-first-input-inverted-

### Operation

Source operation ID: `SveOperation_svbsl1n_s8`

**Operation**



Return a vector in which each element *i* contains:



```text
(op3[i] & ~op1[i]) | (~op3[i] & op2[i])
```



This is, `op3[i]` selects between bits of `~op1[i]` (for true `op3` bits) and bits of `op2[i]` (for false `op3` bits).

## svbsl1n[_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svbsl1n%5B_s32%5D

### Signature (source notation)

```c
svint32_t svbsl1n[_s32](svint32_t op1, svint32_t op2, svint32_t op3);
```

### Description

Bitwise select with first input inverted

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Logical / Bitwise select

- SME attributes: Not specified by source.

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
  "op1": {
    "register": "Zop1.S|Ztied1.S"
  },
  "op2": {
    "register": "Zop2.S"
  },
  "op3": {
    "register": "Zop3.S"
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
BSL1N Ztied1.D, Ztied1.D, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BSL1N--Bitwise-select-with-first-input-inverted-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
BSL1N Zresult.D, Zresult.D, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BSL1N--Bitwise-select-with-first-input-inverted-

### Operation

Source operation ID: `SveOperation_svbsl1n_s8`

**Operation**



Return a vector in which each element *i* contains:



```text
(op3[i] & ~op1[i]) | (~op3[i] & op2[i])
```



This is, `op3[i]` selects between bits of `~op1[i]` (for true `op3` bits) and bits of `op2[i]` (for false `op3` bits).

## svbsl1n[_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svbsl1n%5B_s64%5D

### Signature (source notation)

```c
svint64_t svbsl1n[_s64](svint64_t op1, svint64_t op2, svint64_t op3);
```

### Description

Bitwise select with first input inverted

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Logical / Bitwise select

- SME attributes: Not specified by source.

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
  "op1": {
    "register": "Zop1.D|Ztied1.D"
  },
  "op2": {
    "register": "Zop2.D"
  },
  "op3": {
    "register": "Zop3.D"
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
BSL1N Ztied1.D, Ztied1.D, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BSL1N--Bitwise-select-with-first-input-inverted-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
BSL1N Zresult.D, Zresult.D, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BSL1N--Bitwise-select-with-first-input-inverted-

### Operation

Source operation ID: `SveOperation_svbsl1n_s8`

**Operation**



Return a vector in which each element *i* contains:



```text
(op3[i] & ~op1[i]) | (~op3[i] & op2[i])
```



This is, `op3[i]` selects between bits of `~op1[i]` (for true `op3` bits) and bits of `op2[i]` (for false `op3` bits).

## svbsl1n[_s8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svbsl1n%5B_s8%5D

### Signature (source notation)

```c
svint8_t svbsl1n[_s8](svint8_t op1, svint8_t op2, svint8_t op3);
```

### Description

Bitwise select with first input inverted

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Logical / Bitwise select

- SME attributes: Not specified by source.

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
  "op1": {
    "register": "Zop1.B|Ztied1.B"
  },
  "op2": {
    "register": "Zop2.B"
  },
  "op3": {
    "register": "Zop3.B"
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
BSL1N Ztied1.D, Ztied1.D, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BSL1N--Bitwise-select-with-first-input-inverted-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
BSL1N Zresult.D, Zresult.D, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BSL1N--Bitwise-select-with-first-input-inverted-

### Operation

Source operation ID: `SveOperation_svbsl1n_s8`

**Operation**



Return a vector in which each element *i* contains:



```text
(op3[i] & ~op1[i]) | (~op3[i] & op2[i])
```



This is, `op3[i]` selects between bits of `~op1[i]` (for true `op3` bits) and bits of `op2[i]` (for false `op3` bits).

## svbsl1n[_u16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svbsl1n%5B_u16%5D

### Signature (source notation)

```c
svuint16_t svbsl1n[_u16](svuint16_t op1, svuint16_t op2, svuint16_t op3);
```

### Description

Bitwise select with first input inverted

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Logical / Bitwise select

- SME attributes: Not specified by source.

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
  "op1": {
    "register": "Zop1.H|Ztied1.H"
  },
  "op2": {
    "register": "Zop2.H"
  },
  "op3": {
    "register": "Zop3.H"
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
BSL1N Ztied1.D, Ztied1.D, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BSL1N--Bitwise-select-with-first-input-inverted-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
BSL1N Zresult.D, Zresult.D, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BSL1N--Bitwise-select-with-first-input-inverted-

### Operation

Source operation ID: `SveOperation_svbsl1n_s8`

**Operation**



Return a vector in which each element *i* contains:



```text
(op3[i] & ~op1[i]) | (~op3[i] & op2[i])
```



This is, `op3[i]` selects between bits of `~op1[i]` (for true `op3` bits) and bits of `op2[i]` (for false `op3` bits).

## svbsl1n[_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svbsl1n%5B_u32%5D

### Signature (source notation)

```c
svuint32_t svbsl1n[_u32](svuint32_t op1, svuint32_t op2, svuint32_t op3);
```

### Description

Bitwise select with first input inverted

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Logical / Bitwise select

- SME attributes: Not specified by source.

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
  "op1": {
    "register": "Zop1.S|Ztied1.S"
  },
  "op2": {
    "register": "Zop2.S"
  },
  "op3": {
    "register": "Zop3.S"
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
BSL1N Ztied1.D, Ztied1.D, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BSL1N--Bitwise-select-with-first-input-inverted-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
BSL1N Zresult.D, Zresult.D, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BSL1N--Bitwise-select-with-first-input-inverted-

### Operation

Source operation ID: `SveOperation_svbsl1n_s8`

**Operation**



Return a vector in which each element *i* contains:



```text
(op3[i] & ~op1[i]) | (~op3[i] & op2[i])
```



This is, `op3[i]` selects between bits of `~op1[i]` (for true `op3` bits) and bits of `op2[i]` (for false `op3` bits).

## svbsl1n[_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svbsl1n%5B_u64%5D

### Signature (source notation)

```c
svuint64_t svbsl1n[_u64](svuint64_t op1, svuint64_t op2, svuint64_t op3);
```

### Description

Bitwise select with first input inverted

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Logical / Bitwise select

- SME attributes: Not specified by source.

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
  "op1": {
    "register": "Zop1.D|Ztied1.D"
  },
  "op2": {
    "register": "Zop2.D"
  },
  "op3": {
    "register": "Zop3.D"
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
BSL1N Ztied1.D, Ztied1.D, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BSL1N--Bitwise-select-with-first-input-inverted-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
BSL1N Zresult.D, Zresult.D, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BSL1N--Bitwise-select-with-first-input-inverted-

### Operation

Source operation ID: `SveOperation_svbsl1n_s8`

**Operation**



Return a vector in which each element *i* contains:



```text
(op3[i] & ~op1[i]) | (~op3[i] & op2[i])
```



This is, `op3[i]` selects between bits of `~op1[i]` (for true `op3` bits) and bits of `op2[i]` (for false `op3` bits).

## svbsl1n[_u8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svbsl1n%5B_u8%5D

### Signature (source notation)

```c
svuint8_t svbsl1n[_u8](svuint8_t op1, svuint8_t op2, svuint8_t op3);
```

### Description

Bitwise select with first input inverted

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Logical / Bitwise select

- SME attributes: Not specified by source.

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
  "op1": {
    "register": "Zop1.B|Ztied1.B"
  },
  "op2": {
    "register": "Zop2.B"
  },
  "op3": {
    "register": "Zop3.B"
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
BSL1N Ztied1.D, Ztied1.D, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BSL1N--Bitwise-select-with-first-input-inverted-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
BSL1N Zresult.D, Zresult.D, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BSL1N--Bitwise-select-with-first-input-inverted-

### Operation

Source operation ID: `SveOperation_svbsl1n_s8`

**Operation**



Return a vector in which each element *i* contains:



```text
(op3[i] & ~op1[i]) | (~op3[i] & op2[i])
```



This is, `op3[i]` selects between bits of `~op1[i]` (for true `op3` bits) and bits of `op2[i]` (for false `op3` bits).

## svbsl2n[_n_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svbsl2n%5B_n_s16%5D

### Signature (source notation)

```c
svint16_t svbsl2n[_n_s16](svint16_t op1, svint16_t op2, int16_t op3);
```

### Description

Bitwise select with second input inverted

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Logical / Bitwise select

- SME attributes: Not specified by source.

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
  "op1": {
    "register": "Zop1.H|Ztied1.H"
  },
  "op2": {
    "register": "Zop2.H"
  },
  "op3": {
    "register": "Zop3.H[*]"
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
BSL2N Ztied1.D, Ztied1.D, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BSL2N--Bitwise-select-with-second-input-inverted-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
BSL2N Zresult.D, Zresult.D, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BSL2N--Bitwise-select-with-second-input-inverted-

### Operation

Source operation ID: `SveOperation_svbsl2n_n_s8`

**Operation**



Return a vector in which each element *i* contains:



```text
(op3 & op1[i]) | (~op3 & ~op2[i])
```



This is, `op3` selects between bits of `op1[i]` (for true `op3` bits) and bits of `~op2[i]` (for false `op3` bits).

## svbsl2n[_n_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svbsl2n%5B_n_s32%5D

### Signature (source notation)

```c
svint32_t svbsl2n[_n_s32](svint32_t op1, svint32_t op2, int32_t op3);
```

### Description

Bitwise select with second input inverted

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Logical / Bitwise select

- SME attributes: Not specified by source.

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
  "op1": {
    "register": "Zop1.S|Ztied1.S"
  },
  "op2": {
    "register": "Zop2.S"
  },
  "op3": {
    "register": "Zop3.S[*]"
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
BSL2N Ztied1.D, Ztied1.D, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BSL2N--Bitwise-select-with-second-input-inverted-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
BSL2N Zresult.D, Zresult.D, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BSL2N--Bitwise-select-with-second-input-inverted-

### Operation

Source operation ID: `SveOperation_svbsl2n_n_s8`

**Operation**



Return a vector in which each element *i* contains:



```text
(op3 & op1[i]) | (~op3 & ~op2[i])
```



This is, `op3` selects between bits of `op1[i]` (for true `op3` bits) and bits of `~op2[i]` (for false `op3` bits).

## svbsl2n[_n_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svbsl2n%5B_n_s64%5D

### Signature (source notation)

```c
svint64_t svbsl2n[_n_s64](svint64_t op1, svint64_t op2, int64_t op3);
```

### Description

Bitwise select with second input inverted

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Logical / Bitwise select

- SME attributes: Not specified by source.

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
  "op1": {
    "register": "Zop1.D|Ztied1.D"
  },
  "op2": {
    "register": "Zop2.D"
  },
  "op3": {
    "register": "Zop3.D[*]"
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
BSL2N Ztied1.D, Ztied1.D, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BSL2N--Bitwise-select-with-second-input-inverted-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
BSL2N Zresult.D, Zresult.D, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BSL2N--Bitwise-select-with-second-input-inverted-

### Operation

Source operation ID: `SveOperation_svbsl2n_n_s8`

**Operation**



Return a vector in which each element *i* contains:



```text
(op3 & op1[i]) | (~op3 & ~op2[i])
```



This is, `op3` selects between bits of `op1[i]` (for true `op3` bits) and bits of `~op2[i]` (for false `op3` bits).

## svbsl2n[_n_s8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svbsl2n%5B_n_s8%5D

### Signature (source notation)

```c
svint8_t svbsl2n[_n_s8](svint8_t op1, svint8_t op2, int8_t op3);
```

### Description

Bitwise select with second input inverted

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Logical / Bitwise select

- SME attributes: Not specified by source.

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
  "op1": {
    "register": "Zop1.B|Ztied1.B"
  },
  "op2": {
    "register": "Zop2.B"
  },
  "op3": {
    "register": "Zop3.B[*]"
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
BSL2N Ztied1.D, Ztied1.D, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BSL2N--Bitwise-select-with-second-input-inverted-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
BSL2N Zresult.D, Zresult.D, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BSL2N--Bitwise-select-with-second-input-inverted-

### Operation

Source operation ID: `SveOperation_svbsl2n_n_s8`

**Operation**



Return a vector in which each element *i* contains:



```text
(op3 & op1[i]) | (~op3 & ~op2[i])
```



This is, `op3` selects between bits of `op1[i]` (for true `op3` bits) and bits of `~op2[i]` (for false `op3` bits).

## svbsl2n[_n_u16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svbsl2n%5B_n_u16%5D

### Signature (source notation)

```c
svuint16_t svbsl2n[_n_u16](svuint16_t op1, svuint16_t op2, uint16_t op3);
```

### Description

Bitwise select with second input inverted

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Logical / Bitwise select

- SME attributes: Not specified by source.

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
  "op1": {
    "register": "Zop1.H|Ztied1.H"
  },
  "op2": {
    "register": "Zop2.H"
  },
  "op3": {
    "register": "Zop3.H[*]"
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
BSL2N Ztied1.D, Ztied1.D, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BSL2N--Bitwise-select-with-second-input-inverted-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
BSL2N Zresult.D, Zresult.D, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BSL2N--Bitwise-select-with-second-input-inverted-

### Operation

Source operation ID: `SveOperation_svbsl2n_n_s8`

**Operation**



Return a vector in which each element *i* contains:



```text
(op3 & op1[i]) | (~op3 & ~op2[i])
```



This is, `op3` selects between bits of `op1[i]` (for true `op3` bits) and bits of `~op2[i]` (for false `op3` bits).

## svbsl2n[_n_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svbsl2n%5B_n_u32%5D

### Signature (source notation)

```c
svuint32_t svbsl2n[_n_u32](svuint32_t op1, svuint32_t op2, uint32_t op3);
```

### Description

Bitwise select with second input inverted

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Logical / Bitwise select

- SME attributes: Not specified by source.

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
  "op1": {
    "register": "Zop1.S|Ztied1.S"
  },
  "op2": {
    "register": "Zop2.S"
  },
  "op3": {
    "register": "Zop3.S[*]"
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
BSL2N Ztied1.D, Ztied1.D, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BSL2N--Bitwise-select-with-second-input-inverted-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
BSL2N Zresult.D, Zresult.D, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BSL2N--Bitwise-select-with-second-input-inverted-

### Operation

Source operation ID: `SveOperation_svbsl2n_n_s8`

**Operation**



Return a vector in which each element *i* contains:



```text
(op3 & op1[i]) | (~op3 & ~op2[i])
```



This is, `op3` selects between bits of `op1[i]` (for true `op3` bits) and bits of `~op2[i]` (for false `op3` bits).

## svbsl2n[_n_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svbsl2n%5B_n_u64%5D

### Signature (source notation)

```c
svuint64_t svbsl2n[_n_u64](svuint64_t op1, svuint64_t op2, uint64_t op3);
```

### Description

Bitwise select with second input inverted

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Logical / Bitwise select

- SME attributes: Not specified by source.

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
  "op1": {
    "register": "Zop1.D|Ztied1.D"
  },
  "op2": {
    "register": "Zop2.D"
  },
  "op3": {
    "register": "Zop3.D[*]"
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
BSL2N Ztied1.D, Ztied1.D, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BSL2N--Bitwise-select-with-second-input-inverted-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
BSL2N Zresult.D, Zresult.D, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BSL2N--Bitwise-select-with-second-input-inverted-

### Operation

Source operation ID: `SveOperation_svbsl2n_n_s8`

**Operation**



Return a vector in which each element *i* contains:



```text
(op3 & op1[i]) | (~op3 & ~op2[i])
```



This is, `op3` selects between bits of `op1[i]` (for true `op3` bits) and bits of `~op2[i]` (for false `op3` bits).

## svbsl2n[_n_u8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svbsl2n%5B_n_u8%5D

### Signature (source notation)

```c
svuint8_t svbsl2n[_n_u8](svuint8_t op1, svuint8_t op2, uint8_t op3);
```

### Description

Bitwise select with second input inverted

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Logical / Bitwise select

- SME attributes: Not specified by source.

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
  "op1": {
    "register": "Zop1.B|Ztied1.B"
  },
  "op2": {
    "register": "Zop2.B"
  },
  "op3": {
    "register": "Zop3.B[*]"
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
BSL2N Ztied1.D, Ztied1.D, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BSL2N--Bitwise-select-with-second-input-inverted-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
BSL2N Zresult.D, Zresult.D, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BSL2N--Bitwise-select-with-second-input-inverted-

### Operation

Source operation ID: `SveOperation_svbsl2n_n_s8`

**Operation**



Return a vector in which each element *i* contains:



```text
(op3 & op1[i]) | (~op3 & ~op2[i])
```



This is, `op3` selects between bits of `op1[i]` (for true `op3` bits) and bits of `~op2[i]` (for false `op3` bits).

## svbsl2n[_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svbsl2n%5B_s16%5D

### Signature (source notation)

```c
svint16_t svbsl2n[_s16](svint16_t op1, svint16_t op2, svint16_t op3);
```

### Description

Bitwise select with second input inverted

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Logical / Bitwise select

- SME attributes: Not specified by source.

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
  "op1": {
    "register": "Zop1.H|Ztied1.H"
  },
  "op2": {
    "register": "Zop2.H"
  },
  "op3": {
    "register": "Zop3.H"
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
BSL2N Ztied1.D, Ztied1.D, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BSL2N--Bitwise-select-with-second-input-inverted-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
BSL2N Zresult.D, Zresult.D, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BSL2N--Bitwise-select-with-second-input-inverted-

### Operation

Source operation ID: `SveOperation_svbsl2n_s8`

**Operation**



Return a vector in which each element *i* contains:



```text
(op3[i] & op1[i]) | (~op3[i] & ~op2[i])
```



This is, `op3[i]` selects between bits of `op1[i]` (for true `op3` bits) and bits of `~op2[i]` (for false `op3` bits).

## svbsl2n[_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svbsl2n%5B_s32%5D

### Signature (source notation)

```c
svint32_t svbsl2n[_s32](svint32_t op1, svint32_t op2, svint32_t op3);
```

### Description

Bitwise select with second input inverted

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Logical / Bitwise select

- SME attributes: Not specified by source.

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
  "op1": {
    "register": "Zop1.S|Ztied1.S"
  },
  "op2": {
    "register": "Zop2.S"
  },
  "op3": {
    "register": "Zop3.S"
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
BSL2N Ztied1.D, Ztied1.D, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BSL2N--Bitwise-select-with-second-input-inverted-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
BSL2N Zresult.D, Zresult.D, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BSL2N--Bitwise-select-with-second-input-inverted-

### Operation

Source operation ID: `SveOperation_svbsl2n_s8`

**Operation**



Return a vector in which each element *i* contains:



```text
(op3[i] & op1[i]) | (~op3[i] & ~op2[i])
```



This is, `op3[i]` selects between bits of `op1[i]` (for true `op3` bits) and bits of `~op2[i]` (for false `op3` bits).

## svbsl2n[_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svbsl2n%5B_s64%5D

### Signature (source notation)

```c
svint64_t svbsl2n[_s64](svint64_t op1, svint64_t op2, svint64_t op3);
```

### Description

Bitwise select with second input inverted

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Logical / Bitwise select

- SME attributes: Not specified by source.

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
  "op1": {
    "register": "Zop1.D|Ztied1.D"
  },
  "op2": {
    "register": "Zop2.D"
  },
  "op3": {
    "register": "Zop3.D"
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
BSL2N Ztied1.D, Ztied1.D, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BSL2N--Bitwise-select-with-second-input-inverted-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
BSL2N Zresult.D, Zresult.D, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BSL2N--Bitwise-select-with-second-input-inverted-

### Operation

Source operation ID: `SveOperation_svbsl2n_s8`

**Operation**



Return a vector in which each element *i* contains:



```text
(op3[i] & op1[i]) | (~op3[i] & ~op2[i])
```



This is, `op3[i]` selects between bits of `op1[i]` (for true `op3` bits) and bits of `~op2[i]` (for false `op3` bits).

## svbsl2n[_s8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svbsl2n%5B_s8%5D

### Signature (source notation)

```c
svint8_t svbsl2n[_s8](svint8_t op1, svint8_t op2, svint8_t op3);
```

### Description

Bitwise select with second input inverted

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Logical / Bitwise select

- SME attributes: Not specified by source.

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
  "op1": {
    "register": "Zop1.B|Ztied1.B"
  },
  "op2": {
    "register": "Zop2.B"
  },
  "op3": {
    "register": "Zop3.B"
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
BSL2N Ztied1.D, Ztied1.D, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BSL2N--Bitwise-select-with-second-input-inverted-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
BSL2N Zresult.D, Zresult.D, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BSL2N--Bitwise-select-with-second-input-inverted-

### Operation

Source operation ID: `SveOperation_svbsl2n_s8`

**Operation**



Return a vector in which each element *i* contains:



```text
(op3[i] & op1[i]) | (~op3[i] & ~op2[i])
```



This is, `op3[i]` selects between bits of `op1[i]` (for true `op3` bits) and bits of `~op2[i]` (for false `op3` bits).

## svbsl2n[_u16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svbsl2n%5B_u16%5D

### Signature (source notation)

```c
svuint16_t svbsl2n[_u16](svuint16_t op1, svuint16_t op2, svuint16_t op3);
```

### Description

Bitwise select with second input inverted

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Logical / Bitwise select

- SME attributes: Not specified by source.

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
  "op1": {
    "register": "Zop1.H|Ztied1.H"
  },
  "op2": {
    "register": "Zop2.H"
  },
  "op3": {
    "register": "Zop3.H"
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
BSL2N Ztied1.D, Ztied1.D, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BSL2N--Bitwise-select-with-second-input-inverted-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
BSL2N Zresult.D, Zresult.D, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BSL2N--Bitwise-select-with-second-input-inverted-

### Operation

Source operation ID: `SveOperation_svbsl2n_s8`

**Operation**



Return a vector in which each element *i* contains:



```text
(op3[i] & op1[i]) | (~op3[i] & ~op2[i])
```



This is, `op3[i]` selects between bits of `op1[i]` (for true `op3` bits) and bits of `~op2[i]` (for false `op3` bits).

## svbsl2n[_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svbsl2n%5B_u32%5D

### Signature (source notation)

```c
svuint32_t svbsl2n[_u32](svuint32_t op1, svuint32_t op2, svuint32_t op3);
```

### Description

Bitwise select with second input inverted

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Logical / Bitwise select

- SME attributes: Not specified by source.

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
  "op1": {
    "register": "Zop1.S|Ztied1.S"
  },
  "op2": {
    "register": "Zop2.S"
  },
  "op3": {
    "register": "Zop3.S"
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
BSL2N Ztied1.D, Ztied1.D, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BSL2N--Bitwise-select-with-second-input-inverted-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
BSL2N Zresult.D, Zresult.D, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BSL2N--Bitwise-select-with-second-input-inverted-

### Operation

Source operation ID: `SveOperation_svbsl2n_s8`

**Operation**



Return a vector in which each element *i* contains:



```text
(op3[i] & op1[i]) | (~op3[i] & ~op2[i])
```



This is, `op3[i]` selects between bits of `op1[i]` (for true `op3` bits) and bits of `~op2[i]` (for false `op3` bits).

## svbsl2n[_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svbsl2n%5B_u64%5D

### Signature (source notation)

```c
svuint64_t svbsl2n[_u64](svuint64_t op1, svuint64_t op2, svuint64_t op3);
```

### Description

Bitwise select with second input inverted

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Logical / Bitwise select

- SME attributes: Not specified by source.

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
  "op1": {
    "register": "Zop1.D|Ztied1.D"
  },
  "op2": {
    "register": "Zop2.D"
  },
  "op3": {
    "register": "Zop3.D"
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
BSL2N Ztied1.D, Ztied1.D, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BSL2N--Bitwise-select-with-second-input-inverted-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
BSL2N Zresult.D, Zresult.D, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BSL2N--Bitwise-select-with-second-input-inverted-

### Operation

Source operation ID: `SveOperation_svbsl2n_s8`

**Operation**



Return a vector in which each element *i* contains:



```text
(op3[i] & op1[i]) | (~op3[i] & ~op2[i])
```



This is, `op3[i]` selects between bits of `op1[i]` (for true `op3` bits) and bits of `~op2[i]` (for false `op3` bits).

## svbsl2n[_u8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svbsl2n%5B_u8%5D

### Signature (source notation)

```c
svuint8_t svbsl2n[_u8](svuint8_t op1, svuint8_t op2, svuint8_t op3);
```

### Description

Bitwise select with second input inverted

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Logical / Bitwise select

- SME attributes: Not specified by source.

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
  "op1": {
    "register": "Zop1.B|Ztied1.B"
  },
  "op2": {
    "register": "Zop2.B"
  },
  "op3": {
    "register": "Zop3.B"
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
BSL2N Ztied1.D, Ztied1.D, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BSL2N--Bitwise-select-with-second-input-inverted-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
BSL2N Zresult.D, Zresult.D, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BSL2N--Bitwise-select-with-second-input-inverted-

### Operation

Source operation ID: `SveOperation_svbsl2n_s8`

**Operation**



Return a vector in which each element *i* contains:



```text
(op3[i] & op1[i]) | (~op3[i] & ~op2[i])
```



This is, `op3[i]` selects between bits of `op1[i]` (for true `op3` bits) and bits of `~op2[i]` (for false `op3` bits).

## svbsl[_n_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svbsl%5B_n_s16%5D

### Signature (source notation)

```c
svint16_t svbsl[_n_s16](svint16_t op1, svint16_t op2, int16_t op3);
```

### Description

Bitwise select

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Logical / Bitwise select

- SME attributes: Not specified by source.

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
  "op1": {
    "register": "Zop1.H|Ztied1.H"
  },
  "op2": {
    "register": "Zop2.H"
  },
  "op3": {
    "register": "Zop3.H[*]"
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
BSL Ztied1.D, Ztied1.D, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BSL--Bitwise-select-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
BSL Zresult.D, Zresult.D, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BSL--Bitwise-select-

### Operation

Source operation ID: `SveOperation_svbsl_n_s8`

**Operation**



Return a vector in which each element *i* contains:



```text
(op3 & op1[i]) | (~op3 & op2[i])
```



This is, `op3` selects between bits of `op1[i]` (for true `op3` bits) and bits of `op2[i]` (for false `op3` bits).

## svbsl[_n_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svbsl%5B_n_s32%5D

### Signature (source notation)

```c
svint32_t svbsl[_n_s32](svint32_t op1, svint32_t op2, int32_t op3);
```

### Description

Bitwise select

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Logical / Bitwise select

- SME attributes: Not specified by source.

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
  "op1": {
    "register": "Zop1.S|Ztied1.S"
  },
  "op2": {
    "register": "Zop2.S"
  },
  "op3": {
    "register": "Zop3.S[*]"
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
BSL Ztied1.D, Ztied1.D, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BSL--Bitwise-select-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
BSL Zresult.D, Zresult.D, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BSL--Bitwise-select-

### Operation

Source operation ID: `SveOperation_svbsl_n_s8`

**Operation**



Return a vector in which each element *i* contains:



```text
(op3 & op1[i]) | (~op3 & op2[i])
```



This is, `op3` selects between bits of `op1[i]` (for true `op3` bits) and bits of `op2[i]` (for false `op3` bits).

## svbsl[_n_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svbsl%5B_n_s64%5D

### Signature (source notation)

```c
svint64_t svbsl[_n_s64](svint64_t op1, svint64_t op2, int64_t op3);
```

### Description

Bitwise select

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Logical / Bitwise select

- SME attributes: Not specified by source.

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
  "op1": {
    "register": "Zop1.D|Ztied1.D"
  },
  "op2": {
    "register": "Zop2.D"
  },
  "op3": {
    "register": "Zop3.D[*]"
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
BSL Ztied1.D, Ztied1.D, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BSL--Bitwise-select-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
BSL Zresult.D, Zresult.D, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BSL--Bitwise-select-

### Operation

Source operation ID: `SveOperation_svbsl_n_s8`

**Operation**



Return a vector in which each element *i* contains:



```text
(op3 & op1[i]) | (~op3 & op2[i])
```



This is, `op3` selects between bits of `op1[i]` (for true `op3` bits) and bits of `op2[i]` (for false `op3` bits).

## svbsl[_n_s8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svbsl%5B_n_s8%5D

### Signature (source notation)

```c
svint8_t svbsl[_n_s8](svint8_t op1, svint8_t op2, int8_t op3);
```

### Description

Bitwise select

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Logical / Bitwise select

- SME attributes: Not specified by source.

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
  "op1": {
    "register": "Zop1.B|Ztied1.B"
  },
  "op2": {
    "register": "Zop2.B"
  },
  "op3": {
    "register": "Zop3.B[*]"
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
BSL Ztied1.D, Ztied1.D, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BSL--Bitwise-select-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
BSL Zresult.D, Zresult.D, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BSL--Bitwise-select-

### Operation

Source operation ID: `SveOperation_svbsl_n_s8`

**Operation**



Return a vector in which each element *i* contains:



```text
(op3 & op1[i]) | (~op3 & op2[i])
```



This is, `op3` selects between bits of `op1[i]` (for true `op3` bits) and bits of `op2[i]` (for false `op3` bits).

## svbsl[_n_u16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svbsl%5B_n_u16%5D

### Signature (source notation)

```c
svuint16_t svbsl[_n_u16](svuint16_t op1, svuint16_t op2, uint16_t op3);
```

### Description

Bitwise select

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Logical / Bitwise select

- SME attributes: Not specified by source.

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
  "op1": {
    "register": "Zop1.H|Ztied1.H"
  },
  "op2": {
    "register": "Zop2.H"
  },
  "op3": {
    "register": "Zop3.H[*]"
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
BSL Ztied1.D, Ztied1.D, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BSL--Bitwise-select-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
BSL Zresult.D, Zresult.D, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BSL--Bitwise-select-

### Operation

Source operation ID: `SveOperation_svbsl_n_s8`

**Operation**



Return a vector in which each element *i* contains:



```text
(op3 & op1[i]) | (~op3 & op2[i])
```



This is, `op3` selects between bits of `op1[i]` (for true `op3` bits) and bits of `op2[i]` (for false `op3` bits).

## svbsl[_n_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svbsl%5B_n_u32%5D

### Signature (source notation)

```c
svuint32_t svbsl[_n_u32](svuint32_t op1, svuint32_t op2, uint32_t op3);
```

### Description

Bitwise select

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Logical / Bitwise select

- SME attributes: Not specified by source.

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
  "op1": {
    "register": "Zop1.S|Ztied1.S"
  },
  "op2": {
    "register": "Zop2.S"
  },
  "op3": {
    "register": "Zop3.S[*]"
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
BSL Ztied1.D, Ztied1.D, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BSL--Bitwise-select-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
BSL Zresult.D, Zresult.D, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BSL--Bitwise-select-

### Operation

Source operation ID: `SveOperation_svbsl_n_s8`

**Operation**



Return a vector in which each element *i* contains:



```text
(op3 & op1[i]) | (~op3 & op2[i])
```



This is, `op3` selects between bits of `op1[i]` (for true `op3` bits) and bits of `op2[i]` (for false `op3` bits).

## svbsl[_n_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svbsl%5B_n_u64%5D

### Signature (source notation)

```c
svuint64_t svbsl[_n_u64](svuint64_t op1, svuint64_t op2, uint64_t op3);
```

### Description

Bitwise select

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Logical / Bitwise select

- SME attributes: Not specified by source.

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
  "op1": {
    "register": "Zop1.D|Ztied1.D"
  },
  "op2": {
    "register": "Zop2.D"
  },
  "op3": {
    "register": "Zop3.D[*]"
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
BSL Ztied1.D, Ztied1.D, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BSL--Bitwise-select-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
BSL Zresult.D, Zresult.D, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BSL--Bitwise-select-

### Operation

Source operation ID: `SveOperation_svbsl_n_s8`

**Operation**



Return a vector in which each element *i* contains:



```text
(op3 & op1[i]) | (~op3 & op2[i])
```



This is, `op3` selects between bits of `op1[i]` (for true `op3` bits) and bits of `op2[i]` (for false `op3` bits).

## svbsl[_n_u8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svbsl%5B_n_u8%5D

### Signature (source notation)

```c
svuint8_t svbsl[_n_u8](svuint8_t op1, svuint8_t op2, uint8_t op3);
```

### Description

Bitwise select

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Logical / Bitwise select

- SME attributes: Not specified by source.

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
  "op1": {
    "register": "Zop1.B|Ztied1.B"
  },
  "op2": {
    "register": "Zop2.B"
  },
  "op3": {
    "register": "Zop3.B[*]"
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
BSL Ztied1.D, Ztied1.D, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BSL--Bitwise-select-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
BSL Zresult.D, Zresult.D, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BSL--Bitwise-select-

### Operation

Source operation ID: `SveOperation_svbsl_n_s8`

**Operation**



Return a vector in which each element *i* contains:



```text
(op3 & op1[i]) | (~op3 & op2[i])
```



This is, `op3` selects between bits of `op1[i]` (for true `op3` bits) and bits of `op2[i]` (for false `op3` bits).

## svbsl[_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svbsl%5B_s16%5D

### Signature (source notation)

```c
svint16_t svbsl[_s16](svint16_t op1, svint16_t op2, svint16_t op3);
```

### Description

Bitwise select

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Logical / Bitwise select

- SME attributes: Not specified by source.

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
  "op1": {
    "register": "Zop1.H|Ztied1.H"
  },
  "op2": {
    "register": "Zop2.H"
  },
  "op3": {
    "register": "Zop3.H"
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
BSL Ztied1.D, Ztied1.D, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BSL--Bitwise-select-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
BSL Zresult.D, Zresult.D, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BSL--Bitwise-select-

### Operation

Source operation ID: `SveOperation_svbsl_s8`

**Operation**



Return a vector in which each element *i* contains:



```text
(op3[i] & op1[i]) | (~op3[i] & op2[i])
```



This is, `op3[i]` selects between bits of `op1[i]` (for true `op3` bits) and bits of `op2[i]` (for false `op3` bits).

## svbsl[_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svbsl%5B_s32%5D

### Signature (source notation)

```c
svint32_t svbsl[_s32](svint32_t op1, svint32_t op2, svint32_t op3);
```

### Description

Bitwise select

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Logical / Bitwise select

- SME attributes: Not specified by source.

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
  "op1": {
    "register": "Zop1.S|Ztied1.S"
  },
  "op2": {
    "register": "Zop2.S"
  },
  "op3": {
    "register": "Zop3.S"
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
BSL Ztied1.D, Ztied1.D, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BSL--Bitwise-select-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
BSL Zresult.D, Zresult.D, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BSL--Bitwise-select-

### Operation

Source operation ID: `SveOperation_svbsl_s8`

**Operation**



Return a vector in which each element *i* contains:



```text
(op3[i] & op1[i]) | (~op3[i] & op2[i])
```



This is, `op3[i]` selects between bits of `op1[i]` (for true `op3` bits) and bits of `op2[i]` (for false `op3` bits).

## svbsl[_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svbsl%5B_s64%5D

### Signature (source notation)

```c
svint64_t svbsl[_s64](svint64_t op1, svint64_t op2, svint64_t op3);
```

### Description

Bitwise select

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Logical / Bitwise select

- SME attributes: Not specified by source.

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
  "op1": {
    "register": "Zop1.D|Ztied1.D"
  },
  "op2": {
    "register": "Zop2.D"
  },
  "op3": {
    "register": "Zop3.D"
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
BSL Ztied1.D, Ztied1.D, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BSL--Bitwise-select-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
BSL Zresult.D, Zresult.D, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BSL--Bitwise-select-

### Operation

Source operation ID: `SveOperation_svbsl_s8`

**Operation**



Return a vector in which each element *i* contains:



```text
(op3[i] & op1[i]) | (~op3[i] & op2[i])
```



This is, `op3[i]` selects between bits of `op1[i]` (for true `op3` bits) and bits of `op2[i]` (for false `op3` bits).

## svbsl[_s8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svbsl%5B_s8%5D

### Signature (source notation)

```c
svint8_t svbsl[_s8](svint8_t op1, svint8_t op2, svint8_t op3);
```

### Description

Bitwise select

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Logical / Bitwise select

- SME attributes: Not specified by source.

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
  "op1": {
    "register": "Zop1.B|Ztied1.B"
  },
  "op2": {
    "register": "Zop2.B"
  },
  "op3": {
    "register": "Zop3.B"
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
BSL Ztied1.D, Ztied1.D, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BSL--Bitwise-select-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
BSL Zresult.D, Zresult.D, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BSL--Bitwise-select-

### Operation

Source operation ID: `SveOperation_svbsl_s8`

**Operation**



Return a vector in which each element *i* contains:



```text
(op3[i] & op1[i]) | (~op3[i] & op2[i])
```



This is, `op3[i]` selects between bits of `op1[i]` (for true `op3` bits) and bits of `op2[i]` (for false `op3` bits).

## svbsl[_u16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svbsl%5B_u16%5D

### Signature (source notation)

```c
svuint16_t svbsl[_u16](svuint16_t op1, svuint16_t op2, svuint16_t op3);
```

### Description

Bitwise select

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Logical / Bitwise select

- SME attributes: Not specified by source.

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
  "op1": {
    "register": "Zop1.H|Ztied1.H"
  },
  "op2": {
    "register": "Zop2.H"
  },
  "op3": {
    "register": "Zop3.H"
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
BSL Ztied1.D, Ztied1.D, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BSL--Bitwise-select-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
BSL Zresult.D, Zresult.D, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BSL--Bitwise-select-

### Operation

Source operation ID: `SveOperation_svbsl_s8`

**Operation**



Return a vector in which each element *i* contains:



```text
(op3[i] & op1[i]) | (~op3[i] & op2[i])
```



This is, `op3[i]` selects between bits of `op1[i]` (for true `op3` bits) and bits of `op2[i]` (for false `op3` bits).

## svbsl[_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svbsl%5B_u32%5D

### Signature (source notation)

```c
svuint32_t svbsl[_u32](svuint32_t op1, svuint32_t op2, svuint32_t op3);
```

### Description

Bitwise select

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Logical / Bitwise select

- SME attributes: Not specified by source.

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
  "op1": {
    "register": "Zop1.S|Ztied1.S"
  },
  "op2": {
    "register": "Zop2.S"
  },
  "op3": {
    "register": "Zop3.S"
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
BSL Ztied1.D, Ztied1.D, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BSL--Bitwise-select-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
BSL Zresult.D, Zresult.D, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BSL--Bitwise-select-

### Operation

Source operation ID: `SveOperation_svbsl_s8`

**Operation**



Return a vector in which each element *i* contains:



```text
(op3[i] & op1[i]) | (~op3[i] & op2[i])
```



This is, `op3[i]` selects between bits of `op1[i]` (for true `op3` bits) and bits of `op2[i]` (for false `op3` bits).

## svbsl[_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svbsl%5B_u64%5D

### Signature (source notation)

```c
svuint64_t svbsl[_u64](svuint64_t op1, svuint64_t op2, svuint64_t op3);
```

### Description

Bitwise select

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Logical / Bitwise select

- SME attributes: Not specified by source.

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
  "op1": {
    "register": "Zop1.D|Ztied1.D"
  },
  "op2": {
    "register": "Zop2.D"
  },
  "op3": {
    "register": "Zop3.D"
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
BSL Ztied1.D, Ztied1.D, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BSL--Bitwise-select-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
BSL Zresult.D, Zresult.D, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BSL--Bitwise-select-

### Operation

Source operation ID: `SveOperation_svbsl_s8`

**Operation**



Return a vector in which each element *i* contains:



```text
(op3[i] & op1[i]) | (~op3[i] & op2[i])
```



This is, `op3[i]` selects between bits of `op1[i]` (for true `op3` bits) and bits of `op2[i]` (for false `op3` bits).

## svbsl[_u8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svbsl%5B_u8%5D

### Signature (source notation)

```c
svuint8_t svbsl[_u8](svuint8_t op1, svuint8_t op2, svuint8_t op3);
```

### Description

Bitwise select

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Logical / Bitwise select

- SME attributes: Not specified by source.

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
  "op1": {
    "register": "Zop1.B|Ztied1.B"
  },
  "op2": {
    "register": "Zop2.B"
  },
  "op3": {
    "register": "Zop3.B"
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
BSL Ztied1.D, Ztied1.D, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BSL--Bitwise-select-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
BSL Zresult.D, Zresult.D, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BSL--Bitwise-select-

### Operation

Source operation ID: `SveOperation_svbsl_s8`

**Operation**



Return a vector in which each element *i* contains:



```text
(op3[i] & op1[i]) | (~op3[i] & op2[i])
```



This is, `op3[i]` selects between bits of `op1[i]` (for true `op3` bits) and bits of `op2[i]` (for false `op3` bits).

## svnbsl[_n_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svnbsl%5B_n_s16%5D

### Signature (source notation)

```c
svint16_t svnbsl[_n_s16](svint16_t op1, svint16_t op2, int16_t op3);
```

### Description

Bitwise select

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Logical / Bitwise select

- SME attributes: Not specified by source.

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
  "op1": {
    "register": "Zop1.H|Ztied1.H"
  },
  "op2": {
    "register": "Zop2.H"
  },
  "op3": {
    "register": "Zop3.H[*]"
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
NBSL Ztied1.D, Ztied1.D, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/NBSL--Bitwise-inverted-select-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
NBSL Zresult.D, Zresult.D, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/NBSL--Bitwise-inverted-select-

### Operation

Source operation ID: `SveOperation_svnbsl_n_s8`

**Operation**



Return a vector in which each element *i* contains:



```text
(op3 & ~op1[i]) | (~op3 & ~op2[i])
```



This is, `op3` selects between bits of `~op1[i]` (for true `op3` bits) and bits of `~op2[i]` (for false `op3` bits).

## svnbsl[_n_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svnbsl%5B_n_s32%5D

### Signature (source notation)

```c
svint32_t svnbsl[_n_s32](svint32_t op1, svint32_t op2, int32_t op3);
```

### Description

Bitwise select

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Logical / Bitwise select

- SME attributes: Not specified by source.

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
  "op1": {
    "register": "Zop1.S|Ztied1.S"
  },
  "op2": {
    "register": "Zop2.S"
  },
  "op3": {
    "register": "Zop3.S[*]"
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
NBSL Ztied1.D, Ztied1.D, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/NBSL--Bitwise-inverted-select-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
NBSL Zresult.D, Zresult.D, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/NBSL--Bitwise-inverted-select-

### Operation

Source operation ID: `SveOperation_svnbsl_n_s8`

**Operation**



Return a vector in which each element *i* contains:



```text
(op3 & ~op1[i]) | (~op3 & ~op2[i])
```



This is, `op3` selects between bits of `~op1[i]` (for true `op3` bits) and bits of `~op2[i]` (for false `op3` bits).

