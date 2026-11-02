# SME2 / Vector manipulation / Unzip elements — Part 2

## svuzpq2[_u64]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svuzpq2%5B_u64%5D

### Signature (source notation)

```c
svuint64_t svuzpq2[_u64](svuint64_t zn, svuint64_t zm);
```

### Description

Concatenate odd elements within each pair of quadword vector segments

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector manipulation / Unzip elements

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p1)|FEAT_SME2p1
```

### Return type metadata

```json
{
  "return_base_type": "uint64",
  "element_bit_size": "64",
  "value": "svuint64_t"
}
```

### Argument preparation and constraints

```json
{
  "zn": {
    "register": "Zreg2.D"
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
    "Zreg1.D": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
UZPQ2 Zreg1.D, Zreg2.D, Zreg3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/UZPQ2--Concatenate-odd-elements-within-each-pair-of-quadword-vector-segments-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svuzpq2[_u8]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svuzpq2%5B_u8%5D

### Signature (source notation)

```c
svuint8_t svuzpq2[_u8](svuint8_t zn, svuint8_t zm);
```

### Description

Concatenate odd elements within each pair of quadword vector segments

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector manipulation / Unzip elements

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p1)|FEAT_SME2p1
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
    "register": "Zreg2.B"
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
    "Zreg1.B": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
UZPQ2 Zreg1.B, Zreg2.B, Zreg3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/UZPQ2--Concatenate-odd-elements-within-each-pair-of-quadword-vector-segments-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svuzpq[_bf16_x2]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svuzpq%5B_bf16_x2%5D

### Signature (source notation)

```c
svbfloat16x2_t svuzpq[_bf16_x2](svbfloat16x2_t zn)
    __arm_streaming;
```

### Description

Concatenate elements from two vectors

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Vector manipulation / Unzip elements

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
  "return_base_type": "bfloat16",
  "element_bit_size": "16",
  "value": "svbfloat16x2_t"
}
```

### Argument preparation and constraints

```json
{
  "zn": {
    "register sequence": "Zreg3.Q, Zreg4.Q"
  }
}
```

### Result mapping

```json
[
  {
    "{ Zreg1.Q, Zreg2.Q }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
UZP { Zreg1.Q, Zreg2.Q }, Zreg3.Q, Zreg4.Q
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/UZP--two-registers---Concatenate-elements-from-two-vectors-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svuzpq[_bf16_x4]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svuzpq%5B_bf16_x4%5D

### Signature (source notation)

```c
svbfloat16x4_t svuzpq[_bf16_x4](svbfloat16x4_t zn)
    __arm_streaming;
```

### Description

Concatenate elements from four vectors

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Vector manipulation / Unzip elements

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
  "return_base_type": "bfloat16",
  "element_bit_size": "16",
  "value": "svbfloat16x4_t"
}
```

### Argument preparation and constraints

```json
{
  "zn": {
    "Z multi-vector": "{ Zreg3.Q - Zreg4.Q }"
  }
}
```

### Result mapping

```json
[
  {
    "{ Zreg1.Q - Zreg2.Q }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
UZP { Zreg1.Q - Zreg2.Q }, { Zreg3.Q - Zreg4.Q }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/UZP--four-registers---Concatenate-elements-from-four-vectors-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svuzpq[_f16_x2]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svuzpq%5B_f16_x2%5D

### Signature (source notation)

```c
svfloat16x2_t svuzpq[_f16_x2](svfloat16x2_t zn)
    __arm_streaming;
```

### Description

Concatenate elements from two vectors

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Vector manipulation / Unzip elements

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
  "return_base_type": "float16",
  "element_bit_size": "16",
  "value": "svfloat16x2_t"
}
```

### Argument preparation and constraints

```json
{
  "zn": {
    "register sequence": "Zreg3.Q, Zreg4.Q"
  }
}
```

### Result mapping

```json
[
  {
    "{ Zreg1.Q, Zreg2.Q }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
UZP { Zreg1.Q, Zreg2.Q }, Zreg3.Q, Zreg4.Q
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/UZP--two-registers---Concatenate-elements-from-two-vectors-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svuzpq[_f16_x4]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svuzpq%5B_f16_x4%5D

### Signature (source notation)

```c
svfloat16x4_t svuzpq[_f16_x4](svfloat16x4_t zn)
    __arm_streaming;
```

### Description

Concatenate elements from four vectors

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Vector manipulation / Unzip elements

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
  "return_base_type": "float16",
  "element_bit_size": "16",
  "value": "svfloat16x4_t"
}
```

### Argument preparation and constraints

```json
{
  "zn": {
    "Z multi-vector": "{ Zreg3.Q - Zreg4.Q }"
  }
}
```

### Result mapping

```json
[
  {
    "{ Zreg1.Q - Zreg2.Q }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
UZP { Zreg1.Q - Zreg2.Q }, { Zreg3.Q - Zreg4.Q }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/UZP--four-registers---Concatenate-elements-from-four-vectors-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svuzpq[_f32_x2]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svuzpq%5B_f32_x2%5D

### Signature (source notation)

```c
svfloat32x2_t svuzpq[_f32_x2](svfloat32x2_t zn)
    __arm_streaming;
```

### Description

Concatenate elements from two vectors

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Vector manipulation / Unzip elements

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
  "return_base_type": "float32",
  "element_bit_size": "32",
  "value": "svfloat32x2_t"
}
```

### Argument preparation and constraints

```json
{
  "zn": {
    "register sequence": "Zreg3.Q, Zreg4.Q"
  }
}
```

### Result mapping

```json
[
  {
    "{ Zreg1.Q, Zreg2.Q }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
UZP { Zreg1.Q, Zreg2.Q }, Zreg3.Q, Zreg4.Q
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/UZP--two-registers---Concatenate-elements-from-two-vectors-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svuzpq[_f32_x4]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svuzpq%5B_f32_x4%5D

### Signature (source notation)

```c
svfloat32x4_t svuzpq[_f32_x4](svfloat32x4_t zn)
    __arm_streaming;
```

### Description

Concatenate elements from four vectors

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Vector manipulation / Unzip elements

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
  "return_base_type": "float32",
  "element_bit_size": "32",
  "value": "svfloat32x4_t"
}
```

### Argument preparation and constraints

```json
{
  "zn": {
    "Z multi-vector": "{ Zreg3.Q - Zreg4.Q }"
  }
}
```

### Result mapping

```json
[
  {
    "{ Zreg1.Q - Zreg2.Q }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
UZP { Zreg1.Q - Zreg2.Q }, { Zreg3.Q - Zreg4.Q }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/UZP--four-registers---Concatenate-elements-from-four-vectors-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svuzpq[_f64_x2]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svuzpq%5B_f64_x2%5D

### Signature (source notation)

```c
svfloat64x2_t svuzpq[_f64_x2](svfloat64x2_t zn)
    __arm_streaming;
```

### Description

Concatenate elements from two vectors

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Vector manipulation / Unzip elements

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
  "return_base_type": "float64",
  "element_bit_size": "64",
  "value": "svfloat64x2_t"
}
```

### Argument preparation and constraints

```json
{
  "zn": {
    "register sequence": "Zreg3.Q, Zreg4.Q"
  }
}
```

### Result mapping

```json
[
  {
    "{ Zreg1.Q, Zreg2.Q }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
UZP { Zreg1.Q, Zreg2.Q }, Zreg3.Q, Zreg4.Q
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/UZP--two-registers---Concatenate-elements-from-two-vectors-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svuzpq[_f64_x4]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svuzpq%5B_f64_x4%5D

### Signature (source notation)

```c
svfloat64x4_t svuzpq[_f64_x4](svfloat64x4_t zn)
    __arm_streaming;
```

### Description

Concatenate elements from four vectors

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Vector manipulation / Unzip elements

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
  "return_base_type": "float64",
  "element_bit_size": "64",
  "value": "svfloat64x4_t"
}
```

### Argument preparation and constraints

```json
{
  "zn": {
    "Z multi-vector": "{ Zreg3.Q - Zreg4.Q }"
  }
}
```

### Result mapping

```json
[
  {
    "{ Zreg1.Q - Zreg2.Q }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
UZP { Zreg1.Q - Zreg2.Q }, { Zreg3.Q - Zreg4.Q }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/UZP--four-registers---Concatenate-elements-from-four-vectors-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svuzpq[_mf8_x2]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svuzpq%5B_mf8_x2%5D

### Signature (source notation)

```c
svmfloat8x2_t svuzpq[_mf8_x2](svmfloat8x2_t zn)
    __arm_streaming;
```

### Description

Concatenate elements from two vectors

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Vector manipulation / Unzip elements

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
  "return_base_type": "mfloat8",
  "element_bit_size": "8",
  "value": "svmfloat8x2_t"
}
```

### Argument preparation and constraints

```json
{
  "zn": {
    "register sequence": "Zreg3.Q, Zreg4.Q"
  }
}
```

### Result mapping

```json
[
  {
    "{ Zreg1.Q, Zreg2.Q }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
UZP { Zreg1.Q, Zreg2.Q }, Zreg3.Q, Zreg4.Q
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/UZP--two-registers---Concatenate-elements-from-two-vectors-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svuzpq[_mf8_x4]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svuzpq%5B_mf8_x4%5D

### Signature (source notation)

```c
svmfloat8x4_t svuzpq[_mf8_x4](svmfloat8x4_t zn)
    __arm_streaming;
```

### Description

Concatenate elements from four vectors

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Vector manipulation / Unzip elements

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
  "return_base_type": "mfloat8",
  "element_bit_size": "8",
  "value": "svmfloat8x4_t"
}
```

### Argument preparation and constraints

```json
{
  "zn": {
    "Z multi-vector": "{ Zreg3.Q - Zreg4.Q }"
  }
}
```

### Result mapping

```json
[
  {
    "{ Zreg1.Q - Zreg2.Q }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
UZP { Zreg1.Q - Zreg2.Q }, { Zreg3.Q - Zreg4.Q }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/UZP--four-registers---Concatenate-elements-from-four-vectors-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svuzpq[_s16_x2]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svuzpq%5B_s16_x2%5D

### Signature (source notation)

```c
svint16x2_t svuzpq[_s16_x2](svint16x2_t zn)
    __arm_streaming;
```

### Description

Concatenate elements from two vectors

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Vector manipulation / Unzip elements

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
    "register sequence": "Zreg3.Q, Zreg4.Q"
  }
}
```

### Result mapping

```json
[
  {
    "{ Zreg1.Q, Zreg2.Q }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
UZP { Zreg1.Q, Zreg2.Q }, Zreg3.Q, Zreg4.Q
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/UZP--two-registers---Concatenate-elements-from-two-vectors-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svuzpq[_s16_x4]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svuzpq%5B_s16_x4%5D

### Signature (source notation)

```c
svint16x4_t svuzpq[_s16_x4](svint16x4_t zn)
    __arm_streaming;
```

### Description

Concatenate elements from four vectors

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Vector manipulation / Unzip elements

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
    "Z multi-vector": "{ Zreg3.Q - Zreg4.Q }"
  }
}
```

### Result mapping

```json
[
  {
    "{ Zreg1.Q - Zreg2.Q }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
UZP { Zreg1.Q - Zreg2.Q }, { Zreg3.Q - Zreg4.Q }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/UZP--four-registers---Concatenate-elements-from-four-vectors-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svuzpq[_s32_x2]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svuzpq%5B_s32_x2%5D

### Signature (source notation)

```c
svint32x2_t svuzpq[_s32_x2](svint32x2_t zn)
    __arm_streaming;
```

### Description

Concatenate elements from two vectors

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Vector manipulation / Unzip elements

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
    "register sequence": "Zreg3.Q, Zreg4.Q"
  }
}
```

### Result mapping

```json
[
  {
    "{ Zreg1.Q, Zreg2.Q }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
UZP { Zreg1.Q, Zreg2.Q }, Zreg3.Q, Zreg4.Q
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/UZP--two-registers---Concatenate-elements-from-two-vectors-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svuzpq[_s32_x4]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svuzpq%5B_s32_x4%5D

### Signature (source notation)

```c
svint32x4_t svuzpq[_s32_x4](svint32x4_t zn)
    __arm_streaming;
```

### Description

Concatenate elements from four vectors

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Vector manipulation / Unzip elements

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
    "Z multi-vector": "{ Zreg3.Q - Zreg4.Q }"
  }
}
```

### Result mapping

```json
[
  {
    "{ Zreg1.Q - Zreg2.Q }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
UZP { Zreg1.Q - Zreg2.Q }, { Zreg3.Q - Zreg4.Q }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/UZP--four-registers---Concatenate-elements-from-four-vectors-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svuzpq[_s64_x2]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svuzpq%5B_s64_x2%5D

### Signature (source notation)

```c
svint64x2_t svuzpq[_s64_x2](svint64x2_t zn)
    __arm_streaming;
```

### Description

Concatenate elements from two vectors

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Vector manipulation / Unzip elements

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
    "register sequence": "Zreg3.Q, Zreg4.Q"
  }
}
```

### Result mapping

```json
[
  {
    "{ Zreg1.Q, Zreg2.Q }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
UZP { Zreg1.Q, Zreg2.Q }, Zreg3.Q, Zreg4.Q
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/UZP--two-registers---Concatenate-elements-from-two-vectors-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svuzpq[_s64_x4]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svuzpq%5B_s64_x4%5D

### Signature (source notation)

```c
svint64x4_t svuzpq[_s64_x4](svint64x4_t zn)
    __arm_streaming;
```

### Description

Concatenate elements from four vectors

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Vector manipulation / Unzip elements

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
    "Z multi-vector": "{ Zreg3.Q - Zreg4.Q }"
  }
}
```

### Result mapping

```json
[
  {
    "{ Zreg1.Q - Zreg2.Q }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
UZP { Zreg1.Q - Zreg2.Q }, { Zreg3.Q - Zreg4.Q }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/UZP--four-registers---Concatenate-elements-from-four-vectors-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svuzpq[_s8_x2]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svuzpq%5B_s8_x2%5D

### Signature (source notation)

```c
svint8x2_t svuzpq[_s8_x2](svint8x2_t zn)
    __arm_streaming;
```

### Description

Concatenate elements from two vectors

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Vector manipulation / Unzip elements

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
  "zn": {
    "register sequence": "Zreg3.Q, Zreg4.Q"
  }
}
```

### Result mapping

```json
[
  {
    "{ Zreg1.Q, Zreg2.Q }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
UZP { Zreg1.Q, Zreg2.Q }, Zreg3.Q, Zreg4.Q
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/UZP--two-registers---Concatenate-elements-from-two-vectors-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svuzpq[_s8_x4]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svuzpq%5B_s8_x4%5D

### Signature (source notation)

```c
svint8x4_t svuzpq[_s8_x4](svint8x4_t zn)
    __arm_streaming;
```

### Description

Concatenate elements from four vectors

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Vector manipulation / Unzip elements

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
  "zn": {
    "Z multi-vector": "{ Zreg3.Q - Zreg4.Q }"
  }
}
```

### Result mapping

```json
[
  {
    "{ Zreg1.Q - Zreg2.Q }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
UZP { Zreg1.Q - Zreg2.Q }, { Zreg3.Q - Zreg4.Q }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/UZP--four-registers---Concatenate-elements-from-four-vectors-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svuzpq[_u16_x2]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svuzpq%5B_u16_x2%5D

### Signature (source notation)

```c
svuint16x2_t svuzpq[_u16_x2](svuint16x2_t zn)
    __arm_streaming;
```

### Description

Concatenate elements from two vectors

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Vector manipulation / Unzip elements

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
    "register sequence": "Zreg3.Q, Zreg4.Q"
  }
}
```

### Result mapping

```json
[
  {
    "{ Zreg1.Q, Zreg2.Q }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
UZP { Zreg1.Q, Zreg2.Q }, Zreg3.Q, Zreg4.Q
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/UZP--two-registers---Concatenate-elements-from-two-vectors-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svuzpq[_u16_x4]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svuzpq%5B_u16_x4%5D

### Signature (source notation)

```c
svuint16x4_t svuzpq[_u16_x4](svuint16x4_t zn)
    __arm_streaming;
```

### Description

Concatenate elements from four vectors

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Vector manipulation / Unzip elements

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
    "Z multi-vector": "{ Zreg3.Q - Zreg4.Q }"
  }
}
```

### Result mapping

```json
[
  {
    "{ Zreg1.Q - Zreg2.Q }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
UZP { Zreg1.Q - Zreg2.Q }, { Zreg3.Q - Zreg4.Q }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/UZP--four-registers---Concatenate-elements-from-four-vectors-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svuzpq[_u32_x2]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svuzpq%5B_u32_x2%5D

### Signature (source notation)

```c
svuint32x2_t svuzpq[_u32_x2](svuint32x2_t zn)
    __arm_streaming;
```

### Description

Concatenate elements from two vectors

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Vector manipulation / Unzip elements

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
    "register sequence": "Zreg3.Q, Zreg4.Q"
  }
}
```

### Result mapping

```json
[
  {
    "{ Zreg1.Q, Zreg2.Q }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
UZP { Zreg1.Q, Zreg2.Q }, Zreg3.Q, Zreg4.Q
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/UZP--two-registers---Concatenate-elements-from-two-vectors-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svuzpq[_u32_x4]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svuzpq%5B_u32_x4%5D

### Signature (source notation)

```c
svuint32x4_t svuzpq[_u32_x4](svuint32x4_t zn)
    __arm_streaming;
```

### Description

Concatenate elements from four vectors

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Vector manipulation / Unzip elements

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
    "Z multi-vector": "{ Zreg3.Q - Zreg4.Q }"
  }
}
```

### Result mapping

```json
[
  {
    "{ Zreg1.Q - Zreg2.Q }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
UZP { Zreg1.Q - Zreg2.Q }, { Zreg3.Q - Zreg4.Q }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/UZP--four-registers---Concatenate-elements-from-four-vectors-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svuzpq[_u64_x2]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svuzpq%5B_u64_x2%5D

### Signature (source notation)

```c
svuint64x2_t svuzpq[_u64_x2](svuint64x2_t zn)
    __arm_streaming;
```

### Description

Concatenate elements from two vectors

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Vector manipulation / Unzip elements

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
    "register sequence": "Zreg3.Q, Zreg4.Q"
  }
}
```

### Result mapping

```json
[
  {
    "{ Zreg1.Q, Zreg2.Q }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
UZP { Zreg1.Q, Zreg2.Q }, Zreg3.Q, Zreg4.Q
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/UZP--two-registers---Concatenate-elements-from-two-vectors-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svuzpq[_u64_x4]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svuzpq%5B_u64_x4%5D

### Signature (source notation)

```c
svuint64x4_t svuzpq[_u64_x4](svuint64x4_t zn)
    __arm_streaming;
```

### Description

Concatenate elements from four vectors

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Vector manipulation / Unzip elements

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
    "Z multi-vector": "{ Zreg3.Q - Zreg4.Q }"
  }
}
```

### Result mapping

```json
[
  {
    "{ Zreg1.Q - Zreg2.Q }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
UZP { Zreg1.Q - Zreg2.Q }, { Zreg3.Q - Zreg4.Q }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/UZP--four-registers---Concatenate-elements-from-four-vectors-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svuzpq[_u8_x2]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svuzpq%5B_u8_x2%5D

### Signature (source notation)

```c
svuint8x2_t svuzpq[_u8_x2](svuint8x2_t zn)
    __arm_streaming;
```

### Description

Concatenate elements from two vectors

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Vector manipulation / Unzip elements

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
  "zn": {
    "register sequence": "Zreg3.Q, Zreg4.Q"
  }
}
```

### Result mapping

```json
[
  {
    "{ Zreg1.Q, Zreg2.Q }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
UZP { Zreg1.Q, Zreg2.Q }, Zreg3.Q, Zreg4.Q
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/UZP--two-registers---Concatenate-elements-from-two-vectors-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svuzpq[_u8_x4]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svuzpq%5B_u8_x4%5D

### Signature (source notation)

```c
svuint8x4_t svuzpq[_u8_x4](svuint8x4_t zn)
    __arm_streaming;
```

### Description

Concatenate elements from four vectors

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Vector manipulation / Unzip elements

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
  "zn": {
    "Z multi-vector": "{ Zreg3.Q - Zreg4.Q }"
  }
}
```

### Result mapping

```json
[
  {
    "{ Zreg1.Q - Zreg2.Q }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
UZP { Zreg1.Q - Zreg2.Q }, { Zreg3.Q - Zreg4.Q }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/UZP--four-registers---Concatenate-elements-from-four-vectors-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

