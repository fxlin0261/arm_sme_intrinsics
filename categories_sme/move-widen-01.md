# SME / Move / Widen — Part 1

## svmovlb[_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmovlb%5B_s16%5D

### Signature (source notation)

```c
svint16_t svmovlb[_s16](svint8_t op);
```

### Description

Move long (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Move / Widen

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
  "op": {
    "register": "Zop.B"
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
SSHLLB Zresult.H, Zop.B, #0
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SSHLLB--Signed-shift-left-long-by-immediate--bottom--

### Operation

Source operation ID: `SveOperation_svmovlb_s16`

**Operation**



Return a vector in which each element *i* contains `(int16_t)op[i * 2]`.

## svmovlb[_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmovlb%5B_s32%5D

### Signature (source notation)

```c
svint32_t svmovlb[_s32](svint16_t op);
```

### Description

Move long (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Move / Widen

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
  "op": {
    "register": "Zop.H"
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
SSHLLB Zresult.S, Zop.H, #0
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SSHLLB--Signed-shift-left-long-by-immediate--bottom--

### Operation

Source operation ID: `SveOperation_svmovlb_s32`

**Operation**



Return a vector in which each element *i* contains `(int32_t)op[i * 2]`.

## svmovlb[_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmovlb%5B_s64%5D

### Signature (source notation)

```c
svint64_t svmovlb[_s64](svint32_t op);
```

### Description

Move long (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Move / Widen

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
  "op": {
    "register": "Zop.S"
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
SSHLLB Zresult.D, Zop.S, #0
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SSHLLB--Signed-shift-left-long-by-immediate--bottom--

### Operation

Source operation ID: `SveOperation_svmovlb_s64`

**Operation**



Return a vector in which each element *i* contains `(int64_t)op[i * 2]`.

## svmovlb[_u16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmovlb%5B_u16%5D

### Signature (source notation)

```c
svuint16_t svmovlb[_u16](svuint8_t op);
```

### Description

Move long (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Move / Widen

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
  "op": {
    "register": "Zop.B"
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
USHLLB Zresult.H, Zop.B, #0
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/USHLLB--Unsigned-shift-left-long-by-immediate--bottom--

### Operation

Source operation ID: `SveOperation_svmovlb_u16`

**Operation**



Return a vector in which each element *i* contains `(uint16_t)op[i * 2]`.

## svmovlb[_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmovlb%5B_u32%5D

### Signature (source notation)

```c
svuint32_t svmovlb[_u32](svuint16_t op);
```

### Description

Move long (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Move / Widen

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
  "op": {
    "register": "Zop.H"
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
USHLLB Zresult.S, Zop.H, #0
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/USHLLB--Unsigned-shift-left-long-by-immediate--bottom--

### Operation

Source operation ID: `SveOperation_svmovlb_u32`

**Operation**



Return a vector in which each element *i* contains `(uint32_t)op[i * 2]`.

## svmovlb[_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmovlb%5B_u64%5D

### Signature (source notation)

```c
svuint64_t svmovlb[_u64](svuint32_t op);
```

### Description

Move long (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Move / Widen

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
  "op": {
    "register": "Zop.S"
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
USHLLB Zresult.D, Zop.S, #0
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/USHLLB--Unsigned-shift-left-long-by-immediate--bottom--

### Operation

Source operation ID: `SveOperation_svmovlb_u64`

**Operation**



Return a vector in which each element *i* contains `(uint64_t)op[i * 2]`.

## svmovlt[_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmovlt%5B_s16%5D

### Signature (source notation)

```c
svint16_t svmovlt[_s16](svint8_t op);
```

### Description

Move long (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Move / Widen

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
  "op": {
    "register": "Zop.B"
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
SSHLLT Zresult.H, Zop.B, #0
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SSHLLT--Signed-shift-left-long-by-immediate--top--

### Operation

Source operation ID: `SveOperation_svmovlt_s16`

**Operation**



Return a vector in which each element *i* contains `(int16_t)op[i * 2 + 1]`.

## svmovlt[_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmovlt%5B_s32%5D

### Signature (source notation)

```c
svint32_t svmovlt[_s32](svint16_t op);
```

### Description

Move long (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Move / Widen

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
  "op": {
    "register": "Zop.H"
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
SSHLLT Zresult.S, Zop.H, #0
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SSHLLT--Signed-shift-left-long-by-immediate--top--

### Operation

Source operation ID: `SveOperation_svmovlt_s32`

**Operation**



Return a vector in which each element *i* contains `(int32_t)op[i * 2 + 1]`.

## svmovlt[_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmovlt%5B_s64%5D

### Signature (source notation)

```c
svint64_t svmovlt[_s64](svint32_t op);
```

### Description

Move long (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Move / Widen

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
  "op": {
    "register": "Zop.S"
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
SSHLLT Zresult.D, Zop.S, #0
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SSHLLT--Signed-shift-left-long-by-immediate--top--

### Operation

Source operation ID: `SveOperation_svmovlt_s64`

**Operation**



Return a vector in which each element *i* contains `(int64_t)op[i * 2 + 1]`.

## svmovlt[_u16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmovlt%5B_u16%5D

### Signature (source notation)

```c
svuint16_t svmovlt[_u16](svuint8_t op);
```

### Description

Move long (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Move / Widen

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
  "op": {
    "register": "Zop.B"
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
USHLLT Zresult.H, Zop.B, #0
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/USHLLT--Unsigned-shift-left-long-by-immediate--top--

### Operation

Source operation ID: `SveOperation_svmovlt_u16`

**Operation**



Return a vector in which each element *i* contains `(uint16_t)op[i * 2 + 1]`.

## svmovlt[_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmovlt%5B_u32%5D

### Signature (source notation)

```c
svuint32_t svmovlt[_u32](svuint16_t op);
```

### Description

Move long (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Move / Widen

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
  "op": {
    "register": "Zop.H"
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
USHLLT Zresult.S, Zop.H, #0
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/USHLLT--Unsigned-shift-left-long-by-immediate--top--

### Operation

Source operation ID: `SveOperation_svmovlt_u32`

**Operation**



Return a vector in which each element *i* contains `(uint32_t)op[i * 2 + 1]`.

## svmovlt[_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmovlt%5B_u64%5D

### Signature (source notation)

```c
svuint64_t svmovlt[_u64](svuint32_t op);
```

### Description

Move long (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Move / Widen

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
  "op": {
    "register": "Zop.S"
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
USHLLT Zresult.D, Zop.S, #0
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/USHLLT--Unsigned-shift-left-long-by-immediate--top--

### Operation

Source operation ID: `SveOperation_svmovlt_u64`

**Operation**



Return a vector in which each element *i* contains `(uint64_t)op[i * 2 + 1]`.

## svunpkhi[_b]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svunpkhi%5B_b%5D

### Signature (source notation)

```c
svbool_t svunpkhi[_b](svbool_t op);
```

### Description

Unpack and extend high half

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Move / Widen

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
  "return_base_type": "bool",
  "element_bit_size": "16",
  "value": "svbool_t"
}
```

### Argument preparation and constraints

```json
{
  "op": {
    "register": "Pop.B"
  }
}
```

### Result mapping

```json
[
  {
    "Presult.H": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
PUNPKHI Presult.H, Pop.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/PUNPKHI--PUNPKLO--Unpack-and-widen-half-of-predicate-

### Operation

Source operation ID: `SveOperation_svunpkhi_u16`

**Operation**



Extract the highest-indexed half of `op` and zero-extend each element to double the width.

## svunpkhi[_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svunpkhi%5B_s16%5D

### Signature (source notation)

```c
svint16_t svunpkhi[_s16](svint8_t op);
```

### Description

Unpack and extend high half

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Move / Widen

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
  "op": {
    "register": "Zop.B"
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
SUNPKHI Zresult.H, Zop.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SUNPKHI--SUNPKLO--Signed-unpack-and-extend-half-of-vector-

### Operation

Source operation ID: `SveOperation_svunpkhi_s16`

**Operation**



Extract the highest-indexed half of `op` and sign-extend each element to double the width.

## svunpkhi[_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svunpkhi%5B_s32%5D

### Signature (source notation)

```c
svint32_t svunpkhi[_s32](svint16_t op);
```

### Description

Unpack and extend high half

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Move / Widen

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
  "op": {
    "register": "Zop.H"
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
SUNPKHI Zresult.S, Zop.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SUNPKHI--SUNPKLO--Signed-unpack-and-extend-half-of-vector-

### Operation

Source operation ID: `SveOperation_svunpkhi_s16`

**Operation**



Extract the highest-indexed half of `op` and sign-extend each element to double the width.

## svunpkhi[_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svunpkhi%5B_s64%5D

### Signature (source notation)

```c
svint64_t svunpkhi[_s64](svint32_t op);
```

### Description

Unpack and extend high half

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Move / Widen

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
  "op": {
    "register": "Zop.S"
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
SUNPKHI Zresult.D, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SUNPKHI--SUNPKLO--Signed-unpack-and-extend-half-of-vector-

### Operation

Source operation ID: `SveOperation_svunpkhi_s16`

**Operation**



Extract the highest-indexed half of `op` and sign-extend each element to double the width.

## svunpkhi[_u16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svunpkhi%5B_u16%5D

### Signature (source notation)

```c
svuint16_t svunpkhi[_u16](svuint8_t op);
```

### Description

Unpack and extend high half

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Move / Widen

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
  "op": {
    "register": "Zop.B"
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
UUNPKHI Zresult.H, Zop.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UUNPKHI--UUNPKLO--Unsigned-unpack-and-extend-half-of-vector-

### Operation

Source operation ID: `SveOperation_svunpkhi_u16`

**Operation**



Extract the highest-indexed half of `op` and zero-extend each element to double the width.

## svunpkhi[_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svunpkhi%5B_u32%5D

### Signature (source notation)

```c
svuint32_t svunpkhi[_u32](svuint16_t op);
```

### Description

Unpack and extend high half

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Move / Widen

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
  "op": {
    "register": "Zop.H"
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
UUNPKHI Zresult.S, Zop.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UUNPKHI--UUNPKLO--Unsigned-unpack-and-extend-half-of-vector-

### Operation

Source operation ID: `SveOperation_svunpkhi_u16`

**Operation**



Extract the highest-indexed half of `op` and zero-extend each element to double the width.

## svunpkhi[_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svunpkhi%5B_u64%5D

### Signature (source notation)

```c
svuint64_t svunpkhi[_u64](svuint32_t op);
```

### Description

Unpack and extend high half

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Move / Widen

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
  "op": {
    "register": "Zop.S"
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
UUNPKHI Zresult.D, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UUNPKHI--UUNPKLO--Unsigned-unpack-and-extend-half-of-vector-

### Operation

Source operation ID: `SveOperation_svunpkhi_u16`

**Operation**



Extract the highest-indexed half of `op` and zero-extend each element to double the width.

## svunpklo[_b]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svunpklo%5B_b%5D

### Signature (source notation)

```c
svbool_t svunpklo[_b](svbool_t op);
```

### Description

Unpack and extend low half

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Move / Widen

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
  "return_base_type": "bool",
  "element_bit_size": "16",
  "value": "svbool_t"
}
```

### Argument preparation and constraints

```json
{
  "op": {
    "register": "Pop.B"
  }
}
```

### Result mapping

```json
[
  {
    "Presult.H": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
PUNPKLO Presult.H, Pop.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/PUNPKHI--PUNPKLO--Unpack-and-widen-half-of-predicate-

### Operation

Source operation ID: `SveOperation_svunpklo_u16`

**Operation**



Extract the lowest-indexed half of `op` and zero-extend each element to double the width.

## svunpklo[_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svunpklo%5B_s16%5D

### Signature (source notation)

```c
svint16_t svunpklo[_s16](svint8_t op);
```

### Description

Unpack and extend low half

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Move / Widen

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
  "op": {
    "register": "Zop.B"
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
SUNPKLO Zresult.H, Zop.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SUNPKHI--SUNPKLO--Signed-unpack-and-extend-half-of-vector-

### Operation

Source operation ID: `SveOperation_svunpklo_s16`

**Operation**



Extract the lowest-indexed half of `op` and sign-extend each element to double the width.

## svunpklo[_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svunpklo%5B_s32%5D

### Signature (source notation)

```c
svint32_t svunpklo[_s32](svint16_t op);
```

### Description

Unpack and extend low half

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Move / Widen

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
  "op": {
    "register": "Zop.H"
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
SUNPKLO Zresult.S, Zop.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SUNPKHI--SUNPKLO--Signed-unpack-and-extend-half-of-vector-

### Operation

Source operation ID: `SveOperation_svunpklo_s16`

**Operation**



Extract the lowest-indexed half of `op` and sign-extend each element to double the width.

## svunpklo[_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svunpklo%5B_s64%5D

### Signature (source notation)

```c
svint64_t svunpklo[_s64](svint32_t op);
```

### Description

Unpack and extend low half

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Move / Widen

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
  "op": {
    "register": "Zop.S"
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
SUNPKLO Zresult.D, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SUNPKHI--SUNPKLO--Signed-unpack-and-extend-half-of-vector-

### Operation

Source operation ID: `SveOperation_svunpklo_s16`

**Operation**



Extract the lowest-indexed half of `op` and sign-extend each element to double the width.

## svunpklo[_u16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svunpklo%5B_u16%5D

### Signature (source notation)

```c
svuint16_t svunpklo[_u16](svuint8_t op);
```

### Description

Unpack and extend low half

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Move / Widen

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
  "op": {
    "register": "Zop.B"
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
UUNPKLO Zresult.H, Zop.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UUNPKHI--UUNPKLO--Unsigned-unpack-and-extend-half-of-vector-

### Operation

Source operation ID: `SveOperation_svunpklo_u16`

**Operation**



Extract the lowest-indexed half of `op` and zero-extend each element to double the width.

## svunpklo[_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svunpklo%5B_u32%5D

### Signature (source notation)

```c
svuint32_t svunpklo[_u32](svuint16_t op);
```

### Description

Unpack and extend low half

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Move / Widen

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
  "op": {
    "register": "Zop.H"
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
UUNPKLO Zresult.S, Zop.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UUNPKHI--UUNPKLO--Unsigned-unpack-and-extend-half-of-vector-

### Operation

Source operation ID: `SveOperation_svunpklo_u16`

**Operation**



Extract the lowest-indexed half of `op` and zero-extend each element to double the width.

## svunpklo[_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svunpklo%5B_u64%5D

### Signature (source notation)

```c
svuint64_t svunpklo[_u64](svuint32_t op);
```

### Description

Unpack and extend low half

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Move / Widen

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
  "op": {
    "register": "Zop.S"
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
UUNPKLO Zresult.D, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UUNPKHI--UUNPKLO--Unsigned-unpack-and-extend-half-of-vector-

### Operation

Source operation ID: `SveOperation_svunpklo_u16`

**Operation**



Extract the lowest-indexed half of `op` and zero-extend each element to double the width.

