# SME / Vector arithmetic / Reciprocal / Reciprocal exponent — Part 1

## svrecpx[_f16]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrecpx%5B_f16%5D_m

### Signature (source notation)

```c
svfloat16_t svrecpx[_f16]_m(svfloat16_t inactive, svbool_t pg, svfloat16_t op);
```

### Description

Reciprocal exponent

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Reciprocal / Reciprocal exponent

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
FRECPX Ztied.H, Pg/M, Zop.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FRECPX--Floating-point-reciprocal-exponent--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zinactive
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FRECPX Zresult.H, Pg/M, Zop.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FRECPX--Floating-point-reciprocal-exponent--predicated--

### Operation

Source operation ID: `SveOperation_svrecpx_f16_m`

**Operation**



Return a vector in which each active element *i* contains a floating-point value with the same sign and fractional part as `op[i]`, but with the following exponent field:




- the maximum exponent for a normal number, if `op[i]` is a zero or a denormal.
- 

a zero exponent, if `op[i]` is an infinity.



In this case, the new value will be a zero of the same sign as `op[i]`.


- 

the bitwise inverse of `op[i]`'s exponent field otherwise.



In this case, ±1.f×2^n becomes ±1.f×2^(1-n).





Take the inactive elements of the result from the corresponding elements of `inactive`.



**Exceptions**



Active signaling and quiet NaNs both trigger an IEEE Invalid exception.

## svrecpx[_f16]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrecpx%5B_f16%5D_x

### Signature (source notation)

```c
svfloat16_t svrecpx[_f16]_x(svbool_t pg, svfloat16_t op);
```

### Description

Reciprocal exponent

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Reciprocal / Reciprocal exponent

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
FRECPX Ztied.H, Pg/M, Ztied.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FRECPX--Floating-point-reciprocal-exponent--predicated--

When result and op are in different registers, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FRECPX Zresult.H, Pg/M, Zop.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FRECPX--Floating-point-reciprocal-exponent--predicated--

### Operation

Source operation ID: `SveOperation_svrecpx_f16_x`

**Operation**



Return a vector in which each active element *i* contains a floating-point value with the same sign and fractional part as `op[i]`, but with the following exponent field:




- the maximum exponent for a normal number, if `op[i]` is a zero or a denormal.
- 

a zero exponent, if `op[i]` is an infinity.



In this case, the new value will be a zero of the same sign as `op[i]`.


- 

the bitwise inverse of `op[i]`'s exponent field otherwise.



In this case, ±1.f×2^n becomes ±1.f×2^(1-n).





The inactive elements of the result have arbitrary, undefined values.



**Exceptions**



Active signaling and quiet NaNs both trigger an IEEE Invalid exception.

## svrecpx[_f16]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrecpx%5B_f16%5D_z

### Signature (source notation)

```c
svfloat16_t svrecpx[_f16]_z(svbool_t pg, svfloat16_t op);
```

### Description

Reciprocal exponent

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Reciprocal / Reciprocal exponent

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
FRECPX Zresult.H, Pg/M, Zop.H  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FRECPX--Floating-point-reciprocal-exponent--predicated--

### Operation

Source operation ID: `SveOperation_svrecpx_f16_z`

**Operation**



Return a vector in which each active element *i* contains a floating-point value with the same sign and fractional part as `op[i]`, but with the following exponent field:




- the maximum exponent for a normal number, if `op[i]` is a zero or a denormal.
- 

a zero exponent, if `op[i]` is an infinity.



In this case, the new value will be a zero of the same sign as `op[i]`.


- 

the bitwise inverse of `op[i]`'s exponent field otherwise.



In this case, ±1.f×2^n becomes ±1.f×2^(1-n).





Set the inactive elements of the result to zero.



**Exceptions**



Active signaling and quiet NaNs both trigger an IEEE Invalid exception.



**[1]** Note that `result` must be in a different register from `op`

## svrecpx[_f32]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrecpx%5B_f32%5D_m

### Signature (source notation)

```c
svfloat32_t svrecpx[_f32]_m(svfloat32_t inactive, svbool_t pg, svfloat32_t op);
```

### Description

Reciprocal exponent

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Reciprocal / Reciprocal exponent

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
FRECPX Ztied.S, Pg/M, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FRECPX--Floating-point-reciprocal-exponent--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zinactive
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FRECPX Zresult.S, Pg/M, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FRECPX--Floating-point-reciprocal-exponent--predicated--

### Operation

Source operation ID: `SveOperation_svrecpx_f16_m`

**Operation**



Return a vector in which each active element *i* contains a floating-point value with the same sign and fractional part as `op[i]`, but with the following exponent field:




- the maximum exponent for a normal number, if `op[i]` is a zero or a denormal.
- 

a zero exponent, if `op[i]` is an infinity.



In this case, the new value will be a zero of the same sign as `op[i]`.


- 

the bitwise inverse of `op[i]`'s exponent field otherwise.



In this case, ±1.f×2^n becomes ±1.f×2^(1-n).





Take the inactive elements of the result from the corresponding elements of `inactive`.



**Exceptions**



Active signaling and quiet NaNs both trigger an IEEE Invalid exception.

## svrecpx[_f32]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrecpx%5B_f32%5D_x

### Signature (source notation)

```c
svfloat32_t svrecpx[_f32]_x(svbool_t pg, svfloat32_t op);
```

### Description

Reciprocal exponent

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Reciprocal / Reciprocal exponent

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
FRECPX Ztied.S, Pg/M, Ztied.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FRECPX--Floating-point-reciprocal-exponent--predicated--

When result and op are in different registers, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FRECPX Zresult.S, Pg/M, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FRECPX--Floating-point-reciprocal-exponent--predicated--

### Operation

Source operation ID: `SveOperation_svrecpx_f16_x`

**Operation**



Return a vector in which each active element *i* contains a floating-point value with the same sign and fractional part as `op[i]`, but with the following exponent field:




- the maximum exponent for a normal number, if `op[i]` is a zero or a denormal.
- 

a zero exponent, if `op[i]` is an infinity.



In this case, the new value will be a zero of the same sign as `op[i]`.


- 

the bitwise inverse of `op[i]`'s exponent field otherwise.



In this case, ±1.f×2^n becomes ±1.f×2^(1-n).





The inactive elements of the result have arbitrary, undefined values.



**Exceptions**



Active signaling and quiet NaNs both trigger an IEEE Invalid exception.

## svrecpx[_f32]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrecpx%5B_f32%5D_z

### Signature (source notation)

```c
svfloat32_t svrecpx[_f32]_z(svbool_t pg, svfloat32_t op);
```

### Description

Reciprocal exponent

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Reciprocal / Reciprocal exponent

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
FRECPX Zresult.S, Pg/M, Zop.S  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FRECPX--Floating-point-reciprocal-exponent--predicated--

### Operation

Source operation ID: `SveOperation_svrecpx_f16_z`

**Operation**



Return a vector in which each active element *i* contains a floating-point value with the same sign and fractional part as `op[i]`, but with the following exponent field:




- the maximum exponent for a normal number, if `op[i]` is a zero or a denormal.
- 

a zero exponent, if `op[i]` is an infinity.



In this case, the new value will be a zero of the same sign as `op[i]`.


- 

the bitwise inverse of `op[i]`'s exponent field otherwise.



In this case, ±1.f×2^n becomes ±1.f×2^(1-n).





Set the inactive elements of the result to zero.



**Exceptions**



Active signaling and quiet NaNs both trigger an IEEE Invalid exception.



**[1]** Note that `result` must be in a different register from `op`

## svrecpx[_f64]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrecpx%5B_f64%5D_m

### Signature (source notation)

```c
svfloat64_t svrecpx[_f64]_m(svfloat64_t inactive, svbool_t pg, svfloat64_t op);
```

### Description

Reciprocal exponent

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Reciprocal / Reciprocal exponent

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
FRECPX Ztied.D, Pg/M, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FRECPX--Floating-point-reciprocal-exponent--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zinactive
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FRECPX Zresult.D, Pg/M, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FRECPX--Floating-point-reciprocal-exponent--predicated--

### Operation

Source operation ID: `SveOperation_svrecpx_f16_m`

**Operation**



Return a vector in which each active element *i* contains a floating-point value with the same sign and fractional part as `op[i]`, but with the following exponent field:




- the maximum exponent for a normal number, if `op[i]` is a zero or a denormal.
- 

a zero exponent, if `op[i]` is an infinity.



In this case, the new value will be a zero of the same sign as `op[i]`.


- 

the bitwise inverse of `op[i]`'s exponent field otherwise.



In this case, ±1.f×2^n becomes ±1.f×2^(1-n).





Take the inactive elements of the result from the corresponding elements of `inactive`.



**Exceptions**



Active signaling and quiet NaNs both trigger an IEEE Invalid exception.

## svrecpx[_f64]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrecpx%5B_f64%5D_x

### Signature (source notation)

```c
svfloat64_t svrecpx[_f64]_x(svbool_t pg, svfloat64_t op);
```

### Description

Reciprocal exponent

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Reciprocal / Reciprocal exponent

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
FRECPX Ztied.D, Pg/M, Ztied.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FRECPX--Floating-point-reciprocal-exponent--predicated--

When result and op are in different registers, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FRECPX Zresult.D, Pg/M, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FRECPX--Floating-point-reciprocal-exponent--predicated--

### Operation

Source operation ID: `SveOperation_svrecpx_f16_x`

**Operation**



Return a vector in which each active element *i* contains a floating-point value with the same sign and fractional part as `op[i]`, but with the following exponent field:




- the maximum exponent for a normal number, if `op[i]` is a zero or a denormal.
- 

a zero exponent, if `op[i]` is an infinity.



In this case, the new value will be a zero of the same sign as `op[i]`.


- 

the bitwise inverse of `op[i]`'s exponent field otherwise.



In this case, ±1.f×2^n becomes ±1.f×2^(1-n).





The inactive elements of the result have arbitrary, undefined values.



**Exceptions**



Active signaling and quiet NaNs both trigger an IEEE Invalid exception.

## svrecpx[_f64]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrecpx%5B_f64%5D_z

### Signature (source notation)

```c
svfloat64_t svrecpx[_f64]_z(svbool_t pg, svfloat64_t op);
```

### Description

Reciprocal exponent

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Reciprocal / Reciprocal exponent

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
FRECPX Zresult.D, Pg/M, Zop.D  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FRECPX--Floating-point-reciprocal-exponent--predicated--

### Operation

Source operation ID: `SveOperation_svrecpx_f16_z`

**Operation**



Return a vector in which each active element *i* contains a floating-point value with the same sign and fractional part as `op[i]`, but with the following exponent field:




- the maximum exponent for a normal number, if `op[i]` is a zero or a denormal.
- 

a zero exponent, if `op[i]` is an infinity.



In this case, the new value will be a zero of the same sign as `op[i]`.


- 

the bitwise inverse of `op[i]`'s exponent field otherwise.



In this case, ±1.f×2^n becomes ±1.f×2^(1-n).





Set the inactive elements of the result to zero.



**Exceptions**



Active signaling and quiet NaNs both trigger an IEEE Invalid exception.



**[1]** Note that `result` must be in a different register from `op`

