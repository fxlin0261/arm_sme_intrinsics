# SME2 / Shift / Right / Vector saturating rounding shift right and narrow — Part 1

## svqrshr[_n]_s16[_s32_x2]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqrshr%5B_n%5D_s16%5B_s32_x2%5D

### Signature (source notation)

```c
svint16_t svqrshr[_n]_s16[_s32_x2](svint32x2_t zn, uint64_t imm)
    __arm_streaming;
```

### Description

Multi-vector signed saturating rounding shift right narrow by immediate

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Shift / Right / Vector saturating rounding shift right and narrow

- SME attributes: `__arm_streaming`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2
```

### Return type metadata

```json
{
  "return_base_type": "int16",
  "element_bit_size": "16",
  "value": "svint16_t"
}
```

### Argument preparation and constraints

```json
{
  "zn": {
    "Z multi-vector": "{ Zreg2.S, Zreg3.S }"
  },
  "imm": {
    "immediate": "imm1"
  }
}
```

### Result mapping

```json
[
  {
    "Zreg1.H": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
SQRSHR Zreg1.H, { Zreg2.S, Zreg3.S }, #imm1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SQRSHR--two-registers---Multi-vector-signed-saturating-rounding-shift-right-narrow-by-immediate-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svqrshr[_n]_s16[_s64_x4]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqrshr%5B_n%5D_s16%5B_s64_x4%5D

### Signature (source notation)

```c
svint16_t svqrshr[_n]_s16[_s64_x4](svint64x4_t zn, uint64_t imm)
    __arm_streaming;
```

### Description

Multi-vector signed saturating rounding shift right narrow by immediate

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Shift / Right / Vector saturating rounding shift right and narrow

- SME attributes: `__arm_streaming`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2
```

### Return type metadata

```json
{
  "return_base_type": "int16",
  "element_bit_size": "16",
  "value": "svint16_t"
}
```

### Argument preparation and constraints

```json
{
  "zn": {
    "Z multi-vector": "{ Zreg2.D - Zreg3.D }"
  },
  "imm": {
    "immediate": "imm1"
  }
}
```

### Result mapping

```json
[
  {
    "Zreg1.H": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
SQRSHR Zreg1.H, { Zreg2.D - Zreg3.D }, #imm1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SQRSHR--four-registers---Multi-vector-signed-saturating-rounding-shift-right-narrow-by-immediate-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svqrshr[_n]_s8[_s32_x4]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqrshr%5B_n%5D_s8%5B_s32_x4%5D

### Signature (source notation)

```c
svint8_t svqrshr[_n]_s8[_s32_x4](svint32x4_t zn, uint64_t imm)
    __arm_streaming;
```

### Description

Multi-vector signed saturating rounding shift right narrow by immediate

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Shift / Right / Vector saturating rounding shift right and narrow

- SME attributes: `__arm_streaming`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2
```

### Return type metadata

```json
{
  "return_base_type": "int8",
  "element_bit_size": "8",
  "value": "svint8_t"
}
```

### Argument preparation and constraints

```json
{
  "zn": {
    "Z multi-vector": "{ Zreg2.S - Zreg3.S }"
  },
  "imm": {
    "immediate": "imm1"
  }
}
```

### Result mapping

```json
[
  {
    "Zreg1.B": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
SQRSHR Zreg1.B, { Zreg2.S - Zreg3.S }, #imm1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SQRSHR--four-registers---Multi-vector-signed-saturating-rounding-shift-right-narrow-by-immediate-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svqrshr[_n]_u16[_u32_x2]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqrshr%5B_n%5D_u16%5B_u32_x2%5D

### Signature (source notation)

```c
svuint16_t svqrshr[_n]_u16[_u32_x2](svuint32x2_t zn, uint64_t imm)
    __arm_streaming;
```

### Description

Multi-vector unsigned saturating rounding shift right narrow by immediate

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Shift / Right / Vector saturating rounding shift right and narrow

- SME attributes: `__arm_streaming`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2
```

### Return type metadata

```json
{
  "return_base_type": "uint16",
  "element_bit_size": "16",
  "value": "svuint16_t"
}
```

### Argument preparation and constraints

```json
{
  "zn": {
    "Z multi-vector": "{ Zreg2.S, Zreg3.S }"
  },
  "imm": {
    "immediate": "imm1"
  }
}
```

### Result mapping

```json
[
  {
    "Zreg1.H": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
UQRSHR Zreg1.H, { Zreg2.S, Zreg3.S }, #imm1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/UQRSHR--two-registers---Multi-vector-unsigned-saturating-rounding-shift-right-narrow-by-immediate-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svqrshr[_n]_u16[_u64_x4]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqrshr%5B_n%5D_u16%5B_u64_x4%5D

### Signature (source notation)

```c
svuint16_t svqrshr[_n]_u16[_u64_x4](svuint64x4_t zn, uint64_t imm)
    __arm_streaming;
```

### Description

Multi-vector unsigned saturating rounding shift right narrow by immediate

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Shift / Right / Vector saturating rounding shift right and narrow

- SME attributes: `__arm_streaming`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2
```

### Return type metadata

```json
{
  "return_base_type": "uint16",
  "element_bit_size": "16",
  "value": "svuint16_t"
}
```

### Argument preparation and constraints

```json
{
  "zn": {
    "Z multi-vector": "{ Zreg2.D - Zreg3.D }"
  },
  "imm": {
    "immediate": "imm1"
  }
}
```

### Result mapping

```json
[
  {
    "Zreg1.H": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
UQRSHR Zreg1.H, { Zreg2.D - Zreg3.D }, #imm1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/UQRSHR--four-registers---Multi-vector-unsigned-saturating-rounding-shift-right-narrow-by-immediate-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svqrshr[_n]_u8[_u32_x4]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqrshr%5B_n%5D_u8%5B_u32_x4%5D

### Signature (source notation)

```c
svuint8_t svqrshr[_n]_u8[_u32_x4](svuint32x4_t zn, uint64_t imm)
    __arm_streaming;
```

### Description

Multi-vector unsigned saturating rounding shift right narrow by immediate

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Shift / Right / Vector saturating rounding shift right and narrow

- SME attributes: `__arm_streaming`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2
```

### Return type metadata

```json
{
  "return_base_type": "uint8",
  "element_bit_size": "8",
  "value": "svuint8_t"
}
```

### Argument preparation and constraints

```json
{
  "zn": {
    "Z multi-vector": "{ Zreg2.S - Zreg3.S }"
  },
  "imm": {
    "immediate": "imm1"
  }
}
```

### Result mapping

```json
[
  {
    "Zreg1.B": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
UQRSHR Zreg1.B, { Zreg2.S - Zreg3.S }, #imm1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/UQRSHR--four-registers---Multi-vector-unsigned-saturating-rounding-shift-right-narrow-by-immediate-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svqrshrn[_n]_s16[_s32_x2]

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqrshrn%5B_n%5D_s16%5B_s32_x2%5D

### Signature (source notation)

```c
svint16_t svqrshrn[_n]_s16[_s32_x2](svint32x2_t zn, uint64_t imm);
```

### Description

Signed saturating rounding shift right narrow by immediate and interleave

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Shift / Right / Vector saturating rounding shift right and narrow

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p1)|FEAT_SME2
```

### Return type metadata

```json
{
  "return_base_type": "int16",
  "element_bit_size": "16",
  "value": "svint16_t"
}
```

### Argument preparation and constraints

```json
{
  "zn": {
    "Z multi-vector": "{ Zreg2.S, Zreg3.S }"
  },
  "imm": {
    "immediate": "imm1"
  }
}
```

### Result mapping

```json
[
  {
    "Zreg1.H": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
SQRSHRN Zreg1.H, { Zreg2.S, Zreg3.S }, #imm1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQRSHRN--Signed-saturating-rounding-shift-right-narrow-by-immediate-and-interleave-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svqrshrn[_n]_s16[_s64_x4]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqrshrn%5B_n%5D_s16%5B_s64_x4%5D

### Signature (source notation)

```c
svint16_t svqrshrn[_n]_s16[_s64_x4](svint64x4_t zn, uint64_t imm)
    __arm_streaming;
```

### Description

Multi-vector signed saturating rounding shift right narrow by immediate and interleave

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Shift / Right / Vector saturating rounding shift right and narrow

- SME attributes: `__arm_streaming`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2
```

### Return type metadata

```json
{
  "return_base_type": "int16",
  "element_bit_size": "16",
  "value": "svint16_t"
}
```

### Argument preparation and constraints

```json
{
  "zn": {
    "Z multi-vector": "{ Zreg2.D - Zreg3.D }"
  },
  "imm": {
    "immediate": "imm1"
  }
}
```

### Result mapping

```json
[
  {
    "Zreg1.H": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
SQRSHRN Zreg1.H, { Zreg2.D - Zreg3.D }, #imm1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SQRSHRN--Multi-vector-signed-saturating-rounding-shift-right-narrow-by-immediate-and-interleave-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svqrshrn[_n]_s8[_s32_x4]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqrshrn%5B_n%5D_s8%5B_s32_x4%5D

### Signature (source notation)

```c
svint8_t svqrshrn[_n]_s8[_s32_x4](svint32x4_t zn, uint64_t imm)
    __arm_streaming;
```

### Description

Multi-vector signed saturating rounding shift right narrow by immediate and interleave

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Shift / Right / Vector saturating rounding shift right and narrow

- SME attributes: `__arm_streaming`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2
```

### Return type metadata

```json
{
  "return_base_type": "int8",
  "element_bit_size": "8",
  "value": "svint8_t"
}
```

### Argument preparation and constraints

```json
{
  "zn": {
    "Z multi-vector": "{ Zreg2.S - Zreg3.S }"
  },
  "imm": {
    "immediate": "imm1"
  }
}
```

### Result mapping

```json
[
  {
    "Zreg1.B": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
SQRSHRN Zreg1.B, { Zreg2.S - Zreg3.S }, #imm1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SQRSHRN--Multi-vector-signed-saturating-rounding-shift-right-narrow-by-immediate-and-interleave-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svqrshrn[_n]_u16[_u32_x2]

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqrshrn%5B_n%5D_u16%5B_u32_x2%5D

### Signature (source notation)

```c
svuint16_t svqrshrn[_n]_u16[_u32_x2](svuint32x2_t zn, uint64_t imm);
```

### Description

Unsigned saturating rounding shift right narrow by immediate and interleave

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Shift / Right / Vector saturating rounding shift right and narrow

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p1)|FEAT_SME2
```

### Return type metadata

```json
{
  "return_base_type": "uint16",
  "element_bit_size": "16",
  "value": "svuint16_t"
}
```

### Argument preparation and constraints

```json
{
  "zn": {
    "Z multi-vector": "{ Zreg2.S, Zreg3.S }"
  },
  "imm": {
    "immediate": "imm1"
  }
}
```

### Result mapping

```json
[
  {
    "Zreg1.H": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
UQRSHRN Zreg1.H, { Zreg2.S, Zreg3.S }, #imm1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQRSHRN--Unsigned-saturating-rounding-shift-right-narrow-by-immediate-and-interleave-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svqrshrn[_n]_u16[_u64_x4]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqrshrn%5B_n%5D_u16%5B_u64_x4%5D

### Signature (source notation)

```c
svuint16_t svqrshrn[_n]_u16[_u64_x4](svuint64x4_t zn, uint64_t imm)
    __arm_streaming;
```

### Description

Multi-vector unsigned saturating rounding shift right narrow by immediate and interleave

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Shift / Right / Vector saturating rounding shift right and narrow

- SME attributes: `__arm_streaming`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2
```

### Return type metadata

```json
{
  "return_base_type": "uint16",
  "element_bit_size": "16",
  "value": "svuint16_t"
}
```

### Argument preparation and constraints

```json
{
  "zn": {
    "Z multi-vector": "{ Zreg2.D - Zreg3.D }"
  },
  "imm": {
    "immediate": "imm1"
  }
}
```

### Result mapping

```json
[
  {
    "Zreg1.H": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
UQRSHRN Zreg1.H, { Zreg2.D - Zreg3.D }, #imm1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/UQRSHRN--Multi-vector-unsigned-saturating-rounding-shift-right-narrow-by-immediate-and-interleave-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svqrshrn[_n]_u8[_u32_x4]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqrshrn%5B_n%5D_u8%5B_u32_x4%5D

### Signature (source notation)

```c
svuint8_t svqrshrn[_n]_u8[_u32_x4](svuint32x4_t zn, uint64_t imm)
    __arm_streaming;
```

### Description

Multi-vector unsigned saturating rounding shift right narrow by immediate and interleave

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Shift / Right / Vector saturating rounding shift right and narrow

- SME attributes: `__arm_streaming`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2
```

### Return type metadata

```json
{
  "return_base_type": "uint8",
  "element_bit_size": "8",
  "value": "svuint8_t"
}
```

### Argument preparation and constraints

```json
{
  "zn": {
    "Z multi-vector": "{ Zreg2.S - Zreg3.S }"
  },
  "imm": {
    "immediate": "imm1"
  }
}
```

### Result mapping

```json
[
  {
    "Zreg1.B": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
UQRSHRN Zreg1.B, { Zreg2.S - Zreg3.S }, #imm1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/UQRSHRN--Multi-vector-unsigned-saturating-rounding-shift-right-narrow-by-immediate-and-interleave-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svqrshru[_n]_u16[_s32_x2]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqrshru%5B_n%5D_u16%5B_s32_x2%5D

### Signature (source notation)

```c
svuint16_t svqrshru[_n]_u16[_s32_x2](svint32x2_t zn, uint64_t imm)
    __arm_streaming;
```

### Description

Multi-vector signed saturating rounding shift right unsigned narrow by immediate

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Shift / Right / Vector saturating rounding shift right and narrow

- SME attributes: `__arm_streaming`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2
```

### Return type metadata

```json
{
  "return_base_type": "uint16",
  "element_bit_size": "16",
  "value": "svuint16_t"
}
```

### Argument preparation and constraints

```json
{
  "zn": {
    "Z multi-vector": "{ Zreg2.S, Zreg3.S }"
  },
  "imm": {
    "immediate": "imm1"
  }
}
```

### Result mapping

```json
[
  {
    "Zreg1.H": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
SQRSHRU Zreg1.H, { Zreg2.S, Zreg3.S }, #imm1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SQRSHRU--two-registers---Multi-vector-signed-saturating-rounding-shift-right-unsigned-narrow-by-immediate-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svqrshru[_n]_u16[_s64_x4]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqrshru%5B_n%5D_u16%5B_s64_x4%5D

### Signature (source notation)

```c
svuint16_t svqrshru[_n]_u16[_s64_x4](svint64x4_t zn, uint64_t imm)
    __arm_streaming;
```

### Description

Multi-vector signed saturating rounding shift right unsigned narrow by immediate

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Shift / Right / Vector saturating rounding shift right and narrow

- SME attributes: `__arm_streaming`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2
```

### Return type metadata

```json
{
  "return_base_type": "uint16",
  "element_bit_size": "16",
  "value": "svuint16_t"
}
```

### Argument preparation and constraints

```json
{
  "zn": {
    "Z multi-vector": "{ Zreg2.D - Zreg3.D }"
  },
  "imm": {
    "immediate": "imm1"
  }
}
```

### Result mapping

```json
[
  {
    "Zreg1.H": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
SQRSHRU Zreg1.H, { Zreg2.D - Zreg3.D }, #imm1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SQRSHRU--four-registers---Multi-vector-signed-saturating-rounding-shift-right-unsigned-narrow-by-immediate-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svqrshru[_n]_u8[_s32_x4]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqrshru%5B_n%5D_u8%5B_s32_x4%5D

### Signature (source notation)

```c
svuint8_t svqrshru[_n]_u8[_s32_x4](svint32x4_t zn, uint64_t imm)
    __arm_streaming;
```

### Description

Multi-vector signed saturating rounding shift right unsigned narrow by immediate

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Shift / Right / Vector saturating rounding shift right and narrow

- SME attributes: `__arm_streaming`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2
```

### Return type metadata

```json
{
  "return_base_type": "uint8",
  "element_bit_size": "8",
  "value": "svuint8_t"
}
```

### Argument preparation and constraints

```json
{
  "zn": {
    "Z multi-vector": "{ Zreg2.S - Zreg3.S }"
  },
  "imm": {
    "immediate": "imm1"
  }
}
```

### Result mapping

```json
[
  {
    "Zreg1.B": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
SQRSHRU Zreg1.B, { Zreg2.S - Zreg3.S }, #imm1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SQRSHRU--four-registers---Multi-vector-signed-saturating-rounding-shift-right-unsigned-narrow-by-immediate-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svqrshrun[_n]_u16[_s32_x2]

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqrshrun%5B_n%5D_u16%5B_s32_x2%5D

### Signature (source notation)

```c
svuint16_t svqrshrun[_n]_u16[_s32_x2](svint32x2_t zn, uint64_t imm);
```

### Description

Signed saturating rounding shift right unsigned narrow by immediate and interleave

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Shift / Right / Vector saturating rounding shift right and narrow

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p1)|FEAT_SME2
```

### Return type metadata

```json
{
  "return_base_type": "uint16",
  "element_bit_size": "16",
  "value": "svuint16_t"
}
```

### Argument preparation and constraints

```json
{
  "zn": {
    "Z multi-vector": "{ Zreg2.S, Zreg3.S }"
  },
  "imm": {
    "immediate": "imm1"
  }
}
```

### Result mapping

```json
[
  {
    "Zreg1.H": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
SQRSHRUN Zreg1.H, { Zreg2.S, Zreg3.S }, #imm1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQRSHRUN--Signed-saturating-rounding-shift-right-unsigned-narrow-by-immediate-and-interleave-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svqrshrun[_n]_u16[_s64_x4]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqrshrun%5B_n%5D_u16%5B_s64_x4%5D

### Signature (source notation)

```c
svuint16_t svqrshrun[_n]_u16[_s64_x4](svint64x4_t zn, uint64_t imm)
    __arm_streaming;
```

### Description

Multi-vector signed saturating rounding shift right unsigned narrow by immediate and interleave

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Shift / Right / Vector saturating rounding shift right and narrow

- SME attributes: `__arm_streaming`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2
```

### Return type metadata

```json
{
  "return_base_type": "uint16",
  "element_bit_size": "16",
  "value": "svuint16_t"
}
```

### Argument preparation and constraints

```json
{
  "zn": {
    "Z multi-vector": "{ Zreg2.D - Zreg3.D }"
  },
  "imm": {
    "immediate": "imm1"
  }
}
```

### Result mapping

```json
[
  {
    "Zreg1.H": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
SQRSHRUN Zreg1.H, { Zreg2.D - Zreg3.D }, #imm1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SQRSHRUN--Multi-vector-signed-saturating-rounding-shift-right-unsigned-narrow-by-immediate-and-interleave-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svqrshrun[_n]_u8[_s32_x4]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqrshrun%5B_n%5D_u8%5B_s32_x4%5D

### Signature (source notation)

```c
svuint8_t svqrshrun[_n]_u8[_s32_x4](svint32x4_t zn, uint64_t imm)
    __arm_streaming;
```

### Description

Multi-vector signed saturating rounding shift right unsigned narrow by immediate and interleave

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Shift / Right / Vector saturating rounding shift right and narrow

- SME attributes: `__arm_streaming`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2
```

### Return type metadata

```json
{
  "return_base_type": "uint8",
  "element_bit_size": "8",
  "value": "svuint8_t"
}
```

### Argument preparation and constraints

```json
{
  "zn": {
    "Z multi-vector": "{ Zreg2.S - Zreg3.S }"
  },
  "imm": {
    "immediate": "imm1"
  }
}
```

### Result mapping

```json
[
  {
    "Zreg1.B": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
SQRSHRUN Zreg1.B, { Zreg2.S - Zreg3.S }, #imm1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SQRSHRUN--Multi-vector-signed-saturating-rounding-shift-right-unsigned-narrow-by-immediate-and-interleave-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

