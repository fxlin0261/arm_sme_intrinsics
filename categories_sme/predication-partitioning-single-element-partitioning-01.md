# SME / Predication / Partitioning / Single-element partitioning — Part 1

## svpfirst[_b]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svpfirst%5B_b%5D

### Signature (source notation)

```c
svbool_t svpfirst[_b](svbool_t pg, svbool_t op);
```

### Description

Set the first active predicate element to true

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Predication / Partitioning / Single-element partitioning

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
    "register": "Ptied.B"
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
PFIRST Ptied.B, Pg, Ptied.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/PFIRST--Set-the-First-active-predicate-element-to-true-

### Operation

Source operation ID: `SveOperation_svpfirst_b`

**Operation**



Return the result of setting the first active element in `op` to true.

## svpnext_b16

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svpnext_b16

### Signature (source notation)

```c
svbool_t svpnext_b16(svbool_t pg, svbool_t op);
```

### Description

Find next active predicate

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Predication / Partitioning / Single-element partitioning

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
  "element_bit_size": "16",
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
    "register": "Ptied.H"
  }
}
```

### Result mapping

```json
[
  {
    "Ptied.H": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
PNEXT Ptied.H, Pg, Ptied.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/PNEXT--Find-next-active-predicate-

### Operation

Source operation ID: `SveOperation_svpnext_b16`

**Operation**



Find the lowest active element index *i* for which all active and inactive elements of `op` from *i* onwards are false.  If such an index exists, return a predicate in which element *i* is true and all other elements are false.  Return an all-false predicate otherwise.



Only the lowest bit of each element is ever set; the upper bits are always zero.

## svpnext_b32

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svpnext_b32

### Signature (source notation)

```c
svbool_t svpnext_b32(svbool_t pg, svbool_t op);
```

### Description

Find next active predicate

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Predication / Partitioning / Single-element partitioning

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
  "element_bit_size": "32",
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
    "register": "Ptied.S"
  }
}
```

### Result mapping

```json
[
  {
    "Ptied.S": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
PNEXT Ptied.S, Pg, Ptied.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/PNEXT--Find-next-active-predicate-

### Operation

Source operation ID: `SveOperation_svpnext_b16`

**Operation**



Find the lowest active element index *i* for which all active and inactive elements of `op` from *i* onwards are false.  If such an index exists, return a predicate in which element *i* is true and all other elements are false.  Return an all-false predicate otherwise.



Only the lowest bit of each element is ever set; the upper bits are always zero.

## svpnext_b64

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svpnext_b64

### Signature (source notation)

```c
svbool_t svpnext_b64(svbool_t pg, svbool_t op);
```

### Description

Find next active predicate

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Predication / Partitioning / Single-element partitioning

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
  "element_bit_size": "64",
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
    "register": "Ptied.D"
  }
}
```

### Result mapping

```json
[
  {
    "Ptied.D": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
PNEXT Ptied.D, Pg, Ptied.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/PNEXT--Find-next-active-predicate-

### Operation

Source operation ID: `SveOperation_svpnext_b16`

**Operation**



Find the lowest active element index *i* for which all active and inactive elements of `op` from *i* onwards are false.  If such an index exists, return a predicate in which element *i* is true and all other elements are false.  Return an all-false predicate otherwise.



Only the lowest bit of each element is ever set; the upper bits are always zero.

## svpnext_b8

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svpnext_b8

### Signature (source notation)

```c
svbool_t svpnext_b8(svbool_t pg, svbool_t op);
```

### Description

Find next active predicate

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Predication / Partitioning / Single-element partitioning

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
    "register": "Ptied.B"
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
PNEXT Ptied.B, Pg, Ptied.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/PNEXT--Find-next-active-predicate-

### Operation

Source operation ID: `SveOperation_svpnext_b8`

**Operation**



Find the lowest active element index *i* for which all active and inactive elements of `op` from *i* onwards are false.  If such an index exists, return a predicate in which element *i* is true and all other elements are false.  Return an all-false predicate otherwise.

