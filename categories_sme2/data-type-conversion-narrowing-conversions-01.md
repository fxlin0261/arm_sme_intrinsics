# SME2 / Data type conversion / Narrowing conversions — Part 1

## svqcvt_s16[_s32_x2]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqcvt_s16%5B_s32_x2%5D

### Signature (source notation)

```c
svint16_t svqcvt_s16[_s32_x2](svint32x2_t zn)
    __arm_streaming;
```

### Description

Multi-vector signed saturating extract narrow

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Data type conversion / Narrowing conversions

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
SQCVT Zreg1.H, { Zreg2.S, Zreg3.S }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SQCVT--two-registers---Multi-vector-signed-saturating-extract-narrow-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svqcvt_s16[_s64_x4]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqcvt_s16%5B_s64_x4%5D

### Signature (source notation)

```c
svint16_t svqcvt_s16[_s64_x4](svint64x4_t zn)
    __arm_streaming;
```

### Description

Multi-vector signed saturating extract narrow

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Data type conversion / Narrowing conversions

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
SQCVT Zreg1.H, { Zreg2.D - Zreg3.D }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SQCVT--four-registers---Multi-vector-signed-saturating-extract-narrow-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svqcvt_s8[_s32_x4]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqcvt_s8%5B_s32_x4%5D

### Signature (source notation)

```c
svint8_t svqcvt_s8[_s32_x4](svint32x4_t zn)
    __arm_streaming;
```

### Description

Multi-vector signed saturating extract narrow

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Data type conversion / Narrowing conversions

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
SQCVT Zreg1.B, { Zreg2.S - Zreg3.S }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SQCVT--four-registers---Multi-vector-signed-saturating-extract-narrow-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svqcvt_u16[_s32_x2]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqcvt_u16%5B_s32_x2%5D

### Signature (source notation)

```c
svuint16_t svqcvt_u16[_s32_x2](svint32x2_t zn)
    __arm_streaming;
```

### Description

Multi-vector signed saturating unsigned extract narrow

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Data type conversion / Narrowing conversions

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
SQCVTU Zreg1.H, { Zreg2.S, Zreg3.S }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SQCVTU--two-registers---Multi-vector-signed-saturating-unsigned-extract-narrow-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svqcvt_u16[_s64_x4]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqcvt_u16%5B_s64_x4%5D

### Signature (source notation)

```c
svuint16_t svqcvt_u16[_s64_x4](svint64x4_t zn)
    __arm_streaming;
```

### Description

Multi-vector signed saturating unsigned extract narrow

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Data type conversion / Narrowing conversions

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
SQCVTU Zreg1.H, { Zreg2.D - Zreg3.D }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SQCVTU--four-registers---Multi-vector-signed-saturating-unsigned-extract-narrow-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svqcvt_u16[_u32_x2]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqcvt_u16%5B_u32_x2%5D

### Signature (source notation)

```c
svuint16_t svqcvt_u16[_u32_x2](svuint32x2_t zn)
    __arm_streaming;
```

### Description

Multi-vector unsigned saturating extract narrow

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Data type conversion / Narrowing conversions

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
UQCVT Zreg1.H, { Zreg2.S, Zreg3.S }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/UQCVT--two-registers---Multi-vector-unsigned-saturating-extract-narrow-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svqcvt_u16[_u64_x4]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqcvt_u16%5B_u64_x4%5D

### Signature (source notation)

```c
svuint16_t svqcvt_u16[_u64_x4](svuint64x4_t zn)
    __arm_streaming;
```

### Description

Multi-vector unsigned saturating extract narrow

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Data type conversion / Narrowing conversions

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
UQCVT Zreg1.H, { Zreg2.D - Zreg3.D }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/UQCVT--four-registers---Multi-vector-unsigned-saturating-extract-narrow-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svqcvt_u8[_s32_x4]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqcvt_u8%5B_s32_x4%5D

### Signature (source notation)

```c
svuint8_t svqcvt_u8[_s32_x4](svint32x4_t zn)
    __arm_streaming;
```

### Description

Multi-vector signed saturating unsigned extract narrow

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Data type conversion / Narrowing conversions

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
SQCVTU Zreg1.B, { Zreg2.S - Zreg3.S }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SQCVTU--four-registers---Multi-vector-signed-saturating-unsigned-extract-narrow-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svqcvt_u8[_u32_x4]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqcvt_u8%5B_u32_x4%5D

### Signature (source notation)

```c
svuint8_t svqcvt_u8[_u32_x4](svuint32x4_t zn)
    __arm_streaming;
```

### Description

Multi-vector unsigned saturating extract narrow

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Data type conversion / Narrowing conversions

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
UQCVT Zreg1.B, { Zreg2.S - Zreg3.S }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/UQCVT--four-registers---Multi-vector-unsigned-saturating-extract-narrow-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svqcvtn_s16[_s64_x4]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqcvtn_s16%5B_s64_x4%5D

### Signature (source notation)

```c
svint16_t svqcvtn_s16[_s64_x4](svint64x4_t zn)
    __arm_streaming;
```

### Description

Multi-vector signed saturating extract narrow and interleave

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Data type conversion / Narrowing conversions

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
SQCVTN Zreg1.H, { Zreg2.D - Zreg3.D }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SQCVTN--Multi-vector-signed-saturating-extract-narrow-and-interleave-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svqcvtn_s8[_s32_x4]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqcvtn_s8%5B_s32_x4%5D

### Signature (source notation)

```c
svint8_t svqcvtn_s8[_s32_x4](svint32x4_t zn)
    __arm_streaming;
```

### Description

Multi-vector signed saturating extract narrow and interleave

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Data type conversion / Narrowing conversions

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
SQCVTN Zreg1.B, { Zreg2.S - Zreg3.S }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SQCVTN--Multi-vector-signed-saturating-extract-narrow-and-interleave-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svqcvtn_u16[_s64_x4]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqcvtn_u16%5B_s64_x4%5D

### Signature (source notation)

```c
svuint16_t svqcvtn_u16[_s64_x4](svint64x4_t zn)
    __arm_streaming;
```

### Description

Multi-vector signed saturating unsigned extract narrow and interleave

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Data type conversion / Narrowing conversions

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
SQCVTUN Zreg1.H, { Zreg2.D - Zreg3.D }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SQCVTUN--Multi-vector-signed-saturating-unsigned-extract-narrow-and-interleave-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svqcvtn_u16[_u64_x4]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqcvtn_u16%5B_u64_x4%5D

### Signature (source notation)

```c
svuint16_t svqcvtn_u16[_u64_x4](svuint64x4_t zn)
    __arm_streaming;
```

### Description

Multi-vector unsigned saturating extract narrow and interleave

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Data type conversion / Narrowing conversions

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
UQCVTN Zreg1.H, { Zreg2.D - Zreg3.D }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/UQCVTN--Multi-vector-unsigned-saturating-extract-narrow-and-interleave-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svqcvtn_u8[_s32_x4]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqcvtn_u8%5B_s32_x4%5D

### Signature (source notation)

```c
svuint8_t svqcvtn_u8[_s32_x4](svint32x4_t zn)
    __arm_streaming;
```

### Description

Multi-vector signed saturating unsigned extract narrow and interleave

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Data type conversion / Narrowing conversions

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
SQCVTUN Zreg1.B, { Zreg2.S - Zreg3.S }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SQCVTUN--Multi-vector-signed-saturating-unsigned-extract-narrow-and-interleave-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svqcvtn_u8[_u32_x4]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqcvtn_u8%5B_u32_x4%5D

### Signature (source notation)

```c
svuint8_t svqcvtn_u8[_u32_x4](svuint32x4_t zn)
    __arm_streaming;
```

### Description

Multi-vector unsigned saturating extract narrow and interleave

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Data type conversion / Narrowing conversions

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
UQCVTN Zreg1.B, { Zreg2.S - Zreg3.S }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/UQCVTN--Multi-vector-unsigned-saturating-extract-narrow-and-interleave-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

