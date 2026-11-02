# SME2 / Move / Widen — Part 1

## svunpk_s16[_s8_x2]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svunpk_s16%5B_s8_x2%5D

### Signature (source notation)

```c
svint16x2_t svunpk_s16[_s8_x2](svint8_t zn)
    __arm_streaming;
```

### Description

Unpack and sign-extend multi-vector elements

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Move / Widen

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
  "zn": {
    "register": "Zreg3.B"
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
SUNPK { Zreg1.H, Zreg2.H }, Zreg3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SUNPK--Unpack-and-sign-extend-multi-vector-elements-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svunpk_s16[_s8_x4]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svunpk_s16%5B_s8_x4%5D

### Signature (source notation)

```c
svint16x4_t svunpk_s16[_s8_x4](svint8x2_t zn)
    __arm_streaming;
```

### Description

Unpack and sign-extend multi-vector elements

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Move / Widen

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
  "zn": {
    "Z multi-vector": "{ Zreg3.B, Zreg4.B }"
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
SUNPK { Zreg1.H - Zreg2.H }, { Zreg3.B, Zreg4.B }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SUNPK--Unpack-and-sign-extend-multi-vector-elements-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svunpk_s32[_s16_x2]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svunpk_s32%5B_s16_x2%5D

### Signature (source notation)

```c
svint32x2_t svunpk_s32[_s16_x2](svint16_t zn)
    __arm_streaming;
```

### Description

Unpack and sign-extend multi-vector elements

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Move / Widen

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
  "zn": {
    "register": "Zreg3.H"
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
SUNPK { Zreg1.S, Zreg2.S }, Zreg3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SUNPK--Unpack-and-sign-extend-multi-vector-elements-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svunpk_s32[_s16_x4]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svunpk_s32%5B_s16_x4%5D

### Signature (source notation)

```c
svint32x4_t svunpk_s32[_s16_x4](svint16x2_t zn)
    __arm_streaming;
```

### Description

Unpack and sign-extend multi-vector elements

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Move / Widen

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
  "zn": {
    "Z multi-vector": "{ Zreg3.H, Zreg4.H }"
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
SUNPK { Zreg1.S - Zreg2.S }, { Zreg3.H, Zreg4.H }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SUNPK--Unpack-and-sign-extend-multi-vector-elements-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svunpk_s64[_s32_x2]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svunpk_s64%5B_s32_x2%5D

### Signature (source notation)

```c
svint64x2_t svunpk_s64[_s32_x2](svint32_t zn)
    __arm_streaming;
```

### Description

Unpack and sign-extend multi-vector elements

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Move / Widen

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
  "zn": {
    "register": "Zreg3.S"
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
SUNPK { Zreg1.D, Zreg2.D }, Zreg3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SUNPK--Unpack-and-sign-extend-multi-vector-elements-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svunpk_s64[_s32_x4]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svunpk_s64%5B_s32_x4%5D

### Signature (source notation)

```c
svint64x4_t svunpk_s64[_s32_x4](svint32x2_t zn)
    __arm_streaming;
```

### Description

Unpack and sign-extend multi-vector elements

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Move / Widen

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
  "zn": {
    "Z multi-vector": "{ Zreg3.S, Zreg4.S }"
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
SUNPK { Zreg1.D - Zreg2.D }, { Zreg3.S, Zreg4.S }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SUNPK--Unpack-and-sign-extend-multi-vector-elements-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svunpk_u16[_u8_x2]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svunpk_u16%5B_u8_x2%5D

### Signature (source notation)

```c
svuint16x2_t svunpk_u16[_u8_x2](svuint8_t zn)
    __arm_streaming;
```

### Description

Unpack and zero-extend multi-vector elements

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Move / Widen

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
  "zn": {
    "register": "Zreg3.B"
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
UUNPK { Zreg1.H, Zreg2.H }, Zreg3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/UUNPK--Unpack-and-zero-extend-multi-vector-elements-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svunpk_u16[_u8_x4]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svunpk_u16%5B_u8_x4%5D

### Signature (source notation)

```c
svuint16x4_t svunpk_u16[_u8_x4](svuint8x2_t zn)
    __arm_streaming;
```

### Description

Unpack and zero-extend multi-vector elements

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Move / Widen

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
  "zn": {
    "Z multi-vector": "{ Zreg3.B, Zreg4.B }"
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
UUNPK { Zreg1.H - Zreg2.H }, { Zreg3.B, Zreg4.B }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/UUNPK--Unpack-and-zero-extend-multi-vector-elements-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svunpk_u32[_u16_x2]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svunpk_u32%5B_u16_x2%5D

### Signature (source notation)

```c
svuint32x2_t svunpk_u32[_u16_x2](svuint16_t zn)
    __arm_streaming;
```

### Description

Unpack and zero-extend multi-vector elements

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Move / Widen

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
  "zn": {
    "register": "Zreg3.H"
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
UUNPK { Zreg1.S, Zreg2.S }, Zreg3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/UUNPK--Unpack-and-zero-extend-multi-vector-elements-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svunpk_u32[_u16_x4]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svunpk_u32%5B_u16_x4%5D

### Signature (source notation)

```c
svuint32x4_t svunpk_u32[_u16_x4](svuint16x2_t zn)
    __arm_streaming;
```

### Description

Unpack and zero-extend multi-vector elements

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Move / Widen

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
  "zn": {
    "Z multi-vector": "{ Zreg3.H, Zreg4.H }"
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
UUNPK { Zreg1.S - Zreg2.S }, { Zreg3.H, Zreg4.H }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/UUNPK--Unpack-and-zero-extend-multi-vector-elements-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svunpk_u64[_u32_x2]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svunpk_u64%5B_u32_x2%5D

### Signature (source notation)

```c
svuint64x2_t svunpk_u64[_u32_x2](svuint32_t zn)
    __arm_streaming;
```

### Description

Unpack and zero-extend multi-vector elements

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Move / Widen

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
  "zn": {
    "register": "Zreg3.S"
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
UUNPK { Zreg1.D, Zreg2.D }, Zreg3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/UUNPK--Unpack-and-zero-extend-multi-vector-elements-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svunpk_u64[_u32_x4]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svunpk_u64%5B_u32_x4%5D

### Signature (source notation)

```c
svuint64x4_t svunpk_u64[_u32_x4](svuint32x2_t zn)
    __arm_streaming;
```

### Description

Unpack and zero-extend multi-vector elements

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Move / Widen

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
  "zn": {
    "Z multi-vector": "{ Zreg3.S, Zreg4.S }"
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
UUNPK { Zreg1.D - Zreg2.D }, { Zreg3.S, Zreg4.S }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/UUNPK--Unpack-and-zero-extend-multi-vector-elements-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

