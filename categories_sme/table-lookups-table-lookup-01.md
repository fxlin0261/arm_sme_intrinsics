# SME / Table lookups / Table lookup — Part 1

## svtbl2[_bf16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svtbl2%5B_bf16%5D

### Signature (source notation)

```c
svbfloat16_t svtbl2[_bf16](svbfloat16x2_t data, svuint16_t indices);
```

### Description

Table lookup in two-vector table

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Table lookups / Table lookup

- SME attributes: Not specified by source.

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
  "data": {
    "register": "{Zdata0.H, Zdata1.H}"
  },
  "indices": {
    "register": "Zindices.H"
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
TBL Zresult.H, {Zdata0.H, Zdata1.H}, Zindices.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/TBL--Programmable-table-lookup-in-one-or-two-vector-table--zeroing--

### Operation

Source operation ID: `SveOperation_svtbl2_bf16`

**Operation**



Concatenate the vectors in `data` together to form a double-length vector *v*.  Return a vector in which each element *i* contains:




- element `indices[i]` of *v* if 0 ≤ `indices[i]` < *n*, where *n* is the number of elements in *v*
- zero otherwise

## svtbl2[_f16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svtbl2%5B_f16%5D

### Signature (source notation)

```c
svfloat16_t svtbl2[_f16](svfloat16x2_t data, svuint16_t indices);
```

### Description

Table lookup in two-vector table

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Table lookups / Table lookup

- SME attributes: Not specified by source.

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
  "data": {
    "register": "{Zdata0.H, Zdata1.H}"
  },
  "indices": {
    "register": "Zindices.H"
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
TBL Zresult.H, {Zdata0.H, Zdata1.H}, Zindices.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/TBL--Programmable-table-lookup-in-one-or-two-vector-table--zeroing--

### Operation

Source operation ID: `SveOperation_svtbl2_bf16`

**Operation**



Concatenate the vectors in `data` together to form a double-length vector *v*.  Return a vector in which each element *i* contains:




- element `indices[i]` of *v* if 0 ≤ `indices[i]` < *n*, where *n* is the number of elements in *v*
- zero otherwise

## svtbl2[_f32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svtbl2%5B_f32%5D

### Signature (source notation)

```c
svfloat32_t svtbl2[_f32](svfloat32x2_t data, svuint32_t indices);
```

### Description

Table lookup in two-vector table

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Table lookups / Table lookup

- SME attributes: Not specified by source.

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
  "data": {
    "register": "{Zdata0.S, Zdata1.S}"
  },
  "indices": {
    "register": "Zindices.S"
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
TBL Zresult.S, {Zdata0.S, Zdata1.S}, Zindices.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/TBL--Programmable-table-lookup-in-one-or-two-vector-table--zeroing--

### Operation

Source operation ID: `SveOperation_svtbl2_bf16`

**Operation**



Concatenate the vectors in `data` together to form a double-length vector *v*.  Return a vector in which each element *i* contains:




- element `indices[i]` of *v* if 0 ≤ `indices[i]` < *n*, where *n* is the number of elements in *v*
- zero otherwise

## svtbl2[_f64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svtbl2%5B_f64%5D

### Signature (source notation)

```c
svfloat64_t svtbl2[_f64](svfloat64x2_t data, svuint64_t indices);
```

### Description

Table lookup in two-vector table

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Table lookups / Table lookup

- SME attributes: Not specified by source.

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
  "data": {
    "register": "{Zdata0.D, Zdata1.D}"
  },
  "indices": {
    "register": "Zindices.D"
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
TBL Zresult.D, {Zdata0.D, Zdata1.D}, Zindices.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/TBL--Programmable-table-lookup-in-one-or-two-vector-table--zeroing--

### Operation

Source operation ID: `SveOperation_svtbl2_bf16`

**Operation**



Concatenate the vectors in `data` together to form a double-length vector *v*.  Return a vector in which each element *i* contains:




- element `indices[i]` of *v* if 0 ≤ `indices[i]` < *n*, where *n* is the number of elements in *v*
- zero otherwise

## svtbl2[_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svtbl2%5B_s16%5D

### Signature (source notation)

```c
svint16_t svtbl2[_s16](svint16x2_t data, svuint16_t indices);
```

### Description

Table lookup in two-vector table

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Table lookups / Table lookup

- SME attributes: Not specified by source.

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
  "data": {
    "register": "{Zdata0.H, Zdata1.H}"
  },
  "indices": {
    "register": "Zindices.H"
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
TBL Zresult.H, {Zdata0.H, Zdata1.H}, Zindices.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/TBL--Programmable-table-lookup-in-one-or-two-vector-table--zeroing--

### Operation

Source operation ID: `SveOperation_svtbl2_bf16`

**Operation**



Concatenate the vectors in `data` together to form a double-length vector *v*.  Return a vector in which each element *i* contains:




- element `indices[i]` of *v* if 0 ≤ `indices[i]` < *n*, where *n* is the number of elements in *v*
- zero otherwise

## svtbl2[_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svtbl2%5B_s32%5D

### Signature (source notation)

```c
svint32_t svtbl2[_s32](svint32x2_t data, svuint32_t indices);
```

### Description

Table lookup in two-vector table

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Table lookups / Table lookup

- SME attributes: Not specified by source.

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
  "data": {
    "register": "{Zdata0.S, Zdata1.S}"
  },
  "indices": {
    "register": "Zindices.S"
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
TBL Zresult.S, {Zdata0.S, Zdata1.S}, Zindices.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/TBL--Programmable-table-lookup-in-one-or-two-vector-table--zeroing--

### Operation

Source operation ID: `SveOperation_svtbl2_bf16`

**Operation**



Concatenate the vectors in `data` together to form a double-length vector *v*.  Return a vector in which each element *i* contains:




- element `indices[i]` of *v* if 0 ≤ `indices[i]` < *n*, where *n* is the number of elements in *v*
- zero otherwise

## svtbl2[_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svtbl2%5B_s64%5D

### Signature (source notation)

```c
svint64_t svtbl2[_s64](svint64x2_t data, svuint64_t indices);
```

### Description

Table lookup in two-vector table

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Table lookups / Table lookup

- SME attributes: Not specified by source.

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
  "data": {
    "register": "{Zdata0.D, Zdata1.D}"
  },
  "indices": {
    "register": "Zindices.D"
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
TBL Zresult.D, {Zdata0.D, Zdata1.D}, Zindices.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/TBL--Programmable-table-lookup-in-one-or-two-vector-table--zeroing--

### Operation

Source operation ID: `SveOperation_svtbl2_bf16`

**Operation**



Concatenate the vectors in `data` together to form a double-length vector *v*.  Return a vector in which each element *i* contains:




- element `indices[i]` of *v* if 0 ≤ `indices[i]` < *n*, where *n* is the number of elements in *v*
- zero otherwise

## svtbl2[_s8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svtbl2%5B_s8%5D

### Signature (source notation)

```c
svint8_t svtbl2[_s8](svint8x2_t data, svuint8_t indices);
```

### Description

Table lookup in two-vector table

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Table lookups / Table lookup

- SME attributes: Not specified by source.

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
  "data": {
    "register": "{Zdata0.B, Zdata1.B}"
  },
  "indices": {
    "register": "Zindices.B"
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
TBL Zresult.B, {Zdata0.B, Zdata1.B}, Zindices.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/TBL--Programmable-table-lookup-in-one-or-two-vector-table--zeroing--

### Operation

Source operation ID: `SveOperation_svtbl2_bf16`

**Operation**



Concatenate the vectors in `data` together to form a double-length vector *v*.  Return a vector in which each element *i* contains:




- element `indices[i]` of *v* if 0 ≤ `indices[i]` < *n*, where *n* is the number of elements in *v*
- zero otherwise

## svtbl2[_u16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svtbl2%5B_u16%5D

### Signature (source notation)

```c
svuint16_t svtbl2[_u16](svuint16x2_t data, svuint16_t indices);
```

### Description

Table lookup in two-vector table

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Table lookups / Table lookup

- SME attributes: Not specified by source.

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
  "data": {
    "register": "{Zdata0.H, Zdata1.H}"
  },
  "indices": {
    "register": "Zindices.H"
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
TBL Zresult.H, {Zdata0.H, Zdata1.H}, Zindices.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/TBL--Programmable-table-lookup-in-one-or-two-vector-table--zeroing--

### Operation

Source operation ID: `SveOperation_svtbl2_bf16`

**Operation**



Concatenate the vectors in `data` together to form a double-length vector *v*.  Return a vector in which each element *i* contains:




- element `indices[i]` of *v* if 0 ≤ `indices[i]` < *n*, where *n* is the number of elements in *v*
- zero otherwise

## svtbl2[_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svtbl2%5B_u32%5D

### Signature (source notation)

```c
svuint32_t svtbl2[_u32](svuint32x2_t data, svuint32_t indices);
```

### Description

Table lookup in two-vector table

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Table lookups / Table lookup

- SME attributes: Not specified by source.

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
  "data": {
    "register": "{Zdata0.S, Zdata1.S}"
  },
  "indices": {
    "register": "Zindices.S"
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
TBL Zresult.S, {Zdata0.S, Zdata1.S}, Zindices.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/TBL--Programmable-table-lookup-in-one-or-two-vector-table--zeroing--

### Operation

Source operation ID: `SveOperation_svtbl2_bf16`

**Operation**



Concatenate the vectors in `data` together to form a double-length vector *v*.  Return a vector in which each element *i* contains:




- element `indices[i]` of *v* if 0 ≤ `indices[i]` < *n*, where *n* is the number of elements in *v*
- zero otherwise

## svtbl2[_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svtbl2%5B_u64%5D

### Signature (source notation)

```c
svuint64_t svtbl2[_u64](svuint64x2_t data, svuint64_t indices);
```

### Description

Table lookup in two-vector table

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Table lookups / Table lookup

- SME attributes: Not specified by source.

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
  "data": {
    "register": "{Zdata0.D, Zdata1.D}"
  },
  "indices": {
    "register": "Zindices.D"
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
TBL Zresult.D, {Zdata0.D, Zdata1.D}, Zindices.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/TBL--Programmable-table-lookup-in-one-or-two-vector-table--zeroing--

### Operation

Source operation ID: `SveOperation_svtbl2_bf16`

**Operation**



Concatenate the vectors in `data` together to form a double-length vector *v*.  Return a vector in which each element *i* contains:




- element `indices[i]` of *v* if 0 ≤ `indices[i]` < *n*, where *n* is the number of elements in *v*
- zero otherwise

## svtbl2[_u8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svtbl2%5B_u8%5D

### Signature (source notation)

```c
svuint8_t svtbl2[_u8](svuint8x2_t data, svuint8_t indices);
```

### Description

Table lookup in two-vector table

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Table lookups / Table lookup

- SME attributes: Not specified by source.

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
  "data": {
    "register": "{Zdata0.B, Zdata1.B}"
  },
  "indices": {
    "register": "Zindices.B"
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
TBL Zresult.B, {Zdata0.B, Zdata1.B}, Zindices.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/TBL--Programmable-table-lookup-in-one-or-two-vector-table--zeroing--

### Operation

Source operation ID: `SveOperation_svtbl2_bf16`

**Operation**



Concatenate the vectors in `data` together to form a double-length vector *v*.  Return a vector in which each element *i* contains:




- element `indices[i]` of *v* if 0 ≤ `indices[i]` < *n*, where *n* is the number of elements in *v*
- zero otherwise

## svtbl[_bf16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svtbl%5B_bf16%5D

### Signature (source notation)

```c
svbfloat16_t svtbl[_bf16](svbfloat16_t data, svuint16_t indices);
```

### Description

Table lookup in single-vector table

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Table lookups / Table lookup

- SME attributes: Not specified by source.

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
  "data": {
    "register": "Zdata.H"
  },
  "indices": {
    "register": "Zindices.H"
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
TBL Zresult.H, Zdata.H, Zindices.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/TBL--Programmable-table-lookup-in-one-or-two-vector-table--zeroing--

### Operation

Source operation ID: `SveOperation_svtbl_bf16`

**Operation**



Return a vector in which each element *i* contains:




- `data[indices[i]]` if 0 ≤ `indices[i]` < *n*, where *n* is the number of elements in `data`
- zero otherwise

## svtbl[_f16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svtbl%5B_f16%5D

### Signature (source notation)

```c
svfloat16_t svtbl[_f16](svfloat16_t data, svuint16_t indices);
```

### Description

Table lookup in single-vector table

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Table lookups / Table lookup

- SME attributes: Not specified by source.

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
  "data": {
    "register": "Zdata.H"
  },
  "indices": {
    "register": "Zindices.H"
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
TBL Zresult.H, Zdata.H, Zindices.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/TBL--Programmable-table-lookup-in-one-or-two-vector-table--zeroing--

### Operation

Source operation ID: `SveOperation_svtbl_bf16`

**Operation**



Return a vector in which each element *i* contains:




- `data[indices[i]]` if 0 ≤ `indices[i]` < *n*, where *n* is the number of elements in `data`
- zero otherwise

## svtbl[_f32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svtbl%5B_f32%5D

### Signature (source notation)

```c
svfloat32_t svtbl[_f32](svfloat32_t data, svuint32_t indices);
```

### Description

Table lookup in single-vector table

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Table lookups / Table lookup

- SME attributes: Not specified by source.

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
  "data": {
    "register": "Zdata.S"
  },
  "indices": {
    "register": "Zindices.S"
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
TBL Zresult.S, Zdata.S, Zindices.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/TBL--Programmable-table-lookup-in-one-or-two-vector-table--zeroing--

### Operation

Source operation ID: `SveOperation_svtbl_bf16`

**Operation**



Return a vector in which each element *i* contains:




- `data[indices[i]]` if 0 ≤ `indices[i]` < *n*, where *n* is the number of elements in `data`
- zero otherwise

## svtbl[_f64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svtbl%5B_f64%5D

### Signature (source notation)

```c
svfloat64_t svtbl[_f64](svfloat64_t data, svuint64_t indices);
```

### Description

Table lookup in single-vector table

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Table lookups / Table lookup

- SME attributes: Not specified by source.

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
  "data": {
    "register": "Zdata.D"
  },
  "indices": {
    "register": "Zindices.D"
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
TBL Zresult.D, Zdata.D, Zindices.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/TBL--Programmable-table-lookup-in-one-or-two-vector-table--zeroing--

### Operation

Source operation ID: `SveOperation_svtbl_bf16`

**Operation**



Return a vector in which each element *i* contains:




- `data[indices[i]]` if 0 ≤ `indices[i]` < *n*, where *n* is the number of elements in `data`
- zero otherwise

## svtbl[_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svtbl%5B_s16%5D

### Signature (source notation)

```c
svint16_t svtbl[_s16](svint16_t data, svuint16_t indices);
```

### Description

Table lookup in single-vector table

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Table lookups / Table lookup

- SME attributes: Not specified by source.

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
  "data": {
    "register": "Zdata.H"
  },
  "indices": {
    "register": "Zindices.H"
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
TBL Zresult.H, Zdata.H, Zindices.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/TBL--Programmable-table-lookup-in-one-or-two-vector-table--zeroing--

### Operation

Source operation ID: `SveOperation_svtbl_bf16`

**Operation**



Return a vector in which each element *i* contains:




- `data[indices[i]]` if 0 ≤ `indices[i]` < *n*, where *n* is the number of elements in `data`
- zero otherwise

## svtbl[_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svtbl%5B_s32%5D

### Signature (source notation)

```c
svint32_t svtbl[_s32](svint32_t data, svuint32_t indices);
```

### Description

Table lookup in single-vector table

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Table lookups / Table lookup

- SME attributes: Not specified by source.

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
  "data": {
    "register": "Zdata.S"
  },
  "indices": {
    "register": "Zindices.S"
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
TBL Zresult.S, Zdata.S, Zindices.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/TBL--Programmable-table-lookup-in-one-or-two-vector-table--zeroing--

### Operation

Source operation ID: `SveOperation_svtbl_bf16`

**Operation**



Return a vector in which each element *i* contains:




- `data[indices[i]]` if 0 ≤ `indices[i]` < *n*, where *n* is the number of elements in `data`
- zero otherwise

## svtbl[_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svtbl%5B_s64%5D

### Signature (source notation)

```c
svint64_t svtbl[_s64](svint64_t data, svuint64_t indices);
```

### Description

Table lookup in single-vector table

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Table lookups / Table lookup

- SME attributes: Not specified by source.

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
  "data": {
    "register": "Zdata.D"
  },
  "indices": {
    "register": "Zindices.D"
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
TBL Zresult.D, Zdata.D, Zindices.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/TBL--Programmable-table-lookup-in-one-or-two-vector-table--zeroing--

### Operation

Source operation ID: `SveOperation_svtbl_bf16`

**Operation**



Return a vector in which each element *i* contains:




- `data[indices[i]]` if 0 ≤ `indices[i]` < *n*, where *n* is the number of elements in `data`
- zero otherwise

## svtbl[_s8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svtbl%5B_s8%5D

### Signature (source notation)

```c
svint8_t svtbl[_s8](svint8_t data, svuint8_t indices);
```

### Description

Table lookup in single-vector table

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Table lookups / Table lookup

- SME attributes: Not specified by source.

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
  "data": {
    "register": "Zdata.B"
  },
  "indices": {
    "register": "Zindices.B"
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
TBL Zresult.B, Zdata.B, Zindices.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/TBL--Programmable-table-lookup-in-one-or-two-vector-table--zeroing--

### Operation

Source operation ID: `SveOperation_svtbl_bf16`

**Operation**



Return a vector in which each element *i* contains:




- `data[indices[i]]` if 0 ≤ `indices[i]` < *n*, where *n* is the number of elements in `data`
- zero otherwise

## svtbl[_u16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svtbl%5B_u16%5D

### Signature (source notation)

```c
svuint16_t svtbl[_u16](svuint16_t data, svuint16_t indices);
```

### Description

Table lookup in single-vector table

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Table lookups / Table lookup

- SME attributes: Not specified by source.

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
  "data": {
    "register": "Zdata.H"
  },
  "indices": {
    "register": "Zindices.H"
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
TBL Zresult.H, Zdata.H, Zindices.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/TBL--Programmable-table-lookup-in-one-or-two-vector-table--zeroing--

### Operation

Source operation ID: `SveOperation_svtbl_bf16`

**Operation**



Return a vector in which each element *i* contains:




- `data[indices[i]]` if 0 ≤ `indices[i]` < *n*, where *n* is the number of elements in `data`
- zero otherwise

## svtbl[_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svtbl%5B_u32%5D

### Signature (source notation)

```c
svuint32_t svtbl[_u32](svuint32_t data, svuint32_t indices);
```

### Description

Table lookup in single-vector table

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Table lookups / Table lookup

- SME attributes: Not specified by source.

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
  "data": {
    "register": "Zdata.S"
  },
  "indices": {
    "register": "Zindices.S"
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
TBL Zresult.S, Zdata.S, Zindices.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/TBL--Programmable-table-lookup-in-one-or-two-vector-table--zeroing--

### Operation

Source operation ID: `SveOperation_svtbl_bf16`

**Operation**



Return a vector in which each element *i* contains:




- `data[indices[i]]` if 0 ≤ `indices[i]` < *n*, where *n* is the number of elements in `data`
- zero otherwise

## svtbl[_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svtbl%5B_u64%5D

### Signature (source notation)

```c
svuint64_t svtbl[_u64](svuint64_t data, svuint64_t indices);
```

### Description

Table lookup in single-vector table

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Table lookups / Table lookup

- SME attributes: Not specified by source.

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
  "data": {
    "register": "Zdata.D"
  },
  "indices": {
    "register": "Zindices.D"
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
TBL Zresult.D, Zdata.D, Zindices.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/TBL--Programmable-table-lookup-in-one-or-two-vector-table--zeroing--

### Operation

Source operation ID: `SveOperation_svtbl_bf16`

**Operation**



Return a vector in which each element *i* contains:




- `data[indices[i]]` if 0 ≤ `indices[i]` < *n*, where *n* is the number of elements in `data`
- zero otherwise

## svtbl[_u8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svtbl%5B_u8%5D

### Signature (source notation)

```c
svuint8_t svtbl[_u8](svuint8_t data, svuint8_t indices);
```

### Description

Table lookup in single-vector table

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Table lookups / Table lookup

- SME attributes: Not specified by source.

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
  "data": {
    "register": "Zdata.B"
  },
  "indices": {
    "register": "Zindices.B"
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
TBL Zresult.B, Zdata.B, Zindices.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/TBL--Programmable-table-lookup-in-one-or-two-vector-table--zeroing--

### Operation

Source operation ID: `SveOperation_svtbl_bf16`

**Operation**



Return a vector in which each element *i* contains:




- `data[indices[i]]` if 0 ≤ `indices[i]` < *n*, where *n* is the number of elements in `data`
- zero otherwise

## svtblq[_bf16]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svtblq%5B_bf16%5D

### Signature (source notation)

```c
svbfloat16_t svtblq[_bf16](svbfloat16_t zn, svuint16_t zm);
```

### Description

Programmable table lookup within each quadword vector segment (zeroing)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Table lookups / Table lookup

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p1)|FEAT_SME2p1
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
  "zn": {
    "register": "Zreg2.H"
  },
  "zm": {
    "register": "Zreg3.H"
  }
}
```

### Result mapping

```json
[
  {
    "Zreg1.H": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
TBLQ Zreg1.H, { Zreg2.H }, Zreg3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/TBLQ--Programmable-table-lookup-within-each-quadword-vector-segment--zeroing--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svtblq[_f16]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svtblq%5B_f16%5D

### Signature (source notation)

```c
svfloat16_t svtblq[_f16](svfloat16_t zn, svuint16_t zm);
```

### Description

Programmable table lookup within each quadword vector segment (zeroing)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Table lookups / Table lookup

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p1)|FEAT_SME2p1
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
  "zn": {
    "register": "Zreg2.H"
  },
  "zm": {
    "register": "Zreg3.H"
  }
}
```

### Result mapping

```json
[
  {
    "Zreg1.H": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
TBLQ Zreg1.H, { Zreg2.H }, Zreg3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/TBLQ--Programmable-table-lookup-within-each-quadword-vector-segment--zeroing--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svtblq[_f32]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svtblq%5B_f32%5D

### Signature (source notation)

```c
svfloat32_t svtblq[_f32](svfloat32_t zn, svuint32_t zm);
```

### Description

Programmable table lookup within each quadword vector segment (zeroing)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Table lookups / Table lookup

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p1)|FEAT_SME2p1
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
  "zn": {
    "register": "Zreg2.S"
  },
  "zm": {
    "register": "Zreg3.S"
  }
}
```

### Result mapping

```json
[
  {
    "Zreg1.S": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
TBLQ Zreg1.S, { Zreg2.S }, Zreg3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/TBLQ--Programmable-table-lookup-within-each-quadword-vector-segment--zeroing--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svtblq[_f64]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svtblq%5B_f64%5D

### Signature (source notation)

```c
svfloat64_t svtblq[_f64](svfloat64_t zn, svuint64_t zm);
```

### Description

Programmable table lookup within each quadword vector segment (zeroing)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Table lookups / Table lookup

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p1)|FEAT_SME2p1
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
  "zn": {
    "register": "Zreg2.D"
  },
  "zm": {
    "register": "Zreg3.D"
  }
}
```

### Result mapping

```json
[
  {
    "Zreg1.D": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
TBLQ Zreg1.D, { Zreg2.D }, Zreg3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/TBLQ--Programmable-table-lookup-within-each-quadword-vector-segment--zeroing--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svtblq[_mf8]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svtblq%5B_mf8%5D

### Signature (source notation)

```c
svmfloat8_t svtblq[_mf8](svmfloat8_t zn, svuint8_t zm);
```

### Description

Programmable table lookup within each quadword vector segment (zeroing)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Table lookups / Table lookup

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p1)|FEAT_SME2p1
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
  "zn": {
    "register": "Zreg2.B"
  },
  "zm": {
    "register": "Zreg3.B"
  }
}
```

### Result mapping

```json
[
  {
    "Zreg1.B": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
TBLQ Zreg1.B, { Zreg2.B }, Zreg3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/TBLQ--Programmable-table-lookup-within-each-quadword-vector-segment--zeroing--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svtblq[_s16]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svtblq%5B_s16%5D

### Signature (source notation)

```c
svint16_t svtblq[_s16](svint16_t zn, svuint16_t zm);
```

### Description

Programmable table lookup within each quadword vector segment (zeroing)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Table lookups / Table lookup

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p1)|FEAT_SME2p1
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
  "zn": {
    "register": "Zreg2.H"
  },
  "zm": {
    "register": "Zreg3.H"
  }
}
```

### Result mapping

```json
[
  {
    "Zreg1.H": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
TBLQ Zreg1.H, { Zreg2.H }, Zreg3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/TBLQ--Programmable-table-lookup-within-each-quadword-vector-segment--zeroing--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svtblq[_s32]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svtblq%5B_s32%5D

### Signature (source notation)

```c
svint32_t svtblq[_s32](svint32_t zn, svuint32_t zm);
```

### Description

Programmable table lookup within each quadword vector segment (zeroing)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Table lookups / Table lookup

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p1)|FEAT_SME2p1
```

### Return type metadata

```json
{
  "return_base_type": "int32",
  "element_bit_size": "32",
  "value": "svint32_t"
}
```

### Argument preparation and constraints

```json
{
  "zn": {
    "register": "Zreg2.S"
  },
  "zm": {
    "register": "Zreg3.S"
  }
}
```

### Result mapping

```json
[
  {
    "Zreg1.S": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
TBLQ Zreg1.S, { Zreg2.S }, Zreg3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/TBLQ--Programmable-table-lookup-within-each-quadword-vector-segment--zeroing--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svtblq[_s64]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svtblq%5B_s64%5D

### Signature (source notation)

```c
svint64_t svtblq[_s64](svint64_t zn, svuint64_t zm);
```

### Description

Programmable table lookup within each quadword vector segment (zeroing)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Table lookups / Table lookup

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p1)|FEAT_SME2p1
```

### Return type metadata

```json
{
  "return_base_type": "int64",
  "element_bit_size": "64",
  "value": "svint64_t"
}
```

### Argument preparation and constraints

```json
{
  "zn": {
    "register": "Zreg2.D"
  },
  "zm": {
    "register": "Zreg3.D"
  }
}
```

### Result mapping

```json
[
  {
    "Zreg1.D": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
TBLQ Zreg1.D, { Zreg2.D }, Zreg3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/TBLQ--Programmable-table-lookup-within-each-quadword-vector-segment--zeroing--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svtblq[_s8]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svtblq%5B_s8%5D

### Signature (source notation)

```c
svint8_t svtblq[_s8](svint8_t zn, svuint8_t zm);
```

### Description

Programmable table lookup within each quadword vector segment (zeroing)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Table lookups / Table lookup

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p1)|FEAT_SME2p1
```

### Return type metadata

```json
{
  "return_base_type": "int8",
  "element_bit_size": "8",
  "value": "svint8_t"
}
```

### Argument preparation and constraints

```json
{
  "zn": {
    "register": "Zreg2.B"
  },
  "zm": {
    "register": "Zreg3.B"
  }
}
```

### Result mapping

```json
[
  {
    "Zreg1.B": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
TBLQ Zreg1.B, { Zreg2.B }, Zreg3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/TBLQ--Programmable-table-lookup-within-each-quadword-vector-segment--zeroing--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svtblq[_u16]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svtblq%5B_u16%5D

### Signature (source notation)

```c
svuint16_t svtblq[_u16](svuint16_t zn, svuint16_t zm);
```

### Description

Programmable table lookup within each quadword vector segment (zeroing)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Table lookups / Table lookup

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p1)|FEAT_SME2p1
```

### Return type metadata

```json
{
  "return_base_type": "uint16",
  "element_bit_size": "16",
  "value": "svuint16_t"
}
```

### Argument preparation and constraints

```json
{
  "zn": {
    "register": "Zreg2.H"
  },
  "zm": {
    "register": "Zreg3.H"
  }
}
```

### Result mapping

```json
[
  {
    "Zreg1.H": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
TBLQ Zreg1.H, { Zreg2.H }, Zreg3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/TBLQ--Programmable-table-lookup-within-each-quadword-vector-segment--zeroing--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svtblq[_u32]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svtblq%5B_u32%5D

### Signature (source notation)

```c
svuint32_t svtblq[_u32](svuint32_t zn, svuint32_t zm);
```

### Description

Programmable table lookup within each quadword vector segment (zeroing)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Table lookups / Table lookup

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p1)|FEAT_SME2p1
```

### Return type metadata

```json
{
  "return_base_type": "uint32",
  "element_bit_size": "32",
  "value": "svuint32_t"
}
```

### Argument preparation and constraints

```json
{
  "zn": {
    "register": "Zreg2.S"
  },
  "zm": {
    "register": "Zreg3.S"
  }
}
```

### Result mapping

```json
[
  {
    "Zreg1.S": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
TBLQ Zreg1.S, { Zreg2.S }, Zreg3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/TBLQ--Programmable-table-lookup-within-each-quadword-vector-segment--zeroing--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svtblq[_u64]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svtblq%5B_u64%5D

### Signature (source notation)

```c
svuint64_t svtblq[_u64](svuint64_t zn, svuint64_t zm);
```

### Description

Programmable table lookup within each quadword vector segment (zeroing)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Table lookups / Table lookup

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p1)|FEAT_SME2p1
```

### Return type metadata

```json
{
  "return_base_type": "uint64",
  "element_bit_size": "64",
  "value": "svuint64_t"
}
```

### Argument preparation and constraints

```json
{
  "zn": {
    "register": "Zreg2.D"
  },
  "zm": {
    "register": "Zreg3.D"
  }
}
```

### Result mapping

```json
[
  {
    "Zreg1.D": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
TBLQ Zreg1.D, { Zreg2.D }, Zreg3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/TBLQ--Programmable-table-lookup-within-each-quadword-vector-segment--zeroing--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svtblq[_u8]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svtblq%5B_u8%5D

### Signature (source notation)

```c
svuint8_t svtblq[_u8](svuint8_t zn, svuint8_t zm);
```

### Description

Programmable table lookup within each quadword vector segment (zeroing)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Table lookups / Table lookup

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p1)|FEAT_SME2p1
```

### Return type metadata

```json
{
  "return_base_type": "uint8",
  "element_bit_size": "8",
  "value": "svuint8_t"
}
```

### Argument preparation and constraints

```json
{
  "zn": {
    "register": "Zreg2.B"
  },
  "zm": {
    "register": "Zreg3.B"
  }
}
```

### Result mapping

```json
[
  {
    "Zreg1.B": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
TBLQ Zreg1.B, { Zreg2.B }, Zreg3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/TBLQ--Programmable-table-lookup-within-each-quadword-vector-segment--zeroing--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

