# SME2 / ZT0 Vector / Zero — Part 1

## svzero_zt

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svzero_zt

### Signature (source notation)

```c
void svzero_zt(uint64_t zt)
    __arm_out("zt0");
```

### Description

Zero ZT0

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: ZT0 Vector / Zero

- SME attributes: `__arm_out("zt0")`

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
  "zt": {
    "register": "ZT0"
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
ZERO { ZT0 }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/ZERO--table---Zero-ZT0-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

