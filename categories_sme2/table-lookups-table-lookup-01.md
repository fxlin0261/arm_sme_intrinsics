# SME2 / Table lookups / Table lookup — Part 1

## svluti2_lane[_bf16]

ISA classification: SME2 + FEAT_LUT

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svluti2_lane%5B_bf16%5D

### Signature (source notation)

```c
svbfloat16_t svluti2_lane[_bf16](svbfloat16_t table, svuint8_t indices, uint64_t imm_idx);
```

### Description

Lookup table read with 2-bit indices (8-bit and 16-bit)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Table lookups / Table lookup

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2,FEAT_LUT
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
  "table": {
    "register": "Zreg2.H"
  },
  "indices": {
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
    "Zreg1.H": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
LUTI2 Zreg1.H, { Zreg2.H }, Zreg3[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/LUTI2--8-bit-and-16-bit---Lookup-table-read-with-2-bit-indices--8-bit-and-16-bit--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svluti2_lane[_f16]

ISA classification: SME2 + FEAT_LUT

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svluti2_lane%5B_f16%5D

### Signature (source notation)

```c
svfloat16_t svluti2_lane[_f16](svfloat16_t table, svuint8_t indices, uint64_t imm_idx);
```

### Description

Lookup table read with 2-bit indices (8-bit and 16-bit)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Table lookups / Table lookup

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2,FEAT_LUT
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
  "table": {
    "register": "Zreg2.H"
  },
  "indices": {
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
    "Zreg1.H": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
LUTI2 Zreg1.H, { Zreg2.H }, Zreg3[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/LUTI2--8-bit-and-16-bit---Lookup-table-read-with-2-bit-indices--8-bit-and-16-bit--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svluti2_lane[_s16]

ISA classification: SME2 + FEAT_LUT

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svluti2_lane%5B_s16%5D

### Signature (source notation)

```c
svint16_t svluti2_lane[_s16](svint16_t table, svuint8_t indices, uint64_t imm_idx);
```

### Description

Lookup table read with 2-bit indices (8-bit and 16-bit)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Table lookups / Table lookup

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2,FEAT_LUT
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
  "table": {
    "register": "Zreg2.H"
  },
  "indices": {
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
    "Zreg1.H": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
LUTI2 Zreg1.H, { Zreg2.H }, Zreg3[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/LUTI2--8-bit-and-16-bit---Lookup-table-read-with-2-bit-indices--8-bit-and-16-bit--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svluti2_lane[_s8]

ISA classification: SME2 + FEAT_LUT

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svluti2_lane%5B_s8%5D

### Signature (source notation)

```c
svint8_t svluti2_lane[_s8](svint8_t table, svuint8_t indices, uint64_t imm_idx);
```

### Description

Lookup table read with 2-bit indices (8-bit and 16-bit)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Table lookups / Table lookup

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2,FEAT_LUT
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
  "table": {
    "register": "Zreg2.B"
  },
  "indices": {
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
    "Zreg1.B": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
LUTI2 Zreg1.B, { Zreg2.B }, Zreg3[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/LUTI2--8-bit-and-16-bit---Lookup-table-read-with-2-bit-indices--8-bit-and-16-bit--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svluti2_lane[_u16]

ISA classification: SME2 + FEAT_LUT

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svluti2_lane%5B_u16%5D

### Signature (source notation)

```c
svuint16_t svluti2_lane[_u16](svuint16_t table, svuint8_t indices, uint64_t imm_idx);
```

### Description

Lookup table read with 2-bit indices (8-bit and 16-bit)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Table lookups / Table lookup

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2,FEAT_LUT
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
  "table": {
    "register": "Zreg2.H"
  },
  "indices": {
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
    "Zreg1.H": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
LUTI2 Zreg1.H, { Zreg2.H }, Zreg3[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/LUTI2--8-bit-and-16-bit---Lookup-table-read-with-2-bit-indices--8-bit-and-16-bit--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svluti2_lane[_u8]

ISA classification: SME2 + FEAT_LUT

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svluti2_lane%5B_u8%5D

### Signature (source notation)

```c
svuint8_t svluti2_lane[_u8](svuint8_t table, svuint8_t indices, uint64_t imm_idx);
```

### Description

Lookup table read with 2-bit indices (8-bit and 16-bit)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Table lookups / Table lookup

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2,FEAT_LUT
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
  "table": {
    "register": "Zreg2.B"
  },
  "indices": {
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
    "Zreg1.B": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
LUTI2 Zreg1.B, { Zreg2.B }, Zreg3[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/LUTI2--8-bit-and-16-bit---Lookup-table-read-with-2-bit-indices--8-bit-and-16-bit--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svluti4_lane[_bf16]

ISA classification: SME2 + FEAT_LUT

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svluti4_lane%5B_bf16%5D

### Signature (source notation)

```c
svbfloat16_t svluti4_lane[_bf16](svbfloat16_t table, svuint8_t indices, uint64_t imm_idx);
```

### Description

Lookup table read with 4-bit indices (8-bit and 16-bit)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Table lookups / Table lookup

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2,FEAT_LUT
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
  "table": {
    "register": "Zreg2.H"
  },
  "indices": {
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
    "Zreg1.H": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
LUTI4 Zreg1.H, { Zreg2.H }, Zreg3[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/LUTI4--8-bit-and-16-bit---Lookup-table-read-with-4-bit-indices--8-bit-and-16-bit--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svluti4_lane[_bf16_x2]

ISA classification: SME2 + FEAT_LUT

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svluti4_lane%5B_bf16_x2%5D

### Signature (source notation)

```c
svbfloat16_t svluti4_lane[_bf16_x2](svbfloat16x2_t table, svuint8_t indices, uint64_t imm_idx);
```

### Description

Lookup table read with 4-bit indices (8-bit and 16-bit)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Table lookups / Table lookup

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2,FEAT_LUT
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
  "table": {
    "Z multi-vector": "{ Zreg2.H, Zreg3.H }"
  },
  "indices": {
    "register": "Zreg4"
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
    "Zreg1.H": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
LUTI4 Zreg1.H, { Zreg2.H, Zreg3.H }, Zreg4[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/LUTI4--8-bit-and-16-bit---Lookup-table-read-with-4-bit-indices--8-bit-and-16-bit--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svluti4_lane[_f16]

ISA classification: SME2 + FEAT_LUT

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svluti4_lane%5B_f16%5D

### Signature (source notation)

```c
svfloat16_t svluti4_lane[_f16](svfloat16_t table, svuint8_t indices, uint64_t imm_idx);
```

### Description

Lookup table read with 4-bit indices (8-bit and 16-bit)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Table lookups / Table lookup

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2,FEAT_LUT
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
  "table": {
    "register": "Zreg2.H"
  },
  "indices": {
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
    "Zreg1.H": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
LUTI4 Zreg1.H, { Zreg2.H }, Zreg3[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/LUTI4--8-bit-and-16-bit---Lookup-table-read-with-4-bit-indices--8-bit-and-16-bit--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svluti4_lane[_f16_x2]

ISA classification: SME2 + FEAT_LUT

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svluti4_lane%5B_f16_x2%5D

### Signature (source notation)

```c
svfloat16_t svluti4_lane[_f16_x2](svfloat16x2_t table, svuint8_t indices, uint64_t imm_idx);
```

### Description

Lookup table read with 4-bit indices (8-bit and 16-bit)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Table lookups / Table lookup

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2,FEAT_LUT
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
  "table": {
    "Z multi-vector": "{ Zreg2.H, Zreg3.H }"
  },
  "indices": {
    "register": "Zreg4"
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
    "Zreg1.H": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
LUTI4 Zreg1.H, { Zreg2.H, Zreg3.H }, Zreg4[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/LUTI4--8-bit-and-16-bit---Lookup-table-read-with-4-bit-indices--8-bit-and-16-bit--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svluti4_lane[_s16]

ISA classification: SME2 + FEAT_LUT

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svluti4_lane%5B_s16%5D

### Signature (source notation)

```c
svint16_t svluti4_lane[_s16](svint16_t table, svuint8_t indices, uint64_t imm_idx);
```

### Description

Lookup table read with 4-bit indices (8-bit and 16-bit)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Table lookups / Table lookup

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2,FEAT_LUT
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
  "table": {
    "register": "Zreg2.H"
  },
  "indices": {
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
    "Zreg1.H": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
LUTI4 Zreg1.H, { Zreg2.H }, Zreg3[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/LUTI4--8-bit-and-16-bit---Lookup-table-read-with-4-bit-indices--8-bit-and-16-bit--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svluti4_lane[_s16_x2]

ISA classification: SME2 + FEAT_LUT

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svluti4_lane%5B_s16_x2%5D

### Signature (source notation)

```c
svint16_t svluti4_lane[_s16_x2](svint16x2_t table, svuint8_t indices, uint64_t imm_idx);
```

### Description

Lookup table read with 4-bit indices (8-bit and 16-bit)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Table lookups / Table lookup

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2,FEAT_LUT
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
  "table": {
    "Z multi-vector": "{ Zreg2.H, Zreg3.H }"
  },
  "indices": {
    "register": "Zreg4"
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
    "Zreg1.H": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
LUTI4 Zreg1.H, { Zreg2.H, Zreg3.H }, Zreg4[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/LUTI4--8-bit-and-16-bit---Lookup-table-read-with-4-bit-indices--8-bit-and-16-bit--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svluti4_lane[_s8]

ISA classification: SME2 + FEAT_LUT

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svluti4_lane%5B_s8%5D

### Signature (source notation)

```c
svint8_t svluti4_lane[_s8](svint8_t table, svuint8_t indices, uint64_t imm_idx);
```

### Description

Lookup table read with 4-bit indices (8-bit and 16-bit)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Table lookups / Table lookup

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2,FEAT_LUT
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
  "table": {
    "register": "Zreg2.B"
  },
  "indices": {
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
    "Zreg1.B": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
LUTI4 Zreg1.B, { Zreg2.B }, Zreg3[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/LUTI4--8-bit-and-16-bit---Lookup-table-read-with-4-bit-indices--8-bit-and-16-bit--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svluti4_lane[_u16]

ISA classification: SME2 + FEAT_LUT

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svluti4_lane%5B_u16%5D

### Signature (source notation)

```c
svuint16_t svluti4_lane[_u16](svuint16_t table, svuint8_t indices, uint64_t imm_idx);
```

### Description

Lookup table read with 4-bit indices (8-bit and 16-bit)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Table lookups / Table lookup

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2,FEAT_LUT
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
  "table": {
    "register": "Zreg2.H"
  },
  "indices": {
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
    "Zreg1.H": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
LUTI4 Zreg1.H, { Zreg2.H }, Zreg3[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/LUTI4--8-bit-and-16-bit---Lookup-table-read-with-4-bit-indices--8-bit-and-16-bit--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svluti4_lane[_u16_x2]

ISA classification: SME2 + FEAT_LUT

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svluti4_lane%5B_u16_x2%5D

### Signature (source notation)

```c
svuint16_t svluti4_lane[_u16_x2](svuint16x2_t table, svuint8_t indices, uint64_t imm_idx);
```

### Description

Lookup table read with 4-bit indices (8-bit and 16-bit)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Table lookups / Table lookup

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2,FEAT_LUT
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
  "table": {
    "Z multi-vector": "{ Zreg2.H, Zreg3.H }"
  },
  "indices": {
    "register": "Zreg4"
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
    "Zreg1.H": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
LUTI4 Zreg1.H, { Zreg2.H, Zreg3.H }, Zreg4[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/LUTI4--8-bit-and-16-bit---Lookup-table-read-with-4-bit-indices--8-bit-and-16-bit--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svluti4_lane[_u8]

ISA classification: SME2 + FEAT_LUT

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svluti4_lane%5B_u8%5D

### Signature (source notation)

```c
svuint8_t svluti4_lane[_u8](svuint8_t table, svuint8_t indices, uint64_t imm_idx);
```

### Description

Lookup table read with 4-bit indices (8-bit and 16-bit)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Table lookups / Table lookup

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2,FEAT_LUT
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
  "table": {
    "register": "Zreg2.B"
  },
  "indices": {
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
    "Zreg1.B": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
LUTI4 Zreg1.B, { Zreg2.B }, Zreg3[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/LUTI4--8-bit-and-16-bit---Lookup-table-read-with-4-bit-indices--8-bit-and-16-bit--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svtblq[_bf16]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svtblq%5B_bf16%5D

### Signature (source notation)

```c
svbfloat16_t svtblq[_bf16](svbfloat16_t zn, svuint16_t zm);
```

### Description

Programmable table lookup within each quadword vector segment (zeroing)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Table lookups / Table lookup

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p1)|FEAT_SME2p1
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
  "zn": {
    "register": "Zreg2.H"
  },
  "zm": {
    "register": "Zreg3.H"
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
TBLQ Zreg1.H, { Zreg2.H }, Zreg3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/TBLQ--Programmable-table-lookup-within-each-quadword-vector-segment--zeroing--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svtblq[_f16]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svtblq%5B_f16%5D

### Signature (source notation)

```c
svfloat16_t svtblq[_f16](svfloat16_t zn, svuint16_t zm);
```

### Description

Programmable table lookup within each quadword vector segment (zeroing)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Table lookups / Table lookup

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p1)|FEAT_SME2p1
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
  "zn": {
    "register": "Zreg2.H"
  },
  "zm": {
    "register": "Zreg3.H"
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
TBLQ Zreg1.H, { Zreg2.H }, Zreg3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/TBLQ--Programmable-table-lookup-within-each-quadword-vector-segment--zeroing--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svtblq[_f32]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svtblq%5B_f32%5D

### Signature (source notation)

```c
svfloat32_t svtblq[_f32](svfloat32_t zn, svuint32_t zm);
```

### Description

Programmable table lookup within each quadword vector segment (zeroing)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Table lookups / Table lookup

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p1)|FEAT_SME2p1
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
  "zn": {
    "register": "Zreg2.S"
  },
  "zm": {
    "register": "Zreg3.S"
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
TBLQ Zreg1.S, { Zreg2.S }, Zreg3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/TBLQ--Programmable-table-lookup-within-each-quadword-vector-segment--zeroing--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svtblq[_f64]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svtblq%5B_f64%5D

### Signature (source notation)

```c
svfloat64_t svtblq[_f64](svfloat64_t zn, svuint64_t zm);
```

### Description

Programmable table lookup within each quadword vector segment (zeroing)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Table lookups / Table lookup

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p1)|FEAT_SME2p1
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
  "zn": {
    "register": "Zreg2.D"
  },
  "zm": {
    "register": "Zreg3.D"
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
TBLQ Zreg1.D, { Zreg2.D }, Zreg3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/TBLQ--Programmable-table-lookup-within-each-quadword-vector-segment--zeroing--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svtblq[_mf8]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svtblq%5B_mf8%5D

### Signature (source notation)

```c
svmfloat8_t svtblq[_mf8](svmfloat8_t zn, svuint8_t zm);
```

### Description

Programmable table lookup within each quadword vector segment (zeroing)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Table lookups / Table lookup

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p1)|FEAT_SME2p1
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
  "zn": {
    "register": "Zreg2.B"
  },
  "zm": {
    "register": "Zreg3.B"
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
TBLQ Zreg1.B, { Zreg2.B }, Zreg3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/TBLQ--Programmable-table-lookup-within-each-quadword-vector-segment--zeroing--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svtblq[_s16]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svtblq%5B_s16%5D

### Signature (source notation)

```c
svint16_t svtblq[_s16](svint16_t zn, svuint16_t zm);
```

### Description

Programmable table lookup within each quadword vector segment (zeroing)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Table lookups / Table lookup

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p1)|FEAT_SME2p1
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
  "zn": {
    "register": "Zreg2.H"
  },
  "zm": {
    "register": "Zreg3.H"
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
TBLQ Zreg1.H, { Zreg2.H }, Zreg3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/TBLQ--Programmable-table-lookup-within-each-quadword-vector-segment--zeroing--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svtblq[_s32]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svtblq%5B_s32%5D

### Signature (source notation)

```c
svint32_t svtblq[_s32](svint32_t zn, svuint32_t zm);
```

### Description

Programmable table lookup within each quadword vector segment (zeroing)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Table lookups / Table lookup

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p1)|FEAT_SME2p1
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
  "zn": {
    "register": "Zreg2.S"
  },
  "zm": {
    "register": "Zreg3.S"
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
TBLQ Zreg1.S, { Zreg2.S }, Zreg3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/TBLQ--Programmable-table-lookup-within-each-quadword-vector-segment--zeroing--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svtblq[_s64]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svtblq%5B_s64%5D

### Signature (source notation)

```c
svint64_t svtblq[_s64](svint64_t zn, svuint64_t zm);
```

### Description

Programmable table lookup within each quadword vector segment (zeroing)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Table lookups / Table lookup

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p1)|FEAT_SME2p1
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
  "zn": {
    "register": "Zreg2.D"
  },
  "zm": {
    "register": "Zreg3.D"
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
TBLQ Zreg1.D, { Zreg2.D }, Zreg3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/TBLQ--Programmable-table-lookup-within-each-quadword-vector-segment--zeroing--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svtblq[_s8]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svtblq%5B_s8%5D

### Signature (source notation)

```c
svint8_t svtblq[_s8](svint8_t zn, svuint8_t zm);
```

### Description

Programmable table lookup within each quadword vector segment (zeroing)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Table lookups / Table lookup

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p1)|FEAT_SME2p1
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
  "zn": {
    "register": "Zreg2.B"
  },
  "zm": {
    "register": "Zreg3.B"
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
TBLQ Zreg1.B, { Zreg2.B }, Zreg3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/TBLQ--Programmable-table-lookup-within-each-quadword-vector-segment--zeroing--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svtblq[_u16]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svtblq%5B_u16%5D

### Signature (source notation)

```c
svuint16_t svtblq[_u16](svuint16_t zn, svuint16_t zm);
```

### Description

Programmable table lookup within each quadword vector segment (zeroing)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Table lookups / Table lookup

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p1)|FEAT_SME2p1
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
  "zn": {
    "register": "Zreg2.H"
  },
  "zm": {
    "register": "Zreg3.H"
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
TBLQ Zreg1.H, { Zreg2.H }, Zreg3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/TBLQ--Programmable-table-lookup-within-each-quadword-vector-segment--zeroing--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svtblq[_u32]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svtblq%5B_u32%5D

### Signature (source notation)

```c
svuint32_t svtblq[_u32](svuint32_t zn, svuint32_t zm);
```

### Description

Programmable table lookup within each quadword vector segment (zeroing)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Table lookups / Table lookup

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p1)|FEAT_SME2p1
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
  "zn": {
    "register": "Zreg2.S"
  },
  "zm": {
    "register": "Zreg3.S"
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
TBLQ Zreg1.S, { Zreg2.S }, Zreg3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/TBLQ--Programmable-table-lookup-within-each-quadword-vector-segment--zeroing--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svtblq[_u64]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svtblq%5B_u64%5D

### Signature (source notation)

```c
svuint64_t svtblq[_u64](svuint64_t zn, svuint64_t zm);
```

### Description

Programmable table lookup within each quadword vector segment (zeroing)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Table lookups / Table lookup

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p1)|FEAT_SME2p1
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
  "zn": {
    "register": "Zreg2.D"
  },
  "zm": {
    "register": "Zreg3.D"
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
TBLQ Zreg1.D, { Zreg2.D }, Zreg3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/TBLQ--Programmable-table-lookup-within-each-quadword-vector-segment--zeroing--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svtblq[_u8]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svtblq%5B_u8%5D

### Signature (source notation)

```c
svuint8_t svtblq[_u8](svuint8_t zn, svuint8_t zm);
```

### Description

Programmable table lookup within each quadword vector segment (zeroing)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Table lookups / Table lookup

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p1)|FEAT_SME2p1
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
  "zn": {
    "register": "Zreg2.B"
  },
  "zm": {
    "register": "Zreg3.B"
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
TBLQ Zreg1.B, { Zreg2.B }, Zreg3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/TBLQ--Programmable-table-lookup-within-each-quadword-vector-segment--zeroing--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

