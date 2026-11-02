# SME / Load / Consecutive — Part 1

## svld1[_bf16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld1%5B_bf16%5D

### Signature (source notation)

```c
svbfloat16_t svld1[_bf16](svbool_t pg, const bfloat16_t *base);
```

### Description

Unextended load

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
LD1H Zresult.H, Pg/Z, [Xarray, Xindex, LSL #1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1H--scalar-plus-scalar--consecutive-registers---Contiguous-load-of-halfwords-to-multiple-consecutive-vectors--scalar-index--

The general implementation is:

```asm
LD1H Zresult.H, Pg/Z, [Xbase, #0, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1H--scalar-plus-immediate--consecutive-registers---Contiguous-load-of-halfwords-to-multiple-consecutive-vectors--immediate-index--

### Operation

Source operation ID: `SveOperation_svld1_bf16`

**Operation**



Return a vector in which each active element *i* contains `base[i]` and in which all other elements are zero.  Do not access memory for inactive elements.

## svld1[_bf16]_x2

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld1%5B_bf16%5D_x2

### Signature (source notation)

```c
svbfloat16x2_t svld1[_bf16]_x2(svcount_t png, bfloat16_t const * rn);
```

### Description

Contiguous load of halfwords to multiple consecutive vectors (immediate index)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Load / Consecutive

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p1)|FEAT_SME2
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
  "png": {
    "register": "PNreg1"
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
    "{ Zreg1.H, Zreg2.H }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
LD1H { Zreg1.H, Zreg2.H }, PNreg1/Z, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1H--scalar-plus-immediate--consecutive-registers---Contiguous-load-of-halfwords-to-multiple-consecutive-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svld1[_bf16]_x4

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld1%5B_bf16%5D_x4

### Signature (source notation)

```c
svbfloat16x4_t svld1[_bf16]_x4(svcount_t png, bfloat16_t const * rn);
```

### Description

Contiguous load of halfwords to multiple consecutive vectors (immediate index)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Load / Consecutive

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p1)|FEAT_SME2
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
  "png": {
    "register": "PNreg1"
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
    "{ Zreg1.H - Zreg2.H }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
LD1H { Zreg1.H - Zreg2.H }, PNreg1/Z, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1H--scalar-plus-immediate--consecutive-registers---Contiguous-load-of-halfwords-to-multiple-consecutive-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svld1[_f16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld1%5B_f16%5D

### Signature (source notation)

```c
svfloat16_t svld1[_f16](svbool_t pg, const float16_t *base);
```

### Description

Unextended load

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
LD1H Zresult.H, Pg/Z, [Xarray, Xindex, LSL #1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1H--scalar-plus-scalar--consecutive-registers---Contiguous-load-of-halfwords-to-multiple-consecutive-vectors--scalar-index--

The general implementation is:

```asm
LD1H Zresult.H, Pg/Z, [Xbase, #0, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1H--scalar-plus-immediate--consecutive-registers---Contiguous-load-of-halfwords-to-multiple-consecutive-vectors--immediate-index--

### Operation

Source operation ID: `SveOperation_svld1_bf16`

**Operation**



Return a vector in which each active element *i* contains `base[i]` and in which all other elements are zero.  Do not access memory for inactive elements.

## svld1[_f16]_x2

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld1%5B_f16%5D_x2

### Signature (source notation)

```c
svfloat16x2_t svld1[_f16]_x2(svcount_t png, float16_t const * rn);
```

### Description

Contiguous load of halfwords to multiple consecutive vectors (immediate index)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Load / Consecutive

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p1)|FEAT_SME2
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
  "png": {
    "register": "PNreg1"
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
    "{ Zreg1.H, Zreg2.H }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
LD1H { Zreg1.H, Zreg2.H }, PNreg1/Z, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1H--scalar-plus-immediate--consecutive-registers---Contiguous-load-of-halfwords-to-multiple-consecutive-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svld1[_f16]_x4

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld1%5B_f16%5D_x4

### Signature (source notation)

```c
svfloat16x4_t svld1[_f16]_x4(svcount_t png, float16_t const * rn);
```

### Description

Contiguous load of halfwords to multiple consecutive vectors (immediate index)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Load / Consecutive

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p1)|FEAT_SME2
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
  "png": {
    "register": "PNreg1"
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
    "{ Zreg1.H - Zreg2.H }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
LD1H { Zreg1.H - Zreg2.H }, PNreg1/Z, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1H--scalar-plus-immediate--consecutive-registers---Contiguous-load-of-halfwords-to-multiple-consecutive-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svld1[_f32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld1%5B_f32%5D

### Signature (source notation)

```c
svfloat32_t svld1[_f32](svbool_t pg, const float32_t *base);
```

### Description

Unextended load

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
LD1W Zresult.S, Pg/Z, [Xarray, Xindex, LSL #2]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1W--scalar-plus-scalar--consecutive-registers---Contiguous-load-of-words-to-multiple-consecutive-vectors--scalar-index--

The general implementation is:

```asm
LD1W Zresult.S, Pg/Z, [Xbase, #0, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1W--scalar-plus-immediate--consecutive-registers---Contiguous-load-of-words-to-multiple-consecutive-vectors--immediate-index--

### Operation

Source operation ID: `SveOperation_svld1_bf16`

**Operation**



Return a vector in which each active element *i* contains `base[i]` and in which all other elements are zero.  Do not access memory for inactive elements.

## svld1[_f32]_x2

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld1%5B_f32%5D_x2

### Signature (source notation)

```c
svfloat32x2_t svld1[_f32]_x2(svcount_t png, float32_t const * rn);
```

### Description

Contiguous load of words to multiple consecutive vectors (immediate index)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Load / Consecutive

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p1)|FEAT_SME2
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
  "png": {
    "register": "PNreg1"
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
    "{ Zreg1.S, Zreg2.S }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
LD1W { Zreg1.S, Zreg2.S }, PNreg1/Z, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1W--scalar-plus-immediate--consecutive-registers---Contiguous-load-of-words-to-multiple-consecutive-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svld1[_f32]_x4

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld1%5B_f32%5D_x4

### Signature (source notation)

```c
svfloat32x4_t svld1[_f32]_x4(svcount_t png, float32_t const * rn);
```

### Description

Contiguous load of words to multiple consecutive vectors (immediate index)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Load / Consecutive

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p1)|FEAT_SME2
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
  "png": {
    "register": "PNreg1"
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
    "{ Zreg1.S - Zreg2.S }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
LD1W { Zreg1.S - Zreg2.S }, PNreg1/Z, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1W--scalar-plus-immediate--consecutive-registers---Contiguous-load-of-words-to-multiple-consecutive-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svld1[_f64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld1%5B_f64%5D

### Signature (source notation)

```c
svfloat64_t svld1[_f64](svbool_t pg, const float64_t *base);
```

### Description

Unextended load

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
LD1D Zresult.D, Pg/Z, [Xarray, Xindex, LSL #3]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1D--scalar-plus-scalar--consecutive-registers---Contiguous-load-of-doublewords-to-multiple-consecutive-vectors--scalar-index--

The general implementation is:

```asm
LD1D Zresult.D, Pg/Z, [Xbase, #0, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1D--scalar-plus-immediate--consecutive-registers---Contiguous-load-of-doublewords-to-multiple-consecutive-vectors--immediate-index--

### Operation

Source operation ID: `SveOperation_svld1_bf16`

**Operation**



Return a vector in which each active element *i* contains `base[i]` and in which all other elements are zero.  Do not access memory for inactive elements.

## svld1[_f64]_x2

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld1%5B_f64%5D_x2

### Signature (source notation)

```c
svfloat64x2_t svld1[_f64]_x2(svcount_t png, float64_t const * rn);
```

### Description

Contiguous load of doublewords to multiple consecutive vectors (immediate index)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Load / Consecutive

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p1)|FEAT_SME2
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
  "png": {
    "register": "PNreg1"
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
    "{ Zreg1.D, Zreg2.D }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
LD1D { Zreg1.D, Zreg2.D }, PNreg1/Z, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1D--scalar-plus-immediate--consecutive-registers---Contiguous-load-of-doublewords-to-multiple-consecutive-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svld1[_f64]_x4

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld1%5B_f64%5D_x4

### Signature (source notation)

```c
svfloat64x4_t svld1[_f64]_x4(svcount_t png, float64_t const * rn);
```

### Description

Contiguous load of doublewords to multiple consecutive vectors (immediate index)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Load / Consecutive

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p1)|FEAT_SME2
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
  "png": {
    "register": "PNreg1"
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
    "{ Zreg1.D - Zreg2.D }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
LD1D { Zreg1.D - Zreg2.D }, PNreg1/Z, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1D--scalar-plus-immediate--consecutive-registers---Contiguous-load-of-doublewords-to-multiple-consecutive-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svld1[_mf8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld1%5B_mf8%5D

### Signature (source notation)

```c
svmfloat8_t svld1[_mf8](svbool_t pg, const mfloat8_t *base);
```

### Description

Unextended load

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
LD1B Zresult.B, Pg/Z, [Xarray, Xindex]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1B--scalar-plus-scalar--consecutive-registers---Contiguous-load-of-bytes-to-multiple-consecutive-vectors--scalar-index--

The general implementation is:

```asm
LD1B Zresult.B, Pg/Z, [Xbase, #0, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1B--scalar-plus-immediate--single-register---Contiguous-load-unsigned-bytes-to-vector--immediate-index--

### Operation

Source operation ID: `SveOperation_svld1_bf16`

**Operation**



Return a vector in which each active element *i* contains `base[i]` and in which all other elements are zero.  Do not access memory for inactive elements.

## svld1[_mf8]_x2

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld1%5B_mf8%5D_x2

### Signature (source notation)

```c
svmfloat8x2_t svld1[_mf8]_x2(svcount_t png, mfloat8_t const * rn);
```

### Description

Contiguous load of bytes to multiple consecutive vectors (immediate index)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Load / Consecutive

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p1)|FEAT_SME2
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
  "png": {
    "register": "PNreg1"
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
    "{ Zreg1.B, Zreg2.B }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
LD1B { Zreg1.B, Zreg2.B }, PNreg1/Z, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1B--scalar-plus-immediate--consecutive-registers---Contiguous-load-of-bytes-to-multiple-consecutive-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svld1[_mf8]_x4

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld1%5B_mf8%5D_x4

### Signature (source notation)

```c
svmfloat8x4_t svld1[_mf8]_x4(svcount_t png, mfloat8_t const * rn);
```

### Description

Contiguous load of bytes to multiple consecutive vectors (immediate index)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Load / Consecutive

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p1)|FEAT_SME2
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
  "png": {
    "register": "PNreg1"
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
    "{ Zreg1.B - Zreg2.B }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
LD1B { Zreg1.B - Zreg2.B }, PNreg1/Z, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1B--scalar-plus-immediate--consecutive-registers---Contiguous-load-of-bytes-to-multiple-consecutive-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svld1[_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld1%5B_s16%5D

### Signature (source notation)

```c
svint16_t svld1[_s16](svbool_t pg, const int16_t *base);
```

### Description

Unextended load

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
LD1H Zresult.H, Pg/Z, [Xarray, Xindex, LSL #1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1H--scalar-plus-scalar--consecutive-registers---Contiguous-load-of-halfwords-to-multiple-consecutive-vectors--scalar-index--

The general implementation is:

```asm
LD1H Zresult.H, Pg/Z, [Xbase, #0, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1H--scalar-plus-immediate--consecutive-registers---Contiguous-load-of-halfwords-to-multiple-consecutive-vectors--immediate-index--

### Operation

Source operation ID: `SveOperation_svld1_bf16`

**Operation**



Return a vector in which each active element *i* contains `base[i]` and in which all other elements are zero.  Do not access memory for inactive elements.

## svld1[_s16]_x2

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld1%5B_s16%5D_x2

### Signature (source notation)

```c
svint16x2_t svld1[_s16]_x2(svcount_t png, int16_t const * rn);
```

### Description

Contiguous load of halfwords to multiple consecutive vectors (immediate index)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Load / Consecutive

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p1)|FEAT_SME2
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
  "png": {
    "register": "PNreg1"
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
    "{ Zreg1.H, Zreg2.H }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
LD1H { Zreg1.H, Zreg2.H }, PNreg1/Z, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1H--scalar-plus-immediate--consecutive-registers---Contiguous-load-of-halfwords-to-multiple-consecutive-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svld1[_s16]_x4

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld1%5B_s16%5D_x4

### Signature (source notation)

```c
svint16x4_t svld1[_s16]_x4(svcount_t png, int16_t const * rn);
```

### Description

Contiguous load of halfwords to multiple consecutive vectors (immediate index)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Load / Consecutive

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p1)|FEAT_SME2
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
  "png": {
    "register": "PNreg1"
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
    "{ Zreg1.H - Zreg2.H }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
LD1H { Zreg1.H - Zreg2.H }, PNreg1/Z, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1H--scalar-plus-immediate--consecutive-registers---Contiguous-load-of-halfwords-to-multiple-consecutive-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svld1[_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld1%5B_s32%5D

### Signature (source notation)

```c
svint32_t svld1[_s32](svbool_t pg, const int32_t *base);
```

### Description

Unextended load

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
LD1W Zresult.S, Pg/Z, [Xarray, Xindex, LSL #2]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1W--scalar-plus-scalar--consecutive-registers---Contiguous-load-of-words-to-multiple-consecutive-vectors--scalar-index--

The general implementation is:

```asm
LD1W Zresult.S, Pg/Z, [Xbase, #0, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1W--scalar-plus-immediate--consecutive-registers---Contiguous-load-of-words-to-multiple-consecutive-vectors--immediate-index--

### Operation

Source operation ID: `SveOperation_svld1_bf16`

**Operation**



Return a vector in which each active element *i* contains `base[i]` and in which all other elements are zero.  Do not access memory for inactive elements.

## svld1[_s32]_x2

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld1%5B_s32%5D_x2

### Signature (source notation)

```c
svint32x2_t svld1[_s32]_x2(svcount_t png, int32_t const * rn);
```

### Description

Contiguous load of words to multiple consecutive vectors (immediate index)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Load / Consecutive

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p1)|FEAT_SME2
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
  "png": {
    "register": "PNreg1"
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
    "{ Zreg1.S, Zreg2.S }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
LD1W { Zreg1.S, Zreg2.S }, PNreg1/Z, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1W--scalar-plus-immediate--consecutive-registers---Contiguous-load-of-words-to-multiple-consecutive-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svld1[_s32]_x4

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld1%5B_s32%5D_x4

### Signature (source notation)

```c
svint32x4_t svld1[_s32]_x4(svcount_t png, int32_t const * rn);
```

### Description

Contiguous load of words to multiple consecutive vectors (immediate index)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Load / Consecutive

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p1)|FEAT_SME2
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
  "png": {
    "register": "PNreg1"
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
    "{ Zreg1.S - Zreg2.S }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
LD1W { Zreg1.S - Zreg2.S }, PNreg1/Z, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1W--scalar-plus-immediate--consecutive-registers---Contiguous-load-of-words-to-multiple-consecutive-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svld1[_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld1%5B_s64%5D

### Signature (source notation)

```c
svint64_t svld1[_s64](svbool_t pg, const int64_t *base);
```

### Description

Unextended load

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
LD1D Zresult.D, Pg/Z, [Xarray, Xindex, LSL #3]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1D--scalar-plus-scalar--consecutive-registers---Contiguous-load-of-doublewords-to-multiple-consecutive-vectors--scalar-index--

The general implementation is:

```asm
LD1D Zresult.D, Pg/Z, [Xbase, #0, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1D--scalar-plus-immediate--consecutive-registers---Contiguous-load-of-doublewords-to-multiple-consecutive-vectors--immediate-index--

### Operation

Source operation ID: `SveOperation_svld1_bf16`

**Operation**



Return a vector in which each active element *i* contains `base[i]` and in which all other elements are zero.  Do not access memory for inactive elements.

## svld1[_s64]_x2

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld1%5B_s64%5D_x2

### Signature (source notation)

```c
svint64x2_t svld1[_s64]_x2(svcount_t png, int64_t const * rn);
```

### Description

Contiguous load of doublewords to multiple consecutive vectors (immediate index)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Load / Consecutive

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p1)|FEAT_SME2
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
  "png": {
    "register": "PNreg1"
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
    "{ Zreg1.D, Zreg2.D }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
LD1D { Zreg1.D, Zreg2.D }, PNreg1/Z, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1D--scalar-plus-immediate--consecutive-registers---Contiguous-load-of-doublewords-to-multiple-consecutive-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svld1[_s64]_x4

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld1%5B_s64%5D_x4

### Signature (source notation)

```c
svint64x4_t svld1[_s64]_x4(svcount_t png, int64_t const * rn);
```

### Description

Contiguous load of doublewords to multiple consecutive vectors (immediate index)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Load / Consecutive

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p1)|FEAT_SME2
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
  "png": {
    "register": "PNreg1"
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
    "{ Zreg1.D - Zreg2.D }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
LD1D { Zreg1.D - Zreg2.D }, PNreg1/Z, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1D--scalar-plus-immediate--consecutive-registers---Contiguous-load-of-doublewords-to-multiple-consecutive-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svld1[_s8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld1%5B_s8%5D

### Signature (source notation)

```c
svint8_t svld1[_s8](svbool_t pg, const int8_t *base);
```

### Description

Unextended load

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
LD1B Zresult.B, Pg/Z, [Xarray, Xindex]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1B--scalar-plus-scalar--consecutive-registers---Contiguous-load-of-bytes-to-multiple-consecutive-vectors--scalar-index--

The general implementation is:

```asm
LD1B Zresult.B, Pg/Z, [Xbase, #0, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1B--scalar-plus-immediate--single-register---Contiguous-load-unsigned-bytes-to-vector--immediate-index--

### Operation

Source operation ID: `SveOperation_svld1_bf16`

**Operation**



Return a vector in which each active element *i* contains `base[i]` and in which all other elements are zero.  Do not access memory for inactive elements.

## svld1[_s8]_x2

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld1%5B_s8%5D_x2

### Signature (source notation)

```c
svint8x2_t svld1[_s8]_x2(svcount_t png, int8_t const * rn);
```

### Description

Contiguous load of bytes to multiple consecutive vectors (immediate index)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Load / Consecutive

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p1)|FEAT_SME2
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
  "png": {
    "register": "PNreg1"
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
    "{ Zreg1.B, Zreg2.B }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
LD1B { Zreg1.B, Zreg2.B }, PNreg1/Z, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1B--scalar-plus-immediate--consecutive-registers---Contiguous-load-of-bytes-to-multiple-consecutive-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svld1[_s8]_x4

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld1%5B_s8%5D_x4

### Signature (source notation)

```c
svint8x4_t svld1[_s8]_x4(svcount_t png, int8_t const * rn);
```

### Description

Contiguous load of bytes to multiple consecutive vectors (immediate index)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Load / Consecutive

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p1)|FEAT_SME2
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
  "png": {
    "register": "PNreg1"
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
    "{ Zreg1.B - Zreg2.B }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
LD1B { Zreg1.B - Zreg2.B }, PNreg1/Z, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1B--scalar-plus-immediate--consecutive-registers---Contiguous-load-of-bytes-to-multiple-consecutive-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svld1[_u16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld1%5B_u16%5D

### Signature (source notation)

```c
svuint16_t svld1[_u16](svbool_t pg, const uint16_t *base);
```

### Description

Unextended load

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
LD1H Zresult.H, Pg/Z, [Xarray, Xindex, LSL #1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1H--scalar-plus-scalar--consecutive-registers---Contiguous-load-of-halfwords-to-multiple-consecutive-vectors--scalar-index--

The general implementation is:

```asm
LD1H Zresult.H, Pg/Z, [Xbase, #0, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1H--scalar-plus-immediate--consecutive-registers---Contiguous-load-of-halfwords-to-multiple-consecutive-vectors--immediate-index--

### Operation

Source operation ID: `SveOperation_svld1_bf16`

**Operation**



Return a vector in which each active element *i* contains `base[i]` and in which all other elements are zero.  Do not access memory for inactive elements.

## svld1[_u16]_x2

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld1%5B_u16%5D_x2

### Signature (source notation)

```c
svuint16x2_t svld1[_u16]_x2(svcount_t png, uint16_t const * rn);
```

### Description

Contiguous load of halfwords to multiple consecutive vectors (immediate index)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Load / Consecutive

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p1)|FEAT_SME2
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
  "png": {
    "register": "PNreg1"
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
    "{ Zreg1.H, Zreg2.H }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
LD1H { Zreg1.H, Zreg2.H }, PNreg1/Z, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1H--scalar-plus-immediate--consecutive-registers---Contiguous-load-of-halfwords-to-multiple-consecutive-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svld1[_u16]_x4

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld1%5B_u16%5D_x4

### Signature (source notation)

```c
svuint16x4_t svld1[_u16]_x4(svcount_t png, uint16_t const * rn);
```

### Description

Contiguous load of halfwords to multiple consecutive vectors (immediate index)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Load / Consecutive

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p1)|FEAT_SME2
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
  "png": {
    "register": "PNreg1"
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
    "{ Zreg1.H - Zreg2.H }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
LD1H { Zreg1.H - Zreg2.H }, PNreg1/Z, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1H--scalar-plus-immediate--consecutive-registers---Contiguous-load-of-halfwords-to-multiple-consecutive-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svld1[_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld1%5B_u32%5D

### Signature (source notation)

```c
svuint32_t svld1[_u32](svbool_t pg, const uint32_t *base);
```

### Description

Unextended load

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
LD1W Zresult.S, Pg/Z, [Xarray, Xindex, LSL #2]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1W--scalar-plus-scalar--consecutive-registers---Contiguous-load-of-words-to-multiple-consecutive-vectors--scalar-index--

The general implementation is:

```asm
LD1W Zresult.S, Pg/Z, [Xbase, #0, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1W--scalar-plus-immediate--consecutive-registers---Contiguous-load-of-words-to-multiple-consecutive-vectors--immediate-index--

### Operation

Source operation ID: `SveOperation_svld1_bf16`

**Operation**



Return a vector in which each active element *i* contains `base[i]` and in which all other elements are zero.  Do not access memory for inactive elements.

## svld1[_u32]_x2

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld1%5B_u32%5D_x2

### Signature (source notation)

```c
svuint32x2_t svld1[_u32]_x2(svcount_t png, uint32_t const * rn);
```

### Description

Contiguous load of words to multiple consecutive vectors (immediate index)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Load / Consecutive

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p1)|FEAT_SME2
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
  "png": {
    "register": "PNreg1"
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
    "{ Zreg1.S, Zreg2.S }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
LD1W { Zreg1.S, Zreg2.S }, PNreg1/Z, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1W--scalar-plus-immediate--consecutive-registers---Contiguous-load-of-words-to-multiple-consecutive-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svld1[_u32]_x4

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld1%5B_u32%5D_x4

### Signature (source notation)

```c
svuint32x4_t svld1[_u32]_x4(svcount_t png, uint32_t const * rn);
```

### Description

Contiguous load of words to multiple consecutive vectors (immediate index)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Load / Consecutive

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p1)|FEAT_SME2
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
  "png": {
    "register": "PNreg1"
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
    "{ Zreg1.S - Zreg2.S }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
LD1W { Zreg1.S - Zreg2.S }, PNreg1/Z, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1W--scalar-plus-immediate--consecutive-registers---Contiguous-load-of-words-to-multiple-consecutive-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svld1[_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld1%5B_u64%5D

### Signature (source notation)

```c
svuint64_t svld1[_u64](svbool_t pg, const uint64_t *base);
```

### Description

Unextended load

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
LD1D Zresult.D, Pg/Z, [Xarray, Xindex, LSL #3]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1D--scalar-plus-scalar--consecutive-registers---Contiguous-load-of-doublewords-to-multiple-consecutive-vectors--scalar-index--

The general implementation is:

```asm
LD1D Zresult.D, Pg/Z, [Xbase, #0, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1D--scalar-plus-immediate--consecutive-registers---Contiguous-load-of-doublewords-to-multiple-consecutive-vectors--immediate-index--

### Operation

Source operation ID: `SveOperation_svld1_bf16`

**Operation**



Return a vector in which each active element *i* contains `base[i]` and in which all other elements are zero.  Do not access memory for inactive elements.

## svld1[_u64]_x2

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld1%5B_u64%5D_x2

### Signature (source notation)

```c
svuint64x2_t svld1[_u64]_x2(svcount_t png, uint64_t const * rn);
```

### Description

Contiguous load of doublewords to multiple consecutive vectors (immediate index)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Load / Consecutive

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p1)|FEAT_SME2
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
  "png": {
    "register": "PNreg1"
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
    "{ Zreg1.D, Zreg2.D }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
LD1D { Zreg1.D, Zreg2.D }, PNreg1/Z, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1D--scalar-plus-immediate--consecutive-registers---Contiguous-load-of-doublewords-to-multiple-consecutive-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svld1[_u64]_x4

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld1%5B_u64%5D_x4

### Signature (source notation)

```c
svuint64x4_t svld1[_u64]_x4(svcount_t png, uint64_t const * rn);
```

### Description

Contiguous load of doublewords to multiple consecutive vectors (immediate index)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Load / Consecutive

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p1)|FEAT_SME2
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
  "png": {
    "register": "PNreg1"
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
    "{ Zreg1.D - Zreg2.D }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
LD1D { Zreg1.D - Zreg2.D }, PNreg1/Z, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1D--scalar-plus-immediate--consecutive-registers---Contiguous-load-of-doublewords-to-multiple-consecutive-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svld1[_u8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld1%5B_u8%5D

### Signature (source notation)

```c
svuint8_t svld1[_u8](svbool_t pg, const uint8_t *base);
```

### Description

Unextended load

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
LD1B Zresult.B, Pg/Z, [Xarray, Xindex]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1B--scalar-plus-scalar--consecutive-registers---Contiguous-load-of-bytes-to-multiple-consecutive-vectors--scalar-index--

The general implementation is:

```asm
LD1B Zresult.B, Pg/Z, [Xbase, #0, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1B--scalar-plus-immediate--single-register---Contiguous-load-unsigned-bytes-to-vector--immediate-index--

### Operation

Source operation ID: `SveOperation_svld1_bf16`

**Operation**



Return a vector in which each active element *i* contains `base[i]` and in which all other elements are zero.  Do not access memory for inactive elements.

## svld1[_u8]_x2

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld1%5B_u8%5D_x2

### Signature (source notation)

```c
svuint8x2_t svld1[_u8]_x2(svcount_t png, uint8_t const * rn);
```

### Description

Contiguous load of bytes to multiple consecutive vectors (immediate index)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Load / Consecutive

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p1)|FEAT_SME2
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
  "png": {
    "register": "PNreg1"
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
    "{ Zreg1.B, Zreg2.B }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
LD1B { Zreg1.B, Zreg2.B }, PNreg1/Z, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1B--scalar-plus-immediate--consecutive-registers---Contiguous-load-of-bytes-to-multiple-consecutive-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svld1[_u8]_x4

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld1%5B_u8%5D_x4

### Signature (source notation)

```c
svuint8x4_t svld1[_u8]_x4(svcount_t png, uint8_t const * rn);
```

### Description

Contiguous load of bytes to multiple consecutive vectors (immediate index)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Load / Consecutive

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p1)|FEAT_SME2
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
  "png": {
    "register": "PNreg1"
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
    "{ Zreg1.B - Zreg2.B }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
LD1B { Zreg1.B - Zreg2.B }, PNreg1/Z, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LD1B--scalar-plus-immediate--consecutive-registers---Contiguous-load-of-bytes-to-multiple-consecutive-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svld1_hor_vnum_za128

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld1_hor_vnum_za128

### Signature (source notation)

```c
void svld1_hor_vnum_za128(uint64_t tile, uint32_t slice, svbool_t pg, void const * ptr, int64_t vnum)
    __arm_streaming __arm_inout("za");
```

### Description

Contiguous load of quadwords to 128-bit element ZA tile slice

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Load / Consecutive

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

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
  "element_bit_size": "128",
  "value": "void"
}
```

### Argument preparation and constraints

```json
{
  "tile": {
    "ZA array tile": "ZA0H.Q"
  },
  "slice": {
    "register+immediate": "Wreg2 + imm1"
  },
  "vnum": {
    "registers": "Wreg3, Xreg2"
  },
  "pg": {
    "register": "Preg1"
  },
  "ptr": {
    "register": "Xreg3"
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
RDSVL Xreg1, #1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/RDSVL--Read-multiple-of-Streaming-SVE-vector-register-size-to-scalar-register-

```asm
ADD Wreg1, Wreg2, Wreg3
```

Instruction reference: https://developer.arm.com/documentation/ddi0597/2025-06/Base-Instructions/ADD--ADDS--register---Add--register--

```asm
MADD Xreg1, Xreg1, Xreg2, Xreg3
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/Base-Instructions/MADD--Multiply-add-

```asm
LD1Q {ZA0H.Q[Wreg1, imm1]}, Preg1/Z, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/LD1Q--Contiguous-load-of-quadwords-to-128-bit-element-ZA-tile-slice-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svld1_hor_vnum_za16

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld1_hor_vnum_za16

### Signature (source notation)

```c
void svld1_hor_vnum_za16(uint64_t tile, uint32_t slice, svbool_t pg, void const * ptr, int64_t vnum)
    __arm_streaming __arm_inout("za");
```

### Description

Contiguous load of halfwords to 16-bit element ZA tile slice

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Load / Consecutive

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

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
  "element_bit_size": "16",
  "value": "void"
}
```

### Argument preparation and constraints

```json
{
  "tile": {
    "ZA array tile": "ZA0H.H"
  },
  "slice": {
    "register+immediate": "Wreg2 + imm1"
  },
  "vnum": {
    "registers": "Wreg3, Xreg2"
  },
  "pg": {
    "register": "Preg1"
  },
  "ptr": {
    "register": "Xreg3"
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
RDSVL Xreg1, #1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/RDSVL--Read-multiple-of-Streaming-SVE-vector-register-size-to-scalar-register-

```asm
ADD Wreg1, Wreg2, Wreg3
```

Instruction reference: https://developer.arm.com/documentation/ddi0597/2025-06/Base-Instructions/ADD--ADDS--register---Add--register--

```asm
MADD Xreg1, Xreg1, Xreg2, Xreg3
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/Base-Instructions/MADD--Multiply-add-

```asm
LD1H {ZA0H.H[Wreg1, imm1]}, Preg1/Z, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/LD1H--scalar-plus-scalar--tile-slice---Contiguous-load-of-halfwords-to-16-bit-element-ZA-tile-slice-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svld1_hor_vnum_za32

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld1_hor_vnum_za32

### Signature (source notation)

```c
void svld1_hor_vnum_za32(uint64_t tile, uint32_t slice, svbool_t pg, void const * ptr, int64_t vnum)
    __arm_streaming __arm_inout("za");
```

### Description

Contiguous load of words to 32-bit element ZA tile slice

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Load / Consecutive

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

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
  "element_bit_size": "32",
  "value": "void"
}
```

### Argument preparation and constraints

```json
{
  "tile": {
    "ZA array tile": "ZA0H.S"
  },
  "slice": {
    "register+immediate": "Wreg2 + imm1"
  },
  "vnum": {
    "registers": "Wreg3, Xreg2"
  },
  "pg": {
    "register": "Preg1"
  },
  "ptr": {
    "register": "Xreg3"
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
RDSVL Xreg1, #1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/RDSVL--Read-multiple-of-Streaming-SVE-vector-register-size-to-scalar-register-

```asm
ADD Wreg1, Wreg2, Wreg3
```

Instruction reference: https://developer.arm.com/documentation/ddi0597/2025-06/Base-Instructions/ADD--ADDS--register---Add--register--

```asm
MADD Xreg1, Xreg1, Xreg2, Xreg3
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/Base-Instructions/MADD--Multiply-add-

```asm
LD1W {ZA0H.S[Wreg1, imm1]}, Preg1/Z, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/LD1W--scalar-plus-scalar--tile-slice---Contiguous-load-of-words-to-32-bit-element-ZA-tile-slice-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svld1_hor_vnum_za64

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld1_hor_vnum_za64

### Signature (source notation)

```c
void svld1_hor_vnum_za64(uint64_t tile, uint32_t slice, svbool_t pg, void const * ptr, int64_t vnum)
    __arm_streaming __arm_inout("za");
```

### Description

Contiguous load of doublewords to 64-bit element ZA tile slice

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Load / Consecutive

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

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
  "element_bit_size": "64",
  "value": "void"
}
```

### Argument preparation and constraints

```json
{
  "tile": {
    "ZA array tile": "ZA0H.D"
  },
  "slice": {
    "register+immediate": "Wreg2 + imm1"
  },
  "vnum": {
    "registers": "Wreg3, Xreg2"
  },
  "pg": {
    "register": "Preg1"
  },
  "ptr": {
    "register": "Xreg3"
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
RDSVL Xreg1, #1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/RDSVL--Read-multiple-of-Streaming-SVE-vector-register-size-to-scalar-register-

```asm
ADD Wreg1, Wreg2, Wreg3
```

Instruction reference: https://developer.arm.com/documentation/ddi0597/2025-06/Base-Instructions/ADD--ADDS--register---Add--register--

```asm
MADD Xreg1, Xreg1, Xreg2, Xreg3
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/Base-Instructions/MADD--Multiply-add-

```asm
LD1D {ZA0H.D[Wreg1, imm1]}, Preg1/Z, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/LD1D--scalar-plus-scalar--tile-slice---Contiguous-load-of-doublewords-to-64-bit-element-ZA-tile-slice-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svld1_hor_vnum_za8

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld1_hor_vnum_za8

### Signature (source notation)

```c
void svld1_hor_vnum_za8(uint64_t tile, uint32_t slice, svbool_t pg, void const * ptr, int64_t vnum)
    __arm_streaming __arm_inout("za");
```

### Description

Contiguous load of bytes to 8-bit element ZA tile slice

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Load / Consecutive

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

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
  "tile": {
    "ZA array tile": "ZA0H.B"
  },
  "slice": {
    "register+immediate": "Wreg2 + imm1"
  },
  "vnum": {
    "registers": "Wreg3, Xreg2"
  },
  "pg": {
    "register": "Preg1"
  },
  "ptr": {
    "register": "Xreg3"
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
RDSVL Xreg2, #1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/RDSVL--Read-multiple-of-Streaming-SVE-vector-register-size-to-scalar-register-

```asm
ADD Wreg1, Wreg2, Wreg3
```

Instruction reference: https://developer.arm.com/documentation/ddi0597/2025-06/Base-Instructions/ADD--ADDS--register---Add--register--

```asm
MUL Xreg2, Xreg2, Xreg3
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/Base-Instructions/MUL--Multiply--an-alias-of-MADD-

```asm
LD1B {ZA0H.B[Wreg1, imm1]}, Preg1/Z, [Xreg1, Xreg2]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/LD1B--scalar-plus-scalar--tile-slice---Contiguous-load-of-bytes-to-8-bit-element-ZA-tile-slice-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svld1_hor_za128

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld1_hor_za128

### Signature (source notation)

```c
void svld1_hor_za128(uint64_t tile, uint32_t slice, svbool_t pg, void const * ptr)
    __arm_streaming __arm_inout("za");
```

### Description

Contiguous load of quadwords to 128-bit element ZA tile slice

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Load / Consecutive

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

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
  "element_bit_size": "128",
  "value": "void"
}
```

### Argument preparation and constraints

```json
{
  "tile": {
    "ZA array tile": "ZA0H.Q"
  },
  "slice": {
    "register+immediate": "Wreg1 + imm1"
  },
  "pg": {
    "register": "Preg1"
  },
  "ptr": {
    "register": "Xreg1"
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
LD1Q {ZA0H.Q[Wreg1, imm1]}, Preg1/Z, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/LD1Q--Contiguous-load-of-quadwords-to-128-bit-element-ZA-tile-slice-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svld1_hor_za16

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld1_hor_za16

### Signature (source notation)

```c
void svld1_hor_za16(uint64_t tile, uint32_t slice, svbool_t pg, void const * ptr)
    __arm_streaming __arm_inout("za");
```

### Description

Contiguous load of halfwords to 16-bit element ZA tile slice

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Load / Consecutive

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

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
  "element_bit_size": "16",
  "value": "void"
}
```

### Argument preparation and constraints

```json
{
  "tile": {
    "ZA array tile": "ZA0H.H"
  },
  "slice": {
    "register+immediate": "Wreg1 + imm1"
  },
  "pg": {
    "register": "Preg1"
  },
  "ptr": {
    "register": "Xreg1"
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
LD1H {ZA0H.H[Wreg1, imm1]}, Preg1/Z, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/LD1H--scalar-plus-scalar--tile-slice---Contiguous-load-of-halfwords-to-16-bit-element-ZA-tile-slice-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svld1_hor_za32

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld1_hor_za32

### Signature (source notation)

```c
void svld1_hor_za32(uint64_t tile, uint32_t slice, svbool_t pg, void const * ptr)
    __arm_streaming __arm_inout("za");
```

### Description

Contiguous load of words to 32-bit element ZA tile slice

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Load / Consecutive

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

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
  "element_bit_size": "32",
  "value": "void"
}
```

### Argument preparation and constraints

```json
{
  "tile": {
    "ZA array tile": "ZA0H.S"
  },
  "slice": {
    "register+immediate": "Wreg1 + imm1"
  },
  "pg": {
    "register": "Preg1"
  },
  "ptr": {
    "register": "Xreg1"
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
LD1W {ZA0H.S[Wreg1, imm1]}, Preg1/Z, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/LD1W--scalar-plus-scalar--tile-slice---Contiguous-load-of-words-to-32-bit-element-ZA-tile-slice-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svld1_hor_za64

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld1_hor_za64

### Signature (source notation)

```c
void svld1_hor_za64(uint64_t tile, uint32_t slice, svbool_t pg, void const * ptr)
    __arm_streaming __arm_inout("za");
```

### Description

Contiguous load of doublewords to 64-bit element ZA tile slice

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Load / Consecutive

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

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
  "element_bit_size": "64",
  "value": "void"
}
```

### Argument preparation and constraints

```json
{
  "tile": {
    "ZA array tile": "ZA0H.D"
  },
  "slice": {
    "register+immediate": "Wreg1 + imm1"
  },
  "pg": {
    "register": "Preg1"
  },
  "ptr": {
    "register": "Xreg1"
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
LD1D {ZA0H.D[Wreg1, imm1]}, Preg1/Z, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/LD1D--scalar-plus-scalar--tile-slice---Contiguous-load-of-doublewords-to-64-bit-element-ZA-tile-slice-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svld1_hor_za8

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld1_hor_za8

### Signature (source notation)

```c
void svld1_hor_za8(uint64_t tile, uint32_t slice, svbool_t pg, void const * ptr)
    __arm_streaming __arm_inout("za");
```

### Description

Contiguous load of bytes to 8-bit element ZA tile slice

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Load / Consecutive

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

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
  "tile": {
    "ZA array tile": "ZA0H.B"
  },
  "slice": {
    "register+immediate": "Wreg1 + imm1"
  },
  "pg": {
    "register": "Preg1"
  },
  "ptr": {
    "register": "Xreg1"
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
LD1B {ZA0H.B[Wreg1, imm1]}, Preg1/Z, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/LD1B--scalar-plus-scalar--tile-slice---Contiguous-load-of-bytes-to-8-bit-element-ZA-tile-slice-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svld1_ver_vnum_za128

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld1_ver_vnum_za128

### Signature (source notation)

```c
void svld1_ver_vnum_za128(uint64_t tile, uint32_t slice, svbool_t pg, void const * ptr, int64_t vnum)
    __arm_streaming __arm_inout("za");
```

### Description

Contiguous load of quadwords to 128-bit element ZA tile slice

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Load / Consecutive

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

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
  "element_bit_size": "128",
  "value": "void"
}
```

### Argument preparation and constraints

```json
{
  "tile": {
    "ZA array tile": "ZA0V.Q"
  },
  "slice": {
    "register+immediate": "Wreg2 + imm1"
  },
  "vnum": {
    "registers": "Wreg3, Xreg2"
  },
  "pg": {
    "register": "Preg1"
  },
  "ptr": {
    "register": "Xreg3"
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
RDSVL Xreg1, #1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/RDSVL--Read-multiple-of-Streaming-SVE-vector-register-size-to-scalar-register-

```asm
ADD Wreg1, Wreg2, Wreg3
```

Instruction reference: https://developer.arm.com/documentation/ddi0597/2025-06/Base-Instructions/ADD--ADDS--register---Add--register--

```asm
MADD Xreg1, Xreg1, Xreg2, Xreg3
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/Base-Instructions/MADD--Multiply-add-

```asm
LD1Q {ZA0V.Q[Wreg1, imm1]}, Preg1/Z, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/LD1Q--Contiguous-load-of-quadwords-to-128-bit-element-ZA-tile-slice-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

