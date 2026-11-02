# SME / Vector manipulation / Set all lanes to the same value — Part 2

## svdup_lane[_f32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdup_lane%5B_f32%5D

### Signature (source notation)

```c
svfloat32_t svdup_lane[_f32](svfloat32_t data, uint32_t index);
```

### Description

Broadcast a scalar value

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Set all lanes to the same value

- SME attributes: Not specified by source.

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
  "index": {
    "register": "Zindex.S[*]"
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

When index is in the range [0, 15], this intrinsic can use:

```asm
DUP Zresult.S, Zdata.S[index]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/DUP--indexed---Broadcast-indexed-element-to-vector--unpredicated--

The general implementation is:

```asm
TBL Zresult.S, Zdata.S, Zindex.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/TBL--Programmable-table-lookup-in-one-or-two-vector-table--zeroing--

### Operation

Source operation ID: `SveOperation_svdup_lane_bf16`

**Operation**



If `index` is less than the number of elements in `data`, return a vector in which every element contains `data[index]`.  Return an all-zeros vector otherwise.

## svdup_lane[_f64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdup_lane%5B_f64%5D

### Signature (source notation)

```c
svfloat64_t svdup_lane[_f64](svfloat64_t data, uint64_t index);
```

### Description

Broadcast a scalar value

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Set all lanes to the same value

- SME attributes: Not specified by source.

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
  "index": {
    "register": "Zindex.D[*]"
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

When index is in the range [0, 7], this intrinsic can use:

```asm
DUP Zresult.D, Zdata.D[index]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/DUP--indexed---Broadcast-indexed-element-to-vector--unpredicated--

The general implementation is:

```asm
TBL Zresult.D, Zdata.D, Zindex.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/TBL--Programmable-table-lookup-in-one-or-two-vector-table--zeroing--

### Operation

Source operation ID: `SveOperation_svdup_lane_bf16`

**Operation**



If `index` is less than the number of elements in `data`, return a vector in which every element contains `data[index]`.  Return an all-zeros vector otherwise.

## svdup_lane[_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdup_lane%5B_s16%5D

### Signature (source notation)

```c
svint16_t svdup_lane[_s16](svint16_t data, uint16_t index);
```

### Description

Broadcast a scalar value

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Set all lanes to the same value

- SME attributes: Not specified by source.

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
  "index": {
    "register": "Zindex.H[*]"
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

When index is in the range [0, 31], this intrinsic can use:

```asm
DUP Zresult.H, Zdata.H[index]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/DUP--indexed---Broadcast-indexed-element-to-vector--unpredicated--

The general implementation is:

```asm
TBL Zresult.H, Zdata.H, Zindex.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/TBL--Programmable-table-lookup-in-one-or-two-vector-table--zeroing--

### Operation

Source operation ID: `SveOperation_svdup_lane_bf16`

**Operation**



If `index` is less than the number of elements in `data`, return a vector in which every element contains `data[index]`.  Return an all-zeros vector otherwise.

## svdup_lane[_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdup_lane%5B_s32%5D

### Signature (source notation)

```c
svint32_t svdup_lane[_s32](svint32_t data, uint32_t index);
```

### Description

Broadcast a scalar value

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Set all lanes to the same value

- SME attributes: Not specified by source.

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
  "index": {
    "register": "Zindex.S[*]"
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

When index is in the range [0, 15], this intrinsic can use:

```asm
DUP Zresult.S, Zdata.S[index]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/DUP--indexed---Broadcast-indexed-element-to-vector--unpredicated--

The general implementation is:

```asm
TBL Zresult.S, Zdata.S, Zindex.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/TBL--Programmable-table-lookup-in-one-or-two-vector-table--zeroing--

### Operation

Source operation ID: `SveOperation_svdup_lane_bf16`

**Operation**



If `index` is less than the number of elements in `data`, return a vector in which every element contains `data[index]`.  Return an all-zeros vector otherwise.

## svdup_lane[_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdup_lane%5B_s64%5D

### Signature (source notation)

```c
svint64_t svdup_lane[_s64](svint64_t data, uint64_t index);
```

### Description

Broadcast a scalar value

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Set all lanes to the same value

- SME attributes: Not specified by source.

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
  "index": {
    "register": "Zindex.D[*]"
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

When index is in the range [0, 7], this intrinsic can use:

```asm
DUP Zresult.D, Zdata.D[index]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/DUP--indexed---Broadcast-indexed-element-to-vector--unpredicated--

The general implementation is:

```asm
TBL Zresult.D, Zdata.D, Zindex.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/TBL--Programmable-table-lookup-in-one-or-two-vector-table--zeroing--

### Operation

Source operation ID: `SveOperation_svdup_lane_bf16`

**Operation**



If `index` is less than the number of elements in `data`, return a vector in which every element contains `data[index]`.  Return an all-zeros vector otherwise.

## svdup_lane[_s8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdup_lane%5B_s8%5D

### Signature (source notation)

```c
svint8_t svdup_lane[_s8](svint8_t data, uint8_t index);
```

### Description

Broadcast a scalar value

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Set all lanes to the same value

- SME attributes: Not specified by source.

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
  "index": {
    "register": "Zindex.B[*]"
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

When index is in the range [0, 63], this intrinsic can use:

```asm
DUP Zresult.B, Zdata.B[index]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/DUP--indexed---Broadcast-indexed-element-to-vector--unpredicated--

The general implementation is:

```asm
TBL Zresult.B, Zdata.B, Zindex.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/TBL--Programmable-table-lookup-in-one-or-two-vector-table--zeroing--

### Operation

Source operation ID: `SveOperation_svdup_lane_bf16`

**Operation**



If `index` is less than the number of elements in `data`, return a vector in which every element contains `data[index]`.  Return an all-zeros vector otherwise.

## svdup_lane[_u16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdup_lane%5B_u16%5D

### Signature (source notation)

```c
svuint16_t svdup_lane[_u16](svuint16_t data, uint16_t index);
```

### Description

Broadcast a scalar value

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Set all lanes to the same value

- SME attributes: Not specified by source.

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
  "index": {
    "register": "Zindex.H[*]"
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

When index is in the range [0, 31], this intrinsic can use:

```asm
DUP Zresult.H, Zdata.H[index]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/DUP--indexed---Broadcast-indexed-element-to-vector--unpredicated--

The general implementation is:

```asm
TBL Zresult.H, Zdata.H, Zindex.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/TBL--Programmable-table-lookup-in-one-or-two-vector-table--zeroing--

### Operation

Source operation ID: `SveOperation_svdup_lane_bf16`

**Operation**



If `index` is less than the number of elements in `data`, return a vector in which every element contains `data[index]`.  Return an all-zeros vector otherwise.

## svdup_lane[_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdup_lane%5B_u32%5D

### Signature (source notation)

```c
svuint32_t svdup_lane[_u32](svuint32_t data, uint32_t index);
```

### Description

Broadcast a scalar value

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Set all lanes to the same value

- SME attributes: Not specified by source.

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
  "index": {
    "register": "Zindex.S[*]"
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

When index is in the range [0, 15], this intrinsic can use:

```asm
DUP Zresult.S, Zdata.S[index]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/DUP--indexed---Broadcast-indexed-element-to-vector--unpredicated--

The general implementation is:

```asm
TBL Zresult.S, Zdata.S, Zindex.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/TBL--Programmable-table-lookup-in-one-or-two-vector-table--zeroing--

### Operation

Source operation ID: `SveOperation_svdup_lane_bf16`

**Operation**



If `index` is less than the number of elements in `data`, return a vector in which every element contains `data[index]`.  Return an all-zeros vector otherwise.

## svdup_lane[_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdup_lane%5B_u64%5D

### Signature (source notation)

```c
svuint64_t svdup_lane[_u64](svuint64_t data, uint64_t index);
```

### Description

Broadcast a scalar value

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Set all lanes to the same value

- SME attributes: Not specified by source.

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
  "index": {
    "register": "Zindex.D[*]"
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

When index is in the range [0, 7], this intrinsic can use:

```asm
DUP Zresult.D, Zdata.D[index]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/DUP--indexed---Broadcast-indexed-element-to-vector--unpredicated--

The general implementation is:

```asm
TBL Zresult.D, Zdata.D, Zindex.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/TBL--Programmable-table-lookup-in-one-or-two-vector-table--zeroing--

### Operation

Source operation ID: `SveOperation_svdup_lane_bf16`

**Operation**



If `index` is less than the number of elements in `data`, return a vector in which every element contains `data[index]`.  Return an all-zeros vector otherwise.

## svdup_lane[_u8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdup_lane%5B_u8%5D

### Signature (source notation)

```c
svuint8_t svdup_lane[_u8](svuint8_t data, uint8_t index);
```

### Description

Broadcast a scalar value

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Set all lanes to the same value

- SME attributes: Not specified by source.

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
  "index": {
    "register": "Zindex.B[*]"
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

When index is in the range [0, 63], this intrinsic can use:

```asm
DUP Zresult.B, Zdata.B[index]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/DUP--indexed---Broadcast-indexed-element-to-vector--unpredicated--

The general implementation is:

```asm
TBL Zresult.B, Zdata.B, Zindex.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/TBL--Programmable-table-lookup-in-one-or-two-vector-table--zeroing--

### Operation

Source operation ID: `SveOperation_svdup_lane_bf16`

**Operation**



If `index` is less than the number of elements in `data`, return a vector in which every element contains `data[index]`.  Return an all-zeros vector otherwise.

## svdup_laneq[_bf16]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdup_laneq%5B_bf16%5D

### Signature (source notation)

```c
svbfloat16_t svdup_laneq[_bf16](svbfloat16_t zn, uint64_t imm_idx);
```

### Description

Broadcast indexed element within each quadword vector segment (unpredicated)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector manipulation / Set all lanes to the same value

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
  "imm_idx": {
    "immediate": "imm1"
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
DUPQ Zreg1.H, Zreg2.H[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/DUPQ--Broadcast-indexed-element-within-each-quadword-vector-segment--unpredicated--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svdup_laneq[_f16]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdup_laneq%5B_f16%5D

### Signature (source notation)

```c
svfloat16_t svdup_laneq[_f16](svfloat16_t zn, uint64_t imm_idx);
```

### Description

Broadcast indexed element within each quadword vector segment (unpredicated)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector manipulation / Set all lanes to the same value

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
  "imm_idx": {
    "immediate": "imm1"
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
DUPQ Zreg1.H, Zreg2.H[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/DUPQ--Broadcast-indexed-element-within-each-quadword-vector-segment--unpredicated--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svdup_laneq[_f32]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdup_laneq%5B_f32%5D

### Signature (source notation)

```c
svfloat32_t svdup_laneq[_f32](svfloat32_t zn, uint64_t imm_idx);
```

### Description

Broadcast indexed element within each quadword vector segment (unpredicated)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector manipulation / Set all lanes to the same value

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
  "imm_idx": {
    "immediate": "imm1"
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
DUPQ Zreg1.S, Zreg2.S[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/DUPQ--Broadcast-indexed-element-within-each-quadword-vector-segment--unpredicated--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svdup_laneq[_f64]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdup_laneq%5B_f64%5D

### Signature (source notation)

```c
svfloat64_t svdup_laneq[_f64](svfloat64_t zn, uint64_t imm_idx);
```

### Description

Broadcast indexed element within each quadword vector segment (unpredicated)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector manipulation / Set all lanes to the same value

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
  "imm_idx": {
    "immediate": "imm1"
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
DUPQ Zreg1.D, Zreg2.D[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/DUPQ--Broadcast-indexed-element-within-each-quadword-vector-segment--unpredicated--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svdup_laneq[_mf8]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdup_laneq%5B_mf8%5D

### Signature (source notation)

```c
svmfloat8_t svdup_laneq[_mf8](svmfloat8_t zn, uint64_t imm_idx);
```

### Description

Broadcast indexed element within each quadword vector segment (unpredicated)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector manipulation / Set all lanes to the same value

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
  "imm_idx": {
    "immediate": "imm1"
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
DUPQ Zreg1.B, Zreg2.B[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/DUPQ--Broadcast-indexed-element-within-each-quadword-vector-segment--unpredicated--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svdup_laneq[_s16]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdup_laneq%5B_s16%5D

### Signature (source notation)

```c
svint16_t svdup_laneq[_s16](svint16_t zn, uint64_t imm_idx);
```

### Description

Broadcast indexed element within each quadword vector segment (unpredicated)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector manipulation / Set all lanes to the same value

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
  "imm_idx": {
    "immediate": "imm1"
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
DUPQ Zreg1.H, Zreg2.H[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/DUPQ--Broadcast-indexed-element-within-each-quadword-vector-segment--unpredicated--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svdup_laneq[_s32]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdup_laneq%5B_s32%5D

### Signature (source notation)

```c
svint32_t svdup_laneq[_s32](svint32_t zn, uint64_t imm_idx);
```

### Description

Broadcast indexed element within each quadword vector segment (unpredicated)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector manipulation / Set all lanes to the same value

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
  "imm_idx": {
    "immediate": "imm1"
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
DUPQ Zreg1.S, Zreg2.S[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/DUPQ--Broadcast-indexed-element-within-each-quadword-vector-segment--unpredicated--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svdup_laneq[_s64]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdup_laneq%5B_s64%5D

### Signature (source notation)

```c
svint64_t svdup_laneq[_s64](svint64_t zn, uint64_t imm_idx);
```

### Description

Broadcast indexed element within each quadword vector segment (unpredicated)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector manipulation / Set all lanes to the same value

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
  "imm_idx": {
    "immediate": "imm1"
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
DUPQ Zreg1.D, Zreg2.D[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/DUPQ--Broadcast-indexed-element-within-each-quadword-vector-segment--unpredicated--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svdup_laneq[_s8]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdup_laneq%5B_s8%5D

### Signature (source notation)

```c
svint8_t svdup_laneq[_s8](svint8_t zn, uint64_t imm_idx);
```

### Description

Broadcast indexed element within each quadword vector segment (unpredicated)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector manipulation / Set all lanes to the same value

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
  "imm_idx": {
    "immediate": "imm1"
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
DUPQ Zreg1.B, Zreg2.B[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/DUPQ--Broadcast-indexed-element-within-each-quadword-vector-segment--unpredicated--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svdup_laneq[_u16]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdup_laneq%5B_u16%5D

### Signature (source notation)

```c
svuint16_t svdup_laneq[_u16](svuint16_t zn, uint64_t imm_idx);
```

### Description

Broadcast indexed element within each quadword vector segment (unpredicated)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector manipulation / Set all lanes to the same value

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
  "imm_idx": {
    "immediate": "imm1"
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
DUPQ Zreg1.H, Zreg2.H[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/DUPQ--Broadcast-indexed-element-within-each-quadword-vector-segment--unpredicated--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svdup_laneq[_u32]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdup_laneq%5B_u32%5D

### Signature (source notation)

```c
svuint32_t svdup_laneq[_u32](svuint32_t zn, uint64_t imm_idx);
```

### Description

Broadcast indexed element within each quadword vector segment (unpredicated)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector manipulation / Set all lanes to the same value

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
  "imm_idx": {
    "immediate": "imm1"
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
DUPQ Zreg1.S, Zreg2.S[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/DUPQ--Broadcast-indexed-element-within-each-quadword-vector-segment--unpredicated--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svdup_laneq[_u64]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdup_laneq%5B_u64%5D

### Signature (source notation)

```c
svuint64_t svdup_laneq[_u64](svuint64_t zn, uint64_t imm_idx);
```

### Description

Broadcast indexed element within each quadword vector segment (unpredicated)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector manipulation / Set all lanes to the same value

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
  "imm_idx": {
    "immediate": "imm1"
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
DUPQ Zreg1.D, Zreg2.D[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/DUPQ--Broadcast-indexed-element-within-each-quadword-vector-segment--unpredicated--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svdup_laneq[_u8]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdup_laneq%5B_u8%5D

### Signature (source notation)

```c
svuint8_t svdup_laneq[_u8](svuint8_t zn, uint64_t imm_idx);
```

### Description

Broadcast indexed element within each quadword vector segment (unpredicated)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector manipulation / Set all lanes to the same value

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
  "imm_idx": {
    "immediate": "imm1"
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
DUPQ Zreg1.B, Zreg2.B[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/DUPQ--Broadcast-indexed-element-within-each-quadword-vector-segment--unpredicated--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

