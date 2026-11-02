# SME2 / Predication / Predicate extract — Part 1

## svpext_lane_c16

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svpext_lane_c16

### Signature (source notation)

```c
svbool_t svpext_lane_c16(svcount_t pnn, uint64_t imm);
```

### Description

Predicate extract from predicate-as-counter

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Predicate extract

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

```json
{
  "pnn": {
    "register": "PNreg1"
  },
  "imm": {
    "immediate": "imm1"
  }
}
```

### Result mapping

```json
[
  {
    "Preg1.H": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
PEXT Preg1.H, PNreg1[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/PEXT--predicate---Predicate-extract-from-predicate-as-counter-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svpext_lane_c16_x2

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svpext_lane_c16_x2

### Signature (source notation)

```c
svboolx2_t svpext_lane_c16_x2(svcount_t pnn, uint64_t imm);
```

### Description

Predicate extract pair from predicate-as-counter

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Predicate extract

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
  "value": "svboolx2_t"
}
```

### Argument preparation and constraints

```json
{
  "pnn": {
    "register": "PNreg1"
  },
  "imm": {
    "immediate": "imm1"
  }
}
```

### Result mapping

```json
[
  {
    "{ Preg1.H, Preg2.H }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
PEXT { Preg1.H, Preg2.H }, PNreg1[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/PEXT--predicate-pair---Predicate-extract-pair-from-predicate-as-counter-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svpext_lane_c32

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svpext_lane_c32

### Signature (source notation)

```c
svbool_t svpext_lane_c32(svcount_t pnn, uint64_t imm);
```

### Description

Predicate extract from predicate-as-counter

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Predicate extract

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

```json
{
  "pnn": {
    "register": "PNreg1"
  },
  "imm": {
    "immediate": "imm1"
  }
}
```

### Result mapping

```json
[
  {
    "Preg1.S": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
PEXT Preg1.S, PNreg1[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/PEXT--predicate---Predicate-extract-from-predicate-as-counter-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svpext_lane_c32_x2

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svpext_lane_c32_x2

### Signature (source notation)

```c
svboolx2_t svpext_lane_c32_x2(svcount_t pnn, uint64_t imm);
```

### Description

Predicate extract pair from predicate-as-counter

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Predicate extract

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
  "value": "svboolx2_t"
}
```

### Argument preparation and constraints

```json
{
  "pnn": {
    "register": "PNreg1"
  },
  "imm": {
    "immediate": "imm1"
  }
}
```

### Result mapping

```json
[
  {
    "{ Preg1.S, Preg2.S }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
PEXT { Preg1.S, Preg2.S }, PNreg1[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/PEXT--predicate-pair---Predicate-extract-pair-from-predicate-as-counter-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svpext_lane_c64

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svpext_lane_c64

### Signature (source notation)

```c
svbool_t svpext_lane_c64(svcount_t pnn, uint64_t imm);
```

### Description

Predicate extract from predicate-as-counter

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Predicate extract

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

```json
{
  "pnn": {
    "register": "PNreg1"
  },
  "imm": {
    "immediate": "imm1"
  }
}
```

### Result mapping

```json
[
  {
    "Preg1.D": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
PEXT Preg1.D, PNreg1[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/PEXT--predicate---Predicate-extract-from-predicate-as-counter-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svpext_lane_c64_x2

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svpext_lane_c64_x2

### Signature (source notation)

```c
svboolx2_t svpext_lane_c64_x2(svcount_t pnn, uint64_t imm);
```

### Description

Predicate extract pair from predicate-as-counter

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Predicate extract

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
  "value": "svboolx2_t"
}
```

### Argument preparation and constraints

```json
{
  "pnn": {
    "register": "PNreg1"
  },
  "imm": {
    "immediate": "imm1"
  }
}
```

### Result mapping

```json
[
  {
    "{ Preg1.D, Preg2.D }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
PEXT { Preg1.D, Preg2.D }, PNreg1[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/PEXT--predicate-pair---Predicate-extract-pair-from-predicate-as-counter-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svpext_lane_c8

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svpext_lane_c8

### Signature (source notation)

```c
svbool_t svpext_lane_c8(svcount_t pnn, uint64_t imm);
```

### Description

Predicate extract from predicate-as-counter

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Predicate extract

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

```json
{
  "pnn": {
    "register": "PNreg1"
  },
  "imm": {
    "immediate": "imm1"
  }
}
```

### Result mapping

```json
[
  {
    "Preg1.B": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
PEXT Preg1.B, PNreg1[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/PEXT--predicate---Predicate-extract-from-predicate-as-counter-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svpext_lane_c8_x2

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svpext_lane_c8_x2

### Signature (source notation)

```c
svboolx2_t svpext_lane_c8_x2(svcount_t pnn, uint64_t imm);
```

### Description

Predicate extract pair from predicate-as-counter

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Predicate extract

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
  "value": "svboolx2_t"
}
```

### Argument preparation and constraints

```json
{
  "pnn": {
    "register": "PNreg1"
  },
  "imm": {
    "immediate": "imm1"
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
PEXT { Preg1.B, Preg2.B }, PNreg1[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/PEXT--predicate-pair---Predicate-extract-pair-from-predicate-as-counter-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

