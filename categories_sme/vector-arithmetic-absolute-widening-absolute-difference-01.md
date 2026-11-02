# SME / Vector arithmetic / Absolute / Widening absolute difference — Part 1

## svabdlb[_n_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svabdlb%5B_n_s16%5D

### Signature (source notation)

```c
svint16_t svabdlb[_n_s16](svint8_t op1, int8_t op2);
```

### Description

Absolute difference long (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Absolute / Widening absolute difference

- SME attributes: Not specified by source.

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
SABDLB Zresult.H, Zop1.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SABDLB--Signed-absolute-difference-long--bottom--

### Operation

Source operation ID: `SveOperation_svabdlb_n_s16`

**Operation**



Return a vector in which each element *i* contains the absolute difference between `(int16_t)op1[i * 2]` and `(int16_t)op2`.

## svabdlb[_n_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svabdlb%5B_n_s32%5D

### Signature (source notation)

```c
svint32_t svabdlb[_n_s32](svint16_t op1, int16_t op2);
```

### Description

Absolute difference long (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Absolute / Widening absolute difference

- SME attributes: Not specified by source.

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
SABDLB Zresult.S, Zop1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SABDLB--Signed-absolute-difference-long--bottom--

### Operation

Source operation ID: `SveOperation_svabdlb_n_s32`

**Operation**



Return a vector in which each element *i* contains the absolute difference between `(int32_t)op1[i * 2]` and `(int32_t)op2`.

## svabdlb[_n_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svabdlb%5B_n_s64%5D

### Signature (source notation)

```c
svint64_t svabdlb[_n_s64](svint32_t op1, int32_t op2);
```

### Description

Absolute difference long (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Absolute / Widening absolute difference

- SME attributes: Not specified by source.

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
SABDLB Zresult.D, Zop1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SABDLB--Signed-absolute-difference-long--bottom--

### Operation

Source operation ID: `SveOperation_svabdlb_n_s64`

**Operation**



Return a vector in which each element *i* contains the absolute difference between `(int64_t)op1[i * 2]` and `(int64_t)op2`.

## svabdlb[_n_u16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svabdlb%5B_n_u16%5D

### Signature (source notation)

```c
svuint16_t svabdlb[_n_u16](svuint8_t op1, uint8_t op2);
```

### Description

Absolute difference long (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Absolute / Widening absolute difference

- SME attributes: Not specified by source.

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
UABDLB Zresult.H, Zop1.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UABDLB--Unsigned-absolute-difference-long--bottom--

### Operation

Source operation ID: `SveOperation_svabdlb_n_u16`

**Operation**



Return a vector in which each element *i* contains the absolute difference between `(uint16_t)op1[i * 2]` and `(uint16_t)op2`.

## svabdlb[_n_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svabdlb%5B_n_u32%5D

### Signature (source notation)

```c
svuint32_t svabdlb[_n_u32](svuint16_t op1, uint16_t op2);
```

### Description

Absolute difference long (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Absolute / Widening absolute difference

- SME attributes: Not specified by source.

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
UABDLB Zresult.S, Zop1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UABDLB--Unsigned-absolute-difference-long--bottom--

### Operation

Source operation ID: `SveOperation_svabdlb_n_u32`

**Operation**



Return a vector in which each element *i* contains the absolute difference between `(uint32_t)op1[i * 2]` and `(uint32_t)op2`.

## svabdlb[_n_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svabdlb%5B_n_u64%5D

### Signature (source notation)

```c
svuint64_t svabdlb[_n_u64](svuint32_t op1, uint32_t op2);
```

### Description

Absolute difference long (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Absolute / Widening absolute difference

- SME attributes: Not specified by source.

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
UABDLB Zresult.D, Zop1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UABDLB--Unsigned-absolute-difference-long--bottom--

### Operation

Source operation ID: `SveOperation_svabdlb_n_u64`

**Operation**



Return a vector in which each element *i* contains the absolute difference between `(uint64_t)op1[i * 2]` and `(uint64_t)op2`.

## svabdlb[_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svabdlb%5B_s16%5D

### Signature (source notation)

```c
svint16_t svabdlb[_s16](svint8_t op1, svint8_t op2);
```

### Description

Absolute difference long (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Absolute / Widening absolute difference

- SME attributes: Not specified by source.

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
SABDLB Zresult.H, Zop1.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SABDLB--Signed-absolute-difference-long--bottom--

### Operation

Source operation ID: `SveOperation_svabdlb_s16`

**Operation**



Return a vector in which each element *i* contains the absolute difference between `(int16_t)op1[i * 2]` and `(int16_t)op2[i * 2]`.

## svabdlb[_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svabdlb%5B_s32%5D

### Signature (source notation)

```c
svint32_t svabdlb[_s32](svint16_t op1, svint16_t op2);
```

### Description

Absolute difference long (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Absolute / Widening absolute difference

- SME attributes: Not specified by source.

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
SABDLB Zresult.S, Zop1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SABDLB--Signed-absolute-difference-long--bottom--

### Operation

Source operation ID: `SveOperation_svabdlb_s32`

**Operation**



Return a vector in which each element *i* contains the absolute difference between `(int32_t)op1[i * 2]` and `(int32_t)op2[i * 2]`.

## svabdlb[_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svabdlb%5B_s64%5D

### Signature (source notation)

```c
svint64_t svabdlb[_s64](svint32_t op1, svint32_t op2);
```

### Description

Absolute difference long (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Absolute / Widening absolute difference

- SME attributes: Not specified by source.

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
SABDLB Zresult.D, Zop1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SABDLB--Signed-absolute-difference-long--bottom--

### Operation

Source operation ID: `SveOperation_svabdlb_s64`

**Operation**



Return a vector in which each element *i* contains the absolute difference between `(int64_t)op1[i * 2]` and `(int64_t)op2[i * 2]`.

## svabdlb[_u16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svabdlb%5B_u16%5D

### Signature (source notation)

```c
svuint16_t svabdlb[_u16](svuint8_t op1, svuint8_t op2);
```

### Description

Absolute difference long (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Absolute / Widening absolute difference

- SME attributes: Not specified by source.

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
UABDLB Zresult.H, Zop1.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UABDLB--Unsigned-absolute-difference-long--bottom--

### Operation

Source operation ID: `SveOperation_svabdlb_u16`

**Operation**



Return a vector in which each element *i* contains the absolute difference between `(uint16_t)op1[i * 2]` and `(uint16_t)op2[i * 2]`.

## svabdlb[_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svabdlb%5B_u32%5D

### Signature (source notation)

```c
svuint32_t svabdlb[_u32](svuint16_t op1, svuint16_t op2);
```

### Description

Absolute difference long (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Absolute / Widening absolute difference

- SME attributes: Not specified by source.

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
UABDLB Zresult.S, Zop1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UABDLB--Unsigned-absolute-difference-long--bottom--

### Operation

Source operation ID: `SveOperation_svabdlb_u32`

**Operation**



Return a vector in which each element *i* contains the absolute difference between `(uint32_t)op1[i * 2]` and `(uint32_t)op2[i * 2]`.

## svabdlb[_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svabdlb%5B_u64%5D

### Signature (source notation)

```c
svuint64_t svabdlb[_u64](svuint32_t op1, svuint32_t op2);
```

### Description

Absolute difference long (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Absolute / Widening absolute difference

- SME attributes: Not specified by source.

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
UABDLB Zresult.D, Zop1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UABDLB--Unsigned-absolute-difference-long--bottom--

### Operation

Source operation ID: `SveOperation_svabdlb_u64`

**Operation**



Return a vector in which each element *i* contains the absolute difference between `(uint64_t)op1[i * 2]` and `(uint64_t)op2[i * 2]`.

## svabdlt[_n_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svabdlt%5B_n_s16%5D

### Signature (source notation)

```c
svint16_t svabdlt[_n_s16](svint8_t op1, int8_t op2);
```

### Description

Absolute difference long (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Absolute / Widening absolute difference

- SME attributes: Not specified by source.

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
SABDLT Zresult.H, Zop1.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SABDLT--Signed-absolute-difference-long--top--

### Operation

Source operation ID: `SveOperation_svabdlt_n_s16`

**Operation**



Return a vector in which each element *i* contains the absolute difference between `(int16_t)op1[i * 2 + 1]` and `(int16_t)op2`.

## svabdlt[_n_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svabdlt%5B_n_s32%5D

### Signature (source notation)

```c
svint32_t svabdlt[_n_s32](svint16_t op1, int16_t op2);
```

### Description

Absolute difference long (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Absolute / Widening absolute difference

- SME attributes: Not specified by source.

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
SABDLT Zresult.S, Zop1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SABDLT--Signed-absolute-difference-long--top--

### Operation

Source operation ID: `SveOperation_svabdlt_n_s32`

**Operation**



Return a vector in which each element *i* contains the absolute difference between `(int32_t)op1[i * 2 + 1]` and `(int32_t)op2`.

## svabdlt[_n_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svabdlt%5B_n_s64%5D

### Signature (source notation)

```c
svint64_t svabdlt[_n_s64](svint32_t op1, int32_t op2);
```

### Description

Absolute difference long (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Absolute / Widening absolute difference

- SME attributes: Not specified by source.

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
SABDLT Zresult.D, Zop1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SABDLT--Signed-absolute-difference-long--top--

### Operation

Source operation ID: `SveOperation_svabdlt_n_s64`

**Operation**



Return a vector in which each element *i* contains the absolute difference between `(int64_t)op1[i * 2 + 1]` and `(int64_t)op2`.

## svabdlt[_n_u16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svabdlt%5B_n_u16%5D

### Signature (source notation)

```c
svuint16_t svabdlt[_n_u16](svuint8_t op1, uint8_t op2);
```

### Description

Absolute difference long (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Absolute / Widening absolute difference

- SME attributes: Not specified by source.

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
UABDLT Zresult.H, Zop1.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UABDLT--Unsigned-absolute-difference-long--top--

### Operation

Source operation ID: `SveOperation_svabdlt_n_u16`

**Operation**



Return a vector in which each element *i* contains the absolute difference between `(uint16_t)op1[i * 2 + 1]` and `(uint16_t)op2`.

## svabdlt[_n_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svabdlt%5B_n_u32%5D

### Signature (source notation)

```c
svuint32_t svabdlt[_n_u32](svuint16_t op1, uint16_t op2);
```

### Description

Absolute difference long (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Absolute / Widening absolute difference

- SME attributes: Not specified by source.

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
UABDLT Zresult.S, Zop1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UABDLT--Unsigned-absolute-difference-long--top--

### Operation

Source operation ID: `SveOperation_svabdlt_n_u32`

**Operation**



Return a vector in which each element *i* contains the absolute difference between `(uint32_t)op1[i * 2 + 1]` and `(uint32_t)op2`.

## svabdlt[_n_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svabdlt%5B_n_u64%5D

### Signature (source notation)

```c
svuint64_t svabdlt[_n_u64](svuint32_t op1, uint32_t op2);
```

### Description

Absolute difference long (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Absolute / Widening absolute difference

- SME attributes: Not specified by source.

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
UABDLT Zresult.D, Zop1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UABDLT--Unsigned-absolute-difference-long--top--

### Operation

Source operation ID: `SveOperation_svabdlt_n_u64`

**Operation**



Return a vector in which each element *i* contains the absolute difference between `(uint64_t)op1[i * 2 + 1]` and `(uint64_t)op2`.

## svabdlt[_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svabdlt%5B_s16%5D

### Signature (source notation)

```c
svint16_t svabdlt[_s16](svint8_t op1, svint8_t op2);
```

### Description

Absolute difference long (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Absolute / Widening absolute difference

- SME attributes: Not specified by source.

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
SABDLT Zresult.H, Zop1.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SABDLT--Signed-absolute-difference-long--top--

### Operation

Source operation ID: `SveOperation_svabdlt_s16`

**Operation**



Return a vector in which each element *i* contains the absolute difference between `(int16_t)op1[i * 2 + 1]` and `(int16_t)op2[i * 2 + 1]`.

## svabdlt[_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svabdlt%5B_s32%5D

### Signature (source notation)

```c
svint32_t svabdlt[_s32](svint16_t op1, svint16_t op2);
```

### Description

Absolute difference long (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Absolute / Widening absolute difference

- SME attributes: Not specified by source.

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
SABDLT Zresult.S, Zop1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SABDLT--Signed-absolute-difference-long--top--

### Operation

Source operation ID: `SveOperation_svabdlt_s32`

**Operation**



Return a vector in which each element *i* contains the absolute difference between `(int32_t)op1[i * 2 + 1]` and `(int32_t)op2[i * 2 + 1]`.

## svabdlt[_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svabdlt%5B_s64%5D

### Signature (source notation)

```c
svint64_t svabdlt[_s64](svint32_t op1, svint32_t op2);
```

### Description

Absolute difference long (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Absolute / Widening absolute difference

- SME attributes: Not specified by source.

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
SABDLT Zresult.D, Zop1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SABDLT--Signed-absolute-difference-long--top--

### Operation

Source operation ID: `SveOperation_svabdlt_s64`

**Operation**



Return a vector in which each element *i* contains the absolute difference between `(int64_t)op1[i * 2 + 1]` and `(int64_t)op2[i * 2 + 1]`.

## svabdlt[_u16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svabdlt%5B_u16%5D

### Signature (source notation)

```c
svuint16_t svabdlt[_u16](svuint8_t op1, svuint8_t op2);
```

### Description

Absolute difference long (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Absolute / Widening absolute difference

- SME attributes: Not specified by source.

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
UABDLT Zresult.H, Zop1.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UABDLT--Unsigned-absolute-difference-long--top--

### Operation

Source operation ID: `SveOperation_svabdlt_u16`

**Operation**



Return a vector in which each element *i* contains the absolute difference between `(uint16_t)op1[i * 2 + 1]` and `(uint16_t)op2[i * 2 + 1]`.

## svabdlt[_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svabdlt%5B_u32%5D

### Signature (source notation)

```c
svuint32_t svabdlt[_u32](svuint16_t op1, svuint16_t op2);
```

### Description

Absolute difference long (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Absolute / Widening absolute difference

- SME attributes: Not specified by source.

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
UABDLT Zresult.S, Zop1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UABDLT--Unsigned-absolute-difference-long--top--

### Operation

Source operation ID: `SveOperation_svabdlt_u32`

**Operation**



Return a vector in which each element *i* contains the absolute difference between `(uint32_t)op1[i * 2 + 1]` and `(uint32_t)op2[i * 2 + 1]`.

## svabdlt[_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svabdlt%5B_u64%5D

### Signature (source notation)

```c
svuint64_t svabdlt[_u64](svuint32_t op1, svuint32_t op2);
```

### Description

Absolute difference long (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Absolute / Widening absolute difference

- SME attributes: Not specified by source.

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
UABDLT Zresult.D, Zop1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UABDLT--Unsigned-absolute-difference-long--top--

### Operation

Source operation ID: `SveOperation_svabdlt_u64`

**Operation**



Return a vector in which each element *i* contains the absolute difference between `(uint64_t)op1[i * 2 + 1]` and `(uint64_t)op2[i * 2 + 1]`.

