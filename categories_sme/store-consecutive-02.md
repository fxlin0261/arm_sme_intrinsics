# SME / Store / Consecutive — Part 2

## svst1_ver_vnum_za16

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst1_ver_vnum_za16

### Signature (source notation)

```c
void svst1_ver_vnum_za16(uint64_t tile, uint32_t slice, svbool_t pg, void * ptr, int64_t vnum)
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
    "ZA array tile": "ZA0V.H"
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
ST1H {ZA0V.H[Wreg1, imm1]}, Preg1, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/ST1H--scalar-plus-scalar--tile-slice---Contiguous-store-of-halfwords-from-16-bit-element-ZA-tile-slice-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svst1_ver_vnum_za32

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst1_ver_vnum_za32

### Signature (source notation)

```c
void svst1_ver_vnum_za32(uint64_t tile, uint32_t slice, svbool_t pg, void * ptr, int64_t vnum)
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
    "ZA array tile": "ZA0V.S"
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
ST1W {ZA0V.S[Wreg1, imm1]}, Preg1, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/ST1W--scalar-plus-scalar--tile-slice---Contiguous-store-of-words-from-32-bit-element-ZA-tile-slice-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svst1_ver_vnum_za64

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst1_ver_vnum_za64

### Signature (source notation)

```c
void svst1_ver_vnum_za64(uint64_t tile, uint32_t slice, svbool_t pg, void * ptr, int64_t vnum)
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
    "ZA array tile": "ZA0V.D"
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
ST1D {ZA0V.D[Wreg1, imm1]}, Preg1, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/ST1D--scalar-plus-scalar--tile-slice---Contiguous-store-of-doublewords-from-64-bit-element-ZA-tile-slice-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svst1_ver_vnum_za8

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst1_ver_vnum_za8

### Signature (source notation)

```c
void svst1_ver_vnum_za8(uint64_t tile, uint32_t slice, svbool_t pg, void * ptr, int64_t vnum)
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
    "ZA array tile": "ZA0V.B"
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
ST1B {ZA0V.B[Wreg1, imm1]}, Preg1, [Xreg1, Xreg2]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/ST1B--scalar-plus-scalar--tile-slice---Contiguous-store-of-bytes-from-8-bit-element-ZA-tile-slice-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svst1_ver_za128

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst1_ver_za128

### Signature (source notation)

```c
void svst1_ver_za128(uint64_t tile, uint32_t slice, svbool_t pg, void * ptr)
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
ST1Q {ZA0V.Q[Wreg1, imm1]}, Preg1, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/ST1Q--Contiguous-store-of-quadwords-from-128-bit-element-ZA-tile-slice-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svst1_ver_za16

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst1_ver_za16

### Signature (source notation)

```c
void svst1_ver_za16(uint64_t tile, uint32_t slice, svbool_t pg, void * ptr)
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
    "ZA array tile": "ZA0V.H"
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
ST1H {ZA0V.H[Wreg1, imm1]}, Preg1, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/ST1H--scalar-plus-scalar--tile-slice---Contiguous-store-of-halfwords-from-16-bit-element-ZA-tile-slice-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svst1_ver_za32

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst1_ver_za32

### Signature (source notation)

```c
void svst1_ver_za32(uint64_t tile, uint32_t slice, svbool_t pg, void * ptr)
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
    "ZA array tile": "ZA0V.S"
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
ST1W {ZA0V.S[Wreg1, imm1]}, Preg1, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/ST1W--scalar-plus-scalar--tile-slice---Contiguous-store-of-words-from-32-bit-element-ZA-tile-slice-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svst1_ver_za64

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst1_ver_za64

### Signature (source notation)

```c
void svst1_ver_za64(uint64_t tile, uint32_t slice, svbool_t pg, void * ptr)
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
    "ZA array tile": "ZA0V.D"
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
ST1D {ZA0V.D[Wreg1, imm1]}, Preg1, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/ST1D--scalar-plus-scalar--tile-slice---Contiguous-store-of-doublewords-from-64-bit-element-ZA-tile-slice-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svst1_ver_za8

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst1_ver_za8

### Signature (source notation)

```c
void svst1_ver_za8(uint64_t tile, uint32_t slice, svbool_t pg, void * ptr)
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
    "ZA array tile": "ZA0V.B"
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
ST1B {ZA0V.B[Wreg1, imm1]}, Preg1, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/ST1B--scalar-plus-scalar--tile-slice---Contiguous-store-of-bytes-from-8-bit-element-ZA-tile-slice-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svst1_vnum[_bf16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst1_vnum%5B_bf16%5D

### Signature (source notation)

```c
void svst1_vnum[_bf16](svbool_t pg, bfloat16_t *base, int64_t vnum, svbfloat16_t data);
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
    "register": "Zdata.H"
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

When vnum is in the range [-8, 7], this intrinsic can use:

```asm
ST1H Zdata.H, Pg, [Xbase, #vnum, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST1H--scalar-plus-immediate--consecutive-registers---Contiguous-store-of-halfwords-from-multiple-consecutive-vectors--immediate-index--

The general implementation is:

```asm
ST1H Zdata.H, Pg, [Xbase, Xindex, LSL #1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST1H--scalar-plus-scalar--consecutive-registers---Contiguous-store-of-halfwords-from-multiple-consecutive-vectors--scalar-index--

### Operation

Source operation ID: `SveOperation_svst1_vnum_bf16`

**Operation**



For each active element *i*, store `data[i]` to `base[n * vnum + i]`, where *n* is the number of elements in `data`. Do not access memory for inactive elements.

## svst1_vnum[_bf16_x2]

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst1_vnum%5B_bf16_x2%5D

### Signature (source notation)

```c
void svst1_vnum[_bf16_x2](svcount_t png, bfloat16_t * rn, int64_t vnum, svbfloat16x2_t zt);
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
    "register": "Xreg2"
  },
  "vnum": {
    "register": "Xreg3"
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
RDVL Xreg1, #1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/RDVL--Read-multiple-of-vector-register-size-to-scalar-register-

```asm
MADD Xreg1, Xreg1, Xreg3, Xreg2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/Base-Instructions/MADD--Multiply-add-

```asm
ST1H { Zreg1.H, Zreg2.H }, PNreg1, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST1H--scalar-plus-immediate--consecutive-registers---Contiguous-store-of-halfwords-from-multiple-consecutive-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svst1_vnum[_bf16_x4]

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst1_vnum%5B_bf16_x4%5D

### Signature (source notation)

```c
void svst1_vnum[_bf16_x4](svcount_t png, bfloat16_t * rn, int64_t vnum, svbfloat16x4_t zt);
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
    "register": "Xreg2"
  },
  "vnum": {
    "register": "Xreg3"
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
RDVL Xreg1, #1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/RDVL--Read-multiple-of-vector-register-size-to-scalar-register-

```asm
MADD Xreg1, Xreg1, Xreg3, Xreg2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/Base-Instructions/MADD--Multiply-add-

```asm
ST1H { Zreg1.H - Zreg2.H }, PNreg1, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST1H--scalar-plus-immediate--consecutive-registers---Contiguous-store-of-halfwords-from-multiple-consecutive-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svst1_vnum[_f16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst1_vnum%5B_f16%5D

### Signature (source notation)

```c
void svst1_vnum[_f16](svbool_t pg, float16_t *base, int64_t vnum, svfloat16_t data);
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
    "register": "Zdata.H"
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

When vnum is in the range [-8, 7], this intrinsic can use:

```asm
ST1H Zdata.H, Pg, [Xbase, #vnum, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST1H--scalar-plus-immediate--consecutive-registers---Contiguous-store-of-halfwords-from-multiple-consecutive-vectors--immediate-index--

The general implementation is:

```asm
ST1H Zdata.H, Pg, [Xbase, Xindex, LSL #1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST1H--scalar-plus-scalar--consecutive-registers---Contiguous-store-of-halfwords-from-multiple-consecutive-vectors--scalar-index--

### Operation

Source operation ID: `SveOperation_svst1_vnum_bf16`

**Operation**



For each active element *i*, store `data[i]` to `base[n * vnum + i]`, where *n* is the number of elements in `data`. Do not access memory for inactive elements.

## svst1_vnum[_f16_x2]

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst1_vnum%5B_f16_x2%5D

### Signature (source notation)

```c
void svst1_vnum[_f16_x2](svcount_t png, float16_t * rn, int64_t vnum, svfloat16x2_t zt);
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
    "register": "Xreg2"
  },
  "vnum": {
    "register": "Xreg3"
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
RDVL Xreg1, #1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/RDVL--Read-multiple-of-vector-register-size-to-scalar-register-

```asm
MADD Xreg1, Xreg1, Xreg3, Xreg2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/Base-Instructions/MADD--Multiply-add-

```asm
ST1H { Zreg1.H, Zreg2.H }, PNreg1, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST1H--scalar-plus-immediate--consecutive-registers---Contiguous-store-of-halfwords-from-multiple-consecutive-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svst1_vnum[_f16_x4]

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst1_vnum%5B_f16_x4%5D

### Signature (source notation)

```c
void svst1_vnum[_f16_x4](svcount_t png, float16_t * rn, int64_t vnum, svfloat16x4_t zt);
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
    "register": "Xreg2"
  },
  "vnum": {
    "register": "Xreg3"
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
RDVL Xreg1, #1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/RDVL--Read-multiple-of-vector-register-size-to-scalar-register-

```asm
MADD Xreg1, Xreg1, Xreg3, Xreg2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/Base-Instructions/MADD--Multiply-add-

```asm
ST1H { Zreg1.H - Zreg2.H }, PNreg1, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST1H--scalar-plus-immediate--consecutive-registers---Contiguous-store-of-halfwords-from-multiple-consecutive-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svst1_vnum[_f32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst1_vnum%5B_f32%5D

### Signature (source notation)

```c
void svst1_vnum[_f32](svbool_t pg, float32_t *base, int64_t vnum, svfloat32_t data);
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
    "register": "Zdata.S"
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

When vnum is in the range [-8, 7], this intrinsic can use:

```asm
ST1W Zdata.S, Pg, [Xbase, #vnum, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST1W--scalar-plus-immediate--consecutive-registers---Contiguous-store-of-words-from-multiple-consecutive-vectors--immediate-index--

The general implementation is:

```asm
ST1W Zdata.S, Pg, [Xbase, Xindex, LSL #2]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST1W--scalar-plus-scalar--consecutive-registers---Contiguous-store-of-words-from-multiple-consecutive-vectors--scalar-index--

### Operation

Source operation ID: `SveOperation_svst1_vnum_bf16`

**Operation**



For each active element *i*, store `data[i]` to `base[n * vnum + i]`, where *n* is the number of elements in `data`. Do not access memory for inactive elements.

## svst1_vnum[_f32_x2]

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst1_vnum%5B_f32_x2%5D

### Signature (source notation)

```c
void svst1_vnum[_f32_x2](svcount_t png, float32_t * rn, int64_t vnum, svfloat32x2_t zt);
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
    "register": "Xreg2"
  },
  "vnum": {
    "register": "Xreg3"
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
RDVL Xreg1, #1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/RDVL--Read-multiple-of-vector-register-size-to-scalar-register-

```asm
MADD Xreg1, Xreg1, Xreg3, Xreg2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/Base-Instructions/MADD--Multiply-add-

```asm
ST1W { Zreg1.S, Zreg2.S }, PNreg1, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST1W--scalar-plus-immediate--consecutive-registers---Contiguous-store-of-words-from-multiple-consecutive-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svst1_vnum[_f32_x4]

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst1_vnum%5B_f32_x4%5D

### Signature (source notation)

```c
void svst1_vnum[_f32_x4](svcount_t png, float32_t * rn, int64_t vnum, svfloat32x4_t zt);
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
    "register": "Xreg2"
  },
  "vnum": {
    "register": "Xreg3"
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
RDVL Xreg1, #1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/RDVL--Read-multiple-of-vector-register-size-to-scalar-register-

```asm
MADD Xreg1, Xreg1, Xreg3, Xreg2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/Base-Instructions/MADD--Multiply-add-

```asm
ST1W { Zreg1.S - Zreg2.S }, PNreg1, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST1W--scalar-plus-immediate--consecutive-registers---Contiguous-store-of-words-from-multiple-consecutive-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svst1_vnum[_f64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst1_vnum%5B_f64%5D

### Signature (source notation)

```c
void svst1_vnum[_f64](svbool_t pg, float64_t *base, int64_t vnum, svfloat64_t data);
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

When vnum is in the range [-8, 7], this intrinsic can use:

```asm
ST1D Zdata.D, Pg, [Xbase, #vnum, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST1D--scalar-plus-immediate--consecutive-registers---Contiguous-store-of-doublewords-from-multiple-consecutive-vectors--immediate-index--

The general implementation is:

```asm
ST1D Zdata.D, Pg, [Xbase, Xindex, LSL #3]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST1D--scalar-plus-scalar--consecutive-registers---Contiguous-store-of-doublewords-from-multiple-consecutive-vectors--scalar-index--

### Operation

Source operation ID: `SveOperation_svst1_vnum_bf16`

**Operation**



For each active element *i*, store `data[i]` to `base[n * vnum + i]`, where *n* is the number of elements in `data`. Do not access memory for inactive elements.

## svst1_vnum[_f64_x2]

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst1_vnum%5B_f64_x2%5D

### Signature (source notation)

```c
void svst1_vnum[_f64_x2](svcount_t png, float64_t * rn, int64_t vnum, svfloat64x2_t zt);
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
    "register": "Xreg2"
  },
  "vnum": {
    "register": "Xreg3"
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
RDVL Xreg1, #1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/RDVL--Read-multiple-of-vector-register-size-to-scalar-register-

```asm
MADD Xreg1, Xreg1, Xreg3, Xreg2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/Base-Instructions/MADD--Multiply-add-

```asm
ST1D { Zreg1.D, Zreg2.D }, PNreg1, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST1D--scalar-plus-immediate--consecutive-registers---Contiguous-store-of-doublewords-from-multiple-consecutive-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svst1_vnum[_f64_x4]

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst1_vnum%5B_f64_x4%5D

### Signature (source notation)

```c
void svst1_vnum[_f64_x4](svcount_t png, float64_t * rn, int64_t vnum, svfloat64x4_t zt);
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
    "register": "Xreg2"
  },
  "vnum": {
    "register": "Xreg3"
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
RDVL Xreg1, #1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/RDVL--Read-multiple-of-vector-register-size-to-scalar-register-

```asm
MADD Xreg1, Xreg1, Xreg3, Xreg2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/Base-Instructions/MADD--Multiply-add-

```asm
ST1D { Zreg1.D - Zreg2.D }, PNreg1, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST1D--scalar-plus-immediate--consecutive-registers---Contiguous-store-of-doublewords-from-multiple-consecutive-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svst1_vnum[_mf8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst1_vnum%5B_mf8%5D

### Signature (source notation)

```c
void svst1_vnum[_mf8](svbool_t pg, mfloat8_t *base, int64_t vnum, svmfloat8_t data);
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

When vnum is in the range [-8, 7], this intrinsic can use:

```asm
ST1B Zdata.B, Pg, [Xbase, #vnum, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST1B--scalar-plus-immediate--consecutive-registers---Contiguous-store-of-bytes-from-multiple-consecutive-vectors--immediate-index--

The general implementation is:

```asm
ST1B Zdata.B, Pg, [Xbase, Xindex]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST1B--scalar-plus-scalar--consecutive-registers---Contiguous-store-of-bytes-from-multiple-consecutive-vectors--scalar-index--

### Operation

Source operation ID: `SveOperation_svst1_vnum_bf16`

**Operation**



For each active element *i*, store `data[i]` to `base[n * vnum + i]`, where *n* is the number of elements in `data`. Do not access memory for inactive elements.

## svst1_vnum[_mf8_x2]

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst1_vnum%5B_mf8_x2%5D

### Signature (source notation)

```c
void svst1_vnum[_mf8_x2](svcount_t png, mfloat8_t * rn, int64_t vnum, svmfloat8x2_t zt);
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

## svst1_vnum[_mf8_x4]

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst1_vnum%5B_mf8_x4%5D

### Signature (source notation)

```c
void svst1_vnum[_mf8_x4](svcount_t png, mfloat8_t * rn, int64_t vnum, svmfloat8x4_t zt);
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

## svst1_vnum[_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst1_vnum%5B_s16%5D

### Signature (source notation)

```c
void svst1_vnum[_s16](svbool_t pg, int16_t *base, int64_t vnum, svint16_t data);
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
    "register": "Zdata.H"
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

When vnum is in the range [-8, 7], this intrinsic can use:

```asm
ST1H Zdata.H, Pg, [Xbase, #vnum, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST1H--scalar-plus-immediate--consecutive-registers---Contiguous-store-of-halfwords-from-multiple-consecutive-vectors--immediate-index--

The general implementation is:

```asm
ST1H Zdata.H, Pg, [Xbase, Xindex, LSL #1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST1H--scalar-plus-scalar--consecutive-registers---Contiguous-store-of-halfwords-from-multiple-consecutive-vectors--scalar-index--

### Operation

Source operation ID: `SveOperation_svst1_vnum_bf16`

**Operation**



For each active element *i*, store `data[i]` to `base[n * vnum + i]`, where *n* is the number of elements in `data`. Do not access memory for inactive elements.

## svst1_vnum[_s16_x2]

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst1_vnum%5B_s16_x2%5D

### Signature (source notation)

```c
void svst1_vnum[_s16_x2](svcount_t png, int16_t * rn, int64_t vnum, svint16x2_t zt);
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
    "register": "Xreg2"
  },
  "vnum": {
    "register": "Xreg3"
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
RDVL Xreg1, #1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/RDVL--Read-multiple-of-vector-register-size-to-scalar-register-

```asm
MADD Xreg1, Xreg1, Xreg3, Xreg2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/Base-Instructions/MADD--Multiply-add-

```asm
ST1H { Zreg1.H, Zreg2.H }, PNreg1, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST1H--scalar-plus-immediate--consecutive-registers---Contiguous-store-of-halfwords-from-multiple-consecutive-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svst1_vnum[_s16_x4]

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst1_vnum%5B_s16_x4%5D

### Signature (source notation)

```c
void svst1_vnum[_s16_x4](svcount_t png, int16_t * rn, int64_t vnum, svint16x4_t zt);
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
    "register": "Xreg2"
  },
  "vnum": {
    "register": "Xreg3"
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
RDVL Xreg1, #1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/RDVL--Read-multiple-of-vector-register-size-to-scalar-register-

```asm
MADD Xreg1, Xreg1, Xreg3, Xreg2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/Base-Instructions/MADD--Multiply-add-

```asm
ST1H { Zreg1.H - Zreg2.H }, PNreg1, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST1H--scalar-plus-immediate--consecutive-registers---Contiguous-store-of-halfwords-from-multiple-consecutive-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svst1_vnum[_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst1_vnum%5B_s32%5D

### Signature (source notation)

```c
void svst1_vnum[_s32](svbool_t pg, int32_t *base, int64_t vnum, svint32_t data);
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
    "register": "Zdata.S"
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

When vnum is in the range [-8, 7], this intrinsic can use:

```asm
ST1W Zdata.S, Pg, [Xbase, #vnum, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST1W--scalar-plus-immediate--consecutive-registers---Contiguous-store-of-words-from-multiple-consecutive-vectors--immediate-index--

The general implementation is:

```asm
ST1W Zdata.S, Pg, [Xbase, Xindex, LSL #2]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST1W--scalar-plus-scalar--consecutive-registers---Contiguous-store-of-words-from-multiple-consecutive-vectors--scalar-index--

### Operation

Source operation ID: `SveOperation_svst1_vnum_bf16`

**Operation**



For each active element *i*, store `data[i]` to `base[n * vnum + i]`, where *n* is the number of elements in `data`. Do not access memory for inactive elements.

## svst1_vnum[_s32_x2]

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst1_vnum%5B_s32_x2%5D

### Signature (source notation)

```c
void svst1_vnum[_s32_x2](svcount_t png, int32_t * rn, int64_t vnum, svint32x2_t zt);
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
    "register": "Xreg2"
  },
  "vnum": {
    "register": "Xreg3"
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
RDVL Xreg1, #1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/RDVL--Read-multiple-of-vector-register-size-to-scalar-register-

```asm
MADD Xreg1, Xreg1, Xreg3, Xreg2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/Base-Instructions/MADD--Multiply-add-

```asm
ST1W { Zreg1.S, Zreg2.S }, PNreg1, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST1W--scalar-plus-immediate--consecutive-registers---Contiguous-store-of-words-from-multiple-consecutive-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svst1_vnum[_s32_x4]

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst1_vnum%5B_s32_x4%5D

### Signature (source notation)

```c
void svst1_vnum[_s32_x4](svcount_t png, int32_t * rn, int64_t vnum, svint32x4_t zt);
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
    "register": "Xreg2"
  },
  "vnum": {
    "register": "Xreg3"
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
RDVL Xreg1, #1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/RDVL--Read-multiple-of-vector-register-size-to-scalar-register-

```asm
MADD Xreg1, Xreg1, Xreg3, Xreg2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/Base-Instructions/MADD--Multiply-add-

```asm
ST1W { Zreg1.S - Zreg2.S }, PNreg1, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST1W--scalar-plus-immediate--consecutive-registers---Contiguous-store-of-words-from-multiple-consecutive-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svst1_vnum[_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst1_vnum%5B_s64%5D

### Signature (source notation)

```c
void svst1_vnum[_s64](svbool_t pg, int64_t *base, int64_t vnum, svint64_t data);
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

When vnum is in the range [-8, 7], this intrinsic can use:

```asm
ST1D Zdata.D, Pg, [Xbase, #vnum, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST1D--scalar-plus-immediate--consecutive-registers---Contiguous-store-of-doublewords-from-multiple-consecutive-vectors--immediate-index--

The general implementation is:

```asm
ST1D Zdata.D, Pg, [Xbase, Xindex, LSL #3]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST1D--scalar-plus-scalar--consecutive-registers---Contiguous-store-of-doublewords-from-multiple-consecutive-vectors--scalar-index--

### Operation

Source operation ID: `SveOperation_svst1_vnum_bf16`

**Operation**



For each active element *i*, store `data[i]` to `base[n * vnum + i]`, where *n* is the number of elements in `data`. Do not access memory for inactive elements.

## svst1_vnum[_s64_x2]

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst1_vnum%5B_s64_x2%5D

### Signature (source notation)

```c
void svst1_vnum[_s64_x2](svcount_t png, int64_t * rn, int64_t vnum, svint64x2_t zt);
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
    "register": "Xreg2"
  },
  "vnum": {
    "register": "Xreg3"
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
RDVL Xreg1, #1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/RDVL--Read-multiple-of-vector-register-size-to-scalar-register-

```asm
MADD Xreg1, Xreg1, Xreg3, Xreg2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/Base-Instructions/MADD--Multiply-add-

```asm
ST1D { Zreg1.D, Zreg2.D }, PNreg1, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST1D--scalar-plus-immediate--consecutive-registers---Contiguous-store-of-doublewords-from-multiple-consecutive-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svst1_vnum[_s64_x4]

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst1_vnum%5B_s64_x4%5D

### Signature (source notation)

```c
void svst1_vnum[_s64_x4](svcount_t png, int64_t * rn, int64_t vnum, svint64x4_t zt);
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
    "register": "Xreg2"
  },
  "vnum": {
    "register": "Xreg3"
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
RDVL Xreg1, #1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/RDVL--Read-multiple-of-vector-register-size-to-scalar-register-

```asm
MADD Xreg1, Xreg1, Xreg3, Xreg2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/Base-Instructions/MADD--Multiply-add-

```asm
ST1D { Zreg1.D - Zreg2.D }, PNreg1, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST1D--scalar-plus-immediate--consecutive-registers---Contiguous-store-of-doublewords-from-multiple-consecutive-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svst1_vnum[_s8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst1_vnum%5B_s8%5D

### Signature (source notation)

```c
void svst1_vnum[_s8](svbool_t pg, int8_t *base, int64_t vnum, svint8_t data);
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
    "register": "Zdata.B"
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

When vnum is in the range [-8, 7], this intrinsic can use:

```asm
ST1B Zdata.B, Pg, [Xbase, #vnum, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST1B--scalar-plus-immediate--consecutive-registers---Contiguous-store-of-bytes-from-multiple-consecutive-vectors--immediate-index--

The general implementation is:

```asm
ST1B Zdata.B, Pg, [Xbase, Xindex]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST1B--scalar-plus-scalar--consecutive-registers---Contiguous-store-of-bytes-from-multiple-consecutive-vectors--scalar-index--

### Operation

Source operation ID: `SveOperation_svst1_vnum_bf16`

**Operation**



For each active element *i*, store `data[i]` to `base[n * vnum + i]`, where *n* is the number of elements in `data`. Do not access memory for inactive elements.

## svst1_vnum[_s8_x2]

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst1_vnum%5B_s8_x2%5D

### Signature (source notation)

```c
void svst1_vnum[_s8_x2](svcount_t png, int8_t * rn, int64_t vnum, svint8x2_t zt);
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

## svst1_vnum[_s8_x4]

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst1_vnum%5B_s8_x4%5D

### Signature (source notation)

```c
void svst1_vnum[_s8_x4](svcount_t png, int8_t * rn, int64_t vnum, svint8x4_t zt);
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

## svst1_vnum[_u16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst1_vnum%5B_u16%5D

### Signature (source notation)

```c
void svst1_vnum[_u16](svbool_t pg, uint16_t *base, int64_t vnum, svuint16_t data);
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
    "register": "Zdata.H"
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

When vnum is in the range [-8, 7], this intrinsic can use:

```asm
ST1H Zdata.H, Pg, [Xbase, #vnum, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST1H--scalar-plus-immediate--consecutive-registers---Contiguous-store-of-halfwords-from-multiple-consecutive-vectors--immediate-index--

The general implementation is:

```asm
ST1H Zdata.H, Pg, [Xbase, Xindex, LSL #1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST1H--scalar-plus-scalar--consecutive-registers---Contiguous-store-of-halfwords-from-multiple-consecutive-vectors--scalar-index--

### Operation

Source operation ID: `SveOperation_svst1_vnum_bf16`

**Operation**



For each active element *i*, store `data[i]` to `base[n * vnum + i]`, where *n* is the number of elements in `data`. Do not access memory for inactive elements.

## svst1_vnum[_u16_x2]

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst1_vnum%5B_u16_x2%5D

### Signature (source notation)

```c
void svst1_vnum[_u16_x2](svcount_t png, uint16_t * rn, int64_t vnum, svuint16x2_t zt);
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
    "register": "Xreg2"
  },
  "vnum": {
    "register": "Xreg3"
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
RDVL Xreg1, #1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/RDVL--Read-multiple-of-vector-register-size-to-scalar-register-

```asm
MADD Xreg1, Xreg1, Xreg3, Xreg2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/Base-Instructions/MADD--Multiply-add-

```asm
ST1H { Zreg1.H, Zreg2.H }, PNreg1, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST1H--scalar-plus-immediate--consecutive-registers---Contiguous-store-of-halfwords-from-multiple-consecutive-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svst1_vnum[_u16_x4]

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst1_vnum%5B_u16_x4%5D

### Signature (source notation)

```c
void svst1_vnum[_u16_x4](svcount_t png, uint16_t * rn, int64_t vnum, svuint16x4_t zt);
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
    "register": "Xreg2"
  },
  "vnum": {
    "register": "Xreg3"
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
RDVL Xreg1, #1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/RDVL--Read-multiple-of-vector-register-size-to-scalar-register-

```asm
MADD Xreg1, Xreg1, Xreg3, Xreg2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/Base-Instructions/MADD--Multiply-add-

```asm
ST1H { Zreg1.H - Zreg2.H }, PNreg1, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST1H--scalar-plus-immediate--consecutive-registers---Contiguous-store-of-halfwords-from-multiple-consecutive-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svst1_vnum[_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst1_vnum%5B_u32%5D

### Signature (source notation)

```c
void svst1_vnum[_u32](svbool_t pg, uint32_t *base, int64_t vnum, svuint32_t data);
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
    "register": "Zdata.S"
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

When vnum is in the range [-8, 7], this intrinsic can use:

```asm
ST1W Zdata.S, Pg, [Xbase, #vnum, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST1W--scalar-plus-immediate--consecutive-registers---Contiguous-store-of-words-from-multiple-consecutive-vectors--immediate-index--

The general implementation is:

```asm
ST1W Zdata.S, Pg, [Xbase, Xindex, LSL #2]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST1W--scalar-plus-scalar--consecutive-registers---Contiguous-store-of-words-from-multiple-consecutive-vectors--scalar-index--

### Operation

Source operation ID: `SveOperation_svst1_vnum_bf16`

**Operation**



For each active element *i*, store `data[i]` to `base[n * vnum + i]`, where *n* is the number of elements in `data`. Do not access memory for inactive elements.

## svst1_vnum[_u32_x2]

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst1_vnum%5B_u32_x2%5D

### Signature (source notation)

```c
void svst1_vnum[_u32_x2](svcount_t png, uint32_t * rn, int64_t vnum, svuint32x2_t zt);
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
    "register": "Xreg2"
  },
  "vnum": {
    "register": "Xreg3"
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
RDVL Xreg1, #1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/RDVL--Read-multiple-of-vector-register-size-to-scalar-register-

```asm
MADD Xreg1, Xreg1, Xreg3, Xreg2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/Base-Instructions/MADD--Multiply-add-

```asm
ST1W { Zreg1.S, Zreg2.S }, PNreg1, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST1W--scalar-plus-immediate--consecutive-registers---Contiguous-store-of-words-from-multiple-consecutive-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svst1_vnum[_u32_x4]

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst1_vnum%5B_u32_x4%5D

### Signature (source notation)

```c
void svst1_vnum[_u32_x4](svcount_t png, uint32_t * rn, int64_t vnum, svuint32x4_t zt);
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
    "register": "Xreg2"
  },
  "vnum": {
    "register": "Xreg3"
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
RDVL Xreg1, #1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/RDVL--Read-multiple-of-vector-register-size-to-scalar-register-

```asm
MADD Xreg1, Xreg1, Xreg3, Xreg2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/Base-Instructions/MADD--Multiply-add-

```asm
ST1W { Zreg1.S - Zreg2.S }, PNreg1, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST1W--scalar-plus-immediate--consecutive-registers---Contiguous-store-of-words-from-multiple-consecutive-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svst1_vnum[_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst1_vnum%5B_u64%5D

### Signature (source notation)

```c
void svst1_vnum[_u64](svbool_t pg, uint64_t *base, int64_t vnum, svuint64_t data);
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

When vnum is in the range [-8, 7], this intrinsic can use:

```asm
ST1D Zdata.D, Pg, [Xbase, #vnum, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST1D--scalar-plus-immediate--consecutive-registers---Contiguous-store-of-doublewords-from-multiple-consecutive-vectors--immediate-index--

The general implementation is:

```asm
ST1D Zdata.D, Pg, [Xbase, Xindex, LSL #3]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST1D--scalar-plus-scalar--consecutive-registers---Contiguous-store-of-doublewords-from-multiple-consecutive-vectors--scalar-index--

### Operation

Source operation ID: `SveOperation_svst1_vnum_bf16`

**Operation**



For each active element *i*, store `data[i]` to `base[n * vnum + i]`, where *n* is the number of elements in `data`. Do not access memory for inactive elements.

## svst1_vnum[_u64_x2]

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst1_vnum%5B_u64_x2%5D

### Signature (source notation)

```c
void svst1_vnum[_u64_x2](svcount_t png, uint64_t * rn, int64_t vnum, svuint64x2_t zt);
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
    "register": "Xreg2"
  },
  "vnum": {
    "register": "Xreg3"
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
RDVL Xreg1, #1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/RDVL--Read-multiple-of-vector-register-size-to-scalar-register-

```asm
MADD Xreg1, Xreg1, Xreg3, Xreg2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/Base-Instructions/MADD--Multiply-add-

```asm
ST1D { Zreg1.D, Zreg2.D }, PNreg1, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST1D--scalar-plus-immediate--consecutive-registers---Contiguous-store-of-doublewords-from-multiple-consecutive-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svst1_vnum[_u64_x4]

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst1_vnum%5B_u64_x4%5D

### Signature (source notation)

```c
void svst1_vnum[_u64_x4](svcount_t png, uint64_t * rn, int64_t vnum, svuint64x4_t zt);
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
    "register": "Xreg2"
  },
  "vnum": {
    "register": "Xreg3"
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
RDVL Xreg1, #1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/RDVL--Read-multiple-of-vector-register-size-to-scalar-register-

```asm
MADD Xreg1, Xreg1, Xreg3, Xreg2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/Base-Instructions/MADD--Multiply-add-

```asm
ST1D { Zreg1.D - Zreg2.D }, PNreg1, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST1D--scalar-plus-immediate--consecutive-registers---Contiguous-store-of-doublewords-from-multiple-consecutive-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svst1_vnum[_u8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst1_vnum%5B_u8%5D

### Signature (source notation)

```c
void svst1_vnum[_u8](svbool_t pg, uint8_t *base, int64_t vnum, svuint8_t data);
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
    "register": "Zdata.B"
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

When vnum is in the range [-8, 7], this intrinsic can use:

```asm
ST1B Zdata.B, Pg, [Xbase, #vnum, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST1B--scalar-plus-immediate--consecutive-registers---Contiguous-store-of-bytes-from-multiple-consecutive-vectors--immediate-index--

The general implementation is:

```asm
ST1B Zdata.B, Pg, [Xbase, Xindex]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST1B--scalar-plus-scalar--consecutive-registers---Contiguous-store-of-bytes-from-multiple-consecutive-vectors--scalar-index--

### Operation

Source operation ID: `SveOperation_svst1_vnum_bf16`

**Operation**



For each active element *i*, store `data[i]` to `base[n * vnum + i]`, where *n* is the number of elements in `data`. Do not access memory for inactive elements.

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

## svst1b[_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst1b%5B_s16%5D

### Signature (source notation)

```c
void svst1b[_s16](svbool_t pg, int8_t *base, svint16_t data);
```

### Description

Truncate to 8 bits and store

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
ST1B Zdata.H, Pg, [Xarray, Xindex]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST1B--scalar-plus-scalar--consecutive-registers---Contiguous-store-of-bytes-from-multiple-consecutive-vectors--scalar-index--

The general implementation is:

```asm
ST1B Zdata.H, Pg, [Xbase, #0, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST1B--scalar-plus-immediate--consecutive-registers---Contiguous-store-of-bytes-from-multiple-consecutive-vectors--immediate-index--

### Operation

Source operation ID: `SveOperation_svst1b_s16`

**Operation**



For each active element *i*, truncate `data[i]` to 8 bits and store it to `base[i]`. Do not access memory for inactive elements.

## svst1b[_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svst1b%5B_s32%5D

### Signature (source notation)

```c
void svst1b[_s32](svbool_t pg, int8_t *base, svint32_t data);
```

### Description

Truncate to 8 bits and store

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
ST1B Zdata.S, Pg, [Xarray, Xindex]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST1B--scalar-plus-scalar--consecutive-registers---Contiguous-store-of-bytes-from-multiple-consecutive-vectors--scalar-index--

The general implementation is:

```asm
ST1B Zdata.S, Pg, [Xbase, #0, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ST1B--scalar-plus-immediate--consecutive-registers---Contiguous-store-of-bytes-from-multiple-consecutive-vectors--immediate-index--

### Operation

Source operation ID: `SveOperation_svst1b_s16`

**Operation**



For each active element *i*, truncate `data[i]` to 8 bits and store it to `base[i]`. Do not access memory for inactive elements.

