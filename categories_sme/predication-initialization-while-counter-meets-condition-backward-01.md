# SME / Predication / Initialization / While counter meets condition (backward) — Part 1

## svwhilege_b16[_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwhilege_b16%5B_s32%5D

### Signature (source notation)

```c
svbool_t svwhilege_b16[_s32](int32_t op1, int32_t op2);
```

### Description

While decrementing scalar is greater than or equal to

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Initialization / While counter meets condition (backward)

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
    "Presult.H": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
WHILEGE Presult.H, Wop1, Wop2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/WHILEGE--predicate---While-decrementing-signed-scalar-greater-than-or-equal-to-scalar-

### Operation

Source operation ID: `SveOperation_svwhilege_b8_s32`

**Operation**



Return a predicate of *n* elements in which element *n* - *i* - 1 is active if, for all values *j* in the range [0, *i*], subtracting *j* from `op1` gives a value that is greater than or equal to `op2`.  The subtraction uses modulo arithmetic in `int32_t`, so the minimum value minus one gives the maximum value.



The first type suffix indicates the number of bits in each predicate element.  For example, a suffix of `_b8` indicates that the predicate controls 8-bit data, so element *i* corresponds to bit *i* of the predicate.  A suffix of `_b16` indicates that the predicate controls 16-bit data, so element *i* corresponds to bit *i*×2 of the predicate.  When an element has more than one predicate bit associated with it, only the lowest of those bits is ever true.



Note that when `op2` is the minimum value, every element in the returned predicate will be active.

## svwhilege_b16[_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwhilege_b16%5B_s64%5D

### Signature (source notation)

```c
svbool_t svwhilege_b16[_s64](int64_t op1, int64_t op2);
```

### Description

While decrementing scalar is greater than or equal to

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Initialization / While counter meets condition (backward)

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
    "Presult.H": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
WHILEGE Presult.H, Xop1, Xop2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/WHILEGE--predicate---While-decrementing-signed-scalar-greater-than-or-equal-to-scalar-

### Operation

Source operation ID: `SveOperation_svwhilege_b8_s64`

**Operation**



Return a predicate of *n* elements in which element *n* - *i* - 1 is active if, for all values *j* in the range [0, *i*], subtracting *j* from `op1` gives a value that is greater than or equal to `op2`.  The subtraction uses modulo arithmetic in `int64_t`, so the minimum value minus one gives the maximum value.



The first type suffix indicates the number of bits in each predicate element.  For example, a suffix of `_b8` indicates that the predicate controls 8-bit data, so element *i* corresponds to bit *i* of the predicate.  A suffix of `_b16` indicates that the predicate controls 16-bit data, so element *i* corresponds to bit *i*×2 of the predicate.  When an element has more than one predicate bit associated with it, only the lowest of those bits is ever true.



Note that when `op2` is the minimum value, every element in the returned predicate will be active.

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

## svwhilege_b16[_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwhilege_b16%5B_u32%5D

### Signature (source notation)

```c
svbool_t svwhilege_b16[_u32](uint32_t op1, uint32_t op2);
```

### Description

While decrementing scalar is greater than or equal to

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Initialization / While counter meets condition (backward)

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
    "Presult.H": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
WHILEHS Presult.H, Wop1, Wop2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/WHILEHS--predicate-pair---While-decrementing-unsigned-scalar-higher-or-same-as-scalar--pair-of-predicates--

### Operation

Source operation ID: `SveOperation_svwhilege_b8_u32`

**Operation**



Return a predicate of *n* elements in which element *n* - *i* - 1 is active if, for all values *j* in the range [0, *i*], subtracting *j* from `op1` gives a value that is greater than or equal to `op2`.  The subtraction uses modulo arithmetic in `uint32_t`, so the minimum value minus one gives the maximum value.



The first type suffix indicates the number of bits in each predicate element.  For example, a suffix of `_b8` indicates that the predicate controls 8-bit data, so element *i* corresponds to bit *i* of the predicate.  A suffix of `_b16` indicates that the predicate controls 16-bit data, so element *i* corresponds to bit *i*×2 of the predicate.  When an element has more than one predicate bit associated with it, only the lowest of those bits is ever true.



`svwhilege` handles both signed and unsigned inputs; there are no separate functions for WHILEHS. Note that when `op2` is the minimum value, every element in the returned predicate will be active.

## svwhilege_b16[_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwhilege_b16%5B_u64%5D

### Signature (source notation)

```c
svbool_t svwhilege_b16[_u64](uint64_t op1, uint64_t op2);
```

### Description

While decrementing scalar is greater than or equal to

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Initialization / While counter meets condition (backward)

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
    "Presult.H": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
WHILEHS Presult.H, Xop1, Xop2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/WHILEHS--predicate-pair---While-decrementing-unsigned-scalar-higher-or-same-as-scalar--pair-of-predicates--

### Operation

Source operation ID: `SveOperation_svwhilege_b8_u64`

**Operation**



Return a predicate of *n* elements in which element *n* - *i* - 1 is active if, for all values *j* in the range [0, *i*], subtracting *j* from `op1` gives a value that is greater than or equal to `op2`.  The subtraction uses modulo arithmetic in `uint64_t`, so the minimum value minus one gives the maximum value.



The first type suffix indicates the number of bits in each predicate element.  For example, a suffix of `_b8` indicates that the predicate controls 8-bit data, so element *i* corresponds to bit *i* of the predicate.  A suffix of `_b16` indicates that the predicate controls 16-bit data, so element *i* corresponds to bit *i*×2 of the predicate.  When an element has more than one predicate bit associated with it, only the lowest of those bits is ever true.



`svwhilege` handles both signed and unsigned inputs; there are no separate functions for WHILEHS. Note that when `op2` is the minimum value, every element in the returned predicate will be active.

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

## svwhilege_b32[_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwhilege_b32%5B_s32%5D

### Signature (source notation)

```c
svbool_t svwhilege_b32[_s32](int32_t op1, int32_t op2);
```

### Description

While decrementing scalar is greater than or equal to

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Initialization / While counter meets condition (backward)

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
    "Presult.S": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
WHILEGE Presult.S, Wop1, Wop2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/WHILEGE--predicate---While-decrementing-signed-scalar-greater-than-or-equal-to-scalar-

### Operation

Source operation ID: `SveOperation_svwhilege_b8_s32`

**Operation**



Return a predicate of *n* elements in which element *n* - *i* - 1 is active if, for all values *j* in the range [0, *i*], subtracting *j* from `op1` gives a value that is greater than or equal to `op2`.  The subtraction uses modulo arithmetic in `int32_t`, so the minimum value minus one gives the maximum value.



The first type suffix indicates the number of bits in each predicate element.  For example, a suffix of `_b8` indicates that the predicate controls 8-bit data, so element *i* corresponds to bit *i* of the predicate.  A suffix of `_b16` indicates that the predicate controls 16-bit data, so element *i* corresponds to bit *i*×2 of the predicate.  When an element has more than one predicate bit associated with it, only the lowest of those bits is ever true.



Note that when `op2` is the minimum value, every element in the returned predicate will be active.

## svwhilege_b32[_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwhilege_b32%5B_s64%5D

### Signature (source notation)

```c
svbool_t svwhilege_b32[_s64](int64_t op1, int64_t op2);
```

### Description

While decrementing scalar is greater than or equal to

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Initialization / While counter meets condition (backward)

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
    "Presult.S": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
WHILEGE Presult.S, Xop1, Xop2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/WHILEGE--predicate---While-decrementing-signed-scalar-greater-than-or-equal-to-scalar-

### Operation

Source operation ID: `SveOperation_svwhilege_b8_s64`

**Operation**



Return a predicate of *n* elements in which element *n* - *i* - 1 is active if, for all values *j* in the range [0, *i*], subtracting *j* from `op1` gives a value that is greater than or equal to `op2`.  The subtraction uses modulo arithmetic in `int64_t`, so the minimum value minus one gives the maximum value.



The first type suffix indicates the number of bits in each predicate element.  For example, a suffix of `_b8` indicates that the predicate controls 8-bit data, so element *i* corresponds to bit *i* of the predicate.  A suffix of `_b16` indicates that the predicate controls 16-bit data, so element *i* corresponds to bit *i*×2 of the predicate.  When an element has more than one predicate bit associated with it, only the lowest of those bits is ever true.



Note that when `op2` is the minimum value, every element in the returned predicate will be active.

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

## svwhilege_b32[_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwhilege_b32%5B_u32%5D

### Signature (source notation)

```c
svbool_t svwhilege_b32[_u32](uint32_t op1, uint32_t op2);
```

### Description

While decrementing scalar is greater than or equal to

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Initialization / While counter meets condition (backward)

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
    "Presult.S": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
WHILEHS Presult.S, Wop1, Wop2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/WHILEHS--predicate-pair---While-decrementing-unsigned-scalar-higher-or-same-as-scalar--pair-of-predicates--

### Operation

Source operation ID: `SveOperation_svwhilege_b8_u32`

**Operation**



Return a predicate of *n* elements in which element *n* - *i* - 1 is active if, for all values *j* in the range [0, *i*], subtracting *j* from `op1` gives a value that is greater than or equal to `op2`.  The subtraction uses modulo arithmetic in `uint32_t`, so the minimum value minus one gives the maximum value.



The first type suffix indicates the number of bits in each predicate element.  For example, a suffix of `_b8` indicates that the predicate controls 8-bit data, so element *i* corresponds to bit *i* of the predicate.  A suffix of `_b16` indicates that the predicate controls 16-bit data, so element *i* corresponds to bit *i*×2 of the predicate.  When an element has more than one predicate bit associated with it, only the lowest of those bits is ever true.



`svwhilege` handles both signed and unsigned inputs; there are no separate functions for WHILEHS. Note that when `op2` is the minimum value, every element in the returned predicate will be active.

## svwhilege_b32[_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwhilege_b32%5B_u64%5D

### Signature (source notation)

```c
svbool_t svwhilege_b32[_u64](uint64_t op1, uint64_t op2);
```

### Description

While decrementing scalar is greater than or equal to

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Initialization / While counter meets condition (backward)

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
    "Presult.S": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
WHILEHS Presult.S, Xop1, Xop2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/WHILEHS--predicate-pair---While-decrementing-unsigned-scalar-higher-or-same-as-scalar--pair-of-predicates--

### Operation

Source operation ID: `SveOperation_svwhilege_b8_u64`

**Operation**



Return a predicate of *n* elements in which element *n* - *i* - 1 is active if, for all values *j* in the range [0, *i*], subtracting *j* from `op1` gives a value that is greater than or equal to `op2`.  The subtraction uses modulo arithmetic in `uint64_t`, so the minimum value minus one gives the maximum value.



The first type suffix indicates the number of bits in each predicate element.  For example, a suffix of `_b8` indicates that the predicate controls 8-bit data, so element *i* corresponds to bit *i* of the predicate.  A suffix of `_b16` indicates that the predicate controls 16-bit data, so element *i* corresponds to bit *i*×2 of the predicate.  When an element has more than one predicate bit associated with it, only the lowest of those bits is ever true.



`svwhilege` handles both signed and unsigned inputs; there are no separate functions for WHILEHS. Note that when `op2` is the minimum value, every element in the returned predicate will be active.

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

## svwhilege_b64[_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwhilege_b64%5B_s32%5D

### Signature (source notation)

```c
svbool_t svwhilege_b64[_s32](int32_t op1, int32_t op2);
```

### Description

While decrementing scalar is greater than or equal to

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Initialization / While counter meets condition (backward)

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
    "Presult.D": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
WHILEGE Presult.D, Wop1, Wop2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/WHILEGE--predicate---While-decrementing-signed-scalar-greater-than-or-equal-to-scalar-

### Operation

Source operation ID: `SveOperation_svwhilege_b8_s32`

**Operation**



Return a predicate of *n* elements in which element *n* - *i* - 1 is active if, for all values *j* in the range [0, *i*], subtracting *j* from `op1` gives a value that is greater than or equal to `op2`.  The subtraction uses modulo arithmetic in `int32_t`, so the minimum value minus one gives the maximum value.



The first type suffix indicates the number of bits in each predicate element.  For example, a suffix of `_b8` indicates that the predicate controls 8-bit data, so element *i* corresponds to bit *i* of the predicate.  A suffix of `_b16` indicates that the predicate controls 16-bit data, so element *i* corresponds to bit *i*×2 of the predicate.  When an element has more than one predicate bit associated with it, only the lowest of those bits is ever true.



Note that when `op2` is the minimum value, every element in the returned predicate will be active.

## svwhilege_b64[_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwhilege_b64%5B_s64%5D

### Signature (source notation)

```c
svbool_t svwhilege_b64[_s64](int64_t op1, int64_t op2);
```

### Description

While decrementing scalar is greater than or equal to

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Initialization / While counter meets condition (backward)

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
    "Presult.D": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
WHILEGE Presult.D, Xop1, Xop2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/WHILEGE--predicate---While-decrementing-signed-scalar-greater-than-or-equal-to-scalar-

### Operation

Source operation ID: `SveOperation_svwhilege_b8_s64`

**Operation**



Return a predicate of *n* elements in which element *n* - *i* - 1 is active if, for all values *j* in the range [0, *i*], subtracting *j* from `op1` gives a value that is greater than or equal to `op2`.  The subtraction uses modulo arithmetic in `int64_t`, so the minimum value minus one gives the maximum value.



The first type suffix indicates the number of bits in each predicate element.  For example, a suffix of `_b8` indicates that the predicate controls 8-bit data, so element *i* corresponds to bit *i* of the predicate.  A suffix of `_b16` indicates that the predicate controls 16-bit data, so element *i* corresponds to bit *i*×2 of the predicate.  When an element has more than one predicate bit associated with it, only the lowest of those bits is ever true.



Note that when `op2` is the minimum value, every element in the returned predicate will be active.

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

## svwhilege_b64[_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwhilege_b64%5B_u32%5D

### Signature (source notation)

```c
svbool_t svwhilege_b64[_u32](uint32_t op1, uint32_t op2);
```

### Description

While decrementing scalar is greater than or equal to

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Initialization / While counter meets condition (backward)

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
    "Presult.D": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
WHILEHS Presult.D, Wop1, Wop2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/WHILEHS--predicate-pair---While-decrementing-unsigned-scalar-higher-or-same-as-scalar--pair-of-predicates--

### Operation

Source operation ID: `SveOperation_svwhilege_b8_u32`

**Operation**



Return a predicate of *n* elements in which element *n* - *i* - 1 is active if, for all values *j* in the range [0, *i*], subtracting *j* from `op1` gives a value that is greater than or equal to `op2`.  The subtraction uses modulo arithmetic in `uint32_t`, so the minimum value minus one gives the maximum value.



The first type suffix indicates the number of bits in each predicate element.  For example, a suffix of `_b8` indicates that the predicate controls 8-bit data, so element *i* corresponds to bit *i* of the predicate.  A suffix of `_b16` indicates that the predicate controls 16-bit data, so element *i* corresponds to bit *i*×2 of the predicate.  When an element has more than one predicate bit associated with it, only the lowest of those bits is ever true.



`svwhilege` handles both signed and unsigned inputs; there are no separate functions for WHILEHS. Note that when `op2` is the minimum value, every element in the returned predicate will be active.

## svwhilege_b64[_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwhilege_b64%5B_u64%5D

### Signature (source notation)

```c
svbool_t svwhilege_b64[_u64](uint64_t op1, uint64_t op2);
```

### Description

While decrementing scalar is greater than or equal to

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Initialization / While counter meets condition (backward)

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
    "Presult.D": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
WHILEHS Presult.D, Xop1, Xop2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/WHILEHS--predicate-pair---While-decrementing-unsigned-scalar-higher-or-same-as-scalar--pair-of-predicates--

### Operation

Source operation ID: `SveOperation_svwhilege_b8_u64`

**Operation**



Return a predicate of *n* elements in which element *n* - *i* - 1 is active if, for all values *j* in the range [0, *i*], subtracting *j* from `op1` gives a value that is greater than or equal to `op2`.  The subtraction uses modulo arithmetic in `uint64_t`, so the minimum value minus one gives the maximum value.



The first type suffix indicates the number of bits in each predicate element.  For example, a suffix of `_b8` indicates that the predicate controls 8-bit data, so element *i* corresponds to bit *i* of the predicate.  A suffix of `_b16` indicates that the predicate controls 16-bit data, so element *i* corresponds to bit *i*×2 of the predicate.  When an element has more than one predicate bit associated with it, only the lowest of those bits is ever true.



`svwhilege` handles both signed and unsigned inputs; there are no separate functions for WHILEHS. Note that when `op2` is the minimum value, every element in the returned predicate will be active.

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

## svwhilege_b8[_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwhilege_b8%5B_s32%5D

### Signature (source notation)

```c
svbool_t svwhilege_b8[_s32](int32_t op1, int32_t op2);
```

### Description

While decrementing scalar is greater than or equal to

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Initialization / While counter meets condition (backward)

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
WHILEGE Presult.B, Wop1, Wop2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/WHILEGE--predicate---While-decrementing-signed-scalar-greater-than-or-equal-to-scalar-

### Operation

Source operation ID: `SveOperation_svwhilege_b8_s32`

**Operation**



Return a predicate of *n* elements in which element *n* - *i* - 1 is active if, for all values *j* in the range [0, *i*], subtracting *j* from `op1` gives a value that is greater than or equal to `op2`.  The subtraction uses modulo arithmetic in `int32_t`, so the minimum value minus one gives the maximum value.



The first type suffix indicates the number of bits in each predicate element.  For example, a suffix of `_b8` indicates that the predicate controls 8-bit data, so element *i* corresponds to bit *i* of the predicate.  A suffix of `_b16` indicates that the predicate controls 16-bit data, so element *i* corresponds to bit *i*×2 of the predicate.  When an element has more than one predicate bit associated with it, only the lowest of those bits is ever true.



Note that when `op2` is the minimum value, every element in the returned predicate will be active.

## svwhilege_b8[_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwhilege_b8%5B_s64%5D

### Signature (source notation)

```c
svbool_t svwhilege_b8[_s64](int64_t op1, int64_t op2);
```

### Description

While decrementing scalar is greater than or equal to

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Initialization / While counter meets condition (backward)

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
WHILEGE Presult.B, Xop1, Xop2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/WHILEGE--predicate---While-decrementing-signed-scalar-greater-than-or-equal-to-scalar-

### Operation

Source operation ID: `SveOperation_svwhilege_b8_s64`

**Operation**



Return a predicate of *n* elements in which element *n* - *i* - 1 is active if, for all values *j* in the range [0, *i*], subtracting *j* from `op1` gives a value that is greater than or equal to `op2`.  The subtraction uses modulo arithmetic in `int64_t`, so the minimum value minus one gives the maximum value.



The first type suffix indicates the number of bits in each predicate element.  For example, a suffix of `_b8` indicates that the predicate controls 8-bit data, so element *i* corresponds to bit *i* of the predicate.  A suffix of `_b16` indicates that the predicate controls 16-bit data, so element *i* corresponds to bit *i*×2 of the predicate.  When an element has more than one predicate bit associated with it, only the lowest of those bits is ever true.



Note that when `op2` is the minimum value, every element in the returned predicate will be active.

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

## svwhilege_b8[_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwhilege_b8%5B_u32%5D

### Signature (source notation)

```c
svbool_t svwhilege_b8[_u32](uint32_t op1, uint32_t op2);
```

### Description

While decrementing scalar is greater than or equal to

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Initialization / While counter meets condition (backward)

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
WHILEHS Presult.B, Wop1, Wop2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/WHILEHS--predicate-pair---While-decrementing-unsigned-scalar-higher-or-same-as-scalar--pair-of-predicates--

### Operation

Source operation ID: `SveOperation_svwhilege_b8_u32`

**Operation**



Return a predicate of *n* elements in which element *n* - *i* - 1 is active if, for all values *j* in the range [0, *i*], subtracting *j* from `op1` gives a value that is greater than or equal to `op2`.  The subtraction uses modulo arithmetic in `uint32_t`, so the minimum value minus one gives the maximum value.



The first type suffix indicates the number of bits in each predicate element.  For example, a suffix of `_b8` indicates that the predicate controls 8-bit data, so element *i* corresponds to bit *i* of the predicate.  A suffix of `_b16` indicates that the predicate controls 16-bit data, so element *i* corresponds to bit *i*×2 of the predicate.  When an element has more than one predicate bit associated with it, only the lowest of those bits is ever true.



`svwhilege` handles both signed and unsigned inputs; there are no separate functions for WHILEHS. Note that when `op2` is the minimum value, every element in the returned predicate will be active.

## svwhilege_b8[_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwhilege_b8%5B_u64%5D

### Signature (source notation)

```c
svbool_t svwhilege_b8[_u64](uint64_t op1, uint64_t op2);
```

### Description

While decrementing scalar is greater than or equal to

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Initialization / While counter meets condition (backward)

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
WHILEHS Presult.B, Xop1, Xop2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/WHILEHS--predicate-pair---While-decrementing-unsigned-scalar-higher-or-same-as-scalar--pair-of-predicates--

### Operation

Source operation ID: `SveOperation_svwhilege_b8_u64`

**Operation**



Return a predicate of *n* elements in which element *n* - *i* - 1 is active if, for all values *j* in the range [0, *i*], subtracting *j* from `op1` gives a value that is greater than or equal to `op2`.  The subtraction uses modulo arithmetic in `uint64_t`, so the minimum value minus one gives the maximum value.



The first type suffix indicates the number of bits in each predicate element.  For example, a suffix of `_b8` indicates that the predicate controls 8-bit data, so element *i* corresponds to bit *i* of the predicate.  A suffix of `_b16` indicates that the predicate controls 16-bit data, so element *i* corresponds to bit *i*×2 of the predicate.  When an element has more than one predicate bit associated with it, only the lowest of those bits is ever true.



`svwhilege` handles both signed and unsigned inputs; there are no separate functions for WHILEHS. Note that when `op2` is the minimum value, every element in the returned predicate will be active.

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

## svwhilegt_b16[_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwhilegt_b16%5B_s32%5D

### Signature (source notation)

```c
svbool_t svwhilegt_b16[_s32](int32_t op1, int32_t op2);
```

### Description

While decrementing scalar is greater than

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Initialization / While counter meets condition (backward)

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
    "Presult.H": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
WHILEGT Presult.H, Wop1, Wop2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/WHILEGT--predicate-pair---While-decrementing-signed-scalar-greater-than-scalar--pair-of-predicates--

### Operation

Source operation ID: `SveOperation_svwhilegt_b8_s32`

**Operation**



Return a predicate of *n* elements in which element *n* - *i* - 1 is active if, for all values *j* in the range [0, *i*], subtracting *j* from `op1` gives a value that is greater than `op2`.  The sequence will therefore yield at least one false predicate element before the subtraction wraps.



The first type suffix indicates the number of bits in each predicate element.  For example, a suffix of `_b8` indicates that the predicate controls 8-bit data, so element *i* corresponds to bit *i* of the predicate.  A suffix of `_b16` indicates that the predicate controls 16-bit data, so element *i* corresponds to bit *i*×2 of the predicate.  When an element has more than one predicate bit associated with it, only the lowest of those bits is ever true.

## svwhilegt_b16[_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwhilegt_b16%5B_s64%5D

### Signature (source notation)

```c
svbool_t svwhilegt_b16[_s64](int64_t op1, int64_t op2);
```

### Description

While decrementing scalar is greater than

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Initialization / While counter meets condition (backward)

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
    "Presult.H": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
WHILEGT Presult.H, Xop1, Xop2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/WHILEGT--predicate-pair---While-decrementing-signed-scalar-greater-than-scalar--pair-of-predicates--

### Operation

Source operation ID: `SveOperation_svwhilegt_b8_s32`

**Operation**



Return a predicate of *n* elements in which element *n* - *i* - 1 is active if, for all values *j* in the range [0, *i*], subtracting *j* from `op1` gives a value that is greater than `op2`.  The sequence will therefore yield at least one false predicate element before the subtraction wraps.



The first type suffix indicates the number of bits in each predicate element.  For example, a suffix of `_b8` indicates that the predicate controls 8-bit data, so element *i* corresponds to bit *i* of the predicate.  A suffix of `_b16` indicates that the predicate controls 16-bit data, so element *i* corresponds to bit *i*×2 of the predicate.  When an element has more than one predicate bit associated with it, only the lowest of those bits is ever true.

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

## svwhilegt_b16[_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwhilegt_b16%5B_u32%5D

### Signature (source notation)

```c
svbool_t svwhilegt_b16[_u32](uint32_t op1, uint32_t op2);
```

### Description

While decrementing scalar is greater than

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Initialization / While counter meets condition (backward)

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
    "Presult.H": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
WHILEHI Presult.H, Wop1, Wop2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/WHILEHI--predicate-pair---While-decrementing-unsigned-scalar-higher-than-scalar--pair-of-predicates--

### Operation

Source operation ID: `SveOperation_svwhilegt_b8_u32`

**Operation**



Return a predicate of *n* elements in which element *n* - *i* - 1 is active if, for all values *j* in the range [0, *i*], subtracting *j* from `op1` gives a value that is greater than `op2`.  The sequence will therefore yield at least one false predicate element before the subtraction wraps.



The first type suffix indicates the number of bits in each predicate element.  For example, a suffix of `_b8` indicates that the predicate controls 8-bit data, so element *i* corresponds to bit *i* of the predicate.  A suffix of `_b16` indicates that the predicate controls 16-bit data, so element *i* corresponds to bit *i*×2 of the predicate.  When an element has more than one predicate bit associated with it, only the lowest of those bits is ever true.



`svwhilegt` handles both signed and unsigned inputs; there are no separate functions for WHILEHI.

## svwhilegt_b16[_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwhilegt_b16%5B_u64%5D

### Signature (source notation)

```c
svbool_t svwhilegt_b16[_u64](uint64_t op1, uint64_t op2);
```

### Description

While decrementing scalar is greater than

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Initialization / While counter meets condition (backward)

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
    "Presult.H": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
WHILEHI Presult.H, Xop1, Xop2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/WHILEHI--predicate-pair---While-decrementing-unsigned-scalar-higher-than-scalar--pair-of-predicates--

### Operation

Source operation ID: `SveOperation_svwhilegt_b8_u32`

**Operation**



Return a predicate of *n* elements in which element *n* - *i* - 1 is active if, for all values *j* in the range [0, *i*], subtracting *j* from `op1` gives a value that is greater than `op2`.  The sequence will therefore yield at least one false predicate element before the subtraction wraps.



The first type suffix indicates the number of bits in each predicate element.  For example, a suffix of `_b8` indicates that the predicate controls 8-bit data, so element *i* corresponds to bit *i* of the predicate.  A suffix of `_b16` indicates that the predicate controls 16-bit data, so element *i* corresponds to bit *i*×2 of the predicate.  When an element has more than one predicate bit associated with it, only the lowest of those bits is ever true.



`svwhilegt` handles both signed and unsigned inputs; there are no separate functions for WHILEHI.

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

## svwhilegt_b32[_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwhilegt_b32%5B_s32%5D

### Signature (source notation)

```c
svbool_t svwhilegt_b32[_s32](int32_t op1, int32_t op2);
```

### Description

While decrementing scalar is greater than

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Initialization / While counter meets condition (backward)

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
    "Presult.S": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
WHILEGT Presult.S, Wop1, Wop2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/WHILEGT--predicate-pair---While-decrementing-signed-scalar-greater-than-scalar--pair-of-predicates--

### Operation

Source operation ID: `SveOperation_svwhilegt_b8_s32`

**Operation**



Return a predicate of *n* elements in which element *n* - *i* - 1 is active if, for all values *j* in the range [0, *i*], subtracting *j* from `op1` gives a value that is greater than `op2`.  The sequence will therefore yield at least one false predicate element before the subtraction wraps.



The first type suffix indicates the number of bits in each predicate element.  For example, a suffix of `_b8` indicates that the predicate controls 8-bit data, so element *i* corresponds to bit *i* of the predicate.  A suffix of `_b16` indicates that the predicate controls 16-bit data, so element *i* corresponds to bit *i*×2 of the predicate.  When an element has more than one predicate bit associated with it, only the lowest of those bits is ever true.

## svwhilegt_b32[_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwhilegt_b32%5B_s64%5D

### Signature (source notation)

```c
svbool_t svwhilegt_b32[_s64](int64_t op1, int64_t op2);
```

### Description

While decrementing scalar is greater than

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Initialization / While counter meets condition (backward)

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
    "Presult.S": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
WHILEGT Presult.S, Xop1, Xop2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/WHILEGT--predicate-pair---While-decrementing-signed-scalar-greater-than-scalar--pair-of-predicates--

### Operation

Source operation ID: `SveOperation_svwhilegt_b8_s32`

**Operation**



Return a predicate of *n* elements in which element *n* - *i* - 1 is active if, for all values *j* in the range [0, *i*], subtracting *j* from `op1` gives a value that is greater than `op2`.  The sequence will therefore yield at least one false predicate element before the subtraction wraps.



The first type suffix indicates the number of bits in each predicate element.  For example, a suffix of `_b8` indicates that the predicate controls 8-bit data, so element *i* corresponds to bit *i* of the predicate.  A suffix of `_b16` indicates that the predicate controls 16-bit data, so element *i* corresponds to bit *i*×2 of the predicate.  When an element has more than one predicate bit associated with it, only the lowest of those bits is ever true.

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

## svwhilegt_b32[_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwhilegt_b32%5B_u32%5D

### Signature (source notation)

```c
svbool_t svwhilegt_b32[_u32](uint32_t op1, uint32_t op2);
```

### Description

While decrementing scalar is greater than

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Initialization / While counter meets condition (backward)

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
    "Presult.S": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
WHILEHI Presult.S, Wop1, Wop2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/WHILEHI--predicate-pair---While-decrementing-unsigned-scalar-higher-than-scalar--pair-of-predicates--

### Operation

Source operation ID: `SveOperation_svwhilegt_b8_u32`

**Operation**



Return a predicate of *n* elements in which element *n* - *i* - 1 is active if, for all values *j* in the range [0, *i*], subtracting *j* from `op1` gives a value that is greater than `op2`.  The sequence will therefore yield at least one false predicate element before the subtraction wraps.



The first type suffix indicates the number of bits in each predicate element.  For example, a suffix of `_b8` indicates that the predicate controls 8-bit data, so element *i* corresponds to bit *i* of the predicate.  A suffix of `_b16` indicates that the predicate controls 16-bit data, so element *i* corresponds to bit *i*×2 of the predicate.  When an element has more than one predicate bit associated with it, only the lowest of those bits is ever true.



`svwhilegt` handles both signed and unsigned inputs; there are no separate functions for WHILEHI.

## svwhilegt_b32[_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwhilegt_b32%5B_u64%5D

### Signature (source notation)

```c
svbool_t svwhilegt_b32[_u64](uint64_t op1, uint64_t op2);
```

### Description

While decrementing scalar is greater than

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Initialization / While counter meets condition (backward)

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
    "Presult.S": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
WHILEHI Presult.S, Xop1, Xop2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/WHILEHI--predicate-pair---While-decrementing-unsigned-scalar-higher-than-scalar--pair-of-predicates--

### Operation

Source operation ID: `SveOperation_svwhilegt_b8_u32`

**Operation**



Return a predicate of *n* elements in which element *n* - *i* - 1 is active if, for all values *j* in the range [0, *i*], subtracting *j* from `op1` gives a value that is greater than `op2`.  The sequence will therefore yield at least one false predicate element before the subtraction wraps.



The first type suffix indicates the number of bits in each predicate element.  For example, a suffix of `_b8` indicates that the predicate controls 8-bit data, so element *i* corresponds to bit *i* of the predicate.  A suffix of `_b16` indicates that the predicate controls 16-bit data, so element *i* corresponds to bit *i*×2 of the predicate.  When an element has more than one predicate bit associated with it, only the lowest of those bits is ever true.



`svwhilegt` handles both signed and unsigned inputs; there are no separate functions for WHILEHI.

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

## svwhilegt_b64[_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwhilegt_b64%5B_s32%5D

### Signature (source notation)

```c
svbool_t svwhilegt_b64[_s32](int32_t op1, int32_t op2);
```

### Description

While decrementing scalar is greater than

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Initialization / While counter meets condition (backward)

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
    "Presult.D": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
WHILEGT Presult.D, Wop1, Wop2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/WHILEGT--predicate-pair---While-decrementing-signed-scalar-greater-than-scalar--pair-of-predicates--

### Operation

Source operation ID: `SveOperation_svwhilegt_b8_s32`

**Operation**



Return a predicate of *n* elements in which element *n* - *i* - 1 is active if, for all values *j* in the range [0, *i*], subtracting *j* from `op1` gives a value that is greater than `op2`.  The sequence will therefore yield at least one false predicate element before the subtraction wraps.



The first type suffix indicates the number of bits in each predicate element.  For example, a suffix of `_b8` indicates that the predicate controls 8-bit data, so element *i* corresponds to bit *i* of the predicate.  A suffix of `_b16` indicates that the predicate controls 16-bit data, so element *i* corresponds to bit *i*×2 of the predicate.  When an element has more than one predicate bit associated with it, only the lowest of those bits is ever true.

## svwhilegt_b64[_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwhilegt_b64%5B_s64%5D

### Signature (source notation)

```c
svbool_t svwhilegt_b64[_s64](int64_t op1, int64_t op2);
```

### Description

While decrementing scalar is greater than

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Initialization / While counter meets condition (backward)

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
    "Presult.D": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
WHILEGT Presult.D, Xop1, Xop2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/WHILEGT--predicate-pair---While-decrementing-signed-scalar-greater-than-scalar--pair-of-predicates--

### Operation

Source operation ID: `SveOperation_svwhilegt_b8_s32`

**Operation**



Return a predicate of *n* elements in which element *n* - *i* - 1 is active if, for all values *j* in the range [0, *i*], subtracting *j* from `op1` gives a value that is greater than `op2`.  The sequence will therefore yield at least one false predicate element before the subtraction wraps.



The first type suffix indicates the number of bits in each predicate element.  For example, a suffix of `_b8` indicates that the predicate controls 8-bit data, so element *i* corresponds to bit *i* of the predicate.  A suffix of `_b16` indicates that the predicate controls 16-bit data, so element *i* corresponds to bit *i*×2 of the predicate.  When an element has more than one predicate bit associated with it, only the lowest of those bits is ever true.

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

## svwhilegt_b64[_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwhilegt_b64%5B_u32%5D

### Signature (source notation)

```c
svbool_t svwhilegt_b64[_u32](uint32_t op1, uint32_t op2);
```

### Description

While decrementing scalar is greater than

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Initialization / While counter meets condition (backward)

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
    "Presult.D": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
WHILEHI Presult.D, Wop1, Wop2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/WHILEHI--predicate-pair---While-decrementing-unsigned-scalar-higher-than-scalar--pair-of-predicates--

### Operation

Source operation ID: `SveOperation_svwhilegt_b8_u32`

**Operation**



Return a predicate of *n* elements in which element *n* - *i* - 1 is active if, for all values *j* in the range [0, *i*], subtracting *j* from `op1` gives a value that is greater than `op2`.  The sequence will therefore yield at least one false predicate element before the subtraction wraps.



The first type suffix indicates the number of bits in each predicate element.  For example, a suffix of `_b8` indicates that the predicate controls 8-bit data, so element *i* corresponds to bit *i* of the predicate.  A suffix of `_b16` indicates that the predicate controls 16-bit data, so element *i* corresponds to bit *i*×2 of the predicate.  When an element has more than one predicate bit associated with it, only the lowest of those bits is ever true.



`svwhilegt` handles both signed and unsigned inputs; there are no separate functions for WHILEHI.

## svwhilegt_b64[_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwhilegt_b64%5B_u64%5D

### Signature (source notation)

```c
svbool_t svwhilegt_b64[_u64](uint64_t op1, uint64_t op2);
```

### Description

While decrementing scalar is greater than

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Initialization / While counter meets condition (backward)

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
    "Presult.D": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
WHILEHI Presult.D, Xop1, Xop2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/WHILEHI--predicate-pair---While-decrementing-unsigned-scalar-higher-than-scalar--pair-of-predicates--

### Operation

Source operation ID: `SveOperation_svwhilegt_b8_u32`

**Operation**



Return a predicate of *n* elements in which element *n* - *i* - 1 is active if, for all values *j* in the range [0, *i*], subtracting *j* from `op1` gives a value that is greater than `op2`.  The sequence will therefore yield at least one false predicate element before the subtraction wraps.



The first type suffix indicates the number of bits in each predicate element.  For example, a suffix of `_b8` indicates that the predicate controls 8-bit data, so element *i* corresponds to bit *i* of the predicate.  A suffix of `_b16` indicates that the predicate controls 16-bit data, so element *i* corresponds to bit *i*×2 of the predicate.  When an element has more than one predicate bit associated with it, only the lowest of those bits is ever true.



`svwhilegt` handles both signed and unsigned inputs; there are no separate functions for WHILEHI.

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

