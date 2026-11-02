# SME2 / ZA array / Accumulate / Fused multiply-add — Part 2

## svmla_lane_za32[_s8]_vg4x2

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmla_lane_za32%5B_s8%5D_vg4x2

### Signature (source notation)

```c
void svmla_lane_za32[_s8]_vg4x2(uint32_t slice, svint8x2_t zn, svint8_t zm, uint64_t imm_idx)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector signed integer multiply-add long-long by indexed element

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Fused multiply-add

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
SMLALL ZA.S[Wreg1, imm2:<imm2+3>, VGX2], { Zreg1.B, Zreg2.B }, Zreg3.B[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SMLALL--multiple-and-indexed-vector---Multi-vector-signed-integer-multiply-add-long-long-by-indexed-element-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmla_lane_za32[_s8]_vg4x4

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmla_lane_za32%5B_s8%5D_vg4x4

### Signature (source notation)

```c
void svmla_lane_za32[_s8]_vg4x4(uint32_t slice, svint8x4_t zn, svint8_t zm, uint64_t imm_idx)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector signed integer multiply-add long-long by indexed element

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Fused multiply-add

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
SMLALL ZA.S[Wreg1, imm2:<imm2+3>, VGX4], { Zreg1.B - Zreg2.B }, Zreg3.B[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SMLALL--multiple-and-indexed-vector---Multi-vector-signed-integer-multiply-add-long-long-by-indexed-element-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmla_lane_za32[_u16]_vg2x1

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmla_lane_za32%5B_u16%5D_vg2x1

### Signature (source notation)

```c
void svmla_lane_za32[_u16]_vg2x1(uint32_t slice, svuint16_t zn, svuint16_t zm, uint64_t imm_idx)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector unsigned integer multiply-add long by indexed element

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Fused multiply-add

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
    "register": "Zreg1.H"
  },
  "zm": {
    "register": "Zreg2.H"
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
UMLAL ZA.S[Wreg1, imm2:<imm2+1>], Zreg1.H, Zreg2.H[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/UMLAL--multiple-and-indexed-vector---Multi-vector-unsigned-integer-multiply-add-long-by-indexed-element-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmla_lane_za32[_u16]_vg2x2

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmla_lane_za32%5B_u16%5D_vg2x2

### Signature (source notation)

```c
void svmla_lane_za32[_u16]_vg2x2(uint32_t slice, svuint16x2_t zn, svuint16_t zm, uint64_t imm_idx)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector unsigned integer multiply-add long by indexed element

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Fused multiply-add

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
UMLAL ZA.S[Wreg1, imm2:<imm2+1>, VGX2], { Zreg1.H, Zreg2.H }, Zreg3.H[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/UMLAL--multiple-and-indexed-vector---Multi-vector-unsigned-integer-multiply-add-long-by-indexed-element-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmla_lane_za32[_u16]_vg2x4

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmla_lane_za32%5B_u16%5D_vg2x4

### Signature (source notation)

```c
void svmla_lane_za32[_u16]_vg2x4(uint32_t slice, svuint16x4_t zn, svuint16_t zm, uint64_t imm_idx)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector unsigned integer multiply-add long by indexed element

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Fused multiply-add

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
UMLAL ZA.S[Wreg1, imm2:<imm2+1>, VGX4], { Zreg1.H - Zreg2.H }, Zreg3.H[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/UMLAL--multiple-and-indexed-vector---Multi-vector-unsigned-integer-multiply-add-long-by-indexed-element-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmla_lane_za32[_u8]_vg4x1

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmla_lane_za32%5B_u8%5D_vg4x1

### Signature (source notation)

```c
void svmla_lane_za32[_u8]_vg4x1(uint32_t slice, svuint8_t zn, svuint8_t zm, uint64_t imm_idx)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector unsigned integer multiply-add long-long by indexed element

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Fused multiply-add

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
    "register": "Zreg1.B"
  },
  "zm": {
    "register": "Zreg2.B"
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
UMLALL ZA.S[Wreg1, imm2:<imm2+3>], Zreg1.B, Zreg2.B[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/UMLALL--multiple-and-indexed-vector---Multi-vector-unsigned-integer-multiply-add-long-long-by-indexed-element-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmla_lane_za32[_u8]_vg4x2

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmla_lane_za32%5B_u8%5D_vg4x2

### Signature (source notation)

```c
void svmla_lane_za32[_u8]_vg4x2(uint32_t slice, svuint8x2_t zn, svuint8_t zm, uint64_t imm_idx)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector unsigned integer multiply-add long-long by indexed element

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Fused multiply-add

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
UMLALL ZA.S[Wreg1, imm2:<imm2+3>, VGX2], { Zreg1.B, Zreg2.B }, Zreg3.B[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/UMLALL--multiple-and-indexed-vector---Multi-vector-unsigned-integer-multiply-add-long-long-by-indexed-element-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmla_lane_za32[_u8]_vg4x4

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmla_lane_za32%5B_u8%5D_vg4x4

### Signature (source notation)

```c
void svmla_lane_za32[_u8]_vg4x4(uint32_t slice, svuint8x4_t zn, svuint8_t zm, uint64_t imm_idx)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector unsigned integer multiply-add long-long by indexed element

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Fused multiply-add

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
UMLALL ZA.S[Wreg1, imm2:<imm2+3>, VGX4], { Zreg1.B - Zreg2.B }, Zreg3.B[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/UMLALL--multiple-and-indexed-vector---Multi-vector-unsigned-integer-multiply-add-long-long-by-indexed-element-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmla_lane_za64[_f64]_vg1x2

ISA classification: SME2 + FEAT_SME_F64F64

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmla_lane_za64%5B_f64%5D_vg1x2

### Signature (source notation)

```c
void svmla_lane_za64[_f64]_vg1x2(uint32_t slice, svfloat64x2_t zn, svfloat64_t zm, uint64_t imm_idx)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector floating-point fused multiply-add by indexed element

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Fused multiply-add

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2,FEAT_SME_F64F64
```

### Return type metadata

```json
{
  "return_base_type": "void",
  "element_bit_size": "64",
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
    "Z multi-vector": "{ Zreg1.D, Zreg2.D }"
  },
  "zm": {
    "register": "Zreg3.D"
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
FMLA ZA.D[Wreg1, imm2, VGX2], { Zreg1.D, Zreg2.D }, Zreg3.D[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/FMLA--multiple-and-indexed-vector---Multi-vector-floating-point-fused-multiply-add-by-indexed-element-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmla_lane_za64[_f64]_vg1x4

ISA classification: SME2 + FEAT_SME_F64F64

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmla_lane_za64%5B_f64%5D_vg1x4

### Signature (source notation)

```c
void svmla_lane_za64[_f64]_vg1x4(uint32_t slice, svfloat64x4_t zn, svfloat64_t zm, uint64_t imm_idx)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector floating-point fused multiply-add by indexed element

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Fused multiply-add

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2,FEAT_SME_F64F64
```

### Return type metadata

```json
{
  "return_base_type": "void",
  "element_bit_size": "64",
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
    "Z multi-vector": "{ Zreg1.D - Zreg2.D }"
  },
  "zm": {
    "register": "Zreg3.D"
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
FMLA ZA.D[Wreg1, imm2, VGX4], { Zreg1.D - Zreg2.D }, Zreg3.D[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/FMLA--multiple-and-indexed-vector---Multi-vector-floating-point-fused-multiply-add-by-indexed-element-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmla_lane_za64[_s16]_vg4x1

ISA classification: SME2 + FEAT_SME_I16I64

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmla_lane_za64%5B_s16%5D_vg4x1

### Signature (source notation)

```c
void svmla_lane_za64[_s16]_vg4x1(uint32_t slice, svint16_t zn, svint16_t zm, uint64_t imm_idx)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector signed integer multiply-add long-long by indexed element

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Fused multiply-add

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
    "register": "Zreg1.H"
  },
  "zm": {
    "register": "Zreg2.H"
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
SMLALL ZA.D[Wreg1, imm2:<imm2+3>], Zreg1.H, Zreg2.H[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SMLALL--multiple-and-indexed-vector---Multi-vector-signed-integer-multiply-add-long-long-by-indexed-element-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmla_lane_za64[_s16]_vg4x2

ISA classification: SME2 + FEAT_SME_I16I64

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmla_lane_za64%5B_s16%5D_vg4x2

### Signature (source notation)

```c
void svmla_lane_za64[_s16]_vg4x2(uint32_t slice, svint16x2_t zn, svint16_t zm, uint64_t imm_idx)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector signed integer multiply-add long-long by indexed element

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Fused multiply-add

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
SMLALL ZA.D[Wreg1, imm2:<imm2+3>, VGX2], { Zreg1.H, Zreg2.H }, Zreg3.H[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SMLALL--multiple-and-indexed-vector---Multi-vector-signed-integer-multiply-add-long-long-by-indexed-element-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmla_lane_za64[_s16]_vg4x4

ISA classification: SME2 + FEAT_SME_I16I64

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmla_lane_za64%5B_s16%5D_vg4x4

### Signature (source notation)

```c
void svmla_lane_za64[_s16]_vg4x4(uint32_t slice, svint16x4_t zn, svint16_t zm, uint64_t imm_idx)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector signed integer multiply-add long-long by indexed element

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Fused multiply-add

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
SMLALL ZA.D[Wreg1, imm2:<imm2+3>, VGX4], { Zreg1.H - Zreg2.H }, Zreg3.H[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SMLALL--multiple-and-indexed-vector---Multi-vector-signed-integer-multiply-add-long-long-by-indexed-element-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmla_lane_za64[_u16]_vg4x1

ISA classification: SME2 + FEAT_SME_I16I64

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmla_lane_za64%5B_u16%5D_vg4x1

### Signature (source notation)

```c
void svmla_lane_za64[_u16]_vg4x1(uint32_t slice, svuint16_t zn, svuint16_t zm, uint64_t imm_idx)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector unsigned integer multiply-add long-long by indexed element

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Fused multiply-add

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
    "register": "Zreg1.H"
  },
  "zm": {
    "register": "Zreg2.H"
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
UMLALL ZA.D[Wreg1, imm2:<imm2+3>], Zreg1.H, Zreg2.H[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/UMLALL--multiple-and-indexed-vector---Multi-vector-unsigned-integer-multiply-add-long-long-by-indexed-element-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmla_lane_za64[_u16]_vg4x2

ISA classification: SME2 + FEAT_SME_I16I64

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmla_lane_za64%5B_u16%5D_vg4x2

### Signature (source notation)

```c
void svmla_lane_za64[_u16]_vg4x2(uint32_t slice, svuint16x2_t zn, svuint16_t zm, uint64_t imm_idx)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector unsigned integer multiply-add long-long by indexed element

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Fused multiply-add

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
UMLALL ZA.D[Wreg1, imm2:<imm2+3>, VGX2], { Zreg1.H, Zreg2.H }, Zreg3.H[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/UMLALL--multiple-and-indexed-vector---Multi-vector-unsigned-integer-multiply-add-long-long-by-indexed-element-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmla_lane_za64[_u16]_vg4x4

ISA classification: SME2 + FEAT_SME_I16I64

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmla_lane_za64%5B_u16%5D_vg4x4

### Signature (source notation)

```c
void svmla_lane_za64[_u16]_vg4x4(uint32_t slice, svuint16x4_t zn, svuint16_t zm, uint64_t imm_idx)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector unsigned integer multiply-add long-long by indexed element

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Fused multiply-add

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
UMLALL ZA.D[Wreg1, imm2:<imm2+3>, VGX4], { Zreg1.H - Zreg2.H }, Zreg3.H[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/UMLALL--multiple-and-indexed-vector---Multi-vector-unsigned-integer-multiply-add-long-long-by-indexed-element-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmla_za16[_bf16]_vg1x2

ISA classification: SME2 + FEAT_SME_B16B16

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmla_za16%5B_bf16%5D_vg1x2

### Signature (source notation)

```c
void svmla_za16[_bf16]_vg1x2(uint32_t slice, svbfloat16x2_t zn, svbfloat16x2_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector BFloat16 fused multiply-add

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Fused multiply-add

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME_B16B16
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
BFMLA ZA.H[Wreg1, imm1, VGX2], { Zreg1.H, Zreg2.H }, { Zreg3.H, Zreg4.H }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/BFMLA--multiple-vectors---Multi-vector-BFloat16-fused-multiply-add-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmla_za16[_bf16]_vg1x4

ISA classification: SME2 + FEAT_SME_B16B16

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmla_za16%5B_bf16%5D_vg1x4

### Signature (source notation)

```c
void svmla_za16[_bf16]_vg1x4(uint32_t slice, svbfloat16x4_t zn, svbfloat16x4_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector BFloat16 fused multiply-add

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Fused multiply-add

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME_B16B16
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
BFMLA ZA.H[Wreg1, imm1, VGX4], { Zreg1.H - Zreg2.H }, { Zreg3.H - Zreg4.H }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/BFMLA--multiple-vectors---Multi-vector-BFloat16-fused-multiply-add-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmla_za16[_f16]_vg1x2

ISA classification: SME2 + FEAT_SME_F16F16

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmla_za16%5B_f16%5D_vg1x2

### Signature (source notation)

```c
void svmla_za16[_f16]_vg1x2(uint32_t slice, svfloat16x2_t zn, svfloat16x2_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector floating-point fused multiply-add

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Fused multiply-add

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME_F16F16
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
FMLA ZA.H[Wreg1, imm1, VGX2], { Zreg1.H, Zreg2.H }, { Zreg3.H, Zreg4.H }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/FMLA--multiple-vectors---Multi-vector-floating-point-fused-multiply-add-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmla_za16[_f16]_vg1x4

ISA classification: SME2 + FEAT_SME_F16F16

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmla_za16%5B_f16%5D_vg1x4

### Signature (source notation)

```c
void svmla_za16[_f16]_vg1x4(uint32_t slice, svfloat16x4_t zn, svfloat16x4_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector floating-point fused multiply-add

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Fused multiply-add

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME_F16F16
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
FMLA ZA.H[Wreg1, imm1, VGX4], { Zreg1.H - Zreg2.H }, { Zreg3.H - Zreg4.H }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/FMLA--multiple-vectors---Multi-vector-floating-point-fused-multiply-add-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmla_za16[_mf8]_vg2x1_fpm

ISA classification: SME2 + FEAT_SME_F8F16

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmla_za16%5B_mf8%5D_vg2x1_fpm

### Signature (source notation)

```c
void svmla_za16[_mf8]_vg2x1_fpm(uint32_t slice, svmfloat8_t zn, svmfloat8_t zm, fpm_t fpm)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector 8-bit floating-point multiply-add by vector to half-precision

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Fused multiply-add

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
    "register": "Zreg1.B"
  },
  "zm": {
    "register": "Zreg2.B"
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
FMLAL ZA.H[Wreg2, imm1:<imm1+1>], Zreg1.B, Zreg2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/FMLAL--multiple-and-single-vector--FP8-to-FP16---Multi-vector-8-bit-floating-point-multiply-add-by-vector-to-half-precision-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmla_za16[_mf8]_vg2x2_fpm

ISA classification: SME2 + FEAT_SME_F8F16

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmla_za16%5B_mf8%5D_vg2x2_fpm

### Signature (source notation)

```c
void svmla_za16[_mf8]_vg2x2_fpm(uint32_t slice, svmfloat8x2_t zn, svmfloat8x2_t zm, fpm_t fpm)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector 8-bit floating-point multiply-add to half-precision

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Fused multiply-add

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
FMLAL ZA.H[Wreg2, imm1:<imm1+1>, VGX2], { Zreg1.B, Zreg2.B }, { Zreg3.B, Zreg4.B }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/FMLAL--multiple-vectors--FP8-to-FP16---Multi-vector-8-bit-floating-point-multiply-add-to-half-precision-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmla_za16[_mf8]_vg2x4_fpm

ISA classification: SME2 + FEAT_SME_F8F16

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmla_za16%5B_mf8%5D_vg2x4_fpm

### Signature (source notation)

```c
void svmla_za16[_mf8]_vg2x4_fpm(uint32_t slice, svmfloat8x4_t zn, svmfloat8x4_t zm, fpm_t fpm)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector 8-bit floating-point multiply-add to half-precision

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Fused multiply-add

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
FMLAL ZA.H[Wreg2, imm1:<imm1+1>, VGX4], { Zreg1.B - Zreg2.B }, { Zreg3.B - Zreg4.B }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/FMLAL--multiple-vectors--FP8-to-FP16---Multi-vector-8-bit-floating-point-multiply-add-to-half-precision-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmla_za32[_bf16]_vg2x1

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmla_za32%5B_bf16%5D_vg2x1

### Signature (source notation)

```c
void svmla_za32[_bf16]_vg2x1(uint32_t slice, svbfloat16_t zn, svbfloat16_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector BFloat16 multiply-add long by vector

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Fused multiply-add

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
    "register": "Zreg1.H"
  },
  "zm": {
    "register": "Zreg2.H"
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
BFMLAL ZA.S[Wreg1, imm1:<imm1+1>], Zreg1.H, Zreg2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/BFMLAL--multiple-and-single-vector---Multi-vector-BFloat16-multiply-add-long-by-vector-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmla_za32[_bf16]_vg2x2

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmla_za32%5B_bf16%5D_vg2x2

### Signature (source notation)

```c
void svmla_za32[_bf16]_vg2x2(uint32_t slice, svbfloat16x2_t zn, svbfloat16x2_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector BFloat16 multiply-add long

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Fused multiply-add

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
BFMLAL ZA.S[Wreg1, imm1:<imm1+1>, VGX2], { Zreg1.H, Zreg2.H }, { Zreg3.H, Zreg4.H }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/BFMLAL--multiple-vectors---Multi-vector-BFloat16-multiply-add-long-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmla_za32[_bf16]_vg2x4

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmla_za32%5B_bf16%5D_vg2x4

### Signature (source notation)

```c
void svmla_za32[_bf16]_vg2x4(uint32_t slice, svbfloat16x4_t zn, svbfloat16x4_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector BFloat16 multiply-add long

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Fused multiply-add

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
BFMLAL ZA.S[Wreg1, imm1:<imm1+1>, VGX4], { Zreg1.H - Zreg2.H }, { Zreg3.H - Zreg4.H }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/BFMLAL--multiple-vectors---Multi-vector-BFloat16-multiply-add-long-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmla_za32[_f16]_vg2x1

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmla_za32%5B_f16%5D_vg2x1

### Signature (source notation)

```c
void svmla_za32[_f16]_vg2x1(uint32_t slice, svfloat16_t zn, svfloat16_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector floating-point multiply-add long by vector

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Fused multiply-add

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
    "register": "Zreg1.H"
  },
  "zm": {
    "register": "Zreg2.H"
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
FMLAL ZA.S[Wreg1, imm1:<imm1+1>], Zreg1.H, Zreg2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/FMLAL--multiple-and-single-vector--FP16-to-FP32---Multi-vector-floating-point-multiply-add-long-by-vector-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmla_za32[_f16]_vg2x2

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmla_za32%5B_f16%5D_vg2x2

### Signature (source notation)

```c
void svmla_za32[_f16]_vg2x2(uint32_t slice, svfloat16x2_t zn, svfloat16x2_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector floating-point multiply-add long

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Fused multiply-add

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
FMLAL ZA.S[Wreg1, imm1:<imm1+1>, VGX2], { Zreg1.H, Zreg2.H }, { Zreg3.H, Zreg4.H }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/FMLAL--multiple-vectors--FP16-to-FP32---Multi-vector-floating-point-multiply-add-long-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmla_za32[_f16]_vg2x4

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmla_za32%5B_f16%5D_vg2x4

### Signature (source notation)

```c
void svmla_za32[_f16]_vg2x4(uint32_t slice, svfloat16x4_t zn, svfloat16x4_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector floating-point multiply-add long

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Fused multiply-add

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
FMLAL ZA.S[Wreg1, imm1:<imm1+1>, VGX4], { Zreg1.H - Zreg2.H }, { Zreg3.H - Zreg4.H }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/FMLAL--multiple-vectors--FP16-to-FP32---Multi-vector-floating-point-multiply-add-long-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmla_za32[_f32]_vg1x2

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmla_za32%5B_f32%5D_vg1x2

### Signature (source notation)

```c
void svmla_za32[_f32]_vg1x2(uint32_t slice, svfloat32x2_t zn, svfloat32x2_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector floating-point fused multiply-add

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Fused multiply-add

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
  "element_bit_size": "32",
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
    "Z multi-vector": "{ Zreg1.S, Zreg2.S }"
  },
  "zm": {
    "Z multi-vector": "{ Zreg3.S, Zreg4.S }"
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
FMLA ZA.S[Wreg1, imm1, VGX2], { Zreg1.S, Zreg2.S }, { Zreg3.S, Zreg4.S }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/FMLA--multiple-vectors---Multi-vector-floating-point-fused-multiply-add-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmla_za32[_f32]_vg1x4

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmla_za32%5B_f32%5D_vg1x4

### Signature (source notation)

```c
void svmla_za32[_f32]_vg1x4(uint32_t slice, svfloat32x4_t zn, svfloat32x4_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector floating-point fused multiply-add

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Fused multiply-add

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
  "element_bit_size": "32",
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
    "Z multi-vector": "{ Zreg1.S - Zreg2.S }"
  },
  "zm": {
    "Z multi-vector": "{ Zreg3.S - Zreg4.S }"
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
FMLA ZA.S[Wreg1, imm1, VGX4], { Zreg1.S - Zreg2.S }, { Zreg3.S - Zreg4.S }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/FMLA--multiple-vectors---Multi-vector-floating-point-fused-multiply-add-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmla_za32[_mf8]_vg4x1_fpm

ISA classification: SME2 + FEAT_SME_F8F32

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmla_za32%5B_mf8%5D_vg4x1_fpm

### Signature (source notation)

```c
void svmla_za32[_mf8]_vg4x1_fpm(uint32_t slice, svmfloat8_t zn, svmfloat8_t zm, fpm_t fpm)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector 8-bit floating-point multiply-add by vector to single-precision

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Fused multiply-add

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
    "register": "Zreg1.B"
  },
  "zm": {
    "register": "Zreg2.B"
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
FMLALL ZA.S[Wreg2, imm1:<imm1+3>], Zreg1.B, Zreg2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/FMLALL--multiple-and-single-vector---Multi-vector-8-bit-floating-point-multiply-add-by-vector-to-single-precision-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmla_za32[_mf8]_vg4x2_fpm

ISA classification: SME2 + FEAT_SME_F8F32

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmla_za32%5B_mf8%5D_vg4x2_fpm

### Signature (source notation)

```c
void svmla_za32[_mf8]_vg4x2_fpm(uint32_t slice, svmfloat8x2_t zn, svmfloat8x2_t zm, fpm_t fpm)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector 8-bit floating-point multiply-add to single-precision

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Fused multiply-add

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
FMLALL ZA.S[Wreg2, imm1:<imm1+3>, VGX2], { Zreg1.B, Zreg2.B }, { Zreg3.B, Zreg4.B }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/FMLALL--multiple-vectors---Multi-vector-8-bit-floating-point-multiply-add-to-single-precision-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmla_za32[_mf8]_vg4x4_fpm

ISA classification: SME2 + FEAT_SME_F8F32

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmla_za32%5B_mf8%5D_vg4x4_fpm

### Signature (source notation)

```c
void svmla_za32[_mf8]_vg4x4_fpm(uint32_t slice, svmfloat8x4_t zn, svmfloat8x4_t zm, fpm_t fpm)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector 8-bit floating-point multiply-add to single-precision

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Fused multiply-add

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
FMLALL ZA.S[Wreg2, imm1:<imm1+3>, VGX4], { Zreg1.B - Zreg2.B }, { Zreg3.B - Zreg4.B }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/FMLALL--multiple-vectors---Multi-vector-8-bit-floating-point-multiply-add-to-single-precision-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmla_za32[_s16]_vg2x1

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmla_za32%5B_s16%5D_vg2x1

### Signature (source notation)

```c
void svmla_za32[_s16]_vg2x1(uint32_t slice, svint16_t zn, svint16_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector signed integer multiply-add long by vector

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Fused multiply-add

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
    "register": "Zreg1.H"
  },
  "zm": {
    "register": "Zreg2.H"
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
SMLAL ZA.S[Wreg1, imm1:<imm1+1>], Zreg1.H, Zreg2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SMLAL--multiple-and-single-vector---Multi-vector-signed-integer-multiply-add-long-by-vector-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmla_za32[_s16]_vg2x2

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmla_za32%5B_s16%5D_vg2x2

### Signature (source notation)

```c
void svmla_za32[_s16]_vg2x2(uint32_t slice, svint16x2_t zn, svint16x2_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector signed integer multiply-add long

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Fused multiply-add

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
SMLAL ZA.S[Wreg1, imm1:<imm1+1>, VGX2], { Zreg1.H, Zreg2.H }, { Zreg3.H, Zreg4.H }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SMLAL--multiple-vectors---Multi-vector-signed-integer-multiply-add-long-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmla_za32[_s16]_vg2x4

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmla_za32%5B_s16%5D_vg2x4

### Signature (source notation)

```c
void svmla_za32[_s16]_vg2x4(uint32_t slice, svint16x4_t zn, svint16x4_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector signed integer multiply-add long

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Fused multiply-add

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
SMLAL ZA.S[Wreg1, imm1:<imm1+1>, VGX4], { Zreg1.H - Zreg2.H }, { Zreg3.H - Zreg4.H }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SMLAL--multiple-vectors---Multi-vector-signed-integer-multiply-add-long-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmla_za32[_s8]_vg4x1

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmla_za32%5B_s8%5D_vg4x1

### Signature (source notation)

```c
void svmla_za32[_s8]_vg4x1(uint32_t slice, svint8_t zn, svint8_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector signed integer multiply-add long-long by vector

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Fused multiply-add

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
    "register": "Zreg1.B"
  },
  "zm": {
    "register": "Zreg2.B"
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
SMLALL ZA.S[Wreg1, imm1:<imm1+3>], Zreg1.B, Zreg2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SMLALL--multiple-and-single-vector---Multi-vector-signed-integer-multiply-add-long-long-by-vector-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmla_za32[_s8]_vg4x2

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmla_za32%5B_s8%5D_vg4x2

### Signature (source notation)

```c
void svmla_za32[_s8]_vg4x2(uint32_t slice, svint8x2_t zn, svint8x2_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector signed integer multiply-add long-long

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Fused multiply-add

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
    "Z multi-vector": "{ Zreg3.B, Zreg4.B }"
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
SMLALL ZA.S[Wreg1, imm1:<imm1+3>, VGX2], { Zreg1.B, Zreg2.B }, { Zreg3.B, Zreg4.B }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SMLALL--multiple-vectors---Multi-vector-signed-integer-multiply-add-long-long-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmla_za32[_s8]_vg4x4

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmla_za32%5B_s8%5D_vg4x4

### Signature (source notation)

```c
void svmla_za32[_s8]_vg4x4(uint32_t slice, svint8x4_t zn, svint8x4_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector signed integer multiply-add long-long

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Fused multiply-add

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
    "Z multi-vector": "{ Zreg3.B - Zreg4.B }"
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
SMLALL ZA.S[Wreg1, imm1:<imm1+3>, VGX4], { Zreg1.B - Zreg2.B }, { Zreg3.B - Zreg4.B }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SMLALL--multiple-vectors---Multi-vector-signed-integer-multiply-add-long-long-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmla_za32[_u16]_vg2x1

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmla_za32%5B_u16%5D_vg2x1

### Signature (source notation)

```c
void svmla_za32[_u16]_vg2x1(uint32_t slice, svuint16_t zn, svuint16_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector unsigned integer multiply-add long by vector

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Fused multiply-add

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
    "register": "Zreg1.H"
  },
  "zm": {
    "register": "Zreg2.H"
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
UMLAL ZA.S[Wreg1, imm1:<imm1+1>], Zreg1.H, Zreg2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/UMLAL--multiple-and-single-vector---Multi-vector-unsigned-integer-multiply-add-long-by-vector-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmla_za32[_u16]_vg2x2

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmla_za32%5B_u16%5D_vg2x2

### Signature (source notation)

```c
void svmla_za32[_u16]_vg2x2(uint32_t slice, svuint16x2_t zn, svuint16x2_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector unsigned integer multiply-add long

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Fused multiply-add

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
UMLAL ZA.S[Wreg1, imm1:<imm1+1>, VGX2], { Zreg1.H, Zreg2.H }, { Zreg3.H, Zreg4.H }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/UMLAL--multiple-vectors---Multi-vector-unsigned-integer-multiply-add-long-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmla_za32[_u16]_vg2x4

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmla_za32%5B_u16%5D_vg2x4

### Signature (source notation)

```c
void svmla_za32[_u16]_vg2x4(uint32_t slice, svuint16x4_t zn, svuint16x4_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector unsigned integer multiply-add long

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Fused multiply-add

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
UMLAL ZA.S[Wreg1, imm1:<imm1+1>, VGX4], { Zreg1.H - Zreg2.H }, { Zreg3.H - Zreg4.H }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/UMLAL--multiple-vectors---Multi-vector-unsigned-integer-multiply-add-long-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmla_za32[_u8]_vg4x1

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmla_za32%5B_u8%5D_vg4x1

### Signature (source notation)

```c
void svmla_za32[_u8]_vg4x1(uint32_t slice, svuint8_t zn, svuint8_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector unsigned integer multiply-add long-long by vector

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Fused multiply-add

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
    "register": "Zreg1.B"
  },
  "zm": {
    "register": "Zreg2.B"
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
UMLALL ZA.S[Wreg1, imm1:<imm1+3>], Zreg1.B, Zreg2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/UMLALL--multiple-and-single-vector---Multi-vector-unsigned-integer-multiply-add-long-long-by-vector-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmla_za32[_u8]_vg4x2

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmla_za32%5B_u8%5D_vg4x2

### Signature (source notation)

```c
void svmla_za32[_u8]_vg4x2(uint32_t slice, svuint8x2_t zn, svuint8x2_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector unsigned integer multiply-add long-long

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Fused multiply-add

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
    "Z multi-vector": "{ Zreg3.B, Zreg4.B }"
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
UMLALL ZA.S[Wreg1, imm1:<imm1+3>, VGX2], { Zreg1.B, Zreg2.B }, { Zreg3.B, Zreg4.B }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/UMLALL--multiple-vectors---Multi-vector-unsigned-integer-multiply-add-long-long-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmla_za32[_u8]_vg4x4

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmla_za32%5B_u8%5D_vg4x4

### Signature (source notation)

```c
void svmla_za32[_u8]_vg4x4(uint32_t slice, svuint8x4_t zn, svuint8x4_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector unsigned integer multiply-add long-long

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Fused multiply-add

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
    "Z multi-vector": "{ Zreg3.B - Zreg4.B }"
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
UMLALL ZA.S[Wreg1, imm1:<imm1+3>, VGX4], { Zreg1.B - Zreg2.B }, { Zreg3.B - Zreg4.B }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/UMLALL--multiple-vectors---Multi-vector-unsigned-integer-multiply-add-long-long-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmla_za64[_f64]_vg1x2

ISA classification: SME2 + FEAT_SME_F64F64

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmla_za64%5B_f64%5D_vg1x2

### Signature (source notation)

```c
void svmla_za64[_f64]_vg1x2(uint32_t slice, svfloat64x2_t zn, svfloat64x2_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector floating-point fused multiply-add

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Fused multiply-add

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2,FEAT_SME_F64F64
```

### Return type metadata

```json
{
  "return_base_type": "void",
  "element_bit_size": "64",
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
    "Z multi-vector": "{ Zreg1.D, Zreg2.D }"
  },
  "zm": {
    "Z multi-vector": "{ Zreg3.D, Zreg4.D }"
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
FMLA ZA.D[Wreg1, imm1, VGX2], { Zreg1.D, Zreg2.D }, { Zreg3.D, Zreg4.D }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/FMLA--multiple-vectors---Multi-vector-floating-point-fused-multiply-add-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmla_za64[_f64]_vg1x4

ISA classification: SME2 + FEAT_SME_F64F64

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmla_za64%5B_f64%5D_vg1x4

### Signature (source notation)

```c
void svmla_za64[_f64]_vg1x4(uint32_t slice, svfloat64x4_t zn, svfloat64x4_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector floating-point fused multiply-add

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Fused multiply-add

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2,FEAT_SME_F64F64
```

### Return type metadata

```json
{
  "return_base_type": "void",
  "element_bit_size": "64",
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
    "Z multi-vector": "{ Zreg1.D - Zreg2.D }"
  },
  "zm": {
    "Z multi-vector": "{ Zreg3.D - Zreg4.D }"
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
FMLA ZA.D[Wreg1, imm1, VGX4], { Zreg1.D - Zreg2.D }, { Zreg3.D - Zreg4.D }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/FMLA--multiple-vectors---Multi-vector-floating-point-fused-multiply-add-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmla_za64[_s16]_vg4x1

ISA classification: SME2 + FEAT_SME_I16I64

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmla_za64%5B_s16%5D_vg4x1

### Signature (source notation)

```c
void svmla_za64[_s16]_vg4x1(uint32_t slice, svint16_t zn, svint16_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector signed integer multiply-add long-long by vector

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Fused multiply-add

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
    "register": "Zreg1.H"
  },
  "zm": {
    "register": "Zreg2.H"
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
SMLALL ZA.D[Wreg1, imm1:<imm1+3>], Zreg1.H, Zreg2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SMLALL--multiple-and-single-vector---Multi-vector-signed-integer-multiply-add-long-long-by-vector-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmla_za64[_s16]_vg4x2

ISA classification: SME2 + FEAT_SME_I16I64

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmla_za64%5B_s16%5D_vg4x2

### Signature (source notation)

```c
void svmla_za64[_s16]_vg4x2(uint32_t slice, svint16x2_t zn, svint16x2_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector signed integer multiply-add long-long

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Fused multiply-add

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
SMLALL ZA.D[Wreg1, imm1:<imm1+3>, VGX2], { Zreg1.H, Zreg2.H }, { Zreg3.H, Zreg4.H }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SMLALL--multiple-vectors---Multi-vector-signed-integer-multiply-add-long-long-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

