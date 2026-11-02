# SME2 / Predication / Element selection / Select between two vectors — Part 1

## svsel[_bf16_x2]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsel%5B_bf16_x2%5D

### Signature (source notation)

```c
svbfloat16x2_t svsel[_bf16_x2](svcount_t png, svbfloat16x2_t zn, svbfloat16x2_t zm)
    __arm_streaming;
```

### Description

Multi-vector conditionally select elements from two vectors

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Predication / Element selection / Select between two vectors

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
  "png": {
    "register": "Preg1"
  },
  "zn": {
    "Z multi-vector": "{ Zreg3.H, Zreg4.H }"
  },
  "zm": {
    "Z multi-vector": "{ Zreg5.H, Zreg6.H }"
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
SEL { Zreg1.H, Zreg2.H }, PNreg1, { Zreg3.H, Zreg4.H }, { Zreg5.H, Zreg6.H }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SEL--Multi-vector-conditionally-select-elements-from-two-vectors-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svsel[_bf16_x4]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsel%5B_bf16_x4%5D

### Signature (source notation)

```c
svbfloat16x4_t svsel[_bf16_x4](svcount_t png, svbfloat16x4_t zn, svbfloat16x4_t zm)
    __arm_streaming;
```

### Description

Multi-vector conditionally select elements from two vectors

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Predication / Element selection / Select between two vectors

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
  "png": {
    "register": "Preg1"
  },
  "zn": {
    "Z multi-vector": "{ Zreg3.H - Zreg4.H }"
  },
  "zm": {
    "Z multi-vector": "{ Zreg5.H - Zreg6.H }"
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
SEL { Zreg1.H - Zreg2.H }, PNreg1, { Zreg3.H - Zreg4.H }, { Zreg5.H - Zreg6.H }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SEL--Multi-vector-conditionally-select-elements-from-two-vectors-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svsel[_f16_x2]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsel%5B_f16_x2%5D

### Signature (source notation)

```c
svfloat16x2_t svsel[_f16_x2](svcount_t png, svfloat16x2_t zn, svfloat16x2_t zm)
    __arm_streaming;
```

### Description

Multi-vector conditionally select elements from two vectors

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Predication / Element selection / Select between two vectors

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
  "png": {
    "register": "Preg1"
  },
  "zn": {
    "Z multi-vector": "{ Zreg3.H, Zreg4.H }"
  },
  "zm": {
    "Z multi-vector": "{ Zreg5.H, Zreg6.H }"
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
SEL { Zreg1.H, Zreg2.H }, PNreg1, { Zreg3.H, Zreg4.H }, { Zreg5.H, Zreg6.H }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SEL--Multi-vector-conditionally-select-elements-from-two-vectors-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svsel[_f16_x4]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsel%5B_f16_x4%5D

### Signature (source notation)

```c
svfloat16x4_t svsel[_f16_x4](svcount_t png, svfloat16x4_t zn, svfloat16x4_t zm)
    __arm_streaming;
```

### Description

Multi-vector conditionally select elements from two vectors

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Predication / Element selection / Select between two vectors

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
  "png": {
    "register": "Preg1"
  },
  "zn": {
    "Z multi-vector": "{ Zreg3.H - Zreg4.H }"
  },
  "zm": {
    "Z multi-vector": "{ Zreg5.H - Zreg6.H }"
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
SEL { Zreg1.H - Zreg2.H }, PNreg1, { Zreg3.H - Zreg4.H }, { Zreg5.H - Zreg6.H }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SEL--Multi-vector-conditionally-select-elements-from-two-vectors-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svsel[_f32_x2]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsel%5B_f32_x2%5D

### Signature (source notation)

```c
svfloat32x2_t svsel[_f32_x2](svcount_t png, svfloat32x2_t zn, svfloat32x2_t zm)
    __arm_streaming;
```

### Description

Multi-vector conditionally select elements from two vectors

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Predication / Element selection / Select between two vectors

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
  "png": {
    "register": "Preg1"
  },
  "zn": {
    "Z multi-vector": "{ Zreg3.S, Zreg4.S }"
  },
  "zm": {
    "Z multi-vector": "{ Zreg5.S, Zreg6.S }"
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
SEL { Zreg1.S, Zreg2.S }, PNreg1, { Zreg3.S, Zreg4.S }, { Zreg5.S, Zreg6.S }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SEL--Multi-vector-conditionally-select-elements-from-two-vectors-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svsel[_f32_x4]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsel%5B_f32_x4%5D

### Signature (source notation)

```c
svfloat32x4_t svsel[_f32_x4](svcount_t png, svfloat32x4_t zn, svfloat32x4_t zm)
    __arm_streaming;
```

### Description

Multi-vector conditionally select elements from two vectors

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Predication / Element selection / Select between two vectors

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
  "png": {
    "register": "Preg1"
  },
  "zn": {
    "Z multi-vector": "{ Zreg3.S - Zreg4.S }"
  },
  "zm": {
    "Z multi-vector": "{ Zreg5.S - Zreg6.S }"
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
SEL { Zreg1.S - Zreg2.S }, PNreg1, { Zreg3.S - Zreg4.S }, { Zreg5.S - Zreg6.S }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SEL--Multi-vector-conditionally-select-elements-from-two-vectors-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svsel[_f64_x2]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsel%5B_f64_x2%5D

### Signature (source notation)

```c
svfloat64x2_t svsel[_f64_x2](svcount_t png, svfloat64x2_t zn, svfloat64x2_t zm)
    __arm_streaming;
```

### Description

Multi-vector conditionally select elements from two vectors

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Predication / Element selection / Select between two vectors

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
  "png": {
    "register": "Preg1"
  },
  "zn": {
    "Z multi-vector": "{ Zreg3.D, Zreg4.D }"
  },
  "zm": {
    "Z multi-vector": "{ Zreg5.D, Zreg6.D }"
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
SEL { Zreg1.D, Zreg2.D }, PNreg1, { Zreg3.D, Zreg4.D }, { Zreg5.D, Zreg6.D }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SEL--Multi-vector-conditionally-select-elements-from-two-vectors-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svsel[_f64_x4]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsel%5B_f64_x4%5D

### Signature (source notation)

```c
svfloat64x4_t svsel[_f64_x4](svcount_t png, svfloat64x4_t zn, svfloat64x4_t zm)
    __arm_streaming;
```

### Description

Multi-vector conditionally select elements from two vectors

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Predication / Element selection / Select between two vectors

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
  "png": {
    "register": "Preg1"
  },
  "zn": {
    "Z multi-vector": "{ Zreg3.D - Zreg4.D }"
  },
  "zm": {
    "Z multi-vector": "{ Zreg5.D - Zreg6.D }"
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
SEL { Zreg1.D - Zreg2.D }, PNreg1, { Zreg3.D - Zreg4.D }, { Zreg5.D - Zreg6.D }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SEL--Multi-vector-conditionally-select-elements-from-two-vectors-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svsel[_mf8_x2]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsel%5B_mf8_x2%5D

### Signature (source notation)

```c
svmfloat8x2_t svsel[_mf8_x2](svcount_t png, svmfloat8x2_t zn, svmfloat8x2_t zm)
    __arm_streaming;
```

### Description

Multi-vector conditionally select elements from two vectors

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Predication / Element selection / Select between two vectors

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
  "png": {
    "register": "Preg1"
  },
  "zn": {
    "Z multi-vector": "{ Zreg3.B, Zreg4.B }"
  },
  "zm": {
    "Z multi-vector": "{ Zreg5.B, Zreg6.B }"
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
SEL { Zreg1.B, Zreg2.B }, PNreg1, { Zreg3.B, Zreg4.B }, { Zreg5.B, Zreg6.B }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SEL--Multi-vector-conditionally-select-elements-from-two-vectors-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svsel[_mf8_x4]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsel%5B_mf8_x4%5D

### Signature (source notation)

```c
svmfloat8x4_t svsel[_mf8_x4](svcount_t png, svmfloat8x4_t zn, svmfloat8x4_t zm)
    __arm_streaming;
```

### Description

Multi-vector conditionally select elements from two vectors

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Predication / Element selection / Select between two vectors

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
  "png": {
    "register": "Preg1"
  },
  "zn": {
    "Z multi-vector": "{ Zreg3.B - Zreg4.B }"
  },
  "zm": {
    "Z multi-vector": "{ Zreg5.B - Zreg6.B }"
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
SEL { Zreg1.B - Zreg2.B }, PNreg1, { Zreg3.B - Zreg4.B }, { Zreg5.B - Zreg6.B }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SEL--Multi-vector-conditionally-select-elements-from-two-vectors-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svsel[_s16_x2]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsel%5B_s16_x2%5D

### Signature (source notation)

```c
svint16x2_t svsel[_s16_x2](svcount_t png, svint16x2_t zn, svint16x2_t zm)
    __arm_streaming;
```

### Description

Multi-vector conditionally select elements from two vectors

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Predication / Element selection / Select between two vectors

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
  "png": {
    "register": "Preg1"
  },
  "zn": {
    "Z multi-vector": "{ Zreg3.H, Zreg4.H }"
  },
  "zm": {
    "Z multi-vector": "{ Zreg5.H, Zreg6.H }"
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
SEL { Zreg1.H, Zreg2.H }, PNreg1, { Zreg3.H, Zreg4.H }, { Zreg5.H, Zreg6.H }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SEL--Multi-vector-conditionally-select-elements-from-two-vectors-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svsel[_s16_x4]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsel%5B_s16_x4%5D

### Signature (source notation)

```c
svint16x4_t svsel[_s16_x4](svcount_t png, svint16x4_t zn, svint16x4_t zm)
    __arm_streaming;
```

### Description

Multi-vector conditionally select elements from two vectors

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Predication / Element selection / Select between two vectors

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
  "png": {
    "register": "Preg1"
  },
  "zn": {
    "Z multi-vector": "{ Zreg3.H - Zreg4.H }"
  },
  "zm": {
    "Z multi-vector": "{ Zreg5.H - Zreg6.H }"
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
SEL { Zreg1.H - Zreg2.H }, PNreg1, { Zreg3.H - Zreg4.H }, { Zreg5.H - Zreg6.H }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SEL--Multi-vector-conditionally-select-elements-from-two-vectors-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svsel[_s32_x2]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsel%5B_s32_x2%5D

### Signature (source notation)

```c
svint32x2_t svsel[_s32_x2](svcount_t png, svint32x2_t zn, svint32x2_t zm)
    __arm_streaming;
```

### Description

Multi-vector conditionally select elements from two vectors

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Predication / Element selection / Select between two vectors

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
  "png": {
    "register": "Preg1"
  },
  "zn": {
    "Z multi-vector": "{ Zreg3.S, Zreg4.S }"
  },
  "zm": {
    "Z multi-vector": "{ Zreg5.S, Zreg6.S }"
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
SEL { Zreg1.S, Zreg2.S }, PNreg1, { Zreg3.S, Zreg4.S }, { Zreg5.S, Zreg6.S }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SEL--Multi-vector-conditionally-select-elements-from-two-vectors-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svsel[_s32_x4]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsel%5B_s32_x4%5D

### Signature (source notation)

```c
svint32x4_t svsel[_s32_x4](svcount_t png, svint32x4_t zn, svint32x4_t zm)
    __arm_streaming;
```

### Description

Multi-vector conditionally select elements from two vectors

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Predication / Element selection / Select between two vectors

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
  "png": {
    "register": "Preg1"
  },
  "zn": {
    "Z multi-vector": "{ Zreg3.S - Zreg4.S }"
  },
  "zm": {
    "Z multi-vector": "{ Zreg5.S - Zreg6.S }"
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
SEL { Zreg1.S - Zreg2.S }, PNreg1, { Zreg3.S - Zreg4.S }, { Zreg5.S - Zreg6.S }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SEL--Multi-vector-conditionally-select-elements-from-two-vectors-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svsel[_s64_x2]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsel%5B_s64_x2%5D

### Signature (source notation)

```c
svint64x2_t svsel[_s64_x2](svcount_t png, svint64x2_t zn, svint64x2_t zm)
    __arm_streaming;
```

### Description

Multi-vector conditionally select elements from two vectors

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Predication / Element selection / Select between two vectors

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
  "png": {
    "register": "Preg1"
  },
  "zn": {
    "Z multi-vector": "{ Zreg3.D, Zreg4.D }"
  },
  "zm": {
    "Z multi-vector": "{ Zreg5.D, Zreg6.D }"
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
SEL { Zreg1.D, Zreg2.D }, PNreg1, { Zreg3.D, Zreg4.D }, { Zreg5.D, Zreg6.D }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SEL--Multi-vector-conditionally-select-elements-from-two-vectors-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svsel[_s64_x4]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsel%5B_s64_x4%5D

### Signature (source notation)

```c
svint64x4_t svsel[_s64_x4](svcount_t png, svint64x4_t zn, svint64x4_t zm)
    __arm_streaming;
```

### Description

Multi-vector conditionally select elements from two vectors

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Predication / Element selection / Select between two vectors

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
  "png": {
    "register": "Preg1"
  },
  "zn": {
    "Z multi-vector": "{ Zreg3.D - Zreg4.D }"
  },
  "zm": {
    "Z multi-vector": "{ Zreg5.D - Zreg6.D }"
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
SEL { Zreg1.D - Zreg2.D }, PNreg1, { Zreg3.D - Zreg4.D }, { Zreg5.D - Zreg6.D }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SEL--Multi-vector-conditionally-select-elements-from-two-vectors-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svsel[_s8_x2]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsel%5B_s8_x2%5D

### Signature (source notation)

```c
svint8x2_t svsel[_s8_x2](svcount_t png, svint8x2_t zn, svint8x2_t zm)
    __arm_streaming;
```

### Description

Multi-vector conditionally select elements from two vectors

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Predication / Element selection / Select between two vectors

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
  "png": {
    "register": "Preg1"
  },
  "zn": {
    "Z multi-vector": "{ Zreg3.B, Zreg4.B }"
  },
  "zm": {
    "Z multi-vector": "{ Zreg5.B, Zreg6.B }"
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
SEL { Zreg1.B, Zreg2.B }, PNreg1, { Zreg3.B, Zreg4.B }, { Zreg5.B, Zreg6.B }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SEL--Multi-vector-conditionally-select-elements-from-two-vectors-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svsel[_s8_x4]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsel%5B_s8_x4%5D

### Signature (source notation)

```c
svint8x4_t svsel[_s8_x4](svcount_t png, svint8x4_t zn, svint8x4_t zm)
    __arm_streaming;
```

### Description

Multi-vector conditionally select elements from two vectors

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Predication / Element selection / Select between two vectors

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
  "png": {
    "register": "Preg1"
  },
  "zn": {
    "Z multi-vector": "{ Zreg3.B - Zreg4.B }"
  },
  "zm": {
    "Z multi-vector": "{ Zreg5.B - Zreg6.B }"
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
SEL { Zreg1.B - Zreg2.B }, PNreg1, { Zreg3.B - Zreg4.B }, { Zreg5.B - Zreg6.B }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SEL--Multi-vector-conditionally-select-elements-from-two-vectors-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svsel[_u16_x2]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsel%5B_u16_x2%5D

### Signature (source notation)

```c
svuint16x2_t svsel[_u16_x2](svcount_t png, svuint16x2_t zn, svuint16x2_t zm)
    __arm_streaming;
```

### Description

Multi-vector conditionally select elements from two vectors

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Predication / Element selection / Select between two vectors

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
  "png": {
    "register": "Preg1"
  },
  "zn": {
    "Z multi-vector": "{ Zreg3.H, Zreg4.H }"
  },
  "zm": {
    "Z multi-vector": "{ Zreg5.H, Zreg6.H }"
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
SEL { Zreg1.H, Zreg2.H }, PNreg1, { Zreg3.H, Zreg4.H }, { Zreg5.H, Zreg6.H }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SEL--Multi-vector-conditionally-select-elements-from-two-vectors-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svsel[_u16_x4]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsel%5B_u16_x4%5D

### Signature (source notation)

```c
svuint16x4_t svsel[_u16_x4](svcount_t png, svuint16x4_t zn, svuint16x4_t zm)
    __arm_streaming;
```

### Description

Multi-vector conditionally select elements from two vectors

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Predication / Element selection / Select between two vectors

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
  "png": {
    "register": "Preg1"
  },
  "zn": {
    "Z multi-vector": "{ Zreg3.H - Zreg4.H }"
  },
  "zm": {
    "Z multi-vector": "{ Zreg5.H - Zreg6.H }"
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
SEL { Zreg1.H - Zreg2.H }, PNreg1, { Zreg3.H - Zreg4.H }, { Zreg5.H - Zreg6.H }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SEL--Multi-vector-conditionally-select-elements-from-two-vectors-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svsel[_u32_x2]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsel%5B_u32_x2%5D

### Signature (source notation)

```c
svuint32x2_t svsel[_u32_x2](svcount_t png, svuint32x2_t zn, svuint32x2_t zm)
    __arm_streaming;
```

### Description

Multi-vector conditionally select elements from two vectors

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Predication / Element selection / Select between two vectors

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
  "png": {
    "register": "Preg1"
  },
  "zn": {
    "Z multi-vector": "{ Zreg3.S, Zreg4.S }"
  },
  "zm": {
    "Z multi-vector": "{ Zreg5.S, Zreg6.S }"
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
SEL { Zreg1.S, Zreg2.S }, PNreg1, { Zreg3.S, Zreg4.S }, { Zreg5.S, Zreg6.S }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SEL--Multi-vector-conditionally-select-elements-from-two-vectors-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svsel[_u32_x4]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsel%5B_u32_x4%5D

### Signature (source notation)

```c
svuint32x4_t svsel[_u32_x4](svcount_t png, svuint32x4_t zn, svuint32x4_t zm)
    __arm_streaming;
```

### Description

Multi-vector conditionally select elements from two vectors

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Predication / Element selection / Select between two vectors

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
  "png": {
    "register": "Preg1"
  },
  "zn": {
    "Z multi-vector": "{ Zreg3.S - Zreg4.S }"
  },
  "zm": {
    "Z multi-vector": "{ Zreg5.S - Zreg6.S }"
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
SEL { Zreg1.S - Zreg2.S }, PNreg1, { Zreg3.S - Zreg4.S }, { Zreg5.S - Zreg6.S }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SEL--Multi-vector-conditionally-select-elements-from-two-vectors-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svsel[_u64_x2]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsel%5B_u64_x2%5D

### Signature (source notation)

```c
svuint64x2_t svsel[_u64_x2](svcount_t png, svuint64x2_t zn, svuint64x2_t zm)
    __arm_streaming;
```

### Description

Multi-vector conditionally select elements from two vectors

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Predication / Element selection / Select between two vectors

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
  "png": {
    "register": "Preg1"
  },
  "zn": {
    "Z multi-vector": "{ Zreg3.D, Zreg4.D }"
  },
  "zm": {
    "Z multi-vector": "{ Zreg5.D, Zreg6.D }"
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
SEL { Zreg1.D, Zreg2.D }, PNreg1, { Zreg3.D, Zreg4.D }, { Zreg5.D, Zreg6.D }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SEL--Multi-vector-conditionally-select-elements-from-two-vectors-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svsel[_u64_x4]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsel%5B_u64_x4%5D

### Signature (source notation)

```c
svuint64x4_t svsel[_u64_x4](svcount_t png, svuint64x4_t zn, svuint64x4_t zm)
    __arm_streaming;
```

### Description

Multi-vector conditionally select elements from two vectors

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Predication / Element selection / Select between two vectors

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
  "png": {
    "register": "Preg1"
  },
  "zn": {
    "Z multi-vector": "{ Zreg3.D - Zreg4.D }"
  },
  "zm": {
    "Z multi-vector": "{ Zreg5.D - Zreg6.D }"
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
SEL { Zreg1.D - Zreg2.D }, PNreg1, { Zreg3.D - Zreg4.D }, { Zreg5.D - Zreg6.D }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SEL--Multi-vector-conditionally-select-elements-from-two-vectors-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svsel[_u8_x2]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsel%5B_u8_x2%5D

### Signature (source notation)

```c
svuint8x2_t svsel[_u8_x2](svcount_t png, svuint8x2_t zn, svuint8x2_t zm)
    __arm_streaming;
```

### Description

Multi-vector conditionally select elements from two vectors

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Predication / Element selection / Select between two vectors

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
  "png": {
    "register": "Preg1"
  },
  "zn": {
    "Z multi-vector": "{ Zreg3.B, Zreg4.B }"
  },
  "zm": {
    "Z multi-vector": "{ Zreg5.B, Zreg6.B }"
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
SEL { Zreg1.B, Zreg2.B }, PNreg1, { Zreg3.B, Zreg4.B }, { Zreg5.B, Zreg6.B }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SEL--Multi-vector-conditionally-select-elements-from-two-vectors-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svsel[_u8_x4]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsel%5B_u8_x4%5D

### Signature (source notation)

```c
svuint8x4_t svsel[_u8_x4](svcount_t png, svuint8x4_t zn, svuint8x4_t zm)
    __arm_streaming;
```

### Description

Multi-vector conditionally select elements from two vectors

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Predication / Element selection / Select between two vectors

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
  "png": {
    "register": "Preg1"
  },
  "zn": {
    "Z multi-vector": "{ Zreg3.B - Zreg4.B }"
  },
  "zm": {
    "Z multi-vector": "{ Zreg5.B - Zreg6.B }"
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
SEL { Zreg1.B - Zreg2.B }, PNreg1, { Zreg3.B - Zreg4.B }, { Zreg5.B - Zreg6.B }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SEL--Multi-vector-conditionally-select-elements-from-two-vectors-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

