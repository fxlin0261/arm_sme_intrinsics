# SME2 / Vector tuple manipulation / Set vector in tuple — Part 1

## svset2[_b]

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svset2%5B_b%5D

### Signature (source notation)

```c
svboolx2_t svset2[_b](svboolx2_t tuple, uint64_t imm_index, svbool_t x);
```

### Description

Change one predicate vector in a tuple of two predicate vectors.

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector tuple manipulation / Set vector in tuple

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

```json
{
  "tuple": {
    "register sequence": "Preg1.B, Preg2.B"
  },
  "imm_index": {
    "immediate": "<num>"
  },
  "x": {
    "register": "Preg3.B"
  }
}
```

### Result mapping

```json
[
  {
    "{ Preg1.B, Preg2.B }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
MOV Preg<num>.B, Preg3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/MOV--Move-predicate--unpredicated---an-alias-of-ORR--predicates--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svset4[_b]

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svset4%5B_b%5D

### Signature (source notation)

```c
svboolx4_t svset4[_b](svboolx4_t tuple, uint64_t imm_index, svbool_t x);
```

### Description

Change one predicate vector in a tuple of four predicate vectors.

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector tuple manipulation / Set vector in tuple

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

```json
{
  "tuple": {
    "register sequence": "Preg1.B, Preg2.B, Preg3.B, Preg4.B"
  },
  "imm_index": {
    "immediate": "<num>"
  },
  "x": {
    "register": "Preg5.B"
  }
}
```

### Result mapping

```json
[
  {
    "{ Preg1.B, Preg2.B, Preg3.B, Preg4.B }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
MOV Preg<num>.B, Preg5.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/MOV--Move-predicate--unpredicated---an-alias-of-ORR--predicates--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

