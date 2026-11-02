# SME / Store / Consecutive — Part 4

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

## svst3[_bf16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst3%5B_bf16%5D

### Signature (source notation)

```c
void svst3[_bf16](svbool_t pg, bfloat16_t *base, svbfloat16x3_t data);
```

### Description

Store three vectors into three-element tuples

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
    "register": "{Zdata0.H - Zdata2.H}"
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
ST3H {Zdata0.H - Zdata2.H}, Pg, [Xarray, Xindex, LSL #1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST3H--scalar-plus-scalar---Contiguous-store-three-halfword-structures-from-three-vectors--scalar-index--

The general implementation is:

```asm
ST3H {Zdata0.H - Zdata2.H}, Pg, [Xbase, #0, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST3H--scalar-plus-immediate---Contiguous-store-three-halfword-structures-from-three-vectors--immediate-index--

### Operation

Source operation ID: `SveOperation_svst3_bf16`

**Operation**



For each active element *i* and for each vector index *j*, store `data[j][i]` to `base[i * 3 + j]`. Do not access memory for inactive elements.

## svst3[_f16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst3%5B_f16%5D

### Signature (source notation)

```c
void svst3[_f16](svbool_t pg, float16_t *base, svfloat16x3_t data);
```

### Description

Store three vectors into three-element tuples

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
    "register": "{Zdata0.H - Zdata2.H}"
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
ST3H {Zdata0.H - Zdata2.H}, Pg, [Xarray, Xindex, LSL #1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST3H--scalar-plus-scalar---Contiguous-store-three-halfword-structures-from-three-vectors--scalar-index--

The general implementation is:

```asm
ST3H {Zdata0.H - Zdata2.H}, Pg, [Xbase, #0, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST3H--scalar-plus-immediate---Contiguous-store-three-halfword-structures-from-three-vectors--immediate-index--

### Operation

Source operation ID: `SveOperation_svst3_bf16`

**Operation**



For each active element *i* and for each vector index *j*, store `data[j][i]` to `base[i * 3 + j]`. Do not access memory for inactive elements.

## svst3[_f32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst3%5B_f32%5D

### Signature (source notation)

```c
void svst3[_f32](svbool_t pg, float32_t *base, svfloat32x3_t data);
```

### Description

Store three vectors into three-element tuples

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
    "register": "{Zdata0.S - Zdata2.S}"
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
ST3W {Zdata0.S - Zdata2.S}, Pg, [Xarray, Xindex, LSL #2]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST3W--scalar-plus-scalar---Contiguous-store-three-word-structures-from-three-vectors--scalar-index--

The general implementation is:

```asm
ST3W {Zdata0.S - Zdata2.S}, Pg, [Xbase, #0, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST3W--scalar-plus-immediate---Contiguous-store-three-word-structures-from-three-vectors--immediate-index--

### Operation

Source operation ID: `SveOperation_svst3_bf16`

**Operation**



For each active element *i* and for each vector index *j*, store `data[j][i]` to `base[i * 3 + j]`. Do not access memory for inactive elements.

## svst3[_f64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst3%5B_f64%5D

### Signature (source notation)

```c
void svst3[_f64](svbool_t pg, float64_t *base, svfloat64x3_t data);
```

### Description

Store three vectors into three-element tuples

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
    "register": "{Zdata0.D - Zdata2.D}"
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
ST3D {Zdata0.D - Zdata2.D}, Pg, [Xarray, Xindex, LSL #3]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST3D--scalar-plus-scalar---Contiguous-store-three-doubleword-structures-from-three-vectors--scalar-index--

The general implementation is:

```asm
ST3D {Zdata0.D - Zdata2.D}, Pg, [Xbase, #0, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST3D--scalar-plus-immediate---Contiguous-store-three-doubleword-structures-from-three-vectors--immediate-index--

### Operation

Source operation ID: `SveOperation_svst3_bf16`

**Operation**



For each active element *i* and for each vector index *j*, store `data[j][i]` to `base[i * 3 + j]`. Do not access memory for inactive elements.

## svst3[_mf8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst3%5B_mf8%5D

### Signature (source notation)

```c
void svst3[_mf8](svbool_t pg, mfloat8_t *base, svmfloat8x3_t data);
```

### Description

Store three vectors into three-element tuples

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
    "register": "{Zdata0.B - Zdata2.B}"
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
ST3B {Zdata0.B - Zdata2.B}, Pg, [Xarray, Xindex]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST3B--scalar-plus-scalar---Contiguous-store-three-byte-structures-from-three-vectors--scalar-index--

The general implementation is:

```asm
ST3B {Zdata0.B - Zdata2.B}, Pg, [Xbase, #0, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST3B--scalar-plus-immediate---Contiguous-store-three-byte-structures-from-three-vectors--immediate-index--

### Operation

Source operation ID: `SveOperation_svst3_bf16`

**Operation**



For each active element *i* and for each vector index *j*, store `data[j][i]` to `base[i * 3 + j]`. Do not access memory for inactive elements.

## svst3[_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst3%5B_s16%5D

### Signature (source notation)

```c
void svst3[_s16](svbool_t pg, int16_t *base, svint16x3_t data);
```

### Description

Store three vectors into three-element tuples

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
    "register": "{Zdata0.H - Zdata2.H}"
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
ST3H {Zdata0.H - Zdata2.H}, Pg, [Xarray, Xindex, LSL #1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST3H--scalar-plus-scalar---Contiguous-store-three-halfword-structures-from-three-vectors--scalar-index--

The general implementation is:

```asm
ST3H {Zdata0.H - Zdata2.H}, Pg, [Xbase, #0, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST3H--scalar-plus-immediate---Contiguous-store-three-halfword-structures-from-three-vectors--immediate-index--

### Operation

Source operation ID: `SveOperation_svst3_bf16`

**Operation**



For each active element *i* and for each vector index *j*, store `data[j][i]` to `base[i * 3 + j]`. Do not access memory for inactive elements.

## svst3[_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst3%5B_s32%5D

### Signature (source notation)

```c
void svst3[_s32](svbool_t pg, int32_t *base, svint32x3_t data);
```

### Description

Store three vectors into three-element tuples

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
    "register": "{Zdata0.S - Zdata2.S}"
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
ST3W {Zdata0.S - Zdata2.S}, Pg, [Xarray, Xindex, LSL #2]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST3W--scalar-plus-scalar---Contiguous-store-three-word-structures-from-three-vectors--scalar-index--

The general implementation is:

```asm
ST3W {Zdata0.S - Zdata2.S}, Pg, [Xbase, #0, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST3W--scalar-plus-immediate---Contiguous-store-three-word-structures-from-three-vectors--immediate-index--

### Operation

Source operation ID: `SveOperation_svst3_bf16`

**Operation**



For each active element *i* and for each vector index *j*, store `data[j][i]` to `base[i * 3 + j]`. Do not access memory for inactive elements.

## svst3[_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst3%5B_s64%5D

### Signature (source notation)

```c
void svst3[_s64](svbool_t pg, int64_t *base, svint64x3_t data);
```

### Description

Store three vectors into three-element tuples

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
    "register": "{Zdata0.D - Zdata2.D}"
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
ST3D {Zdata0.D - Zdata2.D}, Pg, [Xarray, Xindex, LSL #3]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST3D--scalar-plus-scalar---Contiguous-store-three-doubleword-structures-from-three-vectors--scalar-index--

The general implementation is:

```asm
ST3D {Zdata0.D - Zdata2.D}, Pg, [Xbase, #0, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST3D--scalar-plus-immediate---Contiguous-store-three-doubleword-structures-from-three-vectors--immediate-index--

### Operation

Source operation ID: `SveOperation_svst3_bf16`

**Operation**



For each active element *i* and for each vector index *j*, store `data[j][i]` to `base[i * 3 + j]`. Do not access memory for inactive elements.

## svst3[_s8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst3%5B_s8%5D

### Signature (source notation)

```c
void svst3[_s8](svbool_t pg, int8_t *base, svint8x3_t data);
```

### Description

Store three vectors into three-element tuples

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
    "register": "{Zdata0.B - Zdata2.B}"
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
ST3B {Zdata0.B - Zdata2.B}, Pg, [Xarray, Xindex]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST3B--scalar-plus-scalar---Contiguous-store-three-byte-structures-from-three-vectors--scalar-index--

The general implementation is:

```asm
ST3B {Zdata0.B - Zdata2.B}, Pg, [Xbase, #0, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST3B--scalar-plus-immediate---Contiguous-store-three-byte-structures-from-three-vectors--immediate-index--

### Operation

Source operation ID: `SveOperation_svst3_bf16`

**Operation**



For each active element *i* and for each vector index *j*, store `data[j][i]` to `base[i * 3 + j]`. Do not access memory for inactive elements.

## svst3[_u16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst3%5B_u16%5D

### Signature (source notation)

```c
void svst3[_u16](svbool_t pg, uint16_t *base, svuint16x3_t data);
```

### Description

Store three vectors into three-element tuples

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
    "register": "{Zdata0.H - Zdata2.H}"
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
ST3H {Zdata0.H - Zdata2.H}, Pg, [Xarray, Xindex, LSL #1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST3H--scalar-plus-scalar---Contiguous-store-three-halfword-structures-from-three-vectors--scalar-index--

The general implementation is:

```asm
ST3H {Zdata0.H - Zdata2.H}, Pg, [Xbase, #0, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST3H--scalar-plus-immediate---Contiguous-store-three-halfword-structures-from-three-vectors--immediate-index--

### Operation

Source operation ID: `SveOperation_svst3_bf16`

**Operation**



For each active element *i* and for each vector index *j*, store `data[j][i]` to `base[i * 3 + j]`. Do not access memory for inactive elements.

## svst3[_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst3%5B_u32%5D

### Signature (source notation)

```c
void svst3[_u32](svbool_t pg, uint32_t *base, svuint32x3_t data);
```

### Description

Store three vectors into three-element tuples

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
    "register": "{Zdata0.S - Zdata2.S}"
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
ST3W {Zdata0.S - Zdata2.S}, Pg, [Xarray, Xindex, LSL #2]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST3W--scalar-plus-scalar---Contiguous-store-three-word-structures-from-three-vectors--scalar-index--

The general implementation is:

```asm
ST3W {Zdata0.S - Zdata2.S}, Pg, [Xbase, #0, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST3W--scalar-plus-immediate---Contiguous-store-three-word-structures-from-three-vectors--immediate-index--

### Operation

Source operation ID: `SveOperation_svst3_bf16`

**Operation**



For each active element *i* and for each vector index *j*, store `data[j][i]` to `base[i * 3 + j]`. Do not access memory for inactive elements.

## svst3[_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst3%5B_u64%5D

### Signature (source notation)

```c
void svst3[_u64](svbool_t pg, uint64_t *base, svuint64x3_t data);
```

### Description

Store three vectors into three-element tuples

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
    "register": "{Zdata0.D - Zdata2.D}"
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
ST3D {Zdata0.D - Zdata2.D}, Pg, [Xarray, Xindex, LSL #3]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST3D--scalar-plus-scalar---Contiguous-store-three-doubleword-structures-from-three-vectors--scalar-index--

The general implementation is:

```asm
ST3D {Zdata0.D - Zdata2.D}, Pg, [Xbase, #0, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST3D--scalar-plus-immediate---Contiguous-store-three-doubleword-structures-from-three-vectors--immediate-index--

### Operation

Source operation ID: `SveOperation_svst3_bf16`

**Operation**



For each active element *i* and for each vector index *j*, store `data[j][i]` to `base[i * 3 + j]`. Do not access memory for inactive elements.

## svst3[_u8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst3%5B_u8%5D

### Signature (source notation)

```c
void svst3[_u8](svbool_t pg, uint8_t *base, svuint8x3_t data);
```

### Description

Store three vectors into three-element tuples

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
    "register": "{Zdata0.B - Zdata2.B}"
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
ST3B {Zdata0.B - Zdata2.B}, Pg, [Xarray, Xindex]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST3B--scalar-plus-scalar---Contiguous-store-three-byte-structures-from-three-vectors--scalar-index--

The general implementation is:

```asm
ST3B {Zdata0.B - Zdata2.B}, Pg, [Xbase, #0, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST3B--scalar-plus-immediate---Contiguous-store-three-byte-structures-from-three-vectors--immediate-index--

### Operation

Source operation ID: `SveOperation_svst3_bf16`

**Operation**



For each active element *i* and for each vector index *j*, store `data[j][i]` to `base[i * 3 + j]`. Do not access memory for inactive elements.

## svst3_vnum[_bf16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst3_vnum%5B_bf16%5D

### Signature (source notation)

```c
void svst3_vnum[_bf16](svbool_t pg, bfloat16_t *base, int64_t vnum, svbfloat16x3_t data);
```

### Description

Store three vectors into three-element tuples

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
    "register": "{Zdata0.H - Zdata2.H}"
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

When vnum is a multiple of 3 in the range [-24, 21], this intrinsic can use:

```asm
ST3H {Zdata0.H - Zdata2.H}, Pg, [Xbase, #vnum, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST3H--scalar-plus-immediate---Contiguous-store-three-halfword-structures-from-three-vectors--immediate-index--

The general implementation is:

```asm
ST3H {Zdata0.H - Zdata2.H}, Pg, [Xbase, Xindex, LSL #1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST3H--scalar-plus-scalar---Contiguous-store-three-halfword-structures-from-three-vectors--scalar-index--

### Operation

Source operation ID: `SveOperation_svst3_vnum_bf16`

**Operation**



For each active element *i* and for each vector index *j*, store `data[j][i]` to `base[n * vnum + i * 3 + j]`, where *n* is the number of elements in `data[j]`. Do not access memory for inactive elements.

## svst3_vnum[_f16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst3_vnum%5B_f16%5D

### Signature (source notation)

```c
void svst3_vnum[_f16](svbool_t pg, float16_t *base, int64_t vnum, svfloat16x3_t data);
```

### Description

Store three vectors into three-element tuples

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
    "register": "{Zdata0.H - Zdata2.H}"
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

When vnum is a multiple of 3 in the range [-24, 21], this intrinsic can use:

```asm
ST3H {Zdata0.H - Zdata2.H}, Pg, [Xbase, #vnum, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST3H--scalar-plus-immediate---Contiguous-store-three-halfword-structures-from-three-vectors--immediate-index--

The general implementation is:

```asm
ST3H {Zdata0.H - Zdata2.H}, Pg, [Xbase, Xindex, LSL #1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST3H--scalar-plus-scalar---Contiguous-store-three-halfword-structures-from-three-vectors--scalar-index--

### Operation

Source operation ID: `SveOperation_svst3_vnum_bf16`

**Operation**



For each active element *i* and for each vector index *j*, store `data[j][i]` to `base[n * vnum + i * 3 + j]`, where *n* is the number of elements in `data[j]`. Do not access memory for inactive elements.

## svst3_vnum[_f32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst3_vnum%5B_f32%5D

### Signature (source notation)

```c
void svst3_vnum[_f32](svbool_t pg, float32_t *base, int64_t vnum, svfloat32x3_t data);
```

### Description

Store three vectors into three-element tuples

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
    "register": "{Zdata0.S - Zdata2.S}"
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

When vnum is a multiple of 3 in the range [-24, 21], this intrinsic can use:

```asm
ST3W {Zdata0.S - Zdata2.S}, Pg, [Xbase, #vnum, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST3W--scalar-plus-immediate---Contiguous-store-three-word-structures-from-three-vectors--immediate-index--

The general implementation is:

```asm
ST3W {Zdata0.S - Zdata2.S}, Pg, [Xbase, Xindex, LSL #2]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST3W--scalar-plus-scalar---Contiguous-store-three-word-structures-from-three-vectors--scalar-index--

### Operation

Source operation ID: `SveOperation_svst3_vnum_bf16`

**Operation**



For each active element *i* and for each vector index *j*, store `data[j][i]` to `base[n * vnum + i * 3 + j]`, where *n* is the number of elements in `data[j]`. Do not access memory for inactive elements.

## svst3_vnum[_f64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst3_vnum%5B_f64%5D

### Signature (source notation)

```c
void svst3_vnum[_f64](svbool_t pg, float64_t *base, int64_t vnum, svfloat64x3_t data);
```

### Description

Store three vectors into three-element tuples

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
    "register": "{Zdata0.D - Zdata2.D}"
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

When vnum is a multiple of 3 in the range [-24, 21], this intrinsic can use:

```asm
ST3D {Zdata0.D - Zdata2.D}, Pg, [Xbase, #vnum, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST3D--scalar-plus-immediate---Contiguous-store-three-doubleword-structures-from-three-vectors--immediate-index--

The general implementation is:

```asm
ST3D {Zdata0.D - Zdata2.D}, Pg, [Xbase, Xindex, LSL #3]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST3D--scalar-plus-scalar---Contiguous-store-three-doubleword-structures-from-three-vectors--scalar-index--

### Operation

Source operation ID: `SveOperation_svst3_vnum_bf16`

**Operation**



For each active element *i* and for each vector index *j*, store `data[j][i]` to `base[n * vnum + i * 3 + j]`, where *n* is the number of elements in `data[j]`. Do not access memory for inactive elements.

## svst3_vnum[_mf8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst3_vnum%5B_mf8%5D

### Signature (source notation)

```c
void svst3_vnum[_mf8](svbool_t pg, mfloat8_t *base, int64_t vnum, svmfloat8x3_t data);
```

### Description

Store three vectors into three-element tuples

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
    "register": "{Zdata0.B - Zdata2.B}"
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

When vnum is a multiple of 3 in the range [-24, 21], this intrinsic can use:

```asm
ST3B {Zdata0.B - Zdata2.B}, Pg, [Xbase, #vnum, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST3B--scalar-plus-immediate---Contiguous-store-three-byte-structures-from-three-vectors--immediate-index--

The general implementation is:

```asm
ST3B {Zdata0.B - Zdata2.B}, Pg, [Xbase, Xindex]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST3B--scalar-plus-scalar---Contiguous-store-three-byte-structures-from-three-vectors--scalar-index--

### Operation

Source operation ID: `SveOperation_svst3_vnum_bf16`

**Operation**



For each active element *i* and for each vector index *j*, store `data[j][i]` to `base[n * vnum + i * 3 + j]`, where *n* is the number of elements in `data[j]`. Do not access memory for inactive elements.

## svst3_vnum[_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst3_vnum%5B_s16%5D

### Signature (source notation)

```c
void svst3_vnum[_s16](svbool_t pg, int16_t *base, int64_t vnum, svint16x3_t data);
```

### Description

Store three vectors into three-element tuples

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
    "register": "{Zdata0.H - Zdata2.H}"
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

When vnum is a multiple of 3 in the range [-24, 21], this intrinsic can use:

```asm
ST3H {Zdata0.H - Zdata2.H}, Pg, [Xbase, #vnum, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST3H--scalar-plus-immediate---Contiguous-store-three-halfword-structures-from-three-vectors--immediate-index--

The general implementation is:

```asm
ST3H {Zdata0.H - Zdata2.H}, Pg, [Xbase, Xindex, LSL #1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST3H--scalar-plus-scalar---Contiguous-store-three-halfword-structures-from-three-vectors--scalar-index--

### Operation

Source operation ID: `SveOperation_svst3_vnum_bf16`

**Operation**



For each active element *i* and for each vector index *j*, store `data[j][i]` to `base[n * vnum + i * 3 + j]`, where *n* is the number of elements in `data[j]`. Do not access memory for inactive elements.

## svst3_vnum[_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst3_vnum%5B_s32%5D

### Signature (source notation)

```c
void svst3_vnum[_s32](svbool_t pg, int32_t *base, int64_t vnum, svint32x3_t data);
```

### Description

Store three vectors into three-element tuples

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
    "register": "{Zdata0.S - Zdata2.S}"
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

When vnum is a multiple of 3 in the range [-24, 21], this intrinsic can use:

```asm
ST3W {Zdata0.S - Zdata2.S}, Pg, [Xbase, #vnum, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST3W--scalar-plus-immediate---Contiguous-store-three-word-structures-from-three-vectors--immediate-index--

The general implementation is:

```asm
ST3W {Zdata0.S - Zdata2.S}, Pg, [Xbase, Xindex, LSL #2]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST3W--scalar-plus-scalar---Contiguous-store-three-word-structures-from-three-vectors--scalar-index--

### Operation

Source operation ID: `SveOperation_svst3_vnum_bf16`

**Operation**



For each active element *i* and for each vector index *j*, store `data[j][i]` to `base[n * vnum + i * 3 + j]`, where *n* is the number of elements in `data[j]`. Do not access memory for inactive elements.

## svst3_vnum[_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst3_vnum%5B_s64%5D

### Signature (source notation)

```c
void svst3_vnum[_s64](svbool_t pg, int64_t *base, int64_t vnum, svint64x3_t data);
```

### Description

Store three vectors into three-element tuples

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
    "register": "{Zdata0.D - Zdata2.D}"
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

When vnum is a multiple of 3 in the range [-24, 21], this intrinsic can use:

```asm
ST3D {Zdata0.D - Zdata2.D}, Pg, [Xbase, #vnum, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST3D--scalar-plus-immediate---Contiguous-store-three-doubleword-structures-from-three-vectors--immediate-index--

The general implementation is:

```asm
ST3D {Zdata0.D - Zdata2.D}, Pg, [Xbase, Xindex, LSL #3]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST3D--scalar-plus-scalar---Contiguous-store-three-doubleword-structures-from-three-vectors--scalar-index--

### Operation

Source operation ID: `SveOperation_svst3_vnum_bf16`

**Operation**



For each active element *i* and for each vector index *j*, store `data[j][i]` to `base[n * vnum + i * 3 + j]`, where *n* is the number of elements in `data[j]`. Do not access memory for inactive elements.

## svst3_vnum[_s8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst3_vnum%5B_s8%5D

### Signature (source notation)

```c
void svst3_vnum[_s8](svbool_t pg, int8_t *base, int64_t vnum, svint8x3_t data);
```

### Description

Store three vectors into three-element tuples

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
    "register": "{Zdata0.B - Zdata2.B}"
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

When vnum is a multiple of 3 in the range [-24, 21], this intrinsic can use:

```asm
ST3B {Zdata0.B - Zdata2.B}, Pg, [Xbase, #vnum, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST3B--scalar-plus-immediate---Contiguous-store-three-byte-structures-from-three-vectors--immediate-index--

The general implementation is:

```asm
ST3B {Zdata0.B - Zdata2.B}, Pg, [Xbase, Xindex]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST3B--scalar-plus-scalar---Contiguous-store-three-byte-structures-from-three-vectors--scalar-index--

### Operation

Source operation ID: `SveOperation_svst3_vnum_bf16`

**Operation**



For each active element *i* and for each vector index *j*, store `data[j][i]` to `base[n * vnum + i * 3 + j]`, where *n* is the number of elements in `data[j]`. Do not access memory for inactive elements.

## svst3_vnum[_u16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst3_vnum%5B_u16%5D

### Signature (source notation)

```c
void svst3_vnum[_u16](svbool_t pg, uint16_t *base, int64_t vnum, svuint16x3_t data);
```

### Description

Store three vectors into three-element tuples

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
    "register": "{Zdata0.H - Zdata2.H}"
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

When vnum is a multiple of 3 in the range [-24, 21], this intrinsic can use:

```asm
ST3H {Zdata0.H - Zdata2.H}, Pg, [Xbase, #vnum, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST3H--scalar-plus-immediate---Contiguous-store-three-halfword-structures-from-three-vectors--immediate-index--

The general implementation is:

```asm
ST3H {Zdata0.H - Zdata2.H}, Pg, [Xbase, Xindex, LSL #1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST3H--scalar-plus-scalar---Contiguous-store-three-halfword-structures-from-three-vectors--scalar-index--

### Operation

Source operation ID: `SveOperation_svst3_vnum_bf16`

**Operation**



For each active element *i* and for each vector index *j*, store `data[j][i]` to `base[n * vnum + i * 3 + j]`, where *n* is the number of elements in `data[j]`. Do not access memory for inactive elements.

## svst3_vnum[_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst3_vnum%5B_u32%5D

### Signature (source notation)

```c
void svst3_vnum[_u32](svbool_t pg, uint32_t *base, int64_t vnum, svuint32x3_t data);
```

### Description

Store three vectors into three-element tuples

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
    "register": "{Zdata0.S - Zdata2.S}"
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

When vnum is a multiple of 3 in the range [-24, 21], this intrinsic can use:

```asm
ST3W {Zdata0.S - Zdata2.S}, Pg, [Xbase, #vnum, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST3W--scalar-plus-immediate---Contiguous-store-three-word-structures-from-three-vectors--immediate-index--

The general implementation is:

```asm
ST3W {Zdata0.S - Zdata2.S}, Pg, [Xbase, Xindex, LSL #2]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST3W--scalar-plus-scalar---Contiguous-store-three-word-structures-from-three-vectors--scalar-index--

### Operation

Source operation ID: `SveOperation_svst3_vnum_bf16`

**Operation**



For each active element *i* and for each vector index *j*, store `data[j][i]` to `base[n * vnum + i * 3 + j]`, where *n* is the number of elements in `data[j]`. Do not access memory for inactive elements.

## svst3_vnum[_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst3_vnum%5B_u64%5D

### Signature (source notation)

```c
void svst3_vnum[_u64](svbool_t pg, uint64_t *base, int64_t vnum, svuint64x3_t data);
```

### Description

Store three vectors into three-element tuples

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
    "register": "{Zdata0.D - Zdata2.D}"
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

When vnum is a multiple of 3 in the range [-24, 21], this intrinsic can use:

```asm
ST3D {Zdata0.D - Zdata2.D}, Pg, [Xbase, #vnum, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST3D--scalar-plus-immediate---Contiguous-store-three-doubleword-structures-from-three-vectors--immediate-index--

The general implementation is:

```asm
ST3D {Zdata0.D - Zdata2.D}, Pg, [Xbase, Xindex, LSL #3]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST3D--scalar-plus-scalar---Contiguous-store-three-doubleword-structures-from-three-vectors--scalar-index--

### Operation

Source operation ID: `SveOperation_svst3_vnum_bf16`

**Operation**



For each active element *i* and for each vector index *j*, store `data[j][i]` to `base[n * vnum + i * 3 + j]`, where *n* is the number of elements in `data[j]`. Do not access memory for inactive elements.

## svst3_vnum[_u8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst3_vnum%5B_u8%5D

### Signature (source notation)

```c
void svst3_vnum[_u8](svbool_t pg, uint8_t *base, int64_t vnum, svuint8x3_t data);
```

### Description

Store three vectors into three-element tuples

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
    "register": "{Zdata0.B - Zdata2.B}"
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

When vnum is a multiple of 3 in the range [-24, 21], this intrinsic can use:

```asm
ST3B {Zdata0.B - Zdata2.B}, Pg, [Xbase, #vnum, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST3B--scalar-plus-immediate---Contiguous-store-three-byte-structures-from-three-vectors--immediate-index--

The general implementation is:

```asm
ST3B {Zdata0.B - Zdata2.B}, Pg, [Xbase, Xindex]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST3B--scalar-plus-scalar---Contiguous-store-three-byte-structures-from-three-vectors--scalar-index--

### Operation

Source operation ID: `SveOperation_svst3_vnum_bf16`

**Operation**



For each active element *i* and for each vector index *j*, store `data[j][i]` to `base[n * vnum + i * 3 + j]`, where *n* is the number of elements in `data[j]`. Do not access memory for inactive elements.

