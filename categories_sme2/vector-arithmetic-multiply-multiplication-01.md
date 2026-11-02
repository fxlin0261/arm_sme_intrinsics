# SME2 / Vector arithmetic / Multiply / Multiplication — Part 1

## svmul[_bf16]_m

ISA classification: SME2 + FEAT_SVE_B16B16

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmul%5B_bf16%5D_m

### Signature (source notation)

```c
svbfloat16_t svmul[_bf16]_m(svbool_t pg, svbfloat16_t zdn, svbfloat16_t zm);
```

### Description

BFloat16 multiply (predicated)

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply / Multiplication

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2,FEAT_SVE_B16B16
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
BFMUL Zreg1.H, Preg1/M, Zreg1.H, Zreg2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/BFMUL--vectors--predicated---BFloat16-multiply--predicated--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmul[_bf16]_x

ISA classification: SME2 + FEAT_SVE_B16B16

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmul%5B_bf16%5D_x

### Signature (source notation)

```c
svbfloat16_t svmul[_bf16]_x(svbool_t pg, svbfloat16_t zdn, svbfloat16_t zm);
```

### Description

BFloat16 multiply (predicated)

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply / Multiplication

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2,FEAT_SVE_B16B16
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
BFMUL Zreg1.H, Preg1/M, Zreg1.H, Zreg2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/BFMUL--vectors--predicated---BFloat16-multiply--predicated--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmul[_bf16]_z

ISA classification: SME2 + FEAT_SVE_B16B16

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmul%5B_bf16%5D_z

### Signature (source notation)

```c
svbfloat16_t svmul[_bf16]_z(svbool_t pg, svbfloat16_t zdn, svbfloat16_t zm);
```

### Description

BFloat16 multiply (predicated)

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply / Multiplication

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2,FEAT_SVE_B16B16
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
BFMUL Zreg1.H, Preg1/M, Zreg1.H, Zreg3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/BFMUL--vectors--predicated---BFloat16-multiply--predicated--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmul[_bf16_x2]

ISA classification: SME2 + FEAT_SVE_BFSCALE

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmul%5B_bf16_x2%5D

### Signature (source notation)

```c
svbfloat16x2_t svmul[_bf16_x2](svbfloat16x2_t zd, svbfloat16x2_t zm)
    __arm_streaming;
```

### Description

Multi-vector BFloat16 multiply

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply / Multiplication

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
BFMUL { Zreg1.H, Zreg2.H }, { Zreg1.H, Zreg2.H }, { Zreg3.H, Zreg4.H }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/BFMUL--multiple-vectors---Multi-vector-BFloat16-multiply-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmul[_bf16_x4]

ISA classification: SME2 + FEAT_SVE_BFSCALE

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmul%5B_bf16_x4%5D

### Signature (source notation)

```c
svbfloat16x4_t svmul[_bf16_x4](svbfloat16x4_t zd, svbfloat16x4_t zm)
    __arm_streaming;
```

### Description

Multi-vector BFloat16 multiply

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply / Multiplication

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
BFMUL { Zreg1.H - Zreg2.H }, { Zreg1.H - Zreg2.H }, { Zreg3.H - Zreg4.H }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/BFMUL--multiple-vectors---Multi-vector-BFloat16-multiply-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmul[_f16_x2]

ISA classification: SME2.2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmul%5B_f16_x2%5D

### Signature (source notation)

```c
svfloat16x2_t svmul[_f16_x2](svfloat16x2_t zd, svfloat16x2_t zm)
    __arm_streaming;
```

### Description

Multi-vector floating-point multiply

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply / Multiplication

- SME attributes: `__arm_streaming`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2p2
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
FMUL { Zreg1.H, Zreg2.H }, { Zreg1.H, Zreg2.H }, { Zreg3.H, Zreg4.H }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/FMUL--multiple-vectors---Multi-vector-floating-point-multiply-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmul[_f16_x4]

ISA classification: SME2.2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmul%5B_f16_x4%5D

### Signature (source notation)

```c
svfloat16x4_t svmul[_f16_x4](svfloat16x4_t zd, svfloat16x4_t zm)
    __arm_streaming;
```

### Description

Multi-vector floating-point multiply

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply / Multiplication

- SME attributes: `__arm_streaming`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2p2
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
FMUL { Zreg1.H - Zreg2.H }, { Zreg1.H - Zreg2.H }, { Zreg3.H - Zreg4.H }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/FMUL--multiple-vectors---Multi-vector-floating-point-multiply-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmul[_f32_x2]

ISA classification: SME2.2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmul%5B_f32_x2%5D

### Signature (source notation)

```c
svfloat32x2_t svmul[_f32_x2](svfloat32x2_t zd, svfloat32x2_t zm)
    __arm_streaming;
```

### Description

Multi-vector floating-point multiply

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply / Multiplication

- SME attributes: `__arm_streaming`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2p2
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
FMUL { Zreg1.S, Zreg2.S }, { Zreg1.S, Zreg2.S }, { Zreg3.S, Zreg4.S }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/FMUL--multiple-vectors---Multi-vector-floating-point-multiply-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmul[_f32_x4]

ISA classification: SME2.2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmul%5B_f32_x4%5D

### Signature (source notation)

```c
svfloat32x4_t svmul[_f32_x4](svfloat32x4_t zd, svfloat32x4_t zm)
    __arm_streaming;
```

### Description

Multi-vector floating-point multiply

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply / Multiplication

- SME attributes: `__arm_streaming`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2p2
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
FMUL { Zreg1.S - Zreg2.S }, { Zreg1.S - Zreg2.S }, { Zreg3.S - Zreg4.S }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/FMUL--multiple-vectors---Multi-vector-floating-point-multiply-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmul[_f64_x2]

ISA classification: SME2.2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmul%5B_f64_x2%5D

### Signature (source notation)

```c
svfloat64x2_t svmul[_f64_x2](svfloat64x2_t zd, svfloat64x2_t zm)
    __arm_streaming;
```

### Description

Multi-vector floating-point multiply

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply / Multiplication

- SME attributes: `__arm_streaming`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2p2
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
FMUL { Zreg1.D, Zreg2.D }, { Zreg1.D, Zreg2.D }, { Zreg3.D, Zreg4.D }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/FMUL--multiple-vectors---Multi-vector-floating-point-multiply-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmul[_f64_x4]

ISA classification: SME2.2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmul%5B_f64_x4%5D

### Signature (source notation)

```c
svfloat64x4_t svmul[_f64_x4](svfloat64x4_t zd, svfloat64x4_t zm)
    __arm_streaming;
```

### Description

Multi-vector floating-point multiply

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply / Multiplication

- SME attributes: `__arm_streaming`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2p2
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
FMUL { Zreg1.D - Zreg2.D }, { Zreg1.D - Zreg2.D }, { Zreg3.D - Zreg4.D }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/FMUL--multiple-vectors---Multi-vector-floating-point-multiply-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmul[_n_bf16]_m

ISA classification: SME2 + FEAT_SVE_B16B16

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmul%5B_n_bf16%5D_m

### Signature (source notation)

```c
svbfloat16_t svmul[_n_bf16]_m(svbool_t pg, svbfloat16_t zdn, bfloat16_t zm);
```

### Description

BFloat16 multiply (predicated)

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply / Multiplication

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2,FEAT_SVE_B16B16
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
    "register": "Hreg1"
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
MOV Zreg1.H, Hreg1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/MOV--SIMD-FP-scalar--unpredicated---Move-indexed-element-or-SIMD-FP-scalar-to-vector--unpredicated---an-alias-of-DUP--indexed--

```asm
BFMUL Zreg2.H, Preg1/M, Zreg2.H, Zreg1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/BFMUL--vectors--predicated---BFloat16-multiply--predicated--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmul[_n_bf16]_x

ISA classification: SME2 + FEAT_SVE_B16B16

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmul%5B_n_bf16%5D_x

### Signature (source notation)

```c
svbfloat16_t svmul[_n_bf16]_x(svbool_t pg, svbfloat16_t zdn, bfloat16_t zm);
```

### Description

BFloat16 multiply (predicated)

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply / Multiplication

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2,FEAT_SVE_B16B16
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
    "register": "Hreg1"
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
MOV Zreg1.H, Hreg1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/MOV--SIMD-FP-scalar--unpredicated---Move-indexed-element-or-SIMD-FP-scalar-to-vector--unpredicated---an-alias-of-DUP--indexed--

```asm
BFMUL Zreg2.H, Preg1/M, Zreg2.H, Zreg1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/BFMUL--vectors--predicated---BFloat16-multiply--predicated--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmul[_n_bf16]_z

ISA classification: SME2 + FEAT_SVE_B16B16

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmul%5B_n_bf16%5D_z

### Signature (source notation)

```c
svbfloat16_t svmul[_n_bf16]_z(svbool_t pg, svbfloat16_t zdn, bfloat16_t zm);
```

### Description

BFloat16 multiply (predicated)

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply / Multiplication

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2,FEAT_SVE_B16B16
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
    "register": "Hreg1"
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
MOV Zreg1.H, Hreg1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/MOV--SIMD-FP-scalar--unpredicated---Move-indexed-element-or-SIMD-FP-scalar-to-vector--unpredicated---an-alias-of-DUP--indexed--

```asm
SEL Zreg2.H, Preg1, Zreg2.H, Zreg3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/SEL--vectors---Conditionally-select-elements-from-two-vectors-

```asm
BFMUL Zreg2.H, Preg1/M, Zreg2.H, Zreg1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/BFMUL--vectors--predicated---BFloat16-multiply--predicated--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmul[_single_bf16_x2]

ISA classification: SME2 + FEAT_SVE_BFSCALE

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmul%5B_single_bf16_x2%5D

### Signature (source notation)

```c
svbfloat16x2_t svmul[_single_bf16_x2](svbfloat16x2_t zd, svbfloat16_t zm)
    __arm_streaming;
```

### Description

Multi-vector BFloat16 multiply by vector

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply / Multiplication

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
BFMUL { Zreg1.H, Zreg2.H }, { Zreg1.H, Zreg2.H }, Zreg3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/BFMUL--multiple-and-single-vector---Multi-vector-BFloat16-multiply-by-vector-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmul[_single_bf16_x4]

ISA classification: SME2 + FEAT_SVE_BFSCALE

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmul%5B_single_bf16_x4%5D

### Signature (source notation)

```c
svbfloat16x4_t svmul[_single_bf16_x4](svbfloat16x4_t zd, svbfloat16_t zm)
    __arm_streaming;
```

### Description

Multi-vector BFloat16 multiply by vector

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply / Multiplication

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
BFMUL { Zreg1.H - Zreg2.H }, { Zreg1.H - Zreg2.H }, Zreg3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/BFMUL--multiple-and-single-vector---Multi-vector-BFloat16-multiply-by-vector-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmul[_single_f16_x2]

ISA classification: SME2.2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmul%5B_single_f16_x2%5D

### Signature (source notation)

```c
svfloat16x2_t svmul[_single_f16_x2](svfloat16x2_t zd, svfloat16_t zm)
    __arm_streaming;
```

### Description

Multi-vector floating-point multiply by vector

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply / Multiplication

- SME attributes: `__arm_streaming`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2p2
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
FMUL { Zreg1.H, Zreg2.H }, { Zreg1.H, Zreg2.H }, Zreg3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/FMUL--multiple-and-single-vector---Multi-vector-floating-point-multiply-by-vector-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmul[_single_f16_x4]

ISA classification: SME2.2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmul%5B_single_f16_x4%5D

### Signature (source notation)

```c
svfloat16x4_t svmul[_single_f16_x4](svfloat16x4_t zd, svfloat16_t zm)
    __arm_streaming;
```

### Description

Multi-vector floating-point multiply by vector

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply / Multiplication

- SME attributes: `__arm_streaming`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2p2
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
FMUL { Zreg1.H - Zreg2.H }, { Zreg1.H - Zreg2.H }, Zreg3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/FMUL--multiple-and-single-vector---Multi-vector-floating-point-multiply-by-vector-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmul[_single_f32_x2]

ISA classification: SME2.2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmul%5B_single_f32_x2%5D

### Signature (source notation)

```c
svfloat32x2_t svmul[_single_f32_x2](svfloat32x2_t zd, svfloat32_t zm)
    __arm_streaming;
```

### Description

Multi-vector floating-point multiply by vector

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply / Multiplication

- SME attributes: `__arm_streaming`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2p2
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
FMUL { Zreg1.S, Zreg2.S }, { Zreg1.S, Zreg2.S }, Zreg3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/FMUL--multiple-and-single-vector---Multi-vector-floating-point-multiply-by-vector-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmul[_single_f32_x4]

ISA classification: SME2.2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmul%5B_single_f32_x4%5D

### Signature (source notation)

```c
svfloat32x4_t svmul[_single_f32_x4](svfloat32x4_t zd, svfloat32_t zm)
    __arm_streaming;
```

### Description

Multi-vector floating-point multiply by vector

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply / Multiplication

- SME attributes: `__arm_streaming`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2p2
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
FMUL { Zreg1.S - Zreg2.S }, { Zreg1.S - Zreg2.S }, Zreg3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/FMUL--multiple-and-single-vector---Multi-vector-floating-point-multiply-by-vector-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmul[_single_f64_x2]

ISA classification: SME2.2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmul%5B_single_f64_x2%5D

### Signature (source notation)

```c
svfloat64x2_t svmul[_single_f64_x2](svfloat64x2_t zd, svfloat64_t zm)
    __arm_streaming;
```

### Description

Multi-vector floating-point multiply by vector

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply / Multiplication

- SME attributes: `__arm_streaming`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2p2
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
FMUL { Zreg1.D, Zreg2.D }, { Zreg1.D, Zreg2.D }, Zreg3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/FMUL--multiple-and-single-vector---Multi-vector-floating-point-multiply-by-vector-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmul[_single_f64_x4]

ISA classification: SME2.2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmul%5B_single_f64_x4%5D

### Signature (source notation)

```c
svfloat64x4_t svmul[_single_f64_x4](svfloat64x4_t zd, svfloat64_t zm)
    __arm_streaming;
```

### Description

Multi-vector floating-point multiply by vector

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply / Multiplication

- SME attributes: `__arm_streaming`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2p2
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
FMUL { Zreg1.D - Zreg2.D }, { Zreg1.D - Zreg2.D }, Zreg3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/FMUL--multiple-and-single-vector---Multi-vector-floating-point-multiply-by-vector-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmul_lane[_bf16]

ISA classification: SME2 + FEAT_SVE_B16B16

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmul_lane%5B_bf16%5D

### Signature (source notation)

```c
svbfloat16_t svmul_lane[_bf16](svbfloat16_t zn, svbfloat16_t zm, uint64_t imm_idx);
```

### Description

BFloat16 multiply by indexed element

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply / Multiplication

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2,FEAT_SVE_B16B16
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
  "zn": {
    "register": "Zreg2.H"
  },
  "zm": {
    "register": "Zreg3.H"
  },
  "imm_idx": {
    "immediate": "imm1"
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
BFMUL Zreg1.H, Zreg2.H, Zreg3.H[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/BFMUL--indexed---BFloat16-multiply-by-indexed-element-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

