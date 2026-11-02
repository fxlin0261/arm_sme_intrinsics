# SME / Vector arithmetic / Multiply / Saturating multiply and widen — Part 1

## svqdmullb[_n_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdmullb%5B_n_s16%5D

### Signature (source notation)

```c
svint16_t svqdmullb[_n_s16](svint8_t op1, int8_t op2);
```

### Description

Saturating doubling multiply long (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply / Saturating multiply and widen

- SME attributes: Not specified by source.

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
    "Zresult.H": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
SQDMULLB Zresult.H, Zop1.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDMULLB--vectors---Signed-saturating-doubling-multiply-long--bottom--

### Operation

Source operation ID: `SveOperation_svqdmullb_n_s16`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Multiply `op1[i * 2]` by `op2`, without loss of precision.
- Double the result, again without loss of precision.
- Saturate the result to the range of `int16_t`.

## svqdmullb[_n_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdmullb%5B_n_s32%5D

### Signature (source notation)

```c
svint32_t svqdmullb[_n_s32](svint16_t op1, int16_t op2);
```

### Description

Saturating doubling multiply long (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply / Saturating multiply and widen

- SME attributes: Not specified by source.

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
    "Zresult.S": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
SQDMULLB Zresult.S, Zop1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDMULLB--vectors---Signed-saturating-doubling-multiply-long--bottom--

### Operation

Source operation ID: `SveOperation_svqdmullb_n_s32`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Multiply `op1[i * 2]` by `op2`, without loss of precision.
- Double the result, again without loss of precision.
- Saturate the result to the range of `int32_t`.

## svqdmullb[_n_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdmullb%5B_n_s64%5D

### Signature (source notation)

```c
svint64_t svqdmullb[_n_s64](svint32_t op1, int32_t op2);
```

### Description

Saturating doubling multiply long (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply / Saturating multiply and widen

- SME attributes: Not specified by source.

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
    "Zresult.D": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
SQDMULLB Zresult.D, Zop1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDMULLB--vectors---Signed-saturating-doubling-multiply-long--bottom--

### Operation

Source operation ID: `SveOperation_svqdmullb_n_s64`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Multiply `op1[i * 2]` by `op2`, without loss of precision.
- Double the result, again without loss of precision.
- Saturate the result to the range of `int64_t`.

## svqdmullb[_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdmullb%5B_s16%5D

### Signature (source notation)

```c
svint16_t svqdmullb[_s16](svint8_t op1, svint8_t op2);
```

### Description

Saturating doubling multiply long (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply / Saturating multiply and widen

- SME attributes: Not specified by source.

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
    "Zresult.H": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
SQDMULLB Zresult.H, Zop1.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDMULLB--vectors---Signed-saturating-doubling-multiply-long--bottom--

### Operation

Source operation ID: `SveOperation_svqdmullb_s16`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Multiply `op1[i * 2]` by `op2[i * 2]`, without loss of precision.
- Double the result, again without loss of precision.
- Saturate the result to the range of `int16_t`.

## svqdmullb[_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdmullb%5B_s32%5D

### Signature (source notation)

```c
svint32_t svqdmullb[_s32](svint16_t op1, svint16_t op2);
```

### Description

Saturating doubling multiply long (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply / Saturating multiply and widen

- SME attributes: Not specified by source.

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
    "Zresult.S": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
SQDMULLB Zresult.S, Zop1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDMULLB--vectors---Signed-saturating-doubling-multiply-long--bottom--

### Operation

Source operation ID: `SveOperation_svqdmullb_s32`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Multiply `op1[i * 2]` by `op2[i * 2]`, without loss of precision.
- Double the result, again without loss of precision.
- Saturate the result to the range of `int32_t`.

## svqdmullb[_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdmullb%5B_s64%5D

### Signature (source notation)

```c
svint64_t svqdmullb[_s64](svint32_t op1, svint32_t op2);
```

### Description

Saturating doubling multiply long (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply / Saturating multiply and widen

- SME attributes: Not specified by source.

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
    "Zresult.D": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
SQDMULLB Zresult.D, Zop1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDMULLB--vectors---Signed-saturating-doubling-multiply-long--bottom--

### Operation

Source operation ID: `SveOperation_svqdmullb_s64`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Multiply `op1[i * 2]` by `op2[i * 2]`, without loss of precision.
- Double the result, again without loss of precision.
- Saturate the result to the range of `int64_t`.

## svqdmullb_lane[_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdmullb_lane%5B_s32%5D

### Signature (source notation)

```c
svint32_t svqdmullb_lane[_s32](svint16_t op1, svint16_t op2, uint64_t imm_index);
```

### Description

Saturating doubling multiply long (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply / Saturating multiply and widen

- SME attributes: Not specified by source.

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
    "Zresult.S": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
SQDMULLB Zresult.S, Zop1.H, Zop2.H[imm_index]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDMULLB--indexed---Signed-saturating-doubling-multiply-long--bottom--indexed--

### Operation

Source operation ID: `SveOperation_svqdmullb_lane_s32`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Multiply `op1[i * 2]` by `op2[base + imm_index]`, without loss of precision, where `op2[base]` is the first element in the same 128-bit quadword as `op2[i * 2]`.
- Double the result, again without loss of precision.
- Saturate the result to the range of `int32_t`.

## svqdmullb_lane[_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdmullb_lane%5B_s64%5D

### Signature (source notation)

```c
svint64_t svqdmullb_lane[_s64](svint32_t op1, svint32_t op2, uint64_t imm_index);
```

### Description

Saturating doubling multiply long (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply / Saturating multiply and widen

- SME attributes: Not specified by source.

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
    "Zresult.D": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
SQDMULLB Zresult.D, Zop1.S, Zop2.S[imm_index]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDMULLB--indexed---Signed-saturating-doubling-multiply-long--bottom--indexed--

### Operation

Source operation ID: `SveOperation_svqdmullb_lane_s64`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Multiply `op1[i * 2]` by `op2[base + imm_index]`, without loss of precision, where `op2[base]` is the first element in the same 128-bit quadword as `op2[i * 2]`.
- Double the result, again without loss of precision.
- Saturate the result to the range of `int64_t`.

## svqdmullt[_n_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdmullt%5B_n_s16%5D

### Signature (source notation)

```c
svint16_t svqdmullt[_n_s16](svint8_t op1, int8_t op2);
```

### Description

Saturating doubling multiply long (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply / Saturating multiply and widen

- SME attributes: Not specified by source.

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
    "Zresult.H": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
SQDMULLT Zresult.H, Zop1.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDMULLT--vectors---Signed-saturating-doubling-multiply-long--top--

### Operation

Source operation ID: `SveOperation_svqdmullt_n_s16`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Multiply `op1[i * 2 + 1]` by `op2`, without loss of precision.
- Double the result, again without loss of precision.
- Saturate the result to the range of `int16_t`.

## svqdmullt[_n_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdmullt%5B_n_s32%5D

### Signature (source notation)

```c
svint32_t svqdmullt[_n_s32](svint16_t op1, int16_t op2);
```

### Description

Saturating doubling multiply long (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply / Saturating multiply and widen

- SME attributes: Not specified by source.

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
    "Zresult.S": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
SQDMULLT Zresult.S, Zop1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDMULLT--vectors---Signed-saturating-doubling-multiply-long--top--

### Operation

Source operation ID: `SveOperation_svqdmullt_n_s32`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Multiply `op1[i * 2 + 1]` by `op2`, without loss of precision.
- Double the result, again without loss of precision.
- Saturate the result to the range of `int32_t`.

## svqdmullt[_n_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdmullt%5B_n_s64%5D

### Signature (source notation)

```c
svint64_t svqdmullt[_n_s64](svint32_t op1, int32_t op2);
```

### Description

Saturating doubling multiply long (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply / Saturating multiply and widen

- SME attributes: Not specified by source.

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
    "Zresult.D": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
SQDMULLT Zresult.D, Zop1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDMULLT--vectors---Signed-saturating-doubling-multiply-long--top--

### Operation

Source operation ID: `SveOperation_svqdmullt_n_s64`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Multiply `op1[i * 2 + 1]` by `op2`, without loss of precision.
- Double the result, again without loss of precision.
- Saturate the result to the range of `int64_t`.

## svqdmullt[_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdmullt%5B_s16%5D

### Signature (source notation)

```c
svint16_t svqdmullt[_s16](svint8_t op1, svint8_t op2);
```

### Description

Saturating doubling multiply long (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply / Saturating multiply and widen

- SME attributes: Not specified by source.

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
    "Zresult.H": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
SQDMULLT Zresult.H, Zop1.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDMULLT--vectors---Signed-saturating-doubling-multiply-long--top--

### Operation

Source operation ID: `SveOperation_svqdmullt_s16`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Multiply `op1[i * 2 + 1]` by `op2[i * 2 + 1]`, without loss of precision.
- Double the result, again without loss of precision.
- Saturate the result to the range of `int16_t`.

## svqdmullt[_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdmullt%5B_s32%5D

### Signature (source notation)

```c
svint32_t svqdmullt[_s32](svint16_t op1, svint16_t op2);
```

### Description

Saturating doubling multiply long (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply / Saturating multiply and widen

- SME attributes: Not specified by source.

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
    "Zresult.S": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
SQDMULLT Zresult.S, Zop1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDMULLT--vectors---Signed-saturating-doubling-multiply-long--top--

### Operation

Source operation ID: `SveOperation_svqdmullt_s32`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Multiply `op1[i * 2 + 1]` by `op2[i * 2 + 1]`, without loss of precision.
- Double the result, again without loss of precision.
- Saturate the result to the range of `int32_t`.

## svqdmullt[_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdmullt%5B_s64%5D

### Signature (source notation)

```c
svint64_t svqdmullt[_s64](svint32_t op1, svint32_t op2);
```

### Description

Saturating doubling multiply long (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply / Saturating multiply and widen

- SME attributes: Not specified by source.

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
    "Zresult.D": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
SQDMULLT Zresult.D, Zop1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDMULLT--vectors---Signed-saturating-doubling-multiply-long--top--

### Operation

Source operation ID: `SveOperation_svqdmullt_s64`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Multiply `op1[i * 2 + 1]` by `op2[i * 2 + 1]`, without loss of precision.
- Double the result, again without loss of precision.
- Saturate the result to the range of `int64_t`.

## svqdmullt_lane[_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdmullt_lane%5B_s32%5D

### Signature (source notation)

```c
svint32_t svqdmullt_lane[_s32](svint16_t op1, svint16_t op2, uint64_t imm_index);
```

### Description

Saturating doubling multiply long (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply / Saturating multiply and widen

- SME attributes: Not specified by source.

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
    "Zresult.S": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
SQDMULLT Zresult.S, Zop1.H, Zop2.H[imm_index]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDMULLT--indexed---Signed-saturating-doubling-multiply-long--top--indexed--

### Operation

Source operation ID: `SveOperation_svqdmullt_lane_s32`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Multiply `op1[i * 2 + 1]` by `op2[base + imm_index]`, without loss of precision, where `op2[base]` is the first element in the same 128-bit quadword as `op2[i * 2]`.
- Double the result, again without loss of precision.
- Saturate the result to the range of `int32_t`.

## svqdmullt_lane[_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqdmullt_lane%5B_s64%5D

### Signature (source notation)

```c
svint64_t svqdmullt_lane[_s64](svint32_t op1, svint32_t op2, uint64_t imm_index);
```

### Description

Saturating doubling multiply long (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply / Saturating multiply and widen

- SME attributes: Not specified by source.

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
    "Zresult.D": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
SQDMULLT Zresult.D, Zop1.S, Zop2.S[imm_index]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQDMULLT--indexed---Signed-saturating-doubling-multiply-long--top--indexed--

### Operation

Source operation ID: `SveOperation_svqdmullt_lane_s64`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Multiply `op1[i * 2 + 1]` by `op2[base + imm_index]`, without loss of precision, where `op2[base]` is the first element in the same 128-bit quadword as `op2[i * 2]`.
- Double the result, again without loss of precision.
- Saturate the result to the range of `int64_t`.

