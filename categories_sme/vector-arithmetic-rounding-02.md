# SME / Vector arithmetic / Rounding — Part 2

## svrintm[_f64]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrintm%5B_f64%5D_z

### Signature (source notation)

```c
svfloat64_t svrintm[_f64]_z(svbool_t pg, svfloat64_t op);
```

### Description

Round towards -∞

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Rounding

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

This intrinsic compiles to the following instructions, or functionally equivalent instructions:

```asm
MOVPRFX Zresult.D, Pg/Z, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
FRINTM Zresult.D, Pg/M, Zop.D  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FRINT-r---Floating-point-round-to-integral-value--predicated--

### Operation

Source operation ID: `SveOperation_svrintm_f16_z`

**Operation**



Return a vector in which each active element *i* contains the result of rounding `op[i]` to an integral value, towards -∞.  Set the inactive elements of the result to zero.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.  The function never triggers an IEEE Inexact exception.



**[1]** Note that `result` must be in a different register from `op`

## svrintn[_f16]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrintn%5B_f16%5D_m

### Signature (source notation)

```c
svfloat16_t svrintn[_f16]_m(svfloat16_t inactive, svbool_t pg, svfloat16_t op);
```

### Description

Round to nearest, ties to even

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Rounding

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
  "inactive": {
    "register": "Zinactive.H|Ztied.H"
  },
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
    "Zresult.H|Ztied.H": "result"
  }
]
```

### Instruction mapping

When result and inactive are in the same register, this intrinsic compiles to:

```asm
FRINTN Ztied.H, Pg/M, Zop.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FRINT-r---Floating-point-round-to-integral-value--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zinactive
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FRINTN Zresult.H, Pg/M, Zop.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FRINT-r---Floating-point-round-to-integral-value--predicated--

### Operation

Source operation ID: `SveOperation_svrintn_f16_m`

**Operation**



Return a vector in which each active element *i* contains the result of rounding `op[i]` to the nearest integral value, or rounding to even in the event of a tie.  Take the inactive elements of the result from the corresponding elements of `inactive`.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.  The function never triggers an IEEE Inexact exception.

## svrintn[_f16]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrintn%5B_f16%5D_x

### Signature (source notation)

```c
svfloat16_t svrintn[_f16]_x(svbool_t pg, svfloat16_t op);
```

### Description

Round to nearest, ties to even

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Rounding

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
  "op": {
    "register": "Zop.H|Ztied.H"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.H|Ztied.H": "result"
  }
]
```

### Instruction mapping

When result and op are in the same register, this intrinsic compiles to:

```asm
FRINTN Ztied.H, Pg/M, Ztied.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FRINT-r---Floating-point-round-to-integral-value--predicated--

When result and op are in different registers, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FRINTN Zresult.H, Pg/M, Zop.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FRINT-r---Floating-point-round-to-integral-value--predicated--

### Operation

Source operation ID: `SveOperation_svrintn_f16_x`

**Operation**



Return a vector in which each active element *i* contains the result of rounding `op[i]` to the nearest integral value, or rounding to even in the event of a tie.  The inactive elements of the result have arbitrary, undefined values.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.  The function never triggers an IEEE Inexact exception.

## svrintn[_f16]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrintn%5B_f16%5D_z

### Signature (source notation)

```c
svfloat16_t svrintn[_f16]_z(svbool_t pg, svfloat16_t op);
```

### Description

Round to nearest, ties to even

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Rounding

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

This intrinsic compiles to the following instructions, or functionally equivalent instructions:

```asm
MOVPRFX Zresult.H, Pg/Z, Zop.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
FRINTN Zresult.H, Pg/M, Zop.H  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FRINT-r---Floating-point-round-to-integral-value--predicated--

### Operation

Source operation ID: `SveOperation_svrintn_f16_z`

**Operation**



Return a vector in which each active element *i* contains the result of rounding `op[i]` to the nearest integral value, or rounding to even in the event of a tie.  Set the inactive elements of the result to zero.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.  The function never triggers an IEEE Inexact exception.



**[1]** Note that `result` must be in a different register from `op`

## svrintn[_f32]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrintn%5B_f32%5D_m

### Signature (source notation)

```c
svfloat32_t svrintn[_f32]_m(svfloat32_t inactive, svbool_t pg, svfloat32_t op);
```

### Description

Round to nearest, ties to even

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Rounding

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
FRINTN Ztied.S, Pg/M, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FRINT-r---Floating-point-round-to-integral-value--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zinactive
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FRINTN Zresult.S, Pg/M, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FRINT-r---Floating-point-round-to-integral-value--predicated--

### Operation

Source operation ID: `SveOperation_svrintn_f16_m`

**Operation**



Return a vector in which each active element *i* contains the result of rounding `op[i]` to the nearest integral value, or rounding to even in the event of a tie.  Take the inactive elements of the result from the corresponding elements of `inactive`.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.  The function never triggers an IEEE Inexact exception.

## svrintn[_f32]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrintn%5B_f32%5D_x

### Signature (source notation)

```c
svfloat32_t svrintn[_f32]_x(svbool_t pg, svfloat32_t op);
```

### Description

Round to nearest, ties to even

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Rounding

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
FRINTN Ztied.S, Pg/M, Ztied.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FRINT-r---Floating-point-round-to-integral-value--predicated--

When result and op are in different registers, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FRINTN Zresult.S, Pg/M, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FRINT-r---Floating-point-round-to-integral-value--predicated--

### Operation

Source operation ID: `SveOperation_svrintn_f16_x`

**Operation**



Return a vector in which each active element *i* contains the result of rounding `op[i]` to the nearest integral value, or rounding to even in the event of a tie.  The inactive elements of the result have arbitrary, undefined values.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.  The function never triggers an IEEE Inexact exception.

## svrintn[_f32]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrintn%5B_f32%5D_z

### Signature (source notation)

```c
svfloat32_t svrintn[_f32]_z(svbool_t pg, svfloat32_t op);
```

### Description

Round to nearest, ties to even

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Rounding

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
FRINTN Zresult.S, Pg/M, Zop.S  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FRINT-r---Floating-point-round-to-integral-value--predicated--

### Operation

Source operation ID: `SveOperation_svrintn_f16_z`

**Operation**



Return a vector in which each active element *i* contains the result of rounding `op[i]` to the nearest integral value, or rounding to even in the event of a tie.  Set the inactive elements of the result to zero.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.  The function never triggers an IEEE Inexact exception.



**[1]** Note that `result` must be in a different register from `op`

## svrintn[_f64]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrintn%5B_f64%5D_m

### Signature (source notation)

```c
svfloat64_t svrintn[_f64]_m(svfloat64_t inactive, svbool_t pg, svfloat64_t op);
```

### Description

Round to nearest, ties to even

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Rounding

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
  "inactive": {
    "register": "Zinactive.D|Ztied.D"
  },
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
    "Zresult.D|Ztied.D": "result"
  }
]
```

### Instruction mapping

When result and inactive are in the same register, this intrinsic compiles to:

```asm
FRINTN Ztied.D, Pg/M, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FRINT-r---Floating-point-round-to-integral-value--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zinactive
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FRINTN Zresult.D, Pg/M, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FRINT-r---Floating-point-round-to-integral-value--predicated--

### Operation

Source operation ID: `SveOperation_svrintn_f16_m`

**Operation**



Return a vector in which each active element *i* contains the result of rounding `op[i]` to the nearest integral value, or rounding to even in the event of a tie.  Take the inactive elements of the result from the corresponding elements of `inactive`.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.  The function never triggers an IEEE Inexact exception.

## svrintn[_f64]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrintn%5B_f64%5D_x

### Signature (source notation)

```c
svfloat64_t svrintn[_f64]_x(svbool_t pg, svfloat64_t op);
```

### Description

Round to nearest, ties to even

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Rounding

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
  "op": {
    "register": "Zop.D|Ztied.D"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.D|Ztied.D": "result"
  }
]
```

### Instruction mapping

When result and op are in the same register, this intrinsic compiles to:

```asm
FRINTN Ztied.D, Pg/M, Ztied.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FRINT-r---Floating-point-round-to-integral-value--predicated--

When result and op are in different registers, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FRINTN Zresult.D, Pg/M, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FRINT-r---Floating-point-round-to-integral-value--predicated--

### Operation

Source operation ID: `SveOperation_svrintn_f16_x`

**Operation**



Return a vector in which each active element *i* contains the result of rounding `op[i]` to the nearest integral value, or rounding to even in the event of a tie.  The inactive elements of the result have arbitrary, undefined values.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.  The function never triggers an IEEE Inexact exception.

## svrintn[_f64]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrintn%5B_f64%5D_z

### Signature (source notation)

```c
svfloat64_t svrintn[_f64]_z(svbool_t pg, svfloat64_t op);
```

### Description

Round to nearest, ties to even

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Rounding

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

This intrinsic compiles to the following instructions, or functionally equivalent instructions:

```asm
MOVPRFX Zresult.D, Pg/Z, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
FRINTN Zresult.D, Pg/M, Zop.D  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FRINT-r---Floating-point-round-to-integral-value--predicated--

### Operation

Source operation ID: `SveOperation_svrintn_f16_z`

**Operation**



Return a vector in which each active element *i* contains the result of rounding `op[i]` to the nearest integral value, or rounding to even in the event of a tie.  Set the inactive elements of the result to zero.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.  The function never triggers an IEEE Inexact exception.



**[1]** Note that `result` must be in a different register from `op`

## svrintp[_f16]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrintp%5B_f16%5D_m

### Signature (source notation)

```c
svfloat16_t svrintp[_f16]_m(svfloat16_t inactive, svbool_t pg, svfloat16_t op);
```

### Description

Round towards +∞

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Rounding

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
  "inactive": {
    "register": "Zinactive.H|Ztied.H"
  },
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
    "Zresult.H|Ztied.H": "result"
  }
]
```

### Instruction mapping

When result and inactive are in the same register, this intrinsic compiles to:

```asm
FRINTP Ztied.H, Pg/M, Zop.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FRINT-r---Floating-point-round-to-integral-value--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zinactive
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FRINTP Zresult.H, Pg/M, Zop.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FRINT-r---Floating-point-round-to-integral-value--predicated--

### Operation

Source operation ID: `SveOperation_svrintp_f16_m`

**Operation**



Return a vector in which each active element *i* contains the result of rounding `op[i]` to an integral value, towards +∞.  Take the inactive elements of the result from the corresponding elements of `inactive`.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.  The function never triggers an IEEE Inexact exception.

## svrintp[_f16]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrintp%5B_f16%5D_x

### Signature (source notation)

```c
svfloat16_t svrintp[_f16]_x(svbool_t pg, svfloat16_t op);
```

### Description

Round towards +∞

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Rounding

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
  "op": {
    "register": "Zop.H|Ztied.H"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.H|Ztied.H": "result"
  }
]
```

### Instruction mapping

When result and op are in the same register, this intrinsic compiles to:

```asm
FRINTP Ztied.H, Pg/M, Ztied.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FRINT-r---Floating-point-round-to-integral-value--predicated--

When result and op are in different registers, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FRINTP Zresult.H, Pg/M, Zop.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FRINT-r---Floating-point-round-to-integral-value--predicated--

### Operation

Source operation ID: `SveOperation_svrintp_f16_x`

**Operation**



Return a vector in which each active element *i* contains the result of rounding `op[i]` to an integral value, towards +∞.  The inactive elements of the result have arbitrary, undefined values.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.  The function never triggers an IEEE Inexact exception.

## svrintp[_f16]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrintp%5B_f16%5D_z

### Signature (source notation)

```c
svfloat16_t svrintp[_f16]_z(svbool_t pg, svfloat16_t op);
```

### Description

Round towards +∞

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Rounding

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

This intrinsic compiles to the following instructions, or functionally equivalent instructions:

```asm
MOVPRFX Zresult.H, Pg/Z, Zop.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
FRINTP Zresult.H, Pg/M, Zop.H  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FRINT-r---Floating-point-round-to-integral-value--predicated--

### Operation

Source operation ID: `SveOperation_svrintp_f16_z`

**Operation**



Return a vector in which each active element *i* contains the result of rounding `op[i]` to an integral value, towards +∞.  Set the inactive elements of the result to zero.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.  The function never triggers an IEEE Inexact exception.



**[1]** Note that `result` must be in a different register from `op`

## svrintp[_f32]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrintp%5B_f32%5D_m

### Signature (source notation)

```c
svfloat32_t svrintp[_f32]_m(svfloat32_t inactive, svbool_t pg, svfloat32_t op);
```

### Description

Round towards +∞

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Rounding

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
FRINTP Ztied.S, Pg/M, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FRINT-r---Floating-point-round-to-integral-value--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zinactive
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FRINTP Zresult.S, Pg/M, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FRINT-r---Floating-point-round-to-integral-value--predicated--

### Operation

Source operation ID: `SveOperation_svrintp_f16_m`

**Operation**



Return a vector in which each active element *i* contains the result of rounding `op[i]` to an integral value, towards +∞.  Take the inactive elements of the result from the corresponding elements of `inactive`.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.  The function never triggers an IEEE Inexact exception.

## svrintp[_f32]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrintp%5B_f32%5D_x

### Signature (source notation)

```c
svfloat32_t svrintp[_f32]_x(svbool_t pg, svfloat32_t op);
```

### Description

Round towards +∞

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Rounding

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
FRINTP Ztied.S, Pg/M, Ztied.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FRINT-r---Floating-point-round-to-integral-value--predicated--

When result and op are in different registers, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FRINTP Zresult.S, Pg/M, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FRINT-r---Floating-point-round-to-integral-value--predicated--

### Operation

Source operation ID: `SveOperation_svrintp_f16_x`

**Operation**



Return a vector in which each active element *i* contains the result of rounding `op[i]` to an integral value, towards +∞.  The inactive elements of the result have arbitrary, undefined values.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.  The function never triggers an IEEE Inexact exception.

## svrintp[_f32]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrintp%5B_f32%5D_z

### Signature (source notation)

```c
svfloat32_t svrintp[_f32]_z(svbool_t pg, svfloat32_t op);
```

### Description

Round towards +∞

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Rounding

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
FRINTP Zresult.S, Pg/M, Zop.S  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FRINT-r---Floating-point-round-to-integral-value--predicated--

### Operation

Source operation ID: `SveOperation_svrintp_f16_z`

**Operation**



Return a vector in which each active element *i* contains the result of rounding `op[i]` to an integral value, towards +∞.  Set the inactive elements of the result to zero.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.  The function never triggers an IEEE Inexact exception.



**[1]** Note that `result` must be in a different register from `op`

## svrintp[_f64]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrintp%5B_f64%5D_m

### Signature (source notation)

```c
svfloat64_t svrintp[_f64]_m(svfloat64_t inactive, svbool_t pg, svfloat64_t op);
```

### Description

Round towards +∞

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Rounding

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
  "inactive": {
    "register": "Zinactive.D|Ztied.D"
  },
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
    "Zresult.D|Ztied.D": "result"
  }
]
```

### Instruction mapping

When result and inactive are in the same register, this intrinsic compiles to:

```asm
FRINTP Ztied.D, Pg/M, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FRINT-r---Floating-point-round-to-integral-value--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zinactive
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FRINTP Zresult.D, Pg/M, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FRINT-r---Floating-point-round-to-integral-value--predicated--

### Operation

Source operation ID: `SveOperation_svrintp_f16_m`

**Operation**



Return a vector in which each active element *i* contains the result of rounding `op[i]` to an integral value, towards +∞.  Take the inactive elements of the result from the corresponding elements of `inactive`.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.  The function never triggers an IEEE Inexact exception.

## svrintp[_f64]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrintp%5B_f64%5D_x

### Signature (source notation)

```c
svfloat64_t svrintp[_f64]_x(svbool_t pg, svfloat64_t op);
```

### Description

Round towards +∞

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Rounding

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
  "op": {
    "register": "Zop.D|Ztied.D"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.D|Ztied.D": "result"
  }
]
```

### Instruction mapping

When result and op are in the same register, this intrinsic compiles to:

```asm
FRINTP Ztied.D, Pg/M, Ztied.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FRINT-r---Floating-point-round-to-integral-value--predicated--

When result and op are in different registers, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FRINTP Zresult.D, Pg/M, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FRINT-r---Floating-point-round-to-integral-value--predicated--

### Operation

Source operation ID: `SveOperation_svrintp_f16_x`

**Operation**



Return a vector in which each active element *i* contains the result of rounding `op[i]` to an integral value, towards +∞.  The inactive elements of the result have arbitrary, undefined values.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.  The function never triggers an IEEE Inexact exception.

## svrintp[_f64]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrintp%5B_f64%5D_z

### Signature (source notation)

```c
svfloat64_t svrintp[_f64]_z(svbool_t pg, svfloat64_t op);
```

### Description

Round towards +∞

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Rounding

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

This intrinsic compiles to the following instructions, or functionally equivalent instructions:

```asm
MOVPRFX Zresult.D, Pg/Z, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
FRINTP Zresult.D, Pg/M, Zop.D  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FRINT-r---Floating-point-round-to-integral-value--predicated--

### Operation

Source operation ID: `SveOperation_svrintp_f16_z`

**Operation**



Return a vector in which each active element *i* contains the result of rounding `op[i]` to an integral value, towards +∞.  Set the inactive elements of the result to zero.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.  The function never triggers an IEEE Inexact exception.



**[1]** Note that `result` must be in a different register from `op`

## svrintx[_f16]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrintx%5B_f16%5D_m

### Signature (source notation)

```c
svfloat16_t svrintx[_f16]_m(svfloat16_t inactive, svbool_t pg, svfloat16_t op);
```

### Description

Round using current rounding mode (exact)

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Rounding

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
  "inactive": {
    "register": "Zinactive.H|Ztied.H"
  },
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
    "Zresult.H|Ztied.H": "result"
  }
]
```

### Instruction mapping

When result and inactive are in the same register, this intrinsic compiles to:

```asm
FRINTX Ztied.H, Pg/M, Zop.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FRINT-r---Floating-point-round-to-integral-value--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zinactive
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FRINTX Zresult.H, Pg/M, Zop.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FRINT-r---Floating-point-round-to-integral-value--predicated--

### Operation

Source operation ID: `SveOperation_svrintx_f16_m`

**Operation**



Return a vector in which each active element *i* contains the result of rounding `op[i]` to an integral value using the current rounding mode.  Take the inactive elements of the result from the corresponding elements of `inactive`.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.  Rounding operations that yield a different value trigger an IEEE Inexact exception.

## svrintx[_f16]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrintx%5B_f16%5D_x

### Signature (source notation)

```c
svfloat16_t svrintx[_f16]_x(svbool_t pg, svfloat16_t op);
```

### Description

Round using current rounding mode (exact)

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Rounding

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
  "op": {
    "register": "Zop.H|Ztied.H"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.H|Ztied.H": "result"
  }
]
```

### Instruction mapping

When result and op are in the same register, this intrinsic compiles to:

```asm
FRINTX Ztied.H, Pg/M, Ztied.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FRINT-r---Floating-point-round-to-integral-value--predicated--

When result and op are in different registers, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FRINTX Zresult.H, Pg/M, Zop.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FRINT-r---Floating-point-round-to-integral-value--predicated--

### Operation

Source operation ID: `SveOperation_svrintx_f16_x`

**Operation**



Return a vector in which each active element *i* contains the result of rounding `op[i]` to an integral value using the current rounding mode.  The inactive elements of the result have arbitrary, undefined values.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.  Rounding operations that yield a different value trigger an IEEE Inexact exception.

## svrintx[_f16]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrintx%5B_f16%5D_z

### Signature (source notation)

```c
svfloat16_t svrintx[_f16]_z(svbool_t pg, svfloat16_t op);
```

### Description

Round using current rounding mode (exact)

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Rounding

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

This intrinsic compiles to the following instructions, or functionally equivalent instructions:

```asm
MOVPRFX Zresult.H, Pg/Z, Zop.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
FRINTX Zresult.H, Pg/M, Zop.H  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FRINT-r---Floating-point-round-to-integral-value--predicated--

### Operation

Source operation ID: `SveOperation_svrintx_f16_z`

**Operation**



Return a vector in which each active element *i* contains the result of rounding `op[i]` to an integral value using the current rounding mode.  Set the inactive elements of the result to zero.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.  Rounding operations that yield a different value trigger an IEEE Inexact exception.



**[1]** Note that `result` must be in a different register from `op`

## svrintx[_f32]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrintx%5B_f32%5D_m

### Signature (source notation)

```c
svfloat32_t svrintx[_f32]_m(svfloat32_t inactive, svbool_t pg, svfloat32_t op);
```

### Description

Round using current rounding mode (exact)

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Rounding

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
FRINTX Ztied.S, Pg/M, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FRINT-r---Floating-point-round-to-integral-value--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zinactive
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FRINTX Zresult.S, Pg/M, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FRINT-r---Floating-point-round-to-integral-value--predicated--

### Operation

Source operation ID: `SveOperation_svrintx_f16_m`

**Operation**



Return a vector in which each active element *i* contains the result of rounding `op[i]` to an integral value using the current rounding mode.  Take the inactive elements of the result from the corresponding elements of `inactive`.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.  Rounding operations that yield a different value trigger an IEEE Inexact exception.

## svrintx[_f32]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrintx%5B_f32%5D_x

### Signature (source notation)

```c
svfloat32_t svrintx[_f32]_x(svbool_t pg, svfloat32_t op);
```

### Description

Round using current rounding mode (exact)

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Rounding

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
FRINTX Ztied.S, Pg/M, Ztied.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FRINT-r---Floating-point-round-to-integral-value--predicated--

When result and op are in different registers, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FRINTX Zresult.S, Pg/M, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FRINT-r---Floating-point-round-to-integral-value--predicated--

### Operation

Source operation ID: `SveOperation_svrintx_f16_x`

**Operation**



Return a vector in which each active element *i* contains the result of rounding `op[i]` to an integral value using the current rounding mode.  The inactive elements of the result have arbitrary, undefined values.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.  Rounding operations that yield a different value trigger an IEEE Inexact exception.

## svrintx[_f32]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrintx%5B_f32%5D_z

### Signature (source notation)

```c
svfloat32_t svrintx[_f32]_z(svbool_t pg, svfloat32_t op);
```

### Description

Round using current rounding mode (exact)

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Rounding

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
FRINTX Zresult.S, Pg/M, Zop.S  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FRINT-r---Floating-point-round-to-integral-value--predicated--

### Operation

Source operation ID: `SveOperation_svrintx_f16_z`

**Operation**



Return a vector in which each active element *i* contains the result of rounding `op[i]` to an integral value using the current rounding mode.  Set the inactive elements of the result to zero.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.  Rounding operations that yield a different value trigger an IEEE Inexact exception.



**[1]** Note that `result` must be in a different register from `op`

## svrintx[_f64]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrintx%5B_f64%5D_m

### Signature (source notation)

```c
svfloat64_t svrintx[_f64]_m(svfloat64_t inactive, svbool_t pg, svfloat64_t op);
```

### Description

Round using current rounding mode (exact)

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Rounding

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
  "inactive": {
    "register": "Zinactive.D|Ztied.D"
  },
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
    "Zresult.D|Ztied.D": "result"
  }
]
```

### Instruction mapping

When result and inactive are in the same register, this intrinsic compiles to:

```asm
FRINTX Ztied.D, Pg/M, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FRINT-r---Floating-point-round-to-integral-value--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zinactive
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FRINTX Zresult.D, Pg/M, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FRINT-r---Floating-point-round-to-integral-value--predicated--

### Operation

Source operation ID: `SveOperation_svrintx_f16_m`

**Operation**



Return a vector in which each active element *i* contains the result of rounding `op[i]` to an integral value using the current rounding mode.  Take the inactive elements of the result from the corresponding elements of `inactive`.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.  Rounding operations that yield a different value trigger an IEEE Inexact exception.

## svrintx[_f64]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrintx%5B_f64%5D_x

### Signature (source notation)

```c
svfloat64_t svrintx[_f64]_x(svbool_t pg, svfloat64_t op);
```

### Description

Round using current rounding mode (exact)

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Rounding

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
  "op": {
    "register": "Zop.D|Ztied.D"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.D|Ztied.D": "result"
  }
]
```

### Instruction mapping

When result and op are in the same register, this intrinsic compiles to:

```asm
FRINTX Ztied.D, Pg/M, Ztied.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FRINT-r---Floating-point-round-to-integral-value--predicated--

When result and op are in different registers, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FRINTX Zresult.D, Pg/M, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FRINT-r---Floating-point-round-to-integral-value--predicated--

### Operation

Source operation ID: `SveOperation_svrintx_f16_x`

**Operation**



Return a vector in which each active element *i* contains the result of rounding `op[i]` to an integral value using the current rounding mode.  The inactive elements of the result have arbitrary, undefined values.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.  Rounding operations that yield a different value trigger an IEEE Inexact exception.

## svrintx[_f64]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrintx%5B_f64%5D_z

### Signature (source notation)

```c
svfloat64_t svrintx[_f64]_z(svbool_t pg, svfloat64_t op);
```

### Description

Round using current rounding mode (exact)

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Rounding

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

This intrinsic compiles to the following instructions, or functionally equivalent instructions:

```asm
MOVPRFX Zresult.D, Pg/Z, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
FRINTX Zresult.D, Pg/M, Zop.D  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FRINT-r---Floating-point-round-to-integral-value--predicated--

### Operation

Source operation ID: `SveOperation_svrintx_f16_z`

**Operation**



Return a vector in which each active element *i* contains the result of rounding `op[i]` to an integral value using the current rounding mode.  Set the inactive elements of the result to zero.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.  Rounding operations that yield a different value trigger an IEEE Inexact exception.



**[1]** Note that `result` must be in a different register from `op`

## svrintz[_f16]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrintz%5B_f16%5D_m

### Signature (source notation)

```c
svfloat16_t svrintz[_f16]_m(svfloat16_t inactive, svbool_t pg, svfloat16_t op);
```

### Description

Round towards zero

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Rounding

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
  "inactive": {
    "register": "Zinactive.H|Ztied.H"
  },
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
    "Zresult.H|Ztied.H": "result"
  }
]
```

### Instruction mapping

When result and inactive are in the same register, this intrinsic compiles to:

```asm
FRINTZ Ztied.H, Pg/M, Zop.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FRINT-r---Floating-point-round-to-integral-value--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zinactive
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FRINTZ Zresult.H, Pg/M, Zop.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FRINT-r---Floating-point-round-to-integral-value--predicated--

### Operation

Source operation ID: `SveOperation_svrintz_f16_m`

**Operation**



Return a vector in which each active element *i* contains the result of rounding `op[i]` to an integral value, towards zero.  Take the inactive elements of the result from the corresponding elements of `inactive`.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.  The function never triggers an IEEE Inexact exception.

## svrintz[_f16]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrintz%5B_f16%5D_x

### Signature (source notation)

```c
svfloat16_t svrintz[_f16]_x(svbool_t pg, svfloat16_t op);
```

### Description

Round towards zero

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Rounding

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
  "op": {
    "register": "Zop.H|Ztied.H"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.H|Ztied.H": "result"
  }
]
```

### Instruction mapping

When result and op are in the same register, this intrinsic compiles to:

```asm
FRINTZ Ztied.H, Pg/M, Ztied.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FRINT-r---Floating-point-round-to-integral-value--predicated--

When result and op are in different registers, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FRINTZ Zresult.H, Pg/M, Zop.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FRINT-r---Floating-point-round-to-integral-value--predicated--

### Operation

Source operation ID: `SveOperation_svrintz_f16_x`

**Operation**



Return a vector in which each active element *i* contains the result of rounding `op[i]` to an integral value, towards zero.  The inactive elements of the result have arbitrary, undefined values.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.  The function never triggers an IEEE Inexact exception.

## svrintz[_f16]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrintz%5B_f16%5D_z

### Signature (source notation)

```c
svfloat16_t svrintz[_f16]_z(svbool_t pg, svfloat16_t op);
```

### Description

Round towards zero

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Rounding

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

This intrinsic compiles to the following instructions, or functionally equivalent instructions:

```asm
MOVPRFX Zresult.H, Pg/Z, Zop.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
FRINTZ Zresult.H, Pg/M, Zop.H  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FRINT-r---Floating-point-round-to-integral-value--predicated--

### Operation

Source operation ID: `SveOperation_svrintz_f16_z`

**Operation**



Return a vector in which each active element *i* contains the result of rounding `op[i]` to an integral value, towards zero.  Set the inactive elements of the result to zero.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.  The function never triggers an IEEE Inexact exception.



**[1]** Note that `result` must be in a different register from `op`

## svrintz[_f32]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrintz%5B_f32%5D_m

### Signature (source notation)

```c
svfloat32_t svrintz[_f32]_m(svfloat32_t inactive, svbool_t pg, svfloat32_t op);
```

### Description

Round towards zero

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Rounding

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
FRINTZ Ztied.S, Pg/M, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FRINT-r---Floating-point-round-to-integral-value--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zinactive
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FRINTZ Zresult.S, Pg/M, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FRINT-r---Floating-point-round-to-integral-value--predicated--

### Operation

Source operation ID: `SveOperation_svrintz_f16_m`

**Operation**



Return a vector in which each active element *i* contains the result of rounding `op[i]` to an integral value, towards zero.  Take the inactive elements of the result from the corresponding elements of `inactive`.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.  The function never triggers an IEEE Inexact exception.

## svrintz[_f32]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrintz%5B_f32%5D_x

### Signature (source notation)

```c
svfloat32_t svrintz[_f32]_x(svbool_t pg, svfloat32_t op);
```

### Description

Round towards zero

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Rounding

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
FRINTZ Ztied.S, Pg/M, Ztied.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FRINT-r---Floating-point-round-to-integral-value--predicated--

When result and op are in different registers, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FRINTZ Zresult.S, Pg/M, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FRINT-r---Floating-point-round-to-integral-value--predicated--

### Operation

Source operation ID: `SveOperation_svrintz_f16_x`

**Operation**



Return a vector in which each active element *i* contains the result of rounding `op[i]` to an integral value, towards zero.  The inactive elements of the result have arbitrary, undefined values.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.  The function never triggers an IEEE Inexact exception.

## svrintz[_f32]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrintz%5B_f32%5D_z

### Signature (source notation)

```c
svfloat32_t svrintz[_f32]_z(svbool_t pg, svfloat32_t op);
```

### Description

Round towards zero

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Rounding

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
FRINTZ Zresult.S, Pg/M, Zop.S  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FRINT-r---Floating-point-round-to-integral-value--predicated--

### Operation

Source operation ID: `SveOperation_svrintz_f16_z`

**Operation**



Return a vector in which each active element *i* contains the result of rounding `op[i]` to an integral value, towards zero.  Set the inactive elements of the result to zero.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.  The function never triggers an IEEE Inexact exception.



**[1]** Note that `result` must be in a different register from `op`

## svrintz[_f64]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrintz%5B_f64%5D_m

### Signature (source notation)

```c
svfloat64_t svrintz[_f64]_m(svfloat64_t inactive, svbool_t pg, svfloat64_t op);
```

### Description

Round towards zero

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Rounding

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
  "inactive": {
    "register": "Zinactive.D|Ztied.D"
  },
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
    "Zresult.D|Ztied.D": "result"
  }
]
```

### Instruction mapping

When result and inactive are in the same register, this intrinsic compiles to:

```asm
FRINTZ Ztied.D, Pg/M, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FRINT-r---Floating-point-round-to-integral-value--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zinactive
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FRINTZ Zresult.D, Pg/M, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FRINT-r---Floating-point-round-to-integral-value--predicated--

### Operation

Source operation ID: `SveOperation_svrintz_f16_m`

**Operation**



Return a vector in which each active element *i* contains the result of rounding `op[i]` to an integral value, towards zero.  Take the inactive elements of the result from the corresponding elements of `inactive`.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.  The function never triggers an IEEE Inexact exception.

## svrintz[_f64]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrintz%5B_f64%5D_x

### Signature (source notation)

```c
svfloat64_t svrintz[_f64]_x(svbool_t pg, svfloat64_t op);
```

### Description

Round towards zero

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Rounding

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
  "op": {
    "register": "Zop.D|Ztied.D"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.D|Ztied.D": "result"
  }
]
```

### Instruction mapping

When result and op are in the same register, this intrinsic compiles to:

```asm
FRINTZ Ztied.D, Pg/M, Ztied.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FRINT-r---Floating-point-round-to-integral-value--predicated--

When result and op are in different registers, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FRINTZ Zresult.D, Pg/M, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FRINT-r---Floating-point-round-to-integral-value--predicated--

### Operation

Source operation ID: `SveOperation_svrintz_f16_x`

**Operation**



Return a vector in which each active element *i* contains the result of rounding `op[i]` to an integral value, towards zero.  The inactive elements of the result have arbitrary, undefined values.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.  The function never triggers an IEEE Inexact exception.

## svrintz[_f64]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrintz%5B_f64%5D_z

### Signature (source notation)

```c
svfloat64_t svrintz[_f64]_z(svbool_t pg, svfloat64_t op);
```

### Description

Round towards zero

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Rounding

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

This intrinsic compiles to the following instructions, or functionally equivalent instructions:

```asm
MOVPRFX Zresult.D, Pg/Z, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
FRINTZ Zresult.D, Pg/M, Zop.D  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FRINT-r---Floating-point-round-to-integral-value--predicated--

### Operation

Source operation ID: `SveOperation_svrintz_f16_z`

**Operation**



Return a vector in which each active element *i* contains the result of rounding `op[i]` to an integral value, towards zero.  Set the inactive elements of the result to zero.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.  The function never triggers an IEEE Inexact exception.



**[1]** Note that `result` must be in a different register from `op`

