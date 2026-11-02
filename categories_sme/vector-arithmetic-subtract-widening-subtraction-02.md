# SME / Vector arithmetic / Subtract / Widening subtraction — Part 2

## svsubwt[_n_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsubwt%5B_n_s64%5D

### Signature (source notation)

```c
svint64_t svsubwt[_n_s64](svint64_t op1, int32_t op2);
```

### Description

Subtract wide (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Subtract / Widening subtraction

- SME attributes: Not specified by source.

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
SSUBWT Zresult.D, Zop1.D, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SSUBWT--Signed-subtract-wide--top--

### Operation

Source operation ID: `SveOperation_svsubwb_n_s64`

**Operation**



Return a vector in which each element *i* contains:



```text
op1[i] - (int64_t)op2
```



The operation uses modulo arithmetic.  The behavior is therefore defined for all inputs; unlike C, there is no undefined behavior for signed overflow.

## svsubwt[_n_u16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsubwt%5B_n_u16%5D

### Signature (source notation)

```c
svuint16_t svsubwt[_n_u16](svuint16_t op1, uint8_t op2);
```

### Description

Subtract wide (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Subtract / Widening subtraction

- SME attributes: Not specified by source.

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
    "register": "Zop1.H"
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
USUBWT Zresult.H, Zop1.H, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/USUBWT--Unsigned-subtract-wide--top--

### Operation

Source operation ID: `SveOperation_svsubwb_n_u16`

**Operation**



Return a vector in which each element *i* contains:



```text
op1[i] - (uint16_t)op2
```

## svsubwt[_n_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsubwt%5B_n_u32%5D

### Signature (source notation)

```c
svuint32_t svsubwt[_n_u32](svuint32_t op1, uint16_t op2);
```

### Description

Subtract wide (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Subtract / Widening subtraction

- SME attributes: Not specified by source.

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
    "register": "Zop1.S"
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
USUBWT Zresult.S, Zop1.S, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/USUBWT--Unsigned-subtract-wide--top--

### Operation

Source operation ID: `SveOperation_svsubwb_n_u32`

**Operation**



Return a vector in which each element *i* contains:



```text
op1[i] - (uint32_t)op2
```

## svsubwt[_n_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsubwt%5B_n_u64%5D

### Signature (source notation)

```c
svuint64_t svsubwt[_n_u64](svuint64_t op1, uint32_t op2);
```

### Description

Subtract wide (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Subtract / Widening subtraction

- SME attributes: Not specified by source.

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
    "register": "Zop1.D"
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
USUBWT Zresult.D, Zop1.D, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/USUBWT--Unsigned-subtract-wide--top--

### Operation

Source operation ID: `SveOperation_svsubwb_n_u64`

**Operation**



Return a vector in which each element *i* contains:



```text
op1[i] - (uint64_t)op2
```

## svsubwt[_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsubwt%5B_s16%5D

### Signature (source notation)

```c
svint16_t svsubwt[_s16](svint16_t op1, svint8_t op2);
```

### Description

Subtract wide (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Subtract / Widening subtraction

- SME attributes: Not specified by source.

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
SSUBWT Zresult.H, Zop1.H, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SSUBWT--Signed-subtract-wide--top--

### Operation

Source operation ID: `SveOperation_svsubwt_s16`

**Operation**



Return a vector in which each element *i* contains:



```text
op1[i] - (int16_t)op2[i * 2 + 1]
```



The operation uses modulo arithmetic.  The behavior is therefore defined for all inputs; unlike C, there is no undefined behavior for signed overflow.

## svsubwt[_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsubwt%5B_s32%5D

### Signature (source notation)

```c
svint32_t svsubwt[_s32](svint32_t op1, svint16_t op2);
```

### Description

Subtract wide (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Subtract / Widening subtraction

- SME attributes: Not specified by source.

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
SSUBWT Zresult.S, Zop1.S, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SSUBWT--Signed-subtract-wide--top--

### Operation

Source operation ID: `SveOperation_svsubwt_s32`

**Operation**



Return a vector in which each element *i* contains:



```text
op1[i] - (int32_t)op2[i * 2 + 1]
```



The operation uses modulo arithmetic.  The behavior is therefore defined for all inputs; unlike C, there is no undefined behavior for signed overflow.

## svsubwt[_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsubwt%5B_s64%5D

### Signature (source notation)

```c
svint64_t svsubwt[_s64](svint64_t op1, svint32_t op2);
```

### Description

Subtract wide (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Subtract / Widening subtraction

- SME attributes: Not specified by source.

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
SSUBWT Zresult.D, Zop1.D, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SSUBWT--Signed-subtract-wide--top--

### Operation

Source operation ID: `SveOperation_svsubwt_s64`

**Operation**



Return a vector in which each element *i* contains:



```text
op1[i] - (int64_t)op2[i * 2 + 1]
```



The operation uses modulo arithmetic.  The behavior is therefore defined for all inputs; unlike C, there is no undefined behavior for signed overflow.

## svsubwt[_u16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsubwt%5B_u16%5D

### Signature (source notation)

```c
svuint16_t svsubwt[_u16](svuint16_t op1, svuint8_t op2);
```

### Description

Subtract wide (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Subtract / Widening subtraction

- SME attributes: Not specified by source.

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
    "register": "Zop1.H"
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
USUBWT Zresult.H, Zop1.H, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/USUBWT--Unsigned-subtract-wide--top--

### Operation

Source operation ID: `SveOperation_svsubwt_u16`

**Operation**



Return a vector in which each element *i* contains:



```text
op1[i] - (uint16_t)op2[i * 2 + 1]
```

## svsubwt[_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsubwt%5B_u32%5D

### Signature (source notation)

```c
svuint32_t svsubwt[_u32](svuint32_t op1, svuint16_t op2);
```

### Description

Subtract wide (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Subtract / Widening subtraction

- SME attributes: Not specified by source.

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
    "register": "Zop1.S"
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
USUBWT Zresult.S, Zop1.S, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/USUBWT--Unsigned-subtract-wide--top--

### Operation

Source operation ID: `SveOperation_svsubwt_u32`

**Operation**



Return a vector in which each element *i* contains:



```text
op1[i] - (uint32_t)op2[i * 2 + 1]
```

## svsubwt[_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsubwt%5B_u64%5D

### Signature (source notation)

```c
svuint64_t svsubwt[_u64](svuint64_t op1, svuint32_t op2);
```

### Description

Subtract wide (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Subtract / Widening subtraction

- SME attributes: Not specified by source.

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
    "register": "Zop1.D"
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
USUBWT Zresult.D, Zop1.D, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/USUBWT--Unsigned-subtract-wide--top--

### Operation

Source operation ID: `SveOperation_svsubwt_u64`

**Operation**



Return a vector in which each element *i* contains:



```text
op1[i] - (uint64_t)op2[i * 2 + 1]
```

