# SME / Shift / Left / Vector shift left and widen — Part 1

## svshllb[_n_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svshllb%5B_n_s16%5D

### Signature (source notation)

```c
svint16_t svshllb[_n_s16](svint8_t op1, uint64_t imm2);
```

### Description

Shift left long (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Shift / Left / Vector shift left and widen

- SME attributes: Not specified by source.

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
  "imm2": {
    "minimum": 0,
    "maximum": 7
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
SSHLLB Zresult.H, Zop1.B, #imm2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SSHLLB--Signed-shift-left-long-by-immediate--bottom--

### Operation

Source operation ID: `SveOperation_svshllb_n_s16`

**Operation**



Return a vector in which each element *i* contains:



```text
(int16_t)op1[i * 2] << imm2
```

## svshllb[_n_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svshllb%5B_n_s32%5D

### Signature (source notation)

```c
svint32_t svshllb[_n_s32](svint16_t op1, uint64_t imm2);
```

### Description

Shift left long (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Shift / Left / Vector shift left and widen

- SME attributes: Not specified by source.

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
  "imm2": {
    "minimum": 0,
    "maximum": 15
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
SSHLLB Zresult.S, Zop1.H, #imm2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SSHLLB--Signed-shift-left-long-by-immediate--bottom--

### Operation

Source operation ID: `SveOperation_svshllb_n_s32`

**Operation**



Return a vector in which each element *i* contains:



```text
(int32_t)op1[i * 2] << imm2
```

## svshllb[_n_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svshllb%5B_n_s64%5D

### Signature (source notation)

```c
svint64_t svshllb[_n_s64](svint32_t op1, uint64_t imm2);
```

### Description

Shift left long (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Shift / Left / Vector shift left and widen

- SME attributes: Not specified by source.

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
  "imm2": {
    "minimum": 0,
    "maximum": 31
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
SSHLLB Zresult.D, Zop1.S, #imm2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SSHLLB--Signed-shift-left-long-by-immediate--bottom--

### Operation

Source operation ID: `SveOperation_svshllb_n_s64`

**Operation**



Return a vector in which each element *i* contains:



```text
(int64_t)op1[i * 2] << imm2
```

## svshllb[_n_u16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svshllb%5B_n_u16%5D

### Signature (source notation)

```c
svuint16_t svshllb[_n_u16](svuint8_t op1, uint64_t imm2);
```

### Description

Shift left long (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Shift / Left / Vector shift left and widen

- SME attributes: Not specified by source.

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
  "imm2": {
    "minimum": 0,
    "maximum": 7
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
USHLLB Zresult.H, Zop1.B, #imm2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/USHLLB--Unsigned-shift-left-long-by-immediate--bottom--

### Operation

Source operation ID: `SveOperation_svshllb_n_u16`

**Operation**



Return a vector in which each element *i* contains:



```text
(uint16_t)op1[i * 2] << imm2
```

## svshllb[_n_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svshllb%5B_n_u32%5D

### Signature (source notation)

```c
svuint32_t svshllb[_n_u32](svuint16_t op1, uint64_t imm2);
```

### Description

Shift left long (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Shift / Left / Vector shift left and widen

- SME attributes: Not specified by source.

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
  "imm2": {
    "minimum": 0,
    "maximum": 15
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
USHLLB Zresult.S, Zop1.H, #imm2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/USHLLB--Unsigned-shift-left-long-by-immediate--bottom--

### Operation

Source operation ID: `SveOperation_svshllb_n_u32`

**Operation**



Return a vector in which each element *i* contains:



```text
(uint32_t)op1[i * 2] << imm2
```

## svshllb[_n_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svshllb%5B_n_u64%5D

### Signature (source notation)

```c
svuint64_t svshllb[_n_u64](svuint32_t op1, uint64_t imm2);
```

### Description

Shift left long (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Shift / Left / Vector shift left and widen

- SME attributes: Not specified by source.

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
  "imm2": {
    "minimum": 0,
    "maximum": 31
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
USHLLB Zresult.D, Zop1.S, #imm2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/USHLLB--Unsigned-shift-left-long-by-immediate--bottom--

### Operation

Source operation ID: `SveOperation_svshllb_n_u64`

**Operation**



Return a vector in which each element *i* contains:



```text
(uint64_t)op1[i * 2] << imm2
```

## svshllt[_n_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svshllt%5B_n_s16%5D

### Signature (source notation)

```c
svint16_t svshllt[_n_s16](svint8_t op1, uint64_t imm2);
```

### Description

Shift left long (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Shift / Left / Vector shift left and widen

- SME attributes: Not specified by source.

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
  "imm2": {
    "minimum": 0,
    "maximum": 7
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
SSHLLT Zresult.H, Zop1.B, #imm2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SSHLLT--Signed-shift-left-long-by-immediate--top--

### Operation

Source operation ID: `SveOperation_svshllt_n_s16`

**Operation**



Return a vector in which each element *i* contains:



```text
(int16_t)op1[i * 2 + 1] << imm2
```

## svshllt[_n_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svshllt%5B_n_s32%5D

### Signature (source notation)

```c
svint32_t svshllt[_n_s32](svint16_t op1, uint64_t imm2);
```

### Description

Shift left long (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Shift / Left / Vector shift left and widen

- SME attributes: Not specified by source.

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
  "imm2": {
    "minimum": 0,
    "maximum": 15
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
SSHLLT Zresult.S, Zop1.H, #imm2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SSHLLT--Signed-shift-left-long-by-immediate--top--

### Operation

Source operation ID: `SveOperation_svshllt_n_s32`

**Operation**



Return a vector in which each element *i* contains:



```text
(int32_t)op1[i * 2 + 1] << imm2
```

## svshllt[_n_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svshllt%5B_n_s64%5D

### Signature (source notation)

```c
svint64_t svshllt[_n_s64](svint32_t op1, uint64_t imm2);
```

### Description

Shift left long (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Shift / Left / Vector shift left and widen

- SME attributes: Not specified by source.

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
  "imm2": {
    "minimum": 0,
    "maximum": 31
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
SSHLLT Zresult.D, Zop1.S, #imm2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SSHLLT--Signed-shift-left-long-by-immediate--top--

### Operation

Source operation ID: `SveOperation_svshllt_n_s64`

**Operation**



Return a vector in which each element *i* contains:



```text
(int64_t)op1[i * 2 + 1] << imm2
```

## svshllt[_n_u16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svshllt%5B_n_u16%5D

### Signature (source notation)

```c
svuint16_t svshllt[_n_u16](svuint8_t op1, uint64_t imm2);
```

### Description

Shift left long (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Shift / Left / Vector shift left and widen

- SME attributes: Not specified by source.

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
  "imm2": {
    "minimum": 0,
    "maximum": 7
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
USHLLT Zresult.H, Zop1.B, #imm2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/USHLLT--Unsigned-shift-left-long-by-immediate--top--

### Operation

Source operation ID: `SveOperation_svshllt_n_u16`

**Operation**



Return a vector in which each element *i* contains:



```text
(uint16_t)op1[i * 2 + 1] << imm2
```

## svshllt[_n_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svshllt%5B_n_u32%5D

### Signature (source notation)

```c
svuint32_t svshllt[_n_u32](svuint16_t op1, uint64_t imm2);
```

### Description

Shift left long (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Shift / Left / Vector shift left and widen

- SME attributes: Not specified by source.

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
  "imm2": {
    "minimum": 0,
    "maximum": 15
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
USHLLT Zresult.S, Zop1.H, #imm2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/USHLLT--Unsigned-shift-left-long-by-immediate--top--

### Operation

Source operation ID: `SveOperation_svshllt_n_u32`

**Operation**



Return a vector in which each element *i* contains:



```text
(uint32_t)op1[i * 2 + 1] << imm2
```

## svshllt[_n_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svshllt%5B_n_u64%5D

### Signature (source notation)

```c
svuint64_t svshllt[_n_u64](svuint32_t op1, uint64_t imm2);
```

### Description

Shift left long (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Shift / Left / Vector shift left and widen

- SME attributes: Not specified by source.

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
  "imm2": {
    "minimum": 0,
    "maximum": 31
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
USHLLT Zresult.D, Zop1.S, #imm2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/USHLLT--Unsigned-shift-left-long-by-immediate--top--

### Operation

Source operation ID: `SveOperation_svshllt_n_u64`

**Operation**



Return a vector in which each element *i* contains:



```text
(uint64_t)op1[i * 2 + 1] << imm2
```

