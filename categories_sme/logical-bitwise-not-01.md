# SME / Logical / Bitwise NOT — Part 1

## svnot[_b]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svnot%5B_b%5D_z

### Signature (source notation)

```c
svbool_t svnot[_b]_z(svbool_t pg, svbool_t op);
```

### Description

Bitwise invert

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / Bitwise NOT

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME
```

### Return type metadata

```json
{
  "return_base_type": "bool",
  "element_bit_size": "8",
  "value": "svbool_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Pg.B"
  },
  "op": {
    "register": "Pop.B"
  }
}
```

### Result mapping

```json
[
  {
    "Presult.B": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
EOR Presult.B, Pg/Z, Pop.B, Pg.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/EOR--predicates---Bitwise-exclusive-OR-predicates-

### Operation

Source operation ID: `SveOperation_svnot_b_z`

**Operation**



Return a predicate in which each active element *i* contains `~op[i]`. Set the inactive elements of the result to zero.

## svnot[_s16]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svnot%5B_s16%5D_m

### Signature (source notation)

```c
svint16_t svnot[_s16]_m(svint16_t inactive, svbool_t pg, svint16_t op);
```

### Description

Bitwise invert

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / Bitwise NOT

- SME attributes: Not specified by source.

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
NOT Ztied.H, Pg/M, Zop.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/NOT--vector---Bitwise-invert--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zinactive
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
NOT Zresult.H, Pg/M, Zop.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/NOT--vector---Bitwise-invert--predicated--

### Operation

Source operation ID: `SveOperation_svnot_s8_m`

**Operation**



Return a vector in which each active element *i* contains `~op[i]`. Take the inactive elements of the result from the corresponding elements of `inactive`.

## svnot[_s16]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svnot%5B_s16%5D_x

### Signature (source notation)

```c
svint16_t svnot[_s16]_x(svbool_t pg, svint16_t op);
```

### Description

Bitwise invert

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / Bitwise NOT

- SME attributes: Not specified by source.

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
NOT Ztied.H, Pg/M, Ztied.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/NOT--vector---Bitwise-invert--predicated--

When result and op are in different registers, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
NOT Zresult.H, Pg/M, Zop.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/NOT--vector---Bitwise-invert--predicated--

### Operation

Source operation ID: `SveOperation_svnot_s8_x`

**Operation**



Return a vector in which each active element *i* contains `~op[i]`. The inactive elements of the result have arbitrary, undefined values.

## svnot[_s16]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svnot%5B_s16%5D_z

### Signature (source notation)

```c
svint16_t svnot[_s16]_z(svbool_t pg, svint16_t op);
```

### Description

Bitwise invert

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / Bitwise NOT

- SME attributes: Not specified by source.

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
NOT Zresult.H, Pg/M, Zop.H  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/NOT--vector---Bitwise-invert--predicated--

### Operation

Source operation ID: `SveOperation_svnot_s8_z`

**Operation**



Return a vector in which each active element *i* contains `~op[i]`. Set the inactive elements of the result to zero.



**[1]** Note that `result` must be in a different register from `op`

## svnot[_s32]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svnot%5B_s32%5D_m

### Signature (source notation)

```c
svint32_t svnot[_s32]_m(svint32_t inactive, svbool_t pg, svint32_t op);
```

### Description

Bitwise invert

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / Bitwise NOT

- SME attributes: Not specified by source.

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
NOT Ztied.S, Pg/M, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/NOT--vector---Bitwise-invert--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zinactive
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
NOT Zresult.S, Pg/M, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/NOT--vector---Bitwise-invert--predicated--

### Operation

Source operation ID: `SveOperation_svnot_s8_m`

**Operation**



Return a vector in which each active element *i* contains `~op[i]`. Take the inactive elements of the result from the corresponding elements of `inactive`.

## svnot[_s32]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svnot%5B_s32%5D_x

### Signature (source notation)

```c
svint32_t svnot[_s32]_x(svbool_t pg, svint32_t op);
```

### Description

Bitwise invert

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / Bitwise NOT

- SME attributes: Not specified by source.

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
NOT Ztied.S, Pg/M, Ztied.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/NOT--vector---Bitwise-invert--predicated--

When result and op are in different registers, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
NOT Zresult.S, Pg/M, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/NOT--vector---Bitwise-invert--predicated--

### Operation

Source operation ID: `SveOperation_svnot_s8_x`

**Operation**



Return a vector in which each active element *i* contains `~op[i]`. The inactive elements of the result have arbitrary, undefined values.

## svnot[_s32]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svnot%5B_s32%5D_z

### Signature (source notation)

```c
svint32_t svnot[_s32]_z(svbool_t pg, svint32_t op);
```

### Description

Bitwise invert

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / Bitwise NOT

- SME attributes: Not specified by source.

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
NOT Zresult.S, Pg/M, Zop.S  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/NOT--vector---Bitwise-invert--predicated--

### Operation

Source operation ID: `SveOperation_svnot_s8_z`

**Operation**



Return a vector in which each active element *i* contains `~op[i]`. Set the inactive elements of the result to zero.



**[1]** Note that `result` must be in a different register from `op`

## svnot[_s64]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svnot%5B_s64%5D_m

### Signature (source notation)

```c
svint64_t svnot[_s64]_m(svint64_t inactive, svbool_t pg, svint64_t op);
```

### Description

Bitwise invert

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / Bitwise NOT

- SME attributes: Not specified by source.

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
NOT Ztied.D, Pg/M, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/NOT--vector---Bitwise-invert--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zinactive
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
NOT Zresult.D, Pg/M, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/NOT--vector---Bitwise-invert--predicated--

### Operation

Source operation ID: `SveOperation_svnot_s8_m`

**Operation**



Return a vector in which each active element *i* contains `~op[i]`. Take the inactive elements of the result from the corresponding elements of `inactive`.

## svnot[_s64]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svnot%5B_s64%5D_x

### Signature (source notation)

```c
svint64_t svnot[_s64]_x(svbool_t pg, svint64_t op);
```

### Description

Bitwise invert

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / Bitwise NOT

- SME attributes: Not specified by source.

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
NOT Ztied.D, Pg/M, Ztied.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/NOT--vector---Bitwise-invert--predicated--

When result and op are in different registers, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
NOT Zresult.D, Pg/M, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/NOT--vector---Bitwise-invert--predicated--

### Operation

Source operation ID: `SveOperation_svnot_s8_x`

**Operation**



Return a vector in which each active element *i* contains `~op[i]`. The inactive elements of the result have arbitrary, undefined values.

## svnot[_s64]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svnot%5B_s64%5D_z

### Signature (source notation)

```c
svint64_t svnot[_s64]_z(svbool_t pg, svint64_t op);
```

### Description

Bitwise invert

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / Bitwise NOT

- SME attributes: Not specified by source.

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
NOT Zresult.D, Pg/M, Zop.D  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/NOT--vector---Bitwise-invert--predicated--

### Operation

Source operation ID: `SveOperation_svnot_s8_z`

**Operation**



Return a vector in which each active element *i* contains `~op[i]`. Set the inactive elements of the result to zero.



**[1]** Note that `result` must be in a different register from `op`

## svnot[_s8]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svnot%5B_s8%5D_m

### Signature (source notation)

```c
svint8_t svnot[_s8]_m(svint8_t inactive, svbool_t pg, svint8_t op);
```

### Description

Bitwise invert

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / Bitwise NOT

- SME attributes: Not specified by source.

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
  "inactive": {
    "register": "Zinactive.B|Ztied.B"
  },
  "pg": {
    "register": "Pg"
  },
  "op": {
    "register": "Zop.B"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.B|Ztied.B": "result"
  }
]
```

### Instruction mapping

When result and inactive are in the same register, this intrinsic compiles to:

```asm
NOT Ztied.B, Pg/M, Zop.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/NOT--vector---Bitwise-invert--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zinactive
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
NOT Zresult.B, Pg/M, Zop.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/NOT--vector---Bitwise-invert--predicated--

### Operation

Source operation ID: `SveOperation_svnot_s8_m`

**Operation**



Return a vector in which each active element *i* contains `~op[i]`. Take the inactive elements of the result from the corresponding elements of `inactive`.

## svnot[_s8]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svnot%5B_s8%5D_x

### Signature (source notation)

```c
svint8_t svnot[_s8]_x(svbool_t pg, svint8_t op);
```

### Description

Bitwise invert

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / Bitwise NOT

- SME attributes: Not specified by source.

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
  "pg": {
    "register": "Pg"
  },
  "op": {
    "register": "Zop.B|Ztied.B"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.B|Ztied.B": "result"
  }
]
```

### Instruction mapping

When result and op are in the same register, this intrinsic compiles to:

```asm
NOT Ztied.B, Pg/M, Ztied.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/NOT--vector---Bitwise-invert--predicated--

When result and op are in different registers, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
NOT Zresult.B, Pg/M, Zop.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/NOT--vector---Bitwise-invert--predicated--

### Operation

Source operation ID: `SveOperation_svnot_s8_x`

**Operation**



Return a vector in which each active element *i* contains `~op[i]`. The inactive elements of the result have arbitrary, undefined values.

## svnot[_s8]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svnot%5B_s8%5D_z

### Signature (source notation)

```c
svint8_t svnot[_s8]_z(svbool_t pg, svint8_t op);
```

### Description

Bitwise invert

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / Bitwise NOT

- SME attributes: Not specified by source.

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
  "pg": {
    "register": "Pg"
  },
  "op": {
    "register": "Zop.B"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.B": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instructions, or functionally equivalent instructions:

```asm
MOVPRFX Zresult.B, Pg/Z, Zop.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
NOT Zresult.B, Pg/M, Zop.B  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/NOT--vector---Bitwise-invert--predicated--

### Operation

Source operation ID: `SveOperation_svnot_s8_z`

**Operation**



Return a vector in which each active element *i* contains `~op[i]`. Set the inactive elements of the result to zero.



**[1]** Note that `result` must be in a different register from `op`

## svnot[_u16]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svnot%5B_u16%5D_m

### Signature (source notation)

```c
svuint16_t svnot[_u16]_m(svuint16_t inactive, svbool_t pg, svuint16_t op);
```

### Description

Bitwise invert

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / Bitwise NOT

- SME attributes: Not specified by source.

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
NOT Ztied.H, Pg/M, Zop.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/NOT--vector---Bitwise-invert--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zinactive
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
NOT Zresult.H, Pg/M, Zop.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/NOT--vector---Bitwise-invert--predicated--

### Operation

Source operation ID: `SveOperation_svnot_s8_m`

**Operation**



Return a vector in which each active element *i* contains `~op[i]`. Take the inactive elements of the result from the corresponding elements of `inactive`.

## svnot[_u16]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svnot%5B_u16%5D_x

### Signature (source notation)

```c
svuint16_t svnot[_u16]_x(svbool_t pg, svuint16_t op);
```

### Description

Bitwise invert

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / Bitwise NOT

- SME attributes: Not specified by source.

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
NOT Ztied.H, Pg/M, Ztied.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/NOT--vector---Bitwise-invert--predicated--

When result and op are in different registers, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
NOT Zresult.H, Pg/M, Zop.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/NOT--vector---Bitwise-invert--predicated--

### Operation

Source operation ID: `SveOperation_svnot_s8_x`

**Operation**



Return a vector in which each active element *i* contains `~op[i]`. The inactive elements of the result have arbitrary, undefined values.

## svnot[_u16]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svnot%5B_u16%5D_z

### Signature (source notation)

```c
svuint16_t svnot[_u16]_z(svbool_t pg, svuint16_t op);
```

### Description

Bitwise invert

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / Bitwise NOT

- SME attributes: Not specified by source.

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
NOT Zresult.H, Pg/M, Zop.H  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/NOT--vector---Bitwise-invert--predicated--

### Operation

Source operation ID: `SveOperation_svnot_s8_z`

**Operation**



Return a vector in which each active element *i* contains `~op[i]`. Set the inactive elements of the result to zero.



**[1]** Note that `result` must be in a different register from `op`

## svnot[_u32]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svnot%5B_u32%5D_m

### Signature (source notation)

```c
svuint32_t svnot[_u32]_m(svuint32_t inactive, svbool_t pg, svuint32_t op);
```

### Description

Bitwise invert

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / Bitwise NOT

- SME attributes: Not specified by source.

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
NOT Ztied.S, Pg/M, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/NOT--vector---Bitwise-invert--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zinactive
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
NOT Zresult.S, Pg/M, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/NOT--vector---Bitwise-invert--predicated--

### Operation

Source operation ID: `SveOperation_svnot_s8_m`

**Operation**



Return a vector in which each active element *i* contains `~op[i]`. Take the inactive elements of the result from the corresponding elements of `inactive`.

## svnot[_u32]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svnot%5B_u32%5D_x

### Signature (source notation)

```c
svuint32_t svnot[_u32]_x(svbool_t pg, svuint32_t op);
```

### Description

Bitwise invert

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / Bitwise NOT

- SME attributes: Not specified by source.

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
NOT Ztied.S, Pg/M, Ztied.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/NOT--vector---Bitwise-invert--predicated--

When result and op are in different registers, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
NOT Zresult.S, Pg/M, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/NOT--vector---Bitwise-invert--predicated--

### Operation

Source operation ID: `SveOperation_svnot_s8_x`

**Operation**



Return a vector in which each active element *i* contains `~op[i]`. The inactive elements of the result have arbitrary, undefined values.

## svnot[_u32]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svnot%5B_u32%5D_z

### Signature (source notation)

```c
svuint32_t svnot[_u32]_z(svbool_t pg, svuint32_t op);
```

### Description

Bitwise invert

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / Bitwise NOT

- SME attributes: Not specified by source.

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
NOT Zresult.S, Pg/M, Zop.S  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/NOT--vector---Bitwise-invert--predicated--

### Operation

Source operation ID: `SveOperation_svnot_s8_z`

**Operation**



Return a vector in which each active element *i* contains `~op[i]`. Set the inactive elements of the result to zero.



**[1]** Note that `result` must be in a different register from `op`

## svnot[_u64]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svnot%5B_u64%5D_m

### Signature (source notation)

```c
svuint64_t svnot[_u64]_m(svuint64_t inactive, svbool_t pg, svuint64_t op);
```

### Description

Bitwise invert

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / Bitwise NOT

- SME attributes: Not specified by source.

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
NOT Ztied.D, Pg/M, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/NOT--vector---Bitwise-invert--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zinactive
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
NOT Zresult.D, Pg/M, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/NOT--vector---Bitwise-invert--predicated--

### Operation

Source operation ID: `SveOperation_svnot_s8_m`

**Operation**



Return a vector in which each active element *i* contains `~op[i]`. Take the inactive elements of the result from the corresponding elements of `inactive`.

## svnot[_u64]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svnot%5B_u64%5D_x

### Signature (source notation)

```c
svuint64_t svnot[_u64]_x(svbool_t pg, svuint64_t op);
```

### Description

Bitwise invert

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / Bitwise NOT

- SME attributes: Not specified by source.

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
NOT Ztied.D, Pg/M, Ztied.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/NOT--vector---Bitwise-invert--predicated--

When result and op are in different registers, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
NOT Zresult.D, Pg/M, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/NOT--vector---Bitwise-invert--predicated--

### Operation

Source operation ID: `SveOperation_svnot_s8_x`

**Operation**



Return a vector in which each active element *i* contains `~op[i]`. The inactive elements of the result have arbitrary, undefined values.

## svnot[_u64]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svnot%5B_u64%5D_z

### Signature (source notation)

```c
svuint64_t svnot[_u64]_z(svbool_t pg, svuint64_t op);
```

### Description

Bitwise invert

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / Bitwise NOT

- SME attributes: Not specified by source.

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
NOT Zresult.D, Pg/M, Zop.D  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/NOT--vector---Bitwise-invert--predicated--

### Operation

Source operation ID: `SveOperation_svnot_s8_z`

**Operation**



Return a vector in which each active element *i* contains `~op[i]`. Set the inactive elements of the result to zero.



**[1]** Note that `result` must be in a different register from `op`

## svnot[_u8]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svnot%5B_u8%5D_m

### Signature (source notation)

```c
svuint8_t svnot[_u8]_m(svuint8_t inactive, svbool_t pg, svuint8_t op);
```

### Description

Bitwise invert

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / Bitwise NOT

- SME attributes: Not specified by source.

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
  "inactive": {
    "register": "Zinactive.B|Ztied.B"
  },
  "pg": {
    "register": "Pg"
  },
  "op": {
    "register": "Zop.B"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.B|Ztied.B": "result"
  }
]
```

### Instruction mapping

When result and inactive are in the same register, this intrinsic compiles to:

```asm
NOT Ztied.B, Pg/M, Zop.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/NOT--vector---Bitwise-invert--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zinactive
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
NOT Zresult.B, Pg/M, Zop.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/NOT--vector---Bitwise-invert--predicated--

### Operation

Source operation ID: `SveOperation_svnot_s8_m`

**Operation**



Return a vector in which each active element *i* contains `~op[i]`. Take the inactive elements of the result from the corresponding elements of `inactive`.

## svnot[_u8]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svnot%5B_u8%5D_x

### Signature (source notation)

```c
svuint8_t svnot[_u8]_x(svbool_t pg, svuint8_t op);
```

### Description

Bitwise invert

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / Bitwise NOT

- SME attributes: Not specified by source.

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
  "pg": {
    "register": "Pg"
  },
  "op": {
    "register": "Zop.B|Ztied.B"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.B|Ztied.B": "result"
  }
]
```

### Instruction mapping

When result and op are in the same register, this intrinsic compiles to:

```asm
NOT Ztied.B, Pg/M, Ztied.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/NOT--vector---Bitwise-invert--predicated--

When result and op are in different registers, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
NOT Zresult.B, Pg/M, Zop.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/NOT--vector---Bitwise-invert--predicated--

### Operation

Source operation ID: `SveOperation_svnot_s8_x`

**Operation**



Return a vector in which each active element *i* contains `~op[i]`. The inactive elements of the result have arbitrary, undefined values.

## svnot[_u8]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svnot%5B_u8%5D_z

### Signature (source notation)

```c
svuint8_t svnot[_u8]_z(svbool_t pg, svuint8_t op);
```

### Description

Bitwise invert

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / Bitwise NOT

- SME attributes: Not specified by source.

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
  "pg": {
    "register": "Pg"
  },
  "op": {
    "register": "Zop.B"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.B": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instructions, or functionally equivalent instructions:

```asm
MOVPRFX Zresult.B, Pg/Z, Zop.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
NOT Zresult.B, Pg/M, Zop.B  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/NOT--vector---Bitwise-invert--predicated--

### Operation

Source operation ID: `SveOperation_svnot_s8_z`

**Operation**



Return a vector in which each active element *i* contains `~op[i]`. Set the inactive elements of the result to zero.



**[1]** Note that `result` must be in a different register from `op`

