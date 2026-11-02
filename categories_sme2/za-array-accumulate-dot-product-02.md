# SME2 / ZA array / Accumulate / Dot product — Part 2

## svdot_za32[_s8]_vg1x2

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdot_za32%5B_s8%5D_vg1x2

### Signature (source notation)

```c
void svdot_za32[_s8]_vg1x2(uint32_t slice, svint8x2_t zn, svint8x2_t zm)
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
SDOT ZA.S[Wreg1, imm1, VGX2], { Zreg1.B, Zreg2.B }, { Zreg3.B, Zreg4.B }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SDOT--4-way--multiple-vectors---Multi-vector-signed-integer-dot-product-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svdot_za32[_s8]_vg1x4

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdot_za32%5B_s8%5D_vg1x4

### Signature (source notation)

```c
void svdot_za32[_s8]_vg1x4(uint32_t slice, svint8x4_t zn, svint8x4_t zm)
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
SDOT ZA.S[Wreg1, imm1, VGX4], { Zreg1.B - Zreg2.B }, { Zreg3.B - Zreg4.B }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SDOT--4-way--multiple-vectors---Multi-vector-signed-integer-dot-product-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svdot_za32[_u16]_vg1x2

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdot_za32%5B_u16%5D_vg1x2

### Signature (source notation)

```c
void svdot_za32[_u16]_vg1x2(uint32_t slice, svuint16x2_t zn, svuint16x2_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector unsigned integer dot-product

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
UDOT ZA.S[Wreg1, imm1, VGX2], { Zreg1.H, Zreg2.H }, { Zreg3.H, Zreg4.H }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/UDOT--2-way--multiple-vectors---Multi-vector-unsigned-integer-dot-product-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svdot_za32[_u16]_vg1x4

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdot_za32%5B_u16%5D_vg1x4

### Signature (source notation)

```c
void svdot_za32[_u16]_vg1x4(uint32_t slice, svuint16x4_t zn, svuint16x4_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector unsigned integer dot-product

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
UDOT ZA.S[Wreg1, imm1, VGX4], { Zreg1.H - Zreg2.H }, { Zreg3.H - Zreg4.H }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/UDOT--2-way--multiple-vectors---Multi-vector-unsigned-integer-dot-product-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svdot_za32[_u8]_vg1x2

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdot_za32%5B_u8%5D_vg1x2

### Signature (source notation)

```c
void svdot_za32[_u8]_vg1x2(uint32_t slice, svuint8x2_t zn, svuint8x2_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector unsigned integer dot-product

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
UDOT ZA.S[Wreg1, imm1, VGX2], { Zreg1.B, Zreg2.B }, { Zreg3.B, Zreg4.B }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/UDOT--4-way--multiple-vectors---Multi-vector-unsigned-integer-dot-product-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svdot_za32[_u8]_vg1x4

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdot_za32%5B_u8%5D_vg1x4

### Signature (source notation)

```c
void svdot_za32[_u8]_vg1x4(uint32_t slice, svuint8x4_t zn, svuint8x4_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector unsigned integer dot-product

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
UDOT ZA.S[Wreg1, imm1, VGX4], { Zreg1.B - Zreg2.B }, { Zreg3.B - Zreg4.B }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/UDOT--4-way--multiple-vectors---Multi-vector-unsigned-integer-dot-product-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svdot_za64[_s16]_vg1x2

ISA classification: SME2 + FEAT_SME_I16I64

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdot_za64%5B_s16%5D_vg1x2

### Signature (source notation)

```c
void svdot_za64[_s16]_vg1x2(uint32_t slice, svint16x2_t zn, svint16x2_t zm)
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
SDOT ZA.D[Wreg1, imm1, VGX2], { Zreg1.H, Zreg2.H }, { Zreg3.H, Zreg4.H }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SDOT--4-way--multiple-vectors---Multi-vector-signed-integer-dot-product-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svdot_za64[_s16]_vg1x4

ISA classification: SME2 + FEAT_SME_I16I64

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdot_za64%5B_s16%5D_vg1x4

### Signature (source notation)

```c
void svdot_za64[_s16]_vg1x4(uint32_t slice, svint16x4_t zn, svint16x4_t zm)
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
SDOT ZA.D[Wreg1, imm1, VGX4], { Zreg1.H - Zreg2.H }, { Zreg3.H - Zreg4.H }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SDOT--4-way--multiple-vectors---Multi-vector-signed-integer-dot-product-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svdot_za64[_u16]_vg1x2

ISA classification: SME2 + FEAT_SME_I16I64

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdot_za64%5B_u16%5D_vg1x2

### Signature (source notation)

```c
void svdot_za64[_u16]_vg1x2(uint32_t slice, svuint16x2_t zn, svuint16x2_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector unsigned integer dot-product

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
UDOT ZA.D[Wreg1, imm1, VGX2], { Zreg1.H, Zreg2.H }, { Zreg3.H, Zreg4.H }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/UDOT--4-way--multiple-vectors---Multi-vector-unsigned-integer-dot-product-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svdot_za64[_u16]_vg1x4

ISA classification: SME2 + FEAT_SME_I16I64

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdot_za64%5B_u16%5D_vg1x4

### Signature (source notation)

```c
void svdot_za64[_u16]_vg1x4(uint32_t slice, svuint16x4_t zn, svuint16x4_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector unsigned integer dot-product

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
UDOT ZA.D[Wreg1, imm1, VGX4], { Zreg1.H - Zreg2.H }, { Zreg3.H - Zreg4.H }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/UDOT--4-way--multiple-vectors---Multi-vector-unsigned-integer-dot-product-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svsudot[_single]_za32[_s8]_vg1x2

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsudot%5B_single%5D_za32%5B_s8%5D_vg1x2

### Signature (source notation)

```c
void svsudot[_single]_za32[_s8]_vg1x2(uint32_t slice, svint8x2_t zn, svuint8_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector signed by unsigned integer dot-product by vector

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
SUDOT ZA.S[Wreg1, imm1, VGX2], { Zreg1.B, Zreg2.B }, Zreg3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SUDOT--4-way--multiple-and-single-vector---Multi-vector-signed-by-unsigned-integer-dot-product-by-vector-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svsudot[_single]_za32[_s8]_vg1x4

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsudot%5B_single%5D_za32%5B_s8%5D_vg1x4

### Signature (source notation)

```c
void svsudot[_single]_za32[_s8]_vg1x4(uint32_t slice, svint8x4_t zn, svuint8_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector signed by unsigned integer dot-product by vector

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
SUDOT ZA.S[Wreg1, imm1, VGX4], { Zreg1.B - Zreg2.B }, Zreg3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SUDOT--4-way--multiple-and-single-vector---Multi-vector-signed-by-unsigned-integer-dot-product-by-vector-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svsudot_lane_za32[_s8]_vg1x2

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsudot_lane_za32%5B_s8%5D_vg1x2

### Signature (source notation)

```c
void svsudot_lane_za32[_s8]_vg1x2(uint32_t slice, svint8x2_t zn, svuint8_t zm, uint64_t imm_idx)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector signed by unsigned integer dot-product by indexed elements

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
SUDOT ZA.S[Wreg1, imm2, VGX2], { Zreg1.B, Zreg2.B }, Zreg3.B[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SUDOT--4-way--multiple-and-indexed-vector---Multi-vector-signed-by-unsigned-integer-dot-product-by-indexed-elements-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svsudot_lane_za32[_s8]_vg1x4

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsudot_lane_za32%5B_s8%5D_vg1x4

### Signature (source notation)

```c
void svsudot_lane_za32[_s8]_vg1x4(uint32_t slice, svint8x4_t zn, svuint8_t zm, uint64_t imm_idx)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector signed by unsigned integer dot-product by indexed elements

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
SUDOT ZA.S[Wreg1, imm2, VGX4], { Zreg1.B - Zreg2.B }, Zreg3.B[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SUDOT--4-way--multiple-and-indexed-vector---Multi-vector-signed-by-unsigned-integer-dot-product-by-indexed-elements-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svsudot_za32[_s8]_vg1x2

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsudot_za32%5B_s8%5D_vg1x2

### Signature (source notation)

```c
void svsudot_za32[_s8]_vg1x2(uint32_t slice, svint8x2_t zn, svuint8x2_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector unsigned by signed integer dot-product

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
USDOT ZA.S[Wreg1, imm1, VGX2], { Zreg1.B, Zreg2.B }, { Zreg3.B, Zreg4.B }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/USDOT--4-way--multiple-vectors---Multi-vector-unsigned-by-signed-integer-dot-product-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svsudot_za32[_s8]_vg1x4

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsudot_za32%5B_s8%5D_vg1x4

### Signature (source notation)

```c
void svsudot_za32[_s8]_vg1x4(uint32_t slice, svint8x4_t zn, svuint8x4_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector unsigned by signed integer dot-product

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
USDOT ZA.S[Wreg1, imm1, VGX4], { Zreg1.B - Zreg2.B }, { Zreg3.B - Zreg4.B }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/USDOT--4-way--multiple-vectors---Multi-vector-unsigned-by-signed-integer-dot-product-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svusdot[_single]_za32[_u8]_vg1x2

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svusdot%5B_single%5D_za32%5B_u8%5D_vg1x2

### Signature (source notation)

```c
void svusdot[_single]_za32[_u8]_vg1x2(uint32_t slice, svuint8x2_t zn, svint8_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector unsigned by signed integer dot-product by vector

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
USDOT ZA.S[Wreg1, imm1, VGX2], { Zreg1.B, Zreg2.B }, Zreg3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/USDOT--4-way--multiple-and-single-vector---Multi-vector-unsigned-by-signed-integer-dot-product-by-vector-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svusdot[_single]_za32[_u8]_vg1x4

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svusdot%5B_single%5D_za32%5B_u8%5D_vg1x4

### Signature (source notation)

```c
void svusdot[_single]_za32[_u8]_vg1x4(uint32_t slice, svuint8x4_t zn, svint8_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector unsigned by signed integer dot-product by vector

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
USDOT ZA.S[Wreg1, imm1, VGX4], { Zreg1.B - Zreg2.B }, Zreg3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/USDOT--4-way--multiple-and-single-vector---Multi-vector-unsigned-by-signed-integer-dot-product-by-vector-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svusdot_lane_za32[_u8]_vg1x2

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svusdot_lane_za32%5B_u8%5D_vg1x2

### Signature (source notation)

```c
void svusdot_lane_za32[_u8]_vg1x2(uint32_t slice, svuint8x2_t zn, svint8_t zm, uint64_t imm_idx)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector unsigned by signed integer dot-product by indexed element

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
USDOT ZA.S[Wreg1, imm2, VGX2], { Zreg1.B, Zreg2.B }, Zreg3.B[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/USDOT--4-way--multiple-and-indexed-vector---Multi-vector-unsigned-by-signed-integer-dot-product-by-indexed-element-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svusdot_lane_za32[_u8]_vg1x4

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svusdot_lane_za32%5B_u8%5D_vg1x4

### Signature (source notation)

```c
void svusdot_lane_za32[_u8]_vg1x4(uint32_t slice, svuint8x4_t zn, svint8_t zm, uint64_t imm_idx)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector unsigned by signed integer dot-product by indexed element

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
USDOT ZA.S[Wreg1, imm2, VGX4], { Zreg1.B - Zreg2.B }, Zreg3.B[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/USDOT--4-way--multiple-and-indexed-vector---Multi-vector-unsigned-by-signed-integer-dot-product-by-indexed-element-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svusdot_za32[_u8]_vg1x2

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svusdot_za32%5B_u8%5D_vg1x2

### Signature (source notation)

```c
void svusdot_za32[_u8]_vg1x2(uint32_t slice, svuint8x2_t zn, svint8x2_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector unsigned by signed integer dot-product

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
USDOT ZA.S[Wreg1, imm1, VGX2], { Zreg1.B, Zreg2.B }, { Zreg3.B, Zreg4.B }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/USDOT--4-way--multiple-vectors---Multi-vector-unsigned-by-signed-integer-dot-product-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svusdot_za32[_u8]_vg1x4

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svusdot_za32%5B_u8%5D_vg1x4

### Signature (source notation)

```c
void svusdot_za32[_u8]_vg1x4(uint32_t slice, svuint8x4_t zn, svint8x4_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector unsigned by signed integer dot-product

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
USDOT ZA.S[Wreg1, imm1, VGX4], { Zreg1.B - Zreg2.B }, { Zreg3.B - Zreg4.B }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/USDOT--4-way--multiple-vectors---Multi-vector-unsigned-by-signed-integer-dot-product-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svvdot_lane_za16[_mf8]_vg1x2_fpm

ISA classification: SME2 + FEAT_SME_F8F16

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svvdot_lane_za16%5B_mf8%5D_vg1x2_fpm

### Signature (source notation)

```c
void svvdot_lane_za16[_mf8]_vg1x2_fpm(uint32_t slice, svmfloat8x2_t zn, svmfloat8_t zm, uint64_t imm_idx, fpm_t fpm)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector 8-bit floating-point vertical dot product by indexed element to half-precision

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
FVDOT ZA.H[Wreg2, imm2, VGX2], { Zreg1.B, Zreg2.B }, Zreg3.B[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/FVDOT--FP8-to-FP16---Multi-vector-8-bit-floating-point-vertical-dot-product-by-indexed-element-to-half-precision-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svvdotb_lane_za32[_mf8]_vg1x4_fpm

ISA classification: SME2 + FEAT_SME_F8F32

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svvdotb_lane_za32%5B_mf8%5D_vg1x4_fpm

### Signature (source notation)

```c
void svvdotb_lane_za32[_mf8]_vg1x4_fpm(uint32_t slice, svmfloat8x2_t zn, svmfloat8_t zm, uint64_t imm_idx, fpm_t fpm)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector 8-bit floating-point vertical dot product by indexed element to single-precision (bottom)

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
FVDOTB ZA.S[Wreg2, imm2, VGX4], { Zreg1.B, Zreg2.B }, Zreg3.B[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/FVDOTB--Multi-vector-8-bit-floating-point-vertical-dot-product-by-indexed-element-to-single-precision--bottom--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svvdott_lane_za32[_mf8]_vg1x4_fpm

ISA classification: SME2 + FEAT_SME_F8F32

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svvdott_lane_za32%5B_mf8%5D_vg1x4_fpm

### Signature (source notation)

```c
void svvdott_lane_za32[_mf8]_vg1x4_fpm(uint32_t slice, svmfloat8x2_t zn, svmfloat8_t zm, uint64_t imm_idx, fpm_t fpm)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector 8-bit floating-point vertical dot product by indexed element to single-precision (top)

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
FVDOTT ZA.S[Wreg2, imm2, VGX4], { Zreg1.B, Zreg2.B }, Zreg3.B[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/FVDOTT--Multi-vector-8-bit-floating-point-vertical-dot-product-by-indexed-element-to-single-precision--top--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

