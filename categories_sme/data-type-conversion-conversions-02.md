# SME / Data type conversion / Conversions — Part 2

## svcvt_f64[_f32]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvt_f64%5B_f32%5D_z

### Signature (source notation)

```c
svfloat64_t svcvt_f64[_f32]_z(svbool_t pg, svfloat32_t op);
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
    "register": "Zop.S"
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
FCVT Zresult.D, Pg/M, Zop.S  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCVT--Floating-point-convert-precision--predicated--

### Operation

Source operation ID: `SveOperation_svcvt_f64_f32_z`

**Operation**



Return a vector in which each active element *i* contains `(float64_t)op[i * 2]`. Set the inactive elements of the result to zero.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.



**[1]** Note that `result` must be in a different register from `op`

## svcvt_f64[_s32]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvt_f64%5B_s32%5D_m

### Signature (source notation)

```c
svfloat64_t svcvt_f64[_s32]_m(svfloat64_t inactive, svbool_t pg, svint32_t op);
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
SCVTF Ztied.D, Pg/M, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SCVTF--predicated---Signed-integer-convert-to-floating-point--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zinactive
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SCVTF Zresult.D, Pg/M, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SCVTF--predicated---Signed-integer-convert-to-floating-point--predicated--

### Operation

Source operation ID: `SveOperation_svcvt_f64_s32_m`

**Operation**



Return a vector in which each active element *i* contains `(float64_t)op[i * 2]`. Take the inactive elements of the result from the corresponding elements of `inactive`.

## svcvt_f64[_s32]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvt_f64%5B_s32%5D_x

### Signature (source notation)

```c
svfloat64_t svcvt_f64[_s32]_x(svbool_t pg, svint32_t op);
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
SCVTF Ztied.D, Pg/M, Ztied.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SCVTF--predicated---Signed-integer-convert-to-floating-point--predicated--

When result and op are in different registers, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SCVTF Zresult.D, Pg/M, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SCVTF--predicated---Signed-integer-convert-to-floating-point--predicated--

### Operation

Source operation ID: `SveOperation_svcvt_f64_s32_x`

**Operation**



Return a vector in which each active element *i* contains `(float64_t)op[i * 2]`. The inactive elements of the result have arbitrary, undefined values.

## svcvt_f64[_s32]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvt_f64%5B_s32%5D_z

### Signature (source notation)

```c
svfloat64_t svcvt_f64[_s32]_z(svbool_t pg, svint32_t op);
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
    "register": "Zop.S"
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
SCVTF Zresult.D, Pg/M, Zop.S  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SCVTF--predicated---Signed-integer-convert-to-floating-point--predicated--

### Operation

Source operation ID: `SveOperation_svcvt_f64_s32_z`

**Operation**



Return a vector in which each active element *i* contains `(float64_t)op[i * 2]`. Set the inactive elements of the result to zero.



**[1]** Note that `result` must be in a different register from `op`

## svcvt_f64[_s64]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvt_f64%5B_s64%5D_m

### Signature (source notation)

```c
svfloat64_t svcvt_f64[_s64]_m(svfloat64_t inactive, svbool_t pg, svint64_t op);
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
SCVTF Ztied.D, Pg/M, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SCVTF--predicated---Signed-integer-convert-to-floating-point--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zinactive
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SCVTF Zresult.D, Pg/M, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SCVTF--predicated---Signed-integer-convert-to-floating-point--predicated--

### Operation

Source operation ID: `SveOperation_svcvt_f64_s64_m`

**Operation**



Return a vector in which each active element *i* contains `(float64_t)op[i]`, rounding according to the current rounding mode. Take the inactive elements of the result from the corresponding elements of `inactive`.

## svcvt_f64[_s64]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvt_f64%5B_s64%5D_x

### Signature (source notation)

```c
svfloat64_t svcvt_f64[_s64]_x(svbool_t pg, svint64_t op);
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
SCVTF Ztied.D, Pg/M, Ztied.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SCVTF--predicated---Signed-integer-convert-to-floating-point--predicated--

When result and op are in different registers, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SCVTF Zresult.D, Pg/M, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SCVTF--predicated---Signed-integer-convert-to-floating-point--predicated--

### Operation

Source operation ID: `SveOperation_svcvt_f64_s64_x`

**Operation**



Return a vector in which each active element *i* contains `(float64_t)op[i]`, rounding according to the current rounding mode. The inactive elements of the result have arbitrary, undefined values.

## svcvt_f64[_s64]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvt_f64%5B_s64%5D_z

### Signature (source notation)

```c
svfloat64_t svcvt_f64[_s64]_z(svbool_t pg, svint64_t op);
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
SCVTF Zresult.D, Pg/M, Zop.D  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SCVTF--predicated---Signed-integer-convert-to-floating-point--predicated--

### Operation

Source operation ID: `SveOperation_svcvt_f64_s64_z`

**Operation**



Return a vector in which each active element *i* contains `(float64_t)op[i]`, rounding according to the current rounding mode. Set the inactive elements of the result to zero.



**[1]** Note that `result` must be in a different register from `op`

## svcvt_f64[_u32]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvt_f64%5B_u32%5D_m

### Signature (source notation)

```c
svfloat64_t svcvt_f64[_u32]_m(svfloat64_t inactive, svbool_t pg, svuint32_t op);
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
UCVTF Ztied.D, Pg/M, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UCVTF--predicated---Unsigned-integer-convert-to-floating-point--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zinactive
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
UCVTF Zresult.D, Pg/M, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UCVTF--predicated---Unsigned-integer-convert-to-floating-point--predicated--

### Operation

Source operation ID: `SveOperation_svcvt_f64_s32_m`

**Operation**



Return a vector in which each active element *i* contains `(float64_t)op[i * 2]`. Take the inactive elements of the result from the corresponding elements of `inactive`.

## svcvt_f64[_u32]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvt_f64%5B_u32%5D_x

### Signature (source notation)

```c
svfloat64_t svcvt_f64[_u32]_x(svbool_t pg, svuint32_t op);
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
UCVTF Ztied.D, Pg/M, Ztied.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UCVTF--predicated---Unsigned-integer-convert-to-floating-point--predicated--

When result and op are in different registers, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
UCVTF Zresult.D, Pg/M, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UCVTF--predicated---Unsigned-integer-convert-to-floating-point--predicated--

### Operation

Source operation ID: `SveOperation_svcvt_f64_s32_x`

**Operation**



Return a vector in which each active element *i* contains `(float64_t)op[i * 2]`. The inactive elements of the result have arbitrary, undefined values.

## svcvt_f64[_u32]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvt_f64%5B_u32%5D_z

### Signature (source notation)

```c
svfloat64_t svcvt_f64[_u32]_z(svbool_t pg, svuint32_t op);
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
    "register": "Zop.S"
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
UCVTF Zresult.D, Pg/M, Zop.S  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UCVTF--predicated---Unsigned-integer-convert-to-floating-point--predicated--

### Operation

Source operation ID: `SveOperation_svcvt_f64_s32_z`

**Operation**



Return a vector in which each active element *i* contains `(float64_t)op[i * 2]`. Set the inactive elements of the result to zero.



**[1]** Note that `result` must be in a different register from `op`

## svcvt_f64[_u64]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvt_f64%5B_u64%5D_m

### Signature (source notation)

```c
svfloat64_t svcvt_f64[_u64]_m(svfloat64_t inactive, svbool_t pg, svuint64_t op);
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
UCVTF Ztied.D, Pg/M, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UCVTF--predicated---Unsigned-integer-convert-to-floating-point--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zinactive
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
UCVTF Zresult.D, Pg/M, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UCVTF--predicated---Unsigned-integer-convert-to-floating-point--predicated--

### Operation

Source operation ID: `SveOperation_svcvt_f64_s64_m`

**Operation**



Return a vector in which each active element *i* contains `(float64_t)op[i]`, rounding according to the current rounding mode. Take the inactive elements of the result from the corresponding elements of `inactive`.

## svcvt_f64[_u64]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvt_f64%5B_u64%5D_x

### Signature (source notation)

```c
svfloat64_t svcvt_f64[_u64]_x(svbool_t pg, svuint64_t op);
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
UCVTF Ztied.D, Pg/M, Ztied.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UCVTF--predicated---Unsigned-integer-convert-to-floating-point--predicated--

When result and op are in different registers, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
UCVTF Zresult.D, Pg/M, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UCVTF--predicated---Unsigned-integer-convert-to-floating-point--predicated--

### Operation

Source operation ID: `SveOperation_svcvt_f64_s64_x`

**Operation**



Return a vector in which each active element *i* contains `(float64_t)op[i]`, rounding according to the current rounding mode. The inactive elements of the result have arbitrary, undefined values.

## svcvt_f64[_u64]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvt_f64%5B_u64%5D_z

### Signature (source notation)

```c
svfloat64_t svcvt_f64[_u64]_z(svbool_t pg, svuint64_t op);
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
UCVTF Zresult.D, Pg/M, Zop.D  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UCVTF--predicated---Unsigned-integer-convert-to-floating-point--predicated--

### Operation

Source operation ID: `SveOperation_svcvt_f64_s64_z`

**Operation**



Return a vector in which each active element *i* contains `(float64_t)op[i]`, rounding according to the current rounding mode. Set the inactive elements of the result to zero.



**[1]** Note that `result` must be in a different register from `op`

## svcvt_s16[_f16]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvt_s16%5B_f16%5D_m

### Signature (source notation)

```c
svint16_t svcvt_s16[_f16]_m(svint16_t inactive, svbool_t pg, svfloat16_t op);
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
  "return_base_type": "int",
  "element_bit_size": "16",
  "value": "svint16_t"
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
FCVTZS Ztied.H, Pg/M, Zop.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCVTZS--Floating-point-convert-to-signed-integer--rounding-toward-zero--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zinactive
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FCVTZS Zresult.H, Pg/M, Zop.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCVTZS--Floating-point-convert-to-signed-integer--rounding-toward-zero--predicated--

### Operation

Source operation ID: `SveOperation_svcvt_s16_f16_m`

**Operation**



Return a vector in which each active element *i* contains `(int16_t)op[i]`, rounding towards zero and saturating to the range of `int16_t`. Take the inactive elements of the result from the corresponding elements of `inactive`.



**Exceptions**



Active signaling and quiet NaNs both trigger an IEEE Invalid exception.

## svcvt_s16[_f16]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvt_s16%5B_f16%5D_x

### Signature (source notation)

```c
svint16_t svcvt_s16[_f16]_x(svbool_t pg, svfloat16_t op);
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
FCVTZS Ztied.H, Pg/M, Ztied.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCVTZS--Floating-point-convert-to-signed-integer--rounding-toward-zero--predicated--

When result and op are in different registers, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FCVTZS Zresult.H, Pg/M, Zop.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCVTZS--Floating-point-convert-to-signed-integer--rounding-toward-zero--predicated--

### Operation

Source operation ID: `SveOperation_svcvt_s16_f16_x`

**Operation**



Return a vector in which each active element *i* contains `(int16_t)op[i]`, rounding towards zero and saturating to the range of `int16_t`. The inactive elements of the result have arbitrary, undefined values.



**Exceptions**



Active signaling and quiet NaNs both trigger an IEEE Invalid exception.

## svcvt_s16[_f16]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvt_s16%5B_f16%5D_z

### Signature (source notation)

```c
svint16_t svcvt_s16[_f16]_z(svbool_t pg, svfloat16_t op);
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
FCVTZS Zresult.H, Pg/M, Zop.H  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCVTZS--Floating-point-convert-to-signed-integer--rounding-toward-zero--predicated--

### Operation

Source operation ID: `SveOperation_svcvt_s16_f16_z`

**Operation**



Return a vector in which each active element *i* contains `(int16_t)op[i]`, rounding towards zero and saturating to the range of `int16_t`. Set the inactive elements of the result to zero.



**Exceptions**



Active signaling and quiet NaNs both trigger an IEEE Invalid exception.



**[1]** Note that `result` must be in a different register from `op`

## svcvt_s32[_f16]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvt_s32%5B_f16%5D_m

### Signature (source notation)

```c
svint32_t svcvt_s32[_f16]_m(svint32_t inactive, svbool_t pg, svfloat16_t op);
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
  "return_base_type": "int",
  "element_bit_size": "32",
  "value": "svint32_t"
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
FCVTZS Ztied.S, Pg/M, Zop.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCVTZS--Floating-point-convert-to-signed-integer--rounding-toward-zero--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zinactive
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FCVTZS Zresult.S, Pg/M, Zop.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCVTZS--Floating-point-convert-to-signed-integer--rounding-toward-zero--predicated--

### Operation

Source operation ID: `SveOperation_svcvt_s32_f16_m`

**Operation**



Return a vector in which each active element *i* contains `(int32_t)op[i * 2]`, rounding towards zero and saturating to the range of `int32_t`. Take the inactive elements of the result from the corresponding elements of `inactive`.



**Exceptions**



Active signaling and quiet NaNs both trigger an IEEE Invalid exception.

## svcvt_s32[_f16]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvt_s32%5B_f16%5D_x

### Signature (source notation)

```c
svint32_t svcvt_s32[_f16]_x(svbool_t pg, svfloat16_t op);
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
FCVTZS Ztied.S, Pg/M, Ztied.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCVTZS--Floating-point-convert-to-signed-integer--rounding-toward-zero--predicated--

When result and op are in different registers, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FCVTZS Zresult.S, Pg/M, Zop.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCVTZS--Floating-point-convert-to-signed-integer--rounding-toward-zero--predicated--

### Operation

Source operation ID: `SveOperation_svcvt_s32_f16_x`

**Operation**



Return a vector in which each active element *i* contains `(int32_t)op[i * 2]`, rounding towards zero and saturating to the range of `int32_t`. The inactive elements of the result have arbitrary, undefined values.



**Exceptions**



Active signaling and quiet NaNs both trigger an IEEE Invalid exception.

## svcvt_s32[_f16]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvt_s32%5B_f16%5D_z

### Signature (source notation)

```c
svint32_t svcvt_s32[_f16]_z(svbool_t pg, svfloat16_t op);
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
FCVTZS Zresult.S, Pg/M, Zop.H  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCVTZS--Floating-point-convert-to-signed-integer--rounding-toward-zero--predicated--

### Operation

Source operation ID: `SveOperation_svcvt_s32_f16_z`

**Operation**



Return a vector in which each active element *i* contains `(int32_t)op[i * 2]`, rounding towards zero and saturating to the range of `int32_t`. Set the inactive elements of the result to zero.



**Exceptions**



Active signaling and quiet NaNs both trigger an IEEE Invalid exception.



**[1]** Note that `result` must be in a different register from `op`

## svcvt_s32[_f32]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvt_s32%5B_f32%5D_m

### Signature (source notation)

```c
svint32_t svcvt_s32[_f32]_m(svint32_t inactive, svbool_t pg, svfloat32_t op);
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
  "return_base_type": "int",
  "element_bit_size": "32",
  "value": "svint32_t"
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
FCVTZS Ztied.S, Pg/M, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCVTZS--Floating-point-convert-to-signed-integer--rounding-toward-zero--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zinactive
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FCVTZS Zresult.S, Pg/M, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCVTZS--Floating-point-convert-to-signed-integer--rounding-toward-zero--predicated--

### Operation

Source operation ID: `SveOperation_svcvt_s32_f32_m`

**Operation**



Return a vector in which each active element *i* contains `(int32_t)op[i]`, rounding towards zero and saturating to the range of `int32_t`. Take the inactive elements of the result from the corresponding elements of `inactive`.



**Exceptions**



Active signaling and quiet NaNs both trigger an IEEE Invalid exception.

## svcvt_s32[_f32]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvt_s32%5B_f32%5D_x

### Signature (source notation)

```c
svint32_t svcvt_s32[_f32]_x(svbool_t pg, svfloat32_t op);
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
FCVTZS Ztied.S, Pg/M, Ztied.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCVTZS--Floating-point-convert-to-signed-integer--rounding-toward-zero--predicated--

When result and op are in different registers, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FCVTZS Zresult.S, Pg/M, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCVTZS--Floating-point-convert-to-signed-integer--rounding-toward-zero--predicated--

### Operation

Source operation ID: `SveOperation_svcvt_s32_f32_x`

**Operation**



Return a vector in which each active element *i* contains `(int32_t)op[i]`, rounding towards zero and saturating to the range of `int32_t`. The inactive elements of the result have arbitrary, undefined values.



**Exceptions**



Active signaling and quiet NaNs both trigger an IEEE Invalid exception.

## svcvt_s32[_f32]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvt_s32%5B_f32%5D_z

### Signature (source notation)

```c
svint32_t svcvt_s32[_f32]_z(svbool_t pg, svfloat32_t op);
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
FCVTZS Zresult.S, Pg/M, Zop.S  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCVTZS--Floating-point-convert-to-signed-integer--rounding-toward-zero--predicated--

### Operation

Source operation ID: `SveOperation_svcvt_s32_f32_z`

**Operation**



Return a vector in which each active element *i* contains `(int32_t)op[i]`, rounding towards zero and saturating to the range of `int32_t`. Set the inactive elements of the result to zero.



**Exceptions**



Active signaling and quiet NaNs both trigger an IEEE Invalid exception.



**[1]** Note that `result` must be in a different register from `op`

## svcvt_s32[_f64]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvt_s32%5B_f64%5D_m

### Signature (source notation)

```c
svint32_t svcvt_s32[_f64]_m(svint32_t inactive, svbool_t pg, svfloat64_t op);
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
  "return_base_type": "int",
  "element_bit_size": "32",
  "value": "svint32_t"
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
FCVTZS Ztied.S, Pg/M, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCVTZS--Floating-point-convert-to-signed-integer--rounding-toward-zero--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zinactive
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FCVTZS Zresult.S, Pg/M, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCVTZS--Floating-point-convert-to-signed-integer--rounding-toward-zero--predicated--

### Operation

Source operation ID: `SveOperation_svcvt_s32_f64_m`

**Operation**



Convert each active element `op[i]` to `int32_t`, rounding towards zero and saturating to the range of `int32_t`. Return the converted value in element `i * 2` of the result vector and return zero in element `i * 2 + 1`.



Take the inactive elements of the result from the corresponding elements of `inactive`.



**Exceptions**



Active signaling and quiet NaNs both trigger an IEEE Invalid exception.

## svcvt_s32[_f64]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvt_s32%5B_f64%5D_x

### Signature (source notation)

```c
svint32_t svcvt_s32[_f64]_x(svbool_t pg, svfloat64_t op);
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
FCVTZS Ztied.S, Pg/M, Ztied.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCVTZS--Floating-point-convert-to-signed-integer--rounding-toward-zero--predicated--

When result and op are in different registers, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FCVTZS Zresult.S, Pg/M, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCVTZS--Floating-point-convert-to-signed-integer--rounding-toward-zero--predicated--

### Operation

Source operation ID: `SveOperation_svcvt_s32_f64_x`

**Operation**



Convert each active element `op[i]` to `int32_t`, rounding towards zero and saturating to the range of `int32_t`. Return the converted value in element `i * 2` of the result vector and return zero in element `i * 2 + 1`.



The inactive elements of the result have arbitrary, undefined values.



**Exceptions**



Active signaling and quiet NaNs both trigger an IEEE Invalid exception.

## svcvt_s32[_f64]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvt_s32%5B_f64%5D_z

### Signature (source notation)

```c
svint32_t svcvt_s32[_f64]_z(svbool_t pg, svfloat64_t op);
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
FCVTZS Zresult.S, Pg/M, Zop.D  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCVTZS--Floating-point-convert-to-signed-integer--rounding-toward-zero--predicated--

### Operation

Source operation ID: `SveOperation_svcvt_s32_f64_z`

**Operation**



Convert each active element `op[i]` to `int32_t`, rounding towards zero and saturating to the range of `int32_t`. Return the converted value in element `i * 2` of the result vector and return zero in element `i * 2 + 1`.



Set the inactive elements of the result to zero.



**Exceptions**



Active signaling and quiet NaNs both trigger an IEEE Invalid exception.



**[1]** Note that `result` must be in a different register from `op`

## svcvt_s64[_f16]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvt_s64%5B_f16%5D_m

### Signature (source notation)

```c
svint64_t svcvt_s64[_f16]_m(svint64_t inactive, svbool_t pg, svfloat16_t op);
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
  "return_base_type": "int",
  "element_bit_size": "64",
  "value": "svint64_t"
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
FCVTZS Ztied.D, Pg/M, Zop.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCVTZS--Floating-point-convert-to-signed-integer--rounding-toward-zero--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zinactive
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FCVTZS Zresult.D, Pg/M, Zop.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCVTZS--Floating-point-convert-to-signed-integer--rounding-toward-zero--predicated--

### Operation

Source operation ID: `SveOperation_svcvt_s64_f16_m`

**Operation**



Return a vector in which each active element *i* contains `(int64_t)op[i * 4]`, rounding towards zero and saturating to the range of `int64_t`. Take the inactive elements of the result from the corresponding elements of `inactive`.



**Exceptions**



Active signaling and quiet NaNs both trigger an IEEE Invalid exception.

## svcvt_s64[_f16]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvt_s64%5B_f16%5D_x

### Signature (source notation)

```c
svint64_t svcvt_s64[_f16]_x(svbool_t pg, svfloat16_t op);
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
FCVTZS Ztied.D, Pg/M, Ztied.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCVTZS--Floating-point-convert-to-signed-integer--rounding-toward-zero--predicated--

When result and op are in different registers, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FCVTZS Zresult.D, Pg/M, Zop.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCVTZS--Floating-point-convert-to-signed-integer--rounding-toward-zero--predicated--

### Operation

Source operation ID: `SveOperation_svcvt_s64_f16_x`

**Operation**



Return a vector in which each active element *i* contains `(int64_t)op[i * 4]`, rounding towards zero and saturating to the range of `int64_t`. The inactive elements of the result have arbitrary, undefined values.



**Exceptions**



Active signaling and quiet NaNs both trigger an IEEE Invalid exception.

## svcvt_s64[_f16]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvt_s64%5B_f16%5D_z

### Signature (source notation)

```c
svint64_t svcvt_s64[_f16]_z(svbool_t pg, svfloat16_t op);
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
FCVTZS Zresult.D, Pg/M, Zop.H  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCVTZS--Floating-point-convert-to-signed-integer--rounding-toward-zero--predicated--

### Operation

Source operation ID: `SveOperation_svcvt_s64_f16_z`

**Operation**



Return a vector in which each active element *i* contains `(int64_t)op[i * 4]`, rounding towards zero and saturating to the range of `int64_t`. Set the inactive elements of the result to zero.



**Exceptions**



Active signaling and quiet NaNs both trigger an IEEE Invalid exception.



**[1]** Note that `result` must be in a different register from `op`

## svcvt_s64[_f32]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvt_s64%5B_f32%5D_m

### Signature (source notation)

```c
svint64_t svcvt_s64[_f32]_m(svint64_t inactive, svbool_t pg, svfloat32_t op);
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
  "return_base_type": "int",
  "element_bit_size": "64",
  "value": "svint64_t"
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
FCVTZS Ztied.D, Pg/M, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCVTZS--Floating-point-convert-to-signed-integer--rounding-toward-zero--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zinactive
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FCVTZS Zresult.D, Pg/M, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCVTZS--Floating-point-convert-to-signed-integer--rounding-toward-zero--predicated--

### Operation

Source operation ID: `SveOperation_svcvt_s64_f32_m`

**Operation**



Return a vector in which each active element *i* contains `(int64_t)op[i * 2]`, rounding towards zero and saturating to the range of `int64_t`. Take the inactive elements of the result from the corresponding elements of `inactive`.



**Exceptions**



Active signaling and quiet NaNs both trigger an IEEE Invalid exception.

## svcvt_s64[_f32]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvt_s64%5B_f32%5D_x

### Signature (source notation)

```c
svint64_t svcvt_s64[_f32]_x(svbool_t pg, svfloat32_t op);
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
FCVTZS Ztied.D, Pg/M, Ztied.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCVTZS--Floating-point-convert-to-signed-integer--rounding-toward-zero--predicated--

When result and op are in different registers, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FCVTZS Zresult.D, Pg/M, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCVTZS--Floating-point-convert-to-signed-integer--rounding-toward-zero--predicated--

### Operation

Source operation ID: `SveOperation_svcvt_s64_f32_x`

**Operation**



Return a vector in which each active element *i* contains `(int64_t)op[i * 2]`, rounding towards zero and saturating to the range of `int64_t`. The inactive elements of the result have arbitrary, undefined values.



**Exceptions**



Active signaling and quiet NaNs both trigger an IEEE Invalid exception.

## svcvt_s64[_f32]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvt_s64%5B_f32%5D_z

### Signature (source notation)

```c
svint64_t svcvt_s64[_f32]_z(svbool_t pg, svfloat32_t op);
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
  "op": {
    "register": "Zop.S"
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
FCVTZS Zresult.D, Pg/M, Zop.S  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCVTZS--Floating-point-convert-to-signed-integer--rounding-toward-zero--predicated--

### Operation

Source operation ID: `SveOperation_svcvt_s64_f32_z`

**Operation**



Return a vector in which each active element *i* contains `(int64_t)op[i * 2]`, rounding towards zero and saturating to the range of `int64_t`. Set the inactive elements of the result to zero.



**Exceptions**



Active signaling and quiet NaNs both trigger an IEEE Invalid exception.



**[1]** Note that `result` must be in a different register from `op`

## svcvt_s64[_f64]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvt_s64%5B_f64%5D_m

### Signature (source notation)

```c
svint64_t svcvt_s64[_f64]_m(svint64_t inactive, svbool_t pg, svfloat64_t op);
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
  "return_base_type": "int",
  "element_bit_size": "64",
  "value": "svint64_t"
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
FCVTZS Ztied.D, Pg/M, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCVTZS--Floating-point-convert-to-signed-integer--rounding-toward-zero--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zinactive
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FCVTZS Zresult.D, Pg/M, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCVTZS--Floating-point-convert-to-signed-integer--rounding-toward-zero--predicated--

### Operation

Source operation ID: `SveOperation_svcvt_s64_f64_m`

**Operation**



Return a vector in which each active element *i* contains `(int64_t)op[i]`, rounding towards zero and saturating to the range of `int64_t`. Take the inactive elements of the result from the corresponding elements of `inactive`.



**Exceptions**



Active signaling and quiet NaNs both trigger an IEEE Invalid exception.

## svcvt_s64[_f64]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvt_s64%5B_f64%5D_x

### Signature (source notation)

```c
svint64_t svcvt_s64[_f64]_x(svbool_t pg, svfloat64_t op);
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
FCVTZS Ztied.D, Pg/M, Ztied.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCVTZS--Floating-point-convert-to-signed-integer--rounding-toward-zero--predicated--

When result and op are in different registers, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FCVTZS Zresult.D, Pg/M, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCVTZS--Floating-point-convert-to-signed-integer--rounding-toward-zero--predicated--

### Operation

Source operation ID: `SveOperation_svcvt_s64_f64_x`

**Operation**



Return a vector in which each active element *i* contains `(int64_t)op[i]`, rounding towards zero and saturating to the range of `int64_t`. The inactive elements of the result have arbitrary, undefined values.



**Exceptions**



Active signaling and quiet NaNs both trigger an IEEE Invalid exception.

## svcvt_s64[_f64]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvt_s64%5B_f64%5D_z

### Signature (source notation)

```c
svint64_t svcvt_s64[_f64]_z(svbool_t pg, svfloat64_t op);
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
FCVTZS Zresult.D, Pg/M, Zop.D  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCVTZS--Floating-point-convert-to-signed-integer--rounding-toward-zero--predicated--

### Operation

Source operation ID: `SveOperation_svcvt_s64_f64_z`

**Operation**



Return a vector in which each active element *i* contains `(int64_t)op[i]`, rounding towards zero and saturating to the range of `int64_t`. Set the inactive elements of the result to zero.



**Exceptions**



Active signaling and quiet NaNs both trigger an IEEE Invalid exception.



**[1]** Note that `result` must be in a different register from `op`

## svcvt_u16[_f16]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvt_u16%5B_f16%5D_m

### Signature (source notation)

```c
svuint16_t svcvt_u16[_f16]_m(svuint16_t inactive, svbool_t pg, svfloat16_t op);
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
  "return_base_type": "uint",
  "element_bit_size": "16",
  "value": "svuint16_t"
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
FCVTZU Ztied.H, Pg/M, Zop.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCVTZU--Floating-point-convert-to-unsigned-integer--rounding-toward-zero--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zinactive
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FCVTZU Zresult.H, Pg/M, Zop.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCVTZU--Floating-point-convert-to-unsigned-integer--rounding-toward-zero--predicated--

### Operation

Source operation ID: `SveOperation_svcvt_u16_f16_m`

**Operation**



Return a vector in which each active element *i* contains `(uint16_t)op[i]`, rounding towards zero and saturating to the range of `uint16_t`. Take the inactive elements of the result from the corresponding elements of `inactive`.



**Exceptions**



Active signaling and quiet NaNs both trigger an IEEE Invalid exception.

## svcvt_u16[_f16]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvt_u16%5B_f16%5D_x

### Signature (source notation)

```c
svuint16_t svcvt_u16[_f16]_x(svbool_t pg, svfloat16_t op);
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
FCVTZU Ztied.H, Pg/M, Ztied.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCVTZU--Floating-point-convert-to-unsigned-integer--rounding-toward-zero--predicated--

When result and op are in different registers, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FCVTZU Zresult.H, Pg/M, Zop.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCVTZU--Floating-point-convert-to-unsigned-integer--rounding-toward-zero--predicated--

### Operation

Source operation ID: `SveOperation_svcvt_u16_f16_x`

**Operation**



Return a vector in which each active element *i* contains `(uint16_t)op[i]`, rounding towards zero and saturating to the range of `uint16_t`. The inactive elements of the result have arbitrary, undefined values.



**Exceptions**



Active signaling and quiet NaNs both trigger an IEEE Invalid exception.

## svcvt_u16[_f16]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvt_u16%5B_f16%5D_z

### Signature (source notation)

```c
svuint16_t svcvt_u16[_f16]_z(svbool_t pg, svfloat16_t op);
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
FCVTZU Zresult.H, Pg/M, Zop.H  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCVTZU--Floating-point-convert-to-unsigned-integer--rounding-toward-zero--predicated--

### Operation

Source operation ID: `SveOperation_svcvt_u16_f16_z`

**Operation**



Return a vector in which each active element *i* contains `(uint16_t)op[i]`, rounding towards zero and saturating to the range of `uint16_t`. Set the inactive elements of the result to zero.



**Exceptions**



Active signaling and quiet NaNs both trigger an IEEE Invalid exception.



**[1]** Note that `result` must be in a different register from `op`

## svcvt_u32[_f16]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvt_u32%5B_f16%5D_m

### Signature (source notation)

```c
svuint32_t svcvt_u32[_f16]_m(svuint32_t inactive, svbool_t pg, svfloat16_t op);
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
FCVTZU Ztied.S, Pg/M, Zop.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCVTZU--Floating-point-convert-to-unsigned-integer--rounding-toward-zero--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zinactive
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FCVTZU Zresult.S, Pg/M, Zop.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCVTZU--Floating-point-convert-to-unsigned-integer--rounding-toward-zero--predicated--

### Operation

Source operation ID: `SveOperation_svcvt_u32_f16_m`

**Operation**



Return a vector in which each active element *i* contains `(uint32_t)op[i * 2]`, rounding towards zero and saturating to the range of `uint32_t`. Take the inactive elements of the result from the corresponding elements of `inactive`.



**Exceptions**



Active signaling and quiet NaNs both trigger an IEEE Invalid exception.

## svcvt_u32[_f16]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvt_u32%5B_f16%5D_x

### Signature (source notation)

```c
svuint32_t svcvt_u32[_f16]_x(svbool_t pg, svfloat16_t op);
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
FCVTZU Ztied.S, Pg/M, Ztied.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCVTZU--Floating-point-convert-to-unsigned-integer--rounding-toward-zero--predicated--

When result and op are in different registers, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FCVTZU Zresult.S, Pg/M, Zop.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCVTZU--Floating-point-convert-to-unsigned-integer--rounding-toward-zero--predicated--

### Operation

Source operation ID: `SveOperation_svcvt_u32_f16_x`

**Operation**



Return a vector in which each active element *i* contains `(uint32_t)op[i * 2]`, rounding towards zero and saturating to the range of `uint32_t`. The inactive elements of the result have arbitrary, undefined values.



**Exceptions**



Active signaling and quiet NaNs both trigger an IEEE Invalid exception.

## svcvt_u32[_f16]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvt_u32%5B_f16%5D_z

### Signature (source notation)

```c
svuint32_t svcvt_u32[_f16]_z(svbool_t pg, svfloat16_t op);
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
FCVTZU Zresult.S, Pg/M, Zop.H  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCVTZU--Floating-point-convert-to-unsigned-integer--rounding-toward-zero--predicated--

### Operation

Source operation ID: `SveOperation_svcvt_u32_f16_z`

**Operation**



Return a vector in which each active element *i* contains `(uint32_t)op[i * 2]`, rounding towards zero and saturating to the range of `uint32_t`. Set the inactive elements of the result to zero.



**Exceptions**



Active signaling and quiet NaNs both trigger an IEEE Invalid exception.



**[1]** Note that `result` must be in a different register from `op`

## svcvt_u32[_f32]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvt_u32%5B_f32%5D_m

### Signature (source notation)

```c
svuint32_t svcvt_u32[_f32]_m(svuint32_t inactive, svbool_t pg, svfloat32_t op);
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
FCVTZU Ztied.S, Pg/M, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCVTZU--Floating-point-convert-to-unsigned-integer--rounding-toward-zero--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zinactive
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FCVTZU Zresult.S, Pg/M, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCVTZU--Floating-point-convert-to-unsigned-integer--rounding-toward-zero--predicated--

### Operation

Source operation ID: `SveOperation_svcvt_u32_f32_m`

**Operation**



Return a vector in which each active element *i* contains `(uint32_t)op[i]`, rounding towards zero and saturating to the range of `uint32_t`. Take the inactive elements of the result from the corresponding elements of `inactive`.



**Exceptions**



Active signaling and quiet NaNs both trigger an IEEE Invalid exception.

## svcvt_u32[_f32]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvt_u32%5B_f32%5D_x

### Signature (source notation)

```c
svuint32_t svcvt_u32[_f32]_x(svbool_t pg, svfloat32_t op);
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
FCVTZU Ztied.S, Pg/M, Ztied.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCVTZU--Floating-point-convert-to-unsigned-integer--rounding-toward-zero--predicated--

When result and op are in different registers, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FCVTZU Zresult.S, Pg/M, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCVTZU--Floating-point-convert-to-unsigned-integer--rounding-toward-zero--predicated--

### Operation

Source operation ID: `SveOperation_svcvt_u32_f32_x`

**Operation**



Return a vector in which each active element *i* contains `(uint32_t)op[i]`, rounding towards zero and saturating to the range of `uint32_t`. The inactive elements of the result have arbitrary, undefined values.



**Exceptions**



Active signaling and quiet NaNs both trigger an IEEE Invalid exception.

## svcvt_u32[_f32]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvt_u32%5B_f32%5D_z

### Signature (source notation)

```c
svuint32_t svcvt_u32[_f32]_z(svbool_t pg, svfloat32_t op);
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
FCVTZU Zresult.S, Pg/M, Zop.S  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCVTZU--Floating-point-convert-to-unsigned-integer--rounding-toward-zero--predicated--

### Operation

Source operation ID: `SveOperation_svcvt_u32_f32_z`

**Operation**



Return a vector in which each active element *i* contains `(uint32_t)op[i]`, rounding towards zero and saturating to the range of `uint32_t`. Set the inactive elements of the result to zero.



**Exceptions**



Active signaling and quiet NaNs both trigger an IEEE Invalid exception.



**[1]** Note that `result` must be in a different register from `op`

## svcvt_u32[_f64]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvt_u32%5B_f64%5D_m

### Signature (source notation)

```c
svuint32_t svcvt_u32[_f64]_m(svuint32_t inactive, svbool_t pg, svfloat64_t op);
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
FCVTZU Ztied.S, Pg/M, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCVTZU--Floating-point-convert-to-unsigned-integer--rounding-toward-zero--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zinactive
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FCVTZU Zresult.S, Pg/M, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCVTZU--Floating-point-convert-to-unsigned-integer--rounding-toward-zero--predicated--

### Operation

Source operation ID: `SveOperation_svcvt_u32_f64_m`

**Operation**



Convert each active element `op[i]` to `uint32_t`, rounding towards zero and saturating to the range of `uint32_t`. Return the converted value in element `i * 2` of the result vector and return zero in element `i * 2 + 1`.



Take the inactive elements of the result from the corresponding elements of `inactive`.



**Exceptions**



Active signaling and quiet NaNs both trigger an IEEE Invalid exception.

## svcvt_u32[_f64]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvt_u32%5B_f64%5D_x

### Signature (source notation)

```c
svuint32_t svcvt_u32[_f64]_x(svbool_t pg, svfloat64_t op);
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
FCVTZU Ztied.S, Pg/M, Ztied.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCVTZU--Floating-point-convert-to-unsigned-integer--rounding-toward-zero--predicated--

When result and op are in different registers, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FCVTZU Zresult.S, Pg/M, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCVTZU--Floating-point-convert-to-unsigned-integer--rounding-toward-zero--predicated--

### Operation

Source operation ID: `SveOperation_svcvt_u32_f64_x`

**Operation**



Convert each active element `op[i]` to `uint32_t`, rounding towards zero and saturating to the range of `uint32_t`. Return the converted value in element `i * 2` of the result vector and return zero in element `i * 2 + 1`.



The inactive elements of the result have arbitrary, undefined values.



**Exceptions**



Active signaling and quiet NaNs both trigger an IEEE Invalid exception.

## svcvt_u32[_f64]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvt_u32%5B_f64%5D_z

### Signature (source notation)

```c
svuint32_t svcvt_u32[_f64]_z(svbool_t pg, svfloat64_t op);
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
FCVTZU Zresult.S, Pg/M, Zop.D  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCVTZU--Floating-point-convert-to-unsigned-integer--rounding-toward-zero--predicated--

### Operation

Source operation ID: `SveOperation_svcvt_u32_f64_z`

**Operation**



Convert each active element `op[i]` to `uint32_t`, rounding towards zero and saturating to the range of `uint32_t`. Return the converted value in element `i * 2` of the result vector and return zero in element `i * 2 + 1`.



Set the inactive elements of the result to zero.



**Exceptions**



Active signaling and quiet NaNs both trigger an IEEE Invalid exception.



**[1]** Note that `result` must be in a different register from `op`

## svcvt_u64[_f16]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvt_u64%5B_f16%5D_m

### Signature (source notation)

```c
svuint64_t svcvt_u64[_f16]_m(svuint64_t inactive, svbool_t pg, svfloat16_t op);
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
  "return_base_type": "uint",
  "element_bit_size": "64",
  "value": "svuint64_t"
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
FCVTZU Ztied.D, Pg/M, Zop.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCVTZU--Floating-point-convert-to-unsigned-integer--rounding-toward-zero--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zinactive
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FCVTZU Zresult.D, Pg/M, Zop.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCVTZU--Floating-point-convert-to-unsigned-integer--rounding-toward-zero--predicated--

### Operation

Source operation ID: `SveOperation_svcvt_u64_f16_m`

**Operation**



Return a vector in which each active element *i* contains `(uint64_t)op[i * 4]`, rounding towards zero and saturating to the range of `uint64_t`. Take the inactive elements of the result from the corresponding elements of `inactive`.



**Exceptions**



Active signaling and quiet NaNs both trigger an IEEE Invalid exception.

## svcvt_u64[_f16]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvt_u64%5B_f16%5D_x

### Signature (source notation)

```c
svuint64_t svcvt_u64[_f16]_x(svbool_t pg, svfloat16_t op);
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
FCVTZU Ztied.D, Pg/M, Ztied.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCVTZU--Floating-point-convert-to-unsigned-integer--rounding-toward-zero--predicated--

When result and op are in different registers, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FCVTZU Zresult.D, Pg/M, Zop.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCVTZU--Floating-point-convert-to-unsigned-integer--rounding-toward-zero--predicated--

### Operation

Source operation ID: `SveOperation_svcvt_u64_f16_x`

**Operation**



Return a vector in which each active element *i* contains `(uint64_t)op[i * 4]`, rounding towards zero and saturating to the range of `uint64_t`. The inactive elements of the result have arbitrary, undefined values.



**Exceptions**



Active signaling and quiet NaNs both trigger an IEEE Invalid exception.

## svcvt_u64[_f16]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvt_u64%5B_f16%5D_z

### Signature (source notation)

```c
svuint64_t svcvt_u64[_f16]_z(svbool_t pg, svfloat16_t op);
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
FCVTZU Zresult.D, Pg/M, Zop.H  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCVTZU--Floating-point-convert-to-unsigned-integer--rounding-toward-zero--predicated--

### Operation

Source operation ID: `SveOperation_svcvt_u64_f16_z`

**Operation**



Return a vector in which each active element *i* contains `(uint64_t)op[i * 4]`, rounding towards zero and saturating to the range of `uint64_t`. Set the inactive elements of the result to zero.



**Exceptions**



Active signaling and quiet NaNs both trigger an IEEE Invalid exception.



**[1]** Note that `result` must be in a different register from `op`

## svcvt_u64[_f32]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvt_u64%5B_f32%5D_m

### Signature (source notation)

```c
svuint64_t svcvt_u64[_f32]_m(svuint64_t inactive, svbool_t pg, svfloat32_t op);
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
  "return_base_type": "uint",
  "element_bit_size": "64",
  "value": "svuint64_t"
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
FCVTZU Ztied.D, Pg/M, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCVTZU--Floating-point-convert-to-unsigned-integer--rounding-toward-zero--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zinactive
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FCVTZU Zresult.D, Pg/M, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCVTZU--Floating-point-convert-to-unsigned-integer--rounding-toward-zero--predicated--

### Operation

Source operation ID: `SveOperation_svcvt_u64_f32_m`

**Operation**



Return a vector in which each active element *i* contains `(uint64_t)op[i * 2]`, rounding towards zero and saturating to the range of `uint64_t`. Take the inactive elements of the result from the corresponding elements of `inactive`.



**Exceptions**



Active signaling and quiet NaNs both trigger an IEEE Invalid exception.

