# SME / Vector arithmetic / Multiply / Widening multiplication — Part 1

## svmullb[_n_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmullb%5B_n_s16%5D

### Signature (source notation)

```c
svint16_t svmullb[_n_s16](svint8_t op1, int8_t op2);
```

### Description

Multiply long (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply / Widening multiplication

- SME attributes: Not specified by source.

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
SMULLB Zresult.H, Zop1.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SMULLB--vectors---Signed-multiply-long--bottom--

### Operation

Source operation ID: `SveOperation_svmullb_n_s16`

**Operation**



Return a vector in which each element *i* contains:



```text
(int16_t)op1[i * 2] * (int16_t)op2
```

## svmullb[_n_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmullb%5B_n_s32%5D

### Signature (source notation)

```c
svint32_t svmullb[_n_s32](svint16_t op1, int16_t op2);
```

### Description

Multiply long (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply / Widening multiplication

- SME attributes: Not specified by source.

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
SMULLB Zresult.S, Zop1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SMULLB--vectors---Signed-multiply-long--bottom--

### Operation

Source operation ID: `SveOperation_svmullb_n_s32`

**Operation**



Return a vector in which each element *i* contains:



```text
(int32_t)op1[i * 2] * (int32_t)op2
```

## svmullb[_n_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmullb%5B_n_s64%5D

### Signature (source notation)

```c
svint64_t svmullb[_n_s64](svint32_t op1, int32_t op2);
```

### Description

Multiply long (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply / Widening multiplication

- SME attributes: Not specified by source.

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
SMULLB Zresult.D, Zop1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SMULLB--vectors---Signed-multiply-long--bottom--

### Operation

Source operation ID: `SveOperation_svmullb_n_s64`

**Operation**



Return a vector in which each element *i* contains:



```text
(int64_t)op1[i * 2] * (int64_t)op2
```

## svmullb[_n_u16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmullb%5B_n_u16%5D

### Signature (source notation)

```c
svuint16_t svmullb[_n_u16](svuint8_t op1, uint8_t op2);
```

### Description

Multiply long (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply / Widening multiplication

- SME attributes: Not specified by source.

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
UMULLB Zresult.H, Zop1.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UMULLB--vectors---Unsigned-multiply-long--bottom--

### Operation

Source operation ID: `SveOperation_svmullb_n_u16`

**Operation**



Return a vector in which each element *i* contains:



```text
(uint16_t)op1[i * 2] * (uint16_t)op2
```

## svmullb[_n_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmullb%5B_n_u32%5D

### Signature (source notation)

```c
svuint32_t svmullb[_n_u32](svuint16_t op1, uint16_t op2);
```

### Description

Multiply long (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply / Widening multiplication

- SME attributes: Not specified by source.

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
UMULLB Zresult.S, Zop1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UMULLB--vectors---Unsigned-multiply-long--bottom--

### Operation

Source operation ID: `SveOperation_svmullb_n_u32`

**Operation**



Return a vector in which each element *i* contains:



```text
(uint32_t)op1[i * 2] * (uint32_t)op2
```

## svmullb[_n_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmullb%5B_n_u64%5D

### Signature (source notation)

```c
svuint64_t svmullb[_n_u64](svuint32_t op1, uint32_t op2);
```

### Description

Multiply long (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply / Widening multiplication

- SME attributes: Not specified by source.

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
UMULLB Zresult.D, Zop1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UMULLB--vectors---Unsigned-multiply-long--bottom--

### Operation

Source operation ID: `SveOperation_svmullb_n_u64`

**Operation**



Return a vector in which each element *i* contains:



```text
(uint64_t)op1[i * 2] * (uint64_t)op2
```

## svmullb[_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmullb%5B_s16%5D

### Signature (source notation)

```c
svint16_t svmullb[_s16](svint8_t op1, svint8_t op2);
```

### Description

Multiply long (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply / Widening multiplication

- SME attributes: Not specified by source.

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
SMULLB Zresult.H, Zop1.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SMULLB--vectors---Signed-multiply-long--bottom--

### Operation

Source operation ID: `SveOperation_svmullb_s16`

**Operation**



Return a vector in which each element *i* contains:



```text
(int16_t)op1[i * 2] * (int16_t)op2[i * 2]
```

## svmullb[_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmullb%5B_s32%5D

### Signature (source notation)

```c
svint32_t svmullb[_s32](svint16_t op1, svint16_t op2);
```

### Description

Multiply long (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply / Widening multiplication

- SME attributes: Not specified by source.

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
SMULLB Zresult.S, Zop1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SMULLB--vectors---Signed-multiply-long--bottom--

### Operation

Source operation ID: `SveOperation_svmullb_s32`

**Operation**



Return a vector in which each element *i* contains:



```text
(int32_t)op1[i * 2] * (int32_t)op2[i * 2]
```

## svmullb[_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmullb%5B_s64%5D

### Signature (source notation)

```c
svint64_t svmullb[_s64](svint32_t op1, svint32_t op2);
```

### Description

Multiply long (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply / Widening multiplication

- SME attributes: Not specified by source.

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
SMULLB Zresult.D, Zop1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SMULLB--vectors---Signed-multiply-long--bottom--

### Operation

Source operation ID: `SveOperation_svmullb_s64`

**Operation**



Return a vector in which each element *i* contains:



```text
(int64_t)op1[i * 2] * (int64_t)op2[i * 2]
```

## svmullb[_u16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmullb%5B_u16%5D

### Signature (source notation)

```c
svuint16_t svmullb[_u16](svuint8_t op1, svuint8_t op2);
```

### Description

Multiply long (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply / Widening multiplication

- SME attributes: Not specified by source.

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
UMULLB Zresult.H, Zop1.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UMULLB--vectors---Unsigned-multiply-long--bottom--

### Operation

Source operation ID: `SveOperation_svmullb_u16`

**Operation**



Return a vector in which each element *i* contains:



```text
(uint16_t)op1[i * 2] * (uint16_t)op2[i * 2]
```

## svmullb[_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmullb%5B_u32%5D

### Signature (source notation)

```c
svuint32_t svmullb[_u32](svuint16_t op1, svuint16_t op2);
```

### Description

Multiply long (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply / Widening multiplication

- SME attributes: Not specified by source.

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
UMULLB Zresult.S, Zop1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UMULLB--vectors---Unsigned-multiply-long--bottom--

### Operation

Source operation ID: `SveOperation_svmullb_u32`

**Operation**



Return a vector in which each element *i* contains:



```text
(uint32_t)op1[i * 2] * (uint32_t)op2[i * 2]
```

## svmullb[_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmullb%5B_u64%5D

### Signature (source notation)

```c
svuint64_t svmullb[_u64](svuint32_t op1, svuint32_t op2);
```

### Description

Multiply long (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply / Widening multiplication

- SME attributes: Not specified by source.

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
UMULLB Zresult.D, Zop1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UMULLB--vectors---Unsigned-multiply-long--bottom--

### Operation

Source operation ID: `SveOperation_svmullb_u64`

**Operation**



Return a vector in which each element *i* contains:



```text
(uint64_t)op1[i * 2] * (uint64_t)op2[i * 2]
```

## svmullb_lane[_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmullb_lane%5B_s32%5D

### Signature (source notation)

```c
svint32_t svmullb_lane[_s32](svint16_t op1, svint16_t op2, uint64_t imm_index);
```

### Description

Multiply long (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply / Widening multiplication

- SME attributes: Not specified by source.

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
SMULLB Zresult.S, Zop1.H, Zop2.H[imm_index]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SMULLB--indexed---Signed-multiply-long--bottom--indexed--

### Operation

Source operation ID: `SveOperation_svmullb_lane_s32`

**Operation**



Return a vector in which each element *i* contains:



```text
(int32_t)op1[i * 2] * (int32_t)op2[base + imm_index]
```



where `op2[base]` is the first element in the same 128-bit quadword as `op2[i * 2]`.

## svmullb_lane[_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmullb_lane%5B_s64%5D

### Signature (source notation)

```c
svint64_t svmullb_lane[_s64](svint32_t op1, svint32_t op2, uint64_t imm_index);
```

### Description

Multiply long (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply / Widening multiplication

- SME attributes: Not specified by source.

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
SMULLB Zresult.D, Zop1.S, Zop2.S[imm_index]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SMULLB--indexed---Signed-multiply-long--bottom--indexed--

### Operation

Source operation ID: `SveOperation_svmullb_lane_s64`

**Operation**



Return a vector in which each element *i* contains:



```text
(int64_t)op1[i * 2] * (int64_t)op2[base + imm_index]
```



where `op2[base]` is the first element in the same 128-bit quadword as `op2[i * 2]`.

## svmullb_lane[_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmullb_lane%5B_u32%5D

### Signature (source notation)

```c
svuint32_t svmullb_lane[_u32](svuint16_t op1, svuint16_t op2, uint64_t imm_index);
```

### Description

Multiply long (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply / Widening multiplication

- SME attributes: Not specified by source.

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
UMULLB Zresult.S, Zop1.H, Zop2.H[imm_index]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UMULLB--indexed---Unsigned-multiply-long--bottom--indexed--

### Operation

Source operation ID: `SveOperation_svmullb_lane_u32`

**Operation**



Return a vector in which each element *i* contains:



```text
(uint32_t)op1[i * 2] * (uint32_t)op2[base + imm_index]
```



where `op2[base]` is the first element in the same 128-bit quadword as `op2[i * 2]`.

## svmullb_lane[_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmullb_lane%5B_u64%5D

### Signature (source notation)

```c
svuint64_t svmullb_lane[_u64](svuint32_t op1, svuint32_t op2, uint64_t imm_index);
```

### Description

Multiply long (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply / Widening multiplication

- SME attributes: Not specified by source.

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
UMULLB Zresult.D, Zop1.S, Zop2.S[imm_index]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UMULLB--indexed---Unsigned-multiply-long--bottom--indexed--

### Operation

Source operation ID: `SveOperation_svmullb_lane_u64`

**Operation**



Return a vector in which each element *i* contains:



```text
(uint64_t)op1[i * 2] * (uint64_t)op2[base + imm_index]
```



where `op2[base]` is the first element in the same 128-bit quadword as `op2[i * 2]`.

## svmullt[_n_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmullt%5B_n_s16%5D

### Signature (source notation)

```c
svint16_t svmullt[_n_s16](svint8_t op1, int8_t op2);
```

### Description

Multiply long (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply / Widening multiplication

- SME attributes: Not specified by source.

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
SMULLT Zresult.H, Zop1.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SMULLT--vectors---Signed-multiply-long--top--

### Operation

Source operation ID: `SveOperation_svmullt_n_s16`

**Operation**



Return a vector in which each element *i* contains:



```text
(int16_t)op1[i * 2 + 1] * (int16_t)op2
```

## svmullt[_n_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmullt%5B_n_s32%5D

### Signature (source notation)

```c
svint32_t svmullt[_n_s32](svint16_t op1, int16_t op2);
```

### Description

Multiply long (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply / Widening multiplication

- SME attributes: Not specified by source.

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
SMULLT Zresult.S, Zop1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SMULLT--vectors---Signed-multiply-long--top--

### Operation

Source operation ID: `SveOperation_svmullt_n_s32`

**Operation**



Return a vector in which each element *i* contains:



```text
(int32_t)op1[i * 2 + 1] * (int32_t)op2
```

## svmullt[_n_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmullt%5B_n_s64%5D

### Signature (source notation)

```c
svint64_t svmullt[_n_s64](svint32_t op1, int32_t op2);
```

### Description

Multiply long (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply / Widening multiplication

- SME attributes: Not specified by source.

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
SMULLT Zresult.D, Zop1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SMULLT--vectors---Signed-multiply-long--top--

### Operation

Source operation ID: `SveOperation_svmullt_n_s64`

**Operation**



Return a vector in which each element *i* contains:



```text
(int64_t)op1[i * 2 + 1] * (int64_t)op2
```

## svmullt[_n_u16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmullt%5B_n_u16%5D

### Signature (source notation)

```c
svuint16_t svmullt[_n_u16](svuint8_t op1, uint8_t op2);
```

### Description

Multiply long (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply / Widening multiplication

- SME attributes: Not specified by source.

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
UMULLT Zresult.H, Zop1.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UMULLT--vectors---Unsigned-multiply-long--top--

### Operation

Source operation ID: `SveOperation_svmullt_n_u16`

**Operation**



Return a vector in which each element *i* contains:



```text
(uint16_t)op1[i * 2 + 1] * (uint16_t)op2
```

## svmullt[_n_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmullt%5B_n_u32%5D

### Signature (source notation)

```c
svuint32_t svmullt[_n_u32](svuint16_t op1, uint16_t op2);
```

### Description

Multiply long (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply / Widening multiplication

- SME attributes: Not specified by source.

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
UMULLT Zresult.S, Zop1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UMULLT--vectors---Unsigned-multiply-long--top--

### Operation

Source operation ID: `SveOperation_svmullt_n_u32`

**Operation**



Return a vector in which each element *i* contains:



```text
(uint32_t)op1[i * 2 + 1] * (uint32_t)op2
```

## svmullt[_n_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmullt%5B_n_u64%5D

### Signature (source notation)

```c
svuint64_t svmullt[_n_u64](svuint32_t op1, uint32_t op2);
```

### Description

Multiply long (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply / Widening multiplication

- SME attributes: Not specified by source.

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
UMULLT Zresult.D, Zop1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UMULLT--vectors---Unsigned-multiply-long--top--

### Operation

Source operation ID: `SveOperation_svmullt_n_u64`

**Operation**



Return a vector in which each element *i* contains:



```text
(uint64_t)op1[i * 2 + 1] * (uint64_t)op2
```

## svmullt[_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmullt%5B_s16%5D

### Signature (source notation)

```c
svint16_t svmullt[_s16](svint8_t op1, svint8_t op2);
```

### Description

Multiply long (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply / Widening multiplication

- SME attributes: Not specified by source.

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
SMULLT Zresult.H, Zop1.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SMULLT--vectors---Signed-multiply-long--top--

### Operation

Source operation ID: `SveOperation_svmullt_s16`

**Operation**



Return a vector in which each element *i* contains:



```text
(int16_t)op1[i * 2 + 1] * (int16_t)op2[i * 2 + 1]
```

## svmullt[_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmullt%5B_s32%5D

### Signature (source notation)

```c
svint32_t svmullt[_s32](svint16_t op1, svint16_t op2);
```

### Description

Multiply long (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply / Widening multiplication

- SME attributes: Not specified by source.

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
SMULLT Zresult.S, Zop1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SMULLT--vectors---Signed-multiply-long--top--

### Operation

Source operation ID: `SveOperation_svmullt_s32`

**Operation**



Return a vector in which each element *i* contains:



```text
(int32_t)op1[i * 2 + 1] * (int32_t)op2[i * 2 + 1]
```

## svmullt[_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmullt%5B_s64%5D

### Signature (source notation)

```c
svint64_t svmullt[_s64](svint32_t op1, svint32_t op2);
```

### Description

Multiply long (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply / Widening multiplication

- SME attributes: Not specified by source.

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
SMULLT Zresult.D, Zop1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SMULLT--vectors---Signed-multiply-long--top--

### Operation

Source operation ID: `SveOperation_svmullt_s64`

**Operation**



Return a vector in which each element *i* contains:



```text
(int64_t)op1[i * 2 + 1] * (int64_t)op2[i * 2 + 1]
```

## svmullt[_u16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmullt%5B_u16%5D

### Signature (source notation)

```c
svuint16_t svmullt[_u16](svuint8_t op1, svuint8_t op2);
```

### Description

Multiply long (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply / Widening multiplication

- SME attributes: Not specified by source.

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
UMULLT Zresult.H, Zop1.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UMULLT--vectors---Unsigned-multiply-long--top--

### Operation

Source operation ID: `SveOperation_svmullt_u16`

**Operation**



Return a vector in which each element *i* contains:



```text
(uint16_t)op1[i * 2 + 1] * (uint16_t)op2[i * 2 + 1]
```

## svmullt[_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmullt%5B_u32%5D

### Signature (source notation)

```c
svuint32_t svmullt[_u32](svuint16_t op1, svuint16_t op2);
```

### Description

Multiply long (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply / Widening multiplication

- SME attributes: Not specified by source.

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
UMULLT Zresult.S, Zop1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UMULLT--vectors---Unsigned-multiply-long--top--

### Operation

Source operation ID: `SveOperation_svmullt_u32`

**Operation**



Return a vector in which each element *i* contains:



```text
(uint32_t)op1[i * 2 + 1] * (uint32_t)op2[i * 2 + 1]
```

## svmullt[_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmullt%5B_u64%5D

### Signature (source notation)

```c
svuint64_t svmullt[_u64](svuint32_t op1, svuint32_t op2);
```

### Description

Multiply long (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply / Widening multiplication

- SME attributes: Not specified by source.

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
UMULLT Zresult.D, Zop1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UMULLT--vectors---Unsigned-multiply-long--top--

### Operation

Source operation ID: `SveOperation_svmullt_u64`

**Operation**



Return a vector in which each element *i* contains:



```text
(uint64_t)op1[i * 2 + 1] * (uint64_t)op2[i * 2 + 1]
```

## svmullt_lane[_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmullt_lane%5B_s32%5D

### Signature (source notation)

```c
svint32_t svmullt_lane[_s32](svint16_t op1, svint16_t op2, uint64_t imm_index);
```

### Description

Multiply long (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply / Widening multiplication

- SME attributes: Not specified by source.

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
SMULLT Zresult.S, Zop1.H, Zop2.H[imm_index]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SMULLT--indexed---Signed-multiply-long--top--indexed--

### Operation

Source operation ID: `SveOperation_svmullt_lane_s32`

**Operation**



Return a vector in which each element *i* contains:



```text
(int32_t)op1[i * 2 + 1] * (int32_t)op2[base + imm_index]
```



where `op2[base]` is the first element in the same 128-bit quadword as `op2[i * 2]`.

## svmullt_lane[_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmullt_lane%5B_s64%5D

### Signature (source notation)

```c
svint64_t svmullt_lane[_s64](svint32_t op1, svint32_t op2, uint64_t imm_index);
```

### Description

Multiply long (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply / Widening multiplication

- SME attributes: Not specified by source.

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
SMULLT Zresult.D, Zop1.S, Zop2.S[imm_index]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SMULLT--indexed---Signed-multiply-long--top--indexed--

### Operation

Source operation ID: `SveOperation_svmullt_lane_s64`

**Operation**



Return a vector in which each element *i* contains:



```text
(int64_t)op1[i * 2 + 1] * (int64_t)op2[base + imm_index]
```



where `op2[base]` is the first element in the same 128-bit quadword as `op2[i * 2]`.

## svmullt_lane[_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmullt_lane%5B_u32%5D

### Signature (source notation)

```c
svuint32_t svmullt_lane[_u32](svuint16_t op1, svuint16_t op2, uint64_t imm_index);
```

### Description

Multiply long (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply / Widening multiplication

- SME attributes: Not specified by source.

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
UMULLT Zresult.S, Zop1.H, Zop2.H[imm_index]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UMULLT--indexed---Unsigned-multiply-long--top--indexed--

### Operation

Source operation ID: `SveOperation_svmullt_lane_u32`

**Operation**



Return a vector in which each element *i* contains:



```text
(uint32_t)op1[i * 2 + 1] * (uint32_t)op2[base + imm_index]
```



where `op2[base]` is the first element in the same 128-bit quadword as `op2[i * 2]`.

## svmullt_lane[_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmullt_lane%5B_u64%5D

### Signature (source notation)

```c
svuint64_t svmullt_lane[_u64](svuint32_t op1, svuint32_t op2, uint64_t imm_index);
```

### Description

Multiply long (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply / Widening multiplication

- SME attributes: Not specified by source.

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
UMULLT Zresult.D, Zop1.S, Zop2.S[imm_index]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UMULLT--indexed---Unsigned-multiply-long--top--indexed--

### Operation

Source operation ID: `SveOperation_svmullt_lane_u64`

**Operation**



Return a vector in which each element *i* contains:



```text
(uint64_t)op1[i * 2 + 1] * (uint64_t)op2[base + imm_index]
```



where `op2[base]` is the first element in the same 128-bit quadword as `op2[i * 2]`.

