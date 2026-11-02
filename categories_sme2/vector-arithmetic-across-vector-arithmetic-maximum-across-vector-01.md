# SME2 / Vector arithmetic / Across vector arithmetic / Maximum across vector — Part 1

## svmaxqv[_f16]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmaxqv%5B_f16%5D

### Signature (source notation)

```c
float16x8_t svmaxqv[_f16](svbool_t pg, svfloat16_t zn);
```

### Description

Floating-point maximum reduction of quadword vector segments

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Across vector arithmetic / Maximum across vector

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
  "return_base_type": "float16x8_t",
  "element_bit_size": "16",
  "value": "float16x8_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Preg1"
  },
  "zn": {
    "register": "Zreg1.H"
  }
}
```

### Result mapping

```json
[
  {
    "Vreg1.8H": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
FMAXQV Vreg1.8H, Preg1, Zreg1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/FMAXQV--Floating-point-maximum-reduction-of-quadword-vector-segments-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmaxqv[_f32]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmaxqv%5B_f32%5D

### Signature (source notation)

```c
float32x4_t svmaxqv[_f32](svbool_t pg, svfloat32_t zn);
```

### Description

Floating-point maximum reduction of quadword vector segments

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Across vector arithmetic / Maximum across vector

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
  "return_base_type": "float32x4_t",
  "element_bit_size": "32",
  "value": "float32x4_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Preg1"
  },
  "zn": {
    "register": "Zreg1.S"
  }
}
```

### Result mapping

```json
[
  {
    "Vreg1.4S": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
FMAXQV Vreg1.4S, Preg1, Zreg1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/FMAXQV--Floating-point-maximum-reduction-of-quadword-vector-segments-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmaxqv[_f64]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmaxqv%5B_f64%5D

### Signature (source notation)

```c
float64x2_t svmaxqv[_f64](svbool_t pg, svfloat64_t zn);
```

### Description

Floating-point maximum reduction of quadword vector segments

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Across vector arithmetic / Maximum across vector

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
  "return_base_type": "float64x2_t",
  "element_bit_size": "64",
  "value": "float64x2_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Preg1"
  },
  "zn": {
    "register": "Zreg1.D"
  }
}
```

### Result mapping

```json
[
  {
    "Vreg1.2D": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
FMAXQV Vreg1.2D, Preg1, Zreg1.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/FMAXQV--Floating-point-maximum-reduction-of-quadword-vector-segments-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmaxqv[_s16]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmaxqv%5B_s16%5D

### Signature (source notation)

```c
int16x8_t svmaxqv[_s16](svbool_t pg, svint16_t zn);
```

### Description

Signed maximum reduction of quadword vector segments

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Across vector arithmetic / Maximum across vector

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
  "return_base_type": "int16x8_t",
  "element_bit_size": "16",
  "value": "int16x8_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Preg1"
  },
  "zn": {
    "register": "Zreg1.H"
  }
}
```

### Result mapping

```json
[
  {
    "Vreg1.8H": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
SMAXQV Vreg1.8H, Preg1, Zreg1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/SMAXQV--Signed-maximum-reduction-of-quadword-vector-segments-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmaxqv[_s32]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmaxqv%5B_s32%5D

### Signature (source notation)

```c
int32x4_t svmaxqv[_s32](svbool_t pg, svint32_t zn);
```

### Description

Signed maximum reduction of quadword vector segments

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Across vector arithmetic / Maximum across vector

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
  "return_base_type": "int32x4_t",
  "element_bit_size": "32",
  "value": "int32x4_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Preg1"
  },
  "zn": {
    "register": "Zreg1.S"
  }
}
```

### Result mapping

```json
[
  {
    "Vreg1.4S": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
SMAXQV Vreg1.4S, Preg1, Zreg1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/SMAXQV--Signed-maximum-reduction-of-quadword-vector-segments-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmaxqv[_s64]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmaxqv%5B_s64%5D

### Signature (source notation)

```c
int64x2_t svmaxqv[_s64](svbool_t pg, svint64_t zn);
```

### Description

Signed maximum reduction of quadword vector segments

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Across vector arithmetic / Maximum across vector

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
  "return_base_type": "int64x2_t",
  "element_bit_size": "64",
  "value": "int64x2_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Preg1"
  },
  "zn": {
    "register": "Zreg1.D"
  }
}
```

### Result mapping

```json
[
  {
    "Vreg1.2D": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
SMAXQV Vreg1.2D, Preg1, Zreg1.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/SMAXQV--Signed-maximum-reduction-of-quadword-vector-segments-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmaxqv[_s8]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmaxqv%5B_s8%5D

### Signature (source notation)

```c
int8x16_t svmaxqv[_s8](svbool_t pg, svint8_t zn);
```

### Description

Signed maximum reduction of quadword vector segments

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Across vector arithmetic / Maximum across vector

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
  "return_base_type": "int8x16_t",
  "element_bit_size": "8",
  "value": "int8x16_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Preg1"
  },
  "zn": {
    "register": "Zreg1.B"
  }
}
```

### Result mapping

```json
[
  {
    "Vreg1.16B": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
SMAXQV Vreg1.16B, Preg1, Zreg1.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/SMAXQV--Signed-maximum-reduction-of-quadword-vector-segments-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmaxqv[_u16]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmaxqv%5B_u16%5D

### Signature (source notation)

```c
uint16x8_t svmaxqv[_u16](svbool_t pg, svuint16_t zn);
```

### Description

Unsigned maximum reduction of quadword vector segments

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Across vector arithmetic / Maximum across vector

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
  "return_base_type": "uint16x8_t",
  "element_bit_size": "16",
  "value": "uint16x8_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Preg1"
  },
  "zn": {
    "register": "Zreg1.H"
  }
}
```

### Result mapping

```json
[
  {
    "Vreg1.8H": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
UMAXQV Vreg1.8H, Preg1, Zreg1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/UMAXQV--Unsigned-maximum-reduction-of-quadword-vector-segments-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmaxqv[_u32]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmaxqv%5B_u32%5D

### Signature (source notation)

```c
uint32x4_t svmaxqv[_u32](svbool_t pg, svuint32_t zn);
```

### Description

Unsigned maximum reduction of quadword vector segments

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Across vector arithmetic / Maximum across vector

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
  "return_base_type": "uint32x4_t",
  "element_bit_size": "32",
  "value": "uint32x4_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Preg1"
  },
  "zn": {
    "register": "Zreg1.S"
  }
}
```

### Result mapping

```json
[
  {
    "Vreg1.4S": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
UMAXQV Vreg1.4S, Preg1, Zreg1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/UMAXQV--Unsigned-maximum-reduction-of-quadword-vector-segments-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmaxqv[_u64]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmaxqv%5B_u64%5D

### Signature (source notation)

```c
uint64x2_t svmaxqv[_u64](svbool_t pg, svuint64_t zn);
```

### Description

Unsigned maximum reduction of quadword vector segments

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Across vector arithmetic / Maximum across vector

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
  "return_base_type": "uint64x2_t",
  "element_bit_size": "64",
  "value": "uint64x2_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Preg1"
  },
  "zn": {
    "register": "Zreg1.D"
  }
}
```

### Result mapping

```json
[
  {
    "Vreg1.2D": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
UMAXQV Vreg1.2D, Preg1, Zreg1.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/UMAXQV--Unsigned-maximum-reduction-of-quadword-vector-segments-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmaxqv[_u8]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmaxqv%5B_u8%5D

### Signature (source notation)

```c
uint8x16_t svmaxqv[_u8](svbool_t pg, svuint8_t zn);
```

### Description

Unsigned maximum reduction of quadword vector segments

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Across vector arithmetic / Maximum across vector

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
  "return_base_type": "uint8x16_t",
  "element_bit_size": "8",
  "value": "uint8x16_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Preg1"
  },
  "zn": {
    "register": "Zreg1.B"
  }
}
```

### Result mapping

```json
[
  {
    "Vreg1.16B": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
UMAXQV Vreg1.16B, Preg1, Zreg1.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/UMAXQV--Unsigned-maximum-reduction-of-quadword-vector-segments-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

