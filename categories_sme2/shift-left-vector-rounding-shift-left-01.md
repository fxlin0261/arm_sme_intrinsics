# SME2 / Shift / Left / Vector rounding shift left — Part 1

## svrshl[_s16_x2]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrshl%5B_s16_x2%5D

### Signature (source notation)

```c
svint16x2_t svrshl[_s16_x2](svint16x2_t zdn, svint16x2_t zm)
    __arm_streaming;
```

### Description

Multi-vector signed rounding shift left

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Shift / Left / Vector rounding shift left

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
SRSHL { Zreg1.H, Zreg2.H }, { Zreg1.H, Zreg2.H }, { Zreg3.H, Zreg4.H }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SRSHL--multiple-vectors---Multi-vector-signed-rounding-shift-left-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svrshl[_s16_x4]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrshl%5B_s16_x4%5D

### Signature (source notation)

```c
svint16x4_t svrshl[_s16_x4](svint16x4_t zdn, svint16x4_t zm)
    __arm_streaming;
```

### Description

Multi-vector signed rounding shift left

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Shift / Left / Vector rounding shift left

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
SRSHL { Zreg1.H - Zreg2.H }, { Zreg1.H - Zreg2.H }, { Zreg3.H - Zreg4.H }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SRSHL--multiple-vectors---Multi-vector-signed-rounding-shift-left-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svrshl[_s32_x2]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrshl%5B_s32_x2%5D

### Signature (source notation)

```c
svint32x2_t svrshl[_s32_x2](svint32x2_t zdn, svint32x2_t zm)
    __arm_streaming;
```

### Description

Multi-vector signed rounding shift left

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Shift / Left / Vector rounding shift left

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
SRSHL { Zreg1.S, Zreg2.S }, { Zreg1.S, Zreg2.S }, { Zreg3.S, Zreg4.S }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SRSHL--multiple-vectors---Multi-vector-signed-rounding-shift-left-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svrshl[_s32_x4]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrshl%5B_s32_x4%5D

### Signature (source notation)

```c
svint32x4_t svrshl[_s32_x4](svint32x4_t zdn, svint32x4_t zm)
    __arm_streaming;
```

### Description

Multi-vector signed rounding shift left

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Shift / Left / Vector rounding shift left

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
SRSHL { Zreg1.S - Zreg2.S }, { Zreg1.S - Zreg2.S }, { Zreg3.S - Zreg4.S }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SRSHL--multiple-vectors---Multi-vector-signed-rounding-shift-left-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svrshl[_s64_x2]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrshl%5B_s64_x2%5D

### Signature (source notation)

```c
svint64x2_t svrshl[_s64_x2](svint64x2_t zdn, svint64x2_t zm)
    __arm_streaming;
```

### Description

Multi-vector signed rounding shift left

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Shift / Left / Vector rounding shift left

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
SRSHL { Zreg1.D, Zreg2.D }, { Zreg1.D, Zreg2.D }, { Zreg3.D, Zreg4.D }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SRSHL--multiple-vectors---Multi-vector-signed-rounding-shift-left-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svrshl[_s64_x4]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrshl%5B_s64_x4%5D

### Signature (source notation)

```c
svint64x4_t svrshl[_s64_x4](svint64x4_t zdn, svint64x4_t zm)
    __arm_streaming;
```

### Description

Multi-vector signed rounding shift left

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Shift / Left / Vector rounding shift left

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
SRSHL { Zreg1.D - Zreg2.D }, { Zreg1.D - Zreg2.D }, { Zreg3.D - Zreg4.D }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SRSHL--multiple-vectors---Multi-vector-signed-rounding-shift-left-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svrshl[_s8_x2]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrshl%5B_s8_x2%5D

### Signature (source notation)

```c
svint8x2_t svrshl[_s8_x2](svint8x2_t zdn, svint8x2_t zm)
    __arm_streaming;
```

### Description

Multi-vector signed rounding shift left

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Shift / Left / Vector rounding shift left

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
SRSHL { Zreg1.B, Zreg2.B }, { Zreg1.B, Zreg2.B }, { Zreg3.B, Zreg4.B }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SRSHL--multiple-vectors---Multi-vector-signed-rounding-shift-left-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svrshl[_s8_x4]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrshl%5B_s8_x4%5D

### Signature (source notation)

```c
svint8x4_t svrshl[_s8_x4](svint8x4_t zdn, svint8x4_t zm)
    __arm_streaming;
```

### Description

Multi-vector signed rounding shift left

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Shift / Left / Vector rounding shift left

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
SRSHL { Zreg1.B - Zreg2.B }, { Zreg1.B - Zreg2.B }, { Zreg3.B - Zreg4.B }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SRSHL--multiple-vectors---Multi-vector-signed-rounding-shift-left-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svrshl[_single_s16_x2]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrshl%5B_single_s16_x2%5D

### Signature (source notation)

```c
svint16x2_t svrshl[_single_s16_x2](svint16x2_t zdn, svint16_t zm)
    __arm_streaming;
```

### Description

Multi-vector signed rounding shift left

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Shift / Left / Vector rounding shift left

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
SRSHL { Zreg1.H, Zreg2.H }, { Zreg1.H, Zreg2.H }, Zreg3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SRSHL--multiple-and-single-vector---Multi-vector-signed-rounding-shift-left-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svrshl[_single_s16_x4]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrshl%5B_single_s16_x4%5D

### Signature (source notation)

```c
svint16x4_t svrshl[_single_s16_x4](svint16x4_t zdn, svint16_t zm)
    __arm_streaming;
```

### Description

Multi-vector signed rounding shift left

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Shift / Left / Vector rounding shift left

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
SRSHL { Zreg1.H - Zreg2.H }, { Zreg1.H - Zreg2.H }, Zreg3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SRSHL--multiple-and-single-vector---Multi-vector-signed-rounding-shift-left-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svrshl[_single_s32_x2]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrshl%5B_single_s32_x2%5D

### Signature (source notation)

```c
svint32x2_t svrshl[_single_s32_x2](svint32x2_t zdn, svint32_t zm)
    __arm_streaming;
```

### Description

Multi-vector signed rounding shift left

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Shift / Left / Vector rounding shift left

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
SRSHL { Zreg1.S, Zreg2.S }, { Zreg1.S, Zreg2.S }, Zreg3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SRSHL--multiple-and-single-vector---Multi-vector-signed-rounding-shift-left-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svrshl[_single_s32_x4]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrshl%5B_single_s32_x4%5D

### Signature (source notation)

```c
svint32x4_t svrshl[_single_s32_x4](svint32x4_t zdn, svint32_t zm)
    __arm_streaming;
```

### Description

Multi-vector signed rounding shift left

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Shift / Left / Vector rounding shift left

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
SRSHL { Zreg1.S - Zreg2.S }, { Zreg1.S - Zreg2.S }, Zreg3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SRSHL--multiple-and-single-vector---Multi-vector-signed-rounding-shift-left-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svrshl[_single_s64_x2]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrshl%5B_single_s64_x2%5D

### Signature (source notation)

```c
svint64x2_t svrshl[_single_s64_x2](svint64x2_t zdn, svint64_t zm)
    __arm_streaming;
```

### Description

Multi-vector signed rounding shift left

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Shift / Left / Vector rounding shift left

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
SRSHL { Zreg1.D, Zreg2.D }, { Zreg1.D, Zreg2.D }, Zreg3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SRSHL--multiple-and-single-vector---Multi-vector-signed-rounding-shift-left-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svrshl[_single_s64_x4]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrshl%5B_single_s64_x4%5D

### Signature (source notation)

```c
svint64x4_t svrshl[_single_s64_x4](svint64x4_t zdn, svint64_t zm)
    __arm_streaming;
```

### Description

Multi-vector signed rounding shift left

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Shift / Left / Vector rounding shift left

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
SRSHL { Zreg1.D - Zreg2.D }, { Zreg1.D - Zreg2.D }, Zreg3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SRSHL--multiple-and-single-vector---Multi-vector-signed-rounding-shift-left-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svrshl[_single_s8_x2]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrshl%5B_single_s8_x2%5D

### Signature (source notation)

```c
svint8x2_t svrshl[_single_s8_x2](svint8x2_t zdn, svint8_t zm)
    __arm_streaming;
```

### Description

Multi-vector signed rounding shift left

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Shift / Left / Vector rounding shift left

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
SRSHL { Zreg1.B, Zreg2.B }, { Zreg1.B, Zreg2.B }, Zreg3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SRSHL--multiple-and-single-vector---Multi-vector-signed-rounding-shift-left-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svrshl[_single_s8_x4]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrshl%5B_single_s8_x4%5D

### Signature (source notation)

```c
svint8x4_t svrshl[_single_s8_x4](svint8x4_t zdn, svint8_t zm)
    __arm_streaming;
```

### Description

Multi-vector signed rounding shift left

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Shift / Left / Vector rounding shift left

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
SRSHL { Zreg1.B - Zreg2.B }, { Zreg1.B - Zreg2.B }, Zreg3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SRSHL--multiple-and-single-vector---Multi-vector-signed-rounding-shift-left-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svrshl[_single_u16_x2]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrshl%5B_single_u16_x2%5D

### Signature (source notation)

```c
svuint16x2_t svrshl[_single_u16_x2](svuint16x2_t zdn, svuint16_t zm)
    __arm_streaming;
```

### Description

Multi-vector unsigned rounding shift left

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Shift / Left / Vector rounding shift left

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
  "value": "svuint16x2_t"
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
URSHL { Zreg1.H, Zreg2.H }, { Zreg1.H, Zreg2.H }, Zreg3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/URSHL--multiple-and-single-vector---Multi-vector-unsigned-rounding-shift-left-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svrshl[_single_u16_x4]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrshl%5B_single_u16_x4%5D

### Signature (source notation)

```c
svuint16x4_t svrshl[_single_u16_x4](svuint16x4_t zdn, svuint16_t zm)
    __arm_streaming;
```

### Description

Multi-vector unsigned rounding shift left

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Shift / Left / Vector rounding shift left

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
  "value": "svuint16x4_t"
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
URSHL { Zreg1.H - Zreg2.H }, { Zreg1.H - Zreg2.H }, Zreg3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/URSHL--multiple-and-single-vector---Multi-vector-unsigned-rounding-shift-left-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svrshl[_single_u32_x2]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrshl%5B_single_u32_x2%5D

### Signature (source notation)

```c
svuint32x2_t svrshl[_single_u32_x2](svuint32x2_t zdn, svuint32_t zm)
    __arm_streaming;
```

### Description

Multi-vector unsigned rounding shift left

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Shift / Left / Vector rounding shift left

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
  "return_base_type": "uint32",
  "element_bit_size": "32",
  "value": "svuint32x2_t"
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
URSHL { Zreg1.S, Zreg2.S }, { Zreg1.S, Zreg2.S }, Zreg3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/URSHL--multiple-and-single-vector---Multi-vector-unsigned-rounding-shift-left-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svrshl[_single_u32_x4]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrshl%5B_single_u32_x4%5D

### Signature (source notation)

```c
svuint32x4_t svrshl[_single_u32_x4](svuint32x4_t zdn, svuint32_t zm)
    __arm_streaming;
```

### Description

Multi-vector unsigned rounding shift left

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Shift / Left / Vector rounding shift left

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
  "return_base_type": "uint32",
  "element_bit_size": "32",
  "value": "svuint32x4_t"
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
URSHL { Zreg1.S - Zreg2.S }, { Zreg1.S - Zreg2.S }, Zreg3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/URSHL--multiple-and-single-vector---Multi-vector-unsigned-rounding-shift-left-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svrshl[_single_u64_x2]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrshl%5B_single_u64_x2%5D

### Signature (source notation)

```c
svuint64x2_t svrshl[_single_u64_x2](svuint64x2_t zdn, svuint64_t zm)
    __arm_streaming;
```

### Description

Multi-vector unsigned rounding shift left

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Shift / Left / Vector rounding shift left

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
  "return_base_type": "uint64",
  "element_bit_size": "64",
  "value": "svuint64x2_t"
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
URSHL { Zreg1.D, Zreg2.D }, { Zreg1.D, Zreg2.D }, Zreg3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/URSHL--multiple-and-single-vector---Multi-vector-unsigned-rounding-shift-left-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svrshl[_single_u64_x4]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrshl%5B_single_u64_x4%5D

### Signature (source notation)

```c
svuint64x4_t svrshl[_single_u64_x4](svuint64x4_t zdn, svuint64_t zm)
    __arm_streaming;
```

### Description

Multi-vector unsigned rounding shift left

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Shift / Left / Vector rounding shift left

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
  "return_base_type": "uint64",
  "element_bit_size": "64",
  "value": "svuint64x4_t"
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
URSHL { Zreg1.D - Zreg2.D }, { Zreg1.D - Zreg2.D }, Zreg3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/URSHL--multiple-and-single-vector---Multi-vector-unsigned-rounding-shift-left-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svrshl[_single_u8_x2]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrshl%5B_single_u8_x2%5D

### Signature (source notation)

```c
svuint8x2_t svrshl[_single_u8_x2](svuint8x2_t zdn, svuint8_t zm)
    __arm_streaming;
```

### Description

Multi-vector unsigned rounding shift left

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Shift / Left / Vector rounding shift left

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
  "value": "svuint8x2_t"
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
URSHL { Zreg1.B, Zreg2.B }, { Zreg1.B, Zreg2.B }, Zreg3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/URSHL--multiple-and-single-vector---Multi-vector-unsigned-rounding-shift-left-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svrshl[_single_u8_x4]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrshl%5B_single_u8_x4%5D

### Signature (source notation)

```c
svuint8x4_t svrshl[_single_u8_x4](svuint8x4_t zdn, svuint8_t zm)
    __arm_streaming;
```

### Description

Multi-vector unsigned rounding shift left

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Shift / Left / Vector rounding shift left

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
  "value": "svuint8x4_t"
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
URSHL { Zreg1.B - Zreg2.B }, { Zreg1.B - Zreg2.B }, Zreg3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/URSHL--multiple-and-single-vector---Multi-vector-unsigned-rounding-shift-left-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svrshl[_u16_x2]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrshl%5B_u16_x2%5D

### Signature (source notation)

```c
svuint16x2_t svrshl[_u16_x2](svuint16x2_t zdn, svuint16x2_t zm)
    __arm_streaming;
```

### Description

Multi-vector unsigned rounding shift left

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Shift / Left / Vector rounding shift left

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
  "value": "svuint16x2_t"
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
URSHL { Zreg1.H, Zreg2.H }, { Zreg1.H, Zreg2.H }, { Zreg3.H, Zreg4.H }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/URSHL--multiple-vectors---Multi-vector-unsigned-rounding-shift-left-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svrshl[_u16_x4]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrshl%5B_u16_x4%5D

### Signature (source notation)

```c
svuint16x4_t svrshl[_u16_x4](svuint16x4_t zdn, svuint16x4_t zm)
    __arm_streaming;
```

### Description

Multi-vector unsigned rounding shift left

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Shift / Left / Vector rounding shift left

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
  "value": "svuint16x4_t"
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
URSHL { Zreg1.H - Zreg2.H }, { Zreg1.H - Zreg2.H }, { Zreg3.H - Zreg4.H }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/URSHL--multiple-vectors---Multi-vector-unsigned-rounding-shift-left-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svrshl[_u32_x2]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrshl%5B_u32_x2%5D

### Signature (source notation)

```c
svuint32x2_t svrshl[_u32_x2](svuint32x2_t zdn, svuint32x2_t zm)
    __arm_streaming;
```

### Description

Multi-vector unsigned rounding shift left

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Shift / Left / Vector rounding shift left

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
  "return_base_type": "uint32",
  "element_bit_size": "32",
  "value": "svuint32x2_t"
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
URSHL { Zreg1.S, Zreg2.S }, { Zreg1.S, Zreg2.S }, { Zreg3.S, Zreg4.S }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/URSHL--multiple-vectors---Multi-vector-unsigned-rounding-shift-left-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svrshl[_u32_x4]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrshl%5B_u32_x4%5D

### Signature (source notation)

```c
svuint32x4_t svrshl[_u32_x4](svuint32x4_t zdn, svuint32x4_t zm)
    __arm_streaming;
```

### Description

Multi-vector unsigned rounding shift left

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Shift / Left / Vector rounding shift left

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
  "return_base_type": "uint32",
  "element_bit_size": "32",
  "value": "svuint32x4_t"
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
URSHL { Zreg1.S - Zreg2.S }, { Zreg1.S - Zreg2.S }, { Zreg3.S - Zreg4.S }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/URSHL--multiple-vectors---Multi-vector-unsigned-rounding-shift-left-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svrshl[_u64_x2]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrshl%5B_u64_x2%5D

### Signature (source notation)

```c
svuint64x2_t svrshl[_u64_x2](svuint64x2_t zdn, svuint64x2_t zm)
    __arm_streaming;
```

### Description

Multi-vector unsigned rounding shift left

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Shift / Left / Vector rounding shift left

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
  "return_base_type": "uint64",
  "element_bit_size": "64",
  "value": "svuint64x2_t"
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
URSHL { Zreg1.D, Zreg2.D }, { Zreg1.D, Zreg2.D }, { Zreg3.D, Zreg4.D }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/URSHL--multiple-vectors---Multi-vector-unsigned-rounding-shift-left-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svrshl[_u64_x4]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrshl%5B_u64_x4%5D

### Signature (source notation)

```c
svuint64x4_t svrshl[_u64_x4](svuint64x4_t zdn, svuint64x4_t zm)
    __arm_streaming;
```

### Description

Multi-vector unsigned rounding shift left

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Shift / Left / Vector rounding shift left

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
  "return_base_type": "uint64",
  "element_bit_size": "64",
  "value": "svuint64x4_t"
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
URSHL { Zreg1.D - Zreg2.D }, { Zreg1.D - Zreg2.D }, { Zreg3.D - Zreg4.D }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/URSHL--multiple-vectors---Multi-vector-unsigned-rounding-shift-left-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svrshl[_u8_x2]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrshl%5B_u8_x2%5D

### Signature (source notation)

```c
svuint8x2_t svrshl[_u8_x2](svuint8x2_t zdn, svuint8x2_t zm)
    __arm_streaming;
```

### Description

Multi-vector unsigned rounding shift left

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Shift / Left / Vector rounding shift left

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
  "value": "svuint8x2_t"
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
URSHL { Zreg1.B, Zreg2.B }, { Zreg1.B, Zreg2.B }, { Zreg3.B, Zreg4.B }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/URSHL--multiple-vectors---Multi-vector-unsigned-rounding-shift-left-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svrshl[_u8_x4]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrshl%5B_u8_x4%5D

### Signature (source notation)

```c
svuint8x4_t svrshl[_u8_x4](svuint8x4_t zdn, svuint8x4_t zm)
    __arm_streaming;
```

### Description

Multi-vector unsigned rounding shift left

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Shift / Left / Vector rounding shift left

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
  "value": "svuint8x4_t"
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
URSHL { Zreg1.B - Zreg2.B }, { Zreg1.B - Zreg2.B }, { Zreg3.B - Zreg4.B }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/URSHL--multiple-vectors---Multi-vector-unsigned-rounding-shift-left-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

