# SME2 / ZT0 Vector / Write — Part 1

## svwrite_lane_zt[_bf16]

ISA classification: SME2 + FEAT_SME_LUTv2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwrite_lane_zt%5B_bf16%5D

### Signature (source notation)

```c
void svwrite_lane_zt[_bf16](uint64_t zt0, svbfloat16_t zt, uint64_t idx)
    __arm_streaming __arm_inout("zt0");
```

### Description

Move vector register to ZT0

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZT0 Vector / Write

- SME attributes: `__arm_streaming`; `__arm_inout("zt0")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME_LUTv2
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
  "zt0": {
    "register": "ZT0"
  },
  "zt": {
    "register": "Zreg1"
  },
  "idx": {
    "immediate": "imm1"
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
MOVT ZT0[imm1, MUL VL], Zreg1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/MOVT--vector-to-table---Move-vector-register-to-ZT0-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svwrite_lane_zt[_f16]

ISA classification: SME2 + FEAT_SME_LUTv2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwrite_lane_zt%5B_f16%5D

### Signature (source notation)

```c
void svwrite_lane_zt[_f16](uint64_t zt0, svfloat16_t zt, uint64_t idx)
    __arm_streaming __arm_inout("zt0");
```

### Description

Move vector register to ZT0

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZT0 Vector / Write

- SME attributes: `__arm_streaming`; `__arm_inout("zt0")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME_LUTv2
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
  "zt0": {
    "register": "ZT0"
  },
  "zt": {
    "register": "Zreg1"
  },
  "idx": {
    "immediate": "imm1"
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
MOVT ZT0[imm1, MUL VL], Zreg1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/MOVT--vector-to-table---Move-vector-register-to-ZT0-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svwrite_lane_zt[_f32]

ISA classification: SME2 + FEAT_SME_LUTv2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwrite_lane_zt%5B_f32%5D

### Signature (source notation)

```c
void svwrite_lane_zt[_f32](uint64_t zt0, svfloat32_t zt, uint64_t idx)
    __arm_streaming __arm_inout("zt0");
```

### Description

Move vector register to ZT0

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZT0 Vector / Write

- SME attributes: `__arm_streaming`; `__arm_inout("zt0")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME_LUTv2
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
  "zt0": {
    "register": "ZT0"
  },
  "zt": {
    "register": "Zreg1"
  },
  "idx": {
    "immediate": "imm1"
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
MOVT ZT0[imm1, MUL VL], Zreg1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/MOVT--vector-to-table---Move-vector-register-to-ZT0-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svwrite_lane_zt[_f64]

ISA classification: SME2 + FEAT_SME_LUTv2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwrite_lane_zt%5B_f64%5D

### Signature (source notation)

```c
void svwrite_lane_zt[_f64](uint64_t zt0, svfloat64_t zt, uint64_t idx)
    __arm_streaming __arm_inout("zt0");
```

### Description

Move vector register to ZT0

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZT0 Vector / Write

- SME attributes: `__arm_streaming`; `__arm_inout("zt0")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME_LUTv2
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
  "zt0": {
    "register": "ZT0"
  },
  "zt": {
    "register": "Zreg1"
  },
  "idx": {
    "immediate": "imm1"
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
MOVT ZT0[imm1, MUL VL], Zreg1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/MOVT--vector-to-table---Move-vector-register-to-ZT0-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svwrite_lane_zt[_s16]

ISA classification: SME2 + FEAT_SME_LUTv2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwrite_lane_zt%5B_s16%5D

### Signature (source notation)

```c
void svwrite_lane_zt[_s16](uint64_t zt0, svint16_t zt, uint64_t idx)
    __arm_streaming __arm_inout("zt0");
```

### Description

Move vector register to ZT0

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZT0 Vector / Write

- SME attributes: `__arm_streaming`; `__arm_inout("zt0")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME_LUTv2
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
  "zt0": {
    "register": "ZT0"
  },
  "zt": {
    "register": "Zreg1"
  },
  "idx": {
    "immediate": "imm1"
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
MOVT ZT0[imm1, MUL VL], Zreg1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/MOVT--vector-to-table---Move-vector-register-to-ZT0-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svwrite_lane_zt[_s32]

ISA classification: SME2 + FEAT_SME_LUTv2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwrite_lane_zt%5B_s32%5D

### Signature (source notation)

```c
void svwrite_lane_zt[_s32](uint64_t zt0, svint32_t zt, uint64_t idx)
    __arm_streaming __arm_inout("zt0");
```

### Description

Move vector register to ZT0

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZT0 Vector / Write

- SME attributes: `__arm_streaming`; `__arm_inout("zt0")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME_LUTv2
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
  "zt0": {
    "register": "ZT0"
  },
  "zt": {
    "register": "Zreg1"
  },
  "idx": {
    "immediate": "imm1"
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
MOVT ZT0[imm1, MUL VL], Zreg1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/MOVT--vector-to-table---Move-vector-register-to-ZT0-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svwrite_lane_zt[_s64]

ISA classification: SME2 + FEAT_SME_LUTv2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwrite_lane_zt%5B_s64%5D

### Signature (source notation)

```c
void svwrite_lane_zt[_s64](uint64_t zt0, svint64_t zt, uint64_t idx)
    __arm_streaming __arm_inout("zt0");
```

### Description

Move vector register to ZT0

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZT0 Vector / Write

- SME attributes: `__arm_streaming`; `__arm_inout("zt0")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME_LUTv2
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
  "zt0": {
    "register": "ZT0"
  },
  "zt": {
    "register": "Zreg1"
  },
  "idx": {
    "immediate": "imm1"
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
MOVT ZT0[imm1, MUL VL], Zreg1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/MOVT--vector-to-table---Move-vector-register-to-ZT0-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svwrite_lane_zt[_s8]

ISA classification: SME2 + FEAT_SME_LUTv2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwrite_lane_zt%5B_s8%5D

### Signature (source notation)

```c
void svwrite_lane_zt[_s8](uint64_t zt0, svint8_t zt, uint64_t idx)
    __arm_streaming __arm_inout("zt0");
```

### Description

Move vector register to ZT0

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZT0 Vector / Write

- SME attributes: `__arm_streaming`; `__arm_inout("zt0")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME_LUTv2
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
  "zt0": {
    "register": "ZT0"
  },
  "zt": {
    "register": "Zreg1"
  },
  "idx": {
    "immediate": "imm1"
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
MOVT ZT0[imm1, MUL VL], Zreg1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/MOVT--vector-to-table---Move-vector-register-to-ZT0-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svwrite_lane_zt[_u16]

ISA classification: SME2 + FEAT_SME_LUTv2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwrite_lane_zt%5B_u16%5D

### Signature (source notation)

```c
void svwrite_lane_zt[_u16](uint64_t zt0, svuint16_t zt, uint64_t idx)
    __arm_streaming __arm_inout("zt0");
```

### Description

Move vector register to ZT0

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZT0 Vector / Write

- SME attributes: `__arm_streaming`; `__arm_inout("zt0")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME_LUTv2
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
  "zt0": {
    "register": "ZT0"
  },
  "zt": {
    "register": "Zreg1"
  },
  "idx": {
    "immediate": "imm1"
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
MOVT ZT0[imm1, MUL VL], Zreg1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/MOVT--vector-to-table---Move-vector-register-to-ZT0-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svwrite_lane_zt[_u32]

ISA classification: SME2 + FEAT_SME_LUTv2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwrite_lane_zt%5B_u32%5D

### Signature (source notation)

```c
void svwrite_lane_zt[_u32](uint64_t zt0, svuint32_t zt, uint64_t idx)
    __arm_streaming __arm_inout("zt0");
```

### Description

Move vector register to ZT0

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZT0 Vector / Write

- SME attributes: `__arm_streaming`; `__arm_inout("zt0")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME_LUTv2
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
  "zt0": {
    "register": "ZT0"
  },
  "zt": {
    "register": "Zreg1"
  },
  "idx": {
    "immediate": "imm1"
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
MOVT ZT0[imm1, MUL VL], Zreg1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/MOVT--vector-to-table---Move-vector-register-to-ZT0-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svwrite_lane_zt[_u64]

ISA classification: SME2 + FEAT_SME_LUTv2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwrite_lane_zt%5B_u64%5D

### Signature (source notation)

```c
void svwrite_lane_zt[_u64](uint64_t zt0, svuint64_t zt, uint64_t idx)
    __arm_streaming __arm_inout("zt0");
```

### Description

Move vector register to ZT0

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZT0 Vector / Write

- SME attributes: `__arm_streaming`; `__arm_inout("zt0")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME_LUTv2
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
  "zt0": {
    "register": "ZT0"
  },
  "zt": {
    "register": "Zreg1"
  },
  "idx": {
    "immediate": "imm1"
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
MOVT ZT0[imm1, MUL VL], Zreg1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/MOVT--vector-to-table---Move-vector-register-to-ZT0-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svwrite_lane_zt[_u8]

ISA classification: SME2 + FEAT_SME_LUTv2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwrite_lane_zt%5B_u8%5D

### Signature (source notation)

```c
void svwrite_lane_zt[_u8](uint64_t zt0, svuint8_t zt, uint64_t idx)
    __arm_streaming __arm_inout("zt0");
```

### Description

Move vector register to ZT0

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZT0 Vector / Write

- SME attributes: `__arm_streaming`; `__arm_inout("zt0")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME_LUTv2
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
  "zt0": {
    "register": "ZT0"
  },
  "zt": {
    "register": "Zreg1"
  },
  "idx": {
    "immediate": "imm1"
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
MOVT ZT0[imm1, MUL VL], Zreg1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/MOVT--vector-to-table---Move-vector-register-to-ZT0-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svwrite_zt[_bf16]

ISA classification: SME2 + FEAT_SME_LUTv2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwrite_zt%5B_bf16%5D

### Signature (source notation)

```c
void svwrite_zt[_bf16](uint64_t zt0, svbfloat16_t zt)
    __arm_streaming __arm_out("zt0");
```

### Description

Move vector register to ZT0

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZT0 Vector / Write

- SME attributes: `__arm_streaming`; `__arm_out("zt0")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME_LUTv2
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
  "zt0": {
    "register": "ZT0"
  },
  "zt": {
    "register": "Zreg1"
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
MOVT ZT0, Zreg1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/MOVT--vector-to-table---Move-vector-register-to-ZT0-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svwrite_zt[_f16]

ISA classification: SME2 + FEAT_SME_LUTv2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwrite_zt%5B_f16%5D

### Signature (source notation)

```c
void svwrite_zt[_f16](uint64_t zt0, svfloat16_t zt)
    __arm_streaming __arm_out("zt0");
```

### Description

Move vector register to ZT0

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZT0 Vector / Write

- SME attributes: `__arm_streaming`; `__arm_out("zt0")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME_LUTv2
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
  "zt0": {
    "register": "ZT0"
  },
  "zt": {
    "register": "Zreg1"
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
MOVT ZT0, Zreg1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/MOVT--vector-to-table---Move-vector-register-to-ZT0-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svwrite_zt[_f32]

ISA classification: SME2 + FEAT_SME_LUTv2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwrite_zt%5B_f32%5D

### Signature (source notation)

```c
void svwrite_zt[_f32](uint64_t zt0, svfloat32_t zt)
    __arm_streaming __arm_out("zt0");
```

### Description

Move vector register to ZT0

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZT0 Vector / Write

- SME attributes: `__arm_streaming`; `__arm_out("zt0")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME_LUTv2
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
  "zt0": {
    "register": "ZT0"
  },
  "zt": {
    "register": "Zreg1"
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
MOVT ZT0, Zreg1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/MOVT--vector-to-table---Move-vector-register-to-ZT0-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svwrite_zt[_f64]

ISA classification: SME2 + FEAT_SME_LUTv2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwrite_zt%5B_f64%5D

### Signature (source notation)

```c
void svwrite_zt[_f64](uint64_t zt0, svfloat64_t zt)
    __arm_streaming __arm_out("zt0");
```

### Description

Move vector register to ZT0

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZT0 Vector / Write

- SME attributes: `__arm_streaming`; `__arm_out("zt0")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME_LUTv2
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
  "zt0": {
    "register": "ZT0"
  },
  "zt": {
    "register": "Zreg1"
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
MOVT ZT0, Zreg1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/MOVT--vector-to-table---Move-vector-register-to-ZT0-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svwrite_zt[_s16]

ISA classification: SME2 + FEAT_SME_LUTv2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwrite_zt%5B_s16%5D

### Signature (source notation)

```c
void svwrite_zt[_s16](uint64_t zt0, svint16_t zt)
    __arm_streaming __arm_out("zt0");
```

### Description

Move vector register to ZT0

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZT0 Vector / Write

- SME attributes: `__arm_streaming`; `__arm_out("zt0")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME_LUTv2
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
  "zt0": {
    "register": "ZT0"
  },
  "zt": {
    "register": "Zreg1"
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
MOVT ZT0, Zreg1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/MOVT--vector-to-table---Move-vector-register-to-ZT0-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svwrite_zt[_s32]

ISA classification: SME2 + FEAT_SME_LUTv2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwrite_zt%5B_s32%5D

### Signature (source notation)

```c
void svwrite_zt[_s32](uint64_t zt0, svint32_t zt)
    __arm_streaming __arm_out("zt0");
```

### Description

Move vector register to ZT0

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZT0 Vector / Write

- SME attributes: `__arm_streaming`; `__arm_out("zt0")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME_LUTv2
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
  "zt0": {
    "register": "ZT0"
  },
  "zt": {
    "register": "Zreg1"
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
MOVT ZT0, Zreg1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/MOVT--vector-to-table---Move-vector-register-to-ZT0-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svwrite_zt[_s64]

ISA classification: SME2 + FEAT_SME_LUTv2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwrite_zt%5B_s64%5D

### Signature (source notation)

```c
void svwrite_zt[_s64](uint64_t zt0, svint64_t zt)
    __arm_streaming __arm_out("zt0");
```

### Description

Move vector register to ZT0

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZT0 Vector / Write

- SME attributes: `__arm_streaming`; `__arm_out("zt0")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME_LUTv2
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
  "zt0": {
    "register": "ZT0"
  },
  "zt": {
    "register": "Zreg1"
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
MOVT ZT0, Zreg1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/MOVT--vector-to-table---Move-vector-register-to-ZT0-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svwrite_zt[_s8]

ISA classification: SME2 + FEAT_SME_LUTv2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwrite_zt%5B_s8%5D

### Signature (source notation)

```c
void svwrite_zt[_s8](uint64_t zt0, svint8_t zt)
    __arm_streaming __arm_out("zt0");
```

### Description

Move vector register to ZT0

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZT0 Vector / Write

- SME attributes: `__arm_streaming`; `__arm_out("zt0")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME_LUTv2
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
  "zt0": {
    "register": "ZT0"
  },
  "zt": {
    "register": "Zreg1"
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
MOVT ZT0, Zreg1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/MOVT--vector-to-table---Move-vector-register-to-ZT0-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svwrite_zt[_u16]

ISA classification: SME2 + FEAT_SME_LUTv2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwrite_zt%5B_u16%5D

### Signature (source notation)

```c
void svwrite_zt[_u16](uint64_t zt0, svuint16_t zt)
    __arm_streaming __arm_out("zt0");
```

### Description

Move vector register to ZT0

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZT0 Vector / Write

- SME attributes: `__arm_streaming`; `__arm_out("zt0")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME_LUTv2
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
  "zt0": {
    "register": "ZT0"
  },
  "zt": {
    "register": "Zreg1"
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
MOVT ZT0, Zreg1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/MOVT--vector-to-table---Move-vector-register-to-ZT0-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svwrite_zt[_u32]

ISA classification: SME2 + FEAT_SME_LUTv2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwrite_zt%5B_u32%5D

### Signature (source notation)

```c
void svwrite_zt[_u32](uint64_t zt0, svuint32_t zt)
    __arm_streaming __arm_out("zt0");
```

### Description

Move vector register to ZT0

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZT0 Vector / Write

- SME attributes: `__arm_streaming`; `__arm_out("zt0")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME_LUTv2
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
  "zt0": {
    "register": "ZT0"
  },
  "zt": {
    "register": "Zreg1"
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
MOVT ZT0, Zreg1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/MOVT--vector-to-table---Move-vector-register-to-ZT0-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svwrite_zt[_u64]

ISA classification: SME2 + FEAT_SME_LUTv2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwrite_zt%5B_u64%5D

### Signature (source notation)

```c
void svwrite_zt[_u64](uint64_t zt0, svuint64_t zt)
    __arm_streaming __arm_out("zt0");
```

### Description

Move vector register to ZT0

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZT0 Vector / Write

- SME attributes: `__arm_streaming`; `__arm_out("zt0")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME_LUTv2
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
  "zt0": {
    "register": "ZT0"
  },
  "zt": {
    "register": "Zreg1"
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
MOVT ZT0, Zreg1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/MOVT--vector-to-table---Move-vector-register-to-ZT0-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svwrite_zt[_u8]

ISA classification: SME2 + FEAT_SME_LUTv2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwrite_zt%5B_u8%5D

### Signature (source notation)

```c
void svwrite_zt[_u8](uint64_t zt0, svuint8_t zt)
    __arm_streaming __arm_out("zt0");
```

### Description

Move vector register to ZT0

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZT0 Vector / Write

- SME attributes: `__arm_streaming`; `__arm_out("zt0")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME_LUTv2
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
  "zt0": {
    "register": "ZT0"
  },
  "zt": {
    "register": "Zreg1"
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
MOVT ZT0, Zreg1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/MOVT--vector-to-table---Move-vector-register-to-ZT0-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

