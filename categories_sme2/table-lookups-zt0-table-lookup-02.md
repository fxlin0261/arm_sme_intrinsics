# SME2 / Table lookups / ZT0 table lookup — Part 2

## svluti4_lane_zt_u16_x2

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svluti4_lane_zt_u16_x2

### Signature (source notation)

```c
svuint16x2_t svluti4_lane_zt_u16_x2(uint64_t zt, svuint8_t zn, uint64_t imm_idx)
    __arm_streaming __arm_in("zt0");
```

### Description

Lookup table read with 4-bit indexes (two registers)

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Table lookups / ZT0 table lookup

- SME attributes: `__arm_streaming`; `__arm_in("zt0")`

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
  "zt": {
    "register": "ZT0"
  },
  "zn": {
    "register": "Zreg3"
  },
  "imm_idx": {
    "immediate": "imm1"
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
LUTI4 { Zreg1.H, Zreg2.H }, ZT0, Zreg3[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/LUTI4--two-registers---Lookup-table-read-with-4-bit-indexes--two-registers--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svluti4_lane_zt_u16_x4

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svluti4_lane_zt_u16_x4

### Signature (source notation)

```c
svuint16x4_t svluti4_lane_zt_u16_x4(uint64_t zt, svuint8_t zn, uint64_t imm_idx)
    __arm_streaming __arm_in("zt0");
```

### Description

Lookup table read with 4-bit indexes (four registers)

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Table lookups / ZT0 table lookup

- SME attributes: `__arm_streaming`; `__arm_in("zt0")`

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
  "zt": {
    "register": "ZT0"
  },
  "zn": {
    "register": "Zreg3"
  },
  "imm_idx": {
    "immediate": "imm1"
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
LUTI4 { Zreg1.H - Zreg2.H }, ZT0, Zreg3[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/LUTI4--four-registers--16-bit-and-32-bit---Lookup-table-read-with-4-bit-indexes--four-registers--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svluti4_lane_zt_u32

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svluti4_lane_zt_u32

### Signature (source notation)

```c
svuint32_t svluti4_lane_zt_u32(uint64_t zt, svuint8_t zn, uint64_t imm_idx)
    __arm_streaming __arm_in("zt0");
```

### Description

Lookup table read with 4-bit indexes (single)

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Table lookups / ZT0 table lookup

- SME attributes: `__arm_streaming`; `__arm_in("zt0")`

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
  "value": "svuint32_t"
}
```

### Argument preparation and constraints

```json
{
  "zt": {
    "register": "ZT0"
  },
  "zn": {
    "register": "Zreg2"
  },
  "imm_idx": {
    "immediate": "imm1"
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
LUTI4 Zreg1.S, ZT0, Zreg2[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/LUTI4--single---Lookup-table-read-with-4-bit-indexes--single--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svluti4_lane_zt_u32_x2

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svluti4_lane_zt_u32_x2

### Signature (source notation)

```c
svuint32x2_t svluti4_lane_zt_u32_x2(uint64_t zt, svuint8_t zn, uint64_t imm_idx)
    __arm_streaming __arm_in("zt0");
```

### Description

Lookup table read with 4-bit indexes (two registers)

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Table lookups / ZT0 table lookup

- SME attributes: `__arm_streaming`; `__arm_in("zt0")`

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
  "zt": {
    "register": "ZT0"
  },
  "zn": {
    "register": "Zreg3"
  },
  "imm_idx": {
    "immediate": "imm1"
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
LUTI4 { Zreg1.S, Zreg2.S }, ZT0, Zreg3[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/LUTI4--two-registers---Lookup-table-read-with-4-bit-indexes--two-registers--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svluti4_lane_zt_u32_x4

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svluti4_lane_zt_u32_x4

### Signature (source notation)

```c
svuint32x4_t svluti4_lane_zt_u32_x4(uint64_t zt, svuint8_t zn, uint64_t imm_idx)
    __arm_streaming __arm_in("zt0");
```

### Description

Lookup table read with 4-bit indexes (four registers)

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Table lookups / ZT0 table lookup

- SME attributes: `__arm_streaming`; `__arm_in("zt0")`

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
  "zt": {
    "register": "ZT0"
  },
  "zn": {
    "register": "Zreg3"
  },
  "imm_idx": {
    "immediate": "imm1"
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
LUTI4 { Zreg1.S - Zreg2.S }, ZT0, Zreg3[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/LUTI4--four-registers--16-bit-and-32-bit---Lookup-table-read-with-4-bit-indexes--four-registers--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svluti4_lane_zt_u8

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svluti4_lane_zt_u8

### Signature (source notation)

```c
svuint8_t svluti4_lane_zt_u8(uint64_t zt, svuint8_t zn, uint64_t imm_idx)
    __arm_streaming __arm_in("zt0");
```

### Description

Lookup table read with 4-bit indexes (single)

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Table lookups / ZT0 table lookup

- SME attributes: `__arm_streaming`; `__arm_in("zt0")`

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
  "value": "svuint8_t"
}
```

### Argument preparation and constraints

```json
{
  "zt": {
    "register": "ZT0"
  },
  "zn": {
    "register": "Zreg2"
  },
  "imm_idx": {
    "immediate": "imm1"
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
LUTI4 Zreg1.B, ZT0, Zreg2[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/LUTI4--single---Lookup-table-read-with-4-bit-indexes--single--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svluti4_lane_zt_u8_x2

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svluti4_lane_zt_u8_x2

### Signature (source notation)

```c
svuint8x2_t svluti4_lane_zt_u8_x2(uint64_t zt, svuint8_t zn, uint64_t imm_idx)
    __arm_streaming __arm_in("zt0");
```

### Description

Lookup table read with 4-bit indexes (two registers)

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Table lookups / ZT0 table lookup

- SME attributes: `__arm_streaming`; `__arm_in("zt0")`

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
  "zt": {
    "register": "ZT0"
  },
  "zn": {
    "register": "Zreg3"
  },
  "imm_idx": {
    "immediate": "imm1"
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
LUTI4 { Zreg1.B, Zreg2.B }, ZT0, Zreg3[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/LUTI4--two-registers---Lookup-table-read-with-4-bit-indexes--two-registers--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svluti4_zt_s8_x4

ISA classification: SME2 + FEAT_SME_LUTv2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svluti4_zt_s8_x4

### Signature (source notation)

```c
svint8x4_t svluti4_zt_s8_x4(uint64_t zt0, svuint8x2_t zn)
    __arm_streaming __arm_in("zt0");
```

### Description

Lookup table read with 4-bit indexes and 8-bit elements (four registers)

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Table lookups / ZT0 table lookup

- SME attributes: `__arm_streaming`; `__arm_in("zt0")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME_LUTv2
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
  "zt0": {
    "register": "ZT0"
  },
  "zn": {
    "Z multi-vector": "{ Zreg3, Zreg4 }"
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
LUTI4 { Zreg1.B - Zreg2.B }, ZT0, { Zreg3, Zreg4 }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/LUTI4--four-registers--8-bit---Lookup-table-read-with-4-bit-indexes-and-8-bit-elements--four-registers--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svluti4_zt_u8_x4

ISA classification: SME2 + FEAT_SME_LUTv2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svluti4_zt_u8_x4

### Signature (source notation)

```c
svuint8x4_t svluti4_zt_u8_x4(uint64_t zt0, svuint8x2_t zn)
    __arm_streaming __arm_in("zt0");
```

### Description

Lookup table read with 4-bit indexes and 8-bit elements (four registers)

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Table lookups / ZT0 table lookup

- SME attributes: `__arm_streaming`; `__arm_in("zt0")`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME_LUTv2
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
  "zt0": {
    "register": "ZT0"
  },
  "zn": {
    "Z multi-vector": "{ Zreg3, Zreg4 }"
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
LUTI4 { Zreg1.B - Zreg2.B }, ZT0, { Zreg3, Zreg4 }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/LUTI4--four-registers--8-bit---Lookup-table-read-with-4-bit-indexes-and-8-bit-elements--four-registers--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

