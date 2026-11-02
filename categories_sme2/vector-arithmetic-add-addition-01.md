# SME2 / Vector arithmetic / Add / Addition — Part 1

## svadd[_bf16]_m

ISA classification: SME2 + FEAT_SVE_B16B16

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svadd%5B_bf16%5D_m

### Signature (source notation)

```c
svbfloat16_t svadd[_bf16]_m(svbool_t pg, svbfloat16_t zdn, svbfloat16_t zm);
```

### Description

BFloat16 add (predicated)

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Addition

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
  "pg": {
    "register": "Preg1"
  },
  "zdn": {
    "register": "Zreg1.H"
  },
  "zm": {
    "register": "Zreg2.H"
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
BFADD Zreg1.H, Preg1/M, Zreg1.H, Zreg2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/BFADD--predicated---BFloat16-add--predicated--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svadd[_bf16]_x

ISA classification: SME2 + FEAT_SVE_B16B16

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svadd%5B_bf16%5D_x

### Signature (source notation)

```c
svbfloat16_t svadd[_bf16]_x(svbool_t pg, svbfloat16_t zdn, svbfloat16_t zm);
```

### Description

BFloat16 add (predicated)

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Addition

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
  "pg": {
    "register": "Preg1"
  },
  "zdn": {
    "register": "Zreg1.H"
  },
  "zm": {
    "register": "Zreg2.H"
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
BFADD Zreg1.H, Preg1/M, Zreg1.H, Zreg2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/BFADD--predicated---BFloat16-add--predicated--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svadd[_bf16]_z

ISA classification: SME2 + FEAT_SVE_B16B16

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svadd%5B_bf16%5D_z

### Signature (source notation)

```c
svbfloat16_t svadd[_bf16]_z(svbool_t pg, svbfloat16_t zdn, svbfloat16_t zm);
```

### Description

BFloat16 add (predicated)

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Addition

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
  "pg": {
    "register": "Preg1"
  },
  "zdn": {
    "register": "Zreg1.H"
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
    "Zreg1.H": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
MOVI Vreg2.2D, #0000000000000000
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SIMD-FP-Instructions/MOVI--Move-immediate--vector--

```asm
SEL Zreg1.H, Preg1, Zreg1.H, Zreg2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/SEL--vectors---Conditionally-select-elements-from-two-vectors-

```asm
BFADD Zreg1.H, Preg1/M, Zreg1.H, Zreg3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/BFADD--predicated---BFloat16-add--predicated--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svadd[_n_bf16]_m

ISA classification: SME2 + FEAT_SVE_B16B16

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svadd%5B_n_bf16%5D_m

### Signature (source notation)

```c
svbfloat16_t svadd[_n_bf16]_m(svbool_t pg, svbfloat16_t zdn, bfloat16_t zm);
```

### Description

BFloat16 add (predicated)

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Addition

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
  "pg": {
    "register": "Preg1"
  },
  "zdn": {
    "register": "Zreg2.H"
  },
  "zm": {
    "register": "Hreg1"
  }
}
```

### Result mapping

```json
[
  {
    "Zreg2.H": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
MOV Zreg1.H, Hreg1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/MOV--SIMD-FP-scalar--unpredicated---Move-indexed-element-or-SIMD-FP-scalar-to-vector--unpredicated---an-alias-of-DUP--indexed--

```asm
BFADD Zreg2.H, Preg1/M, Zreg2.H, Zreg1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/BFADD--predicated---BFloat16-add--predicated--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svadd[_n_bf16]_x

ISA classification: SME2 + FEAT_SVE_B16B16

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svadd%5B_n_bf16%5D_x

### Signature (source notation)

```c
svbfloat16_t svadd[_n_bf16]_x(svbool_t pg, svbfloat16_t zdn, bfloat16_t zm);
```

### Description

BFloat16 add (predicated)

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Addition

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
  "pg": {
    "register": "Preg1"
  },
  "zdn": {
    "register": "Zreg2.H"
  },
  "zm": {
    "register": "Hreg1"
  }
}
```

### Result mapping

```json
[
  {
    "Zreg2.H": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
MOV Zreg1.H, Hreg1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/MOV--SIMD-FP-scalar--unpredicated---Move-indexed-element-or-SIMD-FP-scalar-to-vector--unpredicated---an-alias-of-DUP--indexed--

```asm
BFADD Zreg2.H, Preg1/M, Zreg2.H, Zreg1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/BFADD--predicated---BFloat16-add--predicated--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svadd[_n_bf16]_z

ISA classification: SME2 + FEAT_SVE_B16B16

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svadd%5B_n_bf16%5D_z

### Signature (source notation)

```c
svbfloat16_t svadd[_n_bf16]_z(svbool_t pg, svbfloat16_t zdn, bfloat16_t zm);
```

### Description

BFloat16 add (predicated)

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Addition

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
  "pg": {
    "register": "Preg1"
  },
  "zdn": {
    "register": "Zreg2.H"
  },
  "zm": {
    "register": "Hreg1"
  }
}
```

### Result mapping

```json
[
  {
    "Zreg2.H": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
MOVI Vreg3.2D, #0000000000000000
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SIMD-FP-Instructions/MOVI--Move-immediate--vector--

```asm
MOV Zreg1.H, Hreg1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/MOV--SIMD-FP-scalar--unpredicated---Move-indexed-element-or-SIMD-FP-scalar-to-vector--unpredicated---an-alias-of-DUP--indexed--

```asm
SEL Zreg2.H, Preg1, Zreg2.H, Zreg3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/SEL--vectors---Conditionally-select-elements-from-two-vectors-

```asm
BFADD Zreg2.H, Preg1/M, Zreg2.H, Zreg1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/BFADD--predicated---BFloat16-add--predicated--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svadd[_single_s16_x2]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svadd%5B_single_s16_x2%5D

### Signature (source notation)

```c
svint16x2_t svadd[_single_s16_x2](svint16x2_t zdn, svint16_t zm)
    __arm_streaming;
```

### Description

Add replicated single vector to multi-vector with multi-vector result

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Addition

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
ADD { Zreg1.H, Zreg2.H }, { Zreg1.H, Zreg2.H }, Zreg3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/ADD--to-vector---Add-replicated-single-vector-to-multi-vector-with-multi-vector-result-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svadd[_single_s16_x4]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svadd%5B_single_s16_x4%5D

### Signature (source notation)

```c
svint16x4_t svadd[_single_s16_x4](svint16x4_t zdn, svint16_t zm)
    __arm_streaming;
```

### Description

Add replicated single vector to multi-vector with multi-vector result

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Addition

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
ADD { Zreg1.H - Zreg2.H }, { Zreg1.H - Zreg2.H }, Zreg3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/ADD--to-vector---Add-replicated-single-vector-to-multi-vector-with-multi-vector-result-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svadd[_single_s32_x2]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svadd%5B_single_s32_x2%5D

### Signature (source notation)

```c
svint32x2_t svadd[_single_s32_x2](svint32x2_t zdn, svint32_t zm)
    __arm_streaming;
```

### Description

Add replicated single vector to multi-vector with multi-vector result

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Addition

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
ADD { Zreg1.S, Zreg2.S }, { Zreg1.S, Zreg2.S }, Zreg3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/ADD--to-vector---Add-replicated-single-vector-to-multi-vector-with-multi-vector-result-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svadd[_single_s32_x4]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svadd%5B_single_s32_x4%5D

### Signature (source notation)

```c
svint32x4_t svadd[_single_s32_x4](svint32x4_t zdn, svint32_t zm)
    __arm_streaming;
```

### Description

Add replicated single vector to multi-vector with multi-vector result

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Addition

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
ADD { Zreg1.S - Zreg2.S }, { Zreg1.S - Zreg2.S }, Zreg3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/ADD--to-vector---Add-replicated-single-vector-to-multi-vector-with-multi-vector-result-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svadd[_single_s64_x2]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svadd%5B_single_s64_x2%5D

### Signature (source notation)

```c
svint64x2_t svadd[_single_s64_x2](svint64x2_t zdn, svint64_t zm)
    __arm_streaming;
```

### Description

Add replicated single vector to multi-vector with multi-vector result

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Addition

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
ADD { Zreg1.D, Zreg2.D }, { Zreg1.D, Zreg2.D }, Zreg3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/ADD--to-vector---Add-replicated-single-vector-to-multi-vector-with-multi-vector-result-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svadd[_single_s64_x4]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svadd%5B_single_s64_x4%5D

### Signature (source notation)

```c
svint64x4_t svadd[_single_s64_x4](svint64x4_t zdn, svint64_t zm)
    __arm_streaming;
```

### Description

Add replicated single vector to multi-vector with multi-vector result

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Addition

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
ADD { Zreg1.D - Zreg2.D }, { Zreg1.D - Zreg2.D }, Zreg3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/ADD--to-vector---Add-replicated-single-vector-to-multi-vector-with-multi-vector-result-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svadd[_single_s8_x2]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svadd%5B_single_s8_x2%5D

### Signature (source notation)

```c
svint8x2_t svadd[_single_s8_x2](svint8x2_t zdn, svint8_t zm)
    __arm_streaming;
```

### Description

Add replicated single vector to multi-vector with multi-vector result

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Addition

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
ADD { Zreg1.B, Zreg2.B }, { Zreg1.B, Zreg2.B }, Zreg3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/ADD--to-vector---Add-replicated-single-vector-to-multi-vector-with-multi-vector-result-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svadd[_single_s8_x4]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svadd%5B_single_s8_x4%5D

### Signature (source notation)

```c
svint8x4_t svadd[_single_s8_x4](svint8x4_t zdn, svint8_t zm)
    __arm_streaming;
```

### Description

Add replicated single vector to multi-vector with multi-vector result

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Addition

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
ADD { Zreg1.B - Zreg2.B }, { Zreg1.B - Zreg2.B }, Zreg3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/ADD--to-vector---Add-replicated-single-vector-to-multi-vector-with-multi-vector-result-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svadd[_single_u16_x2]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svadd%5B_single_u16_x2%5D

### Signature (source notation)

```c
svuint16x2_t svadd[_single_u16_x2](svuint16x2_t zdn, svuint16_t zm)
    __arm_streaming;
```

### Description

Add replicated single vector to multi-vector with multi-vector result

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Addition

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
ADD { Zreg1.H, Zreg2.H }, { Zreg1.H, Zreg2.H }, Zreg3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/ADD--to-vector---Add-replicated-single-vector-to-multi-vector-with-multi-vector-result-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svadd[_single_u16_x4]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svadd%5B_single_u16_x4%5D

### Signature (source notation)

```c
svuint16x4_t svadd[_single_u16_x4](svuint16x4_t zdn, svuint16_t zm)
    __arm_streaming;
```

### Description

Add replicated single vector to multi-vector with multi-vector result

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Addition

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
ADD { Zreg1.H - Zreg2.H }, { Zreg1.H - Zreg2.H }, Zreg3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/ADD--to-vector---Add-replicated-single-vector-to-multi-vector-with-multi-vector-result-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svadd[_single_u32_x2]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svadd%5B_single_u32_x2%5D

### Signature (source notation)

```c
svuint32x2_t svadd[_single_u32_x2](svuint32x2_t zdn, svuint32_t zm)
    __arm_streaming;
```

### Description

Add replicated single vector to multi-vector with multi-vector result

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Addition

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
ADD { Zreg1.S, Zreg2.S }, { Zreg1.S, Zreg2.S }, Zreg3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/ADD--to-vector---Add-replicated-single-vector-to-multi-vector-with-multi-vector-result-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svadd[_single_u32_x4]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svadd%5B_single_u32_x4%5D

### Signature (source notation)

```c
svuint32x4_t svadd[_single_u32_x4](svuint32x4_t zdn, svuint32_t zm)
    __arm_streaming;
```

### Description

Add replicated single vector to multi-vector with multi-vector result

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Addition

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
ADD { Zreg1.S - Zreg2.S }, { Zreg1.S - Zreg2.S }, Zreg3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/ADD--to-vector---Add-replicated-single-vector-to-multi-vector-with-multi-vector-result-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svadd[_single_u64_x2]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svadd%5B_single_u64_x2%5D

### Signature (source notation)

```c
svuint64x2_t svadd[_single_u64_x2](svuint64x2_t zdn, svuint64_t zm)
    __arm_streaming;
```

### Description

Add replicated single vector to multi-vector with multi-vector result

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Addition

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
ADD { Zreg1.D, Zreg2.D }, { Zreg1.D, Zreg2.D }, Zreg3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/ADD--to-vector---Add-replicated-single-vector-to-multi-vector-with-multi-vector-result-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svadd[_single_u64_x4]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svadd%5B_single_u64_x4%5D

### Signature (source notation)

```c
svuint64x4_t svadd[_single_u64_x4](svuint64x4_t zdn, svuint64_t zm)
    __arm_streaming;
```

### Description

Add replicated single vector to multi-vector with multi-vector result

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Addition

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
ADD { Zreg1.D - Zreg2.D }, { Zreg1.D - Zreg2.D }, Zreg3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/ADD--to-vector---Add-replicated-single-vector-to-multi-vector-with-multi-vector-result-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svadd[_single_u8_x2]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svadd%5B_single_u8_x2%5D

### Signature (source notation)

```c
svuint8x2_t svadd[_single_u8_x2](svuint8x2_t zdn, svuint8_t zm)
    __arm_streaming;
```

### Description

Add replicated single vector to multi-vector with multi-vector result

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Addition

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
ADD { Zreg1.B, Zreg2.B }, { Zreg1.B, Zreg2.B }, Zreg3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/ADD--to-vector---Add-replicated-single-vector-to-multi-vector-with-multi-vector-result-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svadd[_single_u8_x4]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svadd%5B_single_u8_x4%5D

### Signature (source notation)

```c
svuint8x4_t svadd[_single_u8_x4](svuint8x4_t zdn, svuint8_t zm)
    __arm_streaming;
```

### Description

Add replicated single vector to multi-vector with multi-vector result

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Addition

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
ADD { Zreg1.B - Zreg2.B }, { Zreg1.B - Zreg2.B }, Zreg3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/ADD--to-vector---Add-replicated-single-vector-to-multi-vector-with-multi-vector-result-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

