# SME2 / ZA array / Accumulate / Vertical dot product — Part 1

## svsuvdot_lane_za32[_s8]_vg1x4

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsuvdot_lane_za32%5B_s8%5D_vg1x4

### Signature (source notation)

```c
void svsuvdot_lane_za32[_s8]_vg1x4(uint32_t slice, svint8x4_t zn, svint8_t zm, uint64_t imm_idx)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector signed by unsigned integer vertical dot-product by indexed element

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Vertical dot product

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
SUVDOT ZA.S[Wreg1, imm2, VGX4], { Zreg1.B - Zreg2.B }, Zreg3.B[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SUVDOT--Multi-vector-signed-by-unsigned-integer-vertical-dot-product-by-indexed-element-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svusvdot_lane_za32[_u8]_vg1x4

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svusvdot_lane_za32%5B_u8%5D_vg1x4

### Signature (source notation)

```c
void svusvdot_lane_za32[_u8]_vg1x4(uint32_t slice, svuint8x4_t zn, svuint8_t zm, uint64_t imm_idx)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector unsigned by signed integer vertical dot-product by indexed element

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Vertical dot product

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
USVDOT ZA.S[Wreg1, imm2, VGX4], { Zreg1.B - Zreg2.B }, Zreg3.B[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/USVDOT--Multi-vector-unsigned-by-signed-integer-vertical-dot-product-by-indexed-element-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svvdot_lane_za32[_bf16]_vg1x2

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svvdot_lane_za32%5B_bf16%5D_vg1x2

### Signature (source notation)

```c
void svvdot_lane_za32[_bf16]_vg1x2(uint32_t slice, svbfloat16x2_t zn, svbfloat16_t zm, uint64_t imm_idx)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector BFloat16 vertical dot-product by indexed element

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Vertical dot product

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
BFVDOT ZA.S[Wreg1, imm2, VGX2], { Zreg1.H, Zreg2.H }, Zreg3.H[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/BFVDOT--Multi-vector-BFloat16-vertical-dot-product-by-indexed-element-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svvdot_lane_za32[_f16]_vg1x2

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svvdot_lane_za32%5B_f16%5D_vg1x2

### Signature (source notation)

```c
void svvdot_lane_za32[_f16]_vg1x2(uint32_t slice, svfloat16x2_t zn, svfloat16_t zm, uint64_t imm_idx)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector half-precision vertical dot-product by indexed element

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Vertical dot product

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
FVDOT ZA.S[Wreg1, imm2, VGX2], { Zreg1.H, Zreg2.H }, Zreg3.H[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/FVDOT--FP16-to-FP32---Multi-vector-half-precision-vertical-dot-product-by-indexed-element-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svvdot_lane_za32[_s16]_vg1x2

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svvdot_lane_za32%5B_s16%5D_vg1x2

### Signature (source notation)

```c
void svvdot_lane_za32[_s16]_vg1x2(uint32_t slice, svint16x2_t zn, svint16_t zm, uint64_t imm_idx)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector signed integer vertical dot-product by indexed element

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Vertical dot product

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
SVDOT ZA.S[Wreg1, imm2, VGX2], { Zreg1.H, Zreg2.H }, Zreg3.H[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SVDOT--2-way---Multi-vector-signed-integer-vertical-dot-product-by-indexed-element-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svvdot_lane_za32[_s8]_vg1x4

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svvdot_lane_za32%5B_s8%5D_vg1x4

### Signature (source notation)

```c
void svvdot_lane_za32[_s8]_vg1x4(uint32_t slice, svint8x4_t zn, svint8_t zm, uint64_t imm_idx)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector signed integer vertical dot-product by indexed element

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Vertical dot product

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
SVDOT ZA.S[Wreg1, imm2, VGX4], { Zreg1.B - Zreg2.B }, Zreg3.B[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SVDOT--4-way---Multi-vector-signed-integer-vertical-dot-product-by-indexed-element-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svvdot_lane_za32[_u16]_vg1x2

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svvdot_lane_za32%5B_u16%5D_vg1x2

### Signature (source notation)

```c
void svvdot_lane_za32[_u16]_vg1x2(uint32_t slice, svuint16x2_t zn, svuint16_t zm, uint64_t imm_idx)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector unsigned integer vertical dot-product by indexed element

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Vertical dot product

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
UVDOT ZA.S[Wreg1, imm2, VGX2], { Zreg1.H, Zreg2.H }, Zreg3.H[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/UVDOT--2-way---Multi-vector-unsigned-integer-vertical-dot-product-by-indexed-element-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svvdot_lane_za32[_u8]_vg1x4

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svvdot_lane_za32%5B_u8%5D_vg1x4

### Signature (source notation)

```c
void svvdot_lane_za32[_u8]_vg1x4(uint32_t slice, svuint8x4_t zn, svuint8_t zm, uint64_t imm_idx)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector unsigned integer vertical dot-product by indexed element

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Vertical dot product

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
UVDOT ZA.S[Wreg1, imm2, VGX4], { Zreg1.B - Zreg2.B }, Zreg3.B[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/UVDOT--4-way---Multi-vector-unsigned-integer-vertical-dot-product-by-indexed-element-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svvdot_lane_za64[_s16]_vg1x4

ISA classification: SME2 + FEAT_SME_I16I64

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svvdot_lane_za64%5B_s16%5D_vg1x4

### Signature (source notation)

```c
void svvdot_lane_za64[_s16]_vg1x4(uint32_t slice, svint16x4_t zn, svint16_t zm, uint64_t imm_idx)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector signed integer vertical dot-product by indexed element

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Vertical dot product

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
SVDOT ZA.D[Wreg1, imm2, VGX4], { Zreg1.H - Zreg2.H }, Zreg3.H[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SVDOT--4-way---Multi-vector-signed-integer-vertical-dot-product-by-indexed-element-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svvdot_lane_za64[_u16]_vg1x4

ISA classification: SME2 + FEAT_SME_I16I64

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svvdot_lane_za64%5B_u16%5D_vg1x4

### Signature (source notation)

```c
void svvdot_lane_za64[_u16]_vg1x4(uint32_t slice, svuint16x4_t zn, svuint16_t zm, uint64_t imm_idx)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector unsigned integer vertical dot-product by indexed element

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Vertical dot product

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
UVDOT ZA.D[Wreg1, imm2, VGX4], { Zreg1.H - Zreg2.H }, Zreg3.H[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/UVDOT--4-way---Multi-vector-unsigned-integer-vertical-dot-product-by-indexed-element-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

