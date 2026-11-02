# SME / Vector tuple manipulation / Create uninitialized vector tuple — Part 1

## svundef2_b

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svundef2_b

### Signature (source notation)

```c
svboolx2_t svundef2_b();
```

### Description

Create an uninitialized tuple of two predicate vectors. No instruction is emitted for the uninitialized value itself.

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector tuple manipulation / Create uninitialized vector tuple

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

Not supplied by source.

### Result mapping

Not supplied by source.

### Instruction mapping

Not supplied by source.

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svundef2_bf16

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svundef2_bf16

### Signature (source notation)

```c
svbfloat16x2_t svundef2_bf16();
```

### Description

Create an uninitialized tuple of two vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Create uninitialized vector tuple

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

Source operation ID: `SveOperation_svundef2_bf16`

**Operation**



Return a tuple of two vectors with arbitrary, undefined contents.



This function can be useful for “seeding” a sequence of operations that cumulatively leaves all active elements in a defined state.

## svundef2_f16

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svundef2_f16

### Signature (source notation)

```c
svfloat16x2_t svundef2_f16();
```

### Description

Create an uninitialized tuple of two vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Create uninitialized vector tuple

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

Source operation ID: `SveOperation_svundef2_bf16`

**Operation**



Return a tuple of two vectors with arbitrary, undefined contents.



This function can be useful for “seeding” a sequence of operations that cumulatively leaves all active elements in a defined state.

## svundef2_f32

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svundef2_f32

### Signature (source notation)

```c
svfloat32x2_t svundef2_f32();
```

### Description

Create an uninitialized tuple of two vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Create uninitialized vector tuple

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

Source operation ID: `SveOperation_svundef2_bf16`

**Operation**



Return a tuple of two vectors with arbitrary, undefined contents.



This function can be useful for “seeding” a sequence of operations that cumulatively leaves all active elements in a defined state.

## svundef2_f64

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svundef2_f64

### Signature (source notation)

```c
svfloat64x2_t svundef2_f64();
```

### Description

Create an uninitialized tuple of two vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Create uninitialized vector tuple

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

Source operation ID: `SveOperation_svundef2_bf16`

**Operation**



Return a tuple of two vectors with arbitrary, undefined contents.



This function can be useful for “seeding” a sequence of operations that cumulatively leaves all active elements in a defined state.

## svundef2_mf8

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svundef2_mf8

### Signature (source notation)

```c
svmfloat8x2_t svundef2_mf8();
```

### Description

Create an uninitialized tuple of two vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Create uninitialized vector tuple

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

Source operation ID: `SveOperation_svundef2_bf16`

**Operation**



Return a tuple of two vectors with arbitrary, undefined contents.



This function can be useful for “seeding” a sequence of operations that cumulatively leaves all active elements in a defined state.

## svundef2_s16

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svundef2_s16

### Signature (source notation)

```c
svint16x2_t svundef2_s16();
```

### Description

Create an uninitialized tuple of two vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Create uninitialized vector tuple

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

Source operation ID: `SveOperation_svundef2_bf16`

**Operation**



Return a tuple of two vectors with arbitrary, undefined contents.



This function can be useful for “seeding” a sequence of operations that cumulatively leaves all active elements in a defined state.

## svundef2_s32

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svundef2_s32

### Signature (source notation)

```c
svint32x2_t svundef2_s32();
```

### Description

Create an uninitialized tuple of two vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Create uninitialized vector tuple

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

Source operation ID: `SveOperation_svundef2_bf16`

**Operation**



Return a tuple of two vectors with arbitrary, undefined contents.



This function can be useful for “seeding” a sequence of operations that cumulatively leaves all active elements in a defined state.

## svundef2_s64

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svundef2_s64

### Signature (source notation)

```c
svint64x2_t svundef2_s64();
```

### Description

Create an uninitialized tuple of two vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Create uninitialized vector tuple

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

Source operation ID: `SveOperation_svundef2_bf16`

**Operation**



Return a tuple of two vectors with arbitrary, undefined contents.



This function can be useful for “seeding” a sequence of operations that cumulatively leaves all active elements in a defined state.

## svundef2_s8

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svundef2_s8

### Signature (source notation)

```c
svint8x2_t svundef2_s8();
```

### Description

Create an uninitialized tuple of two vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Create uninitialized vector tuple

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

Source operation ID: `SveOperation_svundef2_bf16`

**Operation**



Return a tuple of two vectors with arbitrary, undefined contents.



This function can be useful for “seeding” a sequence of operations that cumulatively leaves all active elements in a defined state.

## svundef2_u16

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svundef2_u16

### Signature (source notation)

```c
svuint16x2_t svundef2_u16();
```

### Description

Create an uninitialized tuple of two vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Create uninitialized vector tuple

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

Source operation ID: `SveOperation_svundef2_bf16`

**Operation**



Return a tuple of two vectors with arbitrary, undefined contents.



This function can be useful for “seeding” a sequence of operations that cumulatively leaves all active elements in a defined state.

## svundef2_u32

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svundef2_u32

### Signature (source notation)

```c
svuint32x2_t svundef2_u32();
```

### Description

Create an uninitialized tuple of two vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Create uninitialized vector tuple

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

Source operation ID: `SveOperation_svundef2_bf16`

**Operation**



Return a tuple of two vectors with arbitrary, undefined contents.



This function can be useful for “seeding” a sequence of operations that cumulatively leaves all active elements in a defined state.

## svundef2_u64

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svundef2_u64

### Signature (source notation)

```c
svuint64x2_t svundef2_u64();
```

### Description

Create an uninitialized tuple of two vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Create uninitialized vector tuple

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

Source operation ID: `SveOperation_svundef2_bf16`

**Operation**



Return a tuple of two vectors with arbitrary, undefined contents.



This function can be useful for “seeding” a sequence of operations that cumulatively leaves all active elements in a defined state.

## svundef2_u8

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svundef2_u8

### Signature (source notation)

```c
svuint8x2_t svundef2_u8();
```

### Description

Create an uninitialized tuple of two vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Create uninitialized vector tuple

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

Source operation ID: `SveOperation_svundef2_bf16`

**Operation**



Return a tuple of two vectors with arbitrary, undefined contents.



This function can be useful for “seeding” a sequence of operations that cumulatively leaves all active elements in a defined state.

## svundef3_bf16

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svundef3_bf16

### Signature (source notation)

```c
svbfloat16x3_t svundef3_bf16();
```

### Description

Create an uninitialized tuple of three vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Create uninitialized vector tuple

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

Source operation ID: `SveOperation_svundef3_bf16`

**Operation**



Return a tuple of three vectors with arbitrary, undefined contents.



This function can be useful for “seeding” a sequence of operations that cumulatively leaves all active elements in a defined state.

## svundef3_f16

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svundef3_f16

### Signature (source notation)

```c
svfloat16x3_t svundef3_f16();
```

### Description

Create an uninitialized tuple of three vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Create uninitialized vector tuple

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

Source operation ID: `SveOperation_svundef3_bf16`

**Operation**



Return a tuple of three vectors with arbitrary, undefined contents.



This function can be useful for “seeding” a sequence of operations that cumulatively leaves all active elements in a defined state.

## svundef3_f32

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svundef3_f32

### Signature (source notation)

```c
svfloat32x3_t svundef3_f32();
```

### Description

Create an uninitialized tuple of three vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Create uninitialized vector tuple

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

Source operation ID: `SveOperation_svundef3_bf16`

**Operation**



Return a tuple of three vectors with arbitrary, undefined contents.



This function can be useful for “seeding” a sequence of operations that cumulatively leaves all active elements in a defined state.

## svundef3_f64

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svundef3_f64

### Signature (source notation)

```c
svfloat64x3_t svundef3_f64();
```

### Description

Create an uninitialized tuple of three vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Create uninitialized vector tuple

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

Source operation ID: `SveOperation_svundef3_bf16`

**Operation**



Return a tuple of three vectors with arbitrary, undefined contents.



This function can be useful for “seeding” a sequence of operations that cumulatively leaves all active elements in a defined state.

## svundef3_mf8

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svundef3_mf8

### Signature (source notation)

```c
svmfloat8x3_t svundef3_mf8();
```

### Description

Create an uninitialized tuple of three vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Create uninitialized vector tuple

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

Source operation ID: `SveOperation_svundef3_bf16`

**Operation**



Return a tuple of three vectors with arbitrary, undefined contents.



This function can be useful for “seeding” a sequence of operations that cumulatively leaves all active elements in a defined state.

## svundef3_s16

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svundef3_s16

### Signature (source notation)

```c
svint16x3_t svundef3_s16();
```

### Description

Create an uninitialized tuple of three vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Create uninitialized vector tuple

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

Source operation ID: `SveOperation_svundef3_bf16`

**Operation**



Return a tuple of three vectors with arbitrary, undefined contents.



This function can be useful for “seeding” a sequence of operations that cumulatively leaves all active elements in a defined state.

## svundef3_s32

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svundef3_s32

### Signature (source notation)

```c
svint32x3_t svundef3_s32();
```

### Description

Create an uninitialized tuple of three vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Create uninitialized vector tuple

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

Source operation ID: `SveOperation_svundef3_bf16`

**Operation**



Return a tuple of three vectors with arbitrary, undefined contents.



This function can be useful for “seeding” a sequence of operations that cumulatively leaves all active elements in a defined state.

## svundef3_s64

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svundef3_s64

### Signature (source notation)

```c
svint64x3_t svundef3_s64();
```

### Description

Create an uninitialized tuple of three vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Create uninitialized vector tuple

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

Source operation ID: `SveOperation_svundef3_bf16`

**Operation**



Return a tuple of three vectors with arbitrary, undefined contents.



This function can be useful for “seeding” a sequence of operations that cumulatively leaves all active elements in a defined state.

## svundef3_s8

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svundef3_s8

### Signature (source notation)

```c
svint8x3_t svundef3_s8();
```

### Description

Create an uninitialized tuple of three vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Create uninitialized vector tuple

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

Source operation ID: `SveOperation_svundef3_bf16`

**Operation**



Return a tuple of three vectors with arbitrary, undefined contents.



This function can be useful for “seeding” a sequence of operations that cumulatively leaves all active elements in a defined state.

## svundef3_u16

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svundef3_u16

### Signature (source notation)

```c
svuint16x3_t svundef3_u16();
```

### Description

Create an uninitialized tuple of three vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Create uninitialized vector tuple

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

Source operation ID: `SveOperation_svundef3_bf16`

**Operation**



Return a tuple of three vectors with arbitrary, undefined contents.



This function can be useful for “seeding” a sequence of operations that cumulatively leaves all active elements in a defined state.

## svundef3_u32

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svundef3_u32

### Signature (source notation)

```c
svuint32x3_t svundef3_u32();
```

### Description

Create an uninitialized tuple of three vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Create uninitialized vector tuple

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

Source operation ID: `SveOperation_svundef3_bf16`

**Operation**



Return a tuple of three vectors with arbitrary, undefined contents.



This function can be useful for “seeding” a sequence of operations that cumulatively leaves all active elements in a defined state.

## svundef3_u64

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svundef3_u64

### Signature (source notation)

```c
svuint64x3_t svundef3_u64();
```

### Description

Create an uninitialized tuple of three vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Create uninitialized vector tuple

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

Source operation ID: `SveOperation_svundef3_bf16`

**Operation**



Return a tuple of three vectors with arbitrary, undefined contents.



This function can be useful for “seeding” a sequence of operations that cumulatively leaves all active elements in a defined state.

## svundef3_u8

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svundef3_u8

### Signature (source notation)

```c
svuint8x3_t svundef3_u8();
```

### Description

Create an uninitialized tuple of three vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Create uninitialized vector tuple

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

Source operation ID: `SveOperation_svundef3_bf16`

**Operation**



Return a tuple of three vectors with arbitrary, undefined contents.



This function can be useful for “seeding” a sequence of operations that cumulatively leaves all active elements in a defined state.

## svundef4_b

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svundef4_b

### Signature (source notation)

```c
svboolx4_t svundef4_b();
```

### Description

Create an uninitialized tuple of four predicate vectors. No instruction is emitted for the uninitialized value itself.

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector tuple manipulation / Create uninitialized vector tuple

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

Not supplied by source.

### Result mapping

Not supplied by source.

### Instruction mapping

Not supplied by source.

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svundef4_bf16

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svundef4_bf16

### Signature (source notation)

```c
svbfloat16x4_t svundef4_bf16();
```

### Description

Create an uninitialized tuple of four vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Create uninitialized vector tuple

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

Source operation ID: `SveOperation_svundef4_bf16`

**Operation**



Return a tuple of four vectors with arbitrary, undefined contents.



This function can be useful for “seeding” a sequence of operations that cumulatively leaves all active elements in a defined state.

## svundef4_f16

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svundef4_f16

### Signature (source notation)

```c
svfloat16x4_t svundef4_f16();
```

### Description

Create an uninitialized tuple of four vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Create uninitialized vector tuple

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

Source operation ID: `SveOperation_svundef4_bf16`

**Operation**



Return a tuple of four vectors with arbitrary, undefined contents.



This function can be useful for “seeding” a sequence of operations that cumulatively leaves all active elements in a defined state.

## svundef4_f32

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svundef4_f32

### Signature (source notation)

```c
svfloat32x4_t svundef4_f32();
```

### Description

Create an uninitialized tuple of four vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Create uninitialized vector tuple

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

Source operation ID: `SveOperation_svundef4_bf16`

**Operation**



Return a tuple of four vectors with arbitrary, undefined contents.



This function can be useful for “seeding” a sequence of operations that cumulatively leaves all active elements in a defined state.

## svundef4_f64

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svundef4_f64

### Signature (source notation)

```c
svfloat64x4_t svundef4_f64();
```

### Description

Create an uninitialized tuple of four vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Create uninitialized vector tuple

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

Source operation ID: `SveOperation_svundef4_bf16`

**Operation**



Return a tuple of four vectors with arbitrary, undefined contents.



This function can be useful for “seeding” a sequence of operations that cumulatively leaves all active elements in a defined state.

## svundef4_mf8

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svundef4_mf8

### Signature (source notation)

```c
svmfloat8x4_t svundef4_mf8();
```

### Description

Create an uninitialized tuple of four vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Create uninitialized vector tuple

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

Source operation ID: `SveOperation_svundef4_bf16`

**Operation**



Return a tuple of four vectors with arbitrary, undefined contents.



This function can be useful for “seeding” a sequence of operations that cumulatively leaves all active elements in a defined state.

## svundef4_s16

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svundef4_s16

### Signature (source notation)

```c
svint16x4_t svundef4_s16();
```

### Description

Create an uninitialized tuple of four vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Create uninitialized vector tuple

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

Source operation ID: `SveOperation_svundef4_bf16`

**Operation**



Return a tuple of four vectors with arbitrary, undefined contents.



This function can be useful for “seeding” a sequence of operations that cumulatively leaves all active elements in a defined state.

## svundef4_s32

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svundef4_s32

### Signature (source notation)

```c
svint32x4_t svundef4_s32();
```

### Description

Create an uninitialized tuple of four vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Create uninitialized vector tuple

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

Source operation ID: `SveOperation_svundef4_bf16`

**Operation**



Return a tuple of four vectors with arbitrary, undefined contents.



This function can be useful for “seeding” a sequence of operations that cumulatively leaves all active elements in a defined state.

## svundef4_s64

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svundef4_s64

### Signature (source notation)

```c
svint64x4_t svundef4_s64();
```

### Description

Create an uninitialized tuple of four vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Create uninitialized vector tuple

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

Source operation ID: `SveOperation_svundef4_bf16`

**Operation**



Return a tuple of four vectors with arbitrary, undefined contents.



This function can be useful for “seeding” a sequence of operations that cumulatively leaves all active elements in a defined state.

## svundef4_s8

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svundef4_s8

### Signature (source notation)

```c
svint8x4_t svundef4_s8();
```

### Description

Create an uninitialized tuple of four vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Create uninitialized vector tuple

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

Source operation ID: `SveOperation_svundef4_bf16`

**Operation**



Return a tuple of four vectors with arbitrary, undefined contents.



This function can be useful for “seeding” a sequence of operations that cumulatively leaves all active elements in a defined state.

## svundef4_u16

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svundef4_u16

### Signature (source notation)

```c
svuint16x4_t svundef4_u16();
```

### Description

Create an uninitialized tuple of four vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Create uninitialized vector tuple

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

Source operation ID: `SveOperation_svundef4_bf16`

**Operation**



Return a tuple of four vectors with arbitrary, undefined contents.



This function can be useful for “seeding” a sequence of operations that cumulatively leaves all active elements in a defined state.

## svundef4_u32

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svundef4_u32

### Signature (source notation)

```c
svuint32x4_t svundef4_u32();
```

### Description

Create an uninitialized tuple of four vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Create uninitialized vector tuple

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

Source operation ID: `SveOperation_svundef4_bf16`

**Operation**



Return a tuple of four vectors with arbitrary, undefined contents.



This function can be useful for “seeding” a sequence of operations that cumulatively leaves all active elements in a defined state.

## svundef4_u64

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svundef4_u64

### Signature (source notation)

```c
svuint64x4_t svundef4_u64();
```

### Description

Create an uninitialized tuple of four vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Create uninitialized vector tuple

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

Source operation ID: `SveOperation_svundef4_bf16`

**Operation**



Return a tuple of four vectors with arbitrary, undefined contents.



This function can be useful for “seeding” a sequence of operations that cumulatively leaves all active elements in a defined state.

## svundef4_u8

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svundef4_u8

### Signature (source notation)

```c
svuint8x4_t svundef4_u8();
```

### Description

Create an uninitialized tuple of four vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Create uninitialized vector tuple

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

Source operation ID: `SveOperation_svundef4_bf16`

**Operation**



Return a tuple of four vectors with arbitrary, undefined contents.



This function can be useful for “seeding” a sequence of operations that cumulatively leaves all active elements in a defined state.

