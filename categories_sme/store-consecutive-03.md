# SME / Store / Consecutive — Part 3

## svst1b[_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst1b%5B_s64%5D

### Signature (source notation)

```c
void svst1b[_s64](svbool_t pg, int8_t *base, svint64_t data);
```

### Description

Truncate to 8 bits and store

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Store / Consecutive

- SME attributes: Not specified by source.

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
  "value": "void"
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
  "data": {
    "register": "Zdata.D"
  }
}
```

### Result mapping

```json
[]
```

### Instruction mapping

When base has the form &array[index], this intrinsic can use:

```asm
ST1B Zdata.D, Pg, [Xarray, Xindex]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST1B--scalar-plus-scalar--consecutive-registers---Contiguous-store-of-bytes-from-multiple-consecutive-vectors--scalar-index--

The general implementation is:

```asm
ST1B Zdata.D, Pg, [Xbase, #0, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST1B--scalar-plus-immediate--consecutive-registers---Contiguous-store-of-bytes-from-multiple-consecutive-vectors--immediate-index--

### Operation

Source operation ID: `SveOperation_svst1b_s16`

**Operation**



For each active element *i*, truncate `data[i]` to 8 bits and store it to `base[i]`. Do not access memory for inactive elements.

## svst1b[_u16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst1b%5B_u16%5D

### Signature (source notation)

```c
void svst1b[_u16](svbool_t pg, uint8_t *base, svuint16_t data);
```

### Description

Truncate to 8 bits and store

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Store / Consecutive

- SME attributes: Not specified by source.

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
  "value": "void"
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
  "data": {
    "register": "Zdata.H"
  }
}
```

### Result mapping

```json
[]
```

### Instruction mapping

When base has the form &array[index], this intrinsic can use:

```asm
ST1B Zdata.H, Pg, [Xarray, Xindex]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST1B--scalar-plus-scalar--consecutive-registers---Contiguous-store-of-bytes-from-multiple-consecutive-vectors--scalar-index--

The general implementation is:

```asm
ST1B Zdata.H, Pg, [Xbase, #0, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST1B--scalar-plus-immediate--consecutive-registers---Contiguous-store-of-bytes-from-multiple-consecutive-vectors--immediate-index--

### Operation

Source operation ID: `SveOperation_svst1b_s16`

**Operation**



For each active element *i*, truncate `data[i]` to 8 bits and store it to `base[i]`. Do not access memory for inactive elements.

## svst1b[_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst1b%5B_u32%5D

### Signature (source notation)

```c
void svst1b[_u32](svbool_t pg, uint8_t *base, svuint32_t data);
```

### Description

Truncate to 8 bits and store

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Store / Consecutive

- SME attributes: Not specified by source.

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
  "value": "void"
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
  "data": {
    "register": "Zdata.S"
  }
}
```

### Result mapping

```json
[]
```

### Instruction mapping

When base has the form &array[index], this intrinsic can use:

```asm
ST1B Zdata.S, Pg, [Xarray, Xindex]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST1B--scalar-plus-scalar--consecutive-registers---Contiguous-store-of-bytes-from-multiple-consecutive-vectors--scalar-index--

The general implementation is:

```asm
ST1B Zdata.S, Pg, [Xbase, #0, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST1B--scalar-plus-immediate--consecutive-registers---Contiguous-store-of-bytes-from-multiple-consecutive-vectors--immediate-index--

### Operation

Source operation ID: `SveOperation_svst1b_s16`

**Operation**



For each active element *i*, truncate `data[i]` to 8 bits and store it to `base[i]`. Do not access memory for inactive elements.

## svst1b[_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst1b%5B_u64%5D

### Signature (source notation)

```c
void svst1b[_u64](svbool_t pg, uint8_t *base, svuint64_t data);
```

### Description

Truncate to 8 bits and store

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Store / Consecutive

- SME attributes: Not specified by source.

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
  "value": "void"
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
  "data": {
    "register": "Zdata.D"
  }
}
```

### Result mapping

```json
[]
```

### Instruction mapping

When base has the form &array[index], this intrinsic can use:

```asm
ST1B Zdata.D, Pg, [Xarray, Xindex]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST1B--scalar-plus-scalar--consecutive-registers---Contiguous-store-of-bytes-from-multiple-consecutive-vectors--scalar-index--

The general implementation is:

```asm
ST1B Zdata.D, Pg, [Xbase, #0, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST1B--scalar-plus-immediate--consecutive-registers---Contiguous-store-of-bytes-from-multiple-consecutive-vectors--immediate-index--

### Operation

Source operation ID: `SveOperation_svst1b_s16`

**Operation**



For each active element *i*, truncate `data[i]` to 8 bits and store it to `base[i]`. Do not access memory for inactive elements.

## svst1b_vnum[_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst1b_vnum%5B_s16%5D

### Signature (source notation)

```c
void svst1b_vnum[_s16](svbool_t pg, int8_t *base, int64_t vnum, svint16_t data);
```

### Description

Truncate to 8 bits and store

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Store / Consecutive

- SME attributes: Not specified by source.

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
  "value": "void"
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
  "data": {
    "register": "Zdata.H"
  },
  "vnum * svcnth()": {
    "register": "Xindex"
  }
}
```

### Result mapping

```json
[]
```

### Instruction mapping

When vnum is in the range [-8, 7], this intrinsic can use:

```asm
ST1B Zdata.H, Pg, [Xbase, #vnum, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST1B--scalar-plus-immediate--consecutive-registers---Contiguous-store-of-bytes-from-multiple-consecutive-vectors--immediate-index--

The general implementation is:

```asm
ST1B Zdata.H, Pg, [Xbase, Xindex]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST1B--scalar-plus-scalar--consecutive-registers---Contiguous-store-of-bytes-from-multiple-consecutive-vectors--scalar-index--

### Operation

Source operation ID: `SveOperation_svst1b_vnum_s16`

**Operation**



For each active element *i*, truncate `data[i]` to 8 bits and store it to `base[n * vnum + i]`, where *n* is the number of elements in `data`. Do not access memory for inactive elements.

## svst1b_vnum[_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst1b_vnum%5B_s32%5D

### Signature (source notation)

```c
void svst1b_vnum[_s32](svbool_t pg, int8_t *base, int64_t vnum, svint32_t data);
```

### Description

Truncate to 8 bits and store

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Store / Consecutive

- SME attributes: Not specified by source.

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
  "value": "void"
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
  "data": {
    "register": "Zdata.S"
  },
  "vnum * svcntw()": {
    "register": "Xindex"
  }
}
```

### Result mapping

```json
[]
```

### Instruction mapping

When vnum is in the range [-8, 7], this intrinsic can use:

```asm
ST1B Zdata.S, Pg, [Xbase, #vnum, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST1B--scalar-plus-immediate--consecutive-registers---Contiguous-store-of-bytes-from-multiple-consecutive-vectors--immediate-index--

The general implementation is:

```asm
ST1B Zdata.S, Pg, [Xbase, Xindex]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST1B--scalar-plus-scalar--consecutive-registers---Contiguous-store-of-bytes-from-multiple-consecutive-vectors--scalar-index--

### Operation

Source operation ID: `SveOperation_svst1b_vnum_s16`

**Operation**



For each active element *i*, truncate `data[i]` to 8 bits and store it to `base[n * vnum + i]`, where *n* is the number of elements in `data`. Do not access memory for inactive elements.

## svst1b_vnum[_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst1b_vnum%5B_s64%5D

### Signature (source notation)

```c
void svst1b_vnum[_s64](svbool_t pg, int8_t *base, int64_t vnum, svint64_t data);
```

### Description

Truncate to 8 bits and store

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Store / Consecutive

- SME attributes: Not specified by source.

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
  "value": "void"
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
  "data": {
    "register": "Zdata.D"
  },
  "vnum * svcntd()": {
    "register": "Xindex"
  }
}
```

### Result mapping

```json
[]
```

### Instruction mapping

When vnum is in the range [-8, 7], this intrinsic can use:

```asm
ST1B Zdata.D, Pg, [Xbase, #vnum, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST1B--scalar-plus-immediate--consecutive-registers---Contiguous-store-of-bytes-from-multiple-consecutive-vectors--immediate-index--

The general implementation is:

```asm
ST1B Zdata.D, Pg, [Xbase, Xindex]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST1B--scalar-plus-scalar--consecutive-registers---Contiguous-store-of-bytes-from-multiple-consecutive-vectors--scalar-index--

### Operation

Source operation ID: `SveOperation_svst1b_vnum_s16`

**Operation**



For each active element *i*, truncate `data[i]` to 8 bits and store it to `base[n * vnum + i]`, where *n* is the number of elements in `data`. Do not access memory for inactive elements.

## svst1b_vnum[_u16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst1b_vnum%5B_u16%5D

### Signature (source notation)

```c
void svst1b_vnum[_u16](svbool_t pg, uint8_t *base, int64_t vnum, svuint16_t data);
```

### Description

Truncate to 8 bits and store

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Store / Consecutive

- SME attributes: Not specified by source.

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
  "value": "void"
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
  "data": {
    "register": "Zdata.H"
  },
  "vnum * svcnth()": {
    "register": "Xindex"
  }
}
```

### Result mapping

```json
[]
```

### Instruction mapping

When vnum is in the range [-8, 7], this intrinsic can use:

```asm
ST1B Zdata.H, Pg, [Xbase, #vnum, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST1B--scalar-plus-immediate--consecutive-registers---Contiguous-store-of-bytes-from-multiple-consecutive-vectors--immediate-index--

The general implementation is:

```asm
ST1B Zdata.H, Pg, [Xbase, Xindex]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST1B--scalar-plus-scalar--consecutive-registers---Contiguous-store-of-bytes-from-multiple-consecutive-vectors--scalar-index--

### Operation

Source operation ID: `SveOperation_svst1b_vnum_s16`

**Operation**



For each active element *i*, truncate `data[i]` to 8 bits and store it to `base[n * vnum + i]`, where *n* is the number of elements in `data`. Do not access memory for inactive elements.

## svst1b_vnum[_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst1b_vnum%5B_u32%5D

### Signature (source notation)

```c
void svst1b_vnum[_u32](svbool_t pg, uint8_t *base, int64_t vnum, svuint32_t data);
```

### Description

Truncate to 8 bits and store

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Store / Consecutive

- SME attributes: Not specified by source.

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
  "value": "void"
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
  "data": {
    "register": "Zdata.S"
  },
  "vnum * svcntw()": {
    "register": "Xindex"
  }
}
```

### Result mapping

```json
[]
```

### Instruction mapping

When vnum is in the range [-8, 7], this intrinsic can use:

```asm
ST1B Zdata.S, Pg, [Xbase, #vnum, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST1B--scalar-plus-immediate--consecutive-registers---Contiguous-store-of-bytes-from-multiple-consecutive-vectors--immediate-index--

The general implementation is:

```asm
ST1B Zdata.S, Pg, [Xbase, Xindex]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST1B--scalar-plus-scalar--consecutive-registers---Contiguous-store-of-bytes-from-multiple-consecutive-vectors--scalar-index--

### Operation

Source operation ID: `SveOperation_svst1b_vnum_s16`

**Operation**



For each active element *i*, truncate `data[i]` to 8 bits and store it to `base[n * vnum + i]`, where *n* is the number of elements in `data`. Do not access memory for inactive elements.

## svst1b_vnum[_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst1b_vnum%5B_u64%5D

### Signature (source notation)

```c
void svst1b_vnum[_u64](svbool_t pg, uint8_t *base, int64_t vnum, svuint64_t data);
```

### Description

Truncate to 8 bits and store

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Store / Consecutive

- SME attributes: Not specified by source.

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
  "value": "void"
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
  "data": {
    "register": "Zdata.D"
  },
  "vnum * svcntd()": {
    "register": "Xindex"
  }
}
```

### Result mapping

```json
[]
```

### Instruction mapping

When vnum is in the range [-8, 7], this intrinsic can use:

```asm
ST1B Zdata.D, Pg, [Xbase, #vnum, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST1B--scalar-plus-immediate--consecutive-registers---Contiguous-store-of-bytes-from-multiple-consecutive-vectors--immediate-index--

The general implementation is:

```asm
ST1B Zdata.D, Pg, [Xbase, Xindex]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST1B--scalar-plus-scalar--consecutive-registers---Contiguous-store-of-bytes-from-multiple-consecutive-vectors--scalar-index--

### Operation

Source operation ID: `SveOperation_svst1b_vnum_s16`

**Operation**



For each active element *i*, truncate `data[i]` to 8 bits and store it to `base[n * vnum + i]`, where *n* is the number of elements in `data`. Do not access memory for inactive elements.

## svst1h[_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst1h%5B_s32%5D

### Signature (source notation)

```c
void svst1h[_s32](svbool_t pg, int16_t *base, svint32_t data);
```

### Description

Truncate to 16 bits and store

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Store / Consecutive

- SME attributes: Not specified by source.

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
  "value": "void"
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
  "data": {
    "register": "Zdata.S"
  }
}
```

### Result mapping

```json
[]
```

### Instruction mapping

When base has the form &array[index], this intrinsic can use:

```asm
ST1H Zdata.S, Pg, [Xarray, Xindex, LSL #1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST1H--scalar-plus-scalar--consecutive-registers---Contiguous-store-of-halfwords-from-multiple-consecutive-vectors--scalar-index--

The general implementation is:

```asm
ST1H Zdata.S, Pg, [Xbase, #0, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST1H--scalar-plus-immediate--consecutive-registers---Contiguous-store-of-halfwords-from-multiple-consecutive-vectors--immediate-index--

### Operation

Source operation ID: `SveOperation_svst1h_s32`

**Operation**



For each active element *i*, truncate `data[i]` to 16 bits and store it to `base[i]`. Do not access memory for inactive elements.

## svst1h[_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst1h%5B_s64%5D

### Signature (source notation)

```c
void svst1h[_s64](svbool_t pg, int16_t *base, svint64_t data);
```

### Description

Truncate to 16 bits and store

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Store / Consecutive

- SME attributes: Not specified by source.

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
  "value": "void"
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
  "data": {
    "register": "Zdata.D"
  }
}
```

### Result mapping

```json
[]
```

### Instruction mapping

When base has the form &array[index], this intrinsic can use:

```asm
ST1H Zdata.D, Pg, [Xarray, Xindex, LSL #1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST1H--scalar-plus-scalar--consecutive-registers---Contiguous-store-of-halfwords-from-multiple-consecutive-vectors--scalar-index--

The general implementation is:

```asm
ST1H Zdata.D, Pg, [Xbase, #0, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST1H--scalar-plus-immediate--consecutive-registers---Contiguous-store-of-halfwords-from-multiple-consecutive-vectors--immediate-index--

### Operation

Source operation ID: `SveOperation_svst1h_s32`

**Operation**



For each active element *i*, truncate `data[i]` to 16 bits and store it to `base[i]`. Do not access memory for inactive elements.

## svst1h[_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst1h%5B_u32%5D

### Signature (source notation)

```c
void svst1h[_u32](svbool_t pg, uint16_t *base, svuint32_t data);
```

### Description

Truncate to 16 bits and store

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Store / Consecutive

- SME attributes: Not specified by source.

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
  "value": "void"
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
  "data": {
    "register": "Zdata.S"
  }
}
```

### Result mapping

```json
[]
```

### Instruction mapping

When base has the form &array[index], this intrinsic can use:

```asm
ST1H Zdata.S, Pg, [Xarray, Xindex, LSL #1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST1H--scalar-plus-scalar--consecutive-registers---Contiguous-store-of-halfwords-from-multiple-consecutive-vectors--scalar-index--

The general implementation is:

```asm
ST1H Zdata.S, Pg, [Xbase, #0, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST1H--scalar-plus-immediate--consecutive-registers---Contiguous-store-of-halfwords-from-multiple-consecutive-vectors--immediate-index--

### Operation

Source operation ID: `SveOperation_svst1h_s32`

**Operation**



For each active element *i*, truncate `data[i]` to 16 bits and store it to `base[i]`. Do not access memory for inactive elements.

## svst1h[_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst1h%5B_u64%5D

### Signature (source notation)

```c
void svst1h[_u64](svbool_t pg, uint16_t *base, svuint64_t data);
```

### Description

Truncate to 16 bits and store

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Store / Consecutive

- SME attributes: Not specified by source.

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
  "value": "void"
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
  "data": {
    "register": "Zdata.D"
  }
}
```

### Result mapping

```json
[]
```

### Instruction mapping

When base has the form &array[index], this intrinsic can use:

```asm
ST1H Zdata.D, Pg, [Xarray, Xindex, LSL #1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST1H--scalar-plus-scalar--consecutive-registers---Contiguous-store-of-halfwords-from-multiple-consecutive-vectors--scalar-index--

The general implementation is:

```asm
ST1H Zdata.D, Pg, [Xbase, #0, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST1H--scalar-plus-immediate--consecutive-registers---Contiguous-store-of-halfwords-from-multiple-consecutive-vectors--immediate-index--

### Operation

Source operation ID: `SveOperation_svst1h_s32`

**Operation**



For each active element *i*, truncate `data[i]` to 16 bits and store it to `base[i]`. Do not access memory for inactive elements.

## svst1h_vnum[_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst1h_vnum%5B_s32%5D

### Signature (source notation)

```c
void svst1h_vnum[_s32](svbool_t pg, int16_t *base, int64_t vnum, svint32_t data);
```

### Description

Truncate to 16 bits and store

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Store / Consecutive

- SME attributes: Not specified by source.

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
  "value": "void"
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
  "data": {
    "register": "Zdata.S"
  },
  "vnum * svcntw()": {
    "register": "Xindex"
  }
}
```

### Result mapping

```json
[]
```

### Instruction mapping

When vnum is in the range [-8, 7], this intrinsic can use:

```asm
ST1H Zdata.S, Pg, [Xbase, #vnum, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST1H--scalar-plus-immediate--consecutive-registers---Contiguous-store-of-halfwords-from-multiple-consecutive-vectors--immediate-index--

The general implementation is:

```asm
ST1H Zdata.S, Pg, [Xbase, Xindex, LSL #1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST1H--scalar-plus-scalar--consecutive-registers---Contiguous-store-of-halfwords-from-multiple-consecutive-vectors--scalar-index--

### Operation

Source operation ID: `SveOperation_svst1h_vnum_s32`

**Operation**



For each active element *i*, truncate `data[i]` to 16 bits and store it to `base[n * vnum + i]`, where *n* is the number of elements in `data`. Do not access memory for inactive elements.

## svst1h_vnum[_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst1h_vnum%5B_s64%5D

### Signature (source notation)

```c
void svst1h_vnum[_s64](svbool_t pg, int16_t *base, int64_t vnum, svint64_t data);
```

### Description

Truncate to 16 bits and store

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Store / Consecutive

- SME attributes: Not specified by source.

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
  "value": "void"
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
  "data": {
    "register": "Zdata.D"
  },
  "vnum * svcntd()": {
    "register": "Xindex"
  }
}
```

### Result mapping

```json
[]
```

### Instruction mapping

When vnum is in the range [-8, 7], this intrinsic can use:

```asm
ST1H Zdata.D, Pg, [Xbase, #vnum, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST1H--scalar-plus-immediate--consecutive-registers---Contiguous-store-of-halfwords-from-multiple-consecutive-vectors--immediate-index--

The general implementation is:

```asm
ST1H Zdata.D, Pg, [Xbase, Xindex, LSL #1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST1H--scalar-plus-scalar--consecutive-registers---Contiguous-store-of-halfwords-from-multiple-consecutive-vectors--scalar-index--

### Operation

Source operation ID: `SveOperation_svst1h_vnum_s32`

**Operation**



For each active element *i*, truncate `data[i]` to 16 bits and store it to `base[n * vnum + i]`, where *n* is the number of elements in `data`. Do not access memory for inactive elements.

## svst1h_vnum[_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst1h_vnum%5B_u32%5D

### Signature (source notation)

```c
void svst1h_vnum[_u32](svbool_t pg, uint16_t *base, int64_t vnum, svuint32_t data);
```

### Description

Truncate to 16 bits and store

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Store / Consecutive

- SME attributes: Not specified by source.

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
  "value": "void"
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
  "data": {
    "register": "Zdata.S"
  },
  "vnum * svcntw()": {
    "register": "Xindex"
  }
}
```

### Result mapping

```json
[]
```

### Instruction mapping

When vnum is in the range [-8, 7], this intrinsic can use:

```asm
ST1H Zdata.S, Pg, [Xbase, #vnum, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST1H--scalar-plus-immediate--consecutive-registers---Contiguous-store-of-halfwords-from-multiple-consecutive-vectors--immediate-index--

The general implementation is:

```asm
ST1H Zdata.S, Pg, [Xbase, Xindex, LSL #1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST1H--scalar-plus-scalar--consecutive-registers---Contiguous-store-of-halfwords-from-multiple-consecutive-vectors--scalar-index--

### Operation

Source operation ID: `SveOperation_svst1h_vnum_s32`

**Operation**



For each active element *i*, truncate `data[i]` to 16 bits and store it to `base[n * vnum + i]`, where *n* is the number of elements in `data`. Do not access memory for inactive elements.

## svst1h_vnum[_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst1h_vnum%5B_u64%5D

### Signature (source notation)

```c
void svst1h_vnum[_u64](svbool_t pg, uint16_t *base, int64_t vnum, svuint64_t data);
```

### Description

Truncate to 16 bits and store

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Store / Consecutive

- SME attributes: Not specified by source.

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
  "value": "void"
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
  "data": {
    "register": "Zdata.D"
  },
  "vnum * svcntd()": {
    "register": "Xindex"
  }
}
```

### Result mapping

```json
[]
```

### Instruction mapping

When vnum is in the range [-8, 7], this intrinsic can use:

```asm
ST1H Zdata.D, Pg, [Xbase, #vnum, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST1H--scalar-plus-immediate--consecutive-registers---Contiguous-store-of-halfwords-from-multiple-consecutive-vectors--immediate-index--

The general implementation is:

```asm
ST1H Zdata.D, Pg, [Xbase, Xindex, LSL #1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST1H--scalar-plus-scalar--consecutive-registers---Contiguous-store-of-halfwords-from-multiple-consecutive-vectors--scalar-index--

### Operation

Source operation ID: `SveOperation_svst1h_vnum_s32`

**Operation**



For each active element *i*, truncate `data[i]` to 16 bits and store it to `base[n * vnum + i]`, where *n* is the number of elements in `data`. Do not access memory for inactive elements.

## svst1w[_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst1w%5B_s64%5D

### Signature (source notation)

```c
void svst1w[_s64](svbool_t pg, int32_t *base, svint64_t data);
```

### Description

Truncate to 32 bits and store

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Store / Consecutive

- SME attributes: Not specified by source.

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
  "value": "void"
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
  "data": {
    "register": "Zdata.D"
  }
}
```

### Result mapping

```json
[]
```

### Instruction mapping

When base has the form &array[index], this intrinsic can use:

```asm
ST1W Zdata.D, Pg, [Xarray, Xindex, LSL #2]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST1W--scalar-plus-scalar--consecutive-registers---Contiguous-store-of-words-from-multiple-consecutive-vectors--scalar-index--

The general implementation is:

```asm
ST1W Zdata.D, Pg, [Xbase, #0, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST1W--scalar-plus-immediate--consecutive-registers---Contiguous-store-of-words-from-multiple-consecutive-vectors--immediate-index--

### Operation

Source operation ID: `SveOperation_svst1w_s64`

**Operation**



For each active element *i*, truncate `data[i]` to 32 bits and store it to `base[i]`. Do not access memory for inactive elements.

## svst1w[_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst1w%5B_u64%5D

### Signature (source notation)

```c
void svst1w[_u64](svbool_t pg, uint32_t *base, svuint64_t data);
```

### Description

Truncate to 32 bits and store

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Store / Consecutive

- SME attributes: Not specified by source.

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
  "value": "void"
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
  "data": {
    "register": "Zdata.D"
  }
}
```

### Result mapping

```json
[]
```

### Instruction mapping

When base has the form &array[index], this intrinsic can use:

```asm
ST1W Zdata.D, Pg, [Xarray, Xindex, LSL #2]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST1W--scalar-plus-scalar--consecutive-registers---Contiguous-store-of-words-from-multiple-consecutive-vectors--scalar-index--

The general implementation is:

```asm
ST1W Zdata.D, Pg, [Xbase, #0, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST1W--scalar-plus-immediate--consecutive-registers---Contiguous-store-of-words-from-multiple-consecutive-vectors--immediate-index--

### Operation

Source operation ID: `SveOperation_svst1w_s64`

**Operation**



For each active element *i*, truncate `data[i]` to 32 bits and store it to `base[i]`. Do not access memory for inactive elements.

## svst1w_vnum[_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst1w_vnum%5B_s64%5D

### Signature (source notation)

```c
void svst1w_vnum[_s64](svbool_t pg, int32_t *base, int64_t vnum, svint64_t data);
```

### Description

Truncate to 32 bits and store

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Store / Consecutive

- SME attributes: Not specified by source.

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
  "value": "void"
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
  "data": {
    "register": "Zdata.D"
  },
  "vnum * svcntd()": {
    "register": "Xindex"
  }
}
```

### Result mapping

```json
[]
```

### Instruction mapping

When vnum is in the range [-8, 7], this intrinsic can use:

```asm
ST1W Zdata.D, Pg, [Xbase, #vnum, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST1W--scalar-plus-immediate--consecutive-registers---Contiguous-store-of-words-from-multiple-consecutive-vectors--immediate-index--

The general implementation is:

```asm
ST1W Zdata.D, Pg, [Xbase, Xindex, LSL #2]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST1W--scalar-plus-scalar--consecutive-registers---Contiguous-store-of-words-from-multiple-consecutive-vectors--scalar-index--

### Operation

Source operation ID: `SveOperation_svst1w_vnum_s64`

**Operation**



For each active element *i*, truncate `data[i]` to 32 bits and store it to `base[n * vnum + i]`, where *n* is the number of elements in `data`. Do not access memory for inactive elements.

## svst1w_vnum[_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst1w_vnum%5B_u64%5D

### Signature (source notation)

```c
void svst1w_vnum[_u64](svbool_t pg, uint32_t *base, int64_t vnum, svuint64_t data);
```

### Description

Truncate to 32 bits and store

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Store / Consecutive

- SME attributes: Not specified by source.

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
  "value": "void"
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
  "data": {
    "register": "Zdata.D"
  },
  "vnum * svcntd()": {
    "register": "Xindex"
  }
}
```

### Result mapping

```json
[]
```

### Instruction mapping

When vnum is in the range [-8, 7], this intrinsic can use:

```asm
ST1W Zdata.D, Pg, [Xbase, #vnum, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST1W--scalar-plus-immediate--consecutive-registers---Contiguous-store-of-words-from-multiple-consecutive-vectors--immediate-index--

The general implementation is:

```asm
ST1W Zdata.D, Pg, [Xbase, Xindex, LSL #2]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST1W--scalar-plus-scalar--consecutive-registers---Contiguous-store-of-words-from-multiple-consecutive-vectors--scalar-index--

### Operation

Source operation ID: `SveOperation_svst1w_vnum_s64`

**Operation**



For each active element *i*, truncate `data[i]` to 32 bits and store it to `base[n * vnum + i]`, where *n* is the number of elements in `data`. Do not access memory for inactive elements.

## svst2[_bf16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst2%5B_bf16%5D

### Signature (source notation)

```c
void svst2[_bf16](svbool_t pg, bfloat16_t *base, svbfloat16x2_t data);
```

### Description

Store two vectors into two-element tuples

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Store / Consecutive

- SME attributes: Not specified by source.

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
  "value": "void"
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
  "data": {
    "register": "{Zdata0.H, Zdata1.H}"
  }
}
```

### Result mapping

```json
[]
```

### Instruction mapping

When base has the form &array[index], this intrinsic can use:

```asm
ST2H {Zdata0.H, Zdata1.H}, Pg, [Xarray, Xindex, LSL #1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST2H--scalar-plus-scalar---Contiguous-store-two-halfword-structures-from-two-vectors--scalar-index--

The general implementation is:

```asm
ST2H {Zdata0.H, Zdata1.H}, Pg, [Xbase, #0, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST2H--scalar-plus-immediate---Contiguous-store-two-halfword-structures-from-two-vectors--immediate-index--

### Operation

Source operation ID: `SveOperation_svst2_bf16`

**Operation**



For each active element *i* and for each vector index *j*, store `data[j][i]` to `base[i * 2 + j]`. Do not access memory for inactive elements.

## svst2[_f16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst2%5B_f16%5D

### Signature (source notation)

```c
void svst2[_f16](svbool_t pg, float16_t *base, svfloat16x2_t data);
```

### Description

Store two vectors into two-element tuples

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Store / Consecutive

- SME attributes: Not specified by source.

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
  "value": "void"
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
  "data": {
    "register": "{Zdata0.H, Zdata1.H}"
  }
}
```

### Result mapping

```json
[]
```

### Instruction mapping

When base has the form &array[index], this intrinsic can use:

```asm
ST2H {Zdata0.H, Zdata1.H}, Pg, [Xarray, Xindex, LSL #1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST2H--scalar-plus-scalar---Contiguous-store-two-halfword-structures-from-two-vectors--scalar-index--

The general implementation is:

```asm
ST2H {Zdata0.H, Zdata1.H}, Pg, [Xbase, #0, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST2H--scalar-plus-immediate---Contiguous-store-two-halfword-structures-from-two-vectors--immediate-index--

### Operation

Source operation ID: `SveOperation_svst2_bf16`

**Operation**



For each active element *i* and for each vector index *j*, store `data[j][i]` to `base[i * 2 + j]`. Do not access memory for inactive elements.

## svst2[_f32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst2%5B_f32%5D

### Signature (source notation)

```c
void svst2[_f32](svbool_t pg, float32_t *base, svfloat32x2_t data);
```

### Description

Store two vectors into two-element tuples

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Store / Consecutive

- SME attributes: Not specified by source.

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
  "value": "void"
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
  "data": {
    "register": "{Zdata0.S, Zdata1.S}"
  }
}
```

### Result mapping

```json
[]
```

### Instruction mapping

When base has the form &array[index], this intrinsic can use:

```asm
ST2W {Zdata0.S, Zdata1.S}, Pg, [Xarray, Xindex, LSL #2]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST2W--scalar-plus-scalar---Contiguous-store-two-word-structures-from-two-vectors--scalar-index--

The general implementation is:

```asm
ST2W {Zdata0.S, Zdata1.S}, Pg, [Xbase, #0, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST2W--scalar-plus-immediate---Contiguous-store-two-word-structures-from-two-vectors--immediate-index--

### Operation

Source operation ID: `SveOperation_svst2_bf16`

**Operation**



For each active element *i* and for each vector index *j*, store `data[j][i]` to `base[i * 2 + j]`. Do not access memory for inactive elements.

## svst2[_f64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst2%5B_f64%5D

### Signature (source notation)

```c
void svst2[_f64](svbool_t pg, float64_t *base, svfloat64x2_t data);
```

### Description

Store two vectors into two-element tuples

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Store / Consecutive

- SME attributes: Not specified by source.

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
  "value": "void"
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
  "data": {
    "register": "{Zdata0.D, Zdata1.D}"
  }
}
```

### Result mapping

```json
[]
```

### Instruction mapping

When base has the form &array[index], this intrinsic can use:

```asm
ST2D {Zdata0.D, Zdata1.D}, Pg, [Xarray, Xindex, LSL #3]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST2D--scalar-plus-scalar---Contiguous-store-two-doubleword-structures-from-two-vectors--scalar-index--

The general implementation is:

```asm
ST2D {Zdata0.D, Zdata1.D}, Pg, [Xbase, #0, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST2D--scalar-plus-immediate---Contiguous-store-two-doubleword-structures-from-two-vectors--immediate-index--

### Operation

Source operation ID: `SveOperation_svst2_bf16`

**Operation**



For each active element *i* and for each vector index *j*, store `data[j][i]` to `base[i * 2 + j]`. Do not access memory for inactive elements.

## svst2[_mf8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst2%5B_mf8%5D

### Signature (source notation)

```c
void svst2[_mf8](svbool_t pg, mfloat8_t *base, svmfloat8x2_t data);
```

### Description

Store two vectors into two-element tuples

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Store / Consecutive

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME
```

### Return type metadata

```json
{
  "return_base_type": "void",
  "element_bit_size": "8",
  "value": "void"
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
  "data": {
    "register": "{Zdata0.B, Zdata1.B}"
  }
}
```

### Result mapping

```json
[]
```

### Instruction mapping

When base has the form &array[index], this intrinsic can use:

```asm
ST2B {Zdata0.B, Zdata1.B}, Pg, [Xarray, Xindex]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST2B--scalar-plus-scalar---Contiguous-store-two-byte-structures-from-two-vectors--scalar-index--

The general implementation is:

```asm
ST2B {Zdata0.B, Zdata1.B}, Pg, [Xbase, #0, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST2B--scalar-plus-immediate---Contiguous-store-two-byte-structures-from-two-vectors--immediate-index--

### Operation

Source operation ID: `SveOperation_svst2_bf16`

**Operation**



For each active element *i* and for each vector index *j*, store `data[j][i]` to `base[i * 2 + j]`. Do not access memory for inactive elements.

## svst2[_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst2%5B_s16%5D

### Signature (source notation)

```c
void svst2[_s16](svbool_t pg, int16_t *base, svint16x2_t data);
```

### Description

Store two vectors into two-element tuples

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Store / Consecutive

- SME attributes: Not specified by source.

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
  "value": "void"
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
  "data": {
    "register": "{Zdata0.H, Zdata1.H}"
  }
}
```

### Result mapping

```json
[]
```

### Instruction mapping

When base has the form &array[index], this intrinsic can use:

```asm
ST2H {Zdata0.H, Zdata1.H}, Pg, [Xarray, Xindex, LSL #1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST2H--scalar-plus-scalar---Contiguous-store-two-halfword-structures-from-two-vectors--scalar-index--

The general implementation is:

```asm
ST2H {Zdata0.H, Zdata1.H}, Pg, [Xbase, #0, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST2H--scalar-plus-immediate---Contiguous-store-two-halfword-structures-from-two-vectors--immediate-index--

### Operation

Source operation ID: `SveOperation_svst2_bf16`

**Operation**



For each active element *i* and for each vector index *j*, store `data[j][i]` to `base[i * 2 + j]`. Do not access memory for inactive elements.

## svst2[_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst2%5B_s32%5D

### Signature (source notation)

```c
void svst2[_s32](svbool_t pg, int32_t *base, svint32x2_t data);
```

### Description

Store two vectors into two-element tuples

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Store / Consecutive

- SME attributes: Not specified by source.

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
  "value": "void"
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
  "data": {
    "register": "{Zdata0.S, Zdata1.S}"
  }
}
```

### Result mapping

```json
[]
```

### Instruction mapping

When base has the form &array[index], this intrinsic can use:

```asm
ST2W {Zdata0.S, Zdata1.S}, Pg, [Xarray, Xindex, LSL #2]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST2W--scalar-plus-scalar---Contiguous-store-two-word-structures-from-two-vectors--scalar-index--

The general implementation is:

```asm
ST2W {Zdata0.S, Zdata1.S}, Pg, [Xbase, #0, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST2W--scalar-plus-immediate---Contiguous-store-two-word-structures-from-two-vectors--immediate-index--

### Operation

Source operation ID: `SveOperation_svst2_bf16`

**Operation**



For each active element *i* and for each vector index *j*, store `data[j][i]` to `base[i * 2 + j]`. Do not access memory for inactive elements.

## svst2[_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst2%5B_s64%5D

### Signature (source notation)

```c
void svst2[_s64](svbool_t pg, int64_t *base, svint64x2_t data);
```

### Description

Store two vectors into two-element tuples

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Store / Consecutive

- SME attributes: Not specified by source.

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
  "value": "void"
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
  "data": {
    "register": "{Zdata0.D, Zdata1.D}"
  }
}
```

### Result mapping

```json
[]
```

### Instruction mapping

When base has the form &array[index], this intrinsic can use:

```asm
ST2D {Zdata0.D, Zdata1.D}, Pg, [Xarray, Xindex, LSL #3]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST2D--scalar-plus-scalar---Contiguous-store-two-doubleword-structures-from-two-vectors--scalar-index--

The general implementation is:

```asm
ST2D {Zdata0.D, Zdata1.D}, Pg, [Xbase, #0, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST2D--scalar-plus-immediate---Contiguous-store-two-doubleword-structures-from-two-vectors--immediate-index--

### Operation

Source operation ID: `SveOperation_svst2_bf16`

**Operation**



For each active element *i* and for each vector index *j*, store `data[j][i]` to `base[i * 2 + j]`. Do not access memory for inactive elements.

## svst2[_s8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst2%5B_s8%5D

### Signature (source notation)

```c
void svst2[_s8](svbool_t pg, int8_t *base, svint8x2_t data);
```

### Description

Store two vectors into two-element tuples

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Store / Consecutive

- SME attributes: Not specified by source.

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
  "value": "void"
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
  "data": {
    "register": "{Zdata0.B, Zdata1.B}"
  }
}
```

### Result mapping

```json
[]
```

### Instruction mapping

When base has the form &array[index], this intrinsic can use:

```asm
ST2B {Zdata0.B, Zdata1.B}, Pg, [Xarray, Xindex]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST2B--scalar-plus-scalar---Contiguous-store-two-byte-structures-from-two-vectors--scalar-index--

The general implementation is:

```asm
ST2B {Zdata0.B, Zdata1.B}, Pg, [Xbase, #0, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST2B--scalar-plus-immediate---Contiguous-store-two-byte-structures-from-two-vectors--immediate-index--

### Operation

Source operation ID: `SveOperation_svst2_bf16`

**Operation**



For each active element *i* and for each vector index *j*, store `data[j][i]` to `base[i * 2 + j]`. Do not access memory for inactive elements.

## svst2[_u16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst2%5B_u16%5D

### Signature (source notation)

```c
void svst2[_u16](svbool_t pg, uint16_t *base, svuint16x2_t data);
```

### Description

Store two vectors into two-element tuples

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Store / Consecutive

- SME attributes: Not specified by source.

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
  "value": "void"
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
  "data": {
    "register": "{Zdata0.H, Zdata1.H}"
  }
}
```

### Result mapping

```json
[]
```

### Instruction mapping

When base has the form &array[index], this intrinsic can use:

```asm
ST2H {Zdata0.H, Zdata1.H}, Pg, [Xarray, Xindex, LSL #1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST2H--scalar-plus-scalar---Contiguous-store-two-halfword-structures-from-two-vectors--scalar-index--

The general implementation is:

```asm
ST2H {Zdata0.H, Zdata1.H}, Pg, [Xbase, #0, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST2H--scalar-plus-immediate---Contiguous-store-two-halfword-structures-from-two-vectors--immediate-index--

### Operation

Source operation ID: `SveOperation_svst2_bf16`

**Operation**



For each active element *i* and for each vector index *j*, store `data[j][i]` to `base[i * 2 + j]`. Do not access memory for inactive elements.

## svst2[_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst2%5B_u32%5D

### Signature (source notation)

```c
void svst2[_u32](svbool_t pg, uint32_t *base, svuint32x2_t data);
```

### Description

Store two vectors into two-element tuples

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Store / Consecutive

- SME attributes: Not specified by source.

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
  "value": "void"
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
  "data": {
    "register": "{Zdata0.S, Zdata1.S}"
  }
}
```

### Result mapping

```json
[]
```

### Instruction mapping

When base has the form &array[index], this intrinsic can use:

```asm
ST2W {Zdata0.S, Zdata1.S}, Pg, [Xarray, Xindex, LSL #2]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST2W--scalar-plus-scalar---Contiguous-store-two-word-structures-from-two-vectors--scalar-index--

The general implementation is:

```asm
ST2W {Zdata0.S, Zdata1.S}, Pg, [Xbase, #0, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST2W--scalar-plus-immediate---Contiguous-store-two-word-structures-from-two-vectors--immediate-index--

### Operation

Source operation ID: `SveOperation_svst2_bf16`

**Operation**



For each active element *i* and for each vector index *j*, store `data[j][i]` to `base[i * 2 + j]`. Do not access memory for inactive elements.

## svst2[_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst2%5B_u64%5D

### Signature (source notation)

```c
void svst2[_u64](svbool_t pg, uint64_t *base, svuint64x2_t data);
```

### Description

Store two vectors into two-element tuples

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Store / Consecutive

- SME attributes: Not specified by source.

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
  "value": "void"
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
  "data": {
    "register": "{Zdata0.D, Zdata1.D}"
  }
}
```

### Result mapping

```json
[]
```

### Instruction mapping

When base has the form &array[index], this intrinsic can use:

```asm
ST2D {Zdata0.D, Zdata1.D}, Pg, [Xarray, Xindex, LSL #3]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST2D--scalar-plus-scalar---Contiguous-store-two-doubleword-structures-from-two-vectors--scalar-index--

The general implementation is:

```asm
ST2D {Zdata0.D, Zdata1.D}, Pg, [Xbase, #0, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST2D--scalar-plus-immediate---Contiguous-store-two-doubleword-structures-from-two-vectors--immediate-index--

### Operation

Source operation ID: `SveOperation_svst2_bf16`

**Operation**



For each active element *i* and for each vector index *j*, store `data[j][i]` to `base[i * 2 + j]`. Do not access memory for inactive elements.

## svst2[_u8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst2%5B_u8%5D

### Signature (source notation)

```c
void svst2[_u8](svbool_t pg, uint8_t *base, svuint8x2_t data);
```

### Description

Store two vectors into two-element tuples

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Store / Consecutive

- SME attributes: Not specified by source.

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
  "value": "void"
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
  "data": {
    "register": "{Zdata0.B, Zdata1.B}"
  }
}
```

### Result mapping

```json
[]
```

### Instruction mapping

When base has the form &array[index], this intrinsic can use:

```asm
ST2B {Zdata0.B, Zdata1.B}, Pg, [Xarray, Xindex]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST2B--scalar-plus-scalar---Contiguous-store-two-byte-structures-from-two-vectors--scalar-index--

The general implementation is:

```asm
ST2B {Zdata0.B, Zdata1.B}, Pg, [Xbase, #0, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST2B--scalar-plus-immediate---Contiguous-store-two-byte-structures-from-two-vectors--immediate-index--

### Operation

Source operation ID: `SveOperation_svst2_bf16`

**Operation**



For each active element *i* and for each vector index *j*, store `data[j][i]` to `base[i * 2 + j]`. Do not access memory for inactive elements.

## svst2_vnum[_bf16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst2_vnum%5B_bf16%5D

### Signature (source notation)

```c
void svst2_vnum[_bf16](svbool_t pg, bfloat16_t *base, int64_t vnum, svbfloat16x2_t data);
```

### Description

Store two vectors into two-element tuples

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Store / Consecutive

- SME attributes: Not specified by source.

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
  "value": "void"
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
  "data": {
    "register": "{Zdata0.H, Zdata1.H}"
  },
  "vnum * svcnth()": {
    "register": "Xindex"
  }
}
```

### Result mapping

```json
[]
```

### Instruction mapping

When vnum is a multiple of 2 in the range [-16, 14], this intrinsic can use:

```asm
ST2H {Zdata0.H, Zdata1.H}, Pg, [Xbase, #vnum, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST2H--scalar-plus-immediate---Contiguous-store-two-halfword-structures-from-two-vectors--immediate-index--

The general implementation is:

```asm
ST2H {Zdata0.H, Zdata1.H}, Pg, [Xbase, Xindex, LSL #1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST2H--scalar-plus-scalar---Contiguous-store-two-halfword-structures-from-two-vectors--scalar-index--

### Operation

Source operation ID: `SveOperation_svst2_vnum_bf16`

**Operation**



For each active element *i* and for each vector index *j*, store `data[j][i]` to `base[n * vnum + i * 2 + j]`, where *n* is the number of elements in `data[j]`. Do not access memory for inactive elements.

## svst2_vnum[_f16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst2_vnum%5B_f16%5D

### Signature (source notation)

```c
void svst2_vnum[_f16](svbool_t pg, float16_t *base, int64_t vnum, svfloat16x2_t data);
```

### Description

Store two vectors into two-element tuples

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Store / Consecutive

- SME attributes: Not specified by source.

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
  "value": "void"
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
  "data": {
    "register": "{Zdata0.H, Zdata1.H}"
  },
  "vnum * svcnth()": {
    "register": "Xindex"
  }
}
```

### Result mapping

```json
[]
```

### Instruction mapping

When vnum is a multiple of 2 in the range [-16, 14], this intrinsic can use:

```asm
ST2H {Zdata0.H, Zdata1.H}, Pg, [Xbase, #vnum, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST2H--scalar-plus-immediate---Contiguous-store-two-halfword-structures-from-two-vectors--immediate-index--

The general implementation is:

```asm
ST2H {Zdata0.H, Zdata1.H}, Pg, [Xbase, Xindex, LSL #1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST2H--scalar-plus-scalar---Contiguous-store-two-halfword-structures-from-two-vectors--scalar-index--

### Operation

Source operation ID: `SveOperation_svst2_vnum_bf16`

**Operation**



For each active element *i* and for each vector index *j*, store `data[j][i]` to `base[n * vnum + i * 2 + j]`, where *n* is the number of elements in `data[j]`. Do not access memory for inactive elements.

## svst2_vnum[_f32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst2_vnum%5B_f32%5D

### Signature (source notation)

```c
void svst2_vnum[_f32](svbool_t pg, float32_t *base, int64_t vnum, svfloat32x2_t data);
```

### Description

Store two vectors into two-element tuples

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Store / Consecutive

- SME attributes: Not specified by source.

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
  "value": "void"
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
  "data": {
    "register": "{Zdata0.S, Zdata1.S}"
  },
  "vnum * svcntw()": {
    "register": "Xindex"
  }
}
```

### Result mapping

```json
[]
```

### Instruction mapping

When vnum is a multiple of 2 in the range [-16, 14], this intrinsic can use:

```asm
ST2W {Zdata0.S, Zdata1.S}, Pg, [Xbase, #vnum, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST2W--scalar-plus-immediate---Contiguous-store-two-word-structures-from-two-vectors--immediate-index--

The general implementation is:

```asm
ST2W {Zdata0.S, Zdata1.S}, Pg, [Xbase, Xindex, LSL #2]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST2W--scalar-plus-scalar---Contiguous-store-two-word-structures-from-two-vectors--scalar-index--

### Operation

Source operation ID: `SveOperation_svst2_vnum_bf16`

**Operation**



For each active element *i* and for each vector index *j*, store `data[j][i]` to `base[n * vnum + i * 2 + j]`, where *n* is the number of elements in `data[j]`. Do not access memory for inactive elements.

## svst2_vnum[_f64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst2_vnum%5B_f64%5D

### Signature (source notation)

```c
void svst2_vnum[_f64](svbool_t pg, float64_t *base, int64_t vnum, svfloat64x2_t data);
```

### Description

Store two vectors into two-element tuples

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Store / Consecutive

- SME attributes: Not specified by source.

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
  "value": "void"
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
  "data": {
    "register": "{Zdata0.D, Zdata1.D}"
  },
  "vnum * svcntd()": {
    "register": "Xindex"
  }
}
```

### Result mapping

```json
[]
```

### Instruction mapping

When vnum is a multiple of 2 in the range [-16, 14], this intrinsic can use:

```asm
ST2D {Zdata0.D, Zdata1.D}, Pg, [Xbase, #vnum, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST2D--scalar-plus-immediate---Contiguous-store-two-doubleword-structures-from-two-vectors--immediate-index--

The general implementation is:

```asm
ST2D {Zdata0.D, Zdata1.D}, Pg, [Xbase, Xindex, LSL #3]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST2D--scalar-plus-scalar---Contiguous-store-two-doubleword-structures-from-two-vectors--scalar-index--

### Operation

Source operation ID: `SveOperation_svst2_vnum_bf16`

**Operation**



For each active element *i* and for each vector index *j*, store `data[j][i]` to `base[n * vnum + i * 2 + j]`, where *n* is the number of elements in `data[j]`. Do not access memory for inactive elements.

## svst2_vnum[_mf8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst2_vnum%5B_mf8%5D

### Signature (source notation)

```c
void svst2_vnum[_mf8](svbool_t pg, mfloat8_t *base, int64_t vnum, svmfloat8x2_t data);
```

### Description

Store two vectors into two-element tuples

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Store / Consecutive

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME
```

### Return type metadata

```json
{
  "return_base_type": "void",
  "element_bit_size": "8",
  "value": "void"
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
  "data": {
    "register": "{Zdata0.B, Zdata1.B}"
  },
  "vnum * svcntb()": {
    "register": "Xindex"
  }
}
```

### Result mapping

```json
[]
```

### Instruction mapping

When vnum is a multiple of 2 in the range [-16, 14], this intrinsic can use:

```asm
ST2B {Zdata0.B, Zdata1.B}, Pg, [Xbase, #vnum, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST2B--scalar-plus-immediate---Contiguous-store-two-byte-structures-from-two-vectors--immediate-index--

The general implementation is:

```asm
ST2B {Zdata0.B, Zdata1.B}, Pg, [Xbase, Xindex]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST2B--scalar-plus-scalar---Contiguous-store-two-byte-structures-from-two-vectors--scalar-index--

### Operation

Source operation ID: `SveOperation_svst2_vnum_bf16`

**Operation**



For each active element *i* and for each vector index *j*, store `data[j][i]` to `base[n * vnum + i * 2 + j]`, where *n* is the number of elements in `data[j]`. Do not access memory for inactive elements.

## svst2_vnum[_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst2_vnum%5B_s16%5D

### Signature (source notation)

```c
void svst2_vnum[_s16](svbool_t pg, int16_t *base, int64_t vnum, svint16x2_t data);
```

### Description

Store two vectors into two-element tuples

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Store / Consecutive

- SME attributes: Not specified by source.

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
  "value": "void"
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
  "data": {
    "register": "{Zdata0.H, Zdata1.H}"
  },
  "vnum * svcnth()": {
    "register": "Xindex"
  }
}
```

### Result mapping

```json
[]
```

### Instruction mapping

When vnum is a multiple of 2 in the range [-16, 14], this intrinsic can use:

```asm
ST2H {Zdata0.H, Zdata1.H}, Pg, [Xbase, #vnum, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST2H--scalar-plus-immediate---Contiguous-store-two-halfword-structures-from-two-vectors--immediate-index--

The general implementation is:

```asm
ST2H {Zdata0.H, Zdata1.H}, Pg, [Xbase, Xindex, LSL #1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST2H--scalar-plus-scalar---Contiguous-store-two-halfword-structures-from-two-vectors--scalar-index--

### Operation

Source operation ID: `SveOperation_svst2_vnum_bf16`

**Operation**



For each active element *i* and for each vector index *j*, store `data[j][i]` to `base[n * vnum + i * 2 + j]`, where *n* is the number of elements in `data[j]`. Do not access memory for inactive elements.

## svst2_vnum[_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst2_vnum%5B_s32%5D

### Signature (source notation)

```c
void svst2_vnum[_s32](svbool_t pg, int32_t *base, int64_t vnum, svint32x2_t data);
```

### Description

Store two vectors into two-element tuples

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Store / Consecutive

- SME attributes: Not specified by source.

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
  "value": "void"
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
  "data": {
    "register": "{Zdata0.S, Zdata1.S}"
  },
  "vnum * svcntw()": {
    "register": "Xindex"
  }
}
```

### Result mapping

```json
[]
```

### Instruction mapping

When vnum is a multiple of 2 in the range [-16, 14], this intrinsic can use:

```asm
ST2W {Zdata0.S, Zdata1.S}, Pg, [Xbase, #vnum, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST2W--scalar-plus-immediate---Contiguous-store-two-word-structures-from-two-vectors--immediate-index--

The general implementation is:

```asm
ST2W {Zdata0.S, Zdata1.S}, Pg, [Xbase, Xindex, LSL #2]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST2W--scalar-plus-scalar---Contiguous-store-two-word-structures-from-two-vectors--scalar-index--

### Operation

Source operation ID: `SveOperation_svst2_vnum_bf16`

**Operation**



For each active element *i* and for each vector index *j*, store `data[j][i]` to `base[n * vnum + i * 2 + j]`, where *n* is the number of elements in `data[j]`. Do not access memory for inactive elements.

## svst2_vnum[_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst2_vnum%5B_s64%5D

### Signature (source notation)

```c
void svst2_vnum[_s64](svbool_t pg, int64_t *base, int64_t vnum, svint64x2_t data);
```

### Description

Store two vectors into two-element tuples

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Store / Consecutive

- SME attributes: Not specified by source.

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
  "value": "void"
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
  "data": {
    "register": "{Zdata0.D, Zdata1.D}"
  },
  "vnum * svcntd()": {
    "register": "Xindex"
  }
}
```

### Result mapping

```json
[]
```

### Instruction mapping

When vnum is a multiple of 2 in the range [-16, 14], this intrinsic can use:

```asm
ST2D {Zdata0.D, Zdata1.D}, Pg, [Xbase, #vnum, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST2D--scalar-plus-immediate---Contiguous-store-two-doubleword-structures-from-two-vectors--immediate-index--

The general implementation is:

```asm
ST2D {Zdata0.D, Zdata1.D}, Pg, [Xbase, Xindex, LSL #3]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST2D--scalar-plus-scalar---Contiguous-store-two-doubleword-structures-from-two-vectors--scalar-index--

### Operation

Source operation ID: `SveOperation_svst2_vnum_bf16`

**Operation**



For each active element *i* and for each vector index *j*, store `data[j][i]` to `base[n * vnum + i * 2 + j]`, where *n* is the number of elements in `data[j]`. Do not access memory for inactive elements.

## svst2_vnum[_s8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst2_vnum%5B_s8%5D

### Signature (source notation)

```c
void svst2_vnum[_s8](svbool_t pg, int8_t *base, int64_t vnum, svint8x2_t data);
```

### Description

Store two vectors into two-element tuples

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Store / Consecutive

- SME attributes: Not specified by source.

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
  "value": "void"
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
  "data": {
    "register": "{Zdata0.B, Zdata1.B}"
  },
  "vnum * svcntb()": {
    "register": "Xindex"
  }
}
```

### Result mapping

```json
[]
```

### Instruction mapping

When vnum is a multiple of 2 in the range [-16, 14], this intrinsic can use:

```asm
ST2B {Zdata0.B, Zdata1.B}, Pg, [Xbase, #vnum, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST2B--scalar-plus-immediate---Contiguous-store-two-byte-structures-from-two-vectors--immediate-index--

The general implementation is:

```asm
ST2B {Zdata0.B, Zdata1.B}, Pg, [Xbase, Xindex]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST2B--scalar-plus-scalar---Contiguous-store-two-byte-structures-from-two-vectors--scalar-index--

### Operation

Source operation ID: `SveOperation_svst2_vnum_bf16`

**Operation**



For each active element *i* and for each vector index *j*, store `data[j][i]` to `base[n * vnum + i * 2 + j]`, where *n* is the number of elements in `data[j]`. Do not access memory for inactive elements.

## svst2_vnum[_u16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst2_vnum%5B_u16%5D

### Signature (source notation)

```c
void svst2_vnum[_u16](svbool_t pg, uint16_t *base, int64_t vnum, svuint16x2_t data);
```

### Description

Store two vectors into two-element tuples

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Store / Consecutive

- SME attributes: Not specified by source.

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
  "value": "void"
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
  "data": {
    "register": "{Zdata0.H, Zdata1.H}"
  },
  "vnum * svcnth()": {
    "register": "Xindex"
  }
}
```

### Result mapping

```json
[]
```

### Instruction mapping

When vnum is a multiple of 2 in the range [-16, 14], this intrinsic can use:

```asm
ST2H {Zdata0.H, Zdata1.H}, Pg, [Xbase, #vnum, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST2H--scalar-plus-immediate---Contiguous-store-two-halfword-structures-from-two-vectors--immediate-index--

The general implementation is:

```asm
ST2H {Zdata0.H, Zdata1.H}, Pg, [Xbase, Xindex, LSL #1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST2H--scalar-plus-scalar---Contiguous-store-two-halfword-structures-from-two-vectors--scalar-index--

### Operation

Source operation ID: `SveOperation_svst2_vnum_bf16`

**Operation**



For each active element *i* and for each vector index *j*, store `data[j][i]` to `base[n * vnum + i * 2 + j]`, where *n* is the number of elements in `data[j]`. Do not access memory for inactive elements.

## svst2_vnum[_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst2_vnum%5B_u32%5D

### Signature (source notation)

```c
void svst2_vnum[_u32](svbool_t pg, uint32_t *base, int64_t vnum, svuint32x2_t data);
```

### Description

Store two vectors into two-element tuples

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Store / Consecutive

- SME attributes: Not specified by source.

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
  "value": "void"
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
  "data": {
    "register": "{Zdata0.S, Zdata1.S}"
  },
  "vnum * svcntw()": {
    "register": "Xindex"
  }
}
```

### Result mapping

```json
[]
```

### Instruction mapping

When vnum is a multiple of 2 in the range [-16, 14], this intrinsic can use:

```asm
ST2W {Zdata0.S, Zdata1.S}, Pg, [Xbase, #vnum, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST2W--scalar-plus-immediate---Contiguous-store-two-word-structures-from-two-vectors--immediate-index--

The general implementation is:

```asm
ST2W {Zdata0.S, Zdata1.S}, Pg, [Xbase, Xindex, LSL #2]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST2W--scalar-plus-scalar---Contiguous-store-two-word-structures-from-two-vectors--scalar-index--

### Operation

Source operation ID: `SveOperation_svst2_vnum_bf16`

**Operation**



For each active element *i* and for each vector index *j*, store `data[j][i]` to `base[n * vnum + i * 2 + j]`, where *n* is the number of elements in `data[j]`. Do not access memory for inactive elements.

## svst2_vnum[_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst2_vnum%5B_u64%5D

### Signature (source notation)

```c
void svst2_vnum[_u64](svbool_t pg, uint64_t *base, int64_t vnum, svuint64x2_t data);
```

### Description

Store two vectors into two-element tuples

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Store / Consecutive

- SME attributes: Not specified by source.

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
  "value": "void"
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
  "data": {
    "register": "{Zdata0.D, Zdata1.D}"
  },
  "vnum * svcntd()": {
    "register": "Xindex"
  }
}
```

### Result mapping

```json
[]
```

### Instruction mapping

When vnum is a multiple of 2 in the range [-16, 14], this intrinsic can use:

```asm
ST2D {Zdata0.D, Zdata1.D}, Pg, [Xbase, #vnum, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST2D--scalar-plus-immediate---Contiguous-store-two-doubleword-structures-from-two-vectors--immediate-index--

The general implementation is:

```asm
ST2D {Zdata0.D, Zdata1.D}, Pg, [Xbase, Xindex, LSL #3]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST2D--scalar-plus-scalar---Contiguous-store-two-doubleword-structures-from-two-vectors--scalar-index--

### Operation

Source operation ID: `SveOperation_svst2_vnum_bf16`

**Operation**



For each active element *i* and for each vector index *j*, store `data[j][i]` to `base[n * vnum + i * 2 + j]`, where *n* is the number of elements in `data[j]`. Do not access memory for inactive elements.

## svst2_vnum[_u8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst2_vnum%5B_u8%5D

### Signature (source notation)

```c
void svst2_vnum[_u8](svbool_t pg, uint8_t *base, int64_t vnum, svuint8x2_t data);
```

### Description

Store two vectors into two-element tuples

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Store / Consecutive

- SME attributes: Not specified by source.

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
  "value": "void"
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
  "data": {
    "register": "{Zdata0.B, Zdata1.B}"
  },
  "vnum * svcntb()": {
    "register": "Xindex"
  }
}
```

### Result mapping

```json
[]
```

### Instruction mapping

When vnum is a multiple of 2 in the range [-16, 14], this intrinsic can use:

```asm
ST2B {Zdata0.B, Zdata1.B}, Pg, [Xbase, #vnum, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST2B--scalar-plus-immediate---Contiguous-store-two-byte-structures-from-two-vectors--immediate-index--

The general implementation is:

```asm
ST2B {Zdata0.B, Zdata1.B}, Pg, [Xbase, Xindex]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST2B--scalar-plus-scalar---Contiguous-store-two-byte-structures-from-two-vectors--scalar-index--

### Operation

Source operation ID: `SveOperation_svst2_vnum_bf16`

**Operation**



For each active element *i* and for each vector index *j*, store `data[j][i]` to `base[n * vnum + i * 2 + j]`, where *n* is the number of elements in `data[j]`. Do not access memory for inactive elements.

## svst2q[_bf16]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst2q%5B_bf16%5D

### Signature (source notation)

```c
void svst2q[_bf16](svbool_t pg, bfloat16_t const * rn, svbfloat16x2_t zt);
```

### Description

Contiguous store two-quadword structures from two vectors (immediate index)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Store / Consecutive

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p1)|FEAT_SME2p1
```

### Return type metadata

```json
{
  "return_base_type": "void",
  "element_bit_size": "16",
  "value": "void"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Preg1"
  },
  "rn": {
    "register": "Xreg1"
  },
  "zt": {
    "Z multi-vector": "{ Zreg1.Q, Zreg2.Q }"
  }
}
```

### Result mapping

```json
[]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
ST2Q { Zreg1.Q, Zreg2.Q }, Preg1, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/ST2Q--scalar-plus-immediate---Contiguous-store-two-quadword-structures-from-two-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svst2q[_f16]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst2q%5B_f16%5D

### Signature (source notation)

```c
void svst2q[_f16](svbool_t pg, float16_t const * rn, svfloat16x2_t zt);
```

### Description

Contiguous store two-quadword structures from two vectors (immediate index)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Store / Consecutive

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p1)|FEAT_SME2p1
```

### Return type metadata

```json
{
  "return_base_type": "void",
  "element_bit_size": "16",
  "value": "void"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Preg1"
  },
  "rn": {
    "register": "Xreg1"
  },
  "zt": {
    "Z multi-vector": "{ Zreg1.Q, Zreg2.Q }"
  }
}
```

### Result mapping

```json
[]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
ST2Q { Zreg1.Q, Zreg2.Q }, Preg1, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/ST2Q--scalar-plus-immediate---Contiguous-store-two-quadword-structures-from-two-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

