# SME / Load / Consecutive — Part 4

## svld2[_mf8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld2%5B_mf8%5D

### Signature (source notation)

```c
svmfloat8x2_t svld2[_mf8](svbool_t pg, const mfloat8_t *base);
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
  "return_base_type": "mfloat8",
  "element_bit_size": "8",
  "value": "svmfloat8x2_t"
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
    "{Zresult0.B, Zresult1.B}": "result"
  }
]
```

### Instruction mapping

When base has the form &array[index], this intrinsic can use:

```asm
LD2B {Zresult0.B, Zresult1.B}, Pg/Z, [Xarray, Xindex]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD2B--scalar-plus-scalar---Contiguous-load-two-byte-structures-to-two-vectors--scalar-index--

The general implementation is:

```asm
LD2B {Zresult0.B, Zresult1.B}, Pg/Z, [Xbase, #0, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD2B--scalar-plus-immediate---Contiguous-load-two-byte-structures-to-two-vectors--immediate-index--

### Operation

Source operation ID: `SveOperation_svld2_bf16`

**Operation**



Return a tuple of two vectors in which each active element *i* of vector *j* contains `base[i * 2 + j]` and in which all other elements are zero.  Do not access memory for inactive elements.

## svld2[_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld2%5B_s16%5D

### Signature (source notation)

```c
svint16x2_t svld2[_s16](svbool_t pg, const int16_t *base);
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
  "return_base_type": "int",
  "element_bit_size": "16",
  "value": "svint16x2_t"
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

## svld2[_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld2%5B_s32%5D

### Signature (source notation)

```c
svint32x2_t svld2[_s32](svbool_t pg, const int32_t *base);
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
  "return_base_type": "int",
  "element_bit_size": "32",
  "value": "svint32x2_t"
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

## svld2[_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld2%5B_s64%5D

### Signature (source notation)

```c
svint64x2_t svld2[_s64](svbool_t pg, const int64_t *base);
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
  "return_base_type": "int",
  "element_bit_size": "64",
  "value": "svint64x2_t"
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

## svld2[_s8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld2%5B_s8%5D

### Signature (source notation)

```c
svint8x2_t svld2[_s8](svbool_t pg, const int8_t *base);
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
  "return_base_type": "int",
  "element_bit_size": "8",
  "value": "svint8x2_t"
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
    "{Zresult0.B, Zresult1.B}": "result"
  }
]
```

### Instruction mapping

When base has the form &array[index], this intrinsic can use:

```asm
LD2B {Zresult0.B, Zresult1.B}, Pg/Z, [Xarray, Xindex]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD2B--scalar-plus-scalar---Contiguous-load-two-byte-structures-to-two-vectors--scalar-index--

The general implementation is:

```asm
LD2B {Zresult0.B, Zresult1.B}, Pg/Z, [Xbase, #0, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD2B--scalar-plus-immediate---Contiguous-load-two-byte-structures-to-two-vectors--immediate-index--

### Operation

Source operation ID: `SveOperation_svld2_bf16`

**Operation**



Return a tuple of two vectors in which each active element *i* of vector *j* contains `base[i * 2 + j]` and in which all other elements are zero.  Do not access memory for inactive elements.

## svld2[_u16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld2%5B_u16%5D

### Signature (source notation)

```c
svuint16x2_t svld2[_u16](svbool_t pg, const uint16_t *base);
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
  "return_base_type": "uint",
  "element_bit_size": "16",
  "value": "svuint16x2_t"
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

## svld2[_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld2%5B_u32%5D

### Signature (source notation)

```c
svuint32x2_t svld2[_u32](svbool_t pg, const uint32_t *base);
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
  "return_base_type": "uint",
  "element_bit_size": "32",
  "value": "svuint32x2_t"
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

## svld2[_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld2%5B_u64%5D

### Signature (source notation)

```c
svuint64x2_t svld2[_u64](svbool_t pg, const uint64_t *base);
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
  "return_base_type": "uint",
  "element_bit_size": "64",
  "value": "svuint64x2_t"
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

## svld2[_u8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld2%5B_u8%5D

### Signature (source notation)

```c
svuint8x2_t svld2[_u8](svbool_t pg, const uint8_t *base);
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
  "return_base_type": "uint",
  "element_bit_size": "8",
  "value": "svuint8x2_t"
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
    "{Zresult0.B, Zresult1.B}": "result"
  }
]
```

### Instruction mapping

When base has the form &array[index], this intrinsic can use:

```asm
LD2B {Zresult0.B, Zresult1.B}, Pg/Z, [Xarray, Xindex]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD2B--scalar-plus-scalar---Contiguous-load-two-byte-structures-to-two-vectors--scalar-index--

The general implementation is:

```asm
LD2B {Zresult0.B, Zresult1.B}, Pg/Z, [Xbase, #0, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD2B--scalar-plus-immediate---Contiguous-load-two-byte-structures-to-two-vectors--immediate-index--

### Operation

Source operation ID: `SveOperation_svld2_bf16`

**Operation**



Return a tuple of two vectors in which each active element *i* of vector *j* contains `base[i * 2 + j]` and in which all other elements are zero.  Do not access memory for inactive elements.

## svld2_vnum[_bf16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld2_vnum%5B_bf16%5D

### Signature (source notation)

```c
svbfloat16x2_t svld2_vnum[_bf16](svbool_t pg, const bfloat16_t *base, int64_t vnum);
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
    "{Zresult0.H, Zresult1.H}": "result"
  }
]
```

### Instruction mapping

When vnum is a multiple of 2 in the range [-16, 14], this intrinsic can use:

```asm
LD2H {Zresult0.H, Zresult1.H}, Pg/Z, [Xbase, #vnum, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD2H--scalar-plus-immediate---Contiguous-load-two-halfword-structures-to-two-vectors--immediate-index--

The general implementation is:

```asm
LD2H {Zresult0.H, Zresult1.H}, Pg/Z, [Xbase, Xindex, LSL #1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD2H--scalar-plus-scalar---Contiguous-load-two-halfword-structures-to-two-vectors--scalar-index--

### Operation

Source operation ID: `SveOperation_svld2_vnum_bf16`

**Operation**



Return a tuple of two *n*-element vectors in which each active element *i* of vector *j* contains `base[n * vnum + i * 2 + j]` and in which all other elements are zero.  Do not access memory for inactive elements.

## svld2_vnum[_f16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld2_vnum%5B_f16%5D

### Signature (source notation)

```c
svfloat16x2_t svld2_vnum[_f16](svbool_t pg, const float16_t *base, int64_t vnum);
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
    "{Zresult0.H, Zresult1.H}": "result"
  }
]
```

### Instruction mapping

When vnum is a multiple of 2 in the range [-16, 14], this intrinsic can use:

```asm
LD2H {Zresult0.H, Zresult1.H}, Pg/Z, [Xbase, #vnum, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD2H--scalar-plus-immediate---Contiguous-load-two-halfword-structures-to-two-vectors--immediate-index--

The general implementation is:

```asm
LD2H {Zresult0.H, Zresult1.H}, Pg/Z, [Xbase, Xindex, LSL #1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD2H--scalar-plus-scalar---Contiguous-load-two-halfword-structures-to-two-vectors--scalar-index--

### Operation

Source operation ID: `SveOperation_svld2_vnum_bf16`

**Operation**



Return a tuple of two *n*-element vectors in which each active element *i* of vector *j* contains `base[n * vnum + i * 2 + j]` and in which all other elements are zero.  Do not access memory for inactive elements.

## svld2_vnum[_f32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld2_vnum%5B_f32%5D

### Signature (source notation)

```c
svfloat32x2_t svld2_vnum[_f32](svbool_t pg, const float32_t *base, int64_t vnum);
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
    "{Zresult0.S, Zresult1.S}": "result"
  }
]
```

### Instruction mapping

When vnum is a multiple of 2 in the range [-16, 14], this intrinsic can use:

```asm
LD2W {Zresult0.S, Zresult1.S}, Pg/Z, [Xbase, #vnum, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD2W--scalar-plus-immediate---Contiguous-load-two-word-structures-to-two-vectors--immediate-index--

The general implementation is:

```asm
LD2W {Zresult0.S, Zresult1.S}, Pg/Z, [Xbase, Xindex, LSL #2]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD2W--scalar-plus-scalar---Contiguous-load-two-word-structures-to-two-vectors--scalar-index--

### Operation

Source operation ID: `SveOperation_svld2_vnum_bf16`

**Operation**



Return a tuple of two *n*-element vectors in which each active element *i* of vector *j* contains `base[n * vnum + i * 2 + j]` and in which all other elements are zero.  Do not access memory for inactive elements.

## svld2_vnum[_f64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld2_vnum%5B_f64%5D

### Signature (source notation)

```c
svfloat64x2_t svld2_vnum[_f64](svbool_t pg, const float64_t *base, int64_t vnum);
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
    "{Zresult0.D, Zresult1.D}": "result"
  }
]
```

### Instruction mapping

When vnum is a multiple of 2 in the range [-16, 14], this intrinsic can use:

```asm
LD2D {Zresult0.D, Zresult1.D}, Pg/Z, [Xbase, #vnum, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD2D--scalar-plus-immediate---Contiguous-load-two-doubleword-structures-to-two-vectors--immediate-index--

The general implementation is:

```asm
LD2D {Zresult0.D, Zresult1.D}, Pg/Z, [Xbase, Xindex, LSL #3]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD2D--scalar-plus-scalar---Contiguous-load-two-doubleword-structures-to-two-vectors--scalar-index--

### Operation

Source operation ID: `SveOperation_svld2_vnum_bf16`

**Operation**



Return a tuple of two *n*-element vectors in which each active element *i* of vector *j* contains `base[n * vnum + i * 2 + j]` and in which all other elements are zero.  Do not access memory for inactive elements.

## svld2_vnum[_mf8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld2_vnum%5B_mf8%5D

### Signature (source notation)

```c
svmfloat8x2_t svld2_vnum[_mf8](svbool_t pg, const mfloat8_t *base, int64_t vnum);
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
  "return_base_type": "mfloat8",
  "element_bit_size": "8",
  "value": "svmfloat8x2_t"
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
  "vnum * svcntb()": {
    "register": "Xindex"
  }
}
```

### Result mapping

```json
[
  {
    "{Zresult0.B, Zresult1.B}": "result"
  }
]
```

### Instruction mapping

When vnum is a multiple of 2 in the range [-16, 14], this intrinsic can use:

```asm
LD2B {Zresult0.B, Zresult1.B}, Pg/Z, [Xbase, #vnum, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD2B--scalar-plus-immediate---Contiguous-load-two-byte-structures-to-two-vectors--immediate-index--

The general implementation is:

```asm
LD2B {Zresult0.B, Zresult1.B}, Pg/Z, [Xbase, Xindex]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD2B--scalar-plus-scalar---Contiguous-load-two-byte-structures-to-two-vectors--scalar-index--

### Operation

Source operation ID: `SveOperation_svld2_vnum_bf16`

**Operation**



Return a tuple of two *n*-element vectors in which each active element *i* of vector *j* contains `base[n * vnum + i * 2 + j]` and in which all other elements are zero.  Do not access memory for inactive elements.

## svld2_vnum[_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld2_vnum%5B_s16%5D

### Signature (source notation)

```c
svint16x2_t svld2_vnum[_s16](svbool_t pg, const int16_t *base, int64_t vnum);
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
  "return_base_type": "int",
  "element_bit_size": "16",
  "value": "svint16x2_t"
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
    "{Zresult0.H, Zresult1.H}": "result"
  }
]
```

### Instruction mapping

When vnum is a multiple of 2 in the range [-16, 14], this intrinsic can use:

```asm
LD2H {Zresult0.H, Zresult1.H}, Pg/Z, [Xbase, #vnum, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD2H--scalar-plus-immediate---Contiguous-load-two-halfword-structures-to-two-vectors--immediate-index--

The general implementation is:

```asm
LD2H {Zresult0.H, Zresult1.H}, Pg/Z, [Xbase, Xindex, LSL #1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD2H--scalar-plus-scalar---Contiguous-load-two-halfword-structures-to-two-vectors--scalar-index--

### Operation

Source operation ID: `SveOperation_svld2_vnum_bf16`

**Operation**



Return a tuple of two *n*-element vectors in which each active element *i* of vector *j* contains `base[n * vnum + i * 2 + j]` and in which all other elements are zero.  Do not access memory for inactive elements.

## svld2_vnum[_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld2_vnum%5B_s32%5D

### Signature (source notation)

```c
svint32x2_t svld2_vnum[_s32](svbool_t pg, const int32_t *base, int64_t vnum);
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
  "return_base_type": "int",
  "element_bit_size": "32",
  "value": "svint32x2_t"
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
    "{Zresult0.S, Zresult1.S}": "result"
  }
]
```

### Instruction mapping

When vnum is a multiple of 2 in the range [-16, 14], this intrinsic can use:

```asm
LD2W {Zresult0.S, Zresult1.S}, Pg/Z, [Xbase, #vnum, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD2W--scalar-plus-immediate---Contiguous-load-two-word-structures-to-two-vectors--immediate-index--

The general implementation is:

```asm
LD2W {Zresult0.S, Zresult1.S}, Pg/Z, [Xbase, Xindex, LSL #2]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD2W--scalar-plus-scalar---Contiguous-load-two-word-structures-to-two-vectors--scalar-index--

### Operation

Source operation ID: `SveOperation_svld2_vnum_bf16`

**Operation**



Return a tuple of two *n*-element vectors in which each active element *i* of vector *j* contains `base[n * vnum + i * 2 + j]` and in which all other elements are zero.  Do not access memory for inactive elements.

## svld2_vnum[_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld2_vnum%5B_s64%5D

### Signature (source notation)

```c
svint64x2_t svld2_vnum[_s64](svbool_t pg, const int64_t *base, int64_t vnum);
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
  "return_base_type": "int",
  "element_bit_size": "64",
  "value": "svint64x2_t"
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
    "{Zresult0.D, Zresult1.D}": "result"
  }
]
```

### Instruction mapping

When vnum is a multiple of 2 in the range [-16, 14], this intrinsic can use:

```asm
LD2D {Zresult0.D, Zresult1.D}, Pg/Z, [Xbase, #vnum, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD2D--scalar-plus-immediate---Contiguous-load-two-doubleword-structures-to-two-vectors--immediate-index--

The general implementation is:

```asm
LD2D {Zresult0.D, Zresult1.D}, Pg/Z, [Xbase, Xindex, LSL #3]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD2D--scalar-plus-scalar---Contiguous-load-two-doubleword-structures-to-two-vectors--scalar-index--

### Operation

Source operation ID: `SveOperation_svld2_vnum_bf16`

**Operation**



Return a tuple of two *n*-element vectors in which each active element *i* of vector *j* contains `base[n * vnum + i * 2 + j]` and in which all other elements are zero.  Do not access memory for inactive elements.

## svld2_vnum[_s8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld2_vnum%5B_s8%5D

### Signature (source notation)

```c
svint8x2_t svld2_vnum[_s8](svbool_t pg, const int8_t *base, int64_t vnum);
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
  "return_base_type": "int",
  "element_bit_size": "8",
  "value": "svint8x2_t"
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
  "vnum * svcntb()": {
    "register": "Xindex"
  }
}
```

### Result mapping

```json
[
  {
    "{Zresult0.B, Zresult1.B}": "result"
  }
]
```

### Instruction mapping

When vnum is a multiple of 2 in the range [-16, 14], this intrinsic can use:

```asm
LD2B {Zresult0.B, Zresult1.B}, Pg/Z, [Xbase, #vnum, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD2B--scalar-plus-immediate---Contiguous-load-two-byte-structures-to-two-vectors--immediate-index--

The general implementation is:

```asm
LD2B {Zresult0.B, Zresult1.B}, Pg/Z, [Xbase, Xindex]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD2B--scalar-plus-scalar---Contiguous-load-two-byte-structures-to-two-vectors--scalar-index--

### Operation

Source operation ID: `SveOperation_svld2_vnum_bf16`

**Operation**



Return a tuple of two *n*-element vectors in which each active element *i* of vector *j* contains `base[n * vnum + i * 2 + j]` and in which all other elements are zero.  Do not access memory for inactive elements.

## svld2_vnum[_u16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld2_vnum%5B_u16%5D

### Signature (source notation)

```c
svuint16x2_t svld2_vnum[_u16](svbool_t pg, const uint16_t *base, int64_t vnum);
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
  "return_base_type": "uint",
  "element_bit_size": "16",
  "value": "svuint16x2_t"
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
    "{Zresult0.H, Zresult1.H}": "result"
  }
]
```

### Instruction mapping

When vnum is a multiple of 2 in the range [-16, 14], this intrinsic can use:

```asm
LD2H {Zresult0.H, Zresult1.H}, Pg/Z, [Xbase, #vnum, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD2H--scalar-plus-immediate---Contiguous-load-two-halfword-structures-to-two-vectors--immediate-index--

The general implementation is:

```asm
LD2H {Zresult0.H, Zresult1.H}, Pg/Z, [Xbase, Xindex, LSL #1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD2H--scalar-plus-scalar---Contiguous-load-two-halfword-structures-to-two-vectors--scalar-index--

### Operation

Source operation ID: `SveOperation_svld2_vnum_bf16`

**Operation**



Return a tuple of two *n*-element vectors in which each active element *i* of vector *j* contains `base[n * vnum + i * 2 + j]` and in which all other elements are zero.  Do not access memory for inactive elements.

## svld2_vnum[_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld2_vnum%5B_u32%5D

### Signature (source notation)

```c
svuint32x2_t svld2_vnum[_u32](svbool_t pg, const uint32_t *base, int64_t vnum);
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
  "return_base_type": "uint",
  "element_bit_size": "32",
  "value": "svuint32x2_t"
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
    "{Zresult0.S, Zresult1.S}": "result"
  }
]
```

### Instruction mapping

When vnum is a multiple of 2 in the range [-16, 14], this intrinsic can use:

```asm
LD2W {Zresult0.S, Zresult1.S}, Pg/Z, [Xbase, #vnum, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD2W--scalar-plus-immediate---Contiguous-load-two-word-structures-to-two-vectors--immediate-index--

The general implementation is:

```asm
LD2W {Zresult0.S, Zresult1.S}, Pg/Z, [Xbase, Xindex, LSL #2]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD2W--scalar-plus-scalar---Contiguous-load-two-word-structures-to-two-vectors--scalar-index--

### Operation

Source operation ID: `SveOperation_svld2_vnum_bf16`

**Operation**



Return a tuple of two *n*-element vectors in which each active element *i* of vector *j* contains `base[n * vnum + i * 2 + j]` and in which all other elements are zero.  Do not access memory for inactive elements.

## svld2_vnum[_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld2_vnum%5B_u64%5D

### Signature (source notation)

```c
svuint64x2_t svld2_vnum[_u64](svbool_t pg, const uint64_t *base, int64_t vnum);
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
  "return_base_type": "uint",
  "element_bit_size": "64",
  "value": "svuint64x2_t"
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
    "{Zresult0.D, Zresult1.D}": "result"
  }
]
```

### Instruction mapping

When vnum is a multiple of 2 in the range [-16, 14], this intrinsic can use:

```asm
LD2D {Zresult0.D, Zresult1.D}, Pg/Z, [Xbase, #vnum, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD2D--scalar-plus-immediate---Contiguous-load-two-doubleword-structures-to-two-vectors--immediate-index--

The general implementation is:

```asm
LD2D {Zresult0.D, Zresult1.D}, Pg/Z, [Xbase, Xindex, LSL #3]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD2D--scalar-plus-scalar---Contiguous-load-two-doubleword-structures-to-two-vectors--scalar-index--

### Operation

Source operation ID: `SveOperation_svld2_vnum_bf16`

**Operation**



Return a tuple of two *n*-element vectors in which each active element *i* of vector *j* contains `base[n * vnum + i * 2 + j]` and in which all other elements are zero.  Do not access memory for inactive elements.

## svld2_vnum[_u8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld2_vnum%5B_u8%5D

### Signature (source notation)

```c
svuint8x2_t svld2_vnum[_u8](svbool_t pg, const uint8_t *base, int64_t vnum);
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
  "return_base_type": "uint",
  "element_bit_size": "8",
  "value": "svuint8x2_t"
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
  "vnum * svcntb()": {
    "register": "Xindex"
  }
}
```

### Result mapping

```json
[
  {
    "{Zresult0.B, Zresult1.B}": "result"
  }
]
```

### Instruction mapping

When vnum is a multiple of 2 in the range [-16, 14], this intrinsic can use:

```asm
LD2B {Zresult0.B, Zresult1.B}, Pg/Z, [Xbase, #vnum, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD2B--scalar-plus-immediate---Contiguous-load-two-byte-structures-to-two-vectors--immediate-index--

The general implementation is:

```asm
LD2B {Zresult0.B, Zresult1.B}, Pg/Z, [Xbase, Xindex]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD2B--scalar-plus-scalar---Contiguous-load-two-byte-structures-to-two-vectors--scalar-index--

### Operation

Source operation ID: `SveOperation_svld2_vnum_bf16`

**Operation**



Return a tuple of two *n*-element vectors in which each active element *i* of vector *j* contains `base[n * vnum + i * 2 + j]` and in which all other elements are zero.  Do not access memory for inactive elements.

## svld2q[_bf16]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld2q%5B_bf16%5D

### Signature (source notation)

```c
svbfloat16x2_t svld2q[_bf16](svbool_t pg, bfloat16_t const * rn);
```

### Description

Contiguous load two-quadword structures to two vectors (immediate index)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Load / Consecutive

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
  "return_base_type": "bfloat16",
  "element_bit_size": "16",
  "value": "svbfloat16x2_t"
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
  }
}
```

### Result mapping

```json
[
  {
    "{ Zreg1.Q, Zreg2.Q }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
LD2Q { Zreg1.Q, Zreg2.Q }, Preg1/Z, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/LD2Q--scalar-plus-immediate---Contiguous-load-two-quadword-structures-to-two-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svld2q[_f16]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld2q%5B_f16%5D

### Signature (source notation)

```c
svfloat16x2_t svld2q[_f16](svbool_t pg, float16_t const * rn);
```

### Description

Contiguous load two-quadword structures to two vectors (immediate index)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Load / Consecutive

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
  "return_base_type": "float16",
  "element_bit_size": "16",
  "value": "svfloat16x2_t"
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
  }
}
```

### Result mapping

```json
[
  {
    "{ Zreg1.Q, Zreg2.Q }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
LD2Q { Zreg1.Q, Zreg2.Q }, Preg1/Z, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/LD2Q--scalar-plus-immediate---Contiguous-load-two-quadword-structures-to-two-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svld2q[_f32]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld2q%5B_f32%5D

### Signature (source notation)

```c
svfloat32x2_t svld2q[_f32](svbool_t pg, float32_t const * rn);
```

### Description

Contiguous load two-quadword structures to two vectors (immediate index)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Load / Consecutive

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
  "return_base_type": "float32",
  "element_bit_size": "32",
  "value": "svfloat32x2_t"
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
  }
}
```

### Result mapping

```json
[
  {
    "{ Zreg1.Q, Zreg2.Q }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
LD2Q { Zreg1.Q, Zreg2.Q }, Preg1/Z, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/LD2Q--scalar-plus-immediate---Contiguous-load-two-quadword-structures-to-two-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svld2q[_f64]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld2q%5B_f64%5D

### Signature (source notation)

```c
svfloat64x2_t svld2q[_f64](svbool_t pg, float64_t const * rn);
```

### Description

Contiguous load two-quadword structures to two vectors (immediate index)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Load / Consecutive

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
  "return_base_type": "float64",
  "element_bit_size": "64",
  "value": "svfloat64x2_t"
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
  }
}
```

### Result mapping

```json
[
  {
    "{ Zreg1.Q, Zreg2.Q }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
LD2Q { Zreg1.Q, Zreg2.Q }, Preg1/Z, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/LD2Q--scalar-plus-immediate---Contiguous-load-two-quadword-structures-to-two-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svld2q[_mf8]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld2q%5B_mf8%5D

### Signature (source notation)

```c
svmfloat8x2_t svld2q[_mf8](svbool_t pg, mfloat8_t const * rn);
```

### Description

Contiguous load two-quadword structures to two vectors (immediate index)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Load / Consecutive

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
  "return_base_type": "mfloat8",
  "element_bit_size": "8",
  "value": "svmfloat8x2_t"
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
  }
}
```

### Result mapping

```json
[
  {
    "{ Zreg1.Q, Zreg2.Q }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
LD2Q { Zreg1.Q, Zreg2.Q }, Preg1/Z, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/LD2Q--scalar-plus-immediate---Contiguous-load-two-quadword-structures-to-two-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svld2q[_s16]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld2q%5B_s16%5D

### Signature (source notation)

```c
svint16x2_t svld2q[_s16](svbool_t pg, int16_t const * rn);
```

### Description

Contiguous load two-quadword structures to two vectors (immediate index)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Load / Consecutive

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
  "return_base_type": "int16",
  "element_bit_size": "16",
  "value": "svint16x2_t"
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
  }
}
```

### Result mapping

```json
[
  {
    "{ Zreg1.Q, Zreg2.Q }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
LD2Q { Zreg1.Q, Zreg2.Q }, Preg1/Z, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/LD2Q--scalar-plus-immediate---Contiguous-load-two-quadword-structures-to-two-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svld2q[_s32]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld2q%5B_s32%5D

### Signature (source notation)

```c
svint32x2_t svld2q[_s32](svbool_t pg, int32_t const * rn);
```

### Description

Contiguous load two-quadword structures to two vectors (immediate index)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Load / Consecutive

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
  "return_base_type": "int32",
  "element_bit_size": "32",
  "value": "svint32x2_t"
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
  }
}
```

### Result mapping

```json
[
  {
    "{ Zreg1.Q, Zreg2.Q }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
LD2Q { Zreg1.Q, Zreg2.Q }, Preg1/Z, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/LD2Q--scalar-plus-immediate---Contiguous-load-two-quadword-structures-to-two-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svld2q[_s64]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld2q%5B_s64%5D

### Signature (source notation)

```c
svint64x2_t svld2q[_s64](svbool_t pg, int64_t const * rn);
```

### Description

Contiguous load two-quadword structures to two vectors (immediate index)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Load / Consecutive

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
  "return_base_type": "int64",
  "element_bit_size": "64",
  "value": "svint64x2_t"
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
  }
}
```

### Result mapping

```json
[
  {
    "{ Zreg1.Q, Zreg2.Q }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
LD2Q { Zreg1.Q, Zreg2.Q }, Preg1/Z, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/LD2Q--scalar-plus-immediate---Contiguous-load-two-quadword-structures-to-two-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svld2q[_s8]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld2q%5B_s8%5D

### Signature (source notation)

```c
svint8x2_t svld2q[_s8](svbool_t pg, int8_t const * rn);
```

### Description

Contiguous load two-quadword structures to two vectors (immediate index)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Load / Consecutive

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
  "return_base_type": "int8",
  "element_bit_size": "8",
  "value": "svint8x2_t"
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
  }
}
```

### Result mapping

```json
[
  {
    "{ Zreg1.Q, Zreg2.Q }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
LD2Q { Zreg1.Q, Zreg2.Q }, Preg1/Z, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/LD2Q--scalar-plus-immediate---Contiguous-load-two-quadword-structures-to-two-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svld2q[_u16]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld2q%5B_u16%5D

### Signature (source notation)

```c
svuint16x2_t svld2q[_u16](svbool_t pg, uint16_t const * rn);
```

### Description

Contiguous load two-quadword structures to two vectors (immediate index)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Load / Consecutive

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
  "return_base_type": "uint16",
  "element_bit_size": "16",
  "value": "svuint16x2_t"
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
  }
}
```

### Result mapping

```json
[
  {
    "{ Zreg1.Q, Zreg2.Q }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
LD2Q { Zreg1.Q, Zreg2.Q }, Preg1/Z, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/LD2Q--scalar-plus-immediate---Contiguous-load-two-quadword-structures-to-two-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svld2q[_u32]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld2q%5B_u32%5D

### Signature (source notation)

```c
svuint32x2_t svld2q[_u32](svbool_t pg, uint32_t const * rn);
```

### Description

Contiguous load two-quadword structures to two vectors (immediate index)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Load / Consecutive

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
  "return_base_type": "uint32",
  "element_bit_size": "32",
  "value": "svuint32x2_t"
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
  }
}
```

### Result mapping

```json
[
  {
    "{ Zreg1.Q, Zreg2.Q }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
LD2Q { Zreg1.Q, Zreg2.Q }, Preg1/Z, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/LD2Q--scalar-plus-immediate---Contiguous-load-two-quadword-structures-to-two-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svld2q[_u64]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld2q%5B_u64%5D

### Signature (source notation)

```c
svuint64x2_t svld2q[_u64](svbool_t pg, uint64_t const * rn);
```

### Description

Contiguous load two-quadword structures to two vectors (immediate index)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Load / Consecutive

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
  "return_base_type": "uint64",
  "element_bit_size": "64",
  "value": "svuint64x2_t"
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
  }
}
```

### Result mapping

```json
[
  {
    "{ Zreg1.Q, Zreg2.Q }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
LD2Q { Zreg1.Q, Zreg2.Q }, Preg1/Z, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/LD2Q--scalar-plus-immediate---Contiguous-load-two-quadword-structures-to-two-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svld2q[_u8]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld2q%5B_u8%5D

### Signature (source notation)

```c
svuint8x2_t svld2q[_u8](svbool_t pg, uint8_t const * rn);
```

### Description

Contiguous load two-quadword structures to two vectors (immediate index)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Load / Consecutive

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
  "return_base_type": "uint8",
  "element_bit_size": "8",
  "value": "svuint8x2_t"
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
  }
}
```

### Result mapping

```json
[
  {
    "{ Zreg1.Q, Zreg2.Q }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
LD2Q { Zreg1.Q, Zreg2.Q }, Preg1/Z, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/LD2Q--scalar-plus-immediate---Contiguous-load-two-quadword-structures-to-two-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svld2q_vnum[_bf16]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld2q_vnum%5B_bf16%5D

### Signature (source notation)

```c
svbfloat16x2_t svld2q_vnum[_bf16](svbool_t pg, bfloat16_t const * rn, int64_t vnum);
```

### Description

Contiguous load two-quadword structures to two vectors (immediate index)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Load / Consecutive

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
  "return_base_type": "bfloat16",
  "element_bit_size": "16",
  "value": "svbfloat16x2_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Preg1"
  },
  "rn": {
    "register": "Xreg3"
  },
  "vnum": {
    "register": "Xreg2"
  }
}
```

### Result mapping

```json
[
  {
    "{ Zreg1.Q, Zreg2.Q }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
RDVL Xreg1, #1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/RDVL--Read-multiple-of-vector-register-size-to-scalar-register-

```asm
MADD Xreg1, Xreg1, Xreg2, Xreg3
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/Base-Instructions/MADD--Multiply-add-

```asm
LD2Q { Zreg1.Q, Zreg2.Q }, Preg1/Z, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/LD2Q--scalar-plus-immediate---Contiguous-load-two-quadword-structures-to-two-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svld2q_vnum[_f16]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld2q_vnum%5B_f16%5D

### Signature (source notation)

```c
svfloat16x2_t svld2q_vnum[_f16](svbool_t pg, float16_t const * rn, int64_t vnum);
```

### Description

Contiguous load two-quadword structures to two vectors (immediate index)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Load / Consecutive

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
  "return_base_type": "float16",
  "element_bit_size": "16",
  "value": "svfloat16x2_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Preg1"
  },
  "rn": {
    "register": "Xreg3"
  },
  "vnum": {
    "register": "Xreg2"
  }
}
```

### Result mapping

```json
[
  {
    "{ Zreg1.Q, Zreg2.Q }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
RDVL Xreg1, #1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/RDVL--Read-multiple-of-vector-register-size-to-scalar-register-

```asm
MADD Xreg1, Xreg1, Xreg2, Xreg3
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/Base-Instructions/MADD--Multiply-add-

```asm
LD2Q { Zreg1.Q, Zreg2.Q }, Preg1/Z, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/LD2Q--scalar-plus-immediate---Contiguous-load-two-quadword-structures-to-two-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svld2q_vnum[_f32]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld2q_vnum%5B_f32%5D

### Signature (source notation)

```c
svfloat32x2_t svld2q_vnum[_f32](svbool_t pg, float32_t const * rn, int64_t vnum);
```

### Description

Contiguous load two-quadword structures to two vectors (immediate index)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Load / Consecutive

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
  "return_base_type": "float32",
  "element_bit_size": "32",
  "value": "svfloat32x2_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Preg1"
  },
  "rn": {
    "register": "Xreg3"
  },
  "vnum": {
    "register": "Xreg2"
  }
}
```

### Result mapping

```json
[
  {
    "{ Zreg1.Q, Zreg2.Q }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
RDVL Xreg1, #1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/RDVL--Read-multiple-of-vector-register-size-to-scalar-register-

```asm
MADD Xreg1, Xreg1, Xreg2, Xreg3
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/Base-Instructions/MADD--Multiply-add-

```asm
LD2Q { Zreg1.Q, Zreg2.Q }, Preg1/Z, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/LD2Q--scalar-plus-immediate---Contiguous-load-two-quadword-structures-to-two-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svld2q_vnum[_f64]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld2q_vnum%5B_f64%5D

### Signature (source notation)

```c
svfloat64x2_t svld2q_vnum[_f64](svbool_t pg, float64_t const * rn, int64_t vnum);
```

### Description

Contiguous load two-quadword structures to two vectors (immediate index)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Load / Consecutive

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
  "return_base_type": "float64",
  "element_bit_size": "64",
  "value": "svfloat64x2_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Preg1"
  },
  "rn": {
    "register": "Xreg3"
  },
  "vnum": {
    "register": "Xreg2"
  }
}
```

### Result mapping

```json
[
  {
    "{ Zreg1.Q, Zreg2.Q }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
RDVL Xreg1, #1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/RDVL--Read-multiple-of-vector-register-size-to-scalar-register-

```asm
MADD Xreg1, Xreg1, Xreg2, Xreg3
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/Base-Instructions/MADD--Multiply-add-

```asm
LD2Q { Zreg1.Q, Zreg2.Q }, Preg1/Z, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/LD2Q--scalar-plus-immediate---Contiguous-load-two-quadword-structures-to-two-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svld2q_vnum[_mf8]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld2q_vnum%5B_mf8%5D

### Signature (source notation)

```c
svmfloat8x2_t svld2q_vnum[_mf8](svbool_t pg, mfloat8_t const * rn, int64_t vnum);
```

### Description

Contiguous load two-quadword structures to two vectors (immediate index)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Load / Consecutive

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
  "return_base_type": "mfloat8",
  "element_bit_size": "8",
  "value": "svmfloat8x2_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Preg1"
  },
  "rn": {
    "register": "Xreg3"
  },
  "vnum": {
    "register": "Xreg2"
  }
}
```

### Result mapping

```json
[
  {
    "{ Zreg1.Q, Zreg2.Q }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
RDVL Xreg1, #1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/RDVL--Read-multiple-of-vector-register-size-to-scalar-register-

```asm
MADD Xreg1, Xreg1, Xreg2, Xreg3
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/Base-Instructions/MADD--Multiply-add-

```asm
LD2Q { Zreg1.Q, Zreg2.Q }, Preg1/Z, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/LD2Q--scalar-plus-immediate---Contiguous-load-two-quadword-structures-to-two-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svld2q_vnum[_s16]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld2q_vnum%5B_s16%5D

### Signature (source notation)

```c
svint16x2_t svld2q_vnum[_s16](svbool_t pg, int16_t const * rn, int64_t vnum);
```

### Description

Contiguous load two-quadword structures to two vectors (immediate index)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Load / Consecutive

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
  "return_base_type": "int16",
  "element_bit_size": "16",
  "value": "svint16x2_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Preg1"
  },
  "rn": {
    "register": "Xreg3"
  },
  "vnum": {
    "register": "Xreg2"
  }
}
```

### Result mapping

```json
[
  {
    "{ Zreg1.Q, Zreg2.Q }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
RDVL Xreg1, #1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/RDVL--Read-multiple-of-vector-register-size-to-scalar-register-

```asm
MADD Xreg1, Xreg1, Xreg2, Xreg3
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/Base-Instructions/MADD--Multiply-add-

```asm
LD2Q { Zreg1.Q, Zreg2.Q }, Preg1/Z, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/LD2Q--scalar-plus-immediate---Contiguous-load-two-quadword-structures-to-two-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svld2q_vnum[_s32]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld2q_vnum%5B_s32%5D

### Signature (source notation)

```c
svint32x2_t svld2q_vnum[_s32](svbool_t pg, int32_t const * rn, int64_t vnum);
```

### Description

Contiguous load two-quadword structures to two vectors (immediate index)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Load / Consecutive

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
  "return_base_type": "int32",
  "element_bit_size": "32",
  "value": "svint32x2_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Preg1"
  },
  "rn": {
    "register": "Xreg3"
  },
  "vnum": {
    "register": "Xreg2"
  }
}
```

### Result mapping

```json
[
  {
    "{ Zreg1.Q, Zreg2.Q }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
RDVL Xreg1, #1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/RDVL--Read-multiple-of-vector-register-size-to-scalar-register-

```asm
MADD Xreg1, Xreg1, Xreg2, Xreg3
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/Base-Instructions/MADD--Multiply-add-

```asm
LD2Q { Zreg1.Q, Zreg2.Q }, Preg1/Z, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/LD2Q--scalar-plus-immediate---Contiguous-load-two-quadword-structures-to-two-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svld2q_vnum[_s64]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld2q_vnum%5B_s64%5D

### Signature (source notation)

```c
svint64x2_t svld2q_vnum[_s64](svbool_t pg, int64_t const * rn, int64_t vnum);
```

### Description

Contiguous load two-quadword structures to two vectors (immediate index)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Load / Consecutive

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
  "return_base_type": "int64",
  "element_bit_size": "64",
  "value": "svint64x2_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Preg1"
  },
  "rn": {
    "register": "Xreg3"
  },
  "vnum": {
    "register": "Xreg2"
  }
}
```

### Result mapping

```json
[
  {
    "{ Zreg1.Q, Zreg2.Q }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
RDVL Xreg1, #1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/RDVL--Read-multiple-of-vector-register-size-to-scalar-register-

```asm
MADD Xreg1, Xreg1, Xreg2, Xreg3
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/Base-Instructions/MADD--Multiply-add-

```asm
LD2Q { Zreg1.Q, Zreg2.Q }, Preg1/Z, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/LD2Q--scalar-plus-immediate---Contiguous-load-two-quadword-structures-to-two-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svld2q_vnum[_s8]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld2q_vnum%5B_s8%5D

### Signature (source notation)

```c
svint8x2_t svld2q_vnum[_s8](svbool_t pg, int8_t const * rn, int64_t vnum);
```

### Description

Contiguous load two-quadword structures to two vectors (immediate index)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Load / Consecutive

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
  "return_base_type": "int8",
  "element_bit_size": "8",
  "value": "svint8x2_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Preg1"
  },
  "rn": {
    "register": "Xreg3"
  },
  "vnum": {
    "register": "Xreg2"
  }
}
```

### Result mapping

```json
[
  {
    "{ Zreg1.Q, Zreg2.Q }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
RDVL Xreg1, #1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/RDVL--Read-multiple-of-vector-register-size-to-scalar-register-

```asm
MADD Xreg1, Xreg1, Xreg2, Xreg3
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/Base-Instructions/MADD--Multiply-add-

```asm
LD2Q { Zreg1.Q, Zreg2.Q }, Preg1/Z, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/LD2Q--scalar-plus-immediate---Contiguous-load-two-quadword-structures-to-two-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svld2q_vnum[_u16]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld2q_vnum%5B_u16%5D

### Signature (source notation)

```c
svuint16x2_t svld2q_vnum[_u16](svbool_t pg, uint16_t const * rn, int64_t vnum);
```

### Description

Contiguous load two-quadword structures to two vectors (immediate index)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Load / Consecutive

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
  "return_base_type": "uint16",
  "element_bit_size": "16",
  "value": "svuint16x2_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Preg1"
  },
  "rn": {
    "register": "Xreg3"
  },
  "vnum": {
    "register": "Xreg2"
  }
}
```

### Result mapping

```json
[
  {
    "{ Zreg1.Q, Zreg2.Q }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
RDVL Xreg1, #1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/RDVL--Read-multiple-of-vector-register-size-to-scalar-register-

```asm
MADD Xreg1, Xreg1, Xreg2, Xreg3
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/Base-Instructions/MADD--Multiply-add-

```asm
LD2Q { Zreg1.Q, Zreg2.Q }, Preg1/Z, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/LD2Q--scalar-plus-immediate---Contiguous-load-two-quadword-structures-to-two-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svld2q_vnum[_u32]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld2q_vnum%5B_u32%5D

### Signature (source notation)

```c
svuint32x2_t svld2q_vnum[_u32](svbool_t pg, uint32_t const * rn, int64_t vnum);
```

### Description

Contiguous load two-quadword structures to two vectors (immediate index)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Load / Consecutive

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
  "return_base_type": "uint32",
  "element_bit_size": "32",
  "value": "svuint32x2_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Preg1"
  },
  "rn": {
    "register": "Xreg3"
  },
  "vnum": {
    "register": "Xreg2"
  }
}
```

### Result mapping

```json
[
  {
    "{ Zreg1.Q, Zreg2.Q }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
RDVL Xreg1, #1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/RDVL--Read-multiple-of-vector-register-size-to-scalar-register-

```asm
MADD Xreg1, Xreg1, Xreg2, Xreg3
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/Base-Instructions/MADD--Multiply-add-

```asm
LD2Q { Zreg1.Q, Zreg2.Q }, Preg1/Z, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/LD2Q--scalar-plus-immediate---Contiguous-load-two-quadword-structures-to-two-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svld2q_vnum[_u64]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld2q_vnum%5B_u64%5D

### Signature (source notation)

```c
svuint64x2_t svld2q_vnum[_u64](svbool_t pg, uint64_t const * rn, int64_t vnum);
```

### Description

Contiguous load two-quadword structures to two vectors (immediate index)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Load / Consecutive

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
  "return_base_type": "uint64",
  "element_bit_size": "64",
  "value": "svuint64x2_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Preg1"
  },
  "rn": {
    "register": "Xreg3"
  },
  "vnum": {
    "register": "Xreg2"
  }
}
```

### Result mapping

```json
[
  {
    "{ Zreg1.Q, Zreg2.Q }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
RDVL Xreg1, #1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/RDVL--Read-multiple-of-vector-register-size-to-scalar-register-

```asm
MADD Xreg1, Xreg1, Xreg2, Xreg3
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/Base-Instructions/MADD--Multiply-add-

```asm
LD2Q { Zreg1.Q, Zreg2.Q }, Preg1/Z, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/LD2Q--scalar-plus-immediate---Contiguous-load-two-quadword-structures-to-two-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svld2q_vnum[_u8]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld2q_vnum%5B_u8%5D

### Signature (source notation)

```c
svuint8x2_t svld2q_vnum[_u8](svbool_t pg, uint8_t const * rn, int64_t vnum);
```

### Description

Contiguous load two-quadword structures to two vectors (immediate index)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Load / Consecutive

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
  "return_base_type": "uint8",
  "element_bit_size": "8",
  "value": "svuint8x2_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Preg1"
  },
  "rn": {
    "register": "Xreg3"
  },
  "vnum": {
    "register": "Xreg2"
  }
}
```

### Result mapping

```json
[
  {
    "{ Zreg1.Q, Zreg2.Q }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
RDVL Xreg1, #1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/RDVL--Read-multiple-of-vector-register-size-to-scalar-register-

```asm
MADD Xreg1, Xreg1, Xreg2, Xreg3
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/Base-Instructions/MADD--Multiply-add-

```asm
LD2Q { Zreg1.Q, Zreg2.Q }, Preg1/Z, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/LD2Q--scalar-plus-immediate---Contiguous-load-two-quadword-structures-to-two-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svld3[_bf16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld3%5B_bf16%5D

### Signature (source notation)

```c
svbfloat16x3_t svld3[_bf16](svbool_t pg, const bfloat16_t *base);
```

### Description

Load three-element tuples into three vectors

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
  "value": "svbfloat16x3_t"
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
    "{Zresult0.H - Zresult2.H}": "result"
  }
]
```

### Instruction mapping

When base has the form &array[index], this intrinsic can use:

```asm
LD3H {Zresult0.H - Zresult2.H}, Pg/Z, [Xarray, Xindex, LSL #1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD3H--scalar-plus-scalar---Contiguous-load-three-halfword-structures-to-three-vectors--scalar-index--

The general implementation is:

```asm
LD3H {Zresult0.H - Zresult2.H}, Pg/Z, [Xbase, #0, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD3H--scalar-plus-immediate---Contiguous-load-three-halfword-structures-to-three-vectors--immediate-index--

### Operation

Source operation ID: `SveOperation_svld3_bf16`

**Operation**



Return a tuple of three vectors in which each active element *i* of vector *j* contains `base[i * 3 + j]` and in which all other elements are zero.  Do not access memory for inactive elements.

## svld3[_f16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld3%5B_f16%5D

### Signature (source notation)

```c
svfloat16x3_t svld3[_f16](svbool_t pg, const float16_t *base);
```

### Description

Load three-element tuples into three vectors

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
  "value": "svfloat16x3_t"
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
    "{Zresult0.H - Zresult2.H}": "result"
  }
]
```

### Instruction mapping

When base has the form &array[index], this intrinsic can use:

```asm
LD3H {Zresult0.H - Zresult2.H}, Pg/Z, [Xarray, Xindex, LSL #1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD3H--scalar-plus-scalar---Contiguous-load-three-halfword-structures-to-three-vectors--scalar-index--

The general implementation is:

```asm
LD3H {Zresult0.H - Zresult2.H}, Pg/Z, [Xbase, #0, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD3H--scalar-plus-immediate---Contiguous-load-three-halfword-structures-to-three-vectors--immediate-index--

### Operation

Source operation ID: `SveOperation_svld3_bf16`

**Operation**



Return a tuple of three vectors in which each active element *i* of vector *j* contains `base[i * 3 + j]` and in which all other elements are zero.  Do not access memory for inactive elements.

