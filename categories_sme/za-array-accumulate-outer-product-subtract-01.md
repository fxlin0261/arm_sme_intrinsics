# SME / ZA array / Accumulate / Outer product subtract — Part 1

## svmops_za32[_bf16]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmops_za32%5B_bf16%5D_m

### Signature (source notation)

```c
void svmops_za32[_bf16]_m(uint64_t tile, svbool_t pn, svbool_t pm, svbfloat16_t zn, svbfloat16_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

BFloat16 sum of outer products and subtract

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Outer product subtract

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME
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
BFMOPS ZA0.S, Preg1/M, Preg2/M, Zreg1.H, Zreg2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/BFMOPS--widening---BFloat16-sum-of-outer-products-and-subtract-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmops_za32[_f16]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmops_za32%5B_f16%5D_m

### Signature (source notation)

```c
void svmops_za32[_f16]_m(uint64_t tile, svbool_t pn, svbool_t pm, svfloat16_t zn, svfloat16_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Half-precision sum of outer products and subtract

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Outer product subtract

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME
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
FMOPS ZA0.S, Preg1/M, Preg2/M, Zreg1.H, Zreg2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/FMOPS--widening---Half-precision-sum-of-outer-products-and-subtract-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmops_za32[_f32]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmops_za32%5B_f32%5D_m

### Signature (source notation)

```c
void svmops_za32[_f32]_m(uint64_t tile, svbool_t pn, svbool_t pm, svfloat32_t zn, svfloat32_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Floating-point outer product and subtract

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Outer product subtract

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME
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
FMOPS ZA0.S, Preg1/M, Preg2/M, Zreg1.S, Zreg2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/FMOPS--non-widening---Floating-point-outer-product-and-subtract-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmops_za32[_s8]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmops_za32%5B_s8%5D_m

### Signature (source notation)

```c
void svmops_za32[_s8]_m(uint64_t tile, svbool_t pn, svbool_t pm, svint8_t zn, svint8_t zm)
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
FEAT_SME
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
  }
}
```

### Result mapping

```json
[]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
SMOPS ZA0.S, Preg1/M, Preg2/M, Zreg1.B, Zreg2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SMOPS--4-way---Signed-integer-sum-of-outer-products-and-subtract-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmops_za32[_u8]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmops_za32%5B_u8%5D_m

### Signature (source notation)

```c
void svmops_za32[_u8]_m(uint64_t tile, svbool_t pn, svbool_t pm, svuint8_t zn, svuint8_t zm)
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
FEAT_SME
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
  }
}
```

### Result mapping

```json
[]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
UMOPS ZA0.S, Preg1/M, Preg2/M, Zreg1.B, Zreg2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/UMOPS--4-way---Unsigned-integer-sum-of-outer-products-and-subtract-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmops_za64[_f64]_m

ISA classification: SME + FEAT_SME_F64F64

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmops_za64%5B_f64%5D_m

### Signature (source notation)

```c
void svmops_za64[_f64]_m(uint64_t tile, svbool_t pn, svbool_t pm, svfloat64_t zn, svfloat64_t zm)
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
FEAT_SME_F64F64
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
  "pn": {
    "register": "Preg1"
  },
  "pm": {
    "register": "Preg2"
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
FMOPS ZA0.D, Preg1/M, Preg2/M, Zreg1.D, Zreg2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/FMOPS--non-widening---Floating-point-outer-product--subtracting-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmops_za64[_s16]_m

ISA classification: SME + FEAT_SME_I16I64

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmops_za64%5B_s16%5D_m

### Signature (source notation)

```c
void svmops_za64[_s16]_m(uint64_t tile, svbool_t pn, svbool_t pm, svint16_t zn, svint16_t zm)
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
FEAT_SME_I16I64
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
SMOPS ZA0.D, Preg1/M, Preg2/M, Zreg1.H, Zreg2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SMOPS--4-way---Signed-integer-sum-of-outer-products-and-subtract-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmops_za64[_u16]_m

ISA classification: SME + FEAT_SME_I16I64

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmops_za64%5B_u16%5D_m

### Signature (source notation)

```c
void svmops_za64[_u16]_m(uint64_t tile, svbool_t pn, svbool_t pm, svuint16_t zn, svuint16_t zm)
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
FEAT_SME_I16I64
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
UMOPS ZA0.D, Preg1/M, Preg2/M, Zreg1.H, Zreg2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/UMOPS--4-way---Unsigned-integer-sum-of-outer-products-and-subtract-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svsumops_za32[_s8]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsumops_za32%5B_s8%5D_m

### Signature (source notation)

```c
void svsumops_za32[_s8]_m(uint64_t tile, svbool_t pn, svbool_t pm, svint8_t zn, svuint8_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Signed by unsigned integer sum of outer products and subtract

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Outer product subtract

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME
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
  }
}
```

### Result mapping

```json
[]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
SUMOPS ZA0.S, Preg1/M, Preg2/M, Zreg1.B, Zreg2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SUMOPS--Signed-by-unsigned-integer-sum-of-outer-products-and-subtract-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svsumops_za64[_s16]_m

ISA classification: SME + FEAT_SME_I16I64

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsumops_za64%5B_s16%5D_m

### Signature (source notation)

```c
void svsumops_za64[_s16]_m(uint64_t tile, svbool_t pn, svbool_t pm, svint16_t zn, svuint16_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Signed by unsigned integer sum of outer products and subtract

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Outer product subtract

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME_I16I64
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
SUMOPS ZA0.D, Preg1/M, Preg2/M, Zreg1.H, Zreg2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SUMOPS--Signed-by-unsigned-integer-sum-of-outer-products-and-subtract-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svusmops_za32[_u8]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svusmops_za32%5B_u8%5D_m

### Signature (source notation)

```c
void svusmops_za32[_u8]_m(uint64_t tile, svbool_t pn, svbool_t pm, svuint8_t zn, svint8_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Unsigned by signed integer sum of outer products and subtract

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Outer product subtract

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME
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
  }
}
```

### Result mapping

```json
[]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
USMOPS ZA0.S, Preg1/M, Preg2/M, Zreg1.B, Zreg2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/USMOPS--Unsigned-by-signed-integer-sum-of-outer-products-and-subtract-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svusmops_za64[_u16]_m

ISA classification: SME + FEAT_SME_I16I64

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svusmops_za64%5B_u16%5D_m

### Signature (source notation)

```c
void svusmops_za64[_u16]_m(uint64_t tile, svbool_t pn, svbool_t pm, svuint16_t zn, svint16_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Unsigned by signed integer sum of outer products and subtract

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Outer product subtract

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME_I16I64
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
USMOPS ZA0.D, Preg1/M, Preg2/M, Zreg1.H, Zreg2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/USMOPS--Unsigned-by-signed-integer-sum-of-outer-products-and-subtract-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

