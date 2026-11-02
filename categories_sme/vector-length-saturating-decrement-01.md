# SME / Vector length / Saturating decrement — Part 1

## svqdecb[_n_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdecb%5B_n_s32%5D

### Signature (source notation)

```c
int32_t svqdecb[_n_s32](int32_t op, uint64_t imm_factor);
```

### Description

Saturating decrement by number of byte elements

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector length / Saturating decrement

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
  "imm_factor": {
    "minimum": 1,
    "maximum": 16
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
SQDECB Xtied, Wtied, ALL, MUL #imm_factor
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDECB--Signed-saturating-decrement-scalar-by-multiple-of-8-bit-predicate-constraint-element-count-

### Operation

Source operation ID: `SveOperation_svqdecb_n_s32`

**Operation**



Return the result of the following procedure:




- Multiply the number of 8-bit elements in a full vector by `imm_factor`.
- Subtract this value from `op`, without loss of precision.
- Saturate the result to the range of `int32_t`.

## svqdecb[_n_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdecb%5B_n_s64%5D

### Signature (source notation)

```c
int64_t svqdecb[_n_s64](int64_t op, uint64_t imm_factor);
```

### Description

Saturating decrement by number of byte elements

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector length / Saturating decrement

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
  "imm_factor": {
    "minimum": 1,
    "maximum": 16
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
SQDECB Xtied, ALL, MUL #imm_factor
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDECB--Signed-saturating-decrement-scalar-by-multiple-of-8-bit-predicate-constraint-element-count-

### Operation

Source operation ID: `SveOperation_svqdecb_n_s64`

**Operation**



Return the result of the following procedure:




- Multiply the number of 8-bit elements in a full vector by `imm_factor`.
- Subtract this value from `op`, without loss of precision.
- Saturate the result to the range of `int64_t`.

## svqdecb[_n_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdecb%5B_n_u32%5D

### Signature (source notation)

```c
uint32_t svqdecb[_n_u32](uint32_t op, uint64_t imm_factor);
```

### Description

Saturating decrement by number of byte elements

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector length / Saturating decrement

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
  "imm_factor": {
    "minimum": 1,
    "maximum": 16
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
UQDECB Wtied, ALL, MUL #imm_factor
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQDECB--Unsigned-saturating-decrement-scalar-by-multiple-of-8-bit-predicate-constraint-element-count-

### Operation

Source operation ID: `SveOperation_svqdecb_n_u32`

**Operation**



Return the result of the following procedure:




- Multiply the number of 8-bit elements in a full vector by `imm_factor`.
- Subtract this value from `op`, without loss of precision.
- Saturate the result to the range of `uint32_t`.

## svqdecb[_n_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdecb%5B_n_u64%5D

### Signature (source notation)

```c
uint64_t svqdecb[_n_u64](uint64_t op, uint64_t imm_factor);
```

### Description

Saturating decrement by number of byte elements

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector length / Saturating decrement

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
  "imm_factor": {
    "minimum": 1,
    "maximum": 16
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
UQDECB Xtied, ALL, MUL #imm_factor
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQDECB--Unsigned-saturating-decrement-scalar-by-multiple-of-8-bit-predicate-constraint-element-count-

### Operation

Source operation ID: `SveOperation_svqdecb_n_u64`

**Operation**



Return the result of the following procedure:




- Multiply the number of 8-bit elements in a full vector by `imm_factor`.
- Subtract this value from `op`, without loss of precision.
- Saturate the result to the range of `uint64_t`.

## svqdecb_pat[_n_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdecb_pat%5B_n_s32%5D

### Signature (source notation)

```c
int32_t svqdecb_pat[_n_s32](int32_t op, enum svpattern pattern, uint64_t imm_factor);
```

### Description

Saturating decrement by number of byte elements

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector length / Saturating decrement

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
  "imm_factor": {
    "minimum": 1,
    "maximum": 16
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
SQDECB Xtied, Wtied, pattern, MUL #imm_factor
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDECB--Signed-saturating-decrement-scalar-by-multiple-of-8-bit-predicate-constraint-element-count-

### Operation

Source operation ID: `SveOperation_svqdecb_pat_n_s32`

**Operation**



Return the result of the following procedure:




- Multiply the number of 8-bit elements in vector pattern `pattern` by `imm_factor`.
- Subtract this value from `op`, without loss of precision.
- Saturate the result to the range of `int32_t`.

## svqdecb_pat[_n_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdecb_pat%5B_n_s64%5D

### Signature (source notation)

```c
int64_t svqdecb_pat[_n_s64](int64_t op, enum svpattern pattern, uint64_t imm_factor);
```

### Description

Saturating decrement by number of byte elements

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector length / Saturating decrement

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
  "imm_factor": {
    "minimum": 1,
    "maximum": 16
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
SQDECB Xtied, pattern, MUL #imm_factor
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDECB--Signed-saturating-decrement-scalar-by-multiple-of-8-bit-predicate-constraint-element-count-

### Operation

Source operation ID: `SveOperation_svqdecb_pat_n_s64`

**Operation**



Return the result of the following procedure:




- Multiply the number of 8-bit elements in vector pattern `pattern` by `imm_factor`.
- Subtract this value from `op`, without loss of precision.
- Saturate the result to the range of `int64_t`.

## svqdecb_pat[_n_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdecb_pat%5B_n_u32%5D

### Signature (source notation)

```c
uint32_t svqdecb_pat[_n_u32](uint32_t op, enum svpattern pattern, uint64_t imm_factor);
```

### Description

Saturating decrement by number of byte elements

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector length / Saturating decrement

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
  "imm_factor": {
    "minimum": 1,
    "maximum": 16
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
UQDECB Wtied, pattern, MUL #imm_factor
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQDECB--Unsigned-saturating-decrement-scalar-by-multiple-of-8-bit-predicate-constraint-element-count-

### Operation

Source operation ID: `SveOperation_svqdecb_pat_n_u32`

**Operation**



Return the result of the following procedure:




- Multiply the number of 8-bit elements in vector pattern `pattern` by `imm_factor`.
- Subtract this value from `op`, without loss of precision.
- Saturate the result to the range of `uint32_t`.

## svqdecb_pat[_n_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdecb_pat%5B_n_u64%5D

### Signature (source notation)

```c
uint64_t svqdecb_pat[_n_u64](uint64_t op, enum svpattern pattern, uint64_t imm_factor);
```

### Description

Saturating decrement by number of byte elements

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector length / Saturating decrement

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
  "imm_factor": {
    "minimum": 1,
    "maximum": 16
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
UQDECB Xtied, pattern, MUL #imm_factor
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQDECB--Unsigned-saturating-decrement-scalar-by-multiple-of-8-bit-predicate-constraint-element-count-

### Operation

Source operation ID: `SveOperation_svqdecb_pat_n_u64`

**Operation**



Return the result of the following procedure:




- Multiply the number of 8-bit elements in vector pattern `pattern` by `imm_factor`.
- Subtract this value from `op`, without loss of precision.
- Saturate the result to the range of `uint64_t`.

## svqdecd[_n_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdecd%5B_n_s32%5D

### Signature (source notation)

```c
int32_t svqdecd[_n_s32](int32_t op, uint64_t imm_factor);
```

### Description

Saturating decrement by number of doubleword elements

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector length / Saturating decrement

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
  "imm_factor": {
    "minimum": 1,
    "maximum": 16
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
SQDECD Xtied, Wtied, ALL, MUL #imm_factor
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDECD--scalar---Signed-saturating-decrement-scalar-by-multiple-of-64-bit-predicate-constraint-element-count-

### Operation

Source operation ID: `SveOperation_svqdecd_n_s32`

**Operation**



Return the result of the following procedure:




- Multiply the number of 64-bit elements in a full vector by `imm_factor`.
- Subtract this value from `op`, without loss of precision.
- Saturate the result to the range of `int32_t`.

## svqdecd[_n_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdecd%5B_n_s64%5D

### Signature (source notation)

```c
int64_t svqdecd[_n_s64](int64_t op, uint64_t imm_factor);
```

### Description

Saturating decrement by number of doubleword elements

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector length / Saturating decrement

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
  "imm_factor": {
    "minimum": 1,
    "maximum": 16
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
SQDECD Xtied, ALL, MUL #imm_factor
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDECD--scalar---Signed-saturating-decrement-scalar-by-multiple-of-64-bit-predicate-constraint-element-count-

### Operation

Source operation ID: `SveOperation_svqdecd_n_s64`

**Operation**



Return the result of the following procedure:




- Multiply the number of 64-bit elements in a full vector by `imm_factor`.
- Subtract this value from `op`, without loss of precision.
- Saturate the result to the range of `int64_t`.

## svqdecd[_n_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdecd%5B_n_u32%5D

### Signature (source notation)

```c
uint32_t svqdecd[_n_u32](uint32_t op, uint64_t imm_factor);
```

### Description

Saturating decrement by number of doubleword elements

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector length / Saturating decrement

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
  "imm_factor": {
    "minimum": 1,
    "maximum": 16
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
UQDECD Wtied, ALL, MUL #imm_factor
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQDECD--scalar---Unsigned-saturating-decrement-scalar-by-multiple-of-64-bit-predicate-constraint-element-count-

### Operation

Source operation ID: `SveOperation_svqdecd_n_u32`

**Operation**



Return the result of the following procedure:




- Multiply the number of 64-bit elements in a full vector by `imm_factor`.
- Subtract this value from `op`, without loss of precision.
- Saturate the result to the range of `uint32_t`.

## svqdecd[_n_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdecd%5B_n_u64%5D

### Signature (source notation)

```c
uint64_t svqdecd[_n_u64](uint64_t op, uint64_t imm_factor);
```

### Description

Saturating decrement by number of doubleword elements

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector length / Saturating decrement

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
  "imm_factor": {
    "minimum": 1,
    "maximum": 16
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
UQDECD Xtied, ALL, MUL #imm_factor
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQDECD--scalar---Unsigned-saturating-decrement-scalar-by-multiple-of-64-bit-predicate-constraint-element-count-

### Operation

Source operation ID: `SveOperation_svqdecd_n_u64`

**Operation**



Return the result of the following procedure:




- Multiply the number of 64-bit elements in a full vector by `imm_factor`.
- Subtract this value from `op`, without loss of precision.
- Saturate the result to the range of `uint64_t`.

## svqdecd[_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdecd%5B_s64%5D

### Signature (source notation)

```c
svint64_t svqdecd[_s64](svint64_t op, uint64_t imm_factor);
```

### Description

Saturating decrement by number of doubleword elements

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector length / Saturating decrement

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
  "imm_factor": {
    "minimum": 1,
    "maximum": 16
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
SQDECD Ztied.D, ALL, MUL #imm_factor
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDECD--vector---Signed-saturating-decrement-vector-by-multiple-of-64-bit-predicate-constraint-element-count-

When result and op are in different registers, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SQDECD Zresult.D, ALL, MUL #imm_factor
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDECD--vector---Signed-saturating-decrement-vector-by-multiple-of-64-bit-predicate-constraint-element-count-

### Operation

Source operation ID: `SveOperation_svqdecd_s64`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Multiply the number of 64-bit elements in a full vector by `imm_factor`.
- Subtract this value from `op[i]`, without loss of precision.
- Saturate the result to the range of `int64_t`.

## svqdecd[_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdecd%5B_u64%5D

### Signature (source notation)

```c
svuint64_t svqdecd[_u64](svuint64_t op, uint64_t imm_factor);
```

### Description

Saturating decrement by number of doubleword elements

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector length / Saturating decrement

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
  "imm_factor": {
    "minimum": 1,
    "maximum": 16
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
UQDECD Ztied.D, ALL, MUL #imm_factor
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQDECD--vector---Unsigned-saturating-decrement-vector-by-multiple-of-64-bit-predicate-constraint-element-count-

When result and op are in different registers, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
UQDECD Zresult.D, ALL, MUL #imm_factor
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQDECD--vector---Unsigned-saturating-decrement-vector-by-multiple-of-64-bit-predicate-constraint-element-count-

### Operation

Source operation ID: `SveOperation_svqdecd_u64`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Multiply the number of 64-bit elements in a full vector by `imm_factor`.
- Subtract this value from `op[i]`, without loss of precision.
- Saturate the result to the range of `uint64_t`.

## svqdecd_pat[_n_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdecd_pat%5B_n_s32%5D

### Signature (source notation)

```c
int32_t svqdecd_pat[_n_s32](int32_t op, enum svpattern pattern, uint64_t imm_factor);
```

### Description

Saturating decrement by number of doubleword elements

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector length / Saturating decrement

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
  "imm_factor": {
    "minimum": 1,
    "maximum": 16
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
SQDECD Xtied, Wtied, pattern, MUL #imm_factor
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDECD--scalar---Signed-saturating-decrement-scalar-by-multiple-of-64-bit-predicate-constraint-element-count-

### Operation

Source operation ID: `SveOperation_svqdecd_pat_n_s32`

**Operation**



Return the result of the following procedure:




- Multiply the number of 64-bit elements in vector pattern `pattern` by `imm_factor`.
- Subtract this value from `op`, without loss of precision.
- Saturate the result to the range of `int32_t`.

## svqdecd_pat[_n_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdecd_pat%5B_n_s64%5D

### Signature (source notation)

```c
int64_t svqdecd_pat[_n_s64](int64_t op, enum svpattern pattern, uint64_t imm_factor);
```

### Description

Saturating decrement by number of doubleword elements

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector length / Saturating decrement

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
  "imm_factor": {
    "minimum": 1,
    "maximum": 16
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
SQDECD Xtied, pattern, MUL #imm_factor
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDECD--scalar---Signed-saturating-decrement-scalar-by-multiple-of-64-bit-predicate-constraint-element-count-

### Operation

Source operation ID: `SveOperation_svqdecd_pat_n_s64`

**Operation**



Return the result of the following procedure:




- Multiply the number of 64-bit elements in vector pattern `pattern` by `imm_factor`.
- Subtract this value from `op`, without loss of precision.
- Saturate the result to the range of `int64_t`.

## svqdecd_pat[_n_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdecd_pat%5B_n_u32%5D

### Signature (source notation)

```c
uint32_t svqdecd_pat[_n_u32](uint32_t op, enum svpattern pattern, uint64_t imm_factor);
```

### Description

Saturating decrement by number of doubleword elements

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector length / Saturating decrement

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
  "imm_factor": {
    "minimum": 1,
    "maximum": 16
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
UQDECD Wtied, pattern, MUL #imm_factor
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQDECD--scalar---Unsigned-saturating-decrement-scalar-by-multiple-of-64-bit-predicate-constraint-element-count-

### Operation

Source operation ID: `SveOperation_svqdecd_pat_n_u32`

**Operation**



Return the result of the following procedure:




- Multiply the number of 64-bit elements in vector pattern `pattern` by `imm_factor`.
- Subtract this value from `op`, without loss of precision.
- Saturate the result to the range of `uint32_t`.

## svqdecd_pat[_n_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdecd_pat%5B_n_u64%5D

### Signature (source notation)

```c
uint64_t svqdecd_pat[_n_u64](uint64_t op, enum svpattern pattern, uint64_t imm_factor);
```

### Description

Saturating decrement by number of doubleword elements

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector length / Saturating decrement

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
  "imm_factor": {
    "minimum": 1,
    "maximum": 16
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
UQDECD Xtied, pattern, MUL #imm_factor
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQDECD--scalar---Unsigned-saturating-decrement-scalar-by-multiple-of-64-bit-predicate-constraint-element-count-

### Operation

Source operation ID: `SveOperation_svqdecd_pat_n_u64`

**Operation**



Return the result of the following procedure:




- Multiply the number of 64-bit elements in vector pattern `pattern` by `imm_factor`.
- Subtract this value from `op`, without loss of precision.
- Saturate the result to the range of `uint64_t`.

## svqdecd_pat[_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdecd_pat%5B_s64%5D

### Signature (source notation)

```c
svint64_t svqdecd_pat[_s64](svint64_t op, enum svpattern pattern, uint64_t imm_factor);
```

### Description

Saturating decrement by number of doubleword elements

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector length / Saturating decrement

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
  "imm_factor": {
    "minimum": 1,
    "maximum": 16
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
SQDECD Ztied.D, pattern, MUL #imm_factor
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDECD--vector---Signed-saturating-decrement-vector-by-multiple-of-64-bit-predicate-constraint-element-count-

When result and op are in different registers, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SQDECD Zresult.D, pattern, MUL #imm_factor
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDECD--vector---Signed-saturating-decrement-vector-by-multiple-of-64-bit-predicate-constraint-element-count-

### Operation

Source operation ID: `SveOperation_svqdecd_pat_s64`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Multiply the number of 64-bit elements in vector pattern `pattern` by `imm_factor`.
- Subtract this value from `op[i]`, without loss of precision.
- Saturate the result to the range of `int64_t`.

## svqdecd_pat[_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdecd_pat%5B_u64%5D

### Signature (source notation)

```c
svuint64_t svqdecd_pat[_u64](svuint64_t op, enum svpattern pattern, uint64_t imm_factor);
```

### Description

Saturating decrement by number of doubleword elements

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector length / Saturating decrement

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
  "imm_factor": {
    "minimum": 1,
    "maximum": 16
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
UQDECD Ztied.D, pattern, MUL #imm_factor
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQDECD--vector---Unsigned-saturating-decrement-vector-by-multiple-of-64-bit-predicate-constraint-element-count-

When result and op are in different registers, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
UQDECD Zresult.D, pattern, MUL #imm_factor
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQDECD--vector---Unsigned-saturating-decrement-vector-by-multiple-of-64-bit-predicate-constraint-element-count-

### Operation

Source operation ID: `SveOperation_svqdecd_pat_u64`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Multiply the number of 64-bit elements in vector pattern `pattern` by `imm_factor`.
- Subtract this value from `op[i]`, without loss of precision.
- Saturate the result to the range of `uint64_t`.

## svqdech[_n_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdech%5B_n_s32%5D

### Signature (source notation)

```c
int32_t svqdech[_n_s32](int32_t op, uint64_t imm_factor);
```

### Description

Saturating decrement by number of halfword elements

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector length / Saturating decrement

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
  "imm_factor": {
    "minimum": 1,
    "maximum": 16
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
SQDECH Xtied, Wtied, ALL, MUL #imm_factor
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDECH--scalar---Signed-saturating-decrement-scalar-by-multiple-of-16-bit-predicate-constraint-element-count-

### Operation

Source operation ID: `SveOperation_svqdech_n_s32`

**Operation**



Return the result of the following procedure:




- Multiply the number of 16-bit elements in a full vector by `imm_factor`.
- Subtract this value from `op`, without loss of precision.
- Saturate the result to the range of `int32_t`.

## svqdech[_n_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdech%5B_n_s64%5D

### Signature (source notation)

```c
int64_t svqdech[_n_s64](int64_t op, uint64_t imm_factor);
```

### Description

Saturating decrement by number of halfword elements

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector length / Saturating decrement

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
  "imm_factor": {
    "minimum": 1,
    "maximum": 16
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
SQDECH Xtied, ALL, MUL #imm_factor
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDECH--scalar---Signed-saturating-decrement-scalar-by-multiple-of-16-bit-predicate-constraint-element-count-

### Operation

Source operation ID: `SveOperation_svqdech_n_s64`

**Operation**



Return the result of the following procedure:




- Multiply the number of 16-bit elements in a full vector by `imm_factor`.
- Subtract this value from `op`, without loss of precision.
- Saturate the result to the range of `int64_t`.

## svqdech[_n_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdech%5B_n_u32%5D

### Signature (source notation)

```c
uint32_t svqdech[_n_u32](uint32_t op, uint64_t imm_factor);
```

### Description

Saturating decrement by number of halfword elements

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector length / Saturating decrement

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
  "imm_factor": {
    "minimum": 1,
    "maximum": 16
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
UQDECH Wtied, ALL, MUL #imm_factor
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQDECH--scalar---Unsigned-saturating-decrement-scalar-by-multiple-of-16-bit-predicate-constraint-element-count-

### Operation

Source operation ID: `SveOperation_svqdech_n_u32`

**Operation**



Return the result of the following procedure:




- Multiply the number of 16-bit elements in a full vector by `imm_factor`.
- Subtract this value from `op`, without loss of precision.
- Saturate the result to the range of `uint32_t`.

## svqdech[_n_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdech%5B_n_u64%5D

### Signature (source notation)

```c
uint64_t svqdech[_n_u64](uint64_t op, uint64_t imm_factor);
```

### Description

Saturating decrement by number of halfword elements

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector length / Saturating decrement

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
  "imm_factor": {
    "minimum": 1,
    "maximum": 16
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
UQDECH Xtied, ALL, MUL #imm_factor
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQDECH--scalar---Unsigned-saturating-decrement-scalar-by-multiple-of-16-bit-predicate-constraint-element-count-

### Operation

Source operation ID: `SveOperation_svqdech_n_u64`

**Operation**



Return the result of the following procedure:




- Multiply the number of 16-bit elements in a full vector by `imm_factor`.
- Subtract this value from `op`, without loss of precision.
- Saturate the result to the range of `uint64_t`.

## svqdech[_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdech%5B_s16%5D

### Signature (source notation)

```c
svint16_t svqdech[_s16](svint16_t op, uint64_t imm_factor);
```

### Description

Saturating decrement by number of halfword elements

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector length / Saturating decrement

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
  "imm_factor": {
    "minimum": 1,
    "maximum": 16
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
SQDECH Ztied.H, ALL, MUL #imm_factor
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDECH--vector---Signed-saturating-decrement-vector-by-multiple-of-16-bit-predicate-constraint-element-count-

When result and op are in different registers, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SQDECH Zresult.H, ALL, MUL #imm_factor
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDECH--vector---Signed-saturating-decrement-vector-by-multiple-of-16-bit-predicate-constraint-element-count-

### Operation

Source operation ID: `SveOperation_svqdech_s16`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Multiply the number of 16-bit elements in a full vector by `imm_factor`.
- Subtract this value from `op[i]`, without loss of precision.
- Saturate the result to the range of `int16_t`.

## svqdech[_u16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdech%5B_u16%5D

### Signature (source notation)

```c
svuint16_t svqdech[_u16](svuint16_t op, uint64_t imm_factor);
```

### Description

Saturating decrement by number of halfword elements

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector length / Saturating decrement

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
  "imm_factor": {
    "minimum": 1,
    "maximum": 16
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
UQDECH Ztied.H, ALL, MUL #imm_factor
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQDECH--vector---Unsigned-saturating-decrement-vector-by-multiple-of-16-bit-predicate-constraint-element-count-

When result and op are in different registers, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
UQDECH Zresult.H, ALL, MUL #imm_factor
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQDECH--vector---Unsigned-saturating-decrement-vector-by-multiple-of-16-bit-predicate-constraint-element-count-

### Operation

Source operation ID: `SveOperation_svqdech_u16`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Multiply the number of 16-bit elements in a full vector by `imm_factor`.
- Subtract this value from `op[i]`, without loss of precision.
- Saturate the result to the range of `uint16_t`.

## svqdech_pat[_n_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdech_pat%5B_n_s32%5D

### Signature (source notation)

```c
int32_t svqdech_pat[_n_s32](int32_t op, enum svpattern pattern, uint64_t imm_factor);
```

### Description

Saturating decrement by number of halfword elements

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector length / Saturating decrement

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
  "imm_factor": {
    "minimum": 1,
    "maximum": 16
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
SQDECH Xtied, Wtied, pattern, MUL #imm_factor
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDECH--scalar---Signed-saturating-decrement-scalar-by-multiple-of-16-bit-predicate-constraint-element-count-

### Operation

Source operation ID: `SveOperation_svqdech_pat_n_s32`

**Operation**



Return the result of the following procedure:




- Multiply the number of 16-bit elements in vector pattern `pattern` by `imm_factor`.
- Subtract this value from `op`, without loss of precision.
- Saturate the result to the range of `int32_t`.

## svqdech_pat[_n_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdech_pat%5B_n_s64%5D

### Signature (source notation)

```c
int64_t svqdech_pat[_n_s64](int64_t op, enum svpattern pattern, uint64_t imm_factor);
```

### Description

Saturating decrement by number of halfword elements

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector length / Saturating decrement

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
  "imm_factor": {
    "minimum": 1,
    "maximum": 16
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
SQDECH Xtied, pattern, MUL #imm_factor
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDECH--scalar---Signed-saturating-decrement-scalar-by-multiple-of-16-bit-predicate-constraint-element-count-

### Operation

Source operation ID: `SveOperation_svqdech_pat_n_s64`

**Operation**



Return the result of the following procedure:




- Multiply the number of 16-bit elements in vector pattern `pattern` by `imm_factor`.
- Subtract this value from `op`, without loss of precision.
- Saturate the result to the range of `int64_t`.

## svqdech_pat[_n_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdech_pat%5B_n_u32%5D

### Signature (source notation)

```c
uint32_t svqdech_pat[_n_u32](uint32_t op, enum svpattern pattern, uint64_t imm_factor);
```

### Description

Saturating decrement by number of halfword elements

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector length / Saturating decrement

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
  "imm_factor": {
    "minimum": 1,
    "maximum": 16
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
UQDECH Wtied, pattern, MUL #imm_factor
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQDECH--scalar---Unsigned-saturating-decrement-scalar-by-multiple-of-16-bit-predicate-constraint-element-count-

### Operation

Source operation ID: `SveOperation_svqdech_pat_n_u32`

**Operation**



Return the result of the following procedure:




- Multiply the number of 16-bit elements in vector pattern `pattern` by `imm_factor`.
- Subtract this value from `op`, without loss of precision.
- Saturate the result to the range of `uint32_t`.

## svqdech_pat[_n_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdech_pat%5B_n_u64%5D

### Signature (source notation)

```c
uint64_t svqdech_pat[_n_u64](uint64_t op, enum svpattern pattern, uint64_t imm_factor);
```

### Description

Saturating decrement by number of halfword elements

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector length / Saturating decrement

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
  "imm_factor": {
    "minimum": 1,
    "maximum": 16
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
UQDECH Xtied, pattern, MUL #imm_factor
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQDECH--scalar---Unsigned-saturating-decrement-scalar-by-multiple-of-16-bit-predicate-constraint-element-count-

### Operation

Source operation ID: `SveOperation_svqdech_pat_n_u64`

**Operation**



Return the result of the following procedure:




- Multiply the number of 16-bit elements in vector pattern `pattern` by `imm_factor`.
- Subtract this value from `op`, without loss of precision.
- Saturate the result to the range of `uint64_t`.

## svqdech_pat[_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdech_pat%5B_s16%5D

### Signature (source notation)

```c
svint16_t svqdech_pat[_s16](svint16_t op, enum svpattern pattern, uint64_t imm_factor);
```

### Description

Saturating decrement by number of halfword elements

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector length / Saturating decrement

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
  "imm_factor": {
    "minimum": 1,
    "maximum": 16
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
SQDECH Ztied.H, pattern, MUL #imm_factor
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDECH--vector---Signed-saturating-decrement-vector-by-multiple-of-16-bit-predicate-constraint-element-count-

When result and op are in different registers, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SQDECH Zresult.H, pattern, MUL #imm_factor
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDECH--vector---Signed-saturating-decrement-vector-by-multiple-of-16-bit-predicate-constraint-element-count-

### Operation

Source operation ID: `SveOperation_svqdech_pat_s16`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Multiply the number of 16-bit elements in vector pattern `pattern` by `imm_factor`.
- Subtract this value from `op[i]`, without loss of precision.
- Saturate the result to the range of `int16_t`.

## svqdech_pat[_u16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdech_pat%5B_u16%5D

### Signature (source notation)

```c
svuint16_t svqdech_pat[_u16](svuint16_t op, enum svpattern pattern, uint64_t imm_factor);
```

### Description

Saturating decrement by number of halfword elements

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector length / Saturating decrement

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
  "imm_factor": {
    "minimum": 1,
    "maximum": 16
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
UQDECH Ztied.H, pattern, MUL #imm_factor
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQDECH--vector---Unsigned-saturating-decrement-vector-by-multiple-of-16-bit-predicate-constraint-element-count-

When result and op are in different registers, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
UQDECH Zresult.H, pattern, MUL #imm_factor
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQDECH--vector---Unsigned-saturating-decrement-vector-by-multiple-of-16-bit-predicate-constraint-element-count-

### Operation

Source operation ID: `SveOperation_svqdech_pat_u16`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Multiply the number of 16-bit elements in vector pattern `pattern` by `imm_factor`.
- Subtract this value from `op[i]`, without loss of precision.
- Saturate the result to the range of `uint16_t`.

## svqdecw[_n_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdecw%5B_n_s32%5D

### Signature (source notation)

```c
int32_t svqdecw[_n_s32](int32_t op, uint64_t imm_factor);
```

### Description

Saturating decrement by number of word elements

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector length / Saturating decrement

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
  "imm_factor": {
    "minimum": 1,
    "maximum": 16
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
SQDECW Xtied, Wtied, ALL, MUL #imm_factor
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDECW--scalar---Signed-saturating-decrement-scalar-by-multiple-of-32-bit-predicate-constraint-element-count-

### Operation

Source operation ID: `SveOperation_svqdecw_n_s32`

**Operation**



Return the result of the following procedure:




- Multiply the number of 32-bit elements in a full vector by `imm_factor`.
- Subtract this value from `op`, without loss of precision.
- Saturate the result to the range of `int32_t`.

## svqdecw[_n_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdecw%5B_n_s64%5D

### Signature (source notation)

```c
int64_t svqdecw[_n_s64](int64_t op, uint64_t imm_factor);
```

### Description

Saturating decrement by number of word elements

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector length / Saturating decrement

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
  "imm_factor": {
    "minimum": 1,
    "maximum": 16
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
SQDECW Xtied, ALL, MUL #imm_factor
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDECW--scalar---Signed-saturating-decrement-scalar-by-multiple-of-32-bit-predicate-constraint-element-count-

### Operation

Source operation ID: `SveOperation_svqdecw_n_s64`

**Operation**



Return the result of the following procedure:




- Multiply the number of 32-bit elements in a full vector by `imm_factor`.
- Subtract this value from `op`, without loss of precision.
- Saturate the result to the range of `int64_t`.

## svqdecw[_n_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdecw%5B_n_u32%5D

### Signature (source notation)

```c
uint32_t svqdecw[_n_u32](uint32_t op, uint64_t imm_factor);
```

### Description

Saturating decrement by number of word elements

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector length / Saturating decrement

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
  "imm_factor": {
    "minimum": 1,
    "maximum": 16
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
UQDECW Wtied, ALL, MUL #imm_factor
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQDECW--scalar---Unsigned-saturating-decrement-scalar-by-multiple-of-32-bit-predicate-constraint-element-count-

### Operation

Source operation ID: `SveOperation_svqdecw_n_u32`

**Operation**



Return the result of the following procedure:




- Multiply the number of 32-bit elements in a full vector by `imm_factor`.
- Subtract this value from `op`, without loss of precision.
- Saturate the result to the range of `uint32_t`.

## svqdecw[_n_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdecw%5B_n_u64%5D

### Signature (source notation)

```c
uint64_t svqdecw[_n_u64](uint64_t op, uint64_t imm_factor);
```

### Description

Saturating decrement by number of word elements

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector length / Saturating decrement

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
  "imm_factor": {
    "minimum": 1,
    "maximum": 16
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
UQDECW Xtied, ALL, MUL #imm_factor
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQDECW--scalar---Unsigned-saturating-decrement-scalar-by-multiple-of-32-bit-predicate-constraint-element-count-

### Operation

Source operation ID: `SveOperation_svqdecw_n_u64`

**Operation**



Return the result of the following procedure:




- Multiply the number of 32-bit elements in a full vector by `imm_factor`.
- Subtract this value from `op`, without loss of precision.
- Saturate the result to the range of `uint64_t`.

## svqdecw[_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdecw%5B_s32%5D

### Signature (source notation)

```c
svint32_t svqdecw[_s32](svint32_t op, uint64_t imm_factor);
```

### Description

Saturating decrement by number of word elements

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector length / Saturating decrement

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
  "imm_factor": {
    "minimum": 1,
    "maximum": 16
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
SQDECW Ztied.S, ALL, MUL #imm_factor
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDECW--vector---Signed-saturating-decrement-vector-by-multiple-of-32-bit-predicate-constraint-element-count-

When result and op are in different registers, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SQDECW Zresult.S, ALL, MUL #imm_factor
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDECW--vector---Signed-saturating-decrement-vector-by-multiple-of-32-bit-predicate-constraint-element-count-

### Operation

Source operation ID: `SveOperation_svqdecw_s32`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Multiply the number of 32-bit elements in a full vector by `imm_factor`.
- Subtract this value from `op[i]`, without loss of precision.
- Saturate the result to the range of `int32_t`.

## svqdecw[_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdecw%5B_u32%5D

### Signature (source notation)

```c
svuint32_t svqdecw[_u32](svuint32_t op, uint64_t imm_factor);
```

### Description

Saturating decrement by number of word elements

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector length / Saturating decrement

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
  "imm_factor": {
    "minimum": 1,
    "maximum": 16
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
UQDECW Ztied.S, ALL, MUL #imm_factor
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQDECW--vector---Unsigned-saturating-decrement-vector-by-multiple-of-32-bit-predicate-constraint-element-count-

When result and op are in different registers, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
UQDECW Zresult.S, ALL, MUL #imm_factor
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQDECW--vector---Unsigned-saturating-decrement-vector-by-multiple-of-32-bit-predicate-constraint-element-count-

### Operation

Source operation ID: `SveOperation_svqdecw_u32`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Multiply the number of 32-bit elements in a full vector by `imm_factor`.
- Subtract this value from `op[i]`, without loss of precision.
- Saturate the result to the range of `uint32_t`.

## svqdecw_pat[_n_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdecw_pat%5B_n_s32%5D

### Signature (source notation)

```c
int32_t svqdecw_pat[_n_s32](int32_t op, enum svpattern pattern, uint64_t imm_factor);
```

### Description

Saturating decrement by number of word elements

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector length / Saturating decrement

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
  "imm_factor": {
    "minimum": 1,
    "maximum": 16
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
SQDECW Xtied, Wtied, pattern, MUL #imm_factor
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDECW--scalar---Signed-saturating-decrement-scalar-by-multiple-of-32-bit-predicate-constraint-element-count-

### Operation

Source operation ID: `SveOperation_svqdecw_pat_n_s32`

**Operation**



Return the result of the following procedure:




- Multiply the number of 32-bit elements in vector pattern `pattern` by `imm_factor`.
- Subtract this value from `op`, without loss of precision.
- Saturate the result to the range of `int32_t`.

## svqdecw_pat[_n_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdecw_pat%5B_n_s64%5D

### Signature (source notation)

```c
int64_t svqdecw_pat[_n_s64](int64_t op, enum svpattern pattern, uint64_t imm_factor);
```

### Description

Saturating decrement by number of word elements

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector length / Saturating decrement

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
  "imm_factor": {
    "minimum": 1,
    "maximum": 16
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
SQDECW Xtied, pattern, MUL #imm_factor
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDECW--scalar---Signed-saturating-decrement-scalar-by-multiple-of-32-bit-predicate-constraint-element-count-

### Operation

Source operation ID: `SveOperation_svqdecw_pat_n_s64`

**Operation**



Return the result of the following procedure:




- Multiply the number of 32-bit elements in vector pattern `pattern` by `imm_factor`.
- Subtract this value from `op`, without loss of precision.
- Saturate the result to the range of `int64_t`.

## svqdecw_pat[_n_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdecw_pat%5B_n_u32%5D

### Signature (source notation)

```c
uint32_t svqdecw_pat[_n_u32](uint32_t op, enum svpattern pattern, uint64_t imm_factor);
```

### Description

Saturating decrement by number of word elements

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector length / Saturating decrement

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
  "imm_factor": {
    "minimum": 1,
    "maximum": 16
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
UQDECW Wtied, pattern, MUL #imm_factor
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQDECW--scalar---Unsigned-saturating-decrement-scalar-by-multiple-of-32-bit-predicate-constraint-element-count-

### Operation

Source operation ID: `SveOperation_svqdecw_pat_n_u32`

**Operation**



Return the result of the following procedure:




- Multiply the number of 32-bit elements in vector pattern `pattern` by `imm_factor`.
- Subtract this value from `op`, without loss of precision.
- Saturate the result to the range of `uint32_t`.

## svqdecw_pat[_n_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdecw_pat%5B_n_u64%5D

### Signature (source notation)

```c
uint64_t svqdecw_pat[_n_u64](uint64_t op, enum svpattern pattern, uint64_t imm_factor);
```

### Description

Saturating decrement by number of word elements

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector length / Saturating decrement

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
  "imm_factor": {
    "minimum": 1,
    "maximum": 16
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
UQDECW Xtied, pattern, MUL #imm_factor
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQDECW--scalar---Unsigned-saturating-decrement-scalar-by-multiple-of-32-bit-predicate-constraint-element-count-

### Operation

Source operation ID: `SveOperation_svqdecw_pat_n_u64`

**Operation**



Return the result of the following procedure:




- Multiply the number of 32-bit elements in vector pattern `pattern` by `imm_factor`.
- Subtract this value from `op`, without loss of precision.
- Saturate the result to the range of `uint64_t`.

## svqdecw_pat[_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdecw_pat%5B_s32%5D

### Signature (source notation)

```c
svint32_t svqdecw_pat[_s32](svint32_t op, enum svpattern pattern, uint64_t imm_factor);
```

### Description

Saturating decrement by number of word elements

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector length / Saturating decrement

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
  "imm_factor": {
    "minimum": 1,
    "maximum": 16
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
SQDECW Ztied.S, pattern, MUL #imm_factor
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDECW--vector---Signed-saturating-decrement-vector-by-multiple-of-32-bit-predicate-constraint-element-count-

When result and op are in different registers, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SQDECW Zresult.S, pattern, MUL #imm_factor
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDECW--vector---Signed-saturating-decrement-vector-by-multiple-of-32-bit-predicate-constraint-element-count-

### Operation

Source operation ID: `SveOperation_svqdecw_pat_s32`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Multiply the number of 32-bit elements in vector pattern `pattern` by `imm_factor`.
- Subtract this value from `op[i]`, without loss of precision.
- Saturate the result to the range of `int32_t`.

## svqdecw_pat[_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdecw_pat%5B_u32%5D

### Signature (source notation)

```c
svuint32_t svqdecw_pat[_u32](svuint32_t op, enum svpattern pattern, uint64_t imm_factor);
```

### Description

Saturating decrement by number of word elements

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector length / Saturating decrement

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
  "imm_factor": {
    "minimum": 1,
    "maximum": 16
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
UQDECW Ztied.S, pattern, MUL #imm_factor
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQDECW--vector---Unsigned-saturating-decrement-vector-by-multiple-of-32-bit-predicate-constraint-element-count-

When result and op are in different registers, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
UQDECW Zresult.S, pattern, MUL #imm_factor
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQDECW--vector---Unsigned-saturating-decrement-vector-by-multiple-of-32-bit-predicate-constraint-element-count-

### Operation

Source operation ID: `SveOperation_svqdecw_pat_u32`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Multiply the number of 32-bit elements in vector pattern `pattern` by `imm_factor`.
- Subtract this value from `op[i]`, without loss of precision.
- Saturate the result to the range of `uint32_t`.

