# SME2 / Vector arithmetic / Rounding — Part 1

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

## svrinta[_f32_x2]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrinta%5B_f32_x2%5D

### Signature (source notation)

```c
svfloat32x2_t svrinta[_f32_x2](svfloat32x2_t zn)
    __arm_streaming;
```

### Description

Multi-vector floating-point round to integral value, to nearest with ties away from zero

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Vector arithmetic / Rounding

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
FRINTA { Zreg1.S, Zreg2.S }, { Zreg3.S, Zreg4.S }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/FRINTA--Multi-vector-floating-point-round-to-integral-value--to-nearest-with-ties-away-from-zero-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svrinta[_f32_x4]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrinta%5B_f32_x4%5D

### Signature (source notation)

```c
svfloat32x4_t svrinta[_f32_x4](svfloat32x4_t zn)
    __arm_streaming;
```

### Description

Multi-vector floating-point round to integral value, to nearest with ties away from zero

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Vector arithmetic / Rounding

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
FRINTA { Zreg1.S - Zreg2.S }, { Zreg3.S - Zreg4.S }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/FRINTA--Multi-vector-floating-point-round-to-integral-value--to-nearest-with-ties-away-from-zero-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svrintm[_f32_x2]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrintm%5B_f32_x2%5D

### Signature (source notation)

```c
svfloat32x2_t svrintm[_f32_x2](svfloat32x2_t zn)
    __arm_streaming;
```

### Description

Multi-vector floating-point round to integral value, toward minus Infinity

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Vector arithmetic / Rounding

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
FRINTM { Zreg1.S, Zreg2.S }, { Zreg3.S, Zreg4.S }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/FRINTM--Multi-vector-floating-point-round-to-integral-value--toward-minus-Infinity-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svrintm[_f32_x4]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrintm%5B_f32_x4%5D

### Signature (source notation)

```c
svfloat32x4_t svrintm[_f32_x4](svfloat32x4_t zn)
    __arm_streaming;
```

### Description

Multi-vector floating-point round to integral value, toward minus Infinity

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Vector arithmetic / Rounding

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
FRINTM { Zreg1.S - Zreg2.S }, { Zreg3.S - Zreg4.S }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/FRINTM--Multi-vector-floating-point-round-to-integral-value--toward-minus-Infinity-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svrintn[_f32_x2]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrintn%5B_f32_x2%5D

### Signature (source notation)

```c
svfloat32x2_t svrintn[_f32_x2](svfloat32x2_t zn)
    __arm_streaming;
```

### Description

Multi-vector floating-point round to integral value, to nearest with ties to even

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Vector arithmetic / Rounding

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
FRINTN { Zreg1.S, Zreg2.S }, { Zreg3.S, Zreg4.S }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/FRINTN--Multi-vector-floating-point-round-to-integral-value--to-nearest-with-ties-to-even-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svrintn[_f32_x4]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrintn%5B_f32_x4%5D

### Signature (source notation)

```c
svfloat32x4_t svrintn[_f32_x4](svfloat32x4_t zn)
    __arm_streaming;
```

### Description

Multi-vector floating-point round to integral value, to nearest with ties to even

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Vector arithmetic / Rounding

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
FRINTN { Zreg1.S - Zreg2.S }, { Zreg3.S - Zreg4.S }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/FRINTN--Multi-vector-floating-point-round-to-integral-value--to-nearest-with-ties-to-even-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svrintp[_f32_x2]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrintp%5B_f32_x2%5D

### Signature (source notation)

```c
svfloat32x2_t svrintp[_f32_x2](svfloat32x2_t zn)
    __arm_streaming;
```

### Description

Multi-vector floating-point round to integral value, toward plus Infinity

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Vector arithmetic / Rounding

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
FRINTP { Zreg1.S, Zreg2.S }, { Zreg3.S, Zreg4.S }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/FRINTP--Multi-vector-floating-point-round-to-integral-value--toward-plus-Infinity-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svrintp[_f32_x4]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrintp%5B_f32_x4%5D

### Signature (source notation)

```c
svfloat32x4_t svrintp[_f32_x4](svfloat32x4_t zn)
    __arm_streaming;
```

### Description

Multi-vector floating-point round to integral value, toward plus Infinity

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Vector arithmetic / Rounding

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
FRINTP { Zreg1.S - Zreg2.S }, { Zreg3.S - Zreg4.S }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/FRINTP--Multi-vector-floating-point-round-to-integral-value--toward-plus-Infinity-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

