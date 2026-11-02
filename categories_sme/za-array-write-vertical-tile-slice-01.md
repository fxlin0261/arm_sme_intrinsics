# SME / ZA array / Write / Vertical tile slice — Part 1

## svwrite_ver_za128[_bf16]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwrite_ver_za128%5B_bf16%5D_m

### Signature (source notation)

```c
void svwrite_ver_za128[_bf16]_m(uint64_t tile, uint32_t slice, svbool_t pg, svbfloat16_t zn)
    __arm_streaming __arm_inout("za");
```

### Description

Move vector register to ZA tile slice--an-alias-of-MOVA (vector to tile, single)

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Write / Vertical tile slice

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

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
    "ZA array tile": "ZA0V.Q"
  },
  "slice": {
    "register+immediate": "Wreg1 + imm1"
  },
  "pg": {
    "register": "Preg1"
  },
  "zn": {
    "register": "Zreg1.Q"
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
MOV ZA0V.Q[Wreg1, imm1], Preg1/M, Zreg1.Q
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/MOV--vector-to-tile--single---Move-vector-register-to-ZA-tile-slice--an-alias-of-MOVA--vector-to-tile--single--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svwrite_ver_za128[_f16]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwrite_ver_za128%5B_f16%5D_m

### Signature (source notation)

```c
void svwrite_ver_za128[_f16]_m(uint64_t tile, uint32_t slice, svbool_t pg, svfloat16_t zn)
    __arm_streaming __arm_inout("za");
```

### Description

Move vector register to ZA tile slice--an-alias-of-MOVA (vector to tile, single)

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Write / Vertical tile slice

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

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
    "ZA array tile": "ZA0V.Q"
  },
  "slice": {
    "register+immediate": "Wreg1 + imm1"
  },
  "pg": {
    "register": "Preg1"
  },
  "zn": {
    "register": "Zreg1.Q"
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
MOV ZA0V.Q[Wreg1, imm1], Preg1/M, Zreg1.Q
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/MOV--vector-to-tile--single---Move-vector-register-to-ZA-tile-slice--an-alias-of-MOVA--vector-to-tile--single--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svwrite_ver_za128[_f32]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwrite_ver_za128%5B_f32%5D_m

### Signature (source notation)

```c
void svwrite_ver_za128[_f32]_m(uint64_t tile, uint32_t slice, svbool_t pg, svfloat32_t zn)
    __arm_streaming __arm_inout("za");
```

### Description

Move vector register to ZA tile slice--an-alias-of-MOVA (vector to tile, single)

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Write / Vertical tile slice

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

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
    "ZA array tile": "ZA0V.Q"
  },
  "slice": {
    "register+immediate": "Wreg1 + imm1"
  },
  "pg": {
    "register": "Preg1"
  },
  "zn": {
    "register": "Zreg1.Q"
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
MOV ZA0V.Q[Wreg1, imm1], Preg1/M, Zreg1.Q
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/MOV--vector-to-tile--single---Move-vector-register-to-ZA-tile-slice--an-alias-of-MOVA--vector-to-tile--single--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svwrite_ver_za128[_f64]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwrite_ver_za128%5B_f64%5D_m

### Signature (source notation)

```c
void svwrite_ver_za128[_f64]_m(uint64_t tile, uint32_t slice, svbool_t pg, svfloat64_t zn)
    __arm_streaming __arm_inout("za");
```

### Description

Move vector register to ZA tile slice--an-alias-of-MOVA (vector to tile, single)

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Write / Vertical tile slice

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

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
    "ZA array tile": "ZA0V.Q"
  },
  "slice": {
    "register+immediate": "Wreg1 + imm1"
  },
  "pg": {
    "register": "Preg1"
  },
  "zn": {
    "register": "Zreg1.Q"
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
MOV ZA0V.Q[Wreg1, imm1], Preg1/M, Zreg1.Q
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/MOV--vector-to-tile--single---Move-vector-register-to-ZA-tile-slice--an-alias-of-MOVA--vector-to-tile--single--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svwrite_ver_za128[_mf8]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwrite_ver_za128%5B_mf8%5D_m

### Signature (source notation)

```c
void svwrite_ver_za128[_mf8]_m(uint64_t tile, uint32_t slice, svbool_t pg, svmfloat8_t zn)
    __arm_streaming __arm_inout("za");
```

### Description

Move vector register to ZA tile slice--an-alias-of-MOVA (vector to tile, single)

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Write / Vertical tile slice

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

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
    "ZA array tile": "ZA0V.Q"
  },
  "slice": {
    "register+immediate": "Wreg1 + imm1"
  },
  "pg": {
    "register": "Preg1"
  },
  "zn": {
    "register": "Zreg1.Q"
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
MOV ZA0V.Q[Wreg1, imm1], Preg1/M, Zreg1.Q
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/MOV--vector-to-tile--single---Move-vector-register-to-ZA-tile-slice--an-alias-of-MOVA--vector-to-tile--single--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svwrite_ver_za128[_s16]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwrite_ver_za128%5B_s16%5D_m

### Signature (source notation)

```c
void svwrite_ver_za128[_s16]_m(uint64_t tile, uint32_t slice, svbool_t pg, svint16_t zn)
    __arm_streaming __arm_inout("za");
```

### Description

Move vector register to ZA tile slice--an-alias-of-MOVA (vector to tile, single)

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Write / Vertical tile slice

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

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
    "ZA array tile": "ZA0V.Q"
  },
  "slice": {
    "register+immediate": "Wreg1 + imm1"
  },
  "pg": {
    "register": "Preg1"
  },
  "zn": {
    "register": "Zreg1.Q"
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
MOV ZA0V.Q[Wreg1, imm1], Preg1/M, Zreg1.Q
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/MOV--vector-to-tile--single---Move-vector-register-to-ZA-tile-slice--an-alias-of-MOVA--vector-to-tile--single--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svwrite_ver_za128[_s32]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwrite_ver_za128%5B_s32%5D_m

### Signature (source notation)

```c
void svwrite_ver_za128[_s32]_m(uint64_t tile, uint32_t slice, svbool_t pg, svint32_t zn)
    __arm_streaming __arm_inout("za");
```

### Description

Move vector register to ZA tile slice--an-alias-of-MOVA (vector to tile, single)

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Write / Vertical tile slice

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

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
    "ZA array tile": "ZA0V.Q"
  },
  "slice": {
    "register+immediate": "Wreg1 + imm1"
  },
  "pg": {
    "register": "Preg1"
  },
  "zn": {
    "register": "Zreg1.Q"
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
MOV ZA0V.Q[Wreg1, imm1], Preg1/M, Zreg1.Q
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/MOV--vector-to-tile--single---Move-vector-register-to-ZA-tile-slice--an-alias-of-MOVA--vector-to-tile--single--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svwrite_ver_za128[_s64]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwrite_ver_za128%5B_s64%5D_m

### Signature (source notation)

```c
void svwrite_ver_za128[_s64]_m(uint64_t tile, uint32_t slice, svbool_t pg, svint64_t zn)
    __arm_streaming __arm_inout("za");
```

### Description

Move vector register to ZA tile slice--an-alias-of-MOVA (vector to tile, single)

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Write / Vertical tile slice

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

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
    "ZA array tile": "ZA0V.Q"
  },
  "slice": {
    "register+immediate": "Wreg1 + imm1"
  },
  "pg": {
    "register": "Preg1"
  },
  "zn": {
    "register": "Zreg1.Q"
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
MOV ZA0V.Q[Wreg1, imm1], Preg1/M, Zreg1.Q
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/MOV--vector-to-tile--single---Move-vector-register-to-ZA-tile-slice--an-alias-of-MOVA--vector-to-tile--single--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svwrite_ver_za128[_s8]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwrite_ver_za128%5B_s8%5D_m

### Signature (source notation)

```c
void svwrite_ver_za128[_s8]_m(uint64_t tile, uint32_t slice, svbool_t pg, svint8_t zn)
    __arm_streaming __arm_inout("za");
```

### Description

Move vector register to ZA tile slice--an-alias-of-MOVA (vector to tile, single)

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Write / Vertical tile slice

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

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
    "ZA array tile": "ZA0V.Q"
  },
  "slice": {
    "register+immediate": "Wreg1 + imm1"
  },
  "pg": {
    "register": "Preg1"
  },
  "zn": {
    "register": "Zreg1.Q"
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
MOV ZA0V.Q[Wreg1, imm1], Preg1/M, Zreg1.Q
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/MOV--vector-to-tile--single---Move-vector-register-to-ZA-tile-slice--an-alias-of-MOVA--vector-to-tile--single--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svwrite_ver_za128[_u16]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwrite_ver_za128%5B_u16%5D_m

### Signature (source notation)

```c
void svwrite_ver_za128[_u16]_m(uint64_t tile, uint32_t slice, svbool_t pg, svuint16_t zn)
    __arm_streaming __arm_inout("za");
```

### Description

Move vector register to ZA tile slice--an-alias-of-MOVA (vector to tile, single)

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Write / Vertical tile slice

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

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
    "ZA array tile": "ZA0V.Q"
  },
  "slice": {
    "register+immediate": "Wreg1 + imm1"
  },
  "pg": {
    "register": "Preg1"
  },
  "zn": {
    "register": "Zreg1.Q"
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
MOV ZA0V.Q[Wreg1, imm1], Preg1/M, Zreg1.Q
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/MOV--vector-to-tile--single---Move-vector-register-to-ZA-tile-slice--an-alias-of-MOVA--vector-to-tile--single--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svwrite_ver_za128[_u32]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwrite_ver_za128%5B_u32%5D_m

### Signature (source notation)

```c
void svwrite_ver_za128[_u32]_m(uint64_t tile, uint32_t slice, svbool_t pg, svuint32_t zn)
    __arm_streaming __arm_inout("za");
```

### Description

Move vector register to ZA tile slice--an-alias-of-MOVA (vector to tile, single)

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Write / Vertical tile slice

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

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
    "ZA array tile": "ZA0V.Q"
  },
  "slice": {
    "register+immediate": "Wreg1 + imm1"
  },
  "pg": {
    "register": "Preg1"
  },
  "zn": {
    "register": "Zreg1.Q"
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
MOV ZA0V.Q[Wreg1, imm1], Preg1/M, Zreg1.Q
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/MOV--vector-to-tile--single---Move-vector-register-to-ZA-tile-slice--an-alias-of-MOVA--vector-to-tile--single--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svwrite_ver_za128[_u64]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwrite_ver_za128%5B_u64%5D_m

### Signature (source notation)

```c
void svwrite_ver_za128[_u64]_m(uint64_t tile, uint32_t slice, svbool_t pg, svuint64_t zn)
    __arm_streaming __arm_inout("za");
```

### Description

Move vector register to ZA tile slice--an-alias-of-MOVA (vector to tile, single)

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Write / Vertical tile slice

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

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
    "ZA array tile": "ZA0V.Q"
  },
  "slice": {
    "register+immediate": "Wreg1 + imm1"
  },
  "pg": {
    "register": "Preg1"
  },
  "zn": {
    "register": "Zreg1.Q"
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
MOV ZA0V.Q[Wreg1, imm1], Preg1/M, Zreg1.Q
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/MOV--vector-to-tile--single---Move-vector-register-to-ZA-tile-slice--an-alias-of-MOVA--vector-to-tile--single--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svwrite_ver_za128[_u8]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwrite_ver_za128%5B_u8%5D_m

### Signature (source notation)

```c
void svwrite_ver_za128[_u8]_m(uint64_t tile, uint32_t slice, svbool_t pg, svuint8_t zn)
    __arm_streaming __arm_inout("za");
```

### Description

Move vector register to ZA tile slice--an-alias-of-MOVA (vector to tile, single)

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Write / Vertical tile slice

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

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
    "ZA array tile": "ZA0V.Q"
  },
  "slice": {
    "register+immediate": "Wreg1 + imm1"
  },
  "pg": {
    "register": "Preg1"
  },
  "zn": {
    "register": "Zreg1.Q"
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
MOV ZA0V.Q[Wreg1, imm1], Preg1/M, Zreg1.Q
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/MOV--vector-to-tile--single---Move-vector-register-to-ZA-tile-slice--an-alias-of-MOVA--vector-to-tile--single--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svwrite_ver_za16[_bf16]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwrite_ver_za16%5B_bf16%5D_m

### Signature (source notation)

```c
void svwrite_ver_za16[_bf16]_m(uint64_t tile, uint32_t slice, svbool_t pg, svbfloat16_t zn)
    __arm_streaming __arm_inout("za");
```

### Description

Move vector register to ZA tile slice--an-alias-of-MOVA (vector to tile, single)

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Write / Vertical tile slice

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

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
  "zn": {
    "register": "Zreg1.H"
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
MOV ZA0V.H[Wreg1, imm1], Preg1/M, Zreg1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/MOV--vector-to-tile--single---Move-vector-register-to-ZA-tile-slice--an-alias-of-MOVA--vector-to-tile--single--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svwrite_ver_za16[_f16]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwrite_ver_za16%5B_f16%5D_m

### Signature (source notation)

```c
void svwrite_ver_za16[_f16]_m(uint64_t tile, uint32_t slice, svbool_t pg, svfloat16_t zn)
    __arm_streaming __arm_inout("za");
```

### Description

Move vector register to ZA tile slice--an-alias-of-MOVA (vector to tile, single)

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Write / Vertical tile slice

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

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
  "zn": {
    "register": "Zreg1.H"
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
MOV ZA0V.H[Wreg1, imm1], Preg1/M, Zreg1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/MOV--vector-to-tile--single---Move-vector-register-to-ZA-tile-slice--an-alias-of-MOVA--vector-to-tile--single--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svwrite_ver_za16[_s16]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwrite_ver_za16%5B_s16%5D_m

### Signature (source notation)

```c
void svwrite_ver_za16[_s16]_m(uint64_t tile, uint32_t slice, svbool_t pg, svint16_t zn)
    __arm_streaming __arm_inout("za");
```

### Description

Move vector register to ZA tile slice--an-alias-of-MOVA (vector to tile, single)

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Write / Vertical tile slice

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

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
  "zn": {
    "register": "Zreg1.H"
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
MOV ZA0V.H[Wreg1, imm1], Preg1/M, Zreg1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/MOV--vector-to-tile--single---Move-vector-register-to-ZA-tile-slice--an-alias-of-MOVA--vector-to-tile--single--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svwrite_ver_za16[_u16]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwrite_ver_za16%5B_u16%5D_m

### Signature (source notation)

```c
void svwrite_ver_za16[_u16]_m(uint64_t tile, uint32_t slice, svbool_t pg, svuint16_t zn)
    __arm_streaming __arm_inout("za");
```

### Description

Move vector register to ZA tile slice--an-alias-of-MOVA (vector to tile, single)

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Write / Vertical tile slice

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

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
  "zn": {
    "register": "Zreg1.H"
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
MOV ZA0V.H[Wreg1, imm1], Preg1/M, Zreg1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/MOV--vector-to-tile--single---Move-vector-register-to-ZA-tile-slice--an-alias-of-MOVA--vector-to-tile--single--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svwrite_ver_za32[_f32]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwrite_ver_za32%5B_f32%5D_m

### Signature (source notation)

```c
void svwrite_ver_za32[_f32]_m(uint64_t tile, uint32_t slice, svbool_t pg, svfloat32_t zn)
    __arm_streaming __arm_inout("za");
```

### Description

Move vector register to ZA tile slice--an-alias-of-MOVA (vector to tile, single)

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Write / Vertical tile slice

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

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
  "zn": {
    "register": "Zreg1.S"
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
MOV ZA0V.S[Wreg1, imm1], Preg1/M, Zreg1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/MOV--vector-to-tile--single---Move-vector-register-to-ZA-tile-slice--an-alias-of-MOVA--vector-to-tile--single--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svwrite_ver_za32[_s32]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwrite_ver_za32%5B_s32%5D_m

### Signature (source notation)

```c
void svwrite_ver_za32[_s32]_m(uint64_t tile, uint32_t slice, svbool_t pg, svint32_t zn)
    __arm_streaming __arm_inout("za");
```

### Description

Move vector register to ZA tile slice--an-alias-of-MOVA (vector to tile, single)

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Write / Vertical tile slice

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

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
  "zn": {
    "register": "Zreg1.S"
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
MOV ZA0V.S[Wreg1, imm1], Preg1/M, Zreg1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/MOV--vector-to-tile--single---Move-vector-register-to-ZA-tile-slice--an-alias-of-MOVA--vector-to-tile--single--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svwrite_ver_za32[_u32]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwrite_ver_za32%5B_u32%5D_m

### Signature (source notation)

```c
void svwrite_ver_za32[_u32]_m(uint64_t tile, uint32_t slice, svbool_t pg, svuint32_t zn)
    __arm_streaming __arm_inout("za");
```

### Description

Move vector register to ZA tile slice--an-alias-of-MOVA (vector to tile, single)

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Write / Vertical tile slice

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

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
  "zn": {
    "register": "Zreg1.S"
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
MOV ZA0V.S[Wreg1, imm1], Preg1/M, Zreg1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/MOV--vector-to-tile--single---Move-vector-register-to-ZA-tile-slice--an-alias-of-MOVA--vector-to-tile--single--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svwrite_ver_za64[_f64]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwrite_ver_za64%5B_f64%5D_m

### Signature (source notation)

```c
void svwrite_ver_za64[_f64]_m(uint64_t tile, uint32_t slice, svbool_t pg, svfloat64_t zn)
    __arm_streaming __arm_inout("za");
```

### Description

Move vector register to ZA tile slice--an-alias-of-MOVA (vector to tile, single)

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Write / Vertical tile slice

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

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
  "zn": {
    "register": "Zreg1.D"
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
MOV ZA0V.D[Wreg1, imm1], Preg1/M, Zreg1.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/MOV--vector-to-tile--single---Move-vector-register-to-ZA-tile-slice--an-alias-of-MOVA--vector-to-tile--single--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svwrite_ver_za64[_s64]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwrite_ver_za64%5B_s64%5D_m

### Signature (source notation)

```c
void svwrite_ver_za64[_s64]_m(uint64_t tile, uint32_t slice, svbool_t pg, svint64_t zn)
    __arm_streaming __arm_inout("za");
```

### Description

Move vector register to ZA tile slice--an-alias-of-MOVA (vector to tile, single)

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Write / Vertical tile slice

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

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
  "zn": {
    "register": "Zreg1.D"
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
MOV ZA0V.D[Wreg1, imm1], Preg1/M, Zreg1.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/MOV--vector-to-tile--single---Move-vector-register-to-ZA-tile-slice--an-alias-of-MOVA--vector-to-tile--single--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svwrite_ver_za64[_u64]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwrite_ver_za64%5B_u64%5D_m

### Signature (source notation)

```c
void svwrite_ver_za64[_u64]_m(uint64_t tile, uint32_t slice, svbool_t pg, svuint64_t zn)
    __arm_streaming __arm_inout("za");
```

### Description

Move vector register to ZA tile slice--an-alias-of-MOVA (vector to tile, single)

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Write / Vertical tile slice

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

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
  "zn": {
    "register": "Zreg1.D"
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
MOV ZA0V.D[Wreg1, imm1], Preg1/M, Zreg1.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/MOV--vector-to-tile--single---Move-vector-register-to-ZA-tile-slice--an-alias-of-MOVA--vector-to-tile--single--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svwrite_ver_za8[_mf8]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwrite_ver_za8%5B_mf8%5D_m

### Signature (source notation)

```c
void svwrite_ver_za8[_mf8]_m(uint64_t tile, uint32_t slice, svbool_t pg, svmfloat8_t zn)
    __arm_streaming __arm_inout("za");
```

### Description

Move vector register to ZA tile slice--an-alias-of-MOVA (vector to tile, single)

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Write / Vertical tile slice

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

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
  "zn": {
    "register": "Zreg1.B"
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
MOV ZA0V.B[Wreg1, imm1], Preg1/M, Zreg1.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/MOV--vector-to-tile--single---Move-vector-register-to-ZA-tile-slice--an-alias-of-MOVA--vector-to-tile--single--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svwrite_ver_za8[_s8]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwrite_ver_za8%5B_s8%5D_m

### Signature (source notation)

```c
void svwrite_ver_za8[_s8]_m(uint64_t tile, uint32_t slice, svbool_t pg, svint8_t zn)
    __arm_streaming __arm_inout("za");
```

### Description

Move vector register to ZA tile slice--an-alias-of-MOVA (vector to tile, single)

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Write / Vertical tile slice

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

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
  "zn": {
    "register": "Zreg1.B"
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
MOV ZA0V.B[Wreg1, imm1], Preg1/M, Zreg1.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/MOV--vector-to-tile--single---Move-vector-register-to-ZA-tile-slice--an-alias-of-MOVA--vector-to-tile--single--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svwrite_ver_za8[_u8]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwrite_ver_za8%5B_u8%5D_m

### Signature (source notation)

```c
void svwrite_ver_za8[_u8]_m(uint64_t tile, uint32_t slice, svbool_t pg, svuint8_t zn)
    __arm_streaming __arm_inout("za");
```

### Description

Move vector register to ZA tile slice--an-alias-of-MOVA (vector to tile, single)

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Write / Vertical tile slice

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

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
  "zn": {
    "register": "Zreg1.B"
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
MOV ZA0V.B[Wreg1, imm1], Preg1/M, Zreg1.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/MOV--vector-to-tile--single---Move-vector-register-to-ZA-tile-slice--an-alias-of-MOVA--vector-to-tile--single--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

