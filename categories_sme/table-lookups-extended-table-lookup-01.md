# SME / Table lookups / Extended table lookup — Part 1

## svtbx[_bf16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svtbx%5B_bf16%5D

### Signature (source notation)

```c
svbfloat16_t svtbx[_bf16](svbfloat16_t fallback, svbfloat16_t data, svuint16_t indices);
```

### Description

Table lookup in single-vector table (merging)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Table lookups / Extended table lookup

- SME attributes: Not specified by source.

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
  "fallback": {
    "register": "Ztied.H"
  },
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
    "Ztied.H": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
TBX Ztied.H, Zdata.H, Zindices.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/TBX--Programmable-table-lookup-in-single-vector-table--merging--

### Operation

Source operation ID: `SveOperation_svtbx_bf16`

**Operation**



Return a vector in which each element *i* contains:




- `data[indices[i]]` if 0 ≤ `indices[i]` < *n*, where *n* is the number of elements in `data`
- `fallback[i]` otherwise

## svtbx[_f16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svtbx%5B_f16%5D

### Signature (source notation)

```c
svfloat16_t svtbx[_f16](svfloat16_t fallback, svfloat16_t data, svuint16_t indices);
```

### Description

Table lookup in single-vector table (merging)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Table lookups / Extended table lookup

- SME attributes: Not specified by source.

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
  "fallback": {
    "register": "Ztied.H"
  },
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
    "Ztied.H": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
TBX Ztied.H, Zdata.H, Zindices.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/TBX--Programmable-table-lookup-in-single-vector-table--merging--

### Operation

Source operation ID: `SveOperation_svtbx_bf16`

**Operation**



Return a vector in which each element *i* contains:




- `data[indices[i]]` if 0 ≤ `indices[i]` < *n*, where *n* is the number of elements in `data`
- `fallback[i]` otherwise

## svtbx[_f32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svtbx%5B_f32%5D

### Signature (source notation)

```c
svfloat32_t svtbx[_f32](svfloat32_t fallback, svfloat32_t data, svuint32_t indices);
```

### Description

Table lookup in single-vector table (merging)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Table lookups / Extended table lookup

- SME attributes: Not specified by source.

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
  "fallback": {
    "register": "Ztied.S"
  },
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
    "Ztied.S": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
TBX Ztied.S, Zdata.S, Zindices.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/TBX--Programmable-table-lookup-in-single-vector-table--merging--

### Operation

Source operation ID: `SveOperation_svtbx_bf16`

**Operation**



Return a vector in which each element *i* contains:




- `data[indices[i]]` if 0 ≤ `indices[i]` < *n*, where *n* is the number of elements in `data`
- `fallback[i]` otherwise

## svtbx[_f64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svtbx%5B_f64%5D

### Signature (source notation)

```c
svfloat64_t svtbx[_f64](svfloat64_t fallback, svfloat64_t data, svuint64_t indices);
```

### Description

Table lookup in single-vector table (merging)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Table lookups / Extended table lookup

- SME attributes: Not specified by source.

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
  "fallback": {
    "register": "Ztied.D"
  },
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
    "Ztied.D": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
TBX Ztied.D, Zdata.D, Zindices.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/TBX--Programmable-table-lookup-in-single-vector-table--merging--

### Operation

Source operation ID: `SveOperation_svtbx_bf16`

**Operation**



Return a vector in which each element *i* contains:




- `data[indices[i]]` if 0 ≤ `indices[i]` < *n*, where *n* is the number of elements in `data`
- `fallback[i]` otherwise

## svtbx[_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svtbx%5B_s16%5D

### Signature (source notation)

```c
svint16_t svtbx[_s16](svint16_t fallback, svint16_t data, svuint16_t indices);
```

### Description

Table lookup in single-vector table (merging)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Table lookups / Extended table lookup

- SME attributes: Not specified by source.

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
  "fallback": {
    "register": "Ztied.H"
  },
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
    "Ztied.H": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
TBX Ztied.H, Zdata.H, Zindices.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/TBX--Programmable-table-lookup-in-single-vector-table--merging--

### Operation

Source operation ID: `SveOperation_svtbx_bf16`

**Operation**



Return a vector in which each element *i* contains:




- `data[indices[i]]` if 0 ≤ `indices[i]` < *n*, where *n* is the number of elements in `data`
- `fallback[i]` otherwise

## svtbx[_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svtbx%5B_s32%5D

### Signature (source notation)

```c
svint32_t svtbx[_s32](svint32_t fallback, svint32_t data, svuint32_t indices);
```

### Description

Table lookup in single-vector table (merging)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Table lookups / Extended table lookup

- SME attributes: Not specified by source.

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
  "fallback": {
    "register": "Ztied.S"
  },
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
    "Ztied.S": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
TBX Ztied.S, Zdata.S, Zindices.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/TBX--Programmable-table-lookup-in-single-vector-table--merging--

### Operation

Source operation ID: `SveOperation_svtbx_bf16`

**Operation**



Return a vector in which each element *i* contains:




- `data[indices[i]]` if 0 ≤ `indices[i]` < *n*, where *n* is the number of elements in `data`
- `fallback[i]` otherwise

## svtbx[_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svtbx%5B_s64%5D

### Signature (source notation)

```c
svint64_t svtbx[_s64](svint64_t fallback, svint64_t data, svuint64_t indices);
```

### Description

Table lookup in single-vector table (merging)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Table lookups / Extended table lookup

- SME attributes: Not specified by source.

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
  "fallback": {
    "register": "Ztied.D"
  },
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
    "Ztied.D": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
TBX Ztied.D, Zdata.D, Zindices.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/TBX--Programmable-table-lookup-in-single-vector-table--merging--

### Operation

Source operation ID: `SveOperation_svtbx_bf16`

**Operation**



Return a vector in which each element *i* contains:




- `data[indices[i]]` if 0 ≤ `indices[i]` < *n*, where *n* is the number of elements in `data`
- `fallback[i]` otherwise

## svtbx[_s8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svtbx%5B_s8%5D

### Signature (source notation)

```c
svint8_t svtbx[_s8](svint8_t fallback, svint8_t data, svuint8_t indices);
```

### Description

Table lookup in single-vector table (merging)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Table lookups / Extended table lookup

- SME attributes: Not specified by source.

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
  "fallback": {
    "register": "Ztied.B"
  },
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
    "Ztied.B": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
TBX Ztied.B, Zdata.B, Zindices.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/TBX--Programmable-table-lookup-in-single-vector-table--merging--

### Operation

Source operation ID: `SveOperation_svtbx_bf16`

**Operation**



Return a vector in which each element *i* contains:




- `data[indices[i]]` if 0 ≤ `indices[i]` < *n*, where *n* is the number of elements in `data`
- `fallback[i]` otherwise

## svtbx[_u16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svtbx%5B_u16%5D

### Signature (source notation)

```c
svuint16_t svtbx[_u16](svuint16_t fallback, svuint16_t data, svuint16_t indices);
```

### Description

Table lookup in single-vector table (merging)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Table lookups / Extended table lookup

- SME attributes: Not specified by source.

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
  "fallback": {
    "register": "Ztied.H"
  },
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
    "Ztied.H": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
TBX Ztied.H, Zdata.H, Zindices.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/TBX--Programmable-table-lookup-in-single-vector-table--merging--

### Operation

Source operation ID: `SveOperation_svtbx_bf16`

**Operation**



Return a vector in which each element *i* contains:




- `data[indices[i]]` if 0 ≤ `indices[i]` < *n*, where *n* is the number of elements in `data`
- `fallback[i]` otherwise

## svtbx[_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svtbx%5B_u32%5D

### Signature (source notation)

```c
svuint32_t svtbx[_u32](svuint32_t fallback, svuint32_t data, svuint32_t indices);
```

### Description

Table lookup in single-vector table (merging)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Table lookups / Extended table lookup

- SME attributes: Not specified by source.

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
  "fallback": {
    "register": "Ztied.S"
  },
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
    "Ztied.S": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
TBX Ztied.S, Zdata.S, Zindices.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/TBX--Programmable-table-lookup-in-single-vector-table--merging--

### Operation

Source operation ID: `SveOperation_svtbx_bf16`

**Operation**



Return a vector in which each element *i* contains:




- `data[indices[i]]` if 0 ≤ `indices[i]` < *n*, where *n* is the number of elements in `data`
- `fallback[i]` otherwise

## svtbx[_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svtbx%5B_u64%5D

### Signature (source notation)

```c
svuint64_t svtbx[_u64](svuint64_t fallback, svuint64_t data, svuint64_t indices);
```

### Description

Table lookup in single-vector table (merging)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Table lookups / Extended table lookup

- SME attributes: Not specified by source.

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
  "fallback": {
    "register": "Ztied.D"
  },
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
    "Ztied.D": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
TBX Ztied.D, Zdata.D, Zindices.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/TBX--Programmable-table-lookup-in-single-vector-table--merging--

### Operation

Source operation ID: `SveOperation_svtbx_bf16`

**Operation**



Return a vector in which each element *i* contains:




- `data[indices[i]]` if 0 ≤ `indices[i]` < *n*, where *n* is the number of elements in `data`
- `fallback[i]` otherwise

## svtbx[_u8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svtbx%5B_u8%5D

### Signature (source notation)

```c
svuint8_t svtbx[_u8](svuint8_t fallback, svuint8_t data, svuint8_t indices);
```

### Description

Table lookup in single-vector table (merging)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Table lookups / Extended table lookup

- SME attributes: Not specified by source.

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
  "fallback": {
    "register": "Ztied.B"
  },
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
    "Ztied.B": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
TBX Ztied.B, Zdata.B, Zindices.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/TBX--Programmable-table-lookup-in-single-vector-table--merging--

### Operation

Source operation ID: `SveOperation_svtbx_bf16`

**Operation**



Return a vector in which each element *i* contains:




- `data[indices[i]]` if 0 ≤ `indices[i]` < *n*, where *n* is the number of elements in `data`
- `fallback[i]` otherwise

## svtbxq[_bf16]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svtbxq%5B_bf16%5D

### Signature (source notation)

```c
svbfloat16_t svtbxq[_bf16](svbfloat16_t fallback, svbfloat16_t zn, svuint16_t zm);
```

### Description

Programmable table lookup within each quadword vector segment (merging)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Table lookups / Extended table lookup

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
  "fallback": {
    "register": "Zreg1.H"
  },
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
TBXQ Zreg1.H, Zreg2.H, Zreg3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/TBXQ--Programmable-table-lookup-within-each-quadword-vector-segment--merging--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svtbxq[_f16]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svtbxq%5B_f16%5D

### Signature (source notation)

```c
svfloat16_t svtbxq[_f16](svfloat16_t fallback, svfloat16_t zn, svuint16_t zm);
```

### Description

Programmable table lookup within each quadword vector segment (merging)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Table lookups / Extended table lookup

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
  "fallback": {
    "register": "Zreg1.H"
  },
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
TBXQ Zreg1.H, Zreg2.H, Zreg3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/TBXQ--Programmable-table-lookup-within-each-quadword-vector-segment--merging--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svtbxq[_f32]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svtbxq%5B_f32%5D

### Signature (source notation)

```c
svfloat32_t svtbxq[_f32](svfloat32_t fallback, svfloat32_t zn, svuint32_t zm);
```

### Description

Programmable table lookup within each quadword vector segment (merging)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Table lookups / Extended table lookup

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
  "fallback": {
    "register": "Zreg1.S"
  },
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
TBXQ Zreg1.S, Zreg2.S, Zreg3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/TBXQ--Programmable-table-lookup-within-each-quadword-vector-segment--merging--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svtbxq[_f64]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svtbxq%5B_f64%5D

### Signature (source notation)

```c
svfloat64_t svtbxq[_f64](svfloat64_t fallback, svfloat64_t zn, svuint64_t zm);
```

### Description

Programmable table lookup within each quadword vector segment (merging)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Table lookups / Extended table lookup

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
  "fallback": {
    "register": "Zreg1.D"
  },
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
TBXQ Zreg1.D, Zreg2.D, Zreg3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/TBXQ--Programmable-table-lookup-within-each-quadword-vector-segment--merging--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svtbxq[_mf8]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svtbxq%5B_mf8%5D

### Signature (source notation)

```c
svmfloat8_t svtbxq[_mf8](svmfloat8_t fallback, svmfloat8_t zn, svuint8_t zm);
```

### Description

Programmable table lookup within each quadword vector segment (merging)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Table lookups / Extended table lookup

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
  "fallback": {
    "register": "Zreg1.B"
  },
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
TBXQ Zreg1.B, Zreg2.B, Zreg3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/TBXQ--Programmable-table-lookup-within-each-quadword-vector-segment--merging--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svtbxq[_s16]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svtbxq%5B_s16%5D

### Signature (source notation)

```c
svint16_t svtbxq[_s16](svint16_t fallback, svint16_t zn, svuint16_t zm);
```

### Description

Programmable table lookup within each quadword vector segment (merging)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Table lookups / Extended table lookup

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
  "fallback": {
    "register": "Zreg1.H"
  },
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
TBXQ Zreg1.H, Zreg2.H, Zreg3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/TBXQ--Programmable-table-lookup-within-each-quadword-vector-segment--merging--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svtbxq[_s32]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svtbxq%5B_s32%5D

### Signature (source notation)

```c
svint32_t svtbxq[_s32](svint32_t fallback, svint32_t zn, svuint32_t zm);
```

### Description

Programmable table lookup within each quadword vector segment (merging)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Table lookups / Extended table lookup

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
  "fallback": {
    "register": "Zreg1.S"
  },
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
TBXQ Zreg1.S, Zreg2.S, Zreg3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/TBXQ--Programmable-table-lookup-within-each-quadword-vector-segment--merging--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svtbxq[_s64]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svtbxq%5B_s64%5D

### Signature (source notation)

```c
svint64_t svtbxq[_s64](svint64_t fallback, svint64_t zn, svuint64_t zm);
```

### Description

Programmable table lookup within each quadword vector segment (merging)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Table lookups / Extended table lookup

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
  "fallback": {
    "register": "Zreg1.D"
  },
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
TBXQ Zreg1.D, Zreg2.D, Zreg3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/TBXQ--Programmable-table-lookup-within-each-quadword-vector-segment--merging--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svtbxq[_s8]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svtbxq%5B_s8%5D

### Signature (source notation)

```c
svint8_t svtbxq[_s8](svint8_t fallback, svint8_t zn, svuint8_t zm);
```

### Description

Programmable table lookup within each quadword vector segment (merging)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Table lookups / Extended table lookup

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
  "fallback": {
    "register": "Zreg1.B"
  },
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
TBXQ Zreg1.B, Zreg2.B, Zreg3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/TBXQ--Programmable-table-lookup-within-each-quadword-vector-segment--merging--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svtbxq[_u16]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svtbxq%5B_u16%5D

### Signature (source notation)

```c
svuint16_t svtbxq[_u16](svuint16_t fallback, svuint16_t zn, svuint16_t zm);
```

### Description

Programmable table lookup within each quadword vector segment (merging)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Table lookups / Extended table lookup

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
  "fallback": {
    "register": "Zreg1.H"
  },
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
TBXQ Zreg1.H, Zreg2.H, Zreg3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/TBXQ--Programmable-table-lookup-within-each-quadword-vector-segment--merging--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svtbxq[_u32]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svtbxq%5B_u32%5D

### Signature (source notation)

```c
svuint32_t svtbxq[_u32](svuint32_t fallback, svuint32_t zn, svuint32_t zm);
```

### Description

Programmable table lookup within each quadword vector segment (merging)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Table lookups / Extended table lookup

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
  "fallback": {
    "register": "Zreg1.S"
  },
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
TBXQ Zreg1.S, Zreg2.S, Zreg3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/TBXQ--Programmable-table-lookup-within-each-quadword-vector-segment--merging--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svtbxq[_u64]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svtbxq%5B_u64%5D

### Signature (source notation)

```c
svuint64_t svtbxq[_u64](svuint64_t fallback, svuint64_t zn, svuint64_t zm);
```

### Description

Programmable table lookup within each quadword vector segment (merging)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Table lookups / Extended table lookup

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
  "fallback": {
    "register": "Zreg1.D"
  },
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
TBXQ Zreg1.D, Zreg2.D, Zreg3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/TBXQ--Programmable-table-lookup-within-each-quadword-vector-segment--merging--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svtbxq[_u8]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svtbxq%5B_u8%5D

### Signature (source notation)

```c
svuint8_t svtbxq[_u8](svuint8_t fallback, svuint8_t zn, svuint8_t zm);
```

### Description

Programmable table lookup within each quadword vector segment (merging)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Table lookups / Extended table lookup

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
  "fallback": {
    "register": "Zreg1.B"
  },
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
TBXQ Zreg1.B, Zreg2.B, Zreg3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/TBXQ--Programmable-table-lookup-within-each-quadword-vector-segment--merging--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

