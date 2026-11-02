# SME2 / Predication / Element selection / Concatenate active elements — Part 1

## svcompact[_bf16]

ISA classification: SME2.2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcompact%5B_bf16%5D

### Signature (source notation)

```c
svbfloat16_t svcompact[_bf16](svbool_t pg, svbfloat16_t zn);
```

### Description

Copy Active vector elements to lower-numbered elements

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Element selection / Concatenate active elements

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2p2
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
    "register": "Zreg2.H"
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
COMPACT Zreg1.H, Preg1, Zreg2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/COMPACT--Copy-Active-vector-elements-to-lower-numbered-elements-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svcompact[_f16]

ISA classification: SME2.2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcompact%5B_f16%5D

### Signature (source notation)

```c
svfloat16_t svcompact[_f16](svbool_t pg, svfloat16_t zn);
```

### Description

Copy Active vector elements to lower-numbered elements

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Element selection / Concatenate active elements

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2p2
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
    "register": "Zreg2.H"
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
COMPACT Zreg1.H, Preg1, Zreg2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/COMPACT--Copy-Active-vector-elements-to-lower-numbered-elements-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svcompact[_f32]

ISA classification: SME2.2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcompact%5B_f32%5D

### Signature (source notation)

```c
svfloat32_t svcompact[_f32](svbool_t pg, svfloat32_t op);
```

### Description

Shuffle active elements of vector to the right and fill with zero

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Predication / Element selection / Concatenate active elements

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2p2
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

This intrinsic compiles to the following instruction:

```asm
COMPACT Zresult.S, Pg, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/COMPACT--Copy-Active-vector-elements-to-lower-numbered-elements-

### Operation

Source operation ID: `SveOperation_svcompact_f32`

**Operation**



Concatenate the active elements of `op` together, filling any remaining (higher-indexed) elements with zero.

## svcompact[_f64]

ISA classification: SME2.2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcompact%5B_f64%5D

### Signature (source notation)

```c
svfloat64_t svcompact[_f64](svbool_t pg, svfloat64_t op);
```

### Description

Shuffle active elements of vector to the right and fill with zero

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Predication / Element selection / Concatenate active elements

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2p2
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

This intrinsic compiles to the following instruction:

```asm
COMPACT Zresult.D, Pg, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/COMPACT--Copy-Active-vector-elements-to-lower-numbered-elements-

### Operation

Source operation ID: `SveOperation_svcompact_f32`

**Operation**



Concatenate the active elements of `op` together, filling any remaining (higher-indexed) elements with zero.

## svcompact[_mf8]

ISA classification: SME2.2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcompact%5B_mf8%5D

### Signature (source notation)

```c
svmfloat8_t svcompact[_mf8](svbool_t pg, svmfloat8_t zn);
```

### Description

Copy Active vector elements to lower-numbered elements

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Element selection / Concatenate active elements

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2p2
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
    "register": "Zreg2.B"
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
COMPACT Zreg1.B, Preg1, Zreg2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/COMPACT--Copy-Active-vector-elements-to-lower-numbered-elements-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svcompact[_s16]

ISA classification: SME2.2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcompact%5B_s16%5D

### Signature (source notation)

```c
svint16_t svcompact[_s16](svbool_t pg, svint16_t zn);
```

### Description

Copy Active vector elements to lower-numbered elements

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Element selection / Concatenate active elements

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2p2
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
  "pg": {
    "register": "Preg1"
  },
  "zn": {
    "register": "Zreg2.H"
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
COMPACT Zreg1.H, Preg1, Zreg2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/COMPACT--Copy-Active-vector-elements-to-lower-numbered-elements-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svcompact[_s32]

ISA classification: SME2.2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcompact%5B_s32%5D

### Signature (source notation)

```c
svint32_t svcompact[_s32](svbool_t pg, svint32_t op);
```

### Description

Shuffle active elements of vector to the right and fill with zero

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Predication / Element selection / Concatenate active elements

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2p2
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

This intrinsic compiles to the following instruction:

```asm
COMPACT Zresult.S, Pg, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/COMPACT--Copy-Active-vector-elements-to-lower-numbered-elements-

### Operation

Source operation ID: `SveOperation_svcompact_f32`

**Operation**



Concatenate the active elements of `op` together, filling any remaining (higher-indexed) elements with zero.

## svcompact[_s64]

ISA classification: SME2.2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcompact%5B_s64%5D

### Signature (source notation)

```c
svint64_t svcompact[_s64](svbool_t pg, svint64_t op);
```

### Description

Shuffle active elements of vector to the right and fill with zero

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Predication / Element selection / Concatenate active elements

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2p2
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

This intrinsic compiles to the following instruction:

```asm
COMPACT Zresult.D, Pg, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/COMPACT--Copy-Active-vector-elements-to-lower-numbered-elements-

### Operation

Source operation ID: `SveOperation_svcompact_f32`

**Operation**



Concatenate the active elements of `op` together, filling any remaining (higher-indexed) elements with zero.

## svcompact[_s8]

ISA classification: SME2.2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcompact%5B_s8%5D

### Signature (source notation)

```c
svint8_t svcompact[_s8](svbool_t pg, svint8_t zn);
```

### Description

Copy Active vector elements to lower-numbered elements

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Element selection / Concatenate active elements

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2p2
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
  "pg": {
    "register": "Preg1"
  },
  "zn": {
    "register": "Zreg2.B"
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
COMPACT Zreg1.B, Preg1, Zreg2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/COMPACT--Copy-Active-vector-elements-to-lower-numbered-elements-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svcompact[_u16]

ISA classification: SME2.2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcompact%5B_u16%5D

### Signature (source notation)

```c
svuint16_t svcompact[_u16](svbool_t pg, svuint16_t zn);
```

### Description

Copy Active vector elements to lower-numbered elements

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Element selection / Concatenate active elements

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2p2
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
  "pg": {
    "register": "Preg1"
  },
  "zn": {
    "register": "Zreg2.H"
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
COMPACT Zreg1.H, Preg1, Zreg2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/COMPACT--Copy-Active-vector-elements-to-lower-numbered-elements-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svcompact[_u32]

ISA classification: SME2.2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcompact%5B_u32%5D

### Signature (source notation)

```c
svuint32_t svcompact[_u32](svbool_t pg, svuint32_t op);
```

### Description

Shuffle active elements of vector to the right and fill with zero

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Predication / Element selection / Concatenate active elements

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2p2
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

This intrinsic compiles to the following instruction:

```asm
COMPACT Zresult.S, Pg, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/COMPACT--Copy-Active-vector-elements-to-lower-numbered-elements-

### Operation

Source operation ID: `SveOperation_svcompact_f32`

**Operation**



Concatenate the active elements of `op` together, filling any remaining (higher-indexed) elements with zero.

## svcompact[_u64]

ISA classification: SME2.2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcompact%5B_u64%5D

### Signature (source notation)

```c
svuint64_t svcompact[_u64](svbool_t pg, svuint64_t op);
```

### Description

Shuffle active elements of vector to the right and fill with zero

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Predication / Element selection / Concatenate active elements

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2p2
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

This intrinsic compiles to the following instruction:

```asm
COMPACT Zresult.D, Pg, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/COMPACT--Copy-Active-vector-elements-to-lower-numbered-elements-

### Operation

Source operation ID: `SveOperation_svcompact_f32`

**Operation**



Concatenate the active elements of `op` together, filling any remaining (higher-indexed) elements with zero.

## svcompact[_u8]

ISA classification: SME2.2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcompact%5B_u8%5D

### Signature (source notation)

```c
svuint8_t svcompact[_u8](svbool_t pg, svuint8_t zn);
```

### Description

Copy Active vector elements to lower-numbered elements

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Element selection / Concatenate active elements

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2p2
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
  "pg": {
    "register": "Preg1"
  },
  "zn": {
    "register": "Zreg2.B"
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
COMPACT Zreg1.B, Preg1, Zreg2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/COMPACT--Copy-Active-vector-elements-to-lower-numbered-elements-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

