# SME / Vector manipulation / Create uninitialized vector — Part 1

## svundef_bf16

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svundef_bf16

### Signature (source notation)

```c
svbfloat16_t svundef_bf16();
```

### Description

Create an uninitialized vector

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Create uninitialized vector

- SME attributes: Not specified by source.

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

Source operation ID: `SveOperation_svundef_bf16`

**Operation**



Return a vector with arbitrary, undefined contents.



This function can be useful for “seeding” a sequence of operations that cumulatively leaves all active elements in a defined state.

## svundef_f16

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svundef_f16

### Signature (source notation)

```c
svfloat16_t svundef_f16();
```

### Description

Create an uninitialized vector

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Create uninitialized vector

- SME attributes: Not specified by source.

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

Source operation ID: `SveOperation_svundef_bf16`

**Operation**



Return a vector with arbitrary, undefined contents.



This function can be useful for “seeding” a sequence of operations that cumulatively leaves all active elements in a defined state.

## svundef_f32

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svundef_f32

### Signature (source notation)

```c
svfloat32_t svundef_f32();
```

### Description

Create an uninitialized vector

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Create uninitialized vector

- SME attributes: Not specified by source.

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

Source operation ID: `SveOperation_svundef_bf16`

**Operation**



Return a vector with arbitrary, undefined contents.



This function can be useful for “seeding” a sequence of operations that cumulatively leaves all active elements in a defined state.

## svundef_f64

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svundef_f64

### Signature (source notation)

```c
svfloat64_t svundef_f64();
```

### Description

Create an uninitialized vector

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Create uninitialized vector

- SME attributes: Not specified by source.

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

Source operation ID: `SveOperation_svundef_bf16`

**Operation**



Return a vector with arbitrary, undefined contents.



This function can be useful for “seeding” a sequence of operations that cumulatively leaves all active elements in a defined state.

## svundef_mf8

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svundef_mf8

### Signature (source notation)

```c
svmfloat8_t svundef_mf8();
```

### Description

Create an uninitialized vector

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Create uninitialized vector

- SME attributes: Not specified by source.

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

Source operation ID: `SveOperation_svundef_bf16`

**Operation**



Return a vector with arbitrary, undefined contents.



This function can be useful for “seeding” a sequence of operations that cumulatively leaves all active elements in a defined state.

## svundef_s16

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svundef_s16

### Signature (source notation)

```c
svint16_t svundef_s16();
```

### Description

Create an uninitialized vector

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Create uninitialized vector

- SME attributes: Not specified by source.

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

Source operation ID: `SveOperation_svundef_bf16`

**Operation**



Return a vector with arbitrary, undefined contents.



This function can be useful for “seeding” a sequence of operations that cumulatively leaves all active elements in a defined state.

## svundef_s32

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svundef_s32

### Signature (source notation)

```c
svint32_t svundef_s32();
```

### Description

Create an uninitialized vector

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Create uninitialized vector

- SME attributes: Not specified by source.

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

Source operation ID: `SveOperation_svundef_bf16`

**Operation**



Return a vector with arbitrary, undefined contents.



This function can be useful for “seeding” a sequence of operations that cumulatively leaves all active elements in a defined state.

## svundef_s64

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svundef_s64

### Signature (source notation)

```c
svint64_t svundef_s64();
```

### Description

Create an uninitialized vector

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Create uninitialized vector

- SME attributes: Not specified by source.

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

Source operation ID: `SveOperation_svundef_bf16`

**Operation**



Return a vector with arbitrary, undefined contents.



This function can be useful for “seeding” a sequence of operations that cumulatively leaves all active elements in a defined state.

## svundef_s8

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svundef_s8

### Signature (source notation)

```c
svint8_t svundef_s8();
```

### Description

Create an uninitialized vector

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Create uninitialized vector

- SME attributes: Not specified by source.

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

Source operation ID: `SveOperation_svundef_bf16`

**Operation**



Return a vector with arbitrary, undefined contents.



This function can be useful for “seeding” a sequence of operations that cumulatively leaves all active elements in a defined state.

## svundef_u16

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svundef_u16

### Signature (source notation)

```c
svuint16_t svundef_u16();
```

### Description

Create an uninitialized vector

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Create uninitialized vector

- SME attributes: Not specified by source.

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

Source operation ID: `SveOperation_svundef_bf16`

**Operation**



Return a vector with arbitrary, undefined contents.



This function can be useful for “seeding” a sequence of operations that cumulatively leaves all active elements in a defined state.

## svundef_u32

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svundef_u32

### Signature (source notation)

```c
svuint32_t svundef_u32();
```

### Description

Create an uninitialized vector

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Create uninitialized vector

- SME attributes: Not specified by source.

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

Source operation ID: `SveOperation_svundef_bf16`

**Operation**



Return a vector with arbitrary, undefined contents.



This function can be useful for “seeding” a sequence of operations that cumulatively leaves all active elements in a defined state.

## svundef_u64

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svundef_u64

### Signature (source notation)

```c
svuint64_t svundef_u64();
```

### Description

Create an uninitialized vector

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Create uninitialized vector

- SME attributes: Not specified by source.

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

Source operation ID: `SveOperation_svundef_bf16`

**Operation**



Return a vector with arbitrary, undefined contents.



This function can be useful for “seeding” a sequence of operations that cumulatively leaves all active elements in a defined state.

## svundef_u8

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svundef_u8

### Signature (source notation)

```c
svuint8_t svundef_u8();
```

### Description

Create an uninitialized vector

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Create uninitialized vector

- SME attributes: Not specified by source.

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

Source operation ID: `SveOperation_svundef_bf16`

**Operation**



Return a vector with arbitrary, undefined contents.



This function can be useful for “seeding” a sequence of operations that cumulatively leaves all active elements in a defined state.

