# SME / Vector manipulation / Reverse elements — Part 2

## svrevd[_s16]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrevd%5B_s16%5D_x

### Signature (source notation)

```c
svint16_t svrevd[_s16]_x(svbool_t pg, svint16_t zn);
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

## svrevd[_s16]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrevd%5B_s16%5D_z

### Signature (source notation)

```c
svint16_t svrevd[_s16]_z(svbool_t pg, svint16_t zn);
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

## svrevd[_s32]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrevd%5B_s32%5D_m

### Signature (source notation)

```c
svint32_t svrevd[_s32]_m(svint32_t zd, svbool_t pg, svint32_t zn);
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
  "return_base_type": "int32",
  "element_bit_size": "32",
  "value": "svint32_t"
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

## svrevd[_s32]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrevd%5B_s32%5D_x

### Signature (source notation)

```c
svint32_t svrevd[_s32]_x(svbool_t pg, svint32_t zn);
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
  "return_base_type": "int32",
  "element_bit_size": "32",
  "value": "svint32_t"
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

## svrevd[_s32]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrevd%5B_s32%5D_z

### Signature (source notation)

```c
svint32_t svrevd[_s32]_z(svbool_t pg, svint32_t zn);
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
  "return_base_type": "int32",
  "element_bit_size": "32",
  "value": "svint32_t"
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

## svrevd[_s64]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrevd%5B_s64%5D_m

### Signature (source notation)

```c
svint64_t svrevd[_s64]_m(svint64_t zd, svbool_t pg, svint64_t zn);
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
  "return_base_type": "int64",
  "element_bit_size": "64",
  "value": "svint64_t"
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

## svrevd[_s64]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrevd%5B_s64%5D_x

### Signature (source notation)

```c
svint64_t svrevd[_s64]_x(svbool_t pg, svint64_t zn);
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
  "return_base_type": "int64",
  "element_bit_size": "64",
  "value": "svint64_t"
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

## svrevd[_s64]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrevd%5B_s64%5D_z

### Signature (source notation)

```c
svint64_t svrevd[_s64]_z(svbool_t pg, svint64_t zn);
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
  "return_base_type": "int64",
  "element_bit_size": "64",
  "value": "svint64_t"
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
MOV Zreg1.B, #0
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOV--immediate--unpredicated---Move-signed-immediate-to-vector-elements--unpredicated---an-alias-of-DUP--immediate--

```asm
REVD Zreg1.Q, Preg1/M, Zreg2.Q
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/REVD--Reverse-64-bit-doublewords-in-elements--predicated--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svrevd[_s8]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrevd%5B_s8%5D_m

### Signature (source notation)

```c
svint8_t svrevd[_s8]_m(svint8_t zd, svbool_t pg, svint8_t zn);
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
  "return_base_type": "int8",
  "element_bit_size": "8",
  "value": "svint8_t"
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

## svrevd[_s8]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrevd%5B_s8%5D_x

### Signature (source notation)

```c
svint8_t svrevd[_s8]_x(svbool_t pg, svint8_t zn);
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

## svrevd[_s8]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrevd%5B_s8%5D_z

### Signature (source notation)

```c
svint8_t svrevd[_s8]_z(svbool_t pg, svint8_t zn);
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

## svrevd[_u16]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrevd%5B_u16%5D_m

### Signature (source notation)

```c
svuint16_t svrevd[_u16]_m(svuint16_t zd, svbool_t pg, svuint16_t zn);
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
  "return_base_type": "uint16",
  "element_bit_size": "16",
  "value": "svuint16_t"
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

## svrevd[_u16]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrevd%5B_u16%5D_x

### Signature (source notation)

```c
svuint16_t svrevd[_u16]_x(svbool_t pg, svuint16_t zn);
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

## svrevd[_u16]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrevd%5B_u16%5D_z

### Signature (source notation)

```c
svuint16_t svrevd[_u16]_z(svbool_t pg, svuint16_t zn);
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

## svrevd[_u32]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrevd%5B_u32%5D_m

### Signature (source notation)

```c
svuint32_t svrevd[_u32]_m(svuint32_t zd, svbool_t pg, svuint32_t zn);
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
  "return_base_type": "uint32",
  "element_bit_size": "32",
  "value": "svuint32_t"
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

## svrevd[_u32]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrevd%5B_u32%5D_x

### Signature (source notation)

```c
svuint32_t svrevd[_u32]_x(svbool_t pg, svuint32_t zn);
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
  "return_base_type": "uint32",
  "element_bit_size": "32",
  "value": "svuint32_t"
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

## svrevd[_u32]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrevd%5B_u32%5D_z

### Signature (source notation)

```c
svuint32_t svrevd[_u32]_z(svbool_t pg, svuint32_t zn);
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
  "return_base_type": "uint32",
  "element_bit_size": "32",
  "value": "svuint32_t"
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

## svrevd[_u64]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrevd%5B_u64%5D_m

### Signature (source notation)

```c
svuint64_t svrevd[_u64]_m(svuint64_t zd, svbool_t pg, svuint64_t zn);
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
  "return_base_type": "uint64",
  "element_bit_size": "64",
  "value": "svuint64_t"
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

## svrevd[_u64]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrevd%5B_u64%5D_x

### Signature (source notation)

```c
svuint64_t svrevd[_u64]_x(svbool_t pg, svuint64_t zn);
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
  "return_base_type": "uint64",
  "element_bit_size": "64",
  "value": "svuint64_t"
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

## svrevd[_u64]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrevd%5B_u64%5D_z

### Signature (source notation)

```c
svuint64_t svrevd[_u64]_z(svbool_t pg, svuint64_t zn);
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
  "return_base_type": "uint64",
  "element_bit_size": "64",
  "value": "svuint64_t"
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
MOV Zreg1.B, #0
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOV--immediate--unpredicated---Move-signed-immediate-to-vector-elements--unpredicated---an-alias-of-DUP--immediate--

```asm
REVD Zreg1.Q, Preg1/M, Zreg2.Q
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/REVD--Reverse-64-bit-doublewords-in-elements--predicated--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svrevd[_u8]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrevd%5B_u8%5D_m

### Signature (source notation)

```c
svuint8_t svrevd[_u8]_m(svuint8_t zd, svbool_t pg, svuint8_t zn);
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
  "return_base_type": "uint8",
  "element_bit_size": "8",
  "value": "svuint8_t"
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

## svrevd[_u8]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrevd%5B_u8%5D_x

### Signature (source notation)

```c
svuint8_t svrevd[_u8]_x(svbool_t pg, svuint8_t zn);
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

## svrevd[_u8]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrevd%5B_u8%5D_z

### Signature (source notation)

```c
svuint8_t svrevd[_u8]_z(svbool_t pg, svuint8_t zn);
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

## svrevh[_s32]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrevh%5B_s32%5D_m

### Signature (source notation)

```c
svint32_t svrevh[_s32]_m(svint32_t inactive, svbool_t pg, svint32_t op);
```

### Description

Reverse halfwords within elements

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
REVH Ztied.S, Pg/M, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/REVB--REVH--REVW--Reverse-bytes---halfwords---words-within-elements--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zinactive
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
REVH Zresult.S, Pg/M, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/REVB--REVH--REVW--Reverse-bytes---halfwords---words-within-elements--predicated--

### Operation

Source operation ID: `SveOperation_svrevh_s32_m`

**Operation**



Return a vector in which each active element *i* contains the result of reversing the order of the 16-bit halfwords in `op[i]`. Take the inactive elements of the result from the corresponding elements of `inactive`.

## svrevh[_s32]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrevh%5B_s32%5D_x

### Signature (source notation)

```c
svint32_t svrevh[_s32]_x(svbool_t pg, svint32_t op);
```

### Description

Reverse halfwords within elements

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
REVH Ztied.S, Pg/M, Ztied.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/REVB--REVH--REVW--Reverse-bytes---halfwords---words-within-elements--predicated--

When result and op are in different registers, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
REVH Zresult.S, Pg/M, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/REVB--REVH--REVW--Reverse-bytes---halfwords---words-within-elements--predicated--

### Operation

Source operation ID: `SveOperation_svrevh_s32_x`

**Operation**



Return a vector in which each active element *i* contains the result of reversing the order of the 16-bit halfwords in `op[i]`. The inactive elements of the result have arbitrary, undefined values.

## svrevh[_s32]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrevh%5B_s32%5D_z

### Signature (source notation)

```c
svint32_t svrevh[_s32]_z(svbool_t pg, svint32_t op);
```

### Description

Reverse halfwords within elements

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
REVH Zresult.S, Pg/M, Zop.S  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/REVB--REVH--REVW--Reverse-bytes---halfwords---words-within-elements--predicated--

### Operation

Source operation ID: `SveOperation_svrevh_s32_z`

**Operation**



Return a vector in which each active element *i* contains the result of reversing the order of the 16-bit halfwords in `op[i]`. Set the inactive elements of the result to zero.



**[1]** Note that `result` must be in a different register from `op`

## svrevh[_s64]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrevh%5B_s64%5D_m

### Signature (source notation)

```c
svint64_t svrevh[_s64]_m(svint64_t inactive, svbool_t pg, svint64_t op);
```

### Description

Reverse halfwords within elements

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
REVH Ztied.D, Pg/M, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/REVB--REVH--REVW--Reverse-bytes---halfwords---words-within-elements--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zinactive
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
REVH Zresult.D, Pg/M, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/REVB--REVH--REVW--Reverse-bytes---halfwords---words-within-elements--predicated--

### Operation

Source operation ID: `SveOperation_svrevh_s32_m`

**Operation**



Return a vector in which each active element *i* contains the result of reversing the order of the 16-bit halfwords in `op[i]`. Take the inactive elements of the result from the corresponding elements of `inactive`.

## svrevh[_s64]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrevh%5B_s64%5D_x

### Signature (source notation)

```c
svint64_t svrevh[_s64]_x(svbool_t pg, svint64_t op);
```

### Description

Reverse halfwords within elements

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
REVH Ztied.D, Pg/M, Ztied.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/REVB--REVH--REVW--Reverse-bytes---halfwords---words-within-elements--predicated--

When result and op are in different registers, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
REVH Zresult.D, Pg/M, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/REVB--REVH--REVW--Reverse-bytes---halfwords---words-within-elements--predicated--

### Operation

Source operation ID: `SveOperation_svrevh_s32_x`

**Operation**



Return a vector in which each active element *i* contains the result of reversing the order of the 16-bit halfwords in `op[i]`. The inactive elements of the result have arbitrary, undefined values.

## svrevh[_s64]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrevh%5B_s64%5D_z

### Signature (source notation)

```c
svint64_t svrevh[_s64]_z(svbool_t pg, svint64_t op);
```

### Description

Reverse halfwords within elements

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
REVH Zresult.D, Pg/M, Zop.D  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/REVB--REVH--REVW--Reverse-bytes---halfwords---words-within-elements--predicated--

### Operation

Source operation ID: `SveOperation_svrevh_s32_z`

**Operation**



Return a vector in which each active element *i* contains the result of reversing the order of the 16-bit halfwords in `op[i]`. Set the inactive elements of the result to zero.



**[1]** Note that `result` must be in a different register from `op`

## svrevh[_u32]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrevh%5B_u32%5D_m

### Signature (source notation)

```c
svuint32_t svrevh[_u32]_m(svuint32_t inactive, svbool_t pg, svuint32_t op);
```

### Description

Reverse halfwords within elements

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
REVH Ztied.S, Pg/M, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/REVB--REVH--REVW--Reverse-bytes---halfwords---words-within-elements--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zinactive
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
REVH Zresult.S, Pg/M, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/REVB--REVH--REVW--Reverse-bytes---halfwords---words-within-elements--predicated--

### Operation

Source operation ID: `SveOperation_svrevh_s32_m`

**Operation**



Return a vector in which each active element *i* contains the result of reversing the order of the 16-bit halfwords in `op[i]`. Take the inactive elements of the result from the corresponding elements of `inactive`.

## svrevh[_u32]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrevh%5B_u32%5D_x

### Signature (source notation)

```c
svuint32_t svrevh[_u32]_x(svbool_t pg, svuint32_t op);
```

### Description

Reverse halfwords within elements

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
REVH Ztied.S, Pg/M, Ztied.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/REVB--REVH--REVW--Reverse-bytes---halfwords---words-within-elements--predicated--

When result and op are in different registers, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
REVH Zresult.S, Pg/M, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/REVB--REVH--REVW--Reverse-bytes---halfwords---words-within-elements--predicated--

### Operation

Source operation ID: `SveOperation_svrevh_s32_x`

**Operation**



Return a vector in which each active element *i* contains the result of reversing the order of the 16-bit halfwords in `op[i]`. The inactive elements of the result have arbitrary, undefined values.

## svrevh[_u32]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrevh%5B_u32%5D_z

### Signature (source notation)

```c
svuint32_t svrevh[_u32]_z(svbool_t pg, svuint32_t op);
```

### Description

Reverse halfwords within elements

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
REVH Zresult.S, Pg/M, Zop.S  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/REVB--REVH--REVW--Reverse-bytes---halfwords---words-within-elements--predicated--

### Operation

Source operation ID: `SveOperation_svrevh_s32_z`

**Operation**



Return a vector in which each active element *i* contains the result of reversing the order of the 16-bit halfwords in `op[i]`. Set the inactive elements of the result to zero.



**[1]** Note that `result` must be in a different register from `op`

## svrevh[_u64]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrevh%5B_u64%5D_m

### Signature (source notation)

```c
svuint64_t svrevh[_u64]_m(svuint64_t inactive, svbool_t pg, svuint64_t op);
```

### Description

Reverse halfwords within elements

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
REVH Ztied.D, Pg/M, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/REVB--REVH--REVW--Reverse-bytes---halfwords---words-within-elements--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zinactive
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
REVH Zresult.D, Pg/M, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/REVB--REVH--REVW--Reverse-bytes---halfwords---words-within-elements--predicated--

### Operation

Source operation ID: `SveOperation_svrevh_s32_m`

**Operation**



Return a vector in which each active element *i* contains the result of reversing the order of the 16-bit halfwords in `op[i]`. Take the inactive elements of the result from the corresponding elements of `inactive`.

## svrevh[_u64]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrevh%5B_u64%5D_x

### Signature (source notation)

```c
svuint64_t svrevh[_u64]_x(svbool_t pg, svuint64_t op);
```

### Description

Reverse halfwords within elements

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
REVH Ztied.D, Pg/M, Ztied.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/REVB--REVH--REVW--Reverse-bytes---halfwords---words-within-elements--predicated--

When result and op are in different registers, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
REVH Zresult.D, Pg/M, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/REVB--REVH--REVW--Reverse-bytes---halfwords---words-within-elements--predicated--

### Operation

Source operation ID: `SveOperation_svrevh_s32_x`

**Operation**



Return a vector in which each active element *i* contains the result of reversing the order of the 16-bit halfwords in `op[i]`. The inactive elements of the result have arbitrary, undefined values.

## svrevh[_u64]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrevh%5B_u64%5D_z

### Signature (source notation)

```c
svuint64_t svrevh[_u64]_z(svbool_t pg, svuint64_t op);
```

### Description

Reverse halfwords within elements

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
REVH Zresult.D, Pg/M, Zop.D  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/REVB--REVH--REVW--Reverse-bytes---halfwords---words-within-elements--predicated--

### Operation

Source operation ID: `SveOperation_svrevh_s32_z`

**Operation**



Return a vector in which each active element *i* contains the result of reversing the order of the 16-bit halfwords in `op[i]`. Set the inactive elements of the result to zero.



**[1]** Note that `result` must be in a different register from `op`

## svrevw[_s64]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrevw%5B_s64%5D_m

### Signature (source notation)

```c
svint64_t svrevw[_s64]_m(svint64_t inactive, svbool_t pg, svint64_t op);
```

### Description

Reverse words within elements

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
REVW Ztied.D, Pg/M, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/REVB--REVH--REVW--Reverse-bytes---halfwords---words-within-elements--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zinactive
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
REVW Zresult.D, Pg/M, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/REVB--REVH--REVW--Reverse-bytes---halfwords---words-within-elements--predicated--

### Operation

Source operation ID: `SveOperation_svrevw_s64_m`

**Operation**



Return a vector in which each active element *i* contains the result of reversing the order of the 32-bit words in `op[i]`. Take the inactive elements of the result from the corresponding elements of `inactive`.

## svrevw[_s64]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrevw%5B_s64%5D_x

### Signature (source notation)

```c
svint64_t svrevw[_s64]_x(svbool_t pg, svint64_t op);
```

### Description

Reverse words within elements

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
REVW Ztied.D, Pg/M, Ztied.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/REVB--REVH--REVW--Reverse-bytes---halfwords---words-within-elements--predicated--

When result and op are in different registers, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
REVW Zresult.D, Pg/M, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/REVB--REVH--REVW--Reverse-bytes---halfwords---words-within-elements--predicated--

### Operation

Source operation ID: `SveOperation_svrevw_s64_x`

**Operation**



Return a vector in which each active element *i* contains the result of reversing the order of the 32-bit words in `op[i]`. The inactive elements of the result have arbitrary, undefined values.

## svrevw[_s64]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrevw%5B_s64%5D_z

### Signature (source notation)

```c
svint64_t svrevw[_s64]_z(svbool_t pg, svint64_t op);
```

### Description

Reverse words within elements

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
REVW Zresult.D, Pg/M, Zop.D  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/REVB--REVH--REVW--Reverse-bytes---halfwords---words-within-elements--predicated--

### Operation

Source operation ID: `SveOperation_svrevw_s64_z`

**Operation**



Return a vector in which each active element *i* contains the result of reversing the order of the 32-bit words in `op[i]`. Set the inactive elements of the result to zero.



**[1]** Note that `result` must be in a different register from `op`

## svrevw[_u64]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrevw%5B_u64%5D_m

### Signature (source notation)

```c
svuint64_t svrevw[_u64]_m(svuint64_t inactive, svbool_t pg, svuint64_t op);
```

### Description

Reverse words within elements

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
REVW Ztied.D, Pg/M, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/REVB--REVH--REVW--Reverse-bytes---halfwords---words-within-elements--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zinactive
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
REVW Zresult.D, Pg/M, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/REVB--REVH--REVW--Reverse-bytes---halfwords---words-within-elements--predicated--

### Operation

Source operation ID: `SveOperation_svrevw_s64_m`

**Operation**



Return a vector in which each active element *i* contains the result of reversing the order of the 32-bit words in `op[i]`. Take the inactive elements of the result from the corresponding elements of `inactive`.

## svrevw[_u64]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrevw%5B_u64%5D_x

### Signature (source notation)

```c
svuint64_t svrevw[_u64]_x(svbool_t pg, svuint64_t op);
```

### Description

Reverse words within elements

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
REVW Ztied.D, Pg/M, Ztied.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/REVB--REVH--REVW--Reverse-bytes---halfwords---words-within-elements--predicated--

When result and op are in different registers, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
REVW Zresult.D, Pg/M, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/REVB--REVH--REVW--Reverse-bytes---halfwords---words-within-elements--predicated--

### Operation

Source operation ID: `SveOperation_svrevw_s64_x`

**Operation**



Return a vector in which each active element *i* contains the result of reversing the order of the 32-bit words in `op[i]`. The inactive elements of the result have arbitrary, undefined values.

## svrevw[_u64]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrevw%5B_u64%5D_z

### Signature (source notation)

```c
svuint64_t svrevw[_u64]_z(svbool_t pg, svuint64_t op);
```

### Description

Reverse words within elements

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
REVW Zresult.D, Pg/M, Zop.D  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/REVB--REVH--REVW--Reverse-bytes---halfwords---words-within-elements--predicated--

### Operation

Source operation ID: `SveOperation_svrevw_s64_z`

**Operation**



Return a vector in which each active element *i* contains the result of reversing the order of the 32-bit words in `op[i]`. Set the inactive elements of the result to zero.



**[1]** Note that `result` must be in a different register from `op`

