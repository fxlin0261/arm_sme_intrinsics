# SME / Vector arithmetic / Add / Narrowing addition — Part 1

## svaddhnb[_n_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svaddhnb%5B_n_s16%5D

### Signature (source notation)

```c
svint8_t svaddhnb[_n_s16](svint16_t op1, int16_t op2);
```

### Description

Add narrow high part (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Narrowing addition

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
ADDHNB Zresult.B, Zop1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ADDHNB--Add-narrow-high-part--bottom--

### Operation

Source operation ID: `SveOperation_svaddhnb_n_s16`

**Operation**



Return a vector in which, for each even element index *i*:




- element *i* contains the high half of `op1[i/2] + op2`
- element *i* + 1 contains zero



The operation uses modulo arithmetic.  The behavior is therefore defined for all inputs; unlike C, there is no undefined behavior for signed overflow.

## svaddhnb[_n_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svaddhnb%5B_n_s32%5D

### Signature (source notation)

```c
svint16_t svaddhnb[_n_s32](svint32_t op1, int32_t op2);
```

### Description

Add narrow high part (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Narrowing addition

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
ADDHNB Zresult.H, Zop1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ADDHNB--Add-narrow-high-part--bottom--

### Operation

Source operation ID: `SveOperation_svaddhnb_n_s16`

**Operation**



Return a vector in which, for each even element index *i*:




- element *i* contains the high half of `op1[i/2] + op2`
- element *i* + 1 contains zero



The operation uses modulo arithmetic.  The behavior is therefore defined for all inputs; unlike C, there is no undefined behavior for signed overflow.

## svaddhnb[_n_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svaddhnb%5B_n_s64%5D

### Signature (source notation)

```c
svint32_t svaddhnb[_n_s64](svint64_t op1, int64_t op2);
```

### Description

Add narrow high part (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Narrowing addition

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
ADDHNB Zresult.S, Zop1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ADDHNB--Add-narrow-high-part--bottom--

### Operation

Source operation ID: `SveOperation_svaddhnb_n_s16`

**Operation**



Return a vector in which, for each even element index *i*:




- element *i* contains the high half of `op1[i/2] + op2`
- element *i* + 1 contains zero



The operation uses modulo arithmetic.  The behavior is therefore defined for all inputs; unlike C, there is no undefined behavior for signed overflow.

## svaddhnb[_n_u16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svaddhnb%5B_n_u16%5D

### Signature (source notation)

```c
svuint8_t svaddhnb[_n_u16](svuint16_t op1, uint16_t op2);
```

### Description

Add narrow high part (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Narrowing addition

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
ADDHNB Zresult.B, Zop1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ADDHNB--Add-narrow-high-part--bottom--

### Operation

Source operation ID: `SveOperation_svaddhnb_n_u16`

**Operation**



Return a vector in which, for each even element index *i*:




- element *i* contains the high half of `op1[i/2] + op2`
- element *i* + 1 contains zero

## svaddhnb[_n_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svaddhnb%5B_n_u32%5D

### Signature (source notation)

```c
svuint16_t svaddhnb[_n_u32](svuint32_t op1, uint32_t op2);
```

### Description

Add narrow high part (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Narrowing addition

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
ADDHNB Zresult.H, Zop1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ADDHNB--Add-narrow-high-part--bottom--

### Operation

Source operation ID: `SveOperation_svaddhnb_n_u16`

**Operation**



Return a vector in which, for each even element index *i*:




- element *i* contains the high half of `op1[i/2] + op2`
- element *i* + 1 contains zero

## svaddhnb[_n_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svaddhnb%5B_n_u64%5D

### Signature (source notation)

```c
svuint32_t svaddhnb[_n_u64](svuint64_t op1, uint64_t op2);
```

### Description

Add narrow high part (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Narrowing addition

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
ADDHNB Zresult.S, Zop1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ADDHNB--Add-narrow-high-part--bottom--

### Operation

Source operation ID: `SveOperation_svaddhnb_n_u16`

**Operation**



Return a vector in which, for each even element index *i*:




- element *i* contains the high half of `op1[i/2] + op2`
- element *i* + 1 contains zero

## svaddhnb[_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svaddhnb%5B_s16%5D

### Signature (source notation)

```c
svint8_t svaddhnb[_s16](svint16_t op1, svint16_t op2);
```

### Description

Add narrow high part (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Narrowing addition

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
ADDHNB Zresult.B, Zop1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ADDHNB--Add-narrow-high-part--bottom--

### Operation

Source operation ID: `SveOperation_svaddhnb_s16`

**Operation**



Return a vector in which, for each even element index *i*:




- element *i* contains the high half of `op1[i/2] + op2[i/2]`
- element *i* + 1 contains zero



The operation uses modulo arithmetic.  The behavior is therefore defined for all inputs; unlike C, there is no undefined behavior for signed overflow.

## svaddhnb[_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svaddhnb%5B_s32%5D

### Signature (source notation)

```c
svint16_t svaddhnb[_s32](svint32_t op1, svint32_t op2);
```

### Description

Add narrow high part (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Narrowing addition

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
ADDHNB Zresult.H, Zop1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ADDHNB--Add-narrow-high-part--bottom--

### Operation

Source operation ID: `SveOperation_svaddhnb_s16`

**Operation**



Return a vector in which, for each even element index *i*:




- element *i* contains the high half of `op1[i/2] + op2[i/2]`
- element *i* + 1 contains zero



The operation uses modulo arithmetic.  The behavior is therefore defined for all inputs; unlike C, there is no undefined behavior for signed overflow.

## svaddhnb[_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svaddhnb%5B_s64%5D

### Signature (source notation)

```c
svint32_t svaddhnb[_s64](svint64_t op1, svint64_t op2);
```

### Description

Add narrow high part (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Narrowing addition

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
ADDHNB Zresult.S, Zop1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ADDHNB--Add-narrow-high-part--bottom--

### Operation

Source operation ID: `SveOperation_svaddhnb_s16`

**Operation**



Return a vector in which, for each even element index *i*:




- element *i* contains the high half of `op1[i/2] + op2[i/2]`
- element *i* + 1 contains zero



The operation uses modulo arithmetic.  The behavior is therefore defined for all inputs; unlike C, there is no undefined behavior for signed overflow.

## svaddhnb[_u16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svaddhnb%5B_u16%5D

### Signature (source notation)

```c
svuint8_t svaddhnb[_u16](svuint16_t op1, svuint16_t op2);
```

### Description

Add narrow high part (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Narrowing addition

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
ADDHNB Zresult.B, Zop1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ADDHNB--Add-narrow-high-part--bottom--

### Operation

Source operation ID: `SveOperation_svaddhnb_u16`

**Operation**



Return a vector in which, for each even element index *i*:




- element *i* contains the high half of `op1[i/2] + op2[i/2]`
- element *i* + 1 contains zero

## svaddhnb[_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svaddhnb%5B_u32%5D

### Signature (source notation)

```c
svuint16_t svaddhnb[_u32](svuint32_t op1, svuint32_t op2);
```

### Description

Add narrow high part (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Narrowing addition

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
ADDHNB Zresult.H, Zop1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ADDHNB--Add-narrow-high-part--bottom--

### Operation

Source operation ID: `SveOperation_svaddhnb_u16`

**Operation**



Return a vector in which, for each even element index *i*:




- element *i* contains the high half of `op1[i/2] + op2[i/2]`
- element *i* + 1 contains zero

## svaddhnb[_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svaddhnb%5B_u64%5D

### Signature (source notation)

```c
svuint32_t svaddhnb[_u64](svuint64_t op1, svuint64_t op2);
```

### Description

Add narrow high part (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Narrowing addition

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
ADDHNB Zresult.S, Zop1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ADDHNB--Add-narrow-high-part--bottom--

### Operation

Source operation ID: `SveOperation_svaddhnb_u16`

**Operation**



Return a vector in which, for each even element index *i*:




- element *i* contains the high half of `op1[i/2] + op2[i/2]`
- element *i* + 1 contains zero

## svaddhnt[_n_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svaddhnt%5B_n_s16%5D

### Signature (source notation)

```c
svint8_t svaddhnt[_n_s16](svint8_t even, svint16_t op1, int16_t op2);
```

### Description

Add narrow high part (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Narrowing addition

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
ADDHNT Ztied.B, Zop1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ADDHNT--Add-narrow-high-part--top--

### Operation

Source operation ID: `SveOperation_svaddhnt_n_s16`

**Operation**



Return a vector in which, for each even element index *i*:




- element *i* contains `even[i]`
- element *i* + 1 contains the high half of `op1[i/2] + op2`



The operation uses modulo arithmetic.  The behavior is therefore defined for all inputs; unlike C, there is no undefined behavior for signed overflow.

## svaddhnt[_n_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svaddhnt%5B_n_s32%5D

### Signature (source notation)

```c
svint16_t svaddhnt[_n_s32](svint16_t even, svint32_t op1, int32_t op2);
```

### Description

Add narrow high part (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Narrowing addition

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
ADDHNT Ztied.H, Zop1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ADDHNT--Add-narrow-high-part--top--

### Operation

Source operation ID: `SveOperation_svaddhnt_n_s16`

**Operation**



Return a vector in which, for each even element index *i*:




- element *i* contains `even[i]`
- element *i* + 1 contains the high half of `op1[i/2] + op2`



The operation uses modulo arithmetic.  The behavior is therefore defined for all inputs; unlike C, there is no undefined behavior for signed overflow.

## svaddhnt[_n_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svaddhnt%5B_n_s64%5D

### Signature (source notation)

```c
svint32_t svaddhnt[_n_s64](svint32_t even, svint64_t op1, int64_t op2);
```

### Description

Add narrow high part (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Narrowing addition

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
ADDHNT Ztied.S, Zop1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ADDHNT--Add-narrow-high-part--top--

### Operation

Source operation ID: `SveOperation_svaddhnt_n_s16`

**Operation**



Return a vector in which, for each even element index *i*:




- element *i* contains `even[i]`
- element *i* + 1 contains the high half of `op1[i/2] + op2`



The operation uses modulo arithmetic.  The behavior is therefore defined for all inputs; unlike C, there is no undefined behavior for signed overflow.

## svaddhnt[_n_u16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svaddhnt%5B_n_u16%5D

### Signature (source notation)

```c
svuint8_t svaddhnt[_n_u16](svuint8_t even, svuint16_t op1, uint16_t op2);
```

### Description

Add narrow high part (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Narrowing addition

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
ADDHNT Ztied.B, Zop1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ADDHNT--Add-narrow-high-part--top--

### Operation

Source operation ID: `SveOperation_svaddhnt_n_u16`

**Operation**



Return a vector in which, for each even element index *i*:




- element *i* contains `even[i]`
- element *i* + 1 contains the high half of `op1[i/2] + op2`

## svaddhnt[_n_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svaddhnt%5B_n_u32%5D

### Signature (source notation)

```c
svuint16_t svaddhnt[_n_u32](svuint16_t even, svuint32_t op1, uint32_t op2);
```

### Description

Add narrow high part (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Narrowing addition

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
ADDHNT Ztied.H, Zop1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ADDHNT--Add-narrow-high-part--top--

### Operation

Source operation ID: `SveOperation_svaddhnt_n_u16`

**Operation**



Return a vector in which, for each even element index *i*:




- element *i* contains `even[i]`
- element *i* + 1 contains the high half of `op1[i/2] + op2`

## svaddhnt[_n_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svaddhnt%5B_n_u64%5D

### Signature (source notation)

```c
svuint32_t svaddhnt[_n_u64](svuint32_t even, svuint64_t op1, uint64_t op2);
```

### Description

Add narrow high part (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Narrowing addition

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
ADDHNT Ztied.S, Zop1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ADDHNT--Add-narrow-high-part--top--

### Operation

Source operation ID: `SveOperation_svaddhnt_n_u16`

**Operation**



Return a vector in which, for each even element index *i*:




- element *i* contains `even[i]`
- element *i* + 1 contains the high half of `op1[i/2] + op2`

## svaddhnt[_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svaddhnt%5B_s16%5D

### Signature (source notation)

```c
svint8_t svaddhnt[_s16](svint8_t even, svint16_t op1, svint16_t op2);
```

### Description

Add narrow high part (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Narrowing addition

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
ADDHNT Ztied.B, Zop1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ADDHNT--Add-narrow-high-part--top--

### Operation

Source operation ID: `SveOperation_svaddhnt_s16`

**Operation**



Return a vector in which, for each even element index *i*:




- element *i* contains `even[i]`
- element *i* + 1 contains the high half of `op1[i/2] + op2[i/2]`



The operation uses modulo arithmetic.  The behavior is therefore defined for all inputs; unlike C, there is no undefined behavior for signed overflow.

## svaddhnt[_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svaddhnt%5B_s32%5D

### Signature (source notation)

```c
svint16_t svaddhnt[_s32](svint16_t even, svint32_t op1, svint32_t op2);
```

### Description

Add narrow high part (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Narrowing addition

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
ADDHNT Ztied.H, Zop1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ADDHNT--Add-narrow-high-part--top--

### Operation

Source operation ID: `SveOperation_svaddhnt_s16`

**Operation**



Return a vector in which, for each even element index *i*:




- element *i* contains `even[i]`
- element *i* + 1 contains the high half of `op1[i/2] + op2[i/2]`



The operation uses modulo arithmetic.  The behavior is therefore defined for all inputs; unlike C, there is no undefined behavior for signed overflow.

## svaddhnt[_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svaddhnt%5B_s64%5D

### Signature (source notation)

```c
svint32_t svaddhnt[_s64](svint32_t even, svint64_t op1, svint64_t op2);
```

### Description

Add narrow high part (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Narrowing addition

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
ADDHNT Ztied.S, Zop1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ADDHNT--Add-narrow-high-part--top--

### Operation

Source operation ID: `SveOperation_svaddhnt_s16`

**Operation**



Return a vector in which, for each even element index *i*:




- element *i* contains `even[i]`
- element *i* + 1 contains the high half of `op1[i/2] + op2[i/2]`



The operation uses modulo arithmetic.  The behavior is therefore defined for all inputs; unlike C, there is no undefined behavior for signed overflow.

## svaddhnt[_u16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svaddhnt%5B_u16%5D

### Signature (source notation)

```c
svuint8_t svaddhnt[_u16](svuint8_t even, svuint16_t op1, svuint16_t op2);
```

### Description

Add narrow high part (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Narrowing addition

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
ADDHNT Ztied.B, Zop1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ADDHNT--Add-narrow-high-part--top--

### Operation

Source operation ID: `SveOperation_svaddhnt_u16`

**Operation**



Return a vector in which, for each even element index *i*:




- element *i* contains `even[i]`
- element *i* + 1 contains the high half of `op1[i/2] + op2[i/2]`

## svaddhnt[_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svaddhnt%5B_u32%5D

### Signature (source notation)

```c
svuint16_t svaddhnt[_u32](svuint16_t even, svuint32_t op1, svuint32_t op2);
```

### Description

Add narrow high part (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Narrowing addition

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
ADDHNT Ztied.H, Zop1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ADDHNT--Add-narrow-high-part--top--

### Operation

Source operation ID: `SveOperation_svaddhnt_u16`

**Operation**



Return a vector in which, for each even element index *i*:




- element *i* contains `even[i]`
- element *i* + 1 contains the high half of `op1[i/2] + op2[i/2]`

## svaddhnt[_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svaddhnt%5B_u64%5D

### Signature (source notation)

```c
svuint32_t svaddhnt[_u64](svuint32_t even, svuint64_t op1, svuint64_t op2);
```

### Description

Add narrow high part (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Narrowing addition

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
ADDHNT Ztied.S, Zop1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ADDHNT--Add-narrow-high-part--top--

### Operation

Source operation ID: `SveOperation_svaddhnt_u16`

**Operation**



Return a vector in which, for each even element index *i*:




- element *i* contains `even[i]`
- element *i* + 1 contains the high half of `op1[i/2] + op2[i/2]`

## svraddhnb[_n_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svraddhnb%5B_n_s16%5D

### Signature (source notation)

```c
svint8_t svraddhnb[_n_s16](svint16_t op1, int16_t op2);
```

### Description

Rounding add narrow high part (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Narrowing addition

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
RADDHNB Zresult.B, Zop1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/RADDHNB--Rounding-add-narrow-high-part--bottom--

### Operation

Source operation ID: `SveOperation_svraddhnb_n_s16`

**Operation**



Return a vector in which each even-indexed (“bottom”) element *i* contains the result of the following procedure:




- Add `op1[i/2]` and `op2` together, without loss of precision.
- Divide the result by 2 to the power 8, rounding to nearest with ties towards +∞.
- Truncate the result to the range of `int8_t`.



Set the odd-indexed elements of the result vector to zero.

## svraddhnb[_n_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svraddhnb%5B_n_s32%5D

### Signature (source notation)

```c
svint16_t svraddhnb[_n_s32](svint32_t op1, int32_t op2);
```

### Description

Rounding add narrow high part (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Narrowing addition

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
RADDHNB Zresult.H, Zop1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/RADDHNB--Rounding-add-narrow-high-part--bottom--

### Operation

Source operation ID: `SveOperation_svraddhnb_n_s32`

**Operation**



Return a vector in which each even-indexed (“bottom”) element *i* contains the result of the following procedure:




- Add `op1[i/2]` and `op2` together, without loss of precision.
- Divide the result by 2 to the power 16, rounding to nearest with ties towards +∞.
- Truncate the result to the range of `int16_t`.



Set the odd-indexed elements of the result vector to zero.

## svraddhnb[_n_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svraddhnb%5B_n_s64%5D

### Signature (source notation)

```c
svint32_t svraddhnb[_n_s64](svint64_t op1, int64_t op2);
```

### Description

Rounding add narrow high part (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Narrowing addition

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
RADDHNB Zresult.S, Zop1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/RADDHNB--Rounding-add-narrow-high-part--bottom--

### Operation

Source operation ID: `SveOperation_svraddhnb_n_s64`

**Operation**



Return a vector in which each even-indexed (“bottom”) element *i* contains the result of the following procedure:




- Add `op1[i/2]` and `op2` together, without loss of precision.
- Divide the result by 2 to the power 32, rounding to nearest with ties towards +∞.
- Truncate the result to the range of `int32_t`.



Set the odd-indexed elements of the result vector to zero.

## svraddhnb[_n_u16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svraddhnb%5B_n_u16%5D

### Signature (source notation)

```c
svuint8_t svraddhnb[_n_u16](svuint16_t op1, uint16_t op2);
```

### Description

Rounding add narrow high part (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Narrowing addition

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
RADDHNB Zresult.B, Zop1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/RADDHNB--Rounding-add-narrow-high-part--bottom--

### Operation

Source operation ID: `SveOperation_svraddhnb_n_u16`

**Operation**



Return a vector in which each even-indexed (“bottom”) element *i* contains the result of the following procedure:




- Add `op1[i/2]` and `op2` together, without loss of precision.
- Divide the result by 2 to the power 8, rounding to nearest with ties towards +∞.
- Truncate the result to the range of `uint8_t`.



Set the odd-indexed elements of the result vector to zero.

## svraddhnb[_n_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svraddhnb%5B_n_u32%5D

### Signature (source notation)

```c
svuint16_t svraddhnb[_n_u32](svuint32_t op1, uint32_t op2);
```

### Description

Rounding add narrow high part (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Narrowing addition

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
RADDHNB Zresult.H, Zop1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/RADDHNB--Rounding-add-narrow-high-part--bottom--

### Operation

Source operation ID: `SveOperation_svraddhnb_n_u32`

**Operation**



Return a vector in which each even-indexed (“bottom”) element *i* contains the result of the following procedure:




- Add `op1[i/2]` and `op2` together, without loss of precision.
- Divide the result by 2 to the power 16, rounding to nearest with ties towards +∞.
- Truncate the result to the range of `uint16_t`.



Set the odd-indexed elements of the result vector to zero.

## svraddhnb[_n_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svraddhnb%5B_n_u64%5D

### Signature (source notation)

```c
svuint32_t svraddhnb[_n_u64](svuint64_t op1, uint64_t op2);
```

### Description

Rounding add narrow high part (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Narrowing addition

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
RADDHNB Zresult.S, Zop1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/RADDHNB--Rounding-add-narrow-high-part--bottom--

### Operation

Source operation ID: `SveOperation_svraddhnb_n_u64`

**Operation**



Return a vector in which each even-indexed (“bottom”) element *i* contains the result of the following procedure:




- Add `op1[i/2]` and `op2` together, without loss of precision.
- Divide the result by 2 to the power 32, rounding to nearest with ties towards +∞.
- Truncate the result to the range of `uint32_t`.



Set the odd-indexed elements of the result vector to zero.

## svraddhnb[_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svraddhnb%5B_s16%5D

### Signature (source notation)

```c
svint8_t svraddhnb[_s16](svint16_t op1, svint16_t op2);
```

### Description

Rounding add narrow high part (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Narrowing addition

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
RADDHNB Zresult.B, Zop1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/RADDHNB--Rounding-add-narrow-high-part--bottom--

### Operation

Source operation ID: `SveOperation_svraddhnb_s16`

**Operation**



Return a vector in which each even-indexed (“bottom”) element *i* contains the result of the following procedure:




- Add `op1[i/2]` and `op2[i/2]` together, without loss of precision.
- Divide the result by 2 to the power 8, rounding to nearest with ties towards +∞.
- Truncate the result to the range of `int8_t`.



Set the odd-indexed elements of the result vector to zero.

## svraddhnb[_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svraddhnb%5B_s32%5D

### Signature (source notation)

```c
svint16_t svraddhnb[_s32](svint32_t op1, svint32_t op2);
```

### Description

Rounding add narrow high part (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Narrowing addition

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
RADDHNB Zresult.H, Zop1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/RADDHNB--Rounding-add-narrow-high-part--bottom--

### Operation

Source operation ID: `SveOperation_svraddhnb_s32`

**Operation**



Return a vector in which each even-indexed (“bottom”) element *i* contains the result of the following procedure:




- Add `op1[i/2]` and `op2[i/2]` together, without loss of precision.
- Divide the result by 2 to the power 16, rounding to nearest with ties towards +∞.
- Truncate the result to the range of `int16_t`.



Set the odd-indexed elements of the result vector to zero.

## svraddhnb[_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svraddhnb%5B_s64%5D

### Signature (source notation)

```c
svint32_t svraddhnb[_s64](svint64_t op1, svint64_t op2);
```

### Description

Rounding add narrow high part (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Narrowing addition

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
RADDHNB Zresult.S, Zop1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/RADDHNB--Rounding-add-narrow-high-part--bottom--

### Operation

Source operation ID: `SveOperation_svraddhnb_s64`

**Operation**



Return a vector in which each even-indexed (“bottom”) element *i* contains the result of the following procedure:




- Add `op1[i/2]` and `op2[i/2]` together, without loss of precision.
- Divide the result by 2 to the power 32, rounding to nearest with ties towards +∞.
- Truncate the result to the range of `int32_t`.



Set the odd-indexed elements of the result vector to zero.

## svraddhnb[_u16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svraddhnb%5B_u16%5D

### Signature (source notation)

```c
svuint8_t svraddhnb[_u16](svuint16_t op1, svuint16_t op2);
```

### Description

Rounding add narrow high part (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Narrowing addition

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
RADDHNB Zresult.B, Zop1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/RADDHNB--Rounding-add-narrow-high-part--bottom--

### Operation

Source operation ID: `SveOperation_svraddhnb_u16`

**Operation**



Return a vector in which each even-indexed (“bottom”) element *i* contains the result of the following procedure:




- Add `op1[i/2]` and `op2[i/2]` together, without loss of precision.
- Divide the result by 2 to the power 8, rounding to nearest with ties towards +∞.
- Truncate the result to the range of `uint8_t`.



Set the odd-indexed elements of the result vector to zero.

## svraddhnb[_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svraddhnb%5B_u32%5D

### Signature (source notation)

```c
svuint16_t svraddhnb[_u32](svuint32_t op1, svuint32_t op2);
```

### Description

Rounding add narrow high part (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Narrowing addition

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
RADDHNB Zresult.H, Zop1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/RADDHNB--Rounding-add-narrow-high-part--bottom--

### Operation

Source operation ID: `SveOperation_svraddhnb_u32`

**Operation**



Return a vector in which each even-indexed (“bottom”) element *i* contains the result of the following procedure:




- Add `op1[i/2]` and `op2[i/2]` together, without loss of precision.
- Divide the result by 2 to the power 16, rounding to nearest with ties towards +∞.
- Truncate the result to the range of `uint16_t`.



Set the odd-indexed elements of the result vector to zero.

## svraddhnb[_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svraddhnb%5B_u64%5D

### Signature (source notation)

```c
svuint32_t svraddhnb[_u64](svuint64_t op1, svuint64_t op2);
```

### Description

Rounding add narrow high part (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Narrowing addition

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
RADDHNB Zresult.S, Zop1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/RADDHNB--Rounding-add-narrow-high-part--bottom--

### Operation

Source operation ID: `SveOperation_svraddhnb_u64`

**Operation**



Return a vector in which each even-indexed (“bottom”) element *i* contains the result of the following procedure:




- Add `op1[i/2]` and `op2[i/2]` together, without loss of precision.
- Divide the result by 2 to the power 32, rounding to nearest with ties towards +∞.
- Truncate the result to the range of `uint32_t`.



Set the odd-indexed elements of the result vector to zero.

## svraddhnt[_n_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svraddhnt%5B_n_s16%5D

### Signature (source notation)

```c
svint8_t svraddhnt[_n_s16](svint8_t even, svint16_t op1, int16_t op2);
```

### Description

Rounding add narrow high part (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Narrowing addition

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
RADDHNT Ztied.B, Zop1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/RADDHNT--Rounding-add-narrow-high-part--top--

### Operation

Source operation ID: `SveOperation_svraddhnt_n_s16`

**Operation**



Return a vector in which each odd-indexed (“top”) element *i* contains the result of the following procedure:




- Add `op1[i/2]` and `op2` together, without loss of precision.
- Divide the result by 2 to the power 8, rounding to nearest with ties towards +∞.
- Truncate the result to the range of `int8_t`.



Copy the even-indexed elements of the result vector from the corresponding elements of `even`.

## svraddhnt[_n_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svraddhnt%5B_n_s32%5D

### Signature (source notation)

```c
svint16_t svraddhnt[_n_s32](svint16_t even, svint32_t op1, int32_t op2);
```

### Description

Rounding add narrow high part (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Narrowing addition

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
RADDHNT Ztied.H, Zop1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/RADDHNT--Rounding-add-narrow-high-part--top--

### Operation

Source operation ID: `SveOperation_svraddhnt_n_s32`

**Operation**



Return a vector in which each odd-indexed (“top”) element *i* contains the result of the following procedure:




- Add `op1[i/2]` and `op2` together, without loss of precision.
- Divide the result by 2 to the power 16, rounding to nearest with ties towards +∞.
- Truncate the result to the range of `int16_t`.



Copy the even-indexed elements of the result vector from the corresponding elements of `even`.

## svraddhnt[_n_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svraddhnt%5B_n_s64%5D

### Signature (source notation)

```c
svint32_t svraddhnt[_n_s64](svint32_t even, svint64_t op1, int64_t op2);
```

### Description

Rounding add narrow high part (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Narrowing addition

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
RADDHNT Ztied.S, Zop1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/RADDHNT--Rounding-add-narrow-high-part--top--

### Operation

Source operation ID: `SveOperation_svraddhnt_n_s64`

**Operation**



Return a vector in which each odd-indexed (“top”) element *i* contains the result of the following procedure:




- Add `op1[i/2]` and `op2` together, without loss of precision.
- Divide the result by 2 to the power 32, rounding to nearest with ties towards +∞.
- Truncate the result to the range of `int32_t`.



Copy the even-indexed elements of the result vector from the corresponding elements of `even`.

## svraddhnt[_n_u16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svraddhnt%5B_n_u16%5D

### Signature (source notation)

```c
svuint8_t svraddhnt[_n_u16](svuint8_t even, svuint16_t op1, uint16_t op2);
```

### Description

Rounding add narrow high part (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Narrowing addition

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
RADDHNT Ztied.B, Zop1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/RADDHNT--Rounding-add-narrow-high-part--top--

### Operation

Source operation ID: `SveOperation_svraddhnt_n_u16`

**Operation**



Return a vector in which each odd-indexed (“top”) element *i* contains the result of the following procedure:




- Add `op1[i/2]` and `op2` together, without loss of precision.
- Divide the result by 2 to the power 8, rounding to nearest with ties towards +∞.
- Truncate the result to the range of `uint8_t`.



Copy the even-indexed elements of the result vector from the corresponding elements of `even`.

## svraddhnt[_n_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svraddhnt%5B_n_u32%5D

### Signature (source notation)

```c
svuint16_t svraddhnt[_n_u32](svuint16_t even, svuint32_t op1, uint32_t op2);
```

### Description

Rounding add narrow high part (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Narrowing addition

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
RADDHNT Ztied.H, Zop1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/RADDHNT--Rounding-add-narrow-high-part--top--

### Operation

Source operation ID: `SveOperation_svraddhnt_n_u32`

**Operation**



Return a vector in which each odd-indexed (“top”) element *i* contains the result of the following procedure:




- Add `op1[i/2]` and `op2` together, without loss of precision.
- Divide the result by 2 to the power 16, rounding to nearest with ties towards +∞.
- Truncate the result to the range of `uint16_t`.



Copy the even-indexed elements of the result vector from the corresponding elements of `even`.

## svraddhnt[_n_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svraddhnt%5B_n_u64%5D

### Signature (source notation)

```c
svuint32_t svraddhnt[_n_u64](svuint32_t even, svuint64_t op1, uint64_t op2);
```

### Description

Rounding add narrow high part (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Narrowing addition

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
RADDHNT Ztied.S, Zop1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/RADDHNT--Rounding-add-narrow-high-part--top--

### Operation

Source operation ID: `SveOperation_svraddhnt_n_u64`

**Operation**



Return a vector in which each odd-indexed (“top”) element *i* contains the result of the following procedure:




- Add `op1[i/2]` and `op2` together, without loss of precision.
- Divide the result by 2 to the power 32, rounding to nearest with ties towards +∞.
- Truncate the result to the range of `uint32_t`.



Copy the even-indexed elements of the result vector from the corresponding elements of `even`.

## svraddhnt[_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svraddhnt%5B_s16%5D

### Signature (source notation)

```c
svint8_t svraddhnt[_s16](svint8_t even, svint16_t op1, svint16_t op2);
```

### Description

Rounding add narrow high part (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Narrowing addition

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
RADDHNT Ztied.B, Zop1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/RADDHNT--Rounding-add-narrow-high-part--top--

### Operation

Source operation ID: `SveOperation_svraddhnt_s16`

**Operation**



Return a vector in which each odd-indexed (“top”) element *i* contains the result of the following procedure:




- Add `op1[i/2]` and `op2[i/2]` together, without loss of precision.
- Divide the result by 2 to the power 8, rounding to nearest with ties towards +∞.
- Truncate the result to the range of `int8_t`.



Copy the even-indexed elements of the result vector from the corresponding elements of `even`.

## svraddhnt[_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svraddhnt%5B_s32%5D

### Signature (source notation)

```c
svint16_t svraddhnt[_s32](svint16_t even, svint32_t op1, svint32_t op2);
```

### Description

Rounding add narrow high part (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Narrowing addition

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
RADDHNT Ztied.H, Zop1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/RADDHNT--Rounding-add-narrow-high-part--top--

### Operation

Source operation ID: `SveOperation_svraddhnt_s32`

**Operation**



Return a vector in which each odd-indexed (“top”) element *i* contains the result of the following procedure:




- Add `op1[i/2]` and `op2[i/2]` together, without loss of precision.
- Divide the result by 2 to the power 16, rounding to nearest with ties towards +∞.
- Truncate the result to the range of `int16_t`.



Copy the even-indexed elements of the result vector from the corresponding elements of `even`.

## svraddhnt[_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svraddhnt%5B_s64%5D

### Signature (source notation)

```c
svint32_t svraddhnt[_s64](svint32_t even, svint64_t op1, svint64_t op2);
```

### Description

Rounding add narrow high part (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Narrowing addition

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
RADDHNT Ztied.S, Zop1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/RADDHNT--Rounding-add-narrow-high-part--top--

### Operation

Source operation ID: `SveOperation_svraddhnt_s64`

**Operation**



Return a vector in which each odd-indexed (“top”) element *i* contains the result of the following procedure:




- Add `op1[i/2]` and `op2[i/2]` together, without loss of precision.
- Divide the result by 2 to the power 32, rounding to nearest with ties towards +∞.
- Truncate the result to the range of `int32_t`.



Copy the even-indexed elements of the result vector from the corresponding elements of `even`.

## svraddhnt[_u16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svraddhnt%5B_u16%5D

### Signature (source notation)

```c
svuint8_t svraddhnt[_u16](svuint8_t even, svuint16_t op1, svuint16_t op2);
```

### Description

Rounding add narrow high part (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Narrowing addition

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
RADDHNT Ztied.B, Zop1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/RADDHNT--Rounding-add-narrow-high-part--top--

### Operation

Source operation ID: `SveOperation_svraddhnt_u16`

**Operation**



Return a vector in which each odd-indexed (“top”) element *i* contains the result of the following procedure:




- Add `op1[i/2]` and `op2[i/2]` together, without loss of precision.
- Divide the result by 2 to the power 8, rounding to nearest with ties towards +∞.
- Truncate the result to the range of `uint8_t`.



Copy the even-indexed elements of the result vector from the corresponding elements of `even`.

## svraddhnt[_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svraddhnt%5B_u32%5D

### Signature (source notation)

```c
svuint16_t svraddhnt[_u32](svuint16_t even, svuint32_t op1, svuint32_t op2);
```

### Description

Rounding add narrow high part (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Narrowing addition

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
RADDHNT Ztied.H, Zop1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/RADDHNT--Rounding-add-narrow-high-part--top--

### Operation

Source operation ID: `SveOperation_svraddhnt_u32`

**Operation**



Return a vector in which each odd-indexed (“top”) element *i* contains the result of the following procedure:




- Add `op1[i/2]` and `op2[i/2]` together, without loss of precision.
- Divide the result by 2 to the power 16, rounding to nearest with ties towards +∞.
- Truncate the result to the range of `uint16_t`.



Copy the even-indexed elements of the result vector from the corresponding elements of `even`.

## svraddhnt[_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svraddhnt%5B_u64%5D

### Signature (source notation)

```c
svuint32_t svraddhnt[_u64](svuint32_t even, svuint64_t op1, svuint64_t op2);
```

### Description

Rounding add narrow high part (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Add / Narrowing addition

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
RADDHNT Ztied.S, Zop1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/RADDHNT--Rounding-add-narrow-high-part--top--

### Operation

Source operation ID: `SveOperation_svraddhnt_u64`

**Operation**



Return a vector in which each odd-indexed (“top”) element *i* contains the result of the following procedure:




- Add `op1[i/2]` and `op2[i/2]` together, without loss of precision.
- Divide the result by 2 to the power 32, rounding to nearest with ties towards +∞.
- Truncate the result to the range of `uint32_t`.



Copy the even-indexed elements of the result vector from the corresponding elements of `even`.

