# SME / Logical / NAND — Part 1

## svnand[_b]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svnand%5B_b%5D_z

### Signature (source notation)

```c
svbool_t svnand[_b]_z(svbool_t pg, svbool_t op1, svbool_t op2);
```

### Description

Bitwise NAND

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / NAND

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
NAND Presult.B, Pg/Z, Pop1.B, Pop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/NAND--Bitwise-NAND-predicates-

### Operation

Source operation ID: `SveOperation_svnand_b_z`

**Operation**



Return a predicate in which each active element *i* contains `~(op1[i] & op2[i])`. Set the inactive elements of the result to zero.

