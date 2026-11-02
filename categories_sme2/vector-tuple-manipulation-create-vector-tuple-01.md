# SME2 / Vector tuple manipulation / Create vector tuple — Part 1

## svcreate2[_b]

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcreate2%5B_b%5D

### Signature (source notation)

```c
svboolx2_t svcreate2[_b](svbool_t x, svbool_t y);
```

### Description

Create a tuple of two predicate vectors. The tuple construction has no fixed instruction sequence; any emitted moves are register-allocation dependent.

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector tuple manipulation / Create vector tuple

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

## svcreate4[_b]

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcreate4%5B_b%5D

### Signature (source notation)

```c
svboolx4_t svcreate4[_b](svbool_t x, svbool_t y, svbool_t z, svbool_t w);
```

### Description

Create a tuple of four predicate vectors. The tuple construction has no fixed instruction sequence; any emitted moves are register-allocation dependent.

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector tuple manipulation / Create vector tuple

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

