# SME2 / ZA array / Accumulate / Fused multiply-subtract — Part 2

## svmls_lane_za64[_s16]_vg4x1

ISA classification: SME2 + FEAT_SME_I16I64

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmls_lane_za64%5B_s16%5D_vg4x1

### Signature (source notation)

```c
void svmls_lane_za64[_s16]_vg4x1(uint32_t slice, svint16_t zn, svint16_t zm, uint64_t imm_idx)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector signed integer multiply-subtract long-long by indexed element

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Fused multiply-subtract

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
SMLSLL ZA.D[Wreg1, imm2:<imm2+3>], Zreg1.H, Zreg2.H[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SMLSLL--multiple-and-indexed-vector---Multi-vector-signed-integer-multiply-subtract-long-long-by-indexed-element-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmls_lane_za64[_s16]_vg4x2

ISA classification: SME2 + FEAT_SME_I16I64

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmls_lane_za64%5B_s16%5D_vg4x2

### Signature (source notation)

```c
void svmls_lane_za64[_s16]_vg4x2(uint32_t slice, svint16x2_t zn, svint16_t zm, uint64_t imm_idx)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector signed integer multiply-subtract long-long by indexed element

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Fused multiply-subtract

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
SMLSLL ZA.D[Wreg1, imm2:<imm2+3>, VGX2], { Zreg1.H, Zreg2.H }, Zreg3.H[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SMLSLL--multiple-and-indexed-vector---Multi-vector-signed-integer-multiply-subtract-long-long-by-indexed-element-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmls_lane_za64[_s16]_vg4x4

ISA classification: SME2 + FEAT_SME_I16I64

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmls_lane_za64%5B_s16%5D_vg4x4

### Signature (source notation)

```c
void svmls_lane_za64[_s16]_vg4x4(uint32_t slice, svint16x4_t zn, svint16_t zm, uint64_t imm_idx)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector signed integer multiply-subtract long-long by indexed element

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Fused multiply-subtract

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
SMLSLL ZA.D[Wreg1, imm2:<imm2+3>, VGX4], { Zreg1.H - Zreg2.H }, Zreg3.H[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SMLSLL--multiple-and-indexed-vector---Multi-vector-signed-integer-multiply-subtract-long-long-by-indexed-element-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmls_lane_za64[_u16]_vg4x1

ISA classification: SME2 + FEAT_SME_I16I64

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmls_lane_za64%5B_u16%5D_vg4x1

### Signature (source notation)

```c
void svmls_lane_za64[_u16]_vg4x1(uint32_t slice, svuint16_t zn, svuint16_t zm, uint64_t imm_idx)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector unsigned integer multiply-subtract long-long by indexed element

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Fused multiply-subtract

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
UMLSLL ZA.D[Wreg1, imm2:<imm2+3>], Zreg1.H, Zreg2.H[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/UMLSLL--multiple-and-indexed-vector---Multi-vector-unsigned-integer-multiply-subtract-long-long-by-indexed-element-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmls_lane_za64[_u16]_vg4x2

ISA classification: SME2 + FEAT_SME_I16I64

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmls_lane_za64%5B_u16%5D_vg4x2

### Signature (source notation)

```c
void svmls_lane_za64[_u16]_vg4x2(uint32_t slice, svuint16x2_t zn, svuint16_t zm, uint64_t imm_idx)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector unsigned integer multiply-subtract long-long by indexed element

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Fused multiply-subtract

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
UMLSLL ZA.D[Wreg1, imm2:<imm2+3>, VGX2], { Zreg1.H, Zreg2.H }, Zreg3.H[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/UMLSLL--multiple-and-indexed-vector---Multi-vector-unsigned-integer-multiply-subtract-long-long-by-indexed-element-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmls_lane_za64[_u16]_vg4x4

ISA classification: SME2 + FEAT_SME_I16I64

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmls_lane_za64%5B_u16%5D_vg4x4

### Signature (source notation)

```c
void svmls_lane_za64[_u16]_vg4x4(uint32_t slice, svuint16x4_t zn, svuint16_t zm, uint64_t imm_idx)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector unsigned integer multiply-subtract long-long by indexed element

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Fused multiply-subtract

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
UMLSLL ZA.D[Wreg1, imm2:<imm2+3>, VGX4], { Zreg1.H - Zreg2.H }, Zreg3.H[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/UMLSLL--multiple-and-indexed-vector---Multi-vector-unsigned-integer-multiply-subtract-long-long-by-indexed-element-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmls_za16[_bf16]_vg1x2

ISA classification: SME2 + FEAT_SME_B16B16

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmls_za16%5B_bf16%5D_vg1x2

### Signature (source notation)

```c
void svmls_za16[_bf16]_vg1x2(uint32_t slice, svbfloat16x2_t zn, svbfloat16x2_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector BFloat16 fused multiply-subtract

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Fused multiply-subtract

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
BFMLS ZA.H[Wreg1, imm1, VGX2], { Zreg1.H, Zreg2.H }, { Zreg3.H, Zreg4.H }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/BFMLS--multiple-vectors---Multi-vector-BFloat16-fused-multiply-subtract-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmls_za16[_bf16]_vg1x4

ISA classification: SME2 + FEAT_SME_B16B16

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmls_za16%5B_bf16%5D_vg1x4

### Signature (source notation)

```c
void svmls_za16[_bf16]_vg1x4(uint32_t slice, svbfloat16x4_t zn, svbfloat16x4_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector BFloat16 fused multiply-subtract

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Fused multiply-subtract

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
BFMLS ZA.H[Wreg1, imm1, VGX4], { Zreg1.H - Zreg2.H }, { Zreg3.H - Zreg4.H }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/BFMLS--multiple-vectors---Multi-vector-BFloat16-fused-multiply-subtract-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmls_za16[_f16]_vg1x2

ISA classification: SME2 + FEAT_SME_F16F16

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmls_za16%5B_f16%5D_vg1x2

### Signature (source notation)

```c
void svmls_za16[_f16]_vg1x2(uint32_t slice, svfloat16x2_t zn, svfloat16x2_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector floating-point fused multiply-subtract

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Fused multiply-subtract

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
FMLS ZA.H[Wreg1, imm1, VGX2], { Zreg1.H, Zreg2.H }, { Zreg3.H, Zreg4.H }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/FMLS--multiple-vectors---Multi-vector-floating-point-fused-multiply-subtract-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmls_za16[_f16]_vg1x4

ISA classification: SME2 + FEAT_SME_F16F16

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmls_za16%5B_f16%5D_vg1x4

### Signature (source notation)

```c
void svmls_za16[_f16]_vg1x4(uint32_t slice, svfloat16x4_t zn, svfloat16x4_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector floating-point fused multiply-subtract

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Fused multiply-subtract

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
FMLS ZA.H[Wreg1, imm1, VGX4], { Zreg1.H - Zreg2.H }, { Zreg3.H - Zreg4.H }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/FMLS--multiple-vectors---Multi-vector-floating-point-fused-multiply-subtract-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmls_za32[_bf16]_vg2x1

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmls_za32%5B_bf16%5D_vg2x1

### Signature (source notation)

```c
void svmls_za32[_bf16]_vg2x1(uint32_t slice, svbfloat16_t zn, svbfloat16_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector BFloat16 multiply-subtract long by vector

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Fused multiply-subtract

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
BFMLSL ZA.S[Wreg1, imm1:<imm1+1>], Zreg1.H, Zreg2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/BFMLSL--multiple-and-single-vector---Multi-vector-BFloat16-multiply-subtract-long-by-vector-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmls_za32[_bf16]_vg2x2

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmls_za32%5B_bf16%5D_vg2x2

### Signature (source notation)

```c
void svmls_za32[_bf16]_vg2x2(uint32_t slice, svbfloat16x2_t zn, svbfloat16x2_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector BFloat16 multiply-subtract long

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Fused multiply-subtract

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
BFMLSL ZA.S[Wreg1, imm1:<imm1+1>, VGX2], { Zreg1.H, Zreg2.H }, { Zreg3.H, Zreg4.H }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/BFMLSL--multiple-vectors---Multi-vector-BFloat16-multiply-subtract-long-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmls_za32[_bf16]_vg2x4

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmls_za32%5B_bf16%5D_vg2x4

### Signature (source notation)

```c
void svmls_za32[_bf16]_vg2x4(uint32_t slice, svbfloat16x4_t zn, svbfloat16x4_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector BFloat16 multiply-subtract long

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Fused multiply-subtract

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
BFMLSL ZA.S[Wreg1, imm1:<imm1+1>, VGX4], { Zreg1.H - Zreg2.H }, { Zreg3.H - Zreg4.H }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/BFMLSL--multiple-vectors---Multi-vector-BFloat16-multiply-subtract-long-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmls_za32[_f16]_vg2x1

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmls_za32%5B_f16%5D_vg2x1

### Signature (source notation)

```c
void svmls_za32[_f16]_vg2x1(uint32_t slice, svfloat16_t zn, svfloat16_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector floating-point multiply-subtract long by vector

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Fused multiply-subtract

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
FMLSL ZA.S[Wreg1, imm1:<imm1+1>], Zreg1.H, Zreg2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/FMLSL--multiple-and-single-vector---Multi-vector-floating-point-multiply-subtract-long-by-vector-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmls_za32[_f16]_vg2x2

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmls_za32%5B_f16%5D_vg2x2

### Signature (source notation)

```c
void svmls_za32[_f16]_vg2x2(uint32_t slice, svfloat16x2_t zn, svfloat16x2_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector floating-point multiply-subtract long

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Fused multiply-subtract

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
FMLSL ZA.S[Wreg1, imm1:<imm1+1>, VGX2], { Zreg1.H, Zreg2.H }, { Zreg3.H, Zreg4.H }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/FMLSL--multiple-vectors---Multi-vector-floating-point-multiply-subtract-long-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmls_za32[_f16]_vg2x4

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmls_za32%5B_f16%5D_vg2x4

### Signature (source notation)

```c
void svmls_za32[_f16]_vg2x4(uint32_t slice, svfloat16x4_t zn, svfloat16x4_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector floating-point multiply-subtract long

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Fused multiply-subtract

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
FMLSL ZA.S[Wreg1, imm1:<imm1+1>, VGX4], { Zreg1.H - Zreg2.H }, { Zreg3.H - Zreg4.H }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/FMLSL--multiple-vectors---Multi-vector-floating-point-multiply-subtract-long-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmls_za32[_f32]_vg1x2

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmls_za32%5B_f32%5D_vg1x2

### Signature (source notation)

```c
void svmls_za32[_f32]_vg1x2(uint32_t slice, svfloat32x2_t zn, svfloat32x2_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector floating-point fused multiply-subtract

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Fused multiply-subtract

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
FMLS ZA.S[Wreg1, imm1, VGX2], { Zreg1.S, Zreg2.S }, { Zreg3.S, Zreg4.S }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/FMLS--multiple-vectors---Multi-vector-floating-point-fused-multiply-subtract-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmls_za32[_f32]_vg1x4

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmls_za32%5B_f32%5D_vg1x4

### Signature (source notation)

```c
void svmls_za32[_f32]_vg1x4(uint32_t slice, svfloat32x4_t zn, svfloat32x4_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector floating-point fused multiply-subtract

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Fused multiply-subtract

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
FMLS ZA.S[Wreg1, imm1, VGX4], { Zreg1.S - Zreg2.S }, { Zreg3.S - Zreg4.S }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/FMLS--multiple-vectors---Multi-vector-floating-point-fused-multiply-subtract-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmls_za32[_s16]_vg2x1

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmls_za32%5B_s16%5D_vg2x1

### Signature (source notation)

```c
void svmls_za32[_s16]_vg2x1(uint32_t slice, svint16_t zn, svint16_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector signed integer multiply-subtract long by vector

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Fused multiply-subtract

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
SMLSL ZA.S[Wreg1, imm1:<imm1+1>], Zreg1.H, Zreg2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SMLSL--multiple-and-single-vector---Multi-vector-signed-integer-multiply-subtract-long-by-vector-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmls_za32[_s16]_vg2x2

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmls_za32%5B_s16%5D_vg2x2

### Signature (source notation)

```c
void svmls_za32[_s16]_vg2x2(uint32_t slice, svint16x2_t zn, svint16x2_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector signed integer multiply-subtract long

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Fused multiply-subtract

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
SMLSL ZA.S[Wreg1, imm1:<imm1+1>, VGX2], { Zreg1.H, Zreg2.H }, { Zreg3.H, Zreg4.H }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SMLSL--multiple-vectors---Multi-vector-signed-integer-multiply-subtract-long-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmls_za32[_s16]_vg2x4

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmls_za32%5B_s16%5D_vg2x4

### Signature (source notation)

```c
void svmls_za32[_s16]_vg2x4(uint32_t slice, svint16x4_t zn, svint16x4_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector signed integer multiply-subtract long

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Fused multiply-subtract

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
SMLSL ZA.S[Wreg1, imm1:<imm1+1>, VGX4], { Zreg1.H - Zreg2.H }, { Zreg3.H - Zreg4.H }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SMLSL--multiple-vectors---Multi-vector-signed-integer-multiply-subtract-long-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmls_za32[_s8]_vg4x1

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmls_za32%5B_s8%5D_vg4x1

### Signature (source notation)

```c
void svmls_za32[_s8]_vg4x1(uint32_t slice, svint8_t zn, svint8_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector signed integer multiply-subtract long-long by vector

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Fused multiply-subtract

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
SMLSLL ZA.S[Wreg1, imm1:<imm1+3>], Zreg1.B, Zreg2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SMLSLL--multiple-and-single-vector---Multi-vector-signed-integer-multiply-subtract-long-long-by-vector-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmls_za32[_s8]_vg4x2

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmls_za32%5B_s8%5D_vg4x2

### Signature (source notation)

```c
void svmls_za32[_s8]_vg4x2(uint32_t slice, svint8x2_t zn, svint8x2_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector signed integer multiply-subtract long-long

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Fused multiply-subtract

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
SMLSLL ZA.S[Wreg1, imm1:<imm1+3>, VGX2], { Zreg1.B, Zreg2.B }, { Zreg3.B, Zreg4.B }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SMLSLL--multiple-vectors---Multi-vector-signed-integer-multiply-subtract-long-long-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmls_za32[_s8]_vg4x4

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmls_za32%5B_s8%5D_vg4x4

### Signature (source notation)

```c
void svmls_za32[_s8]_vg4x4(uint32_t slice, svint8x4_t zn, svint8x4_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector signed integer multiply-subtract long-long

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Fused multiply-subtract

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
SMLSLL ZA.S[Wreg1, imm1:<imm1+3>, VGX4], { Zreg1.B - Zreg2.B }, { Zreg3.B - Zreg4.B }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SMLSLL--multiple-vectors---Multi-vector-signed-integer-multiply-subtract-long-long-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmls_za32[_u16]_vg2x1

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmls_za32%5B_u16%5D_vg2x1

### Signature (source notation)

```c
void svmls_za32[_u16]_vg2x1(uint32_t slice, svuint16_t zn, svuint16_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector unsigned integer multiply-subtract long by vector

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Fused multiply-subtract

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
UMLSL ZA.S[Wreg1, imm1:<imm1+1>], Zreg1.H, Zreg2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/UMLSL--multiple-and-single-vector---Multi-vector-unsigned-integer-multiply-subtract-long-by-vector-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmls_za32[_u16]_vg2x2

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmls_za32%5B_u16%5D_vg2x2

### Signature (source notation)

```c
void svmls_za32[_u16]_vg2x2(uint32_t slice, svuint16x2_t zn, svuint16x2_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector unsigned integer multiply-subtract long

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Fused multiply-subtract

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
UMLSL ZA.S[Wreg1, imm1:<imm1+1>, VGX2], { Zreg1.H, Zreg2.H }, { Zreg3.H, Zreg4.H }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/UMLSL--multiple-vectors---Multi-vector-unsigned-integer-multiply-subtract-long-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmls_za32[_u16]_vg2x4

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmls_za32%5B_u16%5D_vg2x4

### Signature (source notation)

```c
void svmls_za32[_u16]_vg2x4(uint32_t slice, svuint16x4_t zn, svuint16x4_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector unsigned integer multiply-subtract long

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Fused multiply-subtract

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
UMLSL ZA.S[Wreg1, imm1:<imm1+1>, VGX4], { Zreg1.H - Zreg2.H }, { Zreg3.H - Zreg4.H }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/UMLSL--multiple-vectors---Multi-vector-unsigned-integer-multiply-subtract-long-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmls_za32[_u8]_vg4x1

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmls_za32%5B_u8%5D_vg4x1

### Signature (source notation)

```c
void svmls_za32[_u8]_vg4x1(uint32_t slice, svuint8_t zn, svuint8_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector unsigned integer multiply-subtract long-long by vector

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Fused multiply-subtract

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
UMLSLL ZA.S[Wreg1, imm1:<imm1+3>], Zreg1.B, Zreg2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/UMLSLL--multiple-and-single-vector---Multi-vector-unsigned-integer-multiply-subtract-long-long-by-vector-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmls_za32[_u8]_vg4x2

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmls_za32%5B_u8%5D_vg4x2

### Signature (source notation)

```c
void svmls_za32[_u8]_vg4x2(uint32_t slice, svuint8x2_t zn, svuint8x2_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector unsigned integer multiply-subtract long-long

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Fused multiply-subtract

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
UMLSLL ZA.S[Wreg1, imm1:<imm1+3>, VGX2], { Zreg1.B, Zreg2.B }, { Zreg3.B, Zreg4.B }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/UMLSLL--multiple-vectors---Multi-vector-unsigned-integer-multiply-subtract-long-long-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmls_za32[_u8]_vg4x4

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmls_za32%5B_u8%5D_vg4x4

### Signature (source notation)

```c
void svmls_za32[_u8]_vg4x4(uint32_t slice, svuint8x4_t zn, svuint8x4_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector unsigned integer multiply-subtract long-long

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Fused multiply-subtract

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
UMLSLL ZA.S[Wreg1, imm1:<imm1+3>, VGX4], { Zreg1.B - Zreg2.B }, { Zreg3.B - Zreg4.B }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/UMLSLL--multiple-vectors---Multi-vector-unsigned-integer-multiply-subtract-long-long-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmls_za64[_f64]_vg1x2

ISA classification: SME2 + FEAT_SME_F64F64

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmls_za64%5B_f64%5D_vg1x2

### Signature (source notation)

```c
void svmls_za64[_f64]_vg1x2(uint32_t slice, svfloat64x2_t zn, svfloat64x2_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector floating-point fused multiply-subtract

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Fused multiply-subtract

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
FMLS ZA.D[Wreg1, imm1, VGX2], { Zreg1.D, Zreg2.D }, { Zreg3.D, Zreg4.D }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/FMLS--multiple-vectors---Multi-vector-floating-point-fused-multiply-subtract-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmls_za64[_f64]_vg1x4

ISA classification: SME2 + FEAT_SME_F64F64

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmls_za64%5B_f64%5D_vg1x4

### Signature (source notation)

```c
void svmls_za64[_f64]_vg1x4(uint32_t slice, svfloat64x4_t zn, svfloat64x4_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector floating-point fused multiply-subtract

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Fused multiply-subtract

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
FMLS ZA.D[Wreg1, imm1, VGX4], { Zreg1.D - Zreg2.D }, { Zreg3.D - Zreg4.D }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/FMLS--multiple-vectors---Multi-vector-floating-point-fused-multiply-subtract-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmls_za64[_s16]_vg4x1

ISA classification: SME2 + FEAT_SME_I16I64

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmls_za64%5B_s16%5D_vg4x1

### Signature (source notation)

```c
void svmls_za64[_s16]_vg4x1(uint32_t slice, svint16_t zn, svint16_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector signed integer multiply-subtract long-long by vector

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Fused multiply-subtract

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
SMLSLL ZA.D[Wreg1, imm1:<imm1+3>], Zreg1.H, Zreg2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SMLSLL--multiple-and-single-vector---Multi-vector-signed-integer-multiply-subtract-long-long-by-vector-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmls_za64[_s16]_vg4x2

ISA classification: SME2 + FEAT_SME_I16I64

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmls_za64%5B_s16%5D_vg4x2

### Signature (source notation)

```c
void svmls_za64[_s16]_vg4x2(uint32_t slice, svint16x2_t zn, svint16x2_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector signed integer multiply-subtract long-long

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Fused multiply-subtract

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
SMLSLL ZA.D[Wreg1, imm1:<imm1+3>, VGX2], { Zreg1.H, Zreg2.H }, { Zreg3.H, Zreg4.H }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SMLSLL--multiple-vectors---Multi-vector-signed-integer-multiply-subtract-long-long-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmls_za64[_s16]_vg4x4

ISA classification: SME2 + FEAT_SME_I16I64

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmls_za64%5B_s16%5D_vg4x4

### Signature (source notation)

```c
void svmls_za64[_s16]_vg4x4(uint32_t slice, svint16x4_t zn, svint16x4_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector signed integer multiply-subtract long-long

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Fused multiply-subtract

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
SMLSLL ZA.D[Wreg1, imm1:<imm1+3>, VGX4], { Zreg1.H - Zreg2.H }, { Zreg3.H - Zreg4.H }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SMLSLL--multiple-vectors---Multi-vector-signed-integer-multiply-subtract-long-long-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmls_za64[_u16]_vg4x1

ISA classification: SME2 + FEAT_SME_I16I64

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmls_za64%5B_u16%5D_vg4x1

### Signature (source notation)

```c
void svmls_za64[_u16]_vg4x1(uint32_t slice, svuint16_t zn, svuint16_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector unsigned integer multiply-subtract long-long by vector

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Fused multiply-subtract

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
UMLSLL ZA.D[Wreg1, imm1:<imm1+3>], Zreg1.H, Zreg2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/UMLSLL--multiple-and-single-vector---Multi-vector-unsigned-integer-multiply-subtract-long-long-by-vector-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmls_za64[_u16]_vg4x2

ISA classification: SME2 + FEAT_SME_I16I64

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmls_za64%5B_u16%5D_vg4x2

### Signature (source notation)

```c
void svmls_za64[_u16]_vg4x2(uint32_t slice, svuint16x2_t zn, svuint16x2_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector unsigned integer multiply-subtract long-long

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Fused multiply-subtract

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
UMLSLL ZA.D[Wreg1, imm1:<imm1+3>, VGX2], { Zreg1.H, Zreg2.H }, { Zreg3.H, Zreg4.H }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/UMLSLL--multiple-vectors---Multi-vector-unsigned-integer-multiply-subtract-long-long-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmls_za64[_u16]_vg4x4

ISA classification: SME2 + FEAT_SME_I16I64

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmls_za64%5B_u16%5D_vg4x4

### Signature (source notation)

```c
void svmls_za64[_u16]_vg4x4(uint32_t slice, svuint16x4_t zn, svuint16x4_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector unsigned integer multiply-subtract long-long

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Fused multiply-subtract

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
UMLSLL ZA.D[Wreg1, imm1:<imm1+3>, VGX4], { Zreg1.H - Zreg2.H }, { Zreg3.H - Zreg4.H }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/UMLSLL--multiple-vectors---Multi-vector-unsigned-integer-multiply-subtract-long-long-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

