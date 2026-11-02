# SME / Store / Consecutive — Part 8

## svstnt1_vnum[_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svstnt1_vnum%5B_u64%5D

### Signature (source notation)

```c
void svstnt1_vnum[_u64](svbool_t pg, uint64_t *base, int64_t vnum, svuint64_t data);
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
STNT1D Zdata.D, Pg, [Xbase, #vnum, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/STNT1D--scalar-plus-immediate--consecutive-registers---Contiguous-store-non-temporal-of-doublewords-from-multiple-consecutive-vectors--immediate-index--

The general implementation is:

```asm
STNT1D Zdata.D, Pg, [Xbase, Xindex, LSL #3]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/STNT1D--scalar-plus-scalar--consecutive-registers---Contiguous-store-non-temporal-of-doublewords-from-multiple-consecutive-vectors--scalar-index--

### Operation

Source operation ID: `SveOperation_svstnt1_vnum_bf16`

**Operation**



For each active element *i*, store `data[i]` to `base[n * vnum + i]`, where *n* is the number of elements in `data`. Do not access memory for inactive elements.  Provide a hint to the system that the stored memory is unlikely to be accessed again soon.

## svstnt1_vnum[_u64_x2]

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svstnt1_vnum%5B_u64_x2%5D

### Signature (source notation)

```c
void svstnt1_vnum[_u64_x2](svcount_t png, uint64_t * rn, int64_t vnum, svuint64x2_t zt);
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
STNT1D { Zreg1.D, Zreg2.D }, PNreg1, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/STNT1D--scalar-plus-immediate--consecutive-registers---Contiguous-store-non-temporal-of-doublewords-from-multiple-consecutive-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svstnt1_vnum[_u64_x4]

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svstnt1_vnum%5B_u64_x4%5D

### Signature (source notation)

```c
void svstnt1_vnum[_u64_x4](svcount_t png, uint64_t * rn, int64_t vnum, svuint64x4_t zt);
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
STNT1D { Zreg1.D - Zreg2.D }, PNreg1, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/STNT1D--scalar-plus-immediate--consecutive-registers---Contiguous-store-non-temporal-of-doublewords-from-multiple-consecutive-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svstnt1_vnum[_u8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svstnt1_vnum%5B_u8%5D

### Signature (source notation)

```c
void svstnt1_vnum[_u8](svbool_t pg, uint8_t *base, int64_t vnum, svuint8_t data);
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
STNT1B Zdata.B, Pg, [Xbase, #vnum, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/STNT1B--scalar-plus-immediate--consecutive-registers---Contiguous-store-non-temporal-of-bytes-from-multiple-consecutive-vectors--immediate-index--

The general implementation is:

```asm
STNT1B Zdata.B, Pg, [Xbase, Xindex]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/STNT1B--scalar-plus-scalar--consecutive-registers---Contiguous-store-non-temporal-of-bytes-from-multiple-consecutive-vectors--scalar-index--

### Operation

Source operation ID: `SveOperation_svstnt1_vnum_bf16`

**Operation**



For each active element *i*, store `data[i]` to `base[n * vnum + i]`, where *n* is the number of elements in `data`. Do not access memory for inactive elements.  Provide a hint to the system that the stored memory is unlikely to be accessed again soon.

## svstnt1_vnum[_u8_x2]

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svstnt1_vnum%5B_u8_x2%5D

### Signature (source notation)

```c
void svstnt1_vnum[_u8_x2](svcount_t png, uint8_t * rn, int64_t vnum, svuint8x2_t zt);
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
STNT1B { Zreg1.B, Zreg2.B }, PNreg1, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/STNT1B--scalar-plus-immediate--consecutive-registers---Contiguous-store-non-temporal-of-bytes-from-multiple-consecutive-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svstnt1_vnum[_u8_x4]

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svstnt1_vnum%5B_u8_x4%5D

### Signature (source notation)

```c
void svstnt1_vnum[_u8_x4](svcount_t png, uint8_t * rn, int64_t vnum, svuint8x4_t zt);
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
STNT1B { Zreg1.B - Zreg2.B }, PNreg1, [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/STNT1B--scalar-plus-immediate--consecutive-registers---Contiguous-store-non-temporal-of-bytes-from-multiple-consecutive-vectors--immediate-index--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svstr_vnum_za

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svstr_vnum_za

### Signature (source notation)

```c
void svstr_vnum_za(uint32_t slice, void * ptr, int64_t vnum)
    __arm_in("za");
```

### Description

Store ZA array vector

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Store / Consecutive

- SME attributes: `__arm_in("za")`

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
  "slice": {
    "register+immediate": "Wreg2 + imm1"
  },
  "ptr": {
    "register": "Xreg3"
  },
  "vnum": {
    "registers": "Xreg1, Wreg3"
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
MADD Xreg1, Xreg2, Xreg1, Xreg3
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/Base-Instructions/MADD--Multiply-add-

```asm
STR ZA[Wreg1, imm1], [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/STR--array-vector---Store-ZA-array-vector-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svstr_za

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svstr_za

### Signature (source notation)

```c
void svstr_za(uint32_t slice, void * ptr)
    __arm_in("za");
```

### Description

Store ZA array vector

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Store / Consecutive

- SME attributes: `__arm_in("za")`

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
  "slice": {
    "register+immediate": "Wreg1 + imm1"
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
STR ZA[Wreg1, imm1], [Xreg1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/STR--array-vector---Store-ZA-array-vector-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

