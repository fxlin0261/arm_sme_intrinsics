# SME2 / ZA array / Zero — Part 1

## svzero_za64_vg1x2

ISA classification: SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svzero_za64_vg1x2

### Signature (source notation)

```c
void svzero_za64_vg1x2(uint32_t slice)
    __arm_streaming __arm_inout("za");
```

### Description

Zero ZA single-vector groups

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Zero

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
ZERO ZA.D[Wreg1, imm1, VGX2]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/ZERO--single-vector---Zero-ZA-single-vector-groups-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svzero_za64_vg1x4

ISA classification: SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svzero_za64_vg1x4

### Signature (source notation)

```c
void svzero_za64_vg1x4(uint32_t slice)
    __arm_streaming __arm_inout("za");
```

### Description

Zero ZA single-vector groups

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Zero

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
ZERO ZA.D[Wreg1, imm1, VGX4]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/ZERO--single-vector---Zero-ZA-single-vector-groups-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svzero_za64_vg2x1

ISA classification: SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svzero_za64_vg2x1

### Signature (source notation)

```c
void svzero_za64_vg2x1(uint32_t slice)
    __arm_streaming __arm_inout("za");
```

### Description

Zero ZA double-vector groups

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Zero

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
ZERO ZA.D[Wreg1, imm1:<imm1+1>]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/ZERO--double-vector---Zero-ZA-double-vector-groups-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svzero_za64_vg2x2

ISA classification: SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svzero_za64_vg2x2

### Signature (source notation)

```c
void svzero_za64_vg2x2(uint32_t slice)
    __arm_streaming __arm_inout("za");
```

### Description

Zero ZA double-vector groups

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Zero

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
ZERO ZA.D[Wreg1, imm1:<imm1+1>, VGX2]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/ZERO--double-vector---Zero-ZA-double-vector-groups-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svzero_za64_vg2x4

ISA classification: SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svzero_za64_vg2x4

### Signature (source notation)

```c
void svzero_za64_vg2x4(uint32_t slice)
    __arm_streaming __arm_inout("za");
```

### Description

Zero ZA double-vector groups

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Zero

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
ZERO ZA.D[Wreg1, imm1:<imm1+1>, VGX4]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/ZERO--double-vector---Zero-ZA-double-vector-groups-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svzero_za64_vg4x1

ISA classification: SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svzero_za64_vg4x1

### Signature (source notation)

```c
void svzero_za64_vg4x1(uint32_t slice)
    __arm_streaming __arm_inout("za");
```

### Description

Zero ZA quad-vector groups

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Zero

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
ZERO ZA.D[Wreg1, imm1:<imm1+3>]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/ZERO--quad-vector---Zero-ZA-quad-vector-groups-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svzero_za64_vg4x2

ISA classification: SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svzero_za64_vg4x2

### Signature (source notation)

```c
void svzero_za64_vg4x2(uint32_t slice)
    __arm_streaming __arm_inout("za");
```

### Description

Zero ZA quad-vector groups

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Zero

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
ZERO ZA.D[Wreg1, imm1:<imm1+3>, VGX2]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/ZERO--quad-vector---Zero-ZA-quad-vector-groups-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svzero_za64_vg4x4

ISA classification: SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svzero_za64_vg4x4

### Signature (source notation)

```c
void svzero_za64_vg4x4(uint32_t slice)
    __arm_streaming __arm_inout("za");
```

### Description

Zero ZA quad-vector groups

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Zero

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
ZERO ZA.D[Wreg1, imm1:<imm1+3>, VGX4]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/ZERO--quad-vector---Zero-ZA-quad-vector-groups-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

