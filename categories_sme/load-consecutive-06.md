# SME / Load / Consecutive — Part 6

## svld4[_bf16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld4%5B_bf16%5D

### Signature (source notation)

```c
svbfloat16x4_t svld4[_bf16](svbool_t pg, const bfloat16_t *base);
```

### Description

Load four-element tuples into four vectors

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
  "value": "svbfloat16x4_t"
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
    "{Zresult0.H - Zresult3.H}": "result"
  }
]
```

### Instruction mapping

When base has the form &array[index], this intrinsic can use:

```asm
LD4H {Zresult0.H - Zresult3.H}, Pg/Z, [Xarray, Xindex, LSL #1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD4H--scalar-plus-scalar---Contiguous-load-four-halfword-structures-to-four-vectors--scalar-index--

The general implementation is:

```asm
LD4H {Zresult0.H - Zresult3.H}, Pg/Z, [Xbase, #0, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD4H--scalar-plus-immediate---Contiguous-load-four-halfword-structures-to-four-vectors--immediate-index--

### Operation

Source operation ID: `SveOperation_svld4_bf16`

**Operation**



Return a tuple of four vectors in which each active element *i* of vector *j* contains `base[i * 4 + j]` and in which all other elements are zero.  Do not access memory for inactive elements.

## svld4[_f16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld4%5B_f16%5D

### Signature (source notation)

```c
svfloat16x4_t svld4[_f16](svbool_t pg, const float16_t *base);
```

### Description

Load four-element tuples into four vectors

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
  "value": "svfloat16x4_t"
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
    "{Zresult0.H - Zresult3.H}": "result"
  }
]
```

### Instruction mapping

When base has the form &array[index], this intrinsic can use:

```asm
LD4H {Zresult0.H - Zresult3.H}, Pg/Z, [Xarray, Xindex, LSL #1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD4H--scalar-plus-scalar---Contiguous-load-four-halfword-structures-to-four-vectors--scalar-index--

The general implementation is:

```asm
LD4H {Zresult0.H - Zresult3.H}, Pg/Z, [Xbase, #0, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD4H--scalar-plus-immediate---Contiguous-load-four-halfword-structures-to-four-vectors--immediate-index--

### Operation

Source operation ID: `SveOperation_svld4_bf16`

**Operation**



Return a tuple of four vectors in which each active element *i* of vector *j* contains `base[i * 4 + j]` and in which all other elements are zero.  Do not access memory for inactive elements.

## svld4[_f32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld4%5B_f32%5D

### Signature (source notation)

```c
svfloat32x4_t svld4[_f32](svbool_t pg, const float32_t *base);
```

### Description

Load four-element tuples into four vectors

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
  "value": "svfloat32x4_t"
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
    "{Zresult0.S - Zresult3.S}": "result"
  }
]
```

### Instruction mapping

When base has the form &array[index], this intrinsic can use:

```asm
LD4W {Zresult0.S - Zresult3.S}, Pg/Z, [Xarray, Xindex, LSL #2]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD4W--scalar-plus-scalar---Contiguous-load-four-word-structures-to-four-vectors--scalar-index--

The general implementation is:

```asm
LD4W {Zresult0.S - Zresult3.S}, Pg/Z, [Xbase, #0, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD4W--scalar-plus-immediate---Contiguous-load-four-word-structures-to-four-vectors--immediate-index--

### Operation

Source operation ID: `SveOperation_svld4_bf16`

**Operation**



Return a tuple of four vectors in which each active element *i* of vector *j* contains `base[i * 4 + j]` and in which all other elements are zero.  Do not access memory for inactive elements.

## svld4[_f64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld4%5B_f64%5D

### Signature (source notation)

```c
svfloat64x4_t svld4[_f64](svbool_t pg, const float64_t *base);
```

### Description

Load four-element tuples into four vectors

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
  "value": "svfloat64x4_t"
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
    "{Zresult0.D - Zresult3.D}": "result"
  }
]
```

### Instruction mapping

When base has the form &array[index], this intrinsic can use:

```asm
LD4D {Zresult0.D - Zresult3.D}, Pg/Z, [Xarray, Xindex, LSL #3]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD4D--scalar-plus-scalar---Contiguous-load-four-doubleword-structures-to-four-vectors--scalar-index--

The general implementation is:

```asm
LD4D {Zresult0.D - Zresult3.D}, Pg/Z, [Xbase, #0, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD4D--scalar-plus-immediate---Contiguous-load-four-doubleword-structures-to-four-vectors--immediate-index--

### Operation

Source operation ID: `SveOperation_svld4_bf16`

**Operation**



Return a tuple of four vectors in which each active element *i* of vector *j* contains `base[i * 4 + j]` and in which all other elements are zero.  Do not access memory for inactive elements.

## svld4[_mf8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld4%5B_mf8%5D

### Signature (source notation)

```c
svmfloat8x4_t svld4[_mf8](svbool_t pg, const mfloat8_t *base);
```

### Description

Load four-element tuples into four vectors

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
  "value": "svmfloat8x4_t"
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
    "{Zresult0.B - Zresult3.B}": "result"
  }
]
```

### Instruction mapping

When base has the form &array[index], this intrinsic can use:

```asm
LD4B {Zresult0.B - Zresult3.B}, Pg/Z, [Xarray, Xindex]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD4B--scalar-plus-scalar---Contiguous-load-four-byte-structures-to-four-vectors--scalar-index--

The general implementation is:

```asm
LD4B {Zresult0.B - Zresult3.B}, Pg/Z, [Xbase, #0, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD4B--scalar-plus-immediate---Contiguous-load-four-byte-structures-to-four-vectors--immediate-index--

### Operation

Source operation ID: `SveOperation_svld4_bf16`

**Operation**



Return a tuple of four vectors in which each active element *i* of vector *j* contains `base[i * 4 + j]` and in which all other elements are zero.  Do not access memory for inactive elements.

## svld4[_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld4%5B_s16%5D

### Signature (source notation)

```c
svint16x4_t svld4[_s16](svbool_t pg, const int16_t *base);
```

### Description

Load four-element tuples into four vectors

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
  "value": "svint16x4_t"
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
    "{Zresult0.H - Zresult3.H}": "result"
  }
]
```

### Instruction mapping

When base has the form &array[index], this intrinsic can use:

```asm
LD4H {Zresult0.H - Zresult3.H}, Pg/Z, [Xarray, Xindex, LSL #1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD4H--scalar-plus-scalar---Contiguous-load-four-halfword-structures-to-four-vectors--scalar-index--

The general implementation is:

```asm
LD4H {Zresult0.H - Zresult3.H}, Pg/Z, [Xbase, #0, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD4H--scalar-plus-immediate---Contiguous-load-four-halfword-structures-to-four-vectors--immediate-index--

### Operation

Source operation ID: `SveOperation_svld4_bf16`

**Operation**



Return a tuple of four vectors in which each active element *i* of vector *j* contains `base[i * 4 + j]` and in which all other elements are zero.  Do not access memory for inactive elements.

## svld4[_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld4%5B_s32%5D

### Signature (source notation)

```c
svint32x4_t svld4[_s32](svbool_t pg, const int32_t *base);
```

### Description

Load four-element tuples into four vectors

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
  "value": "svint32x4_t"
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
    "{Zresult0.S - Zresult3.S}": "result"
  }
]
```

### Instruction mapping

When base has the form &array[index], this intrinsic can use:

```asm
LD4W {Zresult0.S - Zresult3.S}, Pg/Z, [Xarray, Xindex, LSL #2]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD4W--scalar-plus-scalar---Contiguous-load-four-word-structures-to-four-vectors--scalar-index--

The general implementation is:

```asm
LD4W {Zresult0.S - Zresult3.S}, Pg/Z, [Xbase, #0, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD4W--scalar-plus-immediate---Contiguous-load-four-word-structures-to-four-vectors--immediate-index--

### Operation

Source operation ID: `SveOperation_svld4_bf16`

**Operation**



Return a tuple of four vectors in which each active element *i* of vector *j* contains `base[i * 4 + j]` and in which all other elements are zero.  Do not access memory for inactive elements.

## svld4[_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld4%5B_s64%5D

### Signature (source notation)

```c
svint64x4_t svld4[_s64](svbool_t pg, const int64_t *base);
```

### Description

Load four-element tuples into four vectors

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
  "value": "svint64x4_t"
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
    "{Zresult0.D - Zresult3.D}": "result"
  }
]
```

### Instruction mapping

When base has the form &array[index], this intrinsic can use:

```asm
LD4D {Zresult0.D - Zresult3.D}, Pg/Z, [Xarray, Xindex, LSL #3]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD4D--scalar-plus-scalar---Contiguous-load-four-doubleword-structures-to-four-vectors--scalar-index--

The general implementation is:

```asm
LD4D {Zresult0.D - Zresult3.D}, Pg/Z, [Xbase, #0, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD4D--scalar-plus-immediate---Contiguous-load-four-doubleword-structures-to-four-vectors--immediate-index--

### Operation

Source operation ID: `SveOperation_svld4_bf16`

**Operation**



Return a tuple of four vectors in which each active element *i* of vector *j* contains `base[i * 4 + j]` and in which all other elements are zero.  Do not access memory for inactive elements.

## svld4[_s8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld4%5B_s8%5D

### Signature (source notation)

```c
svint8x4_t svld4[_s8](svbool_t pg, const int8_t *base);
```

### Description

Load four-element tuples into four vectors

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
  "value": "svint8x4_t"
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
    "{Zresult0.B - Zresult3.B}": "result"
  }
]
```

### Instruction mapping

When base has the form &array[index], this intrinsic can use:

```asm
LD4B {Zresult0.B - Zresult3.B}, Pg/Z, [Xarray, Xindex]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD4B--scalar-plus-scalar---Contiguous-load-four-byte-structures-to-four-vectors--scalar-index--

The general implementation is:

```asm
LD4B {Zresult0.B - Zresult3.B}, Pg/Z, [Xbase, #0, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD4B--scalar-plus-immediate---Contiguous-load-four-byte-structures-to-four-vectors--immediate-index--

### Operation

Source operation ID: `SveOperation_svld4_bf16`

**Operation**



Return a tuple of four vectors in which each active element *i* of vector *j* contains `base[i * 4 + j]` and in which all other elements are zero.  Do not access memory for inactive elements.

## svld4[_u16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld4%5B_u16%5D

### Signature (source notation)

```c
svuint16x4_t svld4[_u16](svbool_t pg, const uint16_t *base);
```

### Description

Load four-element tuples into four vectors

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
  "value": "svuint16x4_t"
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
    "{Zresult0.H - Zresult3.H}": "result"
  }
]
```

### Instruction mapping

When base has the form &array[index], this intrinsic can use:

```asm
LD4H {Zresult0.H - Zresult3.H}, Pg/Z, [Xarray, Xindex, LSL #1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD4H--scalar-plus-scalar---Contiguous-load-four-halfword-structures-to-four-vectors--scalar-index--

The general implementation is:

```asm
LD4H {Zresult0.H - Zresult3.H}, Pg/Z, [Xbase, #0, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD4H--scalar-plus-immediate---Contiguous-load-four-halfword-structures-to-four-vectors--immediate-index--

### Operation

Source operation ID: `SveOperation_svld4_bf16`

**Operation**



Return a tuple of four vectors in which each active element *i* of vector *j* contains `base[i * 4 + j]` and in which all other elements are zero.  Do not access memory for inactive elements.

## svld4[_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld4%5B_u32%5D

### Signature (source notation)

```c
svuint32x4_t svld4[_u32](svbool_t pg, const uint32_t *base);
```

### Description

Load four-element tuples into four vectors

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
  "value": "svuint32x4_t"
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
    "{Zresult0.S - Zresult3.S}": "result"
  }
]
```

### Instruction mapping

When base has the form &array[index], this intrinsic can use:

```asm
LD4W {Zresult0.S - Zresult3.S}, Pg/Z, [Xarray, Xindex, LSL #2]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD4W--scalar-plus-scalar---Contiguous-load-four-word-structures-to-four-vectors--scalar-index--

The general implementation is:

```asm
LD4W {Zresult0.S - Zresult3.S}, Pg/Z, [Xbase, #0, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD4W--scalar-plus-immediate---Contiguous-load-four-word-structures-to-four-vectors--immediate-index--

### Operation

Source operation ID: `SveOperation_svld4_bf16`

**Operation**



Return a tuple of four vectors in which each active element *i* of vector *j* contains `base[i * 4 + j]` and in which all other elements are zero.  Do not access memory for inactive elements.

## svld4[_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld4%5B_u64%5D

### Signature (source notation)

```c
svuint64x4_t svld4[_u64](svbool_t pg, const uint64_t *base);
```

### Description

Load four-element tuples into four vectors

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
  "value": "svuint64x4_t"
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
    "{Zresult0.D - Zresult3.D}": "result"
  }
]
```

### Instruction mapping

When base has the form &array[index], this intrinsic can use:

```asm
LD4D {Zresult0.D - Zresult3.D}, Pg/Z, [Xarray, Xindex, LSL #3]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD4D--scalar-plus-scalar---Contiguous-load-four-doubleword-structures-to-four-vectors--scalar-index--

The general implementation is:

```asm
LD4D {Zresult0.D - Zresult3.D}, Pg/Z, [Xbase, #0, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD4D--scalar-plus-immediate---Contiguous-load-four-doubleword-structures-to-four-vectors--immediate-index--

### Operation

Source operation ID: `SveOperation_svld4_bf16`

**Operation**



Return a tuple of four vectors in which each active element *i* of vector *j* contains `base[i * 4 + j]` and in which all other elements are zero.  Do not access memory for inactive elements.

## svld4[_u8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld4%5B_u8%5D

### Signature (source notation)

```c
svuint8x4_t svld4[_u8](svbool_t pg, const uint8_t *base);
```

### Description

Load four-element tuples into four vectors

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
  "value": "svuint8x4_t"
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
    "{Zresult0.B - Zresult3.B}": "result"
  }
]
```

### Instruction mapping

When base has the form &array[index], this intrinsic can use:

```asm
LD4B {Zresult0.B - Zresult3.B}, Pg/Z, [Xarray, Xindex]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD4B--scalar-plus-scalar---Contiguous-load-four-byte-structures-to-four-vectors--scalar-index--

The general implementation is:

```asm
LD4B {Zresult0.B - Zresult3.B}, Pg/Z, [Xbase, #0, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD4B--scalar-plus-immediate---Contiguous-load-four-byte-structures-to-four-vectors--immediate-index--

### Operation

Source operation ID: `SveOperation_svld4_bf16`

**Operation**



Return a tuple of four vectors in which each active element *i* of vector *j* contains `base[i * 4 + j]` and in which all other elements are zero.  Do not access memory for inactive elements.

## svld4_vnum[_bf16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld4_vnum%5B_bf16%5D

### Signature (source notation)

```c
svbfloat16x4_t svld4_vnum[_bf16](svbool_t pg, const bfloat16_t *base, int64_t vnum);
```

### Description

Load four-element tuples into four vectors

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
  "value": "svbfloat16x4_t"
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
    "{Zresult0.H - Zresult3.H}": "result"
  }
]
```

### Instruction mapping

When vnum is a multiple of 4 in the range [-32, 28], this intrinsic can use:

```asm
LD4H {Zresult0.H - Zresult3.H}, Pg/Z, [Xbase, #vnum, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD4H--scalar-plus-immediate---Contiguous-load-four-halfword-structures-to-four-vectors--immediate-index--

The general implementation is:

```asm
LD4H {Zresult0.H - Zresult3.H}, Pg/Z, [Xbase, Xindex, LSL #1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD4H--scalar-plus-scalar---Contiguous-load-four-halfword-structures-to-four-vectors--scalar-index--

### Operation

Source operation ID: `SveOperation_svld4_vnum_bf16`

**Operation**



Return a tuple of four *n*-element vectors in which each active element *i* of vector *j* contains `base[n * vnum + i * 4 + j]` and in which all other elements are zero.  Do not access memory for inactive elements.

## svld4_vnum[_f16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld4_vnum%5B_f16%5D

### Signature (source notation)

```c
svfloat16x4_t svld4_vnum[_f16](svbool_t pg, const float16_t *base, int64_t vnum);
```

### Description

Load four-element tuples into four vectors

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
  "value": "svfloat16x4_t"
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
    "{Zresult0.H - Zresult3.H}": "result"
  }
]
```

### Instruction mapping

When vnum is a multiple of 4 in the range [-32, 28], this intrinsic can use:

```asm
LD4H {Zresult0.H - Zresult3.H}, Pg/Z, [Xbase, #vnum, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD4H--scalar-plus-immediate---Contiguous-load-four-halfword-structures-to-four-vectors--immediate-index--

The general implementation is:

```asm
LD4H {Zresult0.H - Zresult3.H}, Pg/Z, [Xbase, Xindex, LSL #1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD4H--scalar-plus-scalar---Contiguous-load-four-halfword-structures-to-four-vectors--scalar-index--

### Operation

Source operation ID: `SveOperation_svld4_vnum_bf16`

**Operation**



Return a tuple of four *n*-element vectors in which each active element *i* of vector *j* contains `base[n * vnum + i * 4 + j]` and in which all other elements are zero.  Do not access memory for inactive elements.

## svld4_vnum[_f32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld4_vnum%5B_f32%5D

### Signature (source notation)

```c
svfloat32x4_t svld4_vnum[_f32](svbool_t pg, const float32_t *base, int64_t vnum);
```

### Description

Load four-element tuples into four vectors

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
  "value": "svfloat32x4_t"
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
    "{Zresult0.S - Zresult3.S}": "result"
  }
]
```

### Instruction mapping

When vnum is a multiple of 4 in the range [-32, 28], this intrinsic can use:

```asm
LD4W {Zresult0.S - Zresult3.S}, Pg/Z, [Xbase, #vnum, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD4W--scalar-plus-immediate---Contiguous-load-four-word-structures-to-four-vectors--immediate-index--

The general implementation is:

```asm
LD4W {Zresult0.S - Zresult3.S}, Pg/Z, [Xbase, Xindex, LSL #2]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD4W--scalar-plus-scalar---Contiguous-load-four-word-structures-to-four-vectors--scalar-index--

### Operation

Source operation ID: `SveOperation_svld4_vnum_bf16`

**Operation**



Return a tuple of four *n*-element vectors in which each active element *i* of vector *j* contains `base[n * vnum + i * 4 + j]` and in which all other elements are zero.  Do not access memory for inactive elements.

## svld4_vnum[_f64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld4_vnum%5B_f64%5D

### Signature (source notation)

```c
svfloat64x4_t svld4_vnum[_f64](svbool_t pg, const float64_t *base, int64_t vnum);
```

### Description

Load four-element tuples into four vectors

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
  "value": "svfloat64x4_t"
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
    "{Zresult0.D - Zresult3.D}": "result"
  }
]
```

### Instruction mapping

When vnum is a multiple of 4 in the range [-32, 28], this intrinsic can use:

```asm
LD4D {Zresult0.D - Zresult3.D}, Pg/Z, [Xbase, #vnum, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD4D--scalar-plus-immediate---Contiguous-load-four-doubleword-structures-to-four-vectors--immediate-index--

The general implementation is:

```asm
LD4D {Zresult0.D - Zresult3.D}, Pg/Z, [Xbase, Xindex, LSL #3]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD4D--scalar-plus-scalar---Contiguous-load-four-doubleword-structures-to-four-vectors--scalar-index--

### Operation

Source operation ID: `SveOperation_svld4_vnum_bf16`

**Operation**



Return a tuple of four *n*-element vectors in which each active element *i* of vector *j* contains `base[n * vnum + i * 4 + j]` and in which all other elements are zero.  Do not access memory for inactive elements.

## svld4_vnum[_mf8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld4_vnum%5B_mf8%5D

### Signature (source notation)

```c
svmfloat8x4_t svld4_vnum[_mf8](svbool_t pg, const mfloat8_t *base, int64_t vnum);
```

### Description

Load four-element tuples into four vectors

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
  "value": "svmfloat8x4_t"
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
    "{Zresult0.B - Zresult3.B}": "result"
  }
]
```

### Instruction mapping

When vnum is a multiple of 4 in the range [-32, 28], this intrinsic can use:

```asm
LD4B {Zresult0.B - Zresult3.B}, Pg/Z, [Xbase, #vnum, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD4B--scalar-plus-immediate---Contiguous-load-four-byte-structures-to-four-vectors--immediate-index--

The general implementation is:

```asm
LD4B {Zresult0.B - Zresult3.B}, Pg/Z, [Xbase, Xindex]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD4B--scalar-plus-scalar---Contiguous-load-four-byte-structures-to-four-vectors--scalar-index--

### Operation

Source operation ID: `SveOperation_svld4_vnum_bf16`

**Operation**



Return a tuple of four *n*-element vectors in which each active element *i* of vector *j* contains `base[n * vnum + i * 4 + j]` and in which all other elements are zero.  Do not access memory for inactive elements.

## svld4_vnum[_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld4_vnum%5B_s16%5D

### Signature (source notation)

```c
svint16x4_t svld4_vnum[_s16](svbool_t pg, const int16_t *base, int64_t vnum);
```

### Description

Load four-element tuples into four vectors

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
  "value": "svint16x4_t"
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
    "{Zresult0.H - Zresult3.H}": "result"
  }
]
```

### Instruction mapping

When vnum is a multiple of 4 in the range [-32, 28], this intrinsic can use:

```asm
LD4H {Zresult0.H - Zresult3.H}, Pg/Z, [Xbase, #vnum, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD4H--scalar-plus-immediate---Contiguous-load-four-halfword-structures-to-four-vectors--immediate-index--

The general implementation is:

```asm
LD4H {Zresult0.H - Zresult3.H}, Pg/Z, [Xbase, Xindex, LSL #1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD4H--scalar-plus-scalar---Contiguous-load-four-halfword-structures-to-four-vectors--scalar-index--

### Operation

Source operation ID: `SveOperation_svld4_vnum_bf16`

**Operation**



Return a tuple of four *n*-element vectors in which each active element *i* of vector *j* contains `base[n * vnum + i * 4 + j]` and in which all other elements are zero.  Do not access memory for inactive elements.

## svld4_vnum[_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld4_vnum%5B_s32%5D

### Signature (source notation)

```c
svint32x4_t svld4_vnum[_s32](svbool_t pg, const int32_t *base, int64_t vnum);
```

### Description

Load four-element tuples into four vectors

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
  "value": "svint32x4_t"
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
    "{Zresult0.S - Zresult3.S}": "result"
  }
]
```

### Instruction mapping

When vnum is a multiple of 4 in the range [-32, 28], this intrinsic can use:

```asm
LD4W {Zresult0.S - Zresult3.S}, Pg/Z, [Xbase, #vnum, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD4W--scalar-plus-immediate---Contiguous-load-four-word-structures-to-four-vectors--immediate-index--

The general implementation is:

```asm
LD4W {Zresult0.S - Zresult3.S}, Pg/Z, [Xbase, Xindex, LSL #2]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD4W--scalar-plus-scalar---Contiguous-load-four-word-structures-to-four-vectors--scalar-index--

### Operation

Source operation ID: `SveOperation_svld4_vnum_bf16`

**Operation**



Return a tuple of four *n*-element vectors in which each active element *i* of vector *j* contains `base[n * vnum + i * 4 + j]` and in which all other elements are zero.  Do not access memory for inactive elements.

## svld4_vnum[_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld4_vnum%5B_s64%5D

### Signature (source notation)

```c
svint64x4_t svld4_vnum[_s64](svbool_t pg, const int64_t *base, int64_t vnum);
```

### Description

Load four-element tuples into four vectors

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
  "value": "svint64x4_t"
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
    "{Zresult0.D - Zresult3.D}": "result"
  }
]
```

### Instruction mapping

When vnum is a multiple of 4 in the range [-32, 28], this intrinsic can use:

```asm
LD4D {Zresult0.D - Zresult3.D}, Pg/Z, [Xbase, #vnum, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD4D--scalar-plus-immediate---Contiguous-load-four-doubleword-structures-to-four-vectors--immediate-index--

The general implementation is:

```asm
LD4D {Zresult0.D - Zresult3.D}, Pg/Z, [Xbase, Xindex, LSL #3]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD4D--scalar-plus-scalar---Contiguous-load-four-doubleword-structures-to-four-vectors--scalar-index--

### Operation

Source operation ID: `SveOperation_svld4_vnum_bf16`

**Operation**



Return a tuple of four *n*-element vectors in which each active element *i* of vector *j* contains `base[n * vnum + i * 4 + j]` and in which all other elements are zero.  Do not access memory for inactive elements.

## svld4_vnum[_s8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld4_vnum%5B_s8%5D

### Signature (source notation)

```c
svint8x4_t svld4_vnum[_s8](svbool_t pg, const int8_t *base, int64_t vnum);
```

### Description

Load four-element tuples into four vectors

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
  "value": "svint8x4_t"
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
    "{Zresult0.B - Zresult3.B}": "result"
  }
]
```

### Instruction mapping

When vnum is a multiple of 4 in the range [-32, 28], this intrinsic can use:

```asm
LD4B {Zresult0.B - Zresult3.B}, Pg/Z, [Xbase, #vnum, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD4B--scalar-plus-immediate---Contiguous-load-four-byte-structures-to-four-vectors--immediate-index--

The general implementation is:

```asm
LD4B {Zresult0.B - Zresult3.B}, Pg/Z, [Xbase, Xindex]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD4B--scalar-plus-scalar---Contiguous-load-four-byte-structures-to-four-vectors--scalar-index--

### Operation

Source operation ID: `SveOperation_svld4_vnum_bf16`

**Operation**



Return a tuple of four *n*-element vectors in which each active element *i* of vector *j* contains `base[n * vnum + i * 4 + j]` and in which all other elements are zero.  Do not access memory for inactive elements.

## svld4_vnum[_u16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld4_vnum%5B_u16%5D

### Signature (source notation)

```c
svuint16x4_t svld4_vnum[_u16](svbool_t pg, const uint16_t *base, int64_t vnum);
```

### Description

Load four-element tuples into four vectors

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
  "value": "svuint16x4_t"
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
    "{Zresult0.H - Zresult3.H}": "result"
  }
]
```

### Instruction mapping

When vnum is a multiple of 4 in the range [-32, 28], this intrinsic can use:

```asm
LD4H {Zresult0.H - Zresult3.H}, Pg/Z, [Xbase, #vnum, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD4H--scalar-plus-immediate---Contiguous-load-four-halfword-structures-to-four-vectors--immediate-index--

The general implementation is:

```asm
LD4H {Zresult0.H - Zresult3.H}, Pg/Z, [Xbase, Xindex, LSL #1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD4H--scalar-plus-scalar---Contiguous-load-four-halfword-structures-to-four-vectors--scalar-index--

### Operation

Source operation ID: `SveOperation_svld4_vnum_bf16`

**Operation**



Return a tuple of four *n*-element vectors in which each active element *i* of vector *j* contains `base[n * vnum + i * 4 + j]` and in which all other elements are zero.  Do not access memory for inactive elements.

## svld4_vnum[_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld4_vnum%5B_u32%5D

### Signature (source notation)

```c
svuint32x4_t svld4_vnum[_u32](svbool_t pg, const uint32_t *base, int64_t vnum);
```

### Description

Load four-element tuples into four vectors

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
  "value": "svuint32x4_t"
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
    "{Zresult0.S - Zresult3.S}": "result"
  }
]
```

### Instruction mapping

When vnum is a multiple of 4 in the range [-32, 28], this intrinsic can use:

```asm
LD4W {Zresult0.S - Zresult3.S}, Pg/Z, [Xbase, #vnum, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD4W--scalar-plus-immediate---Contiguous-load-four-word-structures-to-four-vectors--immediate-index--

The general implementation is:

```asm
LD4W {Zresult0.S - Zresult3.S}, Pg/Z, [Xbase, Xindex, LSL #2]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD4W--scalar-plus-scalar---Contiguous-load-four-word-structures-to-four-vectors--scalar-index--

### Operation

Source operation ID: `SveOperation_svld4_vnum_bf16`

**Operation**



Return a tuple of four *n*-element vectors in which each active element *i* of vector *j* contains `base[n * vnum + i * 4 + j]` and in which all other elements are zero.  Do not access memory for inactive elements.

## svld4_vnum[_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld4_vnum%5B_u64%5D

### Signature (source notation)

```c
svuint64x4_t svld4_vnum[_u64](svbool_t pg, const uint64_t *base, int64_t vnum);
```

### Description

Load four-element tuples into four vectors

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
  "value": "svuint64x4_t"
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
    "{Zresult0.D - Zresult3.D}": "result"
  }
]
```

### Instruction mapping

When vnum is a multiple of 4 in the range [-32, 28], this intrinsic can use:

```asm
LD4D {Zresult0.D - Zresult3.D}, Pg/Z, [Xbase, #vnum, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD4D--scalar-plus-immediate---Contiguous-load-four-doubleword-structures-to-four-vectors--immediate-index--

The general implementation is:

```asm
LD4D {Zresult0.D - Zresult3.D}, Pg/Z, [Xbase, Xindex, LSL #3]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD4D--scalar-plus-scalar---Contiguous-load-four-doubleword-structures-to-four-vectors--scalar-index--

### Operation

Source operation ID: `SveOperation_svld4_vnum_bf16`

**Operation**



Return a tuple of four *n*-element vectors in which each active element *i* of vector *j* contains `base[n * vnum + i * 4 + j]` and in which all other elements are zero.  Do not access memory for inactive elements.

## svld4_vnum[_u8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld4_vnum%5B_u8%5D

### Signature (source notation)

```c
svuint8x4_t svld4_vnum[_u8](svbool_t pg, const uint8_t *base, int64_t vnum);
```

### Description

Load four-element tuples into four vectors

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
  "value": "svuint8x4_t"
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
    "{Zresult0.B - Zresult3.B}": "result"
  }
]
```

### Instruction mapping

When vnum is a multiple of 4 in the range [-32, 28], this intrinsic can use:

```asm
LD4B {Zresult0.B - Zresult3.B}, Pg/Z, [Xbase, #vnum, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD4B--scalar-plus-immediate---Contiguous-load-four-byte-structures-to-four-vectors--immediate-index--

The general implementation is:

```asm
LD4B {Zresult0.B - Zresult3.B}, Pg/Z, [Xbase, Xindex]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD4B--scalar-plus-scalar---Contiguous-load-four-byte-structures-to-four-vectors--scalar-index--

### Operation

Source operation ID: `SveOperation_svld4_vnum_bf16`

**Operation**



Return a tuple of four *n*-element vectors in which each active element *i* of vector *j* contains `base[n * vnum + i * 4 + j]` and in which all other elements are zero.  Do not access memory for inactive elements.

## svld4q[_bf16]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld4q%5B_bf16%5D

### Signature (source notation)

```c
svbfloat16x4_t svld4q[_bf16](svbool_t pg, bfloat16_t const * rn);
```

### Description

Contiguous load four-quadword structures to four vectors (immediate index)

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
  "value": "svbfloat16x4_t"
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
    "{ Zreg1.Q - Zreg2.Q }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
LD4Q { Zreg1.Q - Zreg2.Q }, Preg1/Z, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/LD4Q--scalar-plus-immediate---Contiguous-load-four-quadword-structures-to-four-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svld4q[_f16]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld4q%5B_f16%5D

### Signature (source notation)

```c
svfloat16x4_t svld4q[_f16](svbool_t pg, float16_t const * rn);
```

### Description

Contiguous load four-quadword structures to four vectors (immediate index)

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
  "value": "svfloat16x4_t"
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
    "{ Zreg1.Q - Zreg2.Q }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
LD4Q { Zreg1.Q - Zreg2.Q }, Preg1/Z, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/LD4Q--scalar-plus-immediate---Contiguous-load-four-quadword-structures-to-four-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svld4q[_f32]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld4q%5B_f32%5D

### Signature (source notation)

```c
svfloat32x4_t svld4q[_f32](svbool_t pg, float32_t const * rn);
```

### Description

Contiguous load four-quadword structures to four vectors (immediate index)

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
  "value": "svfloat32x4_t"
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
    "{ Zreg1.Q - Zreg2.Q }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
LD4Q { Zreg1.Q - Zreg2.Q }, Preg1/Z, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/LD4Q--scalar-plus-immediate---Contiguous-load-four-quadword-structures-to-four-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svld4q[_f64]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld4q%5B_f64%5D

### Signature (source notation)

```c
svfloat64x4_t svld4q[_f64](svbool_t pg, float64_t const * rn);
```

### Description

Contiguous load four-quadword structures to four vectors (immediate index)

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
  "value": "svfloat64x4_t"
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
    "{ Zreg1.Q - Zreg2.Q }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
LD4Q { Zreg1.Q - Zreg2.Q }, Preg1/Z, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/LD4Q--scalar-plus-immediate---Contiguous-load-four-quadword-structures-to-four-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svld4q[_mf8]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld4q%5B_mf8%5D

### Signature (source notation)

```c
svmfloat8x4_t svld4q[_mf8](svbool_t pg, mfloat8_t const * rn);
```

### Description

Contiguous load four-quadword structures to four vectors (immediate index)

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
  "value": "svmfloat8x4_t"
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
    "{ Zreg1.Q - Zreg2.Q }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
LD4Q { Zreg1.Q - Zreg2.Q }, Preg1/Z, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/LD4Q--scalar-plus-immediate---Contiguous-load-four-quadword-structures-to-four-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svld4q[_s16]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld4q%5B_s16%5D

### Signature (source notation)

```c
svint16x4_t svld4q[_s16](svbool_t pg, int16_t const * rn);
```

### Description

Contiguous load four-quadword structures to four vectors (immediate index)

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
  "value": "svint16x4_t"
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
    "{ Zreg1.Q - Zreg2.Q }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
LD4Q { Zreg1.Q - Zreg2.Q }, Preg1/Z, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/LD4Q--scalar-plus-immediate---Contiguous-load-four-quadword-structures-to-four-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svld4q[_s32]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld4q%5B_s32%5D

### Signature (source notation)

```c
svint32x4_t svld4q[_s32](svbool_t pg, int32_t const * rn);
```

### Description

Contiguous load four-quadword structures to four vectors (immediate index)

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
  "value": "svint32x4_t"
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
    "{ Zreg1.Q - Zreg2.Q }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
LD4Q { Zreg1.Q - Zreg2.Q }, Preg1/Z, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/LD4Q--scalar-plus-immediate---Contiguous-load-four-quadword-structures-to-four-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svld4q[_s64]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld4q%5B_s64%5D

### Signature (source notation)

```c
svint64x4_t svld4q[_s64](svbool_t pg, int64_t const * rn);
```

### Description

Contiguous load four-quadword structures to four vectors (immediate index)

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
  "value": "svint64x4_t"
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
    "{ Zreg1.Q - Zreg2.Q }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
LD4Q { Zreg1.Q - Zreg2.Q }, Preg1/Z, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/LD4Q--scalar-plus-immediate---Contiguous-load-four-quadword-structures-to-four-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svld4q[_s8]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld4q%5B_s8%5D

### Signature (source notation)

```c
svint8x4_t svld4q[_s8](svbool_t pg, int8_t const * rn);
```

### Description

Contiguous load four-quadword structures to four vectors (immediate index)

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
  "value": "svint8x4_t"
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
    "{ Zreg1.Q - Zreg2.Q }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
LD4Q { Zreg1.Q - Zreg2.Q }, Preg1/Z, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/LD4Q--scalar-plus-immediate---Contiguous-load-four-quadword-structures-to-four-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svld4q[_u16]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld4q%5B_u16%5D

### Signature (source notation)

```c
svuint16x4_t svld4q[_u16](svbool_t pg, uint16_t const * rn);
```

### Description

Contiguous load four-quadword structures to four vectors (immediate index)

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
  "value": "svuint16x4_t"
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
    "{ Zreg1.Q - Zreg2.Q }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
LD4Q { Zreg1.Q - Zreg2.Q }, Preg1/Z, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/LD4Q--scalar-plus-immediate---Contiguous-load-four-quadword-structures-to-four-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svld4q[_u32]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld4q%5B_u32%5D

### Signature (source notation)

```c
svuint32x4_t svld4q[_u32](svbool_t pg, uint32_t const * rn);
```

### Description

Contiguous load four-quadword structures to four vectors (immediate index)

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
  "value": "svuint32x4_t"
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
    "{ Zreg1.Q - Zreg2.Q }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
LD4Q { Zreg1.Q - Zreg2.Q }, Preg1/Z, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/LD4Q--scalar-plus-immediate---Contiguous-load-four-quadword-structures-to-four-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svld4q[_u64]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld4q%5B_u64%5D

### Signature (source notation)

```c
svuint64x4_t svld4q[_u64](svbool_t pg, uint64_t const * rn);
```

### Description

Contiguous load four-quadword structures to four vectors (immediate index)

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
  "value": "svuint64x4_t"
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
    "{ Zreg1.Q - Zreg2.Q }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
LD4Q { Zreg1.Q - Zreg2.Q }, Preg1/Z, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/LD4Q--scalar-plus-immediate---Contiguous-load-four-quadword-structures-to-four-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svld4q[_u8]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld4q%5B_u8%5D

### Signature (source notation)

```c
svuint8x4_t svld4q[_u8](svbool_t pg, uint8_t const * rn);
```

### Description

Contiguous load four-quadword structures to four vectors (immediate index)

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
  "value": "svuint8x4_t"
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
    "{ Zreg1.Q - Zreg2.Q }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
LD4Q { Zreg1.Q - Zreg2.Q }, Preg1/Z, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/LD4Q--scalar-plus-immediate---Contiguous-load-four-quadword-structures-to-four-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svld4q_vnum[_bf16]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld4q_vnum%5B_bf16%5D

### Signature (source notation)

```c
svbfloat16x4_t svld4q_vnum[_bf16](svbool_t pg, bfloat16_t const * rn, int64_t vnum);
```

### Description

Contiguous load four-quadword structures to four vectors (immediate index)

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
  "value": "svbfloat16x4_t"
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
    "{ Zreg1.Q - Zreg2.Q }": "result"
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
LD4Q { Zreg1.Q - Zreg2.Q }, Preg1/Z, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/LD4Q--scalar-plus-immediate---Contiguous-load-four-quadword-structures-to-four-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svld4q_vnum[_f16]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld4q_vnum%5B_f16%5D

### Signature (source notation)

```c
svfloat16x4_t svld4q_vnum[_f16](svbool_t pg, float16_t const * rn, int64_t vnum);
```

### Description

Contiguous load four-quadword structures to four vectors (immediate index)

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
  "value": "svfloat16x4_t"
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
    "{ Zreg1.Q - Zreg2.Q }": "result"
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
LD4Q { Zreg1.Q - Zreg2.Q }, Preg1/Z, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/LD4Q--scalar-plus-immediate---Contiguous-load-four-quadword-structures-to-four-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svld4q_vnum[_f32]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld4q_vnum%5B_f32%5D

### Signature (source notation)

```c
svfloat32x4_t svld4q_vnum[_f32](svbool_t pg, float32_t const * rn, int64_t vnum);
```

### Description

Contiguous load four-quadword structures to four vectors (immediate index)

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
  "value": "svfloat32x4_t"
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
    "{ Zreg1.Q - Zreg2.Q }": "result"
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
LD4Q { Zreg1.Q - Zreg2.Q }, Preg1/Z, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/LD4Q--scalar-plus-immediate---Contiguous-load-four-quadword-structures-to-four-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svld4q_vnum[_f64]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld4q_vnum%5B_f64%5D

### Signature (source notation)

```c
svfloat64x4_t svld4q_vnum[_f64](svbool_t pg, float64_t const * rn, int64_t vnum);
```

### Description

Contiguous load four-quadword structures to four vectors (immediate index)

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
  "value": "svfloat64x4_t"
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
    "{ Zreg1.Q - Zreg2.Q }": "result"
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
LD4Q { Zreg1.Q - Zreg2.Q }, Preg1/Z, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/LD4Q--scalar-plus-immediate---Contiguous-load-four-quadword-structures-to-four-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svld4q_vnum[_mf8]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld4q_vnum%5B_mf8%5D

### Signature (source notation)

```c
svmfloat8x4_t svld4q_vnum[_mf8](svbool_t pg, mfloat8_t const * rn, int64_t vnum);
```

### Description

Contiguous load four-quadword structures to four vectors (immediate index)

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
  "value": "svmfloat8x4_t"
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
    "{ Zreg1.Q - Zreg2.Q }": "result"
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
LD4Q { Zreg1.Q - Zreg2.Q }, Preg1/Z, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/LD4Q--scalar-plus-immediate---Contiguous-load-four-quadword-structures-to-four-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svld4q_vnum[_s16]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld4q_vnum%5B_s16%5D

### Signature (source notation)

```c
svint16x4_t svld4q_vnum[_s16](svbool_t pg, int16_t const * rn, int64_t vnum);
```

### Description

Contiguous load four-quadword structures to four vectors (immediate index)

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
  "value": "svint16x4_t"
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
    "{ Zreg1.Q - Zreg2.Q }": "result"
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
LD4Q { Zreg1.Q - Zreg2.Q }, Preg1/Z, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/LD4Q--scalar-plus-immediate---Contiguous-load-four-quadword-structures-to-four-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svld4q_vnum[_s32]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld4q_vnum%5B_s32%5D

### Signature (source notation)

```c
svint32x4_t svld4q_vnum[_s32](svbool_t pg, int32_t const * rn, int64_t vnum);
```

### Description

Contiguous load four-quadword structures to four vectors (immediate index)

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
  "value": "svint32x4_t"
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
    "{ Zreg1.Q - Zreg2.Q }": "result"
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
LD4Q { Zreg1.Q - Zreg2.Q }, Preg1/Z, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/LD4Q--scalar-plus-immediate---Contiguous-load-four-quadword-structures-to-four-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svld4q_vnum[_s64]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld4q_vnum%5B_s64%5D

### Signature (source notation)

```c
svint64x4_t svld4q_vnum[_s64](svbool_t pg, int64_t const * rn, int64_t vnum);
```

### Description

Contiguous load four-quadword structures to four vectors (immediate index)

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
  "value": "svint64x4_t"
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
    "{ Zreg1.Q - Zreg2.Q }": "result"
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
LD4Q { Zreg1.Q - Zreg2.Q }, Preg1/Z, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/LD4Q--scalar-plus-immediate---Contiguous-load-four-quadword-structures-to-four-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svld4q_vnum[_s8]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld4q_vnum%5B_s8%5D

### Signature (source notation)

```c
svint8x4_t svld4q_vnum[_s8](svbool_t pg, int8_t const * rn, int64_t vnum);
```

### Description

Contiguous load four-quadword structures to four vectors (immediate index)

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
  "value": "svint8x4_t"
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
    "{ Zreg1.Q - Zreg2.Q }": "result"
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
LD4Q { Zreg1.Q - Zreg2.Q }, Preg1/Z, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/LD4Q--scalar-plus-immediate---Contiguous-load-four-quadword-structures-to-four-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svld4q_vnum[_u16]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld4q_vnum%5B_u16%5D

### Signature (source notation)

```c
svuint16x4_t svld4q_vnum[_u16](svbool_t pg, uint16_t const * rn, int64_t vnum);
```

### Description

Contiguous load four-quadword structures to four vectors (immediate index)

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
  "value": "svuint16x4_t"
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
    "{ Zreg1.Q - Zreg2.Q }": "result"
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
LD4Q { Zreg1.Q - Zreg2.Q }, Preg1/Z, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/LD4Q--scalar-plus-immediate---Contiguous-load-four-quadword-structures-to-four-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svld4q_vnum[_u32]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld4q_vnum%5B_u32%5D

### Signature (source notation)

```c
svuint32x4_t svld4q_vnum[_u32](svbool_t pg, uint32_t const * rn, int64_t vnum);
```

### Description

Contiguous load four-quadword structures to four vectors (immediate index)

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
  "value": "svuint32x4_t"
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
    "{ Zreg1.Q - Zreg2.Q }": "result"
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
LD4Q { Zreg1.Q - Zreg2.Q }, Preg1/Z, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/LD4Q--scalar-plus-immediate---Contiguous-load-four-quadword-structures-to-four-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

