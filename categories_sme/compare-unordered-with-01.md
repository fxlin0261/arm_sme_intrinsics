# SME / Compare / Unordered with — Part 1

## svcmpuo[_f16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcmpuo%5B_f16%5D

### Signature (source notation)

```c
svbool_t svcmpuo[_f16](svbool_t pg, svfloat16_t op1, svfloat16_t op2);
```

### Description

Compare unordered with

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Compare / Unordered with

- SME attributes: Not specified by source.

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
FCMUO Presult.H, Pg/Z, Zop1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCM-cc---vectors---Floating-point-compare-

### Operation

Source operation ID: `SveOperation_svcmpuo_f16`

**Operation**



Return a predicate in which element *i* is true iff element *i* is active and `op1[i]` is unordered with `op2[i]`.

## svcmpuo[_f32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcmpuo%5B_f32%5D

### Signature (source notation)

```c
svbool_t svcmpuo[_f32](svbool_t pg, svfloat32_t op1, svfloat32_t op2);
```

### Description

Compare unordered with

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Compare / Unordered with

- SME attributes: Not specified by source.

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
FCMUO Presult.S, Pg/Z, Zop1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCM-cc---vectors---Floating-point-compare-

### Operation

Source operation ID: `SveOperation_svcmpuo_f16`

**Operation**



Return a predicate in which element *i* is true iff element *i* is active and `op1[i]` is unordered with `op2[i]`.

## svcmpuo[_f64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcmpuo%5B_f64%5D

### Signature (source notation)

```c
svbool_t svcmpuo[_f64](svbool_t pg, svfloat64_t op1, svfloat64_t op2);
```

### Description

Compare unordered with

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Compare / Unordered with

- SME attributes: Not specified by source.

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
FCMUO Presult.D, Pg/Z, Zop1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCM-cc---vectors---Floating-point-compare-

### Operation

Source operation ID: `SveOperation_svcmpuo_f16`

**Operation**



Return a predicate in which element *i* is true iff element *i* is active and `op1[i]` is unordered with `op2[i]`.

## svcmpuo[_n_f16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcmpuo%5B_n_f16%5D

### Signature (source notation)

```c
svbool_t svcmpuo[_n_f16](svbool_t pg, svfloat16_t op1, float16_t op2);
```

### Description

Compare unordered with

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Compare / Unordered with

- SME attributes: Not specified by source.

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
FCMUO Presult.H, Pg/Z, Zop1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCM-cc---vectors---Floating-point-compare-

### Operation

Source operation ID: `SveOperation_svcmpuo_n_f16`

**Operation**



Return a predicate in which element *i* is true iff element *i* is active and `op1[i]` is unordered with `op2`.

## svcmpuo[_n_f32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcmpuo%5B_n_f32%5D

### Signature (source notation)

```c
svbool_t svcmpuo[_n_f32](svbool_t pg, svfloat32_t op1, float32_t op2);
```

### Description

Compare unordered with

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Compare / Unordered with

- SME attributes: Not specified by source.

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
FCMUO Presult.S, Pg/Z, Zop1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCM-cc---vectors---Floating-point-compare-

### Operation

Source operation ID: `SveOperation_svcmpuo_n_f16`

**Operation**



Return a predicate in which element *i* is true iff element *i* is active and `op1[i]` is unordered with `op2`.

## svcmpuo[_n_f64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcmpuo%5B_n_f64%5D

### Signature (source notation)

```c
svbool_t svcmpuo[_n_f64](svbool_t pg, svfloat64_t op1, float64_t op2);
```

### Description

Compare unordered with

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Compare / Unordered with

- SME attributes: Not specified by source.

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
FCMUO Presult.D, Pg/Z, Zop1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCM-cc---vectors---Floating-point-compare-

### Operation

Source operation ID: `SveOperation_svcmpuo_n_f16`

**Operation**



Return a predicate in which element *i* is true iff element *i* is active and `op1[i]` is unordered with `op2`.

