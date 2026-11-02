# SME / Data type conversion / Conversions — Part 1

## svcvt_bf16[_f32]_m

ISA classification: SME + FEAT_BF16

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvt_bf16%5B_f32%5D_m

### Signature (source notation)

```c
svbfloat16_t svcvt_bf16[_f32]_m(svbfloat16_t inactive, svbool_t pg, svfloat32_t op);
```

### Description

Floating-point convert

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Data type conversion / Conversions

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME,FEAT_BF16
```

### Return type metadata

```json
{
  "return_base_type": "bfloat",
  "element_bit_size": "16",
  "value": "svbfloat16_t"
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
    "register": "Zop.S"
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
BFCVT Ztied.H, Pg/M, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BFCVT--Single-precision-down-convert-to-BFloat16-format--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zinactive
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
BFCVT Zresult.H, Pg/M, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BFCVT--Single-precision-down-convert-to-BFloat16-format--predicated--

### Operation

Source operation ID: `SveOperation_svcvt_bf16_f32_m`

**Operation**



Convert each active element `op[i]` to `bfloat16_t`, rounding according to the current rounding mode. Return the converted value in element `i * 2` of the result vector and return zero in element `i * 2 + 1`.



Take the inactive elements of the result from the corresponding elements of `inactive`.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.

## svcvt_bf16[_f32]_x

ISA classification: SME + FEAT_BF16

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvt_bf16%5B_f32%5D_x

### Signature (source notation)

```c
svbfloat16_t svcvt_bf16[_f32]_x(svbool_t pg, svfloat32_t op);
```

### Description

Floating-point convert

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Data type conversion / Conversions

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME,FEAT_BF16
```

### Return type metadata

```json
{
  "return_base_type": "bfloat",
  "element_bit_size": "16",
  "value": "svbfloat16_t"
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
    "Zresult.H|Ztied.H": "result"
  }
]
```

### Instruction mapping

When result and op are in the same register, this intrinsic compiles to:

```asm
BFCVT Ztied.H, Pg/M, Ztied.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BFCVT--Single-precision-down-convert-to-BFloat16-format--predicated--

When result and op are in different registers, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
BFCVT Zresult.H, Pg/M, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BFCVT--Single-precision-down-convert-to-BFloat16-format--predicated--

### Operation

Source operation ID: `SveOperation_svcvt_bf16_f32_x`

**Operation**



Convert each active element `op[i]` to `bfloat16_t`, rounding according to the current rounding mode. Return the converted value in element `i * 2` of the result vector and return zero in element `i * 2 + 1`.



The inactive elements of the result have arbitrary, undefined values.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.

## svcvt_bf16[_f32]_z

ISA classification: SME + FEAT_BF16

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvt_bf16%5B_f32%5D_z

### Signature (source notation)

```c
svbfloat16_t svcvt_bf16[_f32]_z(svbool_t pg, svfloat32_t op);
```

### Description

Floating-point convert

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Data type conversion / Conversions

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME,FEAT_BF16
```

### Return type metadata

```json
{
  "return_base_type": "bfloat",
  "element_bit_size": "16",
  "value": "svbfloat16_t"
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
    "Zresult.H": "result"
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
BFCVT Zresult.H, Pg/M, Zop.S  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BFCVT--Single-precision-down-convert-to-BFloat16-format--predicated--

### Operation

Source operation ID: `SveOperation_svcvt_bf16_f32_z`

**Operation**



Convert each active element `op[i]` to `bfloat16_t`, rounding according to the current rounding mode. Return the converted value in element `i * 2` of the result vector and return zero in element `i * 2 + 1`.



Set the inactive elements of the result to zero.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.



**[1]** Note that `result` must be in a different register from `op`

## svcvt_f16[_f32]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvt_f16%5B_f32%5D_m

### Signature (source notation)

```c
svfloat16_t svcvt_f16[_f32]_m(svfloat16_t inactive, svbool_t pg, svfloat32_t op);
```

### Description

Floating-point convert

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Data type conversion / Conversions

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
    "register": "Zop.S"
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
FCVT Ztied.H, Pg/M, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCVT--Floating-point-convert-precision--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zinactive
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FCVT Zresult.H, Pg/M, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCVT--Floating-point-convert-precision--predicated--

### Operation

Source operation ID: `SveOperation_svcvt_f16_f32_m`

**Operation**



Convert each active element `op[i]` to `float16_t`, rounding according to the current rounding mode. Return the converted value in element `i * 2` of the result vector and return zero in element `i * 2 + 1`.



Take the inactive elements of the result from the corresponding elements of `inactive`.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.

## svcvt_f16[_f32]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvt_f16%5B_f32%5D_x

### Signature (source notation)

```c
svfloat16_t svcvt_f16[_f32]_x(svbool_t pg, svfloat32_t op);
```

### Description

Floating-point convert

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Data type conversion / Conversions

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
    "register": "Zop.S|Ztied.S"
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
FCVT Ztied.H, Pg/M, Ztied.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCVT--Floating-point-convert-precision--predicated--

When result and op are in different registers, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FCVT Zresult.H, Pg/M, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCVT--Floating-point-convert-precision--predicated--

### Operation

Source operation ID: `SveOperation_svcvt_f16_f32_x`

**Operation**



Convert each active element `op[i]` to `float16_t`, rounding according to the current rounding mode. Return the converted value in element `i * 2` of the result vector and return zero in element `i * 2 + 1`.



The inactive elements of the result have arbitrary, undefined values.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.

## svcvt_f16[_f32]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvt_f16%5B_f32%5D_z

### Signature (source notation)

```c
svfloat16_t svcvt_f16[_f32]_z(svbool_t pg, svfloat32_t op);
```

### Description

Floating-point convert

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Data type conversion / Conversions

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
    "register": "Zop.S"
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
MOVPRFX Zresult.S, Pg/Z, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
FCVT Zresult.H, Pg/M, Zop.S  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCVT--Floating-point-convert-precision--predicated--

### Operation

Source operation ID: `SveOperation_svcvt_f16_f32_z`

**Operation**



Convert each active element `op[i]` to `float16_t`, rounding according to the current rounding mode. Return the converted value in element `i * 2` of the result vector and return zero in element `i * 2 + 1`.



Set the inactive elements of the result to zero.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.



**[1]** Note that `result` must be in a different register from `op`

## svcvt_f16[_f64]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvt_f16%5B_f64%5D_m

### Signature (source notation)

```c
svfloat16_t svcvt_f16[_f64]_m(svfloat16_t inactive, svbool_t pg, svfloat64_t op);
```

### Description

Floating-point convert

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Data type conversion / Conversions

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
    "register": "Zop.D"
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
FCVT Ztied.H, Pg/M, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCVT--Floating-point-convert-precision--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zinactive
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FCVT Zresult.H, Pg/M, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCVT--Floating-point-convert-precision--predicated--

### Operation

Source operation ID: `SveOperation_svcvt_f16_f64_m`

**Operation**



Convert each active element `op[i]` to `float16_t`, rounding according to the current rounding mode. Return the converted value in element `i * 4` of the result vector, setting elements `i * 4 + 1`, `i * 4 + 2`, and `i * 4 + 3` to zero. Take the inactive elements of the result from the corresponding elements of `inactive`.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.

## svcvt_f16[_f64]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvt_f16%5B_f64%5D_x

### Signature (source notation)

```c
svfloat16_t svcvt_f16[_f64]_x(svbool_t pg, svfloat64_t op);
```

### Description

Floating-point convert

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Data type conversion / Conversions

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
    "register": "Zop.D|Ztied.D"
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
FCVT Ztied.H, Pg/M, Ztied.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCVT--Floating-point-convert-precision--predicated--

When result and op are in different registers, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FCVT Zresult.H, Pg/M, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCVT--Floating-point-convert-precision--predicated--

### Operation

Source operation ID: `SveOperation_svcvt_f16_f64_x`

**Operation**



Convert each active element `op[i]` to `float16_t`, rounding according to the current rounding mode. Return the converted value in element `i * 4` of the result vector, setting elements `i * 4 + 1`, `i * 4 + 2`, and `i * 4 + 3` to zero. The inactive elements of the result have arbitrary, undefined values.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.

## svcvt_f16[_f64]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvt_f16%5B_f64%5D_z

### Signature (source notation)

```c
svfloat16_t svcvt_f16[_f64]_z(svbool_t pg, svfloat64_t op);
```

### Description

Floating-point convert

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Data type conversion / Conversions

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
    "register": "Zop.D"
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
MOVPRFX Zresult.D, Pg/Z, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
FCVT Zresult.H, Pg/M, Zop.D  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCVT--Floating-point-convert-precision--predicated--

### Operation

Source operation ID: `SveOperation_svcvt_f16_f64_z`

**Operation**



Convert each active element `op[i]` to `float16_t`, rounding according to the current rounding mode. Return the converted value in element `i * 4` of the result vector, setting elements `i * 4 + 1`, `i * 4 + 2`, and `i * 4 + 3` to zero. Set the inactive elements of the result to zero.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.



**[1]** Note that `result` must be in a different register from `op`

## svcvt_f16[_s16]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvt_f16%5B_s16%5D_m

### Signature (source notation)

```c
svfloat16_t svcvt_f16[_s16]_m(svfloat16_t inactive, svbool_t pg, svint16_t op);
```

### Description

Floating-point convert

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Data type conversion / Conversions

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
SCVTF Ztied.H, Pg/M, Zop.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SCVTF--predicated---Signed-integer-convert-to-floating-point--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zinactive
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SCVTF Zresult.H, Pg/M, Zop.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SCVTF--predicated---Signed-integer-convert-to-floating-point--predicated--

### Operation

Source operation ID: `SveOperation_svcvt_f16_s16_m`

**Operation**



Return a vector in which each active element *i* contains `(float16_t)op[i]`, rounding according to the current rounding mode. Take the inactive elements of the result from the corresponding elements of `inactive`.

## svcvt_f16[_s16]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvt_f16%5B_s16%5D_x

### Signature (source notation)

```c
svfloat16_t svcvt_f16[_s16]_x(svbool_t pg, svint16_t op);
```

### Description

Floating-point convert

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Data type conversion / Conversions

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
SCVTF Ztied.H, Pg/M, Ztied.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SCVTF--predicated---Signed-integer-convert-to-floating-point--predicated--

When result and op are in different registers, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SCVTF Zresult.H, Pg/M, Zop.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SCVTF--predicated---Signed-integer-convert-to-floating-point--predicated--

### Operation

Source operation ID: `SveOperation_svcvt_f16_s16_x`

**Operation**



Return a vector in which each active element *i* contains `(float16_t)op[i]`, rounding according to the current rounding mode. The inactive elements of the result have arbitrary, undefined values.

## svcvt_f16[_s16]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvt_f16%5B_s16%5D_z

### Signature (source notation)

```c
svfloat16_t svcvt_f16[_s16]_z(svbool_t pg, svint16_t op);
```

### Description

Floating-point convert

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Data type conversion / Conversions

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
SCVTF Zresult.H, Pg/M, Zop.H  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SCVTF--predicated---Signed-integer-convert-to-floating-point--predicated--

### Operation

Source operation ID: `SveOperation_svcvt_f16_s16_z`

**Operation**



Return a vector in which each active element *i* contains `(float16_t)op[i]`, rounding according to the current rounding mode. Set the inactive elements of the result to zero.



**[1]** Note that `result` must be in a different register from `op`

## svcvt_f16[_s32]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvt_f16%5B_s32%5D_m

### Signature (source notation)

```c
svfloat16_t svcvt_f16[_s32]_m(svfloat16_t inactive, svbool_t pg, svint32_t op);
```

### Description

Floating-point convert

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Data type conversion / Conversions

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
    "register": "Zop.S"
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
SCVTF Ztied.H, Pg/M, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SCVTF--predicated---Signed-integer-convert-to-floating-point--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zinactive
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SCVTF Zresult.H, Pg/M, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SCVTF--predicated---Signed-integer-convert-to-floating-point--predicated--

### Operation

Source operation ID: `SveOperation_svcvt_f16_s32_m`

**Operation**



Convert each active element `op[i]` to `float16_t`, rounding according to the current rounding mode. Return the converted value in element `i * 2` of the result vector and return zero in element `i * 2 + 1`.



Take the inactive elements of the result from the corresponding elements of `inactive`.

## svcvt_f16[_s32]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvt_f16%5B_s32%5D_x

### Signature (source notation)

```c
svfloat16_t svcvt_f16[_s32]_x(svbool_t pg, svint32_t op);
```

### Description

Floating-point convert

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Data type conversion / Conversions

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
    "register": "Zop.S|Ztied.S"
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
SCVTF Ztied.H, Pg/M, Ztied.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SCVTF--predicated---Signed-integer-convert-to-floating-point--predicated--

When result and op are in different registers, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SCVTF Zresult.H, Pg/M, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SCVTF--predicated---Signed-integer-convert-to-floating-point--predicated--

### Operation

Source operation ID: `SveOperation_svcvt_f16_s32_x`

**Operation**



Convert each active element `op[i]` to `float16_t`, rounding according to the current rounding mode. Return the converted value in element `i * 2` of the result vector and return zero in element `i * 2 + 1`.



The inactive elements of the result have arbitrary, undefined values.

## svcvt_f16[_s32]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvt_f16%5B_s32%5D_z

### Signature (source notation)

```c
svfloat16_t svcvt_f16[_s32]_z(svbool_t pg, svint32_t op);
```

### Description

Floating-point convert

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Data type conversion / Conversions

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
    "register": "Zop.S"
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
MOVPRFX Zresult.S, Pg/Z, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
SCVTF Zresult.H, Pg/M, Zop.S  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SCVTF--predicated---Signed-integer-convert-to-floating-point--predicated--

### Operation

Source operation ID: `SveOperation_svcvt_f16_s32_z`

**Operation**



Convert each active element `op[i]` to `float16_t`, rounding according to the current rounding mode. Return the converted value in element `i * 2` of the result vector and return zero in element `i * 2 + 1`.



Set the inactive elements of the result to zero.



**[1]** Note that `result` must be in a different register from `op`

## svcvt_f16[_s64]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvt_f16%5B_s64%5D_m

### Signature (source notation)

```c
svfloat16_t svcvt_f16[_s64]_m(svfloat16_t inactive, svbool_t pg, svint64_t op);
```

### Description

Floating-point convert

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Data type conversion / Conversions

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
    "register": "Zop.D"
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
SCVTF Ztied.H, Pg/M, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SCVTF--predicated---Signed-integer-convert-to-floating-point--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zinactive
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SCVTF Zresult.H, Pg/M, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SCVTF--predicated---Signed-integer-convert-to-floating-point--predicated--

### Operation

Source operation ID: `SveOperation_svcvt_f16_s64_m`

**Operation**



Convert each active element `op[i]` to `float16_t`, rounding according to the current rounding mode. Return the converted value in element `i * 4` of the result vector, setting elements `i * 4 + 1`, `i * 4 + 2`, and `i * 4 + 3` to zero. Take the inactive elements of the result from the corresponding elements of `inactive`.

## svcvt_f16[_s64]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvt_f16%5B_s64%5D_x

### Signature (source notation)

```c
svfloat16_t svcvt_f16[_s64]_x(svbool_t pg, svint64_t op);
```

### Description

Floating-point convert

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Data type conversion / Conversions

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
    "register": "Zop.D|Ztied.D"
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
SCVTF Ztied.H, Pg/M, Ztied.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SCVTF--predicated---Signed-integer-convert-to-floating-point--predicated--

When result and op are in different registers, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SCVTF Zresult.H, Pg/M, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SCVTF--predicated---Signed-integer-convert-to-floating-point--predicated--

### Operation

Source operation ID: `SveOperation_svcvt_f16_s64_x`

**Operation**



Convert each active element `op[i]` to `float16_t`, rounding according to the current rounding mode. Return the converted value in element `i * 4` of the result vector, setting elements `i * 4 + 1`, `i * 4 + 2`, and `i * 4 + 3` to zero. The inactive elements of the result have arbitrary, undefined values.

## svcvt_f16[_s64]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvt_f16%5B_s64%5D_z

### Signature (source notation)

```c
svfloat16_t svcvt_f16[_s64]_z(svbool_t pg, svint64_t op);
```

### Description

Floating-point convert

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Data type conversion / Conversions

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
    "register": "Zop.D"
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
MOVPRFX Zresult.D, Pg/Z, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
SCVTF Zresult.H, Pg/M, Zop.D  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SCVTF--predicated---Signed-integer-convert-to-floating-point--predicated--

### Operation

Source operation ID: `SveOperation_svcvt_f16_s64_z`

**Operation**



Convert each active element `op[i]` to `float16_t`, rounding according to the current rounding mode. Return the converted value in element `i * 4` of the result vector, setting elements `i * 4 + 1`, `i * 4 + 2`, and `i * 4 + 3` to zero. Set the inactive elements of the result to zero.



**[1]** Note that `result` must be in a different register from `op`

## svcvt_f16[_u16]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvt_f16%5B_u16%5D_m

### Signature (source notation)

```c
svfloat16_t svcvt_f16[_u16]_m(svfloat16_t inactive, svbool_t pg, svuint16_t op);
```

### Description

Floating-point convert

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Data type conversion / Conversions

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
UCVTF Ztied.H, Pg/M, Zop.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UCVTF--predicated---Unsigned-integer-convert-to-floating-point--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zinactive
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
UCVTF Zresult.H, Pg/M, Zop.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UCVTF--predicated---Unsigned-integer-convert-to-floating-point--predicated--

### Operation

Source operation ID: `SveOperation_svcvt_f16_s16_m`

**Operation**



Return a vector in which each active element *i* contains `(float16_t)op[i]`, rounding according to the current rounding mode. Take the inactive elements of the result from the corresponding elements of `inactive`.

## svcvt_f16[_u16]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvt_f16%5B_u16%5D_x

### Signature (source notation)

```c
svfloat16_t svcvt_f16[_u16]_x(svbool_t pg, svuint16_t op);
```

### Description

Floating-point convert

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Data type conversion / Conversions

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
UCVTF Ztied.H, Pg/M, Ztied.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UCVTF--predicated---Unsigned-integer-convert-to-floating-point--predicated--

When result and op are in different registers, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
UCVTF Zresult.H, Pg/M, Zop.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UCVTF--predicated---Unsigned-integer-convert-to-floating-point--predicated--

### Operation

Source operation ID: `SveOperation_svcvt_f16_s16_x`

**Operation**



Return a vector in which each active element *i* contains `(float16_t)op[i]`, rounding according to the current rounding mode. The inactive elements of the result have arbitrary, undefined values.

## svcvt_f16[_u16]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvt_f16%5B_u16%5D_z

### Signature (source notation)

```c
svfloat16_t svcvt_f16[_u16]_z(svbool_t pg, svuint16_t op);
```

### Description

Floating-point convert

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Data type conversion / Conversions

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
UCVTF Zresult.H, Pg/M, Zop.H  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UCVTF--predicated---Unsigned-integer-convert-to-floating-point--predicated--

### Operation

Source operation ID: `SveOperation_svcvt_f16_s16_z`

**Operation**



Return a vector in which each active element *i* contains `(float16_t)op[i]`, rounding according to the current rounding mode. Set the inactive elements of the result to zero.



**[1]** Note that `result` must be in a different register from `op`

## svcvt_f16[_u32]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvt_f16%5B_u32%5D_m

### Signature (source notation)

```c
svfloat16_t svcvt_f16[_u32]_m(svfloat16_t inactive, svbool_t pg, svuint32_t op);
```

### Description

Floating-point convert

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Data type conversion / Conversions

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
    "register": "Zop.S"
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
UCVTF Ztied.H, Pg/M, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UCVTF--predicated---Unsigned-integer-convert-to-floating-point--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zinactive
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
UCVTF Zresult.H, Pg/M, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UCVTF--predicated---Unsigned-integer-convert-to-floating-point--predicated--

### Operation

Source operation ID: `SveOperation_svcvt_f16_s32_m`

**Operation**



Convert each active element `op[i]` to `float16_t`, rounding according to the current rounding mode. Return the converted value in element `i * 2` of the result vector and return zero in element `i * 2 + 1`.



Take the inactive elements of the result from the corresponding elements of `inactive`.

## svcvt_f16[_u32]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvt_f16%5B_u32%5D_x

### Signature (source notation)

```c
svfloat16_t svcvt_f16[_u32]_x(svbool_t pg, svuint32_t op);
```

### Description

Floating-point convert

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Data type conversion / Conversions

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
    "register": "Zop.S|Ztied.S"
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
UCVTF Ztied.H, Pg/M, Ztied.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UCVTF--predicated---Unsigned-integer-convert-to-floating-point--predicated--

When result and op are in different registers, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
UCVTF Zresult.H, Pg/M, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UCVTF--predicated---Unsigned-integer-convert-to-floating-point--predicated--

### Operation

Source operation ID: `SveOperation_svcvt_f16_s32_x`

**Operation**



Convert each active element `op[i]` to `float16_t`, rounding according to the current rounding mode. Return the converted value in element `i * 2` of the result vector and return zero in element `i * 2 + 1`.



The inactive elements of the result have arbitrary, undefined values.

## svcvt_f16[_u32]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvt_f16%5B_u32%5D_z

### Signature (source notation)

```c
svfloat16_t svcvt_f16[_u32]_z(svbool_t pg, svuint32_t op);
```

### Description

Floating-point convert

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Data type conversion / Conversions

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
    "register": "Zop.S"
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
MOVPRFX Zresult.S, Pg/Z, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
UCVTF Zresult.H, Pg/M, Zop.S  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UCVTF--predicated---Unsigned-integer-convert-to-floating-point--predicated--

### Operation

Source operation ID: `SveOperation_svcvt_f16_s32_z`

**Operation**



Convert each active element `op[i]` to `float16_t`, rounding according to the current rounding mode. Return the converted value in element `i * 2` of the result vector and return zero in element `i * 2 + 1`.



Set the inactive elements of the result to zero.



**[1]** Note that `result` must be in a different register from `op`

## svcvt_f16[_u64]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvt_f16%5B_u64%5D_m

### Signature (source notation)

```c
svfloat16_t svcvt_f16[_u64]_m(svfloat16_t inactive, svbool_t pg, svuint64_t op);
```

### Description

Floating-point convert

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Data type conversion / Conversions

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
    "register": "Zop.D"
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
UCVTF Ztied.H, Pg/M, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UCVTF--predicated---Unsigned-integer-convert-to-floating-point--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zinactive
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
UCVTF Zresult.H, Pg/M, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UCVTF--predicated---Unsigned-integer-convert-to-floating-point--predicated--

### Operation

Source operation ID: `SveOperation_svcvt_f16_s64_m`

**Operation**



Convert each active element `op[i]` to `float16_t`, rounding according to the current rounding mode. Return the converted value in element `i * 4` of the result vector, setting elements `i * 4 + 1`, `i * 4 + 2`, and `i * 4 + 3` to zero. Take the inactive elements of the result from the corresponding elements of `inactive`.

## svcvt_f16[_u64]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvt_f16%5B_u64%5D_x

### Signature (source notation)

```c
svfloat16_t svcvt_f16[_u64]_x(svbool_t pg, svuint64_t op);
```

### Description

Floating-point convert

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Data type conversion / Conversions

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
    "register": "Zop.D|Ztied.D"
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
UCVTF Ztied.H, Pg/M, Ztied.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UCVTF--predicated---Unsigned-integer-convert-to-floating-point--predicated--

When result and op are in different registers, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
UCVTF Zresult.H, Pg/M, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UCVTF--predicated---Unsigned-integer-convert-to-floating-point--predicated--

### Operation

Source operation ID: `SveOperation_svcvt_f16_s64_x`

**Operation**



Convert each active element `op[i]` to `float16_t`, rounding according to the current rounding mode. Return the converted value in element `i * 4` of the result vector, setting elements `i * 4 + 1`, `i * 4 + 2`, and `i * 4 + 3` to zero. The inactive elements of the result have arbitrary, undefined values.

## svcvt_f16[_u64]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvt_f16%5B_u64%5D_z

### Signature (source notation)

```c
svfloat16_t svcvt_f16[_u64]_z(svbool_t pg, svuint64_t op);
```

### Description

Floating-point convert

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Data type conversion / Conversions

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
    "register": "Zop.D"
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
MOVPRFX Zresult.D, Pg/Z, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
UCVTF Zresult.H, Pg/M, Zop.D  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UCVTF--predicated---Unsigned-integer-convert-to-floating-point--predicated--

### Operation

Source operation ID: `SveOperation_svcvt_f16_s64_z`

**Operation**



Convert each active element `op[i]` to `float16_t`, rounding according to the current rounding mode. Return the converted value in element `i * 4` of the result vector, setting elements `i * 4 + 1`, `i * 4 + 2`, and `i * 4 + 3` to zero. Set the inactive elements of the result to zero.



**[1]** Note that `result` must be in a different register from `op`

## svcvt_f32[_f16]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvt_f32%5B_f16%5D_m

### Signature (source notation)

```c
svfloat32_t svcvt_f32[_f16]_m(svfloat32_t inactive, svbool_t pg, svfloat16_t op);
```

### Description

Floating-point convert

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Data type conversion / Conversions

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
    "register": "Zop.H"
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
FCVT Ztied.S, Pg/M, Zop.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCVT--Floating-point-convert-precision--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zinactive
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FCVT Zresult.S, Pg/M, Zop.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCVT--Floating-point-convert-precision--predicated--

### Operation

Source operation ID: `SveOperation_svcvt_f32_f16_m`

**Operation**



Return a vector in which each active element *i* contains `(float32_t)op[i * 2]`. Take the inactive elements of the result from the corresponding elements of `inactive`.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.

## svcvt_f32[_f16]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvt_f32%5B_f16%5D_x

### Signature (source notation)

```c
svfloat32_t svcvt_f32[_f16]_x(svbool_t pg, svfloat16_t op);
```

### Description

Floating-point convert

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Data type conversion / Conversions

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
    "register": "Zop.H|Ztied.H"
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
FCVT Ztied.S, Pg/M, Ztied.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCVT--Floating-point-convert-precision--predicated--

When result and op are in different registers, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FCVT Zresult.S, Pg/M, Zop.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCVT--Floating-point-convert-precision--predicated--

### Operation

Source operation ID: `SveOperation_svcvt_f32_f16_x`

**Operation**



Return a vector in which each active element *i* contains `(float32_t)op[i * 2]`. The inactive elements of the result have arbitrary, undefined values.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.

## svcvt_f32[_f16]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvt_f32%5B_f16%5D_z

### Signature (source notation)

```c
svfloat32_t svcvt_f32[_f16]_z(svbool_t pg, svfloat16_t op);
```

### Description

Floating-point convert

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Data type conversion / Conversions

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
    "register": "Zop.H"
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
FCVT Zresult.S, Pg/M, Zop.H  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCVT--Floating-point-convert-precision--predicated--

### Operation

Source operation ID: `SveOperation_svcvt_f32_f16_z`

**Operation**



Return a vector in which each active element *i* contains `(float32_t)op[i * 2]`. Set the inactive elements of the result to zero.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.



**[1]** Note that `result` must be in a different register from `op`

## svcvt_f32[_f64]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvt_f32%5B_f64%5D_m

### Signature (source notation)

```c
svfloat32_t svcvt_f32[_f64]_m(svfloat32_t inactive, svbool_t pg, svfloat64_t op);
```

### Description

Floating-point convert

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Data type conversion / Conversions

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
    "register": "Zop.D"
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
FCVT Ztied.S, Pg/M, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCVT--Floating-point-convert-precision--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zinactive
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FCVT Zresult.S, Pg/M, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCVT--Floating-point-convert-precision--predicated--

### Operation

Source operation ID: `SveOperation_svcvt_f32_f64_m`

**Operation**



Convert each active element `op[i]` to `float32_t`, rounding according to the current rounding mode. Return the converted value in element `i * 2` of the result vector and return zero in element `i * 2 + 1`.



Take the inactive elements of the result from the corresponding elements of `inactive`.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.

## svcvt_f32[_f64]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvt_f32%5B_f64%5D_x

### Signature (source notation)

```c
svfloat32_t svcvt_f32[_f64]_x(svbool_t pg, svfloat64_t op);
```

### Description

Floating-point convert

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Data type conversion / Conversions

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
    "register": "Zop.D|Ztied.D"
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
FCVT Ztied.S, Pg/M, Ztied.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCVT--Floating-point-convert-precision--predicated--

When result and op are in different registers, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FCVT Zresult.S, Pg/M, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCVT--Floating-point-convert-precision--predicated--

### Operation

Source operation ID: `SveOperation_svcvt_f32_f64_x`

**Operation**



Convert each active element `op[i]` to `float32_t`, rounding according to the current rounding mode. Return the converted value in element `i * 2` of the result vector and return zero in element `i * 2 + 1`.



The inactive elements of the result have arbitrary, undefined values.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.

## svcvt_f32[_f64]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvt_f32%5B_f64%5D_z

### Signature (source notation)

```c
svfloat32_t svcvt_f32[_f64]_z(svbool_t pg, svfloat64_t op);
```

### Description

Floating-point convert

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Data type conversion / Conversions

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
    "register": "Zop.D"
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
MOVPRFX Zresult.D, Pg/Z, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
FCVT Zresult.S, Pg/M, Zop.D  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCVT--Floating-point-convert-precision--predicated--

### Operation

Source operation ID: `SveOperation_svcvt_f32_f64_z`

**Operation**



Convert each active element `op[i]` to `float32_t`, rounding according to the current rounding mode. Return the converted value in element `i * 2` of the result vector and return zero in element `i * 2 + 1`.



Set the inactive elements of the result to zero.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.



**[1]** Note that `result` must be in a different register from `op`

## svcvt_f32[_s32]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvt_f32%5B_s32%5D_m

### Signature (source notation)

```c
svfloat32_t svcvt_f32[_s32]_m(svfloat32_t inactive, svbool_t pg, svint32_t op);
```

### Description

Floating-point convert

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Data type conversion / Conversions

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
SCVTF Ztied.S, Pg/M, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SCVTF--predicated---Signed-integer-convert-to-floating-point--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zinactive
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SCVTF Zresult.S, Pg/M, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SCVTF--predicated---Signed-integer-convert-to-floating-point--predicated--

### Operation

Source operation ID: `SveOperation_svcvt_f32_s32_m`

**Operation**



Return a vector in which each active element *i* contains `(float32_t)op[i]`, rounding according to the current rounding mode. Take the inactive elements of the result from the corresponding elements of `inactive`.

## svcvt_f32[_s32]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvt_f32%5B_s32%5D_x

### Signature (source notation)

```c
svfloat32_t svcvt_f32[_s32]_x(svbool_t pg, svint32_t op);
```

### Description

Floating-point convert

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Data type conversion / Conversions

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
SCVTF Ztied.S, Pg/M, Ztied.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SCVTF--predicated---Signed-integer-convert-to-floating-point--predicated--

When result and op are in different registers, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SCVTF Zresult.S, Pg/M, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SCVTF--predicated---Signed-integer-convert-to-floating-point--predicated--

### Operation

Source operation ID: `SveOperation_svcvt_f32_s32_x`

**Operation**



Return a vector in which each active element *i* contains `(float32_t)op[i]`, rounding according to the current rounding mode. The inactive elements of the result have arbitrary, undefined values.

## svcvt_f32[_s32]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvt_f32%5B_s32%5D_z

### Signature (source notation)

```c
svfloat32_t svcvt_f32[_s32]_z(svbool_t pg, svint32_t op);
```

### Description

Floating-point convert

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Data type conversion / Conversions

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
SCVTF Zresult.S, Pg/M, Zop.S  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SCVTF--predicated---Signed-integer-convert-to-floating-point--predicated--

### Operation

Source operation ID: `SveOperation_svcvt_f32_s32_z`

**Operation**



Return a vector in which each active element *i* contains `(float32_t)op[i]`, rounding according to the current rounding mode. Set the inactive elements of the result to zero.



**[1]** Note that `result` must be in a different register from `op`

## svcvt_f32[_s64]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvt_f32%5B_s64%5D_m

### Signature (source notation)

```c
svfloat32_t svcvt_f32[_s64]_m(svfloat32_t inactive, svbool_t pg, svint64_t op);
```

### Description

Floating-point convert

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Data type conversion / Conversions

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
    "register": "Zop.D"
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
SCVTF Ztied.S, Pg/M, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SCVTF--predicated---Signed-integer-convert-to-floating-point--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zinactive
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SCVTF Zresult.S, Pg/M, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SCVTF--predicated---Signed-integer-convert-to-floating-point--predicated--

### Operation

Source operation ID: `SveOperation_svcvt_f32_s64_m`

**Operation**



Convert each active element `op[i]` to `float32_t`, rounding according to the current rounding mode. Return the converted value in element `i * 2` of the result vector and return zero in element `i * 2 + 1`.



Take the inactive elements of the result from the corresponding elements of `inactive`.

## svcvt_f32[_s64]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvt_f32%5B_s64%5D_x

### Signature (source notation)

```c
svfloat32_t svcvt_f32[_s64]_x(svbool_t pg, svint64_t op);
```

### Description

Floating-point convert

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Data type conversion / Conversions

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
    "register": "Zop.D|Ztied.D"
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
SCVTF Ztied.S, Pg/M, Ztied.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SCVTF--predicated---Signed-integer-convert-to-floating-point--predicated--

When result and op are in different registers, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SCVTF Zresult.S, Pg/M, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SCVTF--predicated---Signed-integer-convert-to-floating-point--predicated--

### Operation

Source operation ID: `SveOperation_svcvt_f32_s64_x`

**Operation**



Convert each active element `op[i]` to `float32_t`, rounding according to the current rounding mode. Return the converted value in element `i * 2` of the result vector and return zero in element `i * 2 + 1`.



The inactive elements of the result have arbitrary, undefined values.

## svcvt_f32[_s64]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvt_f32%5B_s64%5D_z

### Signature (source notation)

```c
svfloat32_t svcvt_f32[_s64]_z(svbool_t pg, svint64_t op);
```

### Description

Floating-point convert

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Data type conversion / Conversions

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
    "register": "Zop.D"
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
MOVPRFX Zresult.D, Pg/Z, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
SCVTF Zresult.S, Pg/M, Zop.D  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SCVTF--predicated---Signed-integer-convert-to-floating-point--predicated--

### Operation

Source operation ID: `SveOperation_svcvt_f32_s64_z`

**Operation**



Convert each active element `op[i]` to `float32_t`, rounding according to the current rounding mode. Return the converted value in element `i * 2` of the result vector and return zero in element `i * 2 + 1`.



Set the inactive elements of the result to zero.



**[1]** Note that `result` must be in a different register from `op`

## svcvt_f32[_u32]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvt_f32%5B_u32%5D_m

### Signature (source notation)

```c
svfloat32_t svcvt_f32[_u32]_m(svfloat32_t inactive, svbool_t pg, svuint32_t op);
```

### Description

Floating-point convert

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Data type conversion / Conversions

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
UCVTF Ztied.S, Pg/M, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UCVTF--predicated---Unsigned-integer-convert-to-floating-point--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zinactive
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
UCVTF Zresult.S, Pg/M, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UCVTF--predicated---Unsigned-integer-convert-to-floating-point--predicated--

### Operation

Source operation ID: `SveOperation_svcvt_f32_s32_m`

**Operation**



Return a vector in which each active element *i* contains `(float32_t)op[i]`, rounding according to the current rounding mode. Take the inactive elements of the result from the corresponding elements of `inactive`.

## svcvt_f32[_u32]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvt_f32%5B_u32%5D_x

### Signature (source notation)

```c
svfloat32_t svcvt_f32[_u32]_x(svbool_t pg, svuint32_t op);
```

### Description

Floating-point convert

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Data type conversion / Conversions

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
UCVTF Ztied.S, Pg/M, Ztied.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UCVTF--predicated---Unsigned-integer-convert-to-floating-point--predicated--

When result and op are in different registers, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
UCVTF Zresult.S, Pg/M, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UCVTF--predicated---Unsigned-integer-convert-to-floating-point--predicated--

### Operation

Source operation ID: `SveOperation_svcvt_f32_s32_x`

**Operation**



Return a vector in which each active element *i* contains `(float32_t)op[i]`, rounding according to the current rounding mode. The inactive elements of the result have arbitrary, undefined values.

## svcvt_f32[_u32]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvt_f32%5B_u32%5D_z

### Signature (source notation)

```c
svfloat32_t svcvt_f32[_u32]_z(svbool_t pg, svuint32_t op);
```

### Description

Floating-point convert

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Data type conversion / Conversions

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
UCVTF Zresult.S, Pg/M, Zop.S  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UCVTF--predicated---Unsigned-integer-convert-to-floating-point--predicated--

### Operation

Source operation ID: `SveOperation_svcvt_f32_s32_z`

**Operation**



Return a vector in which each active element *i* contains `(float32_t)op[i]`, rounding according to the current rounding mode. Set the inactive elements of the result to zero.



**[1]** Note that `result` must be in a different register from `op`

## svcvt_f32[_u64]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvt_f32%5B_u64%5D_m

### Signature (source notation)

```c
svfloat32_t svcvt_f32[_u64]_m(svfloat32_t inactive, svbool_t pg, svuint64_t op);
```

### Description

Floating-point convert

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Data type conversion / Conversions

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
    "register": "Zop.D"
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
UCVTF Ztied.S, Pg/M, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UCVTF--predicated---Unsigned-integer-convert-to-floating-point--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zinactive
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
UCVTF Zresult.S, Pg/M, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UCVTF--predicated---Unsigned-integer-convert-to-floating-point--predicated--

### Operation

Source operation ID: `SveOperation_svcvt_f32_s64_m`

**Operation**



Convert each active element `op[i]` to `float32_t`, rounding according to the current rounding mode. Return the converted value in element `i * 2` of the result vector and return zero in element `i * 2 + 1`.



Take the inactive elements of the result from the corresponding elements of `inactive`.

## svcvt_f32[_u64]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvt_f32%5B_u64%5D_x

### Signature (source notation)

```c
svfloat32_t svcvt_f32[_u64]_x(svbool_t pg, svuint64_t op);
```

### Description

Floating-point convert

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Data type conversion / Conversions

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
    "register": "Zop.D|Ztied.D"
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
UCVTF Ztied.S, Pg/M, Ztied.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UCVTF--predicated---Unsigned-integer-convert-to-floating-point--predicated--

When result and op are in different registers, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
UCVTF Zresult.S, Pg/M, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UCVTF--predicated---Unsigned-integer-convert-to-floating-point--predicated--

### Operation

Source operation ID: `SveOperation_svcvt_f32_s64_x`

**Operation**



Convert each active element `op[i]` to `float32_t`, rounding according to the current rounding mode. Return the converted value in element `i * 2` of the result vector and return zero in element `i * 2 + 1`.



The inactive elements of the result have arbitrary, undefined values.

## svcvt_f32[_u64]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvt_f32%5B_u64%5D_z

### Signature (source notation)

```c
svfloat32_t svcvt_f32[_u64]_z(svbool_t pg, svuint64_t op);
```

### Description

Floating-point convert

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Data type conversion / Conversions

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
    "register": "Zop.D"
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
MOVPRFX Zresult.D, Pg/Z, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
UCVTF Zresult.S, Pg/M, Zop.D  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UCVTF--predicated---Unsigned-integer-convert-to-floating-point--predicated--

### Operation

Source operation ID: `SveOperation_svcvt_f32_s64_z`

**Operation**



Convert each active element `op[i]` to `float32_t`, rounding according to the current rounding mode. Return the converted value in element `i * 2` of the result vector and return zero in element `i * 2 + 1`.



Set the inactive elements of the result to zero.



**[1]** Note that `result` must be in a different register from `op`

## svcvt_f64[_f16]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvt_f64%5B_f16%5D_m

### Signature (source notation)

```c
svfloat64_t svcvt_f64[_f16]_m(svfloat64_t inactive, svbool_t pg, svfloat16_t op);
```

### Description

Floating-point convert

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Data type conversion / Conversions

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
    "register": "Zop.H"
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
FCVT Ztied.D, Pg/M, Zop.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCVT--Floating-point-convert-precision--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zinactive
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FCVT Zresult.D, Pg/M, Zop.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCVT--Floating-point-convert-precision--predicated--

### Operation

Source operation ID: `SveOperation_svcvt_f64_f16_m`

**Operation**



Return a vector in which each active element *i* contains `(float64_t)op[i * 4]`. Take the inactive elements of the result from the corresponding elements of `inactive`.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.

## svcvt_f64[_f16]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvt_f64%5B_f16%5D_x

### Signature (source notation)

```c
svfloat64_t svcvt_f64[_f16]_x(svbool_t pg, svfloat16_t op);
```

### Description

Floating-point convert

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Data type conversion / Conversions

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
    "register": "Zop.H|Ztied.H"
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
FCVT Ztied.D, Pg/M, Ztied.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCVT--Floating-point-convert-precision--predicated--

When result and op are in different registers, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FCVT Zresult.D, Pg/M, Zop.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCVT--Floating-point-convert-precision--predicated--

### Operation

Source operation ID: `SveOperation_svcvt_f64_f16_x`

**Operation**



Return a vector in which each active element *i* contains `(float64_t)op[i * 4]`. The inactive elements of the result have arbitrary, undefined values.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.

## svcvt_f64[_f16]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvt_f64%5B_f16%5D_z

### Signature (source notation)

```c
svfloat64_t svcvt_f64[_f16]_z(svbool_t pg, svfloat16_t op);
```

### Description

Floating-point convert

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Data type conversion / Conversions

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
    "register": "Zop.H"
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
FCVT Zresult.D, Pg/M, Zop.H  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCVT--Floating-point-convert-precision--predicated--

### Operation

Source operation ID: `SveOperation_svcvt_f64_f16_z`

**Operation**



Return a vector in which each active element *i* contains `(float64_t)op[i * 4]`. Set the inactive elements of the result to zero.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.



**[1]** Note that `result` must be in a different register from `op`

## svcvt_f64[_f32]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvt_f64%5B_f32%5D_m

### Signature (source notation)

```c
svfloat64_t svcvt_f64[_f32]_m(svfloat64_t inactive, svbool_t pg, svfloat32_t op);
```

### Description

Floating-point convert

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Data type conversion / Conversions

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
    "register": "Zop.S"
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
FCVT Ztied.D, Pg/M, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCVT--Floating-point-convert-precision--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zinactive
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FCVT Zresult.D, Pg/M, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCVT--Floating-point-convert-precision--predicated--

### Operation

Source operation ID: `SveOperation_svcvt_f64_f32_m`

**Operation**



Return a vector in which each active element *i* contains `(float64_t)op[i * 2]`. Take the inactive elements of the result from the corresponding elements of `inactive`.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.

## svcvt_f64[_f32]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvt_f64%5B_f32%5D_x

### Signature (source notation)

```c
svfloat64_t svcvt_f64[_f32]_x(svbool_t pg, svfloat32_t op);
```

### Description

Floating-point convert

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Data type conversion / Conversions

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
    "register": "Zop.S|Ztied.S"
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
FCVT Ztied.D, Pg/M, Ztied.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCVT--Floating-point-convert-precision--predicated--

When result and op are in different registers, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FCVT Zresult.D, Pg/M, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCVT--Floating-point-convert-precision--predicated--

### Operation

Source operation ID: `SveOperation_svcvt_f64_f32_x`

**Operation**



Return a vector in which each active element *i* contains `(float64_t)op[i * 2]`. The inactive elements of the result have arbitrary, undefined values.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.

