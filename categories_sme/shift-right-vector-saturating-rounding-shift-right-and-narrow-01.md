# SME / Shift / Right / Vector saturating rounding shift right and narrow — Part 1

## svqrshrn[_n]_s16[_s32_x2]

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqrshrn%5B_n%5D_s16%5B_s32_x2%5D

### Signature (source notation)

```c
svint16_t svqrshrn[_n]_s16[_s32_x2](svint32x2_t zn, uint64_t imm);
```

### Description

Signed saturating rounding shift right narrow by immediate and interleave

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Shift / Right / Vector saturating rounding shift right and narrow

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p1)|FEAT_SME2
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
    "Z multi-vector": "{ Zreg2.S, Zreg3.S }"
  },
  "imm": {
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
SQRSHRN Zreg1.H, { Zreg2.S, Zreg3.S }, #imm1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQRSHRN--Signed-saturating-rounding-shift-right-narrow-by-immediate-and-interleave-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svqrshrn[_n]_u16[_u32_x2]

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqrshrn%5B_n%5D_u16%5B_u32_x2%5D

### Signature (source notation)

```c
svuint16_t svqrshrn[_n]_u16[_u32_x2](svuint32x2_t zn, uint64_t imm);
```

### Description

Unsigned saturating rounding shift right narrow by immediate and interleave

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Shift / Right / Vector saturating rounding shift right and narrow

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p1)|FEAT_SME2
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
    "Z multi-vector": "{ Zreg2.S, Zreg3.S }"
  },
  "imm": {
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
UQRSHRN Zreg1.H, { Zreg2.S, Zreg3.S }, #imm1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQRSHRN--Unsigned-saturating-rounding-shift-right-narrow-by-immediate-and-interleave-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svqrshrnb[_n_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqrshrnb%5B_n_s16%5D

### Signature (source notation)

```c
svint8_t svqrshrnb[_n_s16](svint16_t op1, uint64_t imm2);
```

### Description

Saturating rounding shift right narrow (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Shift / Right / Vector saturating rounding shift right and narrow

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
    "register": "Zop1.H"
  },
  "imm2": {
    "minimum": 1,
    "maximum": 8
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
SQRSHRNB Zresult.B, Zop1.H, #imm2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQRSHRNB--Signed-saturating-rounding-shift-right-narrow-by-immediate--bottom--

### Operation

Source operation ID: `SveOperation_svqrshrnb_n_s16`

**Operation**



Return a vector in which each even-indexed (“bottom”) element *i* contains the result of the following procedure:




- Divide `op1[i/2]` by 2 to the power `imm2`, rounding to nearest with ties towards +∞.
- Saturate the result to the range of `int8_t`.



Set the odd-indexed elements of the result vector to zero.

## svqrshrnb[_n_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqrshrnb%5B_n_s32%5D

### Signature (source notation)

```c
svint16_t svqrshrnb[_n_s32](svint32_t op1, uint64_t imm2);
```

### Description

Saturating rounding shift right narrow (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Shift / Right / Vector saturating rounding shift right and narrow

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
    "register": "Zop1.S"
  },
  "imm2": {
    "minimum": 1,
    "maximum": 16
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
SQRSHRNB Zresult.H, Zop1.S, #imm2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQRSHRNB--Signed-saturating-rounding-shift-right-narrow-by-immediate--bottom--

### Operation

Source operation ID: `SveOperation_svqrshrnb_n_s32`

**Operation**



Return a vector in which each even-indexed (“bottom”) element *i* contains the result of the following procedure:




- Divide `op1[i/2]` by 2 to the power `imm2`, rounding to nearest with ties towards +∞.
- Saturate the result to the range of `int16_t`.



Set the odd-indexed elements of the result vector to zero.

## svqrshrnb[_n_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqrshrnb%5B_n_s64%5D

### Signature (source notation)

```c
svint32_t svqrshrnb[_n_s64](svint64_t op1, uint64_t imm2);
```

### Description

Saturating rounding shift right narrow (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Shift / Right / Vector saturating rounding shift right and narrow

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
    "register": "Zop1.D"
  },
  "imm2": {
    "minimum": 1,
    "maximum": 32
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
SQRSHRNB Zresult.S, Zop1.D, #imm2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQRSHRNB--Signed-saturating-rounding-shift-right-narrow-by-immediate--bottom--

### Operation

Source operation ID: `SveOperation_svqrshrnb_n_s64`

**Operation**



Return a vector in which each even-indexed (“bottom”) element *i* contains the result of the following procedure:




- Divide `op1[i/2]` by 2 to the power `imm2`, rounding to nearest with ties towards +∞.
- Saturate the result to the range of `int32_t`.



Set the odd-indexed elements of the result vector to zero.

## svqrshrnb[_n_u16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqrshrnb%5B_n_u16%5D

### Signature (source notation)

```c
svuint8_t svqrshrnb[_n_u16](svuint16_t op1, uint64_t imm2);
```

### Description

Saturating rounding shift right narrow (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Shift / Right / Vector saturating rounding shift right and narrow

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
    "register": "Zop1.H"
  },
  "imm2": {
    "minimum": 1,
    "maximum": 8
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
UQRSHRNB Zresult.B, Zop1.H, #imm2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQRSHRNB--Unsigned-saturating-rounding-shift-right-narrow-by-immediate--bottom--

### Operation

Source operation ID: `SveOperation_svqrshrnb_n_u16`

**Operation**



Return a vector in which each even-indexed (“bottom”) element *i* contains the result of the following procedure:




- Divide `op1[i/2]` by 2 to the power `imm2`, rounding to nearest with ties towards +∞.
- Saturate the result to the range of `uint8_t`.



Set the odd-indexed elements of the result vector to zero.

## svqrshrnb[_n_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqrshrnb%5B_n_u32%5D

### Signature (source notation)

```c
svuint16_t svqrshrnb[_n_u32](svuint32_t op1, uint64_t imm2);
```

### Description

Saturating rounding shift right narrow (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Shift / Right / Vector saturating rounding shift right and narrow

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
    "register": "Zop1.S"
  },
  "imm2": {
    "minimum": 1,
    "maximum": 16
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
UQRSHRNB Zresult.H, Zop1.S, #imm2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQRSHRNB--Unsigned-saturating-rounding-shift-right-narrow-by-immediate--bottom--

### Operation

Source operation ID: `SveOperation_svqrshrnb_n_u32`

**Operation**



Return a vector in which each even-indexed (“bottom”) element *i* contains the result of the following procedure:




- Divide `op1[i/2]` by 2 to the power `imm2`, rounding to nearest with ties towards +∞.
- Saturate the result to the range of `uint16_t`.



Set the odd-indexed elements of the result vector to zero.

## svqrshrnb[_n_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqrshrnb%5B_n_u64%5D

### Signature (source notation)

```c
svuint32_t svqrshrnb[_n_u64](svuint64_t op1, uint64_t imm2);
```

### Description

Saturating rounding shift right narrow (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Shift / Right / Vector saturating rounding shift right and narrow

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
    "register": "Zop1.D"
  },
  "imm2": {
    "minimum": 1,
    "maximum": 32
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
UQRSHRNB Zresult.S, Zop1.D, #imm2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQRSHRNB--Unsigned-saturating-rounding-shift-right-narrow-by-immediate--bottom--

### Operation

Source operation ID: `SveOperation_svqrshrnb_n_u64`

**Operation**



Return a vector in which each even-indexed (“bottom”) element *i* contains the result of the following procedure:




- Divide `op1[i/2]` by 2 to the power `imm2`, rounding to nearest with ties towards +∞.
- Saturate the result to the range of `uint32_t`.



Set the odd-indexed elements of the result vector to zero.

## svqrshrnt[_n_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqrshrnt%5B_n_s16%5D

### Signature (source notation)

```c
svint8_t svqrshrnt[_n_s16](svint8_t even, svint16_t op1, uint64_t imm2);
```

### Description

Saturating rounding shift right narrow (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Shift / Right / Vector saturating rounding shift right and narrow

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
  "even": {
    "register": "Ztied.B"
  },
  "op1": {
    "register": "Zop1.H"
  },
  "imm2": {
    "minimum": 1,
    "maximum": 8
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
SQRSHRNT Ztied.B, Zop1.H, #imm2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQRSHRNT--Signed-saturating-rounding-shift-right-narrow-by-immediate--top--

### Operation

Source operation ID: `SveOperation_svqrshrnt_n_s16`

**Operation**



Return a vector in which each odd-indexed (“top”) element *i* contains the result of the following procedure:




- Divide `op1[i/2]` by 2 to the power `imm2`, rounding to nearest with ties towards +∞.
- Saturate the result to the range of `int8_t`.



Copy the even-indexed elements of the result vector from the corresponding elements of `even`.

## svqrshrnt[_n_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqrshrnt%5B_n_s32%5D

### Signature (source notation)

```c
svint16_t svqrshrnt[_n_s32](svint16_t even, svint32_t op1, uint64_t imm2);
```

### Description

Saturating rounding shift right narrow (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Shift / Right / Vector saturating rounding shift right and narrow

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
  "even": {
    "register": "Ztied.H"
  },
  "op1": {
    "register": "Zop1.S"
  },
  "imm2": {
    "minimum": 1,
    "maximum": 16
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
SQRSHRNT Ztied.H, Zop1.S, #imm2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQRSHRNT--Signed-saturating-rounding-shift-right-narrow-by-immediate--top--

### Operation

Source operation ID: `SveOperation_svqrshrnt_n_s32`

**Operation**



Return a vector in which each odd-indexed (“top”) element *i* contains the result of the following procedure:




- Divide `op1[i/2]` by 2 to the power `imm2`, rounding to nearest with ties towards +∞.
- Saturate the result to the range of `int16_t`.



Copy the even-indexed elements of the result vector from the corresponding elements of `even`.

## svqrshrnt[_n_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqrshrnt%5B_n_s64%5D

### Signature (source notation)

```c
svint32_t svqrshrnt[_n_s64](svint32_t even, svint64_t op1, uint64_t imm2);
```

### Description

Saturating rounding shift right narrow (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Shift / Right / Vector saturating rounding shift right and narrow

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
  "even": {
    "register": "Ztied.S"
  },
  "op1": {
    "register": "Zop1.D"
  },
  "imm2": {
    "minimum": 1,
    "maximum": 32
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
SQRSHRNT Ztied.S, Zop1.D, #imm2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQRSHRNT--Signed-saturating-rounding-shift-right-narrow-by-immediate--top--

### Operation

Source operation ID: `SveOperation_svqrshrnt_n_s64`

**Operation**



Return a vector in which each odd-indexed (“top”) element *i* contains the result of the following procedure:




- Divide `op1[i/2]` by 2 to the power `imm2`, rounding to nearest with ties towards +∞.
- Saturate the result to the range of `int32_t`.



Copy the even-indexed elements of the result vector from the corresponding elements of `even`.

## svqrshrnt[_n_u16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqrshrnt%5B_n_u16%5D

### Signature (source notation)

```c
svuint8_t svqrshrnt[_n_u16](svuint8_t even, svuint16_t op1, uint64_t imm2);
```

### Description

Saturating rounding shift right narrow (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Shift / Right / Vector saturating rounding shift right and narrow

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
  "even": {
    "register": "Ztied.B"
  },
  "op1": {
    "register": "Zop1.H"
  },
  "imm2": {
    "minimum": 1,
    "maximum": 8
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
UQRSHRNT Ztied.B, Zop1.H, #imm2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQRSHRNT--Unsigned-saturating-rounding-shift-right-narrow-by-immediate--top--

### Operation

Source operation ID: `SveOperation_svqrshrnt_n_u16`

**Operation**



Return a vector in which each odd-indexed (“top”) element *i* contains the result of the following procedure:




- Divide `op1[i/2]` by 2 to the power `imm2`, rounding to nearest with ties towards +∞.
- Saturate the result to the range of `uint8_t`.



Copy the even-indexed elements of the result vector from the corresponding elements of `even`.

## svqrshrnt[_n_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqrshrnt%5B_n_u32%5D

### Signature (source notation)

```c
svuint16_t svqrshrnt[_n_u32](svuint16_t even, svuint32_t op1, uint64_t imm2);
```

### Description

Saturating rounding shift right narrow (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Shift / Right / Vector saturating rounding shift right and narrow

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
  "even": {
    "register": "Ztied.H"
  },
  "op1": {
    "register": "Zop1.S"
  },
  "imm2": {
    "minimum": 1,
    "maximum": 16
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
UQRSHRNT Ztied.H, Zop1.S, #imm2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQRSHRNT--Unsigned-saturating-rounding-shift-right-narrow-by-immediate--top--

### Operation

Source operation ID: `SveOperation_svqrshrnt_n_u32`

**Operation**



Return a vector in which each odd-indexed (“top”) element *i* contains the result of the following procedure:




- Divide `op1[i/2]` by 2 to the power `imm2`, rounding to nearest with ties towards +∞.
- Saturate the result to the range of `uint16_t`.



Copy the even-indexed elements of the result vector from the corresponding elements of `even`.

## svqrshrnt[_n_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqrshrnt%5B_n_u64%5D

### Signature (source notation)

```c
svuint32_t svqrshrnt[_n_u64](svuint32_t even, svuint64_t op1, uint64_t imm2);
```

### Description

Saturating rounding shift right narrow (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Shift / Right / Vector saturating rounding shift right and narrow

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
  "even": {
    "register": "Ztied.S"
  },
  "op1": {
    "register": "Zop1.D"
  },
  "imm2": {
    "minimum": 1,
    "maximum": 32
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
UQRSHRNT Ztied.S, Zop1.D, #imm2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQRSHRNT--Unsigned-saturating-rounding-shift-right-narrow-by-immediate--top--

### Operation

Source operation ID: `SveOperation_svqrshrnt_n_u64`

**Operation**



Return a vector in which each odd-indexed (“top”) element *i* contains the result of the following procedure:




- Divide `op1[i/2]` by 2 to the power `imm2`, rounding to nearest with ties towards +∞.
- Saturate the result to the range of `uint32_t`.



Copy the even-indexed elements of the result vector from the corresponding elements of `even`.

## svqrshrun[_n]_u16[_s32_x2]

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqrshrun%5B_n%5D_u16%5B_s32_x2%5D

### Signature (source notation)

```c
svuint16_t svqrshrun[_n]_u16[_s32_x2](svint32x2_t zn, uint64_t imm);
```

### Description

Signed saturating rounding shift right unsigned narrow by immediate and interleave

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Shift / Right / Vector saturating rounding shift right and narrow

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p1)|FEAT_SME2
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
    "Z multi-vector": "{ Zreg2.S, Zreg3.S }"
  },
  "imm": {
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
SQRSHRUN Zreg1.H, { Zreg2.S, Zreg3.S }, #imm1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQRSHRUN--Signed-saturating-rounding-shift-right-unsigned-narrow-by-immediate-and-interleave-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svqrshrunb[_n_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqrshrunb%5B_n_s16%5D

### Signature (source notation)

```c
svuint8_t svqrshrunb[_n_s16](svint16_t op1, uint64_t imm2);
```

### Description

Saturating rounding shift right unsigned narrow (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Shift / Right / Vector saturating rounding shift right and narrow

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
    "register": "Zop1.H"
  },
  "imm2": {
    "minimum": 1,
    "maximum": 8
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
SQRSHRUNB Zresult.B, Zop1.H, #imm2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQRSHRUNB--Signed-saturating-rounding-shift-right-unsigned-narrow-by-immediate--bottom--

### Operation

Source operation ID: `SveOperation_svqrshrnb_n_u16`

**Operation**



Return a vector in which each even-indexed (“bottom”) element *i* contains the result of the following procedure:




- Divide `op1[i/2]` by 2 to the power `imm2`, rounding to nearest with ties towards +∞.
- Saturate the result to the range of `uint8_t`.



Set the odd-indexed elements of the result vector to zero.

## svqrshrunb[_n_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqrshrunb%5B_n_s32%5D

### Signature (source notation)

```c
svuint16_t svqrshrunb[_n_s32](svint32_t op1, uint64_t imm2);
```

### Description

Saturating rounding shift right unsigned narrow (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Shift / Right / Vector saturating rounding shift right and narrow

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
    "register": "Zop1.S"
  },
  "imm2": {
    "minimum": 1,
    "maximum": 16
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
SQRSHRUNB Zresult.H, Zop1.S, #imm2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQRSHRUNB--Signed-saturating-rounding-shift-right-unsigned-narrow-by-immediate--bottom--

### Operation

Source operation ID: `SveOperation_svqrshrnb_n_u32`

**Operation**



Return a vector in which each even-indexed (“bottom”) element *i* contains the result of the following procedure:




- Divide `op1[i/2]` by 2 to the power `imm2`, rounding to nearest with ties towards +∞.
- Saturate the result to the range of `uint16_t`.



Set the odd-indexed elements of the result vector to zero.

## svqrshrunb[_n_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqrshrunb%5B_n_s64%5D

### Signature (source notation)

```c
svuint32_t svqrshrunb[_n_s64](svint64_t op1, uint64_t imm2);
```

### Description

Saturating rounding shift right unsigned narrow (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Shift / Right / Vector saturating rounding shift right and narrow

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
    "register": "Zop1.D"
  },
  "imm2": {
    "minimum": 1,
    "maximum": 32
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
SQRSHRUNB Zresult.S, Zop1.D, #imm2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQRSHRUNB--Signed-saturating-rounding-shift-right-unsigned-narrow-by-immediate--bottom--

### Operation

Source operation ID: `SveOperation_svqrshrnb_n_u64`

**Operation**



Return a vector in which each even-indexed (“bottom”) element *i* contains the result of the following procedure:




- Divide `op1[i/2]` by 2 to the power `imm2`, rounding to nearest with ties towards +∞.
- Saturate the result to the range of `uint32_t`.



Set the odd-indexed elements of the result vector to zero.

## svqrshrunt[_n_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqrshrunt%5B_n_s16%5D

### Signature (source notation)

```c
svuint8_t svqrshrunt[_n_s16](svuint8_t even, svint16_t op1, uint64_t imm2);
```

### Description

Saturating rounding shift right unsigned narrow (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Shift / Right / Vector saturating rounding shift right and narrow

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
  "even": {
    "register": "Ztied.B"
  },
  "op1": {
    "register": "Zop1.H"
  },
  "imm2": {
    "minimum": 1,
    "maximum": 8
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
SQRSHRUNT Ztied.B, Zop1.H, #imm2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQRSHRUNT--Signed-saturating-rounding-shift-right-unsigned-narrow-by-immediate--top--

### Operation

Source operation ID: `SveOperation_svqrshrnt_n_u16`

**Operation**



Return a vector in which each odd-indexed (“top”) element *i* contains the result of the following procedure:




- Divide `op1[i/2]` by 2 to the power `imm2`, rounding to nearest with ties towards +∞.
- Saturate the result to the range of `uint8_t`.



Copy the even-indexed elements of the result vector from the corresponding elements of `even`.

## svqrshrunt[_n_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqrshrunt%5B_n_s32%5D

### Signature (source notation)

```c
svuint16_t svqrshrunt[_n_s32](svuint16_t even, svint32_t op1, uint64_t imm2);
```

### Description

Saturating rounding shift right unsigned narrow (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Shift / Right / Vector saturating rounding shift right and narrow

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
  "even": {
    "register": "Ztied.H"
  },
  "op1": {
    "register": "Zop1.S"
  },
  "imm2": {
    "minimum": 1,
    "maximum": 16
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
SQRSHRUNT Ztied.H, Zop1.S, #imm2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQRSHRUNT--Signed-saturating-rounding-shift-right-unsigned-narrow-by-immediate--top--

### Operation

Source operation ID: `SveOperation_svqrshrnt_n_u32`

**Operation**



Return a vector in which each odd-indexed (“top”) element *i* contains the result of the following procedure:




- Divide `op1[i/2]` by 2 to the power `imm2`, rounding to nearest with ties towards +∞.
- Saturate the result to the range of `uint16_t`.



Copy the even-indexed elements of the result vector from the corresponding elements of `even`.

## svqrshrunt[_n_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqrshrunt%5B_n_s64%5D

### Signature (source notation)

```c
svuint32_t svqrshrunt[_n_s64](svuint32_t even, svint64_t op1, uint64_t imm2);
```

### Description

Saturating rounding shift right unsigned narrow (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Shift / Right / Vector saturating rounding shift right and narrow

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
  "even": {
    "register": "Ztied.S"
  },
  "op1": {
    "register": "Zop1.D"
  },
  "imm2": {
    "minimum": 1,
    "maximum": 32
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
SQRSHRUNT Ztied.S, Zop1.D, #imm2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQRSHRUNT--Signed-saturating-rounding-shift-right-unsigned-narrow-by-immediate--top--

### Operation

Source operation ID: `SveOperation_svqrshrnt_n_u64`

**Operation**



Return a vector in which each odd-indexed (“top”) element *i* contains the result of the following procedure:




- Divide `op1[i/2]` by 2 to the power `imm2`, rounding to nearest with ties towards +∞.
- Saturate the result to the range of `uint32_t`.



Copy the even-indexed elements of the result vector from the corresponding elements of `even`.

