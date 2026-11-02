# SME / Vector tuple manipulation / Extract vector from tuple — Part 1

## svget2[_b]

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svget2%5B_b%5D

### Signature (source notation)

```c
svbool_t svget2[_b](svboolx2_t tuple, uint64_t imm_index);
```

### Description

Extract one predicate vector from a tuple of two predicate vectors. This intrinsic does not emit an instruction.

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector tuple manipulation / Extract vector from tuple

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
  "value": "svbool_t"
}
```

### Argument preparation and constraints

Not supplied by source.

### Result mapping

Not supplied by source.

### Instruction mapping

Not supplied by source.

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svget2[_bf16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svget2%5B_bf16%5D

### Signature (source notation)

```c
svbfloat16_t svget2[_bf16](svbfloat16x2_t tuple, uint64_t imm_index);
```

### Description

Extract one vector from a tuple of two vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Extract vector from tuple

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

Not supplied by source.

### Result mapping

Not supplied by source.

### Instruction mapping

Not supplied by source.

### Operation

Source operation ID: `SveOperation_svget2_bf16`

**Operation**



Return vector `imm_index` of `tuple`. `imm_index` must be an integer constant expression in the range [0, 1].

## svget2[_f16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svget2%5B_f16%5D

### Signature (source notation)

```c
svfloat16_t svget2[_f16](svfloat16x2_t tuple, uint64_t imm_index);
```

### Description

Extract one vector from a tuple of two vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Extract vector from tuple

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

Not supplied by source.

### Result mapping

Not supplied by source.

### Instruction mapping

Not supplied by source.

### Operation

Source operation ID: `SveOperation_svget2_bf16`

**Operation**



Return vector `imm_index` of `tuple`. `imm_index` must be an integer constant expression in the range [0, 1].

## svget2[_f32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svget2%5B_f32%5D

### Signature (source notation)

```c
svfloat32_t svget2[_f32](svfloat32x2_t tuple, uint64_t imm_index);
```

### Description

Extract one vector from a tuple of two vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Extract vector from tuple

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

Not supplied by source.

### Result mapping

Not supplied by source.

### Instruction mapping

Not supplied by source.

### Operation

Source operation ID: `SveOperation_svget2_bf16`

**Operation**



Return vector `imm_index` of `tuple`. `imm_index` must be an integer constant expression in the range [0, 1].

## svget2[_f64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svget2%5B_f64%5D

### Signature (source notation)

```c
svfloat64_t svget2[_f64](svfloat64x2_t tuple, uint64_t imm_index);
```

### Description

Extract one vector from a tuple of two vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Extract vector from tuple

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

Not supplied by source.

### Result mapping

Not supplied by source.

### Instruction mapping

Not supplied by source.

### Operation

Source operation ID: `SveOperation_svget2_bf16`

**Operation**



Return vector `imm_index` of `tuple`. `imm_index` must be an integer constant expression in the range [0, 1].

## svget2[_mf8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svget2%5B_mf8%5D

### Signature (source notation)

```c
svmfloat8_t svget2[_mf8](svmfloat8x2_t tuple, uint64_t imm_index);
```

### Description

Extract one vector from a tuple of two vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Extract vector from tuple

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
  "return_base_type": "mfloat8",
  "element_bit_size": "8",
  "value": "svmfloat8_t"
}
```

### Argument preparation and constraints

Not supplied by source.

### Result mapping

Not supplied by source.

### Instruction mapping

Not supplied by source.

### Operation

Source operation ID: `SveOperation_svget2_bf16`

**Operation**



Return vector `imm_index` of `tuple`. `imm_index` must be an integer constant expression in the range [0, 1].

## svget2[_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svget2%5B_s16%5D

### Signature (source notation)

```c
svint16_t svget2[_s16](svint16x2_t tuple, uint64_t imm_index);
```

### Description

Extract one vector from a tuple of two vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Extract vector from tuple

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

Not supplied by source.

### Result mapping

Not supplied by source.

### Instruction mapping

Not supplied by source.

### Operation

Source operation ID: `SveOperation_svget2_bf16`

**Operation**



Return vector `imm_index` of `tuple`. `imm_index` must be an integer constant expression in the range [0, 1].

## svget2[_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svget2%5B_s32%5D

### Signature (source notation)

```c
svint32_t svget2[_s32](svint32x2_t tuple, uint64_t imm_index);
```

### Description

Extract one vector from a tuple of two vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Extract vector from tuple

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

Not supplied by source.

### Result mapping

Not supplied by source.

### Instruction mapping

Not supplied by source.

### Operation

Source operation ID: `SveOperation_svget2_bf16`

**Operation**



Return vector `imm_index` of `tuple`. `imm_index` must be an integer constant expression in the range [0, 1].

## svget2[_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svget2%5B_s64%5D

### Signature (source notation)

```c
svint64_t svget2[_s64](svint64x2_t tuple, uint64_t imm_index);
```

### Description

Extract one vector from a tuple of two vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Extract vector from tuple

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

Not supplied by source.

### Result mapping

Not supplied by source.

### Instruction mapping

Not supplied by source.

### Operation

Source operation ID: `SveOperation_svget2_bf16`

**Operation**



Return vector `imm_index` of `tuple`. `imm_index` must be an integer constant expression in the range [0, 1].

## svget2[_s8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svget2%5B_s8%5D

### Signature (source notation)

```c
svint8_t svget2[_s8](svint8x2_t tuple, uint64_t imm_index);
```

### Description

Extract one vector from a tuple of two vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Extract vector from tuple

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

Not supplied by source.

### Result mapping

Not supplied by source.

### Instruction mapping

Not supplied by source.

### Operation

Source operation ID: `SveOperation_svget2_bf16`

**Operation**



Return vector `imm_index` of `tuple`. `imm_index` must be an integer constant expression in the range [0, 1].

## svget2[_u16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svget2%5B_u16%5D

### Signature (source notation)

```c
svuint16_t svget2[_u16](svuint16x2_t tuple, uint64_t imm_index);
```

### Description

Extract one vector from a tuple of two vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Extract vector from tuple

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

Not supplied by source.

### Result mapping

Not supplied by source.

### Instruction mapping

Not supplied by source.

### Operation

Source operation ID: `SveOperation_svget2_bf16`

**Operation**



Return vector `imm_index` of `tuple`. `imm_index` must be an integer constant expression in the range [0, 1].

## svget2[_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svget2%5B_u32%5D

### Signature (source notation)

```c
svuint32_t svget2[_u32](svuint32x2_t tuple, uint64_t imm_index);
```

### Description

Extract one vector from a tuple of two vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Extract vector from tuple

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

Not supplied by source.

### Result mapping

Not supplied by source.

### Instruction mapping

Not supplied by source.

### Operation

Source operation ID: `SveOperation_svget2_bf16`

**Operation**



Return vector `imm_index` of `tuple`. `imm_index` must be an integer constant expression in the range [0, 1].

## svget2[_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svget2%5B_u64%5D

### Signature (source notation)

```c
svuint64_t svget2[_u64](svuint64x2_t tuple, uint64_t imm_index);
```

### Description

Extract one vector from a tuple of two vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Extract vector from tuple

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

Not supplied by source.

### Result mapping

Not supplied by source.

### Instruction mapping

Not supplied by source.

### Operation

Source operation ID: `SveOperation_svget2_bf16`

**Operation**



Return vector `imm_index` of `tuple`. `imm_index` must be an integer constant expression in the range [0, 1].

## svget2[_u8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svget2%5B_u8%5D

### Signature (source notation)

```c
svuint8_t svget2[_u8](svuint8x2_t tuple, uint64_t imm_index);
```

### Description

Extract one vector from a tuple of two vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Extract vector from tuple

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

Not supplied by source.

### Result mapping

Not supplied by source.

### Instruction mapping

Not supplied by source.

### Operation

Source operation ID: `SveOperation_svget2_bf16`

**Operation**



Return vector `imm_index` of `tuple`. `imm_index` must be an integer constant expression in the range [0, 1].

## svget3[_bf16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svget3%5B_bf16%5D

### Signature (source notation)

```c
svbfloat16_t svget3[_bf16](svbfloat16x3_t tuple, uint64_t imm_index);
```

### Description

Extract one vector from a tuple of three vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Extract vector from tuple

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

Not supplied by source.

### Result mapping

Not supplied by source.

### Instruction mapping

Not supplied by source.

### Operation

Source operation ID: `SveOperation_svget3_bf16`

**Operation**



Return vector `imm_index` of `tuple`. `imm_index` must be an integer constant expression in the range [0, 2].

## svget3[_f16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svget3%5B_f16%5D

### Signature (source notation)

```c
svfloat16_t svget3[_f16](svfloat16x3_t tuple, uint64_t imm_index);
```

### Description

Extract one vector from a tuple of three vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Extract vector from tuple

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

Not supplied by source.

### Result mapping

Not supplied by source.

### Instruction mapping

Not supplied by source.

### Operation

Source operation ID: `SveOperation_svget3_bf16`

**Operation**



Return vector `imm_index` of `tuple`. `imm_index` must be an integer constant expression in the range [0, 2].

## svget3[_f32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svget3%5B_f32%5D

### Signature (source notation)

```c
svfloat32_t svget3[_f32](svfloat32x3_t tuple, uint64_t imm_index);
```

### Description

Extract one vector from a tuple of three vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Extract vector from tuple

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

Not supplied by source.

### Result mapping

Not supplied by source.

### Instruction mapping

Not supplied by source.

### Operation

Source operation ID: `SveOperation_svget3_bf16`

**Operation**



Return vector `imm_index` of `tuple`. `imm_index` must be an integer constant expression in the range [0, 2].

## svget3[_f64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svget3%5B_f64%5D

### Signature (source notation)

```c
svfloat64_t svget3[_f64](svfloat64x3_t tuple, uint64_t imm_index);
```

### Description

Extract one vector from a tuple of three vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Extract vector from tuple

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

Not supplied by source.

### Result mapping

Not supplied by source.

### Instruction mapping

Not supplied by source.

### Operation

Source operation ID: `SveOperation_svget3_bf16`

**Operation**



Return vector `imm_index` of `tuple`. `imm_index` must be an integer constant expression in the range [0, 2].

## svget3[_mf8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svget3%5B_mf8%5D

### Signature (source notation)

```c
svmfloat8_t svget3[_mf8](svmfloat8x3_t tuple, uint64_t imm_index);
```

### Description

Extract one vector from a tuple of three vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Extract vector from tuple

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
  "return_base_type": "mfloat8",
  "element_bit_size": "8",
  "value": "svmfloat8_t"
}
```

### Argument preparation and constraints

Not supplied by source.

### Result mapping

Not supplied by source.

### Instruction mapping

Not supplied by source.

### Operation

Source operation ID: `SveOperation_svget3_bf16`

**Operation**



Return vector `imm_index` of `tuple`. `imm_index` must be an integer constant expression in the range [0, 2].

## svget3[_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svget3%5B_s16%5D

### Signature (source notation)

```c
svint16_t svget3[_s16](svint16x3_t tuple, uint64_t imm_index);
```

### Description

Extract one vector from a tuple of three vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Extract vector from tuple

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

Not supplied by source.

### Result mapping

Not supplied by source.

### Instruction mapping

Not supplied by source.

### Operation

Source operation ID: `SveOperation_svget3_bf16`

**Operation**



Return vector `imm_index` of `tuple`. `imm_index` must be an integer constant expression in the range [0, 2].

## svget3[_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svget3%5B_s32%5D

### Signature (source notation)

```c
svint32_t svget3[_s32](svint32x3_t tuple, uint64_t imm_index);
```

### Description

Extract one vector from a tuple of three vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Extract vector from tuple

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

Not supplied by source.

### Result mapping

Not supplied by source.

### Instruction mapping

Not supplied by source.

### Operation

Source operation ID: `SveOperation_svget3_bf16`

**Operation**



Return vector `imm_index` of `tuple`. `imm_index` must be an integer constant expression in the range [0, 2].

## svget3[_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svget3%5B_s64%5D

### Signature (source notation)

```c
svint64_t svget3[_s64](svint64x3_t tuple, uint64_t imm_index);
```

### Description

Extract one vector from a tuple of three vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Extract vector from tuple

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

Not supplied by source.

### Result mapping

Not supplied by source.

### Instruction mapping

Not supplied by source.

### Operation

Source operation ID: `SveOperation_svget3_bf16`

**Operation**



Return vector `imm_index` of `tuple`. `imm_index` must be an integer constant expression in the range [0, 2].

## svget3[_s8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svget3%5B_s8%5D

### Signature (source notation)

```c
svint8_t svget3[_s8](svint8x3_t tuple, uint64_t imm_index);
```

### Description

Extract one vector from a tuple of three vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Extract vector from tuple

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

Not supplied by source.

### Result mapping

Not supplied by source.

### Instruction mapping

Not supplied by source.

### Operation

Source operation ID: `SveOperation_svget3_bf16`

**Operation**



Return vector `imm_index` of `tuple`. `imm_index` must be an integer constant expression in the range [0, 2].

## svget3[_u16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svget3%5B_u16%5D

### Signature (source notation)

```c
svuint16_t svget3[_u16](svuint16x3_t tuple, uint64_t imm_index);
```

### Description

Extract one vector from a tuple of three vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Extract vector from tuple

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

Not supplied by source.

### Result mapping

Not supplied by source.

### Instruction mapping

Not supplied by source.

### Operation

Source operation ID: `SveOperation_svget3_bf16`

**Operation**



Return vector `imm_index` of `tuple`. `imm_index` must be an integer constant expression in the range [0, 2].

## svget3[_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svget3%5B_u32%5D

### Signature (source notation)

```c
svuint32_t svget3[_u32](svuint32x3_t tuple, uint64_t imm_index);
```

### Description

Extract one vector from a tuple of three vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Extract vector from tuple

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

Not supplied by source.

### Result mapping

Not supplied by source.

### Instruction mapping

Not supplied by source.

### Operation

Source operation ID: `SveOperation_svget3_bf16`

**Operation**



Return vector `imm_index` of `tuple`. `imm_index` must be an integer constant expression in the range [0, 2].

## svget3[_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svget3%5B_u64%5D

### Signature (source notation)

```c
svuint64_t svget3[_u64](svuint64x3_t tuple, uint64_t imm_index);
```

### Description

Extract one vector from a tuple of three vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Extract vector from tuple

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

Not supplied by source.

### Result mapping

Not supplied by source.

### Instruction mapping

Not supplied by source.

### Operation

Source operation ID: `SveOperation_svget3_bf16`

**Operation**



Return vector `imm_index` of `tuple`. `imm_index` must be an integer constant expression in the range [0, 2].

## svget3[_u8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svget3%5B_u8%5D

### Signature (source notation)

```c
svuint8_t svget3[_u8](svuint8x3_t tuple, uint64_t imm_index);
```

### Description

Extract one vector from a tuple of three vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Extract vector from tuple

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

Not supplied by source.

### Result mapping

Not supplied by source.

### Instruction mapping

Not supplied by source.

### Operation

Source operation ID: `SveOperation_svget3_bf16`

**Operation**



Return vector `imm_index` of `tuple`. `imm_index` must be an integer constant expression in the range [0, 2].

## svget4[_b]

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svget4%5B_b%5D

### Signature (source notation)

```c
svbool_t svget4[_b](svboolx4_t tuple, uint64_t imm_index);
```

### Description

Extract one predicate vector from a tuple of four predicate vectors. This intrinsic does not emit an instruction.

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector tuple manipulation / Extract vector from tuple

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
  "value": "svbool_t"
}
```

### Argument preparation and constraints

Not supplied by source.

### Result mapping

Not supplied by source.

### Instruction mapping

Not supplied by source.

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svget4[_bf16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svget4%5B_bf16%5D

### Signature (source notation)

```c
svbfloat16_t svget4[_bf16](svbfloat16x4_t tuple, uint64_t imm_index);
```

### Description

Extract one vector from a tuple of four vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Extract vector from tuple

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

Not supplied by source.

### Result mapping

Not supplied by source.

### Instruction mapping

Not supplied by source.

### Operation

Source operation ID: `SveOperation_svget4_bf16`

**Operation**



Return vector `imm_index` of `tuple`. `imm_index` must be an integer constant expression in the range [0, 3].

## svget4[_f16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svget4%5B_f16%5D

### Signature (source notation)

```c
svfloat16_t svget4[_f16](svfloat16x4_t tuple, uint64_t imm_index);
```

### Description

Extract one vector from a tuple of four vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Extract vector from tuple

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

Not supplied by source.

### Result mapping

Not supplied by source.

### Instruction mapping

Not supplied by source.

### Operation

Source operation ID: `SveOperation_svget4_bf16`

**Operation**



Return vector `imm_index` of `tuple`. `imm_index` must be an integer constant expression in the range [0, 3].

## svget4[_f32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svget4%5B_f32%5D

### Signature (source notation)

```c
svfloat32_t svget4[_f32](svfloat32x4_t tuple, uint64_t imm_index);
```

### Description

Extract one vector from a tuple of four vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Extract vector from tuple

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

Not supplied by source.

### Result mapping

Not supplied by source.

### Instruction mapping

Not supplied by source.

### Operation

Source operation ID: `SveOperation_svget4_bf16`

**Operation**



Return vector `imm_index` of `tuple`. `imm_index` must be an integer constant expression in the range [0, 3].

## svget4[_f64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svget4%5B_f64%5D

### Signature (source notation)

```c
svfloat64_t svget4[_f64](svfloat64x4_t tuple, uint64_t imm_index);
```

### Description

Extract one vector from a tuple of four vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Extract vector from tuple

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

Not supplied by source.

### Result mapping

Not supplied by source.

### Instruction mapping

Not supplied by source.

### Operation

Source operation ID: `SveOperation_svget4_bf16`

**Operation**



Return vector `imm_index` of `tuple`. `imm_index` must be an integer constant expression in the range [0, 3].

## svget4[_mf8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svget4%5B_mf8%5D

### Signature (source notation)

```c
svmfloat8_t svget4[_mf8](svmfloat8x4_t tuple, uint64_t imm_index);
```

### Description

Extract one vector from a tuple of four vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Extract vector from tuple

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
  "return_base_type": "mfloat8",
  "element_bit_size": "8",
  "value": "svmfloat8_t"
}
```

### Argument preparation and constraints

Not supplied by source.

### Result mapping

Not supplied by source.

### Instruction mapping

Not supplied by source.

### Operation

Source operation ID: `SveOperation_svget4_bf16`

**Operation**



Return vector `imm_index` of `tuple`. `imm_index` must be an integer constant expression in the range [0, 3].

## svget4[_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svget4%5B_s16%5D

### Signature (source notation)

```c
svint16_t svget4[_s16](svint16x4_t tuple, uint64_t imm_index);
```

### Description

Extract one vector from a tuple of four vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Extract vector from tuple

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

Not supplied by source.

### Result mapping

Not supplied by source.

### Instruction mapping

Not supplied by source.

### Operation

Source operation ID: `SveOperation_svget4_bf16`

**Operation**



Return vector `imm_index` of `tuple`. `imm_index` must be an integer constant expression in the range [0, 3].

## svget4[_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svget4%5B_s32%5D

### Signature (source notation)

```c
svint32_t svget4[_s32](svint32x4_t tuple, uint64_t imm_index);
```

### Description

Extract one vector from a tuple of four vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Extract vector from tuple

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

Not supplied by source.

### Result mapping

Not supplied by source.

### Instruction mapping

Not supplied by source.

### Operation

Source operation ID: `SveOperation_svget4_bf16`

**Operation**



Return vector `imm_index` of `tuple`. `imm_index` must be an integer constant expression in the range [0, 3].

## svget4[_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svget4%5B_s64%5D

### Signature (source notation)

```c
svint64_t svget4[_s64](svint64x4_t tuple, uint64_t imm_index);
```

### Description

Extract one vector from a tuple of four vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Extract vector from tuple

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

Not supplied by source.

### Result mapping

Not supplied by source.

### Instruction mapping

Not supplied by source.

### Operation

Source operation ID: `SveOperation_svget4_bf16`

**Operation**



Return vector `imm_index` of `tuple`. `imm_index` must be an integer constant expression in the range [0, 3].

## svget4[_s8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svget4%5B_s8%5D

### Signature (source notation)

```c
svint8_t svget4[_s8](svint8x4_t tuple, uint64_t imm_index);
```

### Description

Extract one vector from a tuple of four vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Extract vector from tuple

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

Not supplied by source.

### Result mapping

Not supplied by source.

### Instruction mapping

Not supplied by source.

### Operation

Source operation ID: `SveOperation_svget4_bf16`

**Operation**



Return vector `imm_index` of `tuple`. `imm_index` must be an integer constant expression in the range [0, 3].

## svget4[_u16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svget4%5B_u16%5D

### Signature (source notation)

```c
svuint16_t svget4[_u16](svuint16x4_t tuple, uint64_t imm_index);
```

### Description

Extract one vector from a tuple of four vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Extract vector from tuple

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

Not supplied by source.

### Result mapping

Not supplied by source.

### Instruction mapping

Not supplied by source.

### Operation

Source operation ID: `SveOperation_svget4_bf16`

**Operation**



Return vector `imm_index` of `tuple`. `imm_index` must be an integer constant expression in the range [0, 3].

## svget4[_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svget4%5B_u32%5D

### Signature (source notation)

```c
svuint32_t svget4[_u32](svuint32x4_t tuple, uint64_t imm_index);
```

### Description

Extract one vector from a tuple of four vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Extract vector from tuple

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

Not supplied by source.

### Result mapping

Not supplied by source.

### Instruction mapping

Not supplied by source.

### Operation

Source operation ID: `SveOperation_svget4_bf16`

**Operation**



Return vector `imm_index` of `tuple`. `imm_index` must be an integer constant expression in the range [0, 3].

## svget4[_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svget4%5B_u64%5D

### Signature (source notation)

```c
svuint64_t svget4[_u64](svuint64x4_t tuple, uint64_t imm_index);
```

### Description

Extract one vector from a tuple of four vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Extract vector from tuple

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

Not supplied by source.

### Result mapping

Not supplied by source.

### Instruction mapping

Not supplied by source.

### Operation

Source operation ID: `SveOperation_svget4_bf16`

**Operation**



Return vector `imm_index` of `tuple`. `imm_index` must be an integer constant expression in the range [0, 3].

## svget4[_u8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svget4%5B_u8%5D

### Signature (source notation)

```c
svuint8_t svget4[_u8](svuint8x4_t tuple, uint64_t imm_index);
```

### Description

Extract one vector from a tuple of four vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Extract vector from tuple

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

Not supplied by source.

### Result mapping

Not supplied by source.

### Instruction mapping

Not supplied by source.

### Operation

Source operation ID: `SveOperation_svget4_bf16`

**Operation**



Return vector `imm_index` of `tuple`. `imm_index` must be an integer constant expression in the range [0, 3].

