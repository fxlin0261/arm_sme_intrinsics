# SME / Store / Consecutive — Part 6

## svst4_vnum[_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst4_vnum%5B_u64%5D

### Signature (source notation)

```c
void svst4_vnum[_u64](svbool_t pg, uint64_t *base, int64_t vnum, svuint64x4_t data);
```

### Description

Store four vectors into four-element tuples

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
    "register": "{Zdata0.D - Zdata3.D}"
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

When vnum is a multiple of 4 in the range [-32, 28], this intrinsic can use:

```asm
ST4D {Zdata0.D - Zdata3.D}, Pg, [Xbase, #vnum, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST4D--scalar-plus-immediate---Contiguous-store-four-doubleword-structures-from-four-vectors--immediate-index--

The general implementation is:

```asm
ST4D {Zdata0.D - Zdata3.D}, Pg, [Xbase, Xindex, LSL #3]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST4D--scalar-plus-scalar---Contiguous-store-four-doubleword-structures-from-four-vectors--scalar-index--

### Operation

Source operation ID: `SveOperation_svst4_vnum_bf16`

**Operation**



For each active element *i* and for each vector index *j*, store `data[j][i]` to `base[n * vnum + i * 4 + j]`, where *n* is the number of elements in `data[j]`. Do not access memory for inactive elements.

## svst4_vnum[_u8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst4_vnum%5B_u8%5D

### Signature (source notation)

```c
void svst4_vnum[_u8](svbool_t pg, uint8_t *base, int64_t vnum, svuint8x4_t data);
```

### Description

Store four vectors into four-element tuples

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
    "register": "{Zdata0.B - Zdata3.B}"
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

When vnum is a multiple of 4 in the range [-32, 28], this intrinsic can use:

```asm
ST4B {Zdata0.B - Zdata3.B}, Pg, [Xbase, #vnum, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST4B--scalar-plus-immediate---Contiguous-store-four-byte-structures-from-four-vectors--immediate-index--

The general implementation is:

```asm
ST4B {Zdata0.B - Zdata3.B}, Pg, [Xbase, Xindex]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST4B--scalar-plus-scalar---Contiguous-store-four-byte-structures-from-four-vectors--scalar-index--

### Operation

Source operation ID: `SveOperation_svst4_vnum_bf16`

**Operation**



For each active element *i* and for each vector index *j*, store `data[j][i]` to `base[n * vnum + i * 4 + j]`, where *n* is the number of elements in `data[j]`. Do not access memory for inactive elements.

## svst4q[_bf16]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst4q%5B_bf16%5D

### Signature (source notation)

```c
void svst4q[_bf16](svbool_t pg, bfloat16_t const * rn, svbfloat16x4_t zt);
```

### Description

Contiguous store four-quadword structures from four vectors (immediate index)

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
    "Z multi-vector": "{ Zreg1.Q - Zreg2.Q }"
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
ST4Q { Zreg1.Q - Zreg2.Q }, Preg1, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/ST4Q--scalar-plus-immediate---Contiguous-store-four-quadword-structures-from-four-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svst4q[_f16]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst4q%5B_f16%5D

### Signature (source notation)

```c
void svst4q[_f16](svbool_t pg, float16_t const * rn, svfloat16x4_t zt);
```

### Description

Contiguous store four-quadword structures from four vectors (immediate index)

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
    "Z multi-vector": "{ Zreg1.Q - Zreg2.Q }"
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
ST4Q { Zreg1.Q - Zreg2.Q }, Preg1, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/ST4Q--scalar-plus-immediate---Contiguous-store-four-quadword-structures-from-four-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svst4q[_f32]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst4q%5B_f32%5D

### Signature (source notation)

```c
void svst4q[_f32](svbool_t pg, float32_t const * rn, svfloat32x4_t zt);
```

### Description

Contiguous store four-quadword structures from four vectors (immediate index)

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
  "element_bit_size": "32",
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
    "Z multi-vector": "{ Zreg1.Q - Zreg2.Q }"
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
ST4Q { Zreg1.Q - Zreg2.Q }, Preg1, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/ST4Q--scalar-plus-immediate---Contiguous-store-four-quadword-structures-from-four-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svst4q[_f64]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst4q%5B_f64%5D

### Signature (source notation)

```c
void svst4q[_f64](svbool_t pg, float64_t const * rn, svfloat64x4_t zt);
```

### Description

Contiguous store four-quadword structures from four vectors (immediate index)

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
  "element_bit_size": "64",
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
    "Z multi-vector": "{ Zreg1.Q - Zreg2.Q }"
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
ST4Q { Zreg1.Q - Zreg2.Q }, Preg1, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/ST4Q--scalar-plus-immediate---Contiguous-store-four-quadword-structures-from-four-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svst4q[_mf8]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst4q%5B_mf8%5D

### Signature (source notation)

```c
void svst4q[_mf8](svbool_t pg, mfloat8_t const * rn, svmfloat8x4_t zt);
```

### Description

Contiguous store four-quadword structures from four vectors (immediate index)

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
  "element_bit_size": "8",
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
    "Z multi-vector": "{ Zreg1.Q - Zreg2.Q }"
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
ST4Q { Zreg1.Q - Zreg2.Q }, Preg1, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/ST4Q--scalar-plus-immediate---Contiguous-store-four-quadword-structures-from-four-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svst4q[_s16]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst4q%5B_s16%5D

### Signature (source notation)

```c
void svst4q[_s16](svbool_t pg, int16_t const * rn, svint16x4_t zt);
```

### Description

Contiguous store four-quadword structures from four vectors (immediate index)

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
    "Z multi-vector": "{ Zreg1.Q - Zreg2.Q }"
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
ST4Q { Zreg1.Q - Zreg2.Q }, Preg1, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/ST4Q--scalar-plus-immediate---Contiguous-store-four-quadword-structures-from-four-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svst4q[_s32]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst4q%5B_s32%5D

### Signature (source notation)

```c
void svst4q[_s32](svbool_t pg, int32_t const * rn, svint32x4_t zt);
```

### Description

Contiguous store four-quadword structures from four vectors (immediate index)

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
  "element_bit_size": "32",
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
    "Z multi-vector": "{ Zreg1.Q - Zreg2.Q }"
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
ST4Q { Zreg1.Q - Zreg2.Q }, Preg1, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/ST4Q--scalar-plus-immediate---Contiguous-store-four-quadword-structures-from-four-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svst4q[_s64]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst4q%5B_s64%5D

### Signature (source notation)

```c
void svst4q[_s64](svbool_t pg, int64_t const * rn, svint64x4_t zt);
```

### Description

Contiguous store four-quadword structures from four vectors (immediate index)

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
  "element_bit_size": "64",
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
    "Z multi-vector": "{ Zreg1.Q - Zreg2.Q }"
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
ST4Q { Zreg1.Q - Zreg2.Q }, Preg1, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/ST4Q--scalar-plus-immediate---Contiguous-store-four-quadword-structures-from-four-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svst4q[_s8]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst4q%5B_s8%5D

### Signature (source notation)

```c
void svst4q[_s8](svbool_t pg, int8_t const * rn, svint8x4_t zt);
```

### Description

Contiguous store four-quadword structures from four vectors (immediate index)

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
  "element_bit_size": "8",
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
    "Z multi-vector": "{ Zreg1.Q - Zreg2.Q }"
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
ST4Q { Zreg1.Q - Zreg2.Q }, Preg1, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/ST4Q--scalar-plus-immediate---Contiguous-store-four-quadword-structures-from-four-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svst4q[_u16]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst4q%5B_u16%5D

### Signature (source notation)

```c
void svst4q[_u16](svbool_t pg, uint16_t const * rn, svuint16x4_t zt);
```

### Description

Contiguous store four-quadword structures from four vectors (immediate index)

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
    "Z multi-vector": "{ Zreg1.Q - Zreg2.Q }"
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
ST4Q { Zreg1.Q - Zreg2.Q }, Preg1, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/ST4Q--scalar-plus-immediate---Contiguous-store-four-quadword-structures-from-four-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svst4q[_u32]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst4q%5B_u32%5D

### Signature (source notation)

```c
void svst4q[_u32](svbool_t pg, uint32_t const * rn, svuint32x4_t zt);
```

### Description

Contiguous store four-quadword structures from four vectors (immediate index)

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
  "element_bit_size": "32",
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
    "Z multi-vector": "{ Zreg1.Q - Zreg2.Q }"
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
ST4Q { Zreg1.Q - Zreg2.Q }, Preg1, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/ST4Q--scalar-plus-immediate---Contiguous-store-four-quadword-structures-from-four-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svst4q[_u64]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst4q%5B_u64%5D

### Signature (source notation)

```c
void svst4q[_u64](svbool_t pg, uint64_t const * rn, svuint64x4_t zt);
```

### Description

Contiguous store four-quadword structures from four vectors (immediate index)

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
  "element_bit_size": "64",
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
    "Z multi-vector": "{ Zreg1.Q - Zreg2.Q }"
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
ST4Q { Zreg1.Q - Zreg2.Q }, Preg1, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/ST4Q--scalar-plus-immediate---Contiguous-store-four-quadword-structures-from-four-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svst4q[_u8]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst4q%5B_u8%5D

### Signature (source notation)

```c
void svst4q[_u8](svbool_t pg, uint8_t const * rn, svuint8x4_t zt);
```

### Description

Contiguous store four-quadword structures from four vectors (immediate index)

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
  "element_bit_size": "8",
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
    "Z multi-vector": "{ Zreg1.Q - Zreg2.Q }"
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
ST4Q { Zreg1.Q - Zreg2.Q }, Preg1, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/ST4Q--scalar-plus-immediate---Contiguous-store-four-quadword-structures-from-four-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svst4q_vnum[_bf16]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst4q_vnum%5B_bf16%5D

### Signature (source notation)

```c
void svst4q_vnum[_bf16](svbool_t pg, bfloat16_t const * rn, int64_t vnum, svbfloat16x4_t zt);
```

### Description

Contiguous store four-quadword structures from four vectors (immediate index)

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
    "register": "Xreg3"
  },
  "vnum": {
    "register": "Xreg2"
  },
  "zt": {
    "Z multi-vector": "{ Zreg1.Q - Zreg2.Q }"
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
RDVL Xreg1, #1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/RDVL--Read-multiple-of-vector-register-size-to-scalar-register-

```asm
MADD Xreg1, Xreg1, Xreg2, Xreg3
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/Base-Instructions/MADD--Multiply-add-

```asm
ST4Q { Zreg1.Q - Zreg2.Q }, Preg1, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/ST4Q--scalar-plus-immediate---Contiguous-store-four-quadword-structures-from-four-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svst4q_vnum[_f16]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst4q_vnum%5B_f16%5D

### Signature (source notation)

```c
void svst4q_vnum[_f16](svbool_t pg, float16_t const * rn, int64_t vnum, svfloat16x4_t zt);
```

### Description

Contiguous store four-quadword structures from four vectors (immediate index)

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
    "register": "Xreg3"
  },
  "vnum": {
    "register": "Xreg2"
  },
  "zt": {
    "Z multi-vector": "{ Zreg1.Q - Zreg2.Q }"
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
RDVL Xreg1, #1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/RDVL--Read-multiple-of-vector-register-size-to-scalar-register-

```asm
MADD Xreg1, Xreg1, Xreg2, Xreg3
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/Base-Instructions/MADD--Multiply-add-

```asm
ST4Q { Zreg1.Q - Zreg2.Q }, Preg1, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/ST4Q--scalar-plus-immediate---Contiguous-store-four-quadword-structures-from-four-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svst4q_vnum[_f32]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst4q_vnum%5B_f32%5D

### Signature (source notation)

```c
void svst4q_vnum[_f32](svbool_t pg, float32_t const * rn, int64_t vnum, svfloat32x4_t zt);
```

### Description

Contiguous store four-quadword structures from four vectors (immediate index)

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
  "element_bit_size": "32",
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
    "register": "Xreg3"
  },
  "vnum": {
    "register": "Xreg2"
  },
  "zt": {
    "Z multi-vector": "{ Zreg1.Q - Zreg2.Q }"
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
RDVL Xreg1, #1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/RDVL--Read-multiple-of-vector-register-size-to-scalar-register-

```asm
MADD Xreg1, Xreg1, Xreg2, Xreg3
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/Base-Instructions/MADD--Multiply-add-

```asm
ST4Q { Zreg1.Q - Zreg2.Q }, Preg1, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/ST4Q--scalar-plus-immediate---Contiguous-store-four-quadword-structures-from-four-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svst4q_vnum[_f64]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst4q_vnum%5B_f64%5D

### Signature (source notation)

```c
void svst4q_vnum[_f64](svbool_t pg, float64_t const * rn, int64_t vnum, svfloat64x4_t zt);
```

### Description

Contiguous store four-quadword structures from four vectors (immediate index)

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
  "element_bit_size": "64",
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
    "register": "Xreg3"
  },
  "vnum": {
    "register": "Xreg2"
  },
  "zt": {
    "Z multi-vector": "{ Zreg1.Q - Zreg2.Q }"
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
RDVL Xreg1, #1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/RDVL--Read-multiple-of-vector-register-size-to-scalar-register-

```asm
MADD Xreg1, Xreg1, Xreg2, Xreg3
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/Base-Instructions/MADD--Multiply-add-

```asm
ST4Q { Zreg1.Q - Zreg2.Q }, Preg1, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/ST4Q--scalar-plus-immediate---Contiguous-store-four-quadword-structures-from-four-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svst4q_vnum[_mf8]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst4q_vnum%5B_mf8%5D

### Signature (source notation)

```c
void svst4q_vnum[_mf8](svbool_t pg, mfloat8_t const * rn, int64_t vnum, svmfloat8x4_t zt);
```

### Description

Contiguous store four-quadword structures from four vectors (immediate index)

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
  "element_bit_size": "8",
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
    "register": "Xreg3"
  },
  "vnum": {
    "register": "Xreg2"
  },
  "zt": {
    "Z multi-vector": "{ Zreg1.Q - Zreg2.Q }"
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
RDVL Xreg1, #1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/RDVL--Read-multiple-of-vector-register-size-to-scalar-register-

```asm
MADD Xreg1, Xreg1, Xreg2, Xreg3
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/Base-Instructions/MADD--Multiply-add-

```asm
ST4Q { Zreg1.Q - Zreg2.Q }, Preg1, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/ST4Q--scalar-plus-immediate---Contiguous-store-four-quadword-structures-from-four-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svst4q_vnum[_s16]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst4q_vnum%5B_s16%5D

### Signature (source notation)

```c
void svst4q_vnum[_s16](svbool_t pg, int16_t const * rn, int64_t vnum, svint16x4_t zt);
```

### Description

Contiguous store four-quadword structures from four vectors (immediate index)

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
    "register": "Xreg3"
  },
  "vnum": {
    "register": "Xreg2"
  },
  "zt": {
    "Z multi-vector": "{ Zreg1.Q - Zreg2.Q }"
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
RDVL Xreg1, #1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/RDVL--Read-multiple-of-vector-register-size-to-scalar-register-

```asm
MADD Xreg1, Xreg1, Xreg2, Xreg3
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/Base-Instructions/MADD--Multiply-add-

```asm
ST4Q { Zreg1.Q - Zreg2.Q }, Preg1, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/ST4Q--scalar-plus-immediate---Contiguous-store-four-quadword-structures-from-four-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svst4q_vnum[_s32]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst4q_vnum%5B_s32%5D

### Signature (source notation)

```c
void svst4q_vnum[_s32](svbool_t pg, int32_t const * rn, int64_t vnum, svint32x4_t zt);
```

### Description

Contiguous store four-quadword structures from four vectors (immediate index)

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
  "element_bit_size": "32",
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
    "register": "Xreg3"
  },
  "vnum": {
    "register": "Xreg2"
  },
  "zt": {
    "Z multi-vector": "{ Zreg1.Q - Zreg2.Q }"
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
RDVL Xreg1, #1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/RDVL--Read-multiple-of-vector-register-size-to-scalar-register-

```asm
MADD Xreg1, Xreg1, Xreg2, Xreg3
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/Base-Instructions/MADD--Multiply-add-

```asm
ST4Q { Zreg1.Q - Zreg2.Q }, Preg1, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/ST4Q--scalar-plus-immediate---Contiguous-store-four-quadword-structures-from-four-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svst4q_vnum[_s64]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst4q_vnum%5B_s64%5D

### Signature (source notation)

```c
void svst4q_vnum[_s64](svbool_t pg, int64_t const * rn, int64_t vnum, svint64x4_t zt);
```

### Description

Contiguous store four-quadword structures from four vectors (immediate index)

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
  "element_bit_size": "64",
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
    "register": "Xreg3"
  },
  "vnum": {
    "register": "Xreg2"
  },
  "zt": {
    "Z multi-vector": "{ Zreg1.Q - Zreg2.Q }"
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
RDVL Xreg1, #1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/RDVL--Read-multiple-of-vector-register-size-to-scalar-register-

```asm
MADD Xreg1, Xreg1, Xreg2, Xreg3
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/Base-Instructions/MADD--Multiply-add-

```asm
ST4Q { Zreg1.Q - Zreg2.Q }, Preg1, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/ST4Q--scalar-plus-immediate---Contiguous-store-four-quadword-structures-from-four-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svst4q_vnum[_s8]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst4q_vnum%5B_s8%5D

### Signature (source notation)

```c
void svst4q_vnum[_s8](svbool_t pg, int8_t const * rn, int64_t vnum, svint8x4_t zt);
```

### Description

Contiguous store four-quadword structures from four vectors (immediate index)

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
  "element_bit_size": "8",
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
    "register": "Xreg3"
  },
  "vnum": {
    "register": "Xreg2"
  },
  "zt": {
    "Z multi-vector": "{ Zreg1.Q - Zreg2.Q }"
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
RDVL Xreg1, #1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/RDVL--Read-multiple-of-vector-register-size-to-scalar-register-

```asm
MADD Xreg1, Xreg1, Xreg2, Xreg3
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/Base-Instructions/MADD--Multiply-add-

```asm
ST4Q { Zreg1.Q - Zreg2.Q }, Preg1, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/ST4Q--scalar-plus-immediate---Contiguous-store-four-quadword-structures-from-four-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svst4q_vnum[_u16]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst4q_vnum%5B_u16%5D

### Signature (source notation)

```c
void svst4q_vnum[_u16](svbool_t pg, uint16_t const * rn, int64_t vnum, svuint16x4_t zt);
```

### Description

Contiguous store four-quadword structures from four vectors (immediate index)

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
    "register": "Xreg3"
  },
  "vnum": {
    "register": "Xreg2"
  },
  "zt": {
    "Z multi-vector": "{ Zreg1.Q - Zreg2.Q }"
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
RDVL Xreg1, #1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/RDVL--Read-multiple-of-vector-register-size-to-scalar-register-

```asm
MADD Xreg1, Xreg1, Xreg2, Xreg3
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/Base-Instructions/MADD--Multiply-add-

```asm
ST4Q { Zreg1.Q - Zreg2.Q }, Preg1, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/ST4Q--scalar-plus-immediate---Contiguous-store-four-quadword-structures-from-four-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svst4q_vnum[_u32]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst4q_vnum%5B_u32%5D

### Signature (source notation)

```c
void svst4q_vnum[_u32](svbool_t pg, uint32_t const * rn, int64_t vnum, svuint32x4_t zt);
```

### Description

Contiguous store four-quadword structures from four vectors (immediate index)

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
  "element_bit_size": "32",
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
    "register": "Xreg3"
  },
  "vnum": {
    "register": "Xreg2"
  },
  "zt": {
    "Z multi-vector": "{ Zreg1.Q - Zreg2.Q }"
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
RDVL Xreg1, #1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/RDVL--Read-multiple-of-vector-register-size-to-scalar-register-

```asm
MADD Xreg1, Xreg1, Xreg2, Xreg3
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/Base-Instructions/MADD--Multiply-add-

```asm
ST4Q { Zreg1.Q - Zreg2.Q }, Preg1, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/ST4Q--scalar-plus-immediate---Contiguous-store-four-quadword-structures-from-four-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svst4q_vnum[_u64]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst4q_vnum%5B_u64%5D

### Signature (source notation)

```c
void svst4q_vnum[_u64](svbool_t pg, uint64_t const * rn, int64_t vnum, svuint64x4_t zt);
```

### Description

Contiguous store four-quadword structures from four vectors (immediate index)

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
  "element_bit_size": "64",
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
    "register": "Xreg3"
  },
  "vnum": {
    "register": "Xreg2"
  },
  "zt": {
    "Z multi-vector": "{ Zreg1.Q - Zreg2.Q }"
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
RDVL Xreg1, #1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/RDVL--Read-multiple-of-vector-register-size-to-scalar-register-

```asm
MADD Xreg1, Xreg1, Xreg2, Xreg3
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/Base-Instructions/MADD--Multiply-add-

```asm
ST4Q { Zreg1.Q - Zreg2.Q }, Preg1, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/ST4Q--scalar-plus-immediate---Contiguous-store-four-quadword-structures-from-four-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svst4q_vnum[_u8]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst4q_vnum%5B_u8%5D

### Signature (source notation)

```c
void svst4q_vnum[_u8](svbool_t pg, uint8_t const * rn, int64_t vnum, svuint8x4_t zt);
```

### Description

Contiguous store four-quadword structures from four vectors (immediate index)

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
  "element_bit_size": "8",
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
    "register": "Xreg3"
  },
  "vnum": {
    "register": "Xreg2"
  },
  "zt": {
    "Z multi-vector": "{ Zreg1.Q - Zreg2.Q }"
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
RDVL Xreg1, #1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/RDVL--Read-multiple-of-vector-register-size-to-scalar-register-

```asm
MADD Xreg1, Xreg1, Xreg2, Xreg3
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/Base-Instructions/MADD--Multiply-add-

```asm
ST4Q { Zreg1.Q - Zreg2.Q }, Preg1, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/ST4Q--scalar-plus-immediate---Contiguous-store-four-quadword-structures-from-four-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svstnt1[_bf16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svstnt1%5B_bf16%5D

### Signature (source notation)

```c
void svstnt1[_bf16](svbool_t pg, bfloat16_t *base, svbfloat16_t data);
```

### Description

Non-truncating store, non-temporal

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
STNT1H Zdata.H, Pg, [Xarray, Xindex, LSL #1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/STNT1H--scalar-plus-scalar--consecutive-registers---Contiguous-store-non-temporal-of-halfwords-from-multiple-consecutive-vectors--scalar-index--

The general implementation is:

```asm
STNT1H Zdata.H, Pg, [Xbase, #0, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/STNT1H--scalar-plus-immediate--consecutive-registers---Contiguous-store-non-temporal-of-halfwords-from-multiple-consecutive-vectors--immediate-index--

### Operation

Source operation ID: `SveOperation_svstnt1_bf16`

**Operation**



For each active element *i*, store `data[i]` to `base[i]`. Do not access memory for inactive elements.  Provide a hint to the system that the stored memory is unlikely to be accessed again soon.

## svstnt1[_bf16_x2]

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svstnt1%5B_bf16_x2%5D

### Signature (source notation)

```c
void svstnt1[_bf16_x2](svcount_t png, bfloat16_t * rn, svbfloat16x2_t zt);
```

### Description

Contiguous store non-temporal of halfwords from multiple consecutive vectors (immediate index)

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
STNT1H { Zreg1.H, Zreg2.H }, PNreg1, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/STNT1H--scalar-plus-immediate--consecutive-registers---Contiguous-store-non-temporal-of-halfwords-from-multiple-consecutive-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svstnt1[_bf16_x4]

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svstnt1%5B_bf16_x4%5D

### Signature (source notation)

```c
void svstnt1[_bf16_x4](svcount_t png, bfloat16_t * rn, svbfloat16x4_t zt);
```

### Description

Contiguous store non-temporal of halfwords from multiple consecutive vectors (immediate index)

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
STNT1H { Zreg1.H - Zreg2.H }, PNreg1, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/STNT1H--scalar-plus-immediate--consecutive-registers---Contiguous-store-non-temporal-of-halfwords-from-multiple-consecutive-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svstnt1[_f16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svstnt1%5B_f16%5D

### Signature (source notation)

```c
void svstnt1[_f16](svbool_t pg, float16_t *base, svfloat16_t data);
```

### Description

Non-truncating store, non-temporal

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
STNT1H Zdata.H, Pg, [Xarray, Xindex, LSL #1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/STNT1H--scalar-plus-scalar--consecutive-registers---Contiguous-store-non-temporal-of-halfwords-from-multiple-consecutive-vectors--scalar-index--

The general implementation is:

```asm
STNT1H Zdata.H, Pg, [Xbase, #0, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/STNT1H--scalar-plus-immediate--consecutive-registers---Contiguous-store-non-temporal-of-halfwords-from-multiple-consecutive-vectors--immediate-index--

### Operation

Source operation ID: `SveOperation_svstnt1_bf16`

**Operation**



For each active element *i*, store `data[i]` to `base[i]`. Do not access memory for inactive elements.  Provide a hint to the system that the stored memory is unlikely to be accessed again soon.

## svstnt1[_f16_x2]

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svstnt1%5B_f16_x2%5D

### Signature (source notation)

```c
void svstnt1[_f16_x2](svcount_t png, float16_t * rn, svfloat16x2_t zt);
```

### Description

Contiguous store non-temporal of halfwords from multiple consecutive vectors (immediate index)

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
STNT1H { Zreg1.H, Zreg2.H }, PNreg1, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/STNT1H--scalar-plus-immediate--consecutive-registers---Contiguous-store-non-temporal-of-halfwords-from-multiple-consecutive-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svstnt1[_f16_x4]

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svstnt1%5B_f16_x4%5D

### Signature (source notation)

```c
void svstnt1[_f16_x4](svcount_t png, float16_t * rn, svfloat16x4_t zt);
```

### Description

Contiguous store non-temporal of halfwords from multiple consecutive vectors (immediate index)

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
STNT1H { Zreg1.H - Zreg2.H }, PNreg1, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/STNT1H--scalar-plus-immediate--consecutive-registers---Contiguous-store-non-temporal-of-halfwords-from-multiple-consecutive-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svstnt1[_f32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svstnt1%5B_f32%5D

### Signature (source notation)

```c
void svstnt1[_f32](svbool_t pg, float32_t *base, svfloat32_t data);
```

### Description

Non-truncating store, non-temporal

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
STNT1W Zdata.S, Pg, [Xarray, Xindex, LSL #2]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/STNT1W--scalar-plus-scalar--consecutive-registers---Contiguous-store-non-temporal-of-words-from-multiple-consecutive-vectors--scalar-index--

The general implementation is:

```asm
STNT1W Zdata.S, Pg, [Xbase, #0, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/STNT1W--scalar-plus-immediate--consecutive-registers---Contiguous-store-non-temporal-of-words-from-multiple-consecutive-vectors--immediate-index--

### Operation

Source operation ID: `SveOperation_svstnt1_bf16`

**Operation**



For each active element *i*, store `data[i]` to `base[i]`. Do not access memory for inactive elements.  Provide a hint to the system that the stored memory is unlikely to be accessed again soon.

## svstnt1[_f32_x2]

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svstnt1%5B_f32_x2%5D

### Signature (source notation)

```c
void svstnt1[_f32_x2](svcount_t png, float32_t * rn, svfloat32x2_t zt);
```

### Description

Contiguous store non-temporal of words from multiple consecutive vectors (immediate index)

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
STNT1W { Zreg1.S, Zreg2.S }, PNreg1, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/STNT1W--scalar-plus-immediate--consecutive-registers---Contiguous-store-non-temporal-of-words-from-multiple-consecutive-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svstnt1[_f32_x4]

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svstnt1%5B_f32_x4%5D

### Signature (source notation)

```c
void svstnt1[_f32_x4](svcount_t png, float32_t * rn, svfloat32x4_t zt);
```

### Description

Contiguous store non-temporal of words from multiple consecutive vectors (immediate index)

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
STNT1W { Zreg1.S - Zreg2.S }, PNreg1, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/STNT1W--scalar-plus-immediate--consecutive-registers---Contiguous-store-non-temporal-of-words-from-multiple-consecutive-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svstnt1[_f64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svstnt1%5B_f64%5D

### Signature (source notation)

```c
void svstnt1[_f64](svbool_t pg, float64_t *base, svfloat64_t data);
```

### Description

Non-truncating store, non-temporal

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
STNT1D Zdata.D, Pg, [Xarray, Xindex, LSL #3]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/STNT1D--scalar-plus-scalar--consecutive-registers---Contiguous-store-non-temporal-of-doublewords-from-multiple-consecutive-vectors--scalar-index--

The general implementation is:

```asm
STNT1D Zdata.D, Pg, [Xbase, #0, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/STNT1D--scalar-plus-immediate--consecutive-registers---Contiguous-store-non-temporal-of-doublewords-from-multiple-consecutive-vectors--immediate-index--

### Operation

Source operation ID: `SveOperation_svstnt1_bf16`

**Operation**



For each active element *i*, store `data[i]` to `base[i]`. Do not access memory for inactive elements.  Provide a hint to the system that the stored memory is unlikely to be accessed again soon.

## svstnt1[_f64_x2]

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svstnt1%5B_f64_x2%5D

### Signature (source notation)

```c
void svstnt1[_f64_x2](svcount_t png, float64_t * rn, svfloat64x2_t zt);
```

### Description

Contiguous store non-temporal of doublewords from multiple consecutive vectors (immediate index)

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
STNT1D { Zreg1.D, Zreg2.D }, PNreg1, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/STNT1D--scalar-plus-immediate--consecutive-registers---Contiguous-store-non-temporal-of-doublewords-from-multiple-consecutive-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svstnt1[_f64_x4]

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svstnt1%5B_f64_x4%5D

### Signature (source notation)

```c
void svstnt1[_f64_x4](svcount_t png, float64_t * rn, svfloat64x4_t zt);
```

### Description

Contiguous store non-temporal of doublewords from multiple consecutive vectors (immediate index)

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
STNT1D { Zreg1.D - Zreg2.D }, PNreg1, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/STNT1D--scalar-plus-immediate--consecutive-registers---Contiguous-store-non-temporal-of-doublewords-from-multiple-consecutive-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svstnt1[_mf8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svstnt1%5B_mf8%5D

### Signature (source notation)

```c
void svstnt1[_mf8](svbool_t pg, mfloat8_t *base, svmfloat8_t data);
```

### Description

Non-truncating store, non-temporal

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
STNT1B Zdata.B, Pg, [Xarray, Xindex]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/STNT1B--scalar-plus-scalar--consecutive-registers---Contiguous-store-non-temporal-of-bytes-from-multiple-consecutive-vectors--scalar-index--

The general implementation is:

```asm
STNT1B Zdata.B, Pg, [Xbase, #0, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/STNT1B--scalar-plus-immediate--consecutive-registers---Contiguous-store-non-temporal-of-bytes-from-multiple-consecutive-vectors--immediate-index--

### Operation

Source operation ID: `SveOperation_svstnt1_bf16`

**Operation**



For each active element *i*, store `data[i]` to `base[i]`. Do not access memory for inactive elements.  Provide a hint to the system that the stored memory is unlikely to be accessed again soon.

## svstnt1[_mf8_x2]

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svstnt1%5B_mf8_x2%5D

### Signature (source notation)

```c
void svstnt1[_mf8_x2](svcount_t png, mfloat8_t * rn, svmfloat8x2_t zt);
```

### Description

Contiguous store non-temporal of bytes from multiple consecutive vectors (immediate index)

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
STNT1B { Zreg1.B, Zreg2.B }, PNreg1, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/STNT1B--scalar-plus-immediate--consecutive-registers---Contiguous-store-non-temporal-of-bytes-from-multiple-consecutive-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svstnt1[_mf8_x4]

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svstnt1%5B_mf8_x4%5D

### Signature (source notation)

```c
void svstnt1[_mf8_x4](svcount_t png, mfloat8_t * rn, svmfloat8x4_t zt);
```

### Description

Contiguous store non-temporal of bytes from multiple consecutive vectors (immediate index)

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
STNT1B { Zreg1.B - Zreg2.B }, PNreg1, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/STNT1B--scalar-plus-immediate--consecutive-registers---Contiguous-store-non-temporal-of-bytes-from-multiple-consecutive-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svstnt1[_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svstnt1%5B_s16%5D

### Signature (source notation)

```c
void svstnt1[_s16](svbool_t pg, int16_t *base, svint16_t data);
```

### Description

Non-truncating store, non-temporal

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
STNT1H Zdata.H, Pg, [Xarray, Xindex, LSL #1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/STNT1H--scalar-plus-scalar--consecutive-registers---Contiguous-store-non-temporal-of-halfwords-from-multiple-consecutive-vectors--scalar-index--

The general implementation is:

```asm
STNT1H Zdata.H, Pg, [Xbase, #0, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/STNT1H--scalar-plus-immediate--consecutive-registers---Contiguous-store-non-temporal-of-halfwords-from-multiple-consecutive-vectors--immediate-index--

### Operation

Source operation ID: `SveOperation_svstnt1_bf16`

**Operation**



For each active element *i*, store `data[i]` to `base[i]`. Do not access memory for inactive elements.  Provide a hint to the system that the stored memory is unlikely to be accessed again soon.

## svstnt1[_s16_x2]

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svstnt1%5B_s16_x2%5D

### Signature (source notation)

```c
void svstnt1[_s16_x2](svcount_t png, int16_t * rn, svint16x2_t zt);
```

### Description

Contiguous store non-temporal of halfwords from multiple consecutive vectors (immediate index)

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
STNT1H { Zreg1.H, Zreg2.H }, PNreg1, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/STNT1H--scalar-plus-immediate--consecutive-registers---Contiguous-store-non-temporal-of-halfwords-from-multiple-consecutive-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svstnt1[_s16_x4]

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svstnt1%5B_s16_x4%5D

### Signature (source notation)

```c
void svstnt1[_s16_x4](svcount_t png, int16_t * rn, svint16x4_t zt);
```

### Description

Contiguous store non-temporal of halfwords from multiple consecutive vectors (immediate index)

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
STNT1H { Zreg1.H - Zreg2.H }, PNreg1, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/STNT1H--scalar-plus-immediate--consecutive-registers---Contiguous-store-non-temporal-of-halfwords-from-multiple-consecutive-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svstnt1[_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svstnt1%5B_s32%5D

### Signature (source notation)

```c
void svstnt1[_s32](svbool_t pg, int32_t *base, svint32_t data);
```

### Description

Non-truncating store, non-temporal

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
STNT1W Zdata.S, Pg, [Xarray, Xindex, LSL #2]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/STNT1W--scalar-plus-scalar--consecutive-registers---Contiguous-store-non-temporal-of-words-from-multiple-consecutive-vectors--scalar-index--

The general implementation is:

```asm
STNT1W Zdata.S, Pg, [Xbase, #0, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/STNT1W--scalar-plus-immediate--consecutive-registers---Contiguous-store-non-temporal-of-words-from-multiple-consecutive-vectors--immediate-index--

### Operation

Source operation ID: `SveOperation_svstnt1_bf16`

**Operation**



For each active element *i*, store `data[i]` to `base[i]`. Do not access memory for inactive elements.  Provide a hint to the system that the stored memory is unlikely to be accessed again soon.

## svstnt1[_s32_x2]

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svstnt1%5B_s32_x2%5D

### Signature (source notation)

```c
void svstnt1[_s32_x2](svcount_t png, int32_t * rn, svint32x2_t zt);
```

### Description

Contiguous store non-temporal of words from multiple consecutive vectors (immediate index)

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
STNT1W { Zreg1.S, Zreg2.S }, PNreg1, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/STNT1W--scalar-plus-immediate--consecutive-registers---Contiguous-store-non-temporal-of-words-from-multiple-consecutive-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svstnt1[_s32_x4]

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svstnt1%5B_s32_x4%5D

### Signature (source notation)

```c
void svstnt1[_s32_x4](svcount_t png, int32_t * rn, svint32x4_t zt);
```

### Description

Contiguous store non-temporal of words from multiple consecutive vectors (immediate index)

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
STNT1W { Zreg1.S - Zreg2.S }, PNreg1, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/STNT1W--scalar-plus-immediate--consecutive-registers---Contiguous-store-non-temporal-of-words-from-multiple-consecutive-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svstnt1[_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svstnt1%5B_s64%5D

### Signature (source notation)

```c
void svstnt1[_s64](svbool_t pg, int64_t *base, svint64_t data);
```

### Description

Non-truncating store, non-temporal

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
STNT1D Zdata.D, Pg, [Xarray, Xindex, LSL #3]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/STNT1D--scalar-plus-scalar--consecutive-registers---Contiguous-store-non-temporal-of-doublewords-from-multiple-consecutive-vectors--scalar-index--

The general implementation is:

```asm
STNT1D Zdata.D, Pg, [Xbase, #0, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/STNT1D--scalar-plus-immediate--consecutive-registers---Contiguous-store-non-temporal-of-doublewords-from-multiple-consecutive-vectors--immediate-index--

### Operation

Source operation ID: `SveOperation_svstnt1_bf16`

**Operation**



For each active element *i*, store `data[i]` to `base[i]`. Do not access memory for inactive elements.  Provide a hint to the system that the stored memory is unlikely to be accessed again soon.

