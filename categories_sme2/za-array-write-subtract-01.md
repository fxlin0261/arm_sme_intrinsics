# SME2 / ZA array / Write / Subtract — Part 1

## svsub_write[_single]_za32[_s32]_vg1x2

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsub_write%5B_single%5D_za32%5B_s32%5D_vg1x2

### Signature (source notation)

```c
void svsub_write[_single]_za32[_s32]_vg1x2(uint32_t slice, svint32x2_t zn, svint32_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Subtract replicated single vector from multi-vector with ZA array vector results

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Write / Subtract

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
  "slice": {
    "register+immediate": "Wreg1 + imm1"
  },
  "zn": {
    "Z multi-vector": "{ Zreg1.S, Zreg2.S }"
  },
  "zm": {
    "register": "Zreg3.S"
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
SUB ZA.S[Wreg1, imm1, VGX2], { Zreg1.S, Zreg2.S }, Zreg3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SUB--array-results--multiple-and-single-vector---Subtract-replicated-single-vector-from-multi-vector-with-ZA-array-vector-results-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svsub_write[_single]_za32[_s32]_vg1x4

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsub_write%5B_single%5D_za32%5B_s32%5D_vg1x4

### Signature (source notation)

```c
void svsub_write[_single]_za32[_s32]_vg1x4(uint32_t slice, svint32x4_t zn, svint32_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Subtract replicated single vector from multi-vector with ZA array vector results

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Write / Subtract

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
  "slice": {
    "register+immediate": "Wreg1 + imm1"
  },
  "zn": {
    "Z multi-vector": "{ Zreg1.S - Zreg2.S }"
  },
  "zm": {
    "register": "Zreg3.S"
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
SUB ZA.S[Wreg1, imm1, VGX4], { Zreg1.S - Zreg2.S }, Zreg3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SUB--array-results--multiple-and-single-vector---Subtract-replicated-single-vector-from-multi-vector-with-ZA-array-vector-results-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svsub_write[_single]_za32[_u32]_vg1x2

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsub_write%5B_single%5D_za32%5B_u32%5D_vg1x2

### Signature (source notation)

```c
void svsub_write[_single]_za32[_u32]_vg1x2(uint32_t slice, svuint32x2_t zn, svuint32_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Subtract replicated single vector from multi-vector with ZA array vector results

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Write / Subtract

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
  "slice": {
    "register+immediate": "Wreg1 + imm1"
  },
  "zn": {
    "Z multi-vector": "{ Zreg1.S, Zreg2.S }"
  },
  "zm": {
    "register": "Zreg3.S"
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
SUB ZA.S[Wreg1, imm1, VGX2], { Zreg1.S, Zreg2.S }, Zreg3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SUB--array-results--multiple-and-single-vector---Subtract-replicated-single-vector-from-multi-vector-with-ZA-array-vector-results-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svsub_write[_single]_za32[_u32]_vg1x4

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsub_write%5B_single%5D_za32%5B_u32%5D_vg1x4

### Signature (source notation)

```c
void svsub_write[_single]_za32[_u32]_vg1x4(uint32_t slice, svuint32x4_t zn, svuint32_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Subtract replicated single vector from multi-vector with ZA array vector results

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Write / Subtract

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
  "slice": {
    "register+immediate": "Wreg1 + imm1"
  },
  "zn": {
    "Z multi-vector": "{ Zreg1.S - Zreg2.S }"
  },
  "zm": {
    "register": "Zreg3.S"
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
SUB ZA.S[Wreg1, imm1, VGX4], { Zreg1.S - Zreg2.S }, Zreg3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SUB--array-results--multiple-and-single-vector---Subtract-replicated-single-vector-from-multi-vector-with-ZA-array-vector-results-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svsub_write[_single]_za64[_s64]_vg1x2

ISA classification: SME2 + FEAT_SME_I16I64

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsub_write%5B_single%5D_za64%5B_s64%5D_vg1x2

### Signature (source notation)

```c
void svsub_write[_single]_za64[_s64]_vg1x2(uint32_t slice, svint64x2_t zn, svint64_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Subtract replicated single vector from multi-vector with ZA array vector results

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Write / Subtract

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2,FEAT_SME_I16I64
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
  "slice": {
    "register+immediate": "Wreg1 + imm1"
  },
  "zn": {
    "Z multi-vector": "{ Zreg1.D, Zreg2.D }"
  },
  "zm": {
    "register": "Zreg3.D"
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
SUB ZA.D[Wreg1, imm1, VGX2], { Zreg1.D, Zreg2.D }, Zreg3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SUB--array-results--multiple-and-single-vector---Subtract-replicated-single-vector-from-multi-vector-with-ZA-array-vector-results-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svsub_write[_single]_za64[_s64]_vg1x4

ISA classification: SME2 + FEAT_SME_I16I64

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsub_write%5B_single%5D_za64%5B_s64%5D_vg1x4

### Signature (source notation)

```c
void svsub_write[_single]_za64[_s64]_vg1x4(uint32_t slice, svint64x4_t zn, svint64_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Subtract replicated single vector from multi-vector with ZA array vector results

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Write / Subtract

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2,FEAT_SME_I16I64
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
  "slice": {
    "register+immediate": "Wreg1 + imm1"
  },
  "zn": {
    "Z multi-vector": "{ Zreg1.D - Zreg2.D }"
  },
  "zm": {
    "register": "Zreg3.D"
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
SUB ZA.D[Wreg1, imm1, VGX4], { Zreg1.D - Zreg2.D }, Zreg3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SUB--array-results--multiple-and-single-vector---Subtract-replicated-single-vector-from-multi-vector-with-ZA-array-vector-results-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svsub_write[_single]_za64[_u64]_vg1x2

ISA classification: SME2 + FEAT_SME_I16I64

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsub_write%5B_single%5D_za64%5B_u64%5D_vg1x2

### Signature (source notation)

```c
void svsub_write[_single]_za64[_u64]_vg1x2(uint32_t slice, svuint64x2_t zn, svuint64_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Subtract replicated single vector from multi-vector with ZA array vector results

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Write / Subtract

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2,FEAT_SME_I16I64
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
  "slice": {
    "register+immediate": "Wreg1 + imm1"
  },
  "zn": {
    "Z multi-vector": "{ Zreg1.D, Zreg2.D }"
  },
  "zm": {
    "register": "Zreg3.D"
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
SUB ZA.D[Wreg1, imm1, VGX2], { Zreg1.D, Zreg2.D }, Zreg3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SUB--array-results--multiple-and-single-vector---Subtract-replicated-single-vector-from-multi-vector-with-ZA-array-vector-results-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svsub_write[_single]_za64[_u64]_vg1x4

ISA classification: SME2 + FEAT_SME_I16I64

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsub_write%5B_single%5D_za64%5B_u64%5D_vg1x4

### Signature (source notation)

```c
void svsub_write[_single]_za64[_u64]_vg1x4(uint32_t slice, svuint64x4_t zn, svuint64_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Subtract replicated single vector from multi-vector with ZA array vector results

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Write / Subtract

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2,FEAT_SME_I16I64
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
  "slice": {
    "register+immediate": "Wreg1 + imm1"
  },
  "zn": {
    "Z multi-vector": "{ Zreg1.D - Zreg2.D }"
  },
  "zm": {
    "register": "Zreg3.D"
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
SUB ZA.D[Wreg1, imm1, VGX4], { Zreg1.D - Zreg2.D }, Zreg3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SUB--array-results--multiple-and-single-vector---Subtract-replicated-single-vector-from-multi-vector-with-ZA-array-vector-results-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svsub_write_za32[_s32]_vg1x2

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsub_write_za32%5B_s32%5D_vg1x2

### Signature (source notation)

```c
void svsub_write_za32[_s32]_vg1x2(uint32_t slice, svint32x2_t zn, svint32x2_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Subtract multi-vector from multi-vector with ZA array vector results

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Write / Subtract

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
  "slice": {
    "register+immediate": "Wreg1 + imm1"
  },
  "zn": {
    "Z multi-vector": "{ Zreg1.S, Zreg2.S }"
  },
  "zm": {
    "Z multi-vector": "{ Zreg3.S, Zreg4.S }"
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
SUB ZA.S[Wreg1, imm1, VGX2], { Zreg1.S, Zreg2.S }, { Zreg3.S, Zreg4.S }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SUB--array-results--multiple-vectors---Subtract-multi-vector-from-multi-vector-with-ZA-array-vector-results-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svsub_write_za32[_s32]_vg1x4

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsub_write_za32%5B_s32%5D_vg1x4

### Signature (source notation)

```c
void svsub_write_za32[_s32]_vg1x4(uint32_t slice, svint32x4_t zn, svint32x4_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Subtract multi-vector from multi-vector with ZA array vector results

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Write / Subtract

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
  "slice": {
    "register+immediate": "Wreg1 + imm1"
  },
  "zn": {
    "Z multi-vector": "{ Zreg1.S - Zreg2.S }"
  },
  "zm": {
    "Z multi-vector": "{ Zreg3.S - Zreg4.S }"
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
SUB ZA.S[Wreg1, imm1, VGX4], { Zreg1.S - Zreg2.S }, { Zreg3.S - Zreg4.S }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SUB--array-results--multiple-vectors---Subtract-multi-vector-from-multi-vector-with-ZA-array-vector-results-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svsub_write_za32[_u32]_vg1x2

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsub_write_za32%5B_u32%5D_vg1x2

### Signature (source notation)

```c
void svsub_write_za32[_u32]_vg1x2(uint32_t slice, svuint32x2_t zn, svuint32x2_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Subtract multi-vector from multi-vector with ZA array vector results

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Write / Subtract

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
  "slice": {
    "register+immediate": "Wreg1 + imm1"
  },
  "zn": {
    "Z multi-vector": "{ Zreg1.S, Zreg2.S }"
  },
  "zm": {
    "Z multi-vector": "{ Zreg3.S, Zreg4.S }"
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
SUB ZA.S[Wreg1, imm1, VGX2], { Zreg1.S, Zreg2.S }, { Zreg3.S, Zreg4.S }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SUB--array-results--multiple-vectors---Subtract-multi-vector-from-multi-vector-with-ZA-array-vector-results-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svsub_write_za32[_u32]_vg1x4

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsub_write_za32%5B_u32%5D_vg1x4

### Signature (source notation)

```c
void svsub_write_za32[_u32]_vg1x4(uint32_t slice, svuint32x4_t zn, svuint32x4_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Subtract multi-vector from multi-vector with ZA array vector results

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Write / Subtract

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
  "slice": {
    "register+immediate": "Wreg1 + imm1"
  },
  "zn": {
    "Z multi-vector": "{ Zreg1.S - Zreg2.S }"
  },
  "zm": {
    "Z multi-vector": "{ Zreg3.S - Zreg4.S }"
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
SUB ZA.S[Wreg1, imm1, VGX4], { Zreg1.S - Zreg2.S }, { Zreg3.S - Zreg4.S }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SUB--array-results--multiple-vectors---Subtract-multi-vector-from-multi-vector-with-ZA-array-vector-results-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svsub_write_za64[_s64]_vg1x2

ISA classification: SME2 + FEAT_SME_I16I64

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsub_write_za64%5B_s64%5D_vg1x2

### Signature (source notation)

```c
void svsub_write_za64[_s64]_vg1x2(uint32_t slice, svint64x2_t zn, svint64x2_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Subtract multi-vector from multi-vector with ZA array vector results

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Write / Subtract

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2,FEAT_SME_I16I64
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
  "slice": {
    "register+immediate": "Wreg1 + imm1"
  },
  "zn": {
    "Z multi-vector": "{ Zreg1.D, Zreg2.D }"
  },
  "zm": {
    "Z multi-vector": "{ Zreg3.D, Zreg4.D }"
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
SUB ZA.D[Wreg1, imm1, VGX2], { Zreg1.D, Zreg2.D }, { Zreg3.D, Zreg4.D }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SUB--array-results--multiple-vectors---Subtract-multi-vector-from-multi-vector-with-ZA-array-vector-results-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svsub_write_za64[_s64]_vg1x4

ISA classification: SME2 + FEAT_SME_I16I64

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsub_write_za64%5B_s64%5D_vg1x4

### Signature (source notation)

```c
void svsub_write_za64[_s64]_vg1x4(uint32_t slice, svint64x4_t zn, svint64x4_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Subtract multi-vector from multi-vector with ZA array vector results

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Write / Subtract

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2,FEAT_SME_I16I64
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
  "slice": {
    "register+immediate": "Wreg1 + imm1"
  },
  "zn": {
    "Z multi-vector": "{ Zreg1.D - Zreg2.D }"
  },
  "zm": {
    "Z multi-vector": "{ Zreg3.D - Zreg4.D }"
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
SUB ZA.D[Wreg1, imm1, VGX4], { Zreg1.D - Zreg2.D }, { Zreg3.D - Zreg4.D }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SUB--array-results--multiple-vectors---Subtract-multi-vector-from-multi-vector-with-ZA-array-vector-results-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svsub_write_za64[_u64]_vg1x2

ISA classification: SME2 + FEAT_SME_I16I64

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsub_write_za64%5B_u64%5D_vg1x2

### Signature (source notation)

```c
void svsub_write_za64[_u64]_vg1x2(uint32_t slice, svuint64x2_t zn, svuint64x2_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Subtract multi-vector from multi-vector with ZA array vector results

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Write / Subtract

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2,FEAT_SME_I16I64
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
  "slice": {
    "register+immediate": "Wreg1 + imm1"
  },
  "zn": {
    "Z multi-vector": "{ Zreg1.D, Zreg2.D }"
  },
  "zm": {
    "Z multi-vector": "{ Zreg3.D, Zreg4.D }"
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
SUB ZA.D[Wreg1, imm1, VGX2], { Zreg1.D, Zreg2.D }, { Zreg3.D, Zreg4.D }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SUB--array-results--multiple-vectors---Subtract-multi-vector-from-multi-vector-with-ZA-array-vector-results-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svsub_write_za64[_u64]_vg1x4

ISA classification: SME2 + FEAT_SME_I16I64

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsub_write_za64%5B_u64%5D_vg1x4

### Signature (source notation)

```c
void svsub_write_za64[_u64]_vg1x4(uint32_t slice, svuint64x4_t zn, svuint64x4_t zm)
    __arm_streaming __arm_inout("za");
```

### Description

Subtract multi-vector from multi-vector with ZA array vector results

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Write / Subtract

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2,FEAT_SME_I16I64
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
  "slice": {
    "register+immediate": "Wreg1 + imm1"
  },
  "zn": {
    "Z multi-vector": "{ Zreg1.D - Zreg2.D }"
  },
  "zm": {
    "Z multi-vector": "{ Zreg3.D - Zreg4.D }"
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
SUB ZA.D[Wreg1, imm1, VGX4], { Zreg1.D - Zreg2.D }, { Zreg3.D - Zreg4.D }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SUB--array-results--multiple-vectors---Subtract-multi-vector-from-multi-vector-with-ZA-array-vector-results-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

