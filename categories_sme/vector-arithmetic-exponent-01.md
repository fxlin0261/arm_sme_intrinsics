# SME / Vector arithmetic / Exponent — Part 1

## svscale[_f16]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svscale%5B_f16%5D_m

### Signature (source notation)

```c
svfloat16_t svscale[_f16]_m(svbool_t pg, svfloat16_t op1, svint16_t op2);
```

### Description

Adjust exponent

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Exponent

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
FSCALE Ztied1.H, Pg/M, Ztied1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FSCALE--Floating-point-adjust-exponent--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FSCALE Zresult.H, Pg/M, Zresult.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FSCALE--Floating-point-adjust-exponent--predicated--

### Operation

Source operation ID: `SveOperation_svscale_f16_m`

**Operation**



Return a vector in which each active element *i* contains the result of multiplying `op1[i]` by 2 to the power `op2[i]`. Take the inactive elements of the result from the corresponding elements of `op1`.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.

## svscale[_f16]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svscale%5B_f16%5D_x

### Signature (source notation)

```c
svfloat16_t svscale[_f16]_x(svbool_t pg, svfloat16_t op1, svint16_t op2);
```

### Description

Adjust exponent

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Exponent

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
FSCALE Ztied1.H, Pg/M, Ztied1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FSCALE--Floating-point-adjust-exponent--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FSCALE Zresult.H, Pg/M, Zresult.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FSCALE--Floating-point-adjust-exponent--predicated--

### Operation

Source operation ID: `SveOperation_svscale_f16_x`

**Operation**



Return a vector in which each active element *i* contains the result of multiplying `op1[i]` by 2 to the power `op2[i]`. The inactive elements of the result have arbitrary, undefined values.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.

## svscale[_f16]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svscale%5B_f16%5D_z

### Signature (source notation)

```c
svfloat16_t svscale[_f16]_z(svbool_t pg, svfloat16_t op1, svint16_t op2);
```

### Description

Adjust exponent

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Exponent

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
FSCALE Zresult.H, Pg/M, Zresult.H, Zop2.H  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FSCALE--Floating-point-adjust-exponent--predicated--

### Operation

Source operation ID: `SveOperation_svscale_f16_z`

**Operation**



Return a vector in which each active element *i* contains the result of multiplying `op1[i]` by 2 to the power `op2[i]`. Set the inactive elements of the result to zero.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.



**[1]** Note that `result` must be in a different register from `op2`

## svscale[_f32]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svscale%5B_f32%5D_m

### Signature (source notation)

```c
svfloat32_t svscale[_f32]_m(svbool_t pg, svfloat32_t op1, svint32_t op2);
```

### Description

Adjust exponent

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Exponent

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
FSCALE Ztied1.S, Pg/M, Ztied1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FSCALE--Floating-point-adjust-exponent--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FSCALE Zresult.S, Pg/M, Zresult.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FSCALE--Floating-point-adjust-exponent--predicated--

### Operation

Source operation ID: `SveOperation_svscale_f16_m`

**Operation**



Return a vector in which each active element *i* contains the result of multiplying `op1[i]` by 2 to the power `op2[i]`. Take the inactive elements of the result from the corresponding elements of `op1`.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.

## svscale[_f32]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svscale%5B_f32%5D_x

### Signature (source notation)

```c
svfloat32_t svscale[_f32]_x(svbool_t pg, svfloat32_t op1, svint32_t op2);
```

### Description

Adjust exponent

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Exponent

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
FSCALE Ztied1.S, Pg/M, Ztied1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FSCALE--Floating-point-adjust-exponent--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FSCALE Zresult.S, Pg/M, Zresult.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FSCALE--Floating-point-adjust-exponent--predicated--

### Operation

Source operation ID: `SveOperation_svscale_f16_x`

**Operation**



Return a vector in which each active element *i* contains the result of multiplying `op1[i]` by 2 to the power `op2[i]`. The inactive elements of the result have arbitrary, undefined values.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.

## svscale[_f32]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svscale%5B_f32%5D_z

### Signature (source notation)

```c
svfloat32_t svscale[_f32]_z(svbool_t pg, svfloat32_t op1, svint32_t op2);
```

### Description

Adjust exponent

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Exponent

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
FSCALE Zresult.S, Pg/M, Zresult.S, Zop2.S  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FSCALE--Floating-point-adjust-exponent--predicated--

### Operation

Source operation ID: `SveOperation_svscale_f16_z`

**Operation**



Return a vector in which each active element *i* contains the result of multiplying `op1[i]` by 2 to the power `op2[i]`. Set the inactive elements of the result to zero.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.



**[1]** Note that `result` must be in a different register from `op2`

## svscale[_f64]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svscale%5B_f64%5D_m

### Signature (source notation)

```c
svfloat64_t svscale[_f64]_m(svbool_t pg, svfloat64_t op1, svint64_t op2);
```

### Description

Adjust exponent

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Exponent

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
FSCALE Ztied1.D, Pg/M, Ztied1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FSCALE--Floating-point-adjust-exponent--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FSCALE Zresult.D, Pg/M, Zresult.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FSCALE--Floating-point-adjust-exponent--predicated--

### Operation

Source operation ID: `SveOperation_svscale_f16_m`

**Operation**



Return a vector in which each active element *i* contains the result of multiplying `op1[i]` by 2 to the power `op2[i]`. Take the inactive elements of the result from the corresponding elements of `op1`.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.

## svscale[_f64]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svscale%5B_f64%5D_x

### Signature (source notation)

```c
svfloat64_t svscale[_f64]_x(svbool_t pg, svfloat64_t op1, svint64_t op2);
```

### Description

Adjust exponent

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Exponent

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
FSCALE Ztied1.D, Pg/M, Ztied1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FSCALE--Floating-point-adjust-exponent--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FSCALE Zresult.D, Pg/M, Zresult.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FSCALE--Floating-point-adjust-exponent--predicated--

### Operation

Source operation ID: `SveOperation_svscale_f16_x`

**Operation**



Return a vector in which each active element *i* contains the result of multiplying `op1[i]` by 2 to the power `op2[i]`. The inactive elements of the result have arbitrary, undefined values.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.

## svscale[_f64]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svscale%5B_f64%5D_z

### Signature (source notation)

```c
svfloat64_t svscale[_f64]_z(svbool_t pg, svfloat64_t op1, svint64_t op2);
```

### Description

Adjust exponent

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Exponent

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
FSCALE Zresult.D, Pg/M, Zresult.D, Zop2.D  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FSCALE--Floating-point-adjust-exponent--predicated--

### Operation

Source operation ID: `SveOperation_svscale_f16_z`

**Operation**



Return a vector in which each active element *i* contains the result of multiplying `op1[i]` by 2 to the power `op2[i]`. Set the inactive elements of the result to zero.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.



**[1]** Note that `result` must be in a different register from `op2`

## svscale[_n_f16]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svscale%5B_n_f16%5D_m

### Signature (source notation)

```c
svfloat16_t svscale[_n_f16]_m(svbool_t pg, svfloat16_t op1, int16_t op2);
```

### Description

Adjust exponent

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Exponent

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
FSCALE Ztied1.H, Pg/M, Ztied1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FSCALE--Floating-point-adjust-exponent--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FSCALE Zresult.H, Pg/M, Zresult.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FSCALE--Floating-point-adjust-exponent--predicated--

### Operation

Source operation ID: `SveOperation_svscale_n_f16_m`

**Operation**



Return a vector in which each active element *i* contains the result of multiplying `op1[i]` by 2 to the power `op2`. Take the inactive elements of the result from the corresponding elements of `op1`.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.

## svscale[_n_f16]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svscale%5B_n_f16%5D_x

### Signature (source notation)

```c
svfloat16_t svscale[_n_f16]_x(svbool_t pg, svfloat16_t op1, int16_t op2);
```

### Description

Adjust exponent

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Exponent

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
FSCALE Ztied1.H, Pg/M, Ztied1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FSCALE--Floating-point-adjust-exponent--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FSCALE Zresult.H, Pg/M, Zresult.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FSCALE--Floating-point-adjust-exponent--predicated--

### Operation

Source operation ID: `SveOperation_svscale_n_f16_x`

**Operation**



Return a vector in which each active element *i* contains the result of multiplying `op1[i]` by 2 to the power `op2`. The inactive elements of the result have arbitrary, undefined values.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.

## svscale[_n_f16]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svscale%5B_n_f16%5D_z

### Signature (source notation)

```c
svfloat16_t svscale[_n_f16]_z(svbool_t pg, svfloat16_t op1, int16_t op2);
```

### Description

Adjust exponent

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Exponent

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

This intrinsic compiles to the following instructions, or functionally equivalent instructions:

```asm
MOVPRFX Zresult.H, Pg/Z, Zop1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
FSCALE Zresult.H, Pg/M, Zresult.H, Zop2.H  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FSCALE--Floating-point-adjust-exponent--predicated--

### Operation

Source operation ID: `SveOperation_svscale_n_f16_z`

**Operation**



Return a vector in which each active element *i* contains the result of multiplying `op1[i]` by 2 to the power `op2`. Set the inactive elements of the result to zero.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.



**[1]** Note that `result` must be in a different register from `op2`

## svscale[_n_f32]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svscale%5B_n_f32%5D_m

### Signature (source notation)

```c
svfloat32_t svscale[_n_f32]_m(svbool_t pg, svfloat32_t op1, int32_t op2);
```

### Description

Adjust exponent

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Exponent

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
FSCALE Ztied1.S, Pg/M, Ztied1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FSCALE--Floating-point-adjust-exponent--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FSCALE Zresult.S, Pg/M, Zresult.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FSCALE--Floating-point-adjust-exponent--predicated--

### Operation

Source operation ID: `SveOperation_svscale_n_f16_m`

**Operation**



Return a vector in which each active element *i* contains the result of multiplying `op1[i]` by 2 to the power `op2`. Take the inactive elements of the result from the corresponding elements of `op1`.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.

## svscale[_n_f32]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svscale%5B_n_f32%5D_x

### Signature (source notation)

```c
svfloat32_t svscale[_n_f32]_x(svbool_t pg, svfloat32_t op1, int32_t op2);
```

### Description

Adjust exponent

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Exponent

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
FSCALE Ztied1.S, Pg/M, Ztied1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FSCALE--Floating-point-adjust-exponent--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FSCALE Zresult.S, Pg/M, Zresult.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FSCALE--Floating-point-adjust-exponent--predicated--

### Operation

Source operation ID: `SveOperation_svscale_n_f16_x`

**Operation**



Return a vector in which each active element *i* contains the result of multiplying `op1[i]` by 2 to the power `op2`. The inactive elements of the result have arbitrary, undefined values.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.

## svscale[_n_f32]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svscale%5B_n_f32%5D_z

### Signature (source notation)

```c
svfloat32_t svscale[_n_f32]_z(svbool_t pg, svfloat32_t op1, int32_t op2);
```

### Description

Adjust exponent

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Exponent

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

This intrinsic compiles to the following instructions, or functionally equivalent instructions:

```asm
MOVPRFX Zresult.S, Pg/Z, Zop1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
FSCALE Zresult.S, Pg/M, Zresult.S, Zop2.S  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FSCALE--Floating-point-adjust-exponent--predicated--

### Operation

Source operation ID: `SveOperation_svscale_n_f16_z`

**Operation**



Return a vector in which each active element *i* contains the result of multiplying `op1[i]` by 2 to the power `op2`. Set the inactive elements of the result to zero.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.



**[1]** Note that `result` must be in a different register from `op2`

## svscale[_n_f64]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svscale%5B_n_f64%5D_m

### Signature (source notation)

```c
svfloat64_t svscale[_n_f64]_m(svbool_t pg, svfloat64_t op1, int64_t op2);
```

### Description

Adjust exponent

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Exponent

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
FSCALE Ztied1.D, Pg/M, Ztied1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FSCALE--Floating-point-adjust-exponent--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FSCALE Zresult.D, Pg/M, Zresult.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FSCALE--Floating-point-adjust-exponent--predicated--

### Operation

Source operation ID: `SveOperation_svscale_n_f16_m`

**Operation**



Return a vector in which each active element *i* contains the result of multiplying `op1[i]` by 2 to the power `op2`. Take the inactive elements of the result from the corresponding elements of `op1`.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.

## svscale[_n_f64]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svscale%5B_n_f64%5D_x

### Signature (source notation)

```c
svfloat64_t svscale[_n_f64]_x(svbool_t pg, svfloat64_t op1, int64_t op2);
```

### Description

Adjust exponent

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Exponent

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
FSCALE Ztied1.D, Pg/M, Ztied1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FSCALE--Floating-point-adjust-exponent--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FSCALE Zresult.D, Pg/M, Zresult.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FSCALE--Floating-point-adjust-exponent--predicated--

### Operation

Source operation ID: `SveOperation_svscale_n_f16_x`

**Operation**



Return a vector in which each active element *i* contains the result of multiplying `op1[i]` by 2 to the power `op2`. The inactive elements of the result have arbitrary, undefined values.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.

## svscale[_n_f64]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svscale%5B_n_f64%5D_z

### Signature (source notation)

```c
svfloat64_t svscale[_n_f64]_z(svbool_t pg, svfloat64_t op1, int64_t op2);
```

### Description

Adjust exponent

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Exponent

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

This intrinsic compiles to the following instructions, or functionally equivalent instructions:

```asm
MOVPRFX Zresult.D, Pg/Z, Zop1.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
FSCALE Zresult.D, Pg/M, Zresult.D, Zop2.D  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FSCALE--Floating-point-adjust-exponent--predicated--

### Operation

Source operation ID: `SveOperation_svscale_n_f16_z`

**Operation**



Return a vector in which each active element *i* contains the result of multiplying `op1[i]` by 2 to the power `op2`. Set the inactive elements of the result to zero.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.



**[1]** Note that `result` must be in a different register from `op2`

