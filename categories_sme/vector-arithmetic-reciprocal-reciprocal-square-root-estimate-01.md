# SME / Vector arithmetic / Reciprocal / Reciprocal square-root estimate — Part 1

## svrsqrte[_f16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrsqrte%5B_f16%5D

### Signature (source notation)

```c
svfloat16_t svrsqrte[_f16](svfloat16_t op);
```

### Description

Reciprocal square root estimate

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Reciprocal / Reciprocal square-root estimate

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

This intrinsic compiles to the following instruction:

```asm
FRSQRTE Zresult.H, Zop.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FRSQRTE--Floating-point-reciprocal-square-root-estimate--unpredicated--

### Operation

Source operation ID: `SveOperation_svrsqrte_f16`

**Operation**



Return a vector in which element *i* contains an estimate of 1/√`op[i]`, calculated as for [FRSQRTE](https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/FRSQRTE--Floating-point-reciprocal-square-root-estimate--unpredicated--).



**Exceptions**



Signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.  Zeros trigger an IEEE DivideByZero exception and negative values trigger an IEEE Invalid exception.

## svrsqrte[_f32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrsqrte%5B_f32%5D

### Signature (source notation)

```c
svfloat32_t svrsqrte[_f32](svfloat32_t op);
```

### Description

Reciprocal square root estimate

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Reciprocal / Reciprocal square-root estimate

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

This intrinsic compiles to the following instruction:

```asm
FRSQRTE Zresult.S, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FRSQRTE--Floating-point-reciprocal-square-root-estimate--unpredicated--

### Operation

Source operation ID: `SveOperation_svrsqrte_f16`

**Operation**



Return a vector in which element *i* contains an estimate of 1/√`op[i]`, calculated as for [FRSQRTE](https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/FRSQRTE--Floating-point-reciprocal-square-root-estimate--unpredicated--).



**Exceptions**



Signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.  Zeros trigger an IEEE DivideByZero exception and negative values trigger an IEEE Invalid exception.

## svrsqrte[_f64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrsqrte%5B_f64%5D

### Signature (source notation)

```c
svfloat64_t svrsqrte[_f64](svfloat64_t op);
```

### Description

Reciprocal square root estimate

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Reciprocal / Reciprocal square-root estimate

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

This intrinsic compiles to the following instruction:

```asm
FRSQRTE Zresult.D, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FRSQRTE--Floating-point-reciprocal-square-root-estimate--unpredicated--

### Operation

Source operation ID: `SveOperation_svrsqrte_f16`

**Operation**



Return a vector in which element *i* contains an estimate of 1/√`op[i]`, calculated as for [FRSQRTE](https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/FRSQRTE--Floating-point-reciprocal-square-root-estimate--unpredicated--).



**Exceptions**



Signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.  Zeros trigger an IEEE DivideByZero exception and negative values trigger an IEEE Invalid exception.

## svrsqrte[_u32]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrsqrte%5B_u32%5D_m

### Signature (source notation)

```c
svuint32_t svrsqrte[_u32]_m(svuint32_t inactive, svbool_t pg, svuint32_t op);
```

### Description

Reciprocal square root estimate

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Reciprocal / Reciprocal square-root estimate

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
URSQRTE Ztied.S, Pg/M, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/URSQRTE--Unsigned-reciprocal-square-root-estimate--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zinactive
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
URSQRTE Zresult.S, Pg/M, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/URSQRTE--Unsigned-reciprocal-square-root-estimate--predicated--

### Operation

Source operation ID: `SveOperation_svrsqrte_u32_m`

**Operation**



Return a vector in which active element *i* contains an estimate of 1/√`op[i]`, calculated as for [URSQRTE](https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/URSQRTE--Unsigned-reciprocal-square-root-estimate--predicated--). Take the inactive elements of the result from the corresponding elements of `inactive`.

## svrsqrte[_u32]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrsqrte%5B_u32%5D_x

### Signature (source notation)

```c
svuint32_t svrsqrte[_u32]_x(svbool_t pg, svuint32_t op);
```

### Description

Reciprocal square root estimate

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Reciprocal / Reciprocal square-root estimate

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
URSQRTE Ztied.S, Pg/M, Ztied.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/URSQRTE--Unsigned-reciprocal-square-root-estimate--predicated--

When result and op are in different registers, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
URSQRTE Zresult.S, Pg/M, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/URSQRTE--Unsigned-reciprocal-square-root-estimate--predicated--

### Operation

Source operation ID: `SveOperation_svrsqrte_u32_x`

**Operation**



Return a vector in which active element *i* contains an estimate of 1/√`op[i]`, calculated as for [URSQRTE](https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/URSQRTE--Unsigned-reciprocal-square-root-estimate--predicated--). The inactive elements of the result have arbitrary, undefined values.

## svrsqrte[_u32]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrsqrte%5B_u32%5D_z

### Signature (source notation)

```c
svuint32_t svrsqrte[_u32]_z(svbool_t pg, svuint32_t op);
```

### Description

Reciprocal square root estimate

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Reciprocal / Reciprocal square-root estimate

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
URSQRTE Zresult.S, Pg/M, Zop.S  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/URSQRTE--Unsigned-reciprocal-square-root-estimate--predicated--

### Operation

Source operation ID: `SveOperation_svrsqrte_u32_z`

**Operation**



Return a vector in which active element *i* contains an estimate of 1/√`op[i]`, calculated as for [URSQRTE](https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/URSQRTE--Unsigned-reciprocal-square-root-estimate--predicated--). Set the inactive elements of the result to zero.



**[1]** Note that `result` must be in a different register from `op`

