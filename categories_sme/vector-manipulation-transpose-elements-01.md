# SME / Vector manipulation / Transpose elements — Part 1

## svtrn1[_bf16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svtrn1%5B_bf16%5D

### Signature (source notation)

```c
svbfloat16_t svtrn1[_bf16](svbfloat16_t op1, svbfloat16_t op2);
```

### Description

Interleave even elements from two inputs.



This diagram shows the operation of the svtrn1_bf16 intrinsic for a vector length of 128 bits:





![Source diagram: svtrn1_16_128.svg](https://developer.arm.com/architectures/instruction-sets/intrinsics/data/images/svtrn1_16_128.svg)

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Transpose elements

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
    "Zresult.H": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
TRN1 Zresult.H, Zop1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/TRN1--TRN2--vectors---Interleave-even-or-odd-elements-from-two-vectors-

### Operation

Source operation ID: `SveOperation_svtrn1_bf16`

**Operation**



Extract the even-indexed elements from `op1` and `op2` and interleave them, so that each even element of `op1` is followed by the corresponding element of `op2`.

## svtrn1[_f16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svtrn1%5B_f16%5D

### Signature (source notation)

```c
svfloat16_t svtrn1[_f16](svfloat16_t op1, svfloat16_t op2);
```

### Description

Interleave even elements from two inputs.



This diagram shows the operation of the svtrn1_f16 intrinsic for a vector length of 128 bits:





![Source diagram: svtrn1_16_128.svg](https://developer.arm.com/architectures/instruction-sets/intrinsics/data/images/svtrn1_16_128.svg)

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Transpose elements

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
    "Zresult.H": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
TRN1 Zresult.H, Zop1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/TRN1--TRN2--vectors---Interleave-even-or-odd-elements-from-two-vectors-

### Operation

Source operation ID: `SveOperation_svtrn1_bf16`

**Operation**



Extract the even-indexed elements from `op1` and `op2` and interleave them, so that each even element of `op1` is followed by the corresponding element of `op2`.

## svtrn1[_f32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svtrn1%5B_f32%5D

### Signature (source notation)

```c
svfloat32_t svtrn1[_f32](svfloat32_t op1, svfloat32_t op2);
```

### Description

Interleave even elements from two inputs.



This diagram shows the operation of the svtrn1_f32 intrinsic for a vector length of 256 bits:





![Source diagram: svtrn1_32_256.svg](https://developer.arm.com/architectures/instruction-sets/intrinsics/data/images/svtrn1_32_256.svg)

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Transpose elements

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
    "Zresult.S": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
TRN1 Zresult.S, Zop1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/TRN1--TRN2--vectors---Interleave-even-or-odd-elements-from-two-vectors-

### Operation

Source operation ID: `SveOperation_svtrn1_bf16`

**Operation**



Extract the even-indexed elements from `op1` and `op2` and interleave them, so that each even element of `op1` is followed by the corresponding element of `op2`.

## svtrn1[_f64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svtrn1%5B_f64%5D

### Signature (source notation)

```c
svfloat64_t svtrn1[_f64](svfloat64_t op1, svfloat64_t op2);
```

### Description

Interleave even elements from two inputs.



This diagram shows the operation of the svtrn1_f64 intrinsic for a vector length of 512 bits:





![Source diagram: svtrn1_64_512.svg](https://developer.arm.com/architectures/instruction-sets/intrinsics/data/images/svtrn1_64_512.svg)

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Transpose elements

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
    "Zresult.D": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
TRN1 Zresult.D, Zop1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/TRN1--TRN2--vectors---Interleave-even-or-odd-elements-from-two-vectors-

### Operation

Source operation ID: `SveOperation_svtrn1_bf16`

**Operation**



Extract the even-indexed elements from `op1` and `op2` and interleave them, so that each even element of `op1` is followed by the corresponding element of `op2`.

## svtrn1[_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svtrn1%5B_s16%5D

### Signature (source notation)

```c
svint16_t svtrn1[_s16](svint16_t op1, svint16_t op2);
```

### Description

Interleave even elements from two inputs.



This diagram shows the operation of the svtrn1_s16 intrinsic for a vector length of 128 bits:





![Source diagram: svtrn1_16_128.svg](https://developer.arm.com/architectures/instruction-sets/intrinsics/data/images/svtrn1_16_128.svg)

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Transpose elements

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
    "register": "Zop2.H"
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
TRN1 Zresult.H, Zop1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/TRN1--TRN2--vectors---Interleave-even-or-odd-elements-from-two-vectors-

### Operation

Source operation ID: `SveOperation_svtrn1_bf16`

**Operation**



Extract the even-indexed elements from `op1` and `op2` and interleave them, so that each even element of `op1` is followed by the corresponding element of `op2`.

## svtrn1[_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svtrn1%5B_s32%5D

### Signature (source notation)

```c
svint32_t svtrn1[_s32](svint32_t op1, svint32_t op2);
```

### Description

Interleave even elements from two inputs.



This diagram shows the operation of the svtrn1_s32 intrinsic for a vector length of 256 bits:





![Source diagram: svtrn1_32_256.svg](https://developer.arm.com/architectures/instruction-sets/intrinsics/data/images/svtrn1_32_256.svg)

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Transpose elements

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
    "register": "Zop2.S"
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
TRN1 Zresult.S, Zop1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/TRN1--TRN2--vectors---Interleave-even-or-odd-elements-from-two-vectors-

### Operation

Source operation ID: `SveOperation_svtrn1_bf16`

**Operation**



Extract the even-indexed elements from `op1` and `op2` and interleave them, so that each even element of `op1` is followed by the corresponding element of `op2`.

## svtrn1[_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svtrn1%5B_s64%5D

### Signature (source notation)

```c
svint64_t svtrn1[_s64](svint64_t op1, svint64_t op2);
```

### Description

Interleave even elements from two inputs.



This diagram shows the operation of the svtrn1_s64 intrinsic for a vector length of 512 bits:





![Source diagram: svtrn1_64_512.svg](https://developer.arm.com/architectures/instruction-sets/intrinsics/data/images/svtrn1_64_512.svg)

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Transpose elements

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
    "register": "Zop2.D"
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
TRN1 Zresult.D, Zop1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/TRN1--TRN2--vectors---Interleave-even-or-odd-elements-from-two-vectors-

### Operation

Source operation ID: `SveOperation_svtrn1_bf16`

**Operation**



Extract the even-indexed elements from `op1` and `op2` and interleave them, so that each even element of `op1` is followed by the corresponding element of `op2`.

## svtrn1[_s8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svtrn1%5B_s8%5D

### Signature (source notation)

```c
svint8_t svtrn1[_s8](svint8_t op1, svint8_t op2);
```

### Description

Interleave even elements from two inputs.



This diagram shows the operation of the svtrn1_s8 intrinsic for a vector length of 128 bits:





![Source diagram: svtrn1_8_128.svg](https://developer.arm.com/architectures/instruction-sets/intrinsics/data/images/svtrn1_8_128.svg)

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Transpose elements

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
    "Zresult.B": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
TRN1 Zresult.B, Zop1.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/TRN1--TRN2--vectors---Interleave-even-or-odd-elements-from-two-vectors-

### Operation

Source operation ID: `SveOperation_svtrn1_bf16`

**Operation**



Extract the even-indexed elements from `op1` and `op2` and interleave them, so that each even element of `op1` is followed by the corresponding element of `op2`.

## svtrn1[_u16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svtrn1%5B_u16%5D

### Signature (source notation)

```c
svuint16_t svtrn1[_u16](svuint16_t op1, svuint16_t op2);
```

### Description

Interleave even elements from two inputs.



This diagram shows the operation of the svtrn1_u16 intrinsic for a vector length of 128 bits:





![Source diagram: svtrn1_16_128.svg](https://developer.arm.com/architectures/instruction-sets/intrinsics/data/images/svtrn1_16_128.svg)

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Transpose elements

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
    "register": "Zop2.H"
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
TRN1 Zresult.H, Zop1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/TRN1--TRN2--vectors---Interleave-even-or-odd-elements-from-two-vectors-

### Operation

Source operation ID: `SveOperation_svtrn1_bf16`

**Operation**



Extract the even-indexed elements from `op1` and `op2` and interleave them, so that each even element of `op1` is followed by the corresponding element of `op2`.

## svtrn1[_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svtrn1%5B_u32%5D

### Signature (source notation)

```c
svuint32_t svtrn1[_u32](svuint32_t op1, svuint32_t op2);
```

### Description

Interleave even elements from two inputs.



This diagram shows the operation of the svtrn1_u32 intrinsic for a vector length of 256 bits:





![Source diagram: svtrn1_32_256.svg](https://developer.arm.com/architectures/instruction-sets/intrinsics/data/images/svtrn1_32_256.svg)

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Transpose elements

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
    "register": "Zop2.S"
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
TRN1 Zresult.S, Zop1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/TRN1--TRN2--vectors---Interleave-even-or-odd-elements-from-two-vectors-

### Operation

Source operation ID: `SveOperation_svtrn1_bf16`

**Operation**



Extract the even-indexed elements from `op1` and `op2` and interleave them, so that each even element of `op1` is followed by the corresponding element of `op2`.

## svtrn1[_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svtrn1%5B_u64%5D

### Signature (source notation)

```c
svuint64_t svtrn1[_u64](svuint64_t op1, svuint64_t op2);
```

### Description

Interleave even elements from two inputs.



This diagram shows the operation of the svtrn1_u64 intrinsic for a vector length of 512 bits:





![Source diagram: svtrn1_64_512.svg](https://developer.arm.com/architectures/instruction-sets/intrinsics/data/images/svtrn1_64_512.svg)

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Transpose elements

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
    "register": "Zop2.D"
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
TRN1 Zresult.D, Zop1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/TRN1--TRN2--vectors---Interleave-even-or-odd-elements-from-two-vectors-

### Operation

Source operation ID: `SveOperation_svtrn1_bf16`

**Operation**



Extract the even-indexed elements from `op1` and `op2` and interleave them, so that each even element of `op1` is followed by the corresponding element of `op2`.

## svtrn1[_u8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svtrn1%5B_u8%5D

### Signature (source notation)

```c
svuint8_t svtrn1[_u8](svuint8_t op1, svuint8_t op2);
```

### Description

Interleave even elements from two inputs.



This diagram shows the operation of the svtrn1_u8 intrinsic for a vector length of 128 bits:





![Source diagram: svtrn1_8_128.svg](https://developer.arm.com/architectures/instruction-sets/intrinsics/data/images/svtrn1_8_128.svg)

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Transpose elements

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
    "Zresult.B": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
TRN1 Zresult.B, Zop1.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/TRN1--TRN2--vectors---Interleave-even-or-odd-elements-from-two-vectors-

### Operation

Source operation ID: `SveOperation_svtrn1_bf16`

**Operation**



Extract the even-indexed elements from `op1` and `op2` and interleave them, so that each even element of `op1` is followed by the corresponding element of `op2`.

## svtrn1_b16

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svtrn1_b16

### Signature (source notation)

```c
svbool_t svtrn1_b16(svbool_t op1, svbool_t op2);
```

### Description

Interleave even elements from two predicates.



This diagram shows the operation of the svtrn1_b16 intrinsic for a vector length of 128 bits:





![Source diagram: svtrn1_p__16_128.svg](https://developer.arm.com/architectures/instruction-sets/intrinsics/data/images/svtrn1_p__16_128.svg)

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Transpose elements

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
  "op1": {
    "register": "Pop1.H"
  },
  "op2": {
    "register": "Pop2.H"
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
TRN1 Presult.H, Pop1.H, Pop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/TRN1--TRN2--predicates---Interleave-even-or-odd-elements-from-two-predicates-

### Operation

Source operation ID: `SveOperation_svtrn1_bf16`

**Operation**



Extract the even-indexed elements from `op1` and `op2` and interleave them, so that each even element of `op1` is followed by the corresponding element of `op2`.

## svtrn1_b32

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svtrn1_b32

### Signature (source notation)

```c
svbool_t svtrn1_b32(svbool_t op1, svbool_t op2);
```

### Description

Interleave even elements from two predicates.



This diagram shows the operation of the svtrn1_b32 intrinsic for a vector length of 256 bits:





![Source diagram: svtrn1_p__32_256.svg](https://developer.arm.com/architectures/instruction-sets/intrinsics/data/images/svtrn1_p__32_256.svg)

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Transpose elements

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
  "op1": {
    "register": "Pop1.S"
  },
  "op2": {
    "register": "Pop2.S"
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
TRN1 Presult.S, Pop1.S, Pop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/TRN1--TRN2--predicates---Interleave-even-or-odd-elements-from-two-predicates-

### Operation

Source operation ID: `SveOperation_svtrn1_bf16`

**Operation**



Extract the even-indexed elements from `op1` and `op2` and interleave them, so that each even element of `op1` is followed by the corresponding element of `op2`.

## svtrn1_b64

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svtrn1_b64

### Signature (source notation)

```c
svbool_t svtrn1_b64(svbool_t op1, svbool_t op2);
```

### Description

Interleave even elements from two predicates.



This diagram shows the operation of the svtrn1_b64 intrinsic for a vector length of 512 bits:





![Source diagram: svtrn1_p__64_512.svg](https://developer.arm.com/architectures/instruction-sets/intrinsics/data/images/svtrn1_p__64_512.svg)

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Transpose elements

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
  "op1": {
    "register": "Pop1.D"
  },
  "op2": {
    "register": "Pop2.D"
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
TRN1 Presult.D, Pop1.D, Pop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/TRN1--TRN2--predicates---Interleave-even-or-odd-elements-from-two-predicates-

### Operation

Source operation ID: `SveOperation_svtrn1_bf16`

**Operation**



Extract the even-indexed elements from `op1` and `op2` and interleave them, so that each even element of `op1` is followed by the corresponding element of `op2`.

## svtrn1_b8

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svtrn1_b8

### Signature (source notation)

```c
svbool_t svtrn1_b8(svbool_t op1, svbool_t op2);
```

### Description

Interleave even elements from two predicates.



This diagram shows the operation of the svtrn1_b8 intrinsic for a vector length of 128 bits:





![Source diagram: svtrn1_p__8_128.svg](https://developer.arm.com/architectures/instruction-sets/intrinsics/data/images/svtrn1_p__8_128.svg)

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Transpose elements

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
  "op1": {
    "register": "Pop1.B"
  },
  "op2": {
    "register": "Pop2.B"
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
TRN1 Presult.B, Pop1.B, Pop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/TRN1--TRN2--predicates---Interleave-even-or-odd-elements-from-two-predicates-

### Operation

Source operation ID: `SveOperation_svtrn1_bf16`

**Operation**



Extract the even-indexed elements from `op1` and `op2` and interleave them, so that each even element of `op1` is followed by the corresponding element of `op2`.

## svtrn2[_bf16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svtrn2%5B_bf16%5D

### Signature (source notation)

```c
svbfloat16_t svtrn2[_bf16](svbfloat16_t op1, svbfloat16_t op2);
```

### Description

Interleave odd elements from two inputs

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Transpose elements

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
    "Zresult.H": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
TRN2 Zresult.H, Zop1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/TRN1--TRN2--vectors---Interleave-even-or-odd-elements-from-two-vectors-

### Operation

Source operation ID: `SveOperation_svtrn2_bf16`

**Operation**



Extract the odd-indexed elements from `op1` and `op2` and interleave them, so that each odd element of `op1` is followed by the corresponding element of `op2`.

## svtrn2[_f16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svtrn2%5B_f16%5D

### Signature (source notation)

```c
svfloat16_t svtrn2[_f16](svfloat16_t op1, svfloat16_t op2);
```

### Description

Interleave odd elements from two inputs

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Transpose elements

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
    "Zresult.H": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
TRN2 Zresult.H, Zop1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/TRN1--TRN2--vectors---Interleave-even-or-odd-elements-from-two-vectors-

### Operation

Source operation ID: `SveOperation_svtrn2_bf16`

**Operation**



Extract the odd-indexed elements from `op1` and `op2` and interleave them, so that each odd element of `op1` is followed by the corresponding element of `op2`.

## svtrn2[_f32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svtrn2%5B_f32%5D

### Signature (source notation)

```c
svfloat32_t svtrn2[_f32](svfloat32_t op1, svfloat32_t op2);
```

### Description

Interleave odd elements from two inputs

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Transpose elements

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
    "Zresult.S": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
TRN2 Zresult.S, Zop1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/TRN1--TRN2--vectors---Interleave-even-or-odd-elements-from-two-vectors-

### Operation

Source operation ID: `SveOperation_svtrn2_bf16`

**Operation**



Extract the odd-indexed elements from `op1` and `op2` and interleave them, so that each odd element of `op1` is followed by the corresponding element of `op2`.

## svtrn2[_f64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svtrn2%5B_f64%5D

### Signature (source notation)

```c
svfloat64_t svtrn2[_f64](svfloat64_t op1, svfloat64_t op2);
```

### Description

Interleave odd elements from two inputs

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Transpose elements

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
    "Zresult.D": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
TRN2 Zresult.D, Zop1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/TRN1--TRN2--vectors---Interleave-even-or-odd-elements-from-two-vectors-

### Operation

Source operation ID: `SveOperation_svtrn2_bf16`

**Operation**



Extract the odd-indexed elements from `op1` and `op2` and interleave them, so that each odd element of `op1` is followed by the corresponding element of `op2`.

## svtrn2[_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svtrn2%5B_s16%5D

### Signature (source notation)

```c
svint16_t svtrn2[_s16](svint16_t op1, svint16_t op2);
```

### Description

Interleave odd elements from two inputs

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Transpose elements

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
    "register": "Zop2.H"
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
TRN2 Zresult.H, Zop1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/TRN1--TRN2--vectors---Interleave-even-or-odd-elements-from-two-vectors-

### Operation

Source operation ID: `SveOperation_svtrn2_bf16`

**Operation**



Extract the odd-indexed elements from `op1` and `op2` and interleave them, so that each odd element of `op1` is followed by the corresponding element of `op2`.

## svtrn2[_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svtrn2%5B_s32%5D

### Signature (source notation)

```c
svint32_t svtrn2[_s32](svint32_t op1, svint32_t op2);
```

### Description

Interleave odd elements from two inputs

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Transpose elements

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
    "register": "Zop2.S"
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
TRN2 Zresult.S, Zop1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/TRN1--TRN2--vectors---Interleave-even-or-odd-elements-from-two-vectors-

### Operation

Source operation ID: `SveOperation_svtrn2_bf16`

**Operation**



Extract the odd-indexed elements from `op1` and `op2` and interleave them, so that each odd element of `op1` is followed by the corresponding element of `op2`.

## svtrn2[_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svtrn2%5B_s64%5D

### Signature (source notation)

```c
svint64_t svtrn2[_s64](svint64_t op1, svint64_t op2);
```

### Description

Interleave odd elements from two inputs

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Transpose elements

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
    "register": "Zop2.D"
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
TRN2 Zresult.D, Zop1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/TRN1--TRN2--vectors---Interleave-even-or-odd-elements-from-two-vectors-

### Operation

Source operation ID: `SveOperation_svtrn2_bf16`

**Operation**



Extract the odd-indexed elements from `op1` and `op2` and interleave them, so that each odd element of `op1` is followed by the corresponding element of `op2`.

## svtrn2[_s8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svtrn2%5B_s8%5D

### Signature (source notation)

```c
svint8_t svtrn2[_s8](svint8_t op1, svint8_t op2);
```

### Description

Interleave odd elements from two inputs

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Transpose elements

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
    "Zresult.B": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
TRN2 Zresult.B, Zop1.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/TRN1--TRN2--vectors---Interleave-even-or-odd-elements-from-two-vectors-

### Operation

Source operation ID: `SveOperation_svtrn2_bf16`

**Operation**



Extract the odd-indexed elements from `op1` and `op2` and interleave them, so that each odd element of `op1` is followed by the corresponding element of `op2`.

## svtrn2[_u16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svtrn2%5B_u16%5D

### Signature (source notation)

```c
svuint16_t svtrn2[_u16](svuint16_t op1, svuint16_t op2);
```

### Description

Interleave odd elements from two inputs

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Transpose elements

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
    "register": "Zop2.H"
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
TRN2 Zresult.H, Zop1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/TRN1--TRN2--vectors---Interleave-even-or-odd-elements-from-two-vectors-

### Operation

Source operation ID: `SveOperation_svtrn2_bf16`

**Operation**



Extract the odd-indexed elements from `op1` and `op2` and interleave them, so that each odd element of `op1` is followed by the corresponding element of `op2`.

## svtrn2[_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svtrn2%5B_u32%5D

### Signature (source notation)

```c
svuint32_t svtrn2[_u32](svuint32_t op1, svuint32_t op2);
```

### Description

Interleave odd elements from two inputs

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Transpose elements

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
    "register": "Zop2.S"
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
TRN2 Zresult.S, Zop1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/TRN1--TRN2--vectors---Interleave-even-or-odd-elements-from-two-vectors-

### Operation

Source operation ID: `SveOperation_svtrn2_bf16`

**Operation**



Extract the odd-indexed elements from `op1` and `op2` and interleave them, so that each odd element of `op1` is followed by the corresponding element of `op2`.

## svtrn2[_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svtrn2%5B_u64%5D

### Signature (source notation)

```c
svuint64_t svtrn2[_u64](svuint64_t op1, svuint64_t op2);
```

### Description

Interleave odd elements from two inputs

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Transpose elements

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
    "register": "Zop2.D"
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
TRN2 Zresult.D, Zop1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/TRN1--TRN2--vectors---Interleave-even-or-odd-elements-from-two-vectors-

### Operation

Source operation ID: `SveOperation_svtrn2_bf16`

**Operation**



Extract the odd-indexed elements from `op1` and `op2` and interleave them, so that each odd element of `op1` is followed by the corresponding element of `op2`.

## svtrn2[_u8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svtrn2%5B_u8%5D

### Signature (source notation)

```c
svuint8_t svtrn2[_u8](svuint8_t op1, svuint8_t op2);
```

### Description

Interleave odd elements from two inputs

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Transpose elements

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
    "Zresult.B": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
TRN2 Zresult.B, Zop1.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/TRN1--TRN2--vectors---Interleave-even-or-odd-elements-from-two-vectors-

### Operation

Source operation ID: `SveOperation_svtrn2_bf16`

**Operation**



Extract the odd-indexed elements from `op1` and `op2` and interleave them, so that each odd element of `op1` is followed by the corresponding element of `op2`.

## svtrn2_b16

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svtrn2_b16

### Signature (source notation)

```c
svbool_t svtrn2_b16(svbool_t op1, svbool_t op2);
```

### Description

Interleave odd elements from two inputs

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Transpose elements

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
  "op1": {
    "register": "Pop1.H"
  },
  "op2": {
    "register": "Pop2.H"
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
TRN2 Presult.H, Pop1.H, Pop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/TRN1--TRN2--predicates---Interleave-even-or-odd-elements-from-two-predicates-

### Operation

Source operation ID: `SveOperation_svtrn2_bf16`

**Operation**



Extract the odd-indexed elements from `op1` and `op2` and interleave them, so that each odd element of `op1` is followed by the corresponding element of `op2`.

## svtrn2_b32

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svtrn2_b32

### Signature (source notation)

```c
svbool_t svtrn2_b32(svbool_t op1, svbool_t op2);
```

### Description

Interleave odd elements from two inputs

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Transpose elements

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
  "op1": {
    "register": "Pop1.S"
  },
  "op2": {
    "register": "Pop2.S"
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
TRN2 Presult.S, Pop1.S, Pop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/TRN1--TRN2--predicates---Interleave-even-or-odd-elements-from-two-predicates-

### Operation

Source operation ID: `SveOperation_svtrn2_bf16`

**Operation**



Extract the odd-indexed elements from `op1` and `op2` and interleave them, so that each odd element of `op1` is followed by the corresponding element of `op2`.

## svtrn2_b64

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svtrn2_b64

### Signature (source notation)

```c
svbool_t svtrn2_b64(svbool_t op1, svbool_t op2);
```

### Description

Interleave odd elements from two inputs

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Transpose elements

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
  "op1": {
    "register": "Pop1.D"
  },
  "op2": {
    "register": "Pop2.D"
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
TRN2 Presult.D, Pop1.D, Pop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/TRN1--TRN2--predicates---Interleave-even-or-odd-elements-from-two-predicates-

### Operation

Source operation ID: `SveOperation_svtrn2_bf16`

**Operation**



Extract the odd-indexed elements from `op1` and `op2` and interleave them, so that each odd element of `op1` is followed by the corresponding element of `op2`.

## svtrn2_b8

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svtrn2_b8

### Signature (source notation)

```c
svbool_t svtrn2_b8(svbool_t op1, svbool_t op2);
```

### Description

Interleave odd elements from two inputs

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Transpose elements

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
  "op1": {
    "register": "Pop1.B"
  },
  "op2": {
    "register": "Pop2.B"
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
TRN2 Presult.B, Pop1.B, Pop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/TRN1--TRN2--predicates---Interleave-even-or-odd-elements-from-two-predicates-

### Operation

Source operation ID: `SveOperation_svtrn2_bf16`

**Operation**



Extract the odd-indexed elements from `op1` and `op2` and interleave them, so that each odd element of `op1` is followed by the corresponding element of `op2`.

