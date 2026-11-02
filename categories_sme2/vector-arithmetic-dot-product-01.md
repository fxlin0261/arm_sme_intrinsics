# SME2 / Vector arithmetic / Dot product — Part 1

## svdot[_f16_mf8]_fpm

ISA classification: SME2 + FEAT_SSVE_FP8DOT2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdot%5B_f16_mf8%5D_fpm

### Signature (source notation)

```c
svfloat16_t svdot[_f16_mf8]_fpm(svfloat16_t zda, svmfloat8_t zn, svmfloat8_t zm, fpm_t fpm);
```

### Description

8-bit floating-point dot product to half-precision

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Dot product

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME,FEAT_SSVE_FP8DOT2
```

### Return type metadata

```json
{
  "return_base_type": "float16",
  "element_bit_size": "16",
  "value": "svfloat16_t"
}
```

### Argument preparation and constraints

```json
{
  "zda": {
    "register": "Zreg1.H"
  },
  "zn": {
    "register": "Zreg2.B"
  },
  "zm": {
    "register": "Zreg3.B"
  },
  "fpm": {
    "register": "Xreg1"
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
MSR FPMR, Xreg1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/Base-Instructions/MSR--register---Move-general-purpose-register-to-System-register-

```asm
FDOT Zreg1.H, Zreg2.B, Zreg3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/FDOT--2-way--vectors--FP8-to-FP16---8-bit-floating-point-dot-product-to-half-precision-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svdot[_f32_f16]

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdot%5B_f32_f16%5D

### Signature (source notation)

```c
svfloat32_t svdot[_f32_f16](svfloat32_t zda, svfloat16_t zn, svfloat16_t zm);
```

### Description

Half-precision dot product to single-precision

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Dot product

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p1)|FEAT_SME2
```

### Return type metadata

```json
{
  "return_base_type": "float32",
  "element_bit_size": "32",
  "value": "svfloat32_t"
}
```

### Argument preparation and constraints

```json
{
  "zda": {
    "register": "Zreg1.S"
  },
  "zn": {
    "register": "Zreg2.H"
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
    "Zreg1.S": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
FDOT Zreg1.S, Zreg2.H, Zreg3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FDOT--2-way--vectors--FP16-to-FP32---Half-precision-dot-product-to-single-precision-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svdot[_f32_mf8]_fpm

ISA classification: SME2 + FEAT_SSVE_FP8DOT4

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdot%5B_f32_mf8%5D_fpm

### Signature (source notation)

```c
svfloat32_t svdot[_f32_mf8]_fpm(svfloat32_t zda, svmfloat8_t zn, svmfloat8_t zm, fpm_t fpm);
```

### Description

8-bit floating-point dot product to single-precision

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Dot product

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME,FEAT_SSVE_FP8DOT4
```

### Return type metadata

```json
{
  "return_base_type": "float32",
  "element_bit_size": "32",
  "value": "svfloat32_t"
}
```

### Argument preparation and constraints

```json
{
  "zda": {
    "register": "Zreg1.S"
  },
  "zn": {
    "register": "Zreg2.B"
  },
  "zm": {
    "register": "Zreg3.B"
  },
  "fpm": {
    "register": "Xreg1"
  }
}
```

### Result mapping

```json
[
  {
    "Zreg1.S": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
MSR FPMR, Xreg1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/Base-Instructions/MSR--register---Move-general-purpose-register-to-System-register-

```asm
FDOT Zreg1.S, Zreg2.B, Zreg3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/FDOT--4-way--vectors---8-bit-floating-point-dot-product-to-single-precision-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svdot[_n_f16_mf8]_fpm

ISA classification: SME2 + FEAT_SSVE_FP8DOT2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdot%5B_n_f16_mf8%5D_fpm

### Signature (source notation)

```c
svfloat16_t svdot[_n_f16_mf8]_fpm(svfloat16_t zda, svmfloat8_t zn, mfloat8_t zm, fpm_t fpm);
```

### Description

8-bit floating-point dot product to half-precision

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Dot product

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME,FEAT_SSVE_FP8DOT2
```

### Return type metadata

```json
{
  "return_base_type": "float16",
  "element_bit_size": "16",
  "value": "svfloat16_t"
}
```

### Argument preparation and constraints

```json
{
  "zda": {
    "register": "Zreg2.H"
  },
  "zn": {
    "register": "Zreg3.B"
  },
  "zm": {
    "register": "Breg1"
  },
  "fpm": {
    "register": "Xreg1"
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
MOV Zreg1.B, Breg1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/MOV--SIMD-FP-scalar--unpredicated---Move-indexed-element-or-SIMD-FP-scalar-to-vector--unpredicated---an-alias-of-DUP--indexed--

```asm
MSR FPMR, Xreg1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/Base-Instructions/MSR--register---Move-general-purpose-register-to-System-register-

```asm
FDOT Zreg2.H, Zreg3.B, Zreg1.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/FDOT--2-way--vectors--FP8-to-FP16---8-bit-floating-point-dot-product-to-half-precision-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svdot[_n_f32_mf8]_fpm

ISA classification: SME2 + FEAT_SSVE_FP8DOT4

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdot%5B_n_f32_mf8%5D_fpm

### Signature (source notation)

```c
svfloat32_t svdot[_n_f32_mf8]_fpm(svfloat32_t zda, svmfloat8_t zn, mfloat8_t zm, fpm_t fpm);
```

### Description

8-bit floating-point dot product to single-precision

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Dot product

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME,FEAT_SSVE_FP8DOT4
```

### Return type metadata

```json
{
  "return_base_type": "float32",
  "element_bit_size": "32",
  "value": "svfloat32_t"
}
```

### Argument preparation and constraints

```json
{
  "zda": {
    "register": "Zreg2.S"
  },
  "zn": {
    "register": "Zreg3.B"
  },
  "zm": {
    "register": "Breg1"
  },
  "fpm": {
    "register": "Xreg1"
  }
}
```

### Result mapping

```json
[
  {
    "Zreg2.S": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
MOV Zreg1.B, Breg1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/MOV--SIMD-FP-scalar--unpredicated---Move-indexed-element-or-SIMD-FP-scalar-to-vector--unpredicated---an-alias-of-DUP--indexed--

```asm
MSR FPMR, Xreg1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/Base-Instructions/MSR--register---Move-general-purpose-register-to-System-register-

```asm
FDOT Zreg2.S, Zreg3.B, Zreg1.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/FDOT--4-way--vectors---8-bit-floating-point-dot-product-to-single-precision-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svdot[_s32_s16]

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdot%5B_s32_s16%5D

### Signature (source notation)

```c
svint32_t svdot[_s32_s16](svint32_t zda, svint16_t zn, svint16_t zm);
```

### Description

Signed integer dot product

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Dot product

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p1)|FEAT_SME2
```

### Return type metadata

```json
{
  "return_base_type": "int32",
  "element_bit_size": "32",
  "value": "svint32_t"
}
```

### Argument preparation and constraints

```json
{
  "zda": {
    "register": "Zreg1.S"
  },
  "zn": {
    "register": "Zreg2.H"
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
    "Zreg1.S": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
SDOT Zreg1.S, Zreg2.H, Zreg3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SDOT--2-way--vectors---Signed-integer-dot-product-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svdot[_u32_u16]

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdot%5B_u32_u16%5D

### Signature (source notation)

```c
svuint32_t svdot[_u32_u16](svuint32_t zda, svuint16_t zn, svuint16_t zm);
```

### Description

Unsigned integer dot product

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Dot product

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p1)|FEAT_SME2
```

### Return type metadata

```json
{
  "return_base_type": "uint32",
  "element_bit_size": "32",
  "value": "svuint32_t"
}
```

### Argument preparation and constraints

```json
{
  "zda": {
    "register": "Zreg1.S"
  },
  "zn": {
    "register": "Zreg2.H"
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
    "Zreg1.S": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
UDOT Zreg1.S, Zreg2.H, Zreg3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UDOT--2-way--vectors---Unsigned-integer-dot-product-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svdot_lane[_f16_mf8]_fpm

ISA classification: SME2 + FEAT_SSVE_FP8DOT2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdot_lane%5B_f16_mf8%5D_fpm

### Signature (source notation)

```c
svfloat16_t svdot_lane[_f16_mf8]_fpm(svfloat16_t zda, svmfloat8_t zn, svmfloat8_t zm, uint64_t imm0_7, fpm_t fpm);
```

### Description

8-bit floating-point dot product by indexed element to half-precision

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Dot product

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME,FEAT_SSVE_FP8DOT2
```

### Return type metadata

```json
{
  "return_base_type": "float16",
  "element_bit_size": "16",
  "value": "svfloat16_t"
}
```

### Argument preparation and constraints

```json
{
  "zda": {
    "register": "Zreg1.H"
  },
  "zn": {
    "register": "Zreg2.B"
  },
  "zm": {
    "register": "Zreg3.B"
  },
  "imm0_7": {
    "immediate": "imm1"
  },
  "fpm": {
    "register": "Xreg1"
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
MSR FPMR, Xreg1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/Base-Instructions/MSR--register---Move-general-purpose-register-to-System-register-

```asm
FDOT Zreg1.H, Zreg2.B, Zreg3.B[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/FDOT--2-way--indexed--FP8-to-FP16---8-bit-floating-point-dot-product-by-indexed-element-to-half-precision-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svdot_lane[_f32_f16]

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdot_lane%5B_f32_f16%5D

### Signature (source notation)

```c
svfloat32_t svdot_lane[_f32_f16](svfloat32_t zda, svfloat16_t zn, svfloat16_t zm, uint64_t imm_idx);
```

### Description

Half-precision indexed dot product to single-precision

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Dot product

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p1)|FEAT_SME2
```

### Return type metadata

```json
{
  "return_base_type": "float32",
  "element_bit_size": "32",
  "value": "svfloat32_t"
}
```

### Argument preparation and constraints

```json
{
  "zda": {
    "register": "Zreg1.S"
  },
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
    "Zreg1.S": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
FDOT Zreg1.S, Zreg2.H, Zreg3.H[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FDOT--2-way--indexed--FP16-to-FP32---Half-precision-indexed-dot-product-to-single-precision-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svdot_lane[_f32_mf8]_fpm

ISA classification: SME2 + FEAT_SSVE_FP8DOT4

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdot_lane%5B_f32_mf8%5D_fpm

### Signature (source notation)

```c
svfloat32_t svdot_lane[_f32_mf8]_fpm(svfloat32_t zda, svmfloat8_t zn, svmfloat8_t zm, uint64_t imm0_3, fpm_t fpm);
```

### Description

8-bit floating-point dot product by indexed element to single-precision

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Dot product

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME,FEAT_SSVE_FP8DOT4
```

### Return type metadata

```json
{
  "return_base_type": "float32",
  "element_bit_size": "32",
  "value": "svfloat32_t"
}
```

### Argument preparation and constraints

```json
{
  "zda": {
    "register": "Zreg1.S"
  },
  "zn": {
    "register": "Zreg2.B"
  },
  "zm": {
    "register": "Zreg3.B"
  },
  "imm0_3": {
    "immediate": "imm1"
  },
  "fpm": {
    "register": "Xreg1"
  }
}
```

### Result mapping

```json
[
  {
    "Zreg1.S": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
MSR FPMR, Xreg1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/Base-Instructions/MSR--register---Move-general-purpose-register-to-System-register-

```asm
FDOT Zreg1.S, Zreg2.B, Zreg3.B[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/FDOT--4-way--indexed---8-bit-floating-point-dot-product-by-indexed-element-to-single-precision-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svdot_lane[_s32_s16]

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdot_lane%5B_s32_s16%5D

### Signature (source notation)

```c
svint32_t svdot_lane[_s32_s16](svint32_t zda, svint16_t zn, svint16_t zm, uint64_t imm_idx);
```

### Description

Signed integer indexed dot product

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Dot product

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p1)|FEAT_SME2
```

### Return type metadata

```json
{
  "return_base_type": "int32",
  "element_bit_size": "32",
  "value": "svint32_t"
}
```

### Argument preparation and constraints

```json
{
  "zda": {
    "register": "Zreg1.S"
  },
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
    "Zreg1.S": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
SDOT Zreg1.S, Zreg2.H, Zreg3.H[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SDOT--2-way--indexed---Signed-integer-indexed-dot-product-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svdot_lane[_u32_u16]

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdot_lane%5B_u32_u16%5D

### Signature (source notation)

```c
svuint32_t svdot_lane[_u32_u16](svuint32_t zda, svuint16_t zn, svuint16_t zm, uint64_t imm_idx);
```

### Description

Unsigned integer indexed dot product

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Dot product

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p1)|FEAT_SME2
```

### Return type metadata

```json
{
  "return_base_type": "uint32",
  "element_bit_size": "32",
  "value": "svuint32_t"
}
```

### Argument preparation and constraints

```json
{
  "zda": {
    "register": "Zreg1.S"
  },
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
    "Zreg1.S": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
UDOT Zreg1.S, Zreg2.H, Zreg3.H[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UDOT--2-way--indexed---Unsigned-integer-indexed-dot-product-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

