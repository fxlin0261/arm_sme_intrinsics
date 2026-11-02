# SME / Complex arithmetic / Complex multiply-accumulate — Part 1

## svcmla[_f16]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcmla%5B_f16%5D_m

### Signature (source notation)

```c
svfloat16_t svcmla[_f16]_m(svbool_t pg, svfloat16_t op1, svfloat16_t op2, svfloat16_t op3, uint64_t imm_rotation);
```

### Description

Complex multiply-add with rotate

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Complex arithmetic / Complex multiply-accumulate

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
  },
  "op3": {
    "register": "Zop3.H"
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
FCMLA Ztied1.H, Pg/M, Zop2.H, Zop3.H, #imm_rotation
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCMLA--vectors---Floating-point-complex-multiply-add-with-rotate--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FCMLA Zresult.H, Pg/M, Zop2.H, Zop3.H, #imm_rotation
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCMLA--vectors---Floating-point-complex-multiply-add-with-rotate--predicated--

### Operation

Source operation ID: `SveOperation_svcmla_f16_m`

**Operation**



The arguments and result contain complex values as pairs of real and imaginary components, with the real components in even-indexed elements and the imaginary components in odd-indexed elements.



If *r* is the index of a real component and *i* is the index of the corresponding imaginary component, return a vector *res* in which each active element is given by:

`imm_rotation` == 0

```text
res[r] = op1[r] + op2[r] * op3[r];
res[i] = op1[i] + op2[r] * op3[i];
```

`imm_rotation` == 90

```text
res[r] = op1[r] - op2[i] * op3[i];
res[i] = op1[i] + op2[i] * op3[r];
```

`imm_rotation` == 180

```text
res[r] = op1[r] - op2[r] * op3[r];
res[i] = op1[i] - op2[r] * op3[i];
```

`imm_rotation` == 270

```text
res[r] = op1[r] + op2[i] * op3[i];
res[i] = op1[i] - op2[i] * op3[r];
```



Thus:




- A full `op1 + op2 * op3` operation can be performed using an `imm_rotation` of 0 followed by an `imm_rotation` of 90.
- A full `op1 - op2 * op3` operation can be performed using an `imm_rotation` of 180 followed by an `imm_rotation` of 270.
- A full `op1 + conj(op2) * op3` operation can be performed using an `imm_rotation` of 0 followed by an `imm_rotation` of 270.
- A full `op1 - conj(op2) * op3` operation can be performed using an `imm_rotation` of 180 followed by an `imm_rotation` of 90.



Take the inactive elements of the result from the corresponding elements of `op1`.



The multiplication and addition are fused, with no intermediate rounding after the multiplication.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.  The following also trigger an IEEE Invalid exception:




- adding +∞ and -∞ together
- subtracting an infinity from itself

## svcmla[_f16]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcmla%5B_f16%5D_x

### Signature (source notation)

```c
svfloat16_t svcmla[_f16]_x(svbool_t pg, svfloat16_t op1, svfloat16_t op2, svfloat16_t op3, uint64_t imm_rotation);
```

### Description

Complex multiply-add with rotate

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Complex arithmetic / Complex multiply-accumulate

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
  },
  "op3": {
    "register": "Zop3.H"
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
FCMLA Ztied1.H, Pg/M, Zop2.H, Zop3.H, #imm_rotation
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCMLA--vectors---Floating-point-complex-multiply-add-with-rotate--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FCMLA Zresult.H, Pg/M, Zop2.H, Zop3.H, #imm_rotation
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCMLA--vectors---Floating-point-complex-multiply-add-with-rotate--predicated--

### Operation

Source operation ID: `SveOperation_svcmla_f16_x`

**Operation**



The arguments and result contain complex values as pairs of real and imaginary components, with the real components in even-indexed elements and the imaginary components in odd-indexed elements.



If *r* is the index of a real component and *i* is the index of the corresponding imaginary component, return a vector *res* in which each active element is given by:

`imm_rotation` == 0

```text
res[r] = op1[r] + op2[r] * op3[r];
res[i] = op1[i] + op2[r] * op3[i];
```

`imm_rotation` == 90

```text
res[r] = op1[r] - op2[i] * op3[i];
res[i] = op1[i] + op2[i] * op3[r];
```

`imm_rotation` == 180

```text
res[r] = op1[r] - op2[r] * op3[r];
res[i] = op1[i] - op2[r] * op3[i];
```

`imm_rotation` == 270

```text
res[r] = op1[r] + op2[i] * op3[i];
res[i] = op1[i] - op2[i] * op3[r];
```



Thus:




- A full `op1 + op2 * op3` operation can be performed using an `imm_rotation` of 0 followed by an `imm_rotation` of 90.
- A full `op1 - op2 * op3` operation can be performed using an `imm_rotation` of 180 followed by an `imm_rotation` of 270.
- A full `op1 + conj(op2) * op3` operation can be performed using an `imm_rotation` of 0 followed by an `imm_rotation` of 270.
- A full `op1 - conj(op2) * op3` operation can be performed using an `imm_rotation` of 180 followed by an `imm_rotation` of 90.



The inactive elements of the result have arbitrary, undefined values.



The multiplication and addition are fused, with no intermediate rounding after the multiplication.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.  The following also trigger an IEEE Invalid exception:




- adding +∞ and -∞ together
- subtracting an infinity from itself

## svcmla[_f16]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcmla%5B_f16%5D_z

### Signature (source notation)

```c
svfloat16_t svcmla[_f16]_z(svbool_t pg, svfloat16_t op1, svfloat16_t op2, svfloat16_t op3, uint64_t imm_rotation);
```

### Description

Complex multiply-add with rotate

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Complex arithmetic / Complex multiply-accumulate

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
  },
  "op3": {
    "register": "Zop3.H"
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
MOVPRFX Zresult.H, Pg/Z, Zop1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
FCMLA Zresult.H, Pg/M, Zop2.H, Zop3.H, #imm_rotation  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCMLA--vectors---Floating-point-complex-multiply-add-with-rotate--predicated--

### Operation

Source operation ID: `SveOperation_svcmla_f16_z`

**Operation**



The arguments and result contain complex values as pairs of real and imaginary components, with the real components in even-indexed elements and the imaginary components in odd-indexed elements.



If *r* is the index of a real component and *i* is the index of the corresponding imaginary component, return a vector *res* in which each active element is given by:

`imm_rotation` == 0

```text
res[r] = op1[r] + op2[r] * op3[r];
res[i] = op1[i] + op2[r] * op3[i];
```

`imm_rotation` == 90

```text
res[r] = op1[r] - op2[i] * op3[i];
res[i] = op1[i] + op2[i] * op3[r];
```

`imm_rotation` == 180

```text
res[r] = op1[r] - op2[r] * op3[r];
res[i] = op1[i] - op2[r] * op3[i];
```

`imm_rotation` == 270

```text
res[r] = op1[r] + op2[i] * op3[i];
res[i] = op1[i] - op2[i] * op3[r];
```



Thus:




- A full `op1 + op2 * op3` operation can be performed using an `imm_rotation` of 0 followed by an `imm_rotation` of 90.
- A full `op1 - op2 * op3` operation can be performed using an `imm_rotation` of 180 followed by an `imm_rotation` of 270.
- A full `op1 + conj(op2) * op3` operation can be performed using an `imm_rotation` of 0 followed by an `imm_rotation` of 270.
- A full `op1 - conj(op2) * op3` operation can be performed using an `imm_rotation` of 180 followed by an `imm_rotation` of 90.



Set the inactive elements of the result to zero.



The multiplication and addition are fused, with no intermediate rounding after the multiplication.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.  The following also trigger an IEEE Invalid exception:




- adding +∞ and -∞ together
- subtracting an infinity from itself



**[1]** Note that `result` must be in a different register from `op2` and `op3`

## svcmla[_f32]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcmla%5B_f32%5D_m

### Signature (source notation)

```c
svfloat32_t svcmla[_f32]_m(svbool_t pg, svfloat32_t op1, svfloat32_t op2, svfloat32_t op3, uint64_t imm_rotation);
```

### Description

Complex multiply-add with rotate

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Complex arithmetic / Complex multiply-accumulate

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
  },
  "op3": {
    "register": "Zop3.S"
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
FCMLA Ztied1.S, Pg/M, Zop2.S, Zop3.S, #imm_rotation
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCMLA--vectors---Floating-point-complex-multiply-add-with-rotate--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FCMLA Zresult.S, Pg/M, Zop2.S, Zop3.S, #imm_rotation
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCMLA--vectors---Floating-point-complex-multiply-add-with-rotate--predicated--

### Operation

Source operation ID: `SveOperation_svcmla_f16_m`

**Operation**



The arguments and result contain complex values as pairs of real and imaginary components, with the real components in even-indexed elements and the imaginary components in odd-indexed elements.



If *r* is the index of a real component and *i* is the index of the corresponding imaginary component, return a vector *res* in which each active element is given by:

`imm_rotation` == 0

```text
res[r] = op1[r] + op2[r] * op3[r];
res[i] = op1[i] + op2[r] * op3[i];
```

`imm_rotation` == 90

```text
res[r] = op1[r] - op2[i] * op3[i];
res[i] = op1[i] + op2[i] * op3[r];
```

`imm_rotation` == 180

```text
res[r] = op1[r] - op2[r] * op3[r];
res[i] = op1[i] - op2[r] * op3[i];
```

`imm_rotation` == 270

```text
res[r] = op1[r] + op2[i] * op3[i];
res[i] = op1[i] - op2[i] * op3[r];
```



Thus:




- A full `op1 + op2 * op3` operation can be performed using an `imm_rotation` of 0 followed by an `imm_rotation` of 90.
- A full `op1 - op2 * op3` operation can be performed using an `imm_rotation` of 180 followed by an `imm_rotation` of 270.
- A full `op1 + conj(op2) * op3` operation can be performed using an `imm_rotation` of 0 followed by an `imm_rotation` of 270.
- A full `op1 - conj(op2) * op3` operation can be performed using an `imm_rotation` of 180 followed by an `imm_rotation` of 90.



Take the inactive elements of the result from the corresponding elements of `op1`.



The multiplication and addition are fused, with no intermediate rounding after the multiplication.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.  The following also trigger an IEEE Invalid exception:




- adding +∞ and -∞ together
- subtracting an infinity from itself

## svcmla[_f32]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcmla%5B_f32%5D_x

### Signature (source notation)

```c
svfloat32_t svcmla[_f32]_x(svbool_t pg, svfloat32_t op1, svfloat32_t op2, svfloat32_t op3, uint64_t imm_rotation);
```

### Description

Complex multiply-add with rotate

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Complex arithmetic / Complex multiply-accumulate

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
  },
  "op3": {
    "register": "Zop3.S"
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
FCMLA Ztied1.S, Pg/M, Zop2.S, Zop3.S, #imm_rotation
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCMLA--vectors---Floating-point-complex-multiply-add-with-rotate--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FCMLA Zresult.S, Pg/M, Zop2.S, Zop3.S, #imm_rotation
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCMLA--vectors---Floating-point-complex-multiply-add-with-rotate--predicated--

### Operation

Source operation ID: `SveOperation_svcmla_f16_x`

**Operation**



The arguments and result contain complex values as pairs of real and imaginary components, with the real components in even-indexed elements and the imaginary components in odd-indexed elements.



If *r* is the index of a real component and *i* is the index of the corresponding imaginary component, return a vector *res* in which each active element is given by:

`imm_rotation` == 0

```text
res[r] = op1[r] + op2[r] * op3[r];
res[i] = op1[i] + op2[r] * op3[i];
```

`imm_rotation` == 90

```text
res[r] = op1[r] - op2[i] * op3[i];
res[i] = op1[i] + op2[i] * op3[r];
```

`imm_rotation` == 180

```text
res[r] = op1[r] - op2[r] * op3[r];
res[i] = op1[i] - op2[r] * op3[i];
```

`imm_rotation` == 270

```text
res[r] = op1[r] + op2[i] * op3[i];
res[i] = op1[i] - op2[i] * op3[r];
```



Thus:




- A full `op1 + op2 * op3` operation can be performed using an `imm_rotation` of 0 followed by an `imm_rotation` of 90.
- A full `op1 - op2 * op3` operation can be performed using an `imm_rotation` of 180 followed by an `imm_rotation` of 270.
- A full `op1 + conj(op2) * op3` operation can be performed using an `imm_rotation` of 0 followed by an `imm_rotation` of 270.
- A full `op1 - conj(op2) * op3` operation can be performed using an `imm_rotation` of 180 followed by an `imm_rotation` of 90.



The inactive elements of the result have arbitrary, undefined values.



The multiplication and addition are fused, with no intermediate rounding after the multiplication.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.  The following also trigger an IEEE Invalid exception:




- adding +∞ and -∞ together
- subtracting an infinity from itself

## svcmla[_f32]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcmla%5B_f32%5D_z

### Signature (source notation)

```c
svfloat32_t svcmla[_f32]_z(svbool_t pg, svfloat32_t op1, svfloat32_t op2, svfloat32_t op3, uint64_t imm_rotation);
```

### Description

Complex multiply-add with rotate

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Complex arithmetic / Complex multiply-accumulate

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
  },
  "op3": {
    "register": "Zop3.S"
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
MOVPRFX Zresult.S, Pg/Z, Zop1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
FCMLA Zresult.S, Pg/M, Zop2.S, Zop3.S, #imm_rotation  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCMLA--vectors---Floating-point-complex-multiply-add-with-rotate--predicated--

### Operation

Source operation ID: `SveOperation_svcmla_f16_z`

**Operation**



The arguments and result contain complex values as pairs of real and imaginary components, with the real components in even-indexed elements and the imaginary components in odd-indexed elements.



If *r* is the index of a real component and *i* is the index of the corresponding imaginary component, return a vector *res* in which each active element is given by:

`imm_rotation` == 0

```text
res[r] = op1[r] + op2[r] * op3[r];
res[i] = op1[i] + op2[r] * op3[i];
```

`imm_rotation` == 90

```text
res[r] = op1[r] - op2[i] * op3[i];
res[i] = op1[i] + op2[i] * op3[r];
```

`imm_rotation` == 180

```text
res[r] = op1[r] - op2[r] * op3[r];
res[i] = op1[i] - op2[r] * op3[i];
```

`imm_rotation` == 270

```text
res[r] = op1[r] + op2[i] * op3[i];
res[i] = op1[i] - op2[i] * op3[r];
```



Thus:




- A full `op1 + op2 * op3` operation can be performed using an `imm_rotation` of 0 followed by an `imm_rotation` of 90.
- A full `op1 - op2 * op3` operation can be performed using an `imm_rotation` of 180 followed by an `imm_rotation` of 270.
- A full `op1 + conj(op2) * op3` operation can be performed using an `imm_rotation` of 0 followed by an `imm_rotation` of 270.
- A full `op1 - conj(op2) * op3` operation can be performed using an `imm_rotation` of 180 followed by an `imm_rotation` of 90.



Set the inactive elements of the result to zero.



The multiplication and addition are fused, with no intermediate rounding after the multiplication.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.  The following also trigger an IEEE Invalid exception:




- adding +∞ and -∞ together
- subtracting an infinity from itself



**[1]** Note that `result` must be in a different register from `op2` and `op3`

## svcmla[_f64]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcmla%5B_f64%5D_m

### Signature (source notation)

```c
svfloat64_t svcmla[_f64]_m(svbool_t pg, svfloat64_t op1, svfloat64_t op2, svfloat64_t op3, uint64_t imm_rotation);
```

### Description

Complex multiply-add with rotate

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Complex arithmetic / Complex multiply-accumulate

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
  },
  "op3": {
    "register": "Zop3.D"
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
FCMLA Ztied1.D, Pg/M, Zop2.D, Zop3.D, #imm_rotation
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCMLA--vectors---Floating-point-complex-multiply-add-with-rotate--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FCMLA Zresult.D, Pg/M, Zop2.D, Zop3.D, #imm_rotation
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCMLA--vectors---Floating-point-complex-multiply-add-with-rotate--predicated--

### Operation

Source operation ID: `SveOperation_svcmla_f16_m`

**Operation**



The arguments and result contain complex values as pairs of real and imaginary components, with the real components in even-indexed elements and the imaginary components in odd-indexed elements.



If *r* is the index of a real component and *i* is the index of the corresponding imaginary component, return a vector *res* in which each active element is given by:

`imm_rotation` == 0

```text
res[r] = op1[r] + op2[r] * op3[r];
res[i] = op1[i] + op2[r] * op3[i];
```

`imm_rotation` == 90

```text
res[r] = op1[r] - op2[i] * op3[i];
res[i] = op1[i] + op2[i] * op3[r];
```

`imm_rotation` == 180

```text
res[r] = op1[r] - op2[r] * op3[r];
res[i] = op1[i] - op2[r] * op3[i];
```

`imm_rotation` == 270

```text
res[r] = op1[r] + op2[i] * op3[i];
res[i] = op1[i] - op2[i] * op3[r];
```



Thus:




- A full `op1 + op2 * op3` operation can be performed using an `imm_rotation` of 0 followed by an `imm_rotation` of 90.
- A full `op1 - op2 * op3` operation can be performed using an `imm_rotation` of 180 followed by an `imm_rotation` of 270.
- A full `op1 + conj(op2) * op3` operation can be performed using an `imm_rotation` of 0 followed by an `imm_rotation` of 270.
- A full `op1 - conj(op2) * op3` operation can be performed using an `imm_rotation` of 180 followed by an `imm_rotation` of 90.



Take the inactive elements of the result from the corresponding elements of `op1`.



The multiplication and addition are fused, with no intermediate rounding after the multiplication.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.  The following also trigger an IEEE Invalid exception:




- adding +∞ and -∞ together
- subtracting an infinity from itself

## svcmla[_f64]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcmla%5B_f64%5D_x

### Signature (source notation)

```c
svfloat64_t svcmla[_f64]_x(svbool_t pg, svfloat64_t op1, svfloat64_t op2, svfloat64_t op3, uint64_t imm_rotation);
```

### Description

Complex multiply-add with rotate

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Complex arithmetic / Complex multiply-accumulate

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
  },
  "op3": {
    "register": "Zop3.D"
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
FCMLA Ztied1.D, Pg/M, Zop2.D, Zop3.D, #imm_rotation
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCMLA--vectors---Floating-point-complex-multiply-add-with-rotate--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FCMLA Zresult.D, Pg/M, Zop2.D, Zop3.D, #imm_rotation
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCMLA--vectors---Floating-point-complex-multiply-add-with-rotate--predicated--

### Operation

Source operation ID: `SveOperation_svcmla_f16_x`

**Operation**



The arguments and result contain complex values as pairs of real and imaginary components, with the real components in even-indexed elements and the imaginary components in odd-indexed elements.



If *r* is the index of a real component and *i* is the index of the corresponding imaginary component, return a vector *res* in which each active element is given by:

`imm_rotation` == 0

```text
res[r] = op1[r] + op2[r] * op3[r];
res[i] = op1[i] + op2[r] * op3[i];
```

`imm_rotation` == 90

```text
res[r] = op1[r] - op2[i] * op3[i];
res[i] = op1[i] + op2[i] * op3[r];
```

`imm_rotation` == 180

```text
res[r] = op1[r] - op2[r] * op3[r];
res[i] = op1[i] - op2[r] * op3[i];
```

`imm_rotation` == 270

```text
res[r] = op1[r] + op2[i] * op3[i];
res[i] = op1[i] - op2[i] * op3[r];
```



Thus:




- A full `op1 + op2 * op3` operation can be performed using an `imm_rotation` of 0 followed by an `imm_rotation` of 90.
- A full `op1 - op2 * op3` operation can be performed using an `imm_rotation` of 180 followed by an `imm_rotation` of 270.
- A full `op1 + conj(op2) * op3` operation can be performed using an `imm_rotation` of 0 followed by an `imm_rotation` of 270.
- A full `op1 - conj(op2) * op3` operation can be performed using an `imm_rotation` of 180 followed by an `imm_rotation` of 90.



The inactive elements of the result have arbitrary, undefined values.



The multiplication and addition are fused, with no intermediate rounding after the multiplication.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.  The following also trigger an IEEE Invalid exception:




- adding +∞ and -∞ together
- subtracting an infinity from itself

## svcmla[_f64]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcmla%5B_f64%5D_z

### Signature (source notation)

```c
svfloat64_t svcmla[_f64]_z(svbool_t pg, svfloat64_t op1, svfloat64_t op2, svfloat64_t op3, uint64_t imm_rotation);
```

### Description

Complex multiply-add with rotate

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Complex arithmetic / Complex multiply-accumulate

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
  },
  "op3": {
    "register": "Zop3.D"
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
MOVPRFX Zresult.D, Pg/Z, Zop1.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
FCMLA Zresult.D, Pg/M, Zop2.D, Zop3.D, #imm_rotation  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCMLA--vectors---Floating-point-complex-multiply-add-with-rotate--predicated--

### Operation

Source operation ID: `SveOperation_svcmla_f16_z`

**Operation**



The arguments and result contain complex values as pairs of real and imaginary components, with the real components in even-indexed elements and the imaginary components in odd-indexed elements.



If *r* is the index of a real component and *i* is the index of the corresponding imaginary component, return a vector *res* in which each active element is given by:

`imm_rotation` == 0

```text
res[r] = op1[r] + op2[r] * op3[r];
res[i] = op1[i] + op2[r] * op3[i];
```

`imm_rotation` == 90

```text
res[r] = op1[r] - op2[i] * op3[i];
res[i] = op1[i] + op2[i] * op3[r];
```

`imm_rotation` == 180

```text
res[r] = op1[r] - op2[r] * op3[r];
res[i] = op1[i] - op2[r] * op3[i];
```

`imm_rotation` == 270

```text
res[r] = op1[r] + op2[i] * op3[i];
res[i] = op1[i] - op2[i] * op3[r];
```



Thus:




- A full `op1 + op2 * op3` operation can be performed using an `imm_rotation` of 0 followed by an `imm_rotation` of 90.
- A full `op1 - op2 * op3` operation can be performed using an `imm_rotation` of 180 followed by an `imm_rotation` of 270.
- A full `op1 + conj(op2) * op3` operation can be performed using an `imm_rotation` of 0 followed by an `imm_rotation` of 270.
- A full `op1 - conj(op2) * op3` operation can be performed using an `imm_rotation` of 180 followed by an `imm_rotation` of 90.



Set the inactive elements of the result to zero.



The multiplication and addition are fused, with no intermediate rounding after the multiplication.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.  The following also trigger an IEEE Invalid exception:




- adding +∞ and -∞ together
- subtracting an infinity from itself



**[1]** Note that `result` must be in a different register from `op2` and `op3`

## svcmla[_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcmla%5B_s16%5D

### Signature (source notation)

```c
svint16_t svcmla[_s16](svint16_t op1, svint16_t op2, svint16_t op3, uint64_t imm_rotation);
```

### Description

Complex multiply-add with rotate

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Complex arithmetic / Complex multiply-accumulate

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
  "op1": {
    "register": "Zop1.H|Ztied1.H"
  },
  "op2": {
    "register": "Zop2.H"
  },
  "op3": {
    "register": "Zop3.H"
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
CMLA Ztied1.H, Zop2.H, Zop3.H, #imm_rotation
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CMLA--vectors---Complex-integer-multiply-add-with-rotate-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
CMLA Zresult.H, Zop2.H, Zop3.H, #imm_rotation
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CMLA--vectors---Complex-integer-multiply-add-with-rotate-

### Operation

Source operation ID: `SveOperation_svcmla_s8`

**Operation**



The arguments and result contain complex values as pairs of real and imaginary components, with the real components in even-indexed elements and the imaginary components in odd-indexed elements.



If *r* is the index of a real component and *i* is the index of the corresponding imaginary component, return a vector *res* in which each element is given by:

`imm_rotation` == 0

```text
res[r] = op1[r] + op2[r] * op3[r];
res[i] = op1[i] + op2[r] * op3[i];
```

`imm_rotation` == 90

```text
res[r] = op1[r] - op2[i] * op3[i];
res[i] = op1[i] + op2[i] * op3[r];
```

`imm_rotation` == 180

```text
res[r] = op1[r] - op2[r] * op3[r];
res[i] = op1[i] - op2[r] * op3[i];
```

`imm_rotation` == 270

```text
res[r] = op1[r] + op2[i] * op3[i];
res[i] = op1[i] - op2[i] * op3[r];
```



Thus:




- A full `op1 + op2 * op3` operation can be performed using an `imm_rotation` of 0 followed by an `imm_rotation` of 90.
- A full `op1 - op2 * op3` operation can be performed using an `imm_rotation` of 180 followed by an `imm_rotation` of 270.
- A full `op1 + conj(op2) * op3` operation can be performed using an `imm_rotation` of 0 followed by an `imm_rotation` of 270.
- A full `op1 - conj(op2) * op3` operation can be performed using an `imm_rotation` of 180 followed by an `imm_rotation` of 90.



The operation uses modulo arithmetic.  The behavior is therefore defined for all inputs; unlike C, there is no undefined behavior for signed overflow.

## svcmla[_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcmla%5B_s32%5D

### Signature (source notation)

```c
svint32_t svcmla[_s32](svint32_t op1, svint32_t op2, svint32_t op3, uint64_t imm_rotation);
```

### Description

Complex multiply-add with rotate

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Complex arithmetic / Complex multiply-accumulate

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
  "op1": {
    "register": "Zop1.S|Ztied1.S"
  },
  "op2": {
    "register": "Zop2.S"
  },
  "op3": {
    "register": "Zop3.S"
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
CMLA Ztied1.S, Zop2.S, Zop3.S, #imm_rotation
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CMLA--vectors---Complex-integer-multiply-add-with-rotate-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
CMLA Zresult.S, Zop2.S, Zop3.S, #imm_rotation
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CMLA--vectors---Complex-integer-multiply-add-with-rotate-

### Operation

Source operation ID: `SveOperation_svcmla_s8`

**Operation**



The arguments and result contain complex values as pairs of real and imaginary components, with the real components in even-indexed elements and the imaginary components in odd-indexed elements.



If *r* is the index of a real component and *i* is the index of the corresponding imaginary component, return a vector *res* in which each element is given by:

`imm_rotation` == 0

```text
res[r] = op1[r] + op2[r] * op3[r];
res[i] = op1[i] + op2[r] * op3[i];
```

`imm_rotation` == 90

```text
res[r] = op1[r] - op2[i] * op3[i];
res[i] = op1[i] + op2[i] * op3[r];
```

`imm_rotation` == 180

```text
res[r] = op1[r] - op2[r] * op3[r];
res[i] = op1[i] - op2[r] * op3[i];
```

`imm_rotation` == 270

```text
res[r] = op1[r] + op2[i] * op3[i];
res[i] = op1[i] - op2[i] * op3[r];
```



Thus:




- A full `op1 + op2 * op3` operation can be performed using an `imm_rotation` of 0 followed by an `imm_rotation` of 90.
- A full `op1 - op2 * op3` operation can be performed using an `imm_rotation` of 180 followed by an `imm_rotation` of 270.
- A full `op1 + conj(op2) * op3` operation can be performed using an `imm_rotation` of 0 followed by an `imm_rotation` of 270.
- A full `op1 - conj(op2) * op3` operation can be performed using an `imm_rotation` of 180 followed by an `imm_rotation` of 90.



The operation uses modulo arithmetic.  The behavior is therefore defined for all inputs; unlike C, there is no undefined behavior for signed overflow.

## svcmla[_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcmla%5B_s64%5D

### Signature (source notation)

```c
svint64_t svcmla[_s64](svint64_t op1, svint64_t op2, svint64_t op3, uint64_t imm_rotation);
```

### Description

Complex multiply-add with rotate

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Complex arithmetic / Complex multiply-accumulate

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
  "op1": {
    "register": "Zop1.D|Ztied1.D"
  },
  "op2": {
    "register": "Zop2.D"
  },
  "op3": {
    "register": "Zop3.D"
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
CMLA Ztied1.D, Zop2.D, Zop3.D, #imm_rotation
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CMLA--vectors---Complex-integer-multiply-add-with-rotate-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
CMLA Zresult.D, Zop2.D, Zop3.D, #imm_rotation
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CMLA--vectors---Complex-integer-multiply-add-with-rotate-

### Operation

Source operation ID: `SveOperation_svcmla_s8`

**Operation**



The arguments and result contain complex values as pairs of real and imaginary components, with the real components in even-indexed elements and the imaginary components in odd-indexed elements.



If *r* is the index of a real component and *i* is the index of the corresponding imaginary component, return a vector *res* in which each element is given by:

`imm_rotation` == 0

```text
res[r] = op1[r] + op2[r] * op3[r];
res[i] = op1[i] + op2[r] * op3[i];
```

`imm_rotation` == 90

```text
res[r] = op1[r] - op2[i] * op3[i];
res[i] = op1[i] + op2[i] * op3[r];
```

`imm_rotation` == 180

```text
res[r] = op1[r] - op2[r] * op3[r];
res[i] = op1[i] - op2[r] * op3[i];
```

`imm_rotation` == 270

```text
res[r] = op1[r] + op2[i] * op3[i];
res[i] = op1[i] - op2[i] * op3[r];
```



Thus:




- A full `op1 + op2 * op3` operation can be performed using an `imm_rotation` of 0 followed by an `imm_rotation` of 90.
- A full `op1 - op2 * op3` operation can be performed using an `imm_rotation` of 180 followed by an `imm_rotation` of 270.
- A full `op1 + conj(op2) * op3` operation can be performed using an `imm_rotation` of 0 followed by an `imm_rotation` of 270.
- A full `op1 - conj(op2) * op3` operation can be performed using an `imm_rotation` of 180 followed by an `imm_rotation` of 90.



The operation uses modulo arithmetic.  The behavior is therefore defined for all inputs; unlike C, there is no undefined behavior for signed overflow.

## svcmla[_s8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcmla%5B_s8%5D

### Signature (source notation)

```c
svint8_t svcmla[_s8](svint8_t op1, svint8_t op2, svint8_t op3, uint64_t imm_rotation);
```

### Description

Complex multiply-add with rotate

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Complex arithmetic / Complex multiply-accumulate

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
  "op1": {
    "register": "Zop1.B|Ztied1.B"
  },
  "op2": {
    "register": "Zop2.B"
  },
  "op3": {
    "register": "Zop3.B"
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
CMLA Ztied1.B, Zop2.B, Zop3.B, #imm_rotation
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CMLA--vectors---Complex-integer-multiply-add-with-rotate-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
CMLA Zresult.B, Zop2.B, Zop3.B, #imm_rotation
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CMLA--vectors---Complex-integer-multiply-add-with-rotate-

### Operation

Source operation ID: `SveOperation_svcmla_s8`

**Operation**



The arguments and result contain complex values as pairs of real and imaginary components, with the real components in even-indexed elements and the imaginary components in odd-indexed elements.



If *r* is the index of a real component and *i* is the index of the corresponding imaginary component, return a vector *res* in which each element is given by:

`imm_rotation` == 0

```text
res[r] = op1[r] + op2[r] * op3[r];
res[i] = op1[i] + op2[r] * op3[i];
```

`imm_rotation` == 90

```text
res[r] = op1[r] - op2[i] * op3[i];
res[i] = op1[i] + op2[i] * op3[r];
```

`imm_rotation` == 180

```text
res[r] = op1[r] - op2[r] * op3[r];
res[i] = op1[i] - op2[r] * op3[i];
```

`imm_rotation` == 270

```text
res[r] = op1[r] + op2[i] * op3[i];
res[i] = op1[i] - op2[i] * op3[r];
```



Thus:




- A full `op1 + op2 * op3` operation can be performed using an `imm_rotation` of 0 followed by an `imm_rotation` of 90.
- A full `op1 - op2 * op3` operation can be performed using an `imm_rotation` of 180 followed by an `imm_rotation` of 270.
- A full `op1 + conj(op2) * op3` operation can be performed using an `imm_rotation` of 0 followed by an `imm_rotation` of 270.
- A full `op1 - conj(op2) * op3` operation can be performed using an `imm_rotation` of 180 followed by an `imm_rotation` of 90.



The operation uses modulo arithmetic.  The behavior is therefore defined for all inputs; unlike C, there is no undefined behavior for signed overflow.

## svcmla[_u16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcmla%5B_u16%5D

### Signature (source notation)

```c
svuint16_t svcmla[_u16](svuint16_t op1, svuint16_t op2, svuint16_t op3, uint64_t imm_rotation);
```

### Description

Complex multiply-add with rotate

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Complex arithmetic / Complex multiply-accumulate

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
  "op1": {
    "register": "Zop1.H|Ztied1.H"
  },
  "op2": {
    "register": "Zop2.H"
  },
  "op3": {
    "register": "Zop3.H"
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
CMLA Ztied1.H, Zop2.H, Zop3.H, #imm_rotation
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CMLA--vectors---Complex-integer-multiply-add-with-rotate-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
CMLA Zresult.H, Zop2.H, Zop3.H, #imm_rotation
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CMLA--vectors---Complex-integer-multiply-add-with-rotate-

### Operation

Source operation ID: `SveOperation_svcmla_u8`

**Operation**



The arguments and result contain complex values as pairs of real and imaginary components, with the real components in even-indexed elements and the imaginary components in odd-indexed elements.



If *r* is the index of a real component and *i* is the index of the corresponding imaginary component, return a vector *res* in which each element is given by:

`imm_rotation` == 0

```text
res[r] = op1[r] + op2[r] * op3[r];
res[i] = op1[i] + op2[r] * op3[i];
```

`imm_rotation` == 90

```text
res[r] = op1[r] - op2[i] * op3[i];
res[i] = op1[i] + op2[i] * op3[r];
```

`imm_rotation` == 180

```text
res[r] = op1[r] - op2[r] * op3[r];
res[i] = op1[i] - op2[r] * op3[i];
```

`imm_rotation` == 270

```text
res[r] = op1[r] + op2[i] * op3[i];
res[i] = op1[i] - op2[i] * op3[r];
```



Thus:




- A full `op1 + op2 * op3` operation can be performed using an `imm_rotation` of 0 followed by an `imm_rotation` of 90.
- A full `op1 - op2 * op3` operation can be performed using an `imm_rotation` of 180 followed by an `imm_rotation` of 270.
- A full `op1 + conj(op2) * op3` operation can be performed using an `imm_rotation` of 0 followed by an `imm_rotation` of 270.
- A full `op1 - conj(op2) * op3` operation can be performed using an `imm_rotation` of 180 followed by an `imm_rotation` of 90.

## svcmla[_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcmla%5B_u32%5D

### Signature (source notation)

```c
svuint32_t svcmla[_u32](svuint32_t op1, svuint32_t op2, svuint32_t op3, uint64_t imm_rotation);
```

### Description

Complex multiply-add with rotate

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Complex arithmetic / Complex multiply-accumulate

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
  "op1": {
    "register": "Zop1.S|Ztied1.S"
  },
  "op2": {
    "register": "Zop2.S"
  },
  "op3": {
    "register": "Zop3.S"
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
CMLA Ztied1.S, Zop2.S, Zop3.S, #imm_rotation
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CMLA--vectors---Complex-integer-multiply-add-with-rotate-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
CMLA Zresult.S, Zop2.S, Zop3.S, #imm_rotation
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CMLA--vectors---Complex-integer-multiply-add-with-rotate-

### Operation

Source operation ID: `SveOperation_svcmla_u8`

**Operation**



The arguments and result contain complex values as pairs of real and imaginary components, with the real components in even-indexed elements and the imaginary components in odd-indexed elements.



If *r* is the index of a real component and *i* is the index of the corresponding imaginary component, return a vector *res* in which each element is given by:

`imm_rotation` == 0

```text
res[r] = op1[r] + op2[r] * op3[r];
res[i] = op1[i] + op2[r] * op3[i];
```

`imm_rotation` == 90

```text
res[r] = op1[r] - op2[i] * op3[i];
res[i] = op1[i] + op2[i] * op3[r];
```

`imm_rotation` == 180

```text
res[r] = op1[r] - op2[r] * op3[r];
res[i] = op1[i] - op2[r] * op3[i];
```

`imm_rotation` == 270

```text
res[r] = op1[r] + op2[i] * op3[i];
res[i] = op1[i] - op2[i] * op3[r];
```



Thus:




- A full `op1 + op2 * op3` operation can be performed using an `imm_rotation` of 0 followed by an `imm_rotation` of 90.
- A full `op1 - op2 * op3` operation can be performed using an `imm_rotation` of 180 followed by an `imm_rotation` of 270.
- A full `op1 + conj(op2) * op3` operation can be performed using an `imm_rotation` of 0 followed by an `imm_rotation` of 270.
- A full `op1 - conj(op2) * op3` operation can be performed using an `imm_rotation` of 180 followed by an `imm_rotation` of 90.

## svcmla[_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcmla%5B_u64%5D

### Signature (source notation)

```c
svuint64_t svcmla[_u64](svuint64_t op1, svuint64_t op2, svuint64_t op3, uint64_t imm_rotation);
```

### Description

Complex multiply-add with rotate

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Complex arithmetic / Complex multiply-accumulate

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
  "op1": {
    "register": "Zop1.D|Ztied1.D"
  },
  "op2": {
    "register": "Zop2.D"
  },
  "op3": {
    "register": "Zop3.D"
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
CMLA Ztied1.D, Zop2.D, Zop3.D, #imm_rotation
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CMLA--vectors---Complex-integer-multiply-add-with-rotate-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
CMLA Zresult.D, Zop2.D, Zop3.D, #imm_rotation
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CMLA--vectors---Complex-integer-multiply-add-with-rotate-

### Operation

Source operation ID: `SveOperation_svcmla_u8`

**Operation**



The arguments and result contain complex values as pairs of real and imaginary components, with the real components in even-indexed elements and the imaginary components in odd-indexed elements.



If *r* is the index of a real component and *i* is the index of the corresponding imaginary component, return a vector *res* in which each element is given by:

`imm_rotation` == 0

```text
res[r] = op1[r] + op2[r] * op3[r];
res[i] = op1[i] + op2[r] * op3[i];
```

`imm_rotation` == 90

```text
res[r] = op1[r] - op2[i] * op3[i];
res[i] = op1[i] + op2[i] * op3[r];
```

`imm_rotation` == 180

```text
res[r] = op1[r] - op2[r] * op3[r];
res[i] = op1[i] - op2[r] * op3[i];
```

`imm_rotation` == 270

```text
res[r] = op1[r] + op2[i] * op3[i];
res[i] = op1[i] - op2[i] * op3[r];
```



Thus:




- A full `op1 + op2 * op3` operation can be performed using an `imm_rotation` of 0 followed by an `imm_rotation` of 90.
- A full `op1 - op2 * op3` operation can be performed using an `imm_rotation` of 180 followed by an `imm_rotation` of 270.
- A full `op1 + conj(op2) * op3` operation can be performed using an `imm_rotation` of 0 followed by an `imm_rotation` of 270.
- A full `op1 - conj(op2) * op3` operation can be performed using an `imm_rotation` of 180 followed by an `imm_rotation` of 90.

## svcmla[_u8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcmla%5B_u8%5D

### Signature (source notation)

```c
svuint8_t svcmla[_u8](svuint8_t op1, svuint8_t op2, svuint8_t op3, uint64_t imm_rotation);
```

### Description

Complex multiply-add with rotate

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Complex arithmetic / Complex multiply-accumulate

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
  "op1": {
    "register": "Zop1.B|Ztied1.B"
  },
  "op2": {
    "register": "Zop2.B"
  },
  "op3": {
    "register": "Zop3.B"
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
CMLA Ztied1.B, Zop2.B, Zop3.B, #imm_rotation
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CMLA--vectors---Complex-integer-multiply-add-with-rotate-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
CMLA Zresult.B, Zop2.B, Zop3.B, #imm_rotation
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CMLA--vectors---Complex-integer-multiply-add-with-rotate-

### Operation

Source operation ID: `SveOperation_svcmla_u8`

**Operation**



The arguments and result contain complex values as pairs of real and imaginary components, with the real components in even-indexed elements and the imaginary components in odd-indexed elements.



If *r* is the index of a real component and *i* is the index of the corresponding imaginary component, return a vector *res* in which each element is given by:

`imm_rotation` == 0

```text
res[r] = op1[r] + op2[r] * op3[r];
res[i] = op1[i] + op2[r] * op3[i];
```

`imm_rotation` == 90

```text
res[r] = op1[r] - op2[i] * op3[i];
res[i] = op1[i] + op2[i] * op3[r];
```

`imm_rotation` == 180

```text
res[r] = op1[r] - op2[r] * op3[r];
res[i] = op1[i] - op2[r] * op3[i];
```

`imm_rotation` == 270

```text
res[r] = op1[r] + op2[i] * op3[i];
res[i] = op1[i] - op2[i] * op3[r];
```



Thus:




- A full `op1 + op2 * op3` operation can be performed using an `imm_rotation` of 0 followed by an `imm_rotation` of 90.
- A full `op1 - op2 * op3` operation can be performed using an `imm_rotation` of 180 followed by an `imm_rotation` of 270.
- A full `op1 + conj(op2) * op3` operation can be performed using an `imm_rotation` of 0 followed by an `imm_rotation` of 270.
- A full `op1 - conj(op2) * op3` operation can be performed using an `imm_rotation` of 180 followed by an `imm_rotation` of 90.

## svcmla_lane[_f16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcmla_lane%5B_f16%5D

### Signature (source notation)

```c
svfloat16_t svcmla_lane[_f16](svfloat16_t op1, svfloat16_t op2, svfloat16_t op3, uint64_t imm_index, uint64_t imm_rotation);
```

### Description

Complex multiply-add with rotate

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Complex arithmetic / Complex multiply-accumulate

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
    "register": "Zop1.H|Ztied1.H"
  },
  "op2": {
    "register": "Zop2.H"
  },
  "op3": {
    "register": "Zop3.H"
  },
  "imm_index": {
    "minimum": 0,
    "maximum": 3
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
FCMLA Ztied1.H, Zop2.H, Zop3.H[imm_index], #imm_rotation
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCMLA--indexed---Floating-point-complex-multiply-add-by-indexed-values-with-rotate-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FCMLA Zresult.H, Zop2.H, Zop3.H[imm_index], #imm_rotation
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCMLA--indexed---Floating-point-complex-multiply-add-by-indexed-values-with-rotate-

### Operation

Source operation ID: `SveOperation_svcmla_lane_f16`

**Operation**



The arguments and result contain complex values as pairs of real and imaginary components, with the real components in even-indexed elements and the imaginary components in odd-indexed elements.



If *r* is the index of a real component and *i* is the index of the corresponding imaginary component, return a vector *res* in which each element is given by:

`imm_rotation` == 0

```text
res[r] = op1[r] + op2[r] * op3[base + imm_index * 2];
res[i] = op1[i] + op2[r] * op3[base + imm_index * 2 + 1];
```

`imm_rotation` == 90

```text
res[r] = op1[r] - op2[i] * op3[base + imm_index * 2 + 1];
res[i] = op1[i] + op2[i] * op3[base + imm_index * 2];
```

`imm_rotation` == 180

```text
res[r] = op1[r] - op2[r] * op3[base + imm_index * 2];
res[i] = op1[i] - op2[r] * op3[base + imm_index * 2 + 1];
```

`imm_rotation` == 270

```text
res[r] = op1[r] + op2[i] * op3[base + imm_index * 2 + 1];
res[i] = op1[i] - op2[i] * op3[base + imm_index * 2];
```



where *base* is the index of the first element in the same 128-bit quadword as *i*.



Thus:




- A full `op1 + op2 * op3` operation can be performed using an `imm_rotation` of 0 followed by an `imm_rotation` of 90.
- A full `op1 - op2 * op3` operation can be performed using an `imm_rotation` of 180 followed by an `imm_rotation` of 270.
- A full `op1 + conj(op2) * op3` operation can be performed using an `imm_rotation` of 0 followed by an `imm_rotation` of 270.
- A full `op1 - conj(op2) * op3` operation can be performed using an `imm_rotation` of 180 followed by an `imm_rotation` of 90.



The multiplication and addition are fused, with no intermediate rounding after the multiplication.



**Exceptions**



Signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.  The following also trigger an IEEE Invalid exception:




- adding +∞ and -∞ together
- subtracting an infinity from itself

## svcmla_lane[_f32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcmla_lane%5B_f32%5D

### Signature (source notation)

```c
svfloat32_t svcmla_lane[_f32](svfloat32_t op1, svfloat32_t op2, svfloat32_t op3, uint64_t imm_index, uint64_t imm_rotation);
```

### Description

Complex multiply-add with rotate

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Complex arithmetic / Complex multiply-accumulate

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
    "register": "Zop1.S|Ztied1.S"
  },
  "op2": {
    "register": "Zop2.S"
  },
  "op3": {
    "register": "Zop3.S"
  },
  "imm_index": {
    "minimum": 0,
    "maximum": 1
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
FCMLA Ztied1.S, Zop2.S, Zop3.S[imm_index], #imm_rotation
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCMLA--indexed---Floating-point-complex-multiply-add-by-indexed-values-with-rotate-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FCMLA Zresult.S, Zop2.S, Zop3.S[imm_index], #imm_rotation
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCMLA--indexed---Floating-point-complex-multiply-add-by-indexed-values-with-rotate-

### Operation

Source operation ID: `SveOperation_svcmla_lane_f16`

**Operation**



The arguments and result contain complex values as pairs of real and imaginary components, with the real components in even-indexed elements and the imaginary components in odd-indexed elements.



If *r* is the index of a real component and *i* is the index of the corresponding imaginary component, return a vector *res* in which each element is given by:

`imm_rotation` == 0

```text
res[r] = op1[r] + op2[r] * op3[base + imm_index * 2];
res[i] = op1[i] + op2[r] * op3[base + imm_index * 2 + 1];
```

`imm_rotation` == 90

```text
res[r] = op1[r] - op2[i] * op3[base + imm_index * 2 + 1];
res[i] = op1[i] + op2[i] * op3[base + imm_index * 2];
```

`imm_rotation` == 180

```text
res[r] = op1[r] - op2[r] * op3[base + imm_index * 2];
res[i] = op1[i] - op2[r] * op3[base + imm_index * 2 + 1];
```

`imm_rotation` == 270

```text
res[r] = op1[r] + op2[i] * op3[base + imm_index * 2 + 1];
res[i] = op1[i] - op2[i] * op3[base + imm_index * 2];
```



where *base* is the index of the first element in the same 128-bit quadword as *i*.



Thus:




- A full `op1 + op2 * op3` operation can be performed using an `imm_rotation` of 0 followed by an `imm_rotation` of 90.
- A full `op1 - op2 * op3` operation can be performed using an `imm_rotation` of 180 followed by an `imm_rotation` of 270.
- A full `op1 + conj(op2) * op3` operation can be performed using an `imm_rotation` of 0 followed by an `imm_rotation` of 270.
- A full `op1 - conj(op2) * op3` operation can be performed using an `imm_rotation` of 180 followed by an `imm_rotation` of 90.



The multiplication and addition are fused, with no intermediate rounding after the multiplication.



**Exceptions**



Signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.  The following also trigger an IEEE Invalid exception:




- adding +∞ and -∞ together
- subtracting an infinity from itself

## svcmla_lane[_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcmla_lane%5B_s16%5D

### Signature (source notation)

```c
svint16_t svcmla_lane[_s16](svint16_t op1, svint16_t op2, svint16_t op3, uint64_t imm_index, uint64_t imm_rotation);
```

### Description

Complex multiply-add with rotate

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Complex arithmetic / Complex multiply-accumulate

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
  "op1": {
    "register": "Zop1.H|Ztied1.H"
  },
  "op2": {
    "register": "Zop2.H"
  },
  "op3": {
    "register": "Zop3.H"
  },
  "imm_index": {
    "minimum": 0,
    "maximum": 3
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
CMLA Ztied1.H, Zop2.H, Zop3.H[imm_index], #imm_rotation
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CMLA--indexed---Complex-integer-multiply-add-with-rotate--indexed--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
CMLA Zresult.H, Zop2.H, Zop3.H[imm_index], #imm_rotation
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CMLA--indexed---Complex-integer-multiply-add-with-rotate--indexed--

### Operation

Source operation ID: `SveOperation_svcmla_lane_s16`

**Operation**



The arguments and result contain complex values as pairs of real and imaginary components, with the real components in even-indexed elements and the imaginary components in odd-indexed elements.



If *r* is the index of a real component and *i* is the index of the corresponding imaginary component, return a vector *res* in which each element is given by:

`imm_rotation` == 0

```text
res[r] = op1[r] + op2[r] * op3[base + imm_index * 2];
res[i] = op1[i] + op2[r] * op3[base + imm_index * 2 + 1];
```

`imm_rotation` == 90

```text
res[r] = op1[r] - op2[i] * op3[base + imm_index * 2 + 1];
res[i] = op1[i] + op2[i] * op3[base + imm_index * 2];
```

`imm_rotation` == 180

```text
res[r] = op1[r] - op2[r] * op3[base + imm_index * 2];
res[i] = op1[i] - op2[r] * op3[base + imm_index * 2 + 1];
```

`imm_rotation` == 270

```text
res[r] = op1[r] + op2[i] * op3[base + imm_index * 2 + 1];
res[i] = op1[i] - op2[i] * op3[base + imm_index * 2];
```



where *base* is the index of the first element in the same 128-bit quadword as *i*.



Thus:




- A full `op1 + op2 * op3` operation can be performed using an `imm_rotation` of 0 followed by an `imm_rotation` of 90.
- A full `op1 - op2 * op3` operation can be performed using an `imm_rotation` of 180 followed by an `imm_rotation` of 270.
- A full `op1 + conj(op2) * op3` operation can be performed using an `imm_rotation` of 0 followed by an `imm_rotation` of 270.
- A full `op1 - conj(op2) * op3` operation can be performed using an `imm_rotation` of 180 followed by an `imm_rotation` of 90.



The operation uses modulo arithmetic.  The behavior is therefore defined for all inputs; unlike C, there is no undefined behavior for signed overflow.

## svcmla_lane[_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcmla_lane%5B_s32%5D

### Signature (source notation)

```c
svint32_t svcmla_lane[_s32](svint32_t op1, svint32_t op2, svint32_t op3, uint64_t imm_index, uint64_t imm_rotation);
```

### Description

Complex multiply-add with rotate

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Complex arithmetic / Complex multiply-accumulate

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
  "op1": {
    "register": "Zop1.S|Ztied1.S"
  },
  "op2": {
    "register": "Zop2.S"
  },
  "op3": {
    "register": "Zop3.S"
  },
  "imm_index": {
    "minimum": 0,
    "maximum": 1
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
CMLA Ztied1.S, Zop2.S, Zop3.S[imm_index], #imm_rotation
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CMLA--indexed---Complex-integer-multiply-add-with-rotate--indexed--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
CMLA Zresult.S, Zop2.S, Zop3.S[imm_index], #imm_rotation
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CMLA--indexed---Complex-integer-multiply-add-with-rotate--indexed--

### Operation

Source operation ID: `SveOperation_svcmla_lane_s16`

**Operation**



The arguments and result contain complex values as pairs of real and imaginary components, with the real components in even-indexed elements and the imaginary components in odd-indexed elements.



If *r* is the index of a real component and *i* is the index of the corresponding imaginary component, return a vector *res* in which each element is given by:

`imm_rotation` == 0

```text
res[r] = op1[r] + op2[r] * op3[base + imm_index * 2];
res[i] = op1[i] + op2[r] * op3[base + imm_index * 2 + 1];
```

`imm_rotation` == 90

```text
res[r] = op1[r] - op2[i] * op3[base + imm_index * 2 + 1];
res[i] = op1[i] + op2[i] * op3[base + imm_index * 2];
```

`imm_rotation` == 180

```text
res[r] = op1[r] - op2[r] * op3[base + imm_index * 2];
res[i] = op1[i] - op2[r] * op3[base + imm_index * 2 + 1];
```

`imm_rotation` == 270

```text
res[r] = op1[r] + op2[i] * op3[base + imm_index * 2 + 1];
res[i] = op1[i] - op2[i] * op3[base + imm_index * 2];
```



where *base* is the index of the first element in the same 128-bit quadword as *i*.



Thus:




- A full `op1 + op2 * op3` operation can be performed using an `imm_rotation` of 0 followed by an `imm_rotation` of 90.
- A full `op1 - op2 * op3` operation can be performed using an `imm_rotation` of 180 followed by an `imm_rotation` of 270.
- A full `op1 + conj(op2) * op3` operation can be performed using an `imm_rotation` of 0 followed by an `imm_rotation` of 270.
- A full `op1 - conj(op2) * op3` operation can be performed using an `imm_rotation` of 180 followed by an `imm_rotation` of 90.



The operation uses modulo arithmetic.  The behavior is therefore defined for all inputs; unlike C, there is no undefined behavior for signed overflow.

## svcmla_lane[_u16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcmla_lane%5B_u16%5D

### Signature (source notation)

```c
svuint16_t svcmla_lane[_u16](svuint16_t op1, svuint16_t op2, svuint16_t op3, uint64_t imm_index, uint64_t imm_rotation);
```

### Description

Complex multiply-add with rotate

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Complex arithmetic / Complex multiply-accumulate

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
  "op1": {
    "register": "Zop1.H|Ztied1.H"
  },
  "op2": {
    "register": "Zop2.H"
  },
  "op3": {
    "register": "Zop3.H"
  },
  "imm_index": {
    "minimum": 0,
    "maximum": 3
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
CMLA Ztied1.H, Zop2.H, Zop3.H[imm_index], #imm_rotation
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CMLA--indexed---Complex-integer-multiply-add-with-rotate--indexed--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
CMLA Zresult.H, Zop2.H, Zop3.H[imm_index], #imm_rotation
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CMLA--indexed---Complex-integer-multiply-add-with-rotate--indexed--

### Operation

Source operation ID: `SveOperation_svcmla_lane_u16`

**Operation**



The arguments and result contain complex values as pairs of real and imaginary components, with the real components in even-indexed elements and the imaginary components in odd-indexed elements.



If *r* is the index of a real component and *i* is the index of the corresponding imaginary component, return a vector *res* in which each element is given by:

`imm_rotation` == 0

```text
res[r] = op1[r] + op2[r] * op3[base + imm_index * 2];
res[i] = op1[i] + op2[r] * op3[base + imm_index * 2 + 1];
```

`imm_rotation` == 90

```text
res[r] = op1[r] - op2[i] * op3[base + imm_index * 2 + 1];
res[i] = op1[i] + op2[i] * op3[base + imm_index * 2];
```

`imm_rotation` == 180

```text
res[r] = op1[r] - op2[r] * op3[base + imm_index * 2];
res[i] = op1[i] - op2[r] * op3[base + imm_index * 2 + 1];
```

`imm_rotation` == 270

```text
res[r] = op1[r] + op2[i] * op3[base + imm_index * 2 + 1];
res[i] = op1[i] - op2[i] * op3[base + imm_index * 2];
```



where *base* is the index of the first element in the same 128-bit quadword as *i*.



Thus:




- A full `op1 + op2 * op3` operation can be performed using an `imm_rotation` of 0 followed by an `imm_rotation` of 90.
- A full `op1 - op2 * op3` operation can be performed using an `imm_rotation` of 180 followed by an `imm_rotation` of 270.
- A full `op1 + conj(op2) * op3` operation can be performed using an `imm_rotation` of 0 followed by an `imm_rotation` of 270.
- A full `op1 - conj(op2) * op3` operation can be performed using an `imm_rotation` of 180 followed by an `imm_rotation` of 90.

## svcmla_lane[_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcmla_lane%5B_u32%5D

### Signature (source notation)

```c
svuint32_t svcmla_lane[_u32](svuint32_t op1, svuint32_t op2, svuint32_t op3, uint64_t imm_index, uint64_t imm_rotation);
```

### Description

Complex multiply-add with rotate

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Complex arithmetic / Complex multiply-accumulate

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
  "op1": {
    "register": "Zop1.S|Ztied1.S"
  },
  "op2": {
    "register": "Zop2.S"
  },
  "op3": {
    "register": "Zop3.S"
  },
  "imm_index": {
    "minimum": 0,
    "maximum": 1
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
CMLA Ztied1.S, Zop2.S, Zop3.S[imm_index], #imm_rotation
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CMLA--indexed---Complex-integer-multiply-add-with-rotate--indexed--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
CMLA Zresult.S, Zop2.S, Zop3.S[imm_index], #imm_rotation
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CMLA--indexed---Complex-integer-multiply-add-with-rotate--indexed--

### Operation

Source operation ID: `SveOperation_svcmla_lane_u16`

**Operation**



The arguments and result contain complex values as pairs of real and imaginary components, with the real components in even-indexed elements and the imaginary components in odd-indexed elements.



If *r* is the index of a real component and *i* is the index of the corresponding imaginary component, return a vector *res* in which each element is given by:

`imm_rotation` == 0

```text
res[r] = op1[r] + op2[r] * op3[base + imm_index * 2];
res[i] = op1[i] + op2[r] * op3[base + imm_index * 2 + 1];
```

`imm_rotation` == 90

```text
res[r] = op1[r] - op2[i] * op3[base + imm_index * 2 + 1];
res[i] = op1[i] + op2[i] * op3[base + imm_index * 2];
```

`imm_rotation` == 180

```text
res[r] = op1[r] - op2[r] * op3[base + imm_index * 2];
res[i] = op1[i] - op2[r] * op3[base + imm_index * 2 + 1];
```

`imm_rotation` == 270

```text
res[r] = op1[r] + op2[i] * op3[base + imm_index * 2 + 1];
res[i] = op1[i] - op2[i] * op3[base + imm_index * 2];
```



where *base* is the index of the first element in the same 128-bit quadword as *i*.



Thus:




- A full `op1 + op2 * op3` operation can be performed using an `imm_rotation` of 0 followed by an `imm_rotation` of 90.
- A full `op1 - op2 * op3` operation can be performed using an `imm_rotation` of 180 followed by an `imm_rotation` of 270.
- A full `op1 + conj(op2) * op3` operation can be performed using an `imm_rotation` of 0 followed by an `imm_rotation` of 270.
- A full `op1 - conj(op2) * op3` operation can be performed using an `imm_rotation` of 180 followed by an `imm_rotation` of 90.

