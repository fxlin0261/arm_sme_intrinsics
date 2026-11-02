# SME / Predication / Predicate move — Part 1

## svpmov[_s16]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svpmov%5B_s16%5D

### Signature (source notation)

```c
svbool_t svpmov[_s16](svint16_t zn);
```

### Description

Bitwise AND predicates

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Predicate move

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p1)|FEAT_SME2p1
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
  "zn": {
    "register": "Zreg1"
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
PMOV Preg1.H, Zreg1[0]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/PTRUE--predicate---Initialize-predicate-from-named-constraint-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svpmov[_s32]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svpmov%5B_s32%5D

### Signature (source notation)

```c
svbool_t svpmov[_s32](svint32_t zn);
```

### Description

Bitwise AND predicates

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Predicate move

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p1)|FEAT_SME2p1
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
  "zn": {
    "register": "Zreg1"
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
PMOV Preg1.S, Zreg1[0]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/PTRUE--predicate---Initialize-predicate-from-named-constraint-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svpmov[_s64]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svpmov%5B_s64%5D

### Signature (source notation)

```c
svbool_t svpmov[_s64](svint64_t zn);
```

### Description

Bitwise AND predicates

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Predicate move

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p1)|FEAT_SME2p1
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
  "zn": {
    "register": "Zreg1"
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
PMOV Preg1.D, Zreg1[0]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/PTRUE--predicate---Initialize-predicate-from-named-constraint-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svpmov[_s8]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svpmov%5B_s8%5D

### Signature (source notation)

```c
svbool_t svpmov[_s8](svint8_t zn);
```

### Description

Move predicate from vector

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Predicate move

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p1)|FEAT_SME2p1
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
  "zn": {
    "register": "Zreg1"
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
PMOV Preg1.B, Zreg1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/PMOV--to-predicate---Move-predicate-from-vector-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svpmov[_u16]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svpmov%5B_u16%5D

### Signature (source notation)

```c
svbool_t svpmov[_u16](svuint16_t zn);
```

### Description

Bitwise AND predicates

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Predicate move

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p1)|FEAT_SME2p1
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
  "zn": {
    "register": "Zreg1"
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
PMOV Preg1.H, Zreg1[0]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/PTRUE--predicate---Initialize-predicate-from-named-constraint-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svpmov[_u32]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svpmov%5B_u32%5D

### Signature (source notation)

```c
svbool_t svpmov[_u32](svuint32_t zn);
```

### Description

Bitwise AND predicates

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Predicate move

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p1)|FEAT_SME2p1
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
  "zn": {
    "register": "Zreg1"
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
PMOV Preg1.S, Zreg1[0]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/PTRUE--predicate---Initialize-predicate-from-named-constraint-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svpmov[_u64]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svpmov%5B_u64%5D

### Signature (source notation)

```c
svbool_t svpmov[_u64](svuint64_t zn);
```

### Description

Bitwise AND predicates

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Predicate move

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p1)|FEAT_SME2p1
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
  "zn": {
    "register": "Zreg1"
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
PMOV Preg1.D, Zreg1[0]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/PTRUE--predicate---Initialize-predicate-from-named-constraint-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svpmov[_u8]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svpmov%5B_u8%5D

### Signature (source notation)

```c
svbool_t svpmov[_u8](svuint8_t zn);
```

### Description

Move predicate from vector

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Predicate move

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p1)|FEAT_SME2p1
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
  "zn": {
    "register": "Zreg1"
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
PMOV Preg1.B, Zreg1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/PMOV--to-predicate---Move-predicate-from-vector-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svpmov_lane[_s16]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svpmov_lane%5B_s16%5D

### Signature (source notation)

```c
svbool_t svpmov_lane[_s16](svint16_t zn, uint64_t imm);
```

### Description

Bitwise AND predicates

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Predicate move

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p1)|FEAT_SME2p1
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
  "zn": {
    "register": "Zreg1"
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
PMOV Preg1.H, Zreg1[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/PTRUE--predicate---Initialize-predicate-from-named-constraint-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svpmov_lane[_s16]_m

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svpmov_lane%5B_s16%5D_m

### Signature (source notation)

```c
svint16_t svpmov_lane[_s16]_m(svint16_t zd, svbool_t pn, uint64_t imm);
```

### Description

Move predicate to vector

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Predicate move

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p1)|FEAT_SME2p1
```

### Return type metadata

```json
{
  "return_base_type": "int16",
  "element_bit_size": "16",
  "value": "svint16_t"
}
```

### Argument preparation and constraints

```json
{
  "zd": {
    "register": "Zreg1"
  },
  "pn": {
    "register": "Preg1"
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
    "Zreg1[imm1]": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
PMOV Zreg1[imm1], Preg1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/PMOV--to-vector---Move-predicate-to-vector-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svpmov_lane[_s32]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svpmov_lane%5B_s32%5D

### Signature (source notation)

```c
svbool_t svpmov_lane[_s32](svint32_t zn, uint64_t imm);
```

### Description

Bitwise AND predicates

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Predicate move

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p1)|FEAT_SME2p1
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
  "zn": {
    "register": "Zreg1"
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
PMOV Preg1.S, Zreg1[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/PTRUE--predicate---Initialize-predicate-from-named-constraint-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svpmov_lane[_s32]_m

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svpmov_lane%5B_s32%5D_m

### Signature (source notation)

```c
svint32_t svpmov_lane[_s32]_m(svint32_t zd, svbool_t pn, uint64_t imm);
```

### Description

Move predicate to vector

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Predicate move

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p1)|FEAT_SME2p1
```

### Return type metadata

```json
{
  "return_base_type": "int32",
  "element_bit_size": "32",
  "value": "svint32_t"
}
```

### Argument preparation and constraints

```json
{
  "zd": {
    "register": "Zreg1"
  },
  "pn": {
    "register": "Preg1"
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
    "Zreg1[imm1]": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
PMOV Zreg1[imm1], Preg1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/PMOV--to-vector---Move-predicate-to-vector-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svpmov_lane[_s64]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svpmov_lane%5B_s64%5D

### Signature (source notation)

```c
svbool_t svpmov_lane[_s64](svint64_t zn, uint64_t imm);
```

### Description

Bitwise AND predicates

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Predicate move

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p1)|FEAT_SME2p1
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
  "zn": {
    "register": "Zreg1"
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
PMOV Preg1.D, Zreg1[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/PTRUE--predicate---Initialize-predicate-from-named-constraint-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svpmov_lane[_s64]_m

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svpmov_lane%5B_s64%5D_m

### Signature (source notation)

```c
svint64_t svpmov_lane[_s64]_m(svint64_t zd, svbool_t pn, uint64_t imm);
```

### Description

Move predicate to vector

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Predicate move

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p1)|FEAT_SME2p1
```

### Return type metadata

```json
{
  "return_base_type": "int64",
  "element_bit_size": "64",
  "value": "svint64_t"
}
```

### Argument preparation and constraints

```json
{
  "zd": {
    "register": "Zreg1"
  },
  "pn": {
    "register": "Preg1"
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
    "Zreg1[imm1]": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
PMOV Zreg1[imm1], Preg1.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/PMOV--to-vector---Move-predicate-to-vector-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svpmov_lane[_s8]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svpmov_lane%5B_s8%5D

### Signature (source notation)

```c
svbool_t svpmov_lane[_s8](svint8_t zn, uint64_t imm);
```

### Description

Move predicate from vector

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Predicate move

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p1)|FEAT_SME2p1
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
  "zn": {
    "register": "Zreg1"
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
PMOV Preg1.B, Zreg1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/PMOV--to-predicate---Move-predicate-from-vector-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svpmov_lane[_u16]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svpmov_lane%5B_u16%5D

### Signature (source notation)

```c
svbool_t svpmov_lane[_u16](svuint16_t zn, uint64_t imm);
```

### Description

Bitwise AND predicates

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Predicate move

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p1)|FEAT_SME2p1
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
  "zn": {
    "register": "Zreg1"
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
PMOV Preg1.H, Zreg1[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/PTRUE--predicate---Initialize-predicate-from-named-constraint-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svpmov_lane[_u16]_m

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svpmov_lane%5B_u16%5D_m

### Signature (source notation)

```c
svuint16_t svpmov_lane[_u16]_m(svuint16_t zd, svbool_t pn, uint64_t imm);
```

### Description

Move predicate to vector

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Predicate move

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p1)|FEAT_SME2p1
```

### Return type metadata

```json
{
  "return_base_type": "uint16",
  "element_bit_size": "16",
  "value": "svuint16_t"
}
```

### Argument preparation and constraints

```json
{
  "zd": {
    "register": "Zreg1"
  },
  "pn": {
    "register": "Preg1"
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
    "Zreg1[imm1]": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
PMOV Zreg1[imm1], Preg1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/PMOV--to-vector---Move-predicate-to-vector-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svpmov_lane[_u32]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svpmov_lane%5B_u32%5D

### Signature (source notation)

```c
svbool_t svpmov_lane[_u32](svuint32_t zn, uint64_t imm);
```

### Description

Bitwise AND predicates

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Predicate move

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p1)|FEAT_SME2p1
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
  "zn": {
    "register": "Zreg1"
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
PMOV Preg1.S, Zreg1[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/PTRUE--predicate---Initialize-predicate-from-named-constraint-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svpmov_lane[_u32]_m

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svpmov_lane%5B_u32%5D_m

### Signature (source notation)

```c
svuint32_t svpmov_lane[_u32]_m(svuint32_t zd, svbool_t pn, uint64_t imm);
```

### Description

Move predicate to vector

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Predicate move

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p1)|FEAT_SME2p1
```

### Return type metadata

```json
{
  "return_base_type": "uint32",
  "element_bit_size": "32",
  "value": "svuint32_t"
}
```

### Argument preparation and constraints

```json
{
  "zd": {
    "register": "Zreg1"
  },
  "pn": {
    "register": "Preg1"
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
    "Zreg1[imm1]": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
PMOV Zreg1[imm1], Preg1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/PMOV--to-vector---Move-predicate-to-vector-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svpmov_lane[_u64]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svpmov_lane%5B_u64%5D

### Signature (source notation)

```c
svbool_t svpmov_lane[_u64](svuint64_t zn, uint64_t imm);
```

### Description

Bitwise AND predicates

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Predicate move

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p1)|FEAT_SME2p1
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
  "zn": {
    "register": "Zreg1"
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
PMOV Preg1.D, Zreg1[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/PTRUE--predicate---Initialize-predicate-from-named-constraint-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svpmov_lane[_u64]_m

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svpmov_lane%5B_u64%5D_m

### Signature (source notation)

```c
svuint64_t svpmov_lane[_u64]_m(svuint64_t zd, svbool_t pn, uint64_t imm);
```

### Description

Move predicate to vector

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Predicate move

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p1)|FEAT_SME2p1
```

### Return type metadata

```json
{
  "return_base_type": "uint64",
  "element_bit_size": "64",
  "value": "svuint64_t"
}
```

### Argument preparation and constraints

```json
{
  "zd": {
    "register": "Zreg1"
  },
  "pn": {
    "register": "Preg1"
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
    "Zreg1[imm1]": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
PMOV Zreg1[imm1], Preg1.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/PMOV--to-vector---Move-predicate-to-vector-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svpmov_lane[_u8]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svpmov_lane%5B_u8%5D

### Signature (source notation)

```c
svbool_t svpmov_lane[_u8](svuint8_t zn, uint64_t imm);
```

### Description

Move predicate from vector

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Predicate move

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p1)|FEAT_SME2p1
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
  "zn": {
    "register": "Zreg1"
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
PMOV Preg1.B, Zreg1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/PMOV--to-predicate---Move-predicate-from-vector-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svpmov_s16_z

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svpmov_s16_z

### Signature (source notation)

```c
svint16_t svpmov_s16_z(svbool_t pn);
```

### Description

Move predicate to vector

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Predicate move

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p1)|FEAT_SME2p1
```

### Return type metadata

```json
{
  "return_base_type": "int16",
  "element_bit_size": "16",
  "value": "svint16_t"
}
```

### Argument preparation and constraints

```json
{
  "pn": {
    "register": "Preg1"
  }
}
```

### Result mapping

```json
[
  {
    "Zreg1[0]": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
PMOV Zreg1[0], Preg1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/PMOV--to-vector---Move-predicate-to-vector-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svpmov_s32_z

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svpmov_s32_z

### Signature (source notation)

```c
svint32_t svpmov_s32_z(svbool_t pn);
```

### Description

Move predicate to vector

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Predicate move

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p1)|FEAT_SME2p1
```

### Return type metadata

```json
{
  "return_base_type": "int32",
  "element_bit_size": "32",
  "value": "svint32_t"
}
```

### Argument preparation and constraints

```json
{
  "pn": {
    "register": "Preg1"
  }
}
```

### Result mapping

```json
[
  {
    "Zreg1[0]": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
PMOV Zreg1[0], Preg1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/PMOV--to-vector---Move-predicate-to-vector-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svpmov_s64_z

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svpmov_s64_z

### Signature (source notation)

```c
svint64_t svpmov_s64_z(svbool_t pn);
```

### Description

Move predicate to vector

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Predicate move

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p1)|FEAT_SME2p1
```

### Return type metadata

```json
{
  "return_base_type": "int64",
  "element_bit_size": "64",
  "value": "svint64_t"
}
```

### Argument preparation and constraints

```json
{
  "pn": {
    "register": "Preg1"
  }
}
```

### Result mapping

```json
[
  {
    "Zreg1[0]": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
PMOV Zreg1[0], Preg1.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/PMOV--to-vector---Move-predicate-to-vector-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svpmov_s8_z

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svpmov_s8_z

### Signature (source notation)

```c
svint8_t svpmov_s8_z(svbool_t pn);
```

### Description

Move predicate to vector

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Predicate move

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p1)|FEAT_SME2p1
```

### Return type metadata

```json
{
  "return_base_type": "int8",
  "element_bit_size": "8",
  "value": "svint8_t"
}
```

### Argument preparation and constraints

```json
{
  "pn": {
    "register": "Preg1"
  }
}
```

### Result mapping

```json
[
  {
    "Zreg1": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
PMOV Zreg1, Preg1.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/PMOV--to-vector---Move-predicate-to-vector-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svpmov_u16_z

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svpmov_u16_z

### Signature (source notation)

```c
svuint16_t svpmov_u16_z(svbool_t pn);
```

### Description

Move predicate to vector

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Predicate move

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p1)|FEAT_SME2p1
```

### Return type metadata

```json
{
  "return_base_type": "uint16",
  "element_bit_size": "16",
  "value": "svuint16_t"
}
```

### Argument preparation and constraints

```json
{
  "pn": {
    "register": "Preg1"
  }
}
```

### Result mapping

```json
[
  {
    "Zreg1[0]": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
PMOV Zreg1[0], Preg1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/PMOV--to-vector---Move-predicate-to-vector-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svpmov_u32_z

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svpmov_u32_z

### Signature (source notation)

```c
svuint32_t svpmov_u32_z(svbool_t pn);
```

### Description

Move predicate to vector

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Predicate move

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p1)|FEAT_SME2p1
```

### Return type metadata

```json
{
  "return_base_type": "uint32",
  "element_bit_size": "32",
  "value": "svuint32_t"
}
```

### Argument preparation and constraints

```json
{
  "pn": {
    "register": "Preg1"
  }
}
```

### Result mapping

```json
[
  {
    "Zreg1[0]": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
PMOV Zreg1[0], Preg1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/PMOV--to-vector---Move-predicate-to-vector-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svpmov_u64_z

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svpmov_u64_z

### Signature (source notation)

```c
svuint64_t svpmov_u64_z(svbool_t pn);
```

### Description

Move predicate to vector

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Predicate move

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p1)|FEAT_SME2p1
```

### Return type metadata

```json
{
  "return_base_type": "uint64",
  "element_bit_size": "64",
  "value": "svuint64_t"
}
```

### Argument preparation and constraints

```json
{
  "pn": {
    "register": "Preg1"
  }
}
```

### Result mapping

```json
[
  {
    "Zreg1[0]": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
PMOV Zreg1[0], Preg1.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/PMOV--to-vector---Move-predicate-to-vector-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svpmov_u8_z

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svpmov_u8_z

### Signature (source notation)

```c
svuint8_t svpmov_u8_z(svbool_t pn);
```

### Description

Move predicate to vector

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Predicate move

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p1)|FEAT_SME2p1
```

### Return type metadata

```json
{
  "return_base_type": "uint8",
  "element_bit_size": "8",
  "value": "svuint8_t"
}
```

### Argument preparation and constraints

```json
{
  "pn": {
    "register": "Preg1"
  }
}
```

### Result mapping

```json
[
  {
    "Zreg1": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
PMOV Zreg1, Preg1.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/PMOV--to-vector---Move-predicate-to-vector-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

