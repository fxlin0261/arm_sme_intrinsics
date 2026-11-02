# SME / Load / Load and replicate — Part 1

## svld1rq[_bf16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld1rq%5B_bf16%5D

### Signature (source notation)

```c
svbfloat16_t svld1rq[_bf16](svbool_t pg, const bfloat16_t *base);
```

### Description

Load and replicate 128 bits of data

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Load / Load and replicate

- SME attributes: Not specified by source.

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
  "value": "svbfloat16_t"
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
LD1RQH Zresult.H, Pg/Z, [Xarray, Xindex, LSL #1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1RQH--scalar-plus-scalar---Contiguous-load-and-replicate-eight-halfwords--scalar-index--

When base has the form &array[index] and index is in the range [-8, 7], this intrinsic can use:

```asm
LD1RQH Zresult.H, Pg/Z, [Xarray, #index * 2]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1RQH--scalar-plus-immediate---Contiguous-load-and-replicate-eight-halfwords--immediate-index--

The general implementation is:

```asm
LD1RQH Zresult.H, Pg/Z, [Xbase, #0]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1RQH--scalar-plus-immediate---Contiguous-load-and-replicate-eight-halfwords--immediate-index--

### Operation

Source operation ID: `SveOperation_svld1rq_bf16`

**Operation**




- Load 128 bits of data from `base` under the control of `pg`, setting inactive elements in the 128 bits to zero.  (Any higher-indexed elements of `pg` have no effect.)
- Duplicate the 128 bits of data to fill a vector and return the result.

## svld1rq[_f16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld1rq%5B_f16%5D

### Signature (source notation)

```c
svfloat16_t svld1rq[_f16](svbool_t pg, const float16_t *base);
```

### Description

Load and replicate 128 bits of data

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Load / Load and replicate

- SME attributes: Not specified by source.

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
LD1RQH Zresult.H, Pg/Z, [Xarray, Xindex, LSL #1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1RQH--scalar-plus-scalar---Contiguous-load-and-replicate-eight-halfwords--scalar-index--

When base has the form &array[index] and index is in the range [-8, 7], this intrinsic can use:

```asm
LD1RQH Zresult.H, Pg/Z, [Xarray, #index * 2]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1RQH--scalar-plus-immediate---Contiguous-load-and-replicate-eight-halfwords--immediate-index--

The general implementation is:

```asm
LD1RQH Zresult.H, Pg/Z, [Xbase, #0]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1RQH--scalar-plus-immediate---Contiguous-load-and-replicate-eight-halfwords--immediate-index--

### Operation

Source operation ID: `SveOperation_svld1rq_bf16`

**Operation**




- Load 128 bits of data from `base` under the control of `pg`, setting inactive elements in the 128 bits to zero.  (Any higher-indexed elements of `pg` have no effect.)
- Duplicate the 128 bits of data to fill a vector and return the result.

## svld1rq[_f32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld1rq%5B_f32%5D

### Signature (source notation)

```c
svfloat32_t svld1rq[_f32](svbool_t pg, const float32_t *base);
```

### Description

Load and replicate 128 bits of data

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Load / Load and replicate

- SME attributes: Not specified by source.

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
LD1RQW Zresult.S, Pg/Z, [Xarray, Xindex, LSL #2]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1RQW--scalar-plus-scalar---Contiguous-load-and-replicate-four-words--scalar-index--

When base has the form &array[index] and index is in the range [-8, 7], this intrinsic can use:

```asm
LD1RQW Zresult.S, Pg/Z, [Xarray, #index * 4]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1RQW--scalar-plus-immediate---Contiguous-load-and-replicate-four-words--immediate-index--

The general implementation is:

```asm
LD1RQW Zresult.S, Pg/Z, [Xbase, #0]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1RQW--scalar-plus-immediate---Contiguous-load-and-replicate-four-words--immediate-index--

### Operation

Source operation ID: `SveOperation_svld1rq_bf16`

**Operation**




- Load 128 bits of data from `base` under the control of `pg`, setting inactive elements in the 128 bits to zero.  (Any higher-indexed elements of `pg` have no effect.)
- Duplicate the 128 bits of data to fill a vector and return the result.

## svld1rq[_f64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld1rq%5B_f64%5D

### Signature (source notation)

```c
svfloat64_t svld1rq[_f64](svbool_t pg, const float64_t *base);
```

### Description

Load and replicate 128 bits of data

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Load / Load and replicate

- SME attributes: Not specified by source.

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
LD1RQD Zresult.D, Pg/Z, [Xarray, Xindex, LSL #3]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1RQD--scalar-plus-scalar---Contiguous-load-and-replicate-two-doublewords--scalar-index--

When base has the form &array[index] and index is in the range [-8, 7], this intrinsic can use:

```asm
LD1RQD Zresult.D, Pg/Z, [Xarray, #index * 8]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1RQD--scalar-plus-immediate---Contiguous-load-and-replicate-two-doublewords--immediate-index--

The general implementation is:

```asm
LD1RQD Zresult.D, Pg/Z, [Xbase, #0]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1RQD--scalar-plus-immediate---Contiguous-load-and-replicate-two-doublewords--immediate-index--

### Operation

Source operation ID: `SveOperation_svld1rq_bf16`

**Operation**




- Load 128 bits of data from `base` under the control of `pg`, setting inactive elements in the 128 bits to zero.  (Any higher-indexed elements of `pg` have no effect.)
- Duplicate the 128 bits of data to fill a vector and return the result.

## svld1rq[_mf8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld1rq%5B_mf8%5D

### Signature (source notation)

```c
svmfloat8_t svld1rq[_mf8](svbool_t pg, const mfloat8_t *base);
```

### Description

Load and replicate 128 bits of data

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Load / Load and replicate

- SME attributes: Not specified by source.

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
  "value": "svmfloat8_t"
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
    "Zresult.B": "result"
  }
]
```

### Instruction mapping

When base has the form &array[index], this intrinsic can use:

```asm
LD1RQB Zresult.B, Pg/Z, [Xarray, Xindex]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1RQB--scalar-plus-scalar---Contiguous-load-and-replicate-sixteen-bytes--scalar-index--

When base has the form &array[index] and index is in the range [-8, 7], this intrinsic can use:

```asm
LD1RQB Zresult.B, Pg/Z, [Xarray, #index]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1RQB--scalar-plus-immediate---Contiguous-load-and-replicate-sixteen-bytes--immediate-index--

The general implementation is:

```asm
LD1RQB Zresult.B, Pg/Z, [Xbase, #0]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1RQB--scalar-plus-immediate---Contiguous-load-and-replicate-sixteen-bytes--immediate-index--

### Operation

Source operation ID: `SveOperation_svld1rq_bf16`

**Operation**




- Load 128 bits of data from `base` under the control of `pg`, setting inactive elements in the 128 bits to zero.  (Any higher-indexed elements of `pg` have no effect.)
- Duplicate the 128 bits of data to fill a vector and return the result.

## svld1rq[_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld1rq%5B_s16%5D

### Signature (source notation)

```c
svint16_t svld1rq[_s16](svbool_t pg, const int16_t *base);
```

### Description

Load and replicate 128 bits of data

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Load / Load and replicate

- SME attributes: Not specified by source.

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
LD1RQH Zresult.H, Pg/Z, [Xarray, Xindex, LSL #1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1RQH--scalar-plus-scalar---Contiguous-load-and-replicate-eight-halfwords--scalar-index--

When base has the form &array[index] and index is in the range [-8, 7], this intrinsic can use:

```asm
LD1RQH Zresult.H, Pg/Z, [Xarray, #index * 2]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1RQH--scalar-plus-immediate---Contiguous-load-and-replicate-eight-halfwords--immediate-index--

The general implementation is:

```asm
LD1RQH Zresult.H, Pg/Z, [Xbase, #0]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1RQH--scalar-plus-immediate---Contiguous-load-and-replicate-eight-halfwords--immediate-index--

### Operation

Source operation ID: `SveOperation_svld1rq_bf16`

**Operation**




- Load 128 bits of data from `base` under the control of `pg`, setting inactive elements in the 128 bits to zero.  (Any higher-indexed elements of `pg` have no effect.)
- Duplicate the 128 bits of data to fill a vector and return the result.

## svld1rq[_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld1rq%5B_s32%5D

### Signature (source notation)

```c
svint32_t svld1rq[_s32](svbool_t pg, const int32_t *base);
```

### Description

Load and replicate 128 bits of data

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Load / Load and replicate

- SME attributes: Not specified by source.

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
LD1RQW Zresult.S, Pg/Z, [Xarray, Xindex, LSL #2]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1RQW--scalar-plus-scalar---Contiguous-load-and-replicate-four-words--scalar-index--

When base has the form &array[index] and index is in the range [-8, 7], this intrinsic can use:

```asm
LD1RQW Zresult.S, Pg/Z, [Xarray, #index * 4]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1RQW--scalar-plus-immediate---Contiguous-load-and-replicate-four-words--immediate-index--

The general implementation is:

```asm
LD1RQW Zresult.S, Pg/Z, [Xbase, #0]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1RQW--scalar-plus-immediate---Contiguous-load-and-replicate-four-words--immediate-index--

### Operation

Source operation ID: `SveOperation_svld1rq_bf16`

**Operation**




- Load 128 bits of data from `base` under the control of `pg`, setting inactive elements in the 128 bits to zero.  (Any higher-indexed elements of `pg` have no effect.)
- Duplicate the 128 bits of data to fill a vector and return the result.

## svld1rq[_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld1rq%5B_s64%5D

### Signature (source notation)

```c
svint64_t svld1rq[_s64](svbool_t pg, const int64_t *base);
```

### Description

Load and replicate 128 bits of data

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Load / Load and replicate

- SME attributes: Not specified by source.

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
LD1RQD Zresult.D, Pg/Z, [Xarray, Xindex, LSL #3]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1RQD--scalar-plus-scalar---Contiguous-load-and-replicate-two-doublewords--scalar-index--

When base has the form &array[index] and index is in the range [-8, 7], this intrinsic can use:

```asm
LD1RQD Zresult.D, Pg/Z, [Xarray, #index * 8]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1RQD--scalar-plus-immediate---Contiguous-load-and-replicate-two-doublewords--immediate-index--

The general implementation is:

```asm
LD1RQD Zresult.D, Pg/Z, [Xbase, #0]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1RQD--scalar-plus-immediate---Contiguous-load-and-replicate-two-doublewords--immediate-index--

### Operation

Source operation ID: `SveOperation_svld1rq_bf16`

**Operation**




- Load 128 bits of data from `base` under the control of `pg`, setting inactive elements in the 128 bits to zero.  (Any higher-indexed elements of `pg` have no effect.)
- Duplicate the 128 bits of data to fill a vector and return the result.

## svld1rq[_s8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld1rq%5B_s8%5D

### Signature (source notation)

```c
svint8_t svld1rq[_s8](svbool_t pg, const int8_t *base);
```

### Description

Load and replicate 128 bits of data

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Load / Load and replicate

- SME attributes: Not specified by source.

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
  "base": {
    "register": "Xbase"
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

When base has the form &array[index], this intrinsic can use:

```asm
LD1RQB Zresult.B, Pg/Z, [Xarray, Xindex]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1RQB--scalar-plus-scalar---Contiguous-load-and-replicate-sixteen-bytes--scalar-index--

When base has the form &array[index] and index is in the range [-8, 7], this intrinsic can use:

```asm
LD1RQB Zresult.B, Pg/Z, [Xarray, #index]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1RQB--scalar-plus-immediate---Contiguous-load-and-replicate-sixteen-bytes--immediate-index--

The general implementation is:

```asm
LD1RQB Zresult.B, Pg/Z, [Xbase, #0]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1RQB--scalar-plus-immediate---Contiguous-load-and-replicate-sixteen-bytes--immediate-index--

### Operation

Source operation ID: `SveOperation_svld1rq_bf16`

**Operation**




- Load 128 bits of data from `base` under the control of `pg`, setting inactive elements in the 128 bits to zero.  (Any higher-indexed elements of `pg` have no effect.)
- Duplicate the 128 bits of data to fill a vector and return the result.

## svld1rq[_u16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld1rq%5B_u16%5D

### Signature (source notation)

```c
svuint16_t svld1rq[_u16](svbool_t pg, const uint16_t *base);
```

### Description

Load and replicate 128 bits of data

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Load / Load and replicate

- SME attributes: Not specified by source.

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
LD1RQH Zresult.H, Pg/Z, [Xarray, Xindex, LSL #1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1RQH--scalar-plus-scalar---Contiguous-load-and-replicate-eight-halfwords--scalar-index--

When base has the form &array[index] and index is in the range [-8, 7], this intrinsic can use:

```asm
LD1RQH Zresult.H, Pg/Z, [Xarray, #index * 2]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1RQH--scalar-plus-immediate---Contiguous-load-and-replicate-eight-halfwords--immediate-index--

The general implementation is:

```asm
LD1RQH Zresult.H, Pg/Z, [Xbase, #0]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1RQH--scalar-plus-immediate---Contiguous-load-and-replicate-eight-halfwords--immediate-index--

### Operation

Source operation ID: `SveOperation_svld1rq_bf16`

**Operation**




- Load 128 bits of data from `base` under the control of `pg`, setting inactive elements in the 128 bits to zero.  (Any higher-indexed elements of `pg` have no effect.)
- Duplicate the 128 bits of data to fill a vector and return the result.

## svld1rq[_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld1rq%5B_u32%5D

### Signature (source notation)

```c
svuint32_t svld1rq[_u32](svbool_t pg, const uint32_t *base);
```

### Description

Load and replicate 128 bits of data

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Load / Load and replicate

- SME attributes: Not specified by source.

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
LD1RQW Zresult.S, Pg/Z, [Xarray, Xindex, LSL #2]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1RQW--scalar-plus-scalar---Contiguous-load-and-replicate-four-words--scalar-index--

When base has the form &array[index] and index is in the range [-8, 7], this intrinsic can use:

```asm
LD1RQW Zresult.S, Pg/Z, [Xarray, #index * 4]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1RQW--scalar-plus-immediate---Contiguous-load-and-replicate-four-words--immediate-index--

The general implementation is:

```asm
LD1RQW Zresult.S, Pg/Z, [Xbase, #0]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1RQW--scalar-plus-immediate---Contiguous-load-and-replicate-four-words--immediate-index--

### Operation

Source operation ID: `SveOperation_svld1rq_bf16`

**Operation**




- Load 128 bits of data from `base` under the control of `pg`, setting inactive elements in the 128 bits to zero.  (Any higher-indexed elements of `pg` have no effect.)
- Duplicate the 128 bits of data to fill a vector and return the result.

## svld1rq[_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld1rq%5B_u64%5D

### Signature (source notation)

```c
svuint64_t svld1rq[_u64](svbool_t pg, const uint64_t *base);
```

### Description

Load and replicate 128 bits of data

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Load / Load and replicate

- SME attributes: Not specified by source.

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
LD1RQD Zresult.D, Pg/Z, [Xarray, Xindex, LSL #3]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1RQD--scalar-plus-scalar---Contiguous-load-and-replicate-two-doublewords--scalar-index--

When base has the form &array[index] and index is in the range [-8, 7], this intrinsic can use:

```asm
LD1RQD Zresult.D, Pg/Z, [Xarray, #index * 8]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1RQD--scalar-plus-immediate---Contiguous-load-and-replicate-two-doublewords--immediate-index--

The general implementation is:

```asm
LD1RQD Zresult.D, Pg/Z, [Xbase, #0]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1RQD--scalar-plus-immediate---Contiguous-load-and-replicate-two-doublewords--immediate-index--

### Operation

Source operation ID: `SveOperation_svld1rq_bf16`

**Operation**




- Load 128 bits of data from `base` under the control of `pg`, setting inactive elements in the 128 bits to zero.  (Any higher-indexed elements of `pg` have no effect.)
- Duplicate the 128 bits of data to fill a vector and return the result.

## svld1rq[_u8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld1rq%5B_u8%5D

### Signature (source notation)

```c
svuint8_t svld1rq[_u8](svbool_t pg, const uint8_t *base);
```

### Description

Load and replicate 128 bits of data

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Load / Load and replicate

- SME attributes: Not specified by source.

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
  "base": {
    "register": "Xbase"
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

When base has the form &array[index], this intrinsic can use:

```asm
LD1RQB Zresult.B, Pg/Z, [Xarray, Xindex]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1RQB--scalar-plus-scalar---Contiguous-load-and-replicate-sixteen-bytes--scalar-index--

When base has the form &array[index] and index is in the range [-8, 7], this intrinsic can use:

```asm
LD1RQB Zresult.B, Pg/Z, [Xarray, #index]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1RQB--scalar-plus-immediate---Contiguous-load-and-replicate-sixteen-bytes--immediate-index--

The general implementation is:

```asm
LD1RQB Zresult.B, Pg/Z, [Xbase, #0]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1RQB--scalar-plus-immediate---Contiguous-load-and-replicate-sixteen-bytes--immediate-index--

### Operation

Source operation ID: `SveOperation_svld1rq_bf16`

**Operation**




- Load 128 bits of data from `base` under the control of `pg`, setting inactive elements in the 128 bits to zero.  (Any higher-indexed elements of `pg` have no effect.)
- Duplicate the 128 bits of data to fill a vector and return the result.

