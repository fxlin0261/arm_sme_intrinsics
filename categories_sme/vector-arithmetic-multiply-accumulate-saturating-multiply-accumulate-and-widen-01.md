# SME / Vector arithmetic / Multiply-accumulate / Saturating multiply-accumulate and widen — Part 1

## svqdmlalb[_n_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdmlalb%5B_n_s16%5D

### Signature (source notation)

```c
svint16_t svqdmlalb[_n_s16](svint16_t op1, svint8_t op2, int8_t op3);
```

### Description

Saturating doubling multiply-add long (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Saturating multiply-accumulate and widen

- SME attributes: Not specified by source.

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
    "Zresult.H|Ztied1.H": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
SQDMLALB Ztied1.H, Zop2.B, Zop3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDMLALB--vectors---Signed-saturating-doubling-multiply-add-long-to-accumulator--bottom--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SQDMLALB Zresult.H, Zop2.B, Zop3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDMLALB--vectors---Signed-saturating-doubling-multiply-add-long-to-accumulator--bottom--

### Operation

Source operation ID: `SveOperation_svqdmlalb_n_s16`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Multiply `op2[i * 2]` by `op3`, without loss of precision.
- Double the result, again without loss of precision.
- Saturate the result to the range of `int16_t`.
- Add the result to `op1[i]`, without loss of precision.
- Saturate the result to the range of `int16_t`.

## svqdmlalb[_n_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdmlalb%5B_n_s32%5D

### Signature (source notation)

```c
svint32_t svqdmlalb[_n_s32](svint32_t op1, svint16_t op2, int16_t op3);
```

### Description

Saturating doubling multiply-add long (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Saturating multiply-accumulate and widen

- SME attributes: Not specified by source.

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
    "Zresult.S|Ztied1.S": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
SQDMLALB Ztied1.S, Zop2.H, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDMLALB--vectors---Signed-saturating-doubling-multiply-add-long-to-accumulator--bottom--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SQDMLALB Zresult.S, Zop2.H, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDMLALB--vectors---Signed-saturating-doubling-multiply-add-long-to-accumulator--bottom--

### Operation

Source operation ID: `SveOperation_svqdmlalb_n_s32`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Multiply `op2[i * 2]` by `op3`, without loss of precision.
- Double the result, again without loss of precision.
- Saturate the result to the range of `int32_t`.
- Add the result to `op1[i]`, without loss of precision.
- Saturate the result to the range of `int32_t`.

## svqdmlalb[_n_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdmlalb%5B_n_s64%5D

### Signature (source notation)

```c
svint64_t svqdmlalb[_n_s64](svint64_t op1, svint32_t op2, int32_t op3);
```

### Description

Saturating doubling multiply-add long (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Saturating multiply-accumulate and widen

- SME attributes: Not specified by source.

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
    "Zresult.D|Ztied1.D": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
SQDMLALB Ztied1.D, Zop2.S, Zop3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDMLALB--vectors---Signed-saturating-doubling-multiply-add-long-to-accumulator--bottom--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SQDMLALB Zresult.D, Zop2.S, Zop3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDMLALB--vectors---Signed-saturating-doubling-multiply-add-long-to-accumulator--bottom--

### Operation

Source operation ID: `SveOperation_svqdmlalb_n_s64`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Multiply `op2[i * 2]` by `op3`, without loss of precision.
- Double the result, again without loss of precision.
- Saturate the result to the range of `int64_t`.
- Add the result to `op1[i]`, without loss of precision.
- Saturate the result to the range of `int64_t`.

## svqdmlalb[_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdmlalb%5B_s16%5D

### Signature (source notation)

```c
svint16_t svqdmlalb[_s16](svint16_t op1, svint8_t op2, svint8_t op3);
```

### Description

Saturating doubling multiply-add long (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Saturating multiply-accumulate and widen

- SME attributes: Not specified by source.

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
    "Zresult.H|Ztied1.H": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
SQDMLALB Ztied1.H, Zop2.B, Zop3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDMLALB--vectors---Signed-saturating-doubling-multiply-add-long-to-accumulator--bottom--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SQDMLALB Zresult.H, Zop2.B, Zop3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDMLALB--vectors---Signed-saturating-doubling-multiply-add-long-to-accumulator--bottom--

### Operation

Source operation ID: `SveOperation_svqdmlalb_s16`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Multiply `op2[i * 2]` by `op3[i * 2]`, without loss of precision.
- Double the result, again without loss of precision.
- Saturate the result to the range of `int16_t`.
- Add the result to `op1[i]`, without loss of precision.
- Saturate the result to the range of `int16_t`.

## svqdmlalb[_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdmlalb%5B_s32%5D

### Signature (source notation)

```c
svint32_t svqdmlalb[_s32](svint32_t op1, svint16_t op2, svint16_t op3);
```

### Description

Saturating doubling multiply-add long (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Saturating multiply-accumulate and widen

- SME attributes: Not specified by source.

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
    "Zresult.S|Ztied1.S": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
SQDMLALB Ztied1.S, Zop2.H, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDMLALB--vectors---Signed-saturating-doubling-multiply-add-long-to-accumulator--bottom--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SQDMLALB Zresult.S, Zop2.H, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDMLALB--vectors---Signed-saturating-doubling-multiply-add-long-to-accumulator--bottom--

### Operation

Source operation ID: `SveOperation_svqdmlalb_s32`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Multiply `op2[i * 2]` by `op3[i * 2]`, without loss of precision.
- Double the result, again without loss of precision.
- Saturate the result to the range of `int32_t`.
- Add the result to `op1[i]`, without loss of precision.
- Saturate the result to the range of `int32_t`.

## svqdmlalb[_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdmlalb%5B_s64%5D

### Signature (source notation)

```c
svint64_t svqdmlalb[_s64](svint64_t op1, svint32_t op2, svint32_t op3);
```

### Description

Saturating doubling multiply-add long (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Saturating multiply-accumulate and widen

- SME attributes: Not specified by source.

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
    "Zresult.D|Ztied1.D": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
SQDMLALB Ztied1.D, Zop2.S, Zop3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDMLALB--vectors---Signed-saturating-doubling-multiply-add-long-to-accumulator--bottom--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SQDMLALB Zresult.D, Zop2.S, Zop3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDMLALB--vectors---Signed-saturating-doubling-multiply-add-long-to-accumulator--bottom--

### Operation

Source operation ID: `SveOperation_svqdmlalb_s64`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Multiply `op2[i * 2]` by `op3[i * 2]`, without loss of precision.
- Double the result, again without loss of precision.
- Saturate the result to the range of `int64_t`.
- Add the result to `op1[i]`, without loss of precision.
- Saturate the result to the range of `int64_t`.

## svqdmlalb_lane[_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdmlalb_lane%5B_s32%5D

### Signature (source notation)

```c
svint32_t svqdmlalb_lane[_s32](svint32_t op1, svint16_t op2, svint16_t op3, uint64_t imm_index);
```

### Description

Saturating doubling multiply-add long (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Saturating multiply-accumulate and widen

- SME attributes: Not specified by source.

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
    "Zresult.S|Ztied1.S": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
SQDMLALB Ztied1.S, Zop2.H, Zop3.H[imm_index]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDMLALB--indexed---Signed-saturating-doubling-multiply-add-long-to-accumulator--bottom--indexed--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SQDMLALB Zresult.S, Zop2.H, Zop3.H[imm_index]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDMLALB--indexed---Signed-saturating-doubling-multiply-add-long-to-accumulator--bottom--indexed--

### Operation

Source operation ID: `SveOperation_svqdmlalb_lane_s32`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Multiply `op2[i * 2]` by `op3[base + imm_index]`, without loss of precision, where `op3[base]` is the first element in the same 128-bit quadword as `op3[i * 2]`.
- Double the result, again without loss of precision.
- Saturate the result to the range of `int32_t`.
- Add the result to `op1[i]`, without loss of precision.
- Saturate the result to the range of `int32_t`.

## svqdmlalb_lane[_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdmlalb_lane%5B_s64%5D

### Signature (source notation)

```c
svint64_t svqdmlalb_lane[_s64](svint64_t op1, svint32_t op2, svint32_t op3, uint64_t imm_index);
```

### Description

Saturating doubling multiply-add long (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Saturating multiply-accumulate and widen

- SME attributes: Not specified by source.

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
    "Zresult.D|Ztied1.D": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
SQDMLALB Ztied1.D, Zop2.S, Zop3.S[imm_index]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDMLALB--indexed---Signed-saturating-doubling-multiply-add-long-to-accumulator--bottom--indexed--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SQDMLALB Zresult.D, Zop2.S, Zop3.S[imm_index]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDMLALB--indexed---Signed-saturating-doubling-multiply-add-long-to-accumulator--bottom--indexed--

### Operation

Source operation ID: `SveOperation_svqdmlalb_lane_s64`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Multiply `op2[i * 2]` by `op3[base + imm_index]`, without loss of precision, where `op3[base]` is the first element in the same 128-bit quadword as `op3[i * 2]`.
- Double the result, again without loss of precision.
- Saturate the result to the range of `int64_t`.
- Add the result to `op1[i]`, without loss of precision.
- Saturate the result to the range of `int64_t`.

## svqdmlalbt[_n_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdmlalbt%5B_n_s16%5D

### Signature (source notation)

```c
svint16_t svqdmlalbt[_n_s16](svint16_t op1, svint8_t op2, int8_t op3);
```

### Description

Saturating doubling multiply-add long (bottom × top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Saturating multiply-accumulate and widen

- SME attributes: Not specified by source.

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
    "Zresult.H|Ztied1.H": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
SQDMLALBT Ztied1.H, Zop2.B, Zop3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDMLALBT--Signed-saturating-doubling-multiply-add-long-to-accumulator--bottom---top--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SQDMLALBT Zresult.H, Zop2.B, Zop3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDMLALBT--Signed-saturating-doubling-multiply-add-long-to-accumulator--bottom---top--

### Operation

Source operation ID: `SveOperation_svqdmlalb_n_s16`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Multiply `op2[i * 2]` by `op3`, without loss of precision.
- Double the result, again without loss of precision.
- Saturate the result to the range of `int16_t`.
- Add the result to `op1[i]`, without loss of precision.
- Saturate the result to the range of `int16_t`.

## svqdmlalbt[_n_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdmlalbt%5B_n_s32%5D

### Signature (source notation)

```c
svint32_t svqdmlalbt[_n_s32](svint32_t op1, svint16_t op2, int16_t op3);
```

### Description

Saturating doubling multiply-add long (bottom × top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Saturating multiply-accumulate and widen

- SME attributes: Not specified by source.

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
    "Zresult.S|Ztied1.S": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
SQDMLALBT Ztied1.S, Zop2.H, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDMLALBT--Signed-saturating-doubling-multiply-add-long-to-accumulator--bottom---top--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SQDMLALBT Zresult.S, Zop2.H, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDMLALBT--Signed-saturating-doubling-multiply-add-long-to-accumulator--bottom---top--

### Operation

Source operation ID: `SveOperation_svqdmlalb_n_s32`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Multiply `op2[i * 2]` by `op3`, without loss of precision.
- Double the result, again without loss of precision.
- Saturate the result to the range of `int32_t`.
- Add the result to `op1[i]`, without loss of precision.
- Saturate the result to the range of `int32_t`.

## svqdmlalbt[_n_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdmlalbt%5B_n_s64%5D

### Signature (source notation)

```c
svint64_t svqdmlalbt[_n_s64](svint64_t op1, svint32_t op2, int32_t op3);
```

### Description

Saturating doubling multiply-add long (bottom × top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Saturating multiply-accumulate and widen

- SME attributes: Not specified by source.

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
    "Zresult.D|Ztied1.D": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
SQDMLALBT Ztied1.D, Zop2.S, Zop3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDMLALBT--Signed-saturating-doubling-multiply-add-long-to-accumulator--bottom---top--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SQDMLALBT Zresult.D, Zop2.S, Zop3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDMLALBT--Signed-saturating-doubling-multiply-add-long-to-accumulator--bottom---top--

### Operation

Source operation ID: `SveOperation_svqdmlalb_n_s64`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Multiply `op2[i * 2]` by `op3`, without loss of precision.
- Double the result, again without loss of precision.
- Saturate the result to the range of `int64_t`.
- Add the result to `op1[i]`, without loss of precision.
- Saturate the result to the range of `int64_t`.

## svqdmlalbt[_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdmlalbt%5B_s16%5D

### Signature (source notation)

```c
svint16_t svqdmlalbt[_s16](svint16_t op1, svint8_t op2, svint8_t op3);
```

### Description

Saturating doubling multiply-add long (bottom × top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Saturating multiply-accumulate and widen

- SME attributes: Not specified by source.

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
    "Zresult.H|Ztied1.H": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
SQDMLALBT Ztied1.H, Zop2.B, Zop3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDMLALBT--Signed-saturating-doubling-multiply-add-long-to-accumulator--bottom---top--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SQDMLALBT Zresult.H, Zop2.B, Zop3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDMLALBT--Signed-saturating-doubling-multiply-add-long-to-accumulator--bottom---top--

### Operation

Source operation ID: `SveOperation_svqdmlalbt_s16`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Multiply `op2[i * 2]` by `op3[i * 2 + 1]`, without loss of precision.
- Double the result, again without loss of precision.
- Saturate the result to the range of `int16_t`.
- Add the result to `op1[i]`, without loss of precision.
- Saturate the result to the range of `int16_t`.

## svqdmlalbt[_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdmlalbt%5B_s32%5D

### Signature (source notation)

```c
svint32_t svqdmlalbt[_s32](svint32_t op1, svint16_t op2, svint16_t op3);
```

### Description

Saturating doubling multiply-add long (bottom × top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Saturating multiply-accumulate and widen

- SME attributes: Not specified by source.

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
    "Zresult.S|Ztied1.S": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
SQDMLALBT Ztied1.S, Zop2.H, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDMLALBT--Signed-saturating-doubling-multiply-add-long-to-accumulator--bottom---top--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SQDMLALBT Zresult.S, Zop2.H, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDMLALBT--Signed-saturating-doubling-multiply-add-long-to-accumulator--bottom---top--

### Operation

Source operation ID: `SveOperation_svqdmlalbt_s32`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Multiply `op2[i * 2]` by `op3[i * 2 + 1]`, without loss of precision.
- Double the result, again without loss of precision.
- Saturate the result to the range of `int32_t`.
- Add the result to `op1[i]`, without loss of precision.
- Saturate the result to the range of `int32_t`.

## svqdmlalbt[_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdmlalbt%5B_s64%5D

### Signature (source notation)

```c
svint64_t svqdmlalbt[_s64](svint64_t op1, svint32_t op2, svint32_t op3);
```

### Description

Saturating doubling multiply-add long (bottom × top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Saturating multiply-accumulate and widen

- SME attributes: Not specified by source.

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
    "Zresult.D|Ztied1.D": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
SQDMLALBT Ztied1.D, Zop2.S, Zop3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDMLALBT--Signed-saturating-doubling-multiply-add-long-to-accumulator--bottom---top--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SQDMLALBT Zresult.D, Zop2.S, Zop3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDMLALBT--Signed-saturating-doubling-multiply-add-long-to-accumulator--bottom---top--

### Operation

Source operation ID: `SveOperation_svqdmlalbt_s64`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Multiply `op2[i * 2]` by `op3[i * 2 + 1]`, without loss of precision.
- Double the result, again without loss of precision.
- Saturate the result to the range of `int64_t`.
- Add the result to `op1[i]`, without loss of precision.
- Saturate the result to the range of `int64_t`.

## svqdmlalt[_n_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdmlalt%5B_n_s16%5D

### Signature (source notation)

```c
svint16_t svqdmlalt[_n_s16](svint16_t op1, svint8_t op2, int8_t op3);
```

### Description

Saturating doubling multiply-add long (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Saturating multiply-accumulate and widen

- SME attributes: Not specified by source.

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
    "Zresult.H|Ztied1.H": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
SQDMLALT Ztied1.H, Zop2.B, Zop3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDMLALT--vectors---Signed-saturating-doubling-multiply-add-long-to-accumulator--top--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SQDMLALT Zresult.H, Zop2.B, Zop3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDMLALT--vectors---Signed-saturating-doubling-multiply-add-long-to-accumulator--top--

### Operation

Source operation ID: `SveOperation_svqdmlalt_n_s16`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Multiply `op2[i * 2 + 1]` by `op3`, without loss of precision.
- Double the result, again without loss of precision.
- Saturate the result to the range of `int16_t`.
- Add the result to `op1[i]`, without loss of precision.
- Saturate the result to the range of `int16_t`.

## svqdmlalt[_n_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdmlalt%5B_n_s32%5D

### Signature (source notation)

```c
svint32_t svqdmlalt[_n_s32](svint32_t op1, svint16_t op2, int16_t op3);
```

### Description

Saturating doubling multiply-add long (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Saturating multiply-accumulate and widen

- SME attributes: Not specified by source.

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
    "Zresult.S|Ztied1.S": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
SQDMLALT Ztied1.S, Zop2.H, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDMLALT--vectors---Signed-saturating-doubling-multiply-add-long-to-accumulator--top--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SQDMLALT Zresult.S, Zop2.H, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDMLALT--vectors---Signed-saturating-doubling-multiply-add-long-to-accumulator--top--

### Operation

Source operation ID: `SveOperation_svqdmlalt_n_s32`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Multiply `op2[i * 2 + 1]` by `op3`, without loss of precision.
- Double the result, again without loss of precision.
- Saturate the result to the range of `int32_t`.
- Add the result to `op1[i]`, without loss of precision.
- Saturate the result to the range of `int32_t`.

## svqdmlalt[_n_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdmlalt%5B_n_s64%5D

### Signature (source notation)

```c
svint64_t svqdmlalt[_n_s64](svint64_t op1, svint32_t op2, int32_t op3);
```

### Description

Saturating doubling multiply-add long (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Saturating multiply-accumulate and widen

- SME attributes: Not specified by source.

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
    "Zresult.D|Ztied1.D": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
SQDMLALT Ztied1.D, Zop2.S, Zop3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDMLALT--vectors---Signed-saturating-doubling-multiply-add-long-to-accumulator--top--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SQDMLALT Zresult.D, Zop2.S, Zop3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDMLALT--vectors---Signed-saturating-doubling-multiply-add-long-to-accumulator--top--

### Operation

Source operation ID: `SveOperation_svqdmlalt_n_s64`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Multiply `op2[i * 2 + 1]` by `op3`, without loss of precision.
- Double the result, again without loss of precision.
- Saturate the result to the range of `int64_t`.
- Add the result to `op1[i]`, without loss of precision.
- Saturate the result to the range of `int64_t`.

## svqdmlalt[_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdmlalt%5B_s16%5D

### Signature (source notation)

```c
svint16_t svqdmlalt[_s16](svint16_t op1, svint8_t op2, svint8_t op3);
```

### Description

Saturating doubling multiply-add long (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Saturating multiply-accumulate and widen

- SME attributes: Not specified by source.

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
    "Zresult.H|Ztied1.H": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
SQDMLALT Ztied1.H, Zop2.B, Zop3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDMLALT--vectors---Signed-saturating-doubling-multiply-add-long-to-accumulator--top--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SQDMLALT Zresult.H, Zop2.B, Zop3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDMLALT--vectors---Signed-saturating-doubling-multiply-add-long-to-accumulator--top--

### Operation

Source operation ID: `SveOperation_svqdmlalt_s16`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Multiply `op2[i * 2 + 1]` by `op3[i * 2 + 1]`, without loss of precision.
- Double the result, again without loss of precision.
- Saturate the result to the range of `int16_t`.
- Add the result to `op1[i]`, without loss of precision.
- Saturate the result to the range of `int16_t`.

## svqdmlalt[_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdmlalt%5B_s32%5D

### Signature (source notation)

```c
svint32_t svqdmlalt[_s32](svint32_t op1, svint16_t op2, svint16_t op3);
```

### Description

Saturating doubling multiply-add long (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Saturating multiply-accumulate and widen

- SME attributes: Not specified by source.

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
    "Zresult.S|Ztied1.S": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
SQDMLALT Ztied1.S, Zop2.H, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDMLALT--vectors---Signed-saturating-doubling-multiply-add-long-to-accumulator--top--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SQDMLALT Zresult.S, Zop2.H, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDMLALT--vectors---Signed-saturating-doubling-multiply-add-long-to-accumulator--top--

### Operation

Source operation ID: `SveOperation_svqdmlalt_s32`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Multiply `op2[i * 2 + 1]` by `op3[i * 2 + 1]`, without loss of precision.
- Double the result, again without loss of precision.
- Saturate the result to the range of `int32_t`.
- Add the result to `op1[i]`, without loss of precision.
- Saturate the result to the range of `int32_t`.

## svqdmlalt[_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdmlalt%5B_s64%5D

### Signature (source notation)

```c
svint64_t svqdmlalt[_s64](svint64_t op1, svint32_t op2, svint32_t op3);
```

### Description

Saturating doubling multiply-add long (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Saturating multiply-accumulate and widen

- SME attributes: Not specified by source.

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
    "Zresult.D|Ztied1.D": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
SQDMLALT Ztied1.D, Zop2.S, Zop3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDMLALT--vectors---Signed-saturating-doubling-multiply-add-long-to-accumulator--top--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SQDMLALT Zresult.D, Zop2.S, Zop3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDMLALT--vectors---Signed-saturating-doubling-multiply-add-long-to-accumulator--top--

### Operation

Source operation ID: `SveOperation_svqdmlalt_s64`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Multiply `op2[i * 2 + 1]` by `op3[i * 2 + 1]`, without loss of precision.
- Double the result, again without loss of precision.
- Saturate the result to the range of `int64_t`.
- Add the result to `op1[i]`, without loss of precision.
- Saturate the result to the range of `int64_t`.

## svqdmlalt_lane[_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdmlalt_lane%5B_s32%5D

### Signature (source notation)

```c
svint32_t svqdmlalt_lane[_s32](svint32_t op1, svint16_t op2, svint16_t op3, uint64_t imm_index);
```

### Description

Saturating doubling multiply-add long (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Saturating multiply-accumulate and widen

- SME attributes: Not specified by source.

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
    "Zresult.S|Ztied1.S": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
SQDMLALT Ztied1.S, Zop2.H, Zop3.H[imm_index]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDMLALT--indexed---Signed-saturating-doubling-multiply-add-long-to-accumulator--top--indexed--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SQDMLALT Zresult.S, Zop2.H, Zop3.H[imm_index]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDMLALT--indexed---Signed-saturating-doubling-multiply-add-long-to-accumulator--top--indexed--

### Operation

Source operation ID: `SveOperation_svqdmlalt_lane_s32`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Multiply `op2[i * 2 + 1]` by `op3[base + imm_index]`, without loss of precision, where `op3[base]` is the first element in the same 128-bit quadword as `op3[i * 2]`.
- Double the result, again without loss of precision.
- Saturate the result to the range of `int32_t`.
- Add the result to `op1[i]`, without loss of precision.
- Saturate the result to the range of `int32_t`.

## svqdmlalt_lane[_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdmlalt_lane%5B_s64%5D

### Signature (source notation)

```c
svint64_t svqdmlalt_lane[_s64](svint64_t op1, svint32_t op2, svint32_t op3, uint64_t imm_index);
```

### Description

Saturating doubling multiply-add long (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Saturating multiply-accumulate and widen

- SME attributes: Not specified by source.

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
    "Zresult.D|Ztied1.D": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
SQDMLALT Ztied1.D, Zop2.S, Zop3.S[imm_index]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDMLALT--indexed---Signed-saturating-doubling-multiply-add-long-to-accumulator--top--indexed--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SQDMLALT Zresult.D, Zop2.S, Zop3.S[imm_index]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDMLALT--indexed---Signed-saturating-doubling-multiply-add-long-to-accumulator--top--indexed--

### Operation

Source operation ID: `SveOperation_svqdmlalt_lane_s64`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Multiply `op2[i * 2 + 1]` by `op3[base + imm_index]`, without loss of precision, where `op3[base]` is the first element in the same 128-bit quadword as `op3[i * 2]`.
- Double the result, again without loss of precision.
- Saturate the result to the range of `int64_t`.
- Add the result to `op1[i]`, without loss of precision.
- Saturate the result to the range of `int64_t`.

## svqdmlslb[_n_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdmlslb%5B_n_s16%5D

### Signature (source notation)

```c
svint16_t svqdmlslb[_n_s16](svint16_t op1, svint8_t op2, int8_t op3);
```

### Description

Saturating doubling multiply-subtract long (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Saturating multiply-accumulate and widen

- SME attributes: Not specified by source.

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
    "Zresult.H|Ztied1.H": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
SQDMLSLB Ztied1.H, Zop2.B, Zop3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDMLSLB--vectors---Signed-saturating-doubling-multiply-subtract-long-from-accumulator--bottom--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SQDMLSLB Zresult.H, Zop2.B, Zop3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDMLSLB--vectors---Signed-saturating-doubling-multiply-subtract-long-from-accumulator--bottom--

### Operation

Source operation ID: `SveOperation_svqdmlslb_n_s16`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Multiply `op2[i * 2]` by `op3`, without loss of precision.
- Double the result, again without loss of precision.
- Saturate the result to the range of `int16_t`.
- Subtract the result from `op1[i]`, without loss of precision.
- Saturate the result to the range of `int16_t`.

## svqdmlslb[_n_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdmlslb%5B_n_s32%5D

### Signature (source notation)

```c
svint32_t svqdmlslb[_n_s32](svint32_t op1, svint16_t op2, int16_t op3);
```

### Description

Saturating doubling multiply-subtract long (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Saturating multiply-accumulate and widen

- SME attributes: Not specified by source.

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
    "Zresult.S|Ztied1.S": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
SQDMLSLB Ztied1.S, Zop2.H, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDMLSLB--vectors---Signed-saturating-doubling-multiply-subtract-long-from-accumulator--bottom--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SQDMLSLB Zresult.S, Zop2.H, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDMLSLB--vectors---Signed-saturating-doubling-multiply-subtract-long-from-accumulator--bottom--

### Operation

Source operation ID: `SveOperation_svqdmlslb_n_s32`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Multiply `op2[i * 2]` by `op3`, without loss of precision.
- Double the result, again without loss of precision.
- Saturate the result to the range of `int32_t`.
- Subtract the result from `op1[i]`, without loss of precision.
- Saturate the result to the range of `int32_t`.

## svqdmlslb[_n_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdmlslb%5B_n_s64%5D

### Signature (source notation)

```c
svint64_t svqdmlslb[_n_s64](svint64_t op1, svint32_t op2, int32_t op3);
```

### Description

Saturating doubling multiply-subtract long (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Saturating multiply-accumulate and widen

- SME attributes: Not specified by source.

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
    "Zresult.D|Ztied1.D": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
SQDMLSLB Ztied1.D, Zop2.S, Zop3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDMLSLB--vectors---Signed-saturating-doubling-multiply-subtract-long-from-accumulator--bottom--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SQDMLSLB Zresult.D, Zop2.S, Zop3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDMLSLB--vectors---Signed-saturating-doubling-multiply-subtract-long-from-accumulator--bottom--

### Operation

Source operation ID: `SveOperation_svqdmlslb_n_s64`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Multiply `op2[i * 2]` by `op3`, without loss of precision.
- Double the result, again without loss of precision.
- Saturate the result to the range of `int64_t`.
- Subtract the result from `op1[i]`, without loss of precision.
- Saturate the result to the range of `int64_t`.

## svqdmlslb[_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdmlslb%5B_s16%5D

### Signature (source notation)

```c
svint16_t svqdmlslb[_s16](svint16_t op1, svint8_t op2, svint8_t op3);
```

### Description

Saturating doubling multiply-subtract long (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Saturating multiply-accumulate and widen

- SME attributes: Not specified by source.

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
    "Zresult.H|Ztied1.H": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
SQDMLSLB Ztied1.H, Zop2.B, Zop3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDMLSLB--vectors---Signed-saturating-doubling-multiply-subtract-long-from-accumulator--bottom--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SQDMLSLB Zresult.H, Zop2.B, Zop3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDMLSLB--vectors---Signed-saturating-doubling-multiply-subtract-long-from-accumulator--bottom--

### Operation

Source operation ID: `SveOperation_svqdmlslb_s16`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Multiply `op2[i * 2]` by `op3[i * 2]`, without loss of precision.
- Double the result, again without loss of precision.
- Saturate the result to the range of `int16_t`.
- Subtract the result from `op1[i]`, without loss of precision.
- Saturate the result to the range of `int16_t`.

## svqdmlslb[_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdmlslb%5B_s32%5D

### Signature (source notation)

```c
svint32_t svqdmlslb[_s32](svint32_t op1, svint16_t op2, svint16_t op3);
```

### Description

Saturating doubling multiply-subtract long (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Saturating multiply-accumulate and widen

- SME attributes: Not specified by source.

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
    "Zresult.S|Ztied1.S": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
SQDMLSLB Ztied1.S, Zop2.H, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDMLSLB--vectors---Signed-saturating-doubling-multiply-subtract-long-from-accumulator--bottom--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SQDMLSLB Zresult.S, Zop2.H, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDMLSLB--vectors---Signed-saturating-doubling-multiply-subtract-long-from-accumulator--bottom--

### Operation

Source operation ID: `SveOperation_svqdmlslb_s32`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Multiply `op2[i * 2]` by `op3[i * 2]`, without loss of precision.
- Double the result, again without loss of precision.
- Saturate the result to the range of `int32_t`.
- Subtract the result from `op1[i]`, without loss of precision.
- Saturate the result to the range of `int32_t`.

## svqdmlslb[_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdmlslb%5B_s64%5D

### Signature (source notation)

```c
svint64_t svqdmlslb[_s64](svint64_t op1, svint32_t op2, svint32_t op3);
```

### Description

Saturating doubling multiply-subtract long (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Saturating multiply-accumulate and widen

- SME attributes: Not specified by source.

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
    "Zresult.D|Ztied1.D": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
SQDMLSLB Ztied1.D, Zop2.S, Zop3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDMLSLB--vectors---Signed-saturating-doubling-multiply-subtract-long-from-accumulator--bottom--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SQDMLSLB Zresult.D, Zop2.S, Zop3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDMLSLB--vectors---Signed-saturating-doubling-multiply-subtract-long-from-accumulator--bottom--

### Operation

Source operation ID: `SveOperation_svqdmlslb_s64`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Multiply `op2[i * 2]` by `op3[i * 2]`, without loss of precision.
- Double the result, again without loss of precision.
- Saturate the result to the range of `int64_t`.
- Subtract the result from `op1[i]`, without loss of precision.
- Saturate the result to the range of `int64_t`.

## svqdmlslb_lane[_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdmlslb_lane%5B_s32%5D

### Signature (source notation)

```c
svint32_t svqdmlslb_lane[_s32](svint32_t op1, svint16_t op2, svint16_t op3, uint64_t imm_index);
```

### Description

Saturating doubling multiply-subtract long (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Saturating multiply-accumulate and widen

- SME attributes: Not specified by source.

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
    "Zresult.S|Ztied1.S": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
SQDMLSLB Ztied1.S, Zop2.H, Zop3.H[imm_index]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDMLSLB--indexed---Signed-saturating-doubling-multiply-subtract-long-from-accumulator--bottom--indexed--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SQDMLSLB Zresult.S, Zop2.H, Zop3.H[imm_index]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDMLSLB--indexed---Signed-saturating-doubling-multiply-subtract-long-from-accumulator--bottom--indexed--

### Operation

Source operation ID: `SveOperation_svqdmlslb_lane_s32`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Multiply `op2[i * 2]` by `op3[base + imm_index]`, without loss of precision, where `op3[base]` is the first element in the same 128-bit quadword as `op3[i * 2]`.
- Double the result, again without loss of precision.
- Saturate the result to the range of `int32_t`.
- Subtract the result from `op1[i]`, without loss of precision.
- Saturate the result to the range of `int32_t`.

## svqdmlslb_lane[_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdmlslb_lane%5B_s64%5D

### Signature (source notation)

```c
svint64_t svqdmlslb_lane[_s64](svint64_t op1, svint32_t op2, svint32_t op3, uint64_t imm_index);
```

### Description

Saturating doubling multiply-subtract long (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Saturating multiply-accumulate and widen

- SME attributes: Not specified by source.

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
    "Zresult.D|Ztied1.D": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
SQDMLSLB Ztied1.D, Zop2.S, Zop3.S[imm_index]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDMLSLB--indexed---Signed-saturating-doubling-multiply-subtract-long-from-accumulator--bottom--indexed--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SQDMLSLB Zresult.D, Zop2.S, Zop3.S[imm_index]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDMLSLB--indexed---Signed-saturating-doubling-multiply-subtract-long-from-accumulator--bottom--indexed--

### Operation

Source operation ID: `SveOperation_svqdmlslb_lane_s64`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Multiply `op2[i * 2]` by `op3[base + imm_index]`, without loss of precision, where `op3[base]` is the first element in the same 128-bit quadword as `op3[i * 2]`.
- Double the result, again without loss of precision.
- Saturate the result to the range of `int64_t`.
- Subtract the result from `op1[i]`, without loss of precision.
- Saturate the result to the range of `int64_t`.

## svqdmlslbt[_n_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdmlslbt%5B_n_s16%5D

### Signature (source notation)

```c
svint16_t svqdmlslbt[_n_s16](svint16_t op1, svint8_t op2, int8_t op3);
```

### Description

Saturating doubling multiply-subtract long (bottom × top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Saturating multiply-accumulate and widen

- SME attributes: Not specified by source.

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
    "Zresult.H|Ztied1.H": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
SQDMLSLBT Ztied1.H, Zop2.B, Zop3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDMLSLBT--Signed-saturating-doubling-multiply-subtract-long-from-accumulator--bottom---top--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SQDMLSLBT Zresult.H, Zop2.B, Zop3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDMLSLBT--Signed-saturating-doubling-multiply-subtract-long-from-accumulator--bottom---top--

### Operation

Source operation ID: `SveOperation_svqdmlslb_n_s16`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Multiply `op2[i * 2]` by `op3`, without loss of precision.
- Double the result, again without loss of precision.
- Saturate the result to the range of `int16_t`.
- Subtract the result from `op1[i]`, without loss of precision.
- Saturate the result to the range of `int16_t`.

## svqdmlslbt[_n_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdmlslbt%5B_n_s32%5D

### Signature (source notation)

```c
svint32_t svqdmlslbt[_n_s32](svint32_t op1, svint16_t op2, int16_t op3);
```

### Description

Saturating doubling multiply-subtract long (bottom × top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Saturating multiply-accumulate and widen

- SME attributes: Not specified by source.

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
    "Zresult.S|Ztied1.S": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
SQDMLSLBT Ztied1.S, Zop2.H, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDMLSLBT--Signed-saturating-doubling-multiply-subtract-long-from-accumulator--bottom---top--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SQDMLSLBT Zresult.S, Zop2.H, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDMLSLBT--Signed-saturating-doubling-multiply-subtract-long-from-accumulator--bottom---top--

### Operation

Source operation ID: `SveOperation_svqdmlslb_n_s32`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Multiply `op2[i * 2]` by `op3`, without loss of precision.
- Double the result, again without loss of precision.
- Saturate the result to the range of `int32_t`.
- Subtract the result from `op1[i]`, without loss of precision.
- Saturate the result to the range of `int32_t`.

## svqdmlslbt[_n_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdmlslbt%5B_n_s64%5D

### Signature (source notation)

```c
svint64_t svqdmlslbt[_n_s64](svint64_t op1, svint32_t op2, int32_t op3);
```

### Description

Saturating doubling multiply-subtract long (bottom × top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Saturating multiply-accumulate and widen

- SME attributes: Not specified by source.

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
    "Zresult.D|Ztied1.D": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
SQDMLSLBT Ztied1.D, Zop2.S, Zop3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDMLSLBT--Signed-saturating-doubling-multiply-subtract-long-from-accumulator--bottom---top--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SQDMLSLBT Zresult.D, Zop2.S, Zop3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDMLSLBT--Signed-saturating-doubling-multiply-subtract-long-from-accumulator--bottom---top--

### Operation

Source operation ID: `SveOperation_svqdmlslb_n_s64`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Multiply `op2[i * 2]` by `op3`, without loss of precision.
- Double the result, again without loss of precision.
- Saturate the result to the range of `int64_t`.
- Subtract the result from `op1[i]`, without loss of precision.
- Saturate the result to the range of `int64_t`.

## svqdmlslbt[_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdmlslbt%5B_s16%5D

### Signature (source notation)

```c
svint16_t svqdmlslbt[_s16](svint16_t op1, svint8_t op2, svint8_t op3);
```

### Description

Saturating doubling multiply-subtract long (bottom × top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Saturating multiply-accumulate and widen

- SME attributes: Not specified by source.

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
    "Zresult.H|Ztied1.H": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
SQDMLSLBT Ztied1.H, Zop2.B, Zop3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDMLSLBT--Signed-saturating-doubling-multiply-subtract-long-from-accumulator--bottom---top--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SQDMLSLBT Zresult.H, Zop2.B, Zop3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDMLSLBT--Signed-saturating-doubling-multiply-subtract-long-from-accumulator--bottom---top--

### Operation

Source operation ID: `SveOperation_svqdmlslbt_s16`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Multiply `op2[i * 2]` by `op3[i * 2 + 1]`, without loss of precision.
- Double the result, again without loss of precision.
- Saturate the result to the range of `int16_t`.
- Subtract the result from `op1[i]`, without loss of precision.
- Saturate the result to the range of `int16_t`.

## svqdmlslbt[_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdmlslbt%5B_s32%5D

### Signature (source notation)

```c
svint32_t svqdmlslbt[_s32](svint32_t op1, svint16_t op2, svint16_t op3);
```

### Description

Saturating doubling multiply-subtract long (bottom × top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Saturating multiply-accumulate and widen

- SME attributes: Not specified by source.

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
    "Zresult.S|Ztied1.S": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
SQDMLSLBT Ztied1.S, Zop2.H, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDMLSLBT--Signed-saturating-doubling-multiply-subtract-long-from-accumulator--bottom---top--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SQDMLSLBT Zresult.S, Zop2.H, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDMLSLBT--Signed-saturating-doubling-multiply-subtract-long-from-accumulator--bottom---top--

### Operation

Source operation ID: `SveOperation_svqdmlslbt_s32`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Multiply `op2[i * 2]` by `op3[i * 2 + 1]`, without loss of precision.
- Double the result, again without loss of precision.
- Saturate the result to the range of `int32_t`.
- Subtract the result from `op1[i]`, without loss of precision.
- Saturate the result to the range of `int32_t`.

## svqdmlslbt[_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdmlslbt%5B_s64%5D

### Signature (source notation)

```c
svint64_t svqdmlslbt[_s64](svint64_t op1, svint32_t op2, svint32_t op3);
```

### Description

Saturating doubling multiply-subtract long (bottom × top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Saturating multiply-accumulate and widen

- SME attributes: Not specified by source.

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
    "Zresult.D|Ztied1.D": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
SQDMLSLBT Ztied1.D, Zop2.S, Zop3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDMLSLBT--Signed-saturating-doubling-multiply-subtract-long-from-accumulator--bottom---top--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SQDMLSLBT Zresult.D, Zop2.S, Zop3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDMLSLBT--Signed-saturating-doubling-multiply-subtract-long-from-accumulator--bottom---top--

### Operation

Source operation ID: `SveOperation_svqdmlslbt_s64`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Multiply `op2[i * 2]` by `op3[i * 2 + 1]`, without loss of precision.
- Double the result, again without loss of precision.
- Saturate the result to the range of `int64_t`.
- Subtract the result from `op1[i]`, without loss of precision.
- Saturate the result to the range of `int64_t`.

## svqdmlslt[_n_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdmlslt%5B_n_s16%5D

### Signature (source notation)

```c
svint16_t svqdmlslt[_n_s16](svint16_t op1, svint8_t op2, int8_t op3);
```

### Description

Saturating doubling multiply-subtract long (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Saturating multiply-accumulate and widen

- SME attributes: Not specified by source.

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
    "Zresult.H|Ztied1.H": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
SQDMLSLT Ztied1.H, Zop2.B, Zop3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDMLSLT--vectors---Signed-saturating-doubling-multiply-subtract-long-from-accumulator--top--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SQDMLSLT Zresult.H, Zop2.B, Zop3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDMLSLT--vectors---Signed-saturating-doubling-multiply-subtract-long-from-accumulator--top--

### Operation

Source operation ID: `SveOperation_svqdmlslt_n_s16`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Multiply `op2[i * 2 + 1]` by `op3`, without loss of precision.
- Double the result, again without loss of precision.
- Saturate the result to the range of `int16_t`.
- Subtract the result from `op1[i]`, without loss of precision.
- Saturate the result to the range of `int16_t`.

## svqdmlslt[_n_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdmlslt%5B_n_s32%5D

### Signature (source notation)

```c
svint32_t svqdmlslt[_n_s32](svint32_t op1, svint16_t op2, int16_t op3);
```

### Description

Saturating doubling multiply-subtract long (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Saturating multiply-accumulate and widen

- SME attributes: Not specified by source.

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
    "Zresult.S|Ztied1.S": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
SQDMLSLT Ztied1.S, Zop2.H, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDMLSLT--vectors---Signed-saturating-doubling-multiply-subtract-long-from-accumulator--top--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SQDMLSLT Zresult.S, Zop2.H, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDMLSLT--vectors---Signed-saturating-doubling-multiply-subtract-long-from-accumulator--top--

### Operation

Source operation ID: `SveOperation_svqdmlslt_n_s32`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Multiply `op2[i * 2 + 1]` by `op3`, without loss of precision.
- Double the result, again without loss of precision.
- Saturate the result to the range of `int32_t`.
- Subtract the result from `op1[i]`, without loss of precision.
- Saturate the result to the range of `int32_t`.

## svqdmlslt[_n_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdmlslt%5B_n_s64%5D

### Signature (source notation)

```c
svint64_t svqdmlslt[_n_s64](svint64_t op1, svint32_t op2, int32_t op3);
```

### Description

Saturating doubling multiply-subtract long (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Saturating multiply-accumulate and widen

- SME attributes: Not specified by source.

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
    "Zresult.D|Ztied1.D": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
SQDMLSLT Ztied1.D, Zop2.S, Zop3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDMLSLT--vectors---Signed-saturating-doubling-multiply-subtract-long-from-accumulator--top--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SQDMLSLT Zresult.D, Zop2.S, Zop3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDMLSLT--vectors---Signed-saturating-doubling-multiply-subtract-long-from-accumulator--top--

### Operation

Source operation ID: `SveOperation_svqdmlslt_n_s64`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Multiply `op2[i * 2 + 1]` by `op3`, without loss of precision.
- Double the result, again without loss of precision.
- Saturate the result to the range of `int64_t`.
- Subtract the result from `op1[i]`, without loss of precision.
- Saturate the result to the range of `int64_t`.

## svqdmlslt[_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdmlslt%5B_s16%5D

### Signature (source notation)

```c
svint16_t svqdmlslt[_s16](svint16_t op1, svint8_t op2, svint8_t op3);
```

### Description

Saturating doubling multiply-subtract long (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Saturating multiply-accumulate and widen

- SME attributes: Not specified by source.

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
    "Zresult.H|Ztied1.H": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
SQDMLSLT Ztied1.H, Zop2.B, Zop3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDMLSLT--vectors---Signed-saturating-doubling-multiply-subtract-long-from-accumulator--top--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SQDMLSLT Zresult.H, Zop2.B, Zop3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDMLSLT--vectors---Signed-saturating-doubling-multiply-subtract-long-from-accumulator--top--

### Operation

Source operation ID: `SveOperation_svqdmlslt_s16`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Multiply `op2[i * 2 + 1]` by `op3[i * 2 + 1]`, without loss of precision.
- Double the result, again without loss of precision.
- Saturate the result to the range of `int16_t`.
- Subtract the result from `op1[i]`, without loss of precision.
- Saturate the result to the range of `int16_t`.

## svqdmlslt[_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdmlslt%5B_s32%5D

### Signature (source notation)

```c
svint32_t svqdmlslt[_s32](svint32_t op1, svint16_t op2, svint16_t op3);
```

### Description

Saturating doubling multiply-subtract long (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Saturating multiply-accumulate and widen

- SME attributes: Not specified by source.

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
    "Zresult.S|Ztied1.S": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
SQDMLSLT Ztied1.S, Zop2.H, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDMLSLT--vectors---Signed-saturating-doubling-multiply-subtract-long-from-accumulator--top--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SQDMLSLT Zresult.S, Zop2.H, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDMLSLT--vectors---Signed-saturating-doubling-multiply-subtract-long-from-accumulator--top--

### Operation

Source operation ID: `SveOperation_svqdmlslt_s32`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Multiply `op2[i * 2 + 1]` by `op3[i * 2 + 1]`, without loss of precision.
- Double the result, again without loss of precision.
- Saturate the result to the range of `int32_t`.
- Subtract the result from `op1[i]`, without loss of precision.
- Saturate the result to the range of `int32_t`.

## svqdmlslt[_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdmlslt%5B_s64%5D

### Signature (source notation)

```c
svint64_t svqdmlslt[_s64](svint64_t op1, svint32_t op2, svint32_t op3);
```

### Description

Saturating doubling multiply-subtract long (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Saturating multiply-accumulate and widen

- SME attributes: Not specified by source.

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
    "Zresult.D|Ztied1.D": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
SQDMLSLT Ztied1.D, Zop2.S, Zop3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDMLSLT--vectors---Signed-saturating-doubling-multiply-subtract-long-from-accumulator--top--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SQDMLSLT Zresult.D, Zop2.S, Zop3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDMLSLT--vectors---Signed-saturating-doubling-multiply-subtract-long-from-accumulator--top--

### Operation

Source operation ID: `SveOperation_svqdmlslt_s64`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Multiply `op2[i * 2 + 1]` by `op3[i * 2 + 1]`, without loss of precision.
- Double the result, again without loss of precision.
- Saturate the result to the range of `int64_t`.
- Subtract the result from `op1[i]`, without loss of precision.
- Saturate the result to the range of `int64_t`.

## svqdmlslt_lane[_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdmlslt_lane%5B_s32%5D

### Signature (source notation)

```c
svint32_t svqdmlslt_lane[_s32](svint32_t op1, svint16_t op2, svint16_t op3, uint64_t imm_index);
```

### Description

Saturating doubling multiply-subtract long (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Saturating multiply-accumulate and widen

- SME attributes: Not specified by source.

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
    "Zresult.S|Ztied1.S": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
SQDMLSLT Ztied1.S, Zop2.H, Zop3.H[imm_index]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDMLSLT--indexed---Signed-saturating-doubling-multiply-subtract-long-from-accumulator--top--indexed--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SQDMLSLT Zresult.S, Zop2.H, Zop3.H[imm_index]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDMLSLT--indexed---Signed-saturating-doubling-multiply-subtract-long-from-accumulator--top--indexed--

### Operation

Source operation ID: `SveOperation_svqdmlslt_lane_s32`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Multiply `op2[i * 2 + 1]` by `op3[base + imm_index]`, without loss of precision, where `op3[base]` is the first element in the same 128-bit quadword as `op3[i * 2]`.
- Double the result, again without loss of precision.
- Saturate the result to the range of `int32_t`.
- Subtract the result from `op1[i]`, without loss of precision.
- Saturate the result to the range of `int32_t`.

## svqdmlslt_lane[_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdmlslt_lane%5B_s64%5D

### Signature (source notation)

```c
svint64_t svqdmlslt_lane[_s64](svint64_t op1, svint32_t op2, svint32_t op3, uint64_t imm_index);
```

### Description

Saturating doubling multiply-subtract long (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Saturating multiply-accumulate and widen

- SME attributes: Not specified by source.

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
    "Zresult.D|Ztied1.D": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
SQDMLSLT Ztied1.D, Zop2.S, Zop3.S[imm_index]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDMLSLT--indexed---Signed-saturating-doubling-multiply-subtract-long-from-accumulator--top--indexed--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SQDMLSLT Zresult.D, Zop2.S, Zop3.S[imm_index]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDMLSLT--indexed---Signed-saturating-doubling-multiply-subtract-long-from-accumulator--top--indexed--

### Operation

Source operation ID: `SveOperation_svqdmlslt_lane_s64`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Multiply `op2[i * 2 + 1]` by `op3[base + imm_index]`, without loss of precision, where `op3[base]` is the first element in the same 128-bit quadword as `op3[i * 2]`.
- Double the result, again without loss of precision.
- Saturate the result to the range of `int64_t`.
- Subtract the result from `op1[i]`, without loss of precision.
- Saturate the result to the range of `int64_t`.

