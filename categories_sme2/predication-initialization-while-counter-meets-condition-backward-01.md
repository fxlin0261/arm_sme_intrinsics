# SME2 / Predication / Initialization / While counter meets condition (backward) — Part 1

## svwhilege_b16[_s64]_x2

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwhilege_b16%5B_s64%5D_x2

### Signature (source notation)

```c
svboolx2_t svwhilege_b16[_s64]_x2(int64_t rn, int64_t rm);
```

### Description

While decrementing signed scalar greater than or equal to scalar (pair of predicates)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Initialization / While counter meets condition (backward)

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
  "element_bit_size": "16",
  "value": "svboolx2_t"
}
```

### Argument preparation and constraints

```json
{
  "rn": {
    "register": "Xreg1"
  },
  "rm": {
    "register": "Xreg2"
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
WHILEGE { Preg1.H, Preg2.H }, Xreg1, Xreg2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/WHILEGE--predicate-pair---While-decrementing-signed-scalar-greater-than-or-equal-to-scalar--pair-of-predicates--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svwhilege_b16[_u64]_x2

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwhilege_b16%5B_u64%5D_x2

### Signature (source notation)

```c
svboolx2_t svwhilege_b16[_u64]_x2(uint64_t rn, uint64_t rm);
```

### Description

While decrementing unsigned scalar higher or same as scalar (pair of predicates)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Initialization / While counter meets condition (backward)

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
  "element_bit_size": "16",
  "value": "svboolx2_t"
}
```

### Argument preparation and constraints

```json
{
  "rn": {
    "register": "Xreg1"
  },
  "rm": {
    "register": "Xreg2"
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
WHILEHS { Preg1.H, Preg2.H }, Xreg1, Xreg2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/WHILEHS--predicate-pair---While-decrementing-unsigned-scalar-higher-or-same-as-scalar--pair-of-predicates--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svwhilege_b32[_s64]_x2

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwhilege_b32%5B_s64%5D_x2

### Signature (source notation)

```c
svboolx2_t svwhilege_b32[_s64]_x2(int64_t rn, int64_t rm);
```

### Description

While decrementing signed scalar greater than or equal to scalar (pair of predicates)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Initialization / While counter meets condition (backward)

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
  "element_bit_size": "32",
  "value": "svboolx2_t"
}
```

### Argument preparation and constraints

```json
{
  "rn": {
    "register": "Xreg1"
  },
  "rm": {
    "register": "Xreg2"
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
WHILEGE { Preg1.S, Preg2.S }, Xreg1, Xreg2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/WHILEGE--predicate-pair---While-decrementing-signed-scalar-greater-than-or-equal-to-scalar--pair-of-predicates--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svwhilege_b32[_u64]_x2

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwhilege_b32%5B_u64%5D_x2

### Signature (source notation)

```c
svboolx2_t svwhilege_b32[_u64]_x2(uint64_t rn, uint64_t rm);
```

### Description

While decrementing unsigned scalar higher or same as scalar (pair of predicates)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Initialization / While counter meets condition (backward)

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
  "element_bit_size": "32",
  "value": "svboolx2_t"
}
```

### Argument preparation and constraints

```json
{
  "rn": {
    "register": "Xreg1"
  },
  "rm": {
    "register": "Xreg2"
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
WHILEHS { Preg1.S, Preg2.S }, Xreg1, Xreg2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/WHILEHS--predicate-pair---While-decrementing-unsigned-scalar-higher-or-same-as-scalar--pair-of-predicates--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svwhilege_b64[_s64]_x2

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwhilege_b64%5B_s64%5D_x2

### Signature (source notation)

```c
svboolx2_t svwhilege_b64[_s64]_x2(int64_t rn, int64_t rm);
```

### Description

While decrementing signed scalar greater than or equal to scalar (pair of predicates)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Initialization / While counter meets condition (backward)

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
  "element_bit_size": "64",
  "value": "svboolx2_t"
}
```

### Argument preparation and constraints

```json
{
  "rn": {
    "register": "Xreg1"
  },
  "rm": {
    "register": "Xreg2"
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
WHILEGE { Preg1.D, Preg2.D }, Xreg1, Xreg2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/WHILEGE--predicate-pair---While-decrementing-signed-scalar-greater-than-or-equal-to-scalar--pair-of-predicates--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svwhilege_b64[_u64]_x2

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwhilege_b64%5B_u64%5D_x2

### Signature (source notation)

```c
svboolx2_t svwhilege_b64[_u64]_x2(uint64_t rn, uint64_t rm);
```

### Description

While decrementing unsigned scalar higher or same as scalar (pair of predicates)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Initialization / While counter meets condition (backward)

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
  "element_bit_size": "64",
  "value": "svboolx2_t"
}
```

### Argument preparation and constraints

```json
{
  "rn": {
    "register": "Xreg1"
  },
  "rm": {
    "register": "Xreg2"
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
WHILEHS { Preg1.D, Preg2.D }, Xreg1, Xreg2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/WHILEHS--predicate-pair---While-decrementing-unsigned-scalar-higher-or-same-as-scalar--pair-of-predicates--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svwhilege_b8[_s64]_x2

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwhilege_b8%5B_s64%5D_x2

### Signature (source notation)

```c
svboolx2_t svwhilege_b8[_s64]_x2(int64_t rn, int64_t rm);
```

### Description

While decrementing signed scalar greater than or equal to scalar (pair of predicates)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Initialization / While counter meets condition (backward)

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
  "element_bit_size": "8",
  "value": "svboolx2_t"
}
```

### Argument preparation and constraints

```json
{
  "rn": {
    "register": "Xreg1"
  },
  "rm": {
    "register": "Xreg2"
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
WHILEGE { Preg1.B, Preg2.B }, Xreg1, Xreg2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/WHILEGE--predicate-pair---While-decrementing-signed-scalar-greater-than-or-equal-to-scalar--pair-of-predicates--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svwhilege_b8[_u64]_x2

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwhilege_b8%5B_u64%5D_x2

### Signature (source notation)

```c
svboolx2_t svwhilege_b8[_u64]_x2(uint64_t rn, uint64_t rm);
```

### Description

While decrementing unsigned scalar higher or same as scalar (pair of predicates)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Initialization / While counter meets condition (backward)

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
  "element_bit_size": "8",
  "value": "svboolx2_t"
}
```

### Argument preparation and constraints

```json
{
  "rn": {
    "register": "Xreg1"
  },
  "rm": {
    "register": "Xreg2"
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
WHILEHS { Preg1.B, Preg2.B }, Xreg1, Xreg2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/WHILEHS--predicate-pair---While-decrementing-unsigned-scalar-higher-or-same-as-scalar--pair-of-predicates--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svwhilege_c16[_s64]

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwhilege_c16%5B_s64%5D

### Signature (source notation)

```c
svcount_t svwhilege_c16[_s64](int64_t rn, int64_t rm, uint64_t vl);
```

### Description

While decrementing signed scalar greater than or equal to scalar (predicate-as-counter)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Initialization / While counter meets condition (backward)

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
  "rn": {
    "register": "Xreg1"
  },
  "rm": {
    "register": "Xreg2"
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
    "PNreg1.H": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
WHILEGE PNreg1.H, Xreg1, Xreg2, <VL>
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/WHILEGE--predicate-as-counter---While-decrementing-signed-scalar-greater-than-or-equal-to-scalar--predicate-as-counter--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svwhilege_c16[_u64]

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwhilege_c16%5B_u64%5D

### Signature (source notation)

```c
svcount_t svwhilege_c16[_u64](uint64_t rn, uint64_t rm, uint64_t vl);
```

### Description

While decrementing unsigned scalar higher or same as scalar (predicate-as-counter)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Initialization / While counter meets condition (backward)

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
  "rn": {
    "register": "Xreg1"
  },
  "rm": {
    "register": "Xreg2"
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
    "PNreg1.H": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
WHILEHS PNreg1.H, Xreg1, Xreg2, <VL>
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/WHILEHS--predicate-as-counter---While-decrementing-unsigned-scalar-higher-or-same-as-scalar--predicate-as-counter--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svwhilege_c32[_s64]

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwhilege_c32%5B_s64%5D

### Signature (source notation)

```c
svcount_t svwhilege_c32[_s64](int64_t rn, int64_t rm, uint64_t vl);
```

### Description

While decrementing signed scalar greater than or equal to scalar (predicate-as-counter)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Initialization / While counter meets condition (backward)

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
  "rn": {
    "register": "Xreg1"
  },
  "rm": {
    "register": "Xreg2"
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
    "PNreg1.S": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
WHILEGE PNreg1.S, Xreg1, Xreg2, <VL>
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/WHILEGE--predicate-as-counter---While-decrementing-signed-scalar-greater-than-or-equal-to-scalar--predicate-as-counter--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svwhilege_c32[_u64]

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwhilege_c32%5B_u64%5D

### Signature (source notation)

```c
svcount_t svwhilege_c32[_u64](uint64_t rn, uint64_t rm, uint64_t vl);
```

### Description

While decrementing unsigned scalar higher or same as scalar (predicate-as-counter)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Initialization / While counter meets condition (backward)

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
  "rn": {
    "register": "Xreg1"
  },
  "rm": {
    "register": "Xreg2"
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
    "PNreg1.S": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
WHILEHS PNreg1.S, Xreg1, Xreg2, <VL>
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/WHILEHS--predicate-as-counter---While-decrementing-unsigned-scalar-higher-or-same-as-scalar--predicate-as-counter--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svwhilege_c64[_s64]

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwhilege_c64%5B_s64%5D

### Signature (source notation)

```c
svcount_t svwhilege_c64[_s64](int64_t rn, int64_t rm, uint64_t vl);
```

### Description

While decrementing signed scalar greater than or equal to scalar (predicate-as-counter)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Initialization / While counter meets condition (backward)

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
  "rn": {
    "register": "Xreg1"
  },
  "rm": {
    "register": "Xreg2"
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
    "PNreg1.D": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
WHILEGE PNreg1.D, Xreg1, Xreg2, <VL>
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/WHILEGE--predicate-as-counter---While-decrementing-signed-scalar-greater-than-or-equal-to-scalar--predicate-as-counter--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svwhilege_c64[_u64]

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwhilege_c64%5B_u64%5D

### Signature (source notation)

```c
svcount_t svwhilege_c64[_u64](uint64_t rn, uint64_t rm, uint64_t vl);
```

### Description

While decrementing unsigned scalar higher or same as scalar (predicate-as-counter)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Initialization / While counter meets condition (backward)

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
  "rn": {
    "register": "Xreg1"
  },
  "rm": {
    "register": "Xreg2"
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
    "PNreg1.D": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
WHILEHS PNreg1.D, Xreg1, Xreg2, <VL>
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/WHILEHS--predicate-as-counter---While-decrementing-unsigned-scalar-higher-or-same-as-scalar--predicate-as-counter--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svwhilege_c8[_s64]

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwhilege_c8%5B_s64%5D

### Signature (source notation)

```c
svcount_t svwhilege_c8[_s64](int64_t rn, int64_t rm, uint64_t vl);
```

### Description

While decrementing signed scalar greater than or equal to scalar (predicate-as-counter)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Initialization / While counter meets condition (backward)

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
  "rn": {
    "register": "Xreg1"
  },
  "rm": {
    "register": "Xreg2"
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
    "PNreg1.B": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
WHILEGE PNreg1.B, Xreg1, Xreg2, <VL>
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/WHILEGE--predicate-as-counter---While-decrementing-signed-scalar-greater-than-or-equal-to-scalar--predicate-as-counter--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svwhilege_c8[_u64]

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwhilege_c8%5B_u64%5D

### Signature (source notation)

```c
svcount_t svwhilege_c8[_u64](uint64_t rn, uint64_t rm, uint64_t vl);
```

### Description

While decrementing unsigned scalar higher or same as scalar (predicate-as-counter)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Initialization / While counter meets condition (backward)

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
  "rn": {
    "register": "Xreg1"
  },
  "rm": {
    "register": "Xreg2"
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
    "PNreg1.B": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
WHILEHS PNreg1.B, Xreg1, Xreg2, <VL>
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/WHILEHS--predicate-as-counter---While-decrementing-unsigned-scalar-higher-or-same-as-scalar--predicate-as-counter--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svwhilegt_b16[_s64]_x2

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwhilegt_b16%5B_s64%5D_x2

### Signature (source notation)

```c
svboolx2_t svwhilegt_b16[_s64]_x2(int64_t rn, int64_t rm);
```

### Description

While decrementing signed scalar greater than scalar (pair of predicates)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Initialization / While counter meets condition (backward)

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
  "element_bit_size": "16",
  "value": "svboolx2_t"
}
```

### Argument preparation and constraints

```json
{
  "rn": {
    "register": "Xreg1"
  },
  "rm": {
    "register": "Xreg2"
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
WHILEGT { Preg1.H, Preg2.H }, Xreg1, Xreg2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/WHILEGT--predicate-pair---While-decrementing-signed-scalar-greater-than-scalar--pair-of-predicates--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svwhilegt_b16[_u64]_x2

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwhilegt_b16%5B_u64%5D_x2

### Signature (source notation)

```c
svboolx2_t svwhilegt_b16[_u64]_x2(uint64_t rn, uint64_t rm);
```

### Description

While decrementing unsigned scalar higher than scalar (pair of predicates)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Initialization / While counter meets condition (backward)

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
  "element_bit_size": "16",
  "value": "svboolx2_t"
}
```

### Argument preparation and constraints

```json
{
  "rn": {
    "register": "Xreg1"
  },
  "rm": {
    "register": "Xreg2"
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
WHILEHI { Preg1.H, Preg2.H }, Xreg1, Xreg2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/WHILEHI--predicate-pair---While-decrementing-unsigned-scalar-higher-than-scalar--pair-of-predicates--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svwhilegt_b32[_s64]_x2

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwhilegt_b32%5B_s64%5D_x2

### Signature (source notation)

```c
svboolx2_t svwhilegt_b32[_s64]_x2(int64_t rn, int64_t rm);
```

### Description

While decrementing signed scalar greater than scalar (pair of predicates)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Initialization / While counter meets condition (backward)

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
  "element_bit_size": "32",
  "value": "svboolx2_t"
}
```

### Argument preparation and constraints

```json
{
  "rn": {
    "register": "Xreg1"
  },
  "rm": {
    "register": "Xreg2"
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
WHILEGT { Preg1.S, Preg2.S }, Xreg1, Xreg2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/WHILEGT--predicate-pair---While-decrementing-signed-scalar-greater-than-scalar--pair-of-predicates--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svwhilegt_b32[_u64]_x2

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwhilegt_b32%5B_u64%5D_x2

### Signature (source notation)

```c
svboolx2_t svwhilegt_b32[_u64]_x2(uint64_t rn, uint64_t rm);
```

### Description

While decrementing unsigned scalar higher than scalar (pair of predicates)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Initialization / While counter meets condition (backward)

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
  "element_bit_size": "32",
  "value": "svboolx2_t"
}
```

### Argument preparation and constraints

```json
{
  "rn": {
    "register": "Xreg1"
  },
  "rm": {
    "register": "Xreg2"
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
WHILEHI { Preg1.S, Preg2.S }, Xreg1, Xreg2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/WHILEHI--predicate-pair---While-decrementing-unsigned-scalar-higher-than-scalar--pair-of-predicates--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svwhilegt_b64[_s64]_x2

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwhilegt_b64%5B_s64%5D_x2

### Signature (source notation)

```c
svboolx2_t svwhilegt_b64[_s64]_x2(int64_t rn, int64_t rm);
```

### Description

While decrementing signed scalar greater than scalar (pair of predicates)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Initialization / While counter meets condition (backward)

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
  "element_bit_size": "64",
  "value": "svboolx2_t"
}
```

### Argument preparation and constraints

```json
{
  "rn": {
    "register": "Xreg1"
  },
  "rm": {
    "register": "Xreg2"
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
WHILEGT { Preg1.D, Preg2.D }, Xreg1, Xreg2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/WHILEGT--predicate-pair---While-decrementing-signed-scalar-greater-than-scalar--pair-of-predicates--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svwhilegt_b64[_u64]_x2

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwhilegt_b64%5B_u64%5D_x2

### Signature (source notation)

```c
svboolx2_t svwhilegt_b64[_u64]_x2(uint64_t rn, uint64_t rm);
```

### Description

While decrementing unsigned scalar higher than scalar (pair of predicates)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Initialization / While counter meets condition (backward)

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
  "element_bit_size": "64",
  "value": "svboolx2_t"
}
```

### Argument preparation and constraints

```json
{
  "rn": {
    "register": "Xreg1"
  },
  "rm": {
    "register": "Xreg2"
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
WHILEHI { Preg1.D, Preg2.D }, Xreg1, Xreg2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/WHILEHI--predicate-pair---While-decrementing-unsigned-scalar-higher-than-scalar--pair-of-predicates--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svwhilegt_b8[_s64]_x2

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwhilegt_b8%5B_s64%5D_x2

### Signature (source notation)

```c
svboolx2_t svwhilegt_b8[_s64]_x2(int64_t rn, int64_t rm);
```

### Description

While decrementing signed scalar greater than scalar (pair of predicates)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Initialization / While counter meets condition (backward)

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
  "element_bit_size": "8",
  "value": "svboolx2_t"
}
```

### Argument preparation and constraints

```json
{
  "rn": {
    "register": "Xreg1"
  },
  "rm": {
    "register": "Xreg2"
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
WHILEGT { Preg1.B, Preg2.B }, Xreg1, Xreg2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/WHILEGT--predicate-pair---While-decrementing-signed-scalar-greater-than-scalar--pair-of-predicates--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svwhilegt_b8[_u64]_x2

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwhilegt_b8%5B_u64%5D_x2

### Signature (source notation)

```c
svboolx2_t svwhilegt_b8[_u64]_x2(uint64_t rn, uint64_t rm);
```

### Description

While decrementing unsigned scalar higher than scalar (pair of predicates)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Initialization / While counter meets condition (backward)

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
  "element_bit_size": "8",
  "value": "svboolx2_t"
}
```

### Argument preparation and constraints

```json
{
  "rn": {
    "register": "Xreg1"
  },
  "rm": {
    "register": "Xreg2"
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
WHILEHI { Preg1.B, Preg2.B }, Xreg1, Xreg2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/WHILEHI--predicate-pair---While-decrementing-unsigned-scalar-higher-than-scalar--pair-of-predicates--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svwhilegt_c16[_s64]

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwhilegt_c16%5B_s64%5D

### Signature (source notation)

```c
svcount_t svwhilegt_c16[_s64](int64_t rn, int64_t rm, uint64_t vl);
```

### Description

While decrementing signed scalar greater than scalar (predicate-as-counter)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Initialization / While counter meets condition (backward)

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
  "rn": {
    "register": "Xreg1"
  },
  "rm": {
    "register": "Xreg2"
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
    "PNreg1.H": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
WHILEGT PNreg1.H, Xreg1, Xreg2, <VL>
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/WHILEGT--predicate-as-counter---While-decrementing-signed-scalar-greater-than-scalar--predicate-as-counter--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svwhilegt_c16[_u64]

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwhilegt_c16%5B_u64%5D

### Signature (source notation)

```c
svcount_t svwhilegt_c16[_u64](uint64_t rn, uint64_t rm, uint64_t vl);
```

### Description

While decrementing unsigned scalar higher than scalar (predicate-as-counter)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Initialization / While counter meets condition (backward)

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
  "rn": {
    "register": "Xreg1"
  },
  "rm": {
    "register": "Xreg2"
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
    "PNreg1.H": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
WHILEHI PNreg1.H, Xreg1, Xreg2, <VL>
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/WHILEHI--predicate-as-counter---While-decrementing-unsigned-scalar-higher-than-scalar--predicate-as-counter--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svwhilegt_c32[_s64]

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwhilegt_c32%5B_s64%5D

### Signature (source notation)

```c
svcount_t svwhilegt_c32[_s64](int64_t rn, int64_t rm, uint64_t vl);
```

### Description

While decrementing signed scalar greater than scalar (predicate-as-counter)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Initialization / While counter meets condition (backward)

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
  "rn": {
    "register": "Xreg1"
  },
  "rm": {
    "register": "Xreg2"
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
    "PNreg1.S": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
WHILEGT PNreg1.S, Xreg1, Xreg2, <VL>
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/WHILEGT--predicate-as-counter---While-decrementing-signed-scalar-greater-than-scalar--predicate-as-counter--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svwhilegt_c32[_u64]

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwhilegt_c32%5B_u64%5D

### Signature (source notation)

```c
svcount_t svwhilegt_c32[_u64](uint64_t rn, uint64_t rm, uint64_t vl);
```

### Description

While decrementing unsigned scalar higher than scalar (predicate-as-counter)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Initialization / While counter meets condition (backward)

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
  "rn": {
    "register": "Xreg1"
  },
  "rm": {
    "register": "Xreg2"
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
    "PNreg1.S": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
WHILEHI PNreg1.S, Xreg1, Xreg2, <VL>
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/WHILEHI--predicate-as-counter---While-decrementing-unsigned-scalar-higher-than-scalar--predicate-as-counter--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svwhilegt_c64[_s64]

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwhilegt_c64%5B_s64%5D

### Signature (source notation)

```c
svcount_t svwhilegt_c64[_s64](int64_t rn, int64_t rm, uint64_t vl);
```

### Description

While decrementing signed scalar greater than scalar (predicate-as-counter)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Initialization / While counter meets condition (backward)

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
  "rn": {
    "register": "Xreg1"
  },
  "rm": {
    "register": "Xreg2"
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
    "PNreg1.D": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
WHILEGT PNreg1.D, Xreg1, Xreg2, <VL>
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/WHILEGT--predicate-as-counter---While-decrementing-signed-scalar-greater-than-scalar--predicate-as-counter--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svwhilegt_c64[_u64]

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwhilegt_c64%5B_u64%5D

### Signature (source notation)

```c
svcount_t svwhilegt_c64[_u64](uint64_t rn, uint64_t rm, uint64_t vl);
```

### Description

While decrementing unsigned scalar higher than scalar (predicate-as-counter)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Initialization / While counter meets condition (backward)

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
  "rn": {
    "register": "Xreg1"
  },
  "rm": {
    "register": "Xreg2"
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
    "PNreg1.D": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
WHILEHI PNreg1.D, Xreg1, Xreg2, <VL>
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/WHILEHI--predicate-as-counter---While-decrementing-unsigned-scalar-higher-than-scalar--predicate-as-counter--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svwhilegt_c8[_s64]

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwhilegt_c8%5B_s64%5D

### Signature (source notation)

```c
svcount_t svwhilegt_c8[_s64](int64_t rn, int64_t rm, uint64_t vl);
```

### Description

While decrementing signed scalar greater than scalar (predicate-as-counter)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Initialization / While counter meets condition (backward)

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
  "rn": {
    "register": "Xreg1"
  },
  "rm": {
    "register": "Xreg2"
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
    "PNreg1.B": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
WHILEGT PNreg1.B, Xreg1, Xreg2, <VL>
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/WHILEGT--predicate-as-counter---While-decrementing-signed-scalar-greater-than-scalar--predicate-as-counter--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svwhilegt_c8[_u64]

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwhilegt_c8%5B_u64%5D

### Signature (source notation)

```c
svcount_t svwhilegt_c8[_u64](uint64_t rn, uint64_t rm, uint64_t vl);
```

### Description

While decrementing unsigned scalar higher than scalar (predicate-as-counter)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Initialization / While counter meets condition (backward)

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
  "rn": {
    "register": "Xreg1"
  },
  "rm": {
    "register": "Xreg2"
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
    "PNreg1.B": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
WHILEHI PNreg1.B, Xreg1, Xreg2, <VL>
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/WHILEHI--predicate-as-counter---While-decrementing-unsigned-scalar-higher-than-scalar--predicate-as-counter--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

