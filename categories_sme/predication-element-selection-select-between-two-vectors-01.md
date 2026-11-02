# SME / Predication / Element selection / Select between two vectors — Part 1

## svsel[_b]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsel%5B_b%5D

### Signature (source notation)

```c
svbool_t svsel[_b](svbool_t pg, svbool_t op1, svbool_t op2);
```

### Description

Conditionally select elements

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Predication / Element selection / Select between two vectors

- SME attributes: Not specified by source.

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
SEL Presult.B, Pg, Pop1.B, Pop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SEL--predicates---Conditionally-select-elements-from-two-predicates-

### Operation

Source operation ID: `SveOperation_svsel_b`

**Operation**



Return a predicate in which each active element *i* contains `op1[i]` and in which each inactive element *j* contains `op2[j]`.

## svsel[_bf16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsel%5B_bf16%5D

### Signature (source notation)

```c
svbfloat16_t svsel[_bf16](svbool_t pg, svbfloat16_t op1, svbfloat16_t op2);
```

### Description

Conditionally select elements

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Predication / Element selection / Select between two vectors

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME
```

### Return type metadata

```json
{
  "return_base_type": "bfloat",
  "element_bit_size": "16",
  "value": "svbfloat16_t"
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

This intrinsic compiles to the following instruction:

```asm
SEL Zresult.H, Pg, Zop1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SEL--vectors---Conditionally-select-elements-from-two-vectors-

### Operation

Source operation ID: `SveOperation_svsel_bf16`

**Operation**



Return a vector in which each active element *i* contains `op1[i]` and in which each inactive element *j* contains `op2[j]`.

## svsel[_f16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsel%5B_f16%5D

### Signature (source notation)

```c
svfloat16_t svsel[_f16](svbool_t pg, svfloat16_t op1, svfloat16_t op2);
```

### Description

Conditionally select elements

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Predication / Element selection / Select between two vectors

- SME attributes: Not specified by source.

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

This intrinsic compiles to the following instruction:

```asm
SEL Zresult.H, Pg, Zop1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SEL--vectors---Conditionally-select-elements-from-two-vectors-

### Operation

Source operation ID: `SveOperation_svsel_bf16`

**Operation**



Return a vector in which each active element *i* contains `op1[i]` and in which each inactive element *j* contains `op2[j]`.

## svsel[_f32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsel%5B_f32%5D

### Signature (source notation)

```c
svfloat32_t svsel[_f32](svbool_t pg, svfloat32_t op1, svfloat32_t op2);
```

### Description

Conditionally select elements

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Predication / Element selection / Select between two vectors

- SME attributes: Not specified by source.

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

This intrinsic compiles to the following instruction:

```asm
SEL Zresult.S, Pg, Zop1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SEL--vectors---Conditionally-select-elements-from-two-vectors-

### Operation

Source operation ID: `SveOperation_svsel_bf16`

**Operation**



Return a vector in which each active element *i* contains `op1[i]` and in which each inactive element *j* contains `op2[j]`.

## svsel[_f64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsel%5B_f64%5D

### Signature (source notation)

```c
svfloat64_t svsel[_f64](svbool_t pg, svfloat64_t op1, svfloat64_t op2);
```

### Description

Conditionally select elements

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Predication / Element selection / Select between two vectors

- SME attributes: Not specified by source.

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

This intrinsic compiles to the following instruction:

```asm
SEL Zresult.D, Pg, Zop1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SEL--vectors---Conditionally-select-elements-from-two-vectors-

### Operation

Source operation ID: `SveOperation_svsel_bf16`

**Operation**



Return a vector in which each active element *i* contains `op1[i]` and in which each inactive element *j* contains `op2[j]`.

## svsel[_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsel%5B_s16%5D

### Signature (source notation)

```c
svint16_t svsel[_s16](svbool_t pg, svint16_t op1, svint16_t op2);
```

### Description

Conditionally select elements

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Predication / Element selection / Select between two vectors

- SME attributes: Not specified by source.

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

This intrinsic compiles to the following instruction:

```asm
SEL Zresult.H, Pg, Zop1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SEL--vectors---Conditionally-select-elements-from-two-vectors-

### Operation

Source operation ID: `SveOperation_svsel_bf16`

**Operation**



Return a vector in which each active element *i* contains `op1[i]` and in which each inactive element *j* contains `op2[j]`.

## svsel[_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsel%5B_s32%5D

### Signature (source notation)

```c
svint32_t svsel[_s32](svbool_t pg, svint32_t op1, svint32_t op2);
```

### Description

Conditionally select elements

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Predication / Element selection / Select between two vectors

- SME attributes: Not specified by source.

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

This intrinsic compiles to the following instruction:

```asm
SEL Zresult.S, Pg, Zop1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SEL--vectors---Conditionally-select-elements-from-two-vectors-

### Operation

Source operation ID: `SveOperation_svsel_bf16`

**Operation**



Return a vector in which each active element *i* contains `op1[i]` and in which each inactive element *j* contains `op2[j]`.

## svsel[_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsel%5B_s64%5D

### Signature (source notation)

```c
svint64_t svsel[_s64](svbool_t pg, svint64_t op1, svint64_t op2);
```

### Description

Conditionally select elements

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Predication / Element selection / Select between two vectors

- SME attributes: Not specified by source.

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

This intrinsic compiles to the following instruction:

```asm
SEL Zresult.D, Pg, Zop1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SEL--vectors---Conditionally-select-elements-from-two-vectors-

### Operation

Source operation ID: `SveOperation_svsel_bf16`

**Operation**



Return a vector in which each active element *i* contains `op1[i]` and in which each inactive element *j* contains `op2[j]`.

## svsel[_s8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsel%5B_s8%5D

### Signature (source notation)

```c
svint8_t svsel[_s8](svbool_t pg, svint8_t op1, svint8_t op2);
```

### Description

Conditionally select elements

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Predication / Element selection / Select between two vectors

- SME attributes: Not specified by source.

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

This intrinsic compiles to the following instruction:

```asm
SEL Zresult.B, Pg, Zop1.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SEL--vectors---Conditionally-select-elements-from-two-vectors-

### Operation

Source operation ID: `SveOperation_svsel_bf16`

**Operation**



Return a vector in which each active element *i* contains `op1[i]` and in which each inactive element *j* contains `op2[j]`.

## svsel[_u16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsel%5B_u16%5D

### Signature (source notation)

```c
svuint16_t svsel[_u16](svbool_t pg, svuint16_t op1, svuint16_t op2);
```

### Description

Conditionally select elements

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Predication / Element selection / Select between two vectors

- SME attributes: Not specified by source.

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

This intrinsic compiles to the following instruction:

```asm
SEL Zresult.H, Pg, Zop1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SEL--vectors---Conditionally-select-elements-from-two-vectors-

### Operation

Source operation ID: `SveOperation_svsel_bf16`

**Operation**



Return a vector in which each active element *i* contains `op1[i]` and in which each inactive element *j* contains `op2[j]`.

## svsel[_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsel%5B_u32%5D

### Signature (source notation)

```c
svuint32_t svsel[_u32](svbool_t pg, svuint32_t op1, svuint32_t op2);
```

### Description

Conditionally select elements

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Predication / Element selection / Select between two vectors

- SME attributes: Not specified by source.

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

This intrinsic compiles to the following instruction:

```asm
SEL Zresult.S, Pg, Zop1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SEL--vectors---Conditionally-select-elements-from-two-vectors-

### Operation

Source operation ID: `SveOperation_svsel_bf16`

**Operation**



Return a vector in which each active element *i* contains `op1[i]` and in which each inactive element *j* contains `op2[j]`.

## svsel[_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsel%5B_u64%5D

### Signature (source notation)

```c
svuint64_t svsel[_u64](svbool_t pg, svuint64_t op1, svuint64_t op2);
```

### Description

Conditionally select elements

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Predication / Element selection / Select between two vectors

- SME attributes: Not specified by source.

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

This intrinsic compiles to the following instruction:

```asm
SEL Zresult.D, Pg, Zop1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SEL--vectors---Conditionally-select-elements-from-two-vectors-

### Operation

Source operation ID: `SveOperation_svsel_bf16`

**Operation**



Return a vector in which each active element *i* contains `op1[i]` and in which each inactive element *j* contains `op2[j]`.

## svsel[_u8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsel%5B_u8%5D

### Signature (source notation)

```c
svuint8_t svsel[_u8](svbool_t pg, svuint8_t op1, svuint8_t op2);
```

### Description

Conditionally select elements

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Predication / Element selection / Select between two vectors

- SME attributes: Not specified by source.

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

This intrinsic compiles to the following instruction:

```asm
SEL Zresult.B, Pg, Zop1.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SEL--vectors---Conditionally-select-elements-from-two-vectors-

### Operation

Source operation ID: `SveOperation_svsel_bf16`

**Operation**



Return a vector in which each active element *i* contains `op1[i]` and in which each inactive element *j* contains `op2[j]`.

