# SME / Complex arithmetic / Complex addition — Part 1

## svcadd[_f16]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcadd%5B_f16%5D_m

### Signature (source notation)

```c
svfloat16_t svcadd[_f16]_m(svbool_t pg, svfloat16_t op1, svfloat16_t op2, uint64_t imm_rotation);
```

### Description

Complex add with rotate

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Complex arithmetic / Complex addition

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
FCADD Ztied1.H, Pg/M, Ztied1.H, Zop2.H, #imm_rotation
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCADD--Floating-point-complex-add-with-rotate--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FCADD Zresult.H, Pg/M, Zresult.H, Zop2.H, #imm_rotation
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCADD--Floating-point-complex-add-with-rotate--predicated--

### Operation

Source operation ID: `SveOperation_svcadd_f16_m`

**Operation**



The arguments and result contain complex values as pairs of real and imaginary components, with the real components in even-indexed elements and the imaginary components in odd-indexed elements.



If *r* is the index of a real component and *i* is the index of the corresponding imaginary component, return a vector *res* in which each active element is given by:

`imm_rotation` == 90

```text
res[r] = op1[r] - op2[i];
res[i] = op1[i] + op2[r];
```

`imm_rotation` == 270

```text
res[r] = op1[r] + op2[i];
res[i] = op1[i] - op2[r];
```



Take the inactive elements of the result from the corresponding elements of `op1`.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.  The following also trigger an IEEE Invalid exception:




- adding +∞ and -∞ together
- subtracting an infinity from itself

## svcadd[_f16]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcadd%5B_f16%5D_x

### Signature (source notation)

```c
svfloat16_t svcadd[_f16]_x(svbool_t pg, svfloat16_t op1, svfloat16_t op2, uint64_t imm_rotation);
```

### Description

Complex add with rotate

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Complex arithmetic / Complex addition

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
FCADD Ztied1.H, Pg/M, Ztied1.H, Zop2.H, #imm_rotation
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCADD--Floating-point-complex-add-with-rotate--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FCADD Zresult.H, Pg/M, Zresult.H, Zop2.H, #imm_rotation
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCADD--Floating-point-complex-add-with-rotate--predicated--

### Operation

Source operation ID: `SveOperation_svcadd_f16_x`

**Operation**



The arguments and result contain complex values as pairs of real and imaginary components, with the real components in even-indexed elements and the imaginary components in odd-indexed elements.



If *r* is the index of a real component and *i* is the index of the corresponding imaginary component, return a vector *res* in which each active element is given by:

`imm_rotation` == 90

```text
res[r] = op1[r] - op2[i];
res[i] = op1[i] + op2[r];
```

`imm_rotation` == 270

```text
res[r] = op1[r] + op2[i];
res[i] = op1[i] - op2[r];
```



The inactive elements of the result have arbitrary, undefined values.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.  The following also trigger an IEEE Invalid exception:




- adding +∞ and -∞ together
- subtracting an infinity from itself

## svcadd[_f16]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcadd%5B_f16%5D_z

### Signature (source notation)

```c
svfloat16_t svcadd[_f16]_z(svbool_t pg, svfloat16_t op1, svfloat16_t op2, uint64_t imm_rotation);
```

### Description

Complex add with rotate

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Complex arithmetic / Complex addition

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

This intrinsic compiles to the following instructions, or functionally equivalent instructions:

```asm
MOVPRFX Zresult.H, Pg/Z, Zop1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
FCADD Zresult.H, Pg/M, Zresult.H, Zop2.H, #imm_rotation  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCADD--Floating-point-complex-add-with-rotate--predicated--

### Operation

Source operation ID: `SveOperation_svcadd_f16_z`

**Operation**



The arguments and result contain complex values as pairs of real and imaginary components, with the real components in even-indexed elements and the imaginary components in odd-indexed elements.



If *r* is the index of a real component and *i* is the index of the corresponding imaginary component, return a vector *res* in which each active element is given by:

`imm_rotation` == 90

```text
res[r] = op1[r] - op2[i];
res[i] = op1[i] + op2[r];
```

`imm_rotation` == 270

```text
res[r] = op1[r] + op2[i];
res[i] = op1[i] - op2[r];
```



Set the inactive elements of the result to zero.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.  The following also trigger an IEEE Invalid exception:




- adding +∞ and -∞ together
- subtracting an infinity from itself



**[1]** Note that `result` must be in a different register from `op2`

## svcadd[_f32]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcadd%5B_f32%5D_m

### Signature (source notation)

```c
svfloat32_t svcadd[_f32]_m(svbool_t pg, svfloat32_t op1, svfloat32_t op2, uint64_t imm_rotation);
```

### Description

Complex add with rotate

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Complex arithmetic / Complex addition

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
FCADD Ztied1.S, Pg/M, Ztied1.S, Zop2.S, #imm_rotation
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCADD--Floating-point-complex-add-with-rotate--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FCADD Zresult.S, Pg/M, Zresult.S, Zop2.S, #imm_rotation
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCADD--Floating-point-complex-add-with-rotate--predicated--

### Operation

Source operation ID: `SveOperation_svcadd_f16_m`

**Operation**



The arguments and result contain complex values as pairs of real and imaginary components, with the real components in even-indexed elements and the imaginary components in odd-indexed elements.



If *r* is the index of a real component and *i* is the index of the corresponding imaginary component, return a vector *res* in which each active element is given by:

`imm_rotation` == 90

```text
res[r] = op1[r] - op2[i];
res[i] = op1[i] + op2[r];
```

`imm_rotation` == 270

```text
res[r] = op1[r] + op2[i];
res[i] = op1[i] - op2[r];
```



Take the inactive elements of the result from the corresponding elements of `op1`.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.  The following also trigger an IEEE Invalid exception:




- adding +∞ and -∞ together
- subtracting an infinity from itself

## svcadd[_f32]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcadd%5B_f32%5D_x

### Signature (source notation)

```c
svfloat32_t svcadd[_f32]_x(svbool_t pg, svfloat32_t op1, svfloat32_t op2, uint64_t imm_rotation);
```

### Description

Complex add with rotate

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Complex arithmetic / Complex addition

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
FCADD Ztied1.S, Pg/M, Ztied1.S, Zop2.S, #imm_rotation
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCADD--Floating-point-complex-add-with-rotate--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FCADD Zresult.S, Pg/M, Zresult.S, Zop2.S, #imm_rotation
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCADD--Floating-point-complex-add-with-rotate--predicated--

### Operation

Source operation ID: `SveOperation_svcadd_f16_x`

**Operation**



The arguments and result contain complex values as pairs of real and imaginary components, with the real components in even-indexed elements and the imaginary components in odd-indexed elements.



If *r* is the index of a real component and *i* is the index of the corresponding imaginary component, return a vector *res* in which each active element is given by:

`imm_rotation` == 90

```text
res[r] = op1[r] - op2[i];
res[i] = op1[i] + op2[r];
```

`imm_rotation` == 270

```text
res[r] = op1[r] + op2[i];
res[i] = op1[i] - op2[r];
```



The inactive elements of the result have arbitrary, undefined values.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.  The following also trigger an IEEE Invalid exception:




- adding +∞ and -∞ together
- subtracting an infinity from itself

## svcadd[_f32]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcadd%5B_f32%5D_z

### Signature (source notation)

```c
svfloat32_t svcadd[_f32]_z(svbool_t pg, svfloat32_t op1, svfloat32_t op2, uint64_t imm_rotation);
```

### Description

Complex add with rotate

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Complex arithmetic / Complex addition

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

This intrinsic compiles to the following instructions, or functionally equivalent instructions:

```asm
MOVPRFX Zresult.S, Pg/Z, Zop1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
FCADD Zresult.S, Pg/M, Zresult.S, Zop2.S, #imm_rotation  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCADD--Floating-point-complex-add-with-rotate--predicated--

### Operation

Source operation ID: `SveOperation_svcadd_f16_z`

**Operation**



The arguments and result contain complex values as pairs of real and imaginary components, with the real components in even-indexed elements and the imaginary components in odd-indexed elements.



If *r* is the index of a real component and *i* is the index of the corresponding imaginary component, return a vector *res* in which each active element is given by:

`imm_rotation` == 90

```text
res[r] = op1[r] - op2[i];
res[i] = op1[i] + op2[r];
```

`imm_rotation` == 270

```text
res[r] = op1[r] + op2[i];
res[i] = op1[i] - op2[r];
```



Set the inactive elements of the result to zero.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.  The following also trigger an IEEE Invalid exception:




- adding +∞ and -∞ together
- subtracting an infinity from itself



**[1]** Note that `result` must be in a different register from `op2`

## svcadd[_f64]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcadd%5B_f64%5D_m

### Signature (source notation)

```c
svfloat64_t svcadd[_f64]_m(svbool_t pg, svfloat64_t op1, svfloat64_t op2, uint64_t imm_rotation);
```

### Description

Complex add with rotate

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Complex arithmetic / Complex addition

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
FCADD Ztied1.D, Pg/M, Ztied1.D, Zop2.D, #imm_rotation
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCADD--Floating-point-complex-add-with-rotate--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FCADD Zresult.D, Pg/M, Zresult.D, Zop2.D, #imm_rotation
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCADD--Floating-point-complex-add-with-rotate--predicated--

### Operation

Source operation ID: `SveOperation_svcadd_f16_m`

**Operation**



The arguments and result contain complex values as pairs of real and imaginary components, with the real components in even-indexed elements and the imaginary components in odd-indexed elements.



If *r* is the index of a real component and *i* is the index of the corresponding imaginary component, return a vector *res* in which each active element is given by:

`imm_rotation` == 90

```text
res[r] = op1[r] - op2[i];
res[i] = op1[i] + op2[r];
```

`imm_rotation` == 270

```text
res[r] = op1[r] + op2[i];
res[i] = op1[i] - op2[r];
```



Take the inactive elements of the result from the corresponding elements of `op1`.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.  The following also trigger an IEEE Invalid exception:




- adding +∞ and -∞ together
- subtracting an infinity from itself

## svcadd[_f64]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcadd%5B_f64%5D_x

### Signature (source notation)

```c
svfloat64_t svcadd[_f64]_x(svbool_t pg, svfloat64_t op1, svfloat64_t op2, uint64_t imm_rotation);
```

### Description

Complex add with rotate

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Complex arithmetic / Complex addition

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
FCADD Ztied1.D, Pg/M, Ztied1.D, Zop2.D, #imm_rotation
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCADD--Floating-point-complex-add-with-rotate--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FCADD Zresult.D, Pg/M, Zresult.D, Zop2.D, #imm_rotation
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCADD--Floating-point-complex-add-with-rotate--predicated--

### Operation

Source operation ID: `SveOperation_svcadd_f16_x`

**Operation**



The arguments and result contain complex values as pairs of real and imaginary components, with the real components in even-indexed elements and the imaginary components in odd-indexed elements.



If *r* is the index of a real component and *i* is the index of the corresponding imaginary component, return a vector *res* in which each active element is given by:

`imm_rotation` == 90

```text
res[r] = op1[r] - op2[i];
res[i] = op1[i] + op2[r];
```

`imm_rotation` == 270

```text
res[r] = op1[r] + op2[i];
res[i] = op1[i] - op2[r];
```



The inactive elements of the result have arbitrary, undefined values.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.  The following also trigger an IEEE Invalid exception:




- adding +∞ and -∞ together
- subtracting an infinity from itself

## svcadd[_f64]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcadd%5B_f64%5D_z

### Signature (source notation)

```c
svfloat64_t svcadd[_f64]_z(svbool_t pg, svfloat64_t op1, svfloat64_t op2, uint64_t imm_rotation);
```

### Description

Complex add with rotate

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Complex arithmetic / Complex addition

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

This intrinsic compiles to the following instructions, or functionally equivalent instructions:

```asm
MOVPRFX Zresult.D, Pg/Z, Zop1.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
FCADD Zresult.D, Pg/M, Zresult.D, Zop2.D, #imm_rotation  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCADD--Floating-point-complex-add-with-rotate--predicated--

### Operation

Source operation ID: `SveOperation_svcadd_f16_z`

**Operation**



The arguments and result contain complex values as pairs of real and imaginary components, with the real components in even-indexed elements and the imaginary components in odd-indexed elements.



If *r* is the index of a real component and *i* is the index of the corresponding imaginary component, return a vector *res* in which each active element is given by:

`imm_rotation` == 90

```text
res[r] = op1[r] - op2[i];
res[i] = op1[i] + op2[r];
```

`imm_rotation` == 270

```text
res[r] = op1[r] + op2[i];
res[i] = op1[i] - op2[r];
```



Set the inactive elements of the result to zero.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.  The following also trigger an IEEE Invalid exception:




- adding +∞ and -∞ together
- subtracting an infinity from itself



**[1]** Note that `result` must be in a different register from `op2`

## svcadd[_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcadd%5B_s16%5D

### Signature (source notation)

```c
svint16_t svcadd[_s16](svint16_t op1, svint16_t op2, uint64_t imm_rotation);
```

### Description

Complex add with rotate

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Complex arithmetic / Complex addition

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
CADD Ztied1.H, Ztied1.H, Zop2.H, #imm_rotation
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CADD--Complex-integer-add-with-rotate-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
CADD Zresult.H, Zresult.H, Zop2.H, #imm_rotation
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CADD--Complex-integer-add-with-rotate-

### Operation

Source operation ID: `SveOperation_svcadd_s8`

**Operation**



The arguments and result contain complex values as pairs of real and imaginary components, with the real components in even-indexed elements and the imaginary components in odd-indexed elements.



If *r* is the index of a real component and *i* is the index of the corresponding imaginary component, return a vector *res* in which each element is given by:

`imm_rotation` == 90

```text
res[r] = op1[r] - op2[i];
res[i] = op1[i] + op2[r];
```

`imm_rotation` == 270

```text
res[r] = op1[r] + op2[i];
res[i] = op1[i] - op2[r];
```



The operation uses modulo arithmetic.  The behavior is therefore defined for all inputs; unlike C, there is no undefined behavior for signed overflow.

## svcadd[_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcadd%5B_s32%5D

### Signature (source notation)

```c
svint32_t svcadd[_s32](svint32_t op1, svint32_t op2, uint64_t imm_rotation);
```

### Description

Complex add with rotate

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Complex arithmetic / Complex addition

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
CADD Ztied1.S, Ztied1.S, Zop2.S, #imm_rotation
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CADD--Complex-integer-add-with-rotate-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
CADD Zresult.S, Zresult.S, Zop2.S, #imm_rotation
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CADD--Complex-integer-add-with-rotate-

### Operation

Source operation ID: `SveOperation_svcadd_s8`

**Operation**



The arguments and result contain complex values as pairs of real and imaginary components, with the real components in even-indexed elements and the imaginary components in odd-indexed elements.



If *r* is the index of a real component and *i* is the index of the corresponding imaginary component, return a vector *res* in which each element is given by:

`imm_rotation` == 90

```text
res[r] = op1[r] - op2[i];
res[i] = op1[i] + op2[r];
```

`imm_rotation` == 270

```text
res[r] = op1[r] + op2[i];
res[i] = op1[i] - op2[r];
```



The operation uses modulo arithmetic.  The behavior is therefore defined for all inputs; unlike C, there is no undefined behavior for signed overflow.

## svcadd[_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcadd%5B_s64%5D

### Signature (source notation)

```c
svint64_t svcadd[_s64](svint64_t op1, svint64_t op2, uint64_t imm_rotation);
```

### Description

Complex add with rotate

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Complex arithmetic / Complex addition

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
CADD Ztied1.D, Ztied1.D, Zop2.D, #imm_rotation
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CADD--Complex-integer-add-with-rotate-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
CADD Zresult.D, Zresult.D, Zop2.D, #imm_rotation
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CADD--Complex-integer-add-with-rotate-

### Operation

Source operation ID: `SveOperation_svcadd_s8`

**Operation**



The arguments and result contain complex values as pairs of real and imaginary components, with the real components in even-indexed elements and the imaginary components in odd-indexed elements.



If *r* is the index of a real component and *i* is the index of the corresponding imaginary component, return a vector *res* in which each element is given by:

`imm_rotation` == 90

```text
res[r] = op1[r] - op2[i];
res[i] = op1[i] + op2[r];
```

`imm_rotation` == 270

```text
res[r] = op1[r] + op2[i];
res[i] = op1[i] - op2[r];
```



The operation uses modulo arithmetic.  The behavior is therefore defined for all inputs; unlike C, there is no undefined behavior for signed overflow.

## svcadd[_s8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcadd%5B_s8%5D

### Signature (source notation)

```c
svint8_t svcadd[_s8](svint8_t op1, svint8_t op2, uint64_t imm_rotation);
```

### Description

Complex add with rotate

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Complex arithmetic / Complex addition

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
CADD Ztied1.B, Ztied1.B, Zop2.B, #imm_rotation
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CADD--Complex-integer-add-with-rotate-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
CADD Zresult.B, Zresult.B, Zop2.B, #imm_rotation
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CADD--Complex-integer-add-with-rotate-

### Operation

Source operation ID: `SveOperation_svcadd_s8`

**Operation**



The arguments and result contain complex values as pairs of real and imaginary components, with the real components in even-indexed elements and the imaginary components in odd-indexed elements.



If *r* is the index of a real component and *i* is the index of the corresponding imaginary component, return a vector *res* in which each element is given by:

`imm_rotation` == 90

```text
res[r] = op1[r] - op2[i];
res[i] = op1[i] + op2[r];
```

`imm_rotation` == 270

```text
res[r] = op1[r] + op2[i];
res[i] = op1[i] - op2[r];
```



The operation uses modulo arithmetic.  The behavior is therefore defined for all inputs; unlike C, there is no undefined behavior for signed overflow.

## svcadd[_u16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcadd%5B_u16%5D

### Signature (source notation)

```c
svuint16_t svcadd[_u16](svuint16_t op1, svuint16_t op2, uint64_t imm_rotation);
```

### Description

Complex add with rotate

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Complex arithmetic / Complex addition

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
CADD Ztied1.H, Ztied1.H, Zop2.H, #imm_rotation
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CADD--Complex-integer-add-with-rotate-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
CADD Zresult.H, Zresult.H, Zop2.H, #imm_rotation
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CADD--Complex-integer-add-with-rotate-

### Operation

Source operation ID: `SveOperation_svcadd_u8`

**Operation**



The arguments and result contain complex values as pairs of real and imaginary components, with the real components in even-indexed elements and the imaginary components in odd-indexed elements.



If *r* is the index of a real component and *i* is the index of the corresponding imaginary component, return a vector *res* in which each element is given by:

`imm_rotation` == 90

```text
res[r] = op1[r] - op2[i];
res[i] = op1[i] + op2[r];
```

`imm_rotation` == 270

```text
res[r] = op1[r] + op2[i];
res[i] = op1[i] - op2[r];
```

## svcadd[_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcadd%5B_u32%5D

### Signature (source notation)

```c
svuint32_t svcadd[_u32](svuint32_t op1, svuint32_t op2, uint64_t imm_rotation);
```

### Description

Complex add with rotate

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Complex arithmetic / Complex addition

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
CADD Ztied1.S, Ztied1.S, Zop2.S, #imm_rotation
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CADD--Complex-integer-add-with-rotate-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
CADD Zresult.S, Zresult.S, Zop2.S, #imm_rotation
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CADD--Complex-integer-add-with-rotate-

### Operation

Source operation ID: `SveOperation_svcadd_u8`

**Operation**



The arguments and result contain complex values as pairs of real and imaginary components, with the real components in even-indexed elements and the imaginary components in odd-indexed elements.



If *r* is the index of a real component and *i* is the index of the corresponding imaginary component, return a vector *res* in which each element is given by:

`imm_rotation` == 90

```text
res[r] = op1[r] - op2[i];
res[i] = op1[i] + op2[r];
```

`imm_rotation` == 270

```text
res[r] = op1[r] + op2[i];
res[i] = op1[i] - op2[r];
```

## svcadd[_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcadd%5B_u64%5D

### Signature (source notation)

```c
svuint64_t svcadd[_u64](svuint64_t op1, svuint64_t op2, uint64_t imm_rotation);
```

### Description

Complex add with rotate

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Complex arithmetic / Complex addition

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
CADD Ztied1.D, Ztied1.D, Zop2.D, #imm_rotation
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CADD--Complex-integer-add-with-rotate-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
CADD Zresult.D, Zresult.D, Zop2.D, #imm_rotation
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CADD--Complex-integer-add-with-rotate-

### Operation

Source operation ID: `SveOperation_svcadd_u8`

**Operation**



The arguments and result contain complex values as pairs of real and imaginary components, with the real components in even-indexed elements and the imaginary components in odd-indexed elements.



If *r* is the index of a real component and *i* is the index of the corresponding imaginary component, return a vector *res* in which each element is given by:

`imm_rotation` == 90

```text
res[r] = op1[r] - op2[i];
res[i] = op1[i] + op2[r];
```

`imm_rotation` == 270

```text
res[r] = op1[r] + op2[i];
res[i] = op1[i] - op2[r];
```

## svcadd[_u8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcadd%5B_u8%5D

### Signature (source notation)

```c
svuint8_t svcadd[_u8](svuint8_t op1, svuint8_t op2, uint64_t imm_rotation);
```

### Description

Complex add with rotate

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Complex arithmetic / Complex addition

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
CADD Ztied1.B, Ztied1.B, Zop2.B, #imm_rotation
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CADD--Complex-integer-add-with-rotate-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
CADD Zresult.B, Zresult.B, Zop2.B, #imm_rotation
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CADD--Complex-integer-add-with-rotate-

### Operation

Source operation ID: `SveOperation_svcadd_u8`

**Operation**



The arguments and result contain complex values as pairs of real and imaginary components, with the real components in even-indexed elements and the imaginary components in odd-indexed elements.



If *r* is the index of a real component and *i* is the index of the corresponding imaginary component, return a vector *res* in which each element is given by:

`imm_rotation` == 90

```text
res[r] = op1[r] - op2[i];
res[i] = op1[i] + op2[r];
```

`imm_rotation` == 270

```text
res[r] = op1[r] + op2[i];
res[i] = op1[i] - op2[r];
```

