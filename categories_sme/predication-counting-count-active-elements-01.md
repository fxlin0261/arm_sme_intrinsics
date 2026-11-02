# SME / Predication / Counting / Count active elements — Part 1

## svcntp_b16

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcntp_b16

### Signature (source notation)

```c
uint64_t svcntp_b16(svbool_t pg, svbool_t op);
```

### Description

Count set predicate bits

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Predication / Counting / Count active elements

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
  "return_base_type": "uint",
  "element_bit_size": "64",
  "value": "uint64_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Pg"
  },
  "op": {
    "register": "Pop.H"
  }
}
```

### Result mapping

```json
[
  {
    "Xresult": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
CNTP Xresult, Pg, Pop.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CNTP--predicate---Set-scalar-to-count-of-true-predicate-elements-

### Operation

Source operation ID: `SveOperation_svcntp_b16`

**Operation**



Return the number of active elements *i* for which the low bit of `op[i]` is true.

## svcntp_b32

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcntp_b32

### Signature (source notation)

```c
uint64_t svcntp_b32(svbool_t pg, svbool_t op);
```

### Description

Count set predicate bits

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Predication / Counting / Count active elements

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
  "return_base_type": "uint",
  "element_bit_size": "64",
  "value": "uint64_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Pg"
  },
  "op": {
    "register": "Pop.S"
  }
}
```

### Result mapping

```json
[
  {
    "Xresult": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
CNTP Xresult, Pg, Pop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CNTP--predicate---Set-scalar-to-count-of-true-predicate-elements-

### Operation

Source operation ID: `SveOperation_svcntp_b16`

**Operation**



Return the number of active elements *i* for which the low bit of `op[i]` is true.

## svcntp_b64

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcntp_b64

### Signature (source notation)

```c
uint64_t svcntp_b64(svbool_t pg, svbool_t op);
```

### Description

Count set predicate bits

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Predication / Counting / Count active elements

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
  "return_base_type": "uint",
  "element_bit_size": "64",
  "value": "uint64_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Pg"
  },
  "op": {
    "register": "Pop.D"
  }
}
```

### Result mapping

```json
[
  {
    "Xresult": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
CNTP Xresult, Pg, Pop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CNTP--predicate---Set-scalar-to-count-of-true-predicate-elements-

### Operation

Source operation ID: `SveOperation_svcntp_b16`

**Operation**



Return the number of active elements *i* for which the low bit of `op[i]` is true.

## svcntp_b8

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcntp_b8

### Signature (source notation)

```c
uint64_t svcntp_b8(svbool_t pg, svbool_t op);
```

### Description

Count set predicate bits

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Predication / Counting / Count active elements

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
  "return_base_type": "uint",
  "element_bit_size": "64",
  "value": "uint64_t"
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
    "Xresult": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
CNTP Xresult, Pg, Pop.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CNTP--predicate---Set-scalar-to-count-of-true-predicate-elements-

### Operation

Source operation ID: `SveOperation_svcntp_b8`

**Operation**



Return the number of active elements *i* for which `op[i]` is true.

## svcntp_c16

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcntp_c16

### Signature (source notation)

```c
uint64_t svcntp_c16(svcount_t pnn, uint64_t vl);
```

### Description

Set scalar to count from predicate-as-counter

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Counting / Count active elements

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
  "return_base_type": "uint64_t",
  "element_bit_size": "64",
  "value": "uint64_t"
}
```

### Argument preparation and constraints

```json
{
  "pnn": {
    "register": "PNreg1.H"
  },
  "vl": {
    "immediate": "<VL>"
  }
}
```

### Result mapping

```json
[
  {
    "Xreg1": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
CNTP Xreg1, PNreg1.H, <VL>
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CNTP--predicate-as-counter---Set-scalar-to-count-from-predicate-as-counter-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svcntp_c32

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcntp_c32

### Signature (source notation)

```c
uint64_t svcntp_c32(svcount_t pnn, uint64_t vl);
```

### Description

Set scalar to count from predicate-as-counter

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Counting / Count active elements

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
  "return_base_type": "uint64_t",
  "element_bit_size": "64",
  "value": "uint64_t"
}
```

### Argument preparation and constraints

```json
{
  "pnn": {
    "register": "PNreg1.S"
  },
  "vl": {
    "immediate": "<VL>"
  }
}
```

### Result mapping

```json
[
  {
    "Xreg1": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
CNTP Xreg1, PNreg1.S, <VL>
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CNTP--predicate-as-counter---Set-scalar-to-count-from-predicate-as-counter-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svcntp_c64

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcntp_c64

### Signature (source notation)

```c
uint64_t svcntp_c64(svcount_t pnn, uint64_t vl);
```

### Description

Set scalar to count from predicate-as-counter

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Counting / Count active elements

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
  "return_base_type": "uint64_t",
  "element_bit_size": "64",
  "value": "uint64_t"
}
```

### Argument preparation and constraints

```json
{
  "pnn": {
    "register": "PNreg1.D"
  },
  "vl": {
    "immediate": "<VL>"
  }
}
```

### Result mapping

```json
[
  {
    "Xreg1": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
CNTP Xreg1, PNreg1.D, <VL>
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CNTP--predicate-as-counter---Set-scalar-to-count-from-predicate-as-counter-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svcntp_c8

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcntp_c8

### Signature (source notation)

```c
uint64_t svcntp_c8(svcount_t pnn, uint64_t vl);
```

### Description

Set scalar to count from predicate-as-counter

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Counting / Count active elements

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
  "return_base_type": "uint64_t",
  "element_bit_size": "64",
  "value": "uint64_t"
}
```

### Argument preparation and constraints

```json
{
  "pnn": {
    "register": "PNreg1.B"
  },
  "vl": {
    "immediate": "<VL>"
  }
}
```

### Result mapping

```json
[
  {
    "Xreg1": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
CNTP Xreg1, PNreg1.B, <VL>
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CNTP--predicate-as-counter---Set-scalar-to-count-from-predicate-as-counter-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

