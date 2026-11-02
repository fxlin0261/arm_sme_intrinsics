# SME / ZA array / Accumulate / Add — Part 1

## svaddha_za32[_s32]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svaddha_za32%5B_s32%5D_m

### Signature (source notation)

```c
void svaddha_za32[_s32]_m(uint64_t tile, svbool_t pn, svbool_t pm, svint32_t zn)
    __arm_streaming __arm_inout("za");
```

### Description

Add horizontally vector elements to ZA tile

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Add

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
    "ZA array tile": "ZA0.S"
  },
  "pn": {
    "register": "Preg1"
  },
  "pm": {
    "register": "Preg2"
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
ADDHA ZA0.S, Preg1/M, Preg2/M, Zreg1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/ADDHA--Add-horizontally-vector-elements-to-ZA-tile-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svaddha_za32[_u32]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svaddha_za32%5B_u32%5D_m

### Signature (source notation)

```c
void svaddha_za32[_u32]_m(uint64_t tile, svbool_t pn, svbool_t pm, svuint32_t zn)
    __arm_streaming __arm_inout("za");
```

### Description

Add horizontally vector elements to ZA tile

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Add

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
    "ZA array tile": "ZA0.S"
  },
  "pn": {
    "register": "Preg1"
  },
  "pm": {
    "register": "Preg2"
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
ADDHA ZA0.S, Preg1/M, Preg2/M, Zreg1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/ADDHA--Add-horizontally-vector-elements-to-ZA-tile-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svaddha_za64[_s64]_m

ISA classification: SME + FEAT_SME_I16I64

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svaddha_za64%5B_s64%5D_m

### Signature (source notation)

```c
void svaddha_za64[_s64]_m(uint64_t tile, svbool_t pn, svbool_t pm, svint64_t zn)
    __arm_streaming __arm_inout("za");
```

### Description

Add horizontally vector elements to ZA tile

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Add

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME_I16I64
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
    "ZA array tile": "ZA0.D"
  },
  "pn": {
    "register": "Preg1"
  },
  "pm": {
    "register": "Preg2"
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
ADDHA ZA0.D, Preg1/M, Preg2/M, Zreg1.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/ADDHA--Add-horizontally-vector-elements-to-ZA-tile-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svaddha_za64[_u64]_m

ISA classification: SME + FEAT_SME_I16I64

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svaddha_za64%5B_u64%5D_m

### Signature (source notation)

```c
void svaddha_za64[_u64]_m(uint64_t tile, svbool_t pn, svbool_t pm, svuint64_t zn)
    __arm_streaming __arm_inout("za");
```

### Description

Add horizontally vector elements to ZA tile

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Accumulate / Add

- SME attributes: `__arm_streaming`; `__arm_inout("za")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME_I16I64
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
    "ZA array tile": "ZA0.D"
  },
  "pn": {
    "register": "Preg1"
  },
  "pm": {
    "register": "Preg2"
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
ADDHA ZA0.D, Preg1/M, Preg2/M, Zreg1.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/ADDHA--Add-horizontally-vector-elements-to-ZA-tile-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

