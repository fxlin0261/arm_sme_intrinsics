# SME / Store / Consecutive — Part 5

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

## svst3q_vnum[_u16]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst3q_vnum%5B_u16%5D

### Signature (source notation)

```c
void svst3q_vnum[_u16](svbool_t pg, uint16_t const * rn, int64_t vnum, svuint16x3_t zt);
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

## svst3q_vnum[_u32]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst3q_vnum%5B_u32%5D

### Signature (source notation)

```c
void svst3q_vnum[_u32](svbool_t pg, uint32_t const * rn, int64_t vnum, svuint32x3_t zt);
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

## svst3q_vnum[_u64]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst3q_vnum%5B_u64%5D

### Signature (source notation)

```c
void svst3q_vnum[_u64](svbool_t pg, uint64_t const * rn, int64_t vnum, svuint64x3_t zt);
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

## svst3q_vnum[_u8]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst3q_vnum%5B_u8%5D

### Signature (source notation)

```c
void svst3q_vnum[_u8](svbool_t pg, uint8_t const * rn, int64_t vnum, svuint8x3_t zt);
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

## svst4[_bf16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst4%5B_bf16%5D

### Signature (source notation)

```c
void svst4[_bf16](svbool_t pg, bfloat16_t *base, svbfloat16x4_t data);
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
    "register": "{Zdata0.H - Zdata3.H}"
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
ST4H {Zdata0.H - Zdata3.H}, Pg, [Xarray, Xindex, LSL #1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST4H--scalar-plus-scalar---Contiguous-store-four-halfword-structures-from-four-vectors--scalar-index--

The general implementation is:

```asm
ST4H {Zdata0.H - Zdata3.H}, Pg, [Xbase, #0, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST4H--scalar-plus-immediate---Contiguous-store-four-halfword-structures-from-four-vectors--immediate-index--

### Operation

Source operation ID: `SveOperation_svst4_bf16`

**Operation**



For each active element *i* and for each vector index *j*, store `data[j][i]` to `base[i * 4 + j]`. Do not access memory for inactive elements.

## svst4[_f16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst4%5B_f16%5D

### Signature (source notation)

```c
void svst4[_f16](svbool_t pg, float16_t *base, svfloat16x4_t data);
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
    "register": "{Zdata0.H - Zdata3.H}"
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
ST4H {Zdata0.H - Zdata3.H}, Pg, [Xarray, Xindex, LSL #1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST4H--scalar-plus-scalar---Contiguous-store-four-halfword-structures-from-four-vectors--scalar-index--

The general implementation is:

```asm
ST4H {Zdata0.H - Zdata3.H}, Pg, [Xbase, #0, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST4H--scalar-plus-immediate---Contiguous-store-four-halfword-structures-from-four-vectors--immediate-index--

### Operation

Source operation ID: `SveOperation_svst4_bf16`

**Operation**



For each active element *i* and for each vector index *j*, store `data[j][i]` to `base[i * 4 + j]`. Do not access memory for inactive elements.

## svst4[_f32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst4%5B_f32%5D

### Signature (source notation)

```c
void svst4[_f32](svbool_t pg, float32_t *base, svfloat32x4_t data);
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
    "register": "{Zdata0.S - Zdata3.S}"
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
ST4W {Zdata0.S - Zdata3.S}, Pg, [Xarray, Xindex, LSL #2]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST4W--scalar-plus-scalar---Contiguous-store-four-word-structures-from-four-vectors--scalar-index--

The general implementation is:

```asm
ST4W {Zdata0.S - Zdata3.S}, Pg, [Xbase, #0, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST4W--scalar-plus-immediate---Contiguous-store-four-word-structures-from-four-vectors--immediate-index--

### Operation

Source operation ID: `SveOperation_svst4_bf16`

**Operation**



For each active element *i* and for each vector index *j*, store `data[j][i]` to `base[i * 4 + j]`. Do not access memory for inactive elements.

## svst4[_f64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst4%5B_f64%5D

### Signature (source notation)

```c
void svst4[_f64](svbool_t pg, float64_t *base, svfloat64x4_t data);
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
    "register": "{Zdata0.D - Zdata3.D}"
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
ST4D {Zdata0.D - Zdata3.D}, Pg, [Xarray, Xindex, LSL #3]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST4D--scalar-plus-scalar---Contiguous-store-four-doubleword-structures-from-four-vectors--scalar-index--

The general implementation is:

```asm
ST4D {Zdata0.D - Zdata3.D}, Pg, [Xbase, #0, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST4D--scalar-plus-immediate---Contiguous-store-four-doubleword-structures-from-four-vectors--immediate-index--

### Operation

Source operation ID: `SveOperation_svst4_bf16`

**Operation**



For each active element *i* and for each vector index *j*, store `data[j][i]` to `base[i * 4 + j]`. Do not access memory for inactive elements.

## svst4[_mf8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst4%5B_mf8%5D

### Signature (source notation)

```c
void svst4[_mf8](svbool_t pg, mfloat8_t *base, svmfloat8x4_t data);
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
    "register": "{Zdata0.B - Zdata3.B}"
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
ST4B {Zdata0.B - Zdata3.B}, Pg, [Xarray, Xindex]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST4B--scalar-plus-scalar---Contiguous-store-four-byte-structures-from-four-vectors--scalar-index--

The general implementation is:

```asm
ST4B {Zdata0.B - Zdata3.B}, Pg, [Xbase, #0, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST4B--scalar-plus-immediate---Contiguous-store-four-byte-structures-from-four-vectors--immediate-index--

### Operation

Source operation ID: `SveOperation_svst4_bf16`

**Operation**



For each active element *i* and for each vector index *j*, store `data[j][i]` to `base[i * 4 + j]`. Do not access memory for inactive elements.

## svst4[_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst4%5B_s16%5D

### Signature (source notation)

```c
void svst4[_s16](svbool_t pg, int16_t *base, svint16x4_t data);
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
    "register": "{Zdata0.H - Zdata3.H}"
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
ST4H {Zdata0.H - Zdata3.H}, Pg, [Xarray, Xindex, LSL #1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST4H--scalar-plus-scalar---Contiguous-store-four-halfword-structures-from-four-vectors--scalar-index--

The general implementation is:

```asm
ST4H {Zdata0.H - Zdata3.H}, Pg, [Xbase, #0, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST4H--scalar-plus-immediate---Contiguous-store-four-halfword-structures-from-four-vectors--immediate-index--

### Operation

Source operation ID: `SveOperation_svst4_bf16`

**Operation**



For each active element *i* and for each vector index *j*, store `data[j][i]` to `base[i * 4 + j]`. Do not access memory for inactive elements.

## svst4[_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst4%5B_s32%5D

### Signature (source notation)

```c
void svst4[_s32](svbool_t pg, int32_t *base, svint32x4_t data);
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
    "register": "{Zdata0.S - Zdata3.S}"
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
ST4W {Zdata0.S - Zdata3.S}, Pg, [Xarray, Xindex, LSL #2]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST4W--scalar-plus-scalar---Contiguous-store-four-word-structures-from-four-vectors--scalar-index--

The general implementation is:

```asm
ST4W {Zdata0.S - Zdata3.S}, Pg, [Xbase, #0, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST4W--scalar-plus-immediate---Contiguous-store-four-word-structures-from-four-vectors--immediate-index--

### Operation

Source operation ID: `SveOperation_svst4_bf16`

**Operation**



For each active element *i* and for each vector index *j*, store `data[j][i]` to `base[i * 4 + j]`. Do not access memory for inactive elements.

## svst4[_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst4%5B_s64%5D

### Signature (source notation)

```c
void svst4[_s64](svbool_t pg, int64_t *base, svint64x4_t data);
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
ST4D {Zdata0.D - Zdata3.D}, Pg, [Xarray, Xindex, LSL #3]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST4D--scalar-plus-scalar---Contiguous-store-four-doubleword-structures-from-four-vectors--scalar-index--

The general implementation is:

```asm
ST4D {Zdata0.D - Zdata3.D}, Pg, [Xbase, #0, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST4D--scalar-plus-immediate---Contiguous-store-four-doubleword-structures-from-four-vectors--immediate-index--

### Operation

Source operation ID: `SveOperation_svst4_bf16`

**Operation**



For each active element *i* and for each vector index *j*, store `data[j][i]` to `base[i * 4 + j]`. Do not access memory for inactive elements.

## svst4[_s8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst4%5B_s8%5D

### Signature (source notation)

```c
void svst4[_s8](svbool_t pg, int8_t *base, svint8x4_t data);
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
    "register": "{Zdata0.B - Zdata3.B}"
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
ST4B {Zdata0.B - Zdata3.B}, Pg, [Xarray, Xindex]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST4B--scalar-plus-scalar---Contiguous-store-four-byte-structures-from-four-vectors--scalar-index--

The general implementation is:

```asm
ST4B {Zdata0.B - Zdata3.B}, Pg, [Xbase, #0, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST4B--scalar-plus-immediate---Contiguous-store-four-byte-structures-from-four-vectors--immediate-index--

### Operation

Source operation ID: `SveOperation_svst4_bf16`

**Operation**



For each active element *i* and for each vector index *j*, store `data[j][i]` to `base[i * 4 + j]`. Do not access memory for inactive elements.

## svst4[_u16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst4%5B_u16%5D

### Signature (source notation)

```c
void svst4[_u16](svbool_t pg, uint16_t *base, svuint16x4_t data);
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
    "register": "{Zdata0.H - Zdata3.H}"
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
ST4H {Zdata0.H - Zdata3.H}, Pg, [Xarray, Xindex, LSL #1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST4H--scalar-plus-scalar---Contiguous-store-four-halfword-structures-from-four-vectors--scalar-index--

The general implementation is:

```asm
ST4H {Zdata0.H - Zdata3.H}, Pg, [Xbase, #0, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST4H--scalar-plus-immediate---Contiguous-store-four-halfword-structures-from-four-vectors--immediate-index--

### Operation

Source operation ID: `SveOperation_svst4_bf16`

**Operation**



For each active element *i* and for each vector index *j*, store `data[j][i]` to `base[i * 4 + j]`. Do not access memory for inactive elements.

## svst4[_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst4%5B_u32%5D

### Signature (source notation)

```c
void svst4[_u32](svbool_t pg, uint32_t *base, svuint32x4_t data);
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
    "register": "{Zdata0.S - Zdata3.S}"
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
ST4W {Zdata0.S - Zdata3.S}, Pg, [Xarray, Xindex, LSL #2]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST4W--scalar-plus-scalar---Contiguous-store-four-word-structures-from-four-vectors--scalar-index--

The general implementation is:

```asm
ST4W {Zdata0.S - Zdata3.S}, Pg, [Xbase, #0, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST4W--scalar-plus-immediate---Contiguous-store-four-word-structures-from-four-vectors--immediate-index--

### Operation

Source operation ID: `SveOperation_svst4_bf16`

**Operation**



For each active element *i* and for each vector index *j*, store `data[j][i]` to `base[i * 4 + j]`. Do not access memory for inactive elements.

## svst4[_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst4%5B_u64%5D

### Signature (source notation)

```c
void svst4[_u64](svbool_t pg, uint64_t *base, svuint64x4_t data);
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
    "register": "{Zdata0.D - Zdata3.D}"
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
ST4D {Zdata0.D - Zdata3.D}, Pg, [Xarray, Xindex, LSL #3]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST4D--scalar-plus-scalar---Contiguous-store-four-doubleword-structures-from-four-vectors--scalar-index--

The general implementation is:

```asm
ST4D {Zdata0.D - Zdata3.D}, Pg, [Xbase, #0, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST4D--scalar-plus-immediate---Contiguous-store-four-doubleword-structures-from-four-vectors--immediate-index--

### Operation

Source operation ID: `SveOperation_svst4_bf16`

**Operation**



For each active element *i* and for each vector index *j*, store `data[j][i]` to `base[i * 4 + j]`. Do not access memory for inactive elements.

## svst4[_u8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst4%5B_u8%5D

### Signature (source notation)

```c
void svst4[_u8](svbool_t pg, uint8_t *base, svuint8x4_t data);
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
    "register": "{Zdata0.B - Zdata3.B}"
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
ST4B {Zdata0.B - Zdata3.B}, Pg, [Xarray, Xindex]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST4B--scalar-plus-scalar---Contiguous-store-four-byte-structures-from-four-vectors--scalar-index--

The general implementation is:

```asm
ST4B {Zdata0.B - Zdata3.B}, Pg, [Xbase, #0, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST4B--scalar-plus-immediate---Contiguous-store-four-byte-structures-from-four-vectors--immediate-index--

### Operation

Source operation ID: `SveOperation_svst4_bf16`

**Operation**



For each active element *i* and for each vector index *j*, store `data[j][i]` to `base[i * 4 + j]`. Do not access memory for inactive elements.

## svst4_vnum[_bf16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst4_vnum%5B_bf16%5D

### Signature (source notation)

```c
void svst4_vnum[_bf16](svbool_t pg, bfloat16_t *base, int64_t vnum, svbfloat16x4_t data);
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
    "register": "{Zdata0.H - Zdata3.H}"
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

When vnum is a multiple of 4 in the range [-32, 28], this intrinsic can use:

```asm
ST4H {Zdata0.H - Zdata3.H}, Pg, [Xbase, #vnum, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST4H--scalar-plus-immediate---Contiguous-store-four-halfword-structures-from-four-vectors--immediate-index--

The general implementation is:

```asm
ST4H {Zdata0.H - Zdata3.H}, Pg, [Xbase, Xindex, LSL #1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST4H--scalar-plus-scalar---Contiguous-store-four-halfword-structures-from-four-vectors--scalar-index--

### Operation

Source operation ID: `SveOperation_svst4_vnum_bf16`

**Operation**



For each active element *i* and for each vector index *j*, store `data[j][i]` to `base[n * vnum + i * 4 + j]`, where *n* is the number of elements in `data[j]`. Do not access memory for inactive elements.

## svst4_vnum[_f16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst4_vnum%5B_f16%5D

### Signature (source notation)

```c
void svst4_vnum[_f16](svbool_t pg, float16_t *base, int64_t vnum, svfloat16x4_t data);
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
    "register": "{Zdata0.H - Zdata3.H}"
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

When vnum is a multiple of 4 in the range [-32, 28], this intrinsic can use:

```asm
ST4H {Zdata0.H - Zdata3.H}, Pg, [Xbase, #vnum, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST4H--scalar-plus-immediate---Contiguous-store-four-halfword-structures-from-four-vectors--immediate-index--

The general implementation is:

```asm
ST4H {Zdata0.H - Zdata3.H}, Pg, [Xbase, Xindex, LSL #1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST4H--scalar-plus-scalar---Contiguous-store-four-halfword-structures-from-four-vectors--scalar-index--

### Operation

Source operation ID: `SveOperation_svst4_vnum_bf16`

**Operation**



For each active element *i* and for each vector index *j*, store `data[j][i]` to `base[n * vnum + i * 4 + j]`, where *n* is the number of elements in `data[j]`. Do not access memory for inactive elements.

## svst4_vnum[_f32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst4_vnum%5B_f32%5D

### Signature (source notation)

```c
void svst4_vnum[_f32](svbool_t pg, float32_t *base, int64_t vnum, svfloat32x4_t data);
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
    "register": "{Zdata0.S - Zdata3.S}"
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

When vnum is a multiple of 4 in the range [-32, 28], this intrinsic can use:

```asm
ST4W {Zdata0.S - Zdata3.S}, Pg, [Xbase, #vnum, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST4W--scalar-plus-immediate---Contiguous-store-four-word-structures-from-four-vectors--immediate-index--

The general implementation is:

```asm
ST4W {Zdata0.S - Zdata3.S}, Pg, [Xbase, Xindex, LSL #2]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST4W--scalar-plus-scalar---Contiguous-store-four-word-structures-from-four-vectors--scalar-index--

### Operation

Source operation ID: `SveOperation_svst4_vnum_bf16`

**Operation**



For each active element *i* and for each vector index *j*, store `data[j][i]` to `base[n * vnum + i * 4 + j]`, where *n* is the number of elements in `data[j]`. Do not access memory for inactive elements.

## svst4_vnum[_f64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst4_vnum%5B_f64%5D

### Signature (source notation)

```c
void svst4_vnum[_f64](svbool_t pg, float64_t *base, int64_t vnum, svfloat64x4_t data);
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

## svst4_vnum[_mf8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst4_vnum%5B_mf8%5D

### Signature (source notation)

```c
void svst4_vnum[_mf8](svbool_t pg, mfloat8_t *base, int64_t vnum, svmfloat8x4_t data);
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

## svst4_vnum[_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst4_vnum%5B_s16%5D

### Signature (source notation)

```c
void svst4_vnum[_s16](svbool_t pg, int16_t *base, int64_t vnum, svint16x4_t data);
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
    "register": "{Zdata0.H - Zdata3.H}"
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

When vnum is a multiple of 4 in the range [-32, 28], this intrinsic can use:

```asm
ST4H {Zdata0.H - Zdata3.H}, Pg, [Xbase, #vnum, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST4H--scalar-plus-immediate---Contiguous-store-four-halfword-structures-from-four-vectors--immediate-index--

The general implementation is:

```asm
ST4H {Zdata0.H - Zdata3.H}, Pg, [Xbase, Xindex, LSL #1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST4H--scalar-plus-scalar---Contiguous-store-four-halfword-structures-from-four-vectors--scalar-index--

### Operation

Source operation ID: `SveOperation_svst4_vnum_bf16`

**Operation**



For each active element *i* and for each vector index *j*, store `data[j][i]` to `base[n * vnum + i * 4 + j]`, where *n* is the number of elements in `data[j]`. Do not access memory for inactive elements.

## svst4_vnum[_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst4_vnum%5B_s32%5D

### Signature (source notation)

```c
void svst4_vnum[_s32](svbool_t pg, int32_t *base, int64_t vnum, svint32x4_t data);
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
    "register": "{Zdata0.S - Zdata3.S}"
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

When vnum is a multiple of 4 in the range [-32, 28], this intrinsic can use:

```asm
ST4W {Zdata0.S - Zdata3.S}, Pg, [Xbase, #vnum, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST4W--scalar-plus-immediate---Contiguous-store-four-word-structures-from-four-vectors--immediate-index--

The general implementation is:

```asm
ST4W {Zdata0.S - Zdata3.S}, Pg, [Xbase, Xindex, LSL #2]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST4W--scalar-plus-scalar---Contiguous-store-four-word-structures-from-four-vectors--scalar-index--

### Operation

Source operation ID: `SveOperation_svst4_vnum_bf16`

**Operation**



For each active element *i* and for each vector index *j*, store `data[j][i]` to `base[n * vnum + i * 4 + j]`, where *n* is the number of elements in `data[j]`. Do not access memory for inactive elements.

## svst4_vnum[_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst4_vnum%5B_s64%5D

### Signature (source notation)

```c
void svst4_vnum[_s64](svbool_t pg, int64_t *base, int64_t vnum, svint64x4_t data);
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

## svst4_vnum[_s8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst4_vnum%5B_s8%5D

### Signature (source notation)

```c
void svst4_vnum[_s8](svbool_t pg, int8_t *base, int64_t vnum, svint8x4_t data);
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

## svst4_vnum[_u16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst4_vnum%5B_u16%5D

### Signature (source notation)

```c
void svst4_vnum[_u16](svbool_t pg, uint16_t *base, int64_t vnum, svuint16x4_t data);
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
    "register": "{Zdata0.H - Zdata3.H}"
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

When vnum is a multiple of 4 in the range [-32, 28], this intrinsic can use:

```asm
ST4H {Zdata0.H - Zdata3.H}, Pg, [Xbase, #vnum, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST4H--scalar-plus-immediate---Contiguous-store-four-halfword-structures-from-four-vectors--immediate-index--

The general implementation is:

```asm
ST4H {Zdata0.H - Zdata3.H}, Pg, [Xbase, Xindex, LSL #1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST4H--scalar-plus-scalar---Contiguous-store-four-halfword-structures-from-four-vectors--scalar-index--

### Operation

Source operation ID: `SveOperation_svst4_vnum_bf16`

**Operation**



For each active element *i* and for each vector index *j*, store `data[j][i]` to `base[n * vnum + i * 4 + j]`, where *n* is the number of elements in `data[j]`. Do not access memory for inactive elements.

## svst4_vnum[_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst4_vnum%5B_u32%5D

### Signature (source notation)

```c
void svst4_vnum[_u32](svbool_t pg, uint32_t *base, int64_t vnum, svuint32x4_t data);
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
    "register": "{Zdata0.S - Zdata3.S}"
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

When vnum is a multiple of 4 in the range [-32, 28], this intrinsic can use:

```asm
ST4W {Zdata0.S - Zdata3.S}, Pg, [Xbase, #vnum, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST4W--scalar-plus-immediate---Contiguous-store-four-word-structures-from-four-vectors--immediate-index--

The general implementation is:

```asm
ST4W {Zdata0.S - Zdata3.S}, Pg, [Xbase, Xindex, LSL #2]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST4W--scalar-plus-scalar---Contiguous-store-four-word-structures-from-four-vectors--scalar-index--

### Operation

Source operation ID: `SveOperation_svst4_vnum_bf16`

**Operation**



For each active element *i* and for each vector index *j*, store `data[j][i]` to `base[n * vnum + i * 4 + j]`, where *n* is the number of elements in `data[j]`. Do not access memory for inactive elements.

