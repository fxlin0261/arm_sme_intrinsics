# SME2 / Vector arithmetic / Across vector arithmetic / Maximum across vector (IEEE754) — Part 1

## svmaxnmqv[_f16]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmaxnmqv%5B_f16%5D

### Signature (source notation)

```c
float16x8_t svmaxnmqv[_f16](svbool_t pg, svfloat16_t zn);
```

### Description

Floating-point maximum number recursive reduction of quadword vector segments

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Across vector arithmetic / Maximum across vector (IEEE754)

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
FMAXNMQV Vreg1.8H, Preg1, Zreg1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/FMAXNMQV--Floating-point-maximum-number-recursive-reduction-of-quadword-vector-segments-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmaxnmqv[_f32]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmaxnmqv%5B_f32%5D

### Signature (source notation)

```c
float32x4_t svmaxnmqv[_f32](svbool_t pg, svfloat32_t zn);
```

### Description

Floating-point maximum number recursive reduction of quadword vector segments

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Across vector arithmetic / Maximum across vector (IEEE754)

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
FMAXNMQV Vreg1.4S, Preg1, Zreg1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/FMAXNMQV--Floating-point-maximum-number-recursive-reduction-of-quadword-vector-segments-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmaxnmqv[_f64]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmaxnmqv%5B_f64%5D

### Signature (source notation)

```c
float64x2_t svmaxnmqv[_f64](svbool_t pg, svfloat64_t zn);
```

### Description

Floating-point maximum number recursive reduction of quadword vector segments

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Across vector arithmetic / Maximum across vector (IEEE754)

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
FMAXNMQV Vreg1.2D, Preg1, Zreg1.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/FMAXNMQV--Floating-point-maximum-number-recursive-reduction-of-quadword-vector-segments-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

