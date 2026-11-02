# SME2 / Vector manipulation / Set all lanes to the same value — Part 1

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

