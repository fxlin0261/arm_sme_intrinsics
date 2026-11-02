# SME2 / ZA array / Accumulate / Outer product accumulate — Part 1

## svbmopa_za32[_s32]_m

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svbmopa_za32%5B_s32%5D_m

### Signature (source notation)

```c
void svbmopa_za32[_s32]_m(uint64_t tile, svbool_t pn, svbool_t pm, svint32_t zn, svint32_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Bitwise exclusive NOR population count outer product and accumulate

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
  "pn": {
    "register": "Preg1"
  },
  "pm": {
    "register": "Preg2"
  },
  "zn": {
    "register": "Zreg1.S"
  },
  "zm": {
    "register": "Zreg2.S"
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
BMOPA ZA0.S, Preg1/M, Preg2/M, Zreg1.S, Zreg2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/BMOPA--Bitwise-exclusive-NOR-population-count-outer-product-and-accumulate-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svbmopa_za32[_u32]_m

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svbmopa_za32%5B_u32%5D_m

### Signature (source notation)

```c
void svbmopa_za32[_u32]_m(uint64_t tile, svbool_t pn, svbool_t pm, svuint32_t zn, svuint32_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Bitwise exclusive NOR population count outer product and accumulate

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
  "pn": {
    "register": "Preg1"
  },
  "pm": {
    "register": "Preg2"
  },
  "zn": {
    "register": "Zreg1.S"
  },
  "zm": {
    "register": "Zreg2.S"
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
BMOPA ZA0.S, Preg1/M, Preg2/M, Zreg1.S, Zreg2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/BMOPA--Bitwise-exclusive-NOR-population-count-outer-product-and-accumulate-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmop4a[_1x1]_za16[_bf16_bf16]

ISA classification: SME2 + FEAT_SME_MOP4, FEAT_SME_B16B16

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmop4a%5B_1x1%5D_za16%5B_bf16_bf16%5D

### Signature (source notation)

```c
void svmop4a[_1x1]_za16[_bf16_bf16](uint64_t tile, svbfloat16_t zn, svbfloat16_t zm)
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
BFMOP4A ZA0.H, Zreg1.H, Zreg2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/BFMOP4A--non-widening---BFloat16-quarter-tile-outer-product--accumulating-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmop4a[_1x1]_za16[_f16_f16]

ISA classification: SME2 + FEAT_SME_MOP4, FEAT_SME_F16F16

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmop4a%5B_1x1%5D_za16%5B_f16_f16%5D

### Signature (source notation)

```c
void svmop4a[_1x1]_za16[_f16_f16](uint64_t tile, svfloat16_t zn, svfloat16_t zm)
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
FMOP4A ZA0.H, Zreg1.H, Zreg2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/FMOP4A--non-widening---Floating-point-quarter-tile-outer-product--accumulating-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmop4a[_1x1]_za16[_mf8_mf8]_fpm

ISA classification: SME2 + FEAT_SME_MOP4, FEAT_SME_F8F16

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmop4a%5B_1x1%5D_za16%5B_mf8_mf8%5D_fpm

### Signature (source notation)

```c
void svmop4a[_1x1]_za16[_mf8_mf8]_fpm(uint64_t tile, svmfloat8_t zn, svmfloat8_t zm, fpm_t fpm)
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
FMOP4A ZA0.H, Zreg1.B, Zreg2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/FMOP4A--widening--2-way--FP8-to-FP16---8-bit-floating-point-quarter-tile-sum-of-outer-products-to-half-precision--accumulating-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmop4a[_1x1]_za32[_bf16_bf16]

ISA classification: SME2 + FEAT_SME_MOP4

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmop4a%5B_1x1%5D_za32%5B_bf16_bf16%5D

### Signature (source notation)

```c
void svmop4a[_1x1]_za32[_bf16_bf16](uint64_t tile, svbfloat16_t zn, svbfloat16_t zm)
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
BFMOP4A ZA0.S, Zreg1.H, Zreg2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/BFMOP4A--widening---BFloat16-quarter-tile-sum-of-outer-products-to-single-precision--accumulating-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmop4a[_1x1]_za32[_f16_f16]

ISA classification: SME2 + FEAT_SME_MOP4

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmop4a%5B_1x1%5D_za32%5B_f16_f16%5D

### Signature (source notation)

```c
void svmop4a[_1x1]_za32[_f16_f16](uint64_t tile, svfloat16_t zn, svfloat16_t zm)
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
FMOP4A ZA0.S, Zreg1.H, Zreg2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/FMOP4A--widening--2-way--FP16-to-FP32---Half-precision-quarter-tile-sum-of-outer-products-to-single-precision--accumulating-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmop4a[_1x1]_za32[_f32_f32]

ISA classification: SME2 + FEAT_SME_MOP4

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmop4a%5B_1x1%5D_za32%5B_f32_f32%5D

### Signature (source notation)

```c
void svmop4a[_1x1]_za32[_f32_f32](uint64_t tile, svfloat32_t zn, svfloat32_t zm)
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
    "register": "Zreg1.S"
  },
  "zm": {
    "register": "Zreg2.S"
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
FMOP4A ZA0.S, Zreg1.S, Zreg2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/FMOP4A--non-widening---Floating-point-quarter-tile-outer-product--accumulating-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmop4a[_1x1]_za32[_mf8_mf8]_fpm

ISA classification: SME2 + FEAT_SME_MOP4, FEAT_SME_F8F32

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmop4a%5B_1x1%5D_za32%5B_mf8_mf8%5D_fpm

### Signature (source notation)

```c
void svmop4a[_1x1]_za32[_mf8_mf8]_fpm(uint64_t tile, svmfloat8_t zn, svmfloat8_t zm, fpm_t fpm)
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
FMOP4A ZA0.S, Zreg1.B, Zreg2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/FMOP4A--widening--4-way---8-bit-floating-point-quarter-tile-sum-of-outer-products-to-single-precision--accumulating-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmop4a[_1x1]_za32[_s16_s16]

ISA classification: SME2 + FEAT_SME_MOP4

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmop4a%5B_1x1%5D_za32%5B_s16_s16%5D

### Signature (source notation)

```c
void svmop4a[_1x1]_za32[_s16_s16](uint64_t tile, svint16_t zn, svint16_t zm)
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
SMOP4A ZA0.S, Zreg1.H, Zreg2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/SMOP4A--2-way---Signed-16-bit-integer-quarter-tile-sum-of-outer-products-to-32-bit-integer--accumulating-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmop4a[_1x1]_za32[_s8_s8]

ISA classification: SME2 + FEAT_SME_MOP4

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmop4a%5B_1x1%5D_za32%5B_s8_s8%5D

### Signature (source notation)

```c
void svmop4a[_1x1]_za32[_s8_s8](uint64_t tile, svint8_t zn, svint8_t zm)
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
SMOP4A ZA0.S, Zreg1.B, Zreg2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/SMOP4A--4-way---Signed-integer-quarter-tile-sum-of-outer-products--accumulating-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmop4a[_1x1]_za32[_s8_u8]

ISA classification: SME2 + FEAT_SME_MOP4

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmop4a%5B_1x1%5D_za32%5B_s8_u8%5D

### Signature (source notation)

```c
void svmop4a[_1x1]_za32[_s8_u8](uint64_t tile, svint8_t zn, svuint8_t zm)
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
SUMOP4A ZA0.S, Zreg1.B, Zreg2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/SUMOP4A--Signed-by-unsigned-integer-quarter-tile-sum-of-outer-products--accumulating-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmop4a[_1x1]_za32[_u16_u16]

ISA classification: SME2 + FEAT_SME_MOP4

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmop4a%5B_1x1%5D_za32%5B_u16_u16%5D

### Signature (source notation)

```c
void svmop4a[_1x1]_za32[_u16_u16](uint64_t tile, svuint16_t zn, svuint16_t zm)
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
UMOP4A ZA0.S, Zreg1.H, Zreg2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/UMOP4A--2-way---Unsigned-16-bit-integer-quarter-tile-sum-of-outer-products-to-32-bit-integer--accumulating-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmop4a[_1x1]_za32[_u8_s8]

ISA classification: SME2 + FEAT_SME_MOP4

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmop4a%5B_1x1%5D_za32%5B_u8_s8%5D

### Signature (source notation)

```c
void svmop4a[_1x1]_za32[_u8_s8](uint64_t tile, svuint8_t zn, svint8_t zm)
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
USMOP4A ZA0.S, Zreg1.B, Zreg2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/USMOP4A--Unsigned-by-signed-integer-quarter-tile-sum-of-outer-products--accumulating-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmop4a[_1x1]_za32[_u8_u8]

ISA classification: SME2 + FEAT_SME_MOP4

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmop4a%5B_1x1%5D_za32%5B_u8_u8%5D

### Signature (source notation)

```c
void svmop4a[_1x1]_za32[_u8_u8](uint64_t tile, svuint8_t zn, svuint8_t zm)
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
UMOP4A ZA0.S, Zreg1.B, Zreg2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/UMOP4A--4-way---Unsigned-integer-quarter-tile-sum-of-outer-products--accumulating-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmop4a[_1x1]_za64[_f64_f64]

ISA classification: SME2 + FEAT_SME_MOP4, FEAT_SME_F64F64

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmop4a%5B_1x1%5D_za64%5B_f64_f64%5D

### Signature (source notation)

```c
void svmop4a[_1x1]_za64[_f64_f64](uint64_t tile, svfloat64_t zn, svfloat64_t zm)
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
    "register": "Zreg1.D"
  },
  "zm": {
    "register": "Zreg2.D"
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
FMOP4A ZA0.D, Zreg1.D, Zreg2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/FMOP4A--non-widening---Floating-point-quarter-tile-outer-product--accumulating-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmop4a[_1x1]_za64[_s16_s16]

ISA classification: SME2 + FEAT_SME_MOP4, FEAT_SME_I16I64

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmop4a%5B_1x1%5D_za64%5B_s16_s16%5D

### Signature (source notation)

```c
void svmop4a[_1x1]_za64[_s16_s16](uint64_t tile, svint16_t zn, svint16_t zm)
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
SMOP4A ZA0.D, Zreg1.H, Zreg2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/SMOP4A--4-way---Signed-integer-quarter-tile-sum-of-outer-products--accumulating-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmop4a[_1x1]_za64[_s16_u16]

ISA classification: SME2 + FEAT_SME_MOP4, FEAT_SME_I16I64

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmop4a%5B_1x1%5D_za64%5B_s16_u16%5D

### Signature (source notation)

```c
void svmop4a[_1x1]_za64[_s16_u16](uint64_t tile, svint16_t zn, svuint16_t zm)
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
SUMOP4A ZA0.D, Zreg1.H, Zreg2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/SUMOP4A--Signed-by-unsigned-integer-quarter-tile-sum-of-outer-products--accumulating-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmop4a[_1x1]_za64[_u16_s16]

ISA classification: SME2 + FEAT_SME_MOP4, FEAT_SME_I16I64

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmop4a%5B_1x1%5D_za64%5B_u16_s16%5D

### Signature (source notation)

```c
void svmop4a[_1x1]_za64[_u16_s16](uint64_t tile, svuint16_t zn, svint16_t zm)
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
USMOP4A ZA0.D, Zreg1.H, Zreg2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/USMOP4A--Unsigned-by-signed-integer-quarter-tile-sum-of-outer-products--accumulating-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmop4a[_1x1]_za64[_u16_u16]

ISA classification: SME2 + FEAT_SME_MOP4, FEAT_SME_I16I64

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmop4a%5B_1x1%5D_za64%5B_u16_u16%5D

### Signature (source notation)

```c
void svmop4a[_1x1]_za64[_u16_u16](uint64_t tile, svuint16_t zn, svuint16_t zm)
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
UMOP4A ZA0.D, Zreg1.H, Zreg2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/UMOP4A--4-way---Unsigned-integer-quarter-tile-sum-of-outer-products--accumulating-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmop4a[_1x2]_za16[_bf16_bf16]

ISA classification: SME2 + FEAT_SME_MOP4, FEAT_SME_B16B16

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmop4a%5B_1x2%5D_za16%5B_bf16_bf16%5D

### Signature (source notation)

```c
void svmop4a[_1x2]_za16[_bf16_bf16](uint64_t tile, svbfloat16_t zn, svbfloat16x2_t zm)
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
    "register": "Zreg1.H"
  },
  "zm": {
    "Z multi-vector": "{ Zreg2.H, Zreg3.H }"
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
BFMOP4A ZA0.H, Zreg1.H, { Zreg2.H, Zreg3.H }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/BFMOP4A--non-widening---BFloat16-quarter-tile-outer-product--accumulating-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmop4a[_1x2]_za16[_f16_f16]

ISA classification: SME2 + FEAT_SME_MOP4, FEAT_SME_F16F16

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmop4a%5B_1x2%5D_za16%5B_f16_f16%5D

### Signature (source notation)

```c
void svmop4a[_1x2]_za16[_f16_f16](uint64_t tile, svfloat16_t zn, svfloat16x2_t zm)
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
    "register": "Zreg1.H"
  },
  "zm": {
    "Z multi-vector": "{ Zreg2.H, Zreg3.H }"
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
FMOP4A ZA0.H, Zreg1.H, { Zreg2.H, Zreg3.H }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/FMOP4A--non-widening---Floating-point-quarter-tile-outer-product--accumulating-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmop4a[_1x2]_za16[_mf8_mf8]_fpm

ISA classification: SME2 + FEAT_SME_MOP4, FEAT_SME_F8F16

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmop4a%5B_1x2%5D_za16%5B_mf8_mf8%5D_fpm

### Signature (source notation)

```c
void svmop4a[_1x2]_za16[_mf8_mf8]_fpm(uint64_t tile, svmfloat8_t zn, svmfloat8x2_t zm, fpm_t fpm)
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
    "register": "Zreg1.B"
  },
  "zm": {
    "Z multi-vector": "{ Zreg2.B, Zreg3.B }"
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
FMOP4A ZA0.H, Zreg1.B, { Zreg2.B, Zreg3.B }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/FMOP4A--widening--2-way--FP8-to-FP16---8-bit-floating-point-quarter-tile-sum-of-outer-products-to-half-precision--accumulating-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmop4a[_1x2]_za32[_bf16_bf16]

ISA classification: SME2 + FEAT_SME_MOP4

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmop4a%5B_1x2%5D_za32%5B_bf16_bf16%5D

### Signature (source notation)

```c
void svmop4a[_1x2]_za32[_bf16_bf16](uint64_t tile, svbfloat16_t zn, svbfloat16x2_t zm)
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
    "register": "Zreg1.H"
  },
  "zm": {
    "Z multi-vector": "{ Zreg2.H, Zreg3.H }"
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
BFMOP4A ZA0.S, Zreg1.H, { Zreg2.H, Zreg3.H }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/BFMOP4A--widening---BFloat16-quarter-tile-sum-of-outer-products-to-single-precision--accumulating-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmop4a[_1x2]_za32[_f16_f16]

ISA classification: SME2 + FEAT_SME_MOP4

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmop4a%5B_1x2%5D_za32%5B_f16_f16%5D

### Signature (source notation)

```c
void svmop4a[_1x2]_za32[_f16_f16](uint64_t tile, svfloat16_t zn, svfloat16x2_t zm)
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
    "register": "Zreg1.H"
  },
  "zm": {
    "Z multi-vector": "{ Zreg2.H, Zreg3.H }"
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
FMOP4A ZA0.S, Zreg1.H, { Zreg2.H, Zreg3.H }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/FMOP4A--widening--2-way--FP16-to-FP32---Half-precision-quarter-tile-sum-of-outer-products-to-single-precision--accumulating-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmop4a[_1x2]_za32[_f32_f32]

ISA classification: SME2 + FEAT_SME_MOP4

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmop4a%5B_1x2%5D_za32%5B_f32_f32%5D

### Signature (source notation)

```c
void svmop4a[_1x2]_za32[_f32_f32](uint64_t tile, svfloat32_t zn, svfloat32x2_t zm)
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
    "register": "Zreg1.S"
  },
  "zm": {
    "Z multi-vector": "{ Zreg2.S, Zreg3.S }"
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
FMOP4A ZA0.S, Zreg1.S, { Zreg2.S, Zreg3.S }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/FMOP4A--non-widening---Floating-point-quarter-tile-outer-product--accumulating-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmop4a[_1x2]_za32[_mf8_mf8]_fpm

ISA classification: SME2 + FEAT_SME_MOP4, FEAT_SME_F8F32

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmop4a%5B_1x2%5D_za32%5B_mf8_mf8%5D_fpm

### Signature (source notation)

```c
void svmop4a[_1x2]_za32[_mf8_mf8]_fpm(uint64_t tile, svmfloat8_t zn, svmfloat8x2_t zm, fpm_t fpm)
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
    "register": "Zreg1.B"
  },
  "zm": {
    "Z multi-vector": "{ Zreg2.B, Zreg3.B }"
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
FMOP4A ZA0.S, Zreg1.B, { Zreg2.B, Zreg3.B }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/FMOP4A--widening--4-way---8-bit-floating-point-quarter-tile-sum-of-outer-products-to-single-precision--accumulating-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmop4a[_1x2]_za32[_s16_s16]

ISA classification: SME2 + FEAT_SME_MOP4

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmop4a%5B_1x2%5D_za32%5B_s16_s16%5D

### Signature (source notation)

```c
void svmop4a[_1x2]_za32[_s16_s16](uint64_t tile, svint16_t zn, svint16x2_t zm)
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
    "register": "Zreg1.H"
  },
  "zm": {
    "Z multi-vector": "{ Zreg2.H, Zreg3.H }"
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
SMOP4A ZA0.S, Zreg1.H, { Zreg2.H, Zreg3.H }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/SMOP4A--2-way---Signed-16-bit-integer-quarter-tile-sum-of-outer-products-to-32-bit-integer--accumulating-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmop4a[_1x2]_za32[_s8_s8]

ISA classification: SME2 + FEAT_SME_MOP4

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmop4a%5B_1x2%5D_za32%5B_s8_s8%5D

### Signature (source notation)

```c
void svmop4a[_1x2]_za32[_s8_s8](uint64_t tile, svint8_t zn, svint8x2_t zm)
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
    "register": "Zreg1.B"
  },
  "zm": {
    "Z multi-vector": "{ Zreg2.B, Zreg3.B }"
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
SMOP4A ZA0.S, Zreg1.B, { Zreg2.B, Zreg3.B }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/SMOP4A--4-way---Signed-integer-quarter-tile-sum-of-outer-products--accumulating-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmop4a[_1x2]_za32[_s8_u8]

ISA classification: SME2 + FEAT_SME_MOP4

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmop4a%5B_1x2%5D_za32%5B_s8_u8%5D

### Signature (source notation)

```c
void svmop4a[_1x2]_za32[_s8_u8](uint64_t tile, svint8_t zn, svuint8x2_t zm)
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
    "register": "Zreg1.B"
  },
  "zm": {
    "Z multi-vector": "{ Zreg2.B, Zreg3.B }"
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
SUMOP4A ZA0.S, Zreg1.B, { Zreg2.B, Zreg3.B }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/SUMOP4A--Signed-by-unsigned-integer-quarter-tile-sum-of-outer-products--accumulating-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmop4a[_1x2]_za32[_u16_u16]

ISA classification: SME2 + FEAT_SME_MOP4

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmop4a%5B_1x2%5D_za32%5B_u16_u16%5D

### Signature (source notation)

```c
void svmop4a[_1x2]_za32[_u16_u16](uint64_t tile, svuint16_t zn, svuint16x2_t zm)
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
    "register": "Zreg1.H"
  },
  "zm": {
    "Z multi-vector": "{ Zreg2.H, Zreg3.H }"
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
UMOP4A ZA0.S, Zreg1.H, { Zreg2.H, Zreg3.H }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/UMOP4A--2-way---Unsigned-16-bit-integer-quarter-tile-sum-of-outer-products-to-32-bit-integer--accumulating-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmop4a[_1x2]_za32[_u8_s8]

ISA classification: SME2 + FEAT_SME_MOP4

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmop4a%5B_1x2%5D_za32%5B_u8_s8%5D

### Signature (source notation)

```c
void svmop4a[_1x2]_za32[_u8_s8](uint64_t tile, svuint8_t zn, svint8x2_t zm)
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
    "register": "Zreg1.B"
  },
  "zm": {
    "Z multi-vector": "{ Zreg2.B, Zreg3.B }"
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
USMOP4A ZA0.S, Zreg1.B, { Zreg2.B, Zreg3.B }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/USMOP4A--Unsigned-by-signed-integer-quarter-tile-sum-of-outer-products--accumulating-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmop4a[_1x2]_za32[_u8_u8]

ISA classification: SME2 + FEAT_SME_MOP4

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmop4a%5B_1x2%5D_za32%5B_u8_u8%5D

### Signature (source notation)

```c
void svmop4a[_1x2]_za32[_u8_u8](uint64_t tile, svuint8_t zn, svuint8x2_t zm)
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
    "register": "Zreg1.B"
  },
  "zm": {
    "Z multi-vector": "{ Zreg2.B, Zreg3.B }"
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
UMOP4A ZA0.S, Zreg1.B, { Zreg2.B, Zreg3.B }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/UMOP4A--4-way---Unsigned-integer-quarter-tile-sum-of-outer-products--accumulating-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmop4a[_1x2]_za64[_f64_f64]

ISA classification: SME2 + FEAT_SME_MOP4, FEAT_SME_F64F64

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmop4a%5B_1x2%5D_za64%5B_f64_f64%5D

### Signature (source notation)

```c
void svmop4a[_1x2]_za64[_f64_f64](uint64_t tile, svfloat64_t zn, svfloat64x2_t zm)
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
    "register": "Zreg1.D"
  },
  "zm": {
    "Z multi-vector": "{ Zreg2.D, Zreg3.D }"
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
FMOP4A ZA0.D, Zreg1.D, { Zreg2.D, Zreg3.D }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/FMOP4A--non-widening---Floating-point-quarter-tile-outer-product--accumulating-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmop4a[_1x2]_za64[_s16_s16]

ISA classification: SME2 + FEAT_SME_MOP4, FEAT_SME_I16I64

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmop4a%5B_1x2%5D_za64%5B_s16_s16%5D

### Signature (source notation)

```c
void svmop4a[_1x2]_za64[_s16_s16](uint64_t tile, svint16_t zn, svint16x2_t zm)
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
    "register": "Zreg1.H"
  },
  "zm": {
    "Z multi-vector": "{ Zreg2.H, Zreg3.H }"
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
SMOP4A ZA0.D, Zreg1.H, { Zreg2.H, Zreg3.H }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/SMOP4A--4-way---Signed-integer-quarter-tile-sum-of-outer-products--accumulating-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmop4a[_1x2]_za64[_s16_u16]

ISA classification: SME2 + FEAT_SME_MOP4, FEAT_SME_I16I64

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmop4a%5B_1x2%5D_za64%5B_s16_u16%5D

### Signature (source notation)

```c
void svmop4a[_1x2]_za64[_s16_u16](uint64_t tile, svint16_t zn, svuint16x2_t zm)
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
    "register": "Zreg1.H"
  },
  "zm": {
    "Z multi-vector": "{ Zreg2.H, Zreg3.H }"
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
SUMOP4A ZA0.D, Zreg1.H, { Zreg2.H, Zreg3.H }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/SUMOP4A--Signed-by-unsigned-integer-quarter-tile-sum-of-outer-products--accumulating-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmop4a[_1x2]_za64[_u16_s16]

ISA classification: SME2 + FEAT_SME_MOP4, FEAT_SME_I16I64

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmop4a%5B_1x2%5D_za64%5B_u16_s16%5D

### Signature (source notation)

```c
void svmop4a[_1x2]_za64[_u16_s16](uint64_t tile, svuint16_t zn, svint16x2_t zm)
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
    "register": "Zreg1.H"
  },
  "zm": {
    "Z multi-vector": "{ Zreg2.H, Zreg3.H }"
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
USMOP4A ZA0.D, Zreg1.H, { Zreg2.H, Zreg3.H }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/USMOP4A--Unsigned-by-signed-integer-quarter-tile-sum-of-outer-products--accumulating-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmop4a[_1x2]_za64[_u16_u16]

ISA classification: SME2 + FEAT_SME_MOP4, FEAT_SME_I16I64

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmop4a%5B_1x2%5D_za64%5B_u16_u16%5D

### Signature (source notation)

```c
void svmop4a[_1x2]_za64[_u16_u16](uint64_t tile, svuint16_t zn, svuint16x2_t zm)
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
    "register": "Zreg1.H"
  },
  "zm": {
    "Z multi-vector": "{ Zreg2.H, Zreg3.H }"
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
UMOP4A ZA0.D, Zreg1.H, { Zreg2.H, Zreg3.H }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/UMOP4A--4-way---Unsigned-integer-quarter-tile-sum-of-outer-products--accumulating-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmop4a[_2x1]_za16[_bf16_bf16]

ISA classification: SME2 + FEAT_SME_MOP4, FEAT_SME_B16B16

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmop4a%5B_2x1%5D_za16%5B_bf16_bf16%5D

### Signature (source notation)

```c
void svmop4a[_2x1]_za16[_bf16_bf16](uint64_t tile, svbfloat16x2_t zn, svbfloat16_t zm)
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
BFMOP4A ZA0.H, { Zreg1.H, Zreg2.H }, Zreg3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/BFMOP4A--non-widening---BFloat16-quarter-tile-outer-product--accumulating-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmop4a[_2x1]_za16[_f16_f16]

ISA classification: SME2 + FEAT_SME_MOP4, FEAT_SME_F16F16

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmop4a%5B_2x1%5D_za16%5B_f16_f16%5D

### Signature (source notation)

```c
void svmop4a[_2x1]_za16[_f16_f16](uint64_t tile, svfloat16x2_t zn, svfloat16_t zm)
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
FMOP4A ZA0.H, { Zreg1.H, Zreg2.H }, Zreg3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/FMOP4A--non-widening---Floating-point-quarter-tile-outer-product--accumulating-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmop4a[_2x1]_za16[_mf8_mf8]_fpm

ISA classification: SME2 + FEAT_SME_MOP4, FEAT_SME_F8F16

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmop4a%5B_2x1%5D_za16%5B_mf8_mf8%5D_fpm

### Signature (source notation)

```c
void svmop4a[_2x1]_za16[_mf8_mf8]_fpm(uint64_t tile, svmfloat8x2_t zn, svmfloat8_t zm, fpm_t fpm)
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
FMOP4A ZA0.H, { Zreg1.B, Zreg2.B }, Zreg3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/FMOP4A--widening--2-way--FP8-to-FP16---8-bit-floating-point-quarter-tile-sum-of-outer-products-to-half-precision--accumulating-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmop4a[_2x1]_za32[_bf16_bf16]

ISA classification: SME2 + FEAT_SME_MOP4

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmop4a%5B_2x1%5D_za32%5B_bf16_bf16%5D

### Signature (source notation)

```c
void svmop4a[_2x1]_za32[_bf16_bf16](uint64_t tile, svbfloat16x2_t zn, svbfloat16_t zm)
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
BFMOP4A ZA0.S, { Zreg1.H, Zreg2.H }, Zreg3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/BFMOP4A--widening---BFloat16-quarter-tile-sum-of-outer-products-to-single-precision--accumulating-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmop4a[_2x1]_za32[_f16_f16]

ISA classification: SME2 + FEAT_SME_MOP4

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmop4a%5B_2x1%5D_za32%5B_f16_f16%5D

### Signature (source notation)

```c
void svmop4a[_2x1]_za32[_f16_f16](uint64_t tile, svfloat16x2_t zn, svfloat16_t zm)
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
FMOP4A ZA0.S, { Zreg1.H, Zreg2.H }, Zreg3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/FMOP4A--widening--2-way--FP16-to-FP32---Half-precision-quarter-tile-sum-of-outer-products-to-single-precision--accumulating-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmop4a[_2x1]_za32[_f32_f32]

ISA classification: SME2 + FEAT_SME_MOP4

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmop4a%5B_2x1%5D_za32%5B_f32_f32%5D

### Signature (source notation)

```c
void svmop4a[_2x1]_za32[_f32_f32](uint64_t tile, svfloat32x2_t zn, svfloat32_t zm)
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
    "register": "Zreg3.S"
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
FMOP4A ZA0.S, { Zreg1.S, Zreg2.S }, Zreg3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/FMOP4A--non-widening---Floating-point-quarter-tile-outer-product--accumulating-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmop4a[_2x1]_za32[_mf8_mf8]_fpm

ISA classification: SME2 + FEAT_SME_MOP4, FEAT_SME_F8F32

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmop4a%5B_2x1%5D_za32%5B_mf8_mf8%5D_fpm

### Signature (source notation)

```c
void svmop4a[_2x1]_za32[_mf8_mf8]_fpm(uint64_t tile, svmfloat8x2_t zn, svmfloat8_t zm, fpm_t fpm)
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
FMOP4A ZA0.S, { Zreg1.B, Zreg2.B }, Zreg3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/FMOP4A--widening--4-way---8-bit-floating-point-quarter-tile-sum-of-outer-products-to-single-precision--accumulating-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmop4a[_2x1]_za32[_s16_s16]

ISA classification: SME2 + FEAT_SME_MOP4

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmop4a%5B_2x1%5D_za32%5B_s16_s16%5D

### Signature (source notation)

```c
void svmop4a[_2x1]_za32[_s16_s16](uint64_t tile, svint16x2_t zn, svint16_t zm)
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
SMOP4A ZA0.S, { Zreg1.H, Zreg2.H }, Zreg3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/SMOP4A--2-way---Signed-16-bit-integer-quarter-tile-sum-of-outer-products-to-32-bit-integer--accumulating-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmop4a[_2x1]_za32[_s8_s8]

ISA classification: SME2 + FEAT_SME_MOP4

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmop4a%5B_2x1%5D_za32%5B_s8_s8%5D

### Signature (source notation)

```c
void svmop4a[_2x1]_za32[_s8_s8](uint64_t tile, svint8x2_t zn, svint8_t zm)
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
SMOP4A ZA0.S, { Zreg1.B, Zreg2.B }, Zreg3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/SMOP4A--4-way---Signed-integer-quarter-tile-sum-of-outer-products--accumulating-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmop4a[_2x1]_za32[_s8_u8]

ISA classification: SME2 + FEAT_SME_MOP4

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmop4a%5B_2x1%5D_za32%5B_s8_u8%5D

### Signature (source notation)

```c
void svmop4a[_2x1]_za32[_s8_u8](uint64_t tile, svint8x2_t zn, svuint8_t zm)
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
SUMOP4A ZA0.S, { Zreg1.B, Zreg2.B }, Zreg3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/SUMOP4A--Signed-by-unsigned-integer-quarter-tile-sum-of-outer-products--accumulating-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmop4a[_2x1]_za32[_u16_u16]

ISA classification: SME2 + FEAT_SME_MOP4

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmop4a%5B_2x1%5D_za32%5B_u16_u16%5D

### Signature (source notation)

```c
void svmop4a[_2x1]_za32[_u16_u16](uint64_t tile, svuint16x2_t zn, svuint16_t zm)
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
UMOP4A ZA0.S, { Zreg1.H, Zreg2.H }, Zreg3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/UMOP4A--2-way---Unsigned-16-bit-integer-quarter-tile-sum-of-outer-products-to-32-bit-integer--accumulating-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmop4a[_2x1]_za32[_u8_s8]

ISA classification: SME2 + FEAT_SME_MOP4

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmop4a%5B_2x1%5D_za32%5B_u8_s8%5D

### Signature (source notation)

```c
void svmop4a[_2x1]_za32[_u8_s8](uint64_t tile, svuint8x2_t zn, svint8_t zm)
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
USMOP4A ZA0.S, { Zreg1.B, Zreg2.B }, Zreg3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/USMOP4A--Unsigned-by-signed-integer-quarter-tile-sum-of-outer-products--accumulating-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

