# SME / Vector manipulation / Reverse elements — Part 1

## svrev[_bf16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrev%5B_bf16%5D

### Signature (source notation)

```c
svbfloat16_t svrev[_bf16](svbfloat16_t op);
```

### Description

Reverse all elements

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Reverse elements

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
  "return_base_type": "bfloat",
  "element_bit_size": "16",
  "value": "svbfloat16_t"
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
    "Zresult.H": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
REV Zresult.H, Zop.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/REV--vector---Reverse-all-elements-in-a-vector--unpredicated--

### Operation

Source operation ID: `SveOperation_svrev_bf16`

**Operation**



Reverse the order of `op`'s elements and return the result.  The first element of the returned vector is therefore the last element of `op`, and so on.

## svrev[_f16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrev%5B_f16%5D

### Signature (source notation)

```c
svfloat16_t svrev[_f16](svfloat16_t op);
```

### Description

Reverse all elements

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Reverse elements

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
  "return_base_type": "float",
  "element_bit_size": "16",
  "value": "svfloat16_t"
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
    "Zresult.H": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
REV Zresult.H, Zop.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/REV--vector---Reverse-all-elements-in-a-vector--unpredicated--

### Operation

Source operation ID: `SveOperation_svrev_bf16`

**Operation**



Reverse the order of `op`'s elements and return the result.  The first element of the returned vector is therefore the last element of `op`, and so on.

## svrev[_f32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrev%5B_f32%5D

### Signature (source notation)

```c
svfloat32_t svrev[_f32](svfloat32_t op);
```

### Description

Reverse all elements

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Reverse elements

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
  "return_base_type": "float",
  "element_bit_size": "32",
  "value": "svfloat32_t"
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
    "Zresult.S": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
REV Zresult.S, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/REV--vector---Reverse-all-elements-in-a-vector--unpredicated--

### Operation

Source operation ID: `SveOperation_svrev_bf16`

**Operation**



Reverse the order of `op`'s elements and return the result.  The first element of the returned vector is therefore the last element of `op`, and so on.

## svrev[_f64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrev%5B_f64%5D

### Signature (source notation)

```c
svfloat64_t svrev[_f64](svfloat64_t op);
```

### Description

Reverse all elements

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Reverse elements

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
  "return_base_type": "float",
  "element_bit_size": "64",
  "value": "svfloat64_t"
}
```

### Argument preparation and constraints

```json
{
  "op": {
    "register": "Zop.D"
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
REV Zresult.D, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/REV--vector---Reverse-all-elements-in-a-vector--unpredicated--

### Operation

Source operation ID: `SveOperation_svrev_bf16`

**Operation**



Reverse the order of `op`'s elements and return the result.  The first element of the returned vector is therefore the last element of `op`, and so on.

## svrev[_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrev%5B_s16%5D

### Signature (source notation)

```c
svint16_t svrev[_s16](svint16_t op);
```

### Description

Reverse all elements

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Reverse elements

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
    "register": "Zop.H"
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
REV Zresult.H, Zop.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/REV--vector---Reverse-all-elements-in-a-vector--unpredicated--

### Operation

Source operation ID: `SveOperation_svrev_bf16`

**Operation**



Reverse the order of `op`'s elements and return the result.  The first element of the returned vector is therefore the last element of `op`, and so on.

## svrev[_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrev%5B_s32%5D

### Signature (source notation)

```c
svint32_t svrev[_s32](svint32_t op);
```

### Description

Reverse all elements

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Reverse elements

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
    "register": "Zop.S"
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
REV Zresult.S, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/REV--vector---Reverse-all-elements-in-a-vector--unpredicated--

### Operation

Source operation ID: `SveOperation_svrev_bf16`

**Operation**



Reverse the order of `op`'s elements and return the result.  The first element of the returned vector is therefore the last element of `op`, and so on.

## svrev[_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrev%5B_s64%5D

### Signature (source notation)

```c
svint64_t svrev[_s64](svint64_t op);
```

### Description

Reverse all elements

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Reverse elements

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
    "register": "Zop.D"
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
REV Zresult.D, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/REV--vector---Reverse-all-elements-in-a-vector--unpredicated--

### Operation

Source operation ID: `SveOperation_svrev_bf16`

**Operation**



Reverse the order of `op`'s elements and return the result.  The first element of the returned vector is therefore the last element of `op`, and so on.

## svrev[_s8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrev%5B_s8%5D

### Signature (source notation)

```c
svint8_t svrev[_s8](svint8_t op);
```

### Description

Reverse all elements

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Reverse elements

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
  "op": {
    "register": "Zop.B"
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
REV Zresult.B, Zop.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/REV--vector---Reverse-all-elements-in-a-vector--unpredicated--

### Operation

Source operation ID: `SveOperation_svrev_bf16`

**Operation**



Reverse the order of `op`'s elements and return the result.  The first element of the returned vector is therefore the last element of `op`, and so on.

## svrev[_u16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrev%5B_u16%5D

### Signature (source notation)

```c
svuint16_t svrev[_u16](svuint16_t op);
```

### Description

Reverse all elements

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Reverse elements

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
    "register": "Zop.H"
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
REV Zresult.H, Zop.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/REV--vector---Reverse-all-elements-in-a-vector--unpredicated--

### Operation

Source operation ID: `SveOperation_svrev_bf16`

**Operation**



Reverse the order of `op`'s elements and return the result.  The first element of the returned vector is therefore the last element of `op`, and so on.

## svrev[_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrev%5B_u32%5D

### Signature (source notation)

```c
svuint32_t svrev[_u32](svuint32_t op);
```

### Description

Reverse all elements

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Reverse elements

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
    "register": "Zop.S"
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
REV Zresult.S, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/REV--vector---Reverse-all-elements-in-a-vector--unpredicated--

### Operation

Source operation ID: `SveOperation_svrev_bf16`

**Operation**



Reverse the order of `op`'s elements and return the result.  The first element of the returned vector is therefore the last element of `op`, and so on.

## svrev[_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrev%5B_u64%5D

### Signature (source notation)

```c
svuint64_t svrev[_u64](svuint64_t op);
```

### Description

Reverse all elements

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Reverse elements

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
    "register": "Zop.D"
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
REV Zresult.D, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/REV--vector---Reverse-all-elements-in-a-vector--unpredicated--

### Operation

Source operation ID: `SveOperation_svrev_bf16`

**Operation**



Reverse the order of `op`'s elements and return the result.  The first element of the returned vector is therefore the last element of `op`, and so on.

## svrev[_u8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrev%5B_u8%5D

### Signature (source notation)

```c
svuint8_t svrev[_u8](svuint8_t op);
```

### Description

Reverse all elements

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Reverse elements

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
  "op": {
    "register": "Zop.B"
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
REV Zresult.B, Zop.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/REV--vector---Reverse-all-elements-in-a-vector--unpredicated--

### Operation

Source operation ID: `SveOperation_svrev_bf16`

**Operation**



Reverse the order of `op`'s elements and return the result.  The first element of the returned vector is therefore the last element of `op`, and so on.

## svrev_b16

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrev_b16

### Signature (source notation)

```c
svbool_t svrev_b16(svbool_t op);
```

### Description

Reverse all elements

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Reverse elements

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
    "register": "Pop.H"
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
REV Presult.H, Pop.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/REV--predicate---Reverse-all-elements-in-a-predicate-

### Operation

Source operation ID: `SveOperation_svrev_b8`

**Operation**



Reverse the order of `op`'s elements and return the result.  The first element of the returned predicate is therefore the last element of `op`, and so on.

## svrev_b32

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrev_b32

### Signature (source notation)

```c
svbool_t svrev_b32(svbool_t op);
```

### Description

Reverse all elements

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Reverse elements

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
  "element_bit_size": "32",
  "value": "svbool_t"
}
```

### Argument preparation and constraints

```json
{
  "op": {
    "register": "Pop.S"
  }
}
```

### Result mapping

```json
[
  {
    "Presult.S": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
REV Presult.S, Pop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/REV--predicate---Reverse-all-elements-in-a-predicate-

### Operation

Source operation ID: `SveOperation_svrev_b8`

**Operation**



Reverse the order of `op`'s elements and return the result.  The first element of the returned predicate is therefore the last element of `op`, and so on.

## svrev_b64

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrev_b64

### Signature (source notation)

```c
svbool_t svrev_b64(svbool_t op);
```

### Description

Reverse all elements

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Reverse elements

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
  "element_bit_size": "64",
  "value": "svbool_t"
}
```

### Argument preparation and constraints

```json
{
  "op": {
    "register": "Pop.D"
  }
}
```

### Result mapping

```json
[
  {
    "Presult.D": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
REV Presult.D, Pop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/REV--predicate---Reverse-all-elements-in-a-predicate-

### Operation

Source operation ID: `SveOperation_svrev_b8`

**Operation**



Reverse the order of `op`'s elements and return the result.  The first element of the returned predicate is therefore the last element of `op`, and so on.

## svrev_b8

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrev_b8

### Signature (source notation)

```c
svbool_t svrev_b8(svbool_t op);
```

### Description

Reverse all elements

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Reverse elements

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
  "element_bit_size": "8",
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
    "Presult.B": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
REV Presult.B, Pop.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/REV--predicate---Reverse-all-elements-in-a-predicate-

### Operation

Source operation ID: `SveOperation_svrev_b8`

**Operation**



Reverse the order of `op`'s elements and return the result.  The first element of the returned predicate is therefore the last element of `op`, and so on.

## svrevb[_s16]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrevb%5B_s16%5D_m

### Signature (source notation)

```c
svint16_t svrevb[_s16]_m(svint16_t inactive, svbool_t pg, svint16_t op);
```

### Description

Reverse bytes within elements

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Reverse elements

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
  "inactive": {
    "register": "Zinactive.H|Ztied.H"
  },
  "pg": {
    "register": "Pg"
  },
  "op": {
    "register": "Zop.H"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.H|Ztied.H": "result"
  }
]
```

### Instruction mapping

When result and inactive are in the same register, this intrinsic compiles to:

```asm
REVB Ztied.H, Pg/M, Zop.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/REVB--REVH--REVW--Reverse-bytes---halfwords---words-within-elements--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zinactive
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
REVB Zresult.H, Pg/M, Zop.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/REVB--REVH--REVW--Reverse-bytes---halfwords---words-within-elements--predicated--

### Operation

Source operation ID: `SveOperation_svrevb_s16_m`

**Operation**



Return a vector in which each active element *i* contains the result of reversing the order of the bytes in `op[i]`. Take the inactive elements of the result from the corresponding elements of `inactive`.

## svrevb[_s16]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrevb%5B_s16%5D_x

### Signature (source notation)

```c
svint16_t svrevb[_s16]_x(svbool_t pg, svint16_t op);
```

### Description

Reverse bytes within elements

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Reverse elements

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
  "pg": {
    "register": "Pg"
  },
  "op": {
    "register": "Zop.H|Ztied.H"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.H|Ztied.H": "result"
  }
]
```

### Instruction mapping

When result and op are in the same register, this intrinsic compiles to:

```asm
REVB Ztied.H, Pg/M, Ztied.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/REVB--REVH--REVW--Reverse-bytes---halfwords---words-within-elements--predicated--

When result and op are in different registers, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
REVB Zresult.H, Pg/M, Zop.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/REVB--REVH--REVW--Reverse-bytes---halfwords---words-within-elements--predicated--

### Operation

Source operation ID: `SveOperation_svrevb_s16_x`

**Operation**



Return a vector in which each active element *i* contains the result of reversing the order of the bytes in `op[i]`. The inactive elements of the result have arbitrary, undefined values.

## svrevb[_s16]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrevb%5B_s16%5D_z

### Signature (source notation)

```c
svint16_t svrevb[_s16]_z(svbool_t pg, svint16_t op);
```

### Description

Reverse bytes within elements

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Reverse elements

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
  "pg": {
    "register": "Pg"
  },
  "op": {
    "register": "Zop.H"
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

This intrinsic compiles to the following instructions, or functionally equivalent instructions:

```asm
MOVPRFX Zresult.H, Pg/Z, Zop.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
REVB Zresult.H, Pg/M, Zop.H  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/REVB--REVH--REVW--Reverse-bytes---halfwords---words-within-elements--predicated--

### Operation

Source operation ID: `SveOperation_svrevb_s16_z`

**Operation**



Return a vector in which each active element *i* contains the result of reversing the order of the bytes in `op[i]`. Set the inactive elements of the result to zero.



**[1]** Note that `result` must be in a different register from `op`

## svrevb[_s32]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrevb%5B_s32%5D_m

### Signature (source notation)

```c
svint32_t svrevb[_s32]_m(svint32_t inactive, svbool_t pg, svint32_t op);
```

### Description

Reverse bytes within elements

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Reverse elements

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
  "inactive": {
    "register": "Zinactive.S|Ztied.S"
  },
  "pg": {
    "register": "Pg"
  },
  "op": {
    "register": "Zop.S"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.S|Ztied.S": "result"
  }
]
```

### Instruction mapping

When result and inactive are in the same register, this intrinsic compiles to:

```asm
REVB Ztied.S, Pg/M, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/REVB--REVH--REVW--Reverse-bytes---halfwords---words-within-elements--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zinactive
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
REVB Zresult.S, Pg/M, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/REVB--REVH--REVW--Reverse-bytes---halfwords---words-within-elements--predicated--

### Operation

Source operation ID: `SveOperation_svrevb_s16_m`

**Operation**



Return a vector in which each active element *i* contains the result of reversing the order of the bytes in `op[i]`. Take the inactive elements of the result from the corresponding elements of `inactive`.

## svrevb[_s32]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrevb%5B_s32%5D_x

### Signature (source notation)

```c
svint32_t svrevb[_s32]_x(svbool_t pg, svint32_t op);
```

### Description

Reverse bytes within elements

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Reverse elements

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
  "pg": {
    "register": "Pg"
  },
  "op": {
    "register": "Zop.S|Ztied.S"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.S|Ztied.S": "result"
  }
]
```

### Instruction mapping

When result and op are in the same register, this intrinsic compiles to:

```asm
REVB Ztied.S, Pg/M, Ztied.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/REVB--REVH--REVW--Reverse-bytes---halfwords---words-within-elements--predicated--

When result and op are in different registers, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
REVB Zresult.S, Pg/M, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/REVB--REVH--REVW--Reverse-bytes---halfwords---words-within-elements--predicated--

### Operation

Source operation ID: `SveOperation_svrevb_s16_x`

**Operation**



Return a vector in which each active element *i* contains the result of reversing the order of the bytes in `op[i]`. The inactive elements of the result have arbitrary, undefined values.

## svrevb[_s32]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrevb%5B_s32%5D_z

### Signature (source notation)

```c
svint32_t svrevb[_s32]_z(svbool_t pg, svint32_t op);
```

### Description

Reverse bytes within elements

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Reverse elements

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
  "pg": {
    "register": "Pg"
  },
  "op": {
    "register": "Zop.S"
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

This intrinsic compiles to the following instructions, or functionally equivalent instructions:

```asm
MOVPRFX Zresult.S, Pg/Z, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
REVB Zresult.S, Pg/M, Zop.S  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/REVB--REVH--REVW--Reverse-bytes---halfwords---words-within-elements--predicated--

### Operation

Source operation ID: `SveOperation_svrevb_s16_z`

**Operation**



Return a vector in which each active element *i* contains the result of reversing the order of the bytes in `op[i]`. Set the inactive elements of the result to zero.



**[1]** Note that `result` must be in a different register from `op`

## svrevb[_s64]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrevb%5B_s64%5D_m

### Signature (source notation)

```c
svint64_t svrevb[_s64]_m(svint64_t inactive, svbool_t pg, svint64_t op);
```

### Description

Reverse bytes within elements

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Reverse elements

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
  "inactive": {
    "register": "Zinactive.D|Ztied.D"
  },
  "pg": {
    "register": "Pg"
  },
  "op": {
    "register": "Zop.D"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.D|Ztied.D": "result"
  }
]
```

### Instruction mapping

When result and inactive are in the same register, this intrinsic compiles to:

```asm
REVB Ztied.D, Pg/M, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/REVB--REVH--REVW--Reverse-bytes---halfwords---words-within-elements--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zinactive
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
REVB Zresult.D, Pg/M, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/REVB--REVH--REVW--Reverse-bytes---halfwords---words-within-elements--predicated--

### Operation

Source operation ID: `SveOperation_svrevb_s16_m`

**Operation**



Return a vector in which each active element *i* contains the result of reversing the order of the bytes in `op[i]`. Take the inactive elements of the result from the corresponding elements of `inactive`.

## svrevb[_s64]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrevb%5B_s64%5D_x

### Signature (source notation)

```c
svint64_t svrevb[_s64]_x(svbool_t pg, svint64_t op);
```

### Description

Reverse bytes within elements

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Reverse elements

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
  "pg": {
    "register": "Pg"
  },
  "op": {
    "register": "Zop.D|Ztied.D"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.D|Ztied.D": "result"
  }
]
```

### Instruction mapping

When result and op are in the same register, this intrinsic compiles to:

```asm
REVB Ztied.D, Pg/M, Ztied.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/REVB--REVH--REVW--Reverse-bytes---halfwords---words-within-elements--predicated--

When result and op are in different registers, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
REVB Zresult.D, Pg/M, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/REVB--REVH--REVW--Reverse-bytes---halfwords---words-within-elements--predicated--

### Operation

Source operation ID: `SveOperation_svrevb_s16_x`

**Operation**



Return a vector in which each active element *i* contains the result of reversing the order of the bytes in `op[i]`. The inactive elements of the result have arbitrary, undefined values.

## svrevb[_s64]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrevb%5B_s64%5D_z

### Signature (source notation)

```c
svint64_t svrevb[_s64]_z(svbool_t pg, svint64_t op);
```

### Description

Reverse bytes within elements

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Reverse elements

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
  "pg": {
    "register": "Pg"
  },
  "op": {
    "register": "Zop.D"
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

This intrinsic compiles to the following instructions, or functionally equivalent instructions:

```asm
MOVPRFX Zresult.D, Pg/Z, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
REVB Zresult.D, Pg/M, Zop.D  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/REVB--REVH--REVW--Reverse-bytes---halfwords---words-within-elements--predicated--

### Operation

Source operation ID: `SveOperation_svrevb_s16_z`

**Operation**



Return a vector in which each active element *i* contains the result of reversing the order of the bytes in `op[i]`. Set the inactive elements of the result to zero.



**[1]** Note that `result` must be in a different register from `op`

## svrevb[_u16]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrevb%5B_u16%5D_m

### Signature (source notation)

```c
svuint16_t svrevb[_u16]_m(svuint16_t inactive, svbool_t pg, svuint16_t op);
```

### Description

Reverse bytes within elements

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Reverse elements

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
  "inactive": {
    "register": "Zinactive.H|Ztied.H"
  },
  "pg": {
    "register": "Pg"
  },
  "op": {
    "register": "Zop.H"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.H|Ztied.H": "result"
  }
]
```

### Instruction mapping

When result and inactive are in the same register, this intrinsic compiles to:

```asm
REVB Ztied.H, Pg/M, Zop.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/REVB--REVH--REVW--Reverse-bytes---halfwords---words-within-elements--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zinactive
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
REVB Zresult.H, Pg/M, Zop.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/REVB--REVH--REVW--Reverse-bytes---halfwords---words-within-elements--predicated--

### Operation

Source operation ID: `SveOperation_svrevb_s16_m`

**Operation**



Return a vector in which each active element *i* contains the result of reversing the order of the bytes in `op[i]`. Take the inactive elements of the result from the corresponding elements of `inactive`.

## svrevb[_u16]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrevb%5B_u16%5D_x

### Signature (source notation)

```c
svuint16_t svrevb[_u16]_x(svbool_t pg, svuint16_t op);
```

### Description

Reverse bytes within elements

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Reverse elements

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
  "pg": {
    "register": "Pg"
  },
  "op": {
    "register": "Zop.H|Ztied.H"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.H|Ztied.H": "result"
  }
]
```

### Instruction mapping

When result and op are in the same register, this intrinsic compiles to:

```asm
REVB Ztied.H, Pg/M, Ztied.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/REVB--REVH--REVW--Reverse-bytes---halfwords---words-within-elements--predicated--

When result and op are in different registers, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
REVB Zresult.H, Pg/M, Zop.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/REVB--REVH--REVW--Reverse-bytes---halfwords---words-within-elements--predicated--

### Operation

Source operation ID: `SveOperation_svrevb_s16_x`

**Operation**



Return a vector in which each active element *i* contains the result of reversing the order of the bytes in `op[i]`. The inactive elements of the result have arbitrary, undefined values.

## svrevb[_u16]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrevb%5B_u16%5D_z

### Signature (source notation)

```c
svuint16_t svrevb[_u16]_z(svbool_t pg, svuint16_t op);
```

### Description

Reverse bytes within elements

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Reverse elements

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
  "pg": {
    "register": "Pg"
  },
  "op": {
    "register": "Zop.H"
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

This intrinsic compiles to the following instructions, or functionally equivalent instructions:

```asm
MOVPRFX Zresult.H, Pg/Z, Zop.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
REVB Zresult.H, Pg/M, Zop.H  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/REVB--REVH--REVW--Reverse-bytes---halfwords---words-within-elements--predicated--

### Operation

Source operation ID: `SveOperation_svrevb_s16_z`

**Operation**



Return a vector in which each active element *i* contains the result of reversing the order of the bytes in `op[i]`. Set the inactive elements of the result to zero.



**[1]** Note that `result` must be in a different register from `op`

## svrevb[_u32]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrevb%5B_u32%5D_m

### Signature (source notation)

```c
svuint32_t svrevb[_u32]_m(svuint32_t inactive, svbool_t pg, svuint32_t op);
```

### Description

Reverse bytes within elements

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Reverse elements

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
  "inactive": {
    "register": "Zinactive.S|Ztied.S"
  },
  "pg": {
    "register": "Pg"
  },
  "op": {
    "register": "Zop.S"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.S|Ztied.S": "result"
  }
]
```

### Instruction mapping

When result and inactive are in the same register, this intrinsic compiles to:

```asm
REVB Ztied.S, Pg/M, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/REVB--REVH--REVW--Reverse-bytes---halfwords---words-within-elements--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zinactive
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
REVB Zresult.S, Pg/M, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/REVB--REVH--REVW--Reverse-bytes---halfwords---words-within-elements--predicated--

### Operation

Source operation ID: `SveOperation_svrevb_s16_m`

**Operation**



Return a vector in which each active element *i* contains the result of reversing the order of the bytes in `op[i]`. Take the inactive elements of the result from the corresponding elements of `inactive`.

## svrevb[_u32]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrevb%5B_u32%5D_x

### Signature (source notation)

```c
svuint32_t svrevb[_u32]_x(svbool_t pg, svuint32_t op);
```

### Description

Reverse bytes within elements

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Reverse elements

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
  "pg": {
    "register": "Pg"
  },
  "op": {
    "register": "Zop.S|Ztied.S"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.S|Ztied.S": "result"
  }
]
```

### Instruction mapping

When result and op are in the same register, this intrinsic compiles to:

```asm
REVB Ztied.S, Pg/M, Ztied.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/REVB--REVH--REVW--Reverse-bytes---halfwords---words-within-elements--predicated--

When result and op are in different registers, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
REVB Zresult.S, Pg/M, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/REVB--REVH--REVW--Reverse-bytes---halfwords---words-within-elements--predicated--

### Operation

Source operation ID: `SveOperation_svrevb_s16_x`

**Operation**



Return a vector in which each active element *i* contains the result of reversing the order of the bytes in `op[i]`. The inactive elements of the result have arbitrary, undefined values.

## svrevb[_u32]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrevb%5B_u32%5D_z

### Signature (source notation)

```c
svuint32_t svrevb[_u32]_z(svbool_t pg, svuint32_t op);
```

### Description

Reverse bytes within elements

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Reverse elements

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
  "pg": {
    "register": "Pg"
  },
  "op": {
    "register": "Zop.S"
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

This intrinsic compiles to the following instructions, or functionally equivalent instructions:

```asm
MOVPRFX Zresult.S, Pg/Z, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
REVB Zresult.S, Pg/M, Zop.S  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/REVB--REVH--REVW--Reverse-bytes---halfwords---words-within-elements--predicated--

### Operation

Source operation ID: `SveOperation_svrevb_s16_z`

**Operation**



Return a vector in which each active element *i* contains the result of reversing the order of the bytes in `op[i]`. Set the inactive elements of the result to zero.



**[1]** Note that `result` must be in a different register from `op`

## svrevb[_u64]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrevb%5B_u64%5D_m

### Signature (source notation)

```c
svuint64_t svrevb[_u64]_m(svuint64_t inactive, svbool_t pg, svuint64_t op);
```

### Description

Reverse bytes within elements

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Reverse elements

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
  "inactive": {
    "register": "Zinactive.D|Ztied.D"
  },
  "pg": {
    "register": "Pg"
  },
  "op": {
    "register": "Zop.D"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.D|Ztied.D": "result"
  }
]
```

### Instruction mapping

When result and inactive are in the same register, this intrinsic compiles to:

```asm
REVB Ztied.D, Pg/M, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/REVB--REVH--REVW--Reverse-bytes---halfwords---words-within-elements--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zinactive
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
REVB Zresult.D, Pg/M, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/REVB--REVH--REVW--Reverse-bytes---halfwords---words-within-elements--predicated--

### Operation

Source operation ID: `SveOperation_svrevb_s16_m`

**Operation**



Return a vector in which each active element *i* contains the result of reversing the order of the bytes in `op[i]`. Take the inactive elements of the result from the corresponding elements of `inactive`.

## svrevb[_u64]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrevb%5B_u64%5D_x

### Signature (source notation)

```c
svuint64_t svrevb[_u64]_x(svbool_t pg, svuint64_t op);
```

### Description

Reverse bytes within elements

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Reverse elements

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
  "pg": {
    "register": "Pg"
  },
  "op": {
    "register": "Zop.D|Ztied.D"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.D|Ztied.D": "result"
  }
]
```

### Instruction mapping

When result and op are in the same register, this intrinsic compiles to:

```asm
REVB Ztied.D, Pg/M, Ztied.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/REVB--REVH--REVW--Reverse-bytes---halfwords---words-within-elements--predicated--

When result and op are in different registers, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
REVB Zresult.D, Pg/M, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/REVB--REVH--REVW--Reverse-bytes---halfwords---words-within-elements--predicated--

### Operation

Source operation ID: `SveOperation_svrevb_s16_x`

**Operation**



Return a vector in which each active element *i* contains the result of reversing the order of the bytes in `op[i]`. The inactive elements of the result have arbitrary, undefined values.

## svrevb[_u64]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrevb%5B_u64%5D_z

### Signature (source notation)

```c
svuint64_t svrevb[_u64]_z(svbool_t pg, svuint64_t op);
```

### Description

Reverse bytes within elements

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Reverse elements

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
  "pg": {
    "register": "Pg"
  },
  "op": {
    "register": "Zop.D"
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

This intrinsic compiles to the following instructions, or functionally equivalent instructions:

```asm
MOVPRFX Zresult.D, Pg/Z, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
REVB Zresult.D, Pg/M, Zop.D  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/REVB--REVH--REVW--Reverse-bytes---halfwords---words-within-elements--predicated--

### Operation

Source operation ID: `SveOperation_svrevb_s16_z`

**Operation**



Return a vector in which each active element *i* contains the result of reversing the order of the bytes in `op[i]`. Set the inactive elements of the result to zero.



**[1]** Note that `result` must be in a different register from `op`

## svrevd[_bf16]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrevd%5B_bf16%5D_m

### Signature (source notation)

```c
svbfloat16_t svrevd[_bf16]_m(svbfloat16_t zd, svbool_t pg, svbfloat16_t zn);
```

### Description

Reverse 64-bit doublewords in elements (predicated)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector manipulation / Reverse elements

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
  "return_base_type": "bfloat16",
  "element_bit_size": "16",
  "value": "svbfloat16_t"
}
```

### Argument preparation and constraints

```json
{
  "zd": {
    "register": "Zreg1.Q"
  },
  "pg": {
    "register": "Preg1"
  },
  "zn": {
    "register": "Zreg2.Q"
  }
}
```

### Result mapping

```json
[
  {
    "Zreg1.Q": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
REVD Zreg1.Q, Preg1/M, Zreg2.Q
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/REVD--Reverse-64-bit-doublewords-in-elements--predicated--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svrevd[_bf16]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrevd%5B_bf16%5D_x

### Signature (source notation)

```c
svbfloat16_t svrevd[_bf16]_x(svbool_t pg, svbfloat16_t zn);
```

### Description

Reverse 64-bit doublewords in elements (predicated)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector manipulation / Reverse elements

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
  "return_base_type": "bfloat16",
  "element_bit_size": "16",
  "value": "svbfloat16_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Preg1"
  },
  "zn": {
    "register": "Zreg2.Q"
  }
}
```

### Result mapping

```json
[
  {
    "Zreg1.Q": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
REVD Zreg1.Q, Preg1/M, Zreg2.Q
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/REVD--Reverse-64-bit-doublewords-in-elements--predicated--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svrevd[_bf16]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrevd%5B_bf16%5D_z

### Signature (source notation)

```c
svbfloat16_t svrevd[_bf16]_z(svbool_t pg, svbfloat16_t zn);
```

### Description

Reverse 64-bit doublewords in elements (predicated)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector manipulation / Reverse elements

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
  "return_base_type": "bfloat16",
  "element_bit_size": "16",
  "value": "svbfloat16_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Preg1"
  },
  "zn": {
    "register": "Zreg2.Q"
  }
}
```

### Result mapping

```json
[
  {
    "Zreg1.Q": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
MOV Zreg1.H, #0
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOV--immediate--unpredicated---Move-signed-immediate-to-vector-elements--unpredicated---an-alias-of-DUP--immediate--

```asm
REVD Zreg1.Q, Preg1/M, Zreg2.Q
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/REVD--Reverse-64-bit-doublewords-in-elements--predicated--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svrevd[_f16]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrevd%5B_f16%5D_m

### Signature (source notation)

```c
svfloat16_t svrevd[_f16]_m(svfloat16_t zd, svbool_t pg, svfloat16_t zn);
```

### Description

Reverse 64-bit doublewords in elements (predicated)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector manipulation / Reverse elements

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
  "return_base_type": "float16",
  "element_bit_size": "16",
  "value": "svfloat16_t"
}
```

### Argument preparation and constraints

```json
{
  "zd": {
    "register": "Zreg1.Q"
  },
  "pg": {
    "register": "Preg1"
  },
  "zn": {
    "register": "Zreg2.Q"
  }
}
```

### Result mapping

```json
[
  {
    "Zreg1.Q": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
REVD Zreg1.Q, Preg1/M, Zreg2.Q
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/REVD--Reverse-64-bit-doublewords-in-elements--predicated--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svrevd[_f16]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrevd%5B_f16%5D_x

### Signature (source notation)

```c
svfloat16_t svrevd[_f16]_x(svbool_t pg, svfloat16_t zn);
```

### Description

Reverse 64-bit doublewords in elements (predicated)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector manipulation / Reverse elements

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
  "return_base_type": "float16",
  "element_bit_size": "16",
  "value": "svfloat16_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Preg1"
  },
  "zn": {
    "register": "Zreg2.Q"
  }
}
```

### Result mapping

```json
[
  {
    "Zreg1.Q": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
REVD Zreg1.Q, Preg1/M, Zreg2.Q
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/REVD--Reverse-64-bit-doublewords-in-elements--predicated--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svrevd[_f16]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrevd%5B_f16%5D_z

### Signature (source notation)

```c
svfloat16_t svrevd[_f16]_z(svbool_t pg, svfloat16_t zn);
```

### Description

Reverse 64-bit doublewords in elements (predicated)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector manipulation / Reverse elements

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
  "return_base_type": "float16",
  "element_bit_size": "16",
  "value": "svfloat16_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Preg1"
  },
  "zn": {
    "register": "Zreg2.Q"
  }
}
```

### Result mapping

```json
[
  {
    "Zreg1.Q": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
MOV Zreg1.S, #0
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOV--immediate--unpredicated---Move-signed-immediate-to-vector-elements--unpredicated---an-alias-of-DUP--immediate--

```asm
REVD Zreg1.Q, Preg1/M, Zreg2.Q
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/REVD--Reverse-64-bit-doublewords-in-elements--predicated--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svrevd[_f32]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrevd%5B_f32%5D_m

### Signature (source notation)

```c
svfloat32_t svrevd[_f32]_m(svfloat32_t zd, svbool_t pg, svfloat32_t zn);
```

### Description

Reverse 64-bit doublewords in elements (predicated)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector manipulation / Reverse elements

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
  "return_base_type": "float32",
  "element_bit_size": "32",
  "value": "svfloat32_t"
}
```

### Argument preparation and constraints

```json
{
  "zd": {
    "register": "Zreg1.Q"
  },
  "pg": {
    "register": "Preg1"
  },
  "zn": {
    "register": "Zreg2.Q"
  }
}
```

### Result mapping

```json
[
  {
    "Zreg1.Q": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
REVD Zreg1.Q, Preg1/M, Zreg2.Q
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/REVD--Reverse-64-bit-doublewords-in-elements--predicated--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svrevd[_f32]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrevd%5B_f32%5D_x

### Signature (source notation)

```c
svfloat32_t svrevd[_f32]_x(svbool_t pg, svfloat32_t zn);
```

### Description

Reverse 64-bit doublewords in elements (predicated)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector manipulation / Reverse elements

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
  "return_base_type": "float32",
  "element_bit_size": "32",
  "value": "svfloat32_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Preg1"
  },
  "zn": {
    "register": "Zreg2.Q"
  }
}
```

### Result mapping

```json
[
  {
    "Zreg1.Q": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
REVD Zreg1.Q, Preg1/M, Zreg2.Q
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/REVD--Reverse-64-bit-doublewords-in-elements--predicated--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svrevd[_f32]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrevd%5B_f32%5D_z

### Signature (source notation)

```c
svfloat32_t svrevd[_f32]_z(svbool_t pg, svfloat32_t zn);
```

### Description

Reverse 64-bit doublewords in elements (predicated)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector manipulation / Reverse elements

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
  "return_base_type": "float32",
  "element_bit_size": "32",
  "value": "svfloat32_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Preg1"
  },
  "zn": {
    "register": "Zreg2.Q"
  }
}
```

### Result mapping

```json
[
  {
    "Zreg1.Q": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
MOV Zreg1.S, #0
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOV--immediate--unpredicated---Move-signed-immediate-to-vector-elements--unpredicated---an-alias-of-DUP--immediate--

```asm
REVD Zreg1.Q, Preg1/M, Zreg2.Q
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/REVD--Reverse-64-bit-doublewords-in-elements--predicated--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svrevd[_f64]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrevd%5B_f64%5D_m

### Signature (source notation)

```c
svfloat64_t svrevd[_f64]_m(svfloat64_t zd, svbool_t pg, svfloat64_t zn);
```

### Description

Reverse 64-bit doublewords in elements (predicated)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector manipulation / Reverse elements

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
  "return_base_type": "float64",
  "element_bit_size": "64",
  "value": "svfloat64_t"
}
```

### Argument preparation and constraints

```json
{
  "zd": {
    "register": "Zreg1.Q"
  },
  "pg": {
    "register": "Preg1"
  },
  "zn": {
    "register": "Zreg2.Q"
  }
}
```

### Result mapping

```json
[
  {
    "Zreg1.Q": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
REVD Zreg1.Q, Preg1/M, Zreg2.Q
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/REVD--Reverse-64-bit-doublewords-in-elements--predicated--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svrevd[_f64]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrevd%5B_f64%5D_x

### Signature (source notation)

```c
svfloat64_t svrevd[_f64]_x(svbool_t pg, svfloat64_t zn);
```

### Description

Reverse 64-bit doublewords in elements (predicated)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector manipulation / Reverse elements

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
  "return_base_type": "float64",
  "element_bit_size": "64",
  "value": "svfloat64_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Preg1"
  },
  "zn": {
    "register": "Zreg2.Q"
  }
}
```

### Result mapping

```json
[
  {
    "Zreg1.Q": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
REVD Zreg1.Q, Preg1/M, Zreg2.Q
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/REVD--Reverse-64-bit-doublewords-in-elements--predicated--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svrevd[_f64]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrevd%5B_f64%5D_z

### Signature (source notation)

```c
svfloat64_t svrevd[_f64]_z(svbool_t pg, svfloat64_t zn);
```

### Description

Reverse 64-bit doublewords in elements (predicated)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector manipulation / Reverse elements

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
  "return_base_type": "float64",
  "element_bit_size": "64",
  "value": "svfloat64_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Preg1"
  },
  "zn": {
    "register": "Zreg2.Q"
  }
}
```

### Result mapping

```json
[
  {
    "Zreg1.Q": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
MOV Zreg1.D, #0
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOV--immediate--unpredicated---Move-signed-immediate-to-vector-elements--unpredicated---an-alias-of-DUP--immediate--

```asm
REVD Zreg1.Q, Preg1/M, Zreg2.Q
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/REVD--Reverse-64-bit-doublewords-in-elements--predicated--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svrevd[_mf8]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrevd%5B_mf8%5D_m

### Signature (source notation)

```c
svmfloat8_t svrevd[_mf8]_m(svmfloat8_t zd, svbool_t pg, svmfloat8_t zn);
```

### Description

Reverse 64-bit doublewords in elements (predicated)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector manipulation / Reverse elements

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
  "return_base_type": "mfloat8",
  "element_bit_size": "8",
  "value": "svmfloat8_t"
}
```

### Argument preparation and constraints

```json
{
  "zd": {
    "register": "Zreg1.Q"
  },
  "pg": {
    "register": "Preg1"
  },
  "zn": {
    "register": "Zreg2.Q"
  }
}
```

### Result mapping

```json
[
  {
    "Zreg1.Q": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
REVD Zreg1.Q, Preg1/M, Zreg2.Q
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/REVD--Reverse-64-bit-doublewords-in-elements--predicated--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svrevd[_mf8]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrevd%5B_mf8%5D_x

### Signature (source notation)

```c
svmfloat8_t svrevd[_mf8]_x(svbool_t pg, svmfloat8_t zn);
```

### Description

Reverse 64-bit doublewords in elements (predicated)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector manipulation / Reverse elements

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
  "return_base_type": "mfloat8",
  "element_bit_size": "8",
  "value": "svmfloat8_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Preg1"
  },
  "zn": {
    "register": "Zreg2.Q"
  }
}
```

### Result mapping

```json
[
  {
    "Zreg1.Q": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
REVD Zreg1.Q, Preg1/M, Zreg2.Q
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/REVD--Reverse-64-bit-doublewords-in-elements--predicated--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svrevd[_mf8]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrevd%5B_mf8%5D_z

### Signature (source notation)

```c
svmfloat8_t svrevd[_mf8]_z(svbool_t pg, svmfloat8_t zn);
```

### Description

Reverse 64-bit doublewords in elements (predicated)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector manipulation / Reverse elements

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
  "return_base_type": "mfloat8",
  "element_bit_size": "8",
  "value": "svmfloat8_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Preg1"
  },
  "zn": {
    "register": "Zreg2.Q"
  }
}
```

### Result mapping

```json
[
  {
    "Zreg1.Q": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
MOV Zreg1.H, #0
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOV--immediate--unpredicated---Move-signed-immediate-to-vector-elements--unpredicated---an-alias-of-DUP--immediate--

```asm
REVD Zreg1.Q, Preg1/M, Zreg2.Q
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/REVD--Reverse-64-bit-doublewords-in-elements--predicated--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svrevd[_s16]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrevd%5B_s16%5D_m

### Signature (source notation)

```c
svint16_t svrevd[_s16]_m(svint16_t zd, svbool_t pg, svint16_t zn);
```

### Description

Reverse 64-bit doublewords in elements (predicated)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector manipulation / Reverse elements

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
  "return_base_type": "int16",
  "element_bit_size": "16",
  "value": "svint16_t"
}
```

### Argument preparation and constraints

```json
{
  "zd": {
    "register": "Zreg1.Q"
  },
  "pg": {
    "register": "Preg1"
  },
  "zn": {
    "register": "Zreg2.Q"
  }
}
```

### Result mapping

```json
[
  {
    "Zreg1.Q": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
REVD Zreg1.Q, Preg1/M, Zreg2.Q
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/REVD--Reverse-64-bit-doublewords-in-elements--predicated--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

