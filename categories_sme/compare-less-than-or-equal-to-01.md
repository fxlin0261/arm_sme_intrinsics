# SME / Compare / Less than or equal to — Part 1

## svcmple[_f16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcmple%5B_f16%5D

### Signature (source notation)

```c
svbool_t svcmple[_f16](svbool_t pg, svfloat16_t op1, svfloat16_t op2);
```

### Description

Compare less than or equal to

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Compare / Less than or equal to

- SME attributes: Not specified by source.

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
FCMGE Presult.H, Pg/Z, Zop2.H, Zop1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCM-cc---vectors---Floating-point-compare-

### Operation

Source operation ID: `SveOperation_svcmple_f16`

**Operation**



Return a predicate in which element *i* is true iff element *i* is active and `op1[i]` is less than or equal to `op2[i]`.



**Exceptions**



Active signaling and quiet NaNs both trigger an IEEE Invalid exception.

## svcmple[_f32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcmple%5B_f32%5D

### Signature (source notation)

```c
svbool_t svcmple[_f32](svbool_t pg, svfloat32_t op1, svfloat32_t op2);
```

### Description

Compare less than or equal to

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Compare / Less than or equal to

- SME attributes: Not specified by source.

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
FCMGE Presult.S, Pg/Z, Zop2.S, Zop1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCM-cc---vectors---Floating-point-compare-

### Operation

Source operation ID: `SveOperation_svcmple_f16`

**Operation**



Return a predicate in which element *i* is true iff element *i* is active and `op1[i]` is less than or equal to `op2[i]`.



**Exceptions**



Active signaling and quiet NaNs both trigger an IEEE Invalid exception.

## svcmple[_f64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcmple%5B_f64%5D

### Signature (source notation)

```c
svbool_t svcmple[_f64](svbool_t pg, svfloat64_t op1, svfloat64_t op2);
```

### Description

Compare less than or equal to

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Compare / Less than or equal to

- SME attributes: Not specified by source.

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
FCMGE Presult.D, Pg/Z, Zop2.D, Zop1.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCM-cc---vectors---Floating-point-compare-

### Operation

Source operation ID: `SveOperation_svcmple_f16`

**Operation**



Return a predicate in which element *i* is true iff element *i* is active and `op1[i]` is less than or equal to `op2[i]`.



**Exceptions**



Active signaling and quiet NaNs both trigger an IEEE Invalid exception.

## svcmple[_n_f16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcmple%5B_n_f16%5D

### Signature (source notation)

```c
svbool_t svcmple[_n_f16](svbool_t pg, svfloat16_t op1, float16_t op2);
```

### Description

Compare less than or equal to

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Compare / Less than or equal to

- SME attributes: Not specified by source.

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

When op2 is 0.0, this intrinsic can use:

```asm
FCMLE Presult.H, Pg/Z, Zop1.H, #0.0
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCM-cc---zero---Floating-point-compare-with-zero-

The general implementation is:

```asm
FCMGE Presult.H, Pg/Z, Zop2.H, Zop1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCM-cc---vectors---Floating-point-compare-

### Operation

Source operation ID: `SveOperation_svcmple_n_f16`

**Operation**



Return a predicate in which element *i* is true iff element *i* is active and `op1[i]` is less than or equal to `op2`.



**Exceptions**



Active signaling and quiet NaNs both trigger an IEEE Invalid exception.  For these purposes, `op2` is active if any element of `op1` is active.

## svcmple[_n_f32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcmple%5B_n_f32%5D

### Signature (source notation)

```c
svbool_t svcmple[_n_f32](svbool_t pg, svfloat32_t op1, float32_t op2);
```

### Description

Compare less than or equal to

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Compare / Less than or equal to

- SME attributes: Not specified by source.

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

When op2 is 0.0, this intrinsic can use:

```asm
FCMLE Presult.S, Pg/Z, Zop1.S, #0.0
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCM-cc---zero---Floating-point-compare-with-zero-

The general implementation is:

```asm
FCMGE Presult.S, Pg/Z, Zop2.S, Zop1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCM-cc---vectors---Floating-point-compare-

### Operation

Source operation ID: `SveOperation_svcmple_n_f16`

**Operation**



Return a predicate in which element *i* is true iff element *i* is active and `op1[i]` is less than or equal to `op2`.



**Exceptions**



Active signaling and quiet NaNs both trigger an IEEE Invalid exception.  For these purposes, `op2` is active if any element of `op1` is active.

## svcmple[_n_f64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcmple%5B_n_f64%5D

### Signature (source notation)

```c
svbool_t svcmple[_n_f64](svbool_t pg, svfloat64_t op1, float64_t op2);
```

### Description

Compare less than or equal to

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Compare / Less than or equal to

- SME attributes: Not specified by source.

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

When op2 is 0.0, this intrinsic can use:

```asm
FCMLE Presult.D, Pg/Z, Zop1.D, #0.0
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCM-cc---zero---Floating-point-compare-with-zero-

The general implementation is:

```asm
FCMGE Presult.D, Pg/Z, Zop2.D, Zop1.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCM-cc---vectors---Floating-point-compare-

### Operation

Source operation ID: `SveOperation_svcmple_n_f16`

**Operation**



Return a predicate in which element *i* is true iff element *i* is active and `op1[i]` is less than or equal to `op2`.



**Exceptions**



Active signaling and quiet NaNs both trigger an IEEE Invalid exception.  For these purposes, `op2` is active if any element of `op1` is active.

## svcmple[_n_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcmple%5B_n_s16%5D

### Signature (source notation)

```c
svbool_t svcmple[_n_s16](svbool_t pg, svint16_t op1, int16_t op2);
```

### Description

Compare less than or equal to

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Compare / Less than or equal to

- SME attributes: Not specified by source.

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

When op2 is in the range [-16, 15], this intrinsic can use:

```asm
CMPLE Presult.H, Pg/Z, Zop1.H, #op2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CMP-cc---immediate---Compare-vector-to-immediate-

The general implementation is:

```asm
CMPGE Presult.H, Pg/Z, Zop2.H, Zop1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CMP-cc---vectors---Compare-vectors-

### Operation

Source operation ID: `SveOperation_svcmple_n_s8`

**Operation**



Return a predicate in which element *i* is true iff element *i* is active and `op1[i]` is less than or equal to `op2`.

## svcmple[_n_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcmple%5B_n_s32%5D

### Signature (source notation)

```c
svbool_t svcmple[_n_s32](svbool_t pg, svint32_t op1, int32_t op2);
```

### Description

Compare less than or equal to

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Compare / Less than or equal to

- SME attributes: Not specified by source.

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

When op2 is in the range [-16, 15], this intrinsic can use:

```asm
CMPLE Presult.S, Pg/Z, Zop1.S, #op2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CMP-cc---immediate---Compare-vector-to-immediate-

The general implementation is:

```asm
CMPGE Presult.S, Pg/Z, Zop2.S, Zop1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CMP-cc---vectors---Compare-vectors-

### Operation

Source operation ID: `SveOperation_svcmple_n_s8`

**Operation**



Return a predicate in which element *i* is true iff element *i* is active and `op1[i]` is less than or equal to `op2`.

## svcmple[_n_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcmple%5B_n_s64%5D

### Signature (source notation)

```c
svbool_t svcmple[_n_s64](svbool_t pg, svint64_t op1, int64_t op2);
```

### Description

Compare less than or equal to

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Compare / Less than or equal to

- SME attributes: Not specified by source.

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

When op2 is in the range [-16, 15], this intrinsic can use:

```asm
CMPLE Presult.D, Pg/Z, Zop1.D, #op2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CMP-cc---immediate---Compare-vector-to-immediate-

The general implementation is:

```asm
CMPGE Presult.D, Pg/Z, Zop2.D, Zop1.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CMP-cc---vectors---Compare-vectors-

### Operation

Source operation ID: `SveOperation_svcmple_n_s8`

**Operation**



Return a predicate in which element *i* is true iff element *i* is active and `op1[i]` is less than or equal to `op2`.

## svcmple[_n_s8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcmple%5B_n_s8%5D

### Signature (source notation)

```c
svbool_t svcmple[_n_s8](svbool_t pg, svint8_t op1, int8_t op2);
```

### Description

Compare less than or equal to

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Compare / Less than or equal to

- SME attributes: Not specified by source.

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
    "Presult.B": "result"
  }
]
```

### Instruction mapping

When op2 is in the range [-16, 15], this intrinsic can use:

```asm
CMPLE Presult.B, Pg/Z, Zop1.B, #op2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CMP-cc---immediate---Compare-vector-to-immediate-

The general implementation is:

```asm
CMPGE Presult.B, Pg/Z, Zop2.B, Zop1.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CMP-cc---vectors---Compare-vectors-

### Operation

Source operation ID: `SveOperation_svcmple_n_s8`

**Operation**



Return a predicate in which element *i* is true iff element *i* is active and `op1[i]` is less than or equal to `op2`.

## svcmple[_n_u16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcmple%5B_n_u16%5D

### Signature (source notation)

```c
svbool_t svcmple[_n_u16](svbool_t pg, svuint16_t op1, uint16_t op2);
```

### Description

Compare less than or equal to

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Compare / Less than or equal to

- SME attributes: Not specified by source.

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

When op2 is in the range [0, 127], this intrinsic can use:

```asm
CMPLS Presult.H, Pg/Z, Zop1.H, #op2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CMP-cc---immediate---Compare-vector-to-immediate-

The general implementation is:

```asm
CMPHS Presult.H, Pg/Z, Zop2.H, Zop1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CMP-cc---vectors---Compare-vectors-

### Operation

Source operation ID: `SveOperation_svcmple_n_s8`

**Operation**



Return a predicate in which element *i* is true iff element *i* is active and `op1[i]` is less than or equal to `op2`.

## svcmple[_n_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcmple%5B_n_u32%5D

### Signature (source notation)

```c
svbool_t svcmple[_n_u32](svbool_t pg, svuint32_t op1, uint32_t op2);
```

### Description

Compare less than or equal to

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Compare / Less than or equal to

- SME attributes: Not specified by source.

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

When op2 is in the range [0, 127], this intrinsic can use:

```asm
CMPLS Presult.S, Pg/Z, Zop1.S, #op2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CMP-cc---immediate---Compare-vector-to-immediate-

The general implementation is:

```asm
CMPHS Presult.S, Pg/Z, Zop2.S, Zop1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CMP-cc---vectors---Compare-vectors-

### Operation

Source operation ID: `SveOperation_svcmple_n_s8`

**Operation**



Return a predicate in which element *i* is true iff element *i* is active and `op1[i]` is less than or equal to `op2`.

## svcmple[_n_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcmple%5B_n_u64%5D

### Signature (source notation)

```c
svbool_t svcmple[_n_u64](svbool_t pg, svuint64_t op1, uint64_t op2);
```

### Description

Compare less than or equal to

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Compare / Less than or equal to

- SME attributes: Not specified by source.

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

When op2 is in the range [0, 127], this intrinsic can use:

```asm
CMPLS Presult.D, Pg/Z, Zop1.D, #op2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CMP-cc---immediate---Compare-vector-to-immediate-

The general implementation is:

```asm
CMPHS Presult.D, Pg/Z, Zop2.D, Zop1.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CMP-cc---vectors---Compare-vectors-

### Operation

Source operation ID: `SveOperation_svcmple_n_s8`

**Operation**



Return a predicate in which element *i* is true iff element *i* is active and `op1[i]` is less than or equal to `op2`.

## svcmple[_n_u8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcmple%5B_n_u8%5D

### Signature (source notation)

```c
svbool_t svcmple[_n_u8](svbool_t pg, svuint8_t op1, uint8_t op2);
```

### Description

Compare less than or equal to

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Compare / Less than or equal to

- SME attributes: Not specified by source.

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
    "Presult.B": "result"
  }
]
```

### Instruction mapping

When op2 is in the range [0, 127], this intrinsic can use:

```asm
CMPLS Presult.B, Pg/Z, Zop1.B, #op2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CMP-cc---immediate---Compare-vector-to-immediate-

The general implementation is:

```asm
CMPHS Presult.B, Pg/Z, Zop2.B, Zop1.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CMP-cc---vectors---Compare-vectors-

### Operation

Source operation ID: `SveOperation_svcmple_n_s8`

**Operation**



Return a predicate in which element *i* is true iff element *i* is active and `op1[i]` is less than or equal to `op2`.

## svcmple[_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcmple%5B_s16%5D

### Signature (source notation)

```c
svbool_t svcmple[_s16](svbool_t pg, svint16_t op1, svint16_t op2);
```

### Description

Compare less than or equal to

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Compare / Less than or equal to

- SME attributes: Not specified by source.

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
CMPGE Presult.H, Pg/Z, Zop2.H, Zop1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CMP-cc---vectors---Compare-vectors-

### Operation

Source operation ID: `SveOperation_svcmple_s8`

**Operation**



Return a predicate in which element *i* is true iff element *i* is active and `op1[i]` is less than or equal to `op2[i]`.

## svcmple[_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcmple%5B_s32%5D

### Signature (source notation)

```c
svbool_t svcmple[_s32](svbool_t pg, svint32_t op1, svint32_t op2);
```

### Description

Compare less than or equal to

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Compare / Less than or equal to

- SME attributes: Not specified by source.

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
CMPGE Presult.S, Pg/Z, Zop2.S, Zop1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CMP-cc---vectors---Compare-vectors-

### Operation

Source operation ID: `SveOperation_svcmple_s8`

**Operation**



Return a predicate in which element *i* is true iff element *i* is active and `op1[i]` is less than or equal to `op2[i]`.

## svcmple[_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcmple%5B_s64%5D

### Signature (source notation)

```c
svbool_t svcmple[_s64](svbool_t pg, svint64_t op1, svint64_t op2);
```

### Description

Compare less than or equal to

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Compare / Less than or equal to

- SME attributes: Not specified by source.

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
CMPGE Presult.D, Pg/Z, Zop2.D, Zop1.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CMP-cc---vectors---Compare-vectors-

### Operation

Source operation ID: `SveOperation_svcmple_s8`

**Operation**



Return a predicate in which element *i* is true iff element *i* is active and `op1[i]` is less than or equal to `op2[i]`.

## svcmple[_s8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcmple%5B_s8%5D

### Signature (source notation)

```c
svbool_t svcmple[_s8](svbool_t pg, svint8_t op1, svint8_t op2);
```

### Description

Compare less than or equal to

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Compare / Less than or equal to

- SME attributes: Not specified by source.

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
    "Presult.B": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
CMPGE Presult.B, Pg/Z, Zop2.B, Zop1.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CMP-cc---vectors---Compare-vectors-

### Operation

Source operation ID: `SveOperation_svcmple_s8`

**Operation**



Return a predicate in which element *i* is true iff element *i* is active and `op1[i]` is less than or equal to `op2[i]`.

## svcmple[_u16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcmple%5B_u16%5D

### Signature (source notation)

```c
svbool_t svcmple[_u16](svbool_t pg, svuint16_t op1, svuint16_t op2);
```

### Description

Compare less than or equal to

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Compare / Less than or equal to

- SME attributes: Not specified by source.

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
CMPHS Presult.H, Pg/Z, Zop2.H, Zop1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CMP-cc---vectors---Compare-vectors-

### Operation

Source operation ID: `SveOperation_svcmple_s8`

**Operation**



Return a predicate in which element *i* is true iff element *i* is active and `op1[i]` is less than or equal to `op2[i]`.

## svcmple[_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcmple%5B_u32%5D

### Signature (source notation)

```c
svbool_t svcmple[_u32](svbool_t pg, svuint32_t op1, svuint32_t op2);
```

### Description

Compare less than or equal to

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Compare / Less than or equal to

- SME attributes: Not specified by source.

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
CMPHS Presult.S, Pg/Z, Zop2.S, Zop1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CMP-cc---vectors---Compare-vectors-

### Operation

Source operation ID: `SveOperation_svcmple_s8`

**Operation**



Return a predicate in which element *i* is true iff element *i* is active and `op1[i]` is less than or equal to `op2[i]`.

## svcmple[_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcmple%5B_u64%5D

### Signature (source notation)

```c
svbool_t svcmple[_u64](svbool_t pg, svuint64_t op1, svuint64_t op2);
```

### Description

Compare less than or equal to

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Compare / Less than or equal to

- SME attributes: Not specified by source.

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
CMPHS Presult.D, Pg/Z, Zop2.D, Zop1.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CMP-cc---vectors---Compare-vectors-

### Operation

Source operation ID: `SveOperation_svcmple_s8`

**Operation**



Return a predicate in which element *i* is true iff element *i* is active and `op1[i]` is less than or equal to `op2[i]`.

## svcmple[_u8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcmple%5B_u8%5D

### Signature (source notation)

```c
svbool_t svcmple[_u8](svbool_t pg, svuint8_t op1, svuint8_t op2);
```

### Description

Compare less than or equal to

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Compare / Less than or equal to

- SME attributes: Not specified by source.

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
    "Presult.B": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
CMPHS Presult.B, Pg/Z, Zop2.B, Zop1.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CMP-cc---vectors---Compare-vectors-

### Operation

Source operation ID: `SveOperation_svcmple_s8`

**Operation**



Return a predicate in which element *i* is true iff element *i* is active and `op1[i]` is less than or equal to `op2[i]`.

## svcmple_wide[_n_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcmple_wide%5B_n_s16%5D

### Signature (source notation)

```c
svbool_t svcmple_wide[_n_s16](svbool_t pg, svint16_t op1, int64_t op2);
```

### Description

Compare less than or equal to

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Compare / Less than or equal to

- SME attributes: Not specified by source.

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
    "register": "Zop2.D[*]"
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

When op2 is in the range [-16, 15], this intrinsic can use:

```asm
CMPLE Presult.H, Pg/Z, Zop1.H, #op2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CMP-cc---immediate---Compare-vector-to-immediate-

The general implementation is:

```asm
CMPLE Presult.H, Pg/Z, Zop1.H, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CMP-cc---wide-elements---Compare-vector-to-64-bit-wide-elements-

### Operation

Source operation ID: `SveOperation_svcmple_n_s8`

**Operation**



Return a predicate in which element *i* is true iff element *i* is active and `op1[i]` is less than or equal to `op2`.

## svcmple_wide[_n_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcmple_wide%5B_n_s32%5D

### Signature (source notation)

```c
svbool_t svcmple_wide[_n_s32](svbool_t pg, svint32_t op1, int64_t op2);
```

### Description

Compare less than or equal to

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Compare / Less than or equal to

- SME attributes: Not specified by source.

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
    "register": "Zop2.D[*]"
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

When op2 is in the range [-16, 15], this intrinsic can use:

```asm
CMPLE Presult.S, Pg/Z, Zop1.S, #op2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CMP-cc---immediate---Compare-vector-to-immediate-

The general implementation is:

```asm
CMPLE Presult.S, Pg/Z, Zop1.S, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CMP-cc---wide-elements---Compare-vector-to-64-bit-wide-elements-

### Operation

Source operation ID: `SveOperation_svcmple_n_s8`

**Operation**



Return a predicate in which element *i* is true iff element *i* is active and `op1[i]` is less than or equal to `op2`.

## svcmple_wide[_n_s8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcmple_wide%5B_n_s8%5D

### Signature (source notation)

```c
svbool_t svcmple_wide[_n_s8](svbool_t pg, svint8_t op1, int64_t op2);
```

### Description

Compare less than or equal to

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Compare / Less than or equal to

- SME attributes: Not specified by source.

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
    "Presult.B": "result"
  }
]
```

### Instruction mapping

When op2 is in the range [-16, 15], this intrinsic can use:

```asm
CMPLE Presult.B, Pg/Z, Zop1.B, #op2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CMP-cc---immediate---Compare-vector-to-immediate-

The general implementation is:

```asm
CMPLE Presult.B, Pg/Z, Zop1.B, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CMP-cc---wide-elements---Compare-vector-to-64-bit-wide-elements-

### Operation

Source operation ID: `SveOperation_svcmple_n_s8`

**Operation**



Return a predicate in which element *i* is true iff element *i* is active and `op1[i]` is less than or equal to `op2`.

## svcmple_wide[_n_u16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcmple_wide%5B_n_u16%5D

### Signature (source notation)

```c
svbool_t svcmple_wide[_n_u16](svbool_t pg, svuint16_t op1, uint64_t op2);
```

### Description

Compare less than or equal to

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Compare / Less than or equal to

- SME attributes: Not specified by source.

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
    "register": "Zop2.D[*]"
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

When op2 is in the range [0, 127], this intrinsic can use:

```asm
CMPLS Presult.H, Pg/Z, Zop1.H, #op2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CMP-cc---immediate---Compare-vector-to-immediate-

The general implementation is:

```asm
CMPLS Presult.H, Pg/Z, Zop1.H, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CMP-cc---wide-elements---Compare-vector-to-64-bit-wide-elements-

### Operation

Source operation ID: `SveOperation_svcmple_n_s8`

**Operation**



Return a predicate in which element *i* is true iff element *i* is active and `op1[i]` is less than or equal to `op2`.

## svcmple_wide[_n_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcmple_wide%5B_n_u32%5D

### Signature (source notation)

```c
svbool_t svcmple_wide[_n_u32](svbool_t pg, svuint32_t op1, uint64_t op2);
```

### Description

Compare less than or equal to

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Compare / Less than or equal to

- SME attributes: Not specified by source.

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
    "register": "Zop2.D[*]"
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

When op2 is in the range [0, 127], this intrinsic can use:

```asm
CMPLS Presult.S, Pg/Z, Zop1.S, #op2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CMP-cc---immediate---Compare-vector-to-immediate-

The general implementation is:

```asm
CMPLS Presult.S, Pg/Z, Zop1.S, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CMP-cc---wide-elements---Compare-vector-to-64-bit-wide-elements-

### Operation

Source operation ID: `SveOperation_svcmple_n_s8`

**Operation**



Return a predicate in which element *i* is true iff element *i* is active and `op1[i]` is less than or equal to `op2`.

## svcmple_wide[_n_u8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcmple_wide%5B_n_u8%5D

### Signature (source notation)

```c
svbool_t svcmple_wide[_n_u8](svbool_t pg, svuint8_t op1, uint64_t op2);
```

### Description

Compare less than or equal to

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Compare / Less than or equal to

- SME attributes: Not specified by source.

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
    "Presult.B": "result"
  }
]
```

### Instruction mapping

When op2 is in the range [0, 127], this intrinsic can use:

```asm
CMPLS Presult.B, Pg/Z, Zop1.B, #op2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CMP-cc---immediate---Compare-vector-to-immediate-

The general implementation is:

```asm
CMPLS Presult.B, Pg/Z, Zop1.B, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CMP-cc---wide-elements---Compare-vector-to-64-bit-wide-elements-

### Operation

Source operation ID: `SveOperation_svcmple_n_s8`

**Operation**



Return a predicate in which element *i* is true iff element *i* is active and `op1[i]` is less than or equal to `op2`.

## svcmple_wide[_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcmple_wide%5B_s16%5D

### Signature (source notation)

```c
svbool_t svcmple_wide[_s16](svbool_t pg, svint16_t op1, svint64_t op2);
```

### Description

Compare less than or equal to

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Compare / Less than or equal to

- SME attributes: Not specified by source.

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
    "register": "Zop2.D"
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
CMPLE Presult.H, Pg/Z, Zop1.H, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CMP-cc---wide-elements---Compare-vector-to-64-bit-wide-elements-

### Operation

Source operation ID: `SveOperation_svcmple_wide_s16`

**Operation**



Return a predicate in which element *i* is true iff element *i* is active and `op1[i]` is less than or equal to `op2[i/4]`.

## svcmple_wide[_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcmple_wide%5B_s32%5D

### Signature (source notation)

```c
svbool_t svcmple_wide[_s32](svbool_t pg, svint32_t op1, svint64_t op2);
```

### Description

Compare less than or equal to

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Compare / Less than or equal to

- SME attributes: Not specified by source.

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
    "register": "Zop2.D"
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
CMPLE Presult.S, Pg/Z, Zop1.S, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CMP-cc---wide-elements---Compare-vector-to-64-bit-wide-elements-

### Operation

Source operation ID: `SveOperation_svcmple_wide_s32`

**Operation**



Return a predicate in which element *i* is true iff element *i* is active and `op1[i]` is less than or equal to `op2[i/2]`.

## svcmple_wide[_s8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcmple_wide%5B_s8%5D

### Signature (source notation)

```c
svbool_t svcmple_wide[_s8](svbool_t pg, svint8_t op1, svint64_t op2);
```

### Description

Compare less than or equal to

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Compare / Less than or equal to

- SME attributes: Not specified by source.

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
    "Presult.B": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
CMPLE Presult.B, Pg/Z, Zop1.B, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CMP-cc---wide-elements---Compare-vector-to-64-bit-wide-elements-

### Operation

Source operation ID: `SveOperation_svcmple_wide_s8`

**Operation**



Return a predicate in which element *i* is true iff element *i* is active and `op1[i]` is less than or equal to `op2[i/8]`.

## svcmple_wide[_u16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcmple_wide%5B_u16%5D

### Signature (source notation)

```c
svbool_t svcmple_wide[_u16](svbool_t pg, svuint16_t op1, svuint64_t op2);
```

### Description

Compare less than or equal to

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Compare / Less than or equal to

- SME attributes: Not specified by source.

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
    "register": "Zop2.D"
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
CMPLS Presult.H, Pg/Z, Zop1.H, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CMP-cc---wide-elements---Compare-vector-to-64-bit-wide-elements-

### Operation

Source operation ID: `SveOperation_svcmple_wide_s16`

**Operation**



Return a predicate in which element *i* is true iff element *i* is active and `op1[i]` is less than or equal to `op2[i/4]`.

## svcmple_wide[_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcmple_wide%5B_u32%5D

### Signature (source notation)

```c
svbool_t svcmple_wide[_u32](svbool_t pg, svuint32_t op1, svuint64_t op2);
```

### Description

Compare less than or equal to

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Compare / Less than or equal to

- SME attributes: Not specified by source.

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
    "register": "Zop2.D"
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
CMPLS Presult.S, Pg/Z, Zop1.S, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CMP-cc---wide-elements---Compare-vector-to-64-bit-wide-elements-

### Operation

Source operation ID: `SveOperation_svcmple_wide_s32`

**Operation**



Return a predicate in which element *i* is true iff element *i* is active and `op1[i]` is less than or equal to `op2[i/2]`.

## svcmple_wide[_u8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcmple_wide%5B_u8%5D

### Signature (source notation)

```c
svbool_t svcmple_wide[_u8](svbool_t pg, svuint8_t op1, svuint64_t op2);
```

### Description

Compare less than or equal to

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Compare / Less than or equal to

- SME attributes: Not specified by source.

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
    "Presult.B": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
CMPLS Presult.B, Pg/Z, Zop1.B, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CMP-cc---wide-elements---Compare-vector-to-64-bit-wide-elements-

### Operation

Source operation ID: `SveOperation_svcmple_wide_s8`

**Operation**



Return a predicate in which element *i* is true iff element *i* is active and `op1[i]` is less than or equal to `op2[i/8]`.

