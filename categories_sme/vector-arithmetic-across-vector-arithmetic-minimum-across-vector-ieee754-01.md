# SME / Vector arithmetic / Across vector arithmetic / Minimum across vector (IEEE754) — Part 1

## svminnmqv[_f16]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svminnmqv%5B_f16%5D

### Signature (source notation)

```c
float16x8_t svminnmqv[_f16](svbool_t pg, svfloat16_t zn);
```

### Description

Floating-point minimum number recursive reduction of quadword vector segments

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Across vector arithmetic / Minimum across vector (IEEE754)

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
FMINNMQV Vreg1.8H, Preg1, Zreg1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/FMINNMQV--Floating-point-minimum-number-recursive-reduction-of-quadword-vector-segments-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svminnmqv[_f32]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svminnmqv%5B_f32%5D

### Signature (source notation)

```c
float32x4_t svminnmqv[_f32](svbool_t pg, svfloat32_t zn);
```

### Description

Floating-point minimum number recursive reduction of quadword vector segments

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Across vector arithmetic / Minimum across vector (IEEE754)

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
FMINNMQV Vreg1.4S, Preg1, Zreg1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/FMINNMQV--Floating-point-minimum-number-recursive-reduction-of-quadword-vector-segments-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svminnmqv[_f64]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svminnmqv%5B_f64%5D

### Signature (source notation)

```c
float64x2_t svminnmqv[_f64](svbool_t pg, svfloat64_t zn);
```

### Description

Floating-point minimum number recursive reduction of quadword vector segments

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Across vector arithmetic / Minimum across vector (IEEE754)

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
FMINNMQV Vreg1.2D, Preg1, Zreg1.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/FMINNMQV--Floating-point-minimum-number-recursive-reduction-of-quadword-vector-segments-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svminnmv[_f16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svminnmv%5B_f16%5D

### Signature (source notation)

```c
float16_t svminnmv[_f16](svbool_t pg, svfloat16_t op);
```

### Description

Minimum number reduction to scalar

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Across vector arithmetic / Minimum across vector (IEEE754)

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
  "value": "float16_t"
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
    "Hresult": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
FMINNMV Hresult, Pg, Zop.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMINNMV--Floating-point-minimum-number-recursive-reduction-to-scalar-

### Operation

Source operation ID: `SveOperation_svminnmv_f16`

**Operation**



Return:




- a quiet NaN if no elements are active
- a signaling NaN if any active element of `op` is a signaling NaN
- a quiet NaN if all active elements of `op` are quiet NaNs
- the minimum of all active elements of `op` otherwise (excluding NaNs)



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.

## svminnmv[_f32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svminnmv%5B_f32%5D

### Signature (source notation)

```c
float32_t svminnmv[_f32](svbool_t pg, svfloat32_t op);
```

### Description

Minimum number reduction to scalar

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Across vector arithmetic / Minimum across vector (IEEE754)

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
  "value": "float32_t"
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
    "Sresult": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
FMINNMV Sresult, Pg, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMINNMV--Floating-point-minimum-number-recursive-reduction-to-scalar-

### Operation

Source operation ID: `SveOperation_svminnmv_f16`

**Operation**



Return:




- a quiet NaN if no elements are active
- a signaling NaN if any active element of `op` is a signaling NaN
- a quiet NaN if all active elements of `op` are quiet NaNs
- the minimum of all active elements of `op` otherwise (excluding NaNs)



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.

## svminnmv[_f64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svminnmv%5B_f64%5D

### Signature (source notation)

```c
float64_t svminnmv[_f64](svbool_t pg, svfloat64_t op);
```

### Description

Minimum number reduction to scalar

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Across vector arithmetic / Minimum across vector (IEEE754)

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
  "value": "float64_t"
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
    "Dresult": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
FMINNMV Dresult, Pg, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMINNMV--Floating-point-minimum-number-recursive-reduction-to-scalar-

### Operation

Source operation ID: `SveOperation_svminnmv_f16`

**Operation**



Return:




- a quiet NaN if no elements are active
- a signaling NaN if any active element of `op` is a signaling NaN
- a quiet NaN if all active elements of `op` are quiet NaNs
- the minimum of all active elements of `op` otherwise (excluding NaNs)



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.

