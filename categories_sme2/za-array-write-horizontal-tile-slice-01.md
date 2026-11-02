# SME2 / ZA array / Write / Horizontal tile slice — Part 1

## svwrite_hor_za16[_bf16]_vg2

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwrite_hor_za16%5B_bf16%5D_vg2

### Signature (source notation)

```c
void svwrite_hor_za16[_bf16]_vg2(uint64_t tile, uint32_t slice, svbfloat16x2_t zn)
    __arm_streaming __arm_inout("za");
```

### Description

Move two vector registers to two ZA tile slices--an-alias-of-MOVA (vector to tile, two registers)

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Write / Horizontal tile slice

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2
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
  "zn": {
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
MOV ZA0H.H[Wreg1, imm1:<imm1+1>], { Zreg1.H, Zreg2.H }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/MOV--vector-to-tile--two-registers---Move-two-vector-registers-to-two-ZA-tile-slices--an-alias-of-MOVA--vector-to-tile--two-registers--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svwrite_hor_za16[_bf16]_vg4

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwrite_hor_za16%5B_bf16%5D_vg4

### Signature (source notation)

```c
void svwrite_hor_za16[_bf16]_vg4(uint64_t tile, uint32_t slice, svbfloat16x4_t zn)
    __arm_streaming __arm_inout("za");
```

### Description

Move four vector registers to four ZA tile slices--an-alias-of-MOVA (vector to tile, four registers)

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Write / Horizontal tile slice

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2
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
  "zn": {
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
MOV ZA0H.H[Wreg1, imm1:<imm1+3>], { Zreg1.H - Zreg2.H }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/MOV--vector-to-tile--four-registers---Move-four-vector-registers-to-four-ZA-tile-slices--an-alias-of-MOVA--vector-to-tile--four-registers--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svwrite_hor_za16[_f16]_vg2

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwrite_hor_za16%5B_f16%5D_vg2

### Signature (source notation)

```c
void svwrite_hor_za16[_f16]_vg2(uint64_t tile, uint32_t slice, svfloat16x2_t zn)
    __arm_streaming __arm_inout("za");
```

### Description

Move two vector registers to two ZA tile slices--an-alias-of-MOVA (vector to tile, two registers)

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Write / Horizontal tile slice

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2
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
  "zn": {
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
MOV ZA0H.H[Wreg1, imm1:<imm1+1>], { Zreg1.H, Zreg2.H }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/MOV--vector-to-tile--two-registers---Move-two-vector-registers-to-two-ZA-tile-slices--an-alias-of-MOVA--vector-to-tile--two-registers--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svwrite_hor_za16[_f16]_vg4

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwrite_hor_za16%5B_f16%5D_vg4

### Signature (source notation)

```c
void svwrite_hor_za16[_f16]_vg4(uint64_t tile, uint32_t slice, svfloat16x4_t zn)
    __arm_streaming __arm_inout("za");
```

### Description

Move four vector registers to four ZA tile slices--an-alias-of-MOVA (vector to tile, four registers)

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Write / Horizontal tile slice

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2
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
  "zn": {
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
MOV ZA0H.H[Wreg1, imm1:<imm1+3>], { Zreg1.H - Zreg2.H }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/MOV--vector-to-tile--four-registers---Move-four-vector-registers-to-four-ZA-tile-slices--an-alias-of-MOVA--vector-to-tile--four-registers--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svwrite_hor_za16[_s16]_vg2

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwrite_hor_za16%5B_s16%5D_vg2

### Signature (source notation)

```c
void svwrite_hor_za16[_s16]_vg2(uint64_t tile, uint32_t slice, svint16x2_t zn)
    __arm_streaming __arm_inout("za");
```

### Description

Move two vector registers to two ZA tile slices--an-alias-of-MOVA (vector to tile, two registers)

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Write / Horizontal tile slice

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2
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
  "zn": {
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
MOV ZA0H.H[Wreg1, imm1:<imm1+1>], { Zreg1.H, Zreg2.H }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/MOV--vector-to-tile--two-registers---Move-two-vector-registers-to-two-ZA-tile-slices--an-alias-of-MOVA--vector-to-tile--two-registers--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svwrite_hor_za16[_s16]_vg4

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwrite_hor_za16%5B_s16%5D_vg4

### Signature (source notation)

```c
void svwrite_hor_za16[_s16]_vg4(uint64_t tile, uint32_t slice, svint16x4_t zn)
    __arm_streaming __arm_inout("za");
```

### Description

Move four vector registers to four ZA tile slices--an-alias-of-MOVA (vector to tile, four registers)

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Write / Horizontal tile slice

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2
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
  "zn": {
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
MOV ZA0H.H[Wreg1, imm1:<imm1+3>], { Zreg1.H - Zreg2.H }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/MOV--vector-to-tile--four-registers---Move-four-vector-registers-to-four-ZA-tile-slices--an-alias-of-MOVA--vector-to-tile--four-registers--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svwrite_hor_za16[_u16]_vg2

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwrite_hor_za16%5B_u16%5D_vg2

### Signature (source notation)

```c
void svwrite_hor_za16[_u16]_vg2(uint64_t tile, uint32_t slice, svuint16x2_t zn)
    __arm_streaming __arm_inout("za");
```

### Description

Move two vector registers to two ZA tile slices--an-alias-of-MOVA (vector to tile, two registers)

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Write / Horizontal tile slice

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2
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
  "zn": {
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
MOV ZA0H.H[Wreg1, imm1:<imm1+1>], { Zreg1.H, Zreg2.H }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/MOV--vector-to-tile--two-registers---Move-two-vector-registers-to-two-ZA-tile-slices--an-alias-of-MOVA--vector-to-tile--two-registers--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svwrite_hor_za16[_u16]_vg4

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwrite_hor_za16%5B_u16%5D_vg4

### Signature (source notation)

```c
void svwrite_hor_za16[_u16]_vg4(uint64_t tile, uint32_t slice, svuint16x4_t zn)
    __arm_streaming __arm_inout("za");
```

### Description

Move four vector registers to four ZA tile slices--an-alias-of-MOVA (vector to tile, four registers)

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Write / Horizontal tile slice

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2
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
  "zn": {
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
MOV ZA0H.H[Wreg1, imm1:<imm1+3>], { Zreg1.H - Zreg2.H }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/MOV--vector-to-tile--four-registers---Move-four-vector-registers-to-four-ZA-tile-slices--an-alias-of-MOVA--vector-to-tile--four-registers--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svwrite_hor_za32[_f32]_vg2

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwrite_hor_za32%5B_f32%5D_vg2

### Signature (source notation)

```c
void svwrite_hor_za32[_f32]_vg2(uint64_t tile, uint32_t slice, svfloat32x2_t zn)
    __arm_streaming __arm_inout("za");
```

### Description

Move two vector registers to two ZA tile slices--an-alias-of-MOVA (vector to tile, two registers)

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Write / Horizontal tile slice

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2
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
  "zn": {
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
MOV ZA0H.S[Wreg1, imm1:<imm1+1>], { Zreg1.S, Zreg2.S }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/MOV--vector-to-tile--two-registers---Move-two-vector-registers-to-two-ZA-tile-slices--an-alias-of-MOVA--vector-to-tile--two-registers--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svwrite_hor_za32[_f32]_vg4

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwrite_hor_za32%5B_f32%5D_vg4

### Signature (source notation)

```c
void svwrite_hor_za32[_f32]_vg4(uint64_t tile, uint32_t slice, svfloat32x4_t zn)
    __arm_streaming __arm_inout("za");
```

### Description

Move four vector registers to four ZA tile slices--an-alias-of-MOVA (vector to tile, four registers)

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Write / Horizontal tile slice

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2
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
  "zn": {
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
MOV ZA0H.S[Wreg1, imm1:<imm1+3>], { Zreg1.S - Zreg2.S }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/MOV--vector-to-tile--four-registers---Move-four-vector-registers-to-four-ZA-tile-slices--an-alias-of-MOVA--vector-to-tile--four-registers--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svwrite_hor_za32[_s32]_vg2

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwrite_hor_za32%5B_s32%5D_vg2

### Signature (source notation)

```c
void svwrite_hor_za32[_s32]_vg2(uint64_t tile, uint32_t slice, svint32x2_t zn)
    __arm_streaming __arm_inout("za");
```

### Description

Move two vector registers to two ZA tile slices--an-alias-of-MOVA (vector to tile, two registers)

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Write / Horizontal tile slice

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2
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
  "zn": {
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
MOV ZA0H.S[Wreg1, imm1:<imm1+1>], { Zreg1.S, Zreg2.S }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/MOV--vector-to-tile--two-registers---Move-two-vector-registers-to-two-ZA-tile-slices--an-alias-of-MOVA--vector-to-tile--two-registers--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svwrite_hor_za32[_s32]_vg4

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwrite_hor_za32%5B_s32%5D_vg4

### Signature (source notation)

```c
void svwrite_hor_za32[_s32]_vg4(uint64_t tile, uint32_t slice, svint32x4_t zn)
    __arm_streaming __arm_inout("za");
```

### Description

Move four vector registers to four ZA tile slices--an-alias-of-MOVA (vector to tile, four registers)

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Write / Horizontal tile slice

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2
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
  "zn": {
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
MOV ZA0H.S[Wreg1, imm1:<imm1+3>], { Zreg1.S - Zreg2.S }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/MOV--vector-to-tile--four-registers---Move-four-vector-registers-to-four-ZA-tile-slices--an-alias-of-MOVA--vector-to-tile--four-registers--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svwrite_hor_za32[_u32]_vg2

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwrite_hor_za32%5B_u32%5D_vg2

### Signature (source notation)

```c
void svwrite_hor_za32[_u32]_vg2(uint64_t tile, uint32_t slice, svuint32x2_t zn)
    __arm_streaming __arm_inout("za");
```

### Description

Move two vector registers to two ZA tile slices--an-alias-of-MOVA (vector to tile, two registers)

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Write / Horizontal tile slice

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2
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
  "zn": {
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
MOV ZA0H.S[Wreg1, imm1:<imm1+1>], { Zreg1.S, Zreg2.S }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/MOV--vector-to-tile--two-registers---Move-two-vector-registers-to-two-ZA-tile-slices--an-alias-of-MOVA--vector-to-tile--two-registers--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svwrite_hor_za32[_u32]_vg4

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwrite_hor_za32%5B_u32%5D_vg4

### Signature (source notation)

```c
void svwrite_hor_za32[_u32]_vg4(uint64_t tile, uint32_t slice, svuint32x4_t zn)
    __arm_streaming __arm_inout("za");
```

### Description

Move four vector registers to four ZA tile slices--an-alias-of-MOVA (vector to tile, four registers)

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Write / Horizontal tile slice

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2
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
  "zn": {
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
MOV ZA0H.S[Wreg1, imm1:<imm1+3>], { Zreg1.S - Zreg2.S }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/MOV--vector-to-tile--four-registers---Move-four-vector-registers-to-four-ZA-tile-slices--an-alias-of-MOVA--vector-to-tile--four-registers--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svwrite_hor_za64[_f64]_vg2

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwrite_hor_za64%5B_f64%5D_vg2

### Signature (source notation)

```c
void svwrite_hor_za64[_f64]_vg2(uint64_t tile, uint32_t slice, svfloat64x2_t zn)
    __arm_streaming __arm_inout("za");
```

### Description

Move two vector registers to two ZA tile slices--an-alias-of-MOVA (vector to tile, two registers)

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Write / Horizontal tile slice

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2
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
  "zn": {
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
MOV ZA0H.D[Wreg1, imm1:<imm1+1>], { Zreg1.D, Zreg2.D }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/MOV--vector-to-tile--two-registers---Move-two-vector-registers-to-two-ZA-tile-slices--an-alias-of-MOVA--vector-to-tile--two-registers--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svwrite_hor_za64[_f64]_vg4

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwrite_hor_za64%5B_f64%5D_vg4

### Signature (source notation)

```c
void svwrite_hor_za64[_f64]_vg4(uint64_t tile, uint32_t slice, svfloat64x4_t zn)
    __arm_streaming __arm_inout("za");
```

### Description

Move four vector registers to four ZA tile slices--an-alias-of-MOVA (vector to tile, four registers)

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Write / Horizontal tile slice

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2
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
  "zn": {
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
MOV ZA0H.D[Wreg1, imm1:<imm1+3>], { Zreg1.D - Zreg2.D }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/MOV--vector-to-tile--four-registers---Move-four-vector-registers-to-four-ZA-tile-slices--an-alias-of-MOVA--vector-to-tile--four-registers--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svwrite_hor_za64[_s64]_vg2

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwrite_hor_za64%5B_s64%5D_vg2

### Signature (source notation)

```c
void svwrite_hor_za64[_s64]_vg2(uint64_t tile, uint32_t slice, svint64x2_t zn)
    __arm_streaming __arm_inout("za");
```

### Description

Move two vector registers to two ZA tile slices--an-alias-of-MOVA (vector to tile, two registers)

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Write / Horizontal tile slice

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2
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
  "zn": {
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
MOV ZA0H.D[Wreg1, imm1:<imm1+1>], { Zreg1.D, Zreg2.D }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/MOV--vector-to-tile--two-registers---Move-two-vector-registers-to-two-ZA-tile-slices--an-alias-of-MOVA--vector-to-tile--two-registers--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svwrite_hor_za64[_s64]_vg4

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwrite_hor_za64%5B_s64%5D_vg4

### Signature (source notation)

```c
void svwrite_hor_za64[_s64]_vg4(uint64_t tile, uint32_t slice, svint64x4_t zn)
    __arm_streaming __arm_inout("za");
```

### Description

Move four vector registers to four ZA tile slices--an-alias-of-MOVA (vector to tile, four registers)

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Write / Horizontal tile slice

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2
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
  "zn": {
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
MOV ZA0H.D[Wreg1, imm1:<imm1+3>], { Zreg1.D - Zreg2.D }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/MOV--vector-to-tile--four-registers---Move-four-vector-registers-to-four-ZA-tile-slices--an-alias-of-MOVA--vector-to-tile--four-registers--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svwrite_hor_za64[_u64]_vg2

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwrite_hor_za64%5B_u64%5D_vg2

### Signature (source notation)

```c
void svwrite_hor_za64[_u64]_vg2(uint64_t tile, uint32_t slice, svuint64x2_t zn)
    __arm_streaming __arm_inout("za");
```

### Description

Move two vector registers to two ZA tile slices--an-alias-of-MOVA (vector to tile, two registers)

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Write / Horizontal tile slice

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2
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
  "zn": {
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
MOV ZA0H.D[Wreg1, imm1:<imm1+1>], { Zreg1.D, Zreg2.D }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/MOV--vector-to-tile--two-registers---Move-two-vector-registers-to-two-ZA-tile-slices--an-alias-of-MOVA--vector-to-tile--two-registers--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svwrite_hor_za64[_u64]_vg4

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwrite_hor_za64%5B_u64%5D_vg4

### Signature (source notation)

```c
void svwrite_hor_za64[_u64]_vg4(uint64_t tile, uint32_t slice, svuint64x4_t zn)
    __arm_streaming __arm_inout("za");
```

### Description

Move four vector registers to four ZA tile slices--an-alias-of-MOVA (vector to tile, four registers)

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Write / Horizontal tile slice

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2
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
  "zn": {
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
MOV ZA0H.D[Wreg1, imm1:<imm1+3>], { Zreg1.D - Zreg2.D }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/MOV--vector-to-tile--four-registers---Move-four-vector-registers-to-four-ZA-tile-slices--an-alias-of-MOVA--vector-to-tile--four-registers--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svwrite_hor_za8[_mf8]_vg2

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwrite_hor_za8%5B_mf8%5D_vg2

### Signature (source notation)

```c
void svwrite_hor_za8[_mf8]_vg2(uint64_t tile, uint32_t slice, svmfloat8x2_t zn)
    __arm_streaming __arm_inout("za");
```

### Description

Move two vector registers to two ZA tile slices--an-alias-of-MOVA (vector to tile, two registers)

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Write / Horizontal tile slice

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2
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
  "zn": {
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
MOV ZA0H.B[Wreg1, imm1:<imm1+1>], { Zreg1.B, Zreg2.B }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/MOV--vector-to-tile--two-registers---Move-two-vector-registers-to-two-ZA-tile-slices--an-alias-of-MOVA--vector-to-tile--two-registers--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svwrite_hor_za8[_mf8]_vg4

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwrite_hor_za8%5B_mf8%5D_vg4

### Signature (source notation)

```c
void svwrite_hor_za8[_mf8]_vg4(uint64_t tile, uint32_t slice, svmfloat8x4_t zn)
    __arm_streaming __arm_inout("za");
```

### Description

Move four vector registers to four ZA tile slices--an-alias-of-MOVA (vector to tile, four registers)

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Write / Horizontal tile slice

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2
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
  "zn": {
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
MOV ZA0H.B[Wreg1, imm1:<imm1+3>], { Zreg1.B - Zreg2.B }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/MOV--vector-to-tile--four-registers---Move-four-vector-registers-to-four-ZA-tile-slices--an-alias-of-MOVA--vector-to-tile--four-registers--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svwrite_hor_za8[_s8]_vg2

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwrite_hor_za8%5B_s8%5D_vg2

### Signature (source notation)

```c
void svwrite_hor_za8[_s8]_vg2(uint64_t tile, uint32_t slice, svint8x2_t zn)
    __arm_streaming __arm_inout("za");
```

### Description

Move two vector registers to two ZA tile slices--an-alias-of-MOVA (vector to tile, two registers)

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Write / Horizontal tile slice

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2
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
  "zn": {
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
MOV ZA0H.B[Wreg1, imm1:<imm1+1>], { Zreg1.B, Zreg2.B }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/MOV--vector-to-tile--two-registers---Move-two-vector-registers-to-two-ZA-tile-slices--an-alias-of-MOVA--vector-to-tile--two-registers--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svwrite_hor_za8[_s8]_vg4

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwrite_hor_za8%5B_s8%5D_vg4

### Signature (source notation)

```c
void svwrite_hor_za8[_s8]_vg4(uint64_t tile, uint32_t slice, svint8x4_t zn)
    __arm_streaming __arm_inout("za");
```

### Description

Move four vector registers to four ZA tile slices--an-alias-of-MOVA (vector to tile, four registers)

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Write / Horizontal tile slice

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2
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
  "zn": {
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
MOV ZA0H.B[Wreg1, imm1:<imm1+3>], { Zreg1.B - Zreg2.B }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/MOV--vector-to-tile--four-registers---Move-four-vector-registers-to-four-ZA-tile-slices--an-alias-of-MOVA--vector-to-tile--four-registers--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svwrite_hor_za8[_u8]_vg2

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwrite_hor_za8%5B_u8%5D_vg2

### Signature (source notation)

```c
void svwrite_hor_za8[_u8]_vg2(uint64_t tile, uint32_t slice, svuint8x2_t zn)
    __arm_streaming __arm_inout("za");
```

### Description

Move two vector registers to two ZA tile slices--an-alias-of-MOVA (vector to tile, two registers)

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Write / Horizontal tile slice

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2
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
  "zn": {
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
MOV ZA0H.B[Wreg1, imm1:<imm1+1>], { Zreg1.B, Zreg2.B }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/MOV--vector-to-tile--two-registers---Move-two-vector-registers-to-two-ZA-tile-slices--an-alias-of-MOVA--vector-to-tile--two-registers--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svwrite_hor_za8[_u8]_vg4

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwrite_hor_za8%5B_u8%5D_vg4

### Signature (source notation)

```c
void svwrite_hor_za8[_u8]_vg4(uint64_t tile, uint32_t slice, svuint8x4_t zn)
    __arm_streaming __arm_inout("za");
```

### Description

Move four vector registers to four ZA tile slices--an-alias-of-MOVA (vector to tile, four registers)

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Write / Horizontal tile slice

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2
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
  "zn": {
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
MOV ZA0H.B[Wreg1, imm1:<imm1+3>], { Zreg1.B - Zreg2.B }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/MOV--vector-to-tile--four-registers---Move-four-vector-registers-to-four-ZA-tile-slices--an-alias-of-MOVA--vector-to-tile--four-registers--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

