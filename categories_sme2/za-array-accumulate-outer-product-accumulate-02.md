# SME2 / ZA array / Accumulate / Outer product accumulate — Part 2

## svmop4a[_2x1]_za32[_u8_u8]

ISA classification: SME2 + FEAT_SME_MOP4

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmop4a%5B_2x1%5D_za32%5B_u8_u8%5D

### Signature (source notation)

```c
void svmop4a[_2x1]_za32[_u8_u8](uint64_t tile, svuint8x2_t zn, svuint8_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Unsigned integer quarter-tile sum of outer products, accumulating

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Outer product accumulate

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
UMOP4A ZA0.S, { Zreg1.B, Zreg2.B }, Zreg3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/UMOP4A--4-way---Unsigned-integer-quarter-tile-sum-of-outer-products--accumulating-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmop4a[_2x1]_za64[_f64_f64]

ISA classification: SME2 + FEAT_SME_MOP4, FEAT_SME_F64F64

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmop4a%5B_2x1%5D_za64%5B_f64_f64%5D

### Signature (source notation)

```c
void svmop4a[_2x1]_za64[_f64_f64](uint64_t tile, svfloat64x2_t zn, svfloat64_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Floating-point quarter-tile outer product, accumulating

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Outer product accumulate

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
    "register": "Zreg3.D"
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
FMOP4A ZA0.D, { Zreg1.D, Zreg2.D }, Zreg3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/FMOP4A--non-widening---Floating-point-quarter-tile-outer-product--accumulating-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmop4a[_2x1]_za64[_s16_s16]

ISA classification: SME2 + FEAT_SME_MOP4, FEAT_SME_I16I64

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmop4a%5B_2x1%5D_za64%5B_s16_s16%5D

### Signature (source notation)

```c
void svmop4a[_2x1]_za64[_s16_s16](uint64_t tile, svint16x2_t zn, svint16_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Signed integer quarter-tile sum of outer products, accumulating

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Outer product accumulate

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
SMOP4A ZA0.D, { Zreg1.H, Zreg2.H }, Zreg3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/SMOP4A--4-way---Signed-integer-quarter-tile-sum-of-outer-products--accumulating-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmop4a[_2x1]_za64[_s16_u16]

ISA classification: SME2 + FEAT_SME_MOP4, FEAT_SME_I16I64

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmop4a%5B_2x1%5D_za64%5B_s16_u16%5D

### Signature (source notation)

```c
void svmop4a[_2x1]_za64[_s16_u16](uint64_t tile, svint16x2_t zn, svuint16_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Signed by unsigned integer quarter-tile sum of outer products, accumulating

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Outer product accumulate

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
SUMOP4A ZA0.D, { Zreg1.H, Zreg2.H }, Zreg3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/SUMOP4A--Signed-by-unsigned-integer-quarter-tile-sum-of-outer-products--accumulating-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmop4a[_2x1]_za64[_u16_s16]

ISA classification: SME2 + FEAT_SME_MOP4, FEAT_SME_I16I64

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmop4a%5B_2x1%5D_za64%5B_u16_s16%5D

### Signature (source notation)

```c
void svmop4a[_2x1]_za64[_u16_s16](uint64_t tile, svuint16x2_t zn, svint16_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Unsigned by signed integer quarter-tile sum of outer products, accumulating

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Outer product accumulate

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
USMOP4A ZA0.D, { Zreg1.H, Zreg2.H }, Zreg3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/USMOP4A--Unsigned-by-signed-integer-quarter-tile-sum-of-outer-products--accumulating-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmop4a[_2x1]_za64[_u16_u16]

ISA classification: SME2 + FEAT_SME_MOP4, FEAT_SME_I16I64

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmop4a%5B_2x1%5D_za64%5B_u16_u16%5D

### Signature (source notation)

```c
void svmop4a[_2x1]_za64[_u16_u16](uint64_t tile, svuint16x2_t zn, svuint16_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Unsigned integer quarter-tile sum of outer products, accumulating

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Outer product accumulate

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
UMOP4A ZA0.D, { Zreg1.H, Zreg2.H }, Zreg3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/UMOP4A--4-way---Unsigned-integer-quarter-tile-sum-of-outer-products--accumulating-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmop4a[_2x2]_za16[_bf16_bf16]

ISA classification: SME2 + FEAT_SME_MOP4, FEAT_SME_B16B16

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmop4a%5B_2x2%5D_za16%5B_bf16_bf16%5D

### Signature (source notation)

```c
void svmop4a[_2x2]_za16[_bf16_bf16](uint64_t tile, svbfloat16x2_t zn, svbfloat16x2_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

BFloat16 quarter-tile outer product, accumulating

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Outer product accumulate

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
BFMOP4A ZA0.H, { Zreg1.H, Zreg2.H }, { Zreg3.H, Zreg4.H }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/BFMOP4A--non-widening---BFloat16-quarter-tile-outer-product--accumulating-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmop4a[_2x2]_za16[_f16_f16]

ISA classification: SME2 + FEAT_SME_MOP4, FEAT_SME_F16F16

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmop4a%5B_2x2%5D_za16%5B_f16_f16%5D

### Signature (source notation)

```c
void svmop4a[_2x2]_za16[_f16_f16](uint64_t tile, svfloat16x2_t zn, svfloat16x2_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Floating-point quarter-tile outer product, accumulating

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Outer product accumulate

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
FMOP4A ZA0.H, { Zreg1.H, Zreg2.H }, { Zreg3.H, Zreg4.H }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/FMOP4A--non-widening---Floating-point-quarter-tile-outer-product--accumulating-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmop4a[_2x2]_za16[_mf8_mf8]_fpm

ISA classification: SME2 + FEAT_SME_MOP4, FEAT_SME_F8F16

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmop4a%5B_2x2%5D_za16%5B_mf8_mf8%5D_fpm

### Signature (source notation)

```c
void svmop4a[_2x2]_za16[_mf8_mf8]_fpm(uint64_t tile, svmfloat8x2_t zn, svmfloat8x2_t zm, fpm_t fpm)
    __arm_streaming __arm_inout("za");
```

### Description

8-bit floating-point quarter-tile sum of outer products to half-precision, accumulating

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Outer product accumulate

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2,FEAT_SME_MOP4,FEAT_SME_F8F16
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
    "ZA array tile": "ZA0.H"
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
FMOP4A ZA0.H, { Zreg1.B, Zreg2.B }, { Zreg3.B, Zreg4.B }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/FMOP4A--widening--2-way--FP8-to-FP16---8-bit-floating-point-quarter-tile-sum-of-outer-products-to-half-precision--accumulating-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmop4a[_2x2]_za32[_bf16_bf16]

ISA classification: SME2 + FEAT_SME_MOP4

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmop4a%5B_2x2%5D_za32%5B_bf16_bf16%5D

### Signature (source notation)

```c
void svmop4a[_2x2]_za32[_bf16_bf16](uint64_t tile, svbfloat16x2_t zn, svbfloat16x2_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

BFloat16 quarter-tile sum of outer products to single-precision, accumulating

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Outer product accumulate

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
BFMOP4A ZA0.S, { Zreg1.H, Zreg2.H }, { Zreg3.H, Zreg4.H }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/BFMOP4A--widening---BFloat16-quarter-tile-sum-of-outer-products-to-single-precision--accumulating-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmop4a[_2x2]_za32[_f16_f16]

ISA classification: SME2 + FEAT_SME_MOP4

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmop4a%5B_2x2%5D_za32%5B_f16_f16%5D

### Signature (source notation)

```c
void svmop4a[_2x2]_za32[_f16_f16](uint64_t tile, svfloat16x2_t zn, svfloat16x2_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Half-precision quarter-tile sum of outer products to single-precision, accumulating

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Outer product accumulate

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
FMOP4A ZA0.S, { Zreg1.H, Zreg2.H }, { Zreg3.H, Zreg4.H }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/FMOP4A--widening--2-way--FP16-to-FP32---Half-precision-quarter-tile-sum-of-outer-products-to-single-precision--accumulating-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmop4a[_2x2]_za32[_f32_f32]

ISA classification: SME2 + FEAT_SME_MOP4

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmop4a%5B_2x2%5D_za32%5B_f32_f32%5D

### Signature (source notation)

```c
void svmop4a[_2x2]_za32[_f32_f32](uint64_t tile, svfloat32x2_t zn, svfloat32x2_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Floating-point quarter-tile outer product, accumulating

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Outer product accumulate

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
FMOP4A ZA0.S, { Zreg1.S, Zreg2.S }, { Zreg3.S, Zreg4.S }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/FMOP4A--non-widening---Floating-point-quarter-tile-outer-product--accumulating-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmop4a[_2x2]_za32[_mf8_mf8]_fpm

ISA classification: SME2 + FEAT_SME_MOP4, FEAT_SME_F8F32

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmop4a%5B_2x2%5D_za32%5B_mf8_mf8%5D_fpm

### Signature (source notation)

```c
void svmop4a[_2x2]_za32[_mf8_mf8]_fpm(uint64_t tile, svmfloat8x2_t zn, svmfloat8x2_t zm, fpm_t fpm)
    __arm_streaming __arm_inout("za");
```

### Description

8-bit floating-point quarter-tile sum of outer products to single-precision, accumulating

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Outer product accumulate

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2,FEAT_SME_MOP4,FEAT_SME_F8F32
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
FMOP4A ZA0.S, { Zreg1.B, Zreg2.B }, { Zreg3.B, Zreg4.B }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/FMOP4A--widening--4-way---8-bit-floating-point-quarter-tile-sum-of-outer-products-to-single-precision--accumulating-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmop4a[_2x2]_za32[_s16_s16]

ISA classification: SME2 + FEAT_SME_MOP4

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmop4a%5B_2x2%5D_za32%5B_s16_s16%5D

### Signature (source notation)

```c
void svmop4a[_2x2]_za32[_s16_s16](uint64_t tile, svint16x2_t zn, svint16x2_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Signed 16-bit integer quarter-tile sum of outer products to 32-bit integer, accumulating

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Outer product accumulate

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
SMOP4A ZA0.S, { Zreg1.H, Zreg2.H }, { Zreg3.H, Zreg4.H }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/SMOP4A--2-way---Signed-16-bit-integer-quarter-tile-sum-of-outer-products-to-32-bit-integer--accumulating-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmop4a[_2x2]_za32[_s8_s8]

ISA classification: SME2 + FEAT_SME_MOP4

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmop4a%5B_2x2%5D_za32%5B_s8_s8%5D

### Signature (source notation)

```c
void svmop4a[_2x2]_za32[_s8_s8](uint64_t tile, svint8x2_t zn, svint8x2_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Signed integer quarter-tile sum of outer products, accumulating

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Outer product accumulate

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
SMOP4A ZA0.S, { Zreg1.B, Zreg2.B }, { Zreg3.B, Zreg4.B }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/SMOP4A--4-way---Signed-integer-quarter-tile-sum-of-outer-products--accumulating-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmop4a[_2x2]_za32[_s8_u8]

ISA classification: SME2 + FEAT_SME_MOP4

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmop4a%5B_2x2%5D_za32%5B_s8_u8%5D

### Signature (source notation)

```c
void svmop4a[_2x2]_za32[_s8_u8](uint64_t tile, svint8x2_t zn, svuint8x2_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Signed by unsigned integer quarter-tile sum of outer products, accumulating

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Outer product accumulate

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
SUMOP4A ZA0.S, { Zreg1.B, Zreg2.B }, { Zreg3.B, Zreg4.B }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/SUMOP4A--Signed-by-unsigned-integer-quarter-tile-sum-of-outer-products--accumulating-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmop4a[_2x2]_za32[_u16_u16]

ISA classification: SME2 + FEAT_SME_MOP4

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmop4a%5B_2x2%5D_za32%5B_u16_u16%5D

### Signature (source notation)

```c
void svmop4a[_2x2]_za32[_u16_u16](uint64_t tile, svuint16x2_t zn, svuint16x2_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Unsigned 16-bit integer quarter-tile sum of outer products to 32-bit integer, accumulating

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Outer product accumulate

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
UMOP4A ZA0.S, { Zreg1.H, Zreg2.H }, { Zreg3.H, Zreg4.H }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/UMOP4A--2-way---Unsigned-16-bit-integer-quarter-tile-sum-of-outer-products-to-32-bit-integer--accumulating-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmop4a[_2x2]_za32[_u8_s8]

ISA classification: SME2 + FEAT_SME_MOP4

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmop4a%5B_2x2%5D_za32%5B_u8_s8%5D

### Signature (source notation)

```c
void svmop4a[_2x2]_za32[_u8_s8](uint64_t tile, svuint8x2_t zn, svint8x2_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Unsigned by signed integer quarter-tile sum of outer products, accumulating

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Outer product accumulate

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
USMOP4A ZA0.S, { Zreg1.B, Zreg2.B }, { Zreg3.B, Zreg4.B }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/USMOP4A--Unsigned-by-signed-integer-quarter-tile-sum-of-outer-products--accumulating-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmop4a[_2x2]_za32[_u8_u8]

ISA classification: SME2 + FEAT_SME_MOP4

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmop4a%5B_2x2%5D_za32%5B_u8_u8%5D

### Signature (source notation)

```c
void svmop4a[_2x2]_za32[_u8_u8](uint64_t tile, svuint8x2_t zn, svuint8x2_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Unsigned integer quarter-tile sum of outer products, accumulating

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Outer product accumulate

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
UMOP4A ZA0.S, { Zreg1.B, Zreg2.B }, { Zreg3.B, Zreg4.B }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/UMOP4A--4-way---Unsigned-integer-quarter-tile-sum-of-outer-products--accumulating-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmop4a[_2x2]_za64[_f64_f64]

ISA classification: SME2 + FEAT_SME_MOP4, FEAT_SME_F64F64

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmop4a%5B_2x2%5D_za64%5B_f64_f64%5D

### Signature (source notation)

```c
void svmop4a[_2x2]_za64[_f64_f64](uint64_t tile, svfloat64x2_t zn, svfloat64x2_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Floating-point quarter-tile outer product, accumulating

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Outer product accumulate

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
FMOP4A ZA0.D, { Zreg1.D, Zreg2.D }, { Zreg3.D, Zreg4.D }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/FMOP4A--non-widening---Floating-point-quarter-tile-outer-product--accumulating-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmop4a[_2x2]_za64[_s16_s16]

ISA classification: SME2 + FEAT_SME_MOP4, FEAT_SME_I16I64

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmop4a%5B_2x2%5D_za64%5B_s16_s16%5D

### Signature (source notation)

```c
void svmop4a[_2x2]_za64[_s16_s16](uint64_t tile, svint16x2_t zn, svint16x2_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Signed integer quarter-tile sum of outer products, accumulating

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Outer product accumulate

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
SMOP4A ZA0.D, { Zreg1.H, Zreg2.H }, { Zreg3.H, Zreg4.H }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/SMOP4A--4-way---Signed-integer-quarter-tile-sum-of-outer-products--accumulating-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmop4a[_2x2]_za64[_s16_u16]

ISA classification: SME2 + FEAT_SME_MOP4, FEAT_SME_I16I64

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmop4a%5B_2x2%5D_za64%5B_s16_u16%5D

### Signature (source notation)

```c
void svmop4a[_2x2]_za64[_s16_u16](uint64_t tile, svint16x2_t zn, svuint16x2_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Signed by unsigned integer quarter-tile sum of outer products, accumulating

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Outer product accumulate

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
SUMOP4A ZA0.D, { Zreg1.H, Zreg2.H }, { Zreg3.H, Zreg4.H }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/SUMOP4A--Signed-by-unsigned-integer-quarter-tile-sum-of-outer-products--accumulating-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmop4a[_2x2]_za64[_u16_s16]

ISA classification: SME2 + FEAT_SME_MOP4, FEAT_SME_I16I64

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmop4a%5B_2x2%5D_za64%5B_u16_s16%5D

### Signature (source notation)

```c
void svmop4a[_2x2]_za64[_u16_s16](uint64_t tile, svuint16x2_t zn, svint16x2_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Unsigned by signed integer quarter-tile sum of outer products, accumulating

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Outer product accumulate

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
USMOP4A ZA0.D, { Zreg1.H, Zreg2.H }, { Zreg3.H, Zreg4.H }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/USMOP4A--Unsigned-by-signed-integer-quarter-tile-sum-of-outer-products--accumulating-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmop4a[_2x2]_za64[_u16_u16]

ISA classification: SME2 + FEAT_SME_MOP4, FEAT_SME_I16I64

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmop4a%5B_2x2%5D_za64%5B_u16_u16%5D

### Signature (source notation)

```c
void svmop4a[_2x2]_za64[_u16_u16](uint64_t tile, svuint16x2_t zn, svuint16x2_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Unsigned integer quarter-tile sum of outer products, accumulating

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Outer product accumulate

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
UMOP4A ZA0.D, { Zreg1.H, Zreg2.H }, { Zreg3.H, Zreg4.H }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/UMOP4A--4-way---Unsigned-integer-quarter-tile-sum-of-outer-products--accumulating-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmopa_za16[_bf16]_m

ISA classification: SME2 + FEAT_SME_B16B16

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmopa_za16%5B_bf16%5D_m

### Signature (source notation)

```c
void svmopa_za16[_bf16]_m(uint64_t tile, svbool_t pn, svbool_t pm, svbfloat16_t zn, svbfloat16_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

BFloat16 outer product, accumulating

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Outer product accumulate

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
BFMOPA ZA0.H, Preg1/M, Preg2/M, Zreg1.H, Zreg2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/BFMOPA--non-widening---BFloat16-outer-product--accumulating-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmopa_za16[_f16]_m

ISA classification: SME2 + FEAT_SME_F16F16

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmopa_za16%5B_f16%5D_m

### Signature (source notation)

```c
void svmopa_za16[_f16]_m(uint64_t tile, svbool_t pn, svbool_t pm, svfloat16_t zn, svfloat16_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Floating-point outer product, accumulating

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Outer product accumulate

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
FMOPA ZA0.H, Preg1/M, Preg2/M, Zreg1.H, Zreg2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/FMOPA--non-widening---Floating-point-outer-product--accumulating-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmopa_za16[_mf8]_m_fpm

ISA classification: SME2 + FEAT_SME_F8F16

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmopa_za16%5B_mf8%5D_m_fpm

### Signature (source notation)

```c
void svmopa_za16[_mf8]_m_fpm(uint64_t tile, svbool_t pn, svbool_t pm, svmfloat8_t zn, svmfloat8_t zm, fpm_t fpm)
    __arm_streaming __arm_inout("za");
```

### Description

8-bit floating-point sum of outer products to half-precision, accumulating

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Outer product accumulate

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
FMOPA ZA0.H, Preg1/M, Preg2/M, Zreg1.B, Zreg2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/FMOPA--widening--2-way--FP8-to-FP16---8-bit-floating-point-sum-of-outer-products-to-half-precision--accumulating-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmopa_za32[_mf8]_m_fpm

ISA classification: SME2 + FEAT_SME_F8F32

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmopa_za32%5B_mf8%5D_m_fpm

### Signature (source notation)

```c
void svmopa_za32[_mf8]_m_fpm(uint64_t tile, svbool_t pn, svbool_t pm, svmfloat8_t zn, svmfloat8_t zm, fpm_t fpm)
    __arm_streaming __arm_inout("za");
```

### Description

8-bit floating-point sum of outer products to single-precision, accumulating

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Outer product accumulate

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
  "tile": {
    "ZA array tile": "ZA0.S"
  },
  "pn": {
    "register": "Preg1"
  },
  "pm": {
    "register": "Preg2"
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
FMOPA ZA0.S, Preg1/M, Preg2/M, Zreg1.B, Zreg2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/FMOPA--widening--4-way---8-bit-floating-point-sum-of-outer-products-to-single-precision--accumulating-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmopa_za32[_s16]_m

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmopa_za32%5B_s16%5D_m

### Signature (source notation)

```c
void svmopa_za32[_s16]_m(uint64_t tile, svbool_t pn, svbool_t pm, svint16_t zn, svint16_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Signed integer sum of outer products and accumulate

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Outer product accumulate

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
    "register": "ZA0.S"
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
SMOPA ZA0.S, Preg1/M, Preg2/M, Zreg1.H, Zreg2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SMOPA--2-way---Signed-integer-sum-of-outer-products-and-accumulate-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmopa_za32[_u16]_m

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmopa_za32%5B_u16%5D_m

### Signature (source notation)

```c
void svmopa_za32[_u16]_m(uint64_t tile, svbool_t pn, svbool_t pm, svuint16_t zn, svuint16_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Unsigned integer sum of outer products and accumulate

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Outer product accumulate

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
    "register": "ZA0.S"
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
UMOPA ZA0.S, Preg1/M, Preg2/M, Zreg1.H, Zreg2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/UMOPA--2-way---Unsigned-integer-sum-of-outer-products-and-accumulate-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svtmopa_lane_za16[_bf16_bf16]

ISA classification: SME2 + FEAT_SME_TMOP, FEAT_SME_B16B16

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svtmopa_lane_za16%5B_bf16_bf16%5D

### Signature (source notation)

```c
void svtmopa_lane_za16[_bf16_bf16](uint64_t tile, svbfloat16x2_t zn, svbfloat16_t zm, svuint8_t zk, uint64_t imm_idx)
    __arm_streaming __arm_inout("za");
```

### Description

BFloat16 sparse outer product, accumulating

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Outer product accumulate

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2,FEAT_SME_TMOP,FEAT_SME_B16B16
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
    "register": "Zreg3.H"
  },
  "zk": {
    "register": "Zreg4"
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
BFTMOPA ZA0.H, { Zreg1.H, Zreg2.H }, Zreg3.H, Zreg4[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/BFTMOPA--non-widening---BFloat16-sparse-outer-product--accumulating-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svtmopa_lane_za16[_f16_f16]

ISA classification: SME2 + FEAT_SME_TMOP, FEAT_SME_F16F16

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svtmopa_lane_za16%5B_f16_f16%5D

### Signature (source notation)

```c
void svtmopa_lane_za16[_f16_f16](uint64_t tile, svfloat16x2_t zn, svfloat16_t zm, svuint8_t zk, uint64_t imm_idx)
    __arm_streaming __arm_inout("za");
```

### Description

Floating-point sparse outer product, accumulating

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Outer product accumulate

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2,FEAT_SME_TMOP,FEAT_SME_F16F16
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
    "register": "Zreg3.H"
  },
  "zk": {
    "register": "Zreg4"
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
FTMOPA ZA0.H, { Zreg1.H, Zreg2.H }, Zreg3.H, Zreg4[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/FTMOPA--non-widening---Floating-point-sparse-outer-product--accumulating-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svtmopa_lane_za16[_mf8_mf8]_fpm

ISA classification: SME2 + FEAT_SME_TMOP, FEAT_SME_F8F16

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svtmopa_lane_za16%5B_mf8_mf8%5D_fpm

### Signature (source notation)

```c
void svtmopa_lane_za16[_mf8_mf8]_fpm(uint64_t tile, svmfloat8x2_t zn, svmfloat8_t zm, svuint8_t zk, uint64_t imm_idx, fpm_t fpm)
    __arm_streaming __arm_inout("za");
```

### Description

8-bit floating-point sparse sum of outer products to half-precision, accumulating

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Outer product accumulate

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2,FEAT_SME_TMOP,FEAT_SME_F8F16
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
    "ZA array tile": "ZA0.H"
  },
  "zn": {
    "Z multi-vector": "{ Zreg1.B, Zreg2.B }"
  },
  "zm": {
    "register": "Zreg3.B"
  },
  "zk": {
    "register": "Zreg4"
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
FTMOPA ZA0.H, { Zreg1.B, Zreg2.B }, Zreg3.B, Zreg4[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/FTMOPA--widening--2-way--FP8-to-FP16---8-bit-floating-point-sparse-sum-of-outer-products-to-half-precision--accumulating-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svtmopa_lane_za32[_bf16_bf16]

ISA classification: SME2 + FEAT_SME_TMOP

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svtmopa_lane_za32%5B_bf16_bf16%5D

### Signature (source notation)

```c
void svtmopa_lane_za32[_bf16_bf16](uint64_t tile, svbfloat16x2_t zn, svbfloat16_t zm, svuint8_t zk, uint64_t imm_idx)
    __arm_streaming __arm_inout("za");
```

### Description

BFloat16 sparse sum of outer products to single-precision, accumulating

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Outer product accumulate

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2,FEAT_SME_TMOP
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
    "register": "Zreg3.H"
  },
  "zk": {
    "register": "Zreg4"
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
BFTMOPA ZA0.S, { Zreg1.H, Zreg2.H }, Zreg3.H, Zreg4[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/BFTMOPA--widening---BFloat16-sparse-sum-of-outer-products-to-single-precision--accumulating-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svtmopa_lane_za32[_f16_f16]

ISA classification: SME2 + FEAT_SME_TMOP

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svtmopa_lane_za32%5B_f16_f16%5D

### Signature (source notation)

```c
void svtmopa_lane_za32[_f16_f16](uint64_t tile, svfloat16x2_t zn, svfloat16_t zm, svuint8_t zk, uint64_t imm_idx)
    __arm_streaming __arm_inout("za");
```

### Description

Half-precision sparse sum of outer products to single-precision, accumulating

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Outer product accumulate

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2,FEAT_SME_TMOP
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
    "register": "Zreg3.H"
  },
  "zk": {
    "register": "Zreg4"
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
FTMOPA ZA0.S, { Zreg1.H, Zreg2.H }, Zreg3.H, Zreg4[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/FTMOPA--widening--2-way--FP16-to-FP32---Half-precision-sparse-sum-of-outer-products-to-single-precision--accumulating-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svtmopa_lane_za32[_f32_f32]

ISA classification: SME2 + FEAT_SME_TMOP

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svtmopa_lane_za32%5B_f32_f32%5D

### Signature (source notation)

```c
void svtmopa_lane_za32[_f32_f32](uint64_t tile, svfloat32x2_t zn, svfloat32_t zm, svuint8_t zk, uint64_t imm_idx)
    __arm_streaming __arm_inout("za");
```

### Description

Floating-point sparse outer product, accumulating

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Outer product accumulate

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2,FEAT_SME_TMOP
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
    "register": "Zreg3.S"
  },
  "zk": {
    "register": "Zreg4"
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
FTMOPA ZA0.S, { Zreg1.S, Zreg2.S }, Zreg3.S, Zreg4[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/FTMOPA--non-widening---Floating-point-sparse-outer-product--accumulating-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svtmopa_lane_za32[_mf8_mf8]_fpm

ISA classification: SME2 + FEAT_SME_TMOP, FEAT_SME_F8F32

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svtmopa_lane_za32%5B_mf8_mf8%5D_fpm

### Signature (source notation)

```c
void svtmopa_lane_za32[_mf8_mf8]_fpm(uint64_t tile, svmfloat8x2_t zn, svmfloat8_t zm, svuint8_t zk, uint64_t imm_idx, fpm_t fpm)
    __arm_streaming __arm_inout("za");
```

### Description

8-bit floating-point sparse sum of outer products to single-precision, accumulating

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Outer product accumulate

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2,FEAT_SME_TMOP,FEAT_SME_F8F32
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
    "register": "Zreg3.B"
  },
  "zk": {
    "register": "Zreg4"
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
FTMOPA ZA0.S, { Zreg1.B, Zreg2.B }, Zreg3.B, Zreg4[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/FTMOPA--widening--4-way---8-bit-floating-point-sparse-sum-of-outer-products-to-single-precision--accumulating-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svtmopa_lane_za32[_s16_s16]

ISA classification: SME2 + FEAT_SME_TMOP

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svtmopa_lane_za32%5B_s16_s16%5D

### Signature (source notation)

```c
void svtmopa_lane_za32[_s16_s16](uint64_t tile, svint16x2_t zn, svint16_t zm, svuint8_t zk, uint64_t imm_idx)
    __arm_streaming __arm_inout("za");
```

### Description

Signed 16-bit integer sparse sum of outer products to 32-bit integer, accumulating

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Outer product accumulate

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2,FEAT_SME_TMOP
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
    "register": "Zreg3.H"
  },
  "zk": {
    "register": "Zreg4"
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
STMOPA ZA0.S, { Zreg1.H, Zreg2.H }, Zreg3.H, Zreg4[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/STMOPA--2-way---Signed-16-bit-integer-sparse-sum-of-outer-products-to-32-bit-integer--accumulating-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svtmopa_lane_za32[_s8_s8]

ISA classification: SME2 + FEAT_SME_TMOP

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svtmopa_lane_za32%5B_s8_s8%5D

### Signature (source notation)

```c
void svtmopa_lane_za32[_s8_s8](uint64_t tile, svint8x2_t zn, svint8_t zm, svuint8_t zk, uint64_t imm_idx)
    __arm_streaming __arm_inout("za");
```

### Description

Signed 8-bit integer sparse sum of outer products to 32-bit integer, accumulating

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Outer product accumulate

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2,FEAT_SME_TMOP
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
    "register": "Zreg3.B"
  },
  "zk": {
    "register": "Zreg4"
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
STMOPA ZA0.S, { Zreg1.B, Zreg2.B }, Zreg3.B, Zreg4[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/STMOPA--4-way---Signed-8-bit-integer-sparse-sum-of-outer-products-to-32-bit-integer--accumulating-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svtmopa_lane_za32[_s8_u8]

ISA classification: SME2 + FEAT_SME_TMOP

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svtmopa_lane_za32%5B_s8_u8%5D

### Signature (source notation)

```c
void svtmopa_lane_za32[_s8_u8](uint64_t tile, svint8x2_t zn, svuint8_t zm, svuint8_t zk, uint64_t imm_idx)
    __arm_streaming __arm_inout("za");
```

### Description

Signed by unsigned 8-bit integer sparse sum of outer products to 32-bit integer, accumulating

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Outer product accumulate

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2,FEAT_SME_TMOP
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
    "register": "Zreg3.B"
  },
  "zk": {
    "register": "Zreg4"
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
SUTMOPA ZA0.S, { Zreg1.B, Zreg2.B }, Zreg3.B, Zreg4[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/SUTMOPA--Signed-by-unsigned-8-bit-integer-sparse-sum-of-outer-products-to-32-bit-integer--accumulating-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svtmopa_lane_za32[_u16_u16]

ISA classification: SME2 + FEAT_SME_TMOP

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svtmopa_lane_za32%5B_u16_u16%5D

### Signature (source notation)

```c
void svtmopa_lane_za32[_u16_u16](uint64_t tile, svuint16x2_t zn, svuint16_t zm, svuint8_t zk, uint64_t imm_idx)
    __arm_streaming __arm_inout("za");
```

### Description

Unsigned 16-bit integer sparse sum of outer products to 32-bit integer, accumulating

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Outer product accumulate

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2,FEAT_SME_TMOP
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
    "register": "Zreg3.H"
  },
  "zk": {
    "register": "Zreg4"
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
UTMOPA ZA0.S, { Zreg1.H, Zreg2.H }, Zreg3.H, Zreg4[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/UTMOPA--2-way---Unsigned-16-bit-integer-sparse-sum-of-outer-products-to-32-bit-integer--accumulating-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svtmopa_lane_za32[_u8_s8]

ISA classification: SME2 + FEAT_SME_TMOP

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svtmopa_lane_za32%5B_u8_s8%5D

### Signature (source notation)

```c
void svtmopa_lane_za32[_u8_s8](uint64_t tile, svuint8x2_t zn, svint8_t zm, svuint8_t zk, uint64_t imm_idx)
    __arm_streaming __arm_inout("za");
```

### Description

Unsigned by signed 8-bit integer sparse sum of outer products to 32-bit integer, accumulating

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Outer product accumulate

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2,FEAT_SME_TMOP
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
    "register": "Zreg3.B"
  },
  "zk": {
    "register": "Zreg4"
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
USTMOPA ZA0.S, { Zreg1.B, Zreg2.B }, Zreg3.B, Zreg4[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/USTMOPA--Unsigned-by-signed-8-bit-integer-sparse-sum-of-outer-products-to-32-bit-integer--accumulating-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svtmopa_lane_za32[_u8_u8]

ISA classification: SME2 + FEAT_SME_TMOP

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svtmopa_lane_za32%5B_u8_u8%5D

### Signature (source notation)

```c
void svtmopa_lane_za32[_u8_u8](uint64_t tile, svuint8x2_t zn, svuint8_t zm, svuint8_t zk, uint64_t imm_idx)
    __arm_streaming __arm_inout("za");
```

### Description

Unsigned 8-bit integer sparse sum of outer products to 32-bit integer, accumulating

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Outer product accumulate

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2,FEAT_SME_TMOP
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
    "register": "Zreg3.B"
  },
  "zk": {
    "register": "Zreg4"
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
UTMOPA ZA0.S, { Zreg1.B, Zreg2.B }, Zreg3.B, Zreg4[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/UTMOPA--4-way---Unsigned-8-bit-integer-sparse-sum-of-outer-products-to-32-bit-integer--accumulating-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

