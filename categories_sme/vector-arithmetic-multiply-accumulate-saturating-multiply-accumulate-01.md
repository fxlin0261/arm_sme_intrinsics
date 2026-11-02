# SME / Vector arithmetic / Multiply-accumulate / Saturating multiply-accumulate — Part 1

## svqrdmlah[_n_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqrdmlah%5B_n_s16%5D

### Signature (source notation)

```c
svint16_t svqrdmlah[_n_s16](svint16_t op1, svint16_t op2, int16_t op3);
```

### Description

Saturating rounding doubling multiply-add high

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Saturating multiply-accumulate

- SME attributes: Not specified by source.

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
    "register": "Zop1.H|Ztied1.H"
  },
  "op2": {
    "register": "Zop2.H"
  },
  "op3": {
    "register": "Zop3.H[*]"
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
SQRDMLAH Ztied1.H, Zop2.H, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQRDMLAH--vectors---Signed-saturating-rounding-doubling-multiply-add-high-to-accumulator--unpredicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SQRDMLAH Zresult.H, Zop2.H, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQRDMLAH--vectors---Signed-saturating-rounding-doubling-multiply-add-high-to-accumulator--unpredicated--

### Operation

Source operation ID: `SveOperation_svqrdmlah_n_s16`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Multiply `op2[i]` by `op3`, without loss of precision.
- Divide the result by 2 to the power 15, rounding to nearest with ties towards +∞.
- Add the result to `op1[i]`, without loss of precision.
- Saturate the result to the range of `int16_t`.

## svqrdmlah[_n_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqrdmlah%5B_n_s32%5D

### Signature (source notation)

```c
svint32_t svqrdmlah[_n_s32](svint32_t op1, svint32_t op2, int32_t op3);
```

### Description

Saturating rounding doubling multiply-add high

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Saturating multiply-accumulate

- SME attributes: Not specified by source.

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
    "register": "Zop1.S|Ztied1.S"
  },
  "op2": {
    "register": "Zop2.S"
  },
  "op3": {
    "register": "Zop3.S[*]"
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
SQRDMLAH Ztied1.S, Zop2.S, Zop3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQRDMLAH--vectors---Signed-saturating-rounding-doubling-multiply-add-high-to-accumulator--unpredicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SQRDMLAH Zresult.S, Zop2.S, Zop3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQRDMLAH--vectors---Signed-saturating-rounding-doubling-multiply-add-high-to-accumulator--unpredicated--

### Operation

Source operation ID: `SveOperation_svqrdmlah_n_s32`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Multiply `op2[i]` by `op3`, without loss of precision.
- Divide the result by 2 to the power 31, rounding to nearest with ties towards +∞.
- Add the result to `op1[i]`, without loss of precision.
- Saturate the result to the range of `int32_t`.

## svqrdmlah[_n_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqrdmlah%5B_n_s64%5D

### Signature (source notation)

```c
svint64_t svqrdmlah[_n_s64](svint64_t op1, svint64_t op2, int64_t op3);
```

### Description

Saturating rounding doubling multiply-add high

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Saturating multiply-accumulate

- SME attributes: Not specified by source.

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
    "register": "Zop1.D|Ztied1.D"
  },
  "op2": {
    "register": "Zop2.D"
  },
  "op3": {
    "register": "Zop3.D[*]"
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
SQRDMLAH Ztied1.D, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQRDMLAH--vectors---Signed-saturating-rounding-doubling-multiply-add-high-to-accumulator--unpredicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SQRDMLAH Zresult.D, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQRDMLAH--vectors---Signed-saturating-rounding-doubling-multiply-add-high-to-accumulator--unpredicated--

### Operation

Source operation ID: `SveOperation_svqrdmlah_n_s64`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Multiply `op2[i]` by `op3`, without loss of precision.
- Divide the result by 2 to the power 63, rounding to nearest with ties towards +∞.
- Add the result to `op1[i]`, without loss of precision.
- Saturate the result to the range of `int64_t`.

## svqrdmlah[_n_s8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqrdmlah%5B_n_s8%5D

### Signature (source notation)

```c
svint8_t svqrdmlah[_n_s8](svint8_t op1, svint8_t op2, int8_t op3);
```

### Description

Saturating rounding doubling multiply-add high

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Saturating multiply-accumulate

- SME attributes: Not specified by source.

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
  "op3": {
    "register": "Zop3.B[*]"
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
SQRDMLAH Ztied1.B, Zop2.B, Zop3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQRDMLAH--vectors---Signed-saturating-rounding-doubling-multiply-add-high-to-accumulator--unpredicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SQRDMLAH Zresult.B, Zop2.B, Zop3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQRDMLAH--vectors---Signed-saturating-rounding-doubling-multiply-add-high-to-accumulator--unpredicated--

### Operation

Source operation ID: `SveOperation_svqrdmlah_n_s8`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Multiply `op2[i]` by `op3`, without loss of precision.
- Divide the result by 2 to the power 7, rounding to nearest with ties towards +∞.
- Add the result to `op1[i]`, without loss of precision.
- Saturate the result to the range of `int8_t`.

## svqrdmlah[_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqrdmlah%5B_s16%5D

### Signature (source notation)

```c
svint16_t svqrdmlah[_s16](svint16_t op1, svint16_t op2, svint16_t op3);
```

### Description

Saturating rounding doubling multiply-add high

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Saturating multiply-accumulate

- SME attributes: Not specified by source.

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
    "register": "Zop1.H|Ztied1.H"
  },
  "op2": {
    "register": "Zop2.H"
  },
  "op3": {
    "register": "Zop3.H"
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
SQRDMLAH Ztied1.H, Zop2.H, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQRDMLAH--vectors---Signed-saturating-rounding-doubling-multiply-add-high-to-accumulator--unpredicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SQRDMLAH Zresult.H, Zop2.H, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQRDMLAH--vectors---Signed-saturating-rounding-doubling-multiply-add-high-to-accumulator--unpredicated--

### Operation

Source operation ID: `SveOperation_svqrdmlah_s16`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Multiply `op2[i]` by `op3[i]`, without loss of precision.
- Divide the result by 2 to the power 15, rounding to nearest with ties towards +∞.
- Add the result to `op1[i]`, without loss of precision.
- Saturate the result to the range of `int16_t`.

## svqrdmlah[_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqrdmlah%5B_s32%5D

### Signature (source notation)

```c
svint32_t svqrdmlah[_s32](svint32_t op1, svint32_t op2, svint32_t op3);
```

### Description

Saturating rounding doubling multiply-add high

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Saturating multiply-accumulate

- SME attributes: Not specified by source.

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
    "register": "Zop1.S|Ztied1.S"
  },
  "op2": {
    "register": "Zop2.S"
  },
  "op3": {
    "register": "Zop3.S"
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
SQRDMLAH Ztied1.S, Zop2.S, Zop3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQRDMLAH--vectors---Signed-saturating-rounding-doubling-multiply-add-high-to-accumulator--unpredicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SQRDMLAH Zresult.S, Zop2.S, Zop3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQRDMLAH--vectors---Signed-saturating-rounding-doubling-multiply-add-high-to-accumulator--unpredicated--

### Operation

Source operation ID: `SveOperation_svqrdmlah_s32`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Multiply `op2[i]` by `op3[i]`, without loss of precision.
- Divide the result by 2 to the power 31, rounding to nearest with ties towards +∞.
- Add the result to `op1[i]`, without loss of precision.
- Saturate the result to the range of `int32_t`.

## svqrdmlah[_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqrdmlah%5B_s64%5D

### Signature (source notation)

```c
svint64_t svqrdmlah[_s64](svint64_t op1, svint64_t op2, svint64_t op3);
```

### Description

Saturating rounding doubling multiply-add high

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Saturating multiply-accumulate

- SME attributes: Not specified by source.

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
    "register": "Zop1.D|Ztied1.D"
  },
  "op2": {
    "register": "Zop2.D"
  },
  "op3": {
    "register": "Zop3.D"
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
SQRDMLAH Ztied1.D, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQRDMLAH--vectors---Signed-saturating-rounding-doubling-multiply-add-high-to-accumulator--unpredicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SQRDMLAH Zresult.D, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQRDMLAH--vectors---Signed-saturating-rounding-doubling-multiply-add-high-to-accumulator--unpredicated--

### Operation

Source operation ID: `SveOperation_svqrdmlah_s64`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Multiply `op2[i]` by `op3[i]`, without loss of precision.
- Divide the result by 2 to the power 63, rounding to nearest with ties towards +∞.
- Add the result to `op1[i]`, without loss of precision.
- Saturate the result to the range of `int64_t`.

## svqrdmlah[_s8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqrdmlah%5B_s8%5D

### Signature (source notation)

```c
svint8_t svqrdmlah[_s8](svint8_t op1, svint8_t op2, svint8_t op3);
```

### Description

Saturating rounding doubling multiply-add high

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Saturating multiply-accumulate

- SME attributes: Not specified by source.

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
  "op3": {
    "register": "Zop3.B"
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
SQRDMLAH Ztied1.B, Zop2.B, Zop3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQRDMLAH--vectors---Signed-saturating-rounding-doubling-multiply-add-high-to-accumulator--unpredicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SQRDMLAH Zresult.B, Zop2.B, Zop3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQRDMLAH--vectors---Signed-saturating-rounding-doubling-multiply-add-high-to-accumulator--unpredicated--

### Operation

Source operation ID: `SveOperation_svqrdmlah_s8`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Multiply `op2[i]` by `op3[i]`, without loss of precision.
- Divide the result by 2 to the power 7, rounding to nearest with ties towards +∞.
- Add the result to `op1[i]`, without loss of precision.
- Saturate the result to the range of `int8_t`.

## svqrdmlah_lane[_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqrdmlah_lane%5B_s16%5D

### Signature (source notation)

```c
svint16_t svqrdmlah_lane[_s16](svint16_t op1, svint16_t op2, svint16_t op3, uint64_t imm_index);
```

### Description

Saturating rounding doubling multiply-add high

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Saturating multiply-accumulate

- SME attributes: Not specified by source.

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
    "register": "Zop1.H|Ztied1.H"
  },
  "op2": {
    "register": "Zop2.H"
  },
  "op3": {
    "register": "Zop3.H"
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
    "Zresult.H|Ztied1.H": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
SQRDMLAH Ztied1.H, Zop2.H, Zop3.H[imm_index]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQRDMLAH--indexed---Signed-saturating-rounding-doubling-multiply-add-high-to-accumulator--indexed--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SQRDMLAH Zresult.H, Zop2.H, Zop3.H[imm_index]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQRDMLAH--indexed---Signed-saturating-rounding-doubling-multiply-add-high-to-accumulator--indexed--

### Operation

Source operation ID: `SveOperation_svqrdmlah_lane_s16`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Multiply `op2[i]` by `op3[base + imm_index]`, without loss of precision, where *base* is the index of the first element in the same 128-bit quadword as *i*.
- Divide the result by 2 to the power 15, rounding to nearest with ties towards +∞.
- Add the result to `op1[i]`, without loss of precision.
- Saturate the result to the range of `int16_t`.

## svqrdmlah_lane[_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqrdmlah_lane%5B_s32%5D

### Signature (source notation)

```c
svint32_t svqrdmlah_lane[_s32](svint32_t op1, svint32_t op2, svint32_t op3, uint64_t imm_index);
```

### Description

Saturating rounding doubling multiply-add high

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Saturating multiply-accumulate

- SME attributes: Not specified by source.

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
    "register": "Zop1.S|Ztied1.S"
  },
  "op2": {
    "register": "Zop2.S"
  },
  "op3": {
    "register": "Zop3.S"
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
    "Zresult.S|Ztied1.S": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
SQRDMLAH Ztied1.S, Zop2.S, Zop3.S[imm_index]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQRDMLAH--indexed---Signed-saturating-rounding-doubling-multiply-add-high-to-accumulator--indexed--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SQRDMLAH Zresult.S, Zop2.S, Zop3.S[imm_index]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQRDMLAH--indexed---Signed-saturating-rounding-doubling-multiply-add-high-to-accumulator--indexed--

### Operation

Source operation ID: `SveOperation_svqrdmlah_lane_s32`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Multiply `op2[i]` by `op3[base + imm_index]`, without loss of precision, where *base* is the index of the first element in the same 128-bit quadword as *i*.
- Divide the result by 2 to the power 31, rounding to nearest with ties towards +∞.
- Add the result to `op1[i]`, without loss of precision.
- Saturate the result to the range of `int32_t`.

## svqrdmlah_lane[_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqrdmlah_lane%5B_s64%5D

### Signature (source notation)

```c
svint64_t svqrdmlah_lane[_s64](svint64_t op1, svint64_t op2, svint64_t op3, uint64_t imm_index);
```

### Description

Saturating rounding doubling multiply-add high

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Saturating multiply-accumulate

- SME attributes: Not specified by source.

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
    "register": "Zop1.D|Ztied1.D"
  },
  "op2": {
    "register": "Zop2.D"
  },
  "op3": {
    "register": "Zop3.D"
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
    "Zresult.D|Ztied1.D": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
SQRDMLAH Ztied1.D, Zop2.D, Zop3.D[imm_index]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQRDMLAH--indexed---Signed-saturating-rounding-doubling-multiply-add-high-to-accumulator--indexed--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SQRDMLAH Zresult.D, Zop2.D, Zop3.D[imm_index]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQRDMLAH--indexed---Signed-saturating-rounding-doubling-multiply-add-high-to-accumulator--indexed--

### Operation

Source operation ID: `SveOperation_svqrdmlah_lane_s64`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Multiply `op2[i]` by `op3[base + imm_index]`, without loss of precision, where *base* is the index of the first element in the same 128-bit quadword as *i*.
- Divide the result by 2 to the power 63, rounding to nearest with ties towards +∞.
- Add the result to `op1[i]`, without loss of precision.
- Saturate the result to the range of `int64_t`.

## svqrdmlsh[_n_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqrdmlsh%5B_n_s16%5D

### Signature (source notation)

```c
svint16_t svqrdmlsh[_n_s16](svint16_t op1, svint16_t op2, int16_t op3);
```

### Description

Saturating rounding doubling multiply-subtract high

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Saturating multiply-accumulate

- SME attributes: Not specified by source.

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
    "register": "Zop1.H|Ztied1.H"
  },
  "op2": {
    "register": "Zop2.H"
  },
  "op3": {
    "register": "Zop3.H[*]"
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
SQRDMLSH Ztied1.H, Zop2.H, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQRDMLSH--vectors---Signed-saturating-rounding-doubling-multiply-subtract-high-from-accumulator--unpredicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SQRDMLSH Zresult.H, Zop2.H, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQRDMLSH--vectors---Signed-saturating-rounding-doubling-multiply-subtract-high-from-accumulator--unpredicated--

### Operation

Source operation ID: `SveOperation_svqrdmlsh_n_s16`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Multiply `op2[i]` by `op3`, without loss of precision.
- Negate the result, again without loss of precision.
- Divide the result by 2 to the power 15, rounding to nearest with ties towards +∞.
- Add the result to `op1[i]`, without loss of precision.
- Saturate the result to the range of `int16_t`.

## svqrdmlsh[_n_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqrdmlsh%5B_n_s32%5D

### Signature (source notation)

```c
svint32_t svqrdmlsh[_n_s32](svint32_t op1, svint32_t op2, int32_t op3);
```

### Description

Saturating rounding doubling multiply-subtract high

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Saturating multiply-accumulate

- SME attributes: Not specified by source.

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
    "register": "Zop1.S|Ztied1.S"
  },
  "op2": {
    "register": "Zop2.S"
  },
  "op3": {
    "register": "Zop3.S[*]"
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
SQRDMLSH Ztied1.S, Zop2.S, Zop3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQRDMLSH--vectors---Signed-saturating-rounding-doubling-multiply-subtract-high-from-accumulator--unpredicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SQRDMLSH Zresult.S, Zop2.S, Zop3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQRDMLSH--vectors---Signed-saturating-rounding-doubling-multiply-subtract-high-from-accumulator--unpredicated--

### Operation

Source operation ID: `SveOperation_svqrdmlsh_n_s32`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Multiply `op2[i]` by `op3`, without loss of precision.
- Negate the result, again without loss of precision.
- Divide the result by 2 to the power 31, rounding to nearest with ties towards +∞.
- Add the result to `op1[i]`, without loss of precision.
- Saturate the result to the range of `int32_t`.

## svqrdmlsh[_n_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqrdmlsh%5B_n_s64%5D

### Signature (source notation)

```c
svint64_t svqrdmlsh[_n_s64](svint64_t op1, svint64_t op2, int64_t op3);
```

### Description

Saturating rounding doubling multiply-subtract high

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Saturating multiply-accumulate

- SME attributes: Not specified by source.

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
    "register": "Zop1.D|Ztied1.D"
  },
  "op2": {
    "register": "Zop2.D"
  },
  "op3": {
    "register": "Zop3.D[*]"
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
SQRDMLSH Ztied1.D, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQRDMLSH--vectors---Signed-saturating-rounding-doubling-multiply-subtract-high-from-accumulator--unpredicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SQRDMLSH Zresult.D, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQRDMLSH--vectors---Signed-saturating-rounding-doubling-multiply-subtract-high-from-accumulator--unpredicated--

### Operation

Source operation ID: `SveOperation_svqrdmlsh_n_s64`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Multiply `op2[i]` by `op3`, without loss of precision.
- Negate the result, again without loss of precision.
- Divide the result by 2 to the power 63, rounding to nearest with ties towards +∞.
- Add the result to `op1[i]`, without loss of precision.
- Saturate the result to the range of `int64_t`.

## svqrdmlsh[_n_s8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqrdmlsh%5B_n_s8%5D

### Signature (source notation)

```c
svint8_t svqrdmlsh[_n_s8](svint8_t op1, svint8_t op2, int8_t op3);
```

### Description

Saturating rounding doubling multiply-subtract high

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Saturating multiply-accumulate

- SME attributes: Not specified by source.

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
  "op3": {
    "register": "Zop3.B[*]"
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
SQRDMLSH Ztied1.B, Zop2.B, Zop3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQRDMLSH--vectors---Signed-saturating-rounding-doubling-multiply-subtract-high-from-accumulator--unpredicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SQRDMLSH Zresult.B, Zop2.B, Zop3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQRDMLSH--vectors---Signed-saturating-rounding-doubling-multiply-subtract-high-from-accumulator--unpredicated--

### Operation

Source operation ID: `SveOperation_svqrdmlsh_n_s8`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Multiply `op2[i]` by `op3`, without loss of precision.
- Negate the result, again without loss of precision.
- Divide the result by 2 to the power 7, rounding to nearest with ties towards +∞.
- Add the result to `op1[i]`, without loss of precision.
- Saturate the result to the range of `int8_t`.

## svqrdmlsh[_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqrdmlsh%5B_s16%5D

### Signature (source notation)

```c
svint16_t svqrdmlsh[_s16](svint16_t op1, svint16_t op2, svint16_t op3);
```

### Description

Saturating rounding doubling multiply-subtract high

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Saturating multiply-accumulate

- SME attributes: Not specified by source.

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
    "register": "Zop1.H|Ztied1.H"
  },
  "op2": {
    "register": "Zop2.H"
  },
  "op3": {
    "register": "Zop3.H"
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
SQRDMLSH Ztied1.H, Zop2.H, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQRDMLSH--vectors---Signed-saturating-rounding-doubling-multiply-subtract-high-from-accumulator--unpredicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SQRDMLSH Zresult.H, Zop2.H, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQRDMLSH--vectors---Signed-saturating-rounding-doubling-multiply-subtract-high-from-accumulator--unpredicated--

### Operation

Source operation ID: `SveOperation_svqrdmlsh_s16`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Multiply `op2[i]` by `op3[i]`, without loss of precision.
- Negate the result, again without loss of precision.
- Divide the result by 2 to the power 15, rounding to nearest with ties towards +∞.
- Add the result to `op1[i]`, without loss of precision.
- Saturate the result to the range of `int16_t`.

## svqrdmlsh[_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqrdmlsh%5B_s32%5D

### Signature (source notation)

```c
svint32_t svqrdmlsh[_s32](svint32_t op1, svint32_t op2, svint32_t op3);
```

### Description

Saturating rounding doubling multiply-subtract high

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Saturating multiply-accumulate

- SME attributes: Not specified by source.

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
    "register": "Zop1.S|Ztied1.S"
  },
  "op2": {
    "register": "Zop2.S"
  },
  "op3": {
    "register": "Zop3.S"
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
SQRDMLSH Ztied1.S, Zop2.S, Zop3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQRDMLSH--vectors---Signed-saturating-rounding-doubling-multiply-subtract-high-from-accumulator--unpredicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SQRDMLSH Zresult.S, Zop2.S, Zop3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQRDMLSH--vectors---Signed-saturating-rounding-doubling-multiply-subtract-high-from-accumulator--unpredicated--

### Operation

Source operation ID: `SveOperation_svqrdmlsh_s32`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Multiply `op2[i]` by `op3[i]`, without loss of precision.
- Negate the result, again without loss of precision.
- Divide the result by 2 to the power 31, rounding to nearest with ties towards +∞.
- Add the result to `op1[i]`, without loss of precision.
- Saturate the result to the range of `int32_t`.

## svqrdmlsh[_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqrdmlsh%5B_s64%5D

### Signature (source notation)

```c
svint64_t svqrdmlsh[_s64](svint64_t op1, svint64_t op2, svint64_t op3);
```

### Description

Saturating rounding doubling multiply-subtract high

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Saturating multiply-accumulate

- SME attributes: Not specified by source.

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
    "register": "Zop1.D|Ztied1.D"
  },
  "op2": {
    "register": "Zop2.D"
  },
  "op3": {
    "register": "Zop3.D"
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
SQRDMLSH Ztied1.D, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQRDMLSH--vectors---Signed-saturating-rounding-doubling-multiply-subtract-high-from-accumulator--unpredicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SQRDMLSH Zresult.D, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQRDMLSH--vectors---Signed-saturating-rounding-doubling-multiply-subtract-high-from-accumulator--unpredicated--

### Operation

Source operation ID: `SveOperation_svqrdmlsh_s64`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Multiply `op2[i]` by `op3[i]`, without loss of precision.
- Negate the result, again without loss of precision.
- Divide the result by 2 to the power 63, rounding to nearest with ties towards +∞.
- Add the result to `op1[i]`, without loss of precision.
- Saturate the result to the range of `int64_t`.

## svqrdmlsh[_s8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqrdmlsh%5B_s8%5D

### Signature (source notation)

```c
svint8_t svqrdmlsh[_s8](svint8_t op1, svint8_t op2, svint8_t op3);
```

### Description

Saturating rounding doubling multiply-subtract high

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Saturating multiply-accumulate

- SME attributes: Not specified by source.

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
  "op3": {
    "register": "Zop3.B"
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
SQRDMLSH Ztied1.B, Zop2.B, Zop3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQRDMLSH--vectors---Signed-saturating-rounding-doubling-multiply-subtract-high-from-accumulator--unpredicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SQRDMLSH Zresult.B, Zop2.B, Zop3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQRDMLSH--vectors---Signed-saturating-rounding-doubling-multiply-subtract-high-from-accumulator--unpredicated--

### Operation

Source operation ID: `SveOperation_svqrdmlsh_s8`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Multiply `op2[i]` by `op3[i]`, without loss of precision.
- Negate the result, again without loss of precision.
- Divide the result by 2 to the power 7, rounding to nearest with ties towards +∞.
- Add the result to `op1[i]`, without loss of precision.
- Saturate the result to the range of `int8_t`.

## svqrdmlsh_lane[_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqrdmlsh_lane%5B_s16%5D

### Signature (source notation)

```c
svint16_t svqrdmlsh_lane[_s16](svint16_t op1, svint16_t op2, svint16_t op3, uint64_t imm_index);
```

### Description

Saturating rounding doubling multiply-subtract high

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Saturating multiply-accumulate

- SME attributes: Not specified by source.

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
    "register": "Zop1.H|Ztied1.H"
  },
  "op2": {
    "register": "Zop2.H"
  },
  "op3": {
    "register": "Zop3.H"
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
    "Zresult.H|Ztied1.H": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
SQRDMLSH Ztied1.H, Zop2.H, Zop3.H[imm_index]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQRDMLSH--indexed---Signed-saturating-rounding-doubling-multiply-subtract-high-from-accumulator--indexed--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SQRDMLSH Zresult.H, Zop2.H, Zop3.H[imm_index]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQRDMLSH--indexed---Signed-saturating-rounding-doubling-multiply-subtract-high-from-accumulator--indexed--

### Operation

Source operation ID: `SveOperation_svqrdmlsh_lane_s16`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Multiply `op2[i]` by `op3[base + imm_index]`, without loss of precision, where *base* is the index of the first element in the same 128-bit quadword as *i*.
- Negate the result, again without loss of precision.
- Divide the result by 2 to the power 15, rounding to nearest with ties towards +∞.
- Add the result to `op1[i]`, without loss of precision.
- Saturate the result to the range of `int16_t`.

## svqrdmlsh_lane[_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqrdmlsh_lane%5B_s32%5D

### Signature (source notation)

```c
svint32_t svqrdmlsh_lane[_s32](svint32_t op1, svint32_t op2, svint32_t op3, uint64_t imm_index);
```

### Description

Saturating rounding doubling multiply-subtract high

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Saturating multiply-accumulate

- SME attributes: Not specified by source.

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
    "register": "Zop1.S|Ztied1.S"
  },
  "op2": {
    "register": "Zop2.S"
  },
  "op3": {
    "register": "Zop3.S"
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
    "Zresult.S|Ztied1.S": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
SQRDMLSH Ztied1.S, Zop2.S, Zop3.S[imm_index]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQRDMLSH--indexed---Signed-saturating-rounding-doubling-multiply-subtract-high-from-accumulator--indexed--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SQRDMLSH Zresult.S, Zop2.S, Zop3.S[imm_index]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQRDMLSH--indexed---Signed-saturating-rounding-doubling-multiply-subtract-high-from-accumulator--indexed--

### Operation

Source operation ID: `SveOperation_svqrdmlsh_lane_s32`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Multiply `op2[i]` by `op3[base + imm_index]`, without loss of precision, where *base* is the index of the first element in the same 128-bit quadword as *i*.
- Negate the result, again without loss of precision.
- Divide the result by 2 to the power 31, rounding to nearest with ties towards +∞.
- Add the result to `op1[i]`, without loss of precision.
- Saturate the result to the range of `int32_t`.

## svqrdmlsh_lane[_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqrdmlsh_lane%5B_s64%5D

### Signature (source notation)

```c
svint64_t svqrdmlsh_lane[_s64](svint64_t op1, svint64_t op2, svint64_t op3, uint64_t imm_index);
```

### Description

Saturating rounding doubling multiply-subtract high

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Saturating multiply-accumulate

- SME attributes: Not specified by source.

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
    "register": "Zop1.D|Ztied1.D"
  },
  "op2": {
    "register": "Zop2.D"
  },
  "op3": {
    "register": "Zop3.D"
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
    "Zresult.D|Ztied1.D": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
SQRDMLSH Ztied1.D, Zop2.D, Zop3.D[imm_index]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQRDMLSH--indexed---Signed-saturating-rounding-doubling-multiply-subtract-high-from-accumulator--indexed--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SQRDMLSH Zresult.D, Zop2.D, Zop3.D[imm_index]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQRDMLSH--indexed---Signed-saturating-rounding-doubling-multiply-subtract-high-from-accumulator--indexed--

### Operation

Source operation ID: `SveOperation_svqrdmlsh_lane_s64`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Multiply `op2[i]` by `op3[base + imm_index]`, without loss of precision, where *base* is the index of the first element in the same 128-bit quadword as *i*.
- Negate the result, again without loss of precision.
- Divide the result by 2 to the power 63, rounding to nearest with ties towards +∞.
- Add the result to `op1[i]`, without loss of precision.
- Saturate the result to the range of `int64_t`.

