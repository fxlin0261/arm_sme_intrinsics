# SME2 / Data type conversion / Reinterpret casts — Part 1

## svreinterpret[_b]

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svreinterpret%5B_b%5D

### Signature (source notation)

```c
svbool_t svreinterpret[_b](svcount_t count);
```

### Description

Reinterpret an svcount_t value as an svbool_t predicate. No instruction is emitted for the reinterpretation itself.

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Data type conversion / Reinterpret casts

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
  "element_bit_size": "1",
  "value": "svbool_t"
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

## svreinterpret[_c]

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svreinterpret%5B_c%5D

### Signature (source notation)

```c
svcount_t svreinterpret[_c](svbool_t pg);
```

### Description

Reinterpret an svbool_t predicate as an svcount_t value. No instruction is emitted for the reinterpretation itself.

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Data type conversion / Reinterpret casts

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
  "return_base_type": "count",
  "element_bit_size": "8",
  "value": "svcount_t"
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

