# SME2 / Predication / Predicated select — Part 1

## svpsel_lane_c16

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svpsel_lane_c16

### Signature (source notation)

```c
svcount_t svpsel_lane_c16(svcount_t pn, svbool_t pm, uint32_t idx);
```

### Description

Predicate select between predicate register or all-false

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Predicated select

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
  "element_bit_size": "16",
  "value": "svcount_t"
}
```

### Argument preparation and constraints

```json
{
  "pn": {
    "register": "Preg2"
  },
  "pm": {
    "register": "Preg3"
  },
  "idx": {
    "index": "[Wreg1, imm1]"
  }
}
```

### Result mapping

```json
[
  {
    "Preg1": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
PSEL Preg1, Preg2, Preg3.H[Wreg1, imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/PSEL--Predicate-select-between-predicate-register-or-all-false-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svpsel_lane_c32

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svpsel_lane_c32

### Signature (source notation)

```c
svcount_t svpsel_lane_c32(svcount_t pn, svbool_t pm, uint32_t idx);
```

### Description

Predicate select between predicate register or all-false

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Predicated select

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
  "element_bit_size": "32",
  "value": "svcount_t"
}
```

### Argument preparation and constraints

```json
{
  "pn": {
    "register": "Preg2"
  },
  "pm": {
    "register": "Preg3"
  },
  "idx": {
    "index": "[Wreg1, imm1]"
  }
}
```

### Result mapping

```json
[
  {
    "Preg1": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
PSEL Preg1, Preg2, Preg3.S[Wreg1, imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/PSEL--Predicate-select-between-predicate-register-or-all-false-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svpsel_lane_c64

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svpsel_lane_c64

### Signature (source notation)

```c
svcount_t svpsel_lane_c64(svcount_t pn, svbool_t pm, uint32_t idx);
```

### Description

Predicate select between predicate register or all-false

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Predicated select

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
  "element_bit_size": "64",
  "value": "svcount_t"
}
```

### Argument preparation and constraints

```json
{
  "pn": {
    "register": "Preg2"
  },
  "pm": {
    "register": "Preg3"
  },
  "idx": {
    "index": "[Wreg1, imm1]"
  }
}
```

### Result mapping

```json
[
  {
    "Preg1": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
PSEL Preg1, Preg2, Preg3.D[Wreg1, imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/PSEL--Predicate-select-between-predicate-register-or-all-false-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svpsel_lane_c8

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svpsel_lane_c8

### Signature (source notation)

```c
svcount_t svpsel_lane_c8(svcount_t pn, svbool_t pm, uint32_t idx);
```

### Description

Predicate select between predicate register or all-false

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Predicated select

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

```json
{
  "pn": {
    "register": "Preg2"
  },
  "pm": {
    "register": "Preg3"
  },
  "idx": {
    "index": "[Wreg1, imm1]"
  }
}
```

### Result mapping

```json
[
  {
    "Preg1": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
PSEL Preg1, Preg2, Preg3.B[Wreg1, imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/PSEL--Predicate-select-between-predicate-register-or-all-false-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

