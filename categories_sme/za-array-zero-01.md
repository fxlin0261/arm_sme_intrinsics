# SME / ZA array / Zero — Part 1

## svzero_mask_za

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svzero_mask_za

### Signature (source notation)

```c
void svzero_mask_za(uint64_t tile_mask)
    __arm_inout("za");
```

### Description

Zero a list of 64-bit element ZA tiles

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Zero

- SME attributes: `__arm_inout("za")`

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
  "tile_mask": {
    "immediate": "{mask}"
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
ZERO {mask}
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/ZERO--tiles---Zero-a-list-of-64-bit-element-ZA-tiles-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svzero_za

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svzero_za

### Signature (source notation)

```c
void svzero_za()
    __arm_out("za");
```

### Description

Zero a list of 64-bit element ZA tiles

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZA array / Zero

- SME attributes: `__arm_out("za")`

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
{}
```

### Result mapping

```json
[]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
ZERO {ZA}
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/ZERO--tiles---Zero-a-list-of-64-bit-element-ZA-tiles-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

