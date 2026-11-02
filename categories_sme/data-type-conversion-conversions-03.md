# SME / Data type conversion / Conversions — Part 3

## svcvt_u64[_f32]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvt_u64%5B_f32%5D_x

### Signature (source notation)

```c
svuint64_t svcvt_u64[_f32]_x(svbool_t pg, svfloat32_t op);
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
FCVTZU Ztied.D, Pg/M, Ztied.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCVTZU--Floating-point-convert-to-unsigned-integer--rounding-toward-zero--predicated--

When result and op are in different registers, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FCVTZU Zresult.D, Pg/M, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCVTZU--Floating-point-convert-to-unsigned-integer--rounding-toward-zero--predicated--

### Operation

Source operation ID: `SveOperation_svcvt_u64_f32_x`

**Operation**



Return a vector in which each active element *i* contains `(uint64_t)op[i * 2]`, rounding towards zero and saturating to the range of `uint64_t`. The inactive elements of the result have arbitrary, undefined values.



**Exceptions**



Active signaling and quiet NaNs both trigger an IEEE Invalid exception.

## svcvt_u64[_f32]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvt_u64%5B_f32%5D_z

### Signature (source notation)

```c
svuint64_t svcvt_u64[_f32]_z(svbool_t pg, svfloat32_t op);
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
FCVTZU Zresult.D, Pg/M, Zop.S  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCVTZU--Floating-point-convert-to-unsigned-integer--rounding-toward-zero--predicated--

### Operation

Source operation ID: `SveOperation_svcvt_u64_f32_z`

**Operation**



Return a vector in which each active element *i* contains `(uint64_t)op[i * 2]`, rounding towards zero and saturating to the range of `uint64_t`. Set the inactive elements of the result to zero.



**Exceptions**



Active signaling and quiet NaNs both trigger an IEEE Invalid exception.



**[1]** Note that `result` must be in a different register from `op`

## svcvt_u64[_f64]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvt_u64%5B_f64%5D_m

### Signature (source notation)

```c
svuint64_t svcvt_u64[_f64]_m(svuint64_t inactive, svbool_t pg, svfloat64_t op);
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
FCVTZU Ztied.D, Pg/M, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCVTZU--Floating-point-convert-to-unsigned-integer--rounding-toward-zero--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zinactive
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FCVTZU Zresult.D, Pg/M, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCVTZU--Floating-point-convert-to-unsigned-integer--rounding-toward-zero--predicated--

### Operation

Source operation ID: `SveOperation_svcvt_u64_f64_m`

**Operation**



Return a vector in which each active element *i* contains `(uint64_t)op[i]`, rounding towards zero and saturating to the range of `uint64_t`. Take the inactive elements of the result from the corresponding elements of `inactive`.



**Exceptions**



Active signaling and quiet NaNs both trigger an IEEE Invalid exception.

## svcvt_u64[_f64]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvt_u64%5B_f64%5D_x

### Signature (source notation)

```c
svuint64_t svcvt_u64[_f64]_x(svbool_t pg, svfloat64_t op);
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
FCVTZU Ztied.D, Pg/M, Ztied.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCVTZU--Floating-point-convert-to-unsigned-integer--rounding-toward-zero--predicated--

When result and op are in different registers, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FCVTZU Zresult.D, Pg/M, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCVTZU--Floating-point-convert-to-unsigned-integer--rounding-toward-zero--predicated--

### Operation

Source operation ID: `SveOperation_svcvt_u64_f64_x`

**Operation**



Return a vector in which each active element *i* contains `(uint64_t)op[i]`, rounding towards zero and saturating to the range of `uint64_t`. The inactive elements of the result have arbitrary, undefined values.



**Exceptions**



Active signaling and quiet NaNs both trigger an IEEE Invalid exception.

## svcvt_u64[_f64]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvt_u64%5B_f64%5D_z

### Signature (source notation)

```c
svuint64_t svcvt_u64[_f64]_z(svbool_t pg, svfloat64_t op);
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
FCVTZU Zresult.D, Pg/M, Zop.D  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCVTZU--Floating-point-convert-to-unsigned-integer--rounding-toward-zero--predicated--

### Operation

Source operation ID: `SveOperation_svcvt_u64_f64_z`

**Operation**



Return a vector in which each active element *i* contains `(uint64_t)op[i]`, rounding towards zero and saturating to the range of `uint64_t`. Set the inactive elements of the result to zero.



**Exceptions**



Active signaling and quiet NaNs both trigger an IEEE Invalid exception.



**[1]** Note that `result` must be in a different register from `op`

## svcvtlt_f32[_f16]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvtlt_f32%5B_f16%5D_m

### Signature (source notation)

```c
svfloat32_t svcvtlt_f32[_f16]_m(svfloat32_t inactive, svbool_t pg, svfloat16_t op);
```

### Description

Up convert long (top)

### Availability

- ISA categories: SME and SME2, SVE2

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
    "register": "Ztied.S"
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
    "Ztied.S": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
FCVTLT Ztied.S, Pg/M, Zop.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCVTLT--Floating-point-up-convert-long--top--predicated--

### Operation

Source operation ID: `SveOperation_svcvtlt_f32_f16_m`

**Operation**



Return a vector in which each active element *i* contains `(float32_t)op[i * 2 + 1]`. Take the inactive elements of the result from the corresponding elements of `inactive`.



`svcvt` provides the partnering “up convert long (bottom)” functionality; there is no separate `svcvtnb` function.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.

## svcvtlt_f32[_f16]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvtlt_f32%5B_f16%5D_x

### Signature (source notation)

```c
svfloat32_t svcvtlt_f32[_f16]_x(svbool_t pg, svfloat16_t op);
```

### Description

Up convert long (top)

### Availability

- ISA categories: SME and SME2, SVE2

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
    "register": "Ztied.H"
  }
}
```

### Result mapping

```json
[
  {
    "Ztied.S": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
FCVTLT Ztied.S, Pg/M, Ztied.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCVTLT--Floating-point-up-convert-long--top--predicated--

### Operation

Source operation ID: `SveOperation_svcvtlt_f32_f16_x`

**Operation**



Return a vector in which each active element *i* contains `(float32_t)op[i * 2 + 1]`. The inactive elements of the result have arbitrary, undefined values.



`svcvt` provides the partnering “up convert long (bottom)” functionality; there is no separate `svcvtnb` function.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.

## svcvtlt_f32[_f16]_z

ISA classification: SME + FEAT_SVE2p2 OR SME2.2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvtlt_f32%5B_f16%5D_z

### Signature (source notation)

```c
svfloat32_t svcvtlt_f32[_f16]_z(svbool_t pg, svfloat16_t op);
```

### Description

Floating-point widening convert (top, predicated)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Data type conversion / Conversions

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p2)|FEAT_SME2p2
```

### Return type metadata

```json
{
  "return_base_type": "float32",
  "element_bit_size": "32",
  "value": "svfloat32_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Preg1"
  },
  "op": {
    "register": "Zreg2.H"
  }
}
```

### Result mapping

```json
[
  {
    "Zreg1.S": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
FCVTLT Zreg1.S, Preg1/Z, Zreg2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/FCVTLT--Floating-point-widening-convert--top--predicated--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svcvtlt_f64[_f32]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvtlt_f64%5B_f32%5D_m

### Signature (source notation)

```c
svfloat64_t svcvtlt_f64[_f32]_m(svfloat64_t inactive, svbool_t pg, svfloat32_t op);
```

### Description

Up convert long (top)

### Availability

- ISA categories: SME and SME2, SVE2

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
    "register": "Ztied.D"
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
    "Ztied.D": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
FCVTLT Ztied.D, Pg/M, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCVTLT--Floating-point-up-convert-long--top--predicated--

### Operation

Source operation ID: `SveOperation_svcvtlt_f64_f32_m`

**Operation**



Return a vector in which each active element *i* contains `(float64_t)op[i * 2 + 1]`. Take the inactive elements of the result from the corresponding elements of `inactive`.



`svcvt` provides the partnering “up convert long (bottom)” functionality; there is no separate `svcvtnb` function.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.

## svcvtlt_f64[_f32]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvtlt_f64%5B_f32%5D_x

### Signature (source notation)

```c
svfloat64_t svcvtlt_f64[_f32]_x(svbool_t pg, svfloat32_t op);
```

### Description

Up convert long (top)

### Availability

- ISA categories: SME and SME2, SVE2

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
    "register": "Ztied.S"
  }
}
```

### Result mapping

```json
[
  {
    "Ztied.D": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
FCVTLT Ztied.D, Pg/M, Ztied.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCVTLT--Floating-point-up-convert-long--top--predicated--

### Operation

Source operation ID: `SveOperation_svcvtlt_f64_f32_x`

**Operation**



Return a vector in which each active element *i* contains `(float64_t)op[i * 2 + 1]`. The inactive elements of the result have arbitrary, undefined values.



`svcvt` provides the partnering “up convert long (bottom)” functionality; there is no separate `svcvtnb` function.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.

## svcvtlt_f64[_f32]_z

ISA classification: SME + FEAT_SVE2p2 OR SME2.2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvtlt_f64%5B_f32%5D_z

### Signature (source notation)

```c
svfloat64_t svcvtlt_f64[_f32]_z(svbool_t pg, svfloat32_t op);
```

### Description

Floating-point widening convert (top, predicated)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Data type conversion / Conversions

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p2)|FEAT_SME2p2
```

### Return type metadata

```json
{
  "return_base_type": "float64",
  "element_bit_size": "64",
  "value": "svfloat64_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Preg1"
  },
  "op": {
    "register": "Zreg2.S"
  }
}
```

### Result mapping

```json
[
  {
    "Zreg1.D": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
FCVTLT Zreg1.D, Preg1/Z, Zreg2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/FCVTLT--Floating-point-widening-convert--top--predicated--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svcvtnt_bf16[_f32]_m

ISA classification: SME + FEAT_BF16

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvtnt_bf16%5B_f32%5D_m

### Signature (source notation)

```c
svbfloat16_t svcvtnt_bf16[_f32]_m(svbfloat16_t even, svbool_t pg, svfloat32_t op);
```

### Description

Down convert and narrow (top)

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
  "even": {
    "register": "Ztied.H"
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
    "Ztied.H": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
BFCVTNT Ztied.H, Pg/M, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BFCVTN--BFloat16-convert--narrow-and-interleave-to-8-bit-floating-point-

### Operation

Source operation ID: `SveOperation_svcvtnt_bf16_f32_m`

**Operation**



Convert each active element `op[i]` to `bfloat16_t`, rounding according to the current rounding mode.  Return the converted value in element `i * 2 + 1` of the result vector.  Set element `i * 2` of the result vector to `even[i * 2]`.



Take the inactive elements of the result from the corresponding elements of `even`.



`svcvt` provides the partnering “down convert and narrow (bottom)” functionality; there is no separate `svcvtnb` function.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.

## svcvtnt_bf16[_f32]_z

ISA classification: SME + FEAT_SVE2p2 OR SME2.2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvtnt_bf16%5B_f32%5D_z

### Signature (source notation)

```c
svbfloat16_t svcvtnt_bf16[_f32]_z(svbfloat16_t even, svbool_t pg, svfloat32_t op);
```

### Description

Single-precision convert to BFloat16 (top, predicated)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Data type conversion / Conversions

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p2)|FEAT_SME2p2
```

### Return type metadata

```json
{
  "return_base_type": "bfloat16",
  "element_bit_size": "16",
  "value": "svbfloat16_t"
}
```

### Argument preparation and constraints

```json
{
  "even": {
    "register": "Zreg1.H"
  },
  "pg": {
    "register": "Preg1"
  },
  "op": {
    "register": "Zreg2.S"
  }
}
```

### Result mapping

```json
[
  {
    "Zreg1.H": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
BFCVTNT Zreg1.H, Preg1/Z, Zreg2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/BFCVTNT--Single-precision-convert-to-BFloat16--top--predicated--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svcvtnt_f16[_f32]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvtnt_f16%5B_f32%5D_m

### Signature (source notation)

```c
svfloat16_t svcvtnt_f16[_f32]_m(svfloat16_t even, svbool_t pg, svfloat32_t op);
```

### Description

Down convert and narrow (top)

### Availability

- ISA categories: SME and SME2, SVE2

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
  "even": {
    "register": "Ztied.H"
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
    "Ztied.H": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
FCVTNT Ztied.H, Pg/M, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCVTNT--predicated---Floating-point-down-convert-and-narrow--top--predicated--

### Operation

Source operation ID: `SveOperation_svcvtnt_f16_f32_m`

**Operation**



Convert each active element `op[i]` to `float16_t`, rounding according to the current rounding mode.  Return the converted value in element `i * 2 + 1` of the result vector.  Set element `i * 2` of the result vector to `even[i * 2]`.



Take the inactive elements of the result from the corresponding elements of `even`.



`svcvt` provides the partnering “down convert and narrow (bottom)” functionality; there is no separate `svcvtnb` function.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.

## svcvtnt_f16[_f32]_z

ISA classification: SME + FEAT_SVE2p2 OR SME2.2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvtnt_f16%5B_f32%5D_z

### Signature (source notation)

```c
svfloat16_t svcvtnt_f16[_f32]_z(svfloat16_t even, svbool_t pg, svfloat32_t op);
```

### Description

Floating-point narrowing convert (top, predicated)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Data type conversion / Conversions

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p2)|FEAT_SME2p2
```

### Return type metadata

```json
{
  "return_base_type": "float16",
  "element_bit_size": "16",
  "value": "svfloat16_t"
}
```

### Argument preparation and constraints

```json
{
  "even": {
    "register": "Zreg1.H"
  },
  "pg": {
    "register": "Preg1"
  },
  "op": {
    "register": "Zreg2.S"
  }
}
```

### Result mapping

```json
[
  {
    "Zreg1.H": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
FCVTNT Zreg1.H, Preg1/Z, Zreg2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/FCVTNT--predicated---Floating-point-narrowing-convert--top--predicated--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svcvtnt_f32[_f64]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvtnt_f32%5B_f64%5D_m

### Signature (source notation)

```c
svfloat32_t svcvtnt_f32[_f64]_m(svfloat32_t even, svbool_t pg, svfloat64_t op);
```

### Description

Down convert and narrow (top)

### Availability

- ISA categories: SME and SME2, SVE2

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
  "even": {
    "register": "Ztied.S"
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
    "Ztied.S": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
FCVTNT Ztied.S, Pg/M, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCVTNT--predicated---Floating-point-down-convert-and-narrow--top--predicated--

### Operation

Source operation ID: `SveOperation_svcvtnt_f32_f64_m`

**Operation**



Convert each active element `op[i]` to `float32_t`, rounding according to the current rounding mode.  Return the converted value in element `i * 2 + 1` of the result vector.  Set element `i * 2` of the result vector to `even[i * 2]`.



Take the inactive elements of the result from the corresponding elements of `even`.



`svcvt` provides the partnering “down convert and narrow (bottom)” functionality; there is no separate `svcvtnb` function.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.

## svcvtnt_f32[_f64]_z

ISA classification: SME + FEAT_SVE2p2 OR SME2.2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvtnt_f32%5B_f64%5D_z

### Signature (source notation)

```c
svfloat32_t svcvtnt_f32[_f64]_z(svfloat32_t even, svbool_t pg, svfloat64_t op);
```

### Description

Floating-point narrowing convert (top, predicated)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Data type conversion / Conversions

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p2)|FEAT_SME2p2
```

### Return type metadata

```json
{
  "return_base_type": "float32",
  "element_bit_size": "32",
  "value": "svfloat32_t"
}
```

### Argument preparation and constraints

```json
{
  "even": {
    "register": "Zreg1.S"
  },
  "pg": {
    "register": "Preg1"
  },
  "op": {
    "register": "Zreg2.D"
  }
}
```

### Result mapping

```json
[
  {
    "Zreg1.S": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
FCVTNT Zreg1.S, Preg1/Z, Zreg2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/FCVTNT--predicated---Floating-point-narrowing-convert--top--predicated--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svcvtx_f32[_f64]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvtx_f32%5B_f64%5D_m

### Signature (source notation)

```c
svfloat32_t svcvtx_f32[_f64]_m(svfloat32_t inactive, svbool_t pg, svfloat64_t op);
```

### Description

Down convert, rounding to odd

### Availability

- ISA categories: SME and SME2, SVE2

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
FCVTX Ztied.S, Pg/M, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCVTX--Double-precision-down-convert-to-single-precision--rounding-to-odd--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zinactive
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FCVTX Zresult.S, Pg/M, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCVTX--Double-precision-down-convert-to-single-precision--rounding-to-odd--predicated--

### Operation

Source operation ID: `SveOperation_svcvtx_f32_f64_m`

**Operation**



Convert each active element `op[i]` to `float32_t`, rounding to odd. Return the converted value in element `i * 2` of the result vector and return zero in element `i * 2 + 1`.



Take the inactive elements of the result from the corresponding elements of `inactive`.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.

## svcvtx_f32[_f64]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvtx_f32%5B_f64%5D_x

### Signature (source notation)

```c
svfloat32_t svcvtx_f32[_f64]_x(svbool_t pg, svfloat64_t op);
```

### Description

Down convert, rounding to odd

### Availability

- ISA categories: SME and SME2, SVE2

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
FCVTX Ztied.S, Pg/M, Ztied.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCVTX--Double-precision-down-convert-to-single-precision--rounding-to-odd--predicated--

When result and op are in different registers, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FCVTX Zresult.S, Pg/M, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCVTX--Double-precision-down-convert-to-single-precision--rounding-to-odd--predicated--

### Operation

Source operation ID: `SveOperation_svcvtx_f32_f64_x`

**Operation**



Convert each active element `op[i]` to `float32_t`, rounding to odd. Return the converted value in element `i * 2` of the result vector and return zero in element `i * 2 + 1`.



The inactive elements of the result have arbitrary, undefined values.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.

## svcvtx_f32[_f64]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvtx_f32%5B_f64%5D_z

### Signature (source notation)

```c
svfloat32_t svcvtx_f32[_f64]_z(svbool_t pg, svfloat64_t op);
```

### Description

Down convert, rounding to odd

### Availability

- ISA categories: SME and SME2, SVE2

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
FCVTX Zresult.S, Pg/M, Zop.D  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCVTX--Double-precision-down-convert-to-single-precision--rounding-to-odd--predicated--

### Operation

Source operation ID: `SveOperation_svcvtx_f32_f64_z`

**Operation**



Convert each active element `op[i]` to `float32_t`, rounding to odd. Return the converted value in element `i * 2` of the result vector and return zero in element `i * 2 + 1`.



Set the inactive elements of the result to zero.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.



**[1]** Note that `result` must be in a different register from `op`

## svcvtxnt_f32[_f64]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvtxnt_f32%5B_f64%5D_m

### Signature (source notation)

```c
svfloat32_t svcvtxnt_f32[_f64]_m(svfloat32_t even, svbool_t pg, svfloat64_t op);
```

### Description

Down convert, rounding to odd (top)

### Availability

- ISA categories: SME and SME2, SVE2

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
  "even": {
    "register": "Ztied.S"
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
    "Ztied.S": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
FCVTXNT Ztied.S, Pg/M, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCVTXNT--Double-precision-down-convert-to-single-precision--rounding-to-odd--top--predicated--

### Operation

Source operation ID: `SveOperation_svcvtxnt_f32_f64_m`

**Operation**



Convert each active element `op[i]` to `float32_t`, rounding to odd. Return the converted value in element `i * 2 + 1` of the result vector and return `even[i * 2]` in element `i * 2`.



Take the inactive elements of the result from the corresponding elements of `even`.



`svcvtx` provides the partnering “down convert, rounding to odd (bottom)” functionality; there is no separate `svcvtxnb` function.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.

## svcvtxnt_f32[_f64]_z

ISA classification: SME + FEAT_SVE2p2 OR SME2.2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvtxnt_f32%5B_f64%5D_z

### Signature (source notation)

```c
svfloat32_t svcvtxnt_f32[_f64]_z(svfloat32_t even, svbool_t pg, svfloat64_t op);
```

### Description

Double-precision convert to single-precision, rounding to odd (top, predicated)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Data type conversion / Conversions

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p2)|FEAT_SME2p2
```

### Return type metadata

```json
{
  "return_base_type": "float32",
  "element_bit_size": "32",
  "value": "svfloat32_t"
}
```

### Argument preparation and constraints

```json
{
  "even": {
    "register": "Zreg1.S"
  },
  "pg": {
    "register": "Preg1"
  },
  "op": {
    "register": "Zreg2.D"
  }
}
```

### Result mapping

```json
[
  {
    "Zreg1.S": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
FCVTXNT Zreg1.S, Preg1/Z, Zreg2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/FCVTXNT--Double-precision-convert-to-single-precision--rounding-to-odd--top--predicated--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

