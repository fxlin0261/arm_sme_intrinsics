# SME2 / Predication / Testing — Part 1

## svfirstp_b16

ISA classification: SME + FEAT_SVE2p2 OR SME2.2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svfirstp_b16

### Signature (source notation)

```c
int64_t svfirstp_b16(svbool_t pg, svbool_t pn);
```

### Description

Scalar index of first true predicate element (predicated)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Testing

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p2)|FEAT_SME2p2
```

### Return type metadata

```json
{
  "return_base_type": "int64_t",
  "element_bit_size": "64",
  "value": "int64_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Preg1"
  },
  "pn": {
    "register": "Preg2"
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
FIRSTP Xreg1, Preg1, Preg2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/FIRSTP--Scalar-index-of-first-true-predicate-element--predicated--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svfirstp_b32

ISA classification: SME + FEAT_SVE2p2 OR SME2.2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svfirstp_b32

### Signature (source notation)

```c
int64_t svfirstp_b32(svbool_t pg, svbool_t pn);
```

### Description

Scalar index of first true predicate element (predicated)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Testing

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p2)|FEAT_SME2p2
```

### Return type metadata

```json
{
  "return_base_type": "int64_t",
  "element_bit_size": "64",
  "value": "int64_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Preg1"
  },
  "pn": {
    "register": "Preg2"
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
FIRSTP Xreg1, Preg1, Preg2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/FIRSTP--Scalar-index-of-first-true-predicate-element--predicated--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svfirstp_b64

ISA classification: SME + FEAT_SVE2p2 OR SME2.2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svfirstp_b64

### Signature (source notation)

```c
int64_t svfirstp_b64(svbool_t pg, svbool_t pn);
```

### Description

Scalar index of first true predicate element (predicated)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Testing

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p2)|FEAT_SME2p2
```

### Return type metadata

```json
{
  "return_base_type": "int64_t",
  "element_bit_size": "64",
  "value": "int64_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Preg1"
  },
  "pn": {
    "register": "Preg2"
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
FIRSTP Xreg1, Preg1, Preg2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/FIRSTP--Scalar-index-of-first-true-predicate-element--predicated--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svfirstp_b8

ISA classification: SME + FEAT_SVE2p2 OR SME2.2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svfirstp_b8

### Signature (source notation)

```c
int64_t svfirstp_b8(svbool_t pg, svbool_t pn);
```

### Description

Scalar index of first true predicate element (predicated)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Testing

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p2)|FEAT_SME2p2
```

### Return type metadata

```json
{
  "return_base_type": "int64_t",
  "element_bit_size": "64",
  "value": "int64_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Preg1"
  },
  "pn": {
    "register": "Preg2"
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
FIRSTP Xreg1, Preg1, Preg2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/FIRSTP--Scalar-index-of-first-true-predicate-element--predicated--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svlastp_b16

ISA classification: SME + FEAT_SVE2p2 OR SME2.2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svlastp_b16

### Signature (source notation)

```c
int64_t svlastp_b16(svbool_t pg, svbool_t pn);
```

### Description

Scalar index of last true predicate element (predicated)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Testing

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p2)|FEAT_SME2p2
```

### Return type metadata

```json
{
  "return_base_type": "int64_t",
  "element_bit_size": "64",
  "value": "int64_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Preg1"
  },
  "pn": {
    "register": "Preg2"
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
LASTP Xreg1, Preg1, Preg2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/LASTP--Scalar-index-of-last-true-predicate-element--predicated--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svlastp_b32

ISA classification: SME + FEAT_SVE2p2 OR SME2.2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svlastp_b32

### Signature (source notation)

```c
int64_t svlastp_b32(svbool_t pg, svbool_t pn);
```

### Description

Scalar index of last true predicate element (predicated)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Testing

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p2)|FEAT_SME2p2
```

### Return type metadata

```json
{
  "return_base_type": "int64_t",
  "element_bit_size": "64",
  "value": "int64_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Preg1"
  },
  "pn": {
    "register": "Preg2"
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
LASTP Xreg1, Preg1, Preg2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/LASTP--Scalar-index-of-last-true-predicate-element--predicated--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svlastp_b64

ISA classification: SME + FEAT_SVE2p2 OR SME2.2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svlastp_b64

### Signature (source notation)

```c
int64_t svlastp_b64(svbool_t pg, svbool_t pn);
```

### Description

Scalar index of last true predicate element (predicated)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Testing

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p2)|FEAT_SME2p2
```

### Return type metadata

```json
{
  "return_base_type": "int64_t",
  "element_bit_size": "64",
  "value": "int64_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Preg1"
  },
  "pn": {
    "register": "Preg2"
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
LASTP Xreg1, Preg1, Preg2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/LASTP--Scalar-index-of-last-true-predicate-element--predicated--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svlastp_b8

ISA classification: SME + FEAT_SVE2p2 OR SME2.2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svlastp_b8

### Signature (source notation)

```c
int64_t svlastp_b8(svbool_t pg, svbool_t pn);
```

### Description

Scalar index of last true predicate element (predicated)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Testing

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p2)|FEAT_SME2p2
```

### Return type metadata

```json
{
  "return_base_type": "int64_t",
  "element_bit_size": "64",
  "value": "int64_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Preg1"
  },
  "pn": {
    "register": "Preg2"
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
LASTP Xreg1, Preg1, Preg2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/LASTP--Scalar-index-of-last-true-predicate-element--predicated--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

