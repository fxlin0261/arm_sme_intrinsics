# SME / Shift / Right / Vector saturating shift right and narrow — Part 1

## svqshrnb[_n_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqshrnb%5B_n_s16%5D

### Signature (source notation)

```c
svint8_t svqshrnb[_n_s16](svint16_t op1, uint64_t imm2);
```

### Description

Saturating shift right narrow (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Shift / Right / Vector saturating shift right and narrow

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
    "register": "Zop1.H"
  },
  "imm2": {
    "minimum": 1,
    "maximum": 8
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
SQSHRNB Zresult.B, Zop1.H, #imm2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQSHRNB--Signed-saturating-shift-right-narrow-by-immediate--bottom--

### Operation

Source operation ID: `SveOperation_svqshrnb_n_s16`

**Operation**



Return a vector in which each even-indexed (“bottom”) element *i* contains the result of the following procedure:




- Divide `op1[i/2]` by 2 to the power `imm2`, rounding towards -∞.
- Saturate the result to the range of `int8_t`.



Set the odd-indexed elements of the result vector to zero.

## svqshrnb[_n_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqshrnb%5B_n_s32%5D

### Signature (source notation)

```c
svint16_t svqshrnb[_n_s32](svint32_t op1, uint64_t imm2);
```

### Description

Saturating shift right narrow (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Shift / Right / Vector saturating shift right and narrow

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
    "register": "Zop1.S"
  },
  "imm2": {
    "minimum": 1,
    "maximum": 16
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
SQSHRNB Zresult.H, Zop1.S, #imm2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQSHRNB--Signed-saturating-shift-right-narrow-by-immediate--bottom--

### Operation

Source operation ID: `SveOperation_svqshrnb_n_s32`

**Operation**



Return a vector in which each even-indexed (“bottom”) element *i* contains the result of the following procedure:




- Divide `op1[i/2]` by 2 to the power `imm2`, rounding towards -∞.
- Saturate the result to the range of `int16_t`.



Set the odd-indexed elements of the result vector to zero.

## svqshrnb[_n_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqshrnb%5B_n_s64%5D

### Signature (source notation)

```c
svint32_t svqshrnb[_n_s64](svint64_t op1, uint64_t imm2);
```

### Description

Saturating shift right narrow (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Shift / Right / Vector saturating shift right and narrow

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
    "register": "Zop1.D"
  },
  "imm2": {
    "minimum": 1,
    "maximum": 32
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
SQSHRNB Zresult.S, Zop1.D, #imm2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQSHRNB--Signed-saturating-shift-right-narrow-by-immediate--bottom--

### Operation

Source operation ID: `SveOperation_svqshrnb_n_s64`

**Operation**



Return a vector in which each even-indexed (“bottom”) element *i* contains the result of the following procedure:




- Divide `op1[i/2]` by 2 to the power `imm2`, rounding towards -∞.
- Saturate the result to the range of `int32_t`.



Set the odd-indexed elements of the result vector to zero.

## svqshrnb[_n_u16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqshrnb%5B_n_u16%5D

### Signature (source notation)

```c
svuint8_t svqshrnb[_n_u16](svuint16_t op1, uint64_t imm2);
```

### Description

Saturating shift right narrow (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Shift / Right / Vector saturating shift right and narrow

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
  "op1": {
    "register": "Zop1.H"
  },
  "imm2": {
    "minimum": 1,
    "maximum": 8
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
UQSHRNB Zresult.B, Zop1.H, #imm2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQSHRNB--Unsigned-saturating-shift-right-narrow-by-immediate--bottom--

### Operation

Source operation ID: `SveOperation_svqshrnb_n_u16`

**Operation**



Return a vector in which each even-indexed (“bottom”) element *i* contains the result of the following procedure:




- Divide `op1[i/2]` by 2 to the power `imm2`, rounding towards -∞.
- Saturate the result to the range of `uint8_t`.



Set the odd-indexed elements of the result vector to zero.

## svqshrnb[_n_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqshrnb%5B_n_u32%5D

### Signature (source notation)

```c
svuint16_t svqshrnb[_n_u32](svuint32_t op1, uint64_t imm2);
```

### Description

Saturating shift right narrow (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Shift / Right / Vector saturating shift right and narrow

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
    "register": "Zop1.S"
  },
  "imm2": {
    "minimum": 1,
    "maximum": 16
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
UQSHRNB Zresult.H, Zop1.S, #imm2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQSHRNB--Unsigned-saturating-shift-right-narrow-by-immediate--bottom--

### Operation

Source operation ID: `SveOperation_svqshrnb_n_u32`

**Operation**



Return a vector in which each even-indexed (“bottom”) element *i* contains the result of the following procedure:




- Divide `op1[i/2]` by 2 to the power `imm2`, rounding towards -∞.
- Saturate the result to the range of `uint16_t`.



Set the odd-indexed elements of the result vector to zero.

## svqshrnb[_n_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqshrnb%5B_n_u64%5D

### Signature (source notation)

```c
svuint32_t svqshrnb[_n_u64](svuint64_t op1, uint64_t imm2);
```

### Description

Saturating shift right narrow (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Shift / Right / Vector saturating shift right and narrow

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
    "register": "Zop1.D"
  },
  "imm2": {
    "minimum": 1,
    "maximum": 32
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
UQSHRNB Zresult.S, Zop1.D, #imm2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQSHRNB--Unsigned-saturating-shift-right-narrow-by-immediate--bottom--

### Operation

Source operation ID: `SveOperation_svqshrnb_n_u64`

**Operation**



Return a vector in which each even-indexed (“bottom”) element *i* contains the result of the following procedure:




- Divide `op1[i/2]` by 2 to the power `imm2`, rounding towards -∞.
- Saturate the result to the range of `uint32_t`.



Set the odd-indexed elements of the result vector to zero.

## svqshrnt[_n_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqshrnt%5B_n_s16%5D

### Signature (source notation)

```c
svint8_t svqshrnt[_n_s16](svint8_t even, svint16_t op1, uint64_t imm2);
```

### Description

Saturating shift right narrow (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Shift / Right / Vector saturating shift right and narrow

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
  "even": {
    "register": "Ztied.B"
  },
  "op1": {
    "register": "Zop1.H"
  },
  "imm2": {
    "minimum": 1,
    "maximum": 8
  }
}
```

### Result mapping

```json
[
  {
    "Ztied.B": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
SQSHRNT Ztied.B, Zop1.H, #imm2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQSHRNT--Signed-saturating-shift-right-narrow-by-immediate--top--

### Operation

Source operation ID: `SveOperation_svqshrnt_n_s16`

**Operation**



Return a vector in which each odd-indexed (“top”) element *i* contains the result of the following procedure:




- Divide `op1[i/2]` by 2 to the power `imm2`, rounding towards -∞.
- Saturate the result to the range of `int8_t`.



Copy the even-indexed elements of the result vector from the corresponding elements of `even`.

## svqshrnt[_n_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqshrnt%5B_n_s32%5D

### Signature (source notation)

```c
svint16_t svqshrnt[_n_s32](svint16_t even, svint32_t op1, uint64_t imm2);
```

### Description

Saturating shift right narrow (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Shift / Right / Vector saturating shift right and narrow

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
  "even": {
    "register": "Ztied.H"
  },
  "op1": {
    "register": "Zop1.S"
  },
  "imm2": {
    "minimum": 1,
    "maximum": 16
  }
}
```

### Result mapping

```json
[
  {
    "Ztied.H": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
SQSHRNT Ztied.H, Zop1.S, #imm2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQSHRNT--Signed-saturating-shift-right-narrow-by-immediate--top--

### Operation

Source operation ID: `SveOperation_svqshrnt_n_s32`

**Operation**



Return a vector in which each odd-indexed (“top”) element *i* contains the result of the following procedure:




- Divide `op1[i/2]` by 2 to the power `imm2`, rounding towards -∞.
- Saturate the result to the range of `int16_t`.



Copy the even-indexed elements of the result vector from the corresponding elements of `even`.

## svqshrnt[_n_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqshrnt%5B_n_s64%5D

### Signature (source notation)

```c
svint32_t svqshrnt[_n_s64](svint32_t even, svint64_t op1, uint64_t imm2);
```

### Description

Saturating shift right narrow (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Shift / Right / Vector saturating shift right and narrow

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
  "even": {
    "register": "Ztied.S"
  },
  "op1": {
    "register": "Zop1.D"
  },
  "imm2": {
    "minimum": 1,
    "maximum": 32
  }
}
```

### Result mapping

```json
[
  {
    "Ztied.S": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
SQSHRNT Ztied.S, Zop1.D, #imm2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQSHRNT--Signed-saturating-shift-right-narrow-by-immediate--top--

### Operation

Source operation ID: `SveOperation_svqshrnt_n_s64`

**Operation**



Return a vector in which each odd-indexed (“top”) element *i* contains the result of the following procedure:




- Divide `op1[i/2]` by 2 to the power `imm2`, rounding towards -∞.
- Saturate the result to the range of `int32_t`.



Copy the even-indexed elements of the result vector from the corresponding elements of `even`.

## svqshrnt[_n_u16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqshrnt%5B_n_u16%5D

### Signature (source notation)

```c
svuint8_t svqshrnt[_n_u16](svuint8_t even, svuint16_t op1, uint64_t imm2);
```

### Description

Saturating shift right narrow (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Shift / Right / Vector saturating shift right and narrow

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
  "even": {
    "register": "Ztied.B"
  },
  "op1": {
    "register": "Zop1.H"
  },
  "imm2": {
    "minimum": 1,
    "maximum": 8
  }
}
```

### Result mapping

```json
[
  {
    "Ztied.B": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
UQSHRNT Ztied.B, Zop1.H, #imm2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQSHRNT--Unsigned-saturating-shift-right-narrow-by-immediate--top--

### Operation

Source operation ID: `SveOperation_svqshrnt_n_u16`

**Operation**



Return a vector in which each odd-indexed (“top”) element *i* contains the result of the following procedure:




- Divide `op1[i/2]` by 2 to the power `imm2`, rounding towards -∞.
- Saturate the result to the range of `uint8_t`.



Copy the even-indexed elements of the result vector from the corresponding elements of `even`.

## svqshrnt[_n_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqshrnt%5B_n_u32%5D

### Signature (source notation)

```c
svuint16_t svqshrnt[_n_u32](svuint16_t even, svuint32_t op1, uint64_t imm2);
```

### Description

Saturating shift right narrow (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Shift / Right / Vector saturating shift right and narrow

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
  "even": {
    "register": "Ztied.H"
  },
  "op1": {
    "register": "Zop1.S"
  },
  "imm2": {
    "minimum": 1,
    "maximum": 16
  }
}
```

### Result mapping

```json
[
  {
    "Ztied.H": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
UQSHRNT Ztied.H, Zop1.S, #imm2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQSHRNT--Unsigned-saturating-shift-right-narrow-by-immediate--top--

### Operation

Source operation ID: `SveOperation_svqshrnt_n_u32`

**Operation**



Return a vector in which each odd-indexed (“top”) element *i* contains the result of the following procedure:




- Divide `op1[i/2]` by 2 to the power `imm2`, rounding towards -∞.
- Saturate the result to the range of `uint16_t`.



Copy the even-indexed elements of the result vector from the corresponding elements of `even`.

## svqshrnt[_n_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqshrnt%5B_n_u64%5D

### Signature (source notation)

```c
svuint32_t svqshrnt[_n_u64](svuint32_t even, svuint64_t op1, uint64_t imm2);
```

### Description

Saturating shift right narrow (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Shift / Right / Vector saturating shift right and narrow

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
  "even": {
    "register": "Ztied.S"
  },
  "op1": {
    "register": "Zop1.D"
  },
  "imm2": {
    "minimum": 1,
    "maximum": 32
  }
}
```

### Result mapping

```json
[
  {
    "Ztied.S": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
UQSHRNT Ztied.S, Zop1.D, #imm2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQSHRNT--Unsigned-saturating-shift-right-narrow-by-immediate--top--

### Operation

Source operation ID: `SveOperation_svqshrnt_n_u64`

**Operation**



Return a vector in which each odd-indexed (“top”) element *i* contains the result of the following procedure:




- Divide `op1[i/2]` by 2 to the power `imm2`, rounding towards -∞.
- Saturate the result to the range of `uint32_t`.



Copy the even-indexed elements of the result vector from the corresponding elements of `even`.

## svqshrunb[_n_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqshrunb%5B_n_s16%5D

### Signature (source notation)

```c
svuint8_t svqshrunb[_n_s16](svint16_t op1, uint64_t imm2);
```

### Description

Saturating shift right unsigned narrow (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Shift / Right / Vector saturating shift right and narrow

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
  "op1": {
    "register": "Zop1.H"
  },
  "imm2": {
    "minimum": 1,
    "maximum": 8
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
SQSHRUNB Zresult.B, Zop1.H, #imm2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQSHRUNB--Signed-saturating-shift-right-unsigned-narrow-by-immediate--bottom--

### Operation

Source operation ID: `SveOperation_svqshrnb_n_u16`

**Operation**



Return a vector in which each even-indexed (“bottom”) element *i* contains the result of the following procedure:




- Divide `op1[i/2]` by 2 to the power `imm2`, rounding towards -∞.
- Saturate the result to the range of `uint8_t`.



Set the odd-indexed elements of the result vector to zero.

## svqshrunb[_n_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqshrunb%5B_n_s32%5D

### Signature (source notation)

```c
svuint16_t svqshrunb[_n_s32](svint32_t op1, uint64_t imm2);
```

### Description

Saturating shift right unsigned narrow (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Shift / Right / Vector saturating shift right and narrow

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
    "register": "Zop1.S"
  },
  "imm2": {
    "minimum": 1,
    "maximum": 16
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
SQSHRUNB Zresult.H, Zop1.S, #imm2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQSHRUNB--Signed-saturating-shift-right-unsigned-narrow-by-immediate--bottom--

### Operation

Source operation ID: `SveOperation_svqshrnb_n_u32`

**Operation**



Return a vector in which each even-indexed (“bottom”) element *i* contains the result of the following procedure:




- Divide `op1[i/2]` by 2 to the power `imm2`, rounding towards -∞.
- Saturate the result to the range of `uint16_t`.



Set the odd-indexed elements of the result vector to zero.

## svqshrunb[_n_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqshrunb%5B_n_s64%5D

### Signature (source notation)

```c
svuint32_t svqshrunb[_n_s64](svint64_t op1, uint64_t imm2);
```

### Description

Saturating shift right unsigned narrow (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Shift / Right / Vector saturating shift right and narrow

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
    "register": "Zop1.D"
  },
  "imm2": {
    "minimum": 1,
    "maximum": 32
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
SQSHRUNB Zresult.S, Zop1.D, #imm2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQSHRUNB--Signed-saturating-shift-right-unsigned-narrow-by-immediate--bottom--

### Operation

Source operation ID: `SveOperation_svqshrnb_n_u64`

**Operation**



Return a vector in which each even-indexed (“bottom”) element *i* contains the result of the following procedure:




- Divide `op1[i/2]` by 2 to the power `imm2`, rounding towards -∞.
- Saturate the result to the range of `uint32_t`.



Set the odd-indexed elements of the result vector to zero.

## svqshrunt[_n_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqshrunt%5B_n_s16%5D

### Signature (source notation)

```c
svuint8_t svqshrunt[_n_s16](svuint8_t even, svint16_t op1, uint64_t imm2);
```

### Description

Saturating shift right unsigned narrow (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Shift / Right / Vector saturating shift right and narrow

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
  "even": {
    "register": "Ztied.B"
  },
  "op1": {
    "register": "Zop1.H"
  },
  "imm2": {
    "minimum": 1,
    "maximum": 8
  }
}
```

### Result mapping

```json
[
  {
    "Ztied.B": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
SQSHRUNT Ztied.B, Zop1.H, #imm2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQSHRUNT--Signed-saturating-shift-right-unsigned-narrow-by-immediate--top--

### Operation

Source operation ID: `SveOperation_svqshrnt_n_u16`

**Operation**



Return a vector in which each odd-indexed (“top”) element *i* contains the result of the following procedure:




- Divide `op1[i/2]` by 2 to the power `imm2`, rounding towards -∞.
- Saturate the result to the range of `uint8_t`.



Copy the even-indexed elements of the result vector from the corresponding elements of `even`.

## svqshrunt[_n_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqshrunt%5B_n_s32%5D

### Signature (source notation)

```c
svuint16_t svqshrunt[_n_s32](svuint16_t even, svint32_t op1, uint64_t imm2);
```

### Description

Saturating shift right unsigned narrow (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Shift / Right / Vector saturating shift right and narrow

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
  "even": {
    "register": "Ztied.H"
  },
  "op1": {
    "register": "Zop1.S"
  },
  "imm2": {
    "minimum": 1,
    "maximum": 16
  }
}
```

### Result mapping

```json
[
  {
    "Ztied.H": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
SQSHRUNT Ztied.H, Zop1.S, #imm2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQSHRUNT--Signed-saturating-shift-right-unsigned-narrow-by-immediate--top--

### Operation

Source operation ID: `SveOperation_svqshrnt_n_u32`

**Operation**



Return a vector in which each odd-indexed (“top”) element *i* contains the result of the following procedure:




- Divide `op1[i/2]` by 2 to the power `imm2`, rounding towards -∞.
- Saturate the result to the range of `uint16_t`.



Copy the even-indexed elements of the result vector from the corresponding elements of `even`.

## svqshrunt[_n_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqshrunt%5B_n_s64%5D

### Signature (source notation)

```c
svuint32_t svqshrunt[_n_s64](svuint32_t even, svint64_t op1, uint64_t imm2);
```

### Description

Saturating shift right unsigned narrow (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Shift / Right / Vector saturating shift right and narrow

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
  "even": {
    "register": "Ztied.S"
  },
  "op1": {
    "register": "Zop1.D"
  },
  "imm2": {
    "minimum": 1,
    "maximum": 32
  }
}
```

### Result mapping

```json
[
  {
    "Ztied.S": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
SQSHRUNT Ztied.S, Zop1.D, #imm2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQSHRUNT--Signed-saturating-shift-right-unsigned-narrow-by-immediate--top--

### Operation

Source operation ID: `SveOperation_svqshrnt_n_u64`

**Operation**



Return a vector in which each odd-indexed (“top”) element *i* contains the result of the following procedure:




- Divide `op1[i/2]` by 2 to the power `imm2`, rounding towards -∞.
- Saturate the result to the range of `uint32_t`.



Copy the even-indexed elements of the result vector from the corresponding elements of `even`.

