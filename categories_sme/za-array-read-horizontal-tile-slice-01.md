# SME / ZA array / Read / Horizontal tile slice — Part 1

## svread_hor_za128[_bf16]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svread_hor_za128%5B_bf16%5D_m

### Signature (source notation)

```c
svbfloat16_t svread_hor_za128[_bf16]_m(svbfloat16_t zd, svbool_t pg, uint64_t tile, uint32_t slice)
    __arm_streaming __arm_in("za");
```

### Description

Move ZA tile slice to vector register--an-alias-of-MOVA (tile to vector, single)

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Read / Horizontal tile slice

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
  "return_base_type": "bfloat16",
  "element_bit_size": "16",
  "value": "svbfloat16_t"
}
```

### Argument preparation and constraints

```json
{
  "zd": {
    "register": "Zreg1.Q"
  },
  "pg": {
    "register": "Preg1"
  },
  "tile": {
    "ZA array tile": "ZA0H.Q"
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
MOV Zreg1.Q, Preg1/M, ZA0H.Q[Wreg1, imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/MOV--tile-to-vector--single---Move-ZA-tile-slice-to-vector-register--an-alias-of-MOVA--tile-to-vector--single--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svread_hor_za128[_f16]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svread_hor_za128%5B_f16%5D_m

### Signature (source notation)

```c
svfloat16_t svread_hor_za128[_f16]_m(svfloat16_t zd, svbool_t pg, uint64_t tile, uint32_t slice)
    __arm_streaming __arm_in("za");
```

### Description

Move ZA tile slice to vector register--an-alias-of-MOVA (tile to vector, single)

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Read / Horizontal tile slice

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
  "return_base_type": "float16",
  "element_bit_size": "16",
  "value": "svfloat16_t"
}
```

### Argument preparation and constraints

```json
{
  "zd": {
    "register": "Zreg1.Q"
  },
  "pg": {
    "register": "Preg1"
  },
  "tile": {
    "ZA array tile": "ZA0H.Q"
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
MOV Zreg1.Q, Preg1/M, ZA0H.Q[Wreg1, imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/MOV--tile-to-vector--single---Move-ZA-tile-slice-to-vector-register--an-alias-of-MOVA--tile-to-vector--single--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svread_hor_za128[_f32]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svread_hor_za128%5B_f32%5D_m

### Signature (source notation)

```c
svfloat32_t svread_hor_za128[_f32]_m(svfloat32_t zd, svbool_t pg, uint64_t tile, uint32_t slice)
    __arm_streaming __arm_in("za");
```

### Description

Move ZA tile slice to vector register--an-alias-of-MOVA (tile to vector, single)

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Read / Horizontal tile slice

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
  "return_base_type": "float32",
  "element_bit_size": "32",
  "value": "svfloat32_t"
}
```

### Argument preparation and constraints

```json
{
  "zd": {
    "register": "Zreg1.Q"
  },
  "pg": {
    "register": "Preg1"
  },
  "tile": {
    "ZA array tile": "ZA0H.Q"
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
MOV Zreg1.Q, Preg1/M, ZA0H.Q[Wreg1, imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/MOV--tile-to-vector--single---Move-ZA-tile-slice-to-vector-register--an-alias-of-MOVA--tile-to-vector--single--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svread_hor_za128[_f64]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svread_hor_za128%5B_f64%5D_m

### Signature (source notation)

```c
svfloat64_t svread_hor_za128[_f64]_m(svfloat64_t zd, svbool_t pg, uint64_t tile, uint32_t slice)
    __arm_streaming __arm_in("za");
```

### Description

Move ZA tile slice to vector register--an-alias-of-MOVA (tile to vector, single)

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Read / Horizontal tile slice

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
  "return_base_type": "float64",
  "element_bit_size": "64",
  "value": "svfloat64_t"
}
```

### Argument preparation and constraints

```json
{
  "zd": {
    "register": "Zreg1.Q"
  },
  "pg": {
    "register": "Preg1"
  },
  "tile": {
    "ZA array tile": "ZA0H.Q"
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
MOV Zreg1.Q, Preg1/M, ZA0H.Q[Wreg1, imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/MOV--tile-to-vector--single---Move-ZA-tile-slice-to-vector-register--an-alias-of-MOVA--tile-to-vector--single--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svread_hor_za128[_mf8]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svread_hor_za128%5B_mf8%5D_m

### Signature (source notation)

```c
svmfloat8_t svread_hor_za128[_mf8]_m(svmfloat8_t zd, svbool_t pg, uint64_t tile, uint32_t slice)
    __arm_streaming __arm_in("za");
```

### Description

Move ZA tile slice to vector register--an-alias-of-MOVA (tile to vector, single)

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Read / Horizontal tile slice

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
  "return_base_type": "mfloat8",
  "element_bit_size": "8",
  "value": "svmfloat8_t"
}
```

### Argument preparation and constraints

```json
{
  "zd": {
    "register": "Zreg1.Q"
  },
  "pg": {
    "register": "Preg1"
  },
  "tile": {
    "ZA array tile": "ZA0H.Q"
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
MOV Zreg1.Q, Preg1/M, ZA0H.Q[Wreg1, imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/MOV--tile-to-vector--single---Move-ZA-tile-slice-to-vector-register--an-alias-of-MOVA--tile-to-vector--single--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svread_hor_za128[_s16]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svread_hor_za128%5B_s16%5D_m

### Signature (source notation)

```c
svint16_t svread_hor_za128[_s16]_m(svint16_t zd, svbool_t pg, uint64_t tile, uint32_t slice)
    __arm_streaming __arm_in("za");
```

### Description

Move ZA tile slice to vector register--an-alias-of-MOVA (tile to vector, single)

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Read / Horizontal tile slice

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
  "return_base_type": "int16",
  "element_bit_size": "16",
  "value": "svint16_t"
}
```

### Argument preparation and constraints

```json
{
  "zd": {
    "register": "Zreg1.Q"
  },
  "pg": {
    "register": "Preg1"
  },
  "tile": {
    "ZA array tile": "ZA0H.Q"
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
MOV Zreg1.Q, Preg1/M, ZA0H.Q[Wreg1, imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/MOV--tile-to-vector--single---Move-ZA-tile-slice-to-vector-register--an-alias-of-MOVA--tile-to-vector--single--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svread_hor_za128[_s32]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svread_hor_za128%5B_s32%5D_m

### Signature (source notation)

```c
svint32_t svread_hor_za128[_s32]_m(svint32_t zd, svbool_t pg, uint64_t tile, uint32_t slice)
    __arm_streaming __arm_in("za");
```

### Description

Move ZA tile slice to vector register--an-alias-of-MOVA (tile to vector, single)

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Read / Horizontal tile slice

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
  "return_base_type": "int32",
  "element_bit_size": "32",
  "value": "svint32_t"
}
```

### Argument preparation and constraints

```json
{
  "zd": {
    "register": "Zreg1.Q"
  },
  "pg": {
    "register": "Preg1"
  },
  "tile": {
    "ZA array tile": "ZA0H.Q"
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
MOV Zreg1.Q, Preg1/M, ZA0H.Q[Wreg1, imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/MOV--tile-to-vector--single---Move-ZA-tile-slice-to-vector-register--an-alias-of-MOVA--tile-to-vector--single--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svread_hor_za128[_s64]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svread_hor_za128%5B_s64%5D_m

### Signature (source notation)

```c
svint64_t svread_hor_za128[_s64]_m(svint64_t zd, svbool_t pg, uint64_t tile, uint32_t slice)
    __arm_streaming __arm_in("za");
```

### Description

Move ZA tile slice to vector register--an-alias-of-MOVA (tile to vector, single)

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Read / Horizontal tile slice

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
  "return_base_type": "int64",
  "element_bit_size": "64",
  "value": "svint64_t"
}
```

### Argument preparation and constraints

```json
{
  "zd": {
    "register": "Zreg1.Q"
  },
  "pg": {
    "register": "Preg1"
  },
  "tile": {
    "ZA array tile": "ZA0H.Q"
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
MOV Zreg1.Q, Preg1/M, ZA0H.Q[Wreg1, imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/MOV--tile-to-vector--single---Move-ZA-tile-slice-to-vector-register--an-alias-of-MOVA--tile-to-vector--single--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svread_hor_za128[_s8]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svread_hor_za128%5B_s8%5D_m

### Signature (source notation)

```c
svint8_t svread_hor_za128[_s8]_m(svint8_t zd, svbool_t pg, uint64_t tile, uint32_t slice)
    __arm_streaming __arm_in("za");
```

### Description

Move ZA tile slice to vector register--an-alias-of-MOVA (tile to vector, single)

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Read / Horizontal tile slice

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
  "return_base_type": "int8",
  "element_bit_size": "8",
  "value": "svint8_t"
}
```

### Argument preparation and constraints

```json
{
  "zd": {
    "register": "Zreg1.Q"
  },
  "pg": {
    "register": "Preg1"
  },
  "tile": {
    "ZA array tile": "ZA0H.Q"
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
MOV Zreg1.Q, Preg1/M, ZA0H.Q[Wreg1, imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/MOV--tile-to-vector--single---Move-ZA-tile-slice-to-vector-register--an-alias-of-MOVA--tile-to-vector--single--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svread_hor_za128[_u16]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svread_hor_za128%5B_u16%5D_m

### Signature (source notation)

```c
svuint16_t svread_hor_za128[_u16]_m(svuint16_t zd, svbool_t pg, uint64_t tile, uint32_t slice)
    __arm_streaming __arm_in("za");
```

### Description

Move ZA tile slice to vector register--an-alias-of-MOVA (tile to vector, single)

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Read / Horizontal tile slice

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
  "return_base_type": "uint16",
  "element_bit_size": "16",
  "value": "svuint16_t"
}
```

### Argument preparation and constraints

```json
{
  "zd": {
    "register": "Zreg1.Q"
  },
  "pg": {
    "register": "Preg1"
  },
  "tile": {
    "ZA array tile": "ZA0H.Q"
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
MOV Zreg1.Q, Preg1/M, ZA0H.Q[Wreg1, imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/MOV--tile-to-vector--single---Move-ZA-tile-slice-to-vector-register--an-alias-of-MOVA--tile-to-vector--single--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svread_hor_za128[_u32]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svread_hor_za128%5B_u32%5D_m

### Signature (source notation)

```c
svuint32_t svread_hor_za128[_u32]_m(svuint32_t zd, svbool_t pg, uint64_t tile, uint32_t slice)
    __arm_streaming __arm_in("za");
```

### Description

Move ZA tile slice to vector register--an-alias-of-MOVA (tile to vector, single)

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Read / Horizontal tile slice

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
  "return_base_type": "uint32",
  "element_bit_size": "32",
  "value": "svuint32_t"
}
```

### Argument preparation and constraints

```json
{
  "zd": {
    "register": "Zreg1.Q"
  },
  "pg": {
    "register": "Preg1"
  },
  "tile": {
    "ZA array tile": "ZA0H.Q"
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
MOV Zreg1.Q, Preg1/M, ZA0H.Q[Wreg1, imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/MOV--tile-to-vector--single---Move-ZA-tile-slice-to-vector-register--an-alias-of-MOVA--tile-to-vector--single--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svread_hor_za128[_u64]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svread_hor_za128%5B_u64%5D_m

### Signature (source notation)

```c
svuint64_t svread_hor_za128[_u64]_m(svuint64_t zd, svbool_t pg, uint64_t tile, uint32_t slice)
    __arm_streaming __arm_in("za");
```

### Description

Move ZA tile slice to vector register--an-alias-of-MOVA (tile to vector, single)

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Read / Horizontal tile slice

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
  "return_base_type": "uint64",
  "element_bit_size": "64",
  "value": "svuint64_t"
}
```

### Argument preparation and constraints

```json
{
  "zd": {
    "register": "Zreg1.Q"
  },
  "pg": {
    "register": "Preg1"
  },
  "tile": {
    "ZA array tile": "ZA0H.Q"
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
MOV Zreg1.Q, Preg1/M, ZA0H.Q[Wreg1, imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/MOV--tile-to-vector--single---Move-ZA-tile-slice-to-vector-register--an-alias-of-MOVA--tile-to-vector--single--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svread_hor_za128[_u8]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svread_hor_za128%5B_u8%5D_m

### Signature (source notation)

```c
svuint8_t svread_hor_za128[_u8]_m(svuint8_t zd, svbool_t pg, uint64_t tile, uint32_t slice)
    __arm_streaming __arm_in("za");
```

### Description

Move ZA tile slice to vector register--an-alias-of-MOVA (tile to vector, single)

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Read / Horizontal tile slice

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
  "return_base_type": "uint8",
  "element_bit_size": "8",
  "value": "svuint8_t"
}
```

### Argument preparation and constraints

```json
{
  "zd": {
    "register": "Zreg1.Q"
  },
  "pg": {
    "register": "Preg1"
  },
  "tile": {
    "ZA array tile": "ZA0H.Q"
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
MOV Zreg1.Q, Preg1/M, ZA0H.Q[Wreg1, imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/MOV--tile-to-vector--single---Move-ZA-tile-slice-to-vector-register--an-alias-of-MOVA--tile-to-vector--single--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svread_hor_za16[_bf16]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svread_hor_za16%5B_bf16%5D_m

### Signature (source notation)

```c
svbfloat16_t svread_hor_za16[_bf16]_m(svbfloat16_t zd, svbool_t pg, uint64_t tile, uint32_t slice)
    __arm_streaming __arm_in("za");
```

### Description

Move ZA tile slice to vector register--an-alias-of-MOVA (tile to vector, single)

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Read / Horizontal tile slice

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
  "return_base_type": "bfloat16",
  "element_bit_size": "16",
  "value": "svbfloat16_t"
}
```

### Argument preparation and constraints

```json
{
  "zd": {
    "register": "Zreg1.H"
  },
  "pg": {
    "register": "Preg1"
  },
  "tile": {
    "ZA array tile": "ZA0H.H"
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
MOV Zreg1.H, Preg1/M, ZA0H.H[Wreg1, imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/MOV--tile-to-vector--single---Move-ZA-tile-slice-to-vector-register--an-alias-of-MOVA--tile-to-vector--single--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svread_hor_za16[_f16]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svread_hor_za16%5B_f16%5D_m

### Signature (source notation)

```c
svfloat16_t svread_hor_za16[_f16]_m(svfloat16_t zd, svbool_t pg, uint64_t tile, uint32_t slice)
    __arm_streaming __arm_in("za");
```

### Description

Move ZA tile slice to vector register--an-alias-of-MOVA (tile to vector, single)

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Read / Horizontal tile slice

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
  "return_base_type": "float16",
  "element_bit_size": "16",
  "value": "svfloat16_t"
}
```

### Argument preparation and constraints

```json
{
  "zd": {
    "register": "Zreg1.H"
  },
  "pg": {
    "register": "Preg1"
  },
  "tile": {
    "ZA array tile": "ZA0H.H"
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
MOV Zreg1.H, Preg1/M, ZA0H.H[Wreg1, imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/MOV--tile-to-vector--single---Move-ZA-tile-slice-to-vector-register--an-alias-of-MOVA--tile-to-vector--single--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svread_hor_za16[_s16]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svread_hor_za16%5B_s16%5D_m

### Signature (source notation)

```c
svint16_t svread_hor_za16[_s16]_m(svint16_t zd, svbool_t pg, uint64_t tile, uint32_t slice)
    __arm_streaming __arm_in("za");
```

### Description

Move ZA tile slice to vector register--an-alias-of-MOVA (tile to vector, single)

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Read / Horizontal tile slice

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
  "return_base_type": "int16",
  "element_bit_size": "16",
  "value": "svint16_t"
}
```

### Argument preparation and constraints

```json
{
  "zd": {
    "register": "Zreg1.H"
  },
  "pg": {
    "register": "Preg1"
  },
  "tile": {
    "ZA array tile": "ZA0H.H"
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
MOV Zreg1.H, Preg1/M, ZA0H.H[Wreg1, imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/MOV--tile-to-vector--single---Move-ZA-tile-slice-to-vector-register--an-alias-of-MOVA--tile-to-vector--single--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svread_hor_za16[_u16]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svread_hor_za16%5B_u16%5D_m

### Signature (source notation)

```c
svuint16_t svread_hor_za16[_u16]_m(svuint16_t zd, svbool_t pg, uint64_t tile, uint32_t slice)
    __arm_streaming __arm_in("za");
```

### Description

Move ZA tile slice to vector register--an-alias-of-MOVA (tile to vector, single)

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Read / Horizontal tile slice

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
  "return_base_type": "uint16",
  "element_bit_size": "16",
  "value": "svuint16_t"
}
```

### Argument preparation and constraints

```json
{
  "zd": {
    "register": "Zreg1.H"
  },
  "pg": {
    "register": "Preg1"
  },
  "tile": {
    "ZA array tile": "ZA0H.H"
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
MOV Zreg1.H, Preg1/M, ZA0H.H[Wreg1, imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/MOV--tile-to-vector--single---Move-ZA-tile-slice-to-vector-register--an-alias-of-MOVA--tile-to-vector--single--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svread_hor_za32[_f32]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svread_hor_za32%5B_f32%5D_m

### Signature (source notation)

```c
svfloat32_t svread_hor_za32[_f32]_m(svfloat32_t zd, svbool_t pg, uint64_t tile, uint32_t slice)
    __arm_streaming __arm_in("za");
```

### Description

Move ZA tile slice to vector register--an-alias-of-MOVA (tile to vector, single)

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Read / Horizontal tile slice

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
  "return_base_type": "float32",
  "element_bit_size": "32",
  "value": "svfloat32_t"
}
```

### Argument preparation and constraints

```json
{
  "zd": {
    "register": "Zreg1.S"
  },
  "pg": {
    "register": "Preg1"
  },
  "tile": {
    "ZA array tile": "ZA0H.S"
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
    "Zreg1.S": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
MOV Zreg1.S, Preg1/M, ZA0H.S[Wreg1, imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/MOV--tile-to-vector--single---Move-ZA-tile-slice-to-vector-register--an-alias-of-MOVA--tile-to-vector--single--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svread_hor_za32[_s32]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svread_hor_za32%5B_s32%5D_m

### Signature (source notation)

```c
svint32_t svread_hor_za32[_s32]_m(svint32_t zd, svbool_t pg, uint64_t tile, uint32_t slice)
    __arm_streaming __arm_in("za");
```

### Description

Move ZA tile slice to vector register--an-alias-of-MOVA (tile to vector, single)

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Read / Horizontal tile slice

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
  "return_base_type": "int32",
  "element_bit_size": "32",
  "value": "svint32_t"
}
```

### Argument preparation and constraints

```json
{
  "zd": {
    "register": "Zreg1.S"
  },
  "pg": {
    "register": "Preg1"
  },
  "tile": {
    "ZA array tile": "ZA0H.S"
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
    "Zreg1.S": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
MOV Zreg1.S, Preg1/M, ZA0H.S[Wreg1, imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/MOV--tile-to-vector--single---Move-ZA-tile-slice-to-vector-register--an-alias-of-MOVA--tile-to-vector--single--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svread_hor_za32[_u32]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svread_hor_za32%5B_u32%5D_m

### Signature (source notation)

```c
svuint32_t svread_hor_za32[_u32]_m(svuint32_t zd, svbool_t pg, uint64_t tile, uint32_t slice)
    __arm_streaming __arm_in("za");
```

### Description

Move ZA tile slice to vector register--an-alias-of-MOVA (tile to vector, single)

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Read / Horizontal tile slice

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
  "return_base_type": "uint32",
  "element_bit_size": "32",
  "value": "svuint32_t"
}
```

### Argument preparation and constraints

```json
{
  "zd": {
    "register": "Zreg1.S"
  },
  "pg": {
    "register": "Preg1"
  },
  "tile": {
    "ZA array tile": "ZA0H.S"
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
    "Zreg1.S": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
MOV Zreg1.S, Preg1/M, ZA0H.S[Wreg1, imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/MOV--tile-to-vector--single---Move-ZA-tile-slice-to-vector-register--an-alias-of-MOVA--tile-to-vector--single--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svread_hor_za64[_f64]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svread_hor_za64%5B_f64%5D_m

### Signature (source notation)

```c
svfloat64_t svread_hor_za64[_f64]_m(svfloat64_t zd, svbool_t pg, uint64_t tile, uint32_t slice)
    __arm_streaming __arm_in("za");
```

### Description

Move ZA tile slice to vector register--an-alias-of-MOVA (tile to vector, single)

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Read / Horizontal tile slice

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
  "return_base_type": "float64",
  "element_bit_size": "64",
  "value": "svfloat64_t"
}
```

### Argument preparation and constraints

```json
{
  "zd": {
    "register": "Zreg1.D"
  },
  "pg": {
    "register": "Preg1"
  },
  "tile": {
    "ZA array tile": "ZA0H.D"
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
    "Zreg1.D": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
MOV Zreg1.D, Preg1/M, ZA0H.D[Wreg1, imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/MOV--tile-to-vector--single---Move-ZA-tile-slice-to-vector-register--an-alias-of-MOVA--tile-to-vector--single--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svread_hor_za64[_s64]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svread_hor_za64%5B_s64%5D_m

### Signature (source notation)

```c
svint64_t svread_hor_za64[_s64]_m(svint64_t zd, svbool_t pg, uint64_t tile, uint32_t slice)
    __arm_streaming __arm_in("za");
```

### Description

Move ZA tile slice to vector register--an-alias-of-MOVA (tile to vector, single)

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Read / Horizontal tile slice

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
  "return_base_type": "int64",
  "element_bit_size": "64",
  "value": "svint64_t"
}
```

### Argument preparation and constraints

```json
{
  "zd": {
    "register": "Zreg1.D"
  },
  "pg": {
    "register": "Preg1"
  },
  "tile": {
    "ZA array tile": "ZA0H.D"
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
    "Zreg1.D": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
MOV Zreg1.D, Preg1/M, ZA0H.D[Wreg1, imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/MOV--tile-to-vector--single---Move-ZA-tile-slice-to-vector-register--an-alias-of-MOVA--tile-to-vector--single--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svread_hor_za64[_u64]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svread_hor_za64%5B_u64%5D_m

### Signature (source notation)

```c
svuint64_t svread_hor_za64[_u64]_m(svuint64_t zd, svbool_t pg, uint64_t tile, uint32_t slice)
    __arm_streaming __arm_in("za");
```

### Description

Move ZA tile slice to vector register--an-alias-of-MOVA (tile to vector, single)

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Read / Horizontal tile slice

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
  "return_base_type": "uint64",
  "element_bit_size": "64",
  "value": "svuint64_t"
}
```

### Argument preparation and constraints

```json
{
  "zd": {
    "register": "Zreg1.D"
  },
  "pg": {
    "register": "Preg1"
  },
  "tile": {
    "ZA array tile": "ZA0H.D"
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
    "Zreg1.D": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
MOV Zreg1.D, Preg1/M, ZA0H.D[Wreg1, imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/MOV--tile-to-vector--single---Move-ZA-tile-slice-to-vector-register--an-alias-of-MOVA--tile-to-vector--single--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svread_hor_za8[_mf8]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svread_hor_za8%5B_mf8%5D_m

### Signature (source notation)

```c
svmfloat8_t svread_hor_za8[_mf8]_m(svmfloat8_t zd, svbool_t pg, uint64_t tile, uint32_t slice)
    __arm_streaming __arm_in("za");
```

### Description

Move ZA tile slice to vector register--an-alias-of-MOVA (tile to vector, single)

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Read / Horizontal tile slice

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
  "return_base_type": "mfloat8",
  "element_bit_size": "8",
  "value": "svmfloat8_t"
}
```

### Argument preparation and constraints

```json
{
  "zd": {
    "register": "Zreg1.B"
  },
  "pg": {
    "register": "Preg1"
  },
  "tile": {
    "ZA array tile": "ZA0H.B"
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
    "Zreg1.B": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
MOV Zreg1.B, Preg1/M, ZA0H.B[Wreg1, imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/MOV--tile-to-vector--single---Move-ZA-tile-slice-to-vector-register--an-alias-of-MOVA--tile-to-vector--single--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svread_hor_za8[_s8]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svread_hor_za8%5B_s8%5D_m

### Signature (source notation)

```c
svint8_t svread_hor_za8[_s8]_m(svint8_t zd, svbool_t pg, uint64_t tile, uint32_t slice)
    __arm_streaming __arm_in("za");
```

### Description

Move ZA tile slice to vector register--an-alias-of-MOVA (tile to vector, single)

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Read / Horizontal tile slice

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
  "return_base_type": "int8",
  "element_bit_size": "8",
  "value": "svint8_t"
}
```

### Argument preparation and constraints

```json
{
  "zd": {
    "register": "Zreg1.B"
  },
  "pg": {
    "register": "Preg1"
  },
  "tile": {
    "ZA array tile": "ZA0H.B"
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
    "Zreg1.B": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
MOV Zreg1.B, Preg1/M, ZA0H.B[Wreg1, imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/MOV--tile-to-vector--single---Move-ZA-tile-slice-to-vector-register--an-alias-of-MOVA--tile-to-vector--single--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svread_hor_za8[_u8]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svread_hor_za8%5B_u8%5D_m

### Signature (source notation)

```c
svuint8_t svread_hor_za8[_u8]_m(svuint8_t zd, svbool_t pg, uint64_t tile, uint32_t slice)
    __arm_streaming __arm_in("za");
```

### Description

Move ZA tile slice to vector register--an-alias-of-MOVA (tile to vector, single)

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Read / Horizontal tile slice

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
  "return_base_type": "uint8",
  "element_bit_size": "8",
  "value": "svuint8_t"
}
```

### Argument preparation and constraints

```json
{
  "zd": {
    "register": "Zreg1.B"
  },
  "pg": {
    "register": "Preg1"
  },
  "tile": {
    "ZA array tile": "ZA0H.B"
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
    "Zreg1.B": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
MOV Zreg1.B, Preg1/M, ZA0H.B[Wreg1, imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/MOV--tile-to-vector--single---Move-ZA-tile-slice-to-vector-register--an-alias-of-MOVA--tile-to-vector--single--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

