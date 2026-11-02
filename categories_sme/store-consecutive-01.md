# SME / Store / Consecutive — Part 1

## svst1[_bf16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst1%5B_bf16%5D

### Signature (source notation)

```c
void svst1[_bf16](svbool_t pg, bfloat16_t *base, svbfloat16_t data);
```

### Description

Non-truncating store

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
ST1H Zdata.H, Pg, [Xarray, Xindex, LSL #1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST1H--scalar-plus-scalar--consecutive-registers---Contiguous-store-of-halfwords-from-multiple-consecutive-vectors--scalar-index--

The general implementation is:

```asm
ST1H Zdata.H, Pg, [Xbase, #0, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST1H--scalar-plus-immediate--consecutive-registers---Contiguous-store-of-halfwords-from-multiple-consecutive-vectors--immediate-index--

### Operation

Source operation ID: `SveOperation_svst1_bf16`

**Operation**



For each active element *i*, store `data[i]` to `base[i]`. Do not access memory for inactive elements.

## svst1[_bf16_x2]

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst1%5B_bf16_x2%5D

### Signature (source notation)

```c
void svst1[_bf16_x2](svcount_t png, bfloat16_t * rn, svbfloat16x2_t zt);
```

### Description

Contiguous store of halfwords from multiple consecutive vectors (immediate index)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Store / Consecutive

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
  "return_base_type": "void",
  "element_bit_size": "16",
  "value": "void"
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
  },
  "zt": {
    "Z multi-vector": "{ Zreg1.H, Zreg2.H }"
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
ST1H { Zreg1.H, Zreg2.H }, PNreg1, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST1H--scalar-plus-immediate--consecutive-registers---Contiguous-store-of-halfwords-from-multiple-consecutive-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svst1[_bf16_x4]

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst1%5B_bf16_x4%5D

### Signature (source notation)

```c
void svst1[_bf16_x4](svcount_t png, bfloat16_t * rn, svbfloat16x4_t zt);
```

### Description

Contiguous store of halfwords from multiple consecutive vectors (immediate index)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Store / Consecutive

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
  "return_base_type": "void",
  "element_bit_size": "16",
  "value": "void"
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
  },
  "zt": {
    "Z multi-vector": "{ Zreg1.H - Zreg2.H }"
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
ST1H { Zreg1.H - Zreg2.H }, PNreg1, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST1H--scalar-plus-immediate--consecutive-registers---Contiguous-store-of-halfwords-from-multiple-consecutive-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svst1[_f16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst1%5B_f16%5D

### Signature (source notation)

```c
void svst1[_f16](svbool_t pg, float16_t *base, svfloat16_t data);
```

### Description

Non-truncating store

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
ST1H Zdata.H, Pg, [Xarray, Xindex, LSL #1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST1H--scalar-plus-scalar--consecutive-registers---Contiguous-store-of-halfwords-from-multiple-consecutive-vectors--scalar-index--

The general implementation is:

```asm
ST1H Zdata.H, Pg, [Xbase, #0, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST1H--scalar-plus-immediate--consecutive-registers---Contiguous-store-of-halfwords-from-multiple-consecutive-vectors--immediate-index--

### Operation

Source operation ID: `SveOperation_svst1_bf16`

**Operation**



For each active element *i*, store `data[i]` to `base[i]`. Do not access memory for inactive elements.

## svst1[_f16_x2]

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst1%5B_f16_x2%5D

### Signature (source notation)

```c
void svst1[_f16_x2](svcount_t png, float16_t * rn, svfloat16x2_t zt);
```

### Description

Contiguous store of halfwords from multiple consecutive vectors (immediate index)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Store / Consecutive

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
  "return_base_type": "void",
  "element_bit_size": "16",
  "value": "void"
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
  },
  "zt": {
    "Z multi-vector": "{ Zreg1.H, Zreg2.H }"
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
ST1H { Zreg1.H, Zreg2.H }, PNreg1, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST1H--scalar-plus-immediate--consecutive-registers---Contiguous-store-of-halfwords-from-multiple-consecutive-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svst1[_f16_x4]

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst1%5B_f16_x4%5D

### Signature (source notation)

```c
void svst1[_f16_x4](svcount_t png, float16_t * rn, svfloat16x4_t zt);
```

### Description

Contiguous store of halfwords from multiple consecutive vectors (immediate index)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Store / Consecutive

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
  "return_base_type": "void",
  "element_bit_size": "16",
  "value": "void"
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
  },
  "zt": {
    "Z multi-vector": "{ Zreg1.H - Zreg2.H }"
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
ST1H { Zreg1.H - Zreg2.H }, PNreg1, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST1H--scalar-plus-immediate--consecutive-registers---Contiguous-store-of-halfwords-from-multiple-consecutive-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svst1[_f32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst1%5B_f32%5D

### Signature (source notation)

```c
void svst1[_f32](svbool_t pg, float32_t *base, svfloat32_t data);
```

### Description

Non-truncating store

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
ST1W Zdata.S, Pg, [Xarray, Xindex, LSL #2]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST1W--scalar-plus-scalar--consecutive-registers---Contiguous-store-of-words-from-multiple-consecutive-vectors--scalar-index--

The general implementation is:

```asm
ST1W Zdata.S, Pg, [Xbase, #0, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST1W--scalar-plus-immediate--consecutive-registers---Contiguous-store-of-words-from-multiple-consecutive-vectors--immediate-index--

### Operation

Source operation ID: `SveOperation_svst1_bf16`

**Operation**



For each active element *i*, store `data[i]` to `base[i]`. Do not access memory for inactive elements.

## svst1[_f32_x2]

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst1%5B_f32_x2%5D

### Signature (source notation)

```c
void svst1[_f32_x2](svcount_t png, float32_t * rn, svfloat32x2_t zt);
```

### Description

Contiguous store of words from multiple consecutive vectors (immediate index)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Store / Consecutive

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
  "return_base_type": "void",
  "element_bit_size": "32",
  "value": "void"
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
  },
  "zt": {
    "Z multi-vector": "{ Zreg1.S, Zreg2.S }"
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
ST1W { Zreg1.S, Zreg2.S }, PNreg1, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST1W--scalar-plus-immediate--consecutive-registers---Contiguous-store-of-words-from-multiple-consecutive-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svst1[_f32_x4]

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst1%5B_f32_x4%5D

### Signature (source notation)

```c
void svst1[_f32_x4](svcount_t png, float32_t * rn, svfloat32x4_t zt);
```

### Description

Contiguous store of words from multiple consecutive vectors (immediate index)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Store / Consecutive

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
  "return_base_type": "void",
  "element_bit_size": "32",
  "value": "void"
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
  },
  "zt": {
    "Z multi-vector": "{ Zreg1.S - Zreg2.S }"
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
ST1W { Zreg1.S - Zreg2.S }, PNreg1, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST1W--scalar-plus-immediate--consecutive-registers---Contiguous-store-of-words-from-multiple-consecutive-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svst1[_f64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst1%5B_f64%5D

### Signature (source notation)

```c
void svst1[_f64](svbool_t pg, float64_t *base, svfloat64_t data);
```

### Description

Non-truncating store

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
ST1D Zdata.D, Pg, [Xarray, Xindex, LSL #3]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST1D--scalar-plus-scalar--consecutive-registers---Contiguous-store-of-doublewords-from-multiple-consecutive-vectors--scalar-index--

The general implementation is:

```asm
ST1D Zdata.D, Pg, [Xbase, #0, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST1D--scalar-plus-immediate--consecutive-registers---Contiguous-store-of-doublewords-from-multiple-consecutive-vectors--immediate-index--

### Operation

Source operation ID: `SveOperation_svst1_bf16`

**Operation**



For each active element *i*, store `data[i]` to `base[i]`. Do not access memory for inactive elements.

## svst1[_f64_x2]

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst1%5B_f64_x2%5D

### Signature (source notation)

```c
void svst1[_f64_x2](svcount_t png, float64_t * rn, svfloat64x2_t zt);
```

### Description

Contiguous store of doublewords from multiple consecutive vectors (immediate index)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Store / Consecutive

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
  "return_base_type": "void",
  "element_bit_size": "64",
  "value": "void"
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
  },
  "zt": {
    "Z multi-vector": "{ Zreg1.D, Zreg2.D }"
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
ST1D { Zreg1.D, Zreg2.D }, PNreg1, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST1D--scalar-plus-immediate--consecutive-registers---Contiguous-store-of-doublewords-from-multiple-consecutive-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svst1[_f64_x4]

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst1%5B_f64_x4%5D

### Signature (source notation)

```c
void svst1[_f64_x4](svcount_t png, float64_t * rn, svfloat64x4_t zt);
```

### Description

Contiguous store of doublewords from multiple consecutive vectors (immediate index)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Store / Consecutive

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
  "return_base_type": "void",
  "element_bit_size": "64",
  "value": "void"
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
  },
  "zt": {
    "Z multi-vector": "{ Zreg1.D - Zreg2.D }"
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
ST1D { Zreg1.D - Zreg2.D }, PNreg1, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST1D--scalar-plus-immediate--consecutive-registers---Contiguous-store-of-doublewords-from-multiple-consecutive-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svst1[_mf8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst1%5B_mf8%5D

### Signature (source notation)

```c
void svst1[_mf8](svbool_t pg, mfloat8_t *base, svmfloat8_t data);
```

### Description

Non-truncating store

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
    "register": "Zdata.B"
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
ST1B Zdata.B, Pg, [Xarray, Xindex]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST1B--scalar-plus-scalar--consecutive-registers---Contiguous-store-of-bytes-from-multiple-consecutive-vectors--scalar-index--

The general implementation is:

```asm
ST1B Zdata.B, Pg, [Xbase, #0, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST1B--scalar-plus-immediate--consecutive-registers---Contiguous-store-of-bytes-from-multiple-consecutive-vectors--immediate-index--

### Operation

Source operation ID: `SveOperation_svst1_bf16`

**Operation**



For each active element *i*, store `data[i]` to `base[i]`. Do not access memory for inactive elements.

## svst1[_mf8_x2]

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst1%5B_mf8_x2%5D

### Signature (source notation)

```c
void svst1[_mf8_x2](svcount_t png, mfloat8_t * rn, svmfloat8x2_t zt);
```

### Description

Contiguous store of bytes from multiple consecutive vectors (immediate index)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Store / Consecutive

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
  "return_base_type": "void",
  "element_bit_size": "8",
  "value": "void"
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
  },
  "zt": {
    "Z multi-vector": "{ Zreg1.B, Zreg2.B }"
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
ST1B { Zreg1.B, Zreg2.B }, PNreg1, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST1B--scalar-plus-immediate--consecutive-registers---Contiguous-store-of-bytes-from-multiple-consecutive-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svst1[_mf8_x4]

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst1%5B_mf8_x4%5D

### Signature (source notation)

```c
void svst1[_mf8_x4](svcount_t png, mfloat8_t * rn, svmfloat8x4_t zt);
```

### Description

Contiguous store of bytes from multiple consecutive vectors (immediate index)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Store / Consecutive

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
  "return_base_type": "void",
  "element_bit_size": "8",
  "value": "void"
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
  },
  "zt": {
    "Z multi-vector": "{ Zreg1.B - Zreg2.B }"
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
ST1B { Zreg1.B - Zreg2.B }, PNreg1, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST1B--scalar-plus-immediate--consecutive-registers---Contiguous-store-of-bytes-from-multiple-consecutive-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svst1[_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst1%5B_s16%5D

### Signature (source notation)

```c
void svst1[_s16](svbool_t pg, int16_t *base, svint16_t data);
```

### Description

Non-truncating store

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
ST1H Zdata.H, Pg, [Xarray, Xindex, LSL #1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST1H--scalar-plus-scalar--consecutive-registers---Contiguous-store-of-halfwords-from-multiple-consecutive-vectors--scalar-index--

The general implementation is:

```asm
ST1H Zdata.H, Pg, [Xbase, #0, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST1H--scalar-plus-immediate--consecutive-registers---Contiguous-store-of-halfwords-from-multiple-consecutive-vectors--immediate-index--

### Operation

Source operation ID: `SveOperation_svst1_bf16`

**Operation**



For each active element *i*, store `data[i]` to `base[i]`. Do not access memory for inactive elements.

## svst1[_s16_x2]

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst1%5B_s16_x2%5D

### Signature (source notation)

```c
void svst1[_s16_x2](svcount_t png, int16_t * rn, svint16x2_t zt);
```

### Description

Contiguous store of halfwords from multiple consecutive vectors (immediate index)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Store / Consecutive

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
  "return_base_type": "void",
  "element_bit_size": "16",
  "value": "void"
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
  },
  "zt": {
    "Z multi-vector": "{ Zreg1.H, Zreg2.H }"
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
ST1H { Zreg1.H, Zreg2.H }, PNreg1, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST1H--scalar-plus-immediate--consecutive-registers---Contiguous-store-of-halfwords-from-multiple-consecutive-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svst1[_s16_x4]

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst1%5B_s16_x4%5D

### Signature (source notation)

```c
void svst1[_s16_x4](svcount_t png, int16_t * rn, svint16x4_t zt);
```

### Description

Contiguous store of halfwords from multiple consecutive vectors (immediate index)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Store / Consecutive

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
  "return_base_type": "void",
  "element_bit_size": "16",
  "value": "void"
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
  },
  "zt": {
    "Z multi-vector": "{ Zreg1.H - Zreg2.H }"
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
ST1H { Zreg1.H - Zreg2.H }, PNreg1, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST1H--scalar-plus-immediate--consecutive-registers---Contiguous-store-of-halfwords-from-multiple-consecutive-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svst1[_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst1%5B_s32%5D

### Signature (source notation)

```c
void svst1[_s32](svbool_t pg, int32_t *base, svint32_t data);
```

### Description

Non-truncating store

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
ST1W Zdata.S, Pg, [Xarray, Xindex, LSL #2]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST1W--scalar-plus-scalar--consecutive-registers---Contiguous-store-of-words-from-multiple-consecutive-vectors--scalar-index--

The general implementation is:

```asm
ST1W Zdata.S, Pg, [Xbase, #0, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST1W--scalar-plus-immediate--consecutive-registers---Contiguous-store-of-words-from-multiple-consecutive-vectors--immediate-index--

### Operation

Source operation ID: `SveOperation_svst1_bf16`

**Operation**



For each active element *i*, store `data[i]` to `base[i]`. Do not access memory for inactive elements.

## svst1[_s32_x2]

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst1%5B_s32_x2%5D

### Signature (source notation)

```c
void svst1[_s32_x2](svcount_t png, int32_t * rn, svint32x2_t zt);
```

### Description

Contiguous store of words from multiple consecutive vectors (immediate index)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Store / Consecutive

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
  "return_base_type": "void",
  "element_bit_size": "32",
  "value": "void"
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
  },
  "zt": {
    "Z multi-vector": "{ Zreg1.S, Zreg2.S }"
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
ST1W { Zreg1.S, Zreg2.S }, PNreg1, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST1W--scalar-plus-immediate--consecutive-registers---Contiguous-store-of-words-from-multiple-consecutive-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svst1[_s32_x4]

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst1%5B_s32_x4%5D

### Signature (source notation)

```c
void svst1[_s32_x4](svcount_t png, int32_t * rn, svint32x4_t zt);
```

### Description

Contiguous store of words from multiple consecutive vectors (immediate index)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Store / Consecutive

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
  "return_base_type": "void",
  "element_bit_size": "32",
  "value": "void"
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
  },
  "zt": {
    "Z multi-vector": "{ Zreg1.S - Zreg2.S }"
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
ST1W { Zreg1.S - Zreg2.S }, PNreg1, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST1W--scalar-plus-immediate--consecutive-registers---Contiguous-store-of-words-from-multiple-consecutive-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svst1[_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst1%5B_s64%5D

### Signature (source notation)

```c
void svst1[_s64](svbool_t pg, int64_t *base, svint64_t data);
```

### Description

Non-truncating store

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
ST1D Zdata.D, Pg, [Xarray, Xindex, LSL #3]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST1D--scalar-plus-scalar--consecutive-registers---Contiguous-store-of-doublewords-from-multiple-consecutive-vectors--scalar-index--

The general implementation is:

```asm
ST1D Zdata.D, Pg, [Xbase, #0, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST1D--scalar-plus-immediate--consecutive-registers---Contiguous-store-of-doublewords-from-multiple-consecutive-vectors--immediate-index--

### Operation

Source operation ID: `SveOperation_svst1_bf16`

**Operation**



For each active element *i*, store `data[i]` to `base[i]`. Do not access memory for inactive elements.

## svst1[_s64_x2]

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst1%5B_s64_x2%5D

### Signature (source notation)

```c
void svst1[_s64_x2](svcount_t png, int64_t * rn, svint64x2_t zt);
```

### Description

Contiguous store of doublewords from multiple consecutive vectors (immediate index)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Store / Consecutive

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
  "return_base_type": "void",
  "element_bit_size": "64",
  "value": "void"
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
  },
  "zt": {
    "Z multi-vector": "{ Zreg1.D, Zreg2.D }"
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
ST1D { Zreg1.D, Zreg2.D }, PNreg1, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST1D--scalar-plus-immediate--consecutive-registers---Contiguous-store-of-doublewords-from-multiple-consecutive-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svst1[_s64_x4]

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst1%5B_s64_x4%5D

### Signature (source notation)

```c
void svst1[_s64_x4](svcount_t png, int64_t * rn, svint64x4_t zt);
```

### Description

Contiguous store of doublewords from multiple consecutive vectors (immediate index)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Store / Consecutive

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
  "return_base_type": "void",
  "element_bit_size": "64",
  "value": "void"
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
  },
  "zt": {
    "Z multi-vector": "{ Zreg1.D - Zreg2.D }"
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
ST1D { Zreg1.D - Zreg2.D }, PNreg1, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST1D--scalar-plus-immediate--consecutive-registers---Contiguous-store-of-doublewords-from-multiple-consecutive-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svst1[_s8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst1%5B_s8%5D

### Signature (source notation)

```c
void svst1[_s8](svbool_t pg, int8_t *base, svint8_t data);
```

### Description

Non-truncating store

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
    "register": "Zdata.B"
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
ST1B Zdata.B, Pg, [Xarray, Xindex]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST1B--scalar-plus-scalar--consecutive-registers---Contiguous-store-of-bytes-from-multiple-consecutive-vectors--scalar-index--

The general implementation is:

```asm
ST1B Zdata.B, Pg, [Xbase, #0, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST1B--scalar-plus-immediate--consecutive-registers---Contiguous-store-of-bytes-from-multiple-consecutive-vectors--immediate-index--

### Operation

Source operation ID: `SveOperation_svst1_bf16`

**Operation**



For each active element *i*, store `data[i]` to `base[i]`. Do not access memory for inactive elements.

## svst1[_s8_x2]

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst1%5B_s8_x2%5D

### Signature (source notation)

```c
void svst1[_s8_x2](svcount_t png, int8_t * rn, svint8x2_t zt);
```

### Description

Contiguous store of bytes from multiple consecutive vectors (immediate index)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Store / Consecutive

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
  "return_base_type": "void",
  "element_bit_size": "8",
  "value": "void"
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
  },
  "zt": {
    "Z multi-vector": "{ Zreg1.B, Zreg2.B }"
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
ST1B { Zreg1.B, Zreg2.B }, PNreg1, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST1B--scalar-plus-immediate--consecutive-registers---Contiguous-store-of-bytes-from-multiple-consecutive-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svst1[_s8_x4]

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst1%5B_s8_x4%5D

### Signature (source notation)

```c
void svst1[_s8_x4](svcount_t png, int8_t * rn, svint8x4_t zt);
```

### Description

Contiguous store of bytes from multiple consecutive vectors (immediate index)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Store / Consecutive

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
  "return_base_type": "void",
  "element_bit_size": "8",
  "value": "void"
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
  },
  "zt": {
    "Z multi-vector": "{ Zreg1.B - Zreg2.B }"
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
ST1B { Zreg1.B - Zreg2.B }, PNreg1, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST1B--scalar-plus-immediate--consecutive-registers---Contiguous-store-of-bytes-from-multiple-consecutive-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svst1[_u16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst1%5B_u16%5D

### Signature (source notation)

```c
void svst1[_u16](svbool_t pg, uint16_t *base, svuint16_t data);
```

### Description

Non-truncating store

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
ST1H Zdata.H, Pg, [Xarray, Xindex, LSL #1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST1H--scalar-plus-scalar--consecutive-registers---Contiguous-store-of-halfwords-from-multiple-consecutive-vectors--scalar-index--

The general implementation is:

```asm
ST1H Zdata.H, Pg, [Xbase, #0, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST1H--scalar-plus-immediate--consecutive-registers---Contiguous-store-of-halfwords-from-multiple-consecutive-vectors--immediate-index--

### Operation

Source operation ID: `SveOperation_svst1_bf16`

**Operation**



For each active element *i*, store `data[i]` to `base[i]`. Do not access memory for inactive elements.

## svst1[_u16_x2]

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst1%5B_u16_x2%5D

### Signature (source notation)

```c
void svst1[_u16_x2](svcount_t png, uint16_t * rn, svuint16x2_t zt);
```

### Description

Contiguous store of halfwords from multiple consecutive vectors (immediate index)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Store / Consecutive

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
  "return_base_type": "void",
  "element_bit_size": "16",
  "value": "void"
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
  },
  "zt": {
    "Z multi-vector": "{ Zreg1.H, Zreg2.H }"
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
ST1H { Zreg1.H, Zreg2.H }, PNreg1, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST1H--scalar-plus-immediate--consecutive-registers---Contiguous-store-of-halfwords-from-multiple-consecutive-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svst1[_u16_x4]

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst1%5B_u16_x4%5D

### Signature (source notation)

```c
void svst1[_u16_x4](svcount_t png, uint16_t * rn, svuint16x4_t zt);
```

### Description

Contiguous store of halfwords from multiple consecutive vectors (immediate index)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Store / Consecutive

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
  "return_base_type": "void",
  "element_bit_size": "16",
  "value": "void"
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
  },
  "zt": {
    "Z multi-vector": "{ Zreg1.H - Zreg2.H }"
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
ST1H { Zreg1.H - Zreg2.H }, PNreg1, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST1H--scalar-plus-immediate--consecutive-registers---Contiguous-store-of-halfwords-from-multiple-consecutive-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svst1[_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst1%5B_u32%5D

### Signature (source notation)

```c
void svst1[_u32](svbool_t pg, uint32_t *base, svuint32_t data);
```

### Description

Non-truncating store

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
ST1W Zdata.S, Pg, [Xarray, Xindex, LSL #2]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST1W--scalar-plus-scalar--consecutive-registers---Contiguous-store-of-words-from-multiple-consecutive-vectors--scalar-index--

The general implementation is:

```asm
ST1W Zdata.S, Pg, [Xbase, #0, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST1W--scalar-plus-immediate--consecutive-registers---Contiguous-store-of-words-from-multiple-consecutive-vectors--immediate-index--

### Operation

Source operation ID: `SveOperation_svst1_bf16`

**Operation**



For each active element *i*, store `data[i]` to `base[i]`. Do not access memory for inactive elements.

## svst1[_u32_x2]

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst1%5B_u32_x2%5D

### Signature (source notation)

```c
void svst1[_u32_x2](svcount_t png, uint32_t * rn, svuint32x2_t zt);
```

### Description

Contiguous store of words from multiple consecutive vectors (immediate index)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Store / Consecutive

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
  "return_base_type": "void",
  "element_bit_size": "32",
  "value": "void"
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
  },
  "zt": {
    "Z multi-vector": "{ Zreg1.S, Zreg2.S }"
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
ST1W { Zreg1.S, Zreg2.S }, PNreg1, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST1W--scalar-plus-immediate--consecutive-registers---Contiguous-store-of-words-from-multiple-consecutive-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svst1[_u32_x4]

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst1%5B_u32_x4%5D

### Signature (source notation)

```c
void svst1[_u32_x4](svcount_t png, uint32_t * rn, svuint32x4_t zt);
```

### Description

Contiguous store of words from multiple consecutive vectors (immediate index)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Store / Consecutive

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
  "return_base_type": "void",
  "element_bit_size": "32",
  "value": "void"
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
  },
  "zt": {
    "Z multi-vector": "{ Zreg1.S - Zreg2.S }"
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
ST1W { Zreg1.S - Zreg2.S }, PNreg1, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST1W--scalar-plus-immediate--consecutive-registers---Contiguous-store-of-words-from-multiple-consecutive-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svst1[_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst1%5B_u64%5D

### Signature (source notation)

```c
void svst1[_u64](svbool_t pg, uint64_t *base, svuint64_t data);
```

### Description

Non-truncating store

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
ST1D Zdata.D, Pg, [Xarray, Xindex, LSL #3]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST1D--scalar-plus-scalar--consecutive-registers---Contiguous-store-of-doublewords-from-multiple-consecutive-vectors--scalar-index--

The general implementation is:

```asm
ST1D Zdata.D, Pg, [Xbase, #0, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST1D--scalar-plus-immediate--consecutive-registers---Contiguous-store-of-doublewords-from-multiple-consecutive-vectors--immediate-index--

### Operation

Source operation ID: `SveOperation_svst1_bf16`

**Operation**



For each active element *i*, store `data[i]` to `base[i]`. Do not access memory for inactive elements.

## svst1[_u64_x2]

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst1%5B_u64_x2%5D

### Signature (source notation)

```c
void svst1[_u64_x2](svcount_t png, uint64_t * rn, svuint64x2_t zt);
```

### Description

Contiguous store of doublewords from multiple consecutive vectors (immediate index)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Store / Consecutive

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
  "return_base_type": "void",
  "element_bit_size": "64",
  "value": "void"
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
  },
  "zt": {
    "Z multi-vector": "{ Zreg1.D, Zreg2.D }"
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
ST1D { Zreg1.D, Zreg2.D }, PNreg1, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST1D--scalar-plus-immediate--consecutive-registers---Contiguous-store-of-doublewords-from-multiple-consecutive-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svst1[_u64_x4]

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst1%5B_u64_x4%5D

### Signature (source notation)

```c
void svst1[_u64_x4](svcount_t png, uint64_t * rn, svuint64x4_t zt);
```

### Description

Contiguous store of doublewords from multiple consecutive vectors (immediate index)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Store / Consecutive

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
  "return_base_type": "void",
  "element_bit_size": "64",
  "value": "void"
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
  },
  "zt": {
    "Z multi-vector": "{ Zreg1.D - Zreg2.D }"
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
ST1D { Zreg1.D - Zreg2.D }, PNreg1, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST1D--scalar-plus-immediate--consecutive-registers---Contiguous-store-of-doublewords-from-multiple-consecutive-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svst1[_u8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst1%5B_u8%5D

### Signature (source notation)

```c
void svst1[_u8](svbool_t pg, uint8_t *base, svuint8_t data);
```

### Description

Non-truncating store

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
    "register": "Zdata.B"
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
ST1B Zdata.B, Pg, [Xarray, Xindex]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST1B--scalar-plus-scalar--consecutive-registers---Contiguous-store-of-bytes-from-multiple-consecutive-vectors--scalar-index--

The general implementation is:

```asm
ST1B Zdata.B, Pg, [Xbase, #0, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST1B--scalar-plus-immediate--consecutive-registers---Contiguous-store-of-bytes-from-multiple-consecutive-vectors--immediate-index--

### Operation

Source operation ID: `SveOperation_svst1_bf16`

**Operation**



For each active element *i*, store `data[i]` to `base[i]`. Do not access memory for inactive elements.

## svst1[_u8_x2]

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst1%5B_u8_x2%5D

### Signature (source notation)

```c
void svst1[_u8_x2](svcount_t png, uint8_t * rn, svuint8x2_t zt);
```

### Description

Contiguous store of bytes from multiple consecutive vectors (immediate index)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Store / Consecutive

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
  "return_base_type": "void",
  "element_bit_size": "8",
  "value": "void"
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
  },
  "zt": {
    "Z multi-vector": "{ Zreg1.B, Zreg2.B }"
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
ST1B { Zreg1.B, Zreg2.B }, PNreg1, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST1B--scalar-plus-immediate--consecutive-registers---Contiguous-store-of-bytes-from-multiple-consecutive-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svst1[_u8_x4]

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst1%5B_u8_x4%5D

### Signature (source notation)

```c
void svst1[_u8_x4](svcount_t png, uint8_t * rn, svuint8x4_t zt);
```

### Description

Contiguous store of bytes from multiple consecutive vectors (immediate index)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Store / Consecutive

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
  "return_base_type": "void",
  "element_bit_size": "8",
  "value": "void"
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
  },
  "zt": {
    "Z multi-vector": "{ Zreg1.B - Zreg2.B }"
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
ST1B { Zreg1.B - Zreg2.B }, PNreg1, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST1B--scalar-plus-immediate--consecutive-registers---Contiguous-store-of-bytes-from-multiple-consecutive-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svst1_hor_vnum_za128

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst1_hor_vnum_za128

### Signature (source notation)

```c
void svst1_hor_vnum_za128(uint64_t tile, uint32_t slice, svbool_t pg, void * ptr, int64_t vnum)
    __arm_streaming __arm_in("za");
```

### Description

Contiguous store of quadwords from 128-bit element ZA tile slice

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Store / Consecutive

- SME attributes: `__arm_streaming`; `__arm_in("za")`

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
ST1Q {ZA0H.Q[Wreg1, imm1]}, Preg1, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/ST1Q--Contiguous-store-of-quadwords-from-128-bit-element-ZA-tile-slice-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svst1_hor_vnum_za16

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst1_hor_vnum_za16

### Signature (source notation)

```c
void svst1_hor_vnum_za16(uint64_t tile, uint32_t slice, svbool_t pg, void * ptr, int64_t vnum)
    __arm_streaming __arm_in("za");
```

### Description

Contiguous store of halfwords from 16-bit element ZA tile slice

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Store / Consecutive

- SME attributes: `__arm_streaming`; `__arm_in("za")`

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
ST1H {ZA0H.H[Wreg1, imm1]}, Preg1, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/ST1H--scalar-plus-scalar--tile-slice---Contiguous-store-of-halfwords-from-16-bit-element-ZA-tile-slice-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svst1_hor_vnum_za32

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst1_hor_vnum_za32

### Signature (source notation)

```c
void svst1_hor_vnum_za32(uint64_t tile, uint32_t slice, svbool_t pg, void * ptr, int64_t vnum)
    __arm_streaming __arm_in("za");
```

### Description

Contiguous store of words from 32-bit element ZA tile slice

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Store / Consecutive

- SME attributes: `__arm_streaming`; `__arm_in("za")`

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
ST1W {ZA0H.S[Wreg1, imm1]}, Preg1, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/ST1W--scalar-plus-scalar--tile-slice---Contiguous-store-of-words-from-32-bit-element-ZA-tile-slice-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svst1_hor_vnum_za64

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst1_hor_vnum_za64

### Signature (source notation)

```c
void svst1_hor_vnum_za64(uint64_t tile, uint32_t slice, svbool_t pg, void * ptr, int64_t vnum)
    __arm_streaming __arm_in("za");
```

### Description

Contiguous store of doublewords from 64-bit element ZA tile slice

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Store / Consecutive

- SME attributes: `__arm_streaming`; `__arm_in("za")`

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
ST1D {ZA0H.D[Wreg1, imm1]}, Preg1, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/ST1D--scalar-plus-scalar--tile-slice---Contiguous-store-of-doublewords-from-64-bit-element-ZA-tile-slice-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svst1_hor_vnum_za8

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst1_hor_vnum_za8

### Signature (source notation)

```c
void svst1_hor_vnum_za8(uint64_t tile, uint32_t slice, svbool_t pg, void * ptr, int64_t vnum)
    __arm_streaming __arm_in("za");
```

### Description

Contiguous store of bytes from 8-bit element ZA tile slice

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Store / Consecutive

- SME attributes: `__arm_streaming`; `__arm_in("za")`

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
ST1B {ZA0H.B[Wreg1, imm1]}, Preg1, [Xreg1, Xreg2]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/ST1B--scalar-plus-scalar--tile-slice---Contiguous-store-of-bytes-from-8-bit-element-ZA-tile-slice-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svst1_hor_za128

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst1_hor_za128

### Signature (source notation)

```c
void svst1_hor_za128(uint64_t tile, uint32_t slice, svbool_t pg, void * ptr)
    __arm_streaming __arm_in("za");
```

### Description

Contiguous store of quadwords from 128-bit element ZA tile slice

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Store / Consecutive

- SME attributes: `__arm_streaming`; `__arm_in("za")`

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
ST1Q {ZA0H.Q[Wreg1, imm1]}, Preg1, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/ST1Q--Contiguous-store-of-quadwords-from-128-bit-element-ZA-tile-slice-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svst1_hor_za16

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst1_hor_za16

### Signature (source notation)

```c
void svst1_hor_za16(uint64_t tile, uint32_t slice, svbool_t pg, void * ptr)
    __arm_streaming __arm_in("za");
```

### Description

Contiguous store of halfwords from 16-bit element ZA tile slice

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Store / Consecutive

- SME attributes: `__arm_streaming`; `__arm_in("za")`

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
ST1H {ZA0H.H[Wreg1, imm1]}, Preg1, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/ST1H--scalar-plus-scalar--tile-slice---Contiguous-store-of-halfwords-from-16-bit-element-ZA-tile-slice-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svst1_hor_za32

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst1_hor_za32

### Signature (source notation)

```c
void svst1_hor_za32(uint64_t tile, uint32_t slice, svbool_t pg, void * ptr)
    __arm_streaming __arm_in("za");
```

### Description

Contiguous store of words from 32-bit element ZA tile slice

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Store / Consecutive

- SME attributes: `__arm_streaming`; `__arm_in("za")`

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
ST1W {ZA0H.S[Wreg1, imm1]}, Preg1, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/ST1W--scalar-plus-scalar--tile-slice---Contiguous-store-of-words-from-32-bit-element-ZA-tile-slice-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svst1_hor_za64

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst1_hor_za64

### Signature (source notation)

```c
void svst1_hor_za64(uint64_t tile, uint32_t slice, svbool_t pg, void * ptr)
    __arm_streaming __arm_in("za");
```

### Description

Contiguous store of doublewords from 64-bit element ZA tile slice

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Store / Consecutive

- SME attributes: `__arm_streaming`; `__arm_in("za")`

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
ST1D {ZA0H.D[Wreg1, imm1]}, Preg1, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/ST1D--scalar-plus-scalar--tile-slice---Contiguous-store-of-doublewords-from-64-bit-element-ZA-tile-slice-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svst1_hor_za8

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst1_hor_za8

### Signature (source notation)

```c
void svst1_hor_za8(uint64_t tile, uint32_t slice, svbool_t pg, void * ptr)
    __arm_streaming __arm_in("za");
```

### Description

Contiguous store of bytes from 8-bit element ZA tile slice

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Store / Consecutive

- SME attributes: `__arm_streaming`; `__arm_in("za")`

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
ST1B {ZA0H.B[Wreg1, imm1]}, Preg1, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/ST1B--scalar-plus-scalar--tile-slice---Contiguous-store-of-bytes-from-8-bit-element-ZA-tile-slice-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svst1_ver_vnum_za128

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst1_ver_vnum_za128

### Signature (source notation)

```c
void svst1_ver_vnum_za128(uint64_t tile, uint32_t slice, svbool_t pg, void * ptr, int64_t vnum)
    __arm_streaming __arm_in("za");
```

### Description

Contiguous store of quadwords from 128-bit element ZA tile slice

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Store / Consecutive

- SME attributes: `__arm_streaming`; `__arm_in("za")`

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
ST1Q {ZA0V.Q[Wreg1, imm1]}, Preg1, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/ST1Q--Contiguous-store-of-quadwords-from-128-bit-element-ZA-tile-slice-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

