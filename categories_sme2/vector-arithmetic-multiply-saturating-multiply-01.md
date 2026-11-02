# SME2 / Vector arithmetic / Multiply / Saturating multiply — Part 1

## svqdmulh[_s16_x2]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdmulh%5B_s16_x2%5D

### Signature (source notation)

```c
svint16x2_t svqdmulh[_s16_x2](svint16x2_t zdn, svint16x2_t zm)
    __arm_streaming;
```

### Description

Multi-vector signed saturating doubling multiply high

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply / Saturating multiply

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
  "value": "svint16x2_t"
}
```

### Argument preparation and constraints

```json
{
  "zdn": {
    "Z multi-vector": "{ Zreg1.H, Zreg2.H }"
  },
  "zm": {
    "Z multi-vector": "{ Zreg3.H, Zreg4.H }"
  }
}
```

### Result mapping

```json
[
  {
    "{ Zreg1.H, Zreg2.H }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
SQDMULH { Zreg1.H, Zreg2.H }, { Zreg1.H, Zreg2.H }, { Zreg3.H, Zreg4.H }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SQDMULH--multiple-vectors---Multi-vector-signed-saturating-doubling-multiply-high-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svqdmulh[_s16_x4]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdmulh%5B_s16_x4%5D

### Signature (source notation)

```c
svint16x4_t svqdmulh[_s16_x4](svint16x4_t zdn, svint16x4_t zm)
    __arm_streaming;
```

### Description

Multi-vector signed saturating doubling multiply high

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply / Saturating multiply

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
  "value": "svint16x4_t"
}
```

### Argument preparation and constraints

```json
{
  "zdn": {
    "Z multi-vector": "{ Zreg1.H - Zreg2.H }"
  },
  "zm": {
    "Z multi-vector": "{ Zreg3.H - Zreg4.H }"
  }
}
```

### Result mapping

```json
[
  {
    "{ Zreg1.H - Zreg2.H }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
SQDMULH { Zreg1.H - Zreg2.H }, { Zreg1.H - Zreg2.H }, { Zreg3.H - Zreg4.H }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SQDMULH--multiple-vectors---Multi-vector-signed-saturating-doubling-multiply-high-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svqdmulh[_s32_x2]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdmulh%5B_s32_x2%5D

### Signature (source notation)

```c
svint32x2_t svqdmulh[_s32_x2](svint32x2_t zdn, svint32x2_t zm)
    __arm_streaming;
```

### Description

Multi-vector signed saturating doubling multiply high

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply / Saturating multiply

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
  "return_base_type": "int32",
  "element_bit_size": "32",
  "value": "svint32x2_t"
}
```

### Argument preparation and constraints

```json
{
  "zdn": {
    "Z multi-vector": "{ Zreg1.S, Zreg2.S }"
  },
  "zm": {
    "Z multi-vector": "{ Zreg3.S, Zreg4.S }"
  }
}
```

### Result mapping

```json
[
  {
    "{ Zreg1.S, Zreg2.S }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
SQDMULH { Zreg1.S, Zreg2.S }, { Zreg1.S, Zreg2.S }, { Zreg3.S, Zreg4.S }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SQDMULH--multiple-vectors---Multi-vector-signed-saturating-doubling-multiply-high-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svqdmulh[_s32_x4]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdmulh%5B_s32_x4%5D

### Signature (source notation)

```c
svint32x4_t svqdmulh[_s32_x4](svint32x4_t zdn, svint32x4_t zm)
    __arm_streaming;
```

### Description

Multi-vector signed saturating doubling multiply high

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply / Saturating multiply

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
  "return_base_type": "int32",
  "element_bit_size": "32",
  "value": "svint32x4_t"
}
```

### Argument preparation and constraints

```json
{
  "zdn": {
    "Z multi-vector": "{ Zreg1.S - Zreg2.S }"
  },
  "zm": {
    "Z multi-vector": "{ Zreg3.S - Zreg4.S }"
  }
}
```

### Result mapping

```json
[
  {
    "{ Zreg1.S - Zreg2.S }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
SQDMULH { Zreg1.S - Zreg2.S }, { Zreg1.S - Zreg2.S }, { Zreg3.S - Zreg4.S }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SQDMULH--multiple-vectors---Multi-vector-signed-saturating-doubling-multiply-high-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svqdmulh[_s64_x2]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdmulh%5B_s64_x2%5D

### Signature (source notation)

```c
svint64x2_t svqdmulh[_s64_x2](svint64x2_t zdn, svint64x2_t zm)
    __arm_streaming;
```

### Description

Multi-vector signed saturating doubling multiply high

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply / Saturating multiply

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
  "return_base_type": "int64",
  "element_bit_size": "64",
  "value": "svint64x2_t"
}
```

### Argument preparation and constraints

```json
{
  "zdn": {
    "Z multi-vector": "{ Zreg1.D, Zreg2.D }"
  },
  "zm": {
    "Z multi-vector": "{ Zreg3.D, Zreg4.D }"
  }
}
```

### Result mapping

```json
[
  {
    "{ Zreg1.D, Zreg2.D }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
SQDMULH { Zreg1.D, Zreg2.D }, { Zreg1.D, Zreg2.D }, { Zreg3.D, Zreg4.D }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SQDMULH--multiple-vectors---Multi-vector-signed-saturating-doubling-multiply-high-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svqdmulh[_s64_x4]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdmulh%5B_s64_x4%5D

### Signature (source notation)

```c
svint64x4_t svqdmulh[_s64_x4](svint64x4_t zdn, svint64x4_t zm)
    __arm_streaming;
```

### Description

Multi-vector signed saturating doubling multiply high

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply / Saturating multiply

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
  "return_base_type": "int64",
  "element_bit_size": "64",
  "value": "svint64x4_t"
}
```

### Argument preparation and constraints

```json
{
  "zdn": {
    "Z multi-vector": "{ Zreg1.D - Zreg2.D }"
  },
  "zm": {
    "Z multi-vector": "{ Zreg3.D - Zreg4.D }"
  }
}
```

### Result mapping

```json
[
  {
    "{ Zreg1.D - Zreg2.D }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
SQDMULH { Zreg1.D - Zreg2.D }, { Zreg1.D - Zreg2.D }, { Zreg3.D - Zreg4.D }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SQDMULH--multiple-vectors---Multi-vector-signed-saturating-doubling-multiply-high-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svqdmulh[_s8_x2]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdmulh%5B_s8_x2%5D

### Signature (source notation)

```c
svint8x2_t svqdmulh[_s8_x2](svint8x2_t zdn, svint8x2_t zm)
    __arm_streaming;
```

### Description

Multi-vector signed saturating doubling multiply high

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply / Saturating multiply

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
  "value": "svint8x2_t"
}
```

### Argument preparation and constraints

```json
{
  "zdn": {
    "Z multi-vector": "{ Zreg1.B, Zreg2.B }"
  },
  "zm": {
    "Z multi-vector": "{ Zreg3.B, Zreg4.B }"
  }
}
```

### Result mapping

```json
[
  {
    "{ Zreg1.B, Zreg2.B }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
SQDMULH { Zreg1.B, Zreg2.B }, { Zreg1.B, Zreg2.B }, { Zreg3.B, Zreg4.B }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SQDMULH--multiple-vectors---Multi-vector-signed-saturating-doubling-multiply-high-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svqdmulh[_s8_x4]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdmulh%5B_s8_x4%5D

### Signature (source notation)

```c
svint8x4_t svqdmulh[_s8_x4](svint8x4_t zdn, svint8x4_t zm)
    __arm_streaming;
```

### Description

Multi-vector signed saturating doubling multiply high

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply / Saturating multiply

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
  "value": "svint8x4_t"
}
```

### Argument preparation and constraints

```json
{
  "zdn": {
    "Z multi-vector": "{ Zreg1.B - Zreg2.B }"
  },
  "zm": {
    "Z multi-vector": "{ Zreg3.B - Zreg4.B }"
  }
}
```

### Result mapping

```json
[
  {
    "{ Zreg1.B - Zreg2.B }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
SQDMULH { Zreg1.B - Zreg2.B }, { Zreg1.B - Zreg2.B }, { Zreg3.B - Zreg4.B }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SQDMULH--multiple-vectors---Multi-vector-signed-saturating-doubling-multiply-high-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svqdmulh[_single_s16_x2]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdmulh%5B_single_s16_x2%5D

### Signature (source notation)

```c
svint16x2_t svqdmulh[_single_s16_x2](svint16x2_t zdn, svint16_t zm)
    __arm_streaming;
```

### Description

Multi-vector signed saturating doubling multiply high by vector

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply / Saturating multiply

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
  "value": "svint16x2_t"
}
```

### Argument preparation and constraints

```json
{
  "zdn": {
    "Z multi-vector": "{ Zreg1.H, Zreg2.H }"
  },
  "zm": {
    "register": "Zreg3.H"
  }
}
```

### Result mapping

```json
[
  {
    "{ Zreg1.H, Zreg2.H }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
SQDMULH { Zreg1.H, Zreg2.H }, { Zreg1.H, Zreg2.H }, Zreg3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SQDMULH--multiple-and-single-vector---Multi-vector-signed-saturating-doubling-multiply-high-by-vector-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svqdmulh[_single_s16_x4]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdmulh%5B_single_s16_x4%5D

### Signature (source notation)

```c
svint16x4_t svqdmulh[_single_s16_x4](svint16x4_t zdn, svint16_t zm)
    __arm_streaming;
```

### Description

Multi-vector signed saturating doubling multiply high by vector

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply / Saturating multiply

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
  "value": "svint16x4_t"
}
```

### Argument preparation and constraints

```json
{
  "zdn": {
    "Z multi-vector": "{ Zreg1.H - Zreg2.H }"
  },
  "zm": {
    "register": "Zreg3.H"
  }
}
```

### Result mapping

```json
[
  {
    "{ Zreg1.H - Zreg2.H }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
SQDMULH { Zreg1.H - Zreg2.H }, { Zreg1.H - Zreg2.H }, Zreg3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SQDMULH--multiple-and-single-vector---Multi-vector-signed-saturating-doubling-multiply-high-by-vector-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svqdmulh[_single_s32_x2]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdmulh%5B_single_s32_x2%5D

### Signature (source notation)

```c
svint32x2_t svqdmulh[_single_s32_x2](svint32x2_t zdn, svint32_t zm)
    __arm_streaming;
```

### Description

Multi-vector signed saturating doubling multiply high by vector

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply / Saturating multiply

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
  "return_base_type": "int32",
  "element_bit_size": "32",
  "value": "svint32x2_t"
}
```

### Argument preparation and constraints

```json
{
  "zdn": {
    "Z multi-vector": "{ Zreg1.S, Zreg2.S }"
  },
  "zm": {
    "register": "Zreg3.S"
  }
}
```

### Result mapping

```json
[
  {
    "{ Zreg1.S, Zreg2.S }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
SQDMULH { Zreg1.S, Zreg2.S }, { Zreg1.S, Zreg2.S }, Zreg3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SQDMULH--multiple-and-single-vector---Multi-vector-signed-saturating-doubling-multiply-high-by-vector-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svqdmulh[_single_s32_x4]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdmulh%5B_single_s32_x4%5D

### Signature (source notation)

```c
svint32x4_t svqdmulh[_single_s32_x4](svint32x4_t zdn, svint32_t zm)
    __arm_streaming;
```

### Description

Multi-vector signed saturating doubling multiply high by vector

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply / Saturating multiply

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
  "return_base_type": "int32",
  "element_bit_size": "32",
  "value": "svint32x4_t"
}
```

### Argument preparation and constraints

```json
{
  "zdn": {
    "Z multi-vector": "{ Zreg1.S - Zreg2.S }"
  },
  "zm": {
    "register": "Zreg3.S"
  }
}
```

### Result mapping

```json
[
  {
    "{ Zreg1.S - Zreg2.S }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
SQDMULH { Zreg1.S - Zreg2.S }, { Zreg1.S - Zreg2.S }, Zreg3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SQDMULH--multiple-and-single-vector---Multi-vector-signed-saturating-doubling-multiply-high-by-vector-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svqdmulh[_single_s64_x2]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdmulh%5B_single_s64_x2%5D

### Signature (source notation)

```c
svint64x2_t svqdmulh[_single_s64_x2](svint64x2_t zdn, svint64_t zm)
    __arm_streaming;
```

### Description

Multi-vector signed saturating doubling multiply high by vector

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply / Saturating multiply

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
  "return_base_type": "int64",
  "element_bit_size": "64",
  "value": "svint64x2_t"
}
```

### Argument preparation and constraints

```json
{
  "zdn": {
    "Z multi-vector": "{ Zreg1.D, Zreg2.D }"
  },
  "zm": {
    "register": "Zreg3.D"
  }
}
```

### Result mapping

```json
[
  {
    "{ Zreg1.D, Zreg2.D }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
SQDMULH { Zreg1.D, Zreg2.D }, { Zreg1.D, Zreg2.D }, Zreg3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SQDMULH--multiple-and-single-vector---Multi-vector-signed-saturating-doubling-multiply-high-by-vector-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svqdmulh[_single_s64_x4]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdmulh%5B_single_s64_x4%5D

### Signature (source notation)

```c
svint64x4_t svqdmulh[_single_s64_x4](svint64x4_t zdn, svint64_t zm)
    __arm_streaming;
```

### Description

Multi-vector signed saturating doubling multiply high by vector

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply / Saturating multiply

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
  "return_base_type": "int64",
  "element_bit_size": "64",
  "value": "svint64x4_t"
}
```

### Argument preparation and constraints

```json
{
  "zdn": {
    "Z multi-vector": "{ Zreg1.D - Zreg2.D }"
  },
  "zm": {
    "register": "Zreg3.D"
  }
}
```

### Result mapping

```json
[
  {
    "{ Zreg1.D - Zreg2.D }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
SQDMULH { Zreg1.D - Zreg2.D }, { Zreg1.D - Zreg2.D }, Zreg3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SQDMULH--multiple-and-single-vector---Multi-vector-signed-saturating-doubling-multiply-high-by-vector-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svqdmulh[_single_s8_x2]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdmulh%5B_single_s8_x2%5D

### Signature (source notation)

```c
svint8x2_t svqdmulh[_single_s8_x2](svint8x2_t zdn, svint8_t zm)
    __arm_streaming;
```

### Description

Multi-vector signed saturating doubling multiply high by vector

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply / Saturating multiply

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
  "value": "svint8x2_t"
}
```

### Argument preparation and constraints

```json
{
  "zdn": {
    "Z multi-vector": "{ Zreg1.B, Zreg2.B }"
  },
  "zm": {
    "register": "Zreg3.B"
  }
}
```

### Result mapping

```json
[
  {
    "{ Zreg1.B, Zreg2.B }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
SQDMULH { Zreg1.B, Zreg2.B }, { Zreg1.B, Zreg2.B }, Zreg3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SQDMULH--multiple-and-single-vector---Multi-vector-signed-saturating-doubling-multiply-high-by-vector-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svqdmulh[_single_s8_x4]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdmulh%5B_single_s8_x4%5D

### Signature (source notation)

```c
svint8x4_t svqdmulh[_single_s8_x4](svint8x4_t zdn, svint8_t zm)
    __arm_streaming;
```

### Description

Multi-vector signed saturating doubling multiply high by vector

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply / Saturating multiply

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
  "value": "svint8x4_t"
}
```

### Argument preparation and constraints

```json
{
  "zdn": {
    "Z multi-vector": "{ Zreg1.B - Zreg2.B }"
  },
  "zm": {
    "register": "Zreg3.B"
  }
}
```

### Result mapping

```json
[
  {
    "{ Zreg1.B - Zreg2.B }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
SQDMULH { Zreg1.B - Zreg2.B }, { Zreg1.B - Zreg2.B }, Zreg3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SQDMULH--multiple-and-single-vector---Multi-vector-signed-saturating-doubling-multiply-high-by-vector-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

