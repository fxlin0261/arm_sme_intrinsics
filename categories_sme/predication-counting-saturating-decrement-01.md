# SME / Predication / Counting / Saturating decrement — Part 1

## svqdecp[_n_s32]_b16

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdecp%5B_n_s32%5D_b16

### Signature (source notation)

```c
int32_t svqdecp[_n_s32]_b16(int32_t op, svbool_t pg);
```

### Description

Saturating decrement by active element count

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Predication / Counting / Saturating decrement

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
  "value": "int32_t"
}
```

### Argument preparation and constraints

```json
{
  "op": {
    "register": "Wtied"
  },
  "pg": {
    "register": "Pg.H"
  }
}
```

### Result mapping

```json
[
  {
    "Wtied": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
SQDECP Xtied, Pg.H, Wtied
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDECP--scalar---Signed-saturating-decrement-scalar-by-count-of-true-predicate-elements-

### Operation

Source operation ID: `SveOperation_svqdecp_n_s32_b16`

**Operation**



Return the result of the following procedure:




- Count the number of 16-bit elements that are active in `pg`.
- Subtract this value from `op`, without loss of precision.
- Saturate the result to the range of `int32_t`.

## svqdecp[_n_s32]_b32

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdecp%5B_n_s32%5D_b32

### Signature (source notation)

```c
int32_t svqdecp[_n_s32]_b32(int32_t op, svbool_t pg);
```

### Description

Saturating decrement by active element count

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Predication / Counting / Saturating decrement

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
  "value": "int32_t"
}
```

### Argument preparation and constraints

```json
{
  "op": {
    "register": "Wtied"
  },
  "pg": {
    "register": "Pg.S"
  }
}
```

### Result mapping

```json
[
  {
    "Wtied": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
SQDECP Xtied, Pg.S, Wtied
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDECP--scalar---Signed-saturating-decrement-scalar-by-count-of-true-predicate-elements-

### Operation

Source operation ID: `SveOperation_svqdecp_n_s32_b32`

**Operation**



Return the result of the following procedure:




- Count the number of 32-bit elements that are active in `pg`.
- Subtract this value from `op`, without loss of precision.
- Saturate the result to the range of `int32_t`.

## svqdecp[_n_s32]_b64

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdecp%5B_n_s32%5D_b64

### Signature (source notation)

```c
int32_t svqdecp[_n_s32]_b64(int32_t op, svbool_t pg);
```

### Description

Saturating decrement by active element count

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Predication / Counting / Saturating decrement

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
  "value": "int32_t"
}
```

### Argument preparation and constraints

```json
{
  "op": {
    "register": "Wtied"
  },
  "pg": {
    "register": "Pg.D"
  }
}
```

### Result mapping

```json
[
  {
    "Wtied": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
SQDECP Xtied, Pg.D, Wtied
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDECP--scalar---Signed-saturating-decrement-scalar-by-count-of-true-predicate-elements-

### Operation

Source operation ID: `SveOperation_svqdecp_n_s32_b64`

**Operation**



Return the result of the following procedure:




- Count the number of 64-bit elements that are active in `pg`.
- Subtract this value from `op`, without loss of precision.
- Saturate the result to the range of `int32_t`.

## svqdecp[_n_s32]_b8

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdecp%5B_n_s32%5D_b8

### Signature (source notation)

```c
int32_t svqdecp[_n_s32]_b8(int32_t op, svbool_t pg);
```

### Description

Saturating decrement by active element count

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Predication / Counting / Saturating decrement

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
  "value": "int32_t"
}
```

### Argument preparation and constraints

```json
{
  "op": {
    "register": "Wtied"
  },
  "pg": {
    "register": "Pg.B"
  }
}
```

### Result mapping

```json
[
  {
    "Wtied": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
SQDECP Xtied, Pg.B, Wtied
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDECP--scalar---Signed-saturating-decrement-scalar-by-count-of-true-predicate-elements-

### Operation

Source operation ID: `SveOperation_svqdecp_n_s32_b8`

**Operation**



Return the result of the following procedure:




- Count the number of 8-bit elements that are active in `pg`.
- Subtract this value from `op`, without loss of precision.
- Saturate the result to the range of `int32_t`.

## svqdecp[_n_s64]_b16

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdecp%5B_n_s64%5D_b16

### Signature (source notation)

```c
int64_t svqdecp[_n_s64]_b16(int64_t op, svbool_t pg);
```

### Description

Saturating decrement by active element count

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Predication / Counting / Saturating decrement

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
  "value": "int64_t"
}
```

### Argument preparation and constraints

```json
{
  "op": {
    "register": "Xtied"
  },
  "pg": {
    "register": "Pg.H"
  }
}
```

### Result mapping

```json
[
  {
    "Xtied": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
SQDECP Xtied, Pg.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDECP--scalar---Signed-saturating-decrement-scalar-by-count-of-true-predicate-elements-

### Operation

Source operation ID: `SveOperation_svqdecp_n_s64_b16`

**Operation**



Return the result of the following procedure:




- Count the number of 16-bit elements that are active in `pg`.
- Subtract this value from `op`, without loss of precision.
- Saturate the result to the range of `int64_t`.

## svqdecp[_n_s64]_b32

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdecp%5B_n_s64%5D_b32

### Signature (source notation)

```c
int64_t svqdecp[_n_s64]_b32(int64_t op, svbool_t pg);
```

### Description

Saturating decrement by active element count

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Predication / Counting / Saturating decrement

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
  "value": "int64_t"
}
```

### Argument preparation and constraints

```json
{
  "op": {
    "register": "Xtied"
  },
  "pg": {
    "register": "Pg.S"
  }
}
```

### Result mapping

```json
[
  {
    "Xtied": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
SQDECP Xtied, Pg.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDECP--scalar---Signed-saturating-decrement-scalar-by-count-of-true-predicate-elements-

### Operation

Source operation ID: `SveOperation_svqdecp_n_s64_b32`

**Operation**



Return the result of the following procedure:




- Count the number of 32-bit elements that are active in `pg`.
- Subtract this value from `op`, without loss of precision.
- Saturate the result to the range of `int64_t`.

## svqdecp[_n_s64]_b64

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdecp%5B_n_s64%5D_b64

### Signature (source notation)

```c
int64_t svqdecp[_n_s64]_b64(int64_t op, svbool_t pg);
```

### Description

Saturating decrement by active element count

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Predication / Counting / Saturating decrement

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
  "value": "int64_t"
}
```

### Argument preparation and constraints

```json
{
  "op": {
    "register": "Xtied"
  },
  "pg": {
    "register": "Pg.D"
  }
}
```

### Result mapping

```json
[
  {
    "Xtied": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
SQDECP Xtied, Pg.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDECP--scalar---Signed-saturating-decrement-scalar-by-count-of-true-predicate-elements-

### Operation

Source operation ID: `SveOperation_svqdecp_n_s64_b64`

**Operation**



Return the result of the following procedure:




- Count the number of 64-bit elements that are active in `pg`.
- Subtract this value from `op`, without loss of precision.
- Saturate the result to the range of `int64_t`.

## svqdecp[_n_s64]_b8

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdecp%5B_n_s64%5D_b8

### Signature (source notation)

```c
int64_t svqdecp[_n_s64]_b8(int64_t op, svbool_t pg);
```

### Description

Saturating decrement by active element count

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Predication / Counting / Saturating decrement

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
  "value": "int64_t"
}
```

### Argument preparation and constraints

```json
{
  "op": {
    "register": "Xtied"
  },
  "pg": {
    "register": "Pg.B"
  }
}
```

### Result mapping

```json
[
  {
    "Xtied": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
SQDECP Xtied, Pg.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDECP--scalar---Signed-saturating-decrement-scalar-by-count-of-true-predicate-elements-

### Operation

Source operation ID: `SveOperation_svqdecp_n_s64_b8`

**Operation**



Return the result of the following procedure:




- Count the number of 8-bit elements that are active in `pg`.
- Subtract this value from `op`, without loss of precision.
- Saturate the result to the range of `int64_t`.

## svqdecp[_n_u32]_b16

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdecp%5B_n_u32%5D_b16

### Signature (source notation)

```c
uint32_t svqdecp[_n_u32]_b16(uint32_t op, svbool_t pg);
```

### Description

Saturating decrement by active element count

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Predication / Counting / Saturating decrement

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
  "value": "uint32_t"
}
```

### Argument preparation and constraints

```json
{
  "op": {
    "register": "Wtied"
  },
  "pg": {
    "register": "Pg.H"
  }
}
```

### Result mapping

```json
[
  {
    "Wtied": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
UQDECP Wtied, Pg.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQDECP--scalar---Unsigned-saturating-decrement-scalar-by-count-of-true-predicate-elements-

### Operation

Source operation ID: `SveOperation_svqdecp_n_u32_b16`

**Operation**



Return the result of the following procedure:




- Count the number of 16-bit elements that are active in `pg`.
- Subtract this value from `op`, without loss of precision.
- Saturate the result to the range of `uint32_t`.

## svqdecp[_n_u32]_b32

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdecp%5B_n_u32%5D_b32

### Signature (source notation)

```c
uint32_t svqdecp[_n_u32]_b32(uint32_t op, svbool_t pg);
```

### Description

Saturating decrement by active element count

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Predication / Counting / Saturating decrement

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
  "value": "uint32_t"
}
```

### Argument preparation and constraints

```json
{
  "op": {
    "register": "Wtied"
  },
  "pg": {
    "register": "Pg.S"
  }
}
```

### Result mapping

```json
[
  {
    "Wtied": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
UQDECP Wtied, Pg.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQDECP--scalar---Unsigned-saturating-decrement-scalar-by-count-of-true-predicate-elements-

### Operation

Source operation ID: `SveOperation_svqdecp_n_u32_b32`

**Operation**



Return the result of the following procedure:




- Count the number of 32-bit elements that are active in `pg`.
- Subtract this value from `op`, without loss of precision.
- Saturate the result to the range of `uint32_t`.

## svqdecp[_n_u32]_b64

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdecp%5B_n_u32%5D_b64

### Signature (source notation)

```c
uint32_t svqdecp[_n_u32]_b64(uint32_t op, svbool_t pg);
```

### Description

Saturating decrement by active element count

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Predication / Counting / Saturating decrement

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
  "value": "uint32_t"
}
```

### Argument preparation and constraints

```json
{
  "op": {
    "register": "Wtied"
  },
  "pg": {
    "register": "Pg.D"
  }
}
```

### Result mapping

```json
[
  {
    "Wtied": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
UQDECP Wtied, Pg.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQDECP--scalar---Unsigned-saturating-decrement-scalar-by-count-of-true-predicate-elements-

### Operation

Source operation ID: `SveOperation_svqdecp_n_u32_b64`

**Operation**



Return the result of the following procedure:




- Count the number of 64-bit elements that are active in `pg`.
- Subtract this value from `op`, without loss of precision.
- Saturate the result to the range of `uint32_t`.

## svqdecp[_n_u32]_b8

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdecp%5B_n_u32%5D_b8

### Signature (source notation)

```c
uint32_t svqdecp[_n_u32]_b8(uint32_t op, svbool_t pg);
```

### Description

Saturating decrement by active element count

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Predication / Counting / Saturating decrement

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
  "value": "uint32_t"
}
```

### Argument preparation and constraints

```json
{
  "op": {
    "register": "Wtied"
  },
  "pg": {
    "register": "Pg.B"
  }
}
```

### Result mapping

```json
[
  {
    "Wtied": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
UQDECP Wtied, Pg.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQDECP--scalar---Unsigned-saturating-decrement-scalar-by-count-of-true-predicate-elements-

### Operation

Source operation ID: `SveOperation_svqdecp_n_u32_b8`

**Operation**



Return the result of the following procedure:




- Count the number of 8-bit elements that are active in `pg`.
- Subtract this value from `op`, without loss of precision.
- Saturate the result to the range of `uint32_t`.

## svqdecp[_n_u64]_b16

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdecp%5B_n_u64%5D_b16

### Signature (source notation)

```c
uint64_t svqdecp[_n_u64]_b16(uint64_t op, svbool_t pg);
```

### Description

Saturating decrement by active element count

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Predication / Counting / Saturating decrement

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
  "op": {
    "register": "Xtied"
  },
  "pg": {
    "register": "Pg.H"
  }
}
```

### Result mapping

```json
[
  {
    "Xtied": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
UQDECP Xtied, Pg.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQDECP--scalar---Unsigned-saturating-decrement-scalar-by-count-of-true-predicate-elements-

### Operation

Source operation ID: `SveOperation_svqdecp_n_u64_b16`

**Operation**



Return the result of the following procedure:




- Count the number of 16-bit elements that are active in `pg`.
- Subtract this value from `op`, without loss of precision.
- Saturate the result to the range of `uint64_t`.

## svqdecp[_n_u64]_b32

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdecp%5B_n_u64%5D_b32

### Signature (source notation)

```c
uint64_t svqdecp[_n_u64]_b32(uint64_t op, svbool_t pg);
```

### Description

Saturating decrement by active element count

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Predication / Counting / Saturating decrement

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
  "op": {
    "register": "Xtied"
  },
  "pg": {
    "register": "Pg.S"
  }
}
```

### Result mapping

```json
[
  {
    "Xtied": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
UQDECP Xtied, Pg.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQDECP--scalar---Unsigned-saturating-decrement-scalar-by-count-of-true-predicate-elements-

### Operation

Source operation ID: `SveOperation_svqdecp_n_u64_b32`

**Operation**



Return the result of the following procedure:




- Count the number of 32-bit elements that are active in `pg`.
- Subtract this value from `op`, without loss of precision.
- Saturate the result to the range of `uint64_t`.

## svqdecp[_n_u64]_b64

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdecp%5B_n_u64%5D_b64

### Signature (source notation)

```c
uint64_t svqdecp[_n_u64]_b64(uint64_t op, svbool_t pg);
```

### Description

Saturating decrement by active element count

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Predication / Counting / Saturating decrement

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
  "op": {
    "register": "Xtied"
  },
  "pg": {
    "register": "Pg.D"
  }
}
```

### Result mapping

```json
[
  {
    "Xtied": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
UQDECP Xtied, Pg.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQDECP--scalar---Unsigned-saturating-decrement-scalar-by-count-of-true-predicate-elements-

### Operation

Source operation ID: `SveOperation_svqdecp_n_u64_b64`

**Operation**



Return the result of the following procedure:




- Count the number of 64-bit elements that are active in `pg`.
- Subtract this value from `op`, without loss of precision.
- Saturate the result to the range of `uint64_t`.

## svqdecp[_n_u64]_b8

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdecp%5B_n_u64%5D_b8

### Signature (source notation)

```c
uint64_t svqdecp[_n_u64]_b8(uint64_t op, svbool_t pg);
```

### Description

Saturating decrement by active element count

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Predication / Counting / Saturating decrement

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
  "op": {
    "register": "Xtied"
  },
  "pg": {
    "register": "Pg.B"
  }
}
```

### Result mapping

```json
[
  {
    "Xtied": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
UQDECP Xtied, Pg.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQDECP--scalar---Unsigned-saturating-decrement-scalar-by-count-of-true-predicate-elements-

### Operation

Source operation ID: `SveOperation_svqdecp_n_u64_b8`

**Operation**



Return the result of the following procedure:




- Count the number of 8-bit elements that are active in `pg`.
- Subtract this value from `op`, without loss of precision.
- Saturate the result to the range of `uint64_t`.

## svqdecp[_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdecp%5B_s16%5D

### Signature (source notation)

```c
svint16_t svqdecp[_s16](svint16_t op, svbool_t pg);
```

### Description

Saturating decrement by active element count

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Predication / Counting / Saturating decrement

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
  "element_bit_size": "16",
  "value": "svint16_t"
}
```

### Argument preparation and constraints

```json
{
  "op": {
    "register": "Zop.H|Ztied.H"
  },
  "pg": {
    "register": "Pg"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.H|Ztied.H": "result"
  }
]
```

### Instruction mapping

When result and op are in the same register, this intrinsic compiles to:

```asm
SQDECP Ztied.H, Pg
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDECP--vector---Signed-saturating-decrement-vector-by-count-of-true-predicate-elements-

When result and op are in different registers, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SQDECP Zresult.H, Pg
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDECP--vector---Signed-saturating-decrement-vector-by-count-of-true-predicate-elements-

### Operation

Source operation ID: `SveOperation_svqdecp_s16`

**Operation**



Return a vector in which each element *i* (whether active or not) contains the result of the following procedure:




- Count the number of active elements, as determined by `pg`.
- Subtract this value from `op[i]`, without loss of precision.
- Saturate the result to the range of `int16_t`.

## svqdecp[_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdecp%5B_s32%5D

### Signature (source notation)

```c
svint32_t svqdecp[_s32](svint32_t op, svbool_t pg);
```

### Description

Saturating decrement by active element count

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Predication / Counting / Saturating decrement

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
  "value": "svint32_t"
}
```

### Argument preparation and constraints

```json
{
  "op": {
    "register": "Zop.S|Ztied.S"
  },
  "pg": {
    "register": "Pg"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.S|Ztied.S": "result"
  }
]
```

### Instruction mapping

When result and op are in the same register, this intrinsic compiles to:

```asm
SQDECP Ztied.S, Pg
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDECP--vector---Signed-saturating-decrement-vector-by-count-of-true-predicate-elements-

When result and op are in different registers, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SQDECP Zresult.S, Pg
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDECP--vector---Signed-saturating-decrement-vector-by-count-of-true-predicate-elements-

### Operation

Source operation ID: `SveOperation_svqdecp_s32`

**Operation**



Return a vector in which each element *i* (whether active or not) contains the result of the following procedure:




- Count the number of active elements, as determined by `pg`.
- Subtract this value from `op[i]`, without loss of precision.
- Saturate the result to the range of `int32_t`.

## svqdecp[_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdecp%5B_s64%5D

### Signature (source notation)

```c
svint64_t svqdecp[_s64](svint64_t op, svbool_t pg);
```

### Description

Saturating decrement by active element count

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Predication / Counting / Saturating decrement

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
  "value": "svint64_t"
}
```

### Argument preparation and constraints

```json
{
  "op": {
    "register": "Zop.D|Ztied.D"
  },
  "pg": {
    "register": "Pg"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.D|Ztied.D": "result"
  }
]
```

### Instruction mapping

When result and op are in the same register, this intrinsic compiles to:

```asm
SQDECP Ztied.D, Pg
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDECP--vector---Signed-saturating-decrement-vector-by-count-of-true-predicate-elements-

When result and op are in different registers, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SQDECP Zresult.D, Pg
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDECP--vector---Signed-saturating-decrement-vector-by-count-of-true-predicate-elements-

### Operation

Source operation ID: `SveOperation_svqdecp_s64`

**Operation**



Return a vector in which each element *i* (whether active or not) contains the result of the following procedure:




- Count the number of active elements, as determined by `pg`.
- Subtract this value from `op[i]`, without loss of precision.
- Saturate the result to the range of `int64_t`.

## svqdecp[_u16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdecp%5B_u16%5D

### Signature (source notation)

```c
svuint16_t svqdecp[_u16](svuint16_t op, svbool_t pg);
```

### Description

Saturating decrement by active element count

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Predication / Counting / Saturating decrement

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
  "element_bit_size": "16",
  "value": "svuint16_t"
}
```

### Argument preparation and constraints

```json
{
  "op": {
    "register": "Zop.H|Ztied.H"
  },
  "pg": {
    "register": "Pg"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.H|Ztied.H": "result"
  }
]
```

### Instruction mapping

When result and op are in the same register, this intrinsic compiles to:

```asm
UQDECP Ztied.H, Pg
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQDECP--vector---Unsigned-saturating-decrement-vector-by-count-of-true-predicate-elements-

When result and op are in different registers, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
UQDECP Zresult.H, Pg
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQDECP--vector---Unsigned-saturating-decrement-vector-by-count-of-true-predicate-elements-

### Operation

Source operation ID: `SveOperation_svqdecp_u16`

**Operation**



Return a vector in which each element *i* (whether active or not) contains the result of the following procedure:




- Count the number of active elements, as determined by `pg`.
- Subtract this value from `op[i]`, without loss of precision.
- Saturate the result to the range of `uint16_t`.

## svqdecp[_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdecp%5B_u32%5D

### Signature (source notation)

```c
svuint32_t svqdecp[_u32](svuint32_t op, svbool_t pg);
```

### Description

Saturating decrement by active element count

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Predication / Counting / Saturating decrement

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
  "value": "svuint32_t"
}
```

### Argument preparation and constraints

```json
{
  "op": {
    "register": "Zop.S|Ztied.S"
  },
  "pg": {
    "register": "Pg"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.S|Ztied.S": "result"
  }
]
```

### Instruction mapping

When result and op are in the same register, this intrinsic compiles to:

```asm
UQDECP Ztied.S, Pg
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQDECP--vector---Unsigned-saturating-decrement-vector-by-count-of-true-predicate-elements-

When result and op are in different registers, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
UQDECP Zresult.S, Pg
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQDECP--vector---Unsigned-saturating-decrement-vector-by-count-of-true-predicate-elements-

### Operation

Source operation ID: `SveOperation_svqdecp_u32`

**Operation**



Return a vector in which each element *i* (whether active or not) contains the result of the following procedure:




- Count the number of active elements, as determined by `pg`.
- Subtract this value from `op[i]`, without loss of precision.
- Saturate the result to the range of `uint32_t`.

## svqdecp[_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdecp%5B_u64%5D

### Signature (source notation)

```c
svuint64_t svqdecp[_u64](svuint64_t op, svbool_t pg);
```

### Description

Saturating decrement by active element count

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Predication / Counting / Saturating decrement

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
  "value": "svuint64_t"
}
```

### Argument preparation and constraints

```json
{
  "op": {
    "register": "Zop.D|Ztied.D"
  },
  "pg": {
    "register": "Pg"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.D|Ztied.D": "result"
  }
]
```

### Instruction mapping

When result and op are in the same register, this intrinsic compiles to:

```asm
UQDECP Ztied.D, Pg
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQDECP--vector---Unsigned-saturating-decrement-vector-by-count-of-true-predicate-elements-

When result and op are in different registers, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
UQDECP Zresult.D, Pg
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQDECP--vector---Unsigned-saturating-decrement-vector-by-count-of-true-predicate-elements-

### Operation

Source operation ID: `SveOperation_svqdecp_u64`

**Operation**



Return a vector in which each element *i* (whether active or not) contains the result of the following procedure:




- Count the number of active elements, as determined by `pg`.
- Subtract this value from `op[i]`, without loss of precision.
- Saturate the result to the range of `uint64_t`.

