# SME / Vector tuple manipulation / Set vector in tuple — Part 1

## svset2[_b]

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svset2%5B_b%5D

### Signature (source notation)

```c
svboolx2_t svset2[_b](svboolx2_t tuple, uint64_t imm_index, svbool_t x);
```

### Description

Change one predicate vector in a tuple of two predicate vectors.

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector tuple manipulation / Set vector in tuple

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
  "tuple": {
    "register sequence": "Preg1.B, Preg2.B"
  },
  "imm_index": {
    "immediate": "<num>"
  },
  "x": {
    "register": "Preg3.B"
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
MOV Preg<num>.B, Preg3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/MOV--Move-predicate--unpredicated---an-alias-of-ORR--predicates--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svset2[_bf16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svset2%5B_bf16%5D

### Signature (source notation)

```c
svbfloat16x2_t svset2[_bf16](svbfloat16x2_t tuple, uint64_t imm_index, svbfloat16_t x);
```

### Description

Change one vector in a tuple of two vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Set vector in tuple

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
  "value": "svbfloat16x2_t"
}
```

### Argument preparation and constraints

Not supplied by source.

### Result mapping

Not supplied by source.

### Instruction mapping

Not supplied by source.

### Operation

Source operation ID: `SveOperation_svset2_bf16`

**Operation**



Return the result of copying `tuple` and replacing vector `imm_index` with `x`.  `imm_index` must be an integer constant expression in the range [0, 1].

## svset2[_f16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svset2%5B_f16%5D

### Signature (source notation)

```c
svfloat16x2_t svset2[_f16](svfloat16x2_t tuple, uint64_t imm_index, svfloat16_t x);
```

### Description

Change one vector in a tuple of two vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Set vector in tuple

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
  "value": "svfloat16x2_t"
}
```

### Argument preparation and constraints

Not supplied by source.

### Result mapping

Not supplied by source.

### Instruction mapping

Not supplied by source.

### Operation

Source operation ID: `SveOperation_svset2_bf16`

**Operation**



Return the result of copying `tuple` and replacing vector `imm_index` with `x`.  `imm_index` must be an integer constant expression in the range [0, 1].

## svset2[_f32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svset2%5B_f32%5D

### Signature (source notation)

```c
svfloat32x2_t svset2[_f32](svfloat32x2_t tuple, uint64_t imm_index, svfloat32_t x);
```

### Description

Change one vector in a tuple of two vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Set vector in tuple

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
  "value": "svfloat32x2_t"
}
```

### Argument preparation and constraints

Not supplied by source.

### Result mapping

Not supplied by source.

### Instruction mapping

Not supplied by source.

### Operation

Source operation ID: `SveOperation_svset2_bf16`

**Operation**



Return the result of copying `tuple` and replacing vector `imm_index` with `x`.  `imm_index` must be an integer constant expression in the range [0, 1].

## svset2[_f64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svset2%5B_f64%5D

### Signature (source notation)

```c
svfloat64x2_t svset2[_f64](svfloat64x2_t tuple, uint64_t imm_index, svfloat64_t x);
```

### Description

Change one vector in a tuple of two vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Set vector in tuple

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
  "value": "svfloat64x2_t"
}
```

### Argument preparation and constraints

Not supplied by source.

### Result mapping

Not supplied by source.

### Instruction mapping

Not supplied by source.

### Operation

Source operation ID: `SveOperation_svset2_bf16`

**Operation**



Return the result of copying `tuple` and replacing vector `imm_index` with `x`.  `imm_index` must be an integer constant expression in the range [0, 1].

## svset2[_mf8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svset2%5B_mf8%5D

### Signature (source notation)

```c
svmfloat8x2_t svset2[_mf8](svmfloat8x2_t tuple, uint64_t imm_index, svmfloat8_t x);
```

### Description

Change one vector in a tuple of two vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Set vector in tuple

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
  "value": "svmfloat8x2_t"
}
```

### Argument preparation and constraints

Not supplied by source.

### Result mapping

Not supplied by source.

### Instruction mapping

Not supplied by source.

### Operation

Source operation ID: `SveOperation_svset2_bf16`

**Operation**



Return the result of copying `tuple` and replacing vector `imm_index` with `x`.  `imm_index` must be an integer constant expression in the range [0, 1].

## svset2[_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svset2%5B_s16%5D

### Signature (source notation)

```c
svint16x2_t svset2[_s16](svint16x2_t tuple, uint64_t imm_index, svint16_t x);
```

### Description

Change one vector in a tuple of two vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Set vector in tuple

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
  "value": "svint16x2_t"
}
```

### Argument preparation and constraints

Not supplied by source.

### Result mapping

Not supplied by source.

### Instruction mapping

Not supplied by source.

### Operation

Source operation ID: `SveOperation_svset2_bf16`

**Operation**



Return the result of copying `tuple` and replacing vector `imm_index` with `x`.  `imm_index` must be an integer constant expression in the range [0, 1].

## svset2[_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svset2%5B_s32%5D

### Signature (source notation)

```c
svint32x2_t svset2[_s32](svint32x2_t tuple, uint64_t imm_index, svint32_t x);
```

### Description

Change one vector in a tuple of two vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Set vector in tuple

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
  "value": "svint32x2_t"
}
```

### Argument preparation and constraints

Not supplied by source.

### Result mapping

Not supplied by source.

### Instruction mapping

Not supplied by source.

### Operation

Source operation ID: `SveOperation_svset2_bf16`

**Operation**



Return the result of copying `tuple` and replacing vector `imm_index` with `x`.  `imm_index` must be an integer constant expression in the range [0, 1].

## svset2[_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svset2%5B_s64%5D

### Signature (source notation)

```c
svint64x2_t svset2[_s64](svint64x2_t tuple, uint64_t imm_index, svint64_t x);
```

### Description

Change one vector in a tuple of two vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Set vector in tuple

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
  "value": "svint64x2_t"
}
```

### Argument preparation and constraints

Not supplied by source.

### Result mapping

Not supplied by source.

### Instruction mapping

Not supplied by source.

### Operation

Source operation ID: `SveOperation_svset2_bf16`

**Operation**



Return the result of copying `tuple` and replacing vector `imm_index` with `x`.  `imm_index` must be an integer constant expression in the range [0, 1].

## svset2[_s8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svset2%5B_s8%5D

### Signature (source notation)

```c
svint8x2_t svset2[_s8](svint8x2_t tuple, uint64_t imm_index, svint8_t x);
```

### Description

Change one vector in a tuple of two vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Set vector in tuple

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
  "value": "svint8x2_t"
}
```

### Argument preparation and constraints

Not supplied by source.

### Result mapping

Not supplied by source.

### Instruction mapping

Not supplied by source.

### Operation

Source operation ID: `SveOperation_svset2_bf16`

**Operation**



Return the result of copying `tuple` and replacing vector `imm_index` with `x`.  `imm_index` must be an integer constant expression in the range [0, 1].

## svset2[_u16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svset2%5B_u16%5D

### Signature (source notation)

```c
svuint16x2_t svset2[_u16](svuint16x2_t tuple, uint64_t imm_index, svuint16_t x);
```

### Description

Change one vector in a tuple of two vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Set vector in tuple

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
  "value": "svuint16x2_t"
}
```

### Argument preparation and constraints

Not supplied by source.

### Result mapping

Not supplied by source.

### Instruction mapping

Not supplied by source.

### Operation

Source operation ID: `SveOperation_svset2_bf16`

**Operation**



Return the result of copying `tuple` and replacing vector `imm_index` with `x`.  `imm_index` must be an integer constant expression in the range [0, 1].

## svset2[_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svset2%5B_u32%5D

### Signature (source notation)

```c
svuint32x2_t svset2[_u32](svuint32x2_t tuple, uint64_t imm_index, svuint32_t x);
```

### Description

Change one vector in a tuple of two vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Set vector in tuple

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
  "value": "svuint32x2_t"
}
```

### Argument preparation and constraints

Not supplied by source.

### Result mapping

Not supplied by source.

### Instruction mapping

Not supplied by source.

### Operation

Source operation ID: `SveOperation_svset2_bf16`

**Operation**



Return the result of copying `tuple` and replacing vector `imm_index` with `x`.  `imm_index` must be an integer constant expression in the range [0, 1].

## svset2[_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svset2%5B_u64%5D

### Signature (source notation)

```c
svuint64x2_t svset2[_u64](svuint64x2_t tuple, uint64_t imm_index, svuint64_t x);
```

### Description

Change one vector in a tuple of two vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Set vector in tuple

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
  "value": "svuint64x2_t"
}
```

### Argument preparation and constraints

Not supplied by source.

### Result mapping

Not supplied by source.

### Instruction mapping

Not supplied by source.

### Operation

Source operation ID: `SveOperation_svset2_bf16`

**Operation**



Return the result of copying `tuple` and replacing vector `imm_index` with `x`.  `imm_index` must be an integer constant expression in the range [0, 1].

## svset2[_u8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svset2%5B_u8%5D

### Signature (source notation)

```c
svuint8x2_t svset2[_u8](svuint8x2_t tuple, uint64_t imm_index, svuint8_t x);
```

### Description

Change one vector in a tuple of two vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Set vector in tuple

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
  "value": "svuint8x2_t"
}
```

### Argument preparation and constraints

Not supplied by source.

### Result mapping

Not supplied by source.

### Instruction mapping

Not supplied by source.

### Operation

Source operation ID: `SveOperation_svset2_bf16`

**Operation**



Return the result of copying `tuple` and replacing vector `imm_index` with `x`.  `imm_index` must be an integer constant expression in the range [0, 1].

## svset3[_bf16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svset3%5B_bf16%5D

### Signature (source notation)

```c
svbfloat16x3_t svset3[_bf16](svbfloat16x3_t tuple, uint64_t imm_index, svbfloat16_t x);
```

### Description

Change one vector in a tuple of three vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Set vector in tuple

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
  "value": "svbfloat16x3_t"
}
```

### Argument preparation and constraints

Not supplied by source.

### Result mapping

Not supplied by source.

### Instruction mapping

Not supplied by source.

### Operation

Source operation ID: `SveOperation_svset3_bf16`

**Operation**



Return the result of copying `tuple` and replacing vector `imm_index` with `x`.  `imm_index` must be an integer constant expression in the range [0, 2].

## svset3[_f16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svset3%5B_f16%5D

### Signature (source notation)

```c
svfloat16x3_t svset3[_f16](svfloat16x3_t tuple, uint64_t imm_index, svfloat16_t x);
```

### Description

Change one vector in a tuple of three vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Set vector in tuple

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
  "value": "svfloat16x3_t"
}
```

### Argument preparation and constraints

Not supplied by source.

### Result mapping

Not supplied by source.

### Instruction mapping

Not supplied by source.

### Operation

Source operation ID: `SveOperation_svset3_bf16`

**Operation**



Return the result of copying `tuple` and replacing vector `imm_index` with `x`.  `imm_index` must be an integer constant expression in the range [0, 2].

## svset3[_f32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svset3%5B_f32%5D

### Signature (source notation)

```c
svfloat32x3_t svset3[_f32](svfloat32x3_t tuple, uint64_t imm_index, svfloat32_t x);
```

### Description

Change one vector in a tuple of three vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Set vector in tuple

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
  "value": "svfloat32x3_t"
}
```

### Argument preparation and constraints

Not supplied by source.

### Result mapping

Not supplied by source.

### Instruction mapping

Not supplied by source.

### Operation

Source operation ID: `SveOperation_svset3_bf16`

**Operation**



Return the result of copying `tuple` and replacing vector `imm_index` with `x`.  `imm_index` must be an integer constant expression in the range [0, 2].

## svset3[_f64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svset3%5B_f64%5D

### Signature (source notation)

```c
svfloat64x3_t svset3[_f64](svfloat64x3_t tuple, uint64_t imm_index, svfloat64_t x);
```

### Description

Change one vector in a tuple of three vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Set vector in tuple

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
  "value": "svfloat64x3_t"
}
```

### Argument preparation and constraints

Not supplied by source.

### Result mapping

Not supplied by source.

### Instruction mapping

Not supplied by source.

### Operation

Source operation ID: `SveOperation_svset3_bf16`

**Operation**



Return the result of copying `tuple` and replacing vector `imm_index` with `x`.  `imm_index` must be an integer constant expression in the range [0, 2].

## svset3[_mf8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svset3%5B_mf8%5D

### Signature (source notation)

```c
svmfloat8x3_t svset3[_mf8](svmfloat8x3_t tuple, uint64_t imm_index, svmfloat8_t x);
```

### Description

Change one vector in a tuple of three vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Set vector in tuple

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
  "value": "svmfloat8x3_t"
}
```

### Argument preparation and constraints

Not supplied by source.

### Result mapping

Not supplied by source.

### Instruction mapping

Not supplied by source.

### Operation

Source operation ID: `SveOperation_svset3_bf16`

**Operation**



Return the result of copying `tuple` and replacing vector `imm_index` with `x`.  `imm_index` must be an integer constant expression in the range [0, 2].

## svset3[_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svset3%5B_s16%5D

### Signature (source notation)

```c
svint16x3_t svset3[_s16](svint16x3_t tuple, uint64_t imm_index, svint16_t x);
```

### Description

Change one vector in a tuple of three vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Set vector in tuple

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
  "value": "svint16x3_t"
}
```

### Argument preparation and constraints

Not supplied by source.

### Result mapping

Not supplied by source.

### Instruction mapping

Not supplied by source.

### Operation

Source operation ID: `SveOperation_svset3_bf16`

**Operation**



Return the result of copying `tuple` and replacing vector `imm_index` with `x`.  `imm_index` must be an integer constant expression in the range [0, 2].

## svset3[_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svset3%5B_s32%5D

### Signature (source notation)

```c
svint32x3_t svset3[_s32](svint32x3_t tuple, uint64_t imm_index, svint32_t x);
```

### Description

Change one vector in a tuple of three vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Set vector in tuple

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
  "value": "svint32x3_t"
}
```

### Argument preparation and constraints

Not supplied by source.

### Result mapping

Not supplied by source.

### Instruction mapping

Not supplied by source.

### Operation

Source operation ID: `SveOperation_svset3_bf16`

**Operation**



Return the result of copying `tuple` and replacing vector `imm_index` with `x`.  `imm_index` must be an integer constant expression in the range [0, 2].

## svset3[_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svset3%5B_s64%5D

### Signature (source notation)

```c
svint64x3_t svset3[_s64](svint64x3_t tuple, uint64_t imm_index, svint64_t x);
```

### Description

Change one vector in a tuple of three vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Set vector in tuple

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
  "value": "svint64x3_t"
}
```

### Argument preparation and constraints

Not supplied by source.

### Result mapping

Not supplied by source.

### Instruction mapping

Not supplied by source.

### Operation

Source operation ID: `SveOperation_svset3_bf16`

**Operation**



Return the result of copying `tuple` and replacing vector `imm_index` with `x`.  `imm_index` must be an integer constant expression in the range [0, 2].

## svset3[_s8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svset3%5B_s8%5D

### Signature (source notation)

```c
svint8x3_t svset3[_s8](svint8x3_t tuple, uint64_t imm_index, svint8_t x);
```

### Description

Change one vector in a tuple of three vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Set vector in tuple

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
  "value": "svint8x3_t"
}
```

### Argument preparation and constraints

Not supplied by source.

### Result mapping

Not supplied by source.

### Instruction mapping

Not supplied by source.

### Operation

Source operation ID: `SveOperation_svset3_bf16`

**Operation**



Return the result of copying `tuple` and replacing vector `imm_index` with `x`.  `imm_index` must be an integer constant expression in the range [0, 2].

## svset3[_u16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svset3%5B_u16%5D

### Signature (source notation)

```c
svuint16x3_t svset3[_u16](svuint16x3_t tuple, uint64_t imm_index, svuint16_t x);
```

### Description

Change one vector in a tuple of three vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Set vector in tuple

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
  "value": "svuint16x3_t"
}
```

### Argument preparation and constraints

Not supplied by source.

### Result mapping

Not supplied by source.

### Instruction mapping

Not supplied by source.

### Operation

Source operation ID: `SveOperation_svset3_bf16`

**Operation**



Return the result of copying `tuple` and replacing vector `imm_index` with `x`.  `imm_index` must be an integer constant expression in the range [0, 2].

## svset3[_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svset3%5B_u32%5D

### Signature (source notation)

```c
svuint32x3_t svset3[_u32](svuint32x3_t tuple, uint64_t imm_index, svuint32_t x);
```

### Description

Change one vector in a tuple of three vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Set vector in tuple

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
  "value": "svuint32x3_t"
}
```

### Argument preparation and constraints

Not supplied by source.

### Result mapping

Not supplied by source.

### Instruction mapping

Not supplied by source.

### Operation

Source operation ID: `SveOperation_svset3_bf16`

**Operation**



Return the result of copying `tuple` and replacing vector `imm_index` with `x`.  `imm_index` must be an integer constant expression in the range [0, 2].

## svset3[_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svset3%5B_u64%5D

### Signature (source notation)

```c
svuint64x3_t svset3[_u64](svuint64x3_t tuple, uint64_t imm_index, svuint64_t x);
```

### Description

Change one vector in a tuple of three vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Set vector in tuple

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
  "value": "svuint64x3_t"
}
```

### Argument preparation and constraints

Not supplied by source.

### Result mapping

Not supplied by source.

### Instruction mapping

Not supplied by source.

### Operation

Source operation ID: `SveOperation_svset3_bf16`

**Operation**



Return the result of copying `tuple` and replacing vector `imm_index` with `x`.  `imm_index` must be an integer constant expression in the range [0, 2].

## svset3[_u8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svset3%5B_u8%5D

### Signature (source notation)

```c
svuint8x3_t svset3[_u8](svuint8x3_t tuple, uint64_t imm_index, svuint8_t x);
```

### Description

Change one vector in a tuple of three vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Set vector in tuple

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
  "value": "svuint8x3_t"
}
```

### Argument preparation and constraints

Not supplied by source.

### Result mapping

Not supplied by source.

### Instruction mapping

Not supplied by source.

### Operation

Source operation ID: `SveOperation_svset3_bf16`

**Operation**



Return the result of copying `tuple` and replacing vector `imm_index` with `x`.  `imm_index` must be an integer constant expression in the range [0, 2].

## svset4[_b]

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svset4%5B_b%5D

### Signature (source notation)

```c
svboolx4_t svset4[_b](svboolx4_t tuple, uint64_t imm_index, svbool_t x);
```

### Description

Change one predicate vector in a tuple of four predicate vectors.

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector tuple manipulation / Set vector in tuple

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
  "value": "svboolx4_t"
}
```

### Argument preparation and constraints

```json
{
  "tuple": {
    "register sequence": "Preg1.B, Preg2.B, Preg3.B, Preg4.B"
  },
  "imm_index": {
    "immediate": "<num>"
  },
  "x": {
    "register": "Preg5.B"
  }
}
```

### Result mapping

```json
[
  {
    "{ Preg1.B, Preg2.B, Preg3.B, Preg4.B }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
MOV Preg<num>.B, Preg5.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/MOV--Move-predicate--unpredicated---an-alias-of-ORR--predicates--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svset4[_bf16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svset4%5B_bf16%5D

### Signature (source notation)

```c
svbfloat16x4_t svset4[_bf16](svbfloat16x4_t tuple, uint64_t imm_index, svbfloat16_t x);
```

### Description

Change one vector in a tuple of four vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Set vector in tuple

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
  "value": "svbfloat16x4_t"
}
```

### Argument preparation and constraints

Not supplied by source.

### Result mapping

Not supplied by source.

### Instruction mapping

Not supplied by source.

### Operation

Source operation ID: `SveOperation_svset4_bf16`

**Operation**



Return the result of copying `tuple` and replacing vector `imm_index` with `x`.  `imm_index` must be an integer constant expression in the range [0, 3].

## svset4[_f16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svset4%5B_f16%5D

### Signature (source notation)

```c
svfloat16x4_t svset4[_f16](svfloat16x4_t tuple, uint64_t imm_index, svfloat16_t x);
```

### Description

Change one vector in a tuple of four vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Set vector in tuple

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
  "value": "svfloat16x4_t"
}
```

### Argument preparation and constraints

Not supplied by source.

### Result mapping

Not supplied by source.

### Instruction mapping

Not supplied by source.

### Operation

Source operation ID: `SveOperation_svset4_bf16`

**Operation**



Return the result of copying `tuple` and replacing vector `imm_index` with `x`.  `imm_index` must be an integer constant expression in the range [0, 3].

## svset4[_f32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svset4%5B_f32%5D

### Signature (source notation)

```c
svfloat32x4_t svset4[_f32](svfloat32x4_t tuple, uint64_t imm_index, svfloat32_t x);
```

### Description

Change one vector in a tuple of four vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Set vector in tuple

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
  "value": "svfloat32x4_t"
}
```

### Argument preparation and constraints

Not supplied by source.

### Result mapping

Not supplied by source.

### Instruction mapping

Not supplied by source.

### Operation

Source operation ID: `SveOperation_svset4_bf16`

**Operation**



Return the result of copying `tuple` and replacing vector `imm_index` with `x`.  `imm_index` must be an integer constant expression in the range [0, 3].

## svset4[_f64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svset4%5B_f64%5D

### Signature (source notation)

```c
svfloat64x4_t svset4[_f64](svfloat64x4_t tuple, uint64_t imm_index, svfloat64_t x);
```

### Description

Change one vector in a tuple of four vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Set vector in tuple

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
  "value": "svfloat64x4_t"
}
```

### Argument preparation and constraints

Not supplied by source.

### Result mapping

Not supplied by source.

### Instruction mapping

Not supplied by source.

### Operation

Source operation ID: `SveOperation_svset4_bf16`

**Operation**



Return the result of copying `tuple` and replacing vector `imm_index` with `x`.  `imm_index` must be an integer constant expression in the range [0, 3].

## svset4[_mf8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svset4%5B_mf8%5D

### Signature (source notation)

```c
svmfloat8x4_t svset4[_mf8](svmfloat8x4_t tuple, uint64_t imm_index, svmfloat8_t x);
```

### Description

Change one vector in a tuple of four vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Set vector in tuple

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
  "value": "svmfloat8x4_t"
}
```

### Argument preparation and constraints

Not supplied by source.

### Result mapping

Not supplied by source.

### Instruction mapping

Not supplied by source.

### Operation

Source operation ID: `SveOperation_svset4_bf16`

**Operation**



Return the result of copying `tuple` and replacing vector `imm_index` with `x`.  `imm_index` must be an integer constant expression in the range [0, 3].

## svset4[_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svset4%5B_s16%5D

### Signature (source notation)

```c
svint16x4_t svset4[_s16](svint16x4_t tuple, uint64_t imm_index, svint16_t x);
```

### Description

Change one vector in a tuple of four vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Set vector in tuple

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
  "value": "svint16x4_t"
}
```

### Argument preparation and constraints

Not supplied by source.

### Result mapping

Not supplied by source.

### Instruction mapping

Not supplied by source.

### Operation

Source operation ID: `SveOperation_svset4_bf16`

**Operation**



Return the result of copying `tuple` and replacing vector `imm_index` with `x`.  `imm_index` must be an integer constant expression in the range [0, 3].

## svset4[_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svset4%5B_s32%5D

### Signature (source notation)

```c
svint32x4_t svset4[_s32](svint32x4_t tuple, uint64_t imm_index, svint32_t x);
```

### Description

Change one vector in a tuple of four vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Set vector in tuple

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
  "value": "svint32x4_t"
}
```

### Argument preparation and constraints

Not supplied by source.

### Result mapping

Not supplied by source.

### Instruction mapping

Not supplied by source.

### Operation

Source operation ID: `SveOperation_svset4_bf16`

**Operation**



Return the result of copying `tuple` and replacing vector `imm_index` with `x`.  `imm_index` must be an integer constant expression in the range [0, 3].

## svset4[_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svset4%5B_s64%5D

### Signature (source notation)

```c
svint64x4_t svset4[_s64](svint64x4_t tuple, uint64_t imm_index, svint64_t x);
```

### Description

Change one vector in a tuple of four vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Set vector in tuple

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
  "value": "svint64x4_t"
}
```

### Argument preparation and constraints

Not supplied by source.

### Result mapping

Not supplied by source.

### Instruction mapping

Not supplied by source.

### Operation

Source operation ID: `SveOperation_svset4_bf16`

**Operation**



Return the result of copying `tuple` and replacing vector `imm_index` with `x`.  `imm_index` must be an integer constant expression in the range [0, 3].

## svset4[_s8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svset4%5B_s8%5D

### Signature (source notation)

```c
svint8x4_t svset4[_s8](svint8x4_t tuple, uint64_t imm_index, svint8_t x);
```

### Description

Change one vector in a tuple of four vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Set vector in tuple

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
  "value": "svint8x4_t"
}
```

### Argument preparation and constraints

Not supplied by source.

### Result mapping

Not supplied by source.

### Instruction mapping

Not supplied by source.

### Operation

Source operation ID: `SveOperation_svset4_bf16`

**Operation**



Return the result of copying `tuple` and replacing vector `imm_index` with `x`.  `imm_index` must be an integer constant expression in the range [0, 3].

## svset4[_u16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svset4%5B_u16%5D

### Signature (source notation)

```c
svuint16x4_t svset4[_u16](svuint16x4_t tuple, uint64_t imm_index, svuint16_t x);
```

### Description

Change one vector in a tuple of four vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Set vector in tuple

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
  "value": "svuint16x4_t"
}
```

### Argument preparation and constraints

Not supplied by source.

### Result mapping

Not supplied by source.

### Instruction mapping

Not supplied by source.

### Operation

Source operation ID: `SveOperation_svset4_bf16`

**Operation**



Return the result of copying `tuple` and replacing vector `imm_index` with `x`.  `imm_index` must be an integer constant expression in the range [0, 3].

## svset4[_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svset4%5B_u32%5D

### Signature (source notation)

```c
svuint32x4_t svset4[_u32](svuint32x4_t tuple, uint64_t imm_index, svuint32_t x);
```

### Description

Change one vector in a tuple of four vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Set vector in tuple

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
  "value": "svuint32x4_t"
}
```

### Argument preparation and constraints

Not supplied by source.

### Result mapping

Not supplied by source.

### Instruction mapping

Not supplied by source.

### Operation

Source operation ID: `SveOperation_svset4_bf16`

**Operation**



Return the result of copying `tuple` and replacing vector `imm_index` with `x`.  `imm_index` must be an integer constant expression in the range [0, 3].

## svset4[_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svset4%5B_u64%5D

### Signature (source notation)

```c
svuint64x4_t svset4[_u64](svuint64x4_t tuple, uint64_t imm_index, svuint64_t x);
```

### Description

Change one vector in a tuple of four vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Set vector in tuple

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
  "value": "svuint64x4_t"
}
```

### Argument preparation and constraints

Not supplied by source.

### Result mapping

Not supplied by source.

### Instruction mapping

Not supplied by source.

### Operation

Source operation ID: `SveOperation_svset4_bf16`

**Operation**



Return the result of copying `tuple` and replacing vector `imm_index` with `x`.  `imm_index` must be an integer constant expression in the range [0, 3].

## svset4[_u8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svset4%5B_u8%5D

### Signature (source notation)

```c
svuint8x4_t svset4[_u8](svuint8x4_t tuple, uint64_t imm_index, svuint8_t x);
```

### Description

Change one vector in a tuple of four vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Set vector in tuple

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
  "value": "svuint8x4_t"
}
```

### Argument preparation and constraints

Not supplied by source.

### Result mapping

Not supplied by source.

### Instruction mapping

Not supplied by source.

### Operation

Source operation ID: `SveOperation_svset4_bf16`

**Operation**



Return the result of copying `tuple` and replacing vector `imm_index` with `x`.  `imm_index` must be an integer constant expression in the range [0, 3].

