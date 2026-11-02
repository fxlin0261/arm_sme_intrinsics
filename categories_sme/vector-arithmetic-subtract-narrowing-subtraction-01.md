# SME / Vector arithmetic / Subtract / Narrowing subtraction — Part 1

## svrsubhnb[_n_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrsubhnb%5B_n_s16%5D

### Signature (source notation)

```c
svint8_t svrsubhnb[_n_s16](svint16_t op1, int16_t op2);
```

### Description

Rounding subtract narrow high part (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Subtract / Narrowing subtraction

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
  "op2": {
    "register": "Zop2.H[*]"
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
RSUBHNB Zresult.B, Zop1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/RSUBHNB--Rounding-subtract-narrow-high-part--bottom--

### Operation

Source operation ID: `SveOperation_svrsubhnb_n_s16`

**Operation**



Return a vector in which each even-indexed (“bottom”) element *i* contains the result of the following procedure:




- Subtract `op2` from `op1[i/2]`, without loss of precision.
- Divide the result by 2 to the power 8, rounding to nearest with ties towards +∞.
- Truncate the result to the range of `int8_t`.



Set the odd-indexed elements of the result vector to zero.

## svrsubhnb[_n_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrsubhnb%5B_n_s32%5D

### Signature (source notation)

```c
svint16_t svrsubhnb[_n_s32](svint32_t op1, int32_t op2);
```

### Description

Rounding subtract narrow high part (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Subtract / Narrowing subtraction

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
  "op2": {
    "register": "Zop2.S[*]"
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
RSUBHNB Zresult.H, Zop1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/RSUBHNB--Rounding-subtract-narrow-high-part--bottom--

### Operation

Source operation ID: `SveOperation_svrsubhnb_n_s32`

**Operation**



Return a vector in which each even-indexed (“bottom”) element *i* contains the result of the following procedure:




- Subtract `op2` from `op1[i/2]`, without loss of precision.
- Divide the result by 2 to the power 16, rounding to nearest with ties towards +∞.
- Truncate the result to the range of `int16_t`.



Set the odd-indexed elements of the result vector to zero.

## svrsubhnb[_n_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrsubhnb%5B_n_s64%5D

### Signature (source notation)

```c
svint32_t svrsubhnb[_n_s64](svint64_t op1, int64_t op2);
```

### Description

Rounding subtract narrow high part (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Subtract / Narrowing subtraction

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
  "op2": {
    "register": "Zop2.D[*]"
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
RSUBHNB Zresult.S, Zop1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/RSUBHNB--Rounding-subtract-narrow-high-part--bottom--

### Operation

Source operation ID: `SveOperation_svrsubhnb_n_s64`

**Operation**



Return a vector in which each even-indexed (“bottom”) element *i* contains the result of the following procedure:




- Subtract `op2` from `op1[i/2]`, without loss of precision.
- Divide the result by 2 to the power 32, rounding to nearest with ties towards +∞.
- Truncate the result to the range of `int32_t`.



Set the odd-indexed elements of the result vector to zero.

## svrsubhnb[_n_u16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrsubhnb%5B_n_u16%5D

### Signature (source notation)

```c
svuint8_t svrsubhnb[_n_u16](svuint16_t op1, uint16_t op2);
```

### Description

Rounding subtract narrow high part (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Subtract / Narrowing subtraction

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
  "op2": {
    "register": "Zop2.H[*]"
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
RSUBHNB Zresult.B, Zop1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/RSUBHNB--Rounding-subtract-narrow-high-part--bottom--

### Operation

Source operation ID: `SveOperation_svrsubhnb_n_u16`

**Operation**



Return a vector in which each even-indexed (“bottom”) element *i* contains the result of the following procedure:




- Subtract `op2` from `op1[i/2]`, without loss of precision.
- Divide the result by 2 to the power 8, rounding to nearest with ties towards +∞.
- Truncate the result to the range of `uint8_t`.



Set the odd-indexed elements of the result vector to zero.

## svrsubhnb[_n_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrsubhnb%5B_n_u32%5D

### Signature (source notation)

```c
svuint16_t svrsubhnb[_n_u32](svuint32_t op1, uint32_t op2);
```

### Description

Rounding subtract narrow high part (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Subtract / Narrowing subtraction

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
  "op2": {
    "register": "Zop2.S[*]"
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
RSUBHNB Zresult.H, Zop1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/RSUBHNB--Rounding-subtract-narrow-high-part--bottom--

### Operation

Source operation ID: `SveOperation_svrsubhnb_n_u32`

**Operation**



Return a vector in which each even-indexed (“bottom”) element *i* contains the result of the following procedure:




- Subtract `op2` from `op1[i/2]`, without loss of precision.
- Divide the result by 2 to the power 16, rounding to nearest with ties towards +∞.
- Truncate the result to the range of `uint16_t`.



Set the odd-indexed elements of the result vector to zero.

## svrsubhnb[_n_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrsubhnb%5B_n_u64%5D

### Signature (source notation)

```c
svuint32_t svrsubhnb[_n_u64](svuint64_t op1, uint64_t op2);
```

### Description

Rounding subtract narrow high part (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Subtract / Narrowing subtraction

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
  "op2": {
    "register": "Zop2.D[*]"
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
RSUBHNB Zresult.S, Zop1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/RSUBHNB--Rounding-subtract-narrow-high-part--bottom--

### Operation

Source operation ID: `SveOperation_svrsubhnb_n_u64`

**Operation**



Return a vector in which each even-indexed (“bottom”) element *i* contains the result of the following procedure:




- Subtract `op2` from `op1[i/2]`, without loss of precision.
- Divide the result by 2 to the power 32, rounding to nearest with ties towards +∞.
- Truncate the result to the range of `uint32_t`.



Set the odd-indexed elements of the result vector to zero.

## svrsubhnb[_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrsubhnb%5B_s16%5D

### Signature (source notation)

```c
svint8_t svrsubhnb[_s16](svint16_t op1, svint16_t op2);
```

### Description

Rounding subtract narrow high part (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Subtract / Narrowing subtraction

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
  "op2": {
    "register": "Zop2.H"
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
RSUBHNB Zresult.B, Zop1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/RSUBHNB--Rounding-subtract-narrow-high-part--bottom--

### Operation

Source operation ID: `SveOperation_svrsubhnb_s16`

**Operation**



Return a vector in which each even-indexed (“bottom”) element *i* contains the result of the following procedure:




- Subtract `op2[i/2]` from `op1[i/2]`, without loss of precision.
- Divide the result by 2 to the power 8, rounding to nearest with ties towards +∞.
- Truncate the result to the range of `int8_t`.



Set the odd-indexed elements of the result vector to zero.

## svrsubhnb[_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrsubhnb%5B_s32%5D

### Signature (source notation)

```c
svint16_t svrsubhnb[_s32](svint32_t op1, svint32_t op2);
```

### Description

Rounding subtract narrow high part (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Subtract / Narrowing subtraction

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
  "op2": {
    "register": "Zop2.S"
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
RSUBHNB Zresult.H, Zop1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/RSUBHNB--Rounding-subtract-narrow-high-part--bottom--

### Operation

Source operation ID: `SveOperation_svrsubhnb_s32`

**Operation**



Return a vector in which each even-indexed (“bottom”) element *i* contains the result of the following procedure:




- Subtract `op2[i/2]` from `op1[i/2]`, without loss of precision.
- Divide the result by 2 to the power 16, rounding to nearest with ties towards +∞.
- Truncate the result to the range of `int16_t`.



Set the odd-indexed elements of the result vector to zero.

## svrsubhnb[_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrsubhnb%5B_s64%5D

### Signature (source notation)

```c
svint32_t svrsubhnb[_s64](svint64_t op1, svint64_t op2);
```

### Description

Rounding subtract narrow high part (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Subtract / Narrowing subtraction

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
  "op2": {
    "register": "Zop2.D"
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
RSUBHNB Zresult.S, Zop1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/RSUBHNB--Rounding-subtract-narrow-high-part--bottom--

### Operation

Source operation ID: `SveOperation_svrsubhnb_s64`

**Operation**



Return a vector in which each even-indexed (“bottom”) element *i* contains the result of the following procedure:




- Subtract `op2[i/2]` from `op1[i/2]`, without loss of precision.
- Divide the result by 2 to the power 32, rounding to nearest with ties towards +∞.
- Truncate the result to the range of `int32_t`.



Set the odd-indexed elements of the result vector to zero.

## svrsubhnb[_u16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrsubhnb%5B_u16%5D

### Signature (source notation)

```c
svuint8_t svrsubhnb[_u16](svuint16_t op1, svuint16_t op2);
```

### Description

Rounding subtract narrow high part (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Subtract / Narrowing subtraction

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
  "op2": {
    "register": "Zop2.H"
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
RSUBHNB Zresult.B, Zop1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/RSUBHNB--Rounding-subtract-narrow-high-part--bottom--

### Operation

Source operation ID: `SveOperation_svrsubhnb_u16`

**Operation**



Return a vector in which each even-indexed (“bottom”) element *i* contains the result of the following procedure:




- Subtract `op2[i/2]` from `op1[i/2]`, without loss of precision.
- Divide the result by 2 to the power 8, rounding to nearest with ties towards +∞.
- Truncate the result to the range of `uint8_t`.



Set the odd-indexed elements of the result vector to zero.

## svrsubhnb[_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrsubhnb%5B_u32%5D

### Signature (source notation)

```c
svuint16_t svrsubhnb[_u32](svuint32_t op1, svuint32_t op2);
```

### Description

Rounding subtract narrow high part (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Subtract / Narrowing subtraction

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
  "op2": {
    "register": "Zop2.S"
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
RSUBHNB Zresult.H, Zop1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/RSUBHNB--Rounding-subtract-narrow-high-part--bottom--

### Operation

Source operation ID: `SveOperation_svrsubhnb_u32`

**Operation**



Return a vector in which each even-indexed (“bottom”) element *i* contains the result of the following procedure:




- Subtract `op2[i/2]` from `op1[i/2]`, without loss of precision.
- Divide the result by 2 to the power 16, rounding to nearest with ties towards +∞.
- Truncate the result to the range of `uint16_t`.



Set the odd-indexed elements of the result vector to zero.

## svrsubhnb[_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrsubhnb%5B_u64%5D

### Signature (source notation)

```c
svuint32_t svrsubhnb[_u64](svuint64_t op1, svuint64_t op2);
```

### Description

Rounding subtract narrow high part (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Subtract / Narrowing subtraction

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
  "op2": {
    "register": "Zop2.D"
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
RSUBHNB Zresult.S, Zop1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/RSUBHNB--Rounding-subtract-narrow-high-part--bottom--

### Operation

Source operation ID: `SveOperation_svrsubhnb_u64`

**Operation**



Return a vector in which each even-indexed (“bottom”) element *i* contains the result of the following procedure:




- Subtract `op2[i/2]` from `op1[i/2]`, without loss of precision.
- Divide the result by 2 to the power 32, rounding to nearest with ties towards +∞.
- Truncate the result to the range of `uint32_t`.



Set the odd-indexed elements of the result vector to zero.

## svrsubhnt[_n_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrsubhnt%5B_n_s16%5D

### Signature (source notation)

```c
svint8_t svrsubhnt[_n_s16](svint8_t even, svint16_t op1, int16_t op2);
```

### Description

Rounding subtract narrow high part (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Subtract / Narrowing subtraction

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
  "op2": {
    "register": "Zop2.H[*]"
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
RSUBHNT Ztied.B, Zop1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/RSUBHNT--Rounding-subtract-narrow-high-part--top--

### Operation

Source operation ID: `SveOperation_svrsubhnt_n_s16`

**Operation**



Return a vector in which each odd-indexed (“top”) element *i* contains the result of the following procedure:




- Subtract `op2` from `op1[i/2]`, without loss of precision.
- Divide the result by 2 to the power 8, rounding to nearest with ties towards +∞.
- Truncate the result to the range of `int8_t`.



Copy the even-indexed elements of the result vector from the corresponding elements of `even`.

## svrsubhnt[_n_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrsubhnt%5B_n_s32%5D

### Signature (source notation)

```c
svint16_t svrsubhnt[_n_s32](svint16_t even, svint32_t op1, int32_t op2);
```

### Description

Rounding subtract narrow high part (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Subtract / Narrowing subtraction

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
  "op2": {
    "register": "Zop2.S[*]"
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
RSUBHNT Ztied.H, Zop1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/RSUBHNT--Rounding-subtract-narrow-high-part--top--

### Operation

Source operation ID: `SveOperation_svrsubhnt_n_s32`

**Operation**



Return a vector in which each odd-indexed (“top”) element *i* contains the result of the following procedure:




- Subtract `op2` from `op1[i/2]`, without loss of precision.
- Divide the result by 2 to the power 16, rounding to nearest with ties towards +∞.
- Truncate the result to the range of `int16_t`.



Copy the even-indexed elements of the result vector from the corresponding elements of `even`.

## svrsubhnt[_n_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrsubhnt%5B_n_s64%5D

### Signature (source notation)

```c
svint32_t svrsubhnt[_n_s64](svint32_t even, svint64_t op1, int64_t op2);
```

### Description

Rounding subtract narrow high part (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Subtract / Narrowing subtraction

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
  "op2": {
    "register": "Zop2.D[*]"
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
RSUBHNT Ztied.S, Zop1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/RSUBHNT--Rounding-subtract-narrow-high-part--top--

### Operation

Source operation ID: `SveOperation_svrsubhnt_n_s64`

**Operation**



Return a vector in which each odd-indexed (“top”) element *i* contains the result of the following procedure:




- Subtract `op2` from `op1[i/2]`, without loss of precision.
- Divide the result by 2 to the power 32, rounding to nearest with ties towards +∞.
- Truncate the result to the range of `int32_t`.



Copy the even-indexed elements of the result vector from the corresponding elements of `even`.

## svrsubhnt[_n_u16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrsubhnt%5B_n_u16%5D

### Signature (source notation)

```c
svuint8_t svrsubhnt[_n_u16](svuint8_t even, svuint16_t op1, uint16_t op2);
```

### Description

Rounding subtract narrow high part (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Subtract / Narrowing subtraction

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
  "op2": {
    "register": "Zop2.H[*]"
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
RSUBHNT Ztied.B, Zop1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/RSUBHNT--Rounding-subtract-narrow-high-part--top--

### Operation

Source operation ID: `SveOperation_svrsubhnt_n_u16`

**Operation**



Return a vector in which each odd-indexed (“top”) element *i* contains the result of the following procedure:




- Subtract `op2` from `op1[i/2]`, without loss of precision.
- Divide the result by 2 to the power 8, rounding to nearest with ties towards +∞.
- Truncate the result to the range of `uint8_t`.



Copy the even-indexed elements of the result vector from the corresponding elements of `even`.

## svrsubhnt[_n_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrsubhnt%5B_n_u32%5D

### Signature (source notation)

```c
svuint16_t svrsubhnt[_n_u32](svuint16_t even, svuint32_t op1, uint32_t op2);
```

### Description

Rounding subtract narrow high part (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Subtract / Narrowing subtraction

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
  "op2": {
    "register": "Zop2.S[*]"
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
RSUBHNT Ztied.H, Zop1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/RSUBHNT--Rounding-subtract-narrow-high-part--top--

### Operation

Source operation ID: `SveOperation_svrsubhnt_n_u32`

**Operation**



Return a vector in which each odd-indexed (“top”) element *i* contains the result of the following procedure:




- Subtract `op2` from `op1[i/2]`, without loss of precision.
- Divide the result by 2 to the power 16, rounding to nearest with ties towards +∞.
- Truncate the result to the range of `uint16_t`.



Copy the even-indexed elements of the result vector from the corresponding elements of `even`.

## svrsubhnt[_n_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrsubhnt%5B_n_u64%5D

### Signature (source notation)

```c
svuint32_t svrsubhnt[_n_u64](svuint32_t even, svuint64_t op1, uint64_t op2);
```

### Description

Rounding subtract narrow high part (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Subtract / Narrowing subtraction

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
  "op2": {
    "register": "Zop2.D[*]"
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
RSUBHNT Ztied.S, Zop1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/RSUBHNT--Rounding-subtract-narrow-high-part--top--

### Operation

Source operation ID: `SveOperation_svrsubhnt_n_u64`

**Operation**



Return a vector in which each odd-indexed (“top”) element *i* contains the result of the following procedure:




- Subtract `op2` from `op1[i/2]`, without loss of precision.
- Divide the result by 2 to the power 32, rounding to nearest with ties towards +∞.
- Truncate the result to the range of `uint32_t`.



Copy the even-indexed elements of the result vector from the corresponding elements of `even`.

## svrsubhnt[_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrsubhnt%5B_s16%5D

### Signature (source notation)

```c
svint8_t svrsubhnt[_s16](svint8_t even, svint16_t op1, svint16_t op2);
```

### Description

Rounding subtract narrow high part (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Subtract / Narrowing subtraction

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
  "op2": {
    "register": "Zop2.H"
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
RSUBHNT Ztied.B, Zop1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/RSUBHNT--Rounding-subtract-narrow-high-part--top--

### Operation

Source operation ID: `SveOperation_svrsubhnt_s16`

**Operation**



Return a vector in which each odd-indexed (“top”) element *i* contains the result of the following procedure:




- Subtract `op2[i/2]` from `op1[i/2]`, without loss of precision.
- Divide the result by 2 to the power 8, rounding to nearest with ties towards +∞.
- Truncate the result to the range of `int8_t`.



Copy the even-indexed elements of the result vector from the corresponding elements of `even`.

## svrsubhnt[_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrsubhnt%5B_s32%5D

### Signature (source notation)

```c
svint16_t svrsubhnt[_s32](svint16_t even, svint32_t op1, svint32_t op2);
```

### Description

Rounding subtract narrow high part (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Subtract / Narrowing subtraction

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
  "op2": {
    "register": "Zop2.S"
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
RSUBHNT Ztied.H, Zop1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/RSUBHNT--Rounding-subtract-narrow-high-part--top--

### Operation

Source operation ID: `SveOperation_svrsubhnt_s32`

**Operation**



Return a vector in which each odd-indexed (“top”) element *i* contains the result of the following procedure:




- Subtract `op2[i/2]` from `op1[i/2]`, without loss of precision.
- Divide the result by 2 to the power 16, rounding to nearest with ties towards +∞.
- Truncate the result to the range of `int16_t`.



Copy the even-indexed elements of the result vector from the corresponding elements of `even`.

## svrsubhnt[_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrsubhnt%5B_s64%5D

### Signature (source notation)

```c
svint32_t svrsubhnt[_s64](svint32_t even, svint64_t op1, svint64_t op2);
```

### Description

Rounding subtract narrow high part (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Subtract / Narrowing subtraction

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
  "op2": {
    "register": "Zop2.D"
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
RSUBHNT Ztied.S, Zop1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/RSUBHNT--Rounding-subtract-narrow-high-part--top--

### Operation

Source operation ID: `SveOperation_svrsubhnt_s64`

**Operation**



Return a vector in which each odd-indexed (“top”) element *i* contains the result of the following procedure:




- Subtract `op2[i/2]` from `op1[i/2]`, without loss of precision.
- Divide the result by 2 to the power 32, rounding to nearest with ties towards +∞.
- Truncate the result to the range of `int32_t`.



Copy the even-indexed elements of the result vector from the corresponding elements of `even`.

## svrsubhnt[_u16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrsubhnt%5B_u16%5D

### Signature (source notation)

```c
svuint8_t svrsubhnt[_u16](svuint8_t even, svuint16_t op1, svuint16_t op2);
```

### Description

Rounding subtract narrow high part (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Subtract / Narrowing subtraction

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
  "op2": {
    "register": "Zop2.H"
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
RSUBHNT Ztied.B, Zop1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/RSUBHNT--Rounding-subtract-narrow-high-part--top--

### Operation

Source operation ID: `SveOperation_svrsubhnt_u16`

**Operation**



Return a vector in which each odd-indexed (“top”) element *i* contains the result of the following procedure:




- Subtract `op2[i/2]` from `op1[i/2]`, without loss of precision.
- Divide the result by 2 to the power 8, rounding to nearest with ties towards +∞.
- Truncate the result to the range of `uint8_t`.



Copy the even-indexed elements of the result vector from the corresponding elements of `even`.

## svrsubhnt[_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrsubhnt%5B_u32%5D

### Signature (source notation)

```c
svuint16_t svrsubhnt[_u32](svuint16_t even, svuint32_t op1, svuint32_t op2);
```

### Description

Rounding subtract narrow high part (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Subtract / Narrowing subtraction

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
  "op2": {
    "register": "Zop2.S"
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
RSUBHNT Ztied.H, Zop1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/RSUBHNT--Rounding-subtract-narrow-high-part--top--

### Operation

Source operation ID: `SveOperation_svrsubhnt_u32`

**Operation**



Return a vector in which each odd-indexed (“top”) element *i* contains the result of the following procedure:




- Subtract `op2[i/2]` from `op1[i/2]`, without loss of precision.
- Divide the result by 2 to the power 16, rounding to nearest with ties towards +∞.
- Truncate the result to the range of `uint16_t`.



Copy the even-indexed elements of the result vector from the corresponding elements of `even`.

## svrsubhnt[_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrsubhnt%5B_u64%5D

### Signature (source notation)

```c
svuint32_t svrsubhnt[_u64](svuint32_t even, svuint64_t op1, svuint64_t op2);
```

### Description

Rounding subtract narrow high part (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Subtract / Narrowing subtraction

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
  "op2": {
    "register": "Zop2.D"
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
RSUBHNT Ztied.S, Zop1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/RSUBHNT--Rounding-subtract-narrow-high-part--top--

### Operation

Source operation ID: `SveOperation_svrsubhnt_u64`

**Operation**



Return a vector in which each odd-indexed (“top”) element *i* contains the result of the following procedure:




- Subtract `op2[i/2]` from `op1[i/2]`, without loss of precision.
- Divide the result by 2 to the power 32, rounding to nearest with ties towards +∞.
- Truncate the result to the range of `uint32_t`.



Copy the even-indexed elements of the result vector from the corresponding elements of `even`.

## svsubhnb[_n_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsubhnb%5B_n_s16%5D

### Signature (source notation)

```c
svint8_t svsubhnb[_n_s16](svint16_t op1, int16_t op2);
```

### Description

Subtract narrow high part (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Subtract / Narrowing subtraction

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
  "op2": {
    "register": "Zop2.H[*]"
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
SUBHNB Zresult.B, Zop1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SUBHNB--Subtract-narrow-high-part--bottom--

### Operation

Source operation ID: `SveOperation_svsubhnb_n_s16`

**Operation**



Return a vector in which, for each even element index *i*:




- element *i* contains the high half of `op1[i/2] - op2`
- element *i* + 1 contains zero



The operation uses modulo arithmetic.  The behavior is therefore defined for all inputs; unlike C, there is no undefined behavior for signed overflow.

## svsubhnb[_n_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsubhnb%5B_n_s32%5D

### Signature (source notation)

```c
svint16_t svsubhnb[_n_s32](svint32_t op1, int32_t op2);
```

### Description

Subtract narrow high part (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Subtract / Narrowing subtraction

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
  "op2": {
    "register": "Zop2.S[*]"
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
SUBHNB Zresult.H, Zop1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SUBHNB--Subtract-narrow-high-part--bottom--

### Operation

Source operation ID: `SveOperation_svsubhnb_n_s16`

**Operation**



Return a vector in which, for each even element index *i*:




- element *i* contains the high half of `op1[i/2] - op2`
- element *i* + 1 contains zero



The operation uses modulo arithmetic.  The behavior is therefore defined for all inputs; unlike C, there is no undefined behavior for signed overflow.

## svsubhnb[_n_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsubhnb%5B_n_s64%5D

### Signature (source notation)

```c
svint32_t svsubhnb[_n_s64](svint64_t op1, int64_t op2);
```

### Description

Subtract narrow high part (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Subtract / Narrowing subtraction

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
  "op2": {
    "register": "Zop2.D[*]"
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
SUBHNB Zresult.S, Zop1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SUBHNB--Subtract-narrow-high-part--bottom--

### Operation

Source operation ID: `SveOperation_svsubhnb_n_s16`

**Operation**



Return a vector in which, for each even element index *i*:




- element *i* contains the high half of `op1[i/2] - op2`
- element *i* + 1 contains zero



The operation uses modulo arithmetic.  The behavior is therefore defined for all inputs; unlike C, there is no undefined behavior for signed overflow.

## svsubhnb[_n_u16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsubhnb%5B_n_u16%5D

### Signature (source notation)

```c
svuint8_t svsubhnb[_n_u16](svuint16_t op1, uint16_t op2);
```

### Description

Subtract narrow high part (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Subtract / Narrowing subtraction

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
  "op2": {
    "register": "Zop2.H[*]"
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
SUBHNB Zresult.B, Zop1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SUBHNB--Subtract-narrow-high-part--bottom--

### Operation

Source operation ID: `SveOperation_svsubhnb_n_u16`

**Operation**



Return a vector in which, for each even element index *i*:




- element *i* contains the high half of `op1[i/2] - op2`
- element *i* + 1 contains zero

## svsubhnb[_n_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsubhnb%5B_n_u32%5D

### Signature (source notation)

```c
svuint16_t svsubhnb[_n_u32](svuint32_t op1, uint32_t op2);
```

### Description

Subtract narrow high part (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Subtract / Narrowing subtraction

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
  "op2": {
    "register": "Zop2.S[*]"
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
SUBHNB Zresult.H, Zop1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SUBHNB--Subtract-narrow-high-part--bottom--

### Operation

Source operation ID: `SveOperation_svsubhnb_n_u16`

**Operation**



Return a vector in which, for each even element index *i*:




- element *i* contains the high half of `op1[i/2] - op2`
- element *i* + 1 contains zero

## svsubhnb[_n_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsubhnb%5B_n_u64%5D

### Signature (source notation)

```c
svuint32_t svsubhnb[_n_u64](svuint64_t op1, uint64_t op2);
```

### Description

Subtract narrow high part (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Subtract / Narrowing subtraction

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
  "op2": {
    "register": "Zop2.D[*]"
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
SUBHNB Zresult.S, Zop1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SUBHNB--Subtract-narrow-high-part--bottom--

### Operation

Source operation ID: `SveOperation_svsubhnb_n_u16`

**Operation**



Return a vector in which, for each even element index *i*:




- element *i* contains the high half of `op1[i/2] - op2`
- element *i* + 1 contains zero

## svsubhnb[_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsubhnb%5B_s16%5D

### Signature (source notation)

```c
svint8_t svsubhnb[_s16](svint16_t op1, svint16_t op2);
```

### Description

Subtract narrow high part (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Subtract / Narrowing subtraction

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
  "op2": {
    "register": "Zop2.H"
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
SUBHNB Zresult.B, Zop1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SUBHNB--Subtract-narrow-high-part--bottom--

### Operation

Source operation ID: `SveOperation_svsubhnb_s16`

**Operation**



Return a vector in which, for each even element index *i*:




- element *i* contains the high half of `op1[i/2] - op2[i/2]`
- element *i* + 1 contains zero



The operation uses modulo arithmetic.  The behavior is therefore defined for all inputs; unlike C, there is no undefined behavior for signed overflow.

## svsubhnb[_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsubhnb%5B_s32%5D

### Signature (source notation)

```c
svint16_t svsubhnb[_s32](svint32_t op1, svint32_t op2);
```

### Description

Subtract narrow high part (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Subtract / Narrowing subtraction

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
  "op2": {
    "register": "Zop2.S"
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
SUBHNB Zresult.H, Zop1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SUBHNB--Subtract-narrow-high-part--bottom--

### Operation

Source operation ID: `SveOperation_svsubhnb_s16`

**Operation**



Return a vector in which, for each even element index *i*:




- element *i* contains the high half of `op1[i/2] - op2[i/2]`
- element *i* + 1 contains zero



The operation uses modulo arithmetic.  The behavior is therefore defined for all inputs; unlike C, there is no undefined behavior for signed overflow.

## svsubhnb[_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsubhnb%5B_s64%5D

### Signature (source notation)

```c
svint32_t svsubhnb[_s64](svint64_t op1, svint64_t op2);
```

### Description

Subtract narrow high part (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Subtract / Narrowing subtraction

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
  "op2": {
    "register": "Zop2.D"
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
SUBHNB Zresult.S, Zop1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SUBHNB--Subtract-narrow-high-part--bottom--

### Operation

Source operation ID: `SveOperation_svsubhnb_s16`

**Operation**



Return a vector in which, for each even element index *i*:




- element *i* contains the high half of `op1[i/2] - op2[i/2]`
- element *i* + 1 contains zero



The operation uses modulo arithmetic.  The behavior is therefore defined for all inputs; unlike C, there is no undefined behavior for signed overflow.

## svsubhnb[_u16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsubhnb%5B_u16%5D

### Signature (source notation)

```c
svuint8_t svsubhnb[_u16](svuint16_t op1, svuint16_t op2);
```

### Description

Subtract narrow high part (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Subtract / Narrowing subtraction

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
  "op2": {
    "register": "Zop2.H"
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
SUBHNB Zresult.B, Zop1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SUBHNB--Subtract-narrow-high-part--bottom--

### Operation

Source operation ID: `SveOperation_svsubhnb_u16`

**Operation**



Return a vector in which, for each even element index *i*:




- element *i* contains the high half of `op1[i/2] - op2[i/2]`
- element *i* + 1 contains zero

## svsubhnb[_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsubhnb%5B_u32%5D

### Signature (source notation)

```c
svuint16_t svsubhnb[_u32](svuint32_t op1, svuint32_t op2);
```

### Description

Subtract narrow high part (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Subtract / Narrowing subtraction

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
  "op2": {
    "register": "Zop2.S"
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
SUBHNB Zresult.H, Zop1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SUBHNB--Subtract-narrow-high-part--bottom--

### Operation

Source operation ID: `SveOperation_svsubhnb_u16`

**Operation**



Return a vector in which, for each even element index *i*:




- element *i* contains the high half of `op1[i/2] - op2[i/2]`
- element *i* + 1 contains zero

## svsubhnb[_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsubhnb%5B_u64%5D

### Signature (source notation)

```c
svuint32_t svsubhnb[_u64](svuint64_t op1, svuint64_t op2);
```

### Description

Subtract narrow high part (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Subtract / Narrowing subtraction

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
  "op2": {
    "register": "Zop2.D"
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
SUBHNB Zresult.S, Zop1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SUBHNB--Subtract-narrow-high-part--bottom--

### Operation

Source operation ID: `SveOperation_svsubhnb_u16`

**Operation**



Return a vector in which, for each even element index *i*:




- element *i* contains the high half of `op1[i/2] - op2[i/2]`
- element *i* + 1 contains zero

## svsubhnt[_n_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsubhnt%5B_n_s16%5D

### Signature (source notation)

```c
svint8_t svsubhnt[_n_s16](svint8_t even, svint16_t op1, int16_t op2);
```

### Description

Subtract narrow high part (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Subtract / Narrowing subtraction

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
  "op2": {
    "register": "Zop2.H[*]"
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
SUBHNT Ztied.B, Zop1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SUBHNT--Subtract-narrow-high-part--top--

### Operation

Source operation ID: `SveOperation_svsubhnt_n_s16`

**Operation**



Return a vector in which, for each even element index *i*:




- element *i* contains `even[i]`
- element *i* + 1 contains the high half of `op1[i/2] - op2`



The operation uses modulo arithmetic.  The behavior is therefore defined for all inputs; unlike C, there is no undefined behavior for signed overflow.

## svsubhnt[_n_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsubhnt%5B_n_s32%5D

### Signature (source notation)

```c
svint16_t svsubhnt[_n_s32](svint16_t even, svint32_t op1, int32_t op2);
```

### Description

Subtract narrow high part (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Subtract / Narrowing subtraction

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
  "op2": {
    "register": "Zop2.S[*]"
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
SUBHNT Ztied.H, Zop1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SUBHNT--Subtract-narrow-high-part--top--

### Operation

Source operation ID: `SveOperation_svsubhnt_n_s16`

**Operation**



Return a vector in which, for each even element index *i*:




- element *i* contains `even[i]`
- element *i* + 1 contains the high half of `op1[i/2] - op2`



The operation uses modulo arithmetic.  The behavior is therefore defined for all inputs; unlike C, there is no undefined behavior for signed overflow.

## svsubhnt[_n_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsubhnt%5B_n_s64%5D

### Signature (source notation)

```c
svint32_t svsubhnt[_n_s64](svint32_t even, svint64_t op1, int64_t op2);
```

### Description

Subtract narrow high part (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Subtract / Narrowing subtraction

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
  "op2": {
    "register": "Zop2.D[*]"
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
SUBHNT Ztied.S, Zop1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SUBHNT--Subtract-narrow-high-part--top--

### Operation

Source operation ID: `SveOperation_svsubhnt_n_s16`

**Operation**



Return a vector in which, for each even element index *i*:




- element *i* contains `even[i]`
- element *i* + 1 contains the high half of `op1[i/2] - op2`



The operation uses modulo arithmetic.  The behavior is therefore defined for all inputs; unlike C, there is no undefined behavior for signed overflow.

## svsubhnt[_n_u16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsubhnt%5B_n_u16%5D

### Signature (source notation)

```c
svuint8_t svsubhnt[_n_u16](svuint8_t even, svuint16_t op1, uint16_t op2);
```

### Description

Subtract narrow high part (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Subtract / Narrowing subtraction

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
  "op2": {
    "register": "Zop2.H[*]"
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
SUBHNT Ztied.B, Zop1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SUBHNT--Subtract-narrow-high-part--top--

### Operation

Source operation ID: `SveOperation_svsubhnt_n_u16`

**Operation**



Return a vector in which, for each even element index *i*:




- element *i* contains `even[i]`
- element *i* + 1 contains the high half of `op1[i/2] - op2`

## svsubhnt[_n_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsubhnt%5B_n_u32%5D

### Signature (source notation)

```c
svuint16_t svsubhnt[_n_u32](svuint16_t even, svuint32_t op1, uint32_t op2);
```

### Description

Subtract narrow high part (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Subtract / Narrowing subtraction

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
  "op2": {
    "register": "Zop2.S[*]"
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
SUBHNT Ztied.H, Zop1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SUBHNT--Subtract-narrow-high-part--top--

### Operation

Source operation ID: `SveOperation_svsubhnt_n_u16`

**Operation**



Return a vector in which, for each even element index *i*:




- element *i* contains `even[i]`
- element *i* + 1 contains the high half of `op1[i/2] - op2`

## svsubhnt[_n_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsubhnt%5B_n_u64%5D

### Signature (source notation)

```c
svuint32_t svsubhnt[_n_u64](svuint32_t even, svuint64_t op1, uint64_t op2);
```

### Description

Subtract narrow high part (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Subtract / Narrowing subtraction

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
  "op2": {
    "register": "Zop2.D[*]"
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
SUBHNT Ztied.S, Zop1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SUBHNT--Subtract-narrow-high-part--top--

### Operation

Source operation ID: `SveOperation_svsubhnt_n_u16`

**Operation**



Return a vector in which, for each even element index *i*:




- element *i* contains `even[i]`
- element *i* + 1 contains the high half of `op1[i/2] - op2`

## svsubhnt[_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsubhnt%5B_s16%5D

### Signature (source notation)

```c
svint8_t svsubhnt[_s16](svint8_t even, svint16_t op1, svint16_t op2);
```

### Description

Subtract narrow high part (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Subtract / Narrowing subtraction

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
  "op2": {
    "register": "Zop2.H"
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
SUBHNT Ztied.B, Zop1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SUBHNT--Subtract-narrow-high-part--top--

### Operation

Source operation ID: `SveOperation_svsubhnt_s16`

**Operation**



Return a vector in which, for each even element index *i*:




- element *i* contains `even[i]`
- element *i* + 1 contains the high half of `op1[i/2] - op2[i/2]`



The operation uses modulo arithmetic.  The behavior is therefore defined for all inputs; unlike C, there is no undefined behavior for signed overflow.

## svsubhnt[_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsubhnt%5B_s32%5D

### Signature (source notation)

```c
svint16_t svsubhnt[_s32](svint16_t even, svint32_t op1, svint32_t op2);
```

### Description

Subtract narrow high part (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Subtract / Narrowing subtraction

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
  "op2": {
    "register": "Zop2.S"
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
SUBHNT Ztied.H, Zop1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SUBHNT--Subtract-narrow-high-part--top--

### Operation

Source operation ID: `SveOperation_svsubhnt_s16`

**Operation**



Return a vector in which, for each even element index *i*:




- element *i* contains `even[i]`
- element *i* + 1 contains the high half of `op1[i/2] - op2[i/2]`



The operation uses modulo arithmetic.  The behavior is therefore defined for all inputs; unlike C, there is no undefined behavior for signed overflow.

## svsubhnt[_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsubhnt%5B_s64%5D

### Signature (source notation)

```c
svint32_t svsubhnt[_s64](svint32_t even, svint64_t op1, svint64_t op2);
```

### Description

Subtract narrow high part (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Subtract / Narrowing subtraction

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
  "op2": {
    "register": "Zop2.D"
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
SUBHNT Ztied.S, Zop1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SUBHNT--Subtract-narrow-high-part--top--

### Operation

Source operation ID: `SveOperation_svsubhnt_s16`

**Operation**



Return a vector in which, for each even element index *i*:




- element *i* contains `even[i]`
- element *i* + 1 contains the high half of `op1[i/2] - op2[i/2]`



The operation uses modulo arithmetic.  The behavior is therefore defined for all inputs; unlike C, there is no undefined behavior for signed overflow.

## svsubhnt[_u16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsubhnt%5B_u16%5D

### Signature (source notation)

```c
svuint8_t svsubhnt[_u16](svuint8_t even, svuint16_t op1, svuint16_t op2);
```

### Description

Subtract narrow high part (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Subtract / Narrowing subtraction

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
  "op2": {
    "register": "Zop2.H"
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
SUBHNT Ztied.B, Zop1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SUBHNT--Subtract-narrow-high-part--top--

### Operation

Source operation ID: `SveOperation_svsubhnt_u16`

**Operation**



Return a vector in which, for each even element index *i*:




- element *i* contains `even[i]`
- element *i* + 1 contains the high half of `op1[i/2] - op2[i/2]`

## svsubhnt[_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsubhnt%5B_u32%5D

### Signature (source notation)

```c
svuint16_t svsubhnt[_u32](svuint16_t even, svuint32_t op1, svuint32_t op2);
```

### Description

Subtract narrow high part (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Subtract / Narrowing subtraction

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
  "op2": {
    "register": "Zop2.S"
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
SUBHNT Ztied.H, Zop1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SUBHNT--Subtract-narrow-high-part--top--

### Operation

Source operation ID: `SveOperation_svsubhnt_u16`

**Operation**



Return a vector in which, for each even element index *i*:




- element *i* contains `even[i]`
- element *i* + 1 contains the high half of `op1[i/2] - op2[i/2]`

## svsubhnt[_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsubhnt%5B_u64%5D

### Signature (source notation)

```c
svuint32_t svsubhnt[_u64](svuint32_t even, svuint64_t op1, svuint64_t op2);
```

### Description

Subtract narrow high part (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Subtract / Narrowing subtraction

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
  "op2": {
    "register": "Zop2.D"
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
SUBHNT Ztied.S, Zop1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SUBHNT--Subtract-narrow-high-part--top--

### Operation

Source operation ID: `SveOperation_svsubhnt_u16`

**Operation**



Return a vector in which, for each even element index *i*:




- element *i* contains `even[i]`
- element *i* + 1 contains the high half of `op1[i/2] - op2[i/2]`

