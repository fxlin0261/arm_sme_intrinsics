# SME / Vector arithmetic / Minimum — Part 1

## svmin[_f16]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmin%5B_f16%5D_m

### Signature (source notation)

```c
svfloat16_t svmin[_f16]_m(svbool_t pg, svfloat16_t op1, svfloat16_t op2);
```

### Description

Minimum

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Minimum

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
FMIN Ztied1.H, Pg/M, Ztied1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMIN--vectors---Floating-point-minimum--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FMIN Zresult.H, Pg/M, Zresult.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMIN--vectors---Floating-point-minimum--predicated--

### Operation

Source operation ID: `SveOperation_svmin_f16_m`

**Operation**



Return a vector in which each active element *i* contains the minimum of `op1[i]` and `op2[i]`. Take the inactive elements of the result from the corresponding elements of `op1`.



This operation treats the minimum of a NaN and anything else as a NaN.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.

## svmin[_f16]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmin%5B_f16%5D_x

### Signature (source notation)

```c
svfloat16_t svmin[_f16]_x(svbool_t pg, svfloat16_t op1, svfloat16_t op2);
```

### Description

Minimum

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Minimum

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
    "register": "Zop2.H|Ztied2.H"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.H|Ztied1.H|Ztied2.H": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
FMIN Ztied1.H, Pg/M, Ztied1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMIN--vectors---Floating-point-minimum--predicated--

When result and op2 are in the same register, this intrinsic compiles to:

```asm
FMIN Ztied2.H, Pg/M, Ztied2.H, Zop1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMIN--vectors---Floating-point-minimum--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FMIN Zresult.H, Pg/M, Zresult.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMIN--vectors---Floating-point-minimum--predicated--

### Operation

Source operation ID: `SveOperation_svmin_f16_x`

**Operation**



Return a vector in which each active element *i* contains the minimum of `op1[i]` and `op2[i]`. The inactive elements of the result have arbitrary, undefined values.



This operation treats the minimum of a NaN and anything else as a NaN.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.

## svmin[_f16]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmin%5B_f16%5D_z

### Signature (source notation)

```c
svfloat16_t svmin[_f16]_z(svbool_t pg, svfloat16_t op1, svfloat16_t op2);
```

### Description

Minimum

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Minimum

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

When result is in a different register from op2, this intrinsic can use:

```asm
MOVPRFX Zresult.H, Pg/Z, Zop1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
FMIN Zresult.H, Pg/M, Zresult.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMIN--vectors---Floating-point-minimum--predicated--

When result is in a different register from op1, this intrinsic can use:

```asm
MOVPRFX Zresult.H, Pg/Z, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
FMIN Zresult.H, Pg/M, Zresult.H, Zop1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMIN--vectors---Floating-point-minimum--predicated--

### Operation

Source operation ID: `SveOperation_svmin_f16_z`

**Operation**



Return a vector in which each active element *i* contains the minimum of `op1[i]` and `op2[i]`. Set the inactive elements of the result to zero.



This operation treats the minimum of a NaN and anything else as a NaN.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.

## svmin[_f32]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmin%5B_f32%5D_m

### Signature (source notation)

```c
svfloat32_t svmin[_f32]_m(svbool_t pg, svfloat32_t op1, svfloat32_t op2);
```

### Description

Minimum

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Minimum

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
FMIN Ztied1.S, Pg/M, Ztied1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMIN--vectors---Floating-point-minimum--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FMIN Zresult.S, Pg/M, Zresult.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMIN--vectors---Floating-point-minimum--predicated--

### Operation

Source operation ID: `SveOperation_svmin_f16_m`

**Operation**



Return a vector in which each active element *i* contains the minimum of `op1[i]` and `op2[i]`. Take the inactive elements of the result from the corresponding elements of `op1`.



This operation treats the minimum of a NaN and anything else as a NaN.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.

## svmin[_f32]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmin%5B_f32%5D_x

### Signature (source notation)

```c
svfloat32_t svmin[_f32]_x(svbool_t pg, svfloat32_t op1, svfloat32_t op2);
```

### Description

Minimum

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Minimum

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
    "register": "Zop2.S|Ztied2.S"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.S|Ztied1.S|Ztied2.S": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
FMIN Ztied1.S, Pg/M, Ztied1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMIN--vectors---Floating-point-minimum--predicated--

When result and op2 are in the same register, this intrinsic compiles to:

```asm
FMIN Ztied2.S, Pg/M, Ztied2.S, Zop1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMIN--vectors---Floating-point-minimum--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FMIN Zresult.S, Pg/M, Zresult.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMIN--vectors---Floating-point-minimum--predicated--

### Operation

Source operation ID: `SveOperation_svmin_f16_x`

**Operation**



Return a vector in which each active element *i* contains the minimum of `op1[i]` and `op2[i]`. The inactive elements of the result have arbitrary, undefined values.



This operation treats the minimum of a NaN and anything else as a NaN.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.

## svmin[_f32]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmin%5B_f32%5D_z

### Signature (source notation)

```c
svfloat32_t svmin[_f32]_z(svbool_t pg, svfloat32_t op1, svfloat32_t op2);
```

### Description

Minimum

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Minimum

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

When result is in a different register from op2, this intrinsic can use:

```asm
MOVPRFX Zresult.S, Pg/Z, Zop1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
FMIN Zresult.S, Pg/M, Zresult.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMIN--vectors---Floating-point-minimum--predicated--

When result is in a different register from op1, this intrinsic can use:

```asm
MOVPRFX Zresult.S, Pg/Z, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
FMIN Zresult.S, Pg/M, Zresult.S, Zop1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMIN--vectors---Floating-point-minimum--predicated--

### Operation

Source operation ID: `SveOperation_svmin_f16_z`

**Operation**



Return a vector in which each active element *i* contains the minimum of `op1[i]` and `op2[i]`. Set the inactive elements of the result to zero.



This operation treats the minimum of a NaN and anything else as a NaN.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.

## svmin[_f64]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmin%5B_f64%5D_m

### Signature (source notation)

```c
svfloat64_t svmin[_f64]_m(svbool_t pg, svfloat64_t op1, svfloat64_t op2);
```

### Description

Minimum

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Minimum

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
FMIN Ztied1.D, Pg/M, Ztied1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMIN--vectors---Floating-point-minimum--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FMIN Zresult.D, Pg/M, Zresult.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMIN--vectors---Floating-point-minimum--predicated--

### Operation

Source operation ID: `SveOperation_svmin_f16_m`

**Operation**



Return a vector in which each active element *i* contains the minimum of `op1[i]` and `op2[i]`. Take the inactive elements of the result from the corresponding elements of `op1`.



This operation treats the minimum of a NaN and anything else as a NaN.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.

## svmin[_f64]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmin%5B_f64%5D_x

### Signature (source notation)

```c
svfloat64_t svmin[_f64]_x(svbool_t pg, svfloat64_t op1, svfloat64_t op2);
```

### Description

Minimum

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Minimum

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
    "register": "Zop2.D|Ztied2.D"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.D|Ztied1.D|Ztied2.D": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
FMIN Ztied1.D, Pg/M, Ztied1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMIN--vectors---Floating-point-minimum--predicated--

When result and op2 are in the same register, this intrinsic compiles to:

```asm
FMIN Ztied2.D, Pg/M, Ztied2.D, Zop1.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMIN--vectors---Floating-point-minimum--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FMIN Zresult.D, Pg/M, Zresult.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMIN--vectors---Floating-point-minimum--predicated--

### Operation

Source operation ID: `SveOperation_svmin_f16_x`

**Operation**



Return a vector in which each active element *i* contains the minimum of `op1[i]` and `op2[i]`. The inactive elements of the result have arbitrary, undefined values.



This operation treats the minimum of a NaN and anything else as a NaN.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.

## svmin[_f64]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmin%5B_f64%5D_z

### Signature (source notation)

```c
svfloat64_t svmin[_f64]_z(svbool_t pg, svfloat64_t op1, svfloat64_t op2);
```

### Description

Minimum

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Minimum

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

When result is in a different register from op2, this intrinsic can use:

```asm
MOVPRFX Zresult.D, Pg/Z, Zop1.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
FMIN Zresult.D, Pg/M, Zresult.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMIN--vectors---Floating-point-minimum--predicated--

When result is in a different register from op1, this intrinsic can use:

```asm
MOVPRFX Zresult.D, Pg/Z, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
FMIN Zresult.D, Pg/M, Zresult.D, Zop1.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMIN--vectors---Floating-point-minimum--predicated--

### Operation

Source operation ID: `SveOperation_svmin_f16_z`

**Operation**



Return a vector in which each active element *i* contains the minimum of `op1[i]` and `op2[i]`. Set the inactive elements of the result to zero.



This operation treats the minimum of a NaN and anything else as a NaN.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.

## svmin[_n_f16]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmin%5B_n_f16%5D_m

### Signature (source notation)

```c
svfloat16_t svmin[_n_f16]_m(svbool_t pg, svfloat16_t op1, float16_t op2);
```

### Description

Minimum

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Minimum

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
    "register": "Ztied1.H"
  },
  "op2": {
    "register": "Zop2.H[*]"
  }
}
```

### Result mapping

```json
[
  {
    "Ztied1.H": "result"
  }
]
```

### Instruction mapping

When op2 is 0.0 or 1.0, this intrinsic can use:

```asm
FMIN Ztied1.H, Pg/M, Ztied1.H, #op2  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMIN--immediate---Floating-point-minimum-with-immediate--predicated--

The general implementation is:

```asm
FMIN Ztied1.H, Pg/M, Ztied1.H, Zop2.H  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMIN--vectors---Floating-point-minimum--predicated--

### Operation

Source operation ID: `SveOperation_svmin_n_f16_m`

**Operation**



Return a vector in which each active element *i* contains the minimum of `op1[i]` and `op2`. Take the inactive elements of the result from the corresponding elements of `op1`.



This operation treats the minimum of a NaN and anything else as a NaN.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.



**[1]** If instead `result` is in a different register from the inputs, the compiler can add a preceding [MOVPRFX (unpredicated)](https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--) instruction

## svmin[_n_f16]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmin%5B_n_f16%5D_x

### Signature (source notation)

```c
svfloat16_t svmin[_n_f16]_x(svbool_t pg, svfloat16_t op1, float16_t op2);
```

### Description

Minimum

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Minimum

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
    "register": "Zop2.H[*]|Ztied2.H[*]"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.H|Ztied1.H|Ztied2.H": "result"
  }
]
```

### Instruction mapping

When op2 is 0.0 or 1.0, this intrinsic can use:

```asm
FMIN Ztied1.H, Pg/M, Ztied1.H, #op2  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMIN--immediate---Floating-point-minimum-with-immediate--predicated--

When result and op1 are in the same register, the general implementation is:

```asm
FMIN Ztied1.H, Pg/M, Ztied1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMIN--vectors---Floating-point-minimum--predicated--

When result and op2 are in the same register, the general implementation is:

```asm
FMIN Ztied2.H, Pg/M, Ztied2.H, Zop1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMIN--vectors---Floating-point-minimum--predicated--

When result is in a different register from the inputs, the general implementation is:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FMIN Zresult.H, Pg/M, Zresult.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMIN--vectors---Floating-point-minimum--predicated--

### Operation

Source operation ID: `SveOperation_svmin_n_f16_x`

**Operation**



Return a vector in which each active element *i* contains the minimum of `op1[i]` and `op2`. The inactive elements of the result have arbitrary, undefined values.



This operation treats the minimum of a NaN and anything else as a NaN.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.



**[1]** If instead `result` is in a different register from the inputs, the compiler can add a preceding [MOVPRFX (unpredicated)](https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--) instruction

## svmin[_n_f16]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmin%5B_n_f16%5D_z

### Signature (source notation)

```c
svfloat16_t svmin[_n_f16]_z(svbool_t pg, svfloat16_t op1, float16_t op2);
```

### Description

Minimum

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Minimum

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
    "register": "Zop1.H"
  },
  "op2": {
    "register": "Zop2.H[*]"
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

When op2 is 0.0 or 1.0, this intrinsic can use:

```asm
MOVPRFX Zresult.H, Pg/Z, Zop1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
FMIN Zresult.H, Pg/M, Zresult.H, #op2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMIN--immediate---Floating-point-minimum-with-immediate--predicated--

When result is in a different register from op2, this intrinsic can use:

```asm
MOVPRFX Zresult.H, Pg/Z, Zop1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
FMIN Zresult.H, Pg/M, Zresult.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMIN--vectors---Floating-point-minimum--predicated--

When result is in a different register from op1, this intrinsic can use:

```asm
MOVPRFX Zresult.H, Pg/Z, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
FMIN Zresult.H, Pg/M, Zresult.H, Zop1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMIN--vectors---Floating-point-minimum--predicated--

### Operation

Source operation ID: `SveOperation_svmin_n_f16_z`

**Operation**



Return a vector in which each active element *i* contains the minimum of `op1[i]` and `op2`. Set the inactive elements of the result to zero.



This operation treats the minimum of a NaN and anything else as a NaN.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.

## svmin[_n_f32]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmin%5B_n_f32%5D_m

### Signature (source notation)

```c
svfloat32_t svmin[_n_f32]_m(svbool_t pg, svfloat32_t op1, float32_t op2);
```

### Description

Minimum

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Minimum

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
    "register": "Ztied1.S"
  },
  "op2": {
    "register": "Zop2.S[*]"
  }
}
```

### Result mapping

```json
[
  {
    "Ztied1.S": "result"
  }
]
```

### Instruction mapping

When op2 is 0.0 or 1.0, this intrinsic can use:

```asm
FMIN Ztied1.S, Pg/M, Ztied1.S, #op2  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMIN--immediate---Floating-point-minimum-with-immediate--predicated--

The general implementation is:

```asm
FMIN Ztied1.S, Pg/M, Ztied1.S, Zop2.S  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMIN--vectors---Floating-point-minimum--predicated--

### Operation

Source operation ID: `SveOperation_svmin_n_f16_m`

**Operation**



Return a vector in which each active element *i* contains the minimum of `op1[i]` and `op2`. Take the inactive elements of the result from the corresponding elements of `op1`.



This operation treats the minimum of a NaN and anything else as a NaN.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.



**[1]** If instead `result` is in a different register from the inputs, the compiler can add a preceding [MOVPRFX (unpredicated)](https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--) instruction

## svmin[_n_f32]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmin%5B_n_f32%5D_x

### Signature (source notation)

```c
svfloat32_t svmin[_n_f32]_x(svbool_t pg, svfloat32_t op1, float32_t op2);
```

### Description

Minimum

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Minimum

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
    "register": "Zop2.S[*]|Ztied2.S[*]"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.S|Ztied1.S|Ztied2.S": "result"
  }
]
```

### Instruction mapping

When op2 is 0.0 or 1.0, this intrinsic can use:

```asm
FMIN Ztied1.S, Pg/M, Ztied1.S, #op2  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMIN--immediate---Floating-point-minimum-with-immediate--predicated--

When result and op1 are in the same register, the general implementation is:

```asm
FMIN Ztied1.S, Pg/M, Ztied1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMIN--vectors---Floating-point-minimum--predicated--

When result and op2 are in the same register, the general implementation is:

```asm
FMIN Ztied2.S, Pg/M, Ztied2.S, Zop1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMIN--vectors---Floating-point-minimum--predicated--

When result is in a different register from the inputs, the general implementation is:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FMIN Zresult.S, Pg/M, Zresult.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMIN--vectors---Floating-point-minimum--predicated--

### Operation

Source operation ID: `SveOperation_svmin_n_f16_x`

**Operation**



Return a vector in which each active element *i* contains the minimum of `op1[i]` and `op2`. The inactive elements of the result have arbitrary, undefined values.



This operation treats the minimum of a NaN and anything else as a NaN.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.



**[1]** If instead `result` is in a different register from the inputs, the compiler can add a preceding [MOVPRFX (unpredicated)](https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--) instruction

## svmin[_n_f32]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmin%5B_n_f32%5D_z

### Signature (source notation)

```c
svfloat32_t svmin[_n_f32]_z(svbool_t pg, svfloat32_t op1, float32_t op2);
```

### Description

Minimum

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Minimum

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
    "register": "Zop1.S"
  },
  "op2": {
    "register": "Zop2.S[*]"
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

When op2 is 0.0 or 1.0, this intrinsic can use:

```asm
MOVPRFX Zresult.S, Pg/Z, Zop1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
FMIN Zresult.S, Pg/M, Zresult.S, #op2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMIN--immediate---Floating-point-minimum-with-immediate--predicated--

When result is in a different register from op2, this intrinsic can use:

```asm
MOVPRFX Zresult.S, Pg/Z, Zop1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
FMIN Zresult.S, Pg/M, Zresult.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMIN--vectors---Floating-point-minimum--predicated--

When result is in a different register from op1, this intrinsic can use:

```asm
MOVPRFX Zresult.S, Pg/Z, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
FMIN Zresult.S, Pg/M, Zresult.S, Zop1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMIN--vectors---Floating-point-minimum--predicated--

### Operation

Source operation ID: `SveOperation_svmin_n_f16_z`

**Operation**



Return a vector in which each active element *i* contains the minimum of `op1[i]` and `op2`. Set the inactive elements of the result to zero.



This operation treats the minimum of a NaN and anything else as a NaN.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.

## svmin[_n_f64]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmin%5B_n_f64%5D_m

### Signature (source notation)

```c
svfloat64_t svmin[_n_f64]_m(svbool_t pg, svfloat64_t op1, float64_t op2);
```

### Description

Minimum

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Minimum

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
    "register": "Ztied1.D"
  },
  "op2": {
    "register": "Zop2.D[*]"
  }
}
```

### Result mapping

```json
[
  {
    "Ztied1.D": "result"
  }
]
```

### Instruction mapping

When op2 is 0.0 or 1.0, this intrinsic can use:

```asm
FMIN Ztied1.D, Pg/M, Ztied1.D, #op2  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMIN--immediate---Floating-point-minimum-with-immediate--predicated--

The general implementation is:

```asm
FMIN Ztied1.D, Pg/M, Ztied1.D, Zop2.D  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMIN--vectors---Floating-point-minimum--predicated--

### Operation

Source operation ID: `SveOperation_svmin_n_f16_m`

**Operation**



Return a vector in which each active element *i* contains the minimum of `op1[i]` and `op2`. Take the inactive elements of the result from the corresponding elements of `op1`.



This operation treats the minimum of a NaN and anything else as a NaN.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.



**[1]** If instead `result` is in a different register from the inputs, the compiler can add a preceding [MOVPRFX (unpredicated)](https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--) instruction

## svmin[_n_f64]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmin%5B_n_f64%5D_x

### Signature (source notation)

```c
svfloat64_t svmin[_n_f64]_x(svbool_t pg, svfloat64_t op1, float64_t op2);
```

### Description

Minimum

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Minimum

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
    "register": "Zop2.D[*]|Ztied2.D[*]"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.D|Ztied1.D|Ztied2.D": "result"
  }
]
```

### Instruction mapping

When op2 is 0.0 or 1.0, this intrinsic can use:

```asm
FMIN Ztied1.D, Pg/M, Ztied1.D, #op2  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMIN--immediate---Floating-point-minimum-with-immediate--predicated--

When result and op1 are in the same register, the general implementation is:

```asm
FMIN Ztied1.D, Pg/M, Ztied1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMIN--vectors---Floating-point-minimum--predicated--

When result and op2 are in the same register, the general implementation is:

```asm
FMIN Ztied2.D, Pg/M, Ztied2.D, Zop1.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMIN--vectors---Floating-point-minimum--predicated--

When result is in a different register from the inputs, the general implementation is:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FMIN Zresult.D, Pg/M, Zresult.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMIN--vectors---Floating-point-minimum--predicated--

### Operation

Source operation ID: `SveOperation_svmin_n_f16_x`

**Operation**



Return a vector in which each active element *i* contains the minimum of `op1[i]` and `op2`. The inactive elements of the result have arbitrary, undefined values.



This operation treats the minimum of a NaN and anything else as a NaN.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.



**[1]** If instead `result` is in a different register from the inputs, the compiler can add a preceding [MOVPRFX (unpredicated)](https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--) instruction

## svmin[_n_f64]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmin%5B_n_f64%5D_z

### Signature (source notation)

```c
svfloat64_t svmin[_n_f64]_z(svbool_t pg, svfloat64_t op1, float64_t op2);
```

### Description

Minimum

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Minimum

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
    "register": "Zop1.D"
  },
  "op2": {
    "register": "Zop2.D[*]"
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

When op2 is 0.0 or 1.0, this intrinsic can use:

```asm
MOVPRFX Zresult.D, Pg/Z, Zop1.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
FMIN Zresult.D, Pg/M, Zresult.D, #op2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMIN--immediate---Floating-point-minimum-with-immediate--predicated--

When result is in a different register from op2, this intrinsic can use:

```asm
MOVPRFX Zresult.D, Pg/Z, Zop1.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
FMIN Zresult.D, Pg/M, Zresult.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMIN--vectors---Floating-point-minimum--predicated--

When result is in a different register from op1, this intrinsic can use:

```asm
MOVPRFX Zresult.D, Pg/Z, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
FMIN Zresult.D, Pg/M, Zresult.D, Zop1.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMIN--vectors---Floating-point-minimum--predicated--

### Operation

Source operation ID: `SveOperation_svmin_n_f16_z`

**Operation**



Return a vector in which each active element *i* contains the minimum of `op1[i]` and `op2`. Set the inactive elements of the result to zero.



This operation treats the minimum of a NaN and anything else as a NaN.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.

## svmin[_n_s16]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmin%5B_n_s16%5D_m

### Signature (source notation)

```c
svint16_t svmin[_n_s16]_m(svbool_t pg, svint16_t op1, int16_t op2);
```

### Description

Minimum

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Minimum

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
  "return_base_type": "int",
  "element_bit_size": "16",
  "value": "svint16_t"
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
    "register": "Zop2.H[*]"
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
SMIN Ztied1.H, Pg/M, Ztied1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SMIN--vectors---Signed-minimum--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SMIN Zresult.H, Pg/M, Zresult.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SMIN--vectors---Signed-minimum--predicated--

### Operation

Source operation ID: `SveOperation_svmin_n_s8_m`

**Operation**



Return a vector in which each active element *i* contains the minimum of `op1[i]` and `op2`. Take the inactive elements of the result from the corresponding elements of `op1`.

## svmin[_n_s16]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmin%5B_n_s16%5D_x

### Signature (source notation)

```c
svint16_t svmin[_n_s16]_x(svbool_t pg, svint16_t op1, int16_t op2);
```

### Description

Minimum

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Minimum

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
  "return_base_type": "int",
  "element_bit_size": "16",
  "value": "svint16_t"
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
    "register": "Zop2.H[*]|Ztied2.H[*]"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.H|Ztied1.H|Ztied2.H": "result"
  }
]
```

### Instruction mapping

When op2 is in the range [-128, 127], this intrinsic can use:

```asm
SMIN Ztied1.H, Ztied1.H, #op2  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SMIN--immediate---Signed-minimum-with-immediate--unpredicated--

When result and op1 are in the same register, the general implementation is:

```asm
SMIN Ztied1.H, Pg/M, Ztied1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SMIN--vectors---Signed-minimum--predicated--

When result and op2 are in the same register, the general implementation is:

```asm
SMIN Ztied2.H, Pg/M, Ztied2.H, Zop1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SMIN--vectors---Signed-minimum--predicated--

When result is in a different register from the inputs, the general implementation is:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SMIN Zresult.H, Pg/M, Zresult.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SMIN--vectors---Signed-minimum--predicated--

### Operation

Source operation ID: `SveOperation_svmin_n_s8_x`

**Operation**



Return a vector in which each active element *i* contains the minimum of `op1[i]` and `op2`. The inactive elements of the result have arbitrary, undefined values.



**[1]** If instead `result` is in a different register from the inputs, the compiler can add a preceding [MOVPRFX (unpredicated)](https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--) instruction

## svmin[_n_s16]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmin%5B_n_s16%5D_z

### Signature (source notation)

```c
svint16_t svmin[_n_s16]_z(svbool_t pg, svint16_t op1, int16_t op2);
```

### Description

Minimum

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Minimum

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
  "return_base_type": "int",
  "element_bit_size": "16",
  "value": "svint16_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Pg"
  },
  "op1": {
    "register": "Zop1.H"
  },
  "op2": {
    "register": "Zop2.H[*]"
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

When result is in a different register from op2, this intrinsic can use:

```asm
MOVPRFX Zresult.H, Pg/Z, Zop1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
SMIN Zresult.H, Pg/M, Zresult.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SMIN--vectors---Signed-minimum--predicated--

When result is in a different register from op1, this intrinsic can use:

```asm
MOVPRFX Zresult.H, Pg/Z, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
SMIN Zresult.H, Pg/M, Zresult.H, Zop1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SMIN--vectors---Signed-minimum--predicated--

### Operation

Source operation ID: `SveOperation_svmin_n_s8_z`

**Operation**



Return a vector in which each active element *i* contains the minimum of `op1[i]` and `op2`. Set the inactive elements of the result to zero.

## svmin[_n_s32]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmin%5B_n_s32%5D_m

### Signature (source notation)

```c
svint32_t svmin[_n_s32]_m(svbool_t pg, svint32_t op1, int32_t op2);
```

### Description

Minimum

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Minimum

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
  "return_base_type": "int",
  "element_bit_size": "32",
  "value": "svint32_t"
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
    "register": "Zop2.S[*]"
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
SMIN Ztied1.S, Pg/M, Ztied1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SMIN--vectors---Signed-minimum--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SMIN Zresult.S, Pg/M, Zresult.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SMIN--vectors---Signed-minimum--predicated--

### Operation

Source operation ID: `SveOperation_svmin_n_s8_m`

**Operation**



Return a vector in which each active element *i* contains the minimum of `op1[i]` and `op2`. Take the inactive elements of the result from the corresponding elements of `op1`.

## svmin[_n_s32]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmin%5B_n_s32%5D_x

### Signature (source notation)

```c
svint32_t svmin[_n_s32]_x(svbool_t pg, svint32_t op1, int32_t op2);
```

### Description

Minimum

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Minimum

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
  "return_base_type": "int",
  "element_bit_size": "32",
  "value": "svint32_t"
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
    "register": "Zop2.S[*]|Ztied2.S[*]"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.S|Ztied1.S|Ztied2.S": "result"
  }
]
```

### Instruction mapping

When op2 is in the range [-128, 127], this intrinsic can use:

```asm
SMIN Ztied1.S, Ztied1.S, #op2  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SMIN--immediate---Signed-minimum-with-immediate--unpredicated--

When result and op1 are in the same register, the general implementation is:

```asm
SMIN Ztied1.S, Pg/M, Ztied1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SMIN--vectors---Signed-minimum--predicated--

When result and op2 are in the same register, the general implementation is:

```asm
SMIN Ztied2.S, Pg/M, Ztied2.S, Zop1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SMIN--vectors---Signed-minimum--predicated--

When result is in a different register from the inputs, the general implementation is:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SMIN Zresult.S, Pg/M, Zresult.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SMIN--vectors---Signed-minimum--predicated--

### Operation

Source operation ID: `SveOperation_svmin_n_s8_x`

**Operation**



Return a vector in which each active element *i* contains the minimum of `op1[i]` and `op2`. The inactive elements of the result have arbitrary, undefined values.



**[1]** If instead `result` is in a different register from the inputs, the compiler can add a preceding [MOVPRFX (unpredicated)](https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--) instruction

## svmin[_n_s32]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmin%5B_n_s32%5D_z

### Signature (source notation)

```c
svint32_t svmin[_n_s32]_z(svbool_t pg, svint32_t op1, int32_t op2);
```

### Description

Minimum

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Minimum

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
  "return_base_type": "int",
  "element_bit_size": "32",
  "value": "svint32_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Pg"
  },
  "op1": {
    "register": "Zop1.S"
  },
  "op2": {
    "register": "Zop2.S[*]"
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

When result is in a different register from op2, this intrinsic can use:

```asm
MOVPRFX Zresult.S, Pg/Z, Zop1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
SMIN Zresult.S, Pg/M, Zresult.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SMIN--vectors---Signed-minimum--predicated--

When result is in a different register from op1, this intrinsic can use:

```asm
MOVPRFX Zresult.S, Pg/Z, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
SMIN Zresult.S, Pg/M, Zresult.S, Zop1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SMIN--vectors---Signed-minimum--predicated--

### Operation

Source operation ID: `SveOperation_svmin_n_s8_z`

**Operation**



Return a vector in which each active element *i* contains the minimum of `op1[i]` and `op2`. Set the inactive elements of the result to zero.

## svmin[_n_s64]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmin%5B_n_s64%5D_m

### Signature (source notation)

```c
svint64_t svmin[_n_s64]_m(svbool_t pg, svint64_t op1, int64_t op2);
```

### Description

Minimum

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Minimum

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
  "return_base_type": "int",
  "element_bit_size": "64",
  "value": "svint64_t"
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
    "register": "Zop2.D[*]"
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
SMIN Ztied1.D, Pg/M, Ztied1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SMIN--vectors---Signed-minimum--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SMIN Zresult.D, Pg/M, Zresult.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SMIN--vectors---Signed-minimum--predicated--

### Operation

Source operation ID: `SveOperation_svmin_n_s8_m`

**Operation**



Return a vector in which each active element *i* contains the minimum of `op1[i]` and `op2`. Take the inactive elements of the result from the corresponding elements of `op1`.

## svmin[_n_s64]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmin%5B_n_s64%5D_x

### Signature (source notation)

```c
svint64_t svmin[_n_s64]_x(svbool_t pg, svint64_t op1, int64_t op2);
```

### Description

Minimum

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Minimum

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
  "return_base_type": "int",
  "element_bit_size": "64",
  "value": "svint64_t"
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
    "register": "Zop2.D[*]|Ztied2.D[*]"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.D|Ztied1.D|Ztied2.D": "result"
  }
]
```

### Instruction mapping

When op2 is in the range [-128, 127], this intrinsic can use:

```asm
SMIN Ztied1.D, Ztied1.D, #op2  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SMIN--immediate---Signed-minimum-with-immediate--unpredicated--

When result and op1 are in the same register, the general implementation is:

```asm
SMIN Ztied1.D, Pg/M, Ztied1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SMIN--vectors---Signed-minimum--predicated--

When result and op2 are in the same register, the general implementation is:

```asm
SMIN Ztied2.D, Pg/M, Ztied2.D, Zop1.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SMIN--vectors---Signed-minimum--predicated--

When result is in a different register from the inputs, the general implementation is:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SMIN Zresult.D, Pg/M, Zresult.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SMIN--vectors---Signed-minimum--predicated--

### Operation

Source operation ID: `SveOperation_svmin_n_s8_x`

**Operation**



Return a vector in which each active element *i* contains the minimum of `op1[i]` and `op2`. The inactive elements of the result have arbitrary, undefined values.



**[1]** If instead `result` is in a different register from the inputs, the compiler can add a preceding [MOVPRFX (unpredicated)](https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--) instruction

## svmin[_n_s64]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmin%5B_n_s64%5D_z

### Signature (source notation)

```c
svint64_t svmin[_n_s64]_z(svbool_t pg, svint64_t op1, int64_t op2);
```

### Description

Minimum

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Minimum

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
  "return_base_type": "int",
  "element_bit_size": "64",
  "value": "svint64_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Pg"
  },
  "op1": {
    "register": "Zop1.D"
  },
  "op2": {
    "register": "Zop2.D[*]"
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

When result is in a different register from op2, this intrinsic can use:

```asm
MOVPRFX Zresult.D, Pg/Z, Zop1.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
SMIN Zresult.D, Pg/M, Zresult.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SMIN--vectors---Signed-minimum--predicated--

When result is in a different register from op1, this intrinsic can use:

```asm
MOVPRFX Zresult.D, Pg/Z, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
SMIN Zresult.D, Pg/M, Zresult.D, Zop1.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SMIN--vectors---Signed-minimum--predicated--

### Operation

Source operation ID: `SveOperation_svmin_n_s8_z`

**Operation**



Return a vector in which each active element *i* contains the minimum of `op1[i]` and `op2`. Set the inactive elements of the result to zero.

## svmin[_n_s8]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmin%5B_n_s8%5D_m

### Signature (source notation)

```c
svint8_t svmin[_n_s8]_m(svbool_t pg, svint8_t op1, int8_t op2);
```

### Description

Minimum

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Minimum

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
  "return_base_type": "int",
  "element_bit_size": "8",
  "value": "svint8_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Pg"
  },
  "op1": {
    "register": "Zop1.B|Ztied1.B"
  },
  "op2": {
    "register": "Zop2.B[*]"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.B|Ztied1.B": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
SMIN Ztied1.B, Pg/M, Ztied1.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SMIN--vectors---Signed-minimum--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SMIN Zresult.B, Pg/M, Zresult.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SMIN--vectors---Signed-minimum--predicated--

### Operation

Source operation ID: `SveOperation_svmin_n_s8_m`

**Operation**



Return a vector in which each active element *i* contains the minimum of `op1[i]` and `op2`. Take the inactive elements of the result from the corresponding elements of `op1`.

## svmin[_n_s8]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmin%5B_n_s8%5D_x

### Signature (source notation)

```c
svint8_t svmin[_n_s8]_x(svbool_t pg, svint8_t op1, int8_t op2);
```

### Description

Minimum

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Minimum

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
  "return_base_type": "int",
  "element_bit_size": "8",
  "value": "svint8_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Pg"
  },
  "op1": {
    "register": "Zop1.B|Ztied1.B"
  },
  "op2": {
    "register": "Zop2.B[*]|Ztied2.B[*]"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.B|Ztied1.B|Ztied2.B": "result"
  }
]
```

### Instruction mapping

When op2 is constant, this intrinsic can use:

```asm
SMIN Ztied1.B, Ztied1.B, #op2  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SMIN--immediate---Signed-minimum-with-immediate--unpredicated--

When result and op1 are in the same register, the general implementation is:

```asm
SMIN Ztied1.B, Pg/M, Ztied1.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SMIN--vectors---Signed-minimum--predicated--

When result and op2 are in the same register, the general implementation is:

```asm
SMIN Ztied2.B, Pg/M, Ztied2.B, Zop1.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SMIN--vectors---Signed-minimum--predicated--

When result is in a different register from the inputs, the general implementation is:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SMIN Zresult.B, Pg/M, Zresult.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SMIN--vectors---Signed-minimum--predicated--

### Operation

Source operation ID: `SveOperation_svmin_n_s8_x`

**Operation**



Return a vector in which each active element *i* contains the minimum of `op1[i]` and `op2`. The inactive elements of the result have arbitrary, undefined values.



**[1]** If instead `result` is in a different register from the inputs, the compiler can add a preceding [MOVPRFX (unpredicated)](https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--) instruction

## svmin[_n_s8]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmin%5B_n_s8%5D_z

### Signature (source notation)

```c
svint8_t svmin[_n_s8]_z(svbool_t pg, svint8_t op1, int8_t op2);
```

### Description

Minimum

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Minimum

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
  "return_base_type": "int",
  "element_bit_size": "8",
  "value": "svint8_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Pg"
  },
  "op1": {
    "register": "Zop1.B"
  },
  "op2": {
    "register": "Zop2.B[*]"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.B": "result"
  }
]
```

### Instruction mapping

When result is in a different register from op2, this intrinsic can use:

```asm
MOVPRFX Zresult.B, Pg/Z, Zop1.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
SMIN Zresult.B, Pg/M, Zresult.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SMIN--vectors---Signed-minimum--predicated--

When result is in a different register from op1, this intrinsic can use:

```asm
MOVPRFX Zresult.B, Pg/Z, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
SMIN Zresult.B, Pg/M, Zresult.B, Zop1.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SMIN--vectors---Signed-minimum--predicated--

### Operation

Source operation ID: `SveOperation_svmin_n_s8_z`

**Operation**



Return a vector in which each active element *i* contains the minimum of `op1[i]` and `op2`. Set the inactive elements of the result to zero.

## svmin[_n_u16]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmin%5B_n_u16%5D_m

### Signature (source notation)

```c
svuint16_t svmin[_n_u16]_m(svbool_t pg, svuint16_t op1, uint16_t op2);
```

### Description

Minimum

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Minimum

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
  "return_base_type": "uint",
  "element_bit_size": "16",
  "value": "svuint16_t"
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
    "register": "Zop2.H[*]"
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
UMIN Ztied1.H, Pg/M, Ztied1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UMIN--vectors---Unsigned-minimum--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
UMIN Zresult.H, Pg/M, Zresult.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UMIN--vectors---Unsigned-minimum--predicated--

### Operation

Source operation ID: `SveOperation_svmin_n_s8_m`

**Operation**



Return a vector in which each active element *i* contains the minimum of `op1[i]` and `op2`. Take the inactive elements of the result from the corresponding elements of `op1`.

## svmin[_n_u16]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmin%5B_n_u16%5D_x

### Signature (source notation)

```c
svuint16_t svmin[_n_u16]_x(svbool_t pg, svuint16_t op1, uint16_t op2);
```

### Description

Minimum

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Minimum

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
  "return_base_type": "uint",
  "element_bit_size": "16",
  "value": "svuint16_t"
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
    "register": "Zop2.H[*]|Ztied2.H[*]"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.H|Ztied1.H|Ztied2.H": "result"
  }
]
```

### Instruction mapping

When op2 is in the range [0, 255], this intrinsic can use:

```asm
UMIN Ztied1.H, Ztied1.H, #op2  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UMIN--immediate---Unsigned-minimum-with-immediate--unpredicated--

When result and op1 are in the same register, the general implementation is:

```asm
UMIN Ztied1.H, Pg/M, Ztied1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UMIN--vectors---Unsigned-minimum--predicated--

When result and op2 are in the same register, the general implementation is:

```asm
UMIN Ztied2.H, Pg/M, Ztied2.H, Zop1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UMIN--vectors---Unsigned-minimum--predicated--

When result is in a different register from the inputs, the general implementation is:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
UMIN Zresult.H, Pg/M, Zresult.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UMIN--vectors---Unsigned-minimum--predicated--

### Operation

Source operation ID: `SveOperation_svmin_n_s8_x`

**Operation**



Return a vector in which each active element *i* contains the minimum of `op1[i]` and `op2`. The inactive elements of the result have arbitrary, undefined values.



**[1]** If instead `result` is in a different register from the inputs, the compiler can add a preceding [MOVPRFX (unpredicated)](https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--) instruction

## svmin[_n_u16]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmin%5B_n_u16%5D_z

### Signature (source notation)

```c
svuint16_t svmin[_n_u16]_z(svbool_t pg, svuint16_t op1, uint16_t op2);
```

### Description

Minimum

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Minimum

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
  "return_base_type": "uint",
  "element_bit_size": "16",
  "value": "svuint16_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Pg"
  },
  "op1": {
    "register": "Zop1.H"
  },
  "op2": {
    "register": "Zop2.H[*]"
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

When result is in a different register from op2, this intrinsic can use:

```asm
MOVPRFX Zresult.H, Pg/Z, Zop1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
UMIN Zresult.H, Pg/M, Zresult.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UMIN--vectors---Unsigned-minimum--predicated--

When result is in a different register from op1, this intrinsic can use:

```asm
MOVPRFX Zresult.H, Pg/Z, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
UMIN Zresult.H, Pg/M, Zresult.H, Zop1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UMIN--vectors---Unsigned-minimum--predicated--

### Operation

Source operation ID: `SveOperation_svmin_n_s8_z`

**Operation**



Return a vector in which each active element *i* contains the minimum of `op1[i]` and `op2`. Set the inactive elements of the result to zero.

## svmin[_n_u32]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmin%5B_n_u32%5D_m

### Signature (source notation)

```c
svuint32_t svmin[_n_u32]_m(svbool_t pg, svuint32_t op1, uint32_t op2);
```

### Description

Minimum

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Minimum

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
  "return_base_type": "uint",
  "element_bit_size": "32",
  "value": "svuint32_t"
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
    "register": "Zop2.S[*]"
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
UMIN Ztied1.S, Pg/M, Ztied1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UMIN--vectors---Unsigned-minimum--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
UMIN Zresult.S, Pg/M, Zresult.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UMIN--vectors---Unsigned-minimum--predicated--

### Operation

Source operation ID: `SveOperation_svmin_n_s8_m`

**Operation**



Return a vector in which each active element *i* contains the minimum of `op1[i]` and `op2`. Take the inactive elements of the result from the corresponding elements of `op1`.

## svmin[_n_u32]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmin%5B_n_u32%5D_x

### Signature (source notation)

```c
svuint32_t svmin[_n_u32]_x(svbool_t pg, svuint32_t op1, uint32_t op2);
```

### Description

Minimum

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Minimum

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
  "return_base_type": "uint",
  "element_bit_size": "32",
  "value": "svuint32_t"
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
    "register": "Zop2.S[*]|Ztied2.S[*]"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.S|Ztied1.S|Ztied2.S": "result"
  }
]
```

### Instruction mapping

When op2 is in the range [0, 255], this intrinsic can use:

```asm
UMIN Ztied1.S, Ztied1.S, #op2  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UMIN--immediate---Unsigned-minimum-with-immediate--unpredicated--

When result and op1 are in the same register, the general implementation is:

```asm
UMIN Ztied1.S, Pg/M, Ztied1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UMIN--vectors---Unsigned-minimum--predicated--

When result and op2 are in the same register, the general implementation is:

```asm
UMIN Ztied2.S, Pg/M, Ztied2.S, Zop1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UMIN--vectors---Unsigned-minimum--predicated--

When result is in a different register from the inputs, the general implementation is:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
UMIN Zresult.S, Pg/M, Zresult.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UMIN--vectors---Unsigned-minimum--predicated--

### Operation

Source operation ID: `SveOperation_svmin_n_s8_x`

**Operation**



Return a vector in which each active element *i* contains the minimum of `op1[i]` and `op2`. The inactive elements of the result have arbitrary, undefined values.



**[1]** If instead `result` is in a different register from the inputs, the compiler can add a preceding [MOVPRFX (unpredicated)](https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--) instruction

## svmin[_n_u32]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmin%5B_n_u32%5D_z

### Signature (source notation)

```c
svuint32_t svmin[_n_u32]_z(svbool_t pg, svuint32_t op1, uint32_t op2);
```

### Description

Minimum

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Minimum

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
  "return_base_type": "uint",
  "element_bit_size": "32",
  "value": "svuint32_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Pg"
  },
  "op1": {
    "register": "Zop1.S"
  },
  "op2": {
    "register": "Zop2.S[*]"
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

When result is in a different register from op2, this intrinsic can use:

```asm
MOVPRFX Zresult.S, Pg/Z, Zop1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
UMIN Zresult.S, Pg/M, Zresult.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UMIN--vectors---Unsigned-minimum--predicated--

When result is in a different register from op1, this intrinsic can use:

```asm
MOVPRFX Zresult.S, Pg/Z, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
UMIN Zresult.S, Pg/M, Zresult.S, Zop1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UMIN--vectors---Unsigned-minimum--predicated--

### Operation

Source operation ID: `SveOperation_svmin_n_s8_z`

**Operation**



Return a vector in which each active element *i* contains the minimum of `op1[i]` and `op2`. Set the inactive elements of the result to zero.

## svmin[_n_u64]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmin%5B_n_u64%5D_m

### Signature (source notation)

```c
svuint64_t svmin[_n_u64]_m(svbool_t pg, svuint64_t op1, uint64_t op2);
```

### Description

Minimum

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Minimum

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
  "return_base_type": "uint",
  "element_bit_size": "64",
  "value": "svuint64_t"
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
    "register": "Zop2.D[*]"
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
UMIN Ztied1.D, Pg/M, Ztied1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UMIN--vectors---Unsigned-minimum--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
UMIN Zresult.D, Pg/M, Zresult.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UMIN--vectors---Unsigned-minimum--predicated--

### Operation

Source operation ID: `SveOperation_svmin_n_s8_m`

**Operation**



Return a vector in which each active element *i* contains the minimum of `op1[i]` and `op2`. Take the inactive elements of the result from the corresponding elements of `op1`.

## svmin[_n_u64]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmin%5B_n_u64%5D_x

### Signature (source notation)

```c
svuint64_t svmin[_n_u64]_x(svbool_t pg, svuint64_t op1, uint64_t op2);
```

### Description

Minimum

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Minimum

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
  "return_base_type": "uint",
  "element_bit_size": "64",
  "value": "svuint64_t"
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
    "register": "Zop2.D[*]|Ztied2.D[*]"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.D|Ztied1.D|Ztied2.D": "result"
  }
]
```

### Instruction mapping

When op2 is in the range [0, 255], this intrinsic can use:

```asm
UMIN Ztied1.D, Ztied1.D, #op2  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UMIN--immediate---Unsigned-minimum-with-immediate--unpredicated--

When result and op1 are in the same register, the general implementation is:

```asm
UMIN Ztied1.D, Pg/M, Ztied1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UMIN--vectors---Unsigned-minimum--predicated--

When result and op2 are in the same register, the general implementation is:

```asm
UMIN Ztied2.D, Pg/M, Ztied2.D, Zop1.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UMIN--vectors---Unsigned-minimum--predicated--

When result is in a different register from the inputs, the general implementation is:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
UMIN Zresult.D, Pg/M, Zresult.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UMIN--vectors---Unsigned-minimum--predicated--

### Operation

Source operation ID: `SveOperation_svmin_n_s8_x`

**Operation**



Return a vector in which each active element *i* contains the minimum of `op1[i]` and `op2`. The inactive elements of the result have arbitrary, undefined values.



**[1]** If instead `result` is in a different register from the inputs, the compiler can add a preceding [MOVPRFX (unpredicated)](https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--) instruction

## svmin[_n_u64]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmin%5B_n_u64%5D_z

### Signature (source notation)

```c
svuint64_t svmin[_n_u64]_z(svbool_t pg, svuint64_t op1, uint64_t op2);
```

### Description

Minimum

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Minimum

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
  "return_base_type": "uint",
  "element_bit_size": "64",
  "value": "svuint64_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Pg"
  },
  "op1": {
    "register": "Zop1.D"
  },
  "op2": {
    "register": "Zop2.D[*]"
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

When result is in a different register from op2, this intrinsic can use:

```asm
MOVPRFX Zresult.D, Pg/Z, Zop1.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
UMIN Zresult.D, Pg/M, Zresult.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UMIN--vectors---Unsigned-minimum--predicated--

When result is in a different register from op1, this intrinsic can use:

```asm
MOVPRFX Zresult.D, Pg/Z, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
UMIN Zresult.D, Pg/M, Zresult.D, Zop1.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UMIN--vectors---Unsigned-minimum--predicated--

### Operation

Source operation ID: `SveOperation_svmin_n_s8_z`

**Operation**



Return a vector in which each active element *i* contains the minimum of `op1[i]` and `op2`. Set the inactive elements of the result to zero.

## svmin[_n_u8]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmin%5B_n_u8%5D_m

### Signature (source notation)

```c
svuint8_t svmin[_n_u8]_m(svbool_t pg, svuint8_t op1, uint8_t op2);
```

### Description

Minimum

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Minimum

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
  "return_base_type": "uint",
  "element_bit_size": "8",
  "value": "svuint8_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Pg"
  },
  "op1": {
    "register": "Zop1.B|Ztied1.B"
  },
  "op2": {
    "register": "Zop2.B[*]"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.B|Ztied1.B": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
UMIN Ztied1.B, Pg/M, Ztied1.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UMIN--vectors---Unsigned-minimum--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
UMIN Zresult.B, Pg/M, Zresult.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UMIN--vectors---Unsigned-minimum--predicated--

### Operation

Source operation ID: `SveOperation_svmin_n_s8_m`

**Operation**



Return a vector in which each active element *i* contains the minimum of `op1[i]` and `op2`. Take the inactive elements of the result from the corresponding elements of `op1`.

## svmin[_n_u8]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmin%5B_n_u8%5D_x

### Signature (source notation)

```c
svuint8_t svmin[_n_u8]_x(svbool_t pg, svuint8_t op1, uint8_t op2);
```

### Description

Minimum

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Minimum

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
  "return_base_type": "uint",
  "element_bit_size": "8",
  "value": "svuint8_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Pg"
  },
  "op1": {
    "register": "Zop1.B|Ztied1.B"
  },
  "op2": {
    "register": "Zop2.B[*]|Ztied2.B[*]"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.B|Ztied1.B|Ztied2.B": "result"
  }
]
```

### Instruction mapping

When op2 is constant, this intrinsic can use:

```asm
UMIN Ztied1.B, Ztied1.B, #op2  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UMIN--immediate---Unsigned-minimum-with-immediate--unpredicated--

When result and op1 are in the same register, the general implementation is:

```asm
UMIN Ztied1.B, Pg/M, Ztied1.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UMIN--vectors---Unsigned-minimum--predicated--

When result and op2 are in the same register, the general implementation is:

```asm
UMIN Ztied2.B, Pg/M, Ztied2.B, Zop1.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UMIN--vectors---Unsigned-minimum--predicated--

When result is in a different register from the inputs, the general implementation is:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
UMIN Zresult.B, Pg/M, Zresult.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UMIN--vectors---Unsigned-minimum--predicated--

### Operation

Source operation ID: `SveOperation_svmin_n_s8_x`

**Operation**



Return a vector in which each active element *i* contains the minimum of `op1[i]` and `op2`. The inactive elements of the result have arbitrary, undefined values.



**[1]** If instead `result` is in a different register from the inputs, the compiler can add a preceding [MOVPRFX (unpredicated)](https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--) instruction

## svmin[_n_u8]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmin%5B_n_u8%5D_z

### Signature (source notation)

```c
svuint8_t svmin[_n_u8]_z(svbool_t pg, svuint8_t op1, uint8_t op2);
```

### Description

Minimum

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Minimum

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
  "return_base_type": "uint",
  "element_bit_size": "8",
  "value": "svuint8_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Pg"
  },
  "op1": {
    "register": "Zop1.B"
  },
  "op2": {
    "register": "Zop2.B[*]"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.B": "result"
  }
]
```

### Instruction mapping

When result is in a different register from op2, this intrinsic can use:

```asm
MOVPRFX Zresult.B, Pg/Z, Zop1.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
UMIN Zresult.B, Pg/M, Zresult.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UMIN--vectors---Unsigned-minimum--predicated--

When result is in a different register from op1, this intrinsic can use:

```asm
MOVPRFX Zresult.B, Pg/Z, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
UMIN Zresult.B, Pg/M, Zresult.B, Zop1.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UMIN--vectors---Unsigned-minimum--predicated--

### Operation

Source operation ID: `SveOperation_svmin_n_s8_z`

**Operation**



Return a vector in which each active element *i* contains the minimum of `op1[i]` and `op2`. Set the inactive elements of the result to zero.

## svmin[_s16]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmin%5B_s16%5D_m

### Signature (source notation)

```c
svint16_t svmin[_s16]_m(svbool_t pg, svint16_t op1, svint16_t op2);
```

### Description

Minimum

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Minimum

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
  "return_base_type": "int",
  "element_bit_size": "16",
  "value": "svint16_t"
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
SMIN Ztied1.H, Pg/M, Ztied1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SMIN--vectors---Signed-minimum--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SMIN Zresult.H, Pg/M, Zresult.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SMIN--vectors---Signed-minimum--predicated--

### Operation

Source operation ID: `SveOperation_svmin_s8_m`

**Operation**



Return a vector in which each active element *i* contains the minimum of `op1[i]` and `op2[i]`. Take the inactive elements of the result from the corresponding elements of `op1`.

## svmin[_s16]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmin%5B_s16%5D_x

### Signature (source notation)

```c
svint16_t svmin[_s16]_x(svbool_t pg, svint16_t op1, svint16_t op2);
```

### Description

Minimum

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Minimum

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
  "return_base_type": "int",
  "element_bit_size": "16",
  "value": "svint16_t"
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
    "register": "Zop2.H|Ztied2.H"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.H|Ztied1.H|Ztied2.H": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
SMIN Ztied1.H, Pg/M, Ztied1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SMIN--vectors---Signed-minimum--predicated--

When result and op2 are in the same register, this intrinsic compiles to:

```asm
SMIN Ztied2.H, Pg/M, Ztied2.H, Zop1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SMIN--vectors---Signed-minimum--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SMIN Zresult.H, Pg/M, Zresult.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SMIN--vectors---Signed-minimum--predicated--

### Operation

Source operation ID: `SveOperation_svmin_s8_x`

**Operation**



Return a vector in which each active element *i* contains the minimum of `op1[i]` and `op2[i]`. The inactive elements of the result have arbitrary, undefined values.

## svmin[_s16]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmin%5B_s16%5D_z

### Signature (source notation)

```c
svint16_t svmin[_s16]_z(svbool_t pg, svint16_t op1, svint16_t op2);
```

### Description

Minimum

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Minimum

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
  "return_base_type": "int",
  "element_bit_size": "16",
  "value": "svint16_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Pg"
  },
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

When result is in a different register from op2, this intrinsic can use:

```asm
MOVPRFX Zresult.H, Pg/Z, Zop1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
SMIN Zresult.H, Pg/M, Zresult.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SMIN--vectors---Signed-minimum--predicated--

When result is in a different register from op1, this intrinsic can use:

```asm
MOVPRFX Zresult.H, Pg/Z, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
SMIN Zresult.H, Pg/M, Zresult.H, Zop1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SMIN--vectors---Signed-minimum--predicated--

### Operation

Source operation ID: `SveOperation_svmin_s8_z`

**Operation**



Return a vector in which each active element *i* contains the minimum of `op1[i]` and `op2[i]`. Set the inactive elements of the result to zero.

## svmin[_s32]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmin%5B_s32%5D_m

### Signature (source notation)

```c
svint32_t svmin[_s32]_m(svbool_t pg, svint32_t op1, svint32_t op2);
```

### Description

Minimum

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Minimum

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
  "return_base_type": "int",
  "element_bit_size": "32",
  "value": "svint32_t"
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
SMIN Ztied1.S, Pg/M, Ztied1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SMIN--vectors---Signed-minimum--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SMIN Zresult.S, Pg/M, Zresult.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SMIN--vectors---Signed-minimum--predicated--

### Operation

Source operation ID: `SveOperation_svmin_s8_m`

**Operation**



Return a vector in which each active element *i* contains the minimum of `op1[i]` and `op2[i]`. Take the inactive elements of the result from the corresponding elements of `op1`.

## svmin[_s32]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmin%5B_s32%5D_x

### Signature (source notation)

```c
svint32_t svmin[_s32]_x(svbool_t pg, svint32_t op1, svint32_t op2);
```

### Description

Minimum

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Minimum

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
  "return_base_type": "int",
  "element_bit_size": "32",
  "value": "svint32_t"
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
    "register": "Zop2.S|Ztied2.S"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.S|Ztied1.S|Ztied2.S": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
SMIN Ztied1.S, Pg/M, Ztied1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SMIN--vectors---Signed-minimum--predicated--

When result and op2 are in the same register, this intrinsic compiles to:

```asm
SMIN Ztied2.S, Pg/M, Ztied2.S, Zop1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SMIN--vectors---Signed-minimum--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SMIN Zresult.S, Pg/M, Zresult.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SMIN--vectors---Signed-minimum--predicated--

### Operation

Source operation ID: `SveOperation_svmin_s8_x`

**Operation**



Return a vector in which each active element *i* contains the minimum of `op1[i]` and `op2[i]`. The inactive elements of the result have arbitrary, undefined values.

## svmin[_s32]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmin%5B_s32%5D_z

### Signature (source notation)

```c
svint32_t svmin[_s32]_z(svbool_t pg, svint32_t op1, svint32_t op2);
```

### Description

Minimum

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Minimum

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
  "return_base_type": "int",
  "element_bit_size": "32",
  "value": "svint32_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Pg"
  },
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

When result is in a different register from op2, this intrinsic can use:

```asm
MOVPRFX Zresult.S, Pg/Z, Zop1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
SMIN Zresult.S, Pg/M, Zresult.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SMIN--vectors---Signed-minimum--predicated--

When result is in a different register from op1, this intrinsic can use:

```asm
MOVPRFX Zresult.S, Pg/Z, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
SMIN Zresult.S, Pg/M, Zresult.S, Zop1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SMIN--vectors---Signed-minimum--predicated--

### Operation

Source operation ID: `SveOperation_svmin_s8_z`

**Operation**



Return a vector in which each active element *i* contains the minimum of `op1[i]` and `op2[i]`. Set the inactive elements of the result to zero.

## svmin[_s64]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmin%5B_s64%5D_m

### Signature (source notation)

```c
svint64_t svmin[_s64]_m(svbool_t pg, svint64_t op1, svint64_t op2);
```

### Description

Minimum

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Minimum

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
  "return_base_type": "int",
  "element_bit_size": "64",
  "value": "svint64_t"
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
SMIN Ztied1.D, Pg/M, Ztied1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SMIN--vectors---Signed-minimum--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SMIN Zresult.D, Pg/M, Zresult.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SMIN--vectors---Signed-minimum--predicated--

### Operation

Source operation ID: `SveOperation_svmin_s8_m`

**Operation**



Return a vector in which each active element *i* contains the minimum of `op1[i]` and `op2[i]`. Take the inactive elements of the result from the corresponding elements of `op1`.

## svmin[_s64]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmin%5B_s64%5D_x

### Signature (source notation)

```c
svint64_t svmin[_s64]_x(svbool_t pg, svint64_t op1, svint64_t op2);
```

### Description

Minimum

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Minimum

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
  "return_base_type": "int",
  "element_bit_size": "64",
  "value": "svint64_t"
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
    "register": "Zop2.D|Ztied2.D"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.D|Ztied1.D|Ztied2.D": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
SMIN Ztied1.D, Pg/M, Ztied1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SMIN--vectors---Signed-minimum--predicated--

When result and op2 are in the same register, this intrinsic compiles to:

```asm
SMIN Ztied2.D, Pg/M, Ztied2.D, Zop1.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SMIN--vectors---Signed-minimum--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SMIN Zresult.D, Pg/M, Zresult.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SMIN--vectors---Signed-minimum--predicated--

### Operation

Source operation ID: `SveOperation_svmin_s8_x`

**Operation**



Return a vector in which each active element *i* contains the minimum of `op1[i]` and `op2[i]`. The inactive elements of the result have arbitrary, undefined values.

