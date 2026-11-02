# SME2 / ZA array / Accumulate / Subtract — Part 1

## svsub_za16[_bf16]_vg1x4

ISA classification: SME2 + FEAT_SME_B16B16

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsub_za16%5B_bf16%5D_vg1x4

### Signature (source notation)

```c
void svsub_za16[_bf16]_vg1x4(uint32_t slice, svbfloat16x4_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector BFloat16 subtract from ZA array vectors

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Subtract

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
  "zm": {
    "Z multi-vector": "{ Zreg1.H - Zreg2.H }"
  }
}
```

### Result mapping

```json
[]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
BFSUB ZA.H[Wreg1, imm1, VGX4], { Zreg1.H - Zreg2.H }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/BFSUB--Multi-vector-BFloat16-subtract-from-ZA-array-vectors-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svsub_za16[_f16]_vg1x4

ISA classification: SME2 + FEAT_SME_F16F16 OR SME2 + FEAT_SME_F8F16

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsub_za16%5B_f16%5D_vg1x4

### Signature (source notation)

```c
void svsub_za16[_f16]_vg1x4(uint32_t slice, svfloat16x4_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector floating-point subtract from ZA array vectors

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Subtract

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME_F16F16|FEAT_SME_F8F16
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
  "zm": {
    "Z multi-vector": "{ Zreg1.H - Zreg2.H }"
  }
}
```

### Result mapping

```json
[]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
FSUB ZA.H[Wreg1, imm1, VGX4], { Zreg1.H - Zreg2.H }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/FSUB--Multi-vector-floating-point-subtract-from-ZA-array-vectors-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svsub_za32[_f32]_vg1x2

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsub_za32%5B_f32%5D_vg1x2

### Signature (source notation)

```c
void svsub_za32[_f32]_vg1x2(uint32_t slice, svfloat32x2_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Floating-point subtract multi-vector from ZA array vector accumulators

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Subtract

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
  "zm": {
    "Z multi-vector": "{ Zreg1.S, Zreg2.S }"
  }
}
```

### Result mapping

```json
[]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
FSUB ZA.S[Wreg1, imm1, VGX2], { Zreg1.S, Zreg2.S }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/FSUB--Floating-point-subtract-multi-vector-from-ZA-array-vector-accumulators-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svsub_za32[_f32]_vg1x4

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsub_za32%5B_f32%5D_vg1x4

### Signature (source notation)

```c
void svsub_za32[_f32]_vg1x4(uint32_t slice, svfloat32x4_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Floating-point subtract multi-vector from ZA array vector accumulators

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Subtract

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
  "zm": {
    "Z multi-vector": "{ Zreg1.S - Zreg2.S }"
  }
}
```

### Result mapping

```json
[]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
FSUB ZA.S[Wreg1, imm1, VGX4], { Zreg1.S - Zreg2.S }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/FSUB--Floating-point-subtract-multi-vector-from-ZA-array-vector-accumulators-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svsub_za32[_s32]_vg1x2

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsub_za32%5B_s32%5D_vg1x2

### Signature (source notation)

```c
void svsub_za32[_s32]_vg1x2(uint32_t slice, svint32x2_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Subtract multi-vector from ZA array vector accumulators

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Subtract

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
  "zm": {
    "Z multi-vector": "{ Zreg1.S, Zreg2.S }"
  }
}
```

### Result mapping

```json
[]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
SUB ZA.S[Wreg1, imm1, VGX2], { Zreg1.S, Zreg2.S }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SUB--array-accumulators---Subtract-multi-vector-from-ZA-array-vector-accumulators-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svsub_za32[_s32]_vg1x4

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsub_za32%5B_s32%5D_vg1x4

### Signature (source notation)

```c
void svsub_za32[_s32]_vg1x4(uint32_t slice, svint32x4_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Subtract multi-vector from ZA array vector accumulators

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Subtract

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
  "zm": {
    "Z multi-vector": "{ Zreg1.S - Zreg2.S }"
  }
}
```

### Result mapping

```json
[]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
SUB ZA.S[Wreg1, imm1, VGX4], { Zreg1.S - Zreg2.S }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SUB--array-accumulators---Subtract-multi-vector-from-ZA-array-vector-accumulators-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svsub_za32[_u32]_vg1x2

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsub_za32%5B_u32%5D_vg1x2

### Signature (source notation)

```c
void svsub_za32[_u32]_vg1x2(uint32_t slice, svuint32x2_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Subtract multi-vector from ZA array vector accumulators

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Subtract

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
  "zm": {
    "Z multi-vector": "{ Zreg1.S, Zreg2.S }"
  }
}
```

### Result mapping

```json
[]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
SUB ZA.S[Wreg1, imm1, VGX2], { Zreg1.S, Zreg2.S }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SUB--array-accumulators---Subtract-multi-vector-from-ZA-array-vector-accumulators-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svsub_za32[_u32]_vg1x4

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsub_za32%5B_u32%5D_vg1x4

### Signature (source notation)

```c
void svsub_za32[_u32]_vg1x4(uint32_t slice, svuint32x4_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Subtract multi-vector from ZA array vector accumulators

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Subtract

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
  "zm": {
    "Z multi-vector": "{ Zreg1.S - Zreg2.S }"
  }
}
```

### Result mapping

```json
[]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
SUB ZA.S[Wreg1, imm1, VGX4], { Zreg1.S - Zreg2.S }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SUB--array-accumulators---Subtract-multi-vector-from-ZA-array-vector-accumulators-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svsub_za64[_f64]_vg1x2

ISA classification: SME2 + FEAT_SME_F64F64

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsub_za64%5B_f64%5D_vg1x2

### Signature (source notation)

```c
void svsub_za64[_f64]_vg1x2(uint32_t slice, svfloat64x2_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector floating-point subtract from ZA array vectors

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Subtract

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
  "zm": {
    "Z multi-vector": "{ Zreg1.D, Zreg2.D }"
  }
}
```

### Result mapping

```json
[]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
FSUB ZA.D[Wreg1, imm1, VGX2], { Zreg1.D, Zreg2.D }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/FSUB--Multi-vector-floating-point-subtract-from-ZA-array-vectors-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svsub_za64[_f64]_vg1x4

ISA classification: SME2 + FEAT_SME_F64F64

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsub_za64%5B_f64%5D_vg1x4

### Signature (source notation)

```c
void svsub_za64[_f64]_vg1x4(uint32_t slice, svfloat64x4_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Multi-vector floating-point subtract from ZA array vectors

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Subtract

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
  "zm": {
    "Z multi-vector": "{ Zreg1.D - Zreg2.D }"
  }
}
```

### Result mapping

```json
[]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
FSUB ZA.D[Wreg1, imm1, VGX4], { Zreg1.D - Zreg2.D }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/FSUB--Multi-vector-floating-point-subtract-from-ZA-array-vectors-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svsub_za64[_s64]_vg1x2

ISA classification: SME2 + FEAT_SME_I16I64

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsub_za64%5B_s64%5D_vg1x2

### Signature (source notation)

```c
void svsub_za64[_s64]_vg1x2(uint32_t slice, svint64x2_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Subtract multi-vector from ZA array vector accumulators

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Subtract

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
  "zm": {
    "Z multi-vector": "{ Zreg1.D, Zreg2.D }"
  }
}
```

### Result mapping

```json
[]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
SUB ZA.D[Wreg1, imm1, VGX2], { Zreg1.D, Zreg2.D }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SUB--array-accumulators---Subtract-multi-vector-from-ZA-array-vector-accumulators-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svsub_za64[_s64]_vg1x4

ISA classification: SME2 + FEAT_SME_I16I64

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsub_za64%5B_s64%5D_vg1x4

### Signature (source notation)

```c
void svsub_za64[_s64]_vg1x4(uint32_t slice, svint64x4_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Subtract multi-vector from ZA array vector accumulators

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Subtract

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
  "zm": {
    "Z multi-vector": "{ Zreg1.D - Zreg2.D }"
  }
}
```

### Result mapping

```json
[]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
SUB ZA.D[Wreg1, imm1, VGX4], { Zreg1.D - Zreg2.D }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SUB--array-accumulators---Subtract-multi-vector-from-ZA-array-vector-accumulators-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svsub_za64[_u64]_vg1x2

ISA classification: SME2 + FEAT_SME_I16I64

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsub_za64%5B_u64%5D_vg1x2

### Signature (source notation)

```c
void svsub_za64[_u64]_vg1x2(uint32_t slice, svuint64x2_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Subtract multi-vector from ZA array vector accumulators

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Subtract

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
  "zm": {
    "Z multi-vector": "{ Zreg1.D, Zreg2.D }"
  }
}
```

### Result mapping

```json
[]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
SUB ZA.D[Wreg1, imm1, VGX2], { Zreg1.D, Zreg2.D }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SUB--array-accumulators---Subtract-multi-vector-from-ZA-array-vector-accumulators-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svsub_za64[_u64]_vg1x4

ISA classification: SME2 + FEAT_SME_I16I64

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsub_za64%5B_u64%5D_vg1x4

### Signature (source notation)

```c
void svsub_za64[_u64]_vg1x4(uint32_t slice, svuint64x4_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Subtract multi-vector from ZA array vector accumulators

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Subtract

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
  "zm": {
    "Z multi-vector": "{ Zreg1.D - Zreg2.D }"
  }
}
```

### Result mapping

```json
[]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
SUB ZA.D[Wreg1, imm1, VGX4], { Zreg1.D - Zreg2.D }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SUB--array-accumulators---Subtract-multi-vector-from-ZA-array-vector-accumulators-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

