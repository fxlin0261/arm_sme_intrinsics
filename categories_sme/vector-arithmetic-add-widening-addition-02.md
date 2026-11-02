# SME / Vector arithmetic / Add / Widening addition — Part 2

## svaddwt[_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svaddwt%5B_s64%5D

### Signature (source notation)

```c
svint64_t svaddwt[_s64](svint64_t op1, svint32_t op2);
```

### Description

Add wide (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Widening addition

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
SADDWT Zresult.D, Zop1.D, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SADDWT--Signed-add-wide--top--

### Operation

Source operation ID: `SveOperation_svaddwt_s64`

**Operation**



Return a vector in which each element *i* contains:



```text
op1[i] + (int64_t)op2[i * 2 + 1]
```



The operation uses modulo arithmetic.  The behavior is therefore defined for all inputs; unlike C, there is no undefined behavior for signed overflow.

## svaddwt[_u16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svaddwt%5B_u16%5D

### Signature (source notation)

```c
svuint16_t svaddwt[_u16](svuint16_t op1, svuint8_t op2);
```

### Description

Add wide (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Widening addition

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
UADDWT Zresult.H, Zop1.H, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UADDWT--Unsigned-add-wide--top--

### Operation

Source operation ID: `SveOperation_svaddwt_u16`

**Operation**



Return a vector in which each element *i* contains:



```text
op1[i] + (uint16_t)op2[i * 2 + 1]
```

## svaddwt[_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svaddwt%5B_u32%5D

### Signature (source notation)

```c
svuint32_t svaddwt[_u32](svuint32_t op1, svuint16_t op2);
```

### Description

Add wide (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Widening addition

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
UADDWT Zresult.S, Zop1.S, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UADDWT--Unsigned-add-wide--top--

### Operation

Source operation ID: `SveOperation_svaddwt_u32`

**Operation**



Return a vector in which each element *i* contains:



```text
op1[i] + (uint32_t)op2[i * 2 + 1]
```

## svaddwt[_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svaddwt%5B_u64%5D

### Signature (source notation)

```c
svuint64_t svaddwt[_u64](svuint64_t op1, svuint32_t op2);
```

### Description

Add wide (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Widening addition

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
UADDWT Zresult.D, Zop1.D, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UADDWT--Unsigned-add-wide--top--

### Operation

Source operation ID: `SveOperation_svaddwt_u64`

**Operation**



Return a vector in which each element *i* contains:



```text
op1[i] + (uint64_t)op2[i * 2 + 1]
```

