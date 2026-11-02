# SME2 / Store / Consecutive — Part 2

## svst1_vnum[_u8_x2]

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst1_vnum%5B_u8_x2%5D

### Signature (source notation)

```c
void svst1_vnum[_u8_x2](svcount_t png, uint8_t * rn, int64_t vnum, svuint8x2_t zt);
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
    "register": "Xreg2"
  },
  "vnum": {
    "register": "Xreg3"
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
RDVL Xreg1, #1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/RDVL--Read-multiple-of-vector-register-size-to-scalar-register-

```asm
MADD Xreg1, Xreg1, Xreg3, Xreg2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/Base-Instructions/MADD--Multiply-add-

```asm
ST1B { Zreg1.B, Zreg2.B }, PNreg1, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST1B--scalar-plus-immediate--consecutive-registers---Contiguous-store-of-bytes-from-multiple-consecutive-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svst1_vnum[_u8_x4]

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst1_vnum%5B_u8_x4%5D

### Signature (source notation)

```c
void svst1_vnum[_u8_x4](svcount_t png, uint8_t * rn, int64_t vnum, svuint8x4_t zt);
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
    "register": "Xreg2"
  },
  "vnum": {
    "register": "Xreg3"
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
RDVL Xreg1, #1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/RDVL--Read-multiple-of-vector-register-size-to-scalar-register-

```asm
MADD Xreg1, Xreg1, Xreg3, Xreg2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/Base-Instructions/MADD--Multiply-add-

```asm
ST1B { Zreg1.B - Zreg2.B }, PNreg1, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST1B--scalar-plus-immediate--consecutive-registers---Contiguous-store-of-bytes-from-multiple-consecutive-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

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

## svst2q[_f32]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst2q%5B_f32%5D

### Signature (source notation)

```c
void svst2q[_f32](svbool_t pg, float32_t const * rn, svfloat32x2_t zt);
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

## svst2q[_f64]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst2q%5B_f64%5D

### Signature (source notation)

```c
void svst2q[_f64](svbool_t pg, float64_t const * rn, svfloat64x2_t zt);
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

## svst2q[_mf8]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst2q%5B_mf8%5D

### Signature (source notation)

```c
void svst2q[_mf8](svbool_t pg, mfloat8_t const * rn, svmfloat8x2_t zt);
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

## svst2q[_s16]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst2q%5B_s16%5D

### Signature (source notation)

```c
void svst2q[_s16](svbool_t pg, int16_t const * rn, svint16x2_t zt);
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

## svst2q[_s32]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst2q%5B_s32%5D

### Signature (source notation)

```c
void svst2q[_s32](svbool_t pg, int32_t const * rn, svint32x2_t zt);
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

## svst2q[_s64]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst2q%5B_s64%5D

### Signature (source notation)

```c
void svst2q[_s64](svbool_t pg, int64_t const * rn, svint64x2_t zt);
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

## svst2q[_s8]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst2q%5B_s8%5D

### Signature (source notation)

```c
void svst2q[_s8](svbool_t pg, int8_t const * rn, svint8x2_t zt);
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

## svst2q[_u16]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst2q%5B_u16%5D

### Signature (source notation)

```c
void svst2q[_u16](svbool_t pg, uint16_t const * rn, svuint16x2_t zt);
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

## svst2q[_u32]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst2q%5B_u32%5D

### Signature (source notation)

```c
void svst2q[_u32](svbool_t pg, uint32_t const * rn, svuint32x2_t zt);
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

## svst2q[_u64]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst2q%5B_u64%5D

### Signature (source notation)

```c
void svst2q[_u64](svbool_t pg, uint64_t const * rn, svuint64x2_t zt);
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

## svst2q[_u8]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst2q%5B_u8%5D

### Signature (source notation)

```c
void svst2q[_u8](svbool_t pg, uint8_t const * rn, svuint8x2_t zt);
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

## svst2q_vnum[_bf16]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst2q_vnum%5B_bf16%5D

### Signature (source notation)

```c
void svst2q_vnum[_bf16](svbool_t pg, bfloat16_t const * rn, int64_t vnum, svbfloat16x2_t zt);
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
    "register": "Xreg3"
  },
  "vnum": {
    "register": "Xreg2"
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
RDVL Xreg1, #1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/RDVL--Read-multiple-of-vector-register-size-to-scalar-register-

```asm
MADD Xreg1, Xreg1, Xreg2, Xreg3
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/Base-Instructions/MADD--Multiply-add-

```asm
ST2Q { Zreg1.Q, Zreg2.Q }, Preg1, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/ST2Q--scalar-plus-immediate---Contiguous-store-two-quadword-structures-from-two-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svst2q_vnum[_f16]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst2q_vnum%5B_f16%5D

### Signature (source notation)

```c
void svst2q_vnum[_f16](svbool_t pg, float16_t const * rn, int64_t vnum, svfloat16x2_t zt);
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
    "register": "Xreg3"
  },
  "vnum": {
    "register": "Xreg2"
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
RDVL Xreg1, #1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/RDVL--Read-multiple-of-vector-register-size-to-scalar-register-

```asm
MADD Xreg1, Xreg1, Xreg2, Xreg3
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/Base-Instructions/MADD--Multiply-add-

```asm
ST2Q { Zreg1.Q, Zreg2.Q }, Preg1, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/ST2Q--scalar-plus-immediate---Contiguous-store-two-quadword-structures-from-two-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svst2q_vnum[_f32]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst2q_vnum%5B_f32%5D

### Signature (source notation)

```c
void svst2q_vnum[_f32](svbool_t pg, float32_t const * rn, int64_t vnum, svfloat32x2_t zt);
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
RDVL Xreg1, #1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/RDVL--Read-multiple-of-vector-register-size-to-scalar-register-

```asm
MADD Xreg1, Xreg1, Xreg2, Xreg3
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/Base-Instructions/MADD--Multiply-add-

```asm
ST2Q { Zreg1.Q, Zreg2.Q }, Preg1, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/ST2Q--scalar-plus-immediate---Contiguous-store-two-quadword-structures-from-two-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svst2q_vnum[_f64]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst2q_vnum%5B_f64%5D

### Signature (source notation)

```c
void svst2q_vnum[_f64](svbool_t pg, float64_t const * rn, int64_t vnum, svfloat64x2_t zt);
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
RDVL Xreg1, #1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/RDVL--Read-multiple-of-vector-register-size-to-scalar-register-

```asm
MADD Xreg1, Xreg1, Xreg2, Xreg3
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/Base-Instructions/MADD--Multiply-add-

```asm
ST2Q { Zreg1.Q, Zreg2.Q }, Preg1, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/ST2Q--scalar-plus-immediate---Contiguous-store-two-quadword-structures-from-two-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svst2q_vnum[_mf8]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst2q_vnum%5B_mf8%5D

### Signature (source notation)

```c
void svst2q_vnum[_mf8](svbool_t pg, mfloat8_t const * rn, int64_t vnum, svmfloat8x2_t zt);
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
RDVL Xreg1, #1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/RDVL--Read-multiple-of-vector-register-size-to-scalar-register-

```asm
MADD Xreg1, Xreg1, Xreg2, Xreg3
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/Base-Instructions/MADD--Multiply-add-

```asm
ST2Q { Zreg1.Q, Zreg2.Q }, Preg1, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/ST2Q--scalar-plus-immediate---Contiguous-store-two-quadword-structures-from-two-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svst2q_vnum[_s16]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst2q_vnum%5B_s16%5D

### Signature (source notation)

```c
void svst2q_vnum[_s16](svbool_t pg, int16_t const * rn, int64_t vnum, svint16x2_t zt);
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
    "register": "Xreg3"
  },
  "vnum": {
    "register": "Xreg2"
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
RDVL Xreg1, #1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/RDVL--Read-multiple-of-vector-register-size-to-scalar-register-

```asm
MADD Xreg1, Xreg1, Xreg2, Xreg3
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/Base-Instructions/MADD--Multiply-add-

```asm
ST2Q { Zreg1.Q, Zreg2.Q }, Preg1, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/ST2Q--scalar-plus-immediate---Contiguous-store-two-quadword-structures-from-two-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svst2q_vnum[_s32]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst2q_vnum%5B_s32%5D

### Signature (source notation)

```c
void svst2q_vnum[_s32](svbool_t pg, int32_t const * rn, int64_t vnum, svint32x2_t zt);
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
RDVL Xreg1, #1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/RDVL--Read-multiple-of-vector-register-size-to-scalar-register-

```asm
MADD Xreg1, Xreg1, Xreg2, Xreg3
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/Base-Instructions/MADD--Multiply-add-

```asm
ST2Q { Zreg1.Q, Zreg2.Q }, Preg1, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/ST2Q--scalar-plus-immediate---Contiguous-store-two-quadword-structures-from-two-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svst2q_vnum[_s64]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst2q_vnum%5B_s64%5D

### Signature (source notation)

```c
void svst2q_vnum[_s64](svbool_t pg, int64_t const * rn, int64_t vnum, svint64x2_t zt);
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
RDVL Xreg1, #1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/RDVL--Read-multiple-of-vector-register-size-to-scalar-register-

```asm
MADD Xreg1, Xreg1, Xreg2, Xreg3
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/Base-Instructions/MADD--Multiply-add-

```asm
ST2Q { Zreg1.Q, Zreg2.Q }, Preg1, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/ST2Q--scalar-plus-immediate---Contiguous-store-two-quadword-structures-from-two-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svst2q_vnum[_s8]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst2q_vnum%5B_s8%5D

### Signature (source notation)

```c
void svst2q_vnum[_s8](svbool_t pg, int8_t const * rn, int64_t vnum, svint8x2_t zt);
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
RDVL Xreg1, #1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/RDVL--Read-multiple-of-vector-register-size-to-scalar-register-

```asm
MADD Xreg1, Xreg1, Xreg2, Xreg3
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/Base-Instructions/MADD--Multiply-add-

```asm
ST2Q { Zreg1.Q, Zreg2.Q }, Preg1, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/ST2Q--scalar-plus-immediate---Contiguous-store-two-quadword-structures-from-two-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svst2q_vnum[_u16]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst2q_vnum%5B_u16%5D

### Signature (source notation)

```c
void svst2q_vnum[_u16](svbool_t pg, uint16_t const * rn, int64_t vnum, svuint16x2_t zt);
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
    "register": "Xreg3"
  },
  "vnum": {
    "register": "Xreg2"
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
RDVL Xreg1, #1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/RDVL--Read-multiple-of-vector-register-size-to-scalar-register-

```asm
MADD Xreg1, Xreg1, Xreg2, Xreg3
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/Base-Instructions/MADD--Multiply-add-

```asm
ST2Q { Zreg1.Q, Zreg2.Q }, Preg1, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/ST2Q--scalar-plus-immediate---Contiguous-store-two-quadword-structures-from-two-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svst2q_vnum[_u32]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst2q_vnum%5B_u32%5D

### Signature (source notation)

```c
void svst2q_vnum[_u32](svbool_t pg, uint32_t const * rn, int64_t vnum, svuint32x2_t zt);
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
RDVL Xreg1, #1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/RDVL--Read-multiple-of-vector-register-size-to-scalar-register-

```asm
MADD Xreg1, Xreg1, Xreg2, Xreg3
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/Base-Instructions/MADD--Multiply-add-

```asm
ST2Q { Zreg1.Q, Zreg2.Q }, Preg1, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/ST2Q--scalar-plus-immediate---Contiguous-store-two-quadword-structures-from-two-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svst2q_vnum[_u64]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst2q_vnum%5B_u64%5D

### Signature (source notation)

```c
void svst2q_vnum[_u64](svbool_t pg, uint64_t const * rn, int64_t vnum, svuint64x2_t zt);
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
RDVL Xreg1, #1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/RDVL--Read-multiple-of-vector-register-size-to-scalar-register-

```asm
MADD Xreg1, Xreg1, Xreg2, Xreg3
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/Base-Instructions/MADD--Multiply-add-

```asm
ST2Q { Zreg1.Q, Zreg2.Q }, Preg1, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/ST2Q--scalar-plus-immediate---Contiguous-store-two-quadword-structures-from-two-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svst2q_vnum[_u8]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst2q_vnum%5B_u8%5D

### Signature (source notation)

```c
void svst2q_vnum[_u8](svbool_t pg, uint8_t const * rn, int64_t vnum, svuint8x2_t zt);
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
RDVL Xreg1, #1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/RDVL--Read-multiple-of-vector-register-size-to-scalar-register-

```asm
MADD Xreg1, Xreg1, Xreg2, Xreg3
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/Base-Instructions/MADD--Multiply-add-

```asm
ST2Q { Zreg1.Q, Zreg2.Q }, Preg1, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/ST2Q--scalar-plus-immediate---Contiguous-store-two-quadword-structures-from-two-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svst3q[_bf16]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst3q%5B_bf16%5D

### Signature (source notation)

```c
void svst3q[_bf16](svbool_t pg, bfloat16_t const * rn, svbfloat16x3_t zt);
```

### Description

Contiguous store three-quadword structures from three vectors (immediate index)

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
ST3Q { Zreg1.Q - Zreg2.Q }, Preg1, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/ST3Q--scalar-plus-immediate---Contiguous-store-three-quadword-structures-from-three-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svst3q[_f16]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst3q%5B_f16%5D

### Signature (source notation)

```c
void svst3q[_f16](svbool_t pg, float16_t const * rn, svfloat16x3_t zt);
```

### Description

Contiguous store three-quadword structures from three vectors (immediate index)

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
ST3Q { Zreg1.Q - Zreg2.Q }, Preg1, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/ST3Q--scalar-plus-immediate---Contiguous-store-three-quadword-structures-from-three-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svst3q[_f32]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst3q%5B_f32%5D

### Signature (source notation)

```c
void svst3q[_f32](svbool_t pg, float32_t const * rn, svfloat32x3_t zt);
```

### Description

Contiguous store three-quadword structures from three vectors (immediate index)

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
ST3Q { Zreg1.Q - Zreg2.Q }, Preg1, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/ST3Q--scalar-plus-immediate---Contiguous-store-three-quadword-structures-from-three-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svst3q[_f64]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst3q%5B_f64%5D

### Signature (source notation)

```c
void svst3q[_f64](svbool_t pg, float64_t const * rn, svfloat64x3_t zt);
```

### Description

Contiguous store three-quadword structures from three vectors (immediate index)

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
ST3Q { Zreg1.Q - Zreg2.Q }, Preg1, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/ST3Q--scalar-plus-immediate---Contiguous-store-three-quadword-structures-from-three-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svst3q[_mf8]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst3q%5B_mf8%5D

### Signature (source notation)

```c
void svst3q[_mf8](svbool_t pg, mfloat8_t const * rn, svmfloat8x3_t zt);
```

### Description

Contiguous store three-quadword structures from three vectors (immediate index)

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
ST3Q { Zreg1.Q - Zreg2.Q }, Preg1, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/ST3Q--scalar-plus-immediate---Contiguous-store-three-quadword-structures-from-three-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svst3q[_s16]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst3q%5B_s16%5D

### Signature (source notation)

```c
void svst3q[_s16](svbool_t pg, int16_t const * rn, svint16x3_t zt);
```

### Description

Contiguous store three-quadword structures from three vectors (immediate index)

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
ST3Q { Zreg1.Q - Zreg2.Q }, Preg1, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/ST3Q--scalar-plus-immediate---Contiguous-store-three-quadword-structures-from-three-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svst3q[_s32]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst3q%5B_s32%5D

### Signature (source notation)

```c
void svst3q[_s32](svbool_t pg, int32_t const * rn, svint32x3_t zt);
```

### Description

Contiguous store three-quadword structures from three vectors (immediate index)

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
ST3Q { Zreg1.Q - Zreg2.Q }, Preg1, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/ST3Q--scalar-plus-immediate---Contiguous-store-three-quadword-structures-from-three-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svst3q[_s64]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst3q%5B_s64%5D

### Signature (source notation)

```c
void svst3q[_s64](svbool_t pg, int64_t const * rn, svint64x3_t zt);
```

### Description

Contiguous store three-quadword structures from three vectors (immediate index)

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
ST3Q { Zreg1.Q - Zreg2.Q }, Preg1, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/ST3Q--scalar-plus-immediate---Contiguous-store-three-quadword-structures-from-three-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svst3q[_s8]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst3q%5B_s8%5D

### Signature (source notation)

```c
void svst3q[_s8](svbool_t pg, int8_t const * rn, svint8x3_t zt);
```

### Description

Contiguous store three-quadword structures from three vectors (immediate index)

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
ST3Q { Zreg1.Q - Zreg2.Q }, Preg1, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/ST3Q--scalar-plus-immediate---Contiguous-store-three-quadword-structures-from-three-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svst3q[_u16]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst3q%5B_u16%5D

### Signature (source notation)

```c
void svst3q[_u16](svbool_t pg, uint16_t const * rn, svuint16x3_t zt);
```

### Description

Contiguous store three-quadword structures from three vectors (immediate index)

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
ST3Q { Zreg1.Q - Zreg2.Q }, Preg1, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/ST3Q--scalar-plus-immediate---Contiguous-store-three-quadword-structures-from-three-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svst3q[_u32]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst3q%5B_u32%5D

### Signature (source notation)

```c
void svst3q[_u32](svbool_t pg, uint32_t const * rn, svuint32x3_t zt);
```

### Description

Contiguous store three-quadword structures from three vectors (immediate index)

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
ST3Q { Zreg1.Q - Zreg2.Q }, Preg1, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/ST3Q--scalar-plus-immediate---Contiguous-store-three-quadword-structures-from-three-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svst3q[_u64]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst3q%5B_u64%5D

### Signature (source notation)

```c
void svst3q[_u64](svbool_t pg, uint64_t const * rn, svuint64x3_t zt);
```

### Description

Contiguous store three-quadword structures from three vectors (immediate index)

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
ST3Q { Zreg1.Q - Zreg2.Q }, Preg1, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/ST3Q--scalar-plus-immediate---Contiguous-store-three-quadword-structures-from-three-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svst3q[_u8]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst3q%5B_u8%5D

### Signature (source notation)

```c
void svst3q[_u8](svbool_t pg, uint8_t const * rn, svuint8x3_t zt);
```

### Description

Contiguous store three-quadword structures from three vectors (immediate index)

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
ST3Q { Zreg1.Q - Zreg2.Q }, Preg1, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/ST3Q--scalar-plus-immediate---Contiguous-store-three-quadword-structures-from-three-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svst3q_vnum[_bf16]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst3q_vnum%5B_bf16%5D

### Signature (source notation)

```c
void svst3q_vnum[_bf16](svbool_t pg, bfloat16_t const * rn, int64_t vnum, svbfloat16x3_t zt);
```

### Description

Contiguous store three-quadword structures from three vectors (immediate index)

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
ST3Q { Zreg1.Q - Zreg2.Q }, Preg1, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/ST3Q--scalar-plus-immediate---Contiguous-store-three-quadword-structures-from-three-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svst3q_vnum[_f16]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst3q_vnum%5B_f16%5D

### Signature (source notation)

```c
void svst3q_vnum[_f16](svbool_t pg, float16_t const * rn, int64_t vnum, svfloat16x3_t zt);
```

### Description

Contiguous store three-quadword structures from three vectors (immediate index)

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
ST3Q { Zreg1.Q - Zreg2.Q }, Preg1, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/ST3Q--scalar-plus-immediate---Contiguous-store-three-quadword-structures-from-three-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svst3q_vnum[_f32]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst3q_vnum%5B_f32%5D

### Signature (source notation)

```c
void svst3q_vnum[_f32](svbool_t pg, float32_t const * rn, int64_t vnum, svfloat32x3_t zt);
```

### Description

Contiguous store three-quadword structures from three vectors (immediate index)

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
ST3Q { Zreg1.Q - Zreg2.Q }, Preg1, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/ST3Q--scalar-plus-immediate---Contiguous-store-three-quadword-structures-from-three-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svst3q_vnum[_f64]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst3q_vnum%5B_f64%5D

### Signature (source notation)

```c
void svst3q_vnum[_f64](svbool_t pg, float64_t const * rn, int64_t vnum, svfloat64x3_t zt);
```

### Description

Contiguous store three-quadword structures from three vectors (immediate index)

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
ST3Q { Zreg1.Q - Zreg2.Q }, Preg1, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/ST3Q--scalar-plus-immediate---Contiguous-store-three-quadword-structures-from-three-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svst3q_vnum[_mf8]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst3q_vnum%5B_mf8%5D

### Signature (source notation)

```c
void svst3q_vnum[_mf8](svbool_t pg, mfloat8_t const * rn, int64_t vnum, svmfloat8x3_t zt);
```

### Description

Contiguous store three-quadword structures from three vectors (immediate index)

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
ST3Q { Zreg1.Q - Zreg2.Q }, Preg1, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/ST3Q--scalar-plus-immediate---Contiguous-store-three-quadword-structures-from-three-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svst3q_vnum[_s16]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst3q_vnum%5B_s16%5D

### Signature (source notation)

```c
void svst3q_vnum[_s16](svbool_t pg, int16_t const * rn, int64_t vnum, svint16x3_t zt);
```

### Description

Contiguous store three-quadword structures from three vectors (immediate index)

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
ST3Q { Zreg1.Q - Zreg2.Q }, Preg1, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/ST3Q--scalar-plus-immediate---Contiguous-store-three-quadword-structures-from-three-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svst3q_vnum[_s32]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst3q_vnum%5B_s32%5D

### Signature (source notation)

```c
void svst3q_vnum[_s32](svbool_t pg, int32_t const * rn, int64_t vnum, svint32x3_t zt);
```

### Description

Contiguous store three-quadword structures from three vectors (immediate index)

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
ST3Q { Zreg1.Q - Zreg2.Q }, Preg1, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/ST3Q--scalar-plus-immediate---Contiguous-store-three-quadword-structures-from-three-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svst3q_vnum[_s64]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst3q_vnum%5B_s64%5D

### Signature (source notation)

```c
void svst3q_vnum[_s64](svbool_t pg, int64_t const * rn, int64_t vnum, svint64x3_t zt);
```

### Description

Contiguous store three-quadword structures from three vectors (immediate index)

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
ST3Q { Zreg1.Q - Zreg2.Q }, Preg1, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/ST3Q--scalar-plus-immediate---Contiguous-store-three-quadword-structures-from-three-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svst3q_vnum[_s8]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst3q_vnum%5B_s8%5D

### Signature (source notation)

```c
void svst3q_vnum[_s8](svbool_t pg, int8_t const * rn, int64_t vnum, svint8x3_t zt);
```

### Description

Contiguous store three-quadword structures from three vectors (immediate index)

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
ST3Q { Zreg1.Q - Zreg2.Q }, Preg1, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/ST3Q--scalar-plus-immediate---Contiguous-store-three-quadword-structures-from-three-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

