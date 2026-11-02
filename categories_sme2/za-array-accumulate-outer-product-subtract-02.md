# SME2 / ZA array / Accumulate / Outer product subtract — Part 2

## svmop4s[_2x2]_za16[_bf16_bf16]

ISA classification: SME2 + FEAT_SME_MOP4, FEAT_SME_B16B16

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmop4s%5B_2x2%5D_za16%5B_bf16_bf16%5D

### Signature (source notation)

```c
void svmop4s[_2x2]_za16[_bf16_bf16](uint64_t tile, svbfloat16x2_t zn, svbfloat16x2_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

BFloat16 quarter-tile outer product, subtracting

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Outer product subtract

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2,FEAT_SME_MOP4,FEAT_SME_B16B16
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
  "tile": {
    "ZA array tile": "ZA0.H"
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
BFMOP4S ZA0.H, { Zreg1.H, Zreg2.H }, { Zreg3.H, Zreg4.H }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/BFMOP4S--non-widening---BFloat16-quarter-tile-outer-product--subtracting-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmop4s[_2x2]_za16[_f16_f16]

ISA classification: SME2 + FEAT_SME_MOP4, FEAT_SME_F16F16

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmop4s%5B_2x2%5D_za16%5B_f16_f16%5D

### Signature (source notation)

```c
void svmop4s[_2x2]_za16[_f16_f16](uint64_t tile, svfloat16x2_t zn, svfloat16x2_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Floating-point quarter-tile outer product, subtracting

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Outer product subtract

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2,FEAT_SME_MOP4,FEAT_SME_F16F16
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
  "tile": {
    "ZA array tile": "ZA0.H"
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
FMOP4S ZA0.H, { Zreg1.H, Zreg2.H }, { Zreg3.H, Zreg4.H }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/FMOP4S--non-widening---Floating-point-quarter-tile-outer-product--subtracting-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmop4s[_2x2]_za32[_bf16_bf16]

ISA classification: SME2 + FEAT_SME_MOP4

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmop4s%5B_2x2%5D_za32%5B_bf16_bf16%5D

### Signature (source notation)

```c
void svmop4s[_2x2]_za32[_bf16_bf16](uint64_t tile, svbfloat16x2_t zn, svbfloat16x2_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

BFloat16 quarter-tile sum of outer products to single-precision, subtracting

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Outer product subtract

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2,FEAT_SME_MOP4
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
  "tile": {
    "ZA array tile": "ZA0.S"
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
BFMOP4S ZA0.S, { Zreg1.H, Zreg2.H }, { Zreg3.H, Zreg4.H }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/BFMOP4S--widening---BFloat16-quarter-tile-sum-of-outer-products-to-single-precision--subtracting-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmop4s[_2x2]_za32[_f16_f16]

ISA classification: SME2 + FEAT_SME_MOP4

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmop4s%5B_2x2%5D_za32%5B_f16_f16%5D

### Signature (source notation)

```c
void svmop4s[_2x2]_za32[_f16_f16](uint64_t tile, svfloat16x2_t zn, svfloat16x2_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Half-precision quarter-tile sum of outer products to single-precision, subtracting

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Outer product subtract

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2,FEAT_SME_MOP4
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
  "tile": {
    "ZA array tile": "ZA0.S"
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
FMOP4S ZA0.S, { Zreg1.H, Zreg2.H }, { Zreg3.H, Zreg4.H }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/FMOP4S--widening---Half-precision-quarter-tile-sum-of-outer-products-to-single-precision--subtracting-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmop4s[_2x2]_za32[_f32_f32]

ISA classification: SME2 + FEAT_SME_MOP4

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmop4s%5B_2x2%5D_za32%5B_f32_f32%5D

### Signature (source notation)

```c
void svmop4s[_2x2]_za32[_f32_f32](uint64_t tile, svfloat32x2_t zn, svfloat32x2_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Floating-point quarter-tile outer product, subtracting

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Outer product subtract

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2,FEAT_SME_MOP4
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
  "tile": {
    "ZA array tile": "ZA0.S"
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
FMOP4S ZA0.S, { Zreg1.S, Zreg2.S }, { Zreg3.S, Zreg4.S }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/FMOP4S--non-widening---Floating-point-quarter-tile-outer-product--subtracting-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmop4s[_2x2]_za32[_s16_s16]

ISA classification: SME2 + FEAT_SME_MOP4

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmop4s%5B_2x2%5D_za32%5B_s16_s16%5D

### Signature (source notation)

```c
void svmop4s[_2x2]_za32[_s16_s16](uint64_t tile, svint16x2_t zn, svint16x2_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Signed 16-bit integer quarter-tile sum of outer products to 32-bit integer, subtracting

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Outer product subtract

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2,FEAT_SME_MOP4
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
  "tile": {
    "ZA array tile": "ZA0.S"
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
SMOP4S ZA0.S, { Zreg1.H, Zreg2.H }, { Zreg3.H, Zreg4.H }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/SMOP4S--2-way---Signed-16-bit-integer-quarter-tile-sum-of-outer-products-to-32-bit-integer--subtracting-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmop4s[_2x2]_za32[_s8_s8]

ISA classification: SME2 + FEAT_SME_MOP4

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmop4s%5B_2x2%5D_za32%5B_s8_s8%5D

### Signature (source notation)

```c
void svmop4s[_2x2]_za32[_s8_s8](uint64_t tile, svint8x2_t zn, svint8x2_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Signed integer quarter-tile sum of outer products, subtracting

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Outer product subtract

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2,FEAT_SME_MOP4
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
  "tile": {
    "ZA array tile": "ZA0.S"
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
SMOP4S ZA0.S, { Zreg1.B, Zreg2.B }, { Zreg3.B, Zreg4.B }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/SMOP4S--4-way---Signed-integer-quarter-tile-sum-of-outer-products--subtracting-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmop4s[_2x2]_za32[_s8_u8]

ISA classification: SME2 + FEAT_SME_MOP4

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmop4s%5B_2x2%5D_za32%5B_s8_u8%5D

### Signature (source notation)

```c
void svmop4s[_2x2]_za32[_s8_u8](uint64_t tile, svint8x2_t zn, svuint8x2_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Signed by unsigned integer quarter-tile sum of outer products, subtracting

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Outer product subtract

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2,FEAT_SME_MOP4
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
  "tile": {
    "ZA array tile": "ZA0.S"
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
SUMOP4S ZA0.S, { Zreg1.B, Zreg2.B }, { Zreg3.B, Zreg4.B }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/SUMOP4S--Signed-by-unsigned-integer-quarter-tile-sum-of-outer-products--subtracting-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmop4s[_2x2]_za32[_u16_u16]

ISA classification: SME2 + FEAT_SME_MOP4

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmop4s%5B_2x2%5D_za32%5B_u16_u16%5D

### Signature (source notation)

```c
void svmop4s[_2x2]_za32[_u16_u16](uint64_t tile, svuint16x2_t zn, svuint16x2_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Unsigned 16-bit integer quarter-tile sum of outer products to 32-bit integer, subtracting

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Outer product subtract

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2,FEAT_SME_MOP4
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
  "tile": {
    "ZA array tile": "ZA0.S"
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
UMOP4S ZA0.S, { Zreg1.H, Zreg2.H }, { Zreg3.H, Zreg4.H }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/UMOP4S--2-way---Unsigned-16-bit-integer-quarter-tile-sum-of-outer-products-to-32-bit-integer--subtracting-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmop4s[_2x2]_za32[_u8_s8]

ISA classification: SME2 + FEAT_SME_MOP4

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmop4s%5B_2x2%5D_za32%5B_u8_s8%5D

### Signature (source notation)

```c
void svmop4s[_2x2]_za32[_u8_s8](uint64_t tile, svuint8x2_t zn, svint8x2_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Unsigned by signed integer quarter-tile sum of outer products, subtracting

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Outer product subtract

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2,FEAT_SME_MOP4
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
  "tile": {
    "ZA array tile": "ZA0.S"
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
USMOP4S ZA0.S, { Zreg1.B, Zreg2.B }, { Zreg3.B, Zreg4.B }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/USMOP4S--Unsigned-by-signed-integer-quarter-tile-sum-of-outer-products--subtracting-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmop4s[_2x2]_za32[_u8_u8]

ISA classification: SME2 + FEAT_SME_MOP4

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmop4s%5B_2x2%5D_za32%5B_u8_u8%5D

### Signature (source notation)

```c
void svmop4s[_2x2]_za32[_u8_u8](uint64_t tile, svuint8x2_t zn, svuint8x2_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Unsigned integer quarter-tile sum of outer products, subtracting

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Outer product subtract

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2,FEAT_SME_MOP4
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
  "tile": {
    "ZA array tile": "ZA0.S"
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
UMOP4S ZA0.S, { Zreg1.B, Zreg2.B }, { Zreg3.B, Zreg4.B }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/UMOP4S--4-way---Unsigned-integer-quarter-tile-sum-of-outer-products--subtracting-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmop4s[_2x2]_za64[_f64_f64]

ISA classification: SME2 + FEAT_SME_MOP4, FEAT_SME_F64F64

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmop4s%5B_2x2%5D_za64%5B_f64_f64%5D

### Signature (source notation)

```c
void svmop4s[_2x2]_za64[_f64_f64](uint64_t tile, svfloat64x2_t zn, svfloat64x2_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Floating-point quarter-tile outer product, subtracting

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Outer product subtract

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2,FEAT_SME_MOP4,FEAT_SME_F64F64
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
  "tile": {
    "ZA array tile": "ZA0.D"
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
FMOP4S ZA0.D, { Zreg1.D, Zreg2.D }, { Zreg3.D, Zreg4.D }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/FMOP4S--non-widening---Floating-point-quarter-tile-outer-product--subtracting-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmop4s[_2x2]_za64[_s16_s16]

ISA classification: SME2 + FEAT_SME_MOP4, FEAT_SME_I16I64

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmop4s%5B_2x2%5D_za64%5B_s16_s16%5D

### Signature (source notation)

```c
void svmop4s[_2x2]_za64[_s16_s16](uint64_t tile, svint16x2_t zn, svint16x2_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Signed integer quarter-tile sum of outer products, subtracting

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Outer product subtract

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2,FEAT_SME_MOP4,FEAT_SME_I16I64
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
  "tile": {
    "ZA array tile": "ZA0.D"
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
SMOP4S ZA0.D, { Zreg1.H, Zreg2.H }, { Zreg3.H, Zreg4.H }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/SMOP4S--4-way---Signed-integer-quarter-tile-sum-of-outer-products--subtracting-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmop4s[_2x2]_za64[_s16_u16]

ISA classification: SME2 + FEAT_SME_MOP4, FEAT_SME_I16I64

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmop4s%5B_2x2%5D_za64%5B_s16_u16%5D

### Signature (source notation)

```c
void svmop4s[_2x2]_za64[_s16_u16](uint64_t tile, svint16x2_t zn, svuint16x2_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Signed by unsigned integer quarter-tile sum of outer products, subtracting

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Outer product subtract

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2,FEAT_SME_MOP4,FEAT_SME_I16I64
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
  "tile": {
    "ZA array tile": "ZA0.D"
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
SUMOP4S ZA0.D, { Zreg1.H, Zreg2.H }, { Zreg3.H, Zreg4.H }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/SUMOP4S--Signed-by-unsigned-integer-quarter-tile-sum-of-outer-products--subtracting-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmop4s[_2x2]_za64[_u16_s16]

ISA classification: SME2 + FEAT_SME_MOP4, FEAT_SME_I16I64

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmop4s%5B_2x2%5D_za64%5B_u16_s16%5D

### Signature (source notation)

```c
void svmop4s[_2x2]_za64[_u16_s16](uint64_t tile, svuint16x2_t zn, svint16x2_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Unsigned by signed integer quarter-tile sum of outer products, subtracting

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Outer product subtract

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2,FEAT_SME_MOP4,FEAT_SME_I16I64
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
  "tile": {
    "ZA array tile": "ZA0.D"
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
USMOP4S ZA0.D, { Zreg1.H, Zreg2.H }, { Zreg3.H, Zreg4.H }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/USMOP4S--Unsigned-by-signed-integer-quarter-tile-sum-of-outer-products--subtracting-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmop4s[_2x2]_za64[_u16_u16]

ISA classification: SME2 + FEAT_SME_MOP4, FEAT_SME_I16I64

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmop4s%5B_2x2%5D_za64%5B_u16_u16%5D

### Signature (source notation)

```c
void svmop4s[_2x2]_za64[_u16_u16](uint64_t tile, svuint16x2_t zn, svuint16x2_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Unsigned integer quarter-tile sum of outer products, subtracting

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Outer product subtract

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2,FEAT_SME_MOP4,FEAT_SME_I16I64
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
  "tile": {
    "ZA array tile": "ZA0.D"
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
UMOP4S ZA0.D, { Zreg1.H, Zreg2.H }, { Zreg3.H, Zreg4.H }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/UMOP4S--4-way---Unsigned-integer-quarter-tile-sum-of-outer-products--subtracting-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmops_za16[_bf16]_m

ISA classification: SME2 + FEAT_SME_B16B16

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmops_za16%5B_bf16%5D_m

### Signature (source notation)

```c
void svmops_za16[_bf16]_m(uint64_t tile, svbool_t pn, svbool_t pm, svbfloat16_t zn, svbfloat16_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

BFloat16 outer product, subtracting

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Outer product subtract

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
  "tile": {
    "ZA array tile": "ZA0.H"
  },
  "pn": {
    "register": "Preg1"
  },
  "pm": {
    "register": "Preg2"
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
BFMOPS ZA0.H, Preg1/M, Preg2/M, Zreg1.H, Zreg2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/BFMOPS--non-widening---BFloat16-outer-product--subtracting-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmops_za16[_f16]_m

ISA classification: SME2 + FEAT_SME_F16F16

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmops_za16%5B_f16%5D_m

### Signature (source notation)

```c
void svmops_za16[_f16]_m(uint64_t tile, svbool_t pn, svbool_t pm, svfloat16_t zn, svfloat16_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Floating-point outer product, subtracting

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Outer product subtract

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
  "tile": {
    "ZA array tile": "ZA0.H"
  },
  "pn": {
    "register": "Preg1"
  },
  "pm": {
    "register": "Preg2"
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
FMOPS ZA0.H, Preg1/M, Preg2/M, Zreg1.H, Zreg2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/FMOPS--non-widening---Floating-point-outer-product--subtracting-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmops_za32[_s16]_m

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmops_za32%5B_s16%5D_m

### Signature (source notation)

```c
void svmops_za32[_s16]_m(uint64_t tile, svbool_t pn, svbool_t pm, svint16_t zn, svint16_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Signed integer sum of outer products and subtract

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Outer product subtract

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
  "tile": {
    "register": "ZA0"
  },
  "pn": {
    "register": "Preg1"
  },
  "pm": {
    "register": "Preg2"
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
SMOPS ZA0.S, Preg1/M, Preg2/M, Zreg1.H, Zreg2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SMOPS--2-way---Signed-integer-sum-of-outer-products-and-subtract-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmops_za32[_u16]_m

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmops_za32%5B_u16%5D_m

### Signature (source notation)

```c
void svmops_za32[_u16]_m(uint64_t tile, svbool_t pn, svbool_t pm, svuint16_t zn, svuint16_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Unsigned integer sum of outer products and subtract

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Outer product subtract

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
  "tile": {
    "register": "ZA0"
  },
  "pn": {
    "register": "Preg1"
  },
  "pm": {
    "register": "Preg2"
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
UMOPS ZA0.S, Preg1/M, Preg2/M, Zreg1.H, Zreg2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/UMOPS--2-way---Unsigned-integer-sum-of-outer-products-and-subtract-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

