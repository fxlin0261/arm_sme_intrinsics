# SME / Vector manipulation / Create vector — Part 1

## svdupq[_n]_bf16

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdupq%5B_n%5D_bf16

### Signature (source notation)

```c
svbfloat16_t svdupq[_n]_bf16(bfloat16_t x0, bfloat16_t x1, bfloat16_t x2, bfloat16_t x3, bfloat16_t x4, bfloat16_t x5, bfloat16_t x6, bfloat16_t x7);
```

### Description

Broadcast a quadword of scalars

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Create vector

- SME attributes: Not specified by source.

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

Source operation ID: `SveOperation_svdupq_n_bf16`

**Operation**



Return a vector in which element *i* contains `x[i%8]` (where `x[0]` refers to `x0`, and so on).



If the compiler chooses to assemble the parameters into the low 128 bits of a vector, the final step of duplicating it to every quadword is compatible with the .Q form of [DUP (indexed)](https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/DUP--indexed---Broadcast-indexed-element-to-vector--unpredicated--).  However, as with other ACLE functions, the compiler can use any sequence that achieves the same effect.  For example, if the scalar values are constants, it may be more efficient to put them in a constant pool and load them using LD1RQ.

## svdupq[_n]_f16

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdupq%5B_n%5D_f16

### Signature (source notation)

```c
svfloat16_t svdupq[_n]_f16(float16_t x0, float16_t x1, float16_t x2, float16_t x3, float16_t x4, float16_t x5, float16_t x6, float16_t x7);
```

### Description

Broadcast a quadword of scalars

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Create vector

- SME attributes: Not specified by source.

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

Source operation ID: `SveOperation_svdupq_n_bf16`

**Operation**



Return a vector in which element *i* contains `x[i%8]` (where `x[0]` refers to `x0`, and so on).



If the compiler chooses to assemble the parameters into the low 128 bits of a vector, the final step of duplicating it to every quadword is compatible with the .Q form of [DUP (indexed)](https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/DUP--indexed---Broadcast-indexed-element-to-vector--unpredicated--).  However, as with other ACLE functions, the compiler can use any sequence that achieves the same effect.  For example, if the scalar values are constants, it may be more efficient to put them in a constant pool and load them using LD1RQ.

## svdupq[_n]_f32

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdupq%5B_n%5D_f32

### Signature (source notation)

```c
svfloat32_t svdupq[_n]_f32(float32_t x0, float32_t x1, float32_t x2, float32_t x3);
```

### Description

Broadcast a quadword of scalars

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Create vector

- SME attributes: Not specified by source.

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

Source operation ID: `SveOperation_svdupq_n_f32`

**Operation**



Return a vector in which element *i* contains `x[i%4]` (where `x[0]` refers to `x0`, and so on).



If the compiler chooses to assemble the parameters into the low 128 bits of a vector, the final step of duplicating it to every quadword is compatible with the .Q form of [DUP (indexed)](https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/DUP--indexed---Broadcast-indexed-element-to-vector--unpredicated--).  However, as with other ACLE functions, the compiler can use any sequence that achieves the same effect.  For example, if the scalar values are constants, it may be more efficient to put them in a constant pool and load them using LD1RQ.

## svdupq[_n]_f64

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdupq%5B_n%5D_f64

### Signature (source notation)

```c
svfloat64_t svdupq[_n]_f64(float64_t x0, float64_t x1);
```

### Description

Broadcast a quadword of scalars

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Create vector

- SME attributes: Not specified by source.

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

Source operation ID: `SveOperation_svdupq_n_f64`

**Operation**



Return a vector in which element *i* contains `x[i%2]` (where `x[0]` refers to `x0`, and so on).



If the compiler chooses to assemble the parameters into the low 128 bits of a vector, the final step of duplicating it to every quadword is compatible with the .Q form of [DUP (indexed)](https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/DUP--indexed---Broadcast-indexed-element-to-vector--unpredicated--).  However, as with other ACLE functions, the compiler can use any sequence that achieves the same effect.  For example, if the scalar values are constants, it may be more efficient to put them in a constant pool and load them using LD1RQ.

## svdupq[_n]_s16

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdupq%5B_n%5D_s16

### Signature (source notation)

```c
svint16_t svdupq[_n]_s16(int16_t x0, int16_t x1, int16_t x2, int16_t x3, int16_t x4, int16_t x5, int16_t x6, int16_t x7);
```

### Description

Broadcast a quadword of scalars

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Create vector

- SME attributes: Not specified by source.

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

Source operation ID: `SveOperation_svdupq_n_bf16`

**Operation**



Return a vector in which element *i* contains `x[i%8]` (where `x[0]` refers to `x0`, and so on).



If the compiler chooses to assemble the parameters into the low 128 bits of a vector, the final step of duplicating it to every quadword is compatible with the .Q form of [DUP (indexed)](https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/DUP--indexed---Broadcast-indexed-element-to-vector--unpredicated--).  However, as with other ACLE functions, the compiler can use any sequence that achieves the same effect.  For example, if the scalar values are constants, it may be more efficient to put them in a constant pool and load them using LD1RQ.

## svdupq[_n]_s32

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdupq%5B_n%5D_s32

### Signature (source notation)

```c
svint32_t svdupq[_n]_s32(int32_t x0, int32_t x1, int32_t x2, int32_t x3);
```

### Description

Broadcast a quadword of scalars

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Create vector

- SME attributes: Not specified by source.

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

Source operation ID: `SveOperation_svdupq_n_f32`

**Operation**



Return a vector in which element *i* contains `x[i%4]` (where `x[0]` refers to `x0`, and so on).



If the compiler chooses to assemble the parameters into the low 128 bits of a vector, the final step of duplicating it to every quadword is compatible with the .Q form of [DUP (indexed)](https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/DUP--indexed---Broadcast-indexed-element-to-vector--unpredicated--).  However, as with other ACLE functions, the compiler can use any sequence that achieves the same effect.  For example, if the scalar values are constants, it may be more efficient to put them in a constant pool and load them using LD1RQ.

## svdupq[_n]_s64

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdupq%5B_n%5D_s64

### Signature (source notation)

```c
svint64_t svdupq[_n]_s64(int64_t x0, int64_t x1);
```

### Description

Broadcast a quadword of scalars

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Create vector

- SME attributes: Not specified by source.

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

Source operation ID: `SveOperation_svdupq_n_f64`

**Operation**



Return a vector in which element *i* contains `x[i%2]` (where `x[0]` refers to `x0`, and so on).



If the compiler chooses to assemble the parameters into the low 128 bits of a vector, the final step of duplicating it to every quadword is compatible with the .Q form of [DUP (indexed)](https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/DUP--indexed---Broadcast-indexed-element-to-vector--unpredicated--).  However, as with other ACLE functions, the compiler can use any sequence that achieves the same effect.  For example, if the scalar values are constants, it may be more efficient to put them in a constant pool and load them using LD1RQ.

## svdupq[_n]_s8

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdupq%5B_n%5D_s8

### Signature (source notation)

```c
svint8_t svdupq[_n]_s8(int8_t x0, int8_t x1, int8_t x2, int8_t x3, int8_t x4, int8_t x5, int8_t x6, int8_t x7, int8_t x8, int8_t x9, int8_t x10, int8_t x11, int8_t x12, int8_t x13, int8_t x14, int8_t x15);
```

### Description

Broadcast a quadword of scalars

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Create vector

- SME attributes: Not specified by source.

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

Source operation ID: `SveOperation_svdupq_n_s8`

**Operation**



Return a vector in which element *i* contains `x[i%16]` (where `x[0]` refers to `x0`, and so on).



If the compiler chooses to assemble the parameters into the low 128 bits of a vector, the final step of duplicating it to every quadword is compatible with the .Q form of [DUP (indexed)](https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/DUP--indexed---Broadcast-indexed-element-to-vector--unpredicated--).  However, as with other ACLE functions, the compiler can use any sequence that achieves the same effect.  For example, if the scalar values are constants, it may be more efficient to put them in a constant pool and load them using LD1RQ.

## svdupq[_n]_u16

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdupq%5B_n%5D_u16

### Signature (source notation)

```c
svuint16_t svdupq[_n]_u16(uint16_t x0, uint16_t x1, uint16_t x2, uint16_t x3, uint16_t x4, uint16_t x5, uint16_t x6, uint16_t x7);
```

### Description

Broadcast a quadword of scalars

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Create vector

- SME attributes: Not specified by source.

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

Source operation ID: `SveOperation_svdupq_n_bf16`

**Operation**



Return a vector in which element *i* contains `x[i%8]` (where `x[0]` refers to `x0`, and so on).



If the compiler chooses to assemble the parameters into the low 128 bits of a vector, the final step of duplicating it to every quadword is compatible with the .Q form of [DUP (indexed)](https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/DUP--indexed---Broadcast-indexed-element-to-vector--unpredicated--).  However, as with other ACLE functions, the compiler can use any sequence that achieves the same effect.  For example, if the scalar values are constants, it may be more efficient to put them in a constant pool and load them using LD1RQ.

## svdupq[_n]_u32

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdupq%5B_n%5D_u32

### Signature (source notation)

```c
svuint32_t svdupq[_n]_u32(uint32_t x0, uint32_t x1, uint32_t x2, uint32_t x3);
```

### Description

Broadcast a quadword of scalars

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Create vector

- SME attributes: Not specified by source.

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

Source operation ID: `SveOperation_svdupq_n_f32`

**Operation**



Return a vector in which element *i* contains `x[i%4]` (where `x[0]` refers to `x0`, and so on).



If the compiler chooses to assemble the parameters into the low 128 bits of a vector, the final step of duplicating it to every quadword is compatible with the .Q form of [DUP (indexed)](https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/DUP--indexed---Broadcast-indexed-element-to-vector--unpredicated--).  However, as with other ACLE functions, the compiler can use any sequence that achieves the same effect.  For example, if the scalar values are constants, it may be more efficient to put them in a constant pool and load them using LD1RQ.

## svdupq[_n]_u64

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdupq%5B_n%5D_u64

### Signature (source notation)

```c
svuint64_t svdupq[_n]_u64(uint64_t x0, uint64_t x1);
```

### Description

Broadcast a quadword of scalars

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Create vector

- SME attributes: Not specified by source.

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

Source operation ID: `SveOperation_svdupq_n_f64`

**Operation**



Return a vector in which element *i* contains `x[i%2]` (where `x[0]` refers to `x0`, and so on).



If the compiler chooses to assemble the parameters into the low 128 bits of a vector, the final step of duplicating it to every quadword is compatible with the .Q form of [DUP (indexed)](https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/DUP--indexed---Broadcast-indexed-element-to-vector--unpredicated--).  However, as with other ACLE functions, the compiler can use any sequence that achieves the same effect.  For example, if the scalar values are constants, it may be more efficient to put them in a constant pool and load them using LD1RQ.

## svdupq[_n]_u8

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdupq%5B_n%5D_u8

### Signature (source notation)

```c
svuint8_t svdupq[_n]_u8(uint8_t x0, uint8_t x1, uint8_t x2, uint8_t x3, uint8_t x4, uint8_t x5, uint8_t x6, uint8_t x7, uint8_t x8, uint8_t x9, uint8_t x10, uint8_t x11, uint8_t x12, uint8_t x13, uint8_t x14, uint8_t x15);
```

### Description

Broadcast a quadword of scalars

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Create vector

- SME attributes: Not specified by source.

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

Source operation ID: `SveOperation_svdupq_n_s8`

**Operation**



Return a vector in which element *i* contains `x[i%16]` (where `x[0]` refers to `x0`, and so on).



If the compiler chooses to assemble the parameters into the low 128 bits of a vector, the final step of duplicating it to every quadword is compatible with the .Q form of [DUP (indexed)](https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/DUP--indexed---Broadcast-indexed-element-to-vector--unpredicated--).  However, as with other ACLE functions, the compiler can use any sequence that achieves the same effect.  For example, if the scalar values are constants, it may be more efficient to put them in a constant pool and load them using LD1RQ.

## svdupq_lane[_bf16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdupq_lane%5B_bf16%5D

### Signature (source notation)

```c
svbfloat16_t svdupq_lane[_bf16](svbfloat16_t data, uint64_t index);
```

### Description

Broadcast a quadword of scalars

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Create vector

- SME attributes: Not specified by source.

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
  "data": {
    "register": "Zdata.D|Zdata.Q"
  },
  "{2 * index, 2 * index + 1, 2 * index, 2 * index + 1, …}": {
    "register": "Zindices_d.D"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.D|Zresult.Q": "result"
  }
]
```

### Instruction mapping

When index is in the range [0, 3], this intrinsic can use:

```asm
DUP Zresult.Q, Zdata.Q[index]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/DUP--indexed---Broadcast-indexed-element-to-vector--unpredicated--

The general implementation is:

```asm
TBL Zresult.D, Zdata.D, Zindices_d.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/TBL--Programmable-table-lookup-in-one-or-two-vector-table--zeroing--

### Operation

Source operation ID: `SveOperation_svdupq_lane_bf16`

**Operation**



If `index` is less than the number of 128-bit quadwords in `data`, return a vector in which element *i* contains `data[index * 8 + (i % 8)]`.  Return an all-zero vector otherwise.



Only the low 63 bits of `index` are significant.

## svdupq_lane[_f16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdupq_lane%5B_f16%5D

### Signature (source notation)

```c
svfloat16_t svdupq_lane[_f16](svfloat16_t data, uint64_t index);
```

### Description

Broadcast a quadword of scalars

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Create vector

- SME attributes: Not specified by source.

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
  "data": {
    "register": "Zdata.D|Zdata.Q"
  },
  "{2 * index, 2 * index + 1, 2 * index, 2 * index + 1, …}": {
    "register": "Zindices_d.D"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.D|Zresult.Q": "result"
  }
]
```

### Instruction mapping

When index is in the range [0, 3], this intrinsic can use:

```asm
DUP Zresult.Q, Zdata.Q[index]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/DUP--indexed---Broadcast-indexed-element-to-vector--unpredicated--

The general implementation is:

```asm
TBL Zresult.D, Zdata.D, Zindices_d.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/TBL--Programmable-table-lookup-in-one-or-two-vector-table--zeroing--

### Operation

Source operation ID: `SveOperation_svdupq_lane_bf16`

**Operation**



If `index` is less than the number of 128-bit quadwords in `data`, return a vector in which element *i* contains `data[index * 8 + (i % 8)]`.  Return an all-zero vector otherwise.



Only the low 63 bits of `index` are significant.

## svdupq_lane[_f32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdupq_lane%5B_f32%5D

### Signature (source notation)

```c
svfloat32_t svdupq_lane[_f32](svfloat32_t data, uint64_t index);
```

### Description

Broadcast a quadword of scalars

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Create vector

- SME attributes: Not specified by source.

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
  "data": {
    "register": "Zdata.D|Zdata.Q"
  },
  "{2 * index, 2 * index + 1, 2 * index, 2 * index + 1, …}": {
    "register": "Zindices_d.D"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.D|Zresult.Q": "result"
  }
]
```

### Instruction mapping

When index is in the range [0, 3], this intrinsic can use:

```asm
DUP Zresult.Q, Zdata.Q[index]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/DUP--indexed---Broadcast-indexed-element-to-vector--unpredicated--

The general implementation is:

```asm
TBL Zresult.D, Zdata.D, Zindices_d.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/TBL--Programmable-table-lookup-in-one-or-two-vector-table--zeroing--

### Operation

Source operation ID: `SveOperation_svdupq_lane_f32`

**Operation**



If `index` is less than the number of 128-bit quadwords in `data`, return a vector in which element *i* contains `data[index * 4 + (i % 4)]`.  Return an all-zero vector otherwise.



Only the low 63 bits of `index` are significant.

## svdupq_lane[_f64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdupq_lane%5B_f64%5D

### Signature (source notation)

```c
svfloat64_t svdupq_lane[_f64](svfloat64_t data, uint64_t index);
```

### Description

Broadcast a quadword of scalars

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Create vector

- SME attributes: Not specified by source.

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
  "data": {
    "register": "Zdata.D|Zdata.Q"
  },
  "{2 * index, 2 * index + 1, 2 * index, 2 * index + 1, …}": {
    "register": "Zindices_d.D"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.D|Zresult.Q": "result"
  }
]
```

### Instruction mapping

When index is in the range [0, 3], this intrinsic can use:

```asm
DUP Zresult.Q, Zdata.Q[index]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/DUP--indexed---Broadcast-indexed-element-to-vector--unpredicated--

The general implementation is:

```asm
TBL Zresult.D, Zdata.D, Zindices_d.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/TBL--Programmable-table-lookup-in-one-or-two-vector-table--zeroing--

### Operation

Source operation ID: `SveOperation_svdupq_lane_f64`

**Operation**



If `index` is less than the number of 128-bit quadwords in `data`, return a vector in which element *i* contains `data[index * 2 + (i % 2)]`.  Return an all-zero vector otherwise.



Only the low 63 bits of `index` are significant.

## svdupq_lane[_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdupq_lane%5B_s16%5D

### Signature (source notation)

```c
svint16_t svdupq_lane[_s16](svint16_t data, uint64_t index);
```

### Description

Broadcast a quadword of scalars

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Create vector

- SME attributes: Not specified by source.

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
  "data": {
    "register": "Zdata.D|Zdata.Q"
  },
  "{2 * index, 2 * index + 1, 2 * index, 2 * index + 1, …}": {
    "register": "Zindices_d.D"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.D|Zresult.Q": "result"
  }
]
```

### Instruction mapping

When index is in the range [0, 3], this intrinsic can use:

```asm
DUP Zresult.Q, Zdata.Q[index]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/DUP--indexed---Broadcast-indexed-element-to-vector--unpredicated--

The general implementation is:

```asm
TBL Zresult.D, Zdata.D, Zindices_d.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/TBL--Programmable-table-lookup-in-one-or-two-vector-table--zeroing--

### Operation

Source operation ID: `SveOperation_svdupq_lane_bf16`

**Operation**



If `index` is less than the number of 128-bit quadwords in `data`, return a vector in which element *i* contains `data[index * 8 + (i % 8)]`.  Return an all-zero vector otherwise.



Only the low 63 bits of `index` are significant.

## svdupq_lane[_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdupq_lane%5B_s32%5D

### Signature (source notation)

```c
svint32_t svdupq_lane[_s32](svint32_t data, uint64_t index);
```

### Description

Broadcast a quadword of scalars

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Create vector

- SME attributes: Not specified by source.

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
  "data": {
    "register": "Zdata.D|Zdata.Q"
  },
  "{2 * index, 2 * index + 1, 2 * index, 2 * index + 1, …}": {
    "register": "Zindices_d.D"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.D|Zresult.Q": "result"
  }
]
```

### Instruction mapping

When index is in the range [0, 3], this intrinsic can use:

```asm
DUP Zresult.Q, Zdata.Q[index]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/DUP--indexed---Broadcast-indexed-element-to-vector--unpredicated--

The general implementation is:

```asm
TBL Zresult.D, Zdata.D, Zindices_d.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/TBL--Programmable-table-lookup-in-one-or-two-vector-table--zeroing--

### Operation

Source operation ID: `SveOperation_svdupq_lane_f32`

**Operation**



If `index` is less than the number of 128-bit quadwords in `data`, return a vector in which element *i* contains `data[index * 4 + (i % 4)]`.  Return an all-zero vector otherwise.



Only the low 63 bits of `index` are significant.

## svdupq_lane[_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdupq_lane%5B_s64%5D

### Signature (source notation)

```c
svint64_t svdupq_lane[_s64](svint64_t data, uint64_t index);
```

### Description

Broadcast a quadword of scalars

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Create vector

- SME attributes: Not specified by source.

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
  "data": {
    "register": "Zdata.D|Zdata.Q"
  },
  "{2 * index, 2 * index + 1, 2 * index, 2 * index + 1, …}": {
    "register": "Zindices_d.D"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.D|Zresult.Q": "result"
  }
]
```

### Instruction mapping

When index is in the range [0, 3], this intrinsic can use:

```asm
DUP Zresult.Q, Zdata.Q[index]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/DUP--indexed---Broadcast-indexed-element-to-vector--unpredicated--

The general implementation is:

```asm
TBL Zresult.D, Zdata.D, Zindices_d.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/TBL--Programmable-table-lookup-in-one-or-two-vector-table--zeroing--

### Operation

Source operation ID: `SveOperation_svdupq_lane_f64`

**Operation**



If `index` is less than the number of 128-bit quadwords in `data`, return a vector in which element *i* contains `data[index * 2 + (i % 2)]`.  Return an all-zero vector otherwise.



Only the low 63 bits of `index` are significant.

## svdupq_lane[_s8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdupq_lane%5B_s8%5D

### Signature (source notation)

```c
svint8_t svdupq_lane[_s8](svint8_t data, uint64_t index);
```

### Description

Broadcast a quadword of scalars

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Create vector

- SME attributes: Not specified by source.

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
  "data": {
    "register": "Zdata.D|Zdata.Q"
  },
  "{2 * index, 2 * index + 1, 2 * index, 2 * index + 1, …}": {
    "register": "Zindices_d.D"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.D|Zresult.Q": "result"
  }
]
```

### Instruction mapping

When index is in the range [0, 3], this intrinsic can use:

```asm
DUP Zresult.Q, Zdata.Q[index]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/DUP--indexed---Broadcast-indexed-element-to-vector--unpredicated--

The general implementation is:

```asm
TBL Zresult.D, Zdata.D, Zindices_d.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/TBL--Programmable-table-lookup-in-one-or-two-vector-table--zeroing--

### Operation

Source operation ID: `SveOperation_svdupq_lane_s8`

**Operation**



If `index` is less than the number of 128-bit quadwords in `data`, return a vector in which element *i* contains `data[index * 16 + (i % 16)]`.  Return an all-zero vector otherwise.



Only the low 63 bits of `index` are significant.

## svdupq_lane[_u16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdupq_lane%5B_u16%5D

### Signature (source notation)

```c
svuint16_t svdupq_lane[_u16](svuint16_t data, uint64_t index);
```

### Description

Broadcast a quadword of scalars

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Create vector

- SME attributes: Not specified by source.

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
  "data": {
    "register": "Zdata.D|Zdata.Q"
  },
  "{2 * index, 2 * index + 1, 2 * index, 2 * index + 1, …}": {
    "register": "Zindices_d.D"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.D|Zresult.Q": "result"
  }
]
```

### Instruction mapping

When index is in the range [0, 3], this intrinsic can use:

```asm
DUP Zresult.Q, Zdata.Q[index]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/DUP--indexed---Broadcast-indexed-element-to-vector--unpredicated--

The general implementation is:

```asm
TBL Zresult.D, Zdata.D, Zindices_d.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/TBL--Programmable-table-lookup-in-one-or-two-vector-table--zeroing--

### Operation

Source operation ID: `SveOperation_svdupq_lane_bf16`

**Operation**



If `index` is less than the number of 128-bit quadwords in `data`, return a vector in which element *i* contains `data[index * 8 + (i % 8)]`.  Return an all-zero vector otherwise.



Only the low 63 bits of `index` are significant.

## svdupq_lane[_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdupq_lane%5B_u32%5D

### Signature (source notation)

```c
svuint32_t svdupq_lane[_u32](svuint32_t data, uint64_t index);
```

### Description

Broadcast a quadword of scalars

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Create vector

- SME attributes: Not specified by source.

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
  "data": {
    "register": "Zdata.D|Zdata.Q"
  },
  "{2 * index, 2 * index + 1, 2 * index, 2 * index + 1, …}": {
    "register": "Zindices_d.D"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.D|Zresult.Q": "result"
  }
]
```

### Instruction mapping

When index is in the range [0, 3], this intrinsic can use:

```asm
DUP Zresult.Q, Zdata.Q[index]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/DUP--indexed---Broadcast-indexed-element-to-vector--unpredicated--

The general implementation is:

```asm
TBL Zresult.D, Zdata.D, Zindices_d.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/TBL--Programmable-table-lookup-in-one-or-two-vector-table--zeroing--

### Operation

Source operation ID: `SveOperation_svdupq_lane_f32`

**Operation**



If `index` is less than the number of 128-bit quadwords in `data`, return a vector in which element *i* contains `data[index * 4 + (i % 4)]`.  Return an all-zero vector otherwise.



Only the low 63 bits of `index` are significant.

## svdupq_lane[_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdupq_lane%5B_u64%5D

### Signature (source notation)

```c
svuint64_t svdupq_lane[_u64](svuint64_t data, uint64_t index);
```

### Description

Broadcast a quadword of scalars

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Create vector

- SME attributes: Not specified by source.

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
  "data": {
    "register": "Zdata.D|Zdata.Q"
  },
  "{2 * index, 2 * index + 1, 2 * index, 2 * index + 1, …}": {
    "register": "Zindices_d.D"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.D|Zresult.Q": "result"
  }
]
```

### Instruction mapping

When index is in the range [0, 3], this intrinsic can use:

```asm
DUP Zresult.Q, Zdata.Q[index]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/DUP--indexed---Broadcast-indexed-element-to-vector--unpredicated--

The general implementation is:

```asm
TBL Zresult.D, Zdata.D, Zindices_d.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/TBL--Programmable-table-lookup-in-one-or-two-vector-table--zeroing--

### Operation

Source operation ID: `SveOperation_svdupq_lane_f64`

**Operation**



If `index` is less than the number of 128-bit quadwords in `data`, return a vector in which element *i* contains `data[index * 2 + (i % 2)]`.  Return an all-zero vector otherwise.



Only the low 63 bits of `index` are significant.

## svdupq_lane[_u8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdupq_lane%5B_u8%5D

### Signature (source notation)

```c
svuint8_t svdupq_lane[_u8](svuint8_t data, uint64_t index);
```

### Description

Broadcast a quadword of scalars

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Create vector

- SME attributes: Not specified by source.

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
  "data": {
    "register": "Zdata.D|Zdata.Q"
  },
  "{2 * index, 2 * index + 1, 2 * index, 2 * index + 1, …}": {
    "register": "Zindices_d.D"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.D|Zresult.Q": "result"
  }
]
```

### Instruction mapping

When index is in the range [0, 3], this intrinsic can use:

```asm
DUP Zresult.Q, Zdata.Q[index]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/DUP--indexed---Broadcast-indexed-element-to-vector--unpredicated--

The general implementation is:

```asm
TBL Zresult.D, Zdata.D, Zindices_d.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/TBL--Programmable-table-lookup-in-one-or-two-vector-table--zeroing--

### Operation

Source operation ID: `SveOperation_svdupq_lane_s8`

**Operation**



If `index` is less than the number of 128-bit quadwords in `data`, return a vector in which element *i* contains `data[index * 16 + (i % 16)]`.  Return an all-zero vector otherwise.



Only the low 63 bits of `index` are significant.

