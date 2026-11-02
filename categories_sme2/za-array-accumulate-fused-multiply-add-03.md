# SME2 / ZA array / Accumulate / Fused multiply-add — Part 3

## svmla_za64[_s16]_vg4x4

ISA classification: SME2 + FEAT_SME_I16I64

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmla_za64%5B_s16%5D_vg4x4

### Signature (source notation)

```c
void svmla_za64[_s16]_vg4x4(uint32_t slice, svint16x4_t zn, svint16x4_t zm)
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
SMLALL ZA.D[Wreg1, imm1:<imm1+3>, VGX4], { Zreg1.H - Zreg2.H }, { Zreg3.H - Zreg4.H }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SMLALL--multiple-vectors---Multi-vector-signed-integer-multiply-add-long-long-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmla_za64[_u16]_vg4x1

ISA classification: SME2 + FEAT_SME_I16I64

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmla_za64%5B_u16%5D_vg4x1

### Signature (source notation)

```c
void svmla_za64[_u16]_vg4x1(uint32_t slice, svuint16_t zn, svuint16_t zm)
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
UMLALL ZA.D[Wreg1, imm1:<imm1+3>], Zreg1.H, Zreg2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/UMLALL--multiple-and-single-vector---Multi-vector-unsigned-integer-multiply-add-long-long-by-vector-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmla_za64[_u16]_vg4x2

ISA classification: SME2 + FEAT_SME_I16I64

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmla_za64%5B_u16%5D_vg4x2

### Signature (source notation)

```c
void svmla_za64[_u16]_vg4x2(uint32_t slice, svuint16x2_t zn, svuint16x2_t zm)
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
UMLALL ZA.D[Wreg1, imm1:<imm1+3>, VGX2], { Zreg1.H, Zreg2.H }, { Zreg3.H, Zreg4.H }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/UMLALL--multiple-vectors---Multi-vector-unsigned-integer-multiply-add-long-long-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmla_za64[_u16]_vg4x4

ISA classification: SME2 + FEAT_SME_I16I64

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmla_za64%5B_u16%5D_vg4x4

### Signature (source notation)

```c
void svmla_za64[_u16]_vg4x4(uint32_t slice, svuint16x4_t zn, svuint16x4_t zm)
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
UMLALL ZA.D[Wreg1, imm1:<imm1+3>, VGX4], { Zreg1.H - Zreg2.H }, { Zreg3.H - Zreg4.H }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/UMLALL--multiple-vectors---Multi-vector-unsigned-integer-multiply-add-long-long-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svsumla[_single]_za32[_s8]_vg4x2

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsumla%5B_single%5D_za32%5B_s8%5D_vg4x2

### Signature (source notation)

```c
void svsumla[_single]_za32[_s8]_vg4x2(uint32_t slice, svint8x2_t zn, svuint8_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector signed by unsigned integer multiply-add long-long by vector

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
SUMLALL ZA.S[Wreg1, imm1:<imm1+3>, VGX2], { Zreg1.B, Zreg2.B }, Zreg3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SUMLALL--multiple-and-single-vector---Multi-vector-signed-by-unsigned-integer-multiply-add-long-long-by-vector-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svsumla[_single]_za32[_s8]_vg4x4

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsumla%5B_single%5D_za32%5B_s8%5D_vg4x4

### Signature (source notation)

```c
void svsumla[_single]_za32[_s8]_vg4x4(uint32_t slice, svint8x4_t zn, svuint8_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector signed by unsigned integer multiply-add long-long by vector

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
SUMLALL ZA.S[Wreg1, imm1:<imm1+3>, VGX4], { Zreg1.B - Zreg2.B }, Zreg3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SUMLALL--multiple-and-single-vector---Multi-vector-signed-by-unsigned-integer-multiply-add-long-long-by-vector-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svsumla_lane_za32[_s8]_vg4x1

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsumla_lane_za32%5B_s8%5D_vg4x1

### Signature (source notation)

```c
void svsumla_lane_za32[_s8]_vg4x1(uint32_t slice, svint8_t zn, svuint8_t zm, uint64_t imm_idx)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector signed by unsigned integer multiply-add long-long by indexed element

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
SUMLALL ZA.S[Wreg1, imm2:<imm2+3>], Zreg1.B, Zreg2.B[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SUMLALL--multiple-and-indexed-vector---Multi-vector-signed-by-unsigned-integer-multiply-add-long-long-by-indexed-element-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svsumla_lane_za32[_s8]_vg4x2

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsumla_lane_za32%5B_s8%5D_vg4x2

### Signature (source notation)

```c
void svsumla_lane_za32[_s8]_vg4x2(uint32_t slice, svint8x2_t zn, svuint8_t zm, uint64_t imm_idx)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector signed by unsigned integer multiply-add long-long by indexed element

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
SUMLALL ZA.S[Wreg1, imm2:<imm2+3>, VGX2], { Zreg1.B, Zreg2.B }, Zreg3.B[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SUMLALL--multiple-and-indexed-vector---Multi-vector-signed-by-unsigned-integer-multiply-add-long-long-by-indexed-element-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svsumla_lane_za32[_s8]_vg4x4

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsumla_lane_za32%5B_s8%5D_vg4x4

### Signature (source notation)

```c
void svsumla_lane_za32[_s8]_vg4x4(uint32_t slice, svint8x4_t zn, svuint8_t zm, uint64_t imm_idx)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector signed by unsigned integer multiply-add long-long by indexed element

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
SUMLALL ZA.S[Wreg1, imm2:<imm2+3>, VGX4], { Zreg1.B - Zreg2.B }, Zreg3.B[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SUMLALL--multiple-and-indexed-vector---Multi-vector-signed-by-unsigned-integer-multiply-add-long-long-by-indexed-element-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svsumla_za32[_s8]_vg4x1

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsumla_za32%5B_s8%5D_vg4x1

### Signature (source notation)

```c
void svsumla_za32[_s8]_vg4x1(uint32_t slice, svint8_t zn, svuint8_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector unsigned by signed integer multiply-add long-long by vector

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
USMLALL ZA.S[Wreg1, imm1:<imm1+3>], Zreg1.B, Zreg2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/USMLALL--multiple-and-single-vector---Multi-vector-unsigned-by-signed-integer-multiply-add-long-long-by-vector-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svsumla_za32[_s8]_vg4x2

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsumla_za32%5B_s8%5D_vg4x2

### Signature (source notation)

```c
void svsumla_za32[_s8]_vg4x2(uint32_t slice, svint8x2_t zn, svuint8x2_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector unsigned by signed integer multiply-add long-long

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
USMLALL ZA.S[Wreg1, imm1:<imm1+3>, VGX2], { Zreg1.B, Zreg2.B }, { Zreg3.B, Zreg4.B }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/USMLALL--multiple-vectors---Multi-vector-unsigned-by-signed-integer-multiply-add-long-long-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svsumla_za32[_s8]_vg4x4

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsumla_za32%5B_s8%5D_vg4x4

### Signature (source notation)

```c
void svsumla_za32[_s8]_vg4x4(uint32_t slice, svint8x4_t zn, svuint8x4_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector unsigned by signed integer multiply-add long-long

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
USMLALL ZA.S[Wreg1, imm1:<imm1+3>, VGX4], { Zreg1.B - Zreg2.B }, { Zreg3.B - Zreg4.B }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/USMLALL--multiple-vectors---Multi-vector-unsigned-by-signed-integer-multiply-add-long-long-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svusmla[_single]_za32[_u8]_vg4x2

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svusmla%5B_single%5D_za32%5B_u8%5D_vg4x2

### Signature (source notation)

```c
void svusmla[_single]_za32[_u8]_vg4x2(uint32_t slice, svuint8x2_t zn, svint8_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector unsigned by signed integer multiply-add long-long by vector

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
USMLALL ZA.S[Wreg1, imm1:<imm1+3>, VGX2], { Zreg1.B, Zreg2.B }, Zreg3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/USMLALL--multiple-and-single-vector---Multi-vector-unsigned-by-signed-integer-multiply-add-long-long-by-vector-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svusmla[_single]_za32[_u8]_vg4x4

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svusmla%5B_single%5D_za32%5B_u8%5D_vg4x4

### Signature (source notation)

```c
void svusmla[_single]_za32[_u8]_vg4x4(uint32_t slice, svuint8x4_t zn, svint8_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector unsigned by signed integer multiply-add long-long by vector

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
USMLALL ZA.S[Wreg1, imm1:<imm1+3>, VGX4], { Zreg1.B - Zreg2.B }, Zreg3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/USMLALL--multiple-and-single-vector---Multi-vector-unsigned-by-signed-integer-multiply-add-long-long-by-vector-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svusmla_lane_za32[_u8]_vg4x1

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svusmla_lane_za32%5B_u8%5D_vg4x1

### Signature (source notation)

```c
void svusmla_lane_za32[_u8]_vg4x1(uint32_t slice, svuint8_t zn, svint8_t zm, uint64_t imm_idx)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector unsigned by signed integer multiply-add long-long by indexed element

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
USMLALL ZA.S[Wreg1, imm2:<imm2+3>], Zreg1.B, Zreg2.B[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/USMLALL--multiple-and-indexed-vector---Multi-vector-unsigned-by-signed-integer-multiply-add-long-long-by-indexed-element-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svusmla_lane_za32[_u8]_vg4x2

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svusmla_lane_za32%5B_u8%5D_vg4x2

### Signature (source notation)

```c
void svusmla_lane_za32[_u8]_vg4x2(uint32_t slice, svuint8x2_t zn, svint8_t zm, uint64_t imm_idx)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector unsigned by signed integer multiply-add long-long by indexed element

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
USMLALL ZA.S[Wreg1, imm2:<imm2+3>, VGX2], { Zreg1.B, Zreg2.B }, Zreg3.B[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/USMLALL--multiple-and-indexed-vector---Multi-vector-unsigned-by-signed-integer-multiply-add-long-long-by-indexed-element-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svusmla_lane_za32[_u8]_vg4x4

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svusmla_lane_za32%5B_u8%5D_vg4x4

### Signature (source notation)

```c
void svusmla_lane_za32[_u8]_vg4x4(uint32_t slice, svuint8x4_t zn, svint8_t zm, uint64_t imm_idx)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector unsigned by signed integer multiply-add long-long by indexed element

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
USMLALL ZA.S[Wreg1, imm2:<imm2+3>, VGX4], { Zreg1.B - Zreg2.B }, Zreg3.B[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/USMLALL--multiple-and-indexed-vector---Multi-vector-unsigned-by-signed-integer-multiply-add-long-long-by-indexed-element-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svusmla_za32[_u8]_vg4x1

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svusmla_za32%5B_u8%5D_vg4x1

### Signature (source notation)

```c
void svusmla_za32[_u8]_vg4x1(uint32_t slice, svuint8_t zn, svint8_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector unsigned by signed integer multiply-add long-long by vector

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
USMLALL ZA.S[Wreg1, imm1:<imm1+3>], Zreg1.B, Zreg2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/USMLALL--multiple-and-single-vector---Multi-vector-unsigned-by-signed-integer-multiply-add-long-long-by-vector-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svusmla_za32[_u8]_vg4x2

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svusmla_za32%5B_u8%5D_vg4x2

### Signature (source notation)

```c
void svusmla_za32[_u8]_vg4x2(uint32_t slice, svuint8x2_t zn, svint8x2_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector unsigned by signed integer multiply-add long-long

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
USMLALL ZA.S[Wreg1, imm1:<imm1+3>, VGX2], { Zreg1.B, Zreg2.B }, { Zreg3.B, Zreg4.B }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/USMLALL--multiple-vectors---Multi-vector-unsigned-by-signed-integer-multiply-add-long-long-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svusmla_za32[_u8]_vg4x4

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svusmla_za32%5B_u8%5D_vg4x4

### Signature (source notation)

```c
void svusmla_za32[_u8]_vg4x4(uint32_t slice, svuint8x4_t zn, svint8x4_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector unsigned by signed integer multiply-add long-long

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
USMLALL ZA.S[Wreg1, imm1:<imm1+3>, VGX4], { Zreg1.B - Zreg2.B }, { Zreg3.B - Zreg4.B }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/USMLALL--multiple-vectors---Multi-vector-unsigned-by-signed-integer-multiply-add-long-long-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

