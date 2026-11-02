# SME / Load / Consecutive — Part 7

## svld4q_vnum[_u64]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld4q_vnum%5B_u64%5D

### Signature (source notation)

```c
svuint64x4_t svld4q_vnum[_u64](svbool_t pg, uint64_t const * rn, int64_t vnum);
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

## svld4q_vnum[_u8]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svld4q_vnum%5B_u8%5D

### Signature (source notation)

```c
svuint8x4_t svld4q_vnum[_u8](svbool_t pg, uint8_t const * rn, int64_t vnum);
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

## svldnt1[_bf16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svldnt1%5B_bf16%5D

### Signature (source notation)

```c
svbfloat16_t svldnt1[_bf16](svbool_t pg, const bfloat16_t *base);
```

### Description

Unextended load, non-temporal

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
LDNT1H Zresult.H, Pg/Z, [Xarray, Xindex, LSL #1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LDNT1H--scalar-plus-scalar--consecutive-registers---Contiguous-load-non-temporal-of-halfwords-to-multiple-consecutive-vectors--scalar-index--

The general implementation is:

```asm
LDNT1H Zresult.H, Pg/Z, [Xbase, #0, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LDNT1H--scalar-plus-immediate--consecutive-registers---Contiguous-load-non-temporal-of-halfwords-to-multiple-consecutive-vectors--immediate-index--

### Operation

Source operation ID: `SveOperation_svldnt1_bf16`

**Operation**



Return a vector in which each active element *i* contains `base[i]` and in which all other elements are zero.  Do not access memory for inactive elements.  Provide a hint to the system that the loaded memory is unlikely to be accessed again soon.

## svldnt1[_bf16]_x2

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svldnt1%5B_bf16%5D_x2

### Signature (source notation)

```c
svbfloat16x2_t svldnt1[_bf16]_x2(svcount_t png, bfloat16_t const * rn);
```

### Description

Contiguous load non-temporal of halfwords to multiple consecutive vectors (immediate index)

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
LDNT1H { Zreg1.H, Zreg2.H }, PNreg1/Z, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LDNT1H--scalar-plus-immediate--consecutive-registers---Contiguous-load-non-temporal-of-halfwords-to-multiple-consecutive-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svldnt1[_bf16]_x4

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svldnt1%5B_bf16%5D_x4

### Signature (source notation)

```c
svbfloat16x4_t svldnt1[_bf16]_x4(svcount_t png, bfloat16_t const * rn);
```

### Description

Contiguous load non-temporal of halfwords to multiple consecutive vectors (immediate index)

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
LDNT1H { Zreg1.H - Zreg2.H }, PNreg1/Z, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LDNT1H--scalar-plus-immediate--consecutive-registers---Contiguous-load-non-temporal-of-halfwords-to-multiple-consecutive-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svldnt1[_f16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svldnt1%5B_f16%5D

### Signature (source notation)

```c
svfloat16_t svldnt1[_f16](svbool_t pg, const float16_t *base);
```

### Description

Unextended load, non-temporal

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
LDNT1H Zresult.H, Pg/Z, [Xarray, Xindex, LSL #1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LDNT1H--scalar-plus-scalar--consecutive-registers---Contiguous-load-non-temporal-of-halfwords-to-multiple-consecutive-vectors--scalar-index--

The general implementation is:

```asm
LDNT1H Zresult.H, Pg/Z, [Xbase, #0, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LDNT1H--scalar-plus-immediate--consecutive-registers---Contiguous-load-non-temporal-of-halfwords-to-multiple-consecutive-vectors--immediate-index--

### Operation

Source operation ID: `SveOperation_svldnt1_bf16`

**Operation**



Return a vector in which each active element *i* contains `base[i]` and in which all other elements are zero.  Do not access memory for inactive elements.  Provide a hint to the system that the loaded memory is unlikely to be accessed again soon.

## svldnt1[_f16]_x2

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svldnt1%5B_f16%5D_x2

### Signature (source notation)

```c
svfloat16x2_t svldnt1[_f16]_x2(svcount_t png, float16_t const * rn);
```

### Description

Contiguous load non-temporal of halfwords to multiple consecutive vectors (immediate index)

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
LDNT1H { Zreg1.H, Zreg2.H }, PNreg1/Z, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LDNT1H--scalar-plus-immediate--consecutive-registers---Contiguous-load-non-temporal-of-halfwords-to-multiple-consecutive-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svldnt1[_f16]_x4

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svldnt1%5B_f16%5D_x4

### Signature (source notation)

```c
svfloat16x4_t svldnt1[_f16]_x4(svcount_t png, float16_t const * rn);
```

### Description

Contiguous load non-temporal of halfwords to multiple consecutive vectors (immediate index)

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
LDNT1H { Zreg1.H - Zreg2.H }, PNreg1/Z, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LDNT1H--scalar-plus-immediate--consecutive-registers---Contiguous-load-non-temporal-of-halfwords-to-multiple-consecutive-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svldnt1[_f32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svldnt1%5B_f32%5D

### Signature (source notation)

```c
svfloat32_t svldnt1[_f32](svbool_t pg, const float32_t *base);
```

### Description

Unextended load, non-temporal

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
LDNT1W Zresult.S, Pg/Z, [Xarray, Xindex, LSL #2]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LDNT1W--scalar-plus-scalar--consecutive-registers---Contiguous-load-non-temporal-of-words-to-multiple-consecutive-vectors--scalar-index--

The general implementation is:

```asm
LDNT1W Zresult.S, Pg/Z, [Xbase, #0, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LDNT1W--scalar-plus-immediate--consecutive-registers---Contiguous-load-non-temporal-of-words-to-multiple-consecutive-vectors--immediate-index--

### Operation

Source operation ID: `SveOperation_svldnt1_bf16`

**Operation**



Return a vector in which each active element *i* contains `base[i]` and in which all other elements are zero.  Do not access memory for inactive elements.  Provide a hint to the system that the loaded memory is unlikely to be accessed again soon.

## svldnt1[_f32]_x2

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svldnt1%5B_f32%5D_x2

### Signature (source notation)

```c
svfloat32x2_t svldnt1[_f32]_x2(svcount_t png, float32_t const * rn);
```

### Description

Contiguous load non-temporal of words to multiple consecutive vectors (immediate index)

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
LDNT1W { Zreg1.S, Zreg2.S }, PNreg1/Z, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LDNT1W--scalar-plus-immediate--consecutive-registers---Contiguous-load-non-temporal-of-words-to-multiple-consecutive-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svldnt1[_f32]_x4

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svldnt1%5B_f32%5D_x4

### Signature (source notation)

```c
svfloat32x4_t svldnt1[_f32]_x4(svcount_t png, float32_t const * rn);
```

### Description

Contiguous load non-temporal of words to multiple consecutive vectors (immediate index)

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
LDNT1W { Zreg1.S - Zreg2.S }, PNreg1/Z, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LDNT1W--scalar-plus-immediate--consecutive-registers---Contiguous-load-non-temporal-of-words-to-multiple-consecutive-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svldnt1[_f64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svldnt1%5B_f64%5D

### Signature (source notation)

```c
svfloat64_t svldnt1[_f64](svbool_t pg, const float64_t *base);
```

### Description

Unextended load, non-temporal

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
LDNT1D Zresult.D, Pg/Z, [Xarray, Xindex, LSL #3]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LDNT1D--scalar-plus-scalar--consecutive-registers---Contiguous-load-non-temporal-of-doublewords-to-multiple-consecutive-vectors--scalar-index--

The general implementation is:

```asm
LDNT1D Zresult.D, Pg/Z, [Xbase, #0, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LDNT1D--scalar-plus-immediate--consecutive-registers---Contiguous-load-non-temporal-of-doublewords-to-multiple-consecutive-vectors--immediate-index--

### Operation

Source operation ID: `SveOperation_svldnt1_bf16`

**Operation**



Return a vector in which each active element *i* contains `base[i]` and in which all other elements are zero.  Do not access memory for inactive elements.  Provide a hint to the system that the loaded memory is unlikely to be accessed again soon.

## svldnt1[_f64]_x2

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svldnt1%5B_f64%5D_x2

### Signature (source notation)

```c
svfloat64x2_t svldnt1[_f64]_x2(svcount_t png, float64_t const * rn);
```

### Description

Contiguous load non-temporal of doublewords to multiple consecutive vectors (immediate index)

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
LDNT1D { Zreg1.D, Zreg2.D }, PNreg1/Z, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LDNT1D--scalar-plus-immediate--consecutive-registers---Contiguous-load-non-temporal-of-doublewords-to-multiple-consecutive-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svldnt1[_f64]_x4

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svldnt1%5B_f64%5D_x4

### Signature (source notation)

```c
svfloat64x4_t svldnt1[_f64]_x4(svcount_t png, float64_t const * rn);
```

### Description

Contiguous load non-temporal of doublewords to multiple consecutive vectors (immediate index)

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
LDNT1D { Zreg1.D - Zreg2.D }, PNreg1/Z, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LDNT1D--scalar-plus-immediate--consecutive-registers---Contiguous-load-non-temporal-of-doublewords-to-multiple-consecutive-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svldnt1[_mf8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svldnt1%5B_mf8%5D

### Signature (source notation)

```c
svmfloat8_t svldnt1[_mf8](svbool_t pg, const mfloat8_t *base);
```

### Description

Unextended load, non-temporal

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
LDNT1B Zresult.B, Pg/Z, [Xarray, Xindex]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LDNT1B--scalar-plus-scalar--consecutive-registers---Contiguous-load-non-temporal-of-bytes-to-multiple-consecutive-vectors--scalar-index--

The general implementation is:

```asm
LDNT1B Zresult.B, Pg/Z, [Xbase, #0, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LDNT1B--scalar-plus-immediate--consecutive-registers---Contiguous-load-non-temporal-of-bytes-to-multiple-consecutive-vectors--immediate-index--

### Operation

Source operation ID: `SveOperation_svldnt1_bf16`

**Operation**



Return a vector in which each active element *i* contains `base[i]` and in which all other elements are zero.  Do not access memory for inactive elements.  Provide a hint to the system that the loaded memory is unlikely to be accessed again soon.

## svldnt1[_mf8]_x2

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svldnt1%5B_mf8%5D_x2

### Signature (source notation)

```c
svmfloat8x2_t svldnt1[_mf8]_x2(svcount_t png, mfloat8_t const * rn);
```

### Description

Contiguous load non-temporal of bytes to multiple consecutive vectors (immediate index)

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
LDNT1B { Zreg1.B, Zreg2.B }, PNreg1/Z, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LDNT1B--scalar-plus-immediate--consecutive-registers---Contiguous-load-non-temporal-of-bytes-to-multiple-consecutive-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svldnt1[_mf8]_x4

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svldnt1%5B_mf8%5D_x4

### Signature (source notation)

```c
svmfloat8x4_t svldnt1[_mf8]_x4(svcount_t png, mfloat8_t const * rn);
```

### Description

Contiguous load non-temporal of bytes to multiple consecutive vectors (immediate index)

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
LDNT1B { Zreg1.B - Zreg2.B }, PNreg1/Z, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LDNT1B--scalar-plus-immediate--consecutive-registers---Contiguous-load-non-temporal-of-bytes-to-multiple-consecutive-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svldnt1[_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svldnt1%5B_s16%5D

### Signature (source notation)

```c
svint16_t svldnt1[_s16](svbool_t pg, const int16_t *base);
```

### Description

Unextended load, non-temporal

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
LDNT1H Zresult.H, Pg/Z, [Xarray, Xindex, LSL #1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LDNT1H--scalar-plus-scalar--consecutive-registers---Contiguous-load-non-temporal-of-halfwords-to-multiple-consecutive-vectors--scalar-index--

The general implementation is:

```asm
LDNT1H Zresult.H, Pg/Z, [Xbase, #0, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LDNT1H--scalar-plus-immediate--consecutive-registers---Contiguous-load-non-temporal-of-halfwords-to-multiple-consecutive-vectors--immediate-index--

### Operation

Source operation ID: `SveOperation_svldnt1_bf16`

**Operation**



Return a vector in which each active element *i* contains `base[i]` and in which all other elements are zero.  Do not access memory for inactive elements.  Provide a hint to the system that the loaded memory is unlikely to be accessed again soon.

## svldnt1[_s16]_x2

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svldnt1%5B_s16%5D_x2

### Signature (source notation)

```c
svint16x2_t svldnt1[_s16]_x2(svcount_t png, int16_t const * rn);
```

### Description

Contiguous load non-temporal of halfwords to multiple consecutive vectors (immediate index)

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
LDNT1H { Zreg1.H, Zreg2.H }, PNreg1/Z, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LDNT1H--scalar-plus-immediate--consecutive-registers---Contiguous-load-non-temporal-of-halfwords-to-multiple-consecutive-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svldnt1[_s16]_x4

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svldnt1%5B_s16%5D_x4

### Signature (source notation)

```c
svint16x4_t svldnt1[_s16]_x4(svcount_t png, int16_t const * rn);
```

### Description

Contiguous load non-temporal of halfwords to multiple consecutive vectors (immediate index)

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
LDNT1H { Zreg1.H - Zreg2.H }, PNreg1/Z, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LDNT1H--scalar-plus-immediate--consecutive-registers---Contiguous-load-non-temporal-of-halfwords-to-multiple-consecutive-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svldnt1[_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svldnt1%5B_s32%5D

### Signature (source notation)

```c
svint32_t svldnt1[_s32](svbool_t pg, const int32_t *base);
```

### Description

Unextended load, non-temporal

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
LDNT1W Zresult.S, Pg/Z, [Xarray, Xindex, LSL #2]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LDNT1W--scalar-plus-scalar--consecutive-registers---Contiguous-load-non-temporal-of-words-to-multiple-consecutive-vectors--scalar-index--

The general implementation is:

```asm
LDNT1W Zresult.S, Pg/Z, [Xbase, #0, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LDNT1W--scalar-plus-immediate--consecutive-registers---Contiguous-load-non-temporal-of-words-to-multiple-consecutive-vectors--immediate-index--

### Operation

Source operation ID: `SveOperation_svldnt1_bf16`

**Operation**



Return a vector in which each active element *i* contains `base[i]` and in which all other elements are zero.  Do not access memory for inactive elements.  Provide a hint to the system that the loaded memory is unlikely to be accessed again soon.

## svldnt1[_s32]_x2

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svldnt1%5B_s32%5D_x2

### Signature (source notation)

```c
svint32x2_t svldnt1[_s32]_x2(svcount_t png, int32_t const * rn);
```

### Description

Contiguous load non-temporal of words to multiple consecutive vectors (immediate index)

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
LDNT1W { Zreg1.S, Zreg2.S }, PNreg1/Z, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LDNT1W--scalar-plus-immediate--consecutive-registers---Contiguous-load-non-temporal-of-words-to-multiple-consecutive-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svldnt1[_s32]_x4

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svldnt1%5B_s32%5D_x4

### Signature (source notation)

```c
svint32x4_t svldnt1[_s32]_x4(svcount_t png, int32_t const * rn);
```

### Description

Contiguous load non-temporal of words to multiple consecutive vectors (immediate index)

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
LDNT1W { Zreg1.S - Zreg2.S }, PNreg1/Z, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LDNT1W--scalar-plus-immediate--consecutive-registers---Contiguous-load-non-temporal-of-words-to-multiple-consecutive-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svldnt1[_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svldnt1%5B_s64%5D

### Signature (source notation)

```c
svint64_t svldnt1[_s64](svbool_t pg, const int64_t *base);
```

### Description

Unextended load, non-temporal

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
LDNT1D Zresult.D, Pg/Z, [Xarray, Xindex, LSL #3]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LDNT1D--scalar-plus-scalar--consecutive-registers---Contiguous-load-non-temporal-of-doublewords-to-multiple-consecutive-vectors--scalar-index--

The general implementation is:

```asm
LDNT1D Zresult.D, Pg/Z, [Xbase, #0, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LDNT1D--scalar-plus-immediate--consecutive-registers---Contiguous-load-non-temporal-of-doublewords-to-multiple-consecutive-vectors--immediate-index--

### Operation

Source operation ID: `SveOperation_svldnt1_bf16`

**Operation**



Return a vector in which each active element *i* contains `base[i]` and in which all other elements are zero.  Do not access memory for inactive elements.  Provide a hint to the system that the loaded memory is unlikely to be accessed again soon.

## svldnt1[_s64]_x2

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svldnt1%5B_s64%5D_x2

### Signature (source notation)

```c
svint64x2_t svldnt1[_s64]_x2(svcount_t png, int64_t const * rn);
```

### Description

Contiguous load non-temporal of doublewords to multiple consecutive vectors (immediate index)

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
LDNT1D { Zreg1.D, Zreg2.D }, PNreg1/Z, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LDNT1D--scalar-plus-immediate--consecutive-registers---Contiguous-load-non-temporal-of-doublewords-to-multiple-consecutive-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svldnt1[_s64]_x4

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svldnt1%5B_s64%5D_x4

### Signature (source notation)

```c
svint64x4_t svldnt1[_s64]_x4(svcount_t png, int64_t const * rn);
```

### Description

Contiguous load non-temporal of doublewords to multiple consecutive vectors (immediate index)

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
LDNT1D { Zreg1.D - Zreg2.D }, PNreg1/Z, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LDNT1D--scalar-plus-immediate--consecutive-registers---Contiguous-load-non-temporal-of-doublewords-to-multiple-consecutive-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svldnt1[_s8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svldnt1%5B_s8%5D

### Signature (source notation)

```c
svint8_t svldnt1[_s8](svbool_t pg, const int8_t *base);
```

### Description

Unextended load, non-temporal

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
LDNT1B Zresult.B, Pg/Z, [Xarray, Xindex]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LDNT1B--scalar-plus-scalar--consecutive-registers---Contiguous-load-non-temporal-of-bytes-to-multiple-consecutive-vectors--scalar-index--

The general implementation is:

```asm
LDNT1B Zresult.B, Pg/Z, [Xbase, #0, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LDNT1B--scalar-plus-immediate--consecutive-registers---Contiguous-load-non-temporal-of-bytes-to-multiple-consecutive-vectors--immediate-index--

### Operation

Source operation ID: `SveOperation_svldnt1_bf16`

**Operation**



Return a vector in which each active element *i* contains `base[i]` and in which all other elements are zero.  Do not access memory for inactive elements.  Provide a hint to the system that the loaded memory is unlikely to be accessed again soon.

## svldnt1[_s8]_x2

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svldnt1%5B_s8%5D_x2

### Signature (source notation)

```c
svint8x2_t svldnt1[_s8]_x2(svcount_t png, int8_t const * rn);
```

### Description

Contiguous load non-temporal of bytes to multiple consecutive vectors (immediate index)

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
LDNT1B { Zreg1.B, Zreg2.B }, PNreg1/Z, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LDNT1B--scalar-plus-immediate--consecutive-registers---Contiguous-load-non-temporal-of-bytes-to-multiple-consecutive-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svldnt1[_s8]_x4

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svldnt1%5B_s8%5D_x4

### Signature (source notation)

```c
svint8x4_t svldnt1[_s8]_x4(svcount_t png, int8_t const * rn);
```

### Description

Contiguous load non-temporal of bytes to multiple consecutive vectors (immediate index)

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
LDNT1B { Zreg1.B - Zreg2.B }, PNreg1/Z, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LDNT1B--scalar-plus-immediate--consecutive-registers---Contiguous-load-non-temporal-of-bytes-to-multiple-consecutive-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svldnt1[_u16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svldnt1%5B_u16%5D

### Signature (source notation)

```c
svuint16_t svldnt1[_u16](svbool_t pg, const uint16_t *base);
```

### Description

Unextended load, non-temporal

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
LDNT1H Zresult.H, Pg/Z, [Xarray, Xindex, LSL #1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LDNT1H--scalar-plus-scalar--consecutive-registers---Contiguous-load-non-temporal-of-halfwords-to-multiple-consecutive-vectors--scalar-index--

The general implementation is:

```asm
LDNT1H Zresult.H, Pg/Z, [Xbase, #0, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LDNT1H--scalar-plus-immediate--consecutive-registers---Contiguous-load-non-temporal-of-halfwords-to-multiple-consecutive-vectors--immediate-index--

### Operation

Source operation ID: `SveOperation_svldnt1_bf16`

**Operation**



Return a vector in which each active element *i* contains `base[i]` and in which all other elements are zero.  Do not access memory for inactive elements.  Provide a hint to the system that the loaded memory is unlikely to be accessed again soon.

## svldnt1[_u16]_x2

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svldnt1%5B_u16%5D_x2

### Signature (source notation)

```c
svuint16x2_t svldnt1[_u16]_x2(svcount_t png, uint16_t const * rn);
```

### Description

Contiguous load non-temporal of halfwords to multiple consecutive vectors (immediate index)

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
LDNT1H { Zreg1.H, Zreg2.H }, PNreg1/Z, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LDNT1H--scalar-plus-immediate--consecutive-registers---Contiguous-load-non-temporal-of-halfwords-to-multiple-consecutive-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svldnt1[_u16]_x4

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svldnt1%5B_u16%5D_x4

### Signature (source notation)

```c
svuint16x4_t svldnt1[_u16]_x4(svcount_t png, uint16_t const * rn);
```

### Description

Contiguous load non-temporal of halfwords to multiple consecutive vectors (immediate index)

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
LDNT1H { Zreg1.H - Zreg2.H }, PNreg1/Z, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LDNT1H--scalar-plus-immediate--consecutive-registers---Contiguous-load-non-temporal-of-halfwords-to-multiple-consecutive-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svldnt1[_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svldnt1%5B_u32%5D

### Signature (source notation)

```c
svuint32_t svldnt1[_u32](svbool_t pg, const uint32_t *base);
```

### Description

Unextended load, non-temporal

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
LDNT1W Zresult.S, Pg/Z, [Xarray, Xindex, LSL #2]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LDNT1W--scalar-plus-scalar--consecutive-registers---Contiguous-load-non-temporal-of-words-to-multiple-consecutive-vectors--scalar-index--

The general implementation is:

```asm
LDNT1W Zresult.S, Pg/Z, [Xbase, #0, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LDNT1W--scalar-plus-immediate--consecutive-registers---Contiguous-load-non-temporal-of-words-to-multiple-consecutive-vectors--immediate-index--

### Operation

Source operation ID: `SveOperation_svldnt1_bf16`

**Operation**



Return a vector in which each active element *i* contains `base[i]` and in which all other elements are zero.  Do not access memory for inactive elements.  Provide a hint to the system that the loaded memory is unlikely to be accessed again soon.

## svldnt1[_u32]_x2

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svldnt1%5B_u32%5D_x2

### Signature (source notation)

```c
svuint32x2_t svldnt1[_u32]_x2(svcount_t png, uint32_t const * rn);
```

### Description

Contiguous load non-temporal of words to multiple consecutive vectors (immediate index)

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
LDNT1W { Zreg1.S, Zreg2.S }, PNreg1/Z, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LDNT1W--scalar-plus-immediate--consecutive-registers---Contiguous-load-non-temporal-of-words-to-multiple-consecutive-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svldnt1[_u32]_x4

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svldnt1%5B_u32%5D_x4

### Signature (source notation)

```c
svuint32x4_t svldnt1[_u32]_x4(svcount_t png, uint32_t const * rn);
```

### Description

Contiguous load non-temporal of words to multiple consecutive vectors (immediate index)

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
LDNT1W { Zreg1.S - Zreg2.S }, PNreg1/Z, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LDNT1W--scalar-plus-immediate--consecutive-registers---Contiguous-load-non-temporal-of-words-to-multiple-consecutive-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svldnt1[_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svldnt1%5B_u64%5D

### Signature (source notation)

```c
svuint64_t svldnt1[_u64](svbool_t pg, const uint64_t *base);
```

### Description

Unextended load, non-temporal

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
LDNT1D Zresult.D, Pg/Z, [Xarray, Xindex, LSL #3]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LDNT1D--scalar-plus-scalar--consecutive-registers---Contiguous-load-non-temporal-of-doublewords-to-multiple-consecutive-vectors--scalar-index--

The general implementation is:

```asm
LDNT1D Zresult.D, Pg/Z, [Xbase, #0, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LDNT1D--scalar-plus-immediate--consecutive-registers---Contiguous-load-non-temporal-of-doublewords-to-multiple-consecutive-vectors--immediate-index--

### Operation

Source operation ID: `SveOperation_svldnt1_bf16`

**Operation**



Return a vector in which each active element *i* contains `base[i]` and in which all other elements are zero.  Do not access memory for inactive elements.  Provide a hint to the system that the loaded memory is unlikely to be accessed again soon.

## svldnt1[_u64]_x2

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svldnt1%5B_u64%5D_x2

### Signature (source notation)

```c
svuint64x2_t svldnt1[_u64]_x2(svcount_t png, uint64_t const * rn);
```

### Description

Contiguous load non-temporal of doublewords to multiple consecutive vectors (immediate index)

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
LDNT1D { Zreg1.D, Zreg2.D }, PNreg1/Z, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LDNT1D--scalar-plus-immediate--consecutive-registers---Contiguous-load-non-temporal-of-doublewords-to-multiple-consecutive-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svldnt1[_u64]_x4

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svldnt1%5B_u64%5D_x4

### Signature (source notation)

```c
svuint64x4_t svldnt1[_u64]_x4(svcount_t png, uint64_t const * rn);
```

### Description

Contiguous load non-temporal of doublewords to multiple consecutive vectors (immediate index)

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
LDNT1D { Zreg1.D - Zreg2.D }, PNreg1/Z, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LDNT1D--scalar-plus-immediate--consecutive-registers---Contiguous-load-non-temporal-of-doublewords-to-multiple-consecutive-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svldnt1[_u8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svldnt1%5B_u8%5D

### Signature (source notation)

```c
svuint8_t svldnt1[_u8](svbool_t pg, const uint8_t *base);
```

### Description

Unextended load, non-temporal

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
LDNT1B Zresult.B, Pg/Z, [Xarray, Xindex]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LDNT1B--scalar-plus-scalar--consecutive-registers---Contiguous-load-non-temporal-of-bytes-to-multiple-consecutive-vectors--scalar-index--

The general implementation is:

```asm
LDNT1B Zresult.B, Pg/Z, [Xbase, #0, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LDNT1B--scalar-plus-immediate--consecutive-registers---Contiguous-load-non-temporal-of-bytes-to-multiple-consecutive-vectors--immediate-index--

### Operation

Source operation ID: `SveOperation_svldnt1_bf16`

**Operation**



Return a vector in which each active element *i* contains `base[i]` and in which all other elements are zero.  Do not access memory for inactive elements.  Provide a hint to the system that the loaded memory is unlikely to be accessed again soon.

## svldnt1[_u8]_x2

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svldnt1%5B_u8%5D_x2

### Signature (source notation)

```c
svuint8x2_t svldnt1[_u8]_x2(svcount_t png, uint8_t const * rn);
```

### Description

Contiguous load non-temporal of bytes to multiple consecutive vectors (immediate index)

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
LDNT1B { Zreg1.B, Zreg2.B }, PNreg1/Z, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LDNT1B--scalar-plus-immediate--consecutive-registers---Contiguous-load-non-temporal-of-bytes-to-multiple-consecutive-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svldnt1[_u8]_x4

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svldnt1%5B_u8%5D_x4

### Signature (source notation)

```c
svuint8x4_t svldnt1[_u8]_x4(svcount_t png, uint8_t const * rn);
```

### Description

Contiguous load non-temporal of bytes to multiple consecutive vectors (immediate index)

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
LDNT1B { Zreg1.B - Zreg2.B }, PNreg1/Z, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LDNT1B--scalar-plus-immediate--consecutive-registers---Contiguous-load-non-temporal-of-bytes-to-multiple-consecutive-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svldnt1_vnum[_bf16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svldnt1_vnum%5B_bf16%5D

### Signature (source notation)

```c
svbfloat16_t svldnt1_vnum[_bf16](svbool_t pg, const bfloat16_t *base, int64_t vnum);
```

### Description

Unextended load, non-temporal

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
LDNT1H Zresult.H, Pg/Z, [Xbase, #vnum, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LDNT1H--scalar-plus-immediate--consecutive-registers---Contiguous-load-non-temporal-of-halfwords-to-multiple-consecutive-vectors--immediate-index--

The general implementation is:

```asm
LDNT1H Zresult.H, Pg/Z, [Xbase, Xindex, LSL #1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LDNT1H--scalar-plus-scalar--consecutive-registers---Contiguous-load-non-temporal-of-halfwords-to-multiple-consecutive-vectors--scalar-index--

### Operation

Source operation ID: `SveOperation_svldnt1_vnum_bf16`

**Operation**



Return a vector of *n* elements in which each active element *i* contains `base[n * vnum + i]` and in which all other elements are zero.  Do not access memory for inactive elements.  Provide a hint to the system that the loaded memory is unlikely to be accessed again soon.

## svldnt1_vnum[_bf16]_x2

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svldnt1_vnum%5B_bf16%5D_x2

### Signature (source notation)

```c
svbfloat16x2_t svldnt1_vnum[_bf16]_x2(svcount_t png, bfloat16_t const * rn, int64_t vnum);
```

### Description

Contiguous load non-temporal of halfwords to multiple consecutive vectors (immediate index)

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
    "register": "Xreg2"
  },
  "vnum": {
    "register": "Xreg3"
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
RDVL Xreg1, #1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/RDVL--Read-multiple-of-vector-register-size-to-scalar-register-

```asm
MADD Xreg1, Xreg1, Xreg3, Xreg2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/Base-Instructions/MADD--Multiply-add-

```asm
LDNT1H { Zreg1.H, Zreg2.H }, PNreg1/Z, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LDNT1H--scalar-plus-immediate--consecutive-registers---Contiguous-load-non-temporal-of-halfwords-to-multiple-consecutive-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svldnt1_vnum[_bf16]_x4

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svldnt1_vnum%5B_bf16%5D_x4

### Signature (source notation)

```c
svbfloat16x4_t svldnt1_vnum[_bf16]_x4(svcount_t png, bfloat16_t const * rn, int64_t vnum);
```

### Description

Contiguous load non-temporal of halfwords to multiple consecutive vectors (immediate index)

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
    "register": "Xreg2"
  },
  "vnum": {
    "register": "Xreg3"
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
RDVL Xreg1, #1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/RDVL--Read-multiple-of-vector-register-size-to-scalar-register-

```asm
MADD Xreg1, Xreg1, Xreg3, Xreg2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/Base-Instructions/MADD--Multiply-add-

```asm
LDNT1H { Zreg1.H - Zreg2.H }, PNreg1/Z, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LDNT1H--scalar-plus-immediate--consecutive-registers---Contiguous-load-non-temporal-of-halfwords-to-multiple-consecutive-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svldnt1_vnum[_f16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svldnt1_vnum%5B_f16%5D

### Signature (source notation)

```c
svfloat16_t svldnt1_vnum[_f16](svbool_t pg, const float16_t *base, int64_t vnum);
```

### Description

Unextended load, non-temporal

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
LDNT1H Zresult.H, Pg/Z, [Xbase, #vnum, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LDNT1H--scalar-plus-immediate--consecutive-registers---Contiguous-load-non-temporal-of-halfwords-to-multiple-consecutive-vectors--immediate-index--

The general implementation is:

```asm
LDNT1H Zresult.H, Pg/Z, [Xbase, Xindex, LSL #1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LDNT1H--scalar-plus-scalar--consecutive-registers---Contiguous-load-non-temporal-of-halfwords-to-multiple-consecutive-vectors--scalar-index--

### Operation

Source operation ID: `SveOperation_svldnt1_vnum_bf16`

**Operation**



Return a vector of *n* elements in which each active element *i* contains `base[n * vnum + i]` and in which all other elements are zero.  Do not access memory for inactive elements.  Provide a hint to the system that the loaded memory is unlikely to be accessed again soon.

## svldnt1_vnum[_f16]_x2

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svldnt1_vnum%5B_f16%5D_x2

### Signature (source notation)

```c
svfloat16x2_t svldnt1_vnum[_f16]_x2(svcount_t png, float16_t const * rn, int64_t vnum);
```

### Description

Contiguous load non-temporal of halfwords to multiple consecutive vectors (immediate index)

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
    "register": "Xreg2"
  },
  "vnum": {
    "register": "Xreg3"
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
RDVL Xreg1, #1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/RDVL--Read-multiple-of-vector-register-size-to-scalar-register-

```asm
MADD Xreg1, Xreg1, Xreg3, Xreg2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/Base-Instructions/MADD--Multiply-add-

```asm
LDNT1H { Zreg1.H, Zreg2.H }, PNreg1/Z, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LDNT1H--scalar-plus-immediate--consecutive-registers---Contiguous-load-non-temporal-of-halfwords-to-multiple-consecutive-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svldnt1_vnum[_f16]_x4

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svldnt1_vnum%5B_f16%5D_x4

### Signature (source notation)

```c
svfloat16x4_t svldnt1_vnum[_f16]_x4(svcount_t png, float16_t const * rn, int64_t vnum);
```

### Description

Contiguous load non-temporal of halfwords to multiple consecutive vectors (immediate index)

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
    "register": "Xreg2"
  },
  "vnum": {
    "register": "Xreg3"
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
RDVL Xreg1, #1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/RDVL--Read-multiple-of-vector-register-size-to-scalar-register-

```asm
MADD Xreg1, Xreg1, Xreg3, Xreg2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/Base-Instructions/MADD--Multiply-add-

```asm
LDNT1H { Zreg1.H - Zreg2.H }, PNreg1/Z, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LDNT1H--scalar-plus-immediate--consecutive-registers---Contiguous-load-non-temporal-of-halfwords-to-multiple-consecutive-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svldnt1_vnum[_f32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svldnt1_vnum%5B_f32%5D

### Signature (source notation)

```c
svfloat32_t svldnt1_vnum[_f32](svbool_t pg, const float32_t *base, int64_t vnum);
```

### Description

Unextended load, non-temporal

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
LDNT1W Zresult.S, Pg/Z, [Xbase, #vnum, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LDNT1W--scalar-plus-immediate--consecutive-registers---Contiguous-load-non-temporal-of-words-to-multiple-consecutive-vectors--immediate-index--

The general implementation is:

```asm
LDNT1W Zresult.S, Pg/Z, [Xbase, Xindex, LSL #2]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LDNT1W--scalar-plus-scalar--consecutive-registers---Contiguous-load-non-temporal-of-words-to-multiple-consecutive-vectors--scalar-index--

### Operation

Source operation ID: `SveOperation_svldnt1_vnum_bf16`

**Operation**



Return a vector of *n* elements in which each active element *i* contains `base[n * vnum + i]` and in which all other elements are zero.  Do not access memory for inactive elements.  Provide a hint to the system that the loaded memory is unlikely to be accessed again soon.

## svldnt1_vnum[_f32]_x2

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svldnt1_vnum%5B_f32%5D_x2

### Signature (source notation)

```c
svfloat32x2_t svldnt1_vnum[_f32]_x2(svcount_t png, float32_t const * rn, int64_t vnum);
```

### Description

Contiguous load non-temporal of words to multiple consecutive vectors (immediate index)

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
    "register": "Xreg2"
  },
  "vnum": {
    "register": "Xreg3"
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
RDVL Xreg1, #1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/RDVL--Read-multiple-of-vector-register-size-to-scalar-register-

```asm
MADD Xreg1, Xreg1, Xreg3, Xreg2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/Base-Instructions/MADD--Multiply-add-

```asm
LDNT1W { Zreg1.S, Zreg2.S }, PNreg1/Z, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LDNT1W--scalar-plus-immediate--consecutive-registers---Contiguous-load-non-temporal-of-words-to-multiple-consecutive-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svldnt1_vnum[_f32]_x4

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svldnt1_vnum%5B_f32%5D_x4

### Signature (source notation)

```c
svfloat32x4_t svldnt1_vnum[_f32]_x4(svcount_t png, float32_t const * rn, int64_t vnum);
```

### Description

Contiguous load non-temporal of words to multiple consecutive vectors (immediate index)

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
    "register": "Xreg2"
  },
  "vnum": {
    "register": "Xreg3"
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
RDVL Xreg1, #1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/RDVL--Read-multiple-of-vector-register-size-to-scalar-register-

```asm
MADD Xreg1, Xreg1, Xreg3, Xreg2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/Base-Instructions/MADD--Multiply-add-

```asm
LDNT1W { Zreg1.S - Zreg2.S }, PNreg1/Z, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LDNT1W--scalar-plus-immediate--consecutive-registers---Contiguous-load-non-temporal-of-words-to-multiple-consecutive-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

