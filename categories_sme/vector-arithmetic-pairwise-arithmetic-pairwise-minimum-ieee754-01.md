# SME / Vector arithmetic / Pairwise arithmetic / Pairwise minimum (IEEE754) — Part 1

## svminnmp[_f16]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svminnmp%5B_f16%5D_m

### Signature (source notation)

```c
svfloat16_t svminnmp[_f16]_m(svbool_t pg, svfloat16_t op1, svfloat16_t op2);
```

### Description

Minimum number pairwise

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Pairwise arithmetic / Pairwise minimum (IEEE754)

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
  "op1": {
    "register": "Zop1.H|Ztied1.H"
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
    "Zresult.H|Ztied1.H": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
FMINNMP Ztied1.H, Pg/M, Ztied1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMINNMP--Floating-point-minimum-number-pairwise-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FMINNMP Zresult.H, Pg/M, Zresult.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMINNMP--Floating-point-minimum-number-pairwise-

### Operation

Source operation ID: `SveOperation_svminnmp_f16_m`

**Operation**



Return a vector in which:




- each active even-indexed element *i* contains the minimum of `op1[i]` and `op1[i + 1]`;
- each active odd-indexed element *i* contains the minimum of `op2[i - 1]` and `op2[i]`.



This minimum operation works as follows:




- The minimum of a signaling NaN and anything else is a signaling NaN.
- The minimum of two quiet NaNs is a quiet NaN.
- Otherwise, the minimum of a quiet NaN and another value is the other value.



Take the inactive elements of the result from the corresponding elements of `op1`.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.

## svminnmp[_f16]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svminnmp%5B_f16%5D_x

### Signature (source notation)

```c
svfloat16_t svminnmp[_f16]_x(svbool_t pg, svfloat16_t op1, svfloat16_t op2);
```

### Description

Minimum number pairwise

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Pairwise arithmetic / Pairwise minimum (IEEE754)

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
  "op1": {
    "register": "Zop1.H|Ztied1.H"
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
    "Zresult.H|Ztied1.H": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
FMINNMP Ztied1.H, Pg/M, Ztied1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMINNMP--Floating-point-minimum-number-pairwise-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FMINNMP Zresult.H, Pg/M, Zresult.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMINNMP--Floating-point-minimum-number-pairwise-

### Operation

Source operation ID: `SveOperation_svminnmp_f16_x`

**Operation**



Return a vector in which:




- each active even-indexed element *i* contains the minimum of `op1[i]` and `op1[i + 1]`;
- each active odd-indexed element *i* contains the minimum of `op2[i - 1]` and `op2[i]`.



This minimum operation works as follows:




- The minimum of a signaling NaN and anything else is a signaling NaN.
- The minimum of two quiet NaNs is a quiet NaN.
- Otherwise, the minimum of a quiet NaN and another value is the other value.



The inactive elements of the result have arbitrary, undefined values.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.

## svminnmp[_f32]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svminnmp%5B_f32%5D_m

### Signature (source notation)

```c
svfloat32_t svminnmp[_f32]_m(svbool_t pg, svfloat32_t op1, svfloat32_t op2);
```

### Description

Minimum number pairwise

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Pairwise arithmetic / Pairwise minimum (IEEE754)

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
  "op1": {
    "register": "Zop1.S|Ztied1.S"
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
    "Zresult.S|Ztied1.S": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
FMINNMP Ztied1.S, Pg/M, Ztied1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMINNMP--Floating-point-minimum-number-pairwise-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FMINNMP Zresult.S, Pg/M, Zresult.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMINNMP--Floating-point-minimum-number-pairwise-

### Operation

Source operation ID: `SveOperation_svminnmp_f16_m`

**Operation**



Return a vector in which:




- each active even-indexed element *i* contains the minimum of `op1[i]` and `op1[i + 1]`;
- each active odd-indexed element *i* contains the minimum of `op2[i - 1]` and `op2[i]`.



This minimum operation works as follows:




- The minimum of a signaling NaN and anything else is a signaling NaN.
- The minimum of two quiet NaNs is a quiet NaN.
- Otherwise, the minimum of a quiet NaN and another value is the other value.



Take the inactive elements of the result from the corresponding elements of `op1`.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.

## svminnmp[_f32]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svminnmp%5B_f32%5D_x

### Signature (source notation)

```c
svfloat32_t svminnmp[_f32]_x(svbool_t pg, svfloat32_t op1, svfloat32_t op2);
```

### Description

Minimum number pairwise

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Pairwise arithmetic / Pairwise minimum (IEEE754)

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
  "op1": {
    "register": "Zop1.S|Ztied1.S"
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
    "Zresult.S|Ztied1.S": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
FMINNMP Ztied1.S, Pg/M, Ztied1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMINNMP--Floating-point-minimum-number-pairwise-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FMINNMP Zresult.S, Pg/M, Zresult.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMINNMP--Floating-point-minimum-number-pairwise-

### Operation

Source operation ID: `SveOperation_svminnmp_f16_x`

**Operation**



Return a vector in which:




- each active even-indexed element *i* contains the minimum of `op1[i]` and `op1[i + 1]`;
- each active odd-indexed element *i* contains the minimum of `op2[i - 1]` and `op2[i]`.



This minimum operation works as follows:




- The minimum of a signaling NaN and anything else is a signaling NaN.
- The minimum of two quiet NaNs is a quiet NaN.
- Otherwise, the minimum of a quiet NaN and another value is the other value.



The inactive elements of the result have arbitrary, undefined values.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.

## svminnmp[_f64]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svminnmp%5B_f64%5D_m

### Signature (source notation)

```c
svfloat64_t svminnmp[_f64]_m(svbool_t pg, svfloat64_t op1, svfloat64_t op2);
```

### Description

Minimum number pairwise

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Pairwise arithmetic / Pairwise minimum (IEEE754)

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
  "op1": {
    "register": "Zop1.D|Ztied1.D"
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
    "Zresult.D|Ztied1.D": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
FMINNMP Ztied1.D, Pg/M, Ztied1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMINNMP--Floating-point-minimum-number-pairwise-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FMINNMP Zresult.D, Pg/M, Zresult.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMINNMP--Floating-point-minimum-number-pairwise-

### Operation

Source operation ID: `SveOperation_svminnmp_f16_m`

**Operation**



Return a vector in which:




- each active even-indexed element *i* contains the minimum of `op1[i]` and `op1[i + 1]`;
- each active odd-indexed element *i* contains the minimum of `op2[i - 1]` and `op2[i]`.



This minimum operation works as follows:




- The minimum of a signaling NaN and anything else is a signaling NaN.
- The minimum of two quiet NaNs is a quiet NaN.
- Otherwise, the minimum of a quiet NaN and another value is the other value.



Take the inactive elements of the result from the corresponding elements of `op1`.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.

## svminnmp[_f64]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svminnmp%5B_f64%5D_x

### Signature (source notation)

```c
svfloat64_t svminnmp[_f64]_x(svbool_t pg, svfloat64_t op1, svfloat64_t op2);
```

### Description

Minimum number pairwise

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Pairwise arithmetic / Pairwise minimum (IEEE754)

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
  "op1": {
    "register": "Zop1.D|Ztied1.D"
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
    "Zresult.D|Ztied1.D": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
FMINNMP Ztied1.D, Pg/M, Ztied1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMINNMP--Floating-point-minimum-number-pairwise-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FMINNMP Zresult.D, Pg/M, Zresult.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMINNMP--Floating-point-minimum-number-pairwise-

### Operation

Source operation ID: `SveOperation_svminnmp_f16_x`

**Operation**



Return a vector in which:




- each active even-indexed element *i* contains the minimum of `op1[i]` and `op1[i + 1]`;
- each active odd-indexed element *i* contains the minimum of `op2[i - 1]` and `op2[i]`.



This minimum operation works as follows:




- The minimum of a signaling NaN and anything else is a signaling NaN.
- The minimum of two quiet NaNs is a quiet NaN.
- Otherwise, the minimum of a quiet NaN and another value is the other value.



The inactive elements of the result have arbitrary, undefined values.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.

