# SME / Vector length / Saturating increment — Part 1

## svqincb[_n_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqincb%5B_n_s32%5D

### Signature (source notation)

```c
int32_t svqincb[_n_s32](int32_t op, uint64_t imm_factor);
```

### Description

Saturating increment by number of byte elements

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector length / Saturating increment

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
SQINCB Xtied, Wtied, ALL, MUL #imm_factor
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQINCB--Signed-saturating-increment-scalar-by-multiple-of-8-bit-predicate-constraint-element-count-

### Operation

Source operation ID: `SveOperation_svqincb_n_s32`

**Operation**



Return the result of the following procedure:




- Multiply the number of 8-bit elements in a full vector by `imm_factor`.
- Add this value to `op`, without loss of precision.
- Saturate the result to the range of `int32_t`.

## svqincb[_n_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqincb%5B_n_s64%5D

### Signature (source notation)

```c
int64_t svqincb[_n_s64](int64_t op, uint64_t imm_factor);
```

### Description

Saturating increment by number of byte elements

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector length / Saturating increment

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
SQINCB Xtied, ALL, MUL #imm_factor
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQINCB--Signed-saturating-increment-scalar-by-multiple-of-8-bit-predicate-constraint-element-count-

### Operation

Source operation ID: `SveOperation_svqincb_n_s64`

**Operation**



Return the result of the following procedure:




- Multiply the number of 8-bit elements in a full vector by `imm_factor`.
- Add this value to `op`, without loss of precision.
- Saturate the result to the range of `int64_t`.

## svqincb[_n_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqincb%5B_n_u32%5D

### Signature (source notation)

```c
uint32_t svqincb[_n_u32](uint32_t op, uint64_t imm_factor);
```

### Description

Saturating increment by number of byte elements

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector length / Saturating increment

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
UQINCB Wtied, ALL, MUL #imm_factor
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQINCB--Unsigned-saturating-increment-scalar-by-multiple-of-8-bit-predicate-constraint-element-count-

### Operation

Source operation ID: `SveOperation_svqincb_n_u32`

**Operation**



Return the result of the following procedure:




- Multiply the number of 8-bit elements in a full vector by `imm_factor`.
- Add this value to `op`, without loss of precision.
- Saturate the result to the range of `uint32_t`.

## svqincb[_n_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqincb%5B_n_u64%5D

### Signature (source notation)

```c
uint64_t svqincb[_n_u64](uint64_t op, uint64_t imm_factor);
```

### Description

Saturating increment by number of byte elements

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector length / Saturating increment

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
UQINCB Xtied, ALL, MUL #imm_factor
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQINCB--Unsigned-saturating-increment-scalar-by-multiple-of-8-bit-predicate-constraint-element-count-

### Operation

Source operation ID: `SveOperation_svqincb_n_u64`

**Operation**



Return the result of the following procedure:




- Multiply the number of 8-bit elements in a full vector by `imm_factor`.
- Add this value to `op`, without loss of precision.
- Saturate the result to the range of `uint64_t`.

## svqincb_pat[_n_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqincb_pat%5B_n_s32%5D

### Signature (source notation)

```c
int32_t svqincb_pat[_n_s32](int32_t op, enum svpattern pattern, uint64_t imm_factor);
```

### Description

Saturating increment by number of byte elements

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector length / Saturating increment

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
SQINCB Xtied, Wtied, pattern, MUL #imm_factor
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQINCB--Signed-saturating-increment-scalar-by-multiple-of-8-bit-predicate-constraint-element-count-

### Operation

Source operation ID: `SveOperation_svqincb_pat_n_s32`

**Operation**



Return the result of the following procedure:




- Multiply the number of 8-bit elements in vector pattern `pattern` by `imm_factor`.
- Add this value to `op`, without loss of precision.
- Saturate the result to the range of `int32_t`.

## svqincb_pat[_n_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqincb_pat%5B_n_s64%5D

### Signature (source notation)

```c
int64_t svqincb_pat[_n_s64](int64_t op, enum svpattern pattern, uint64_t imm_factor);
```

### Description

Saturating increment by number of byte elements

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector length / Saturating increment

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
SQINCB Xtied, pattern, MUL #imm_factor
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQINCB--Signed-saturating-increment-scalar-by-multiple-of-8-bit-predicate-constraint-element-count-

### Operation

Source operation ID: `SveOperation_svqincb_pat_n_s64`

**Operation**



Return the result of the following procedure:




- Multiply the number of 8-bit elements in vector pattern `pattern` by `imm_factor`.
- Add this value to `op`, without loss of precision.
- Saturate the result to the range of `int64_t`.

## svqincb_pat[_n_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqincb_pat%5B_n_u32%5D

### Signature (source notation)

```c
uint32_t svqincb_pat[_n_u32](uint32_t op, enum svpattern pattern, uint64_t imm_factor);
```

### Description

Saturating increment by number of byte elements

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector length / Saturating increment

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
UQINCB Wtied, pattern, MUL #imm_factor
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQINCB--Unsigned-saturating-increment-scalar-by-multiple-of-8-bit-predicate-constraint-element-count-

### Operation

Source operation ID: `SveOperation_svqincb_pat_n_u32`

**Operation**



Return the result of the following procedure:




- Multiply the number of 8-bit elements in vector pattern `pattern` by `imm_factor`.
- Add this value to `op`, without loss of precision.
- Saturate the result to the range of `uint32_t`.

## svqincb_pat[_n_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqincb_pat%5B_n_u64%5D

### Signature (source notation)

```c
uint64_t svqincb_pat[_n_u64](uint64_t op, enum svpattern pattern, uint64_t imm_factor);
```

### Description

Saturating increment by number of byte elements

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector length / Saturating increment

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
UQINCB Xtied, pattern, MUL #imm_factor
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQINCB--Unsigned-saturating-increment-scalar-by-multiple-of-8-bit-predicate-constraint-element-count-

### Operation

Source operation ID: `SveOperation_svqincb_pat_n_u64`

**Operation**



Return the result of the following procedure:




- Multiply the number of 8-bit elements in vector pattern `pattern` by `imm_factor`.
- Add this value to `op`, without loss of precision.
- Saturate the result to the range of `uint64_t`.

## svqincd[_n_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqincd%5B_n_s32%5D

### Signature (source notation)

```c
int32_t svqincd[_n_s32](int32_t op, uint64_t imm_factor);
```

### Description

Saturating increment by number of doubleword elements

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector length / Saturating increment

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
SQINCD Xtied, Wtied, ALL, MUL #imm_factor
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQINCD--scalar---Signed-saturating-increment-scalar-by-multiple-of-64-bit-predicate-constraint-element-count-

### Operation

Source operation ID: `SveOperation_svqincd_n_s32`

**Operation**



Return the result of the following procedure:




- Multiply the number of 64-bit elements in a full vector by `imm_factor`.
- Add this value to `op`, without loss of precision.
- Saturate the result to the range of `int32_t`.

## svqincd[_n_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqincd%5B_n_s64%5D

### Signature (source notation)

```c
int64_t svqincd[_n_s64](int64_t op, uint64_t imm_factor);
```

### Description

Saturating increment by number of doubleword elements

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector length / Saturating increment

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
SQINCD Xtied, ALL, MUL #imm_factor
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQINCD--scalar---Signed-saturating-increment-scalar-by-multiple-of-64-bit-predicate-constraint-element-count-

### Operation

Source operation ID: `SveOperation_svqincd_n_s64`

**Operation**



Return the result of the following procedure:




- Multiply the number of 64-bit elements in a full vector by `imm_factor`.
- Add this value to `op`, without loss of precision.
- Saturate the result to the range of `int64_t`.

## svqincd[_n_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqincd%5B_n_u32%5D

### Signature (source notation)

```c
uint32_t svqincd[_n_u32](uint32_t op, uint64_t imm_factor);
```

### Description

Saturating increment by number of doubleword elements

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector length / Saturating increment

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
UQINCD Wtied, ALL, MUL #imm_factor
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQINCD--scalar---Unsigned-saturating-increment-scalar-by-multiple-of-64-bit-predicate-constraint-element-count-

### Operation

Source operation ID: `SveOperation_svqincd_n_u32`

**Operation**



Return the result of the following procedure:




- Multiply the number of 64-bit elements in a full vector by `imm_factor`.
- Add this value to `op`, without loss of precision.
- Saturate the result to the range of `uint32_t`.

## svqincd[_n_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqincd%5B_n_u64%5D

### Signature (source notation)

```c
uint64_t svqincd[_n_u64](uint64_t op, uint64_t imm_factor);
```

### Description

Saturating increment by number of doubleword elements

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector length / Saturating increment

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
UQINCD Xtied, ALL, MUL #imm_factor
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQINCD--scalar---Unsigned-saturating-increment-scalar-by-multiple-of-64-bit-predicate-constraint-element-count-

### Operation

Source operation ID: `SveOperation_svqincd_n_u64`

**Operation**



Return the result of the following procedure:




- Multiply the number of 64-bit elements in a full vector by `imm_factor`.
- Add this value to `op`, without loss of precision.
- Saturate the result to the range of `uint64_t`.

## svqincd[_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqincd%5B_s64%5D

### Signature (source notation)

```c
svint64_t svqincd[_s64](svint64_t op, uint64_t imm_factor);
```

### Description

Saturating increment by number of doubleword elements

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector length / Saturating increment

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
SQINCD Ztied.D, ALL, MUL #imm_factor
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQINCD--vector---Signed-saturating-increment-vector-by-multiple-of-64-bit-predicate-constraint-element-count-

When result and op are in different registers, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SQINCD Zresult.D, ALL, MUL #imm_factor
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQINCD--vector---Signed-saturating-increment-vector-by-multiple-of-64-bit-predicate-constraint-element-count-

### Operation

Source operation ID: `SveOperation_svqincd_s64`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Multiply the number of 64-bit elements in a full vector by `imm_factor`.
- Add this value to `op[i]`, without loss of precision.
- Saturate the result to the range of `int64_t`.

## svqincd[_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqincd%5B_u64%5D

### Signature (source notation)

```c
svuint64_t svqincd[_u64](svuint64_t op, uint64_t imm_factor);
```

### Description

Saturating increment by number of doubleword elements

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector length / Saturating increment

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
UQINCD Ztied.D, ALL, MUL #imm_factor
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQINCD--vector---Unsigned-saturating-increment-vector-by-multiple-of-64-bit-predicate-constraint-element-count-

When result and op are in different registers, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
UQINCD Zresult.D, ALL, MUL #imm_factor
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQINCD--vector---Unsigned-saturating-increment-vector-by-multiple-of-64-bit-predicate-constraint-element-count-

### Operation

Source operation ID: `SveOperation_svqincd_u64`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Multiply the number of 64-bit elements in a full vector by `imm_factor`.
- Add this value to `op[i]`, without loss of precision.
- Saturate the result to the range of `uint64_t`.

## svqincd_pat[_n_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqincd_pat%5B_n_s32%5D

### Signature (source notation)

```c
int32_t svqincd_pat[_n_s32](int32_t op, enum svpattern pattern, uint64_t imm_factor);
```

### Description

Saturating increment by number of doubleword elements

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector length / Saturating increment

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
SQINCD Xtied, Wtied, pattern, MUL #imm_factor
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQINCD--scalar---Signed-saturating-increment-scalar-by-multiple-of-64-bit-predicate-constraint-element-count-

### Operation

Source operation ID: `SveOperation_svqincd_pat_n_s32`

**Operation**



Return the result of the following procedure:




- Multiply the number of 64-bit elements in vector pattern `pattern` by `imm_factor`.
- Add this value to `op`, without loss of precision.
- Saturate the result to the range of `int32_t`.

## svqincd_pat[_n_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqincd_pat%5B_n_s64%5D

### Signature (source notation)

```c
int64_t svqincd_pat[_n_s64](int64_t op, enum svpattern pattern, uint64_t imm_factor);
```

### Description

Saturating increment by number of doubleword elements

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector length / Saturating increment

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
SQINCD Xtied, pattern, MUL #imm_factor
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQINCD--scalar---Signed-saturating-increment-scalar-by-multiple-of-64-bit-predicate-constraint-element-count-

### Operation

Source operation ID: `SveOperation_svqincd_pat_n_s64`

**Operation**



Return the result of the following procedure:




- Multiply the number of 64-bit elements in vector pattern `pattern` by `imm_factor`.
- Add this value to `op`, without loss of precision.
- Saturate the result to the range of `int64_t`.

## svqincd_pat[_n_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqincd_pat%5B_n_u32%5D

### Signature (source notation)

```c
uint32_t svqincd_pat[_n_u32](uint32_t op, enum svpattern pattern, uint64_t imm_factor);
```

### Description

Saturating increment by number of doubleword elements

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector length / Saturating increment

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
UQINCD Wtied, pattern, MUL #imm_factor
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQINCD--scalar---Unsigned-saturating-increment-scalar-by-multiple-of-64-bit-predicate-constraint-element-count-

### Operation

Source operation ID: `SveOperation_svqincd_pat_n_u32`

**Operation**



Return the result of the following procedure:




- Multiply the number of 64-bit elements in vector pattern `pattern` by `imm_factor`.
- Add this value to `op`, without loss of precision.
- Saturate the result to the range of `uint32_t`.

## svqincd_pat[_n_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqincd_pat%5B_n_u64%5D

### Signature (source notation)

```c
uint64_t svqincd_pat[_n_u64](uint64_t op, enum svpattern pattern, uint64_t imm_factor);
```

### Description

Saturating increment by number of doubleword elements

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector length / Saturating increment

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
UQINCD Xtied, pattern, MUL #imm_factor
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQINCD--scalar---Unsigned-saturating-increment-scalar-by-multiple-of-64-bit-predicate-constraint-element-count-

### Operation

Source operation ID: `SveOperation_svqincd_pat_n_u64`

**Operation**



Return the result of the following procedure:




- Multiply the number of 64-bit elements in vector pattern `pattern` by `imm_factor`.
- Add this value to `op`, without loss of precision.
- Saturate the result to the range of `uint64_t`.

## svqincd_pat[_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqincd_pat%5B_s64%5D

### Signature (source notation)

```c
svint64_t svqincd_pat[_s64](svint64_t op, enum svpattern pattern, uint64_t imm_factor);
```

### Description

Saturating increment by number of doubleword elements

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector length / Saturating increment

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
SQINCD Ztied.D, pattern, MUL #imm_factor
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQINCD--vector---Signed-saturating-increment-vector-by-multiple-of-64-bit-predicate-constraint-element-count-

When result and op are in different registers, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SQINCD Zresult.D, pattern, MUL #imm_factor
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQINCD--vector---Signed-saturating-increment-vector-by-multiple-of-64-bit-predicate-constraint-element-count-

### Operation

Source operation ID: `SveOperation_svqincd_pat_s64`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Multiply the number of 64-bit elements in vector pattern `pattern` by `imm_factor`.
- Add this value to `op[i]`, without loss of precision.
- Saturate the result to the range of `int64_t`.

## svqincd_pat[_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqincd_pat%5B_u64%5D

### Signature (source notation)

```c
svuint64_t svqincd_pat[_u64](svuint64_t op, enum svpattern pattern, uint64_t imm_factor);
```

### Description

Saturating increment by number of doubleword elements

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector length / Saturating increment

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
UQINCD Ztied.D, pattern, MUL #imm_factor
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQINCD--vector---Unsigned-saturating-increment-vector-by-multiple-of-64-bit-predicate-constraint-element-count-

When result and op are in different registers, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
UQINCD Zresult.D, pattern, MUL #imm_factor
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQINCD--vector---Unsigned-saturating-increment-vector-by-multiple-of-64-bit-predicate-constraint-element-count-

### Operation

Source operation ID: `SveOperation_svqincd_pat_u64`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Multiply the number of 64-bit elements in vector pattern `pattern` by `imm_factor`.
- Add this value to `op[i]`, without loss of precision.
- Saturate the result to the range of `uint64_t`.

## svqinch[_n_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqinch%5B_n_s32%5D

### Signature (source notation)

```c
int32_t svqinch[_n_s32](int32_t op, uint64_t imm_factor);
```

### Description

Saturating increment by number of halfword elements

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector length / Saturating increment

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
SQINCH Xtied, Wtied, ALL, MUL #imm_factor
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQINCH--scalar---Signed-saturating-increment-scalar-by-multiple-of-16-bit-predicate-constraint-element-count-

### Operation

Source operation ID: `SveOperation_svqinch_n_s32`

**Operation**



Return the result of the following procedure:




- Multiply the number of 16-bit elements in a full vector by `imm_factor`.
- Add this value to `op`, without loss of precision.
- Saturate the result to the range of `int32_t`.

## svqinch[_n_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqinch%5B_n_s64%5D

### Signature (source notation)

```c
int64_t svqinch[_n_s64](int64_t op, uint64_t imm_factor);
```

### Description

Saturating increment by number of halfword elements

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector length / Saturating increment

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
SQINCH Xtied, ALL, MUL #imm_factor
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQINCH--scalar---Signed-saturating-increment-scalar-by-multiple-of-16-bit-predicate-constraint-element-count-

### Operation

Source operation ID: `SveOperation_svqinch_n_s64`

**Operation**



Return the result of the following procedure:




- Multiply the number of 16-bit elements in a full vector by `imm_factor`.
- Add this value to `op`, without loss of precision.
- Saturate the result to the range of `int64_t`.

## svqinch[_n_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqinch%5B_n_u32%5D

### Signature (source notation)

```c
uint32_t svqinch[_n_u32](uint32_t op, uint64_t imm_factor);
```

### Description

Saturating increment by number of halfword elements

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector length / Saturating increment

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
UQINCH Wtied, ALL, MUL #imm_factor
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQINCH--scalar---Unsigned-saturating-increment-scalar-by-multiple-of-16-bit-predicate-constraint-element-count-

### Operation

Source operation ID: `SveOperation_svqinch_n_u32`

**Operation**



Return the result of the following procedure:




- Multiply the number of 16-bit elements in a full vector by `imm_factor`.
- Add this value to `op`, without loss of precision.
- Saturate the result to the range of `uint32_t`.

## svqinch[_n_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqinch%5B_n_u64%5D

### Signature (source notation)

```c
uint64_t svqinch[_n_u64](uint64_t op, uint64_t imm_factor);
```

### Description

Saturating increment by number of halfword elements

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector length / Saturating increment

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
UQINCH Xtied, ALL, MUL #imm_factor
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQINCH--scalar---Unsigned-saturating-increment-scalar-by-multiple-of-16-bit-predicate-constraint-element-count-

### Operation

Source operation ID: `SveOperation_svqinch_n_u64`

**Operation**



Return the result of the following procedure:




- Multiply the number of 16-bit elements in a full vector by `imm_factor`.
- Add this value to `op`, without loss of precision.
- Saturate the result to the range of `uint64_t`.

## svqinch[_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqinch%5B_s16%5D

### Signature (source notation)

```c
svint16_t svqinch[_s16](svint16_t op, uint64_t imm_factor);
```

### Description

Saturating increment by number of halfword elements

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector length / Saturating increment

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
SQINCH Ztied.H, ALL, MUL #imm_factor
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQINCH--vector---Signed-saturating-increment-vector-by-multiple-of-16-bit-predicate-constraint-element-count-

When result and op are in different registers, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SQINCH Zresult.H, ALL, MUL #imm_factor
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQINCH--vector---Signed-saturating-increment-vector-by-multiple-of-16-bit-predicate-constraint-element-count-

### Operation

Source operation ID: `SveOperation_svqinch_s16`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Multiply the number of 16-bit elements in a full vector by `imm_factor`.
- Add this value to `op[i]`, without loss of precision.
- Saturate the result to the range of `int16_t`.

## svqinch[_u16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqinch%5B_u16%5D

### Signature (source notation)

```c
svuint16_t svqinch[_u16](svuint16_t op, uint64_t imm_factor);
```

### Description

Saturating increment by number of halfword elements

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector length / Saturating increment

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
UQINCH Ztied.H, ALL, MUL #imm_factor
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQINCH--vector---Unsigned-saturating-increment-vector-by-multiple-of-16-bit-predicate-constraint-element-count-

When result and op are in different registers, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
UQINCH Zresult.H, ALL, MUL #imm_factor
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQINCH--vector---Unsigned-saturating-increment-vector-by-multiple-of-16-bit-predicate-constraint-element-count-

### Operation

Source operation ID: `SveOperation_svqinch_u16`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Multiply the number of 16-bit elements in a full vector by `imm_factor`.
- Add this value to `op[i]`, without loss of precision.
- Saturate the result to the range of `uint16_t`.

## svqinch_pat[_n_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqinch_pat%5B_n_s32%5D

### Signature (source notation)

```c
int32_t svqinch_pat[_n_s32](int32_t op, enum svpattern pattern, uint64_t imm_factor);
```

### Description

Saturating increment by number of halfword elements

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector length / Saturating increment

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
SQINCH Xtied, Wtied, pattern, MUL #imm_factor
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQINCH--scalar---Signed-saturating-increment-scalar-by-multiple-of-16-bit-predicate-constraint-element-count-

### Operation

Source operation ID: `SveOperation_svqinch_pat_n_s32`

**Operation**



Return the result of the following procedure:




- Multiply the number of 16-bit elements in vector pattern `pattern` by `imm_factor`.
- Add this value to `op`, without loss of precision.
- Saturate the result to the range of `int32_t`.

## svqinch_pat[_n_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqinch_pat%5B_n_s64%5D

### Signature (source notation)

```c
int64_t svqinch_pat[_n_s64](int64_t op, enum svpattern pattern, uint64_t imm_factor);
```

### Description

Saturating increment by number of halfword elements

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector length / Saturating increment

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
SQINCH Xtied, pattern, MUL #imm_factor
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQINCH--scalar---Signed-saturating-increment-scalar-by-multiple-of-16-bit-predicate-constraint-element-count-

### Operation

Source operation ID: `SveOperation_svqinch_pat_n_s64`

**Operation**



Return the result of the following procedure:




- Multiply the number of 16-bit elements in vector pattern `pattern` by `imm_factor`.
- Add this value to `op`, without loss of precision.
- Saturate the result to the range of `int64_t`.

## svqinch_pat[_n_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqinch_pat%5B_n_u32%5D

### Signature (source notation)

```c
uint32_t svqinch_pat[_n_u32](uint32_t op, enum svpattern pattern, uint64_t imm_factor);
```

### Description

Saturating increment by number of halfword elements

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector length / Saturating increment

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
UQINCH Wtied, pattern, MUL #imm_factor
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQINCH--scalar---Unsigned-saturating-increment-scalar-by-multiple-of-16-bit-predicate-constraint-element-count-

### Operation

Source operation ID: `SveOperation_svqinch_pat_n_u32`

**Operation**



Return the result of the following procedure:




- Multiply the number of 16-bit elements in vector pattern `pattern` by `imm_factor`.
- Add this value to `op`, without loss of precision.
- Saturate the result to the range of `uint32_t`.

## svqinch_pat[_n_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqinch_pat%5B_n_u64%5D

### Signature (source notation)

```c
uint64_t svqinch_pat[_n_u64](uint64_t op, enum svpattern pattern, uint64_t imm_factor);
```

### Description

Saturating increment by number of halfword elements

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector length / Saturating increment

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
UQINCH Xtied, pattern, MUL #imm_factor
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQINCH--scalar---Unsigned-saturating-increment-scalar-by-multiple-of-16-bit-predicate-constraint-element-count-

### Operation

Source operation ID: `SveOperation_svqinch_pat_n_u64`

**Operation**



Return the result of the following procedure:




- Multiply the number of 16-bit elements in vector pattern `pattern` by `imm_factor`.
- Add this value to `op`, without loss of precision.
- Saturate the result to the range of `uint64_t`.

## svqinch_pat[_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqinch_pat%5B_s16%5D

### Signature (source notation)

```c
svint16_t svqinch_pat[_s16](svint16_t op, enum svpattern pattern, uint64_t imm_factor);
```

### Description

Saturating increment by number of halfword elements

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector length / Saturating increment

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
SQINCH Ztied.H, pattern, MUL #imm_factor
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQINCH--vector---Signed-saturating-increment-vector-by-multiple-of-16-bit-predicate-constraint-element-count-

When result and op are in different registers, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SQINCH Zresult.H, pattern, MUL #imm_factor
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQINCH--vector---Signed-saturating-increment-vector-by-multiple-of-16-bit-predicate-constraint-element-count-

### Operation

Source operation ID: `SveOperation_svqinch_pat_s16`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Multiply the number of 16-bit elements in vector pattern `pattern` by `imm_factor`.
- Add this value to `op[i]`, without loss of precision.
- Saturate the result to the range of `int16_t`.

## svqinch_pat[_u16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqinch_pat%5B_u16%5D

### Signature (source notation)

```c
svuint16_t svqinch_pat[_u16](svuint16_t op, enum svpattern pattern, uint64_t imm_factor);
```

### Description

Saturating increment by number of halfword elements

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector length / Saturating increment

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
UQINCH Ztied.H, pattern, MUL #imm_factor
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQINCH--vector---Unsigned-saturating-increment-vector-by-multiple-of-16-bit-predicate-constraint-element-count-

When result and op are in different registers, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
UQINCH Zresult.H, pattern, MUL #imm_factor
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQINCH--vector---Unsigned-saturating-increment-vector-by-multiple-of-16-bit-predicate-constraint-element-count-

### Operation

Source operation ID: `SveOperation_svqinch_pat_u16`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Multiply the number of 16-bit elements in vector pattern `pattern` by `imm_factor`.
- Add this value to `op[i]`, without loss of precision.
- Saturate the result to the range of `uint16_t`.

## svqincw[_n_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqincw%5B_n_s32%5D

### Signature (source notation)

```c
int32_t svqincw[_n_s32](int32_t op, uint64_t imm_factor);
```

### Description

Saturating increment by number of word elements

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector length / Saturating increment

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
SQINCW Xtied, Wtied, ALL, MUL #imm_factor
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQINCW--scalar---Signed-saturating-increment-scalar-by-multiple-of-32-bit-predicate-constraint-element-count-

### Operation

Source operation ID: `SveOperation_svqincw_n_s32`

**Operation**



Return the result of the following procedure:




- Multiply the number of 32-bit elements in a full vector by `imm_factor`.
- Add this value to `op`, without loss of precision.
- Saturate the result to the range of `int32_t`.

## svqincw[_n_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqincw%5B_n_s64%5D

### Signature (source notation)

```c
int64_t svqincw[_n_s64](int64_t op, uint64_t imm_factor);
```

### Description

Saturating increment by number of word elements

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector length / Saturating increment

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
SQINCW Xtied, ALL, MUL #imm_factor
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQINCW--scalar---Signed-saturating-increment-scalar-by-multiple-of-32-bit-predicate-constraint-element-count-

### Operation

Source operation ID: `SveOperation_svqincw_n_s64`

**Operation**



Return the result of the following procedure:




- Multiply the number of 32-bit elements in a full vector by `imm_factor`.
- Add this value to `op`, without loss of precision.
- Saturate the result to the range of `int64_t`.

## svqincw[_n_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqincw%5B_n_u32%5D

### Signature (source notation)

```c
uint32_t svqincw[_n_u32](uint32_t op, uint64_t imm_factor);
```

### Description

Saturating increment by number of word elements

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector length / Saturating increment

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
UQINCW Wtied, ALL, MUL #imm_factor
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQINCW--scalar---Unsigned-saturating-increment-scalar-by-multiple-of-32-bit-predicate-constraint-element-count-

### Operation

Source operation ID: `SveOperation_svqincw_n_u32`

**Operation**



Return the result of the following procedure:




- Multiply the number of 32-bit elements in a full vector by `imm_factor`.
- Add this value to `op`, without loss of precision.
- Saturate the result to the range of `uint32_t`.

## svqincw[_n_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqincw%5B_n_u64%5D

### Signature (source notation)

```c
uint64_t svqincw[_n_u64](uint64_t op, uint64_t imm_factor);
```

### Description

Saturating increment by number of word elements

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector length / Saturating increment

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
UQINCW Xtied, ALL, MUL #imm_factor
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQINCW--scalar---Unsigned-saturating-increment-scalar-by-multiple-of-32-bit-predicate-constraint-element-count-

### Operation

Source operation ID: `SveOperation_svqincw_n_u64`

**Operation**



Return the result of the following procedure:




- Multiply the number of 32-bit elements in a full vector by `imm_factor`.
- Add this value to `op`, without loss of precision.
- Saturate the result to the range of `uint64_t`.

## svqincw[_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqincw%5B_s32%5D

### Signature (source notation)

```c
svint32_t svqincw[_s32](svint32_t op, uint64_t imm_factor);
```

### Description

Saturating increment by number of word elements

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector length / Saturating increment

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
SQINCW Ztied.S, ALL, MUL #imm_factor
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQINCW--vector---Signed-saturating-increment-vector-by-multiple-of-32-bit-predicate-constraint-element-count-

When result and op are in different registers, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SQINCW Zresult.S, ALL, MUL #imm_factor
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQINCW--vector---Signed-saturating-increment-vector-by-multiple-of-32-bit-predicate-constraint-element-count-

### Operation

Source operation ID: `SveOperation_svqincw_s32`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Multiply the number of 32-bit elements in a full vector by `imm_factor`.
- Add this value to `op[i]`, without loss of precision.
- Saturate the result to the range of `int32_t`.

## svqincw[_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqincw%5B_u32%5D

### Signature (source notation)

```c
svuint32_t svqincw[_u32](svuint32_t op, uint64_t imm_factor);
```

### Description

Saturating increment by number of word elements

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector length / Saturating increment

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
UQINCW Ztied.S, ALL, MUL #imm_factor
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQINCW--vector---Unsigned-saturating-increment-vector-by-multiple-of-32-bit-predicate-constraint-element-count-

When result and op are in different registers, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
UQINCW Zresult.S, ALL, MUL #imm_factor
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQINCW--vector---Unsigned-saturating-increment-vector-by-multiple-of-32-bit-predicate-constraint-element-count-

### Operation

Source operation ID: `SveOperation_svqincw_u32`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Multiply the number of 32-bit elements in a full vector by `imm_factor`.
- Add this value to `op[i]`, without loss of precision.
- Saturate the result to the range of `uint32_t`.

## svqincw_pat[_n_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqincw_pat%5B_n_s32%5D

### Signature (source notation)

```c
int32_t svqincw_pat[_n_s32](int32_t op, enum svpattern pattern, uint64_t imm_factor);
```

### Description

Saturating increment by number of word elements

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector length / Saturating increment

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
SQINCW Xtied, Wtied, pattern, MUL #imm_factor
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQINCW--scalar---Signed-saturating-increment-scalar-by-multiple-of-32-bit-predicate-constraint-element-count-

### Operation

Source operation ID: `SveOperation_svqincw_pat_n_s32`

**Operation**



Return the result of the following procedure:




- Multiply the number of 32-bit elements in vector pattern `pattern` by `imm_factor`.
- Add this value to `op`, without loss of precision.
- Saturate the result to the range of `int32_t`.

## svqincw_pat[_n_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqincw_pat%5B_n_s64%5D

### Signature (source notation)

```c
int64_t svqincw_pat[_n_s64](int64_t op, enum svpattern pattern, uint64_t imm_factor);
```

### Description

Saturating increment by number of word elements

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector length / Saturating increment

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
SQINCW Xtied, pattern, MUL #imm_factor
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQINCW--scalar---Signed-saturating-increment-scalar-by-multiple-of-32-bit-predicate-constraint-element-count-

### Operation

Source operation ID: `SveOperation_svqincw_pat_n_s64`

**Operation**



Return the result of the following procedure:




- Multiply the number of 32-bit elements in vector pattern `pattern` by `imm_factor`.
- Add this value to `op`, without loss of precision.
- Saturate the result to the range of `int64_t`.

## svqincw_pat[_n_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqincw_pat%5B_n_u32%5D

### Signature (source notation)

```c
uint32_t svqincw_pat[_n_u32](uint32_t op, enum svpattern pattern, uint64_t imm_factor);
```

### Description

Saturating increment by number of word elements

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector length / Saturating increment

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
UQINCW Wtied, pattern, MUL #imm_factor
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQINCW--scalar---Unsigned-saturating-increment-scalar-by-multiple-of-32-bit-predicate-constraint-element-count-

### Operation

Source operation ID: `SveOperation_svqincw_pat_n_u32`

**Operation**



Return the result of the following procedure:




- Multiply the number of 32-bit elements in vector pattern `pattern` by `imm_factor`.
- Add this value to `op`, without loss of precision.
- Saturate the result to the range of `uint32_t`.

## svqincw_pat[_n_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqincw_pat%5B_n_u64%5D

### Signature (source notation)

```c
uint64_t svqincw_pat[_n_u64](uint64_t op, enum svpattern pattern, uint64_t imm_factor);
```

### Description

Saturating increment by number of word elements

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector length / Saturating increment

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
UQINCW Xtied, pattern, MUL #imm_factor
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQINCW--scalar---Unsigned-saturating-increment-scalar-by-multiple-of-32-bit-predicate-constraint-element-count-

### Operation

Source operation ID: `SveOperation_svqincw_pat_n_u64`

**Operation**



Return the result of the following procedure:




- Multiply the number of 32-bit elements in vector pattern `pattern` by `imm_factor`.
- Add this value to `op`, without loss of precision.
- Saturate the result to the range of `uint64_t`.

## svqincw_pat[_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqincw_pat%5B_s32%5D

### Signature (source notation)

```c
svint32_t svqincw_pat[_s32](svint32_t op, enum svpattern pattern, uint64_t imm_factor);
```

### Description

Saturating increment by number of word elements

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector length / Saturating increment

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
SQINCW Ztied.S, pattern, MUL #imm_factor
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQINCW--vector---Signed-saturating-increment-vector-by-multiple-of-32-bit-predicate-constraint-element-count-

When result and op are in different registers, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SQINCW Zresult.S, pattern, MUL #imm_factor
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQINCW--vector---Signed-saturating-increment-vector-by-multiple-of-32-bit-predicate-constraint-element-count-

### Operation

Source operation ID: `SveOperation_svqincw_pat_s32`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Multiply the number of 32-bit elements in vector pattern `pattern` by `imm_factor`.
- Add this value to `op[i]`, without loss of precision.
- Saturate the result to the range of `int32_t`.

## svqincw_pat[_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqincw_pat%5B_u32%5D

### Signature (source notation)

```c
svuint32_t svqincw_pat[_u32](svuint32_t op, enum svpattern pattern, uint64_t imm_factor);
```

### Description

Saturating increment by number of word elements

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector length / Saturating increment

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
UQINCW Ztied.S, pattern, MUL #imm_factor
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQINCW--vector---Unsigned-saturating-increment-vector-by-multiple-of-32-bit-predicate-constraint-element-count-

When result and op are in different registers, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
UQINCW Zresult.S, pattern, MUL #imm_factor
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQINCW--vector---Unsigned-saturating-increment-vector-by-multiple-of-32-bit-predicate-constraint-element-count-

### Operation

Source operation ID: `SveOperation_svqincw_pat_u32`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Multiply the number of 32-bit elements in vector pattern `pattern` by `imm_factor`.
- Add this value to `op[i]`, without loss of precision.
- Saturate the result to the range of `uint32_t`.

