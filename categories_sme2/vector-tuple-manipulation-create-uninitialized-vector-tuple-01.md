# SME2 / Vector tuple manipulation / Create uninitialized vector tuple — Part 1

## svundef2_b

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svundef2_b

### Signature (source notation)

```c
svboolx2_t svundef2_b();
```

### Description

Create an uninitialized tuple of two predicate vectors. No instruction is emitted for the uninitialized value itself.

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector tuple manipulation / Create uninitialized vector tuple

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p1)|FEAT_SME2
```

### Return type metadata

```json
{
  "return_base_type": "bool",
  "element_bit_size": "8",
  "value": "svboolx2_t"
}
```

### Argument preparation and constraints

Not supplied by source.

### Result mapping

Not supplied by source.

### Instruction mapping

Not supplied by source.

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svundef4_b

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svundef4_b

### Signature (source notation)

```c
svboolx4_t svundef4_b();
```

### Description

Create an uninitialized tuple of four predicate vectors. No instruction is emitted for the uninitialized value itself.

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector tuple manipulation / Create uninitialized vector tuple

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p1)|FEAT_SME2
```

### Return type metadata

```json
{
  "return_base_type": "bool",
  "element_bit_size": "8",
  "value": "svboolx4_t"
}
```

### Argument preparation and constraints

Not supplied by source.

### Result mapping

Not supplied by source.

### Instruction mapping

Not supplied by source.

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

