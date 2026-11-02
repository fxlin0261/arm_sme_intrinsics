# SME / Move / Saturating narrow — Part 1

## svqcvtn_s16[_s32_x2]

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqcvtn_s16%5B_s32_x2%5D

### Signature (source notation)

```c
svint16_t svqcvtn_s16[_s32_x2](svint32x2_t zn);
```

### Description

Signed 32-bit integer saturating extract narrow and interleave to 16-bit integer

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Move / Saturating narrow

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
SQCVTN Zreg1.H, { Zreg2.S, Zreg3.S }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQCVTN--Signed-32-bit-integer-saturating-extract-narrow-and-interleave-to-16-bit-integer-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svqcvtn_u16[_s32_x2]

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqcvtn_u16%5B_s32_x2%5D

### Signature (source notation)

```c
svuint16_t svqcvtn_u16[_s32_x2](svint32x2_t zn);
```

### Description

Signed 32-bit integer saturating unsigned extract narrow and interleave to 16-bit integer

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Move / Saturating narrow

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
SQCVTUN Zreg1.H, { Zreg2.S, Zreg3.S }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQCVTUN--Signed-32-bit-integer-saturating-unsigned-extract-narrow-and-interleave-to-16-bit-integer-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svqcvtn_u16[_u32_x2]

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqcvtn_u16%5B_u32_x2%5D

### Signature (source notation)

```c
svuint16_t svqcvtn_u16[_u32_x2](svuint32x2_t zn);
```

### Description

Unsigned 32-bit integer saturating extract narrow and interleave to 16-bit integer

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Move / Saturating narrow

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
UQCVTN Zreg1.H, { Zreg2.S, Zreg3.S }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQCVTN--Unsigned-32-bit-integer-saturating-extract-narrow-and-interleave-to-16-bit-integer-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svqxtnb[_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqxtnb%5B_s16%5D

### Signature (source notation)

```c
svint8_t svqxtnb[_s16](svint16_t op);
```

### Description

Saturating extract narrow (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Move / Saturating narrow

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
    "register": "Zop.H"
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
SQXTNB Zresult.B, Zop.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQXTNB--Signed-saturating-extract-narrow--bottom--

### Operation

Source operation ID: `SveOperation_svqxtnb_s16`

**Operation**



Return a vector in which, for each even element index *i*:




- element *i* contains the result of saturating `op[i / 2]` to `int8_t`.
- element *i* + 1 contains zero.

## svqxtnb[_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqxtnb%5B_s32%5D

### Signature (source notation)

```c
svint16_t svqxtnb[_s32](svint32_t op);
```

### Description

Saturating extract narrow (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Move / Saturating narrow

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
    "register": "Zop.S"
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
SQXTNB Zresult.H, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQXTNB--Signed-saturating-extract-narrow--bottom--

### Operation

Source operation ID: `SveOperation_svqxtnb_s32`

**Operation**



Return a vector in which, for each even element index *i*:




- element *i* contains the result of saturating `op[i / 2]` to `int16_t`.
- element *i* + 1 contains zero.

## svqxtnb[_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqxtnb%5B_s64%5D

### Signature (source notation)

```c
svint32_t svqxtnb[_s64](svint64_t op);
```

### Description

Saturating extract narrow (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Move / Saturating narrow

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
    "register": "Zop.D"
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
SQXTNB Zresult.S, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQXTNB--Signed-saturating-extract-narrow--bottom--

### Operation

Source operation ID: `SveOperation_svqxtnb_s64`

**Operation**



Return a vector in which, for each even element index *i*:




- element *i* contains the result of saturating `op[i / 2]` to `int32_t`.
- element *i* + 1 contains zero.

## svqxtnb[_u16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqxtnb%5B_u16%5D

### Signature (source notation)

```c
svuint8_t svqxtnb[_u16](svuint16_t op);
```

### Description

Saturating extract narrow (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Move / Saturating narrow

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
    "register": "Zop.H"
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
UQXTNB Zresult.B, Zop.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQXTNB--Unsigned-saturating-extract-narrow--bottom--

### Operation

Source operation ID: `SveOperation_svqxtnb_u16`

**Operation**



Return a vector in which, for each even element index *i*:




- element *i* contains the result of saturating `op[i / 2]` to `uint8_t`.
- element *i* + 1 contains zero.

## svqxtnb[_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqxtnb%5B_u32%5D

### Signature (source notation)

```c
svuint16_t svqxtnb[_u32](svuint32_t op);
```

### Description

Saturating extract narrow (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Move / Saturating narrow

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
    "register": "Zop.S"
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
UQXTNB Zresult.H, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQXTNB--Unsigned-saturating-extract-narrow--bottom--

### Operation

Source operation ID: `SveOperation_svqxtnb_u32`

**Operation**



Return a vector in which, for each even element index *i*:




- element *i* contains the result of saturating `op[i / 2]` to `uint16_t`.
- element *i* + 1 contains zero.

## svqxtnb[_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqxtnb%5B_u64%5D

### Signature (source notation)

```c
svuint32_t svqxtnb[_u64](svuint64_t op);
```

### Description

Saturating extract narrow (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Move / Saturating narrow

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
    "register": "Zop.D"
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
UQXTNB Zresult.S, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQXTNB--Unsigned-saturating-extract-narrow--bottom--

### Operation

Source operation ID: `SveOperation_svqxtnb_u64`

**Operation**



Return a vector in which, for each even element index *i*:




- element *i* contains the result of saturating `op[i / 2]` to `uint32_t`.
- element *i* + 1 contains zero.

## svqxtnt[_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqxtnt%5B_s16%5D

### Signature (source notation)

```c
svint8_t svqxtnt[_s16](svint8_t even, svint16_t op);
```

### Description

Saturating extract narrow (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Move / Saturating narrow

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
  "op": {
    "register": "Zop.H"
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
SQXTNT Ztied.B, Zop.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQXTNT--Signed-saturating-extract-narrow--top--

### Operation

Source operation ID: `SveOperation_svqxtnt_s16`

**Operation**



Return a vector in which, for each even element index *i*:




- element *i* contains `even[i]`.
- element *i* + 1 contains the result of saturating `op[i / 2]` to `int8_t`.

## svqxtnt[_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqxtnt%5B_s32%5D

### Signature (source notation)

```c
svint16_t svqxtnt[_s32](svint16_t even, svint32_t op);
```

### Description

Saturating extract narrow (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Move / Saturating narrow

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
  "op": {
    "register": "Zop.S"
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
SQXTNT Ztied.H, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQXTNT--Signed-saturating-extract-narrow--top--

### Operation

Source operation ID: `SveOperation_svqxtnt_s32`

**Operation**



Return a vector in which, for each even element index *i*:




- element *i* contains `even[i]`.
- element *i* + 1 contains the result of saturating `op[i / 2]` to `int16_t`.

## svqxtnt[_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqxtnt%5B_s64%5D

### Signature (source notation)

```c
svint32_t svqxtnt[_s64](svint32_t even, svint64_t op);
```

### Description

Saturating extract narrow (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Move / Saturating narrow

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
  "op": {
    "register": "Zop.D"
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
SQXTNT Ztied.S, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQXTNT--Signed-saturating-extract-narrow--top--

### Operation

Source operation ID: `SveOperation_svqxtnt_s64`

**Operation**



Return a vector in which, for each even element index *i*:




- element *i* contains `even[i]`.
- element *i* + 1 contains the result of saturating `op[i / 2]` to `int32_t`.

## svqxtnt[_u16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqxtnt%5B_u16%5D

### Signature (source notation)

```c
svuint8_t svqxtnt[_u16](svuint8_t even, svuint16_t op);
```

### Description

Saturating extract narrow (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Move / Saturating narrow

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
  "op": {
    "register": "Zop.H"
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
UQXTNT Ztied.B, Zop.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQXTNT--Unsigned-saturating-extract-narrow--top--

### Operation

Source operation ID: `SveOperation_svqxtnt_u16`

**Operation**



Return a vector in which, for each even element index *i*:




- element *i* contains `even[i]`.
- element *i* + 1 contains the result of saturating `op[i / 2]` to `uint8_t`.

## svqxtnt[_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqxtnt%5B_u32%5D

### Signature (source notation)

```c
svuint16_t svqxtnt[_u32](svuint16_t even, svuint32_t op);
```

### Description

Saturating extract narrow (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Move / Saturating narrow

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
  "op": {
    "register": "Zop.S"
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
UQXTNT Ztied.H, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQXTNT--Unsigned-saturating-extract-narrow--top--

### Operation

Source operation ID: `SveOperation_svqxtnt_u32`

**Operation**



Return a vector in which, for each even element index *i*:




- element *i* contains `even[i]`.
- element *i* + 1 contains the result of saturating `op[i / 2]` to `uint16_t`.

## svqxtnt[_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqxtnt%5B_u64%5D

### Signature (source notation)

```c
svuint32_t svqxtnt[_u64](svuint32_t even, svuint64_t op);
```

### Description

Saturating extract narrow (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Move / Saturating narrow

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
  "op": {
    "register": "Zop.D"
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
UQXTNT Ztied.S, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UQXTNT--Unsigned-saturating-extract-narrow--top--

### Operation

Source operation ID: `SveOperation_svqxtnt_u64`

**Operation**



Return a vector in which, for each even element index *i*:




- element *i* contains `even[i]`.
- element *i* + 1 contains the result of saturating `op[i / 2]` to `uint32_t`.

## svqxtunb[_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqxtunb%5B_s16%5D

### Signature (source notation)

```c
svuint8_t svqxtunb[_s16](svint16_t op);
```

### Description

Saturating extract unsigned narrow (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Move / Saturating narrow

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
    "register": "Zop.H"
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
SQXTUNB Zresult.B, Zop.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQXTUNB--Signed-saturating-unsigned-extract-narrow--bottom--

### Operation

Source operation ID: `SveOperation_svqxtnb_u16`

**Operation**



Return a vector in which, for each even element index *i*:




- element *i* contains the result of saturating `op[i / 2]` to `uint8_t`.
- element *i* + 1 contains zero.

## svqxtunb[_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqxtunb%5B_s32%5D

### Signature (source notation)

```c
svuint16_t svqxtunb[_s32](svint32_t op);
```

### Description

Saturating extract unsigned narrow (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Move / Saturating narrow

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
    "register": "Zop.S"
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
SQXTUNB Zresult.H, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQXTUNB--Signed-saturating-unsigned-extract-narrow--bottom--

### Operation

Source operation ID: `SveOperation_svqxtnb_u32`

**Operation**



Return a vector in which, for each even element index *i*:




- element *i* contains the result of saturating `op[i / 2]` to `uint16_t`.
- element *i* + 1 contains zero.

## svqxtunb[_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqxtunb%5B_s64%5D

### Signature (source notation)

```c
svuint32_t svqxtunb[_s64](svint64_t op);
```

### Description

Saturating extract unsigned narrow (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Move / Saturating narrow

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
    "register": "Zop.D"
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
SQXTUNB Zresult.S, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQXTUNB--Signed-saturating-unsigned-extract-narrow--bottom--

### Operation

Source operation ID: `SveOperation_svqxtnb_u64`

**Operation**



Return a vector in which, for each even element index *i*:




- element *i* contains the result of saturating `op[i / 2]` to `uint32_t`.
- element *i* + 1 contains zero.

## svqxtunt[_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqxtunt%5B_s16%5D

### Signature (source notation)

```c
svuint8_t svqxtunt[_s16](svuint8_t even, svint16_t op);
```

### Description

Saturating extract unsigned narrow (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Move / Saturating narrow

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
  "op": {
    "register": "Zop.H"
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
SQXTUNT Ztied.B, Zop.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQXTUNT--Signed-saturating-unsigned-extract-narrow--top--

### Operation

Source operation ID: `SveOperation_svqxtnt_u16`

**Operation**



Return a vector in which, for each even element index *i*:




- element *i* contains `even[i]`.
- element *i* + 1 contains the result of saturating `op[i / 2]` to `uint8_t`.

## svqxtunt[_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqxtunt%5B_s32%5D

### Signature (source notation)

```c
svuint16_t svqxtunt[_s32](svuint16_t even, svint32_t op);
```

### Description

Saturating extract unsigned narrow (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Move / Saturating narrow

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
  "op": {
    "register": "Zop.S"
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
SQXTUNT Ztied.H, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQXTUNT--Signed-saturating-unsigned-extract-narrow--top--

### Operation

Source operation ID: `SveOperation_svqxtnt_u32`

**Operation**



Return a vector in which, for each even element index *i*:




- element *i* contains `even[i]`.
- element *i* + 1 contains the result of saturating `op[i / 2]` to `uint16_t`.

## svqxtunt[_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqxtunt%5B_s64%5D

### Signature (source notation)

```c
svuint32_t svqxtunt[_s64](svuint32_t even, svint64_t op);
```

### Description

Saturating extract unsigned narrow (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Move / Saturating narrow

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
  "op": {
    "register": "Zop.D"
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
SQXTUNT Ztied.S, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQXTUNT--Signed-saturating-unsigned-extract-narrow--top--

### Operation

Source operation ID: `SveOperation_svqxtnt_u64`

**Operation**



Return a vector in which, for each even element index *i*:




- element *i* contains `even[i]`.
- element *i* + 1 contains the result of saturating `op[i / 2]` to `uint32_t`.

