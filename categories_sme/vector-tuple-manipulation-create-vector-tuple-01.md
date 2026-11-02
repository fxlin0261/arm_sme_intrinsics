# SME / Vector tuple manipulation / Create vector tuple — Part 1

## svcreate2[_b]

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcreate2%5B_b%5D

### Signature (source notation)

```c
svboolx2_t svcreate2[_b](svbool_t x, svbool_t y);
```

### Description

Create a tuple of two predicate vectors. The tuple construction has no fixed instruction sequence; any emitted moves are register-allocation dependent.

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector tuple manipulation / Create vector tuple

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

## svcreate2[_bf16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcreate2%5B_bf16%5D

### Signature (source notation)

```c
svbfloat16x2_t svcreate2[_bf16](svbfloat16_t x0, svbfloat16_t x1);
```

### Description

Create a tuple of two vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Create vector tuple

- SME attributes: Not specified by source.

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

Source operation ID: `SveOperation_svcreate2_bf16`

**Operation**



Combine `x0` and `x1` into a tuple of two vectors.

## svcreate2[_f16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcreate2%5B_f16%5D

### Signature (source notation)

```c
svfloat16x2_t svcreate2[_f16](svfloat16_t x0, svfloat16_t x1);
```

### Description

Create a tuple of two vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Create vector tuple

- SME attributes: Not specified by source.

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

Source operation ID: `SveOperation_svcreate2_bf16`

**Operation**



Combine `x0` and `x1` into a tuple of two vectors.

## svcreate2[_f32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcreate2%5B_f32%5D

### Signature (source notation)

```c
svfloat32x2_t svcreate2[_f32](svfloat32_t x0, svfloat32_t x1);
```

### Description

Create a tuple of two vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Create vector tuple

- SME attributes: Not specified by source.

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

Source operation ID: `SveOperation_svcreate2_bf16`

**Operation**



Combine `x0` and `x1` into a tuple of two vectors.

## svcreate2[_f64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcreate2%5B_f64%5D

### Signature (source notation)

```c
svfloat64x2_t svcreate2[_f64](svfloat64_t x0, svfloat64_t x1);
```

### Description

Create a tuple of two vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Create vector tuple

- SME attributes: Not specified by source.

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

Source operation ID: `SveOperation_svcreate2_bf16`

**Operation**



Combine `x0` and `x1` into a tuple of two vectors.

## svcreate2[_mf8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcreate2%5B_mf8%5D

### Signature (source notation)

```c
svmfloat8x2_t svcreate2[_mf8](svmfloat8_t x0, svmfloat8_t x1);
```

### Description

Create a tuple of two vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Create vector tuple

- SME attributes: Not specified by source.

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

Source operation ID: `SveOperation_svcreate2_bf16`

**Operation**



Combine `x0` and `x1` into a tuple of two vectors.

## svcreate2[_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcreate2%5B_s16%5D

### Signature (source notation)

```c
svint16x2_t svcreate2[_s16](svint16_t x0, svint16_t x1);
```

### Description

Create a tuple of two vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Create vector tuple

- SME attributes: Not specified by source.

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

Source operation ID: `SveOperation_svcreate2_bf16`

**Operation**



Combine `x0` and `x1` into a tuple of two vectors.

## svcreate2[_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcreate2%5B_s32%5D

### Signature (source notation)

```c
svint32x2_t svcreate2[_s32](svint32_t x0, svint32_t x1);
```

### Description

Create a tuple of two vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Create vector tuple

- SME attributes: Not specified by source.

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

Source operation ID: `SveOperation_svcreate2_bf16`

**Operation**



Combine `x0` and `x1` into a tuple of two vectors.

## svcreate2[_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcreate2%5B_s64%5D

### Signature (source notation)

```c
svint64x2_t svcreate2[_s64](svint64_t x0, svint64_t x1);
```

### Description

Create a tuple of two vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Create vector tuple

- SME attributes: Not specified by source.

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

Source operation ID: `SveOperation_svcreate2_bf16`

**Operation**



Combine `x0` and `x1` into a tuple of two vectors.

## svcreate2[_s8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcreate2%5B_s8%5D

### Signature (source notation)

```c
svint8x2_t svcreate2[_s8](svint8_t x0, svint8_t x1);
```

### Description

Create a tuple of two vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Create vector tuple

- SME attributes: Not specified by source.

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

Source operation ID: `SveOperation_svcreate2_bf16`

**Operation**



Combine `x0` and `x1` into a tuple of two vectors.

## svcreate2[_u16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcreate2%5B_u16%5D

### Signature (source notation)

```c
svuint16x2_t svcreate2[_u16](svuint16_t x0, svuint16_t x1);
```

### Description

Create a tuple of two vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Create vector tuple

- SME attributes: Not specified by source.

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

Source operation ID: `SveOperation_svcreate2_bf16`

**Operation**



Combine `x0` and `x1` into a tuple of two vectors.

## svcreate2[_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcreate2%5B_u32%5D

### Signature (source notation)

```c
svuint32x2_t svcreate2[_u32](svuint32_t x0, svuint32_t x1);
```

### Description

Create a tuple of two vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Create vector tuple

- SME attributes: Not specified by source.

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

Source operation ID: `SveOperation_svcreate2_bf16`

**Operation**



Combine `x0` and `x1` into a tuple of two vectors.

## svcreate2[_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcreate2%5B_u64%5D

### Signature (source notation)

```c
svuint64x2_t svcreate2[_u64](svuint64_t x0, svuint64_t x1);
```

### Description

Create a tuple of two vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Create vector tuple

- SME attributes: Not specified by source.

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

Source operation ID: `SveOperation_svcreate2_bf16`

**Operation**



Combine `x0` and `x1` into a tuple of two vectors.

## svcreate2[_u8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcreate2%5B_u8%5D

### Signature (source notation)

```c
svuint8x2_t svcreate2[_u8](svuint8_t x0, svuint8_t x1);
```

### Description

Create a tuple of two vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Create vector tuple

- SME attributes: Not specified by source.

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

Source operation ID: `SveOperation_svcreate2_bf16`

**Operation**



Combine `x0` and `x1` into a tuple of two vectors.

## svcreate3[_bf16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcreate3%5B_bf16%5D

### Signature (source notation)

```c
svbfloat16x3_t svcreate3[_bf16](svbfloat16_t x0, svbfloat16_t x1, svbfloat16_t x2);
```

### Description

Create a tuple of three vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Create vector tuple

- SME attributes: Not specified by source.

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

Source operation ID: `SveOperation_svcreate3_bf16`

**Operation**



Combine `x0`, `x1` and `x2` into a tuple of three vectors.

## svcreate3[_f16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcreate3%5B_f16%5D

### Signature (source notation)

```c
svfloat16x3_t svcreate3[_f16](svfloat16_t x0, svfloat16_t x1, svfloat16_t x2);
```

### Description

Create a tuple of three vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Create vector tuple

- SME attributes: Not specified by source.

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

Source operation ID: `SveOperation_svcreate3_bf16`

**Operation**



Combine `x0`, `x1` and `x2` into a tuple of three vectors.

## svcreate3[_f32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcreate3%5B_f32%5D

### Signature (source notation)

```c
svfloat32x3_t svcreate3[_f32](svfloat32_t x0, svfloat32_t x1, svfloat32_t x2);
```

### Description

Create a tuple of three vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Create vector tuple

- SME attributes: Not specified by source.

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

Source operation ID: `SveOperation_svcreate3_bf16`

**Operation**



Combine `x0`, `x1` and `x2` into a tuple of three vectors.

## svcreate3[_f64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcreate3%5B_f64%5D

### Signature (source notation)

```c
svfloat64x3_t svcreate3[_f64](svfloat64_t x0, svfloat64_t x1, svfloat64_t x2);
```

### Description

Create a tuple of three vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Create vector tuple

- SME attributes: Not specified by source.

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

Source operation ID: `SveOperation_svcreate3_bf16`

**Operation**



Combine `x0`, `x1` and `x2` into a tuple of three vectors.

## svcreate3[_mf8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcreate3%5B_mf8%5D

### Signature (source notation)

```c
svmfloat8x3_t svcreate3[_mf8](svmfloat8_t x0, svmfloat8_t x1, svmfloat8_t x2);
```

### Description

Create a tuple of three vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Create vector tuple

- SME attributes: Not specified by source.

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

Source operation ID: `SveOperation_svcreate3_bf16`

**Operation**



Combine `x0`, `x1` and `x2` into a tuple of three vectors.

## svcreate3[_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcreate3%5B_s16%5D

### Signature (source notation)

```c
svint16x3_t svcreate3[_s16](svint16_t x0, svint16_t x1, svint16_t x2);
```

### Description

Create a tuple of three vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Create vector tuple

- SME attributes: Not specified by source.

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

Source operation ID: `SveOperation_svcreate3_bf16`

**Operation**



Combine `x0`, `x1` and `x2` into a tuple of three vectors.

## svcreate3[_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcreate3%5B_s32%5D

### Signature (source notation)

```c
svint32x3_t svcreate3[_s32](svint32_t x0, svint32_t x1, svint32_t x2);
```

### Description

Create a tuple of three vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Create vector tuple

- SME attributes: Not specified by source.

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

Source operation ID: `SveOperation_svcreate3_bf16`

**Operation**



Combine `x0`, `x1` and `x2` into a tuple of three vectors.

## svcreate3[_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcreate3%5B_s64%5D

### Signature (source notation)

```c
svint64x3_t svcreate3[_s64](svint64_t x0, svint64_t x1, svint64_t x2);
```

### Description

Create a tuple of three vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Create vector tuple

- SME attributes: Not specified by source.

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

Source operation ID: `SveOperation_svcreate3_bf16`

**Operation**



Combine `x0`, `x1` and `x2` into a tuple of three vectors.

## svcreate3[_s8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcreate3%5B_s8%5D

### Signature (source notation)

```c
svint8x3_t svcreate3[_s8](svint8_t x0, svint8_t x1, svint8_t x2);
```

### Description

Create a tuple of three vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Create vector tuple

- SME attributes: Not specified by source.

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

Source operation ID: `SveOperation_svcreate3_bf16`

**Operation**



Combine `x0`, `x1` and `x2` into a tuple of three vectors.

## svcreate3[_u16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcreate3%5B_u16%5D

### Signature (source notation)

```c
svuint16x3_t svcreate3[_u16](svuint16_t x0, svuint16_t x1, svuint16_t x2);
```

### Description

Create a tuple of three vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Create vector tuple

- SME attributes: Not specified by source.

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

Source operation ID: `SveOperation_svcreate3_bf16`

**Operation**



Combine `x0`, `x1` and `x2` into a tuple of three vectors.

## svcreate3[_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcreate3%5B_u32%5D

### Signature (source notation)

```c
svuint32x3_t svcreate3[_u32](svuint32_t x0, svuint32_t x1, svuint32_t x2);
```

### Description

Create a tuple of three vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Create vector tuple

- SME attributes: Not specified by source.

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

Source operation ID: `SveOperation_svcreate3_bf16`

**Operation**



Combine `x0`, `x1` and `x2` into a tuple of three vectors.

## svcreate3[_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcreate3%5B_u64%5D

### Signature (source notation)

```c
svuint64x3_t svcreate3[_u64](svuint64_t x0, svuint64_t x1, svuint64_t x2);
```

### Description

Create a tuple of three vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Create vector tuple

- SME attributes: Not specified by source.

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

Source operation ID: `SveOperation_svcreate3_bf16`

**Operation**



Combine `x0`, `x1` and `x2` into a tuple of three vectors.

## svcreate3[_u8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcreate3%5B_u8%5D

### Signature (source notation)

```c
svuint8x3_t svcreate3[_u8](svuint8_t x0, svuint8_t x1, svuint8_t x2);
```

### Description

Create a tuple of three vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Create vector tuple

- SME attributes: Not specified by source.

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

Source operation ID: `SveOperation_svcreate3_bf16`

**Operation**



Combine `x0`, `x1` and `x2` into a tuple of three vectors.

## svcreate4[_b]

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcreate4%5B_b%5D

### Signature (source notation)

```c
svboolx4_t svcreate4[_b](svbool_t x, svbool_t y, svbool_t z, svbool_t w);
```

### Description

Create a tuple of four predicate vectors. The tuple construction has no fixed instruction sequence; any emitted moves are register-allocation dependent.

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector tuple manipulation / Create vector tuple

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

## svcreate4[_bf16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcreate4%5B_bf16%5D

### Signature (source notation)

```c
svbfloat16x4_t svcreate4[_bf16](svbfloat16_t x0, svbfloat16_t x1, svbfloat16_t x2, svbfloat16_t x3);
```

### Description

Create a tuple of four vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Create vector tuple

- SME attributes: Not specified by source.

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

Source operation ID: `SveOperation_svcreate4_bf16`

**Operation**



Combine `x0`, `x1`, `x2` and `x3` into a tuple of four vectors.

## svcreate4[_f16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcreate4%5B_f16%5D

### Signature (source notation)

```c
svfloat16x4_t svcreate4[_f16](svfloat16_t x0, svfloat16_t x1, svfloat16_t x2, svfloat16_t x3);
```

### Description

Create a tuple of four vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Create vector tuple

- SME attributes: Not specified by source.

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

Source operation ID: `SveOperation_svcreate4_bf16`

**Operation**



Combine `x0`, `x1`, `x2` and `x3` into a tuple of four vectors.

## svcreate4[_f32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcreate4%5B_f32%5D

### Signature (source notation)

```c
svfloat32x4_t svcreate4[_f32](svfloat32_t x0, svfloat32_t x1, svfloat32_t x2, svfloat32_t x3);
```

### Description

Create a tuple of four vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Create vector tuple

- SME attributes: Not specified by source.

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

Source operation ID: `SveOperation_svcreate4_bf16`

**Operation**



Combine `x0`, `x1`, `x2` and `x3` into a tuple of four vectors.

## svcreate4[_f64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcreate4%5B_f64%5D

### Signature (source notation)

```c
svfloat64x4_t svcreate4[_f64](svfloat64_t x0, svfloat64_t x1, svfloat64_t x2, svfloat64_t x3);
```

### Description

Create a tuple of four vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Create vector tuple

- SME attributes: Not specified by source.

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

Source operation ID: `SveOperation_svcreate4_bf16`

**Operation**



Combine `x0`, `x1`, `x2` and `x3` into a tuple of four vectors.

## svcreate4[_mf8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcreate4%5B_mf8%5D

### Signature (source notation)

```c
svmfloat8x4_t svcreate4[_mf8](svmfloat8_t x0, svmfloat8_t x1, svmfloat8_t x2, svmfloat8_t x3);
```

### Description

Create a tuple of four vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Create vector tuple

- SME attributes: Not specified by source.

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

Source operation ID: `SveOperation_svcreate4_bf16`

**Operation**



Combine `x0`, `x1`, `x2` and `x3` into a tuple of four vectors.

## svcreate4[_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcreate4%5B_s16%5D

### Signature (source notation)

```c
svint16x4_t svcreate4[_s16](svint16_t x0, svint16_t x1, svint16_t x2, svint16_t x3);
```

### Description

Create a tuple of four vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Create vector tuple

- SME attributes: Not specified by source.

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

Source operation ID: `SveOperation_svcreate4_bf16`

**Operation**



Combine `x0`, `x1`, `x2` and `x3` into a tuple of four vectors.

## svcreate4[_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcreate4%5B_s32%5D

### Signature (source notation)

```c
svint32x4_t svcreate4[_s32](svint32_t x0, svint32_t x1, svint32_t x2, svint32_t x3);
```

### Description

Create a tuple of four vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Create vector tuple

- SME attributes: Not specified by source.

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

Source operation ID: `SveOperation_svcreate4_bf16`

**Operation**



Combine `x0`, `x1`, `x2` and `x3` into a tuple of four vectors.

## svcreate4[_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcreate4%5B_s64%5D

### Signature (source notation)

```c
svint64x4_t svcreate4[_s64](svint64_t x0, svint64_t x1, svint64_t x2, svint64_t x3);
```

### Description

Create a tuple of four vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Create vector tuple

- SME attributes: Not specified by source.

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

Source operation ID: `SveOperation_svcreate4_bf16`

**Operation**



Combine `x0`, `x1`, `x2` and `x3` into a tuple of four vectors.

## svcreate4[_s8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcreate4%5B_s8%5D

### Signature (source notation)

```c
svint8x4_t svcreate4[_s8](svint8_t x0, svint8_t x1, svint8_t x2, svint8_t x3);
```

### Description

Create a tuple of four vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Create vector tuple

- SME attributes: Not specified by source.

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

Source operation ID: `SveOperation_svcreate4_bf16`

**Operation**



Combine `x0`, `x1`, `x2` and `x3` into a tuple of four vectors.

## svcreate4[_u16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcreate4%5B_u16%5D

### Signature (source notation)

```c
svuint16x4_t svcreate4[_u16](svuint16_t x0, svuint16_t x1, svuint16_t x2, svuint16_t x3);
```

### Description

Create a tuple of four vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Create vector tuple

- SME attributes: Not specified by source.

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

Source operation ID: `SveOperation_svcreate4_bf16`

**Operation**



Combine `x0`, `x1`, `x2` and `x3` into a tuple of four vectors.

## svcreate4[_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcreate4%5B_u32%5D

### Signature (source notation)

```c
svuint32x4_t svcreate4[_u32](svuint32_t x0, svuint32_t x1, svuint32_t x2, svuint32_t x3);
```

### Description

Create a tuple of four vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Create vector tuple

- SME attributes: Not specified by source.

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

Source operation ID: `SveOperation_svcreate4_bf16`

**Operation**



Combine `x0`, `x1`, `x2` and `x3` into a tuple of four vectors.

## svcreate4[_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcreate4%5B_u64%5D

### Signature (source notation)

```c
svuint64x4_t svcreate4[_u64](svuint64_t x0, svuint64_t x1, svuint64_t x2, svuint64_t x3);
```

### Description

Create a tuple of four vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Create vector tuple

- SME attributes: Not specified by source.

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

Source operation ID: `SveOperation_svcreate4_bf16`

**Operation**



Combine `x0`, `x1`, `x2` and `x3` into a tuple of four vectors.

## svcreate4[_u8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcreate4%5B_u8%5D

### Signature (source notation)

```c
svuint8x4_t svcreate4[_u8](svuint8_t x0, svuint8_t x1, svuint8_t x2, svuint8_t x3);
```

### Description

Create a tuple of four vectors

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector tuple manipulation / Create vector tuple

- SME attributes: Not specified by source.

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

Source operation ID: `SveOperation_svcreate4_bf16`

**Operation**



Combine `x0`, `x1`, `x2` and `x3` into a tuple of four vectors.

