# SME / Logical / OR-NOT — Part 1

## svorn[_b]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svorn%5B_b%5D_z

### Signature (source notation)

```c
svbool_t svorn[_b]_z(svbool_t pg, svbool_t op1, svbool_t op2);
```

### Description

Bitwise inclusive OR, inverting second argument

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / OR-NOT

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME
```

### Return type metadata

```json
{
  "return_base_type": "bool",
  "element_bit_size": "8",
  "value": "svbool_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Pg"
  },
  "op1": {
    "register": "Pop1.B"
  },
  "op2": {
    "register": "Pop2.B"
  }
}
```

### Result mapping

```json
[
  {
    "Presult.B": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
ORN Presult.B, Pg/Z, Pop1.B, Pop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ORN--predicates---Bitwise-inclusive-OR-inverted-predicate-

### Operation

Source operation ID: `SveOperation_svorn_b_z`

**Operation**



Return a predicate in which each active element *i* contains `op1[i] | ~op2[i]`. Set the inactive elements of the result to zero.

