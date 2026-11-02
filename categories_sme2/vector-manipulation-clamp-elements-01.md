# SME2 / Vector manipulation / Clamp elements — Part 1

## svclamp[_bf16]

ISA classification: SME2 + FEAT_SVE_B16B16

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svclamp%5B_bf16%5D

### Signature (source notation)

```c
svbfloat16_t svclamp[_bf16](svbfloat16_t op, svbfloat16_t min, svbfloat16_t max);
```

### Description

BFloat16 clamp to minimum/maximum number

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Clamp elements

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2,FEAT_SVE_B16B16
```

### Return type metadata

```json
{
  "return_base_type": "bfloat16",
  "element_bit_size": "16",
  "value": "svbfloat16_t"
}
```

### Argument preparation and constraints

```json
{
  "op": {
    "register": "Zreg1.H"
  },
  "min": {
    "register": "Zreg2.H"
  },
  "max": {
    "register": "Zreg3.H"
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
BFCLAMP Zreg1.H, Zreg2.H, Zreg3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/BFCLAMP--BFloat16-clamp-to-minimum-maximum-number-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svclamp[_f16]

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svclamp%5B_f16%5D

### Signature (source notation)

```c
svfloat16_t svclamp[_f16](svfloat16_t op, svfloat16_t min, svfloat16_t max);
```

### Description

Floating-point clamp to minimum/maximum number

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector manipulation / Clamp elements

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
  "return_base_type": "float16",
  "element_bit_size": "16",
  "value": "svfloat16_t"
}
```

### Argument preparation and constraints

```json
{
  "op": {
    "register": "Zreg1.H"
  },
  "min": {
    "register": "Zreg2.H"
  },
  "max": {
    "register": "Zreg3.H"
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
FCLAMP Zreg1.H, Zreg2.H, Zreg3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCLAMP--Floating-point-clamp-to-minimum-maximum-number-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svclamp[_f32]

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svclamp%5B_f32%5D

### Signature (source notation)

```c
svfloat32_t svclamp[_f32](svfloat32_t op, svfloat32_t min, svfloat32_t max);
```

### Description

Floating-point clamp to minimum/maximum number

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector manipulation / Clamp elements

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
  "return_base_type": "float32",
  "element_bit_size": "32",
  "value": "svfloat32_t"
}
```

### Argument preparation and constraints

```json
{
  "op": {
    "register": "Zreg1.S"
  },
  "min": {
    "register": "Zreg2.S"
  },
  "max": {
    "register": "Zreg3.S"
  }
}
```

### Result mapping

```json
[
  {
    "Zreg1.S": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
FCLAMP Zreg1.S, Zreg2.S, Zreg3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCLAMP--Floating-point-clamp-to-minimum-maximum-number-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svclamp[_f64]

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svclamp%5B_f64%5D

### Signature (source notation)

```c
svfloat64_t svclamp[_f64](svfloat64_t op, svfloat64_t min, svfloat64_t max);
```

### Description

Floating-point clamp to minimum/maximum number

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector manipulation / Clamp elements

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
  "return_base_type": "float64",
  "element_bit_size": "64",
  "value": "svfloat64_t"
}
```

### Argument preparation and constraints

```json
{
  "op": {
    "register": "Zreg1.D"
  },
  "min": {
    "register": "Zreg2.D"
  },
  "max": {
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
FCLAMP Zreg1.D, Zreg2.D, Zreg3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCLAMP--Floating-point-clamp-to-minimum-maximum-number-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svclamp[_single_bf16_x2]

ISA classification: SME2 + FEAT_SVE_B16B16

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svclamp%5B_single_bf16_x2%5D

### Signature (source notation)

```c
svbfloat16x2_t svclamp[_single_bf16_x2](svbfloat16x2_t zd, svbfloat16_t zn, svbfloat16_t zm)
    __arm_streaming;
```

### Description

Multi-vector BFloat16 clamp to minimum/maximum number

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Vector manipulation / Clamp elements

- SME attributes: `__arm_streaming`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2,FEAT_SVE_B16B16
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
  "zd": {
    "Z multi-vector": "{ Zreg1.H, Zreg2.H }"
  },
  "zn": {
    "register": "Zreg3.H"
  },
  "zm": {
    "register": "Zreg4.H"
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
BFCLAMP { Zreg1.H, Zreg2.H }, Zreg3.H, Zreg4.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/BFCLAMP--Multi-vector-BFloat16-clamp-to-minimum-maximum-number-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svclamp[_single_bf16_x4]

ISA classification: SME2 + FEAT_SVE_B16B16

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svclamp%5B_single_bf16_x4%5D

### Signature (source notation)

```c
svbfloat16x4_t svclamp[_single_bf16_x4](svbfloat16x4_t zd, svbfloat16_t zn, svbfloat16_t zm)
    __arm_streaming;
```

### Description

Multi-vector BFloat16 clamp to minimum/maximum number

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Vector manipulation / Clamp elements

- SME attributes: `__arm_streaming`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2,FEAT_SVE_B16B16
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
  "zd": {
    "Z multi-vector": "{ Zreg1.H - Zreg2.H }"
  },
  "zn": {
    "register": "Zreg3.H"
  },
  "zm": {
    "register": "Zreg4.H"
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
BFCLAMP { Zreg1.H - Zreg2.H }, Zreg3.H, Zreg4.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/BFCLAMP--Multi-vector-BFloat16-clamp-to-minimum-maximum-number-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svclamp[_single_f16_x2]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svclamp%5B_single_f16_x2%5D

### Signature (source notation)

```c
svfloat16x2_t svclamp[_single_f16_x2](svfloat16x2_t zd, svfloat16_t zn, svfloat16_t zm)
    __arm_streaming;
```

### Description

Multi-vector floating-point clamp to minimum/maximum number

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Vector manipulation / Clamp elements

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
  "zd": {
    "Z multi-vector": "{ Zreg1.H, Zreg2.H }"
  },
  "zn": {
    "register": "Zreg3.H"
  },
  "zm": {
    "register": "Zreg4.H"
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
FCLAMP { Zreg1.H, Zreg2.H }, Zreg3.H, Zreg4.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/FCLAMP--Multi-vector-floating-point-clamp-to-minimum-maximum-number-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svclamp[_single_f16_x4]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svclamp%5B_single_f16_x4%5D

### Signature (source notation)

```c
svfloat16x4_t svclamp[_single_f16_x4](svfloat16x4_t zd, svfloat16_t zn, svfloat16_t zm)
    __arm_streaming;
```

### Description

Multi-vector floating-point clamp to minimum/maximum number

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Vector manipulation / Clamp elements

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
  "zd": {
    "Z multi-vector": "{ Zreg1.H - Zreg2.H }"
  },
  "zn": {
    "register": "Zreg3.H"
  },
  "zm": {
    "register": "Zreg4.H"
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
FCLAMP { Zreg1.H - Zreg2.H }, Zreg3.H, Zreg4.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/FCLAMP--Multi-vector-floating-point-clamp-to-minimum-maximum-number-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svclamp[_single_f32_x2]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svclamp%5B_single_f32_x2%5D

### Signature (source notation)

```c
svfloat32x2_t svclamp[_single_f32_x2](svfloat32x2_t zd, svfloat32_t zn, svfloat32_t zm)
    __arm_streaming;
```

### Description

Multi-vector floating-point clamp to minimum/maximum number

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Vector manipulation / Clamp elements

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
  "zd": {
    "Z multi-vector": "{ Zreg1.S, Zreg2.S }"
  },
  "zn": {
    "register": "Zreg3.S"
  },
  "zm": {
    "register": "Zreg4.S"
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
FCLAMP { Zreg1.S, Zreg2.S }, Zreg3.S, Zreg4.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/FCLAMP--Multi-vector-floating-point-clamp-to-minimum-maximum-number-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svclamp[_single_f32_x4]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svclamp%5B_single_f32_x4%5D

### Signature (source notation)

```c
svfloat32x4_t svclamp[_single_f32_x4](svfloat32x4_t zd, svfloat32_t zn, svfloat32_t zm)
    __arm_streaming;
```

### Description

Multi-vector floating-point clamp to minimum/maximum number

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Vector manipulation / Clamp elements

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
  "zd": {
    "Z multi-vector": "{ Zreg1.S - Zreg2.S }"
  },
  "zn": {
    "register": "Zreg3.S"
  },
  "zm": {
    "register": "Zreg4.S"
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
FCLAMP { Zreg1.S - Zreg2.S }, Zreg3.S, Zreg4.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/FCLAMP--Multi-vector-floating-point-clamp-to-minimum-maximum-number-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svclamp[_single_f64_x2]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svclamp%5B_single_f64_x2%5D

### Signature (source notation)

```c
svfloat64x2_t svclamp[_single_f64_x2](svfloat64x2_t zd, svfloat64_t zn, svfloat64_t zm)
    __arm_streaming;
```

### Description

Multi-vector floating-point clamp to minimum/maximum number

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Vector manipulation / Clamp elements

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
  "zd": {
    "Z multi-vector": "{ Zreg1.D, Zreg2.D }"
  },
  "zn": {
    "register": "Zreg3.D"
  },
  "zm": {
    "register": "Zreg4.D"
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
FCLAMP { Zreg1.D, Zreg2.D }, Zreg3.D, Zreg4.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/FCLAMP--Multi-vector-floating-point-clamp-to-minimum-maximum-number-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svclamp[_single_f64_x4]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svclamp%5B_single_f64_x4%5D

### Signature (source notation)

```c
svfloat64x4_t svclamp[_single_f64_x4](svfloat64x4_t zd, svfloat64_t zn, svfloat64_t zm)
    __arm_streaming;
```

### Description

Multi-vector floating-point clamp to minimum/maximum number

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Vector manipulation / Clamp elements

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
  "zd": {
    "Z multi-vector": "{ Zreg1.D - Zreg2.D }"
  },
  "zn": {
    "register": "Zreg3.D"
  },
  "zm": {
    "register": "Zreg4.D"
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
FCLAMP { Zreg1.D - Zreg2.D }, Zreg3.D, Zreg4.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/FCLAMP--Multi-vector-floating-point-clamp-to-minimum-maximum-number-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svclamp[_single_s16_x2]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svclamp%5B_single_s16_x2%5D

### Signature (source notation)

```c
svint16x2_t svclamp[_single_s16_x2](svint16x2_t zd, svint16_t zn, svint16_t zm)
    __arm_streaming;
```

### Description

Multi-vector signed clamp to minimum/maximum

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Vector manipulation / Clamp elements

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
  "zd": {
    "Z multi-vector": "{ Zreg1.H, Zreg2.H }"
  },
  "zn": {
    "register": "Zreg3.H"
  },
  "zm": {
    "register": "Zreg4.H"
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
SCLAMP { Zreg1.H, Zreg2.H }, Zreg3.H, Zreg4.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SCLAMP--Multi-vector-signed-clamp-to-minimum-maximum-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svclamp[_single_s16_x4]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svclamp%5B_single_s16_x4%5D

### Signature (source notation)

```c
svint16x4_t svclamp[_single_s16_x4](svint16x4_t zd, svint16_t zn, svint16_t zm)
    __arm_streaming;
```

### Description

Multi-vector signed clamp to minimum/maximum

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Vector manipulation / Clamp elements

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
  "zd": {
    "Z multi-vector": "{ Zreg1.H - Zreg2.H }"
  },
  "zn": {
    "register": "Zreg3.H"
  },
  "zm": {
    "register": "Zreg4.H"
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
SCLAMP { Zreg1.H - Zreg2.H }, Zreg3.H, Zreg4.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SCLAMP--Multi-vector-signed-clamp-to-minimum-maximum-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svclamp[_single_s32_x2]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svclamp%5B_single_s32_x2%5D

### Signature (source notation)

```c
svint32x2_t svclamp[_single_s32_x2](svint32x2_t zd, svint32_t zn, svint32_t zm)
    __arm_streaming;
```

### Description

Multi-vector signed clamp to minimum/maximum

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Vector manipulation / Clamp elements

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
  "zd": {
    "Z multi-vector": "{ Zreg1.S, Zreg2.S }"
  },
  "zn": {
    "register": "Zreg3.S"
  },
  "zm": {
    "register": "Zreg4.S"
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
SCLAMP { Zreg1.S, Zreg2.S }, Zreg3.S, Zreg4.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SCLAMP--Multi-vector-signed-clamp-to-minimum-maximum-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svclamp[_single_s32_x4]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svclamp%5B_single_s32_x4%5D

### Signature (source notation)

```c
svint32x4_t svclamp[_single_s32_x4](svint32x4_t zd, svint32_t zn, svint32_t zm)
    __arm_streaming;
```

### Description

Multi-vector signed clamp to minimum/maximum

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Vector manipulation / Clamp elements

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
  "zd": {
    "Z multi-vector": "{ Zreg1.S - Zreg2.S }"
  },
  "zn": {
    "register": "Zreg3.S"
  },
  "zm": {
    "register": "Zreg4.S"
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
SCLAMP { Zreg1.S - Zreg2.S }, Zreg3.S, Zreg4.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SCLAMP--Multi-vector-signed-clamp-to-minimum-maximum-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svclamp[_single_s64_x2]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svclamp%5B_single_s64_x2%5D

### Signature (source notation)

```c
svint64x2_t svclamp[_single_s64_x2](svint64x2_t zd, svint64_t zn, svint64_t zm)
    __arm_streaming;
```

### Description

Multi-vector signed clamp to minimum/maximum

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Vector manipulation / Clamp elements

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
  "zd": {
    "Z multi-vector": "{ Zreg1.D, Zreg2.D }"
  },
  "zn": {
    "register": "Zreg3.D"
  },
  "zm": {
    "register": "Zreg4.D"
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
SCLAMP { Zreg1.D, Zreg2.D }, Zreg3.D, Zreg4.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SCLAMP--Multi-vector-signed-clamp-to-minimum-maximum-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svclamp[_single_s64_x4]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svclamp%5B_single_s64_x4%5D

### Signature (source notation)

```c
svint64x4_t svclamp[_single_s64_x4](svint64x4_t zd, svint64_t zn, svint64_t zm)
    __arm_streaming;
```

### Description

Multi-vector signed clamp to minimum/maximum

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Vector manipulation / Clamp elements

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
  "zd": {
    "Z multi-vector": "{ Zreg1.D - Zreg2.D }"
  },
  "zn": {
    "register": "Zreg3.D"
  },
  "zm": {
    "register": "Zreg4.D"
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
SCLAMP { Zreg1.D - Zreg2.D }, Zreg3.D, Zreg4.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SCLAMP--Multi-vector-signed-clamp-to-minimum-maximum-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svclamp[_single_s8_x2]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svclamp%5B_single_s8_x2%5D

### Signature (source notation)

```c
svint8x2_t svclamp[_single_s8_x2](svint8x2_t zd, svint8_t zn, svint8_t zm)
    __arm_streaming;
```

### Description

Multi-vector signed clamp to minimum/maximum

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Vector manipulation / Clamp elements

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
  "zd": {
    "Z multi-vector": "{ Zreg1.B, Zreg2.B }"
  },
  "zn": {
    "register": "Zreg3.B"
  },
  "zm": {
    "register": "Zreg4.B"
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
SCLAMP { Zreg1.B, Zreg2.B }, Zreg3.B, Zreg4.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SCLAMP--Multi-vector-signed-clamp-to-minimum-maximum-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svclamp[_single_s8_x4]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svclamp%5B_single_s8_x4%5D

### Signature (source notation)

```c
svint8x4_t svclamp[_single_s8_x4](svint8x4_t zd, svint8_t zn, svint8_t zm)
    __arm_streaming;
```

### Description

Multi-vector signed clamp to minimum/maximum

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Vector manipulation / Clamp elements

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
  "zd": {
    "Z multi-vector": "{ Zreg1.B - Zreg2.B }"
  },
  "zn": {
    "register": "Zreg3.B"
  },
  "zm": {
    "register": "Zreg4.B"
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
SCLAMP { Zreg1.B - Zreg2.B }, Zreg3.B, Zreg4.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SCLAMP--Multi-vector-signed-clamp-to-minimum-maximum-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svclamp[_single_u16_x2]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svclamp%5B_single_u16_x2%5D

### Signature (source notation)

```c
svuint16x2_t svclamp[_single_u16_x2](svuint16x2_t zd, svuint16_t zn, svuint16_t zm)
    __arm_streaming;
```

### Description

Multi-vector unsigned clamp to minimum/maximum

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Vector manipulation / Clamp elements

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
  "zd": {
    "Z multi-vector": "{ Zreg1.H, Zreg2.H }"
  },
  "zn": {
    "register": "Zreg3.H"
  },
  "zm": {
    "register": "Zreg4.H"
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
UCLAMP { Zreg1.H, Zreg2.H }, Zreg3.H, Zreg4.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/UCLAMP--Multi-vector-unsigned-clamp-to-minimum-maximum-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svclamp[_single_u16_x4]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svclamp%5B_single_u16_x4%5D

### Signature (source notation)

```c
svuint16x4_t svclamp[_single_u16_x4](svuint16x4_t zd, svuint16_t zn, svuint16_t zm)
    __arm_streaming;
```

### Description

Multi-vector unsigned clamp to minimum/maximum

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Vector manipulation / Clamp elements

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
  "zd": {
    "Z multi-vector": "{ Zreg1.H - Zreg2.H }"
  },
  "zn": {
    "register": "Zreg3.H"
  },
  "zm": {
    "register": "Zreg4.H"
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
UCLAMP { Zreg1.H - Zreg2.H }, Zreg3.H, Zreg4.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/UCLAMP--Multi-vector-unsigned-clamp-to-minimum-maximum-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svclamp[_single_u32_x2]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svclamp%5B_single_u32_x2%5D

### Signature (source notation)

```c
svuint32x2_t svclamp[_single_u32_x2](svuint32x2_t zd, svuint32_t zn, svuint32_t zm)
    __arm_streaming;
```

### Description

Multi-vector unsigned clamp to minimum/maximum

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Vector manipulation / Clamp elements

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
  "zd": {
    "Z multi-vector": "{ Zreg1.S, Zreg2.S }"
  },
  "zn": {
    "register": "Zreg3.S"
  },
  "zm": {
    "register": "Zreg4.S"
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
UCLAMP { Zreg1.S, Zreg2.S }, Zreg3.S, Zreg4.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/UCLAMP--Multi-vector-unsigned-clamp-to-minimum-maximum-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svclamp[_single_u32_x4]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svclamp%5B_single_u32_x4%5D

### Signature (source notation)

```c
svuint32x4_t svclamp[_single_u32_x4](svuint32x4_t zd, svuint32_t zn, svuint32_t zm)
    __arm_streaming;
```

### Description

Multi-vector unsigned clamp to minimum/maximum

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Vector manipulation / Clamp elements

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
  "zd": {
    "Z multi-vector": "{ Zreg1.S - Zreg2.S }"
  },
  "zn": {
    "register": "Zreg3.S"
  },
  "zm": {
    "register": "Zreg4.S"
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
UCLAMP { Zreg1.S - Zreg2.S }, Zreg3.S, Zreg4.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/UCLAMP--Multi-vector-unsigned-clamp-to-minimum-maximum-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svclamp[_single_u64_x2]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svclamp%5B_single_u64_x2%5D

### Signature (source notation)

```c
svuint64x2_t svclamp[_single_u64_x2](svuint64x2_t zd, svuint64_t zn, svuint64_t zm)
    __arm_streaming;
```

### Description

Multi-vector unsigned clamp to minimum/maximum

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Vector manipulation / Clamp elements

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
  "zd": {
    "Z multi-vector": "{ Zreg1.D, Zreg2.D }"
  },
  "zn": {
    "register": "Zreg3.D"
  },
  "zm": {
    "register": "Zreg4.D"
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
UCLAMP { Zreg1.D, Zreg2.D }, Zreg3.D, Zreg4.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/UCLAMP--Multi-vector-unsigned-clamp-to-minimum-maximum-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svclamp[_single_u64_x4]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svclamp%5B_single_u64_x4%5D

### Signature (source notation)

```c
svuint64x4_t svclamp[_single_u64_x4](svuint64x4_t zd, svuint64_t zn, svuint64_t zm)
    __arm_streaming;
```

### Description

Multi-vector unsigned clamp to minimum/maximum

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Vector manipulation / Clamp elements

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
  "zd": {
    "Z multi-vector": "{ Zreg1.D - Zreg2.D }"
  },
  "zn": {
    "register": "Zreg3.D"
  },
  "zm": {
    "register": "Zreg4.D"
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
UCLAMP { Zreg1.D - Zreg2.D }, Zreg3.D, Zreg4.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/UCLAMP--Multi-vector-unsigned-clamp-to-minimum-maximum-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svclamp[_single_u8_x2]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svclamp%5B_single_u8_x2%5D

### Signature (source notation)

```c
svuint8x2_t svclamp[_single_u8_x2](svuint8x2_t zd, svuint8_t zn, svuint8_t zm)
    __arm_streaming;
```

### Description

Multi-vector unsigned clamp to minimum/maximum

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Vector manipulation / Clamp elements

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
  "zd": {
    "Z multi-vector": "{ Zreg1.B, Zreg2.B }"
  },
  "zn": {
    "register": "Zreg3.B"
  },
  "zm": {
    "register": "Zreg4.B"
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
UCLAMP { Zreg1.B, Zreg2.B }, Zreg3.B, Zreg4.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/UCLAMP--Multi-vector-unsigned-clamp-to-minimum-maximum-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svclamp[_single_u8_x4]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svclamp%5B_single_u8_x4%5D

### Signature (source notation)

```c
svuint8x4_t svclamp[_single_u8_x4](svuint8x4_t zd, svuint8_t zn, svuint8_t zm)
    __arm_streaming;
```

### Description

Multi-vector unsigned clamp to minimum/maximum

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Vector manipulation / Clamp elements

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
  "zd": {
    "Z multi-vector": "{ Zreg1.B - Zreg2.B }"
  },
  "zn": {
    "register": "Zreg3.B"
  },
  "zm": {
    "register": "Zreg4.B"
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
UCLAMP { Zreg1.B - Zreg2.B }, Zreg3.B, Zreg4.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/UCLAMP--Multi-vector-unsigned-clamp-to-minimum-maximum-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

