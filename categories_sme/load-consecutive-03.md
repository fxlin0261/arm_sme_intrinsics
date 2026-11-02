# SME / Load / Consecutive — Part 3

## svld1sb_s64

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld1sb_s64

### Signature (source notation)

```c
svint64_t svld1sb_s64(svbool_t pg, const int8_t *base);
```

### Description

Load 8-bit data and sign-extend

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Load / Consecutive

- SME attributes: Not specified by source.

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
  "base": {
    "register": "Xbase"
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

When base has the form &array[index], this intrinsic can use:

```asm
LD1SB Zresult.D, Pg/Z, [Xarray, Xindex]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1SB--scalar-plus-scalar---Contiguous-load-signed-bytes-to-vector--scalar-index--

The general implementation is:

```asm
LD1SB Zresult.D, Pg/Z, [Xbase, #0, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1SB--scalar-plus-immediate---Contiguous-load-signed-bytes-to-vector--immediate-index--

### Operation

Source operation ID: `SveOperation_svld1sb_s16`

**Operation**



Return a vector in which each active element *i* contains the sign extension of `base[i]` and in which all other elements are zero.  Do not access memory for inactive elements.

## svld1sb_u16

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld1sb_u16

### Signature (source notation)

```c
svuint16_t svld1sb_u16(svbool_t pg, const int8_t *base);
```

### Description

Load 8-bit data and sign-extend

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Load / Consecutive

- SME attributes: Not specified by source.

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
  "base": {
    "register": "Xbase"
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

When base has the form &array[index], this intrinsic can use:

```asm
LD1SB Zresult.H, Pg/Z, [Xarray, Xindex]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1SB--scalar-plus-scalar---Contiguous-load-signed-bytes-to-vector--scalar-index--

The general implementation is:

```asm
LD1SB Zresult.H, Pg/Z, [Xbase, #0, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1SB--scalar-plus-immediate---Contiguous-load-signed-bytes-to-vector--immediate-index--

### Operation

Source operation ID: `SveOperation_svld1sb_s16`

**Operation**



Return a vector in which each active element *i* contains the sign extension of `base[i]` and in which all other elements are zero.  Do not access memory for inactive elements.

## svld1sb_u32

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld1sb_u32

### Signature (source notation)

```c
svuint32_t svld1sb_u32(svbool_t pg, const int8_t *base);
```

### Description

Load 8-bit data and sign-extend

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Load / Consecutive

- SME attributes: Not specified by source.

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
  "base": {
    "register": "Xbase"
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

When base has the form &array[index], this intrinsic can use:

```asm
LD1SB Zresult.S, Pg/Z, [Xarray, Xindex]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1SB--scalar-plus-scalar---Contiguous-load-signed-bytes-to-vector--scalar-index--

The general implementation is:

```asm
LD1SB Zresult.S, Pg/Z, [Xbase, #0, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1SB--scalar-plus-immediate---Contiguous-load-signed-bytes-to-vector--immediate-index--

### Operation

Source operation ID: `SveOperation_svld1sb_s16`

**Operation**



Return a vector in which each active element *i* contains the sign extension of `base[i]` and in which all other elements are zero.  Do not access memory for inactive elements.

## svld1sb_u64

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld1sb_u64

### Signature (source notation)

```c
svuint64_t svld1sb_u64(svbool_t pg, const int8_t *base);
```

### Description

Load 8-bit data and sign-extend

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Load / Consecutive

- SME attributes: Not specified by source.

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
  "base": {
    "register": "Xbase"
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

When base has the form &array[index], this intrinsic can use:

```asm
LD1SB Zresult.D, Pg/Z, [Xarray, Xindex]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1SB--scalar-plus-scalar---Contiguous-load-signed-bytes-to-vector--scalar-index--

The general implementation is:

```asm
LD1SB Zresult.D, Pg/Z, [Xbase, #0, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1SB--scalar-plus-immediate---Contiguous-load-signed-bytes-to-vector--immediate-index--

### Operation

Source operation ID: `SveOperation_svld1sb_s16`

**Operation**



Return a vector in which each active element *i* contains the sign extension of `base[i]` and in which all other elements are zero.  Do not access memory for inactive elements.

## svld1sb_vnum_s16

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld1sb_vnum_s16

### Signature (source notation)

```c
svint16_t svld1sb_vnum_s16(svbool_t pg, const int8_t *base, int64_t vnum);
```

### Description

Load 8-bit data and sign-extend

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Load / Consecutive

- SME attributes: Not specified by source.

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
  "base": {
    "register": "Xbase"
  },
  "vnum * svcnth()": {
    "register": "Xindex"
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

When vnum is in the range [-8, 7], this intrinsic can use:

```asm
LD1SB Zresult.H, Pg/Z, [Xbase, #vnum, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1SB--scalar-plus-immediate---Contiguous-load-signed-bytes-to-vector--immediate-index--

The general implementation is:

```asm
LD1SB Zresult.H, Pg/Z, [Xbase, Xindex]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1SB--scalar-plus-scalar---Contiguous-load-signed-bytes-to-vector--scalar-index--

### Operation

Source operation ID: `SveOperation_svld1sb_vnum_s16`

**Operation**



Return a vector of *n* elements in which each active element *i* contains the sign extension of `base[n * vnum + i]` and in which all other elements are zero.  Do not access memory for inactive elements.

## svld1sb_vnum_s32

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld1sb_vnum_s32

### Signature (source notation)

```c
svint32_t svld1sb_vnum_s32(svbool_t pg, const int8_t *base, int64_t vnum);
```

### Description

Load 8-bit data and sign-extend

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Load / Consecutive

- SME attributes: Not specified by source.

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
  "base": {
    "register": "Xbase"
  },
  "vnum * svcntw()": {
    "register": "Xindex"
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

When vnum is in the range [-8, 7], this intrinsic can use:

```asm
LD1SB Zresult.S, Pg/Z, [Xbase, #vnum, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1SB--scalar-plus-immediate---Contiguous-load-signed-bytes-to-vector--immediate-index--

The general implementation is:

```asm
LD1SB Zresult.S, Pg/Z, [Xbase, Xindex]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1SB--scalar-plus-scalar---Contiguous-load-signed-bytes-to-vector--scalar-index--

### Operation

Source operation ID: `SveOperation_svld1sb_vnum_s16`

**Operation**



Return a vector of *n* elements in which each active element *i* contains the sign extension of `base[n * vnum + i]` and in which all other elements are zero.  Do not access memory for inactive elements.

## svld1sb_vnum_s64

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld1sb_vnum_s64

### Signature (source notation)

```c
svint64_t svld1sb_vnum_s64(svbool_t pg, const int8_t *base, int64_t vnum);
```

### Description

Load 8-bit data and sign-extend

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Load / Consecutive

- SME attributes: Not specified by source.

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
  "base": {
    "register": "Xbase"
  },
  "vnum * svcntd()": {
    "register": "Xindex"
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

When vnum is in the range [-8, 7], this intrinsic can use:

```asm
LD1SB Zresult.D, Pg/Z, [Xbase, #vnum, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1SB--scalar-plus-immediate---Contiguous-load-signed-bytes-to-vector--immediate-index--

The general implementation is:

```asm
LD1SB Zresult.D, Pg/Z, [Xbase, Xindex]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1SB--scalar-plus-scalar---Contiguous-load-signed-bytes-to-vector--scalar-index--

### Operation

Source operation ID: `SveOperation_svld1sb_vnum_s16`

**Operation**



Return a vector of *n* elements in which each active element *i* contains the sign extension of `base[n * vnum + i]` and in which all other elements are zero.  Do not access memory for inactive elements.

## svld1sb_vnum_u16

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld1sb_vnum_u16

### Signature (source notation)

```c
svuint16_t svld1sb_vnum_u16(svbool_t pg, const int8_t *base, int64_t vnum);
```

### Description

Load 8-bit data and sign-extend

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Load / Consecutive

- SME attributes: Not specified by source.

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
  "base": {
    "register": "Xbase"
  },
  "vnum * svcnth()": {
    "register": "Xindex"
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

When vnum is in the range [-8, 7], this intrinsic can use:

```asm
LD1SB Zresult.H, Pg/Z, [Xbase, #vnum, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1SB--scalar-plus-immediate---Contiguous-load-signed-bytes-to-vector--immediate-index--

The general implementation is:

```asm
LD1SB Zresult.H, Pg/Z, [Xbase, Xindex]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1SB--scalar-plus-scalar---Contiguous-load-signed-bytes-to-vector--scalar-index--

### Operation

Source operation ID: `SveOperation_svld1sb_vnum_s16`

**Operation**



Return a vector of *n* elements in which each active element *i* contains the sign extension of `base[n * vnum + i]` and in which all other elements are zero.  Do not access memory for inactive elements.

## svld1sb_vnum_u32

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld1sb_vnum_u32

### Signature (source notation)

```c
svuint32_t svld1sb_vnum_u32(svbool_t pg, const int8_t *base, int64_t vnum);
```

### Description

Load 8-bit data and sign-extend

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Load / Consecutive

- SME attributes: Not specified by source.

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
  "base": {
    "register": "Xbase"
  },
  "vnum * svcntw()": {
    "register": "Xindex"
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

When vnum is in the range [-8, 7], this intrinsic can use:

```asm
LD1SB Zresult.S, Pg/Z, [Xbase, #vnum, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1SB--scalar-plus-immediate---Contiguous-load-signed-bytes-to-vector--immediate-index--

The general implementation is:

```asm
LD1SB Zresult.S, Pg/Z, [Xbase, Xindex]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1SB--scalar-plus-scalar---Contiguous-load-signed-bytes-to-vector--scalar-index--

### Operation

Source operation ID: `SveOperation_svld1sb_vnum_s16`

**Operation**



Return a vector of *n* elements in which each active element *i* contains the sign extension of `base[n * vnum + i]` and in which all other elements are zero.  Do not access memory for inactive elements.

## svld1sb_vnum_u64

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld1sb_vnum_u64

### Signature (source notation)

```c
svuint64_t svld1sb_vnum_u64(svbool_t pg, const int8_t *base, int64_t vnum);
```

### Description

Load 8-bit data and sign-extend

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Load / Consecutive

- SME attributes: Not specified by source.

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
  "base": {
    "register": "Xbase"
  },
  "vnum * svcntd()": {
    "register": "Xindex"
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

When vnum is in the range [-8, 7], this intrinsic can use:

```asm
LD1SB Zresult.D, Pg/Z, [Xbase, #vnum, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1SB--scalar-plus-immediate---Contiguous-load-signed-bytes-to-vector--immediate-index--

The general implementation is:

```asm
LD1SB Zresult.D, Pg/Z, [Xbase, Xindex]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1SB--scalar-plus-scalar---Contiguous-load-signed-bytes-to-vector--scalar-index--

### Operation

Source operation ID: `SveOperation_svld1sb_vnum_s16`

**Operation**



Return a vector of *n* elements in which each active element *i* contains the sign extension of `base[n * vnum + i]` and in which all other elements are zero.  Do not access memory for inactive elements.

## svld1sh_s32

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld1sh_s32

### Signature (source notation)

```c
svint32_t svld1sh_s32(svbool_t pg, const int16_t *base);
```

### Description

Load 16-bit data and sign-extend

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Load / Consecutive

- SME attributes: Not specified by source.

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
  "base": {
    "register": "Xbase"
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

When base has the form &array[index], this intrinsic can use:

```asm
LD1SH Zresult.S, Pg/Z, [Xarray, Xindex, LSL #1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1SH--scalar-plus-scalar---Contiguous-load-signed-halfwords-to-vector--scalar-index--

The general implementation is:

```asm
LD1SH Zresult.S, Pg/Z, [Xbase, #0, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1SH--scalar-plus-immediate---Contiguous-load-signed-halfwords-to-vector--immediate-index--

### Operation

Source operation ID: `SveOperation_svld1sb_s16`

**Operation**



Return a vector in which each active element *i* contains the sign extension of `base[i]` and in which all other elements are zero.  Do not access memory for inactive elements.

## svld1sh_s64

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld1sh_s64

### Signature (source notation)

```c
svint64_t svld1sh_s64(svbool_t pg, const int16_t *base);
```

### Description

Load 16-bit data and sign-extend

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Load / Consecutive

- SME attributes: Not specified by source.

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
  "base": {
    "register": "Xbase"
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

When base has the form &array[index], this intrinsic can use:

```asm
LD1SH Zresult.D, Pg/Z, [Xarray, Xindex, LSL #1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1SH--scalar-plus-scalar---Contiguous-load-signed-halfwords-to-vector--scalar-index--

The general implementation is:

```asm
LD1SH Zresult.D, Pg/Z, [Xbase, #0, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1SH--scalar-plus-immediate---Contiguous-load-signed-halfwords-to-vector--immediate-index--

### Operation

Source operation ID: `SveOperation_svld1sb_s16`

**Operation**



Return a vector in which each active element *i* contains the sign extension of `base[i]` and in which all other elements are zero.  Do not access memory for inactive elements.

## svld1sh_u32

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld1sh_u32

### Signature (source notation)

```c
svuint32_t svld1sh_u32(svbool_t pg, const int16_t *base);
```

### Description

Load 16-bit data and sign-extend

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Load / Consecutive

- SME attributes: Not specified by source.

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
  "base": {
    "register": "Xbase"
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

When base has the form &array[index], this intrinsic can use:

```asm
LD1SH Zresult.S, Pg/Z, [Xarray, Xindex, LSL #1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1SH--scalar-plus-scalar---Contiguous-load-signed-halfwords-to-vector--scalar-index--

The general implementation is:

```asm
LD1SH Zresult.S, Pg/Z, [Xbase, #0, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1SH--scalar-plus-immediate---Contiguous-load-signed-halfwords-to-vector--immediate-index--

### Operation

Source operation ID: `SveOperation_svld1sb_s16`

**Operation**



Return a vector in which each active element *i* contains the sign extension of `base[i]` and in which all other elements are zero.  Do not access memory for inactive elements.

## svld1sh_u64

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld1sh_u64

### Signature (source notation)

```c
svuint64_t svld1sh_u64(svbool_t pg, const int16_t *base);
```

### Description

Load 16-bit data and sign-extend

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Load / Consecutive

- SME attributes: Not specified by source.

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
  "base": {
    "register": "Xbase"
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

When base has the form &array[index], this intrinsic can use:

```asm
LD1SH Zresult.D, Pg/Z, [Xarray, Xindex, LSL #1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1SH--scalar-plus-scalar---Contiguous-load-signed-halfwords-to-vector--scalar-index--

The general implementation is:

```asm
LD1SH Zresult.D, Pg/Z, [Xbase, #0, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1SH--scalar-plus-immediate---Contiguous-load-signed-halfwords-to-vector--immediate-index--

### Operation

Source operation ID: `SveOperation_svld1sb_s16`

**Operation**



Return a vector in which each active element *i* contains the sign extension of `base[i]` and in which all other elements are zero.  Do not access memory for inactive elements.

## svld1sh_vnum_s32

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld1sh_vnum_s32

### Signature (source notation)

```c
svint32_t svld1sh_vnum_s32(svbool_t pg, const int16_t *base, int64_t vnum);
```

### Description

Load 16-bit data and sign-extend

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Load / Consecutive

- SME attributes: Not specified by source.

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
  "base": {
    "register": "Xbase"
  },
  "vnum * svcntw()": {
    "register": "Xindex"
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

When vnum is in the range [-8, 7], this intrinsic can use:

```asm
LD1SH Zresult.S, Pg/Z, [Xbase, #vnum, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1SH--scalar-plus-immediate---Contiguous-load-signed-halfwords-to-vector--immediate-index--

The general implementation is:

```asm
LD1SH Zresult.S, Pg/Z, [Xbase, Xindex, LSL #1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1SH--scalar-plus-scalar---Contiguous-load-signed-halfwords-to-vector--scalar-index--

### Operation

Source operation ID: `SveOperation_svld1sb_vnum_s16`

**Operation**



Return a vector of *n* elements in which each active element *i* contains the sign extension of `base[n * vnum + i]` and in which all other elements are zero.  Do not access memory for inactive elements.

## svld1sh_vnum_s64

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld1sh_vnum_s64

### Signature (source notation)

```c
svint64_t svld1sh_vnum_s64(svbool_t pg, const int16_t *base, int64_t vnum);
```

### Description

Load 16-bit data and sign-extend

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Load / Consecutive

- SME attributes: Not specified by source.

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
  "base": {
    "register": "Xbase"
  },
  "vnum * svcntd()": {
    "register": "Xindex"
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

When vnum is in the range [-8, 7], this intrinsic can use:

```asm
LD1SH Zresult.D, Pg/Z, [Xbase, #vnum, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1SH--scalar-plus-immediate---Contiguous-load-signed-halfwords-to-vector--immediate-index--

The general implementation is:

```asm
LD1SH Zresult.D, Pg/Z, [Xbase, Xindex, LSL #1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1SH--scalar-plus-scalar---Contiguous-load-signed-halfwords-to-vector--scalar-index--

### Operation

Source operation ID: `SveOperation_svld1sb_vnum_s16`

**Operation**



Return a vector of *n* elements in which each active element *i* contains the sign extension of `base[n * vnum + i]` and in which all other elements are zero.  Do not access memory for inactive elements.

## svld1sh_vnum_u32

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld1sh_vnum_u32

### Signature (source notation)

```c
svuint32_t svld1sh_vnum_u32(svbool_t pg, const int16_t *base, int64_t vnum);
```

### Description

Load 16-bit data and sign-extend

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Load / Consecutive

- SME attributes: Not specified by source.

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
  "base": {
    "register": "Xbase"
  },
  "vnum * svcntw()": {
    "register": "Xindex"
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

When vnum is in the range [-8, 7], this intrinsic can use:

```asm
LD1SH Zresult.S, Pg/Z, [Xbase, #vnum, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1SH--scalar-plus-immediate---Contiguous-load-signed-halfwords-to-vector--immediate-index--

The general implementation is:

```asm
LD1SH Zresult.S, Pg/Z, [Xbase, Xindex, LSL #1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1SH--scalar-plus-scalar---Contiguous-load-signed-halfwords-to-vector--scalar-index--

### Operation

Source operation ID: `SveOperation_svld1sb_vnum_s16`

**Operation**



Return a vector of *n* elements in which each active element *i* contains the sign extension of `base[n * vnum + i]` and in which all other elements are zero.  Do not access memory for inactive elements.

## svld1sh_vnum_u64

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld1sh_vnum_u64

### Signature (source notation)

```c
svuint64_t svld1sh_vnum_u64(svbool_t pg, const int16_t *base, int64_t vnum);
```

### Description

Load 16-bit data and sign-extend

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Load / Consecutive

- SME attributes: Not specified by source.

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
  "base": {
    "register": "Xbase"
  },
  "vnum * svcntd()": {
    "register": "Xindex"
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

When vnum is in the range [-8, 7], this intrinsic can use:

```asm
LD1SH Zresult.D, Pg/Z, [Xbase, #vnum, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1SH--scalar-plus-immediate---Contiguous-load-signed-halfwords-to-vector--immediate-index--

The general implementation is:

```asm
LD1SH Zresult.D, Pg/Z, [Xbase, Xindex, LSL #1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1SH--scalar-plus-scalar---Contiguous-load-signed-halfwords-to-vector--scalar-index--

### Operation

Source operation ID: `SveOperation_svld1sb_vnum_s16`

**Operation**



Return a vector of *n* elements in which each active element *i* contains the sign extension of `base[n * vnum + i]` and in which all other elements are zero.  Do not access memory for inactive elements.

## svld1sw_s64

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld1sw_s64

### Signature (source notation)

```c
svint64_t svld1sw_s64(svbool_t pg, const int32_t *base);
```

### Description

Load 32-bit data and sign-extend

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Load / Consecutive

- SME attributes: Not specified by source.

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
  "base": {
    "register": "Xbase"
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

When base has the form &array[index], this intrinsic can use:

```asm
LD1SW Zresult.D, Pg/Z, [Xarray, Xindex, LSL #2]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1SW--scalar-plus-scalar---Contiguous-load-signed-words-to-vector--scalar-index--

The general implementation is:

```asm
LD1SW Zresult.D, Pg/Z, [Xbase, #0, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1SW--scalar-plus-immediate---Contiguous-load-signed-words-to-vector--immediate-index--

### Operation

Source operation ID: `SveOperation_svld1sb_s16`

**Operation**



Return a vector in which each active element *i* contains the sign extension of `base[i]` and in which all other elements are zero.  Do not access memory for inactive elements.

## svld1sw_u64

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld1sw_u64

### Signature (source notation)

```c
svuint64_t svld1sw_u64(svbool_t pg, const int32_t *base);
```

### Description

Load 32-bit data and sign-extend

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Load / Consecutive

- SME attributes: Not specified by source.

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
  "base": {
    "register": "Xbase"
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

When base has the form &array[index], this intrinsic can use:

```asm
LD1SW Zresult.D, Pg/Z, [Xarray, Xindex, LSL #2]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1SW--scalar-plus-scalar---Contiguous-load-signed-words-to-vector--scalar-index--

The general implementation is:

```asm
LD1SW Zresult.D, Pg/Z, [Xbase, #0, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1SW--scalar-plus-immediate---Contiguous-load-signed-words-to-vector--immediate-index--

### Operation

Source operation ID: `SveOperation_svld1sb_s16`

**Operation**



Return a vector in which each active element *i* contains the sign extension of `base[i]` and in which all other elements are zero.  Do not access memory for inactive elements.

## svld1sw_vnum_s64

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld1sw_vnum_s64

### Signature (source notation)

```c
svint64_t svld1sw_vnum_s64(svbool_t pg, const int32_t *base, int64_t vnum);
```

### Description

Load 32-bit data and sign-extend

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Load / Consecutive

- SME attributes: Not specified by source.

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
  "base": {
    "register": "Xbase"
  },
  "vnum * svcntd()": {
    "register": "Xindex"
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

When vnum is in the range [-8, 7], this intrinsic can use:

```asm
LD1SW Zresult.D, Pg/Z, [Xbase, #vnum, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1SW--scalar-plus-immediate---Contiguous-load-signed-words-to-vector--immediate-index--

The general implementation is:

```asm
LD1SW Zresult.D, Pg/Z, [Xbase, Xindex, LSL #2]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1SW--scalar-plus-scalar---Contiguous-load-signed-words-to-vector--scalar-index--

### Operation

Source operation ID: `SveOperation_svld1sb_vnum_s16`

**Operation**



Return a vector of *n* elements in which each active element *i* contains the sign extension of `base[n * vnum + i]` and in which all other elements are zero.  Do not access memory for inactive elements.

## svld1sw_vnum_u64

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld1sw_vnum_u64

### Signature (source notation)

```c
svuint64_t svld1sw_vnum_u64(svbool_t pg, const int32_t *base, int64_t vnum);
```

### Description

Load 32-bit data and sign-extend

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Load / Consecutive

- SME attributes: Not specified by source.

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
  "base": {
    "register": "Xbase"
  },
  "vnum * svcntd()": {
    "register": "Xindex"
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

When vnum is in the range [-8, 7], this intrinsic can use:

```asm
LD1SW Zresult.D, Pg/Z, [Xbase, #vnum, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1SW--scalar-plus-immediate---Contiguous-load-signed-words-to-vector--immediate-index--

The general implementation is:

```asm
LD1SW Zresult.D, Pg/Z, [Xbase, Xindex, LSL #2]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1SW--scalar-plus-scalar---Contiguous-load-signed-words-to-vector--scalar-index--

### Operation

Source operation ID: `SveOperation_svld1sb_vnum_s16`

**Operation**



Return a vector of *n* elements in which each active element *i* contains the sign extension of `base[n * vnum + i]` and in which all other elements are zero.  Do not access memory for inactive elements.

## svld1ub_s16

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld1ub_s16

### Signature (source notation)

```c
svint16_t svld1ub_s16(svbool_t pg, const uint8_t *base);
```

### Description

Load 8-bit data and zero-extend

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Load / Consecutive

- SME attributes: Not specified by source.

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
  "base": {
    "register": "Xbase"
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

When base has the form &array[index], this intrinsic can use:

```asm
LD1B Zresult.H, Pg/Z, [Xarray, Xindex]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1B--scalar-plus-scalar--consecutive-registers---Contiguous-load-of-bytes-to-multiple-consecutive-vectors--scalar-index--

The general implementation is:

```asm
LD1B Zresult.H, Pg/Z, [Xbase, #0, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1B--scalar-plus-immediate--single-register---Contiguous-load-unsigned-bytes-to-vector--immediate-index--

### Operation

Source operation ID: `SveOperation_svld1ub_s16`

**Operation**



Return a vector in which each active element *i* contains the zero extension of `base[i]` and in which all other elements are zero.  Do not access memory for inactive elements.

## svld1ub_s32

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld1ub_s32

### Signature (source notation)

```c
svint32_t svld1ub_s32(svbool_t pg, const uint8_t *base);
```

### Description

Load 8-bit data and zero-extend

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Load / Consecutive

- SME attributes: Not specified by source.

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
  "base": {
    "register": "Xbase"
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

When base has the form &array[index], this intrinsic can use:

```asm
LD1B Zresult.S, Pg/Z, [Xarray, Xindex]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1B--scalar-plus-scalar--consecutive-registers---Contiguous-load-of-bytes-to-multiple-consecutive-vectors--scalar-index--

The general implementation is:

```asm
LD1B Zresult.S, Pg/Z, [Xbase, #0, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1B--scalar-plus-immediate--single-register---Contiguous-load-unsigned-bytes-to-vector--immediate-index--

### Operation

Source operation ID: `SveOperation_svld1ub_s16`

**Operation**



Return a vector in which each active element *i* contains the zero extension of `base[i]` and in which all other elements are zero.  Do not access memory for inactive elements.

## svld1ub_s64

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld1ub_s64

### Signature (source notation)

```c
svint64_t svld1ub_s64(svbool_t pg, const uint8_t *base);
```

### Description

Load 8-bit data and zero-extend

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Load / Consecutive

- SME attributes: Not specified by source.

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
  "base": {
    "register": "Xbase"
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

When base has the form &array[index], this intrinsic can use:

```asm
LD1B Zresult.D, Pg/Z, [Xarray, Xindex]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1B--scalar-plus-scalar--consecutive-registers---Contiguous-load-of-bytes-to-multiple-consecutive-vectors--scalar-index--

The general implementation is:

```asm
LD1B Zresult.D, Pg/Z, [Xbase, #0, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1B--scalar-plus-immediate--single-register---Contiguous-load-unsigned-bytes-to-vector--immediate-index--

### Operation

Source operation ID: `SveOperation_svld1ub_s16`

**Operation**



Return a vector in which each active element *i* contains the zero extension of `base[i]` and in which all other elements are zero.  Do not access memory for inactive elements.

## svld1ub_u16

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld1ub_u16

### Signature (source notation)

```c
svuint16_t svld1ub_u16(svbool_t pg, const uint8_t *base);
```

### Description

Load 8-bit data and zero-extend

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Load / Consecutive

- SME attributes: Not specified by source.

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
  "base": {
    "register": "Xbase"
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

When base has the form &array[index], this intrinsic can use:

```asm
LD1B Zresult.H, Pg/Z, [Xarray, Xindex]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1B--scalar-plus-scalar--consecutive-registers---Contiguous-load-of-bytes-to-multiple-consecutive-vectors--scalar-index--

The general implementation is:

```asm
LD1B Zresult.H, Pg/Z, [Xbase, #0, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1B--scalar-plus-immediate--single-register---Contiguous-load-unsigned-bytes-to-vector--immediate-index--

### Operation

Source operation ID: `SveOperation_svld1ub_s16`

**Operation**



Return a vector in which each active element *i* contains the zero extension of `base[i]` and in which all other elements are zero.  Do not access memory for inactive elements.

## svld1ub_u32

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld1ub_u32

### Signature (source notation)

```c
svuint32_t svld1ub_u32(svbool_t pg, const uint8_t *base);
```

### Description

Load 8-bit data and zero-extend

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Load / Consecutive

- SME attributes: Not specified by source.

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
  "base": {
    "register": "Xbase"
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

When base has the form &array[index], this intrinsic can use:

```asm
LD1B Zresult.S, Pg/Z, [Xarray, Xindex]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1B--scalar-plus-scalar--consecutive-registers---Contiguous-load-of-bytes-to-multiple-consecutive-vectors--scalar-index--

The general implementation is:

```asm
LD1B Zresult.S, Pg/Z, [Xbase, #0, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1B--scalar-plus-immediate--single-register---Contiguous-load-unsigned-bytes-to-vector--immediate-index--

### Operation

Source operation ID: `SveOperation_svld1ub_s16`

**Operation**



Return a vector in which each active element *i* contains the zero extension of `base[i]` and in which all other elements are zero.  Do not access memory for inactive elements.

## svld1ub_u64

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld1ub_u64

### Signature (source notation)

```c
svuint64_t svld1ub_u64(svbool_t pg, const uint8_t *base);
```

### Description

Load 8-bit data and zero-extend

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Load / Consecutive

- SME attributes: Not specified by source.

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
  "base": {
    "register": "Xbase"
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

When base has the form &array[index], this intrinsic can use:

```asm
LD1B Zresult.D, Pg/Z, [Xarray, Xindex]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1B--scalar-plus-scalar--consecutive-registers---Contiguous-load-of-bytes-to-multiple-consecutive-vectors--scalar-index--

The general implementation is:

```asm
LD1B Zresult.D, Pg/Z, [Xbase, #0, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1B--scalar-plus-immediate--single-register---Contiguous-load-unsigned-bytes-to-vector--immediate-index--

### Operation

Source operation ID: `SveOperation_svld1ub_s16`

**Operation**



Return a vector in which each active element *i* contains the zero extension of `base[i]` and in which all other elements are zero.  Do not access memory for inactive elements.

## svld1ub_vnum_s16

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld1ub_vnum_s16

### Signature (source notation)

```c
svint16_t svld1ub_vnum_s16(svbool_t pg, const uint8_t *base, int64_t vnum);
```

### Description

Load 8-bit data and zero-extend

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Load / Consecutive

- SME attributes: Not specified by source.

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
  "base": {
    "register": "Xbase"
  },
  "vnum * svcnth()": {
    "register": "Xindex"
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

When vnum is in the range [-8, 7], this intrinsic can use:

```asm
LD1B Zresult.H, Pg/Z, [Xbase, #vnum, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1B--scalar-plus-immediate--single-register---Contiguous-load-unsigned-bytes-to-vector--immediate-index--

The general implementation is:

```asm
LD1B Zresult.H, Pg/Z, [Xbase, Xindex]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1B--scalar-plus-scalar--consecutive-registers---Contiguous-load-of-bytes-to-multiple-consecutive-vectors--scalar-index--

### Operation

Source operation ID: `SveOperation_svld1ub_vnum_s16`

**Operation**



Return a vector of *n* elements in which each active element *i* contains the zero extension of `base[n * vnum + i]` and in which all other elements are zero.  Do not access memory for inactive elements.

## svld1ub_vnum_s32

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld1ub_vnum_s32

### Signature (source notation)

```c
svint32_t svld1ub_vnum_s32(svbool_t pg, const uint8_t *base, int64_t vnum);
```

### Description

Load 8-bit data and zero-extend

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Load / Consecutive

- SME attributes: Not specified by source.

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
  "base": {
    "register": "Xbase"
  },
  "vnum * svcntw()": {
    "register": "Xindex"
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

When vnum is in the range [-8, 7], this intrinsic can use:

```asm
LD1B Zresult.S, Pg/Z, [Xbase, #vnum, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1B--scalar-plus-immediate--single-register---Contiguous-load-unsigned-bytes-to-vector--immediate-index--

The general implementation is:

```asm
LD1B Zresult.S, Pg/Z, [Xbase, Xindex]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1B--scalar-plus-scalar--consecutive-registers---Contiguous-load-of-bytes-to-multiple-consecutive-vectors--scalar-index--

### Operation

Source operation ID: `SveOperation_svld1ub_vnum_s16`

**Operation**



Return a vector of *n* elements in which each active element *i* contains the zero extension of `base[n * vnum + i]` and in which all other elements are zero.  Do not access memory for inactive elements.

## svld1ub_vnum_s64

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld1ub_vnum_s64

### Signature (source notation)

```c
svint64_t svld1ub_vnum_s64(svbool_t pg, const uint8_t *base, int64_t vnum);
```

### Description

Load 8-bit data and zero-extend

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Load / Consecutive

- SME attributes: Not specified by source.

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
  "base": {
    "register": "Xbase"
  },
  "vnum * svcntd()": {
    "register": "Xindex"
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

When vnum is in the range [-8, 7], this intrinsic can use:

```asm
LD1B Zresult.D, Pg/Z, [Xbase, #vnum, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1B--scalar-plus-immediate--single-register---Contiguous-load-unsigned-bytes-to-vector--immediate-index--

The general implementation is:

```asm
LD1B Zresult.D, Pg/Z, [Xbase, Xindex]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1B--scalar-plus-scalar--consecutive-registers---Contiguous-load-of-bytes-to-multiple-consecutive-vectors--scalar-index--

### Operation

Source operation ID: `SveOperation_svld1ub_vnum_s16`

**Operation**



Return a vector of *n* elements in which each active element *i* contains the zero extension of `base[n * vnum + i]` and in which all other elements are zero.  Do not access memory for inactive elements.

## svld1ub_vnum_u16

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld1ub_vnum_u16

### Signature (source notation)

```c
svuint16_t svld1ub_vnum_u16(svbool_t pg, const uint8_t *base, int64_t vnum);
```

### Description

Load 8-bit data and zero-extend

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Load / Consecutive

- SME attributes: Not specified by source.

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
  "base": {
    "register": "Xbase"
  },
  "vnum * svcnth()": {
    "register": "Xindex"
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

When vnum is in the range [-8, 7], this intrinsic can use:

```asm
LD1B Zresult.H, Pg/Z, [Xbase, #vnum, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1B--scalar-plus-immediate--single-register---Contiguous-load-unsigned-bytes-to-vector--immediate-index--

The general implementation is:

```asm
LD1B Zresult.H, Pg/Z, [Xbase, Xindex]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1B--scalar-plus-scalar--consecutive-registers---Contiguous-load-of-bytes-to-multiple-consecutive-vectors--scalar-index--

### Operation

Source operation ID: `SveOperation_svld1ub_vnum_s16`

**Operation**



Return a vector of *n* elements in which each active element *i* contains the zero extension of `base[n * vnum + i]` and in which all other elements are zero.  Do not access memory for inactive elements.

## svld1ub_vnum_u32

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld1ub_vnum_u32

### Signature (source notation)

```c
svuint32_t svld1ub_vnum_u32(svbool_t pg, const uint8_t *base, int64_t vnum);
```

### Description

Load 8-bit data and zero-extend

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Load / Consecutive

- SME attributes: Not specified by source.

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
  "base": {
    "register": "Xbase"
  },
  "vnum * svcntw()": {
    "register": "Xindex"
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

When vnum is in the range [-8, 7], this intrinsic can use:

```asm
LD1B Zresult.S, Pg/Z, [Xbase, #vnum, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1B--scalar-plus-immediate--single-register---Contiguous-load-unsigned-bytes-to-vector--immediate-index--

The general implementation is:

```asm
LD1B Zresult.S, Pg/Z, [Xbase, Xindex]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1B--scalar-plus-scalar--consecutive-registers---Contiguous-load-of-bytes-to-multiple-consecutive-vectors--scalar-index--

### Operation

Source operation ID: `SveOperation_svld1ub_vnum_s16`

**Operation**



Return a vector of *n* elements in which each active element *i* contains the zero extension of `base[n * vnum + i]` and in which all other elements are zero.  Do not access memory for inactive elements.

## svld1ub_vnum_u64

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld1ub_vnum_u64

### Signature (source notation)

```c
svuint64_t svld1ub_vnum_u64(svbool_t pg, const uint8_t *base, int64_t vnum);
```

### Description

Load 8-bit data and zero-extend

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Load / Consecutive

- SME attributes: Not specified by source.

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
  "base": {
    "register": "Xbase"
  },
  "vnum * svcntd()": {
    "register": "Xindex"
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

When vnum is in the range [-8, 7], this intrinsic can use:

```asm
LD1B Zresult.D, Pg/Z, [Xbase, #vnum, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1B--scalar-plus-immediate--single-register---Contiguous-load-unsigned-bytes-to-vector--immediate-index--

The general implementation is:

```asm
LD1B Zresult.D, Pg/Z, [Xbase, Xindex]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1B--scalar-plus-scalar--consecutive-registers---Contiguous-load-of-bytes-to-multiple-consecutive-vectors--scalar-index--

### Operation

Source operation ID: `SveOperation_svld1ub_vnum_s16`

**Operation**



Return a vector of *n* elements in which each active element *i* contains the zero extension of `base[n * vnum + i]` and in which all other elements are zero.  Do not access memory for inactive elements.

## svld1uh_s32

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld1uh_s32

### Signature (source notation)

```c
svint32_t svld1uh_s32(svbool_t pg, const uint16_t *base);
```

### Description

Load 16-bit data and zero-extend

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Load / Consecutive

- SME attributes: Not specified by source.

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
  "base": {
    "register": "Xbase"
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

When base has the form &array[index], this intrinsic can use:

```asm
LD1H Zresult.S, Pg/Z, [Xarray, Xindex, LSL #1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1H--scalar-plus-scalar--consecutive-registers---Contiguous-load-of-halfwords-to-multiple-consecutive-vectors--scalar-index--

The general implementation is:

```asm
LD1H Zresult.S, Pg/Z, [Xbase, #0, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1H--scalar-plus-immediate--consecutive-registers---Contiguous-load-of-halfwords-to-multiple-consecutive-vectors--immediate-index--

### Operation

Source operation ID: `SveOperation_svld1ub_s16`

**Operation**



Return a vector in which each active element *i* contains the zero extension of `base[i]` and in which all other elements are zero.  Do not access memory for inactive elements.

## svld1uh_s64

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld1uh_s64

### Signature (source notation)

```c
svint64_t svld1uh_s64(svbool_t pg, const uint16_t *base);
```

### Description

Load 16-bit data and zero-extend

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Load / Consecutive

- SME attributes: Not specified by source.

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
  "base": {
    "register": "Xbase"
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

When base has the form &array[index], this intrinsic can use:

```asm
LD1H Zresult.D, Pg/Z, [Xarray, Xindex, LSL #1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1H--scalar-plus-scalar--consecutive-registers---Contiguous-load-of-halfwords-to-multiple-consecutive-vectors--scalar-index--

The general implementation is:

```asm
LD1H Zresult.D, Pg/Z, [Xbase, #0, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1H--scalar-plus-immediate--consecutive-registers---Contiguous-load-of-halfwords-to-multiple-consecutive-vectors--immediate-index--

### Operation

Source operation ID: `SveOperation_svld1ub_s16`

**Operation**



Return a vector in which each active element *i* contains the zero extension of `base[i]` and in which all other elements are zero.  Do not access memory for inactive elements.

## svld1uh_u32

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld1uh_u32

### Signature (source notation)

```c
svuint32_t svld1uh_u32(svbool_t pg, const uint16_t *base);
```

### Description

Load 16-bit data and zero-extend

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Load / Consecutive

- SME attributes: Not specified by source.

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
  "base": {
    "register": "Xbase"
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

When base has the form &array[index], this intrinsic can use:

```asm
LD1H Zresult.S, Pg/Z, [Xarray, Xindex, LSL #1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1H--scalar-plus-scalar--consecutive-registers---Contiguous-load-of-halfwords-to-multiple-consecutive-vectors--scalar-index--

The general implementation is:

```asm
LD1H Zresult.S, Pg/Z, [Xbase, #0, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1H--scalar-plus-immediate--consecutive-registers---Contiguous-load-of-halfwords-to-multiple-consecutive-vectors--immediate-index--

### Operation

Source operation ID: `SveOperation_svld1ub_s16`

**Operation**



Return a vector in which each active element *i* contains the zero extension of `base[i]` and in which all other elements are zero.  Do not access memory for inactive elements.

## svld1uh_u64

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld1uh_u64

### Signature (source notation)

```c
svuint64_t svld1uh_u64(svbool_t pg, const uint16_t *base);
```

### Description

Load 16-bit data and zero-extend

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Load / Consecutive

- SME attributes: Not specified by source.

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
  "base": {
    "register": "Xbase"
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

When base has the form &array[index], this intrinsic can use:

```asm
LD1H Zresult.D, Pg/Z, [Xarray, Xindex, LSL #1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1H--scalar-plus-scalar--consecutive-registers---Contiguous-load-of-halfwords-to-multiple-consecutive-vectors--scalar-index--

The general implementation is:

```asm
LD1H Zresult.D, Pg/Z, [Xbase, #0, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1H--scalar-plus-immediate--consecutive-registers---Contiguous-load-of-halfwords-to-multiple-consecutive-vectors--immediate-index--

### Operation

Source operation ID: `SveOperation_svld1ub_s16`

**Operation**



Return a vector in which each active element *i* contains the zero extension of `base[i]` and in which all other elements are zero.  Do not access memory for inactive elements.

## svld1uh_vnum_s32

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld1uh_vnum_s32

### Signature (source notation)

```c
svint32_t svld1uh_vnum_s32(svbool_t pg, const uint16_t *base, int64_t vnum);
```

### Description

Load 16-bit data and zero-extend

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Load / Consecutive

- SME attributes: Not specified by source.

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
  "base": {
    "register": "Xbase"
  },
  "vnum * svcntw()": {
    "register": "Xindex"
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

When vnum is in the range [-8, 7], this intrinsic can use:

```asm
LD1H Zresult.S, Pg/Z, [Xbase, #vnum, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1H--scalar-plus-immediate--consecutive-registers---Contiguous-load-of-halfwords-to-multiple-consecutive-vectors--immediate-index--

The general implementation is:

```asm
LD1H Zresult.S, Pg/Z, [Xbase, Xindex, LSL #1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1H--scalar-plus-scalar--consecutive-registers---Contiguous-load-of-halfwords-to-multiple-consecutive-vectors--scalar-index--

### Operation

Source operation ID: `SveOperation_svld1ub_vnum_s16`

**Operation**



Return a vector of *n* elements in which each active element *i* contains the zero extension of `base[n * vnum + i]` and in which all other elements are zero.  Do not access memory for inactive elements.

## svld1uh_vnum_s64

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld1uh_vnum_s64

### Signature (source notation)

```c
svint64_t svld1uh_vnum_s64(svbool_t pg, const uint16_t *base, int64_t vnum);
```

### Description

Load 16-bit data and zero-extend

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Load / Consecutive

- SME attributes: Not specified by source.

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
  "base": {
    "register": "Xbase"
  },
  "vnum * svcntd()": {
    "register": "Xindex"
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

When vnum is in the range [-8, 7], this intrinsic can use:

```asm
LD1H Zresult.D, Pg/Z, [Xbase, #vnum, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1H--scalar-plus-immediate--consecutive-registers---Contiguous-load-of-halfwords-to-multiple-consecutive-vectors--immediate-index--

The general implementation is:

```asm
LD1H Zresult.D, Pg/Z, [Xbase, Xindex, LSL #1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1H--scalar-plus-scalar--consecutive-registers---Contiguous-load-of-halfwords-to-multiple-consecutive-vectors--scalar-index--

### Operation

Source operation ID: `SveOperation_svld1ub_vnum_s16`

**Operation**



Return a vector of *n* elements in which each active element *i* contains the zero extension of `base[n * vnum + i]` and in which all other elements are zero.  Do not access memory for inactive elements.

## svld1uh_vnum_u32

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld1uh_vnum_u32

### Signature (source notation)

```c
svuint32_t svld1uh_vnum_u32(svbool_t pg, const uint16_t *base, int64_t vnum);
```

### Description

Load 16-bit data and zero-extend

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Load / Consecutive

- SME attributes: Not specified by source.

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
  "base": {
    "register": "Xbase"
  },
  "vnum * svcntw()": {
    "register": "Xindex"
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

When vnum is in the range [-8, 7], this intrinsic can use:

```asm
LD1H Zresult.S, Pg/Z, [Xbase, #vnum, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1H--scalar-plus-immediate--consecutive-registers---Contiguous-load-of-halfwords-to-multiple-consecutive-vectors--immediate-index--

The general implementation is:

```asm
LD1H Zresult.S, Pg/Z, [Xbase, Xindex, LSL #1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1H--scalar-plus-scalar--consecutive-registers---Contiguous-load-of-halfwords-to-multiple-consecutive-vectors--scalar-index--

### Operation

Source operation ID: `SveOperation_svld1ub_vnum_s16`

**Operation**



Return a vector of *n* elements in which each active element *i* contains the zero extension of `base[n * vnum + i]` and in which all other elements are zero.  Do not access memory for inactive elements.

## svld1uh_vnum_u64

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld1uh_vnum_u64

### Signature (source notation)

```c
svuint64_t svld1uh_vnum_u64(svbool_t pg, const uint16_t *base, int64_t vnum);
```

### Description

Load 16-bit data and zero-extend

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Load / Consecutive

- SME attributes: Not specified by source.

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
  "base": {
    "register": "Xbase"
  },
  "vnum * svcntd()": {
    "register": "Xindex"
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

When vnum is in the range [-8, 7], this intrinsic can use:

```asm
LD1H Zresult.D, Pg/Z, [Xbase, #vnum, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1H--scalar-plus-immediate--consecutive-registers---Contiguous-load-of-halfwords-to-multiple-consecutive-vectors--immediate-index--

The general implementation is:

```asm
LD1H Zresult.D, Pg/Z, [Xbase, Xindex, LSL #1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1H--scalar-plus-scalar--consecutive-registers---Contiguous-load-of-halfwords-to-multiple-consecutive-vectors--scalar-index--

### Operation

Source operation ID: `SveOperation_svld1ub_vnum_s16`

**Operation**



Return a vector of *n* elements in which each active element *i* contains the zero extension of `base[n * vnum + i]` and in which all other elements are zero.  Do not access memory for inactive elements.

## svld1uw_s64

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld1uw_s64

### Signature (source notation)

```c
svint64_t svld1uw_s64(svbool_t pg, const uint32_t *base);
```

### Description

Load 32-bit data and zero-extend

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Load / Consecutive

- SME attributes: Not specified by source.

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
  "base": {
    "register": "Xbase"
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

When base has the form &array[index], this intrinsic can use:

```asm
LD1W Zresult.D, Pg/Z, [Xarray, Xindex, LSL #2]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1W--scalar-plus-scalar--consecutive-registers---Contiguous-load-of-words-to-multiple-consecutive-vectors--scalar-index--

The general implementation is:

```asm
LD1W Zresult.D, Pg/Z, [Xbase, #0, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1W--scalar-plus-immediate--consecutive-registers---Contiguous-load-of-words-to-multiple-consecutive-vectors--immediate-index--

### Operation

Source operation ID: `SveOperation_svld1ub_s16`

**Operation**



Return a vector in which each active element *i* contains the zero extension of `base[i]` and in which all other elements are zero.  Do not access memory for inactive elements.

## svld1uw_u64

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld1uw_u64

### Signature (source notation)

```c
svuint64_t svld1uw_u64(svbool_t pg, const uint32_t *base);
```

### Description

Load 32-bit data and zero-extend

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Load / Consecutive

- SME attributes: Not specified by source.

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
  "base": {
    "register": "Xbase"
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

When base has the form &array[index], this intrinsic can use:

```asm
LD1W Zresult.D, Pg/Z, [Xarray, Xindex, LSL #2]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1W--scalar-plus-scalar--consecutive-registers---Contiguous-load-of-words-to-multiple-consecutive-vectors--scalar-index--

The general implementation is:

```asm
LD1W Zresult.D, Pg/Z, [Xbase, #0, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1W--scalar-plus-immediate--consecutive-registers---Contiguous-load-of-words-to-multiple-consecutive-vectors--immediate-index--

### Operation

Source operation ID: `SveOperation_svld1ub_s16`

**Operation**



Return a vector in which each active element *i* contains the zero extension of `base[i]` and in which all other elements are zero.  Do not access memory for inactive elements.

## svld1uw_vnum_s64

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld1uw_vnum_s64

### Signature (source notation)

```c
svint64_t svld1uw_vnum_s64(svbool_t pg, const uint32_t *base, int64_t vnum);
```

### Description

Load 32-bit data and zero-extend

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Load / Consecutive

- SME attributes: Not specified by source.

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
  "base": {
    "register": "Xbase"
  },
  "vnum * svcntd()": {
    "register": "Xindex"
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

When vnum is in the range [-8, 7], this intrinsic can use:

```asm
LD1W Zresult.D, Pg/Z, [Xbase, #vnum, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1W--scalar-plus-immediate--consecutive-registers---Contiguous-load-of-words-to-multiple-consecutive-vectors--immediate-index--

The general implementation is:

```asm
LD1W Zresult.D, Pg/Z, [Xbase, Xindex, LSL #2]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1W--scalar-plus-scalar--consecutive-registers---Contiguous-load-of-words-to-multiple-consecutive-vectors--scalar-index--

### Operation

Source operation ID: `SveOperation_svld1ub_vnum_s16`

**Operation**



Return a vector of *n* elements in which each active element *i* contains the zero extension of `base[n * vnum + i]` and in which all other elements are zero.  Do not access memory for inactive elements.

## svld1uw_vnum_u64

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld1uw_vnum_u64

### Signature (source notation)

```c
svuint64_t svld1uw_vnum_u64(svbool_t pg, const uint32_t *base, int64_t vnum);
```

### Description

Load 32-bit data and zero-extend

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Load / Consecutive

- SME attributes: Not specified by source.

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
  "base": {
    "register": "Xbase"
  },
  "vnum * svcntd()": {
    "register": "Xindex"
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

When vnum is in the range [-8, 7], this intrinsic can use:

```asm
LD1W Zresult.D, Pg/Z, [Xbase, #vnum, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1W--scalar-plus-immediate--consecutive-registers---Contiguous-load-of-words-to-multiple-consecutive-vectors--immediate-index--

The general implementation is:

```asm
LD1W Zresult.D, Pg/Z, [Xbase, Xindex, LSL #2]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1W--scalar-plus-scalar--consecutive-registers---Contiguous-load-of-words-to-multiple-consecutive-vectors--scalar-index--

### Operation

Source operation ID: `SveOperation_svld1ub_vnum_s16`

**Operation**



Return a vector of *n* elements in which each active element *i* contains the zero extension of `base[n * vnum + i]` and in which all other elements are zero.  Do not access memory for inactive elements.

## svld2[_bf16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld2%5B_bf16%5D

### Signature (source notation)

```c
svbfloat16x2_t svld2[_bf16](svbool_t pg, const bfloat16_t *base);
```

### Description

Load two-element tuples into two vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Load / Consecutive

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME
```

### Return type metadata

```json
{
  "return_base_type": "bfloat",
  "element_bit_size": "16",
  "value": "svbfloat16x2_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Pg"
  },
  "base": {
    "register": "Xbase"
  }
}
```

### Result mapping

```json
[
  {
    "{Zresult0.H, Zresult1.H}": "result"
  }
]
```

### Instruction mapping

When base has the form &array[index], this intrinsic can use:

```asm
LD2H {Zresult0.H, Zresult1.H}, Pg/Z, [Xarray, Xindex, LSL #1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD2H--scalar-plus-scalar---Contiguous-load-two-halfword-structures-to-two-vectors--scalar-index--

The general implementation is:

```asm
LD2H {Zresult0.H, Zresult1.H}, Pg/Z, [Xbase, #0, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD2H--scalar-plus-immediate---Contiguous-load-two-halfword-structures-to-two-vectors--immediate-index--

### Operation

Source operation ID: `SveOperation_svld2_bf16`

**Operation**



Return a tuple of two vectors in which each active element *i* of vector *j* contains `base[i * 2 + j]` and in which all other elements are zero.  Do not access memory for inactive elements.

## svld2[_f16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld2%5B_f16%5D

### Signature (source notation)

```c
svfloat16x2_t svld2[_f16](svbool_t pg, const float16_t *base);
```

### Description

Load two-element tuples into two vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Load / Consecutive

- SME attributes: Not specified by source.

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
  "value": "svfloat16x2_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Pg"
  },
  "base": {
    "register": "Xbase"
  }
}
```

### Result mapping

```json
[
  {
    "{Zresult0.H, Zresult1.H}": "result"
  }
]
```

### Instruction mapping

When base has the form &array[index], this intrinsic can use:

```asm
LD2H {Zresult0.H, Zresult1.H}, Pg/Z, [Xarray, Xindex, LSL #1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD2H--scalar-plus-scalar---Contiguous-load-two-halfword-structures-to-two-vectors--scalar-index--

The general implementation is:

```asm
LD2H {Zresult0.H, Zresult1.H}, Pg/Z, [Xbase, #0, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD2H--scalar-plus-immediate---Contiguous-load-two-halfword-structures-to-two-vectors--immediate-index--

### Operation

Source operation ID: `SveOperation_svld2_bf16`

**Operation**



Return a tuple of two vectors in which each active element *i* of vector *j* contains `base[i * 2 + j]` and in which all other elements are zero.  Do not access memory for inactive elements.

## svld2[_f32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld2%5B_f32%5D

### Signature (source notation)

```c
svfloat32x2_t svld2[_f32](svbool_t pg, const float32_t *base);
```

### Description

Load two-element tuples into two vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Load / Consecutive

- SME attributes: Not specified by source.

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
  "value": "svfloat32x2_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Pg"
  },
  "base": {
    "register": "Xbase"
  }
}
```

### Result mapping

```json
[
  {
    "{Zresult0.S, Zresult1.S}": "result"
  }
]
```

### Instruction mapping

When base has the form &array[index], this intrinsic can use:

```asm
LD2W {Zresult0.S, Zresult1.S}, Pg/Z, [Xarray, Xindex, LSL #2]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD2W--scalar-plus-scalar---Contiguous-load-two-word-structures-to-two-vectors--scalar-index--

The general implementation is:

```asm
LD2W {Zresult0.S, Zresult1.S}, Pg/Z, [Xbase, #0, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD2W--scalar-plus-immediate---Contiguous-load-two-word-structures-to-two-vectors--immediate-index--

### Operation

Source operation ID: `SveOperation_svld2_bf16`

**Operation**



Return a tuple of two vectors in which each active element *i* of vector *j* contains `base[i * 2 + j]` and in which all other elements are zero.  Do not access memory for inactive elements.

## svld2[_f64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld2%5B_f64%5D

### Signature (source notation)

```c
svfloat64x2_t svld2[_f64](svbool_t pg, const float64_t *base);
```

### Description

Load two-element tuples into two vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Load / Consecutive

- SME attributes: Not specified by source.

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
  "value": "svfloat64x2_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Pg"
  },
  "base": {
    "register": "Xbase"
  }
}
```

### Result mapping

```json
[
  {
    "{Zresult0.D, Zresult1.D}": "result"
  }
]
```

### Instruction mapping

When base has the form &array[index], this intrinsic can use:

```asm
LD2D {Zresult0.D, Zresult1.D}, Pg/Z, [Xarray, Xindex, LSL #3]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD2D--scalar-plus-scalar---Contiguous-load-two-doubleword-structures-to-two-vectors--scalar-index--

The general implementation is:

```asm
LD2D {Zresult0.D, Zresult1.D}, Pg/Z, [Xbase, #0, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD2D--scalar-plus-immediate---Contiguous-load-two-doubleword-structures-to-two-vectors--immediate-index--

### Operation

Source operation ID: `SveOperation_svld2_bf16`

**Operation**



Return a tuple of two vectors in which each active element *i* of vector *j* contains `base[i * 2 + j]` and in which all other elements are zero.  Do not access memory for inactive elements.

