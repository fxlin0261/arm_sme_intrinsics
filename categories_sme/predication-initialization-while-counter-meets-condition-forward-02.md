# SME / Predication / Initialization / While counter meets condition (forward) — Part 2

## svwhilelt_b8[_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwhilelt_b8%5B_s32%5D

### Signature (source notation)

```c
svbool_t svwhilelt_b8[_s32](int32_t op1, int32_t op2);
```

### Description

While incrementing scalar is less than

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Predication / Initialization / While counter meets condition (forward)

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
  "return_base_type": "int",
  "element_bit_size": "32",
  "value": "svbool_t"
}
```

### Argument preparation and constraints

```json
{
  "op1": {
    "register": "Wop1"
  },
  "op2": {
    "register": "Wop2"
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
WHILELT Presult.B, Wop1, Wop2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/WHILELT--predicate-pair---While-incrementing-signed-scalar-less-than-scalar--pair-of-predicates--

### Operation

Source operation ID: `SveOperation_svwhilelt_b8_s32`

**Operation**



Return a predicate in which element *i* is active if, for all values *j* in the range [0, *i*], adding *j* to `op1` gives a value that is less than `op2`.  The sequence will therefore yield at least one false predicate element before the addition wraps.



The first type suffix indicates the number of bits in each predicate element.  For example, a suffix of `_b8` indicates that the predicate controls 8-bit data, so element *i* corresponds to bit *i* of the predicate.  A suffix of `_b16` indicates that the predicate controls 16-bit data, so element *i* corresponds to bit *i*×2 of the predicate.  When an element has more than one predicate bit associated with it, only the lowest of those bits is ever true.

## svwhilelt_b8[_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwhilelt_b8%5B_s64%5D

### Signature (source notation)

```c
svbool_t svwhilelt_b8[_s64](int64_t op1, int64_t op2);
```

### Description

While incrementing scalar is less than

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Predication / Initialization / While counter meets condition (forward)

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
  "return_base_type": "int",
  "element_bit_size": "64",
  "value": "svbool_t"
}
```

### Argument preparation and constraints

```json
{
  "op1": {
    "register": "Xop1"
  },
  "op2": {
    "register": "Xop2"
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
WHILELT Presult.B, Xop1, Xop2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/WHILELT--predicate-pair---While-incrementing-signed-scalar-less-than-scalar--pair-of-predicates--

### Operation

Source operation ID: `SveOperation_svwhilelt_b8_s32`

**Operation**



Return a predicate in which element *i* is active if, for all values *j* in the range [0, *i*], adding *j* to `op1` gives a value that is less than `op2`.  The sequence will therefore yield at least one false predicate element before the addition wraps.



The first type suffix indicates the number of bits in each predicate element.  For example, a suffix of `_b8` indicates that the predicate controls 8-bit data, so element *i* corresponds to bit *i* of the predicate.  A suffix of `_b16` indicates that the predicate controls 16-bit data, so element *i* corresponds to bit *i*×2 of the predicate.  When an element has more than one predicate bit associated with it, only the lowest of those bits is ever true.

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

## svwhilelt_b8[_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwhilelt_b8%5B_u32%5D

### Signature (source notation)

```c
svbool_t svwhilelt_b8[_u32](uint32_t op1, uint32_t op2);
```

### Description

While incrementing scalar is less than

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Predication / Initialization / While counter meets condition (forward)

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
  "element_bit_size": "32",
  "value": "svbool_t"
}
```

### Argument preparation and constraints

```json
{
  "op1": {
    "register": "Wop1"
  },
  "op2": {
    "register": "Wop2"
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
WHILELO Presult.B, Wop1, Wop2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/WHILELO--predicate-pair---While-incrementing-unsigned-scalar-lower-than-scalar--pair-of-predicates--

### Operation

Source operation ID: `SveOperation_svwhilelt_b8_u32`

**Operation**



Return a predicate in which element *i* is active if, for all values *j* in the range [0, *i*], adding *j* to `op1` gives a value that is less than `op2`.  The sequence will therefore yield at least one false predicate element before the addition wraps.



The first type suffix indicates the number of bits in each predicate element.  For example, a suffix of `_b8` indicates that the predicate controls 8-bit data, so element *i* corresponds to bit *i* of the predicate.  A suffix of `_b16` indicates that the predicate controls 16-bit data, so element *i* corresponds to bit *i*×2 of the predicate.  When an element has more than one predicate bit associated with it, only the lowest of those bits is ever true.



`svwhilelt` handles both signed and unsigned inputs; there are no separate functions for WHILELO.

## svwhilelt_b8[_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwhilelt_b8%5B_u64%5D

### Signature (source notation)

```c
svbool_t svwhilelt_b8[_u64](uint64_t op1, uint64_t op2);
```

### Description

While incrementing scalar is less than

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Predication / Initialization / While counter meets condition (forward)

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
  "value": "svbool_t"
}
```

### Argument preparation and constraints

```json
{
  "op1": {
    "register": "Xop1"
  },
  "op2": {
    "register": "Xop2"
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
WHILELO Presult.B, Xop1, Xop2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/WHILELO--predicate-pair---While-incrementing-unsigned-scalar-lower-than-scalar--pair-of-predicates--

### Operation

Source operation ID: `SveOperation_svwhilelt_b8_u32`

**Operation**



Return a predicate in which element *i* is active if, for all values *j* in the range [0, *i*], adding *j* to `op1` gives a value that is less than `op2`.  The sequence will therefore yield at least one false predicate element before the addition wraps.



The first type suffix indicates the number of bits in each predicate element.  For example, a suffix of `_b8` indicates that the predicate controls 8-bit data, so element *i* corresponds to bit *i* of the predicate.  A suffix of `_b16` indicates that the predicate controls 16-bit data, so element *i* corresponds to bit *i*×2 of the predicate.  When an element has more than one predicate bit associated with it, only the lowest of those bits is ever true.



`svwhilelt` handles both signed and unsigned inputs; there are no separate functions for WHILELO.

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

