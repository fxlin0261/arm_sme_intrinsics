# SME / Predication / Partitioning / Break after first true condition — Part 1

## svbrka[_b]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svbrka%5B_b%5D_m

### Signature (source notation)

```c
svbool_t svbrka[_b]_m(svbool_t inactive, svbool_t pg, svbool_t op);
```

### Description

Break after first true condition

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Predication / Partitioning / Break after first true condition

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
  "inactive": {
    "register": "Ptied.B"
  },
  "pg": {
    "register": "Pg"
  },
  "op": {
    "register": "Pop.B"
  }
}
```

### Result mapping

```json
[
  {
    "Ptied.B": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
BRKA Ptied.B, Pg/M, Pop.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BRKA--Break-after-first-true-condition-

### Operation

Source operation ID: `SveOperation_svbrka_b_m`

**Operation**



Return a predicate in which each active element is true iff all previous active elements of `op` are false. Take the inactive elements of the result from the corresponding elements of `inactive`.

## svbrka[_b]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svbrka%5B_b%5D_z

### Signature (source notation)

```c
svbool_t svbrka[_b]_z(svbool_t pg, svbool_t op);
```

### Description

Break after first true condition

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Predication / Partitioning / Break after first true condition

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
  "op": {
    "register": "Pop.B"
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
BRKA Presult.B, Pg/Z, Pop.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BRKA--Break-after-first-true-condition-

### Operation

Source operation ID: `SveOperation_svbrka_b_z`

**Operation**



Return a predicate in which each active element is true iff all previous active elements of `op` are false. Set the inactive elements of the result to zero.

## svbrkpa[_b]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svbrkpa%5B_b%5D_z

### Signature (source notation)

```c
svbool_t svbrkpa[_b]_z(svbool_t pg, svbool_t op1, svbool_t op2);
```

### Description

Break after first true condition, propagating from previous partition

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Predication / Partitioning / Break after first true condition

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
BRKPA Presult.B, Pg/Z, Pop1.B, Pop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BRKPA--Break-after-first-true-condition--propagating-from-previous-partition-

### Operation

Source operation ID: `SveOperation_svbrkpa_b_z`

**Operation**



Return a predicate in which element *i* is true iff:




- element *i* is active;
- the last active element of `op1` is true; and
- all active elements of `op2` before *i* are false.

