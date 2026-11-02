# SME / Vector arithmetic / Absolute / Absolute difference and accumulate — Part 1

## svaba[_n_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svaba%5B_n_s16%5D

### Signature (source notation)

```c
svint16_t svaba[_n_s16](svint16_t op1, svint16_t op2, int16_t op3);
```

### Description

Absolute difference and accumulate

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Absolute / Absolute difference and accumulate

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
    "Zresult.H|Ztied1.H": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
SABA Ztied1.H, Zop2.H, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SABA--Signed-absolute-difference-and-accumulate-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SABA Zresult.H, Zop2.H, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SABA--Signed-absolute-difference-and-accumulate-

### Operation

Source operation ID: `SveOperation_svaba_n_s8`

**Operation**



Return a vector in which element *i* contains `op1[i]` plus the absolute difference between `op2[i]` and `op3`.



The absolute difference is logically an unsigned value, but it is reinterpreted as a signed value instead.  For example, the absolute difference between the minimum and maximum values is reinterpreted as -1.



The operation uses modulo arithmetic.  The behavior is therefore defined for all inputs; unlike C, there is no undefined behavior for signed overflow.

## svaba[_n_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svaba%5B_n_s32%5D

### Signature (source notation)

```c
svint32_t svaba[_n_s32](svint32_t op1, svint32_t op2, int32_t op3);
```

### Description

Absolute difference and accumulate

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Absolute / Absolute difference and accumulate

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
    "Zresult.S|Ztied1.S": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
SABA Ztied1.S, Zop2.S, Zop3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SABA--Signed-absolute-difference-and-accumulate-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SABA Zresult.S, Zop2.S, Zop3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SABA--Signed-absolute-difference-and-accumulate-

### Operation

Source operation ID: `SveOperation_svaba_n_s8`

**Operation**



Return a vector in which element *i* contains `op1[i]` plus the absolute difference between `op2[i]` and `op3`.



The absolute difference is logically an unsigned value, but it is reinterpreted as a signed value instead.  For example, the absolute difference between the minimum and maximum values is reinterpreted as -1.



The operation uses modulo arithmetic.  The behavior is therefore defined for all inputs; unlike C, there is no undefined behavior for signed overflow.

## svaba[_n_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svaba%5B_n_s64%5D

### Signature (source notation)

```c
svint64_t svaba[_n_s64](svint64_t op1, svint64_t op2, int64_t op3);
```

### Description

Absolute difference and accumulate

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Absolute / Absolute difference and accumulate

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
    "register": "Zop2.D"
  },
  "op3": {
    "register": "Zop3.D[*]"
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
SABA Ztied1.D, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SABA--Signed-absolute-difference-and-accumulate-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SABA Zresult.D, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SABA--Signed-absolute-difference-and-accumulate-

### Operation

Source operation ID: `SveOperation_svaba_n_s8`

**Operation**



Return a vector in which element *i* contains `op1[i]` plus the absolute difference between `op2[i]` and `op3`.



The absolute difference is logically an unsigned value, but it is reinterpreted as a signed value instead.  For example, the absolute difference between the minimum and maximum values is reinterpreted as -1.



The operation uses modulo arithmetic.  The behavior is therefore defined for all inputs; unlike C, there is no undefined behavior for signed overflow.

## svaba[_n_s8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svaba%5B_n_s8%5D

### Signature (source notation)

```c
svint8_t svaba[_n_s8](svint8_t op1, svint8_t op2, int8_t op3);
```

### Description

Absolute difference and accumulate

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Absolute / Absolute difference and accumulate

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
    "register": "Zop1.B|Ztied1.B"
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
    "Zresult.B|Ztied1.B": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
SABA Ztied1.B, Zop2.B, Zop3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SABA--Signed-absolute-difference-and-accumulate-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SABA Zresult.B, Zop2.B, Zop3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SABA--Signed-absolute-difference-and-accumulate-

### Operation

Source operation ID: `SveOperation_svaba_n_s8`

**Operation**



Return a vector in which element *i* contains `op1[i]` plus the absolute difference between `op2[i]` and `op3`.



The absolute difference is logically an unsigned value, but it is reinterpreted as a signed value instead.  For example, the absolute difference between the minimum and maximum values is reinterpreted as -1.



The operation uses modulo arithmetic.  The behavior is therefore defined for all inputs; unlike C, there is no undefined behavior for signed overflow.

## svaba[_n_u16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svaba%5B_n_u16%5D

### Signature (source notation)

```c
svuint16_t svaba[_n_u16](svuint16_t op1, svuint16_t op2, uint16_t op3);
```

### Description

Absolute difference and accumulate

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Absolute / Absolute difference and accumulate

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
    "register": "Zop1.H|Ztied1.H"
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
    "Zresult.H|Ztied1.H": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
UABA Ztied1.H, Zop2.H, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UABA--Unsigned-absolute-difference-and-accumulate-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
UABA Zresult.H, Zop2.H, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UABA--Unsigned-absolute-difference-and-accumulate-

### Operation

Source operation ID: `SveOperation_svaba_n_u8`

**Operation**



Return a vector in which element *i* contains `op1[i]` plus the absolute difference between `op2[i]` and `op3`.

## svaba[_n_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svaba%5B_n_u32%5D

### Signature (source notation)

```c
svuint32_t svaba[_n_u32](svuint32_t op1, svuint32_t op2, uint32_t op3);
```

### Description

Absolute difference and accumulate

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Absolute / Absolute difference and accumulate

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
    "register": "Zop1.S|Ztied1.S"
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
    "Zresult.S|Ztied1.S": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
UABA Ztied1.S, Zop2.S, Zop3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UABA--Unsigned-absolute-difference-and-accumulate-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
UABA Zresult.S, Zop2.S, Zop3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UABA--Unsigned-absolute-difference-and-accumulate-

### Operation

Source operation ID: `SveOperation_svaba_n_u8`

**Operation**



Return a vector in which element *i* contains `op1[i]` plus the absolute difference between `op2[i]` and `op3`.

## svaba[_n_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svaba%5B_n_u64%5D

### Signature (source notation)

```c
svuint64_t svaba[_n_u64](svuint64_t op1, svuint64_t op2, uint64_t op3);
```

### Description

Absolute difference and accumulate

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Absolute / Absolute difference and accumulate

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
    "register": "Zop1.D|Ztied1.D"
  },
  "op2": {
    "register": "Zop2.D"
  },
  "op3": {
    "register": "Zop3.D[*]"
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
UABA Ztied1.D, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UABA--Unsigned-absolute-difference-and-accumulate-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
UABA Zresult.D, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UABA--Unsigned-absolute-difference-and-accumulate-

### Operation

Source operation ID: `SveOperation_svaba_n_u8`

**Operation**



Return a vector in which element *i* contains `op1[i]` plus the absolute difference between `op2[i]` and `op3`.

## svaba[_n_u8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svaba%5B_n_u8%5D

### Signature (source notation)

```c
svuint8_t svaba[_n_u8](svuint8_t op1, svuint8_t op2, uint8_t op3);
```

### Description

Absolute difference and accumulate

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Absolute / Absolute difference and accumulate

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
    "register": "Zop1.B|Ztied1.B"
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
    "Zresult.B|Ztied1.B": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
UABA Ztied1.B, Zop2.B, Zop3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UABA--Unsigned-absolute-difference-and-accumulate-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
UABA Zresult.B, Zop2.B, Zop3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UABA--Unsigned-absolute-difference-and-accumulate-

### Operation

Source operation ID: `SveOperation_svaba_n_u8`

**Operation**



Return a vector in which element *i* contains `op1[i]` plus the absolute difference between `op2[i]` and `op3`.

## svaba[_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svaba%5B_s16%5D

### Signature (source notation)

```c
svint16_t svaba[_s16](svint16_t op1, svint16_t op2, svint16_t op3);
```

### Description

Absolute difference and accumulate

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Absolute / Absolute difference and accumulate

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
    "Zresult.H|Ztied1.H": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
SABA Ztied1.H, Zop2.H, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SABA--Signed-absolute-difference-and-accumulate-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SABA Zresult.H, Zop2.H, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SABA--Signed-absolute-difference-and-accumulate-

### Operation

Source operation ID: `SveOperation_svaba_s8`

**Operation**



Return a vector in which element *i* contains `op1[i]` plus the absolute difference between `op2[i]` and `op3[i]`.



The absolute difference is logically an unsigned value, but it is reinterpreted as a signed value instead.  For example, the absolute difference between the minimum and maximum values is reinterpreted as -1.



The operation uses modulo arithmetic.  The behavior is therefore defined for all inputs; unlike C, there is no undefined behavior for signed overflow.

## svaba[_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svaba%5B_s32%5D

### Signature (source notation)

```c
svint32_t svaba[_s32](svint32_t op1, svint32_t op2, svint32_t op3);
```

### Description

Absolute difference and accumulate

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Absolute / Absolute difference and accumulate

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
    "Zresult.S|Ztied1.S": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
SABA Ztied1.S, Zop2.S, Zop3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SABA--Signed-absolute-difference-and-accumulate-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SABA Zresult.S, Zop2.S, Zop3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SABA--Signed-absolute-difference-and-accumulate-

### Operation

Source operation ID: `SveOperation_svaba_s8`

**Operation**



Return a vector in which element *i* contains `op1[i]` plus the absolute difference between `op2[i]` and `op3[i]`.



The absolute difference is logically an unsigned value, but it is reinterpreted as a signed value instead.  For example, the absolute difference between the minimum and maximum values is reinterpreted as -1.



The operation uses modulo arithmetic.  The behavior is therefore defined for all inputs; unlike C, there is no undefined behavior for signed overflow.

## svaba[_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svaba%5B_s64%5D

### Signature (source notation)

```c
svint64_t svaba[_s64](svint64_t op1, svint64_t op2, svint64_t op3);
```

### Description

Absolute difference and accumulate

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Absolute / Absolute difference and accumulate

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
    "register": "Zop2.D"
  },
  "op3": {
    "register": "Zop3.D"
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
SABA Ztied1.D, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SABA--Signed-absolute-difference-and-accumulate-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SABA Zresult.D, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SABA--Signed-absolute-difference-and-accumulate-

### Operation

Source operation ID: `SveOperation_svaba_s8`

**Operation**



Return a vector in which element *i* contains `op1[i]` plus the absolute difference between `op2[i]` and `op3[i]`.



The absolute difference is logically an unsigned value, but it is reinterpreted as a signed value instead.  For example, the absolute difference between the minimum and maximum values is reinterpreted as -1.



The operation uses modulo arithmetic.  The behavior is therefore defined for all inputs; unlike C, there is no undefined behavior for signed overflow.

## svaba[_s8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svaba%5B_s8%5D

### Signature (source notation)

```c
svint8_t svaba[_s8](svint8_t op1, svint8_t op2, svint8_t op3);
```

### Description

Absolute difference and accumulate

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Absolute / Absolute difference and accumulate

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
    "register": "Zop1.B|Ztied1.B"
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
    "Zresult.B|Ztied1.B": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
SABA Ztied1.B, Zop2.B, Zop3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SABA--Signed-absolute-difference-and-accumulate-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SABA Zresult.B, Zop2.B, Zop3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SABA--Signed-absolute-difference-and-accumulate-

### Operation

Source operation ID: `SveOperation_svaba_s8`

**Operation**



Return a vector in which element *i* contains `op1[i]` plus the absolute difference between `op2[i]` and `op3[i]`.



The absolute difference is logically an unsigned value, but it is reinterpreted as a signed value instead.  For example, the absolute difference between the minimum and maximum values is reinterpreted as -1.



The operation uses modulo arithmetic.  The behavior is therefore defined for all inputs; unlike C, there is no undefined behavior for signed overflow.

## svaba[_u16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svaba%5B_u16%5D

### Signature (source notation)

```c
svuint16_t svaba[_u16](svuint16_t op1, svuint16_t op2, svuint16_t op3);
```

### Description

Absolute difference and accumulate

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Absolute / Absolute difference and accumulate

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
    "register": "Zop1.H|Ztied1.H"
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
    "Zresult.H|Ztied1.H": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
UABA Ztied1.H, Zop2.H, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UABA--Unsigned-absolute-difference-and-accumulate-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
UABA Zresult.H, Zop2.H, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UABA--Unsigned-absolute-difference-and-accumulate-

### Operation

Source operation ID: `SveOperation_svaba_u8`

**Operation**



Return a vector in which element *i* contains `op1[i]` plus the absolute difference between `op2[i]` and `op3[i]`.

## svaba[_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svaba%5B_u32%5D

### Signature (source notation)

```c
svuint32_t svaba[_u32](svuint32_t op1, svuint32_t op2, svuint32_t op3);
```

### Description

Absolute difference and accumulate

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Absolute / Absolute difference and accumulate

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
    "register": "Zop1.S|Ztied1.S"
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
    "Zresult.S|Ztied1.S": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
UABA Ztied1.S, Zop2.S, Zop3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UABA--Unsigned-absolute-difference-and-accumulate-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
UABA Zresult.S, Zop2.S, Zop3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UABA--Unsigned-absolute-difference-and-accumulate-

### Operation

Source operation ID: `SveOperation_svaba_u8`

**Operation**



Return a vector in which element *i* contains `op1[i]` plus the absolute difference between `op2[i]` and `op3[i]`.

## svaba[_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svaba%5B_u64%5D

### Signature (source notation)

```c
svuint64_t svaba[_u64](svuint64_t op1, svuint64_t op2, svuint64_t op3);
```

### Description

Absolute difference and accumulate

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Absolute / Absolute difference and accumulate

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
    "register": "Zop1.D|Ztied1.D"
  },
  "op2": {
    "register": "Zop2.D"
  },
  "op3": {
    "register": "Zop3.D"
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
UABA Ztied1.D, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UABA--Unsigned-absolute-difference-and-accumulate-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
UABA Zresult.D, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UABA--Unsigned-absolute-difference-and-accumulate-

### Operation

Source operation ID: `SveOperation_svaba_u8`

**Operation**



Return a vector in which element *i* contains `op1[i]` plus the absolute difference between `op2[i]` and `op3[i]`.

## svaba[_u8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svaba%5B_u8%5D

### Signature (source notation)

```c
svuint8_t svaba[_u8](svuint8_t op1, svuint8_t op2, svuint8_t op3);
```

### Description

Absolute difference and accumulate

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Absolute / Absolute difference and accumulate

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
    "register": "Zop1.B|Ztied1.B"
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
    "Zresult.B|Ztied1.B": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
UABA Ztied1.B, Zop2.B, Zop3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UABA--Unsigned-absolute-difference-and-accumulate-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
UABA Zresult.B, Zop2.B, Zop3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UABA--Unsigned-absolute-difference-and-accumulate-

### Operation

Source operation ID: `SveOperation_svaba_u8`

**Operation**



Return a vector in which element *i* contains `op1[i]` plus the absolute difference between `op2[i]` and `op3[i]`.

