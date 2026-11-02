# SME / Predication / Partitioning / Propagate break to next partition — Part 1

## svbrkn[_b]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svbrkn%5B_b%5D_z

### Signature (source notation)

```c
svbool_t svbrkn[_b]_z(svbool_t pg, svbool_t op1, svbool_t op2);
```

### Description

Propagate break to next partition

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Predication / Partitioning / Propagate break to next partition

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
    "register": "Ptied2.B"
  }
}
```

### Result mapping

```json
[
  {
    "Ptied2.B": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
BRKN Ptied2.B, Pg/Z, Pop1.B, Ptied2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BRKN--Propagate-break-to-next-partition-

### Operation

Source operation ID: `SveOperation_svbrkn_b_z`

**Operation**



If `pg` is nonzero and if the last active element of `op1` is true, clear the inactive elements of `op2` and return the result.  Return a zero predicate otherwise.

