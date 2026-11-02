# SME / Vector arithmetic / Rounding — Part 1

## svrint32x[_f32]_m

ISA classification: SME + FEAT_SVE2p2 OR SME2.2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrint32x%5B_f32%5D_m

### Signature (source notation)

```c
svfloat32_t svrint32x[_f32]_m(svfloat32_t inactive, svbool_t pg, svfloat32_t zn);
```

### Description

Floating-point round to 32-bit integer (predicated)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Rounding

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p2)|FEAT_SME2p2
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
  "inactive": {
    "register": "Zreg1.S"
  },
  "pg": {
    "register": "Preg1"
  },
  "zn": {
    "register": "Zreg2.S"
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
FRINT32X Zreg1.S, Preg1/M, Zreg2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/FRINT32X--Floating-point-round-to-32-bit-integer--predicated--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svrint32x[_f32]_x

ISA classification: SME + FEAT_SVE2p2 OR SME2.2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrint32x%5B_f32%5D_x

### Signature (source notation)

```c
svfloat32_t svrint32x[_f32]_x(svbool_t pg, svfloat32_t zn);
```

### Description

Floating-point round to 32-bit integer (predicated)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Rounding

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p2)|FEAT_SME2p2
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
  "pg": {
    "register": "Preg1"
  },
  "zn": {
    "register": "Zreg2.S"
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
FRINT32X Zreg1.S, Preg1/Z, Zreg2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/FRINT32X--Floating-point-round-to-32-bit-integer--predicated--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svrint32x[_f32]_z

ISA classification: SME + FEAT_SVE2p2 OR SME2.2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrint32x%5B_f32%5D_z

### Signature (source notation)

```c
svfloat32_t svrint32x[_f32]_z(svbool_t pg, svfloat32_t zn);
```

### Description

Floating-point round to 32-bit integer (predicated)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Rounding

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p2)|FEAT_SME2p2
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
  "pg": {
    "register": "Preg1"
  },
  "zn": {
    "register": "Zreg2.S"
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
FRINT32X Zreg1.S, Preg1/Z, Zreg2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/FRINT32X--Floating-point-round-to-32-bit-integer--predicated--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svrint32x[_f64]_m

ISA classification: SME + FEAT_SVE2p2 OR SME2.2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrint32x%5B_f64%5D_m

### Signature (source notation)

```c
svfloat64_t svrint32x[_f64]_m(svfloat64_t inactive, svbool_t pg, svfloat64_t zn);
```

### Description

Floating-point round to 32-bit integer (predicated)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Rounding

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p2)|FEAT_SME2p2
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
  "inactive": {
    "register": "Zreg1.D"
  },
  "pg": {
    "register": "Preg1"
  },
  "zn": {
    "register": "Zreg2.D"
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
FRINT32X Zreg1.D, Preg1/M, Zreg2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/FRINT32X--Floating-point-round-to-32-bit-integer--predicated--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svrint32x[_f64]_x

ISA classification: SME + FEAT_SVE2p2 OR SME2.2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrint32x%5B_f64%5D_x

### Signature (source notation)

```c
svfloat64_t svrint32x[_f64]_x(svbool_t pg, svfloat64_t zn);
```

### Description

Floating-point round to 32-bit integer (predicated)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Rounding

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p2)|FEAT_SME2p2
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
  "pg": {
    "register": "Preg1"
  },
  "zn": {
    "register": "Zreg2.D"
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
FRINT32X Zreg1.D, Preg1/Z, Zreg2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/FRINT32X--Floating-point-round-to-32-bit-integer--predicated--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svrint32x[_f64]_z

ISA classification: SME + FEAT_SVE2p2 OR SME2.2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrint32x%5B_f64%5D_z

### Signature (source notation)

```c
svfloat64_t svrint32x[_f64]_z(svbool_t pg, svfloat64_t zn);
```

### Description

Floating-point round to 32-bit integer (predicated)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Rounding

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p2)|FEAT_SME2p2
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
  "pg": {
    "register": "Preg1"
  },
  "zn": {
    "register": "Zreg2.D"
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
FRINT32X Zreg1.D, Preg1/Z, Zreg2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/FRINT32X--Floating-point-round-to-32-bit-integer--predicated--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svrint32z[_f32]_m

ISA classification: SME + FEAT_SVE2p2 OR SME2.2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrint32z%5B_f32%5D_m

### Signature (source notation)

```c
svfloat32_t svrint32z[_f32]_m(svfloat32_t inactive, svbool_t pg, svfloat32_t zn);
```

### Description

Floating-point round to 32-bit integer, rounding toward zero (predicated)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Rounding

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p2)|FEAT_SME2p2
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
  "inactive": {
    "register": "Zreg1.S"
  },
  "pg": {
    "register": "Preg1"
  },
  "zn": {
    "register": "Zreg2.S"
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
FRINT32Z Zreg1.S, Preg1/M, Zreg2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/FRINT32Z--Floating-point-round-to-32-bit-integer--rounding-toward-zero--predicated--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svrint32z[_f32]_x

ISA classification: SME + FEAT_SVE2p2 OR SME2.2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrint32z%5B_f32%5D_x

### Signature (source notation)

```c
svfloat32_t svrint32z[_f32]_x(svbool_t pg, svfloat32_t zn);
```

### Description

Floating-point round to 32-bit integer, rounding toward zero (predicated)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Rounding

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p2)|FEAT_SME2p2
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
  "pg": {
    "register": "Preg1"
  },
  "zn": {
    "register": "Zreg2.S"
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
FRINT32Z Zreg1.S, Preg1/Z, Zreg2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/FRINT32Z--Floating-point-round-to-32-bit-integer--rounding-toward-zero--predicated--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svrint32z[_f32]_z

ISA classification: SME + FEAT_SVE2p2 OR SME2.2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrint32z%5B_f32%5D_z

### Signature (source notation)

```c
svfloat32_t svrint32z[_f32]_z(svbool_t pg, svfloat32_t zn);
```

### Description

Floating-point round to 32-bit integer, rounding toward zero (predicated)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Rounding

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p2)|FEAT_SME2p2
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
  "pg": {
    "register": "Preg1"
  },
  "zn": {
    "register": "Zreg2.S"
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
FRINT32Z Zreg1.S, Preg1/Z, Zreg2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/FRINT32Z--Floating-point-round-to-32-bit-integer--rounding-toward-zero--predicated--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svrint32z[_f64]_m

ISA classification: SME + FEAT_SVE2p2 OR SME2.2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrint32z%5B_f64%5D_m

### Signature (source notation)

```c
svfloat64_t svrint32z[_f64]_m(svfloat64_t inactive, svbool_t pg, svfloat64_t zn);
```

### Description

Floating-point round to 32-bit integer, rounding toward zero (predicated)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Rounding

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p2)|FEAT_SME2p2
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
  "inactive": {
    "register": "Zreg1.D"
  },
  "pg": {
    "register": "Preg1"
  },
  "zn": {
    "register": "Zreg2.D"
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
FRINT32Z Zreg1.D, Preg1/M, Zreg2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/FRINT32Z--Floating-point-round-to-32-bit-integer--rounding-toward-zero--predicated--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svrint32z[_f64]_x

ISA classification: SME + FEAT_SVE2p2 OR SME2.2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrint32z%5B_f64%5D_x

### Signature (source notation)

```c
svfloat64_t svrint32z[_f64]_x(svbool_t pg, svfloat64_t zn);
```

### Description

Floating-point round to 32-bit integer, rounding toward zero (predicated)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Rounding

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p2)|FEAT_SME2p2
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
  "pg": {
    "register": "Preg1"
  },
  "zn": {
    "register": "Zreg2.D"
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
FRINT32Z Zreg1.D, Preg1/Z, Zreg2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/FRINT32Z--Floating-point-round-to-32-bit-integer--rounding-toward-zero--predicated--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svrint32z[_f64]_z

ISA classification: SME + FEAT_SVE2p2 OR SME2.2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrint32z%5B_f64%5D_z

### Signature (source notation)

```c
svfloat64_t svrint32z[_f64]_z(svbool_t pg, svfloat64_t zn);
```

### Description

Floating-point round to 32-bit integer, rounding toward zero (predicated)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Rounding

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p2)|FEAT_SME2p2
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
  "pg": {
    "register": "Preg1"
  },
  "zn": {
    "register": "Zreg2.D"
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
FRINT32Z Zreg1.D, Preg1/Z, Zreg2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/FRINT32Z--Floating-point-round-to-32-bit-integer--rounding-toward-zero--predicated--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svrint64x[_f32]_m

ISA classification: SME + FEAT_SVE2p2 OR SME2.2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrint64x%5B_f32%5D_m

### Signature (source notation)

```c
svfloat32_t svrint64x[_f32]_m(svfloat32_t inactive, svbool_t pg, svfloat32_t zn);
```

### Description

Floating-point round to 64-bit integer (predicated)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Rounding

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p2)|FEAT_SME2p2
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
  "inactive": {
    "register": "Zreg1.S"
  },
  "pg": {
    "register": "Preg1"
  },
  "zn": {
    "register": "Zreg2.S"
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
FRINT64X Zreg1.S, Preg1/M, Zreg2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/FRINT64X--Floating-point-round-to-64-bit-integer--predicated--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svrint64x[_f32]_x

ISA classification: SME + FEAT_SVE2p2 OR SME2.2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrint64x%5B_f32%5D_x

### Signature (source notation)

```c
svfloat32_t svrint64x[_f32]_x(svbool_t pg, svfloat32_t zn);
```

### Description

Floating-point round to 64-bit integer (predicated)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Rounding

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p2)|FEAT_SME2p2
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
  "pg": {
    "register": "Preg1"
  },
  "zn": {
    "register": "Zreg2.S"
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
FRINT64X Zreg1.S, Preg1/Z, Zreg2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/FRINT64X--Floating-point-round-to-64-bit-integer--predicated--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svrint64x[_f32]_z

ISA classification: SME + FEAT_SVE2p2 OR SME2.2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrint64x%5B_f32%5D_z

### Signature (source notation)

```c
svfloat32_t svrint64x[_f32]_z(svbool_t pg, svfloat32_t zn);
```

### Description

Floating-point round to 64-bit integer (predicated)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Rounding

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p2)|FEAT_SME2p2
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
  "pg": {
    "register": "Preg1"
  },
  "zn": {
    "register": "Zreg2.S"
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
FRINT64X Zreg1.S, Preg1/Z, Zreg2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/FRINT64X--Floating-point-round-to-64-bit-integer--predicated--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svrint64x[_f64]_m

ISA classification: SME + FEAT_SVE2p2 OR SME2.2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrint64x%5B_f64%5D_m

### Signature (source notation)

```c
svfloat64_t svrint64x[_f64]_m(svfloat64_t inactive, svbool_t pg, svfloat64_t zn);
```

### Description

Floating-point round to 64-bit integer (predicated)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Rounding

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p2)|FEAT_SME2p2
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
  "inactive": {
    "register": "Zreg1.D"
  },
  "pg": {
    "register": "Preg1"
  },
  "zn": {
    "register": "Zreg2.D"
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
FRINT64X Zreg1.D, Preg1/M, Zreg2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/FRINT64X--Floating-point-round-to-64-bit-integer--predicated--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svrint64x[_f64]_x

ISA classification: SME + FEAT_SVE2p2 OR SME2.2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrint64x%5B_f64%5D_x

### Signature (source notation)

```c
svfloat64_t svrint64x[_f64]_x(svbool_t pg, svfloat64_t zn);
```

### Description

Floating-point round to 64-bit integer (predicated)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Rounding

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p2)|FEAT_SME2p2
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
  "pg": {
    "register": "Preg1"
  },
  "zn": {
    "register": "Zreg2.D"
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
FRINT64X Zreg1.D, Preg1/Z, Zreg2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/FRINT64X--Floating-point-round-to-64-bit-integer--predicated--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svrint64x[_f64]_z

ISA classification: SME + FEAT_SVE2p2 OR SME2.2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrint64x%5B_f64%5D_z

### Signature (source notation)

```c
svfloat64_t svrint64x[_f64]_z(svbool_t pg, svfloat64_t zn);
```

### Description

Floating-point round to 64-bit integer (predicated)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Rounding

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p2)|FEAT_SME2p2
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
  "pg": {
    "register": "Preg1"
  },
  "zn": {
    "register": "Zreg2.D"
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
FRINT64X Zreg1.D, Preg1/Z, Zreg2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/FRINT64X--Floating-point-round-to-64-bit-integer--predicated--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svrint64z[_f32]_m

ISA classification: SME + FEAT_SVE2p2 OR SME2.2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrint64z%5B_f32%5D_m

### Signature (source notation)

```c
svfloat32_t svrint64z[_f32]_m(svfloat32_t inactive, svbool_t pg, svfloat32_t zn);
```

### Description

Floating-point round to 64-bit integer, rounding toward zero (predicated)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Rounding

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p2)|FEAT_SME2p2
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
  "inactive": {
    "register": "Zreg1.S"
  },
  "pg": {
    "register": "Preg1"
  },
  "zn": {
    "register": "Zreg2.S"
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
FRINT64Z Zreg1.S, Preg1/M, Zreg2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/FRINT64Z--Floating-point-round-to-64-bit-integer--rounding-toward-zero--predicated--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svrint64z[_f32]_x

ISA classification: SME + FEAT_SVE2p2 OR SME2.2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrint64z%5B_f32%5D_x

### Signature (source notation)

```c
svfloat32_t svrint64z[_f32]_x(svbool_t pg, svfloat32_t zn);
```

### Description

Floating-point round to 64-bit integer, rounding toward zero (predicated)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Rounding

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p2)|FEAT_SME2p2
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
  "pg": {
    "register": "Preg1"
  },
  "zn": {
    "register": "Zreg2.S"
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
FRINT64Z Zreg1.S, Preg1/Z, Zreg2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/FRINT64Z--Floating-point-round-to-64-bit-integer--rounding-toward-zero--predicated--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svrint64z[_f32]_z

ISA classification: SME + FEAT_SVE2p2 OR SME2.2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrint64z%5B_f32%5D_z

### Signature (source notation)

```c
svfloat32_t svrint64z[_f32]_z(svbool_t pg, svfloat32_t zn);
```

### Description

Floating-point round to 64-bit integer, rounding toward zero (predicated)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Rounding

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p2)|FEAT_SME2p2
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
  "pg": {
    "register": "Preg1"
  },
  "zn": {
    "register": "Zreg2.S"
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
FRINT64Z Zreg1.S, Preg1/Z, Zreg2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/FRINT64Z--Floating-point-round-to-64-bit-integer--rounding-toward-zero--predicated--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svrint64z[_f64]_m

ISA classification: SME + FEAT_SVE2p2 OR SME2.2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrint64z%5B_f64%5D_m

### Signature (source notation)

```c
svfloat64_t svrint64z[_f64]_m(svfloat64_t inactive, svbool_t pg, svfloat64_t zn);
```

### Description

Floating-point round to 64-bit integer, rounding toward zero (predicated)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Rounding

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p2)|FEAT_SME2p2
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
  "inactive": {
    "register": "Zreg1.D"
  },
  "pg": {
    "register": "Preg1"
  },
  "zn": {
    "register": "Zreg2.D"
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
FRINT64Z Zreg1.D, Preg1/M, Zreg2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/FRINT64Z--Floating-point-round-to-64-bit-integer--rounding-toward-zero--predicated--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svrint64z[_f64]_x

ISA classification: SME + FEAT_SVE2p2 OR SME2.2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrint64z%5B_f64%5D_x

### Signature (source notation)

```c
svfloat64_t svrint64z[_f64]_x(svbool_t pg, svfloat64_t zn);
```

### Description

Floating-point round to 64-bit integer, rounding toward zero (predicated)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Rounding

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p2)|FEAT_SME2p2
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
  "pg": {
    "register": "Preg1"
  },
  "zn": {
    "register": "Zreg2.D"
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
FRINT64Z Zreg1.D, Preg1/Z, Zreg2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/FRINT64Z--Floating-point-round-to-64-bit-integer--rounding-toward-zero--predicated--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svrint64z[_f64]_z

ISA classification: SME + FEAT_SVE2p2 OR SME2.2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrint64z%5B_f64%5D_z

### Signature (source notation)

```c
svfloat64_t svrint64z[_f64]_z(svbool_t pg, svfloat64_t zn);
```

### Description

Floating-point round to 64-bit integer, rounding toward zero (predicated)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Rounding

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p2)|FEAT_SME2p2
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
  "pg": {
    "register": "Preg1"
  },
  "zn": {
    "register": "Zreg2.D"
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
FRINT64Z Zreg1.D, Preg1/Z, Zreg2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/FRINT64Z--Floating-point-round-to-64-bit-integer--rounding-toward-zero--predicated--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svrinta[_f16]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrinta%5B_f16%5D_m

### Signature (source notation)

```c
svfloat16_t svrinta[_f16]_m(svfloat16_t inactive, svbool_t pg, svfloat16_t op);
```

### Description

Round to nearest, ties away from zero

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Rounding

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME
```

### Return type metadata

```json
{
  "return_base_type": "float",
  "element_bit_size": "16",
  "value": "svfloat16_t"
}
```

### Argument preparation and constraints

```json
{
  "inactive": {
    "register": "Zinactive.H|Ztied.H"
  },
  "pg": {
    "register": "Pg"
  },
  "op": {
    "register": "Zop.H"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.H|Ztied.H": "result"
  }
]
```

### Instruction mapping

When result and inactive are in the same register, this intrinsic compiles to:

```asm
FRINTA Ztied.H, Pg/M, Zop.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FRINT-r---Floating-point-round-to-integral-value--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zinactive
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FRINTA Zresult.H, Pg/M, Zop.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FRINT-r---Floating-point-round-to-integral-value--predicated--

### Operation

Source operation ID: `SveOperation_svrinta_f16_m`

**Operation**



Return a vector in which each active element *i* contains the result of rounding `op[i]` to the nearest integral value, or rounding away from zero in the event of a tie.  Take the inactive elements of the result from the corresponding elements of `inactive`.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.  The function never triggers an IEEE Inexact exception.

## svrinta[_f16]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrinta%5B_f16%5D_x

### Signature (source notation)

```c
svfloat16_t svrinta[_f16]_x(svbool_t pg, svfloat16_t op);
```

### Description

Round to nearest, ties away from zero

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Rounding

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME
```

### Return type metadata

```json
{
  "return_base_type": "float",
  "element_bit_size": "16",
  "value": "svfloat16_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Pg"
  },
  "op": {
    "register": "Zop.H|Ztied.H"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.H|Ztied.H": "result"
  }
]
```

### Instruction mapping

When result and op are in the same register, this intrinsic compiles to:

```asm
FRINTA Ztied.H, Pg/M, Ztied.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FRINT-r---Floating-point-round-to-integral-value--predicated--

When result and op are in different registers, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FRINTA Zresult.H, Pg/M, Zop.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FRINT-r---Floating-point-round-to-integral-value--predicated--

### Operation

Source operation ID: `SveOperation_svrinta_f16_x`

**Operation**



Return a vector in which each active element *i* contains the result of rounding `op[i]` to the nearest integral value, or rounding away from zero in the event of a tie.  The inactive elements of the result have arbitrary, undefined values.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.  The function never triggers an IEEE Inexact exception.

## svrinta[_f16]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrinta%5B_f16%5D_z

### Signature (source notation)

```c
svfloat16_t svrinta[_f16]_z(svbool_t pg, svfloat16_t op);
```

### Description

Round to nearest, ties away from zero

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Rounding

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME
```

### Return type metadata

```json
{
  "return_base_type": "float",
  "element_bit_size": "16",
  "value": "svfloat16_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Pg"
  },
  "op": {
    "register": "Zop.H"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.H": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instructions, or functionally equivalent instructions:

```asm
MOVPRFX Zresult.H, Pg/Z, Zop.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
FRINTA Zresult.H, Pg/M, Zop.H  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FRINT-r---Floating-point-round-to-integral-value--predicated--

### Operation

Source operation ID: `SveOperation_svrinta_f16_z`

**Operation**



Return a vector in which each active element *i* contains the result of rounding `op[i]` to the nearest integral value, or rounding away from zero in the event of a tie.  Set the inactive elements of the result to zero.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.  The function never triggers an IEEE Inexact exception.



**[1]** Note that `result` must be in a different register from `op`

## svrinta[_f32]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrinta%5B_f32%5D_m

### Signature (source notation)

```c
svfloat32_t svrinta[_f32]_m(svfloat32_t inactive, svbool_t pg, svfloat32_t op);
```

### Description

Round to nearest, ties away from zero

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Rounding

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME
```

### Return type metadata

```json
{
  "return_base_type": "float",
  "element_bit_size": "32",
  "value": "svfloat32_t"
}
```

### Argument preparation and constraints

```json
{
  "inactive": {
    "register": "Zinactive.S|Ztied.S"
  },
  "pg": {
    "register": "Pg"
  },
  "op": {
    "register": "Zop.S"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.S|Ztied.S": "result"
  }
]
```

### Instruction mapping

When result and inactive are in the same register, this intrinsic compiles to:

```asm
FRINTA Ztied.S, Pg/M, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FRINT-r---Floating-point-round-to-integral-value--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zinactive
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FRINTA Zresult.S, Pg/M, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FRINT-r---Floating-point-round-to-integral-value--predicated--

### Operation

Source operation ID: `SveOperation_svrinta_f16_m`

**Operation**



Return a vector in which each active element *i* contains the result of rounding `op[i]` to the nearest integral value, or rounding away from zero in the event of a tie.  Take the inactive elements of the result from the corresponding elements of `inactive`.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.  The function never triggers an IEEE Inexact exception.

## svrinta[_f32]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrinta%5B_f32%5D_x

### Signature (source notation)

```c
svfloat32_t svrinta[_f32]_x(svbool_t pg, svfloat32_t op);
```

### Description

Round to nearest, ties away from zero

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Rounding

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME
```

### Return type metadata

```json
{
  "return_base_type": "float",
  "element_bit_size": "32",
  "value": "svfloat32_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Pg"
  },
  "op": {
    "register": "Zop.S|Ztied.S"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.S|Ztied.S": "result"
  }
]
```

### Instruction mapping

When result and op are in the same register, this intrinsic compiles to:

```asm
FRINTA Ztied.S, Pg/M, Ztied.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FRINT-r---Floating-point-round-to-integral-value--predicated--

When result and op are in different registers, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FRINTA Zresult.S, Pg/M, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FRINT-r---Floating-point-round-to-integral-value--predicated--

### Operation

Source operation ID: `SveOperation_svrinta_f16_x`

**Operation**



Return a vector in which each active element *i* contains the result of rounding `op[i]` to the nearest integral value, or rounding away from zero in the event of a tie.  The inactive elements of the result have arbitrary, undefined values.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.  The function never triggers an IEEE Inexact exception.

## svrinta[_f32]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrinta%5B_f32%5D_z

### Signature (source notation)

```c
svfloat32_t svrinta[_f32]_z(svbool_t pg, svfloat32_t op);
```

### Description

Round to nearest, ties away from zero

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Rounding

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME
```

### Return type metadata

```json
{
  "return_base_type": "float",
  "element_bit_size": "32",
  "value": "svfloat32_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Pg"
  },
  "op": {
    "register": "Zop.S"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.S": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instructions, or functionally equivalent instructions:

```asm
MOVPRFX Zresult.S, Pg/Z, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
FRINTA Zresult.S, Pg/M, Zop.S  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FRINT-r---Floating-point-round-to-integral-value--predicated--

### Operation

Source operation ID: `SveOperation_svrinta_f16_z`

**Operation**



Return a vector in which each active element *i* contains the result of rounding `op[i]` to the nearest integral value, or rounding away from zero in the event of a tie.  Set the inactive elements of the result to zero.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.  The function never triggers an IEEE Inexact exception.



**[1]** Note that `result` must be in a different register from `op`

## svrinta[_f64]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrinta%5B_f64%5D_m

### Signature (source notation)

```c
svfloat64_t svrinta[_f64]_m(svfloat64_t inactive, svbool_t pg, svfloat64_t op);
```

### Description

Round to nearest, ties away from zero

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Rounding

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME
```

### Return type metadata

```json
{
  "return_base_type": "float",
  "element_bit_size": "64",
  "value": "svfloat64_t"
}
```

### Argument preparation and constraints

```json
{
  "inactive": {
    "register": "Zinactive.D|Ztied.D"
  },
  "pg": {
    "register": "Pg"
  },
  "op": {
    "register": "Zop.D"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.D|Ztied.D": "result"
  }
]
```

### Instruction mapping

When result and inactive are in the same register, this intrinsic compiles to:

```asm
FRINTA Ztied.D, Pg/M, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FRINT-r---Floating-point-round-to-integral-value--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zinactive
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FRINTA Zresult.D, Pg/M, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FRINT-r---Floating-point-round-to-integral-value--predicated--

### Operation

Source operation ID: `SveOperation_svrinta_f16_m`

**Operation**



Return a vector in which each active element *i* contains the result of rounding `op[i]` to the nearest integral value, or rounding away from zero in the event of a tie.  Take the inactive elements of the result from the corresponding elements of `inactive`.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.  The function never triggers an IEEE Inexact exception.

## svrinta[_f64]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrinta%5B_f64%5D_x

### Signature (source notation)

```c
svfloat64_t svrinta[_f64]_x(svbool_t pg, svfloat64_t op);
```

### Description

Round to nearest, ties away from zero

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Rounding

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME
```

### Return type metadata

```json
{
  "return_base_type": "float",
  "element_bit_size": "64",
  "value": "svfloat64_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Pg"
  },
  "op": {
    "register": "Zop.D|Ztied.D"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.D|Ztied.D": "result"
  }
]
```

### Instruction mapping

When result and op are in the same register, this intrinsic compiles to:

```asm
FRINTA Ztied.D, Pg/M, Ztied.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FRINT-r---Floating-point-round-to-integral-value--predicated--

When result and op are in different registers, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FRINTA Zresult.D, Pg/M, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FRINT-r---Floating-point-round-to-integral-value--predicated--

### Operation

Source operation ID: `SveOperation_svrinta_f16_x`

**Operation**



Return a vector in which each active element *i* contains the result of rounding `op[i]` to the nearest integral value, or rounding away from zero in the event of a tie.  The inactive elements of the result have arbitrary, undefined values.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.  The function never triggers an IEEE Inexact exception.

## svrinta[_f64]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrinta%5B_f64%5D_z

### Signature (source notation)

```c
svfloat64_t svrinta[_f64]_z(svbool_t pg, svfloat64_t op);
```

### Description

Round to nearest, ties away from zero

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Rounding

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME
```

### Return type metadata

```json
{
  "return_base_type": "float",
  "element_bit_size": "64",
  "value": "svfloat64_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Pg"
  },
  "op": {
    "register": "Zop.D"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.D": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instructions, or functionally equivalent instructions:

```asm
MOVPRFX Zresult.D, Pg/Z, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
FRINTA Zresult.D, Pg/M, Zop.D  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FRINT-r---Floating-point-round-to-integral-value--predicated--

### Operation

Source operation ID: `SveOperation_svrinta_f16_z`

**Operation**



Return a vector in which each active element *i* contains the result of rounding `op[i]` to the nearest integral value, or rounding away from zero in the event of a tie.  Set the inactive elements of the result to zero.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.  The function never triggers an IEEE Inexact exception.



**[1]** Note that `result` must be in a different register from `op`

## svrinti[_f16]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrinti%5B_f16%5D_m

### Signature (source notation)

```c
svfloat16_t svrinti[_f16]_m(svfloat16_t inactive, svbool_t pg, svfloat16_t op);
```

### Description

Round using current rounding mode (inexact)

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Rounding

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME
```

### Return type metadata

```json
{
  "return_base_type": "float",
  "element_bit_size": "16",
  "value": "svfloat16_t"
}
```

### Argument preparation and constraints

```json
{
  "inactive": {
    "register": "Zinactive.H|Ztied.H"
  },
  "pg": {
    "register": "Pg"
  },
  "op": {
    "register": "Zop.H"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.H|Ztied.H": "result"
  }
]
```

### Instruction mapping

When result and inactive are in the same register, this intrinsic compiles to:

```asm
FRINTI Ztied.H, Pg/M, Zop.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FRINT-r---Floating-point-round-to-integral-value--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zinactive
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FRINTI Zresult.H, Pg/M, Zop.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FRINT-r---Floating-point-round-to-integral-value--predicated--

### Operation

Source operation ID: `SveOperation_svrinti_f16_m`

**Operation**



Return a vector in which each active element *i* contains the result of rounding `op[i]` to an integral value using the current rounding mode.  Take the inactive elements of the result from the corresponding elements of `inactive`.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.  The function never triggers an IEEE Inexact exception.

## svrinti[_f16]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrinti%5B_f16%5D_x

### Signature (source notation)

```c
svfloat16_t svrinti[_f16]_x(svbool_t pg, svfloat16_t op);
```

### Description

Round using current rounding mode (inexact)

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Rounding

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME
```

### Return type metadata

```json
{
  "return_base_type": "float",
  "element_bit_size": "16",
  "value": "svfloat16_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Pg"
  },
  "op": {
    "register": "Zop.H|Ztied.H"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.H|Ztied.H": "result"
  }
]
```

### Instruction mapping

When result and op are in the same register, this intrinsic compiles to:

```asm
FRINTI Ztied.H, Pg/M, Ztied.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FRINT-r---Floating-point-round-to-integral-value--predicated--

When result and op are in different registers, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FRINTI Zresult.H, Pg/M, Zop.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FRINT-r---Floating-point-round-to-integral-value--predicated--

### Operation

Source operation ID: `SveOperation_svrinti_f16_x`

**Operation**



Return a vector in which each active element *i* contains the result of rounding `op[i]` to an integral value using the current rounding mode.  The inactive elements of the result have arbitrary, undefined values.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.  The function never triggers an IEEE Inexact exception.

## svrinti[_f16]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrinti%5B_f16%5D_z

### Signature (source notation)

```c
svfloat16_t svrinti[_f16]_z(svbool_t pg, svfloat16_t op);
```

### Description

Round using current rounding mode (inexact)

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Rounding

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME
```

### Return type metadata

```json
{
  "return_base_type": "float",
  "element_bit_size": "16",
  "value": "svfloat16_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Pg"
  },
  "op": {
    "register": "Zop.H"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.H": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instructions, or functionally equivalent instructions:

```asm
MOVPRFX Zresult.H, Pg/Z, Zop.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
FRINTI Zresult.H, Pg/M, Zop.H  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FRINT-r---Floating-point-round-to-integral-value--predicated--

### Operation

Source operation ID: `SveOperation_svrinti_f16_z`

**Operation**



Return a vector in which each active element *i* contains the result of rounding `op[i]` to an integral value using the current rounding mode.  Set the inactive elements of the result to zero.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.  The function never triggers an IEEE Inexact exception.



**[1]** Note that `result` must be in a different register from `op`

## svrinti[_f32]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrinti%5B_f32%5D_m

### Signature (source notation)

```c
svfloat32_t svrinti[_f32]_m(svfloat32_t inactive, svbool_t pg, svfloat32_t op);
```

### Description

Round using current rounding mode (inexact)

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Rounding

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME
```

### Return type metadata

```json
{
  "return_base_type": "float",
  "element_bit_size": "32",
  "value": "svfloat32_t"
}
```

### Argument preparation and constraints

```json
{
  "inactive": {
    "register": "Zinactive.S|Ztied.S"
  },
  "pg": {
    "register": "Pg"
  },
  "op": {
    "register": "Zop.S"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.S|Ztied.S": "result"
  }
]
```

### Instruction mapping

When result and inactive are in the same register, this intrinsic compiles to:

```asm
FRINTI Ztied.S, Pg/M, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FRINT-r---Floating-point-round-to-integral-value--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zinactive
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FRINTI Zresult.S, Pg/M, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FRINT-r---Floating-point-round-to-integral-value--predicated--

### Operation

Source operation ID: `SveOperation_svrinti_f16_m`

**Operation**



Return a vector in which each active element *i* contains the result of rounding `op[i]` to an integral value using the current rounding mode.  Take the inactive elements of the result from the corresponding elements of `inactive`.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.  The function never triggers an IEEE Inexact exception.

## svrinti[_f32]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrinti%5B_f32%5D_x

### Signature (source notation)

```c
svfloat32_t svrinti[_f32]_x(svbool_t pg, svfloat32_t op);
```

### Description

Round using current rounding mode (inexact)

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Rounding

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME
```

### Return type metadata

```json
{
  "return_base_type": "float",
  "element_bit_size": "32",
  "value": "svfloat32_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Pg"
  },
  "op": {
    "register": "Zop.S|Ztied.S"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.S|Ztied.S": "result"
  }
]
```

### Instruction mapping

When result and op are in the same register, this intrinsic compiles to:

```asm
FRINTI Ztied.S, Pg/M, Ztied.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FRINT-r---Floating-point-round-to-integral-value--predicated--

When result and op are in different registers, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FRINTI Zresult.S, Pg/M, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FRINT-r---Floating-point-round-to-integral-value--predicated--

### Operation

Source operation ID: `SveOperation_svrinti_f16_x`

**Operation**



Return a vector in which each active element *i* contains the result of rounding `op[i]` to an integral value using the current rounding mode.  The inactive elements of the result have arbitrary, undefined values.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.  The function never triggers an IEEE Inexact exception.

## svrinti[_f32]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrinti%5B_f32%5D_z

### Signature (source notation)

```c
svfloat32_t svrinti[_f32]_z(svbool_t pg, svfloat32_t op);
```

### Description

Round using current rounding mode (inexact)

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Rounding

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME
```

### Return type metadata

```json
{
  "return_base_type": "float",
  "element_bit_size": "32",
  "value": "svfloat32_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Pg"
  },
  "op": {
    "register": "Zop.S"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.S": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instructions, or functionally equivalent instructions:

```asm
MOVPRFX Zresult.S, Pg/Z, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
FRINTI Zresult.S, Pg/M, Zop.S  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FRINT-r---Floating-point-round-to-integral-value--predicated--

### Operation

Source operation ID: `SveOperation_svrinti_f16_z`

**Operation**



Return a vector in which each active element *i* contains the result of rounding `op[i]` to an integral value using the current rounding mode.  Set the inactive elements of the result to zero.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.  The function never triggers an IEEE Inexact exception.



**[1]** Note that `result` must be in a different register from `op`

## svrinti[_f64]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrinti%5B_f64%5D_m

### Signature (source notation)

```c
svfloat64_t svrinti[_f64]_m(svfloat64_t inactive, svbool_t pg, svfloat64_t op);
```

### Description

Round using current rounding mode (inexact)

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Rounding

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME
```

### Return type metadata

```json
{
  "return_base_type": "float",
  "element_bit_size": "64",
  "value": "svfloat64_t"
}
```

### Argument preparation and constraints

```json
{
  "inactive": {
    "register": "Zinactive.D|Ztied.D"
  },
  "pg": {
    "register": "Pg"
  },
  "op": {
    "register": "Zop.D"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.D|Ztied.D": "result"
  }
]
```

### Instruction mapping

When result and inactive are in the same register, this intrinsic compiles to:

```asm
FRINTI Ztied.D, Pg/M, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FRINT-r---Floating-point-round-to-integral-value--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zinactive
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FRINTI Zresult.D, Pg/M, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FRINT-r---Floating-point-round-to-integral-value--predicated--

### Operation

Source operation ID: `SveOperation_svrinti_f16_m`

**Operation**



Return a vector in which each active element *i* contains the result of rounding `op[i]` to an integral value using the current rounding mode.  Take the inactive elements of the result from the corresponding elements of `inactive`.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.  The function never triggers an IEEE Inexact exception.

## svrinti[_f64]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrinti%5B_f64%5D_x

### Signature (source notation)

```c
svfloat64_t svrinti[_f64]_x(svbool_t pg, svfloat64_t op);
```

### Description

Round using current rounding mode (inexact)

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Rounding

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME
```

### Return type metadata

```json
{
  "return_base_type": "float",
  "element_bit_size": "64",
  "value": "svfloat64_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Pg"
  },
  "op": {
    "register": "Zop.D|Ztied.D"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.D|Ztied.D": "result"
  }
]
```

### Instruction mapping

When result and op are in the same register, this intrinsic compiles to:

```asm
FRINTI Ztied.D, Pg/M, Ztied.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FRINT-r---Floating-point-round-to-integral-value--predicated--

When result and op are in different registers, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FRINTI Zresult.D, Pg/M, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FRINT-r---Floating-point-round-to-integral-value--predicated--

### Operation

Source operation ID: `SveOperation_svrinti_f16_x`

**Operation**



Return a vector in which each active element *i* contains the result of rounding `op[i]` to an integral value using the current rounding mode.  The inactive elements of the result have arbitrary, undefined values.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.  The function never triggers an IEEE Inexact exception.

## svrinti[_f64]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrinti%5B_f64%5D_z

### Signature (source notation)

```c
svfloat64_t svrinti[_f64]_z(svbool_t pg, svfloat64_t op);
```

### Description

Round using current rounding mode (inexact)

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Rounding

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME
```

### Return type metadata

```json
{
  "return_base_type": "float",
  "element_bit_size": "64",
  "value": "svfloat64_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Pg"
  },
  "op": {
    "register": "Zop.D"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.D": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instructions, or functionally equivalent instructions:

```asm
MOVPRFX Zresult.D, Pg/Z, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
FRINTI Zresult.D, Pg/M, Zop.D  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FRINT-r---Floating-point-round-to-integral-value--predicated--

### Operation

Source operation ID: `SveOperation_svrinti_f16_z`

**Operation**



Return a vector in which each active element *i* contains the result of rounding `op[i]` to an integral value using the current rounding mode.  Set the inactive elements of the result to zero.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.  The function never triggers an IEEE Inexact exception.



**[1]** Note that `result` must be in a different register from `op`

## svrintm[_f16]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrintm%5B_f16%5D_m

### Signature (source notation)

```c
svfloat16_t svrintm[_f16]_m(svfloat16_t inactive, svbool_t pg, svfloat16_t op);
```

### Description

Round towards -∞

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Rounding

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME
```

### Return type metadata

```json
{
  "return_base_type": "float",
  "element_bit_size": "16",
  "value": "svfloat16_t"
}
```

### Argument preparation and constraints

```json
{
  "inactive": {
    "register": "Zinactive.H|Ztied.H"
  },
  "pg": {
    "register": "Pg"
  },
  "op": {
    "register": "Zop.H"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.H|Ztied.H": "result"
  }
]
```

### Instruction mapping

When result and inactive are in the same register, this intrinsic compiles to:

```asm
FRINTM Ztied.H, Pg/M, Zop.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FRINT-r---Floating-point-round-to-integral-value--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zinactive
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FRINTM Zresult.H, Pg/M, Zop.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FRINT-r---Floating-point-round-to-integral-value--predicated--

### Operation

Source operation ID: `SveOperation_svrintm_f16_m`

**Operation**



Return a vector in which each active element *i* contains the result of rounding `op[i]` to an integral value, towards -∞.  Take the inactive elements of the result from the corresponding elements of `inactive`.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.  The function never triggers an IEEE Inexact exception.

## svrintm[_f16]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrintm%5B_f16%5D_x

### Signature (source notation)

```c
svfloat16_t svrintm[_f16]_x(svbool_t pg, svfloat16_t op);
```

### Description

Round towards -∞

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Rounding

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME
```

### Return type metadata

```json
{
  "return_base_type": "float",
  "element_bit_size": "16",
  "value": "svfloat16_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Pg"
  },
  "op": {
    "register": "Zop.H|Ztied.H"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.H|Ztied.H": "result"
  }
]
```

### Instruction mapping

When result and op are in the same register, this intrinsic compiles to:

```asm
FRINTM Ztied.H, Pg/M, Ztied.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FRINT-r---Floating-point-round-to-integral-value--predicated--

When result and op are in different registers, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FRINTM Zresult.H, Pg/M, Zop.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FRINT-r---Floating-point-round-to-integral-value--predicated--

### Operation

Source operation ID: `SveOperation_svrintm_f16_x`

**Operation**



Return a vector in which each active element *i* contains the result of rounding `op[i]` to an integral value, towards -∞.  The inactive elements of the result have arbitrary, undefined values.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.  The function never triggers an IEEE Inexact exception.

## svrintm[_f16]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrintm%5B_f16%5D_z

### Signature (source notation)

```c
svfloat16_t svrintm[_f16]_z(svbool_t pg, svfloat16_t op);
```

### Description

Round towards -∞

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Rounding

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME
```

### Return type metadata

```json
{
  "return_base_type": "float",
  "element_bit_size": "16",
  "value": "svfloat16_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Pg"
  },
  "op": {
    "register": "Zop.H"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.H": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instructions, or functionally equivalent instructions:

```asm
MOVPRFX Zresult.H, Pg/Z, Zop.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
FRINTM Zresult.H, Pg/M, Zop.H  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FRINT-r---Floating-point-round-to-integral-value--predicated--

### Operation

Source operation ID: `SveOperation_svrintm_f16_z`

**Operation**



Return a vector in which each active element *i* contains the result of rounding `op[i]` to an integral value, towards -∞.  Set the inactive elements of the result to zero.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.  The function never triggers an IEEE Inexact exception.



**[1]** Note that `result` must be in a different register from `op`

## svrintm[_f32]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrintm%5B_f32%5D_m

### Signature (source notation)

```c
svfloat32_t svrintm[_f32]_m(svfloat32_t inactive, svbool_t pg, svfloat32_t op);
```

### Description

Round towards -∞

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Rounding

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME
```

### Return type metadata

```json
{
  "return_base_type": "float",
  "element_bit_size": "32",
  "value": "svfloat32_t"
}
```

### Argument preparation and constraints

```json
{
  "inactive": {
    "register": "Zinactive.S|Ztied.S"
  },
  "pg": {
    "register": "Pg"
  },
  "op": {
    "register": "Zop.S"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.S|Ztied.S": "result"
  }
]
```

### Instruction mapping

When result and inactive are in the same register, this intrinsic compiles to:

```asm
FRINTM Ztied.S, Pg/M, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FRINT-r---Floating-point-round-to-integral-value--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zinactive
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FRINTM Zresult.S, Pg/M, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FRINT-r---Floating-point-round-to-integral-value--predicated--

### Operation

Source operation ID: `SveOperation_svrintm_f16_m`

**Operation**



Return a vector in which each active element *i* contains the result of rounding `op[i]` to an integral value, towards -∞.  Take the inactive elements of the result from the corresponding elements of `inactive`.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.  The function never triggers an IEEE Inexact exception.

## svrintm[_f32]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrintm%5B_f32%5D_x

### Signature (source notation)

```c
svfloat32_t svrintm[_f32]_x(svbool_t pg, svfloat32_t op);
```

### Description

Round towards -∞

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Rounding

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME
```

### Return type metadata

```json
{
  "return_base_type": "float",
  "element_bit_size": "32",
  "value": "svfloat32_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Pg"
  },
  "op": {
    "register": "Zop.S|Ztied.S"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.S|Ztied.S": "result"
  }
]
```

### Instruction mapping

When result and op are in the same register, this intrinsic compiles to:

```asm
FRINTM Ztied.S, Pg/M, Ztied.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FRINT-r---Floating-point-round-to-integral-value--predicated--

When result and op are in different registers, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FRINTM Zresult.S, Pg/M, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FRINT-r---Floating-point-round-to-integral-value--predicated--

### Operation

Source operation ID: `SveOperation_svrintm_f16_x`

**Operation**



Return a vector in which each active element *i* contains the result of rounding `op[i]` to an integral value, towards -∞.  The inactive elements of the result have arbitrary, undefined values.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.  The function never triggers an IEEE Inexact exception.

## svrintm[_f32]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrintm%5B_f32%5D_z

### Signature (source notation)

```c
svfloat32_t svrintm[_f32]_z(svbool_t pg, svfloat32_t op);
```

### Description

Round towards -∞

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Rounding

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME
```

### Return type metadata

```json
{
  "return_base_type": "float",
  "element_bit_size": "32",
  "value": "svfloat32_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Pg"
  },
  "op": {
    "register": "Zop.S"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.S": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instructions, or functionally equivalent instructions:

```asm
MOVPRFX Zresult.S, Pg/Z, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
FRINTM Zresult.S, Pg/M, Zop.S  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FRINT-r---Floating-point-round-to-integral-value--predicated--

### Operation

Source operation ID: `SveOperation_svrintm_f16_z`

**Operation**



Return a vector in which each active element *i* contains the result of rounding `op[i]` to an integral value, towards -∞.  Set the inactive elements of the result to zero.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.  The function never triggers an IEEE Inexact exception.



**[1]** Note that `result` must be in a different register from `op`

## svrintm[_f64]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrintm%5B_f64%5D_m

### Signature (source notation)

```c
svfloat64_t svrintm[_f64]_m(svfloat64_t inactive, svbool_t pg, svfloat64_t op);
```

### Description

Round towards -∞

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Rounding

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME
```

### Return type metadata

```json
{
  "return_base_type": "float",
  "element_bit_size": "64",
  "value": "svfloat64_t"
}
```

### Argument preparation and constraints

```json
{
  "inactive": {
    "register": "Zinactive.D|Ztied.D"
  },
  "pg": {
    "register": "Pg"
  },
  "op": {
    "register": "Zop.D"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.D|Ztied.D": "result"
  }
]
```

### Instruction mapping

When result and inactive are in the same register, this intrinsic compiles to:

```asm
FRINTM Ztied.D, Pg/M, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FRINT-r---Floating-point-round-to-integral-value--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zinactive
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FRINTM Zresult.D, Pg/M, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FRINT-r---Floating-point-round-to-integral-value--predicated--

### Operation

Source operation ID: `SveOperation_svrintm_f16_m`

**Operation**



Return a vector in which each active element *i* contains the result of rounding `op[i]` to an integral value, towards -∞.  Take the inactive elements of the result from the corresponding elements of `inactive`.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.  The function never triggers an IEEE Inexact exception.

## svrintm[_f64]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrintm%5B_f64%5D_x

### Signature (source notation)

```c
svfloat64_t svrintm[_f64]_x(svbool_t pg, svfloat64_t op);
```

### Description

Round towards -∞

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Rounding

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME
```

### Return type metadata

```json
{
  "return_base_type": "float",
  "element_bit_size": "64",
  "value": "svfloat64_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Pg"
  },
  "op": {
    "register": "Zop.D|Ztied.D"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.D|Ztied.D": "result"
  }
]
```

### Instruction mapping

When result and op are in the same register, this intrinsic compiles to:

```asm
FRINTM Ztied.D, Pg/M, Ztied.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FRINT-r---Floating-point-round-to-integral-value--predicated--

When result and op are in different registers, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FRINTM Zresult.D, Pg/M, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FRINT-r---Floating-point-round-to-integral-value--predicated--

### Operation

Source operation ID: `SveOperation_svrintm_f16_x`

**Operation**



Return a vector in which each active element *i* contains the result of rounding `op[i]` to an integral value, towards -∞.  The inactive elements of the result have arbitrary, undefined values.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.  The function never triggers an IEEE Inexact exception.

