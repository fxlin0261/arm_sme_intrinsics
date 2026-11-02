# SME / Vector arithmetic / Across vector arithmetic / Addition across vector widening — Part 1

## svaddv[_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svaddv%5B_s16%5D

### Signature (source notation)

```c
int64_t svaddv[_s16](svbool_t pg, svint16_t op);
```

### Description

Add reduction

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Across vector arithmetic / Addition across vector widening

- SME attributes: Not specified by source.

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
    "register": "Zop.H"
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
SADDV Dresult, Pg, Zop.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SADDV--Signed-add-reduction-to-scalar-

### Operation

Source operation ID: `SveOperation_svaddv_s8`

**Operation**



Add all active elements of `op` together, without loss of precision, and return the low 64 bits of the result. Return zero if no elements are active.

## svaddv[_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svaddv%5B_s32%5D

### Signature (source notation)

```c
int64_t svaddv[_s32](svbool_t pg, svint32_t op);
```

### Description

Add reduction

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Across vector arithmetic / Addition across vector widening

- SME attributes: Not specified by source.

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
    "register": "Zop.S"
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
SADDV Dresult, Pg, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SADDV--Signed-add-reduction-to-scalar-

### Operation

Source operation ID: `SveOperation_svaddv_s8`

**Operation**



Add all active elements of `op` together, without loss of precision, and return the low 64 bits of the result. Return zero if no elements are active.

## svaddv[_s8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svaddv%5B_s8%5D

### Signature (source notation)

```c
int64_t svaddv[_s8](svbool_t pg, svint8_t op);
```

### Description

Add reduction

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Across vector arithmetic / Addition across vector widening

- SME attributes: Not specified by source.

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
    "register": "Zop.B"
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
SADDV Dresult, Pg, Zop.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SADDV--Signed-add-reduction-to-scalar-

### Operation

Source operation ID: `SveOperation_svaddv_s8`

**Operation**



Add all active elements of `op` together, without loss of precision, and return the low 64 bits of the result. Return zero if no elements are active.

## svaddv[_u16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svaddv%5B_u16%5D

### Signature (source notation)

```c
uint64_t svaddv[_u16](svbool_t pg, svuint16_t op);
```

### Description

Add reduction

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Across vector arithmetic / Addition across vector widening

- SME attributes: Not specified by source.

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
    "register": "Zop.H"
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
UADDV Dresult, Pg, Zop.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UADDV--Unsigned-add-reduction-to-scalar-

### Operation

Source operation ID: `SveOperation_svaddv_s8`

**Operation**



Add all active elements of `op` together, without loss of precision, and return the low 64 bits of the result. Return zero if no elements are active.

## svaddv[_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svaddv%5B_u32%5D

### Signature (source notation)

```c
uint64_t svaddv[_u32](svbool_t pg, svuint32_t op);
```

### Description

Add reduction

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Across vector arithmetic / Addition across vector widening

- SME attributes: Not specified by source.

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
    "register": "Zop.S"
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
UADDV Dresult, Pg, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UADDV--Unsigned-add-reduction-to-scalar-

### Operation

Source operation ID: `SveOperation_svaddv_s8`

**Operation**



Add all active elements of `op` together, without loss of precision, and return the low 64 bits of the result. Return zero if no elements are active.

## svaddv[_u8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svaddv%5B_u8%5D

### Signature (source notation)

```c
uint64_t svaddv[_u8](svbool_t pg, svuint8_t op);
```

### Description

Add reduction

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Across vector arithmetic / Addition across vector widening

- SME attributes: Not specified by source.

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
    "register": "Zop.B"
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
UADDV Dresult, Pg, Zop.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UADDV--Unsigned-add-reduction-to-scalar-

### Operation

Source operation ID: `SveOperation_svaddv_s8`

**Operation**



Add all active elements of `op` together, without loss of precision, and return the low 64 bits of the result. Return zero if no elements are active.

