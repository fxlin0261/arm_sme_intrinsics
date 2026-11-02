# SME2 / ZA array / Accumulate / Dot product — Part 1

## svdot[_single]_za16[_mf8]_vg1x2_fpm

ISA classification: SME2 + FEAT_SME_F8F16

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdot%5B_single%5D_za16%5B_mf8%5D_vg1x2_fpm

### Signature (source notation)

```c
void svdot[_single]_za16[_mf8]_vg1x2_fpm(uint32_t slice, svmfloat8x2_t zn, svmfloat8_t zm, fpm_t fpm)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector 8-bit floating-point dot product by vector to half-precision

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Dot product

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME_F8F16
```

### Return type metadata

```json
{
  "return_base_type": "void",
  "element_bit_size": "8",
  "value": "void"
}
```

### Argument preparation and constraints

```json
{
  "slice": {
    "register+immediate": "Wreg2 + imm1"
  },
  "zn": {
    "Z multi-vector": "{ Zreg1.B, Zreg2.B }"
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
[]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
MSR FPMR, Xreg1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/Base-Instructions/MSR--register---Move-general-purpose-register-to-System-register-

```asm
FDOT ZA.H[Wreg2, imm1, VGX2], { Zreg1.B, Zreg2.B }, Zreg3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/FDOT--2-way--multiple-and-single-vector--FP8-to-FP16---Multi-vector-8-bit-floating-point-dot-product-by-vector-to-half-precision-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svdot[_single]_za16[_mf8]_vg1x4_fpm

ISA classification: SME2 + FEAT_SME_F8F16

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdot%5B_single%5D_za16%5B_mf8%5D_vg1x4_fpm

### Signature (source notation)

```c
void svdot[_single]_za16[_mf8]_vg1x4_fpm(uint32_t slice, svmfloat8x4_t zn, svmfloat8_t zm, fpm_t fpm)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector 8-bit floating-point dot product by vector to half-precision

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Dot product

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME_F8F16
```

### Return type metadata

```json
{
  "return_base_type": "void",
  "element_bit_size": "8",
  "value": "void"
}
```

### Argument preparation and constraints

```json
{
  "slice": {
    "register+immediate": "Wreg2 + imm1"
  },
  "zn": {
    "Z multi-vector": "{ Zreg1.B - Zreg2.B }"
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
[]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
MSR FPMR, Xreg1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/Base-Instructions/MSR--register---Move-general-purpose-register-to-System-register-

```asm
FDOT ZA.H[Wreg2, imm1, VGX4], { Zreg1.B - Zreg2.B }, Zreg3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/FDOT--2-way--multiple-and-single-vector--FP8-to-FP16---Multi-vector-8-bit-floating-point-dot-product-by-vector-to-half-precision-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svdot[_single]_za32[_bf16]_vg1x2

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdot%5B_single%5D_za32%5B_bf16%5D_vg1x2

### Signature (source notation)

```c
void svdot[_single]_za32[_bf16]_vg1x2(uint32_t slice, svbfloat16x2_t zn, svbfloat16_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector BFloat16 dot-product by vector

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Dot product

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2
```

### Return type metadata

```json
{
  "return_base_type": "void",
  "element_bit_size": "16",
  "value": "void"
}
```

### Argument preparation and constraints

```json
{
  "slice": {
    "register+immediate": "Wreg1 + imm1"
  },
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
[]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
BFDOT ZA.S[Wreg1, imm1, VGX2], { Zreg1.H, Zreg2.H }, Zreg3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/BFDOT--multiple-and-single-vector---Multi-vector-BFloat16-dot-product-by-vector-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svdot[_single]_za32[_bf16]_vg1x4

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdot%5B_single%5D_za32%5B_bf16%5D_vg1x4

### Signature (source notation)

```c
void svdot[_single]_za32[_bf16]_vg1x4(uint32_t slice, svbfloat16x4_t zn, svbfloat16_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector BFloat16 dot-product by vector

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Dot product

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2
```

### Return type metadata

```json
{
  "return_base_type": "void",
  "element_bit_size": "16",
  "value": "void"
}
```

### Argument preparation and constraints

```json
{
  "slice": {
    "register+immediate": "Wreg1 + imm1"
  },
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
[]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
BFDOT ZA.S[Wreg1, imm1, VGX4], { Zreg1.H - Zreg2.H }, Zreg3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/BFDOT--multiple-and-single-vector---Multi-vector-BFloat16-dot-product-by-vector-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svdot[_single]_za32[_f16]_vg1x2

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdot%5B_single%5D_za32%5B_f16%5D_vg1x2

### Signature (source notation)

```c
void svdot[_single]_za32[_f16]_vg1x2(uint32_t slice, svfloat16x2_t zn, svfloat16_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector half-precision dot-product by vector

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Dot product

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2
```

### Return type metadata

```json
{
  "return_base_type": "void",
  "element_bit_size": "16",
  "value": "void"
}
```

### Argument preparation and constraints

```json
{
  "slice": {
    "register+immediate": "Wreg1 + imm1"
  },
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
[]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
FDOT ZA.S[Wreg1, imm1, VGX2], { Zreg1.H, Zreg2.H }, Zreg3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/FDOT--2-way--multiple-and-single-vector--FP16-to-FP32---Multi-vector-half-precision-dot-product-by-vector-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svdot[_single]_za32[_f16]_vg1x4

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdot%5B_single%5D_za32%5B_f16%5D_vg1x4

### Signature (source notation)

```c
void svdot[_single]_za32[_f16]_vg1x4(uint32_t slice, svfloat16x4_t zn, svfloat16_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector half-precision dot-product by vector

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Dot product

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2
```

### Return type metadata

```json
{
  "return_base_type": "void",
  "element_bit_size": "16",
  "value": "void"
}
```

### Argument preparation and constraints

```json
{
  "slice": {
    "register+immediate": "Wreg1 + imm1"
  },
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
[]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
FDOT ZA.S[Wreg1, imm1, VGX4], { Zreg1.H - Zreg2.H }, Zreg3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/FDOT--2-way--multiple-and-single-vector--FP16-to-FP32---Multi-vector-half-precision-dot-product-by-vector-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svdot[_single]_za32[_mf8]_vg1x2_fpm

ISA classification: SME2 + FEAT_SME_F8F32

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdot%5B_single%5D_za32%5B_mf8%5D_vg1x2_fpm

### Signature (source notation)

```c
void svdot[_single]_za32[_mf8]_vg1x2_fpm(uint32_t slice, svmfloat8x2_t zn, svmfloat8_t zm, fpm_t fpm)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector 8-bit floating-point dot product by vector to single-precision

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Dot product

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME_F8F32
```

### Return type metadata

```json
{
  "return_base_type": "void",
  "element_bit_size": "8",
  "value": "void"
}
```

### Argument preparation and constraints

```json
{
  "slice": {
    "register+immediate": "Wreg2 + imm1"
  },
  "zn": {
    "Z multi-vector": "{ Zreg1.B, Zreg2.B }"
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
[]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
MSR FPMR, Xreg1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/Base-Instructions/MSR--register---Move-general-purpose-register-to-System-register-

```asm
FDOT ZA.S[Wreg2, imm1, VGX2], { Zreg1.B, Zreg2.B }, Zreg3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/FDOT--4-way--multiple-and-single-vector---Multi-vector-8-bit-floating-point-dot-product-by-vector-to-single-precision-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svdot[_single]_za32[_mf8]_vg1x4_fpm

ISA classification: SME2 + FEAT_SME_F8F32

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdot%5B_single%5D_za32%5B_mf8%5D_vg1x4_fpm

### Signature (source notation)

```c
void svdot[_single]_za32[_mf8]_vg1x4_fpm(uint32_t slice, svmfloat8x4_t zn, svmfloat8_t zm, fpm_t fpm)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector 8-bit floating-point dot product by vector to single-precision

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Dot product

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME_F8F32
```

### Return type metadata

```json
{
  "return_base_type": "void",
  "element_bit_size": "8",
  "value": "void"
}
```

### Argument preparation and constraints

```json
{
  "slice": {
    "register+immediate": "Wreg2 + imm1"
  },
  "zn": {
    "Z multi-vector": "{ Zreg1.B - Zreg2.B }"
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
[]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
MSR FPMR, Xreg1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/Base-Instructions/MSR--register---Move-general-purpose-register-to-System-register-

```asm
FDOT ZA.S[Wreg2, imm1, VGX4], { Zreg1.B - Zreg2.B }, Zreg3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/FDOT--4-way--multiple-and-single-vector---Multi-vector-8-bit-floating-point-dot-product-by-vector-to-single-precision-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svdot[_single]_za32[_s16]_vg1x2

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdot%5B_single%5D_za32%5B_s16%5D_vg1x2

### Signature (source notation)

```c
void svdot[_single]_za32[_s16]_vg1x2(uint32_t slice, svint16x2_t zn, svint16_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector signed integer dot-product by vector

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Dot product

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2
```

### Return type metadata

```json
{
  "return_base_type": "void",
  "element_bit_size": "16",
  "value": "void"
}
```

### Argument preparation and constraints

```json
{
  "slice": {
    "register+immediate": "Wreg1 + imm1"
  },
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
[]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
SDOT ZA.S[Wreg1, imm1, VGX2], { Zreg1.H, Zreg2.H }, Zreg3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SDOT--2-way--multiple-and-single-vector---Multi-vector-signed-integer-dot-product-by-vector-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svdot[_single]_za32[_s16]_vg1x4

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdot%5B_single%5D_za32%5B_s16%5D_vg1x4

### Signature (source notation)

```c
void svdot[_single]_za32[_s16]_vg1x4(uint32_t slice, svint16x4_t zn, svint16_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector signed integer dot-product by vector

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Dot product

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2
```

### Return type metadata

```json
{
  "return_base_type": "void",
  "element_bit_size": "16",
  "value": "void"
}
```

### Argument preparation and constraints

```json
{
  "slice": {
    "register+immediate": "Wreg1 + imm1"
  },
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
[]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
SDOT ZA.S[Wreg1, imm1, VGX4], { Zreg1.H - Zreg2.H }, Zreg3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SDOT--2-way--multiple-and-single-vector---Multi-vector-signed-integer-dot-product-by-vector-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svdot[_single]_za32[_s8]_vg1x2

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdot%5B_single%5D_za32%5B_s8%5D_vg1x2

### Signature (source notation)

```c
void svdot[_single]_za32[_s8]_vg1x2(uint32_t slice, svint8x2_t zn, svint8_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector signed integer dot-product by vector

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Dot product

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2
```

### Return type metadata

```json
{
  "return_base_type": "void",
  "element_bit_size": "8",
  "value": "void"
}
```

### Argument preparation and constraints

```json
{
  "slice": {
    "register+immediate": "Wreg1 + imm1"
  },
  "zn": {
    "Z multi-vector": "{ Zreg1.B, Zreg2.B }"
  },
  "zm": {
    "register": "Zreg3.B"
  }
}
```

### Result mapping

```json
[]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
SDOT ZA.S[Wreg1, imm1, VGX2], { Zreg1.B, Zreg2.B }, Zreg3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SDOT--4-way--multiple-and-single-vector---Multi-vector-signed-integer-dot-product-by-vector-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svdot[_single]_za32[_s8]_vg1x4

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdot%5B_single%5D_za32%5B_s8%5D_vg1x4

### Signature (source notation)

```c
void svdot[_single]_za32[_s8]_vg1x4(uint32_t slice, svint8x4_t zn, svint8_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector signed integer dot-product by vector

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Dot product

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2
```

### Return type metadata

```json
{
  "return_base_type": "void",
  "element_bit_size": "8",
  "value": "void"
}
```

### Argument preparation and constraints

```json
{
  "slice": {
    "register+immediate": "Wreg1 + imm1"
  },
  "zn": {
    "Z multi-vector": "{ Zreg1.B - Zreg2.B }"
  },
  "zm": {
    "register": "Zreg3.B"
  }
}
```

### Result mapping

```json
[]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
SDOT ZA.S[Wreg1, imm1, VGX4], { Zreg1.B - Zreg2.B }, Zreg3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SDOT--4-way--multiple-and-single-vector---Multi-vector-signed-integer-dot-product-by-vector-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svdot[_single]_za32[_u16]_vg1x2

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdot%5B_single%5D_za32%5B_u16%5D_vg1x2

### Signature (source notation)

```c
void svdot[_single]_za32[_u16]_vg1x2(uint32_t slice, svuint16x2_t zn, svuint16_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector unsigned integer dot-product by vector

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Dot product

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2
```

### Return type metadata

```json
{
  "return_base_type": "void",
  "element_bit_size": "16",
  "value": "void"
}
```

### Argument preparation and constraints

```json
{
  "slice": {
    "register+immediate": "Wreg1 + imm1"
  },
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
[]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
UDOT ZA.S[Wreg1, imm1, VGX2], { Zreg1.H, Zreg2.H }, Zreg3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/UDOT--2-way--multiple-and-single-vector---Multi-vector-unsigned-integer-dot-product-by-vector-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svdot[_single]_za32[_u16]_vg1x4

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdot%5B_single%5D_za32%5B_u16%5D_vg1x4

### Signature (source notation)

```c
void svdot[_single]_za32[_u16]_vg1x4(uint32_t slice, svuint16x4_t zn, svuint16_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector unsigned integer dot-product by vector

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Dot product

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2
```

### Return type metadata

```json
{
  "return_base_type": "void",
  "element_bit_size": "16",
  "value": "void"
}
```

### Argument preparation and constraints

```json
{
  "slice": {
    "register+immediate": "Wreg1 + imm1"
  },
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
[]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
UDOT ZA.S[Wreg1, imm1, VGX4], { Zreg1.H - Zreg2.H }, Zreg3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/UDOT--2-way--multiple-and-single-vector---Multi-vector-unsigned-integer-dot-product-by-vector-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svdot[_single]_za32[_u8]_vg1x2

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdot%5B_single%5D_za32%5B_u8%5D_vg1x2

### Signature (source notation)

```c
void svdot[_single]_za32[_u8]_vg1x2(uint32_t slice, svuint8x2_t zn, svuint8_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector unsigned integer dot-product by vector

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Dot product

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2
```

### Return type metadata

```json
{
  "return_base_type": "void",
  "element_bit_size": "8",
  "value": "void"
}
```

### Argument preparation and constraints

```json
{
  "slice": {
    "register+immediate": "Wreg1 + imm1"
  },
  "zn": {
    "Z multi-vector": "{ Zreg1.B, Zreg2.B }"
  },
  "zm": {
    "register": "Zreg3.B"
  }
}
```

### Result mapping

```json
[]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
UDOT ZA.S[Wreg1, imm1, VGX2], { Zreg1.B, Zreg2.B }, Zreg3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/UDOT--4-way--multiple-and-single-vector---Multi-vector-unsigned-integer-dot-product-by-vector-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svdot[_single]_za32[_u8]_vg1x4

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdot%5B_single%5D_za32%5B_u8%5D_vg1x4

### Signature (source notation)

```c
void svdot[_single]_za32[_u8]_vg1x4(uint32_t slice, svuint8x4_t zn, svuint8_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector unsigned integer dot-product by vector

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Dot product

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2
```

### Return type metadata

```json
{
  "return_base_type": "void",
  "element_bit_size": "8",
  "value": "void"
}
```

### Argument preparation and constraints

```json
{
  "slice": {
    "register+immediate": "Wreg1 + imm1"
  },
  "zn": {
    "Z multi-vector": "{ Zreg1.B - Zreg2.B }"
  },
  "zm": {
    "register": "Zreg3.B"
  }
}
```

### Result mapping

```json
[]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
UDOT ZA.S[Wreg1, imm1, VGX4], { Zreg1.B - Zreg2.B }, Zreg3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/UDOT--4-way--multiple-and-single-vector---Multi-vector-unsigned-integer-dot-product-by-vector-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svdot[_single]_za64[_s16]_vg1x2

ISA classification: SME2 + FEAT_SME_I16I64

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdot%5B_single%5D_za64%5B_s16%5D_vg1x2

### Signature (source notation)

```c
void svdot[_single]_za64[_s16]_vg1x2(uint32_t slice, svint16x2_t zn, svint16_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector signed integer dot-product by vector

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Dot product

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2,FEAT_SME_I16I64
```

### Return type metadata

```json
{
  "return_base_type": "void",
  "element_bit_size": "16",
  "value": "void"
}
```

### Argument preparation and constraints

```json
{
  "slice": {
    "register+immediate": "Wreg1 + imm1"
  },
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
[]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
SDOT ZA.D[Wreg1, imm1, VGX2], { Zreg1.H, Zreg2.H }, Zreg3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SDOT--4-way--multiple-and-single-vector---Multi-vector-signed-integer-dot-product-by-vector-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svdot[_single]_za64[_s16]_vg1x4

ISA classification: SME2 + FEAT_SME_I16I64

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdot%5B_single%5D_za64%5B_s16%5D_vg1x4

### Signature (source notation)

```c
void svdot[_single]_za64[_s16]_vg1x4(uint32_t slice, svint16x4_t zn, svint16_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector signed integer dot-product by vector

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Dot product

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2,FEAT_SME_I16I64
```

### Return type metadata

```json
{
  "return_base_type": "void",
  "element_bit_size": "16",
  "value": "void"
}
```

### Argument preparation and constraints

```json
{
  "slice": {
    "register+immediate": "Wreg1 + imm1"
  },
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
[]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
SDOT ZA.D[Wreg1, imm1, VGX4], { Zreg1.H - Zreg2.H }, Zreg3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SDOT--4-way--multiple-and-single-vector---Multi-vector-signed-integer-dot-product-by-vector-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svdot[_single]_za64[_u16]_vg1x2

ISA classification: SME2 + FEAT_SME_I16I64

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdot%5B_single%5D_za64%5B_u16%5D_vg1x2

### Signature (source notation)

```c
void svdot[_single]_za64[_u16]_vg1x2(uint32_t slice, svuint16x2_t zn, svuint16_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector unsigned integer dot-product by vector

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Dot product

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2,FEAT_SME_I16I64
```

### Return type metadata

```json
{
  "return_base_type": "void",
  "element_bit_size": "16",
  "value": "void"
}
```

### Argument preparation and constraints

```json
{
  "slice": {
    "register+immediate": "Wreg1 + imm1"
  },
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
[]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
UDOT ZA.D[Wreg1, imm1, VGX2], { Zreg1.H, Zreg2.H }, Zreg3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/UDOT--4-way--multiple-and-single-vector---Multi-vector-unsigned-integer-dot-product-by-vector-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svdot[_single]_za64[_u16]_vg1x4

ISA classification: SME2 + FEAT_SME_I16I64

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdot%5B_single%5D_za64%5B_u16%5D_vg1x4

### Signature (source notation)

```c
void svdot[_single]_za64[_u16]_vg1x4(uint32_t slice, svuint16x4_t zn, svuint16_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector unsigned integer dot-product by vector

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Dot product

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2,FEAT_SME_I16I64
```

### Return type metadata

```json
{
  "return_base_type": "void",
  "element_bit_size": "16",
  "value": "void"
}
```

### Argument preparation and constraints

```json
{
  "slice": {
    "register+immediate": "Wreg1 + imm1"
  },
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
[]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
UDOT ZA.D[Wreg1, imm1, VGX4], { Zreg1.H - Zreg2.H }, Zreg3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/UDOT--4-way--multiple-and-single-vector---Multi-vector-unsigned-integer-dot-product-by-vector-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svdot_lane_za16[_mf8]_vg1x2_fpm

ISA classification: SME2 + FEAT_SME_F8F16

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdot_lane_za16%5B_mf8%5D_vg1x2_fpm

### Signature (source notation)

```c
void svdot_lane_za16[_mf8]_vg1x2_fpm(uint32_t slice, svmfloat8x2_t zn, svmfloat8_t zm, uint64_t imm_idx, fpm_t fpm)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector 8-bit floating-point dot product by indexed element to half-precision

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Dot product

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME_F8F16
```

### Return type metadata

```json
{
  "return_base_type": "void",
  "element_bit_size": "8",
  "value": "void"
}
```

### Argument preparation and constraints

```json
{
  "slice": {
    "register+immediate": "Wreg2 + imm2"
  },
  "zn": {
    "Z multi-vector": "{ Zreg1.B, Zreg2.B }"
  },
  "zm": {
    "register": "Zreg3.B"
  },
  "imm_idx": {
    "immediate": "imm1"
  },
  "fpm": {
    "register": "Xreg1"
  }
}
```

### Result mapping

```json
[]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
MSR FPMR, Xreg1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/Base-Instructions/MSR--register---Move-general-purpose-register-to-System-register-

```asm
FDOT ZA.H[Wreg2, imm2, VGX2], { Zreg1.B, Zreg2.B }, Zreg3.B[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/FDOT--2-way--multiple-and-indexed-vector--FP8-to-FP16---Multi-vector-8-bit-floating-point-dot-product-by-indexed-element-to-half-precision-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svdot_lane_za16[_mf8]_vg1x4_fpm

ISA classification: SME2 + FEAT_SME_F8F16

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdot_lane_za16%5B_mf8%5D_vg1x4_fpm

### Signature (source notation)

```c
void svdot_lane_za16[_mf8]_vg1x4_fpm(uint32_t slice, svmfloat8x4_t zn, svmfloat8_t zm, uint64_t imm_idx, fpm_t fpm)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector 8-bit floating-point dot product by indexed element to half-precision

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Dot product

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME_F8F16
```

### Return type metadata

```json
{
  "return_base_type": "void",
  "element_bit_size": "8",
  "value": "void"
}
```

### Argument preparation and constraints

```json
{
  "slice": {
    "register+immediate": "Wreg2 + imm2"
  },
  "zn": {
    "Z multi-vector": "{ Zreg1.B - Zreg2.B }"
  },
  "zm": {
    "register": "Zreg3.B"
  },
  "imm_idx": {
    "immediate": "imm1"
  },
  "fpm": {
    "register": "Xreg1"
  }
}
```

### Result mapping

```json
[]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
MSR FPMR, Xreg1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/Base-Instructions/MSR--register---Move-general-purpose-register-to-System-register-

```asm
FDOT ZA.H[Wreg2, imm2, VGX4], { Zreg1.B - Zreg2.B }, Zreg3.B[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/FDOT--2-way--multiple-and-indexed-vector--FP8-to-FP16---Multi-vector-8-bit-floating-point-dot-product-by-indexed-element-to-half-precision-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svdot_lane_za32[_bf16]_vg1x2

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdot_lane_za32%5B_bf16%5D_vg1x2

### Signature (source notation)

```c
void svdot_lane_za32[_bf16]_vg1x2(uint32_t slice, svbfloat16x2_t zn, svbfloat16_t zm, uint64_t imm_idx)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector BFloat16 dot-product by indexed element

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Dot product

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2
```

### Return type metadata

```json
{
  "return_base_type": "void",
  "element_bit_size": "16",
  "value": "void"
}
```

### Argument preparation and constraints

```json
{
  "slice": {
    "register+immediate": "Wreg1 + imm2"
  },
  "zn": {
    "Z multi-vector": "{ Zreg1.H, Zreg2.H }"
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
[]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
BFDOT ZA.S[Wreg1, imm2, VGX2], { Zreg1.H, Zreg2.H }, Zreg3.H[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/BFDOT--multiple-and-indexed-vector---Multi-vector-BFloat16-dot-product-by-indexed-element-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svdot_lane_za32[_bf16]_vg1x4

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdot_lane_za32%5B_bf16%5D_vg1x4

### Signature (source notation)

```c
void svdot_lane_za32[_bf16]_vg1x4(uint32_t slice, svbfloat16x4_t zn, svbfloat16_t zm, uint64_t imm_idx)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector BFloat16 dot-product by indexed element

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Dot product

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2
```

### Return type metadata

```json
{
  "return_base_type": "void",
  "element_bit_size": "16",
  "value": "void"
}
```

### Argument preparation and constraints

```json
{
  "slice": {
    "register+immediate": "Wreg1 + imm2"
  },
  "zn": {
    "Z multi-vector": "{ Zreg1.H - Zreg2.H }"
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
[]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
BFDOT ZA.S[Wreg1, imm2, VGX4], { Zreg1.H - Zreg2.H }, Zreg3.H[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/BFDOT--multiple-and-indexed-vector---Multi-vector-BFloat16-dot-product-by-indexed-element-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svdot_lane_za32[_f16]_vg1x2

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdot_lane_za32%5B_f16%5D_vg1x2

### Signature (source notation)

```c
void svdot_lane_za32[_f16]_vg1x2(uint32_t slice, svfloat16x2_t zn, svfloat16_t zm, uint64_t imm_idx)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector half-precision dot-product by indexed element

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Dot product

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2
```

### Return type metadata

```json
{
  "return_base_type": "void",
  "element_bit_size": "16",
  "value": "void"
}
```

### Argument preparation and constraints

```json
{
  "slice": {
    "register+immediate": "Wreg1 + imm2"
  },
  "zn": {
    "Z multi-vector": "{ Zreg1.H, Zreg2.H }"
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
[]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
FDOT ZA.S[Wreg1, imm2, VGX2], { Zreg1.H, Zreg2.H }, Zreg3.H[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/FDOT--2-way--multiple-and-indexed-vector--FP16-to-FP32---Multi-vector-half-precision-dot-product-by-indexed-element-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svdot_lane_za32[_f16]_vg1x4

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdot_lane_za32%5B_f16%5D_vg1x4

### Signature (source notation)

```c
void svdot_lane_za32[_f16]_vg1x4(uint32_t slice, svfloat16x4_t zn, svfloat16_t zm, uint64_t imm_idx)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector half-precision dot-product by indexed element

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Dot product

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2
```

### Return type metadata

```json
{
  "return_base_type": "void",
  "element_bit_size": "16",
  "value": "void"
}
```

### Argument preparation and constraints

```json
{
  "slice": {
    "register+immediate": "Wreg1 + imm2"
  },
  "zn": {
    "Z multi-vector": "{ Zreg1.H - Zreg2.H }"
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
[]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
FDOT ZA.S[Wreg1, imm2, VGX4], { Zreg1.H - Zreg2.H }, Zreg3.H[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/FDOT--2-way--multiple-and-indexed-vector--FP16-to-FP32---Multi-vector-half-precision-dot-product-by-indexed-element-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svdot_lane_za32[_mf8]_vg1x2_fpm

ISA classification: SME2 + FEAT_SME_F8F32

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdot_lane_za32%5B_mf8%5D_vg1x2_fpm

### Signature (source notation)

```c
void svdot_lane_za32[_mf8]_vg1x2_fpm(uint32_t slice, svmfloat8x2_t zn, svmfloat8_t zm, uint64_t imm_idx, fpm_t fpm)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector 8-bit floating-point dot product by indexed element to single-precision

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Dot product

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME_F8F32
```

### Return type metadata

```json
{
  "return_base_type": "void",
  "element_bit_size": "8",
  "value": "void"
}
```

### Argument preparation and constraints

```json
{
  "slice": {
    "register+immediate": "Wreg2 + imm2"
  },
  "zn": {
    "Z multi-vector": "{ Zreg1.B, Zreg2.B }"
  },
  "zm": {
    "register": "Zreg3.B"
  },
  "imm_idx": {
    "immediate": "imm1"
  },
  "fpm": {
    "register": "Xreg1"
  }
}
```

### Result mapping

```json
[]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
MSR FPMR, Xreg1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/Base-Instructions/MSR--register---Move-general-purpose-register-to-System-register-

```asm
FDOT ZA.S[Wreg2, imm2, VGX2], { Zreg1.B, Zreg2.B }, Zreg3.B[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/FDOT--4-way--multiple-and-indexed-vector---Multi-vector-8-bit-floating-point-dot-product-by-indexed-element-to-single-precision-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svdot_lane_za32[_mf8]_vg1x4_fpm

ISA classification: SME2 + FEAT_SME_F8F32

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdot_lane_za32%5B_mf8%5D_vg1x4_fpm

### Signature (source notation)

```c
void svdot_lane_za32[_mf8]_vg1x4_fpm(uint32_t slice, svmfloat8x4_t zn, svmfloat8_t zm, uint64_t imm_idx, fpm_t fpm)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector 8-bit floating-point dot product by indexed element to single-precision

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Dot product

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME_F8F32
```

### Return type metadata

```json
{
  "return_base_type": "void",
  "element_bit_size": "8",
  "value": "void"
}
```

### Argument preparation and constraints

```json
{
  "slice": {
    "register+immediate": "Wreg2 + imm2"
  },
  "zn": {
    "Z multi-vector": "{ Zreg1.B - Zreg2.B }"
  },
  "zm": {
    "register": "Zreg3.B"
  },
  "imm_idx": {
    "immediate": "imm1"
  },
  "fpm": {
    "register": "Xreg1"
  }
}
```

### Result mapping

```json
[]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
MSR FPMR, Xreg1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/Base-Instructions/MSR--register---Move-general-purpose-register-to-System-register-

```asm
FDOT ZA.S[Wreg2, imm2, VGX4], { Zreg1.B - Zreg2.B }, Zreg3.B[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/FDOT--4-way--multiple-and-indexed-vector---Multi-vector-8-bit-floating-point-dot-product-by-indexed-element-to-single-precision-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svdot_lane_za32[_s16]_vg1x2

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdot_lane_za32%5B_s16%5D_vg1x2

### Signature (source notation)

```c
void svdot_lane_za32[_s16]_vg1x2(uint32_t slice, svint16x2_t zn, svint16_t zm, uint64_t imm_idx)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector signed integer dot-product by indexed element

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Dot product

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2
```

### Return type metadata

```json
{
  "return_base_type": "void",
  "element_bit_size": "16",
  "value": "void"
}
```

### Argument preparation and constraints

```json
{
  "slice": {
    "register+immediate": "Wreg1 + imm2"
  },
  "zn": {
    "Z multi-vector": "{ Zreg1.H, Zreg2.H }"
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
[]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
SDOT ZA.S[Wreg1, imm2, VGX2], { Zreg1.H, Zreg2.H }, Zreg3.H[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SDOT--2-way--multiple-and-indexed-vector---Multi-vector-signed-integer-dot-product-by-indexed-element-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svdot_lane_za32[_s16]_vg1x4

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdot_lane_za32%5B_s16%5D_vg1x4

### Signature (source notation)

```c
void svdot_lane_za32[_s16]_vg1x4(uint32_t slice, svint16x4_t zn, svint16_t zm, uint64_t imm_idx)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector signed integer dot-product by indexed element

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Dot product

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2
```

### Return type metadata

```json
{
  "return_base_type": "void",
  "element_bit_size": "16",
  "value": "void"
}
```

### Argument preparation and constraints

```json
{
  "slice": {
    "register+immediate": "Wreg1 + imm2"
  },
  "zn": {
    "Z multi-vector": "{ Zreg1.H - Zreg2.H }"
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
[]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
SDOT ZA.S[Wreg1, imm2, VGX4], { Zreg1.H - Zreg2.H }, Zreg3.H[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SDOT--2-way--multiple-and-indexed-vector---Multi-vector-signed-integer-dot-product-by-indexed-element-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svdot_lane_za32[_s8]_vg1x2

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdot_lane_za32%5B_s8%5D_vg1x2

### Signature (source notation)

```c
void svdot_lane_za32[_s8]_vg1x2(uint32_t slice, svint8x2_t zn, svint8_t zm, uint64_t imm_idx)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector signed integer dot-product by indexed element

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Dot product

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2
```

### Return type metadata

```json
{
  "return_base_type": "void",
  "element_bit_size": "8",
  "value": "void"
}
```

### Argument preparation and constraints

```json
{
  "slice": {
    "register+immediate": "Wreg1 + imm2"
  },
  "zn": {
    "Z multi-vector": "{ Zreg1.B, Zreg2.B }"
  },
  "zm": {
    "register": "Zreg3.B"
  },
  "imm_idx": {
    "immediate": "imm1"
  }
}
```

### Result mapping

```json
[]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
SDOT ZA.S[Wreg1, imm2, VGX2], { Zreg1.B, Zreg2.B }, Zreg3.B[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SDOT--4-way--multiple-and-indexed-vector---Multi-vector-signed-integer-dot-product-by-indexed-element-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svdot_lane_za32[_s8]_vg1x4

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdot_lane_za32%5B_s8%5D_vg1x4

### Signature (source notation)

```c
void svdot_lane_za32[_s8]_vg1x4(uint32_t slice, svint8x4_t zn, svint8_t zm, uint64_t imm_idx)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector signed integer dot-product by indexed element

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Dot product

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2
```

### Return type metadata

```json
{
  "return_base_type": "void",
  "element_bit_size": "8",
  "value": "void"
}
```

### Argument preparation and constraints

```json
{
  "slice": {
    "register+immediate": "Wreg1 + imm2"
  },
  "zn": {
    "Z multi-vector": "{ Zreg1.B - Zreg2.B }"
  },
  "zm": {
    "register": "Zreg3.B"
  },
  "imm_idx": {
    "immediate": "imm1"
  }
}
```

### Result mapping

```json
[]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
SDOT ZA.S[Wreg1, imm2, VGX4], { Zreg1.B - Zreg2.B }, Zreg3.B[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SDOT--4-way--multiple-and-indexed-vector---Multi-vector-signed-integer-dot-product-by-indexed-element-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svdot_lane_za32[_u16]_vg1x2

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdot_lane_za32%5B_u16%5D_vg1x2

### Signature (source notation)

```c
void svdot_lane_za32[_u16]_vg1x2(uint32_t slice, svuint16x2_t zn, svuint16_t zm, uint64_t imm_idx)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector unsigned integer dot-product by indexed element

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Dot product

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2
```

### Return type metadata

```json
{
  "return_base_type": "void",
  "element_bit_size": "16",
  "value": "void"
}
```

### Argument preparation and constraints

```json
{
  "slice": {
    "register+immediate": "Wreg1 + imm2"
  },
  "zn": {
    "Z multi-vector": "{ Zreg1.H, Zreg2.H }"
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
[]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
UDOT ZA.S[Wreg1, imm2, VGX2], { Zreg1.H, Zreg2.H }, Zreg3.H[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/UDOT--2-way--multiple-and-indexed-vector---Multi-vector-unsigned-integer-dot-product-by-indexed-element-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svdot_lane_za32[_u16]_vg1x4

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdot_lane_za32%5B_u16%5D_vg1x4

### Signature (source notation)

```c
void svdot_lane_za32[_u16]_vg1x4(uint32_t slice, svuint16x4_t zn, svuint16_t zm, uint64_t imm_idx)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector unsigned integer dot-product by indexed element

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Dot product

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2
```

### Return type metadata

```json
{
  "return_base_type": "void",
  "element_bit_size": "16",
  "value": "void"
}
```

### Argument preparation and constraints

```json
{
  "slice": {
    "register+immediate": "Wreg1 + imm2"
  },
  "zn": {
    "Z multi-vector": "{ Zreg1.H - Zreg2.H }"
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
[]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
UDOT ZA.S[Wreg1, imm2, VGX4], { Zreg1.H - Zreg2.H }, Zreg3.H[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/UDOT--2-way--multiple-and-indexed-vector---Multi-vector-unsigned-integer-dot-product-by-indexed-element-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svdot_lane_za32[_u8]_vg1x2

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdot_lane_za32%5B_u8%5D_vg1x2

### Signature (source notation)

```c
void svdot_lane_za32[_u8]_vg1x2(uint32_t slice, svuint8x2_t zn, svuint8_t zm, uint64_t imm_idx)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector unsigned integer dot-product by indexed element

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Dot product

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2
```

### Return type metadata

```json
{
  "return_base_type": "void",
  "element_bit_size": "8",
  "value": "void"
}
```

### Argument preparation and constraints

```json
{
  "slice": {
    "register+immediate": "Wreg1 + imm2"
  },
  "zn": {
    "Z multi-vector": "{ Zreg1.B, Zreg2.B }"
  },
  "zm": {
    "register": "Zreg3.B"
  },
  "imm_idx": {
    "immediate": "imm1"
  }
}
```

### Result mapping

```json
[]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
UDOT ZA.S[Wreg1, imm2, VGX2], { Zreg1.B, Zreg2.B }, Zreg3.B[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/UDOT--4-way--multiple-and-indexed-vector---Multi-vector-unsigned-integer-dot-product-by-indexed-element-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svdot_lane_za32[_u8]_vg1x4

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdot_lane_za32%5B_u8%5D_vg1x4

### Signature (source notation)

```c
void svdot_lane_za32[_u8]_vg1x4(uint32_t slice, svuint8x4_t zn, svuint8_t zm, uint64_t imm_idx)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector unsigned integer dot-product by indexed element

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Dot product

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2
```

### Return type metadata

```json
{
  "return_base_type": "void",
  "element_bit_size": "8",
  "value": "void"
}
```

### Argument preparation and constraints

```json
{
  "slice": {
    "register+immediate": "Wreg1 + imm2"
  },
  "zn": {
    "Z multi-vector": "{ Zreg1.B - Zreg2.B }"
  },
  "zm": {
    "register": "Zreg3.B"
  },
  "imm_idx": {
    "immediate": "imm1"
  }
}
```

### Result mapping

```json
[]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
UDOT ZA.S[Wreg1, imm2, VGX4], { Zreg1.B - Zreg2.B }, Zreg3.B[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/UDOT--4-way--multiple-and-indexed-vector---Multi-vector-unsigned-integer-dot-product-by-indexed-element-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svdot_lane_za64[_s16]_vg1x2

ISA classification: SME2 + FEAT_SME_I16I64

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdot_lane_za64%5B_s16%5D_vg1x2

### Signature (source notation)

```c
void svdot_lane_za64[_s16]_vg1x2(uint32_t slice, svint16x2_t zn, svint16_t zm, uint64_t imm_idx)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector signed integer dot-product by indexed element

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Dot product

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2,FEAT_SME_I16I64
```

### Return type metadata

```json
{
  "return_base_type": "void",
  "element_bit_size": "16",
  "value": "void"
}
```

### Argument preparation and constraints

```json
{
  "slice": {
    "register+immediate": "Wreg1 + imm2"
  },
  "zn": {
    "Z multi-vector": "{ Zreg1.H, Zreg2.H }"
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
[]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
SDOT ZA.D[Wreg1, imm2, VGX2], { Zreg1.H, Zreg2.H }, Zreg3.H[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SDOT--4-way--multiple-and-indexed-vector---Multi-vector-signed-integer-dot-product-by-indexed-element-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svdot_lane_za64[_s16]_vg1x4

ISA classification: SME2 + FEAT_SME_I16I64

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdot_lane_za64%5B_s16%5D_vg1x4

### Signature (source notation)

```c
void svdot_lane_za64[_s16]_vg1x4(uint32_t slice, svint16x4_t zn, svint16_t zm, uint64_t imm_idx)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector signed integer dot-product by indexed element

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Dot product

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2,FEAT_SME_I16I64
```

### Return type metadata

```json
{
  "return_base_type": "void",
  "element_bit_size": "16",
  "value": "void"
}
```

### Argument preparation and constraints

```json
{
  "slice": {
    "register+immediate": "Wreg1 + imm2"
  },
  "zn": {
    "Z multi-vector": "{ Zreg1.H - Zreg2.H }"
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
[]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
SDOT ZA.D[Wreg1, imm2, VGX4], { Zreg1.H - Zreg2.H }, Zreg3.H[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SDOT--4-way--multiple-and-indexed-vector---Multi-vector-signed-integer-dot-product-by-indexed-element-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svdot_lane_za64[_u16]_vg1x2

ISA classification: SME2 + FEAT_SME_I16I64

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdot_lane_za64%5B_u16%5D_vg1x2

### Signature (source notation)

```c
void svdot_lane_za64[_u16]_vg1x2(uint32_t slice, svuint16x2_t zn, svuint16_t zm, uint64_t imm_idx)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector unsigned integer dot-product by indexed element

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Dot product

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2,FEAT_SME_I16I64
```

### Return type metadata

```json
{
  "return_base_type": "void",
  "element_bit_size": "16",
  "value": "void"
}
```

### Argument preparation and constraints

```json
{
  "slice": {
    "register+immediate": "Wreg1 + imm2"
  },
  "zn": {
    "Z multi-vector": "{ Zreg1.H, Zreg2.H }"
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
[]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
UDOT ZA.D[Wreg1, imm2, VGX2], { Zreg1.H, Zreg2.H }, Zreg3.H[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/UDOT--4-way--multiple-and-indexed-vector---Multi-vector-unsigned-integer-dot-product-by-indexed-element-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svdot_lane_za64[_u16]_vg1x4

ISA classification: SME2 + FEAT_SME_I16I64

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdot_lane_za64%5B_u16%5D_vg1x4

### Signature (source notation)

```c
void svdot_lane_za64[_u16]_vg1x4(uint32_t slice, svuint16x4_t zn, svuint16_t zm, uint64_t imm_idx)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector unsigned integer dot-product by indexed element

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Dot product

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2,FEAT_SME_I16I64
```

### Return type metadata

```json
{
  "return_base_type": "void",
  "element_bit_size": "16",
  "value": "void"
}
```

### Argument preparation and constraints

```json
{
  "slice": {
    "register+immediate": "Wreg1 + imm2"
  },
  "zn": {
    "Z multi-vector": "{ Zreg1.H - Zreg2.H }"
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
[]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
UDOT ZA.D[Wreg1, imm2, VGX4], { Zreg1.H - Zreg2.H }, Zreg3.H[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/UDOT--4-way--multiple-and-indexed-vector---Multi-vector-unsigned-integer-dot-product-by-indexed-element-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svdot_za16[_mf8]_vg1x2_fpm

ISA classification: SME2 + FEAT_SME_F8F16

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdot_za16%5B_mf8%5D_vg1x2_fpm

### Signature (source notation)

```c
void svdot_za16[_mf8]_vg1x2_fpm(uint32_t slice, svmfloat8x2_t zn, svmfloat8x2_t zm, fpm_t fpm)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector 8-bit floating-point dot product to half-precision

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Dot product

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME_F8F16
```

### Return type metadata

```json
{
  "return_base_type": "void",
  "element_bit_size": "8",
  "value": "void"
}
```

### Argument preparation and constraints

```json
{
  "slice": {
    "register+immediate": "Wreg2 + imm1"
  },
  "zn": {
    "Z multi-vector": "{ Zreg1.B, Zreg2.B }"
  },
  "zm": {
    "Z multi-vector": "{ Zreg3.B, Zreg4.B }"
  },
  "fpm": {
    "register": "Xreg1"
  }
}
```

### Result mapping

```json
[]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
MSR FPMR, Xreg1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/Base-Instructions/MSR--register---Move-general-purpose-register-to-System-register-

```asm
FDOT ZA.H[Wreg2, imm1, VGX2], { Zreg1.B, Zreg2.B }, { Zreg3.B, Zreg4.B }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/FDOT--2-way--multiple-vectors--FP8-to-FP16---Multi-vector-8-bit-floating-point-dot-product-to-half-precision-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svdot_za16[_mf8]_vg1x4_fpm

ISA classification: SME2 + FEAT_SME_F8F16

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdot_za16%5B_mf8%5D_vg1x4_fpm

### Signature (source notation)

```c
void svdot_za16[_mf8]_vg1x4_fpm(uint32_t slice, svmfloat8x4_t zn, svmfloat8x4_t zm, fpm_t fpm)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector 8-bit floating-point dot product to half-precision

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Dot product

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME_F8F16
```

### Return type metadata

```json
{
  "return_base_type": "void",
  "element_bit_size": "8",
  "value": "void"
}
```

### Argument preparation and constraints

```json
{
  "slice": {
    "register+immediate": "Wreg2 + imm1"
  },
  "zn": {
    "Z multi-vector": "{ Zreg1.B - Zreg2.B }"
  },
  "zm": {
    "Z multi-vector": "{ Zreg3.B - Zreg4.B }"
  },
  "fpm": {
    "register": "Xreg1"
  }
}
```

### Result mapping

```json
[]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
MSR FPMR, Xreg1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/Base-Instructions/MSR--register---Move-general-purpose-register-to-System-register-

```asm
FDOT ZA.H[Wreg2, imm1, VGX4], { Zreg1.B - Zreg2.B }, { Zreg3.B - Zreg4.B }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/FDOT--2-way--multiple-vectors--FP8-to-FP16---Multi-vector-8-bit-floating-point-dot-product-to-half-precision-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svdot_za32[_bf16]_vg1x2

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdot_za32%5B_bf16%5D_vg1x2

### Signature (source notation)

```c
void svdot_za32[_bf16]_vg1x2(uint32_t slice, svbfloat16x2_t zn, svbfloat16x2_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector BFloat16 dot-product

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Dot product

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2
```

### Return type metadata

```json
{
  "return_base_type": "void",
  "element_bit_size": "16",
  "value": "void"
}
```

### Argument preparation and constraints

```json
{
  "slice": {
    "register+immediate": "Wreg1 + imm1"
  },
  "zn": {
    "Z multi-vector": "{ Zreg1.H, Zreg2.H }"
  },
  "zm": {
    "Z multi-vector": "{ Zreg3.H, Zreg4.H }"
  }
}
```

### Result mapping

```json
[]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
BFDOT ZA.S[Wreg1, imm1, VGX2], { Zreg1.H, Zreg2.H }, { Zreg3.H, Zreg4.H }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/BFDOT--multiple-vectors---Multi-vector-BFloat16-dot-product-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svdot_za32[_bf16]_vg1x4

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdot_za32%5B_bf16%5D_vg1x4

### Signature (source notation)

```c
void svdot_za32[_bf16]_vg1x4(uint32_t slice, svbfloat16x4_t zn, svbfloat16x4_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector BFloat16 dot-product

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Dot product

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2
```

### Return type metadata

```json
{
  "return_base_type": "void",
  "element_bit_size": "16",
  "value": "void"
}
```

### Argument preparation and constraints

```json
{
  "slice": {
    "register+immediate": "Wreg1 + imm1"
  },
  "zn": {
    "Z multi-vector": "{ Zreg1.H - Zreg2.H }"
  },
  "zm": {
    "Z multi-vector": "{ Zreg3.H - Zreg4.H }"
  }
}
```

### Result mapping

```json
[]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
BFDOT ZA.S[Wreg1, imm1, VGX4], { Zreg1.H - Zreg2.H }, { Zreg3.H - Zreg4.H }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/BFDOT--multiple-vectors---Multi-vector-BFloat16-dot-product-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svdot_za32[_f16]_vg1x2

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdot_za32%5B_f16%5D_vg1x2

### Signature (source notation)

```c
void svdot_za32[_f16]_vg1x2(uint32_t slice, svfloat16x2_t zn, svfloat16x2_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector half-precision dot-product

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Dot product

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2
```

### Return type metadata

```json
{
  "return_base_type": "void",
  "element_bit_size": "16",
  "value": "void"
}
```

### Argument preparation and constraints

```json
{
  "slice": {
    "register+immediate": "Wreg1 + imm1"
  },
  "zn": {
    "Z multi-vector": "{ Zreg1.H, Zreg2.H }"
  },
  "zm": {
    "Z multi-vector": "{ Zreg3.H, Zreg4.H }"
  }
}
```

### Result mapping

```json
[]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
FDOT ZA.S[Wreg1, imm1, VGX2], { Zreg1.H, Zreg2.H }, { Zreg3.H, Zreg4.H }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/FDOT--2-way--multiple-vectors--FP16-to-FP32---Multi-vector-half-precision-dot-product-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svdot_za32[_f16]_vg1x4

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdot_za32%5B_f16%5D_vg1x4

### Signature (source notation)

```c
void svdot_za32[_f16]_vg1x4(uint32_t slice, svfloat16x4_t zn, svfloat16x4_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector half-precision dot-product

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Dot product

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2
```

### Return type metadata

```json
{
  "return_base_type": "void",
  "element_bit_size": "16",
  "value": "void"
}
```

### Argument preparation and constraints

```json
{
  "slice": {
    "register+immediate": "Wreg1 + imm1"
  },
  "zn": {
    "Z multi-vector": "{ Zreg1.H - Zreg2.H }"
  },
  "zm": {
    "Z multi-vector": "{ Zreg3.H - Zreg4.H }"
  }
}
```

### Result mapping

```json
[]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
FDOT ZA.S[Wreg1, imm1, VGX4], { Zreg1.H - Zreg2.H }, { Zreg3.H - Zreg4.H }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/FDOT--2-way--multiple-vectors--FP16-to-FP32---Multi-vector-half-precision-dot-product-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svdot_za32[_mf8]_vg1x2_fpm

ISA classification: SME2 + FEAT_SME_F8F32

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdot_za32%5B_mf8%5D_vg1x2_fpm

### Signature (source notation)

```c
void svdot_za32[_mf8]_vg1x2_fpm(uint32_t slice, svmfloat8x2_t zn, svmfloat8x2_t zm, fpm_t fpm)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector 8-bit floating-point dot product to single-precision

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Dot product

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME_F8F32
```

### Return type metadata

```json
{
  "return_base_type": "void",
  "element_bit_size": "8",
  "value": "void"
}
```

### Argument preparation and constraints

```json
{
  "slice": {
    "register+immediate": "Wreg2 + imm1"
  },
  "zn": {
    "Z multi-vector": "{ Zreg1.B, Zreg2.B }"
  },
  "zm": {
    "Z multi-vector": "{ Zreg3.B, Zreg4.B }"
  },
  "fpm": {
    "register": "Xreg1"
  }
}
```

### Result mapping

```json
[]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
MSR FPMR, Xreg1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/Base-Instructions/MSR--register---Move-general-purpose-register-to-System-register-

```asm
FDOT ZA.S[Wreg2, imm1, VGX2], { Zreg1.B, Zreg2.B }, { Zreg3.B, Zreg4.B }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/FDOT--4-way--multiple-vectors---Multi-vector-8-bit-floating-point-dot-product-to-single-precision-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svdot_za32[_mf8]_vg1x4_fpm

ISA classification: SME2 + FEAT_SME_F8F32

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdot_za32%5B_mf8%5D_vg1x4_fpm

### Signature (source notation)

```c
void svdot_za32[_mf8]_vg1x4_fpm(uint32_t slice, svmfloat8x4_t zn, svmfloat8x4_t zm, fpm_t fpm)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector 8-bit floating-point dot product to single-precision

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Dot product

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME_F8F32
```

### Return type metadata

```json
{
  "return_base_type": "void",
  "element_bit_size": "8",
  "value": "void"
}
```

### Argument preparation and constraints

```json
{
  "slice": {
    "register+immediate": "Wreg2 + imm1"
  },
  "zn": {
    "Z multi-vector": "{ Zreg1.B - Zreg2.B }"
  },
  "zm": {
    "Z multi-vector": "{ Zreg3.B - Zreg4.B }"
  },
  "fpm": {
    "register": "Xreg1"
  }
}
```

### Result mapping

```json
[]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
MSR FPMR, Xreg1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/Base-Instructions/MSR--register---Move-general-purpose-register-to-System-register-

```asm
FDOT ZA.S[Wreg2, imm1, VGX4], { Zreg1.B - Zreg2.B }, { Zreg3.B - Zreg4.B }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/FDOT--4-way--multiple-vectors---Multi-vector-8-bit-floating-point-dot-product-to-single-precision-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svdot_za32[_s16]_vg1x2

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdot_za32%5B_s16%5D_vg1x2

### Signature (source notation)

```c
void svdot_za32[_s16]_vg1x2(uint32_t slice, svint16x2_t zn, svint16x2_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector signed integer dot-product

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Dot product

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2
```

### Return type metadata

```json
{
  "return_base_type": "void",
  "element_bit_size": "16",
  "value": "void"
}
```

### Argument preparation and constraints

```json
{
  "slice": {
    "register+immediate": "Wreg1 + imm1"
  },
  "zn": {
    "Z multi-vector": "{ Zreg1.H, Zreg2.H }"
  },
  "zm": {
    "Z multi-vector": "{ Zreg3.H, Zreg4.H }"
  }
}
```

### Result mapping

```json
[]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
SDOT ZA.S[Wreg1, imm1, VGX2], { Zreg1.H, Zreg2.H }, { Zreg3.H, Zreg4.H }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SDOT--2-way--multiple-vectors---Multi-vector-signed-integer-dot-product-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svdot_za32[_s16]_vg1x4

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdot_za32%5B_s16%5D_vg1x4

### Signature (source notation)

```c
void svdot_za32[_s16]_vg1x4(uint32_t slice, svint16x4_t zn, svint16x4_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector signed integer dot-product

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Dot product

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2
```

### Return type metadata

```json
{
  "return_base_type": "void",
  "element_bit_size": "16",
  "value": "void"
}
```

### Argument preparation and constraints

```json
{
  "slice": {
    "register+immediate": "Wreg1 + imm1"
  },
  "zn": {
    "Z multi-vector": "{ Zreg1.H - Zreg2.H }"
  },
  "zm": {
    "Z multi-vector": "{ Zreg3.H - Zreg4.H }"
  }
}
```

### Result mapping

```json
[]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
SDOT ZA.S[Wreg1, imm1, VGX4], { Zreg1.H - Zreg2.H }, { Zreg3.H - Zreg4.H }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SDOT--2-way--multiple-vectors---Multi-vector-signed-integer-dot-product-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

