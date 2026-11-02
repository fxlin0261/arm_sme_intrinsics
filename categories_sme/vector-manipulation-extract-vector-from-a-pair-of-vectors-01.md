# SME / Vector manipulation / Extract vector from a pair of vectors — Part 1

## svext[_bf16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svext%5B_bf16%5D

### Signature (source notation)

```c
svbfloat16_t svext[_bf16](svbfloat16_t op1, svbfloat16_t op2, uint64_t imm3);
```

### Description

Extract vector from pair of vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Extract vector from a pair of vectors

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
  "return_base_type": "bfloat",
  "element_bit_size": "16",
  "value": "svbfloat16_t"
}
```

### Argument preparation and constraints

```json
{
  "op1": {
    "register": "Zop1.B|Ztied1.B"
  },
  "op2": {
    "register": "Zop2.B"
  },
  "imm3": {
    "minimum": 0,
    "maximum": 127
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.B|Ztied1.B": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
EXT Ztied1.B, Ztied1.B, Zop2.B, #imm3 * 2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/EXT--Extract-vector-from-pair-of-vectors-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
EXT Zresult.B, Zresult.B, Zop2.B, #imm3 * 2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/EXT--Extract-vector-from-pair-of-vectors-

### Operation

Source operation ID: `SveOperation_svext_bf16`

**Operation**



If `imm3` is less than the number of elements in `op1`, concatenate `op1` and `op2` and return the subvector at index `imm3` onwards. Return `op1` otherwise.

## svext[_f16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svext%5B_f16%5D

### Signature (source notation)

```c
svfloat16_t svext[_f16](svfloat16_t op1, svfloat16_t op2, uint64_t imm3);
```

### Description

Extract vector from pair of vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Extract vector from a pair of vectors

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
  "return_base_type": "float",
  "element_bit_size": "16",
  "value": "svfloat16_t"
}
```

### Argument preparation and constraints

```json
{
  "op1": {
    "register": "Zop1.B|Ztied1.B"
  },
  "op2": {
    "register": "Zop2.B"
  },
  "imm3": {
    "minimum": 0,
    "maximum": 127
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.B|Ztied1.B": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
EXT Ztied1.B, Ztied1.B, Zop2.B, #imm3 * 2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/EXT--Extract-vector-from-pair-of-vectors-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
EXT Zresult.B, Zresult.B, Zop2.B, #imm3 * 2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/EXT--Extract-vector-from-pair-of-vectors-

### Operation

Source operation ID: `SveOperation_svext_bf16`

**Operation**



If `imm3` is less than the number of elements in `op1`, concatenate `op1` and `op2` and return the subvector at index `imm3` onwards. Return `op1` otherwise.

## svext[_f32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svext%5B_f32%5D

### Signature (source notation)

```c
svfloat32_t svext[_f32](svfloat32_t op1, svfloat32_t op2, uint64_t imm3);
```

### Description

Extract vector from pair of vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Extract vector from a pair of vectors

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
  "return_base_type": "float",
  "element_bit_size": "32",
  "value": "svfloat32_t"
}
```

### Argument preparation and constraints

```json
{
  "op1": {
    "register": "Zop1.B|Ztied1.B"
  },
  "op2": {
    "register": "Zop2.B"
  },
  "imm3": {
    "minimum": 0,
    "maximum": 63
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.B|Ztied1.B": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
EXT Ztied1.B, Ztied1.B, Zop2.B, #imm3 * 4
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/EXT--Extract-vector-from-pair-of-vectors-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
EXT Zresult.B, Zresult.B, Zop2.B, #imm3 * 4
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/EXT--Extract-vector-from-pair-of-vectors-

### Operation

Source operation ID: `SveOperation_svext_bf16`

**Operation**



If `imm3` is less than the number of elements in `op1`, concatenate `op1` and `op2` and return the subvector at index `imm3` onwards. Return `op1` otherwise.

## svext[_f64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svext%5B_f64%5D

### Signature (source notation)

```c
svfloat64_t svext[_f64](svfloat64_t op1, svfloat64_t op2, uint64_t imm3);
```

### Description

Extract vector from pair of vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Extract vector from a pair of vectors

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
  "return_base_type": "float",
  "element_bit_size": "64",
  "value": "svfloat64_t"
}
```

### Argument preparation and constraints

```json
{
  "op1": {
    "register": "Zop1.B|Ztied1.B"
  },
  "op2": {
    "register": "Zop2.B"
  },
  "imm3": {
    "minimum": 0,
    "maximum": 31
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.B|Ztied1.B": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
EXT Ztied1.B, Ztied1.B, Zop2.B, #imm3 * 8
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/EXT--Extract-vector-from-pair-of-vectors-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
EXT Zresult.B, Zresult.B, Zop2.B, #imm3 * 8
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/EXT--Extract-vector-from-pair-of-vectors-

### Operation

Source operation ID: `SveOperation_svext_bf16`

**Operation**



If `imm3` is less than the number of elements in `op1`, concatenate `op1` and `op2` and return the subvector at index `imm3` onwards. Return `op1` otherwise.

## svext[_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svext%5B_s16%5D

### Signature (source notation)

```c
svint16_t svext[_s16](svint16_t op1, svint16_t op2, uint64_t imm3);
```

### Description

Extract vector from pair of vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Extract vector from a pair of vectors

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
  "op1": {
    "register": "Zop1.B|Ztied1.B"
  },
  "op2": {
    "register": "Zop2.B"
  },
  "imm3": {
    "minimum": 0,
    "maximum": 127
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.B|Ztied1.B": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
EXT Ztied1.B, Ztied1.B, Zop2.B, #imm3 * 2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/EXT--Extract-vector-from-pair-of-vectors-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
EXT Zresult.B, Zresult.B, Zop2.B, #imm3 * 2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/EXT--Extract-vector-from-pair-of-vectors-

### Operation

Source operation ID: `SveOperation_svext_bf16`

**Operation**



If `imm3` is less than the number of elements in `op1`, concatenate `op1` and `op2` and return the subvector at index `imm3` onwards. Return `op1` otherwise.

## svext[_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svext%5B_s32%5D

### Signature (source notation)

```c
svint32_t svext[_s32](svint32_t op1, svint32_t op2, uint64_t imm3);
```

### Description

Extract vector from pair of vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Extract vector from a pair of vectors

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
  "op1": {
    "register": "Zop1.B|Ztied1.B"
  },
  "op2": {
    "register": "Zop2.B"
  },
  "imm3": {
    "minimum": 0,
    "maximum": 63
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.B|Ztied1.B": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
EXT Ztied1.B, Ztied1.B, Zop2.B, #imm3 * 4
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/EXT--Extract-vector-from-pair-of-vectors-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
EXT Zresult.B, Zresult.B, Zop2.B, #imm3 * 4
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/EXT--Extract-vector-from-pair-of-vectors-

### Operation

Source operation ID: `SveOperation_svext_bf16`

**Operation**



If `imm3` is less than the number of elements in `op1`, concatenate `op1` and `op2` and return the subvector at index `imm3` onwards. Return `op1` otherwise.

## svext[_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svext%5B_s64%5D

### Signature (source notation)

```c
svint64_t svext[_s64](svint64_t op1, svint64_t op2, uint64_t imm3);
```

### Description

Extract vector from pair of vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Extract vector from a pair of vectors

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
  "op1": {
    "register": "Zop1.B|Ztied1.B"
  },
  "op2": {
    "register": "Zop2.B"
  },
  "imm3": {
    "minimum": 0,
    "maximum": 31
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.B|Ztied1.B": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
EXT Ztied1.B, Ztied1.B, Zop2.B, #imm3 * 8
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/EXT--Extract-vector-from-pair-of-vectors-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
EXT Zresult.B, Zresult.B, Zop2.B, #imm3 * 8
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/EXT--Extract-vector-from-pair-of-vectors-

### Operation

Source operation ID: `SveOperation_svext_bf16`

**Operation**



If `imm3` is less than the number of elements in `op1`, concatenate `op1` and `op2` and return the subvector at index `imm3` onwards. Return `op1` otherwise.

## svext[_s8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svext%5B_s8%5D

### Signature (source notation)

```c
svint8_t svext[_s8](svint8_t op1, svint8_t op2, uint64_t imm3);
```

### Description

Extract vector from pair of vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Extract vector from a pair of vectors

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
  "element_bit_size": "8",
  "value": "svint8_t"
}
```

### Argument preparation and constraints

```json
{
  "op1": {
    "register": "Zop1.B|Ztied1.B"
  },
  "op2": {
    "register": "Zop2.B"
  },
  "imm3": {
    "minimum": 0,
    "maximum": 255
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.B|Ztied1.B": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
EXT Ztied1.B, Ztied1.B, Zop2.B, #imm3
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/EXT--Extract-vector-from-pair-of-vectors-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
EXT Zresult.B, Zresult.B, Zop2.B, #imm3
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/EXT--Extract-vector-from-pair-of-vectors-

### Operation

Source operation ID: `SveOperation_svext_bf16`

**Operation**



If `imm3` is less than the number of elements in `op1`, concatenate `op1` and `op2` and return the subvector at index `imm3` onwards. Return `op1` otherwise.

## svext[_u16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svext%5B_u16%5D

### Signature (source notation)

```c
svuint16_t svext[_u16](svuint16_t op1, svuint16_t op2, uint64_t imm3);
```

### Description

Extract vector from pair of vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Extract vector from a pair of vectors

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
  "op1": {
    "register": "Zop1.B|Ztied1.B"
  },
  "op2": {
    "register": "Zop2.B"
  },
  "imm3": {
    "minimum": 0,
    "maximum": 127
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.B|Ztied1.B": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
EXT Ztied1.B, Ztied1.B, Zop2.B, #imm3 * 2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/EXT--Extract-vector-from-pair-of-vectors-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
EXT Zresult.B, Zresult.B, Zop2.B, #imm3 * 2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/EXT--Extract-vector-from-pair-of-vectors-

### Operation

Source operation ID: `SveOperation_svext_bf16`

**Operation**



If `imm3` is less than the number of elements in `op1`, concatenate `op1` and `op2` and return the subvector at index `imm3` onwards. Return `op1` otherwise.

## svext[_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svext%5B_u32%5D

### Signature (source notation)

```c
svuint32_t svext[_u32](svuint32_t op1, svuint32_t op2, uint64_t imm3);
```

### Description

Extract vector from pair of vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Extract vector from a pair of vectors

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
  "op1": {
    "register": "Zop1.B|Ztied1.B"
  },
  "op2": {
    "register": "Zop2.B"
  },
  "imm3": {
    "minimum": 0,
    "maximum": 63
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.B|Ztied1.B": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
EXT Ztied1.B, Ztied1.B, Zop2.B, #imm3 * 4
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/EXT--Extract-vector-from-pair-of-vectors-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
EXT Zresult.B, Zresult.B, Zop2.B, #imm3 * 4
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/EXT--Extract-vector-from-pair-of-vectors-

### Operation

Source operation ID: `SveOperation_svext_bf16`

**Operation**



If `imm3` is less than the number of elements in `op1`, concatenate `op1` and `op2` and return the subvector at index `imm3` onwards. Return `op1` otherwise.

## svext[_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svext%5B_u64%5D

### Signature (source notation)

```c
svuint64_t svext[_u64](svuint64_t op1, svuint64_t op2, uint64_t imm3);
```

### Description

Extract vector from pair of vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Extract vector from a pair of vectors

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
  "op1": {
    "register": "Zop1.B|Ztied1.B"
  },
  "op2": {
    "register": "Zop2.B"
  },
  "imm3": {
    "minimum": 0,
    "maximum": 31
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.B|Ztied1.B": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
EXT Ztied1.B, Ztied1.B, Zop2.B, #imm3 * 8
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/EXT--Extract-vector-from-pair-of-vectors-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
EXT Zresult.B, Zresult.B, Zop2.B, #imm3 * 8
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/EXT--Extract-vector-from-pair-of-vectors-

### Operation

Source operation ID: `SveOperation_svext_bf16`

**Operation**



If `imm3` is less than the number of elements in `op1`, concatenate `op1` and `op2` and return the subvector at index `imm3` onwards. Return `op1` otherwise.

## svext[_u8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svext%5B_u8%5D

### Signature (source notation)

```c
svuint8_t svext[_u8](svuint8_t op1, svuint8_t op2, uint64_t imm3);
```

### Description

Extract vector from pair of vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Extract vector from a pair of vectors

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
  "element_bit_size": "8",
  "value": "svuint8_t"
}
```

### Argument preparation and constraints

```json
{
  "op1": {
    "register": "Zop1.B|Ztied1.B"
  },
  "op2": {
    "register": "Zop2.B"
  },
  "imm3": {
    "minimum": 0,
    "maximum": 255
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.B|Ztied1.B": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
EXT Ztied1.B, Ztied1.B, Zop2.B, #imm3
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/EXT--Extract-vector-from-pair-of-vectors-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
EXT Zresult.B, Zresult.B, Zop2.B, #imm3
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/EXT--Extract-vector-from-pair-of-vectors-

### Operation

Source operation ID: `SveOperation_svext_bf16`

**Operation**



If `imm3` is less than the number of elements in `op1`, concatenate `op1` and `op2` and return the subvector at index `imm3` onwards. Return `op1` otherwise.

## svextq[_bf16]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svextq%5B_bf16%5D

### Signature (source notation)

```c
svbfloat16_t svextq[_bf16](svbfloat16_t zdn, svbfloat16_t zm, int32_t imm);
```

### Description

Extract vector segment from each pair of quadword vector segments

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector manipulation / Extract vector from a pair of vectors

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
  "return_base_type": "bfloat16",
  "element_bit_size": "16",
  "value": "svbfloat16_t"
}
```

### Argument preparation and constraints

```json
{
  "zdn": {
    "register": "Zreg1.B"
  },
  "zm": {
    "register": "Zreg2.B"
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
    "Zreg1.B": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
EXTQ Zreg1.B, Zreg1.B, Zreg2.B, #imm1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/EXTQ--Extract-vector-segment-from-each-pair-of-quadword-vector-segments-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svextq[_f16]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svextq%5B_f16%5D

### Signature (source notation)

```c
svfloat16_t svextq[_f16](svfloat16_t zdn, svfloat16_t zm, int32_t imm);
```

### Description

Extract vector segment from each pair of quadword vector segments

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector manipulation / Extract vector from a pair of vectors

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
  "return_base_type": "float16",
  "element_bit_size": "16",
  "value": "svfloat16_t"
}
```

### Argument preparation and constraints

```json
{
  "zdn": {
    "register": "Zreg1.B"
  },
  "zm": {
    "register": "Zreg2.B"
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
    "Zreg1.B": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
EXTQ Zreg1.B, Zreg1.B, Zreg2.B, #imm1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/EXTQ--Extract-vector-segment-from-each-pair-of-quadword-vector-segments-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svextq[_f32]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svextq%5B_f32%5D

### Signature (source notation)

```c
svfloat32_t svextq[_f32](svfloat32_t zdn, svfloat32_t zm, int32_t imm);
```

### Description

Extract vector segment from each pair of quadword vector segments

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector manipulation / Extract vector from a pair of vectors

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
  "return_base_type": "float32",
  "element_bit_size": "32",
  "value": "svfloat32_t"
}
```

### Argument preparation and constraints

```json
{
  "zdn": {
    "register": "Zreg1.B"
  },
  "zm": {
    "register": "Zreg2.B"
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
    "Zreg1.B": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
EXTQ Zreg1.B, Zreg1.B, Zreg2.B, #imm1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/EXTQ--Extract-vector-segment-from-each-pair-of-quadword-vector-segments-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svextq[_f64]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svextq%5B_f64%5D

### Signature (source notation)

```c
svfloat64_t svextq[_f64](svfloat64_t zdn, svfloat64_t zm, int32_t imm);
```

### Description

Extract vector segment from each pair of quadword vector segments

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector manipulation / Extract vector from a pair of vectors

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
  "return_base_type": "float64",
  "element_bit_size": "64",
  "value": "svfloat64_t"
}
```

### Argument preparation and constraints

```json
{
  "zdn": {
    "register": "Zreg1.B"
  },
  "zm": {
    "register": "Zreg2.B"
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
    "Zreg1.B": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
EXTQ Zreg1.B, Zreg1.B, Zreg2.B, #imm1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/EXTQ--Extract-vector-segment-from-each-pair-of-quadword-vector-segments-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svextq[_mf8]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svextq%5B_mf8%5D

### Signature (source notation)

```c
svmfloat8_t svextq[_mf8](svmfloat8_t zdn, svmfloat8_t zm, int32_t imm);
```

### Description

Extract vector segment from each pair of quadword vector segments

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector manipulation / Extract vector from a pair of vectors

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
  "return_base_type": "mfloat8",
  "element_bit_size": "8",
  "value": "svmfloat8_t"
}
```

### Argument preparation and constraints

```json
{
  "zdn": {
    "register": "Zreg1.B"
  },
  "zm": {
    "register": "Zreg2.B"
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
    "Zreg1.B": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
EXTQ Zreg1.B, Zreg1.B, Zreg2.B, #imm1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/EXTQ--Extract-vector-segment-from-each-pair-of-quadword-vector-segments-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svextq[_s16]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svextq%5B_s16%5D

### Signature (source notation)

```c
svint16_t svextq[_s16](svint16_t zdn, svint16_t zm, int32_t imm);
```

### Description

Extract vector segment from each pair of quadword vector segments

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector manipulation / Extract vector from a pair of vectors

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
  "zdn": {
    "register": "Zreg1.B"
  },
  "zm": {
    "register": "Zreg2.B"
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
    "Zreg1.B": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
EXTQ Zreg1.B, Zreg1.B, Zreg2.B, #imm1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/EXTQ--Extract-vector-segment-from-each-pair-of-quadword-vector-segments-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svextq[_s32]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svextq%5B_s32%5D

### Signature (source notation)

```c
svint32_t svextq[_s32](svint32_t zdn, svint32_t zm, int32_t imm);
```

### Description

Extract vector segment from each pair of quadword vector segments

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector manipulation / Extract vector from a pair of vectors

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
  "zdn": {
    "register": "Zreg1.B"
  },
  "zm": {
    "register": "Zreg2.B"
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
    "Zreg1.B": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
EXTQ Zreg1.B, Zreg1.B, Zreg2.B, #imm1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/EXTQ--Extract-vector-segment-from-each-pair-of-quadword-vector-segments-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svextq[_s64]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svextq%5B_s64%5D

### Signature (source notation)

```c
svint64_t svextq[_s64](svint64_t zdn, svint64_t zm, int32_t imm);
```

### Description

Extract vector segment from each pair of quadword vector segments

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector manipulation / Extract vector from a pair of vectors

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
  "zdn": {
    "register": "Zreg1.B"
  },
  "zm": {
    "register": "Zreg2.B"
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
    "Zreg1.B": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
EXTQ Zreg1.B, Zreg1.B, Zreg2.B, #imm1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/EXTQ--Extract-vector-segment-from-each-pair-of-quadword-vector-segments-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svextq[_s8]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svextq%5B_s8%5D

### Signature (source notation)

```c
svint8_t svextq[_s8](svint8_t zdn, svint8_t zm, int32_t imm);
```

### Description

Extract vector segment from each pair of quadword vector segments

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector manipulation / Extract vector from a pair of vectors

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
  "zdn": {
    "register": "Zreg1.B"
  },
  "zm": {
    "register": "Zreg2.B"
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
    "Zreg1.B": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
EXTQ Zreg1.B, Zreg1.B, Zreg2.B, #imm1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/EXTQ--Extract-vector-segment-from-each-pair-of-quadword-vector-segments-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svextq[_u16]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svextq%5B_u16%5D

### Signature (source notation)

```c
svuint16_t svextq[_u16](svuint16_t zdn, svuint16_t zm, int32_t imm);
```

### Description

Extract vector segment from each pair of quadword vector segments

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector manipulation / Extract vector from a pair of vectors

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
  "zdn": {
    "register": "Zreg1.B"
  },
  "zm": {
    "register": "Zreg2.B"
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
    "Zreg1.B": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
EXTQ Zreg1.B, Zreg1.B, Zreg2.B, #imm1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/EXTQ--Extract-vector-segment-from-each-pair-of-quadword-vector-segments-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svextq[_u32]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svextq%5B_u32%5D

### Signature (source notation)

```c
svuint32_t svextq[_u32](svuint32_t zdn, svuint32_t zm, int32_t imm);
```

### Description

Extract vector segment from each pair of quadword vector segments

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector manipulation / Extract vector from a pair of vectors

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
  "zdn": {
    "register": "Zreg1.B"
  },
  "zm": {
    "register": "Zreg2.B"
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
    "Zreg1.B": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
EXTQ Zreg1.B, Zreg1.B, Zreg2.B, #imm1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/EXTQ--Extract-vector-segment-from-each-pair-of-quadword-vector-segments-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svextq[_u64]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svextq%5B_u64%5D

### Signature (source notation)

```c
svuint64_t svextq[_u64](svuint64_t zdn, svuint64_t zm, int32_t imm);
```

### Description

Extract vector segment from each pair of quadword vector segments

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector manipulation / Extract vector from a pair of vectors

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
  "zdn": {
    "register": "Zreg1.B"
  },
  "zm": {
    "register": "Zreg2.B"
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
    "Zreg1.B": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
EXTQ Zreg1.B, Zreg1.B, Zreg2.B, #imm1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/EXTQ--Extract-vector-segment-from-each-pair-of-quadword-vector-segments-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svextq[_u8]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svextq%5B_u8%5D

### Signature (source notation)

```c
svuint8_t svextq[_u8](svuint8_t zdn, svuint8_t zm, int32_t imm);
```

### Description

Extract vector segment from each pair of quadword vector segments

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector manipulation / Extract vector from a pair of vectors

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
  "zdn": {
    "register": "Zreg1.B"
  },
  "zm": {
    "register": "Zreg2.B"
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
    "Zreg1.B": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
EXTQ Zreg1.B, Zreg1.B, Zreg2.B, #imm1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/EXTQ--Extract-vector-segment-from-each-pair-of-quadword-vector-segments-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svsplice[_bf16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsplice%5B_bf16%5D

### Signature (source notation)

```c
svbfloat16_t svsplice[_bf16](svbool_t pg, svbfloat16_t op1, svbfloat16_t op2);
```

### Description

Splice two vectors under predicate control

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Extract vector from a pair of vectors

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
  "return_base_type": "bfloat",
  "element_bit_size": "16",
  "value": "svbfloat16_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Pg"
  },
  "op1": {
    "register": "Zop1.H|Ztied1.H"
  },
  "op2": {
    "register": "Zop2.H"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.H|Ztied1.H": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
SPLICE Ztied1.H, Pg, Ztied1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SPLICE--Splice-two-vectors-under-predicate-control-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SPLICE Zresult.H, Pg, Zresult.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SPLICE--Splice-two-vectors-under-predicate-control-

### Operation

Source operation ID: `SveOperation_svsplice_bf16`

**Operation**




- If no elements are active, return `op2`.
- Otherwise, take the first active element onwards of `op1` and append elements from the start of `op2` onwards until there are enough elements to fill a vector.

## svsplice[_f16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsplice%5B_f16%5D

### Signature (source notation)

```c
svfloat16_t svsplice[_f16](svbool_t pg, svfloat16_t op1, svfloat16_t op2);
```

### Description

Splice two vectors under predicate control

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Extract vector from a pair of vectors

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
  "return_base_type": "float",
  "element_bit_size": "16",
  "value": "svfloat16_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Pg"
  },
  "op1": {
    "register": "Zop1.H|Ztied1.H"
  },
  "op2": {
    "register": "Zop2.H"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.H|Ztied1.H": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
SPLICE Ztied1.H, Pg, Ztied1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SPLICE--Splice-two-vectors-under-predicate-control-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SPLICE Zresult.H, Pg, Zresult.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SPLICE--Splice-two-vectors-under-predicate-control-

### Operation

Source operation ID: `SveOperation_svsplice_bf16`

**Operation**




- If no elements are active, return `op2`.
- Otherwise, take the first active element onwards of `op1` and append elements from the start of `op2` onwards until there are enough elements to fill a vector.

## svsplice[_f32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsplice%5B_f32%5D

### Signature (source notation)

```c
svfloat32_t svsplice[_f32](svbool_t pg, svfloat32_t op1, svfloat32_t op2);
```

### Description

Splice two vectors under predicate control

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Extract vector from a pair of vectors

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
  "return_base_type": "float",
  "element_bit_size": "32",
  "value": "svfloat32_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Pg"
  },
  "op1": {
    "register": "Zop1.S|Ztied1.S"
  },
  "op2": {
    "register": "Zop2.S"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.S|Ztied1.S": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
SPLICE Ztied1.S, Pg, Ztied1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SPLICE--Splice-two-vectors-under-predicate-control-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SPLICE Zresult.S, Pg, Zresult.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SPLICE--Splice-two-vectors-under-predicate-control-

### Operation

Source operation ID: `SveOperation_svsplice_bf16`

**Operation**




- If no elements are active, return `op2`.
- Otherwise, take the first active element onwards of `op1` and append elements from the start of `op2` onwards until there are enough elements to fill a vector.

## svsplice[_f64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsplice%5B_f64%5D

### Signature (source notation)

```c
svfloat64_t svsplice[_f64](svbool_t pg, svfloat64_t op1, svfloat64_t op2);
```

### Description

Splice two vectors under predicate control

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Extract vector from a pair of vectors

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
  "return_base_type": "float",
  "element_bit_size": "64",
  "value": "svfloat64_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Pg"
  },
  "op1": {
    "register": "Zop1.D|Ztied1.D"
  },
  "op2": {
    "register": "Zop2.D"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.D|Ztied1.D": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
SPLICE Ztied1.D, Pg, Ztied1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SPLICE--Splice-two-vectors-under-predicate-control-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SPLICE Zresult.D, Pg, Zresult.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SPLICE--Splice-two-vectors-under-predicate-control-

### Operation

Source operation ID: `SveOperation_svsplice_bf16`

**Operation**




- If no elements are active, return `op2`.
- Otherwise, take the first active element onwards of `op1` and append elements from the start of `op2` onwards until there are enough elements to fill a vector.

## svsplice[_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsplice%5B_s16%5D

### Signature (source notation)

```c
svint16_t svsplice[_s16](svbool_t pg, svint16_t op1, svint16_t op2);
```

### Description

Splice two vectors under predicate control

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Extract vector from a pair of vectors

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
  "pg": {
    "register": "Pg"
  },
  "op1": {
    "register": "Zop1.H|Ztied1.H"
  },
  "op2": {
    "register": "Zop2.H"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.H|Ztied1.H": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
SPLICE Ztied1.H, Pg, Ztied1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SPLICE--Splice-two-vectors-under-predicate-control-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SPLICE Zresult.H, Pg, Zresult.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SPLICE--Splice-two-vectors-under-predicate-control-

### Operation

Source operation ID: `SveOperation_svsplice_bf16`

**Operation**




- If no elements are active, return `op2`.
- Otherwise, take the first active element onwards of `op1` and append elements from the start of `op2` onwards until there are enough elements to fill a vector.

## svsplice[_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsplice%5B_s32%5D

### Signature (source notation)

```c
svint32_t svsplice[_s32](svbool_t pg, svint32_t op1, svint32_t op2);
```

### Description

Splice two vectors under predicate control

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Extract vector from a pair of vectors

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
  "pg": {
    "register": "Pg"
  },
  "op1": {
    "register": "Zop1.S|Ztied1.S"
  },
  "op2": {
    "register": "Zop2.S"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.S|Ztied1.S": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
SPLICE Ztied1.S, Pg, Ztied1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SPLICE--Splice-two-vectors-under-predicate-control-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SPLICE Zresult.S, Pg, Zresult.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SPLICE--Splice-two-vectors-under-predicate-control-

### Operation

Source operation ID: `SveOperation_svsplice_bf16`

**Operation**




- If no elements are active, return `op2`.
- Otherwise, take the first active element onwards of `op1` and append elements from the start of `op2` onwards until there are enough elements to fill a vector.

## svsplice[_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsplice%5B_s64%5D

### Signature (source notation)

```c
svint64_t svsplice[_s64](svbool_t pg, svint64_t op1, svint64_t op2);
```

### Description

Splice two vectors under predicate control

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Extract vector from a pair of vectors

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
  "pg": {
    "register": "Pg"
  },
  "op1": {
    "register": "Zop1.D|Ztied1.D"
  },
  "op2": {
    "register": "Zop2.D"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.D|Ztied1.D": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
SPLICE Ztied1.D, Pg, Ztied1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SPLICE--Splice-two-vectors-under-predicate-control-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SPLICE Zresult.D, Pg, Zresult.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SPLICE--Splice-two-vectors-under-predicate-control-

### Operation

Source operation ID: `SveOperation_svsplice_bf16`

**Operation**




- If no elements are active, return `op2`.
- Otherwise, take the first active element onwards of `op1` and append elements from the start of `op2` onwards until there are enough elements to fill a vector.

## svsplice[_s8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsplice%5B_s8%5D

### Signature (source notation)

```c
svint8_t svsplice[_s8](svbool_t pg, svint8_t op1, svint8_t op2);
```

### Description

Splice two vectors under predicate control

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Extract vector from a pair of vectors

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
  "element_bit_size": "8",
  "value": "svint8_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Pg"
  },
  "op1": {
    "register": "Zop1.B|Ztied1.B"
  },
  "op2": {
    "register": "Zop2.B"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.B|Ztied1.B": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
SPLICE Ztied1.B, Pg, Ztied1.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SPLICE--Splice-two-vectors-under-predicate-control-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SPLICE Zresult.B, Pg, Zresult.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SPLICE--Splice-two-vectors-under-predicate-control-

### Operation

Source operation ID: `SveOperation_svsplice_bf16`

**Operation**




- If no elements are active, return `op2`.
- Otherwise, take the first active element onwards of `op1` and append elements from the start of `op2` onwards until there are enough elements to fill a vector.

## svsplice[_u16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsplice%5B_u16%5D

### Signature (source notation)

```c
svuint16_t svsplice[_u16](svbool_t pg, svuint16_t op1, svuint16_t op2);
```

### Description

Splice two vectors under predicate control

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Extract vector from a pair of vectors

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
  "pg": {
    "register": "Pg"
  },
  "op1": {
    "register": "Zop1.H|Ztied1.H"
  },
  "op2": {
    "register": "Zop2.H"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.H|Ztied1.H": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
SPLICE Ztied1.H, Pg, Ztied1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SPLICE--Splice-two-vectors-under-predicate-control-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SPLICE Zresult.H, Pg, Zresult.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SPLICE--Splice-two-vectors-under-predicate-control-

### Operation

Source operation ID: `SveOperation_svsplice_bf16`

**Operation**




- If no elements are active, return `op2`.
- Otherwise, take the first active element onwards of `op1` and append elements from the start of `op2` onwards until there are enough elements to fill a vector.

## svsplice[_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsplice%5B_u32%5D

### Signature (source notation)

```c
svuint32_t svsplice[_u32](svbool_t pg, svuint32_t op1, svuint32_t op2);
```

### Description

Splice two vectors under predicate control

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Extract vector from a pair of vectors

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
  "pg": {
    "register": "Pg"
  },
  "op1": {
    "register": "Zop1.S|Ztied1.S"
  },
  "op2": {
    "register": "Zop2.S"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.S|Ztied1.S": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
SPLICE Ztied1.S, Pg, Ztied1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SPLICE--Splice-two-vectors-under-predicate-control-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SPLICE Zresult.S, Pg, Zresult.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SPLICE--Splice-two-vectors-under-predicate-control-

### Operation

Source operation ID: `SveOperation_svsplice_bf16`

**Operation**




- If no elements are active, return `op2`.
- Otherwise, take the first active element onwards of `op1` and append elements from the start of `op2` onwards until there are enough elements to fill a vector.

## svsplice[_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsplice%5B_u64%5D

### Signature (source notation)

```c
svuint64_t svsplice[_u64](svbool_t pg, svuint64_t op1, svuint64_t op2);
```

### Description

Splice two vectors under predicate control

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Extract vector from a pair of vectors

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
  "pg": {
    "register": "Pg"
  },
  "op1": {
    "register": "Zop1.D|Ztied1.D"
  },
  "op2": {
    "register": "Zop2.D"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.D|Ztied1.D": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
SPLICE Ztied1.D, Pg, Ztied1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SPLICE--Splice-two-vectors-under-predicate-control-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SPLICE Zresult.D, Pg, Zresult.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SPLICE--Splice-two-vectors-under-predicate-control-

### Operation

Source operation ID: `SveOperation_svsplice_bf16`

**Operation**




- If no elements are active, return `op2`.
- Otherwise, take the first active element onwards of `op1` and append elements from the start of `op2` onwards until there are enough elements to fill a vector.

## svsplice[_u8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsplice%5B_u8%5D

### Signature (source notation)

```c
svuint8_t svsplice[_u8](svbool_t pg, svuint8_t op1, svuint8_t op2);
```

### Description

Splice two vectors under predicate control

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Extract vector from a pair of vectors

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
  "element_bit_size": "8",
  "value": "svuint8_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Pg"
  },
  "op1": {
    "register": "Zop1.B|Ztied1.B"
  },
  "op2": {
    "register": "Zop2.B"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.B|Ztied1.B": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
SPLICE Ztied1.B, Pg, Ztied1.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SPLICE--Splice-two-vectors-under-predicate-control-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SPLICE Zresult.B, Pg, Zresult.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SPLICE--Splice-two-vectors-under-predicate-control-

### Operation

Source operation ID: `SveOperation_svsplice_bf16`

**Operation**




- If no elements are active, return `op2`.
- Otherwise, take the first active element onwards of `op1` and append elements from the start of `op2` onwards until there are enough elements to fill a vector.

