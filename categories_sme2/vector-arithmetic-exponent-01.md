# SME2 / Vector arithmetic / Exponent — Part 1

## svexpa[_f16]

ISA classification: SME2 + FEAT_SSVE_FEXPA

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svexpa%5B_f16%5D

### Signature (source notation)

```c
svfloat16_t svexpa[_f16](svuint16_t op);
```

### Description

Floating-point exponential accelerator

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Exponent

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2,FEAT_SSVE_FEXPA
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
  "op": {
    "register": "Zop.H"
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
FEXPA Zresult.H, Zop.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FEXPA--Floating-point-exponential-accelerator-

### Operation

Source operation ID: `SveOperation_svexpa_f16`

**Operation**



This function maps directly to the [FEXPA](https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/FEXPA--Floating-point-exponential-accelerator-) instruction; see there for a detailed description.

## svexpa[_f32]

ISA classification: SME2 + FEAT_SSVE_FEXPA

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svexpa%5B_f32%5D

### Signature (source notation)

```c
svfloat32_t svexpa[_f32](svuint32_t op);
```

### Description

Floating-point exponential accelerator

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Exponent

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2,FEAT_SSVE_FEXPA
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
  "op": {
    "register": "Zop.S"
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
FEXPA Zresult.S, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FEXPA--Floating-point-exponential-accelerator-

### Operation

Source operation ID: `SveOperation_svexpa_f16`

**Operation**



This function maps directly to the [FEXPA](https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/FEXPA--Floating-point-exponential-accelerator-) instruction; see there for a detailed description.

## svexpa[_f64]

ISA classification: SME2 + FEAT_SSVE_FEXPA

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svexpa%5B_f64%5D

### Signature (source notation)

```c
svfloat64_t svexpa[_f64](svuint64_t op);
```

### Description

Floating-point exponential accelerator

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Exponent

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2,FEAT_SSVE_FEXPA
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
  "op": {
    "register": "Zop.D"
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
FEXPA Zresult.D, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FEXPA--Floating-point-exponential-accelerator-

### Operation

Source operation ID: `SveOperation_svexpa_f16`

**Operation**



This function maps directly to the [FEXPA](https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/FEXPA--Floating-point-exponential-accelerator-) instruction; see there for a detailed description.

## svscale[_bf16]_m

ISA classification: SME2 + FEAT_SVE_BFSCALE

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svscale%5B_bf16%5D_m

### Signature (source notation)

```c
svbfloat16_t svscale[_bf16]_m(svbool_t pg, svbfloat16_t zdn, svint16_t zm);
```

### Description

BFloat16 adjust exponent (predicated)

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Exponent

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SVE_BFSCALE,FEAT_SME2
```

### Return type metadata

```json
{
  "return_base_type": "bfloat16",
  "element_bit_size": "16",
  "value": "svbfloat16_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Preg1"
  },
  "zdn": {
    "register": "Zreg1.H"
  },
  "zm": {
    "register": "Zreg2.H"
  }
}
```

### Result mapping

```json
[
  {
    "Zreg1.H": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
BFSCALE Zreg1.H, Preg1/M, Zreg1.H, Zreg2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/BFSCALE--BFloat16-adjust-exponent--predicated--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svscale[_bf16]_x

ISA classification: SME2 + FEAT_SVE_BFSCALE

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svscale%5B_bf16%5D_x

### Signature (source notation)

```c
svbfloat16_t svscale[_bf16]_x(svbool_t pg, svbfloat16_t zdn, svint16_t zm);
```

### Description

BFloat16 adjust exponent (predicated)

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Exponent

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SVE_BFSCALE,FEAT_SME2
```

### Return type metadata

```json
{
  "return_base_type": "bfloat16",
  "element_bit_size": "16",
  "value": "svbfloat16_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Preg1"
  },
  "zdn": {
    "register": "Zreg1.H"
  },
  "zm": {
    "register": "Zreg2.H"
  }
}
```

### Result mapping

```json
[
  {
    "Zreg1.H": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
BFSCALE Zreg1.H, Preg1/M, Zreg1.H, Zreg2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/BFSCALE--BFloat16-adjust-exponent--predicated--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svscale[_bf16]_z

ISA classification: SME2 + FEAT_SVE_BFSCALE

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svscale%5B_bf16%5D_z

### Signature (source notation)

```c
svbfloat16_t svscale[_bf16]_z(svbool_t pg, svbfloat16_t zdn, svint16_t zm);
```

### Description

BFloat16 adjust exponent (predicated)

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Exponent

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SVE_BFSCALE,FEAT_SME2
```

### Return type metadata

```json
{
  "return_base_type": "bfloat16",
  "element_bit_size": "16",
  "value": "svbfloat16_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Preg1"
  },
  "zdn": {
    "register": "Zreg1.H"
  },
  "zm": {
    "register": "Zreg3.H"
  }
}
```

### Result mapping

```json
[
  {
    "Zreg1.H": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
MOVI Vreg2.2D, #0000000000000000
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SIMD-FP-Instructions/MOVI--Move-immediate--vector--

```asm
SEL Zreg1.H, Preg1, Zreg1.H, Zreg2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/SEL--vectors---Conditionally-select-elements-from-two-vectors-

```asm
BFSCALE Zreg1.H, Preg1/M, Zreg1.H, Zreg3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/BFSCALE--BFloat16-adjust-exponent--predicated--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svscale[_bf16_x2]

ISA classification: SME2 + FEAT_SVE_BFSCALE

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svscale%5B_bf16_x2%5D

### Signature (source notation)

```c
svbfloat16x2_t svscale[_bf16_x2](svbfloat16x2_t zdn, svint16x2_t zm)
    __arm_streaming;
```

### Description

Multi-vector BFloat16 adjust exponent

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Vector arithmetic / Exponent

- SME attributes: `__arm_streaming`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2,FEAT_SVE_BFSCALE
```

### Return type metadata

```json
{
  "return_base_type": "bfloat16",
  "element_bit_size": "16",
  "value": "svbfloat16x2_t"
}
```

### Argument preparation and constraints

```json
{
  "zdn": {
    "Z multi-vector": "{ Zreg1.H, Zreg2.H }"
  },
  "zm": {
    "Z multi-vector": "{ Zreg3.H, Zreg4.H }"
  }
}
```

### Result mapping

```json
[
  {
    "{ Zreg1.H, Zreg2.H }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
BFSCALE { Zreg1.H, Zreg2.H }, { Zreg1.H, Zreg2.H }, { Zreg3.H, Zreg4.H }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/BFSCALE--multiple-vectors---Multi-vector-BFloat16-adjust-exponent-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svscale[_bf16_x4]

ISA classification: SME2 + FEAT_SVE_BFSCALE

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svscale%5B_bf16_x4%5D

### Signature (source notation)

```c
svbfloat16x4_t svscale[_bf16_x4](svbfloat16x4_t zdn, svint16x4_t zm)
    __arm_streaming;
```

### Description

Multi-vector BFloat16 adjust exponent

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Vector arithmetic / Exponent

- SME attributes: `__arm_streaming`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2,FEAT_SVE_BFSCALE
```

### Return type metadata

```json
{
  "return_base_type": "bfloat16",
  "element_bit_size": "16",
  "value": "svbfloat16x4_t"
}
```

### Argument preparation and constraints

```json
{
  "zdn": {
    "Z multi-vector": "{ Zreg1.H - Zreg2.H }"
  },
  "zm": {
    "Z multi-vector": "{ Zreg3.H - Zreg4.H }"
  }
}
```

### Result mapping

```json
[
  {
    "{ Zreg1.H - Zreg2.H }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
BFSCALE { Zreg1.H - Zreg2.H }, { Zreg1.H - Zreg2.H }, { Zreg3.H - Zreg4.H }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/BFSCALE--multiple-vectors---Multi-vector-BFloat16-adjust-exponent-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svscale[_f16_x2]

ISA classification: SME2 + FEAT_FP8

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svscale%5B_f16_x2%5D

### Signature (source notation)

```c
svfloat16x2_t svscale[_f16_x2](svfloat16x2_t zd, svint16x2_t zm)
    __arm_streaming;
```

### Description

Multi-vector floating-point adjust exponent

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Vector arithmetic / Exponent

- SME attributes: `__arm_streaming`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2,FEAT_FP8
```

### Return type metadata

```json
{
  "return_base_type": "float16",
  "element_bit_size": "16",
  "value": "svfloat16x2_t"
}
```

### Argument preparation and constraints

```json
{
  "zd": {
    "Z multi-vector": "{ Zreg1.H, Zreg2.H }"
  },
  "zm": {
    "Z multi-vector": "{ Zreg3.H, Zreg4.H }"
  }
}
```

### Result mapping

```json
[
  {
    "{ Zreg1.H, Zreg2.H }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
FSCALE { Zreg1.H, Zreg2.H }, { Zreg1.H, Zreg2.H }, { Zreg3.H, Zreg4.H }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/FSCALE--multiple-vectors---Multi-vector-floating-point-adjust-exponent-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svscale[_f16_x4]

ISA classification: SME2 + FEAT_FP8

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svscale%5B_f16_x4%5D

### Signature (source notation)

```c
svfloat16x4_t svscale[_f16_x4](svfloat16x4_t zd, svint16x4_t zm)
    __arm_streaming;
```

### Description

Multi-vector floating-point adjust exponent

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Vector arithmetic / Exponent

- SME attributes: `__arm_streaming`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2,FEAT_FP8
```

### Return type metadata

```json
{
  "return_base_type": "float16",
  "element_bit_size": "16",
  "value": "svfloat16x4_t"
}
```

### Argument preparation and constraints

```json
{
  "zd": {
    "Z multi-vector": "{ Zreg1.H - Zreg2.H }"
  },
  "zm": {
    "Z multi-vector": "{ Zreg3.H - Zreg4.H }"
  }
}
```

### Result mapping

```json
[
  {
    "{ Zreg1.H - Zreg2.H }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
FSCALE { Zreg1.H - Zreg2.H }, { Zreg1.H - Zreg2.H }, { Zreg3.H - Zreg4.H }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/FSCALE--multiple-vectors---Multi-vector-floating-point-adjust-exponent-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svscale[_f32_x2]

ISA classification: SME2 + FEAT_FP8

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svscale%5B_f32_x2%5D

### Signature (source notation)

```c
svfloat32x2_t svscale[_f32_x2](svfloat32x2_t zd, svint32x2_t zm)
    __arm_streaming;
```

### Description

Multi-vector floating-point adjust exponent

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Vector arithmetic / Exponent

- SME attributes: `__arm_streaming`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2,FEAT_FP8
```

### Return type metadata

```json
{
  "return_base_type": "float32",
  "element_bit_size": "32",
  "value": "svfloat32x2_t"
}
```

### Argument preparation and constraints

```json
{
  "zd": {
    "Z multi-vector": "{ Zreg1.S, Zreg2.S }"
  },
  "zm": {
    "Z multi-vector": "{ Zreg3.S, Zreg4.S }"
  }
}
```

### Result mapping

```json
[
  {
    "{ Zreg1.S, Zreg2.S }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
FSCALE { Zreg1.S, Zreg2.S }, { Zreg1.S, Zreg2.S }, { Zreg3.S, Zreg4.S }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/FSCALE--multiple-vectors---Multi-vector-floating-point-adjust-exponent-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svscale[_f32_x4]

ISA classification: SME2 + FEAT_FP8

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svscale%5B_f32_x4%5D

### Signature (source notation)

```c
svfloat32x4_t svscale[_f32_x4](svfloat32x4_t zd, svint32x4_t zm)
    __arm_streaming;
```

### Description

Multi-vector floating-point adjust exponent

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Vector arithmetic / Exponent

- SME attributes: `__arm_streaming`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2,FEAT_FP8
```

### Return type metadata

```json
{
  "return_base_type": "float32",
  "element_bit_size": "32",
  "value": "svfloat32x4_t"
}
```

### Argument preparation and constraints

```json
{
  "zd": {
    "Z multi-vector": "{ Zreg1.S - Zreg2.S }"
  },
  "zm": {
    "Z multi-vector": "{ Zreg3.S - Zreg4.S }"
  }
}
```

### Result mapping

```json
[
  {
    "{ Zreg1.S - Zreg2.S }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
FSCALE { Zreg1.S - Zreg2.S }, { Zreg1.S - Zreg2.S }, { Zreg3.S - Zreg4.S }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/FSCALE--multiple-vectors---Multi-vector-floating-point-adjust-exponent-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svscale[_f64_x2]

ISA classification: SME2 + FEAT_FP8

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svscale%5B_f64_x2%5D

### Signature (source notation)

```c
svfloat64x2_t svscale[_f64_x2](svfloat64x2_t zd, svint64x2_t zm)
    __arm_streaming;
```

### Description

Multi-vector floating-point adjust exponent

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Vector arithmetic / Exponent

- SME attributes: `__arm_streaming`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2,FEAT_FP8
```

### Return type metadata

```json
{
  "return_base_type": "float64",
  "element_bit_size": "64",
  "value": "svfloat64x2_t"
}
```

### Argument preparation and constraints

```json
{
  "zd": {
    "Z multi-vector": "{ Zreg1.D, Zreg2.D }"
  },
  "zm": {
    "Z multi-vector": "{ Zreg3.D, Zreg4.D }"
  }
}
```

### Result mapping

```json
[
  {
    "{ Zreg1.D, Zreg2.D }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
FSCALE { Zreg1.D, Zreg2.D }, { Zreg1.D, Zreg2.D }, { Zreg3.D, Zreg4.D }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/FSCALE--multiple-vectors---Multi-vector-floating-point-adjust-exponent-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svscale[_f64_x4]

ISA classification: SME2 + FEAT_FP8

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svscale%5B_f64_x4%5D

### Signature (source notation)

```c
svfloat64x4_t svscale[_f64_x4](svfloat64x4_t zd, svint64x4_t zm)
    __arm_streaming;
```

### Description

Multi-vector floating-point adjust exponent

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Vector arithmetic / Exponent

- SME attributes: `__arm_streaming`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2,FEAT_FP8
```

### Return type metadata

```json
{
  "return_base_type": "float64",
  "element_bit_size": "64",
  "value": "svfloat64x4_t"
}
```

### Argument preparation and constraints

```json
{
  "zd": {
    "Z multi-vector": "{ Zreg1.D - Zreg2.D }"
  },
  "zm": {
    "Z multi-vector": "{ Zreg3.D - Zreg4.D }"
  }
}
```

### Result mapping

```json
[
  {
    "{ Zreg1.D - Zreg2.D }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
FSCALE { Zreg1.D - Zreg2.D }, { Zreg1.D - Zreg2.D }, { Zreg3.D - Zreg4.D }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/FSCALE--multiple-vectors---Multi-vector-floating-point-adjust-exponent-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svscale[_n_bf16]_m

ISA classification: SME2 + FEAT_SVE_BFSCALE

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svscale%5B_n_bf16%5D_m

### Signature (source notation)

```c
svbfloat16_t svscale[_n_bf16]_m(svbool_t pg, svbfloat16_t zdn, int16_t zm);
```

### Description

BFloat16 adjust exponent (predicated)

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Exponent

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SVE_BFSCALE,FEAT_SME2
```

### Return type metadata

```json
{
  "return_base_type": "bfloat16",
  "element_bit_size": "16",
  "value": "svbfloat16_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Preg1"
  },
  "zdn": {
    "register": "Zreg2.H"
  },
  "zm": {
    "register": "Wreg1"
  }
}
```

### Result mapping

```json
[
  {
    "Zreg2.H": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
MOV Zreg1.H, Wreg1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/MOV--scalar--unpredicated---Move-general-purpose-register-to-vector-elements--unpredicated---an-alias-of-DUP--scalar--

```asm
BFSCALE Zreg2.H, Preg1/M, Zreg2.H, Zreg1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/BFSCALE--BFloat16-adjust-exponent--predicated--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svscale[_n_bf16]_x

ISA classification: SME2 + FEAT_SVE_BFSCALE

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svscale%5B_n_bf16%5D_x

### Signature (source notation)

```c
svbfloat16_t svscale[_n_bf16]_x(svbool_t pg, svbfloat16_t zdn, int16_t zm);
```

### Description

BFloat16 adjust exponent (predicated)

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Exponent

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SVE_BFSCALE,FEAT_SME2
```

### Return type metadata

```json
{
  "return_base_type": "bfloat16",
  "element_bit_size": "16",
  "value": "svbfloat16_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Preg1"
  },
  "zdn": {
    "register": "Zreg2.H"
  },
  "zm": {
    "register": "Wreg1"
  }
}
```

### Result mapping

```json
[
  {
    "Zreg2.H": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
MOV Zreg1.H, Wreg1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/MOV--scalar--unpredicated---Move-general-purpose-register-to-vector-elements--unpredicated---an-alias-of-DUP--scalar--

```asm
BFSCALE Zreg2.H, Preg1/M, Zreg2.H, Zreg1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/BFSCALE--BFloat16-adjust-exponent--predicated--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svscale[_n_bf16]_z

ISA classification: SME2 + FEAT_SVE_BFSCALE

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svscale%5B_n_bf16%5D_z

### Signature (source notation)

```c
svbfloat16_t svscale[_n_bf16]_z(svbool_t pg, svbfloat16_t zdn, int16_t zm);
```

### Description

BFloat16 adjust exponent (predicated)

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Exponent

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SVE_BFSCALE,FEAT_SME2
```

### Return type metadata

```json
{
  "return_base_type": "bfloat16",
  "element_bit_size": "16",
  "value": "svbfloat16_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Preg1"
  },
  "zdn": {
    "register": "Zreg2.H"
  },
  "zm": {
    "register": "Wreg1"
  }
}
```

### Result mapping

```json
[
  {
    "Zreg2.H": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
MOVI Vreg3.2D, #0000000000000000
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SIMD-FP-Instructions/MOVI--Move-immediate--vector--

```asm
MOV Zreg1.H, Wreg1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/MOV--scalar--unpredicated---Move-general-purpose-register-to-vector-elements--unpredicated---an-alias-of-DUP--scalar--

```asm
SEL Zreg2.H, Preg1, Zreg2.H, Zreg3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/SEL--vectors---Conditionally-select-elements-from-two-vectors-

```asm
BFSCALE Zreg2.H, Preg1/M, Zreg2.H, Zreg1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/BFSCALE--BFloat16-adjust-exponent--predicated--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svscale[_single_bf16_x2]

ISA classification: SME2 + FEAT_SVE_BFSCALE

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svscale%5B_single_bf16_x2%5D

### Signature (source notation)

```c
svbfloat16x2_t svscale[_single_bf16_x2](svbfloat16x2_t zn, svint16_t zm)
    __arm_streaming;
```

### Description

Multi-vector BFloat16 adjust exponent by vector

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Vector arithmetic / Exponent

- SME attributes: `__arm_streaming`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2,FEAT_SVE_BFSCALE
```

### Return type metadata

```json
{
  "return_base_type": "bfloat16",
  "element_bit_size": "16",
  "value": "svbfloat16x2_t"
}
```

### Argument preparation and constraints

```json
{
  "zn": {
    "Z multi-vector": "{ Zreg1.H, Zreg2.H }"
  },
  "zm": {
    "register": "Zreg3.H"
  }
}
```

### Result mapping

```json
[
  {
    "{ Zreg1.H, Zreg2.H }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
BFSCALE { Zreg1.H, Zreg2.H }, { Zreg1.H, Zreg2.H }, Zreg3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/BFSCALE--multiple-and-single-vector---Multi-vector-BFloat16-adjust-exponent-by-vector-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svscale[_single_bf16_x4]

ISA classification: SME2 + FEAT_SVE_BFSCALE

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svscale%5B_single_bf16_x4%5D

### Signature (source notation)

```c
svbfloat16x4_t svscale[_single_bf16_x4](svbfloat16x4_t zn, svint16_t zm)
    __arm_streaming;
```

### Description

Multi-vector BFloat16 adjust exponent by vector

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Vector arithmetic / Exponent

- SME attributes: `__arm_streaming`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2,FEAT_SVE_BFSCALE
```

### Return type metadata

```json
{
  "return_base_type": "bfloat16",
  "element_bit_size": "16",
  "value": "svbfloat16x4_t"
}
```

### Argument preparation and constraints

```json
{
  "zn": {
    "Z multi-vector": "{ Zreg1.H - Zreg2.H }"
  },
  "zm": {
    "register": "Zreg3.H"
  }
}
```

### Result mapping

```json
[
  {
    "{ Zreg1.H - Zreg2.H }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
BFSCALE { Zreg1.H - Zreg2.H }, { Zreg1.H - Zreg2.H }, Zreg3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/BFSCALE--multiple-and-single-vector---Multi-vector-BFloat16-adjust-exponent-by-vector-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svscale[_single_f16_x2]

ISA classification: SME2 + FEAT_FP8

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svscale%5B_single_f16_x2%5D

### Signature (source notation)

```c
svfloat16x2_t svscale[_single_f16_x2](svfloat16x2_t zd, svint16_t zm)
    __arm_streaming;
```

### Description

Multi-vector floating-point adjust exponent by vector

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Vector arithmetic / Exponent

- SME attributes: `__arm_streaming`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2,FEAT_FP8
```

### Return type metadata

```json
{
  "return_base_type": "float16",
  "element_bit_size": "16",
  "value": "svfloat16x2_t"
}
```

### Argument preparation and constraints

```json
{
  "zd": {
    "Z multi-vector": "{ Zreg1.H, Zreg2.H }"
  },
  "zm": {
    "register": "Zreg3.H"
  }
}
```

### Result mapping

```json
[
  {
    "{ Zreg1.H, Zreg2.H }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
FSCALE { Zreg1.H, Zreg2.H }, { Zreg1.H, Zreg2.H }, Zreg3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/FSCALE--multiple-and-single-vector---Multi-vector-floating-point-adjust-exponent-by-vector-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svscale[_single_f16_x4]

ISA classification: SME2 + FEAT_FP8

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svscale%5B_single_f16_x4%5D

### Signature (source notation)

```c
svfloat16x4_t svscale[_single_f16_x4](svfloat16x4_t zd, svint16_t zm)
    __arm_streaming;
```

### Description

Multi-vector floating-point adjust exponent by vector

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Vector arithmetic / Exponent

- SME attributes: `__arm_streaming`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2,FEAT_FP8
```

### Return type metadata

```json
{
  "return_base_type": "float16",
  "element_bit_size": "16",
  "value": "svfloat16x4_t"
}
```

### Argument preparation and constraints

```json
{
  "zd": {
    "Z multi-vector": "{ Zreg1.H - Zreg2.H }"
  },
  "zm": {
    "register": "Zreg3.H"
  }
}
```

### Result mapping

```json
[
  {
    "{ Zreg1.H - Zreg2.H }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
FSCALE { Zreg1.H - Zreg2.H }, { Zreg1.H - Zreg2.H }, Zreg3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/FSCALE--multiple-and-single-vector---Multi-vector-floating-point-adjust-exponent-by-vector-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svscale[_single_f32_x2]

ISA classification: SME2 + FEAT_FP8

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svscale%5B_single_f32_x2%5D

### Signature (source notation)

```c
svfloat32x2_t svscale[_single_f32_x2](svfloat32x2_t zd, svint32_t zm)
    __arm_streaming;
```

### Description

Multi-vector floating-point adjust exponent by vector

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Vector arithmetic / Exponent

- SME attributes: `__arm_streaming`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2,FEAT_FP8
```

### Return type metadata

```json
{
  "return_base_type": "float32",
  "element_bit_size": "32",
  "value": "svfloat32x2_t"
}
```

### Argument preparation and constraints

```json
{
  "zd": {
    "Z multi-vector": "{ Zreg1.S, Zreg2.S }"
  },
  "zm": {
    "register": "Zreg3.S"
  }
}
```

### Result mapping

```json
[
  {
    "{ Zreg1.S, Zreg2.S }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
FSCALE { Zreg1.S, Zreg2.S }, { Zreg1.S, Zreg2.S }, Zreg3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/FSCALE--multiple-and-single-vector---Multi-vector-floating-point-adjust-exponent-by-vector-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svscale[_single_f32_x4]

ISA classification: SME2 + FEAT_FP8

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svscale%5B_single_f32_x4%5D

### Signature (source notation)

```c
svfloat32x4_t svscale[_single_f32_x4](svfloat32x4_t zd, svint32_t zm)
    __arm_streaming;
```

### Description

Multi-vector floating-point adjust exponent by vector

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Vector arithmetic / Exponent

- SME attributes: `__arm_streaming`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2,FEAT_FP8
```

### Return type metadata

```json
{
  "return_base_type": "float32",
  "element_bit_size": "32",
  "value": "svfloat32x4_t"
}
```

### Argument preparation and constraints

```json
{
  "zd": {
    "Z multi-vector": "{ Zreg1.S - Zreg2.S }"
  },
  "zm": {
    "register": "Zreg3.S"
  }
}
```

### Result mapping

```json
[
  {
    "{ Zreg1.S - Zreg2.S }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
FSCALE { Zreg1.S - Zreg2.S }, { Zreg1.S - Zreg2.S }, Zreg3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/FSCALE--multiple-and-single-vector---Multi-vector-floating-point-adjust-exponent-by-vector-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svscale[_single_f64_x2]

ISA classification: SME2 + FEAT_FP8

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svscale%5B_single_f64_x2%5D

### Signature (source notation)

```c
svfloat64x2_t svscale[_single_f64_x2](svfloat64x2_t zd, svint64_t zm)
    __arm_streaming;
```

### Description

Multi-vector floating-point adjust exponent by vector

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Vector arithmetic / Exponent

- SME attributes: `__arm_streaming`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2,FEAT_FP8
```

### Return type metadata

```json
{
  "return_base_type": "float64",
  "element_bit_size": "64",
  "value": "svfloat64x2_t"
}
```

### Argument preparation and constraints

```json
{
  "zd": {
    "Z multi-vector": "{ Zreg1.D, Zreg2.D }"
  },
  "zm": {
    "register": "Zreg3.D"
  }
}
```

### Result mapping

```json
[
  {
    "{ Zreg1.D, Zreg2.D }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
FSCALE { Zreg1.D, Zreg2.D }, { Zreg1.D, Zreg2.D }, Zreg3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/FSCALE--multiple-and-single-vector---Multi-vector-floating-point-adjust-exponent-by-vector-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svscale[_single_f64_x4]

ISA classification: SME2 + FEAT_FP8

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svscale%5B_single_f64_x4%5D

### Signature (source notation)

```c
svfloat64x4_t svscale[_single_f64_x4](svfloat64x4_t zd, svint64_t zm)
    __arm_streaming;
```

### Description

Multi-vector floating-point adjust exponent by vector

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Vector arithmetic / Exponent

- SME attributes: `__arm_streaming`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2,FEAT_FP8
```

### Return type metadata

```json
{
  "return_base_type": "float64",
  "element_bit_size": "64",
  "value": "svfloat64x4_t"
}
```

### Argument preparation and constraints

```json
{
  "zd": {
    "Z multi-vector": "{ Zreg1.D - Zreg2.D }"
  },
  "zm": {
    "register": "Zreg3.D"
  }
}
```

### Result mapping

```json
[
  {
    "{ Zreg1.D - Zreg2.D }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
FSCALE { Zreg1.D - Zreg2.D }, { Zreg1.D - Zreg2.D }, Zreg3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/FSCALE--multiple-and-single-vector---Multi-vector-floating-point-adjust-exponent-by-vector-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

