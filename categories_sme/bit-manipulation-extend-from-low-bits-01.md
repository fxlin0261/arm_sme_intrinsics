# SME / Bit manipulation / Extend from low bits — Part 1

## svextb[_s16]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svextb%5B_s16%5D_m

### Signature (source notation)

```c
svint16_t svextb[_s16]_m(svint16_t inactive, svbool_t pg, svint16_t op);
```

### Description

Sign-extend the low 8 bits

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Bit manipulation / Extend from low bits

- SME attributes: Not specified by source.

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
SXTB Ztied.H, Pg/M, Zop.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SXTB--SXTH--SXTW--Signed-byte---halfword---word-extend--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zinactive
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SXTB Zresult.H, Pg/M, Zop.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SXTB--SXTH--SXTW--Signed-byte---halfword---word-extend--predicated--

### Operation

Source operation ID: `SveOperation_svextb_s16_m`

**Operation**



For each active element *i*, sign-extend the low 8 bits of `op[i]` to the width of an element and return the extended value in element *i* of the result vector.



Take the inactive elements of the result from the corresponding elements of `inactive`.

## svextb[_s16]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svextb%5B_s16%5D_x

### Signature (source notation)

```c
svint16_t svextb[_s16]_x(svbool_t pg, svint16_t op);
```

### Description

Sign-extend the low 8 bits

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Bit manipulation / Extend from low bits

- SME attributes: Not specified by source.

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
SXTB Ztied.H, Pg/M, Ztied.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SXTB--SXTH--SXTW--Signed-byte---halfword---word-extend--predicated--

When result and op are in different registers, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SXTB Zresult.H, Pg/M, Zop.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SXTB--SXTH--SXTW--Signed-byte---halfword---word-extend--predicated--

### Operation

Source operation ID: `SveOperation_svextb_s16_x`

**Operation**



For each active element *i*, sign-extend the low 8 bits of `op[i]` to the width of an element and return the extended value in element *i* of the result vector.



The inactive elements of the result have arbitrary, undefined values.

## svextb[_s16]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svextb%5B_s16%5D_z

### Signature (source notation)

```c
svint16_t svextb[_s16]_z(svbool_t pg, svint16_t op);
```

### Description

Sign-extend the low 8 bits

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Bit manipulation / Extend from low bits

- SME attributes: Not specified by source.

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
SXTB Zresult.H, Pg/M, Zop.H  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SXTB--SXTH--SXTW--Signed-byte---halfword---word-extend--predicated--

### Operation

Source operation ID: `SveOperation_svextb_s16_z`

**Operation**



For each active element *i*, sign-extend the low 8 bits of `op[i]` to the width of an element and return the extended value in element *i* of the result vector.



Set the inactive elements of the result to zero.



**[1]** Note that `result` must be in a different register from `op`

## svextb[_s32]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svextb%5B_s32%5D_m

### Signature (source notation)

```c
svint32_t svextb[_s32]_m(svint32_t inactive, svbool_t pg, svint32_t op);
```

### Description

Sign-extend the low 8 bits

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Bit manipulation / Extend from low bits

- SME attributes: Not specified by source.

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
SXTB Ztied.S, Pg/M, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SXTB--SXTH--SXTW--Signed-byte---halfword---word-extend--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zinactive
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SXTB Zresult.S, Pg/M, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SXTB--SXTH--SXTW--Signed-byte---halfword---word-extend--predicated--

### Operation

Source operation ID: `SveOperation_svextb_s16_m`

**Operation**



For each active element *i*, sign-extend the low 8 bits of `op[i]` to the width of an element and return the extended value in element *i* of the result vector.



Take the inactive elements of the result from the corresponding elements of `inactive`.

## svextb[_s32]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svextb%5B_s32%5D_x

### Signature (source notation)

```c
svint32_t svextb[_s32]_x(svbool_t pg, svint32_t op);
```

### Description

Sign-extend the low 8 bits

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Bit manipulation / Extend from low bits

- SME attributes: Not specified by source.

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
SXTB Ztied.S, Pg/M, Ztied.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SXTB--SXTH--SXTW--Signed-byte---halfword---word-extend--predicated--

When result and op are in different registers, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SXTB Zresult.S, Pg/M, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SXTB--SXTH--SXTW--Signed-byte---halfword---word-extend--predicated--

### Operation

Source operation ID: `SveOperation_svextb_s16_x`

**Operation**



For each active element *i*, sign-extend the low 8 bits of `op[i]` to the width of an element and return the extended value in element *i* of the result vector.



The inactive elements of the result have arbitrary, undefined values.

## svextb[_s32]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svextb%5B_s32%5D_z

### Signature (source notation)

```c
svint32_t svextb[_s32]_z(svbool_t pg, svint32_t op);
```

### Description

Sign-extend the low 8 bits

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Bit manipulation / Extend from low bits

- SME attributes: Not specified by source.

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
SXTB Zresult.S, Pg/M, Zop.S  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SXTB--SXTH--SXTW--Signed-byte---halfword---word-extend--predicated--

### Operation

Source operation ID: `SveOperation_svextb_s16_z`

**Operation**



For each active element *i*, sign-extend the low 8 bits of `op[i]` to the width of an element and return the extended value in element *i* of the result vector.



Set the inactive elements of the result to zero.



**[1]** Note that `result` must be in a different register from `op`

## svextb[_s64]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svextb%5B_s64%5D_m

### Signature (source notation)

```c
svint64_t svextb[_s64]_m(svint64_t inactive, svbool_t pg, svint64_t op);
```

### Description

Sign-extend the low 8 bits

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Bit manipulation / Extend from low bits

- SME attributes: Not specified by source.

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
SXTB Ztied.D, Pg/M, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SXTB--SXTH--SXTW--Signed-byte---halfword---word-extend--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zinactive
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SXTB Zresult.D, Pg/M, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SXTB--SXTH--SXTW--Signed-byte---halfword---word-extend--predicated--

### Operation

Source operation ID: `SveOperation_svextb_s16_m`

**Operation**



For each active element *i*, sign-extend the low 8 bits of `op[i]` to the width of an element and return the extended value in element *i* of the result vector.



Take the inactive elements of the result from the corresponding elements of `inactive`.

## svextb[_s64]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svextb%5B_s64%5D_x

### Signature (source notation)

```c
svint64_t svextb[_s64]_x(svbool_t pg, svint64_t op);
```

### Description

Sign-extend the low 8 bits

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Bit manipulation / Extend from low bits

- SME attributes: Not specified by source.

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
SXTB Ztied.D, Pg/M, Ztied.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SXTB--SXTH--SXTW--Signed-byte---halfword---word-extend--predicated--

When result and op are in different registers, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SXTB Zresult.D, Pg/M, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SXTB--SXTH--SXTW--Signed-byte---halfword---word-extend--predicated--

### Operation

Source operation ID: `SveOperation_svextb_s16_x`

**Operation**



For each active element *i*, sign-extend the low 8 bits of `op[i]` to the width of an element and return the extended value in element *i* of the result vector.



The inactive elements of the result have arbitrary, undefined values.

## svextb[_s64]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svextb%5B_s64%5D_z

### Signature (source notation)

```c
svint64_t svextb[_s64]_z(svbool_t pg, svint64_t op);
```

### Description

Sign-extend the low 8 bits

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Bit manipulation / Extend from low bits

- SME attributes: Not specified by source.

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
SXTB Zresult.D, Pg/M, Zop.D  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SXTB--SXTH--SXTW--Signed-byte---halfword---word-extend--predicated--

### Operation

Source operation ID: `SveOperation_svextb_s16_z`

**Operation**



For each active element *i*, sign-extend the low 8 bits of `op[i]` to the width of an element and return the extended value in element *i* of the result vector.



Set the inactive elements of the result to zero.



**[1]** Note that `result` must be in a different register from `op`

## svextb[_u16]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svextb%5B_u16%5D_m

### Signature (source notation)

```c
svuint16_t svextb[_u16]_m(svuint16_t inactive, svbool_t pg, svuint16_t op);
```

### Description

Zero-extend the low 8 bits

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Bit manipulation / Extend from low bits

- SME attributes: Not specified by source.

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
UXTB Ztied.H, Pg/M, Zop.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UXTB--UXTH--UXTW--Unsigned-byte---halfword---word-extend--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zinactive
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
UXTB Zresult.H, Pg/M, Zop.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UXTB--UXTH--UXTW--Unsigned-byte---halfword---word-extend--predicated--

### Operation

Source operation ID: `SveOperation_svextb_u16_m`

**Operation**



For each active element *i*, zero-extend the low 8 bits of `op[i]` to the width of an element and return the extended value in element *i* of the result vector.



Take the inactive elements of the result from the corresponding elements of `inactive`.

## svextb[_u16]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svextb%5B_u16%5D_x

### Signature (source notation)

```c
svuint16_t svextb[_u16]_x(svbool_t pg, svuint16_t op);
```

### Description

Zero-extend the low 8 bits

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Bit manipulation / Extend from low bits

- SME attributes: Not specified by source.

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
    "register": "Ztied.H"
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

This intrinsic compiles to:

```asm
UXTB Ztied.H, Pg/M, Ztied.H  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UXTB--UXTH--UXTW--Unsigned-byte---halfword---word-extend--predicated--

…or, alternatively:

```asm
AND Ztied.H, Ztied.H, #255  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/AND--immediate---Bitwise-AND-with-immediate--unpredicated--

### Operation

Source operation ID: `SveOperation_svextb_u16_x`

**Operation**



For each active element *i*, zero-extend the low 8 bits of `op[i]` to the width of an element and return the extended value in element *i* of the result vector.



The inactive elements of the result have arbitrary, undefined values.



**[1]** If instead `result` and `op` are in different registers, the compiler can add a preceding [MOVPRFX (unpredicated)](https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--) instruction

## svextb[_u16]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svextb%5B_u16%5D_z

### Signature (source notation)

```c
svuint16_t svextb[_u16]_z(svbool_t pg, svuint16_t op);
```

### Description

Zero-extend the low 8 bits

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Bit manipulation / Extend from low bits

- SME attributes: Not specified by source.

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
UXTB Zresult.H, Pg/M, Zop.H  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UXTB--UXTH--UXTW--Unsigned-byte---halfword---word-extend--predicated--

### Operation

Source operation ID: `SveOperation_svextb_u16_z`

**Operation**



For each active element *i*, zero-extend the low 8 bits of `op[i]` to the width of an element and return the extended value in element *i* of the result vector.



Set the inactive elements of the result to zero.



**[1]** Note that `result` must be in a different register from `op`

## svextb[_u32]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svextb%5B_u32%5D_m

### Signature (source notation)

```c
svuint32_t svextb[_u32]_m(svuint32_t inactive, svbool_t pg, svuint32_t op);
```

### Description

Zero-extend the low 8 bits

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Bit manipulation / Extend from low bits

- SME attributes: Not specified by source.

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
UXTB Ztied.S, Pg/M, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UXTB--UXTH--UXTW--Unsigned-byte---halfword---word-extend--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zinactive
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
UXTB Zresult.S, Pg/M, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UXTB--UXTH--UXTW--Unsigned-byte---halfword---word-extend--predicated--

### Operation

Source operation ID: `SveOperation_svextb_u16_m`

**Operation**



For each active element *i*, zero-extend the low 8 bits of `op[i]` to the width of an element and return the extended value in element *i* of the result vector.



Take the inactive elements of the result from the corresponding elements of `inactive`.

## svextb[_u32]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svextb%5B_u32%5D_x

### Signature (source notation)

```c
svuint32_t svextb[_u32]_x(svbool_t pg, svuint32_t op);
```

### Description

Zero-extend the low 8 bits

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Bit manipulation / Extend from low bits

- SME attributes: Not specified by source.

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
    "register": "Ztied.S"
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

This intrinsic compiles to:

```asm
UXTB Ztied.S, Pg/M, Ztied.S  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UXTB--UXTH--UXTW--Unsigned-byte---halfword---word-extend--predicated--

…or, alternatively:

```asm
AND Ztied.S, Ztied.S, #255  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/AND--immediate---Bitwise-AND-with-immediate--unpredicated--

### Operation

Source operation ID: `SveOperation_svextb_u16_x`

**Operation**



For each active element *i*, zero-extend the low 8 bits of `op[i]` to the width of an element and return the extended value in element *i* of the result vector.



The inactive elements of the result have arbitrary, undefined values.



**[1]** If instead `result` and `op` are in different registers, the compiler can add a preceding [MOVPRFX (unpredicated)](https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--) instruction

## svextb[_u32]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svextb%5B_u32%5D_z

### Signature (source notation)

```c
svuint32_t svextb[_u32]_z(svbool_t pg, svuint32_t op);
```

### Description

Zero-extend the low 8 bits

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Bit manipulation / Extend from low bits

- SME attributes: Not specified by source.

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
UXTB Zresult.S, Pg/M, Zop.S  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UXTB--UXTH--UXTW--Unsigned-byte---halfword---word-extend--predicated--

### Operation

Source operation ID: `SveOperation_svextb_u16_z`

**Operation**



For each active element *i*, zero-extend the low 8 bits of `op[i]` to the width of an element and return the extended value in element *i* of the result vector.



Set the inactive elements of the result to zero.



**[1]** Note that `result` must be in a different register from `op`

## svextb[_u64]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svextb%5B_u64%5D_m

### Signature (source notation)

```c
svuint64_t svextb[_u64]_m(svuint64_t inactive, svbool_t pg, svuint64_t op);
```

### Description

Zero-extend the low 8 bits

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Bit manipulation / Extend from low bits

- SME attributes: Not specified by source.

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
UXTB Ztied.D, Pg/M, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UXTB--UXTH--UXTW--Unsigned-byte---halfword---word-extend--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zinactive
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
UXTB Zresult.D, Pg/M, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UXTB--UXTH--UXTW--Unsigned-byte---halfword---word-extend--predicated--

### Operation

Source operation ID: `SveOperation_svextb_u16_m`

**Operation**



For each active element *i*, zero-extend the low 8 bits of `op[i]` to the width of an element and return the extended value in element *i* of the result vector.



Take the inactive elements of the result from the corresponding elements of `inactive`.

## svextb[_u64]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svextb%5B_u64%5D_x

### Signature (source notation)

```c
svuint64_t svextb[_u64]_x(svbool_t pg, svuint64_t op);
```

### Description

Zero-extend the low 8 bits

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Bit manipulation / Extend from low bits

- SME attributes: Not specified by source.

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
    "register": "Ztied.D"
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

This intrinsic compiles to:

```asm
UXTB Ztied.D, Pg/M, Ztied.D  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UXTB--UXTH--UXTW--Unsigned-byte---halfword---word-extend--predicated--

…or, alternatively:

```asm
AND Ztied.D, Ztied.D, #255  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/AND--immediate---Bitwise-AND-with-immediate--unpredicated--

### Operation

Source operation ID: `SveOperation_svextb_u16_x`

**Operation**



For each active element *i*, zero-extend the low 8 bits of `op[i]` to the width of an element and return the extended value in element *i* of the result vector.



The inactive elements of the result have arbitrary, undefined values.



**[1]** If instead `result` and `op` are in different registers, the compiler can add a preceding [MOVPRFX (unpredicated)](https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--) instruction

## svextb[_u64]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svextb%5B_u64%5D_z

### Signature (source notation)

```c
svuint64_t svextb[_u64]_z(svbool_t pg, svuint64_t op);
```

### Description

Zero-extend the low 8 bits

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Bit manipulation / Extend from low bits

- SME attributes: Not specified by source.

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
UXTB Zresult.D, Pg/M, Zop.D  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UXTB--UXTH--UXTW--Unsigned-byte---halfword---word-extend--predicated--

### Operation

Source operation ID: `SveOperation_svextb_u16_z`

**Operation**



For each active element *i*, zero-extend the low 8 bits of `op[i]` to the width of an element and return the extended value in element *i* of the result vector.



Set the inactive elements of the result to zero.



**[1]** Note that `result` must be in a different register from `op`

## svexth[_s32]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svexth%5B_s32%5D_m

### Signature (source notation)

```c
svint32_t svexth[_s32]_m(svint32_t inactive, svbool_t pg, svint32_t op);
```

### Description

Sign-extend the low 16 bits

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Bit manipulation / Extend from low bits

- SME attributes: Not specified by source.

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
SXTH Ztied.S, Pg/M, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SXTB--SXTH--SXTW--Signed-byte---halfword---word-extend--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zinactive
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SXTH Zresult.S, Pg/M, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SXTB--SXTH--SXTW--Signed-byte---halfword---word-extend--predicated--

### Operation

Source operation ID: `SveOperation_svexth_s32_m`

**Operation**



For each active element *i*, sign-extend the low 16 bits of `op[i]` to the width of an element and return the extended value in element *i* of the result vector.



Take the inactive elements of the result from the corresponding elements of `inactive`.

## svexth[_s32]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svexth%5B_s32%5D_x

### Signature (source notation)

```c
svint32_t svexth[_s32]_x(svbool_t pg, svint32_t op);
```

### Description

Sign-extend the low 16 bits

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Bit manipulation / Extend from low bits

- SME attributes: Not specified by source.

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
SXTH Ztied.S, Pg/M, Ztied.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SXTB--SXTH--SXTW--Signed-byte---halfword---word-extend--predicated--

When result and op are in different registers, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SXTH Zresult.S, Pg/M, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SXTB--SXTH--SXTW--Signed-byte---halfword---word-extend--predicated--

### Operation

Source operation ID: `SveOperation_svexth_s32_x`

**Operation**



For each active element *i*, sign-extend the low 16 bits of `op[i]` to the width of an element and return the extended value in element *i* of the result vector.



The inactive elements of the result have arbitrary, undefined values.

## svexth[_s32]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svexth%5B_s32%5D_z

### Signature (source notation)

```c
svint32_t svexth[_s32]_z(svbool_t pg, svint32_t op);
```

### Description

Sign-extend the low 16 bits

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Bit manipulation / Extend from low bits

- SME attributes: Not specified by source.

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
SXTH Zresult.S, Pg/M, Zop.S  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SXTB--SXTH--SXTW--Signed-byte---halfword---word-extend--predicated--

### Operation

Source operation ID: `SveOperation_svexth_s32_z`

**Operation**



For each active element *i*, sign-extend the low 16 bits of `op[i]` to the width of an element and return the extended value in element *i* of the result vector.



Set the inactive elements of the result to zero.



**[1]** Note that `result` must be in a different register from `op`

## svexth[_s64]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svexth%5B_s64%5D_m

### Signature (source notation)

```c
svint64_t svexth[_s64]_m(svint64_t inactive, svbool_t pg, svint64_t op);
```

### Description

Sign-extend the low 16 bits

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Bit manipulation / Extend from low bits

- SME attributes: Not specified by source.

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
SXTH Ztied.D, Pg/M, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SXTB--SXTH--SXTW--Signed-byte---halfword---word-extend--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zinactive
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SXTH Zresult.D, Pg/M, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SXTB--SXTH--SXTW--Signed-byte---halfword---word-extend--predicated--

### Operation

Source operation ID: `SveOperation_svexth_s32_m`

**Operation**



For each active element *i*, sign-extend the low 16 bits of `op[i]` to the width of an element and return the extended value in element *i* of the result vector.



Take the inactive elements of the result from the corresponding elements of `inactive`.

## svexth[_s64]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svexth%5B_s64%5D_x

### Signature (source notation)

```c
svint64_t svexth[_s64]_x(svbool_t pg, svint64_t op);
```

### Description

Sign-extend the low 16 bits

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Bit manipulation / Extend from low bits

- SME attributes: Not specified by source.

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
SXTH Ztied.D, Pg/M, Ztied.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SXTB--SXTH--SXTW--Signed-byte---halfword---word-extend--predicated--

When result and op are in different registers, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SXTH Zresult.D, Pg/M, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SXTB--SXTH--SXTW--Signed-byte---halfword---word-extend--predicated--

### Operation

Source operation ID: `SveOperation_svexth_s32_x`

**Operation**



For each active element *i*, sign-extend the low 16 bits of `op[i]` to the width of an element and return the extended value in element *i* of the result vector.



The inactive elements of the result have arbitrary, undefined values.

## svexth[_s64]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svexth%5B_s64%5D_z

### Signature (source notation)

```c
svint64_t svexth[_s64]_z(svbool_t pg, svint64_t op);
```

### Description

Sign-extend the low 16 bits

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Bit manipulation / Extend from low bits

- SME attributes: Not specified by source.

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
SXTH Zresult.D, Pg/M, Zop.D  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SXTB--SXTH--SXTW--Signed-byte---halfword---word-extend--predicated--

### Operation

Source operation ID: `SveOperation_svexth_s32_z`

**Operation**



For each active element *i*, sign-extend the low 16 bits of `op[i]` to the width of an element and return the extended value in element *i* of the result vector.



Set the inactive elements of the result to zero.



**[1]** Note that `result` must be in a different register from `op`

## svexth[_u32]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svexth%5B_u32%5D_m

### Signature (source notation)

```c
svuint32_t svexth[_u32]_m(svuint32_t inactive, svbool_t pg, svuint32_t op);
```

### Description

Zero-extend the low 16 bits

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Bit manipulation / Extend from low bits

- SME attributes: Not specified by source.

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
UXTH Ztied.S, Pg/M, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UXTB--UXTH--UXTW--Unsigned-byte---halfword---word-extend--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zinactive
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
UXTH Zresult.S, Pg/M, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UXTB--UXTH--UXTW--Unsigned-byte---halfword---word-extend--predicated--

### Operation

Source operation ID: `SveOperation_svexth_u32_m`

**Operation**



For each active element *i*, zero-extend the low 16 bits of `op[i]` to the width of an element and return the extended value in element *i* of the result vector.



Take the inactive elements of the result from the corresponding elements of `inactive`.

## svexth[_u32]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svexth%5B_u32%5D_x

### Signature (source notation)

```c
svuint32_t svexth[_u32]_x(svbool_t pg, svuint32_t op);
```

### Description

Zero-extend the low 16 bits

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Bit manipulation / Extend from low bits

- SME attributes: Not specified by source.

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
    "register": "Ztied.S"
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

This intrinsic compiles to:

```asm
UXTH Ztied.S, Pg/M, Ztied.S  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UXTB--UXTH--UXTW--Unsigned-byte---halfword---word-extend--predicated--

…or, alternatively:

```asm
AND Ztied.S, Ztied.S, #65535  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/AND--immediate---Bitwise-AND-with-immediate--unpredicated--

### Operation

Source operation ID: `SveOperation_svexth_u32_x`

**Operation**



For each active element *i*, zero-extend the low 16 bits of `op[i]` to the width of an element and return the extended value in element *i* of the result vector.



The inactive elements of the result have arbitrary, undefined values.



**[1]** If instead `result` and `op` are in different registers, the compiler can add a preceding [MOVPRFX (unpredicated)](https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--) instruction

## svexth[_u32]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svexth%5B_u32%5D_z

### Signature (source notation)

```c
svuint32_t svexth[_u32]_z(svbool_t pg, svuint32_t op);
```

### Description

Zero-extend the low 16 bits

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Bit manipulation / Extend from low bits

- SME attributes: Not specified by source.

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
UXTH Zresult.S, Pg/M, Zop.S  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UXTB--UXTH--UXTW--Unsigned-byte---halfword---word-extend--predicated--

### Operation

Source operation ID: `SveOperation_svexth_u32_z`

**Operation**



For each active element *i*, zero-extend the low 16 bits of `op[i]` to the width of an element and return the extended value in element *i* of the result vector.



Set the inactive elements of the result to zero.



**[1]** Note that `result` must be in a different register from `op`

## svexth[_u64]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svexth%5B_u64%5D_m

### Signature (source notation)

```c
svuint64_t svexth[_u64]_m(svuint64_t inactive, svbool_t pg, svuint64_t op);
```

### Description

Zero-extend the low 16 bits

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Bit manipulation / Extend from low bits

- SME attributes: Not specified by source.

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
UXTH Ztied.D, Pg/M, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UXTB--UXTH--UXTW--Unsigned-byte---halfword---word-extend--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zinactive
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
UXTH Zresult.D, Pg/M, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UXTB--UXTH--UXTW--Unsigned-byte---halfword---word-extend--predicated--

### Operation

Source operation ID: `SveOperation_svexth_u32_m`

**Operation**



For each active element *i*, zero-extend the low 16 bits of `op[i]` to the width of an element and return the extended value in element *i* of the result vector.



Take the inactive elements of the result from the corresponding elements of `inactive`.

## svexth[_u64]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svexth%5B_u64%5D_x

### Signature (source notation)

```c
svuint64_t svexth[_u64]_x(svbool_t pg, svuint64_t op);
```

### Description

Zero-extend the low 16 bits

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Bit manipulation / Extend from low bits

- SME attributes: Not specified by source.

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
    "register": "Ztied.D"
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

This intrinsic compiles to:

```asm
UXTH Ztied.D, Pg/M, Ztied.D  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UXTB--UXTH--UXTW--Unsigned-byte---halfword---word-extend--predicated--

…or, alternatively:

```asm
AND Ztied.D, Ztied.D, #65535  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/AND--immediate---Bitwise-AND-with-immediate--unpredicated--

### Operation

Source operation ID: `SveOperation_svexth_u32_x`

**Operation**



For each active element *i*, zero-extend the low 16 bits of `op[i]` to the width of an element and return the extended value in element *i* of the result vector.



The inactive elements of the result have arbitrary, undefined values.



**[1]** If instead `result` and `op` are in different registers, the compiler can add a preceding [MOVPRFX (unpredicated)](https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--) instruction

## svexth[_u64]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svexth%5B_u64%5D_z

### Signature (source notation)

```c
svuint64_t svexth[_u64]_z(svbool_t pg, svuint64_t op);
```

### Description

Zero-extend the low 16 bits

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Bit manipulation / Extend from low bits

- SME attributes: Not specified by source.

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
UXTH Zresult.D, Pg/M, Zop.D  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UXTB--UXTH--UXTW--Unsigned-byte---halfword---word-extend--predicated--

### Operation

Source operation ID: `SveOperation_svexth_u32_z`

**Operation**



For each active element *i*, zero-extend the low 16 bits of `op[i]` to the width of an element and return the extended value in element *i* of the result vector.



Set the inactive elements of the result to zero.



**[1]** Note that `result` must be in a different register from `op`

## svextw[_s64]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svextw%5B_s64%5D_m

### Signature (source notation)

```c
svint64_t svextw[_s64]_m(svint64_t inactive, svbool_t pg, svint64_t op);
```

### Description

Sign-extend the low 32 bits

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Bit manipulation / Extend from low bits

- SME attributes: Not specified by source.

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
SXTW Ztied.D, Pg/M, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SXTB--SXTH--SXTW--Signed-byte---halfword---word-extend--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zinactive
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SXTW Zresult.D, Pg/M, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SXTB--SXTH--SXTW--Signed-byte---halfword---word-extend--predicated--

### Operation

Source operation ID: `SveOperation_svextw_s64_m`

**Operation**



For each active element *i*, sign-extend the low 32 bits of `op[i]` to the width of an element and return the extended value in element *i* of the result vector.



Take the inactive elements of the result from the corresponding elements of `inactive`.

## svextw[_s64]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svextw%5B_s64%5D_x

### Signature (source notation)

```c
svint64_t svextw[_s64]_x(svbool_t pg, svint64_t op);
```

### Description

Sign-extend the low 32 bits

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Bit manipulation / Extend from low bits

- SME attributes: Not specified by source.

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
SXTW Ztied.D, Pg/M, Ztied.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SXTB--SXTH--SXTW--Signed-byte---halfword---word-extend--predicated--

When result and op are in different registers, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SXTW Zresult.D, Pg/M, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SXTB--SXTH--SXTW--Signed-byte---halfword---word-extend--predicated--

### Operation

Source operation ID: `SveOperation_svextw_s64_x`

**Operation**



For each active element *i*, sign-extend the low 32 bits of `op[i]` to the width of an element and return the extended value in element *i* of the result vector.



The inactive elements of the result have arbitrary, undefined values.

## svextw[_s64]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svextw%5B_s64%5D_z

### Signature (source notation)

```c
svint64_t svextw[_s64]_z(svbool_t pg, svint64_t op);
```

### Description

Sign-extend the low 32 bits

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Bit manipulation / Extend from low bits

- SME attributes: Not specified by source.

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
SXTW Zresult.D, Pg/M, Zop.D  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SXTB--SXTH--SXTW--Signed-byte---halfword---word-extend--predicated--

### Operation

Source operation ID: `SveOperation_svextw_s64_z`

**Operation**



For each active element *i*, sign-extend the low 32 bits of `op[i]` to the width of an element and return the extended value in element *i* of the result vector.



Set the inactive elements of the result to zero.



**[1]** Note that `result` must be in a different register from `op`

## svextw[_u64]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svextw%5B_u64%5D_m

### Signature (source notation)

```c
svuint64_t svextw[_u64]_m(svuint64_t inactive, svbool_t pg, svuint64_t op);
```

### Description

Zero-extend the low 32 bits

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Bit manipulation / Extend from low bits

- SME attributes: Not specified by source.

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
UXTW Ztied.D, Pg/M, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UXTB--UXTH--UXTW--Unsigned-byte---halfword---word-extend--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zinactive
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
UXTW Zresult.D, Pg/M, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UXTB--UXTH--UXTW--Unsigned-byte---halfword---word-extend--predicated--

### Operation

Source operation ID: `SveOperation_svextw_u64_m`

**Operation**



For each active element *i*, zero-extend the low 32 bits of `op[i]` to the width of an element and return the extended value in element *i* of the result vector.



Take the inactive elements of the result from the corresponding elements of `inactive`.

## svextw[_u64]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svextw%5B_u64%5D_x

### Signature (source notation)

```c
svuint64_t svextw[_u64]_x(svbool_t pg, svuint64_t op);
```

### Description

Zero-extend the low 32 bits

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Bit manipulation / Extend from low bits

- SME attributes: Not specified by source.

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
    "register": "Ztied.D"
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

This intrinsic compiles to:

```asm
UXTW Ztied.D, Pg/M, Ztied.D  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UXTB--UXTH--UXTW--Unsigned-byte---halfword---word-extend--predicated--

…or, alternatively:

```asm
AND Ztied.D, Ztied.D, #4294967295  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/AND--immediate---Bitwise-AND-with-immediate--unpredicated--

### Operation

Source operation ID: `SveOperation_svextw_u64_x`

**Operation**



For each active element *i*, zero-extend the low 32 bits of `op[i]` to the width of an element and return the extended value in element *i* of the result vector.



The inactive elements of the result have arbitrary, undefined values.



**[1]** If instead `result` and `op` are in different registers, the compiler can add a preceding [MOVPRFX (unpredicated)](https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--) instruction

## svextw[_u64]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svextw%5B_u64%5D_z

### Signature (source notation)

```c
svuint64_t svextw[_u64]_z(svbool_t pg, svuint64_t op);
```

### Description

Zero-extend the low 32 bits

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Bit manipulation / Extend from low bits

- SME attributes: Not specified by source.

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
UXTW Zresult.D, Pg/M, Zop.D  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UXTB--UXTH--UXTW--Unsigned-byte---halfword---word-extend--predicated--

### Operation

Source operation ID: `SveOperation_svextw_u64_z`

**Operation**



For each active element *i*, zero-extend the low 32 bits of `op[i]` to the width of an element and return the extended value in element *i* of the result vector.



Set the inactive elements of the result to zero.



**[1]** Note that `result` must be in a different register from `op`

