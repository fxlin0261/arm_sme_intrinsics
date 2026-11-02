# SME / Vector arithmetic / Multiply / Saturating multiply — Part 1

## svqdmulh[_n_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdmulh%5B_n_s16%5D

### Signature (source notation)

```c
svint16_t svqdmulh[_n_s16](svint16_t op1, int16_t op2);
```

### Description

Saturating doubling multiply high

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply / Saturating multiply

- SME attributes: Not specified by source.

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
    "register": "Zop1.H"
  },
  "op2": {
    "register": "Zop2.H[*]"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.H": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
SQDMULH Zresult.H, Zop1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDMULH--vectors---Signed-saturating-doubling-multiply-high--unpredicated--

### Operation

Source operation ID: `SveOperation_svqdmulh_n_s16`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Multiply `op1[i]` by `op2`, without loss of precision.
- Divide the result by 2 to the power 15, rounding towards -∞.
- Saturate the result to the range of `int16_t`.

## svqdmulh[_n_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdmulh%5B_n_s32%5D

### Signature (source notation)

```c
svint32_t svqdmulh[_n_s32](svint32_t op1, int32_t op2);
```

### Description

Saturating doubling multiply high

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply / Saturating multiply

- SME attributes: Not specified by source.

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
    "register": "Zop1.S"
  },
  "op2": {
    "register": "Zop2.S[*]"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.S": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
SQDMULH Zresult.S, Zop1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDMULH--vectors---Signed-saturating-doubling-multiply-high--unpredicated--

### Operation

Source operation ID: `SveOperation_svqdmulh_n_s32`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Multiply `op1[i]` by `op2`, without loss of precision.
- Divide the result by 2 to the power 31, rounding towards -∞.
- Saturate the result to the range of `int32_t`.

## svqdmulh[_n_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdmulh%5B_n_s64%5D

### Signature (source notation)

```c
svint64_t svqdmulh[_n_s64](svint64_t op1, int64_t op2);
```

### Description

Saturating doubling multiply high

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply / Saturating multiply

- SME attributes: Not specified by source.

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
    "register": "Zop1.D"
  },
  "op2": {
    "register": "Zop2.D[*]"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.D": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
SQDMULH Zresult.D, Zop1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDMULH--vectors---Signed-saturating-doubling-multiply-high--unpredicated--

### Operation

Source operation ID: `SveOperation_svqdmulh_n_s64`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Multiply `op1[i]` by `op2`, without loss of precision.
- Divide the result by 2 to the power 63, rounding towards -∞.
- Saturate the result to the range of `int64_t`.

## svqdmulh[_n_s8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdmulh%5B_n_s8%5D

### Signature (source notation)

```c
svint8_t svqdmulh[_n_s8](svint8_t op1, int8_t op2);
```

### Description

Saturating doubling multiply high

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply / Saturating multiply

- SME attributes: Not specified by source.

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
    "register": "Zop1.B"
  },
  "op2": {
    "register": "Zop2.B[*]"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.B": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
SQDMULH Zresult.B, Zop1.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDMULH--vectors---Signed-saturating-doubling-multiply-high--unpredicated--

### Operation

Source operation ID: `SveOperation_svqdmulh_n_s8`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Multiply `op1[i]` by `op2`, without loss of precision.
- Divide the result by 2 to the power 7, rounding towards -∞.
- Saturate the result to the range of `int8_t`.

## svqdmulh[_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdmulh%5B_s16%5D

### Signature (source notation)

```c
svint16_t svqdmulh[_s16](svint16_t op1, svint16_t op2);
```

### Description

Saturating doubling multiply high

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply / Saturating multiply

- SME attributes: Not specified by source.

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
    "register": "Zop1.H"
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
    "Zresult.H": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
SQDMULH Zresult.H, Zop1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDMULH--vectors---Signed-saturating-doubling-multiply-high--unpredicated--

### Operation

Source operation ID: `SveOperation_svqdmulh_s16`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Multiply `op1[i]` by `op2[i]`, without loss of precision.
- Divide the result by 2 to the power 15, rounding towards -∞.
- Saturate the result to the range of `int16_t`.

## svqdmulh[_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdmulh%5B_s32%5D

### Signature (source notation)

```c
svint32_t svqdmulh[_s32](svint32_t op1, svint32_t op2);
```

### Description

Saturating doubling multiply high

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply / Saturating multiply

- SME attributes: Not specified by source.

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
    "register": "Zop1.S"
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
    "Zresult.S": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
SQDMULH Zresult.S, Zop1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDMULH--vectors---Signed-saturating-doubling-multiply-high--unpredicated--

### Operation

Source operation ID: `SveOperation_svqdmulh_s32`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Multiply `op1[i]` by `op2[i]`, without loss of precision.
- Divide the result by 2 to the power 31, rounding towards -∞.
- Saturate the result to the range of `int32_t`.

## svqdmulh[_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdmulh%5B_s64%5D

### Signature (source notation)

```c
svint64_t svqdmulh[_s64](svint64_t op1, svint64_t op2);
```

### Description

Saturating doubling multiply high

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply / Saturating multiply

- SME attributes: Not specified by source.

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
    "register": "Zop1.D"
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
    "Zresult.D": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
SQDMULH Zresult.D, Zop1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDMULH--vectors---Signed-saturating-doubling-multiply-high--unpredicated--

### Operation

Source operation ID: `SveOperation_svqdmulh_s64`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Multiply `op1[i]` by `op2[i]`, without loss of precision.
- Divide the result by 2 to the power 63, rounding towards -∞.
- Saturate the result to the range of `int64_t`.

## svqdmulh[_s8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdmulh%5B_s8%5D

### Signature (source notation)

```c
svint8_t svqdmulh[_s8](svint8_t op1, svint8_t op2);
```

### Description

Saturating doubling multiply high

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply / Saturating multiply

- SME attributes: Not specified by source.

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
    "register": "Zop1.B"
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
    "Zresult.B": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
SQDMULH Zresult.B, Zop1.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDMULH--vectors---Signed-saturating-doubling-multiply-high--unpredicated--

### Operation

Source operation ID: `SveOperation_svqdmulh_s8`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Multiply `op1[i]` by `op2[i]`, without loss of precision.
- Divide the result by 2 to the power 7, rounding towards -∞.
- Saturate the result to the range of `int8_t`.

## svqdmulh_lane[_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdmulh_lane%5B_s16%5D

### Signature (source notation)

```c
svint16_t svqdmulh_lane[_s16](svint16_t op1, svint16_t op2, uint64_t imm_index);
```

### Description

Saturating doubling multiply high

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply / Saturating multiply

- SME attributes: Not specified by source.

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
    "register": "Zop1.H"
  },
  "op2": {
    "register": "Zop2.H"
  },
  "imm_index": {
    "minimum": 0,
    "maximum": 7
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.H": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
SQDMULH Zresult.H, Zop1.H, Zop2.H[imm_index]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDMULH--indexed---Signed-saturating-doubling-multiply-high--indexed--

### Operation

Source operation ID: `SveOperation_svqdmulh_lane_s16`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Multiply `op1[i]` by `op2[base + imm_index]`, without loss of precision, where *base* is the index of the first element in the same 128-bit quadword as *i*.
- Divide the result by 2 to the power 15, rounding towards -∞.
- Saturate the result to the range of `int16_t`.

## svqdmulh_lane[_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdmulh_lane%5B_s32%5D

### Signature (source notation)

```c
svint32_t svqdmulh_lane[_s32](svint32_t op1, svint32_t op2, uint64_t imm_index);
```

### Description

Saturating doubling multiply high

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply / Saturating multiply

- SME attributes: Not specified by source.

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
    "register": "Zop1.S"
  },
  "op2": {
    "register": "Zop2.S"
  },
  "imm_index": {
    "minimum": 0,
    "maximum": 3
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.S": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
SQDMULH Zresult.S, Zop1.S, Zop2.S[imm_index]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDMULH--indexed---Signed-saturating-doubling-multiply-high--indexed--

### Operation

Source operation ID: `SveOperation_svqdmulh_lane_s32`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Multiply `op1[i]` by `op2[base + imm_index]`, without loss of precision, where *base* is the index of the first element in the same 128-bit quadword as *i*.
- Divide the result by 2 to the power 31, rounding towards -∞.
- Saturate the result to the range of `int32_t`.

## svqdmulh_lane[_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdmulh_lane%5B_s64%5D

### Signature (source notation)

```c
svint64_t svqdmulh_lane[_s64](svint64_t op1, svint64_t op2, uint64_t imm_index);
```

### Description

Saturating doubling multiply high

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply / Saturating multiply

- SME attributes: Not specified by source.

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
    "register": "Zop1.D"
  },
  "op2": {
    "register": "Zop2.D"
  },
  "imm_index": {
    "minimum": 0,
    "maximum": 1
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.D": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
SQDMULH Zresult.D, Zop1.D, Zop2.D[imm_index]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDMULH--indexed---Signed-saturating-doubling-multiply-high--indexed--

### Operation

Source operation ID: `SveOperation_svqdmulh_lane_s64`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Multiply `op1[i]` by `op2[base + imm_index]`, without loss of precision, where *base* is the index of the first element in the same 128-bit quadword as *i*.
- Divide the result by 2 to the power 63, rounding towards -∞.
- Saturate the result to the range of `int64_t`.

## svqrdmulh[_n_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqrdmulh%5B_n_s16%5D

### Signature (source notation)

```c
svint16_t svqrdmulh[_n_s16](svint16_t op1, int16_t op2);
```

### Description

Saturating rounding doubling multiply high

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply / Saturating multiply

- SME attributes: Not specified by source.

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
    "register": "Zop1.H"
  },
  "op2": {
    "register": "Zop2.H[*]"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.H": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
SQRDMULH Zresult.H, Zop1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQRDMULH--vectors---Signed-saturating-rounding-doubling-multiply-high--unpredicated--

### Operation

Source operation ID: `SveOperation_svqrdmulh_n_s16`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Multiply `op1[i]` by `op2`, without loss of precision.
- Divide the result by 2 to the power 15, rounding to nearest with ties towards +∞.
- Saturate the result to the range of `int16_t`.

## svqrdmulh[_n_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqrdmulh%5B_n_s32%5D

### Signature (source notation)

```c
svint32_t svqrdmulh[_n_s32](svint32_t op1, int32_t op2);
```

### Description

Saturating rounding doubling multiply high

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply / Saturating multiply

- SME attributes: Not specified by source.

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
    "register": "Zop1.S"
  },
  "op2": {
    "register": "Zop2.S[*]"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.S": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
SQRDMULH Zresult.S, Zop1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQRDMULH--vectors---Signed-saturating-rounding-doubling-multiply-high--unpredicated--

### Operation

Source operation ID: `SveOperation_svqrdmulh_n_s32`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Multiply `op1[i]` by `op2`, without loss of precision.
- Divide the result by 2 to the power 31, rounding to nearest with ties towards +∞.
- Saturate the result to the range of `int32_t`.

## svqrdmulh[_n_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqrdmulh%5B_n_s64%5D

### Signature (source notation)

```c
svint64_t svqrdmulh[_n_s64](svint64_t op1, int64_t op2);
```

### Description

Saturating rounding doubling multiply high

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply / Saturating multiply

- SME attributes: Not specified by source.

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
    "register": "Zop1.D"
  },
  "op2": {
    "register": "Zop2.D[*]"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.D": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
SQRDMULH Zresult.D, Zop1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQRDMULH--vectors---Signed-saturating-rounding-doubling-multiply-high--unpredicated--

### Operation

Source operation ID: `SveOperation_svqrdmulh_n_s64`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Multiply `op1[i]` by `op2`, without loss of precision.
- Divide the result by 2 to the power 63, rounding to nearest with ties towards +∞.
- Saturate the result to the range of `int64_t`.

## svqrdmulh[_n_s8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqrdmulh%5B_n_s8%5D

### Signature (source notation)

```c
svint8_t svqrdmulh[_n_s8](svint8_t op1, int8_t op2);
```

### Description

Saturating rounding doubling multiply high

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply / Saturating multiply

- SME attributes: Not specified by source.

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
    "register": "Zop1.B"
  },
  "op2": {
    "register": "Zop2.B[*]"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.B": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
SQRDMULH Zresult.B, Zop1.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQRDMULH--vectors---Signed-saturating-rounding-doubling-multiply-high--unpredicated--

### Operation

Source operation ID: `SveOperation_svqrdmulh_n_s8`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Multiply `op1[i]` by `op2`, without loss of precision.
- Divide the result by 2 to the power 7, rounding to nearest with ties towards +∞.
- Saturate the result to the range of `int8_t`.

## svqrdmulh[_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqrdmulh%5B_s16%5D

### Signature (source notation)

```c
svint16_t svqrdmulh[_s16](svint16_t op1, svint16_t op2);
```

### Description

Saturating rounding doubling multiply high

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply / Saturating multiply

- SME attributes: Not specified by source.

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
    "register": "Zop1.H"
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
    "Zresult.H": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
SQRDMULH Zresult.H, Zop1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQRDMULH--vectors---Signed-saturating-rounding-doubling-multiply-high--unpredicated--

### Operation

Source operation ID: `SveOperation_svqrdmulh_s16`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Multiply `op1[i]` by `op2[i]`, without loss of precision.
- Divide the result by 2 to the power 15, rounding to nearest with ties towards +∞.
- Saturate the result to the range of `int16_t`.

## svqrdmulh[_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqrdmulh%5B_s32%5D

### Signature (source notation)

```c
svint32_t svqrdmulh[_s32](svint32_t op1, svint32_t op2);
```

### Description

Saturating rounding doubling multiply high

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply / Saturating multiply

- SME attributes: Not specified by source.

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
    "register": "Zop1.S"
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
    "Zresult.S": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
SQRDMULH Zresult.S, Zop1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQRDMULH--vectors---Signed-saturating-rounding-doubling-multiply-high--unpredicated--

### Operation

Source operation ID: `SveOperation_svqrdmulh_s32`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Multiply `op1[i]` by `op2[i]`, without loss of precision.
- Divide the result by 2 to the power 31, rounding to nearest with ties towards +∞.
- Saturate the result to the range of `int32_t`.

## svqrdmulh[_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqrdmulh%5B_s64%5D

### Signature (source notation)

```c
svint64_t svqrdmulh[_s64](svint64_t op1, svint64_t op2);
```

### Description

Saturating rounding doubling multiply high

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply / Saturating multiply

- SME attributes: Not specified by source.

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
    "register": "Zop1.D"
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
    "Zresult.D": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
SQRDMULH Zresult.D, Zop1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQRDMULH--vectors---Signed-saturating-rounding-doubling-multiply-high--unpredicated--

### Operation

Source operation ID: `SveOperation_svqrdmulh_s64`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Multiply `op1[i]` by `op2[i]`, without loss of precision.
- Divide the result by 2 to the power 63, rounding to nearest with ties towards +∞.
- Saturate the result to the range of `int64_t`.

## svqrdmulh[_s8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqrdmulh%5B_s8%5D

### Signature (source notation)

```c
svint8_t svqrdmulh[_s8](svint8_t op1, svint8_t op2);
```

### Description

Saturating rounding doubling multiply high

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply / Saturating multiply

- SME attributes: Not specified by source.

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
    "register": "Zop1.B"
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
    "Zresult.B": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
SQRDMULH Zresult.B, Zop1.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQRDMULH--vectors---Signed-saturating-rounding-doubling-multiply-high--unpredicated--

### Operation

Source operation ID: `SveOperation_svqrdmulh_s8`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Multiply `op1[i]` by `op2[i]`, without loss of precision.
- Divide the result by 2 to the power 7, rounding to nearest with ties towards +∞.
- Saturate the result to the range of `int8_t`.

## svqrdmulh_lane[_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqrdmulh_lane%5B_s16%5D

### Signature (source notation)

```c
svint16_t svqrdmulh_lane[_s16](svint16_t op1, svint16_t op2, uint64_t imm_index);
```

### Description

Saturating rounding doubling multiply high

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply / Saturating multiply

- SME attributes: Not specified by source.

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
    "register": "Zop1.H"
  },
  "op2": {
    "register": "Zop2.H"
  },
  "imm_index": {
    "minimum": 0,
    "maximum": 7
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.H": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
SQRDMULH Zresult.H, Zop1.H, Zop2.H[imm_index]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQRDMULH--indexed---Signed-saturating-rounding-doubling-multiply-high--indexed--

### Operation

Source operation ID: `SveOperation_svqrdmulh_lane_s16`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Multiply `op1[i]` by `op2[base + imm_index]`, without loss of precision, where *base* is the index of the first element in the same 128-bit quadword as *i*.
- Divide the result by 2 to the power 15, rounding to nearest with ties towards +∞.
- Saturate the result to the range of `int16_t`.

## svqrdmulh_lane[_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqrdmulh_lane%5B_s32%5D

### Signature (source notation)

```c
svint32_t svqrdmulh_lane[_s32](svint32_t op1, svint32_t op2, uint64_t imm_index);
```

### Description

Saturating rounding doubling multiply high

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply / Saturating multiply

- SME attributes: Not specified by source.

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
    "register": "Zop1.S"
  },
  "op2": {
    "register": "Zop2.S"
  },
  "imm_index": {
    "minimum": 0,
    "maximum": 3
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.S": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
SQRDMULH Zresult.S, Zop1.S, Zop2.S[imm_index]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQRDMULH--indexed---Signed-saturating-rounding-doubling-multiply-high--indexed--

### Operation

Source operation ID: `SveOperation_svqrdmulh_lane_s32`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Multiply `op1[i]` by `op2[base + imm_index]`, without loss of precision, where *base* is the index of the first element in the same 128-bit quadword as *i*.
- Divide the result by 2 to the power 31, rounding to nearest with ties towards +∞.
- Saturate the result to the range of `int32_t`.

## svqrdmulh_lane[_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqrdmulh_lane%5B_s64%5D

### Signature (source notation)

```c
svint64_t svqrdmulh_lane[_s64](svint64_t op1, svint64_t op2, uint64_t imm_index);
```

### Description

Saturating rounding doubling multiply high

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply / Saturating multiply

- SME attributes: Not specified by source.

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
    "register": "Zop1.D"
  },
  "op2": {
    "register": "Zop2.D"
  },
  "imm_index": {
    "minimum": 0,
    "maximum": 1
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.D": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
SQRDMULH Zresult.D, Zop1.D, Zop2.D[imm_index]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQRDMULH--indexed---Signed-saturating-rounding-doubling-multiply-high--indexed--

### Operation

Source operation ID: `SveOperation_svqrdmulh_lane_s64`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Multiply `op1[i]` by `op2[base + imm_index]`, without loss of precision, where *base* is the index of the first element in the same 128-bit quadword as *i*.
- Divide the result by 2 to the power 63, rounding to nearest with ties towards +∞.
- Saturate the result to the range of `int64_t`.

