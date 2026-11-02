# SME / Compare / Absolute greater than — Part 1

## svacgt[_f16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svacgt%5B_f16%5D

### Signature (source notation)

```c
svbool_t svacgt[_f16](svbool_t pg, svfloat16_t op1, svfloat16_t op2);
```

### Description

Absolute compare greater than

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Compare / Absolute greater than

- SME attributes: Not specified by source.

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
    "Presult.H": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
FACGT Presult.H, Pg/Z, Zop1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FAC-cc---Floating-point-absolute-compare-

### Operation

Source operation ID: `SveOperation_svacgt_f16`

**Operation**



Return a predicate in which element *i* is true iff element *i* is active and the absolute value of `op1[i]` is greater than the absolute value of `op2[i]`.



**Exceptions**



Active signaling and quiet NaNs both trigger an IEEE Invalid exception.

## svacgt[_f32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svacgt%5B_f32%5D

### Signature (source notation)

```c
svbool_t svacgt[_f32](svbool_t pg, svfloat32_t op1, svfloat32_t op2);
```

### Description

Absolute compare greater than

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Compare / Absolute greater than

- SME attributes: Not specified by source.

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
    "Presult.S": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
FACGT Presult.S, Pg/Z, Zop1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FAC-cc---Floating-point-absolute-compare-

### Operation

Source operation ID: `SveOperation_svacgt_f16`

**Operation**



Return a predicate in which element *i* is true iff element *i* is active and the absolute value of `op1[i]` is greater than the absolute value of `op2[i]`.



**Exceptions**



Active signaling and quiet NaNs both trigger an IEEE Invalid exception.

## svacgt[_f64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svacgt%5B_f64%5D

### Signature (source notation)

```c
svbool_t svacgt[_f64](svbool_t pg, svfloat64_t op1, svfloat64_t op2);
```

### Description

Absolute compare greater than

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Compare / Absolute greater than

- SME attributes: Not specified by source.

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
    "Presult.D": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
FACGT Presult.D, Pg/Z, Zop1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FAC-cc---Floating-point-absolute-compare-

### Operation

Source operation ID: `SveOperation_svacgt_f16`

**Operation**



Return a predicate in which element *i* is true iff element *i* is active and the absolute value of `op1[i]` is greater than the absolute value of `op2[i]`.



**Exceptions**



Active signaling and quiet NaNs both trigger an IEEE Invalid exception.

## svacgt[_n_f16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svacgt%5B_n_f16%5D

### Signature (source notation)

```c
svbool_t svacgt[_n_f16](svbool_t pg, svfloat16_t op1, float16_t op2);
```

### Description

Absolute compare greater than

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Compare / Absolute greater than

- SME attributes: Not specified by source.

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
    "Presult.H": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
FACGT Presult.H, Pg/Z, Zop1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FAC-cc---Floating-point-absolute-compare-

### Operation

Source operation ID: `SveOperation_svacgt_n_f16`

**Operation**



Return a predicate in which element *i* is true iff element *i* is active and the absolute value of `op1[i]` is greater than the absolute value of `op2`.



**Exceptions**



Active signaling and quiet NaNs both trigger an IEEE Invalid exception.  For these purposes, `op2` is active if any element of `op1` is active.

## svacgt[_n_f32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svacgt%5B_n_f32%5D

### Signature (source notation)

```c
svbool_t svacgt[_n_f32](svbool_t pg, svfloat32_t op1, float32_t op2);
```

### Description

Absolute compare greater than

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Compare / Absolute greater than

- SME attributes: Not specified by source.

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
    "Presult.S": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
FACGT Presult.S, Pg/Z, Zop1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FAC-cc---Floating-point-absolute-compare-

### Operation

Source operation ID: `SveOperation_svacgt_n_f16`

**Operation**



Return a predicate in which element *i* is true iff element *i* is active and the absolute value of `op1[i]` is greater than the absolute value of `op2`.



**Exceptions**



Active signaling and quiet NaNs both trigger an IEEE Invalid exception.  For these purposes, `op2` is active if any element of `op1` is active.

## svacgt[_n_f64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svacgt%5B_n_f64%5D

### Signature (source notation)

```c
svbool_t svacgt[_n_f64](svbool_t pg, svfloat64_t op1, float64_t op2);
```

### Description

Absolute compare greater than

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Compare / Absolute greater than

- SME attributes: Not specified by source.

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
    "Presult.D": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
FACGT Presult.D, Pg/Z, Zop1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FAC-cc---Floating-point-absolute-compare-

### Operation

Source operation ID: `SveOperation_svacgt_n_f16`

**Operation**



Return a predicate in which element *i* is true iff element *i* is active and the absolute value of `op1[i]` is greater than the absolute value of `op2`.



**Exceptions**



Active signaling and quiet NaNs both trigger an IEEE Invalid exception.  For these purposes, `op2` is active if any element of `op1` is active.

