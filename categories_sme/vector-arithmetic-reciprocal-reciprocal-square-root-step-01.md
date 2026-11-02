# SME / Vector arithmetic / Reciprocal / Reciprocal square-root step — Part 1

## svrsqrts[_f16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrsqrts%5B_f16%5D

### Signature (source notation)

```c
svfloat16_t svrsqrts[_f16](svfloat16_t op1, svfloat16_t op2);
```

### Description

Reciprocal square root step

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Reciprocal / Reciprocal square-root step

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
  "op1": {
    "register": "Zop1.H"
  },
  "op2": {
    "register": "Zop2.H"
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

This intrinsic compiles to the following instruction:

```asm
FRSQRTS Zresult.H, Zop1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FRSQRTS--Floating-point-reciprocal-square-root-step--unpredicated--

### Operation

Source operation ID: `SveOperation_svrsqrts_f16`

**Operation**



Return a vector in which element *i* contains:



```text
(3.0 - op1[i] * op2[i]) / 2.0
```



with the modification that multiplying a zero by an infinity gives zero.  The functions perform a fused operation, with no intermediate rounding after the multiplication.



**Exceptions**



Signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.

## svrsqrts[_f32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrsqrts%5B_f32%5D

### Signature (source notation)

```c
svfloat32_t svrsqrts[_f32](svfloat32_t op1, svfloat32_t op2);
```

### Description

Reciprocal square root step

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Reciprocal / Reciprocal square-root step

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
  "op1": {
    "register": "Zop1.S"
  },
  "op2": {
    "register": "Zop2.S"
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

This intrinsic compiles to the following instruction:

```asm
FRSQRTS Zresult.S, Zop1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FRSQRTS--Floating-point-reciprocal-square-root-step--unpredicated--

### Operation

Source operation ID: `SveOperation_svrsqrts_f16`

**Operation**



Return a vector in which element *i* contains:



```text
(3.0 - op1[i] * op2[i]) / 2.0
```



with the modification that multiplying a zero by an infinity gives zero.  The functions perform a fused operation, with no intermediate rounding after the multiplication.



**Exceptions**



Signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.

## svrsqrts[_f64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrsqrts%5B_f64%5D

### Signature (source notation)

```c
svfloat64_t svrsqrts[_f64](svfloat64_t op1, svfloat64_t op2);
```

### Description

Reciprocal square root step

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Reciprocal / Reciprocal square-root step

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
  "op1": {
    "register": "Zop1.D"
  },
  "op2": {
    "register": "Zop2.D"
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

This intrinsic compiles to the following instruction:

```asm
FRSQRTS Zresult.D, Zop1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FRSQRTS--Floating-point-reciprocal-square-root-step--unpredicated--

### Operation

Source operation ID: `SveOperation_svrsqrts_f16`

**Operation**



Return a vector in which element *i* contains:



```text
(3.0 - op1[i] * op2[i]) / 2.0
```



with the modification that multiplying a zero by an infinity gives zero.  The functions perform a fused operation, with no intermediate rounding after the multiplication.



**Exceptions**



Signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.

