# SME2 / Predication / Initialization / While counter meets condition (forward) — Part 1

## svwhilele_b16[_s64]_x2

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwhilele_b16%5B_s64%5D_x2

### Signature (source notation)

```c
svboolx2_t svwhilele_b16[_s64]_x2(int64_t rn, int64_t rm);
```

### Description

While incrementing signed scalar less than or equal to scalar (pair of predicates)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Initialization / While counter meets condition (forward)

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
WHILELE { Preg1.H, Preg2.H }, Xreg1, Xreg2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/WHILELE--predicate-pair---While-incrementing-signed-scalar-less-than-or-equal-to-scalar--pair-of-predicates--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svwhilele_b16[_u64]_x2

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwhilele_b16%5B_u64%5D_x2

### Signature (source notation)

```c
svboolx2_t svwhilele_b16[_u64]_x2(uint64_t rn, uint64_t rm);
```

### Description

While incrementing unsigned scalar lower or same as scalar (pair of predicates)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Initialization / While counter meets condition (forward)

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
WHILELS { Preg1.H, Preg2.H }, Xreg1, Xreg2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/WHILELS--predicate-pair---While-incrementing-unsigned-scalar-lower-or-same-as-scalar--pair-of-predicates--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svwhilele_b32[_s64]_x2

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwhilele_b32%5B_s64%5D_x2

### Signature (source notation)

```c
svboolx2_t svwhilele_b32[_s64]_x2(int64_t rn, int64_t rm);
```

### Description

While incrementing signed scalar less than or equal to scalar (pair of predicates)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Initialization / While counter meets condition (forward)

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
WHILELE { Preg1.S, Preg2.S }, Xreg1, Xreg2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/WHILELE--predicate-pair---While-incrementing-signed-scalar-less-than-or-equal-to-scalar--pair-of-predicates--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svwhilele_b32[_u64]_x2

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwhilele_b32%5B_u64%5D_x2

### Signature (source notation)

```c
svboolx2_t svwhilele_b32[_u64]_x2(uint64_t rn, uint64_t rm);
```

### Description

While incrementing unsigned scalar lower or same as scalar (pair of predicates)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Initialization / While counter meets condition (forward)

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
WHILELS { Preg1.S, Preg2.S }, Xreg1, Xreg2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/WHILELS--predicate-pair---While-incrementing-unsigned-scalar-lower-or-same-as-scalar--pair-of-predicates--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svwhilele_b64[_s64]_x2

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwhilele_b64%5B_s64%5D_x2

### Signature (source notation)

```c
svboolx2_t svwhilele_b64[_s64]_x2(int64_t rn, int64_t rm);
```

### Description

While incrementing signed scalar less than or equal to scalar (pair of predicates)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Initialization / While counter meets condition (forward)

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
WHILELE { Preg1.D, Preg2.D }, Xreg1, Xreg2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/WHILELE--predicate-pair---While-incrementing-signed-scalar-less-than-or-equal-to-scalar--pair-of-predicates--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svwhilele_b64[_u64]_x2

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwhilele_b64%5B_u64%5D_x2

### Signature (source notation)

```c
svboolx2_t svwhilele_b64[_u64]_x2(uint64_t rn, uint64_t rm);
```

### Description

While incrementing unsigned scalar lower or same as scalar (pair of predicates)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Initialization / While counter meets condition (forward)

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
WHILELS { Preg1.D, Preg2.D }, Xreg1, Xreg2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/WHILELS--predicate-pair---While-incrementing-unsigned-scalar-lower-or-same-as-scalar--pair-of-predicates--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svwhilele_b8[_s64]_x2

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwhilele_b8%5B_s64%5D_x2

### Signature (source notation)

```c
svboolx2_t svwhilele_b8[_s64]_x2(int64_t rn, int64_t rm);
```

### Description

While incrementing signed scalar less than or equal to scalar (pair of predicates)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Initialization / While counter meets condition (forward)

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
WHILELE { Preg1.B, Preg2.B }, Xreg1, Xreg2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/WHILELE--predicate-pair---While-incrementing-signed-scalar-less-than-or-equal-to-scalar--pair-of-predicates--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svwhilele_b8[_u64]_x2

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwhilele_b8%5B_u64%5D_x2

### Signature (source notation)

```c
svboolx2_t svwhilele_b8[_u64]_x2(uint64_t rn, uint64_t rm);
```

### Description

While incrementing unsigned scalar lower or same as scalar (pair of predicates)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Initialization / While counter meets condition (forward)

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
WHILELS { Preg1.B, Preg2.B }, Xreg1, Xreg2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/WHILELS--predicate-pair---While-incrementing-unsigned-scalar-lower-or-same-as-scalar--pair-of-predicates--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svwhilele_c16[_s64]

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwhilele_c16%5B_s64%5D

### Signature (source notation)

```c
svcount_t svwhilele_c16[_s64](int64_t rn, int64_t rm, uint64_t vl);
```

### Description

While incrementing signed scalar less than or equal to scalar (predicate-as-counter)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Initialization / While counter meets condition (forward)

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
WHILELE PNreg1.H, Xreg1, Xreg2, <VL>
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/WHILELE--predicate-as-counter---While-incrementing-signed-scalar-less-than-or-equal-to-scalar--predicate-as-counter--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svwhilele_c16[_u64]

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwhilele_c16%5B_u64%5D

### Signature (source notation)

```c
svcount_t svwhilele_c16[_u64](uint64_t rn, uint64_t rm, uint64_t vl);
```

### Description

While incrementing unsigned scalar lower or same as scalar (predicate-as-counter)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Initialization / While counter meets condition (forward)

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
WHILELS PNreg1.H, Xreg1, Xreg2, <VL>
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/WHILELS--predicate-as-counter---While-incrementing-unsigned-scalar-lower-or-same-as-scalar--predicate-as-counter--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svwhilele_c32[_s64]

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwhilele_c32%5B_s64%5D

### Signature (source notation)

```c
svcount_t svwhilele_c32[_s64](int64_t rn, int64_t rm, uint64_t vl);
```

### Description

While incrementing signed scalar less than or equal to scalar (predicate-as-counter)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Initialization / While counter meets condition (forward)

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
WHILELE PNreg1.S, Xreg1, Xreg2, <VL>
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/WHILELE--predicate-as-counter---While-incrementing-signed-scalar-less-than-or-equal-to-scalar--predicate-as-counter--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svwhilele_c32[_u64]

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwhilele_c32%5B_u64%5D

### Signature (source notation)

```c
svcount_t svwhilele_c32[_u64](uint64_t rn, uint64_t rm, uint64_t vl);
```

### Description

While incrementing unsigned scalar lower or same as scalar (predicate-as-counter)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Initialization / While counter meets condition (forward)

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
WHILELS PNreg1.S, Xreg1, Xreg2, <VL>
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/WHILELS--predicate-as-counter---While-incrementing-unsigned-scalar-lower-or-same-as-scalar--predicate-as-counter--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svwhilele_c64[_s64]

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwhilele_c64%5B_s64%5D

### Signature (source notation)

```c
svcount_t svwhilele_c64[_s64](int64_t rn, int64_t rm, uint64_t vl);
```

### Description

While incrementing signed scalar less than or equal to scalar (predicate-as-counter)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Initialization / While counter meets condition (forward)

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
WHILELE PNreg1.D, Xreg1, Xreg2, <VL>
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/WHILELE--predicate-as-counter---While-incrementing-signed-scalar-less-than-or-equal-to-scalar--predicate-as-counter--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svwhilele_c64[_u64]

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwhilele_c64%5B_u64%5D

### Signature (source notation)

```c
svcount_t svwhilele_c64[_u64](uint64_t rn, uint64_t rm, uint64_t vl);
```

### Description

While incrementing unsigned scalar lower or same as scalar (predicate-as-counter)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Initialization / While counter meets condition (forward)

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
WHILELS PNreg1.D, Xreg1, Xreg2, <VL>
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/WHILELS--predicate-as-counter---While-incrementing-unsigned-scalar-lower-or-same-as-scalar--predicate-as-counter--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svwhilele_c8[_s64]

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwhilele_c8%5B_s64%5D

### Signature (source notation)

```c
svcount_t svwhilele_c8[_s64](int64_t rn, int64_t rm, uint64_t vl);
```

### Description

While incrementing signed scalar less than or equal to scalar (predicate-as-counter)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Initialization / While counter meets condition (forward)

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
WHILELE PNreg1.B, Xreg1, Xreg2, <VL>
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/WHILELE--predicate-as-counter---While-incrementing-signed-scalar-less-than-or-equal-to-scalar--predicate-as-counter--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svwhilele_c8[_u64]

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwhilele_c8%5B_u64%5D

### Signature (source notation)

```c
svcount_t svwhilele_c8[_u64](uint64_t rn, uint64_t rm, uint64_t vl);
```

### Description

While incrementing unsigned scalar lower or same as scalar (predicate-as-counter)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Initialization / While counter meets condition (forward)

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
WHILELS PNreg1.B, Xreg1, Xreg2, <VL>
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/WHILELS--predicate-as-counter---While-incrementing-unsigned-scalar-lower-or-same-as-scalar--predicate-as-counter--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svwhilelt_b16[_s64]_x2

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwhilelt_b16%5B_s64%5D_x2

### Signature (source notation)

```c
svboolx2_t svwhilelt_b16[_s64]_x2(int64_t rn, int64_t rm);
```

### Description

While incrementing signed scalar less than scalar (pair of predicates)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Initialization / While counter meets condition (forward)

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
WHILELT { Preg1.H, Preg2.H }, Xreg1, Xreg2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/WHILELT--predicate-pair---While-incrementing-signed-scalar-less-than-scalar--pair-of-predicates--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svwhilelt_b16[_u64]_x2

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwhilelt_b16%5B_u64%5D_x2

### Signature (source notation)

```c
svboolx2_t svwhilelt_b16[_u64]_x2(uint64_t rn, uint64_t rm);
```

### Description

While incrementing unsigned scalar lower than scalar (pair of predicates)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Initialization / While counter meets condition (forward)

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
WHILELO { Preg1.H, Preg2.H }, Xreg1, Xreg2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/WHILELO--predicate-pair---While-incrementing-unsigned-scalar-lower-than-scalar--pair-of-predicates--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svwhilelt_b32[_s64]_x2

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwhilelt_b32%5B_s64%5D_x2

### Signature (source notation)

```c
svboolx2_t svwhilelt_b32[_s64]_x2(int64_t rn, int64_t rm);
```

### Description

While incrementing signed scalar less than scalar (pair of predicates)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Initialization / While counter meets condition (forward)

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
WHILELT { Preg1.S, Preg2.S }, Xreg1, Xreg2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/WHILELT--predicate-pair---While-incrementing-signed-scalar-less-than-scalar--pair-of-predicates--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svwhilelt_b32[_u64]_x2

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwhilelt_b32%5B_u64%5D_x2

### Signature (source notation)

```c
svboolx2_t svwhilelt_b32[_u64]_x2(uint64_t rn, uint64_t rm);
```

### Description

While incrementing unsigned scalar lower than scalar (pair of predicates)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Initialization / While counter meets condition (forward)

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
WHILELO { Preg1.S, Preg2.S }, Xreg1, Xreg2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/WHILELO--predicate-pair---While-incrementing-unsigned-scalar-lower-than-scalar--pair-of-predicates--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svwhilelt_b64[_s64]_x2

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwhilelt_b64%5B_s64%5D_x2

### Signature (source notation)

```c
svboolx2_t svwhilelt_b64[_s64]_x2(int64_t rn, int64_t rm);
```

### Description

While incrementing signed scalar less than scalar (pair of predicates)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Initialization / While counter meets condition (forward)

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
WHILELT { Preg1.D, Preg2.D }, Xreg1, Xreg2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/WHILELT--predicate-pair---While-incrementing-signed-scalar-less-than-scalar--pair-of-predicates--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svwhilelt_b64[_u64]_x2

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwhilelt_b64%5B_u64%5D_x2

### Signature (source notation)

```c
svboolx2_t svwhilelt_b64[_u64]_x2(uint64_t rn, uint64_t rm);
```

### Description

While incrementing unsigned scalar lower than scalar (pair of predicates)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Initialization / While counter meets condition (forward)

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
WHILELO { Preg1.D, Preg2.D }, Xreg1, Xreg2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/WHILELO--predicate-pair---While-incrementing-unsigned-scalar-lower-than-scalar--pair-of-predicates--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svwhilelt_b8[_s64]_x2

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwhilelt_b8%5B_s64%5D_x2

### Signature (source notation)

```c
svboolx2_t svwhilelt_b8[_s64]_x2(int64_t rn, int64_t rm);
```

### Description

While incrementing signed scalar less than scalar (pair of predicates)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Initialization / While counter meets condition (forward)

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
WHILELT { Preg1.B, Preg2.B }, Xreg1, Xreg2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/WHILELT--predicate-pair---While-incrementing-signed-scalar-less-than-scalar--pair-of-predicates--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svwhilelt_b8[_u64]_x2

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwhilelt_b8%5B_u64%5D_x2

### Signature (source notation)

```c
svboolx2_t svwhilelt_b8[_u64]_x2(uint64_t rn, uint64_t rm);
```

### Description

While incrementing unsigned scalar lower than scalar (pair of predicates)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Initialization / While counter meets condition (forward)

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
WHILELO { Preg1.B, Preg2.B }, Xreg1, Xreg2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/WHILELO--predicate-pair---While-incrementing-unsigned-scalar-lower-than-scalar--pair-of-predicates--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svwhilelt_c16[_s64]

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwhilelt_c16%5B_s64%5D

### Signature (source notation)

```c
svcount_t svwhilelt_c16[_s64](int64_t rn, int64_t rm, uint64_t vl);
```

### Description

While incrementing signed scalar less than scalar (predicate-as-counter)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Initialization / While counter meets condition (forward)

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
WHILELT PNreg1.H, Xreg1, Xreg2, <VL>
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/WHILELT--predicate-as-counter---While-incrementing-signed-scalar-less-than-scalar--predicate-as-counter--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svwhilelt_c16[_u64]

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwhilelt_c16%5B_u64%5D

### Signature (source notation)

```c
svcount_t svwhilelt_c16[_u64](uint64_t rn, uint64_t rm, uint64_t vl);
```

### Description

While incrementing unsigned scalar lower than scalar (predicate-as-counter)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Initialization / While counter meets condition (forward)

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
WHILELO PNreg1.H, Xreg1, Xreg2, <VL>
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/WHILELO--predicate-as-counter---While-incrementing-unsigned-scalar-lower-than-scalar--predicate-as-counter--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svwhilelt_c32[_s64]

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwhilelt_c32%5B_s64%5D

### Signature (source notation)

```c
svcount_t svwhilelt_c32[_s64](int64_t rn, int64_t rm, uint64_t vl);
```

### Description

While incrementing signed scalar less than scalar (predicate-as-counter)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Initialization / While counter meets condition (forward)

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
WHILELT PNreg1.S, Xreg1, Xreg2, <VL>
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/WHILELT--predicate-as-counter---While-incrementing-signed-scalar-less-than-scalar--predicate-as-counter--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svwhilelt_c32[_u64]

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwhilelt_c32%5B_u64%5D

### Signature (source notation)

```c
svcount_t svwhilelt_c32[_u64](uint64_t rn, uint64_t rm, uint64_t vl);
```

### Description

While incrementing unsigned scalar lower than scalar (predicate-as-counter)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Initialization / While counter meets condition (forward)

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
WHILELO PNreg1.S, Xreg1, Xreg2, <VL>
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/WHILELO--predicate-as-counter---While-incrementing-unsigned-scalar-lower-than-scalar--predicate-as-counter--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svwhilelt_c64[_s64]

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwhilelt_c64%5B_s64%5D

### Signature (source notation)

```c
svcount_t svwhilelt_c64[_s64](int64_t rn, int64_t rm, uint64_t vl);
```

### Description

While incrementing signed scalar less than scalar (predicate-as-counter)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Initialization / While counter meets condition (forward)

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
WHILELT PNreg1.D, Xreg1, Xreg2, <VL>
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/WHILELT--predicate-as-counter---While-incrementing-signed-scalar-less-than-scalar--predicate-as-counter--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svwhilelt_c64[_u64]

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwhilelt_c64%5B_u64%5D

### Signature (source notation)

```c
svcount_t svwhilelt_c64[_u64](uint64_t rn, uint64_t rm, uint64_t vl);
```

### Description

While incrementing unsigned scalar lower than scalar (predicate-as-counter)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Initialization / While counter meets condition (forward)

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
WHILELO PNreg1.D, Xreg1, Xreg2, <VL>
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/WHILELO--predicate-as-counter---While-incrementing-unsigned-scalar-lower-than-scalar--predicate-as-counter--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svwhilelt_c8[_s64]

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwhilelt_c8%5B_s64%5D

### Signature (source notation)

```c
svcount_t svwhilelt_c8[_s64](int64_t rn, int64_t rm, uint64_t vl);
```

### Description

While incrementing signed scalar less than scalar (predicate-as-counter)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Initialization / While counter meets condition (forward)

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
WHILELT PNreg1.B, Xreg1, Xreg2, <VL>
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/WHILELT--predicate-as-counter---While-incrementing-signed-scalar-less-than-scalar--predicate-as-counter--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svwhilelt_c8[_u64]

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwhilelt_c8%5B_u64%5D

### Signature (source notation)

```c
svcount_t svwhilelt_c8[_u64](uint64_t rn, uint64_t rm, uint64_t vl);
```

### Description

While incrementing unsigned scalar lower than scalar (predicate-as-counter)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Initialization / While counter meets condition (forward)

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
WHILELO PNreg1.B, Xreg1, Xreg2, <VL>
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/WHILELO--predicate-as-counter---While-incrementing-unsigned-scalar-lower-than-scalar--predicate-as-counter--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

