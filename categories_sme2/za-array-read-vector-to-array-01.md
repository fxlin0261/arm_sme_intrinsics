# SME2 / ZA array / Read / Vector to array — Part 1

## svread_za16_bf16_vg1x2

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svread_za16_bf16_vg1x2

### Signature (source notation)

```c
svbfloat16x2_t svread_za16_bf16_vg1x2(uint32_t slice)
    __arm_streaming __arm_in("za");
```

### Description

Move two ZA single-vector groups to two vector registers--an-alias-of-MOVA (array to vector, two registers)

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Read / Vector to array

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
MOV { Zreg1.D, Zreg2.D }, ZA.D[Wreg1, imm1, VGX2]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/MOV--array-to-vector--two-registers---Move-two-ZA-single-vector-groups-to-two-vector-registers--an-alias-of-MOVA--array-to-vector--two-registers--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svread_za16_bf16_vg1x4

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svread_za16_bf16_vg1x4

### Signature (source notation)

```c
svbfloat16x4_t svread_za16_bf16_vg1x4(uint32_t slice)
    __arm_streaming __arm_in("za");
```

### Description

Move four ZA single-vector groups to four vector registers--an-alias-of-MOVA (array to vector, four registers)

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Read / Vector to array

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
MOV { Zreg1.D - Zreg2.D }, ZA.D[Wreg1, imm1, VGX4]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/MOV--array-to-vector--four-registers---Move-four-ZA-single-vector-groups-to-four-vector-registers--an-alias-of-MOVA--array-to-vector--four-registers--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svread_za16_f16_vg1x2

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svread_za16_f16_vg1x2

### Signature (source notation)

```c
svfloat16x2_t svread_za16_f16_vg1x2(uint32_t slice)
    __arm_streaming __arm_in("za");
```

### Description

Move two ZA single-vector groups to two vector registers--an-alias-of-MOVA (array to vector, two registers)

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Read / Vector to array

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
MOV { Zreg1.D, Zreg2.D }, ZA.D[Wreg1, imm1, VGX2]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/MOV--array-to-vector--two-registers---Move-two-ZA-single-vector-groups-to-two-vector-registers--an-alias-of-MOVA--array-to-vector--two-registers--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svread_za16_f16_vg1x4

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svread_za16_f16_vg1x4

### Signature (source notation)

```c
svfloat16x4_t svread_za16_f16_vg1x4(uint32_t slice)
    __arm_streaming __arm_in("za");
```

### Description

Move four ZA single-vector groups to four vector registers--an-alias-of-MOVA (array to vector, four registers)

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Read / Vector to array

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
MOV { Zreg1.D - Zreg2.D }, ZA.D[Wreg1, imm1, VGX4]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/MOV--array-to-vector--four-registers---Move-four-ZA-single-vector-groups-to-four-vector-registers--an-alias-of-MOVA--array-to-vector--four-registers--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svread_za16_s16_vg1x2

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svread_za16_s16_vg1x2

### Signature (source notation)

```c
svint16x2_t svread_za16_s16_vg1x2(uint32_t slice)
    __arm_streaming __arm_in("za");
```

### Description

Move two ZA single-vector groups to two vector registers--an-alias-of-MOVA (array to vector, two registers)

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Read / Vector to array

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
MOV { Zreg1.D, Zreg2.D }, ZA.D[Wreg1, imm1, VGX2]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/MOV--array-to-vector--two-registers---Move-two-ZA-single-vector-groups-to-two-vector-registers--an-alias-of-MOVA--array-to-vector--two-registers--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svread_za16_s16_vg1x4

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svread_za16_s16_vg1x4

### Signature (source notation)

```c
svint16x4_t svread_za16_s16_vg1x4(uint32_t slice)
    __arm_streaming __arm_in("za");
```

### Description

Move four ZA single-vector groups to four vector registers--an-alias-of-MOVA (array to vector, four registers)

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Read / Vector to array

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
MOV { Zreg1.D - Zreg2.D }, ZA.D[Wreg1, imm1, VGX4]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/MOV--array-to-vector--four-registers---Move-four-ZA-single-vector-groups-to-four-vector-registers--an-alias-of-MOVA--array-to-vector--four-registers--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svread_za16_u16_vg1x2

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svread_za16_u16_vg1x2

### Signature (source notation)

```c
svuint16x2_t svread_za16_u16_vg1x2(uint32_t slice)
    __arm_streaming __arm_in("za");
```

### Description

Move two ZA single-vector groups to two vector registers--an-alias-of-MOVA (array to vector, two registers)

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Read / Vector to array

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
MOV { Zreg1.D, Zreg2.D }, ZA.D[Wreg1, imm1, VGX2]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/MOV--array-to-vector--two-registers---Move-two-ZA-single-vector-groups-to-two-vector-registers--an-alias-of-MOVA--array-to-vector--two-registers--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svread_za16_u16_vg1x4

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svread_za16_u16_vg1x4

### Signature (source notation)

```c
svuint16x4_t svread_za16_u16_vg1x4(uint32_t slice)
    __arm_streaming __arm_in("za");
```

### Description

Move four ZA single-vector groups to four vector registers--an-alias-of-MOVA (array to vector, four registers)

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Read / Vector to array

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
MOV { Zreg1.D - Zreg2.D }, ZA.D[Wreg1, imm1, VGX4]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/MOV--array-to-vector--four-registers---Move-four-ZA-single-vector-groups-to-four-vector-registers--an-alias-of-MOVA--array-to-vector--four-registers--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svread_za32_f32_vg1x2

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svread_za32_f32_vg1x2

### Signature (source notation)

```c
svfloat32x2_t svread_za32_f32_vg1x2(uint32_t slice)
    __arm_streaming __arm_in("za");
```

### Description

Move two ZA single-vector groups to two vector registers--an-alias-of-MOVA (array to vector, two registers)

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Read / Vector to array

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
MOV { Zreg1.D, Zreg2.D }, ZA.D[Wreg1, imm1, VGX2]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/MOV--array-to-vector--two-registers---Move-two-ZA-single-vector-groups-to-two-vector-registers--an-alias-of-MOVA--array-to-vector--two-registers--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svread_za32_f32_vg1x4

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svread_za32_f32_vg1x4

### Signature (source notation)

```c
svfloat32x4_t svread_za32_f32_vg1x4(uint32_t slice)
    __arm_streaming __arm_in("za");
```

### Description

Move four ZA single-vector groups to four vector registers--an-alias-of-MOVA (array to vector, four registers)

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Read / Vector to array

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
MOV { Zreg1.D - Zreg2.D }, ZA.D[Wreg1, imm1, VGX4]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/MOV--array-to-vector--four-registers---Move-four-ZA-single-vector-groups-to-four-vector-registers--an-alias-of-MOVA--array-to-vector--four-registers--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svread_za32_s32_vg1x2

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svread_za32_s32_vg1x2

### Signature (source notation)

```c
svint32x2_t svread_za32_s32_vg1x2(uint32_t slice)
    __arm_streaming __arm_in("za");
```

### Description

Move two ZA single-vector groups to two vector registers--an-alias-of-MOVA (array to vector, two registers)

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Read / Vector to array

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
MOV { Zreg1.D, Zreg2.D }, ZA.D[Wreg1, imm1, VGX2]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/MOV--array-to-vector--two-registers---Move-two-ZA-single-vector-groups-to-two-vector-registers--an-alias-of-MOVA--array-to-vector--two-registers--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svread_za32_s32_vg1x4

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svread_za32_s32_vg1x4

### Signature (source notation)

```c
svint32x4_t svread_za32_s32_vg1x4(uint32_t slice)
    __arm_streaming __arm_in("za");
```

### Description

Move four ZA single-vector groups to four vector registers--an-alias-of-MOVA (array to vector, four registers)

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Read / Vector to array

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
MOV { Zreg1.D - Zreg2.D }, ZA.D[Wreg1, imm1, VGX4]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/MOV--array-to-vector--four-registers---Move-four-ZA-single-vector-groups-to-four-vector-registers--an-alias-of-MOVA--array-to-vector--four-registers--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svread_za32_u32_vg1x2

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svread_za32_u32_vg1x2

### Signature (source notation)

```c
svuint32x2_t svread_za32_u32_vg1x2(uint32_t slice)
    __arm_streaming __arm_in("za");
```

### Description

Move two ZA single-vector groups to two vector registers--an-alias-of-MOVA (array to vector, two registers)

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Read / Vector to array

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
MOV { Zreg1.D, Zreg2.D }, ZA.D[Wreg1, imm1, VGX2]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/MOV--array-to-vector--two-registers---Move-two-ZA-single-vector-groups-to-two-vector-registers--an-alias-of-MOVA--array-to-vector--two-registers--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svread_za32_u32_vg1x4

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svread_za32_u32_vg1x4

### Signature (source notation)

```c
svuint32x4_t svread_za32_u32_vg1x4(uint32_t slice)
    __arm_streaming __arm_in("za");
```

### Description

Move four ZA single-vector groups to four vector registers--an-alias-of-MOVA (array to vector, four registers)

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Read / Vector to array

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
MOV { Zreg1.D - Zreg2.D }, ZA.D[Wreg1, imm1, VGX4]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/MOV--array-to-vector--four-registers---Move-four-ZA-single-vector-groups-to-four-vector-registers--an-alias-of-MOVA--array-to-vector--four-registers--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svread_za64_f64_vg1x2

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svread_za64_f64_vg1x2

### Signature (source notation)

```c
svfloat64x2_t svread_za64_f64_vg1x2(uint32_t slice)
    __arm_streaming __arm_in("za");
```

### Description

Move two ZA single-vector groups to two vector registers--an-alias-of-MOVA (array to vector, two registers)

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Read / Vector to array

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
MOV { Zreg1.D, Zreg2.D }, ZA.D[Wreg1, imm1, VGX2]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/MOV--array-to-vector--two-registers---Move-two-ZA-single-vector-groups-to-two-vector-registers--an-alias-of-MOVA--array-to-vector--two-registers--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svread_za64_f64_vg1x4

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svread_za64_f64_vg1x4

### Signature (source notation)

```c
svfloat64x4_t svread_za64_f64_vg1x4(uint32_t slice)
    __arm_streaming __arm_in("za");
```

### Description

Move four ZA single-vector groups to four vector registers--an-alias-of-MOVA (array to vector, four registers)

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Read / Vector to array

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
MOV { Zreg1.D - Zreg2.D }, ZA.D[Wreg1, imm1, VGX4]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/MOV--array-to-vector--four-registers---Move-four-ZA-single-vector-groups-to-four-vector-registers--an-alias-of-MOVA--array-to-vector--four-registers--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svread_za64_s64_vg1x2

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svread_za64_s64_vg1x2

### Signature (source notation)

```c
svint64x2_t svread_za64_s64_vg1x2(uint32_t slice)
    __arm_streaming __arm_in("za");
```

### Description

Move two ZA single-vector groups to two vector registers--an-alias-of-MOVA (array to vector, two registers)

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Read / Vector to array

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
MOV { Zreg1.D, Zreg2.D }, ZA.D[Wreg1, imm1, VGX2]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/MOV--array-to-vector--two-registers---Move-two-ZA-single-vector-groups-to-two-vector-registers--an-alias-of-MOVA--array-to-vector--two-registers--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svread_za64_s64_vg1x4

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svread_za64_s64_vg1x4

### Signature (source notation)

```c
svint64x4_t svread_za64_s64_vg1x4(uint32_t slice)
    __arm_streaming __arm_in("za");
```

### Description

Move four ZA single-vector groups to four vector registers--an-alias-of-MOVA (array to vector, four registers)

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Read / Vector to array

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
MOV { Zreg1.D - Zreg2.D }, ZA.D[Wreg1, imm1, VGX4]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/MOV--array-to-vector--four-registers---Move-four-ZA-single-vector-groups-to-four-vector-registers--an-alias-of-MOVA--array-to-vector--four-registers--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svread_za64_u64_vg1x2

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svread_za64_u64_vg1x2

### Signature (source notation)

```c
svuint64x2_t svread_za64_u64_vg1x2(uint32_t slice)
    __arm_streaming __arm_in("za");
```

### Description

Move two ZA single-vector groups to two vector registers--an-alias-of-MOVA (array to vector, two registers)

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Read / Vector to array

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
MOV { Zreg1.D, Zreg2.D }, ZA.D[Wreg1, imm1, VGX2]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/MOV--array-to-vector--two-registers---Move-two-ZA-single-vector-groups-to-two-vector-registers--an-alias-of-MOVA--array-to-vector--two-registers--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svread_za64_u64_vg1x4

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svread_za64_u64_vg1x4

### Signature (source notation)

```c
svuint64x4_t svread_za64_u64_vg1x4(uint32_t slice)
    __arm_streaming __arm_in("za");
```

### Description

Move four ZA single-vector groups to four vector registers--an-alias-of-MOVA (array to vector, four registers)

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Read / Vector to array

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
MOV { Zreg1.D - Zreg2.D }, ZA.D[Wreg1, imm1, VGX4]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/MOV--array-to-vector--four-registers---Move-four-ZA-single-vector-groups-to-four-vector-registers--an-alias-of-MOVA--array-to-vector--four-registers--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svread_za8_mf8_vg1x2

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svread_za8_mf8_vg1x2

### Signature (source notation)

```c
svmfloat8x2_t svread_za8_mf8_vg1x2(uint32_t slice)
    __arm_streaming __arm_in("za");
```

### Description

Move two ZA single-vector groups to two vector registers--an-alias-of-MOVA (array to vector, two registers)

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Read / Vector to array

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
MOV { Zreg1.D, Zreg2.D }, ZA.D[Wreg1, imm1, VGX2]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/MOV--array-to-vector--two-registers---Move-two-ZA-single-vector-groups-to-two-vector-registers--an-alias-of-MOVA--array-to-vector--two-registers--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svread_za8_mf8_vg1x4

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svread_za8_mf8_vg1x4

### Signature (source notation)

```c
svmfloat8x4_t svread_za8_mf8_vg1x4(uint32_t slice)
    __arm_streaming __arm_in("za");
```

### Description

Move four ZA single-vector groups to four vector registers--an-alias-of-MOVA (array to vector, four registers)

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Read / Vector to array

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
MOV { Zreg1.D - Zreg2.D }, ZA.D[Wreg1, imm1, VGX4]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/MOV--array-to-vector--four-registers---Move-four-ZA-single-vector-groups-to-four-vector-registers--an-alias-of-MOVA--array-to-vector--four-registers--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svread_za8_s8_vg1x2

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svread_za8_s8_vg1x2

### Signature (source notation)

```c
svint8x2_t svread_za8_s8_vg1x2(uint32_t slice)
    __arm_streaming __arm_in("za");
```

### Description

Move two ZA single-vector groups to two vector registers--an-alias-of-MOVA (array to vector, two registers)

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Read / Vector to array

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
MOV { Zreg1.D, Zreg2.D }, ZA.D[Wreg1, imm1, VGX2]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/MOV--array-to-vector--two-registers---Move-two-ZA-single-vector-groups-to-two-vector-registers--an-alias-of-MOVA--array-to-vector--two-registers--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svread_za8_s8_vg1x4

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svread_za8_s8_vg1x4

### Signature (source notation)

```c
svint8x4_t svread_za8_s8_vg1x4(uint32_t slice)
    __arm_streaming __arm_in("za");
```

### Description

Move four ZA single-vector groups to four vector registers--an-alias-of-MOVA (array to vector, four registers)

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Read / Vector to array

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
MOV { Zreg1.D - Zreg2.D }, ZA.D[Wreg1, imm1, VGX4]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/MOV--array-to-vector--four-registers---Move-four-ZA-single-vector-groups-to-four-vector-registers--an-alias-of-MOVA--array-to-vector--four-registers--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svread_za8_u8_vg1x2

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svread_za8_u8_vg1x2

### Signature (source notation)

```c
svuint8x2_t svread_za8_u8_vg1x2(uint32_t slice)
    __arm_streaming __arm_in("za");
```

### Description

Move two ZA single-vector groups to two vector registers--an-alias-of-MOVA (array to vector, two registers)

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Read / Vector to array

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
MOV { Zreg1.D, Zreg2.D }, ZA.D[Wreg1, imm1, VGX2]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/MOV--array-to-vector--two-registers---Move-two-ZA-single-vector-groups-to-two-vector-registers--an-alias-of-MOVA--array-to-vector--two-registers--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svread_za8_u8_vg1x4

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svread_za8_u8_vg1x4

### Signature (source notation)

```c
svuint8x4_t svread_za8_u8_vg1x4(uint32_t slice)
    __arm_streaming __arm_in("za");
```

### Description

Move four ZA single-vector groups to four vector registers--an-alias-of-MOVA (array to vector, four registers)

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Read / Vector to array

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
MOV { Zreg1.D - Zreg2.D }, ZA.D[Wreg1, imm1, VGX4]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/MOV--array-to-vector--four-registers---Move-four-ZA-single-vector-groups-to-four-vector-registers--an-alias-of-MOVA--array-to-vector--four-registers--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svreadz_za16_bf16_vg1x2

ISA classification: SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svreadz_za16_bf16_vg1x2

### Signature (source notation)

```c
svbfloat16x2_t svreadz_za16_bf16_vg1x2(uint32_t slice)
    __arm_streaming __arm_inout("za");
```

### Description

Move and zero two ZA single-vector groups to Z two-vector operand

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Read / Vector to array

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
MOVAZ { Zreg1.D, Zreg2.D }, ZA.D[Wreg1, imm1, VGX2]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/MOVAZ--array-to-vector--two-registers---Move-and-zero-two-ZA-single-vector-groups-to-Z-two-vector-operand-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svreadz_za16_bf16_vg1x4

ISA classification: SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svreadz_za16_bf16_vg1x4

### Signature (source notation)

```c
svbfloat16x4_t svreadz_za16_bf16_vg1x4(uint32_t slice)
    __arm_streaming __arm_inout("za");
```

### Description

Move and zero four ZA single-vector groups to Z four-vector operand

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Read / Vector to array

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
MOVAZ { Zreg1.D - Zreg2.D }, ZA.D[Wreg1, imm1, VGX4]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/MOVAZ--array-to-vector--four-registers---Move-and-zero-four-ZA-single-vector-groups-to-Z-four-vector-operand-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svreadz_za16_f16_vg1x2

ISA classification: SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svreadz_za16_f16_vg1x2

### Signature (source notation)

```c
svfloat16x2_t svreadz_za16_f16_vg1x2(uint32_t slice)
    __arm_streaming __arm_inout("za");
```

### Description

Move and zero two ZA single-vector groups to Z two-vector operand

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Read / Vector to array

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
MOVAZ { Zreg1.D, Zreg2.D }, ZA.D[Wreg1, imm1, VGX2]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/MOVAZ--array-to-vector--two-registers---Move-and-zero-two-ZA-single-vector-groups-to-Z-two-vector-operand-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svreadz_za16_f16_vg1x4

ISA classification: SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svreadz_za16_f16_vg1x4

### Signature (source notation)

```c
svfloat16x4_t svreadz_za16_f16_vg1x4(uint32_t slice)
    __arm_streaming __arm_inout("za");
```

### Description

Move and zero four ZA single-vector groups to Z four-vector operand

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Read / Vector to array

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
MOVAZ { Zreg1.D - Zreg2.D }, ZA.D[Wreg1, imm1, VGX4]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/MOVAZ--array-to-vector--four-registers---Move-and-zero-four-ZA-single-vector-groups-to-Z-four-vector-operand-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svreadz_za16_s16_vg1x2

ISA classification: SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svreadz_za16_s16_vg1x2

### Signature (source notation)

```c
svint16x2_t svreadz_za16_s16_vg1x2(uint32_t slice)
    __arm_streaming __arm_inout("za");
```

### Description

Move and zero two ZA single-vector groups to Z two-vector operand

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Read / Vector to array

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
MOVAZ { Zreg1.D, Zreg2.D }, ZA.D[Wreg1, imm1, VGX2]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/MOVAZ--array-to-vector--two-registers---Move-and-zero-two-ZA-single-vector-groups-to-Z-two-vector-operand-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svreadz_za16_s16_vg1x4

ISA classification: SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svreadz_za16_s16_vg1x4

### Signature (source notation)

```c
svint16x4_t svreadz_za16_s16_vg1x4(uint32_t slice)
    __arm_streaming __arm_inout("za");
```

### Description

Move and zero four ZA single-vector groups to Z four-vector operand

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Read / Vector to array

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
MOVAZ { Zreg1.D - Zreg2.D }, ZA.D[Wreg1, imm1, VGX4]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/MOVAZ--array-to-vector--four-registers---Move-and-zero-four-ZA-single-vector-groups-to-Z-four-vector-operand-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svreadz_za16_u16_vg1x2

ISA classification: SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svreadz_za16_u16_vg1x2

### Signature (source notation)

```c
svuint16x2_t svreadz_za16_u16_vg1x2(uint32_t slice)
    __arm_streaming __arm_inout("za");
```

### Description

Move and zero two ZA single-vector groups to Z two-vector operand

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Read / Vector to array

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
MOVAZ { Zreg1.D, Zreg2.D }, ZA.D[Wreg1, imm1, VGX2]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/MOVAZ--array-to-vector--two-registers---Move-and-zero-two-ZA-single-vector-groups-to-Z-two-vector-operand-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svreadz_za16_u16_vg1x4

ISA classification: SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svreadz_za16_u16_vg1x4

### Signature (source notation)

```c
svuint16x4_t svreadz_za16_u16_vg1x4(uint32_t slice)
    __arm_streaming __arm_inout("za");
```

### Description

Move and zero four ZA single-vector groups to Z four-vector operand

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Read / Vector to array

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
  "value": "svuint16x4_t"
}
```

### Argument preparation and constraints

```json
{
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
MOVAZ { Zreg1.D - Zreg2.D }, ZA.D[Wreg1, imm1, VGX4]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/MOVAZ--array-to-vector--four-registers---Move-and-zero-four-ZA-single-vector-groups-to-Z-four-vector-operand-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svreadz_za32_f32_vg1x2

ISA classification: SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svreadz_za32_f32_vg1x2

### Signature (source notation)

```c
svfloat32x2_t svreadz_za32_f32_vg1x2(uint32_t slice)
    __arm_streaming __arm_inout("za");
```

### Description

Move and zero two ZA single-vector groups to Z two-vector operand

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Read / Vector to array

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
  "value": "svfloat32x2_t"
}
```

### Argument preparation and constraints

```json
{
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
MOVAZ { Zreg1.D, Zreg2.D }, ZA.D[Wreg1, imm1, VGX2]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/MOVAZ--array-to-vector--two-registers---Move-and-zero-two-ZA-single-vector-groups-to-Z-two-vector-operand-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svreadz_za32_f32_vg1x4

ISA classification: SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svreadz_za32_f32_vg1x4

### Signature (source notation)

```c
svfloat32x4_t svreadz_za32_f32_vg1x4(uint32_t slice)
    __arm_streaming __arm_inout("za");
```

### Description

Move and zero four ZA single-vector groups to Z four-vector operand

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Read / Vector to array

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
  "value": "svfloat32x4_t"
}
```

### Argument preparation and constraints

```json
{
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
MOVAZ { Zreg1.D - Zreg2.D }, ZA.D[Wreg1, imm1, VGX4]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/MOVAZ--array-to-vector--four-registers---Move-and-zero-four-ZA-single-vector-groups-to-Z-four-vector-operand-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svreadz_za32_s32_vg1x2

ISA classification: SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svreadz_za32_s32_vg1x2

### Signature (source notation)

```c
svint32x2_t svreadz_za32_s32_vg1x2(uint32_t slice)
    __arm_streaming __arm_inout("za");
```

### Description

Move and zero two ZA single-vector groups to Z two-vector operand

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Read / Vector to array

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
  "value": "svint32x2_t"
}
```

### Argument preparation and constraints

```json
{
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
MOVAZ { Zreg1.D, Zreg2.D }, ZA.D[Wreg1, imm1, VGX2]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/MOVAZ--array-to-vector--two-registers---Move-and-zero-two-ZA-single-vector-groups-to-Z-two-vector-operand-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svreadz_za32_s32_vg1x4

ISA classification: SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svreadz_za32_s32_vg1x4

### Signature (source notation)

```c
svint32x4_t svreadz_za32_s32_vg1x4(uint32_t slice)
    __arm_streaming __arm_inout("za");
```

### Description

Move and zero four ZA single-vector groups to Z four-vector operand

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Read / Vector to array

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
  "value": "svint32x4_t"
}
```

### Argument preparation and constraints

```json
{
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
MOVAZ { Zreg1.D - Zreg2.D }, ZA.D[Wreg1, imm1, VGX4]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/MOVAZ--array-to-vector--four-registers---Move-and-zero-four-ZA-single-vector-groups-to-Z-four-vector-operand-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svreadz_za32_u32_vg1x2

ISA classification: SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svreadz_za32_u32_vg1x2

### Signature (source notation)

```c
svuint32x2_t svreadz_za32_u32_vg1x2(uint32_t slice)
    __arm_streaming __arm_inout("za");
```

### Description

Move and zero two ZA single-vector groups to Z two-vector operand

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Read / Vector to array

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
  "value": "svuint32x2_t"
}
```

### Argument preparation and constraints

```json
{
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
MOVAZ { Zreg1.D, Zreg2.D }, ZA.D[Wreg1, imm1, VGX2]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/MOVAZ--array-to-vector--two-registers---Move-and-zero-two-ZA-single-vector-groups-to-Z-two-vector-operand-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svreadz_za32_u32_vg1x4

ISA classification: SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svreadz_za32_u32_vg1x4

### Signature (source notation)

```c
svuint32x4_t svreadz_za32_u32_vg1x4(uint32_t slice)
    __arm_streaming __arm_inout("za");
```

### Description

Move and zero four ZA single-vector groups to Z four-vector operand

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Read / Vector to array

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
  "value": "svuint32x4_t"
}
```

### Argument preparation and constraints

```json
{
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
MOVAZ { Zreg1.D - Zreg2.D }, ZA.D[Wreg1, imm1, VGX4]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/MOVAZ--array-to-vector--four-registers---Move-and-zero-four-ZA-single-vector-groups-to-Z-four-vector-operand-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svreadz_za64_f64_vg1x2

ISA classification: SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svreadz_za64_f64_vg1x2

### Signature (source notation)

```c
svfloat64x2_t svreadz_za64_f64_vg1x2(uint32_t slice)
    __arm_streaming __arm_inout("za");
```

### Description

Move and zero two ZA single-vector groups to Z two-vector operand

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Read / Vector to array

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
  "value": "svfloat64x2_t"
}
```

### Argument preparation and constraints

```json
{
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
MOVAZ { Zreg1.D, Zreg2.D }, ZA.D[Wreg1, imm1, VGX2]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/MOVAZ--array-to-vector--two-registers---Move-and-zero-two-ZA-single-vector-groups-to-Z-two-vector-operand-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svreadz_za64_f64_vg1x4

ISA classification: SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svreadz_za64_f64_vg1x4

### Signature (source notation)

```c
svfloat64x4_t svreadz_za64_f64_vg1x4(uint32_t slice)
    __arm_streaming __arm_inout("za");
```

### Description

Move and zero four ZA single-vector groups to Z four-vector operand

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Read / Vector to array

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
  "value": "svfloat64x4_t"
}
```

### Argument preparation and constraints

```json
{
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
MOVAZ { Zreg1.D - Zreg2.D }, ZA.D[Wreg1, imm1, VGX4]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/MOVAZ--array-to-vector--four-registers---Move-and-zero-four-ZA-single-vector-groups-to-Z-four-vector-operand-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svreadz_za64_s64_vg1x2

ISA classification: SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svreadz_za64_s64_vg1x2

### Signature (source notation)

```c
svint64x2_t svreadz_za64_s64_vg1x2(uint32_t slice)
    __arm_streaming __arm_inout("za");
```

### Description

Move and zero two ZA single-vector groups to Z two-vector operand

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Read / Vector to array

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
  "value": "svint64x2_t"
}
```

### Argument preparation and constraints

```json
{
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
MOVAZ { Zreg1.D, Zreg2.D }, ZA.D[Wreg1, imm1, VGX2]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/MOVAZ--array-to-vector--two-registers---Move-and-zero-two-ZA-single-vector-groups-to-Z-two-vector-operand-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svreadz_za64_s64_vg1x4

ISA classification: SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svreadz_za64_s64_vg1x4

### Signature (source notation)

```c
svint64x4_t svreadz_za64_s64_vg1x4(uint32_t slice)
    __arm_streaming __arm_inout("za");
```

### Description

Move and zero four ZA single-vector groups to Z four-vector operand

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Read / Vector to array

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
  "value": "svint64x4_t"
}
```

### Argument preparation and constraints

```json
{
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
MOVAZ { Zreg1.D - Zreg2.D }, ZA.D[Wreg1, imm1, VGX4]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/MOVAZ--array-to-vector--four-registers---Move-and-zero-four-ZA-single-vector-groups-to-Z-four-vector-operand-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svreadz_za64_u64_vg1x2

ISA classification: SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svreadz_za64_u64_vg1x2

### Signature (source notation)

```c
svuint64x2_t svreadz_za64_u64_vg1x2(uint32_t slice)
    __arm_streaming __arm_inout("za");
```

### Description

Move and zero two ZA single-vector groups to Z two-vector operand

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Read / Vector to array

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
  "value": "svuint64x2_t"
}
```

### Argument preparation and constraints

```json
{
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
MOVAZ { Zreg1.D, Zreg2.D }, ZA.D[Wreg1, imm1, VGX2]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/MOVAZ--array-to-vector--two-registers---Move-and-zero-two-ZA-single-vector-groups-to-Z-two-vector-operand-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svreadz_za64_u64_vg1x4

ISA classification: SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svreadz_za64_u64_vg1x4

### Signature (source notation)

```c
svuint64x4_t svreadz_za64_u64_vg1x4(uint32_t slice)
    __arm_streaming __arm_inout("za");
```

### Description

Move and zero four ZA single-vector groups to Z four-vector operand

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Read / Vector to array

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
  "value": "svuint64x4_t"
}
```

### Argument preparation and constraints

```json
{
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
MOVAZ { Zreg1.D - Zreg2.D }, ZA.D[Wreg1, imm1, VGX4]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/MOVAZ--array-to-vector--four-registers---Move-and-zero-four-ZA-single-vector-groups-to-Z-four-vector-operand-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svreadz_za8_mf8_vg1x2

ISA classification: SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svreadz_za8_mf8_vg1x2

### Signature (source notation)

```c
svmfloat8x2_t svreadz_za8_mf8_vg1x2(uint32_t slice)
    __arm_streaming __arm_inout("za");
```

### Description

Move and zero two ZA single-vector groups to Z two-vector operand

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Read / Vector to array

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
  "value": "svmfloat8x2_t"
}
```

### Argument preparation and constraints

```json
{
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
MOVAZ { Zreg1.D, Zreg2.D }, ZA.D[Wreg1, imm1, VGX2]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/MOVAZ--array-to-vector--two-registers---Move-and-zero-two-ZA-single-vector-groups-to-Z-two-vector-operand-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svreadz_za8_mf8_vg1x4

ISA classification: SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svreadz_za8_mf8_vg1x4

### Signature (source notation)

```c
svmfloat8x4_t svreadz_za8_mf8_vg1x4(uint32_t slice)
    __arm_streaming __arm_inout("za");
```

### Description

Move and zero four ZA single-vector groups to Z four-vector operand

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Read / Vector to array

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
  "value": "svmfloat8x4_t"
}
```

### Argument preparation and constraints

```json
{
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
MOVAZ { Zreg1.D - Zreg2.D }, ZA.D[Wreg1, imm1, VGX4]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/MOVAZ--array-to-vector--four-registers---Move-and-zero-four-ZA-single-vector-groups-to-Z-four-vector-operand-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svreadz_za8_s8_vg1x2

ISA classification: SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svreadz_za8_s8_vg1x2

### Signature (source notation)

```c
svint8x2_t svreadz_za8_s8_vg1x2(uint32_t slice)
    __arm_streaming __arm_inout("za");
```

### Description

Move and zero two ZA single-vector groups to Z two-vector operand

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Read / Vector to array

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
  "value": "svint8x2_t"
}
```

### Argument preparation and constraints

```json
{
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
MOVAZ { Zreg1.D, Zreg2.D }, ZA.D[Wreg1, imm1, VGX2]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/MOVAZ--array-to-vector--two-registers---Move-and-zero-two-ZA-single-vector-groups-to-Z-two-vector-operand-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svreadz_za8_s8_vg1x4

ISA classification: SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svreadz_za8_s8_vg1x4

### Signature (source notation)

```c
svint8x4_t svreadz_za8_s8_vg1x4(uint32_t slice)
    __arm_streaming __arm_inout("za");
```

### Description

Move and zero four ZA single-vector groups to Z four-vector operand

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Read / Vector to array

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
  "value": "svint8x4_t"
}
```

### Argument preparation and constraints

```json
{
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
MOVAZ { Zreg1.D - Zreg2.D }, ZA.D[Wreg1, imm1, VGX4]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/MOVAZ--array-to-vector--four-registers---Move-and-zero-four-ZA-single-vector-groups-to-Z-four-vector-operand-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

