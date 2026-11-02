# SME2 / ZA array / Read / Vertical tile slice — Part 1

## svread_ver_za16_bf16_vg2

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svread_ver_za16_bf16_vg2

### Signature (source notation)

```c
svbfloat16x2_t svread_ver_za16_bf16_vg2(uint64_t tile, uint32_t slice)
    __arm_streaming __arm_in("za");
```

### Description

Move two ZA tile slices to two vector registers--an-alias-of-MOVA (tile to vector, two registers)

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Read / Vertical tile slice

- SME attributes: `__arm_streaming`; `__arm_in("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2
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
  "tile": {
    "ZA array tile": "ZA0V.H"
  },
  "slice": {
    "register+immediate": "Wreg1 + imm1"
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
MOV { Zreg1.H, Zreg2.H }, ZA0V.H[Wreg1, imm1:<imm1+1>]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/MOV--tile-to-vector--two-registers---Move-two-ZA-tile-slices-to-two-vector-registers--an-alias-of-MOVA--tile-to-vector--two-registers--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svread_ver_za16_bf16_vg4

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svread_ver_za16_bf16_vg4

### Signature (source notation)

```c
svbfloat16x4_t svread_ver_za16_bf16_vg4(uint64_t tile, uint32_t slice)
    __arm_streaming __arm_in("za");
```

### Description

Move four ZA tile slices to four vector registers--an-alias-of-MOVA (tile to vector, four registers)

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Read / Vertical tile slice

- SME attributes: `__arm_streaming`; `__arm_in("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2
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
  "tile": {
    "ZA array tile": "ZA0V.H"
  },
  "slice": {
    "register+immediate": "Wreg1 + imm1"
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
MOV { Zreg1.H - Zreg2.H }, ZA0V.H[Wreg1, imm1:<imm1+3>]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/MOV--tile-to-vector--four-registers---Move-four-ZA-tile-slices-to-four-vector-registers--an-alias-of-MOVA--tile-to-vector--four-registers--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svread_ver_za16_f16_vg2

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svread_ver_za16_f16_vg2

### Signature (source notation)

```c
svfloat16x2_t svread_ver_za16_f16_vg2(uint64_t tile, uint32_t slice)
    __arm_streaming __arm_in("za");
```

### Description

Move two ZA tile slices to two vector registers--an-alias-of-MOVA (tile to vector, two registers)

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Read / Vertical tile slice

- SME attributes: `__arm_streaming`; `__arm_in("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2
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
  "tile": {
    "ZA array tile": "ZA0V.H"
  },
  "slice": {
    "register+immediate": "Wreg1 + imm1"
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
MOV { Zreg1.H, Zreg2.H }, ZA0V.H[Wreg1, imm1:<imm1+1>]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/MOV--tile-to-vector--two-registers---Move-two-ZA-tile-slices-to-two-vector-registers--an-alias-of-MOVA--tile-to-vector--two-registers--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svread_ver_za16_f16_vg4

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svread_ver_za16_f16_vg4

### Signature (source notation)

```c
svfloat16x4_t svread_ver_za16_f16_vg4(uint64_t tile, uint32_t slice)
    __arm_streaming __arm_in("za");
```

### Description

Move four ZA tile slices to four vector registers--an-alias-of-MOVA (tile to vector, four registers)

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Read / Vertical tile slice

- SME attributes: `__arm_streaming`; `__arm_in("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2
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
  "tile": {
    "ZA array tile": "ZA0V.H"
  },
  "slice": {
    "register+immediate": "Wreg1 + imm1"
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
MOV { Zreg1.H - Zreg2.H }, ZA0V.H[Wreg1, imm1:<imm1+3>]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/MOV--tile-to-vector--four-registers---Move-four-ZA-tile-slices-to-four-vector-registers--an-alias-of-MOVA--tile-to-vector--four-registers--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svread_ver_za16_s16_vg2

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svread_ver_za16_s16_vg2

### Signature (source notation)

```c
svint16x2_t svread_ver_za16_s16_vg2(uint64_t tile, uint32_t slice)
    __arm_streaming __arm_in("za");
```

### Description

Move two ZA tile slices to two vector registers--an-alias-of-MOVA (tile to vector, two registers)

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Read / Vertical tile slice

- SME attributes: `__arm_streaming`; `__arm_in("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2
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
  "tile": {
    "ZA array tile": "ZA0V.H"
  },
  "slice": {
    "register+immediate": "Wreg1 + imm1"
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
MOV { Zreg1.H, Zreg2.H }, ZA0V.H[Wreg1, imm1:<imm1+1>]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/MOV--tile-to-vector--two-registers---Move-two-ZA-tile-slices-to-two-vector-registers--an-alias-of-MOVA--tile-to-vector--two-registers--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svread_ver_za16_s16_vg4

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svread_ver_za16_s16_vg4

### Signature (source notation)

```c
svint16x4_t svread_ver_za16_s16_vg4(uint64_t tile, uint32_t slice)
    __arm_streaming __arm_in("za");
```

### Description

Move four ZA tile slices to four vector registers--an-alias-of-MOVA (tile to vector, four registers)

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Read / Vertical tile slice

- SME attributes: `__arm_streaming`; `__arm_in("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2
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
  "tile": {
    "ZA array tile": "ZA0V.H"
  },
  "slice": {
    "register+immediate": "Wreg1 + imm1"
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
MOV { Zreg1.H - Zreg2.H }, ZA0V.H[Wreg1, imm1:<imm1+3>]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/MOV--tile-to-vector--four-registers---Move-four-ZA-tile-slices-to-four-vector-registers--an-alias-of-MOVA--tile-to-vector--four-registers--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svread_ver_za16_u16_vg2

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svread_ver_za16_u16_vg2

### Signature (source notation)

```c
svuint16x2_t svread_ver_za16_u16_vg2(uint64_t tile, uint32_t slice)
    __arm_streaming __arm_in("za");
```

### Description

Move two ZA tile slices to two vector registers--an-alias-of-MOVA (tile to vector, two registers)

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Read / Vertical tile slice

- SME attributes: `__arm_streaming`; `__arm_in("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2
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
  "tile": {
    "ZA array tile": "ZA0V.H"
  },
  "slice": {
    "register+immediate": "Wreg1 + imm1"
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
MOV { Zreg1.H, Zreg2.H }, ZA0V.H[Wreg1, imm1:<imm1+1>]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/MOV--tile-to-vector--two-registers---Move-two-ZA-tile-slices-to-two-vector-registers--an-alias-of-MOVA--tile-to-vector--two-registers--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svread_ver_za16_u16_vg4

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svread_ver_za16_u16_vg4

### Signature (source notation)

```c
svuint16x4_t svread_ver_za16_u16_vg4(uint64_t tile, uint32_t slice)
    __arm_streaming __arm_in("za");
```

### Description

Move four ZA tile slices to four vector registers--an-alias-of-MOVA (tile to vector, four registers)

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Read / Vertical tile slice

- SME attributes: `__arm_streaming`; `__arm_in("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2
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
  "tile": {
    "ZA array tile": "ZA0V.H"
  },
  "slice": {
    "register+immediate": "Wreg1 + imm1"
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
MOV { Zreg1.H - Zreg2.H }, ZA0V.H[Wreg1, imm1:<imm1+3>]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/MOV--tile-to-vector--four-registers---Move-four-ZA-tile-slices-to-four-vector-registers--an-alias-of-MOVA--tile-to-vector--four-registers--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svread_ver_za32_f32_vg2

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svread_ver_za32_f32_vg2

### Signature (source notation)

```c
svfloat32x2_t svread_ver_za32_f32_vg2(uint64_t tile, uint32_t slice)
    __arm_streaming __arm_in("za");
```

### Description

Move two ZA tile slices to two vector registers--an-alias-of-MOVA (tile to vector, two registers)

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Read / Vertical tile slice

- SME attributes: `__arm_streaming`; `__arm_in("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2
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
  "tile": {
    "ZA array tile": "ZA0V.S"
  },
  "slice": {
    "register+immediate": "Wreg1 + imm1"
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
MOV { Zreg1.S, Zreg2.S }, ZA0V.S[Wreg1, imm1:<imm1+1>]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/MOV--tile-to-vector--two-registers---Move-two-ZA-tile-slices-to-two-vector-registers--an-alias-of-MOVA--tile-to-vector--two-registers--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svread_ver_za32_f32_vg4

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svread_ver_za32_f32_vg4

### Signature (source notation)

```c
svfloat32x4_t svread_ver_za32_f32_vg4(uint64_t tile, uint32_t slice)
    __arm_streaming __arm_in("za");
```

### Description

Move four ZA tile slices to four vector registers--an-alias-of-MOVA (tile to vector, four registers)

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Read / Vertical tile slice

- SME attributes: `__arm_streaming`; `__arm_in("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2
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
  "tile": {
    "ZA array tile": "ZA0V.S"
  },
  "slice": {
    "register+immediate": "Wreg1 + imm1"
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
MOV { Zreg1.S - Zreg2.S }, ZA0V.S[Wreg1, imm1:<imm1+3>]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/MOV--tile-to-vector--four-registers---Move-four-ZA-tile-slices-to-four-vector-registers--an-alias-of-MOVA--tile-to-vector--four-registers--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svread_ver_za32_s32_vg2

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svread_ver_za32_s32_vg2

### Signature (source notation)

```c
svint32x2_t svread_ver_za32_s32_vg2(uint64_t tile, uint32_t slice)
    __arm_streaming __arm_in("za");
```

### Description

Move two ZA tile slices to two vector registers--an-alias-of-MOVA (tile to vector, two registers)

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Read / Vertical tile slice

- SME attributes: `__arm_streaming`; `__arm_in("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2
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
  "tile": {
    "ZA array tile": "ZA0V.S"
  },
  "slice": {
    "register+immediate": "Wreg1 + imm1"
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
MOV { Zreg1.S, Zreg2.S }, ZA0V.S[Wreg1, imm1:<imm1+1>]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/MOV--tile-to-vector--two-registers---Move-two-ZA-tile-slices-to-two-vector-registers--an-alias-of-MOVA--tile-to-vector--two-registers--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svread_ver_za32_s32_vg4

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svread_ver_za32_s32_vg4

### Signature (source notation)

```c
svint32x4_t svread_ver_za32_s32_vg4(uint64_t tile, uint32_t slice)
    __arm_streaming __arm_in("za");
```

### Description

Move four ZA tile slices to four vector registers--an-alias-of-MOVA (tile to vector, four registers)

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Read / Vertical tile slice

- SME attributes: `__arm_streaming`; `__arm_in("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2
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
  "tile": {
    "ZA array tile": "ZA0V.S"
  },
  "slice": {
    "register+immediate": "Wreg1 + imm1"
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
MOV { Zreg1.S - Zreg2.S }, ZA0V.S[Wreg1, imm1:<imm1+3>]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/MOV--tile-to-vector--four-registers---Move-four-ZA-tile-slices-to-four-vector-registers--an-alias-of-MOVA--tile-to-vector--four-registers--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svread_ver_za32_u32_vg2

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svread_ver_za32_u32_vg2

### Signature (source notation)

```c
svuint32x2_t svread_ver_za32_u32_vg2(uint64_t tile, uint32_t slice)
    __arm_streaming __arm_in("za");
```

### Description

Move two ZA tile slices to two vector registers--an-alias-of-MOVA (tile to vector, two registers)

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Read / Vertical tile slice

- SME attributes: `__arm_streaming`; `__arm_in("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2
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
  "tile": {
    "ZA array tile": "ZA0V.S"
  },
  "slice": {
    "register+immediate": "Wreg1 + imm1"
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
MOV { Zreg1.S, Zreg2.S }, ZA0V.S[Wreg1, imm1:<imm1+1>]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/MOV--tile-to-vector--two-registers---Move-two-ZA-tile-slices-to-two-vector-registers--an-alias-of-MOVA--tile-to-vector--two-registers--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svread_ver_za32_u32_vg4

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svread_ver_za32_u32_vg4

### Signature (source notation)

```c
svuint32x4_t svread_ver_za32_u32_vg4(uint64_t tile, uint32_t slice)
    __arm_streaming __arm_in("za");
```

### Description

Move four ZA tile slices to four vector registers--an-alias-of-MOVA (tile to vector, four registers)

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Read / Vertical tile slice

- SME attributes: `__arm_streaming`; `__arm_in("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2
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
  "tile": {
    "ZA array tile": "ZA0V.S"
  },
  "slice": {
    "register+immediate": "Wreg1 + imm1"
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
MOV { Zreg1.S - Zreg2.S }, ZA0V.S[Wreg1, imm1:<imm1+3>]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/MOV--tile-to-vector--four-registers---Move-four-ZA-tile-slices-to-four-vector-registers--an-alias-of-MOVA--tile-to-vector--four-registers--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svread_ver_za64_f64_vg2

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svread_ver_za64_f64_vg2

### Signature (source notation)

```c
svfloat64x2_t svread_ver_za64_f64_vg2(uint64_t tile, uint32_t slice)
    __arm_streaming __arm_in("za");
```

### Description

Move two ZA tile slices to two vector registers--an-alias-of-MOVA (tile to vector, two registers)

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Read / Vertical tile slice

- SME attributes: `__arm_streaming`; `__arm_in("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2
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
  "tile": {
    "ZA array tile": "ZA0V.D"
  },
  "slice": {
    "register+immediate": "Wreg1 + imm1"
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
MOV { Zreg1.D, Zreg2.D }, ZA0V.D[Wreg1, imm1:<imm1+1>]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/MOV--tile-to-vector--two-registers---Move-two-ZA-tile-slices-to-two-vector-registers--an-alias-of-MOVA--tile-to-vector--two-registers--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svread_ver_za64_f64_vg4

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svread_ver_za64_f64_vg4

### Signature (source notation)

```c
svfloat64x4_t svread_ver_za64_f64_vg4(uint64_t tile, uint32_t slice)
    __arm_streaming __arm_in("za");
```

### Description

Move four ZA tile slices to four vector registers--an-alias-of-MOVA (tile to vector, four registers)

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Read / Vertical tile slice

- SME attributes: `__arm_streaming`; `__arm_in("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2
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
  "tile": {
    "ZA array tile": "ZA0V.D"
  },
  "slice": {
    "register+immediate": "Wreg1 + imm1"
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
MOV { Zreg1.D - Zreg2.D }, ZA0V.D[Wreg1, imm1:<imm1+3>]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/MOV--tile-to-vector--four-registers---Move-four-ZA-tile-slices-to-four-vector-registers--an-alias-of-MOVA--tile-to-vector--four-registers--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svread_ver_za64_s64_vg2

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svread_ver_za64_s64_vg2

### Signature (source notation)

```c
svint64x2_t svread_ver_za64_s64_vg2(uint64_t tile, uint32_t slice)
    __arm_streaming __arm_in("za");
```

### Description

Move two ZA tile slices to two vector registers--an-alias-of-MOVA (tile to vector, two registers)

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Read / Vertical tile slice

- SME attributes: `__arm_streaming`; `__arm_in("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2
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
  "tile": {
    "ZA array tile": "ZA0V.D"
  },
  "slice": {
    "register+immediate": "Wreg1 + imm1"
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
MOV { Zreg1.D, Zreg2.D }, ZA0V.D[Wreg1, imm1:<imm1+1>]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/MOV--tile-to-vector--two-registers---Move-two-ZA-tile-slices-to-two-vector-registers--an-alias-of-MOVA--tile-to-vector--two-registers--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svread_ver_za64_s64_vg4

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svread_ver_za64_s64_vg4

### Signature (source notation)

```c
svint64x4_t svread_ver_za64_s64_vg4(uint64_t tile, uint32_t slice)
    __arm_streaming __arm_in("za");
```

### Description

Move four ZA tile slices to four vector registers--an-alias-of-MOVA (tile to vector, four registers)

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Read / Vertical tile slice

- SME attributes: `__arm_streaming`; `__arm_in("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2
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
  "tile": {
    "ZA array tile": "ZA0V.D"
  },
  "slice": {
    "register+immediate": "Wreg1 + imm1"
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
MOV { Zreg1.D - Zreg2.D }, ZA0V.D[Wreg1, imm1:<imm1+3>]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/MOV--tile-to-vector--four-registers---Move-four-ZA-tile-slices-to-four-vector-registers--an-alias-of-MOVA--tile-to-vector--four-registers--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svread_ver_za64_u64_vg2

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svread_ver_za64_u64_vg2

### Signature (source notation)

```c
svuint64x2_t svread_ver_za64_u64_vg2(uint64_t tile, uint32_t slice)
    __arm_streaming __arm_in("za");
```

### Description

Move two ZA tile slices to two vector registers--an-alias-of-MOVA (tile to vector, two registers)

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Read / Vertical tile slice

- SME attributes: `__arm_streaming`; `__arm_in("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2
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
  "tile": {
    "ZA array tile": "ZA0V.D"
  },
  "slice": {
    "register+immediate": "Wreg1 + imm1"
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
MOV { Zreg1.D, Zreg2.D }, ZA0V.D[Wreg1, imm1:<imm1+1>]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/MOV--tile-to-vector--two-registers---Move-two-ZA-tile-slices-to-two-vector-registers--an-alias-of-MOVA--tile-to-vector--two-registers--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svread_ver_za64_u64_vg4

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svread_ver_za64_u64_vg4

### Signature (source notation)

```c
svuint64x4_t svread_ver_za64_u64_vg4(uint64_t tile, uint32_t slice)
    __arm_streaming __arm_in("za");
```

### Description

Move four ZA tile slices to four vector registers--an-alias-of-MOVA (tile to vector, four registers)

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Read / Vertical tile slice

- SME attributes: `__arm_streaming`; `__arm_in("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2
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
  "tile": {
    "ZA array tile": "ZA0V.D"
  },
  "slice": {
    "register+immediate": "Wreg1 + imm1"
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
MOV { Zreg1.D - Zreg2.D }, ZA0V.D[Wreg1, imm1:<imm1+3>]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/MOV--tile-to-vector--four-registers---Move-four-ZA-tile-slices-to-four-vector-registers--an-alias-of-MOVA--tile-to-vector--four-registers--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svread_ver_za8_mf8_vg2

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svread_ver_za8_mf8_vg2

### Signature (source notation)

```c
svmfloat8x2_t svread_ver_za8_mf8_vg2(uint64_t tile, uint32_t slice)
    __arm_streaming __arm_in("za");
```

### Description

Move two ZA tile slices to two vector registers--an-alias-of-MOVA (tile to vector, two registers)

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Read / Vertical tile slice

- SME attributes: `__arm_streaming`; `__arm_in("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2
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
  "tile": {
    "ZA array tile": "ZA0V.B"
  },
  "slice": {
    "register+immediate": "Wreg1 + imm1"
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
MOV { Zreg1.B, Zreg2.B }, ZA0V.B[Wreg1, imm1:<imm1+1>]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/MOV--tile-to-vector--two-registers---Move-two-ZA-tile-slices-to-two-vector-registers--an-alias-of-MOVA--tile-to-vector--two-registers--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svread_ver_za8_mf8_vg4

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svread_ver_za8_mf8_vg4

### Signature (source notation)

```c
svmfloat8x4_t svread_ver_za8_mf8_vg4(uint64_t tile, uint32_t slice)
    __arm_streaming __arm_in("za");
```

### Description

Move four ZA tile slices to four vector registers--an-alias-of-MOVA (tile to vector, four registers)

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Read / Vertical tile slice

- SME attributes: `__arm_streaming`; `__arm_in("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2
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
  "tile": {
    "ZA array tile": "ZA0V.B"
  },
  "slice": {
    "register+immediate": "Wreg1 + imm1"
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
MOV { Zreg1.B - Zreg2.B }, ZA0V.B[Wreg1, imm1:<imm1+3>]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/MOV--tile-to-vector--four-registers---Move-four-ZA-tile-slices-to-four-vector-registers--an-alias-of-MOVA--tile-to-vector--four-registers--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svread_ver_za8_s8_vg2

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svread_ver_za8_s8_vg2

### Signature (source notation)

```c
svint8x2_t svread_ver_za8_s8_vg2(uint64_t tile, uint32_t slice)
    __arm_streaming __arm_in("za");
```

### Description

Move two ZA tile slices to two vector registers--an-alias-of-MOVA (tile to vector, two registers)

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Read / Vertical tile slice

- SME attributes: `__arm_streaming`; `__arm_in("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2
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
  "tile": {
    "ZA array tile": "ZA0V.B"
  },
  "slice": {
    "register+immediate": "Wreg1 + imm1"
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
MOV { Zreg1.B, Zreg2.B }, ZA0V.B[Wreg1, imm1:<imm1+1>]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/MOV--tile-to-vector--two-registers---Move-two-ZA-tile-slices-to-two-vector-registers--an-alias-of-MOVA--tile-to-vector--two-registers--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svread_ver_za8_s8_vg4

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svread_ver_za8_s8_vg4

### Signature (source notation)

```c
svint8x4_t svread_ver_za8_s8_vg4(uint64_t tile, uint32_t slice)
    __arm_streaming __arm_in("za");
```

### Description

Move four ZA tile slices to four vector registers--an-alias-of-MOVA (tile to vector, four registers)

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Read / Vertical tile slice

- SME attributes: `__arm_streaming`; `__arm_in("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2
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
  "tile": {
    "ZA array tile": "ZA0V.B"
  },
  "slice": {
    "register+immediate": "Wreg1 + imm1"
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
MOV { Zreg1.B - Zreg2.B }, ZA0V.B[Wreg1, imm1:<imm1+3>]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/MOV--tile-to-vector--four-registers---Move-four-ZA-tile-slices-to-four-vector-registers--an-alias-of-MOVA--tile-to-vector--four-registers--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svread_ver_za8_u8_vg2

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svread_ver_za8_u8_vg2

### Signature (source notation)

```c
svuint8x2_t svread_ver_za8_u8_vg2(uint64_t tile, uint32_t slice)
    __arm_streaming __arm_in("za");
```

### Description

Move two ZA tile slices to two vector registers--an-alias-of-MOVA (tile to vector, two registers)

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Read / Vertical tile slice

- SME attributes: `__arm_streaming`; `__arm_in("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2
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
  "tile": {
    "ZA array tile": "ZA0V.B"
  },
  "slice": {
    "register+immediate": "Wreg1 + imm1"
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
MOV { Zreg1.B, Zreg2.B }, ZA0V.B[Wreg1, imm1:<imm1+1>]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/MOV--tile-to-vector--two-registers---Move-two-ZA-tile-slices-to-two-vector-registers--an-alias-of-MOVA--tile-to-vector--two-registers--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svread_ver_za8_u8_vg4

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svread_ver_za8_u8_vg4

### Signature (source notation)

```c
svuint8x4_t svread_ver_za8_u8_vg4(uint64_t tile, uint32_t slice)
    __arm_streaming __arm_in("za");
```

### Description

Move four ZA tile slices to four vector registers--an-alias-of-MOVA (tile to vector, four registers)

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Read / Vertical tile slice

- SME attributes: `__arm_streaming`; `__arm_in("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2
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
  "tile": {
    "ZA array tile": "ZA0V.B"
  },
  "slice": {
    "register+immediate": "Wreg1 + imm1"
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
MOV { Zreg1.B - Zreg2.B }, ZA0V.B[Wreg1, imm1:<imm1+3>]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/MOV--tile-to-vector--four-registers---Move-four-ZA-tile-slices-to-four-vector-registers--an-alias-of-MOVA--tile-to-vector--four-registers--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svreadz_ver_za128_bf16

ISA classification: SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svreadz_ver_za128_bf16

### Signature (source notation)

```c
svbfloat16_t svreadz_ver_za128_bf16(uint64_t tile, uint32_t slice)
    __arm_streaming __arm_inout("za");
```

### Description

Move and zero ZA tile slice to Z vector

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Read / Vertical tile slice

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2p1
```

### Return type metadata

```json
{
  "return_base_type": "bfloat16",
  "element_bit_size": "16",
  "value": "svbfloat16_t"
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
  }
}
```

### Result mapping

```json
[
  {
    "Zreg1.Q": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
MOVAZ Zreg1.Q, ZA0V.Q[Wreg1, imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/MOVAZ--tile-to-vector--single---Move-and-zero-ZA-tile-slice-to-Z-vector-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svreadz_ver_za128_f16

ISA classification: SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svreadz_ver_za128_f16

### Signature (source notation)

```c
svfloat16_t svreadz_ver_za128_f16(uint64_t tile, uint32_t slice)
    __arm_streaming __arm_inout("za");
```

### Description

Move and zero ZA tile slice to Z vector

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Read / Vertical tile slice

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2p1
```

### Return type metadata

```json
{
  "return_base_type": "float16",
  "element_bit_size": "16",
  "value": "svfloat16_t"
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
  }
}
```

### Result mapping

```json
[
  {
    "Zreg1.Q": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
MOVAZ Zreg1.Q, ZA0V.Q[Wreg1, imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/MOVAZ--tile-to-vector--single---Move-and-zero-ZA-tile-slice-to-Z-vector-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svreadz_ver_za128_f32

ISA classification: SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svreadz_ver_za128_f32

### Signature (source notation)

```c
svfloat32_t svreadz_ver_za128_f32(uint64_t tile, uint32_t slice)
    __arm_streaming __arm_inout("za");
```

### Description

Move and zero ZA tile slice to Z vector

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Read / Vertical tile slice

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2p1
```

### Return type metadata

```json
{
  "return_base_type": "float32",
  "element_bit_size": "32",
  "value": "svfloat32_t"
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
  }
}
```

### Result mapping

```json
[
  {
    "Zreg1.Q": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
MOVAZ Zreg1.Q, ZA0V.Q[Wreg1, imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/MOVAZ--tile-to-vector--single---Move-and-zero-ZA-tile-slice-to-Z-vector-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svreadz_ver_za128_f64

ISA classification: SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svreadz_ver_za128_f64

### Signature (source notation)

```c
svfloat64_t svreadz_ver_za128_f64(uint64_t tile, uint32_t slice)
    __arm_streaming __arm_inout("za");
```

### Description

Move and zero ZA tile slice to Z vector

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Read / Vertical tile slice

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2p1
```

### Return type metadata

```json
{
  "return_base_type": "float64",
  "element_bit_size": "64",
  "value": "svfloat64_t"
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
  }
}
```

### Result mapping

```json
[
  {
    "Zreg1.Q": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
MOVAZ Zreg1.Q, ZA0V.Q[Wreg1, imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/MOVAZ--tile-to-vector--single---Move-and-zero-ZA-tile-slice-to-Z-vector-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svreadz_ver_za128_mf8

ISA classification: SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svreadz_ver_za128_mf8

### Signature (source notation)

```c
svmfloat8_t svreadz_ver_za128_mf8(uint64_t tile, uint32_t slice)
    __arm_streaming __arm_inout("za");
```

### Description

Move and zero ZA tile slice to Z vector

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Read / Vertical tile slice

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2p1
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
  "tile": {
    "ZA array tile": "ZA0V.Q"
  },
  "slice": {
    "register+immediate": "Wreg1 + imm1"
  }
}
```

### Result mapping

```json
[
  {
    "Zreg1.Q": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
MOVAZ Zreg1.Q, ZA0V.Q[Wreg1, imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/MOVAZ--tile-to-vector--single---Move-and-zero-ZA-tile-slice-to-Z-vector-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svreadz_ver_za128_s16

ISA classification: SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svreadz_ver_za128_s16

### Signature (source notation)

```c
svint16_t svreadz_ver_za128_s16(uint64_t tile, uint32_t slice)
    __arm_streaming __arm_inout("za");
```

### Description

Move and zero ZA tile slice to Z vector

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Read / Vertical tile slice

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2p1
```

### Return type metadata

```json
{
  "return_base_type": "int16",
  "element_bit_size": "16",
  "value": "svint16_t"
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
  }
}
```

### Result mapping

```json
[
  {
    "Zreg1.Q": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
MOVAZ Zreg1.Q, ZA0V.Q[Wreg1, imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/MOVAZ--tile-to-vector--single---Move-and-zero-ZA-tile-slice-to-Z-vector-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svreadz_ver_za128_s32

ISA classification: SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svreadz_ver_za128_s32

### Signature (source notation)

```c
svint32_t svreadz_ver_za128_s32(uint64_t tile, uint32_t slice)
    __arm_streaming __arm_inout("za");
```

### Description

Move and zero ZA tile slice to Z vector

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Read / Vertical tile slice

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2p1
```

### Return type metadata

```json
{
  "return_base_type": "int32",
  "element_bit_size": "32",
  "value": "svint32_t"
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
  }
}
```

### Result mapping

```json
[
  {
    "Zreg1.Q": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
MOVAZ Zreg1.Q, ZA0V.Q[Wreg1, imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/MOVAZ--tile-to-vector--single---Move-and-zero-ZA-tile-slice-to-Z-vector-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svreadz_ver_za128_s64

ISA classification: SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svreadz_ver_za128_s64

### Signature (source notation)

```c
svint64_t svreadz_ver_za128_s64(uint64_t tile, uint32_t slice)
    __arm_streaming __arm_inout("za");
```

### Description

Move and zero ZA tile slice to Z vector

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Read / Vertical tile slice

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2p1
```

### Return type metadata

```json
{
  "return_base_type": "int64",
  "element_bit_size": "64",
  "value": "svint64_t"
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
  }
}
```

### Result mapping

```json
[
  {
    "Zreg1.Q": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
MOVAZ Zreg1.Q, ZA0V.Q[Wreg1, imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/MOVAZ--tile-to-vector--single---Move-and-zero-ZA-tile-slice-to-Z-vector-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svreadz_ver_za128_s8

ISA classification: SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svreadz_ver_za128_s8

### Signature (source notation)

```c
svint8_t svreadz_ver_za128_s8(uint64_t tile, uint32_t slice)
    __arm_streaming __arm_inout("za");
```

### Description

Move and zero ZA tile slice to Z vector

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Read / Vertical tile slice

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2p1
```

### Return type metadata

```json
{
  "return_base_type": "int8",
  "element_bit_size": "8",
  "value": "svint8_t"
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
  }
}
```

### Result mapping

```json
[
  {
    "Zreg1.Q": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
MOVAZ Zreg1.Q, ZA0V.Q[Wreg1, imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/MOVAZ--tile-to-vector--single---Move-and-zero-ZA-tile-slice-to-Z-vector-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svreadz_ver_za128_u16

ISA classification: SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svreadz_ver_za128_u16

### Signature (source notation)

```c
svuint16_t svreadz_ver_za128_u16(uint64_t tile, uint32_t slice)
    __arm_streaming __arm_inout("za");
```

### Description

Move and zero ZA tile slice to Z vector

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Read / Vertical tile slice

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2p1
```

### Return type metadata

```json
{
  "return_base_type": "uint16",
  "element_bit_size": "16",
  "value": "svuint16_t"
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
  }
}
```

### Result mapping

```json
[
  {
    "Zreg1.Q": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
MOVAZ Zreg1.Q, ZA0V.Q[Wreg1, imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/MOVAZ--tile-to-vector--single---Move-and-zero-ZA-tile-slice-to-Z-vector-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svreadz_ver_za128_u32

ISA classification: SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svreadz_ver_za128_u32

### Signature (source notation)

```c
svuint32_t svreadz_ver_za128_u32(uint64_t tile, uint32_t slice)
    __arm_streaming __arm_inout("za");
```

### Description

Move and zero ZA tile slice to Z vector

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Read / Vertical tile slice

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2p1
```

### Return type metadata

```json
{
  "return_base_type": "uint32",
  "element_bit_size": "32",
  "value": "svuint32_t"
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
  }
}
```

### Result mapping

```json
[
  {
    "Zreg1.Q": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
MOVAZ Zreg1.Q, ZA0V.Q[Wreg1, imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/MOVAZ--tile-to-vector--single---Move-and-zero-ZA-tile-slice-to-Z-vector-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svreadz_ver_za128_u64

ISA classification: SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svreadz_ver_za128_u64

### Signature (source notation)

```c
svuint64_t svreadz_ver_za128_u64(uint64_t tile, uint32_t slice)
    __arm_streaming __arm_inout("za");
```

### Description

Move and zero ZA tile slice to Z vector

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Read / Vertical tile slice

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2p1
```

### Return type metadata

```json
{
  "return_base_type": "uint64",
  "element_bit_size": "64",
  "value": "svuint64_t"
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
  }
}
```

### Result mapping

```json
[
  {
    "Zreg1.Q": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
MOVAZ Zreg1.Q, ZA0V.Q[Wreg1, imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/MOVAZ--tile-to-vector--single---Move-and-zero-ZA-tile-slice-to-Z-vector-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svreadz_ver_za128_u8

ISA classification: SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svreadz_ver_za128_u8

### Signature (source notation)

```c
svuint8_t svreadz_ver_za128_u8(uint64_t tile, uint32_t slice)
    __arm_streaming __arm_inout("za");
```

### Description

Move and zero ZA tile slice to Z vector

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Read / Vertical tile slice

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2p1
```

### Return type metadata

```json
{
  "return_base_type": "uint8",
  "element_bit_size": "8",
  "value": "svuint8_t"
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
  }
}
```

### Result mapping

```json
[
  {
    "Zreg1.Q": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
MOVAZ Zreg1.Q, ZA0V.Q[Wreg1, imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/MOVAZ--tile-to-vector--single---Move-and-zero-ZA-tile-slice-to-Z-vector-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svreadz_ver_za16_bf16

ISA classification: SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svreadz_ver_za16_bf16

### Signature (source notation)

```c
svbfloat16_t svreadz_ver_za16_bf16(uint64_t tile, uint32_t slice)
    __arm_streaming __arm_inout("za");
```

### Description

Move and zero ZA tile slice to Z vector

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Read / Vertical tile slice

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2p1
```

### Return type metadata

```json
{
  "return_base_type": "bfloat16",
  "element_bit_size": "16",
  "value": "svbfloat16_t"
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
  }
}
```

### Result mapping

```json
[
  {
    "Zreg1.H": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
MOVAZ Zreg1.H, ZA0V.H[Wreg1, imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/MOVAZ--tile-to-vector--single---Move-and-zero-ZA-tile-slice-to-Z-vector-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svreadz_ver_za16_bf16_vg2

ISA classification: SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svreadz_ver_za16_bf16_vg2

### Signature (source notation)

```c
svbfloat16x2_t svreadz_ver_za16_bf16_vg2(uint64_t tile, uint32_t slice)
    __arm_streaming __arm_inout("za");
```

### Description

Move and zero ZA two-slice operand to Z two-vector operand

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Read / Vertical tile slice

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2p1
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
  "tile": {
    "ZA array tile": "ZA0V.H"
  },
  "slice": {
    "register+immediate": "Wreg1 + imm1"
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
MOVAZ { Zreg1.H, Zreg2.H }, ZA0V.H[Wreg1, imm1:<imm1+1>]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/MOVAZ--tile-to-vector--two-registers---Move-and-zero-ZA-two-slice-operand-to-Z-two-vector-operand-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svreadz_ver_za16_bf16_vg4

ISA classification: SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svreadz_ver_za16_bf16_vg4

### Signature (source notation)

```c
svbfloat16x4_t svreadz_ver_za16_bf16_vg4(uint64_t tile, uint32_t slice)
    __arm_streaming __arm_inout("za");
```

### Description

Move and zero ZA four-slice operand to Z four-vector operand

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Read / Vertical tile slice

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2p1
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
  "tile": {
    "ZA array tile": "ZA0V.H"
  },
  "slice": {
    "register+immediate": "Wreg1 + imm1"
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
MOVAZ { Zreg1.H - Zreg2.H }, ZA0V.H[Wreg1, imm1:<imm1+3>]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/MOVAZ--tile-to-vector--four-registers---Move-and-zero-ZA-four-slice-operand-to-Z-four-vector-operand-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svreadz_ver_za16_f16

ISA classification: SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svreadz_ver_za16_f16

### Signature (source notation)

```c
svfloat16_t svreadz_ver_za16_f16(uint64_t tile, uint32_t slice)
    __arm_streaming __arm_inout("za");
```

### Description

Move and zero ZA tile slice to Z vector

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Read / Vertical tile slice

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2p1
```

### Return type metadata

```json
{
  "return_base_type": "float16",
  "element_bit_size": "16",
  "value": "svfloat16_t"
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
  }
}
```

### Result mapping

```json
[
  {
    "Zreg1.H": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
MOVAZ Zreg1.H, ZA0V.H[Wreg1, imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/MOVAZ--tile-to-vector--single---Move-and-zero-ZA-tile-slice-to-Z-vector-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svreadz_ver_za16_f16_vg2

ISA classification: SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svreadz_ver_za16_f16_vg2

### Signature (source notation)

```c
svfloat16x2_t svreadz_ver_za16_f16_vg2(uint64_t tile, uint32_t slice)
    __arm_streaming __arm_inout("za");
```

### Description

Move and zero ZA two-slice operand to Z two-vector operand

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Read / Vertical tile slice

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2p1
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
  "tile": {
    "ZA array tile": "ZA0V.H"
  },
  "slice": {
    "register+immediate": "Wreg1 + imm1"
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
MOVAZ { Zreg1.H, Zreg2.H }, ZA0V.H[Wreg1, imm1:<imm1+1>]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/MOVAZ--tile-to-vector--two-registers---Move-and-zero-ZA-two-slice-operand-to-Z-two-vector-operand-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svreadz_ver_za16_f16_vg4

ISA classification: SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svreadz_ver_za16_f16_vg4

### Signature (source notation)

```c
svfloat16x4_t svreadz_ver_za16_f16_vg4(uint64_t tile, uint32_t slice)
    __arm_streaming __arm_inout("za");
```

### Description

Move and zero ZA four-slice operand to Z four-vector operand

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Read / Vertical tile slice

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2p1
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
  "tile": {
    "ZA array tile": "ZA0V.H"
  },
  "slice": {
    "register+immediate": "Wreg1 + imm1"
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
MOVAZ { Zreg1.H - Zreg2.H }, ZA0V.H[Wreg1, imm1:<imm1+3>]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/MOVAZ--tile-to-vector--four-registers---Move-and-zero-ZA-four-slice-operand-to-Z-four-vector-operand-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svreadz_ver_za16_s16

ISA classification: SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svreadz_ver_za16_s16

### Signature (source notation)

```c
svint16_t svreadz_ver_za16_s16(uint64_t tile, uint32_t slice)
    __arm_streaming __arm_inout("za");
```

### Description

Move and zero ZA tile slice to Z vector

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Read / Vertical tile slice

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2p1
```

### Return type metadata

```json
{
  "return_base_type": "int16",
  "element_bit_size": "16",
  "value": "svint16_t"
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
  }
}
```

### Result mapping

```json
[
  {
    "Zreg1.H": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
MOVAZ Zreg1.H, ZA0V.H[Wreg1, imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/MOVAZ--tile-to-vector--single---Move-and-zero-ZA-tile-slice-to-Z-vector-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svreadz_ver_za16_s16_vg2

ISA classification: SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svreadz_ver_za16_s16_vg2

### Signature (source notation)

```c
svint16x2_t svreadz_ver_za16_s16_vg2(uint64_t tile, uint32_t slice)
    __arm_streaming __arm_inout("za");
```

### Description

Move and zero ZA two-slice operand to Z two-vector operand

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Read / Vertical tile slice

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2p1
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
  "tile": {
    "ZA array tile": "ZA0V.H"
  },
  "slice": {
    "register+immediate": "Wreg1 + imm1"
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
MOVAZ { Zreg1.H, Zreg2.H }, ZA0V.H[Wreg1, imm1:<imm1+1>]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/MOVAZ--tile-to-vector--two-registers---Move-and-zero-ZA-two-slice-operand-to-Z-two-vector-operand-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svreadz_ver_za16_s16_vg4

ISA classification: SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svreadz_ver_za16_s16_vg4

### Signature (source notation)

```c
svint16x4_t svreadz_ver_za16_s16_vg4(uint64_t tile, uint32_t slice)
    __arm_streaming __arm_inout("za");
```

### Description

Move and zero ZA four-slice operand to Z four-vector operand

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Read / Vertical tile slice

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2p1
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
  "tile": {
    "ZA array tile": "ZA0V.H"
  },
  "slice": {
    "register+immediate": "Wreg1 + imm1"
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
MOVAZ { Zreg1.H - Zreg2.H }, ZA0V.H[Wreg1, imm1:<imm1+3>]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/MOVAZ--tile-to-vector--four-registers---Move-and-zero-ZA-four-slice-operand-to-Z-four-vector-operand-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svreadz_ver_za16_u16

ISA classification: SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svreadz_ver_za16_u16

### Signature (source notation)

```c
svuint16_t svreadz_ver_za16_u16(uint64_t tile, uint32_t slice)
    __arm_streaming __arm_inout("za");
```

### Description

Move and zero ZA tile slice to Z vector

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Read / Vertical tile slice

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2p1
```

### Return type metadata

```json
{
  "return_base_type": "uint16",
  "element_bit_size": "16",
  "value": "svuint16_t"
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
  }
}
```

### Result mapping

```json
[
  {
    "Zreg1.H": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
MOVAZ Zreg1.H, ZA0V.H[Wreg1, imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/MOVAZ--tile-to-vector--single---Move-and-zero-ZA-tile-slice-to-Z-vector-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svreadz_ver_za16_u16_vg2

ISA classification: SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svreadz_ver_za16_u16_vg2

### Signature (source notation)

```c
svuint16x2_t svreadz_ver_za16_u16_vg2(uint64_t tile, uint32_t slice)
    __arm_streaming __arm_inout("za");
```

### Description

Move and zero ZA two-slice operand to Z two-vector operand

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Read / Vertical tile slice

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2p1
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
  "tile": {
    "ZA array tile": "ZA0V.H"
  },
  "slice": {
    "register+immediate": "Wreg1 + imm1"
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
MOVAZ { Zreg1.H, Zreg2.H }, ZA0V.H[Wreg1, imm1:<imm1+1>]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/MOVAZ--tile-to-vector--two-registers---Move-and-zero-ZA-two-slice-operand-to-Z-two-vector-operand-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

