# SME / Logical / OR — Part 1

## svorqv[_s16]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svorqv%5B_s16%5D

### Signature (source notation)

```c
int16x8_t svorqv[_s16](svbool_t pg, svint16_t zn);
```

### Description

Bitwise inclusive OR reduction of quadword vector segments

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Logical / OR

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
  "return_base_type": "int16x8_t",
  "element_bit_size": "16",
  "value": "int16x8_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Preg1"
  },
  "zn": {
    "register": "Zreg1.H"
  }
}
```

### Result mapping

```json
[
  {
    "Vreg1.8H": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
ORQV Vreg1.8H, Preg1, Zreg1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/ORQV--Bitwise-inclusive-OR-reduction-of-quadword-vector-segments-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svorqv[_s32]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svorqv%5B_s32%5D

### Signature (source notation)

```c
int32x4_t svorqv[_s32](svbool_t pg, svint32_t zn);
```

### Description

Bitwise inclusive OR reduction of quadword vector segments

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Logical / OR

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
  "return_base_type": "int32x4_t",
  "element_bit_size": "32",
  "value": "int32x4_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Preg1"
  },
  "zn": {
    "register": "Zreg1.S"
  }
}
```

### Result mapping

```json
[
  {
    "Vreg1.4S": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
ORQV Vreg1.4S, Preg1, Zreg1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/ORQV--Bitwise-inclusive-OR-reduction-of-quadword-vector-segments-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svorqv[_s64]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svorqv%5B_s64%5D

### Signature (source notation)

```c
int64x2_t svorqv[_s64](svbool_t pg, svint64_t zn);
```

### Description

Bitwise inclusive OR reduction of quadword vector segments

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Logical / OR

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
  "return_base_type": "int64x2_t",
  "element_bit_size": "64",
  "value": "int64x2_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Preg1"
  },
  "zn": {
    "register": "Zreg1.D"
  }
}
```

### Result mapping

```json
[
  {
    "Vreg1.2D": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
ORQV Vreg1.2D, Preg1, Zreg1.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/ORQV--Bitwise-inclusive-OR-reduction-of-quadword-vector-segments-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svorqv[_s8]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svorqv%5B_s8%5D

### Signature (source notation)

```c
int8x16_t svorqv[_s8](svbool_t pg, svint8_t zn);
```

### Description

Bitwise inclusive OR reduction of quadword vector segments

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Logical / OR

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
  "return_base_type": "int8x16_t",
  "element_bit_size": "8",
  "value": "int8x16_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Preg1"
  },
  "zn": {
    "register": "Zreg1.B"
  }
}
```

### Result mapping

```json
[
  {
    "Vreg1.16B": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
ORQV Vreg1.16B, Preg1, Zreg1.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/ORQV--Bitwise-inclusive-OR-reduction-of-quadword-vector-segments-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svorqv[_u16]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svorqv%5B_u16%5D

### Signature (source notation)

```c
uint16x8_t svorqv[_u16](svbool_t pg, svuint16_t zn);
```

### Description

Bitwise inclusive OR reduction of quadword vector segments

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Logical / OR

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
  "return_base_type": "uint16x8_t",
  "element_bit_size": "16",
  "value": "uint16x8_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Preg1"
  },
  "zn": {
    "register": "Zreg1.H"
  }
}
```

### Result mapping

```json
[
  {
    "Vreg1.8H": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
ORQV Vreg1.8H, Preg1, Zreg1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/ORQV--Bitwise-inclusive-OR-reduction-of-quadword-vector-segments-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svorqv[_u32]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svorqv%5B_u32%5D

### Signature (source notation)

```c
uint32x4_t svorqv[_u32](svbool_t pg, svuint32_t zn);
```

### Description

Bitwise inclusive OR reduction of quadword vector segments

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Logical / OR

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
  "return_base_type": "uint32x4_t",
  "element_bit_size": "32",
  "value": "uint32x4_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Preg1"
  },
  "zn": {
    "register": "Zreg1.S"
  }
}
```

### Result mapping

```json
[
  {
    "Vreg1.4S": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
ORQV Vreg1.4S, Preg1, Zreg1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/ORQV--Bitwise-inclusive-OR-reduction-of-quadword-vector-segments-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svorqv[_u64]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svorqv%5B_u64%5D

### Signature (source notation)

```c
uint64x2_t svorqv[_u64](svbool_t pg, svuint64_t zn);
```

### Description

Bitwise inclusive OR reduction of quadword vector segments

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Logical / OR

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
  "return_base_type": "uint64x2_t",
  "element_bit_size": "64",
  "value": "uint64x2_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Preg1"
  },
  "zn": {
    "register": "Zreg1.D"
  }
}
```

### Result mapping

```json
[
  {
    "Vreg1.2D": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
ORQV Vreg1.2D, Preg1, Zreg1.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/ORQV--Bitwise-inclusive-OR-reduction-of-quadword-vector-segments-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svorqv[_u8]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svorqv%5B_u8%5D

### Signature (source notation)

```c
uint8x16_t svorqv[_u8](svbool_t pg, svuint8_t zn);
```

### Description

Bitwise inclusive OR reduction of quadword vector segments

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Logical / OR

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
  "return_base_type": "uint8x16_t",
  "element_bit_size": "8",
  "value": "uint8x16_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Preg1"
  },
  "zn": {
    "register": "Zreg1.B"
  }
}
```

### Result mapping

```json
[
  {
    "Vreg1.16B": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
ORQV Vreg1.16B, Preg1, Zreg1.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/ORQV--Bitwise-inclusive-OR-reduction-of-quadword-vector-segments-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svorr[_b]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svorr%5B_b%5D_z

### Signature (source notation)

```c
svbool_t svorr[_b]_z(svbool_t pg, svbool_t op1, svbool_t op2);
```

### Description

Bitwise inclusive OR

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / OR

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
  "pg": {
    "register": "Pg"
  },
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
ORR Presult.B, Pg/Z, Pop1.B, Pop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ORR--predicates---Bitwise-inclusive-OR-predicates-

### Operation

Source operation ID: `SveOperation_svorr_b_z`

**Operation**



Return a predicate in which each active element *i* contains `op1[i] | op2[i]`. Set the inactive elements of the result to zero.

## svorr[_n_s16]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svorr%5B_n_s16%5D_m

### Signature (source notation)

```c
svint16_t svorr[_n_s16]_m(svbool_t pg, svint16_t op1, int16_t op2);
```

### Description

Bitwise inclusive OR

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / OR

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
  "op1": {
    "register": "Zop1.H|Ztied1.H"
  },
  "op2": {
    "register": "Zop2.H[*]"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.H|Ztied1.H": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
ORR Ztied1.H, Pg/M, Ztied1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ORR--vectors--predicated---Bitwise-inclusive-OR--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
ORR Zresult.H, Pg/M, Zresult.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ORR--vectors--predicated---Bitwise-inclusive-OR--predicated--

### Operation

Source operation ID: `SveOperation_svorr_n_s8_m`

**Operation**



Return a vector in which each active element *i* contains `op1[i] | op2`. Take the inactive elements of the result from the corresponding elements of `op1`.

## svorr[_n_s16]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svorr%5B_n_s16%5D_x

### Signature (source notation)

```c
svint16_t svorr[_n_s16]_x(svbool_t pg, svint16_t op1, int16_t op2);
```

### Description

Bitwise inclusive OR

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / OR

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
  "op1": {
    "register": "Zop1.H|Ztied1.H"
  },
  "op2": {
    "register": "Zop2.H[*]|Ztied2.H[*]"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.H|Ztied1.H|Ztied2.H": "result"
  }
]
```

### Instruction mapping

When op2 is a logical immediate[1], this intrinsic can use:

```asm
ORR Ztied1.H, Ztied1.H, #op2  // [2]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ORR--immediate---Bitwise-inclusive-OR-with-immediate--unpredicated--

When result and op1 are in the same register, this intrinsic can use:

```asm
ORR Ztied1.H, Pg/M, Ztied1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ORR--vectors--predicated---Bitwise-inclusive-OR--predicated--

When result and op2 are in the same register, this intrinsic can use:

```asm
ORR Ztied2.H, Pg/M, Ztied2.H, Zop1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ORR--vectors--predicated---Bitwise-inclusive-OR--predicated--

The general implementation is:

```asm
ORR Zresult.D, Zop1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ORR--vectors--unpredicated---Bitwise-inclusive-OR--unpredicated--

### Operation

Source operation ID: `SveOperation_svorr_n_s8_x`

**Operation**



Return a vector in which each active element *i* contains `op1[i] | op2`. The inactive elements of the result have arbitrary, undefined values.



**[1]** This is true if op2 is filled by some replicated bitmask *b* for which either all 0s in *b* are consecutive or all 1s in *b* are consecutive.



**[2]** If instead `result` is in a different register from the inputs, the compiler can add a preceding [MOVPRFX (unpredicated)](https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--) instruction

## svorr[_n_s16]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svorr%5B_n_s16%5D_z

### Signature (source notation)

```c
svint16_t svorr[_n_s16]_z(svbool_t pg, svint16_t op1, int16_t op2);
```

### Description

Bitwise inclusive OR

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / OR

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
  "op1": {
    "register": "Zop1.H"
  },
  "op2": {
    "register": "Zop2.H[*]"
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

When result is in a different register from op2, this intrinsic can use:

```asm
MOVPRFX Zresult.H, Pg/Z, Zop1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
ORR Zresult.H, Pg/M, Zresult.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ORR--vectors--predicated---Bitwise-inclusive-OR--predicated--

When result is in a different register from op1, this intrinsic can use:

```asm
MOVPRFX Zresult.H, Pg/Z, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
ORR Zresult.H, Pg/M, Zresult.H, Zop1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ORR--vectors--predicated---Bitwise-inclusive-OR--predicated--

### Operation

Source operation ID: `SveOperation_svorr_n_s8_z`

**Operation**



Return a vector in which each active element *i* contains `op1[i] | op2`. Set the inactive elements of the result to zero.

## svorr[_n_s32]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svorr%5B_n_s32%5D_m

### Signature (source notation)

```c
svint32_t svorr[_n_s32]_m(svbool_t pg, svint32_t op1, int32_t op2);
```

### Description

Bitwise inclusive OR

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / OR

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
  "op1": {
    "register": "Zop1.S|Ztied1.S"
  },
  "op2": {
    "register": "Zop2.S[*]"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.S|Ztied1.S": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
ORR Ztied1.S, Pg/M, Ztied1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ORR--vectors--predicated---Bitwise-inclusive-OR--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
ORR Zresult.S, Pg/M, Zresult.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ORR--vectors--predicated---Bitwise-inclusive-OR--predicated--

### Operation

Source operation ID: `SveOperation_svorr_n_s8_m`

**Operation**



Return a vector in which each active element *i* contains `op1[i] | op2`. Take the inactive elements of the result from the corresponding elements of `op1`.

## svorr[_n_s32]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svorr%5B_n_s32%5D_x

### Signature (source notation)

```c
svint32_t svorr[_n_s32]_x(svbool_t pg, svint32_t op1, int32_t op2);
```

### Description

Bitwise inclusive OR

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / OR

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
  "op1": {
    "register": "Zop1.S|Ztied1.S"
  },
  "op2": {
    "register": "Zop2.S[*]|Ztied2.S[*]"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.S|Ztied1.S|Ztied2.S": "result"
  }
]
```

### Instruction mapping

When op2 is a logical immediate[1], this intrinsic can use:

```asm
ORR Ztied1.S, Ztied1.S, #op2  // [2]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ORR--immediate---Bitwise-inclusive-OR-with-immediate--unpredicated--

When result and op1 are in the same register, this intrinsic can use:

```asm
ORR Ztied1.S, Pg/M, Ztied1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ORR--vectors--predicated---Bitwise-inclusive-OR--predicated--

When result and op2 are in the same register, this intrinsic can use:

```asm
ORR Ztied2.S, Pg/M, Ztied2.S, Zop1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ORR--vectors--predicated---Bitwise-inclusive-OR--predicated--

The general implementation is:

```asm
ORR Zresult.D, Zop1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ORR--vectors--unpredicated---Bitwise-inclusive-OR--unpredicated--

### Operation

Source operation ID: `SveOperation_svorr_n_s8_x`

**Operation**



Return a vector in which each active element *i* contains `op1[i] | op2`. The inactive elements of the result have arbitrary, undefined values.



**[1]** This is true if op2 is filled by some replicated bitmask *b* for which either all 0s in *b* are consecutive or all 1s in *b* are consecutive.



**[2]** If instead `result` is in a different register from the inputs, the compiler can add a preceding [MOVPRFX (unpredicated)](https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--) instruction

## svorr[_n_s32]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svorr%5B_n_s32%5D_z

### Signature (source notation)

```c
svint32_t svorr[_n_s32]_z(svbool_t pg, svint32_t op1, int32_t op2);
```

### Description

Bitwise inclusive OR

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / OR

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
  "op1": {
    "register": "Zop1.S"
  },
  "op2": {
    "register": "Zop2.S[*]"
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

When result is in a different register from op2, this intrinsic can use:

```asm
MOVPRFX Zresult.S, Pg/Z, Zop1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
ORR Zresult.S, Pg/M, Zresult.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ORR--vectors--predicated---Bitwise-inclusive-OR--predicated--

When result is in a different register from op1, this intrinsic can use:

```asm
MOVPRFX Zresult.S, Pg/Z, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
ORR Zresult.S, Pg/M, Zresult.S, Zop1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ORR--vectors--predicated---Bitwise-inclusive-OR--predicated--

### Operation

Source operation ID: `SveOperation_svorr_n_s8_z`

**Operation**



Return a vector in which each active element *i* contains `op1[i] | op2`. Set the inactive elements of the result to zero.

## svorr[_n_s64]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svorr%5B_n_s64%5D_m

### Signature (source notation)

```c
svint64_t svorr[_n_s64]_m(svbool_t pg, svint64_t op1, int64_t op2);
```

### Description

Bitwise inclusive OR

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / OR

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
  "op1": {
    "register": "Zop1.D|Ztied1.D"
  },
  "op2": {
    "register": "Zop2.D[*]"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.D|Ztied1.D": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
ORR Ztied1.D, Pg/M, Ztied1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ORR--vectors--predicated---Bitwise-inclusive-OR--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
ORR Zresult.D, Pg/M, Zresult.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ORR--vectors--predicated---Bitwise-inclusive-OR--predicated--

### Operation

Source operation ID: `SveOperation_svorr_n_s8_m`

**Operation**



Return a vector in which each active element *i* contains `op1[i] | op2`. Take the inactive elements of the result from the corresponding elements of `op1`.

## svorr[_n_s64]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svorr%5B_n_s64%5D_x

### Signature (source notation)

```c
svint64_t svorr[_n_s64]_x(svbool_t pg, svint64_t op1, int64_t op2);
```

### Description

Bitwise inclusive OR

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / OR

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
  "op1": {
    "register": "Zop1.D|Ztied1.D"
  },
  "op2": {
    "register": "Zop2.D[*]|Ztied2.D[*]"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.D|Ztied1.D|Ztied2.D": "result"
  }
]
```

### Instruction mapping

When op2 is a logical immediate[1], this intrinsic can use:

```asm
ORR Ztied1.D, Ztied1.D, #op2  // [2]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ORR--immediate---Bitwise-inclusive-OR-with-immediate--unpredicated--

When result and op1 are in the same register, this intrinsic can use:

```asm
ORR Ztied1.D, Pg/M, Ztied1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ORR--vectors--predicated---Bitwise-inclusive-OR--predicated--

When result and op2 are in the same register, this intrinsic can use:

```asm
ORR Ztied2.D, Pg/M, Ztied2.D, Zop1.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ORR--vectors--predicated---Bitwise-inclusive-OR--predicated--

The general implementation is:

```asm
ORR Zresult.D, Zop1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ORR--vectors--unpredicated---Bitwise-inclusive-OR--unpredicated--

### Operation

Source operation ID: `SveOperation_svorr_n_s8_x`

**Operation**



Return a vector in which each active element *i* contains `op1[i] | op2`. The inactive elements of the result have arbitrary, undefined values.



**[1]** This is true if op2 is filled by some replicated bitmask *b* for which either all 0s in *b* are consecutive or all 1s in *b* are consecutive.



**[2]** If instead `result` is in a different register from the inputs, the compiler can add a preceding [MOVPRFX (unpredicated)](https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--) instruction

## svorr[_n_s64]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svorr%5B_n_s64%5D_z

### Signature (source notation)

```c
svint64_t svorr[_n_s64]_z(svbool_t pg, svint64_t op1, int64_t op2);
```

### Description

Bitwise inclusive OR

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / OR

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
  "op1": {
    "register": "Zop1.D"
  },
  "op2": {
    "register": "Zop2.D[*]"
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

When result is in a different register from op2, this intrinsic can use:

```asm
MOVPRFX Zresult.D, Pg/Z, Zop1.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
ORR Zresult.D, Pg/M, Zresult.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ORR--vectors--predicated---Bitwise-inclusive-OR--predicated--

When result is in a different register from op1, this intrinsic can use:

```asm
MOVPRFX Zresult.D, Pg/Z, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
ORR Zresult.D, Pg/M, Zresult.D, Zop1.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ORR--vectors--predicated---Bitwise-inclusive-OR--predicated--

### Operation

Source operation ID: `SveOperation_svorr_n_s8_z`

**Operation**



Return a vector in which each active element *i* contains `op1[i] | op2`. Set the inactive elements of the result to zero.

## svorr[_n_s8]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svorr%5B_n_s8%5D_m

### Signature (source notation)

```c
svint8_t svorr[_n_s8]_m(svbool_t pg, svint8_t op1, int8_t op2);
```

### Description

Bitwise inclusive OR

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / OR

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
  "pg": {
    "register": "Pg"
  },
  "op1": {
    "register": "Zop1.B|Ztied1.B"
  },
  "op2": {
    "register": "Zop2.B[*]"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.B|Ztied1.B": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
ORR Ztied1.B, Pg/M, Ztied1.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ORR--vectors--predicated---Bitwise-inclusive-OR--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
ORR Zresult.B, Pg/M, Zresult.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ORR--vectors--predicated---Bitwise-inclusive-OR--predicated--

### Operation

Source operation ID: `SveOperation_svorr_n_s8_m`

**Operation**



Return a vector in which each active element *i* contains `op1[i] | op2`. Take the inactive elements of the result from the corresponding elements of `op1`.

## svorr[_n_s8]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svorr%5B_n_s8%5D_x

### Signature (source notation)

```c
svint8_t svorr[_n_s8]_x(svbool_t pg, svint8_t op1, int8_t op2);
```

### Description

Bitwise inclusive OR

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / OR

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
  "pg": {
    "register": "Pg"
  },
  "op1": {
    "register": "Zop1.B|Ztied1.B"
  },
  "op2": {
    "register": "Zop2.B[*]|Ztied2.B[*]"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.B|Ztied1.B|Ztied2.B": "result"
  }
]
```

### Instruction mapping

When op2 is a logical immediate[1], this intrinsic can use:

```asm
ORR Ztied1.B, Ztied1.B, #op2  // [2]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ORR--immediate---Bitwise-inclusive-OR-with-immediate--unpredicated--

When result and op1 are in the same register, this intrinsic can use:

```asm
ORR Ztied1.B, Pg/M, Ztied1.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ORR--vectors--predicated---Bitwise-inclusive-OR--predicated--

When result and op2 are in the same register, this intrinsic can use:

```asm
ORR Ztied2.B, Pg/M, Ztied2.B, Zop1.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ORR--vectors--predicated---Bitwise-inclusive-OR--predicated--

The general implementation is:

```asm
ORR Zresult.D, Zop1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ORR--vectors--unpredicated---Bitwise-inclusive-OR--unpredicated--

### Operation

Source operation ID: `SveOperation_svorr_n_s8_x`

**Operation**



Return a vector in which each active element *i* contains `op1[i] | op2`. The inactive elements of the result have arbitrary, undefined values.



**[1]** This is true if op2 is filled by some replicated bitmask *b* for which either all 0s in *b* are consecutive or all 1s in *b* are consecutive.



**[2]** If instead `result` is in a different register from the inputs, the compiler can add a preceding [MOVPRFX (unpredicated)](https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--) instruction

## svorr[_n_s8]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svorr%5B_n_s8%5D_z

### Signature (source notation)

```c
svint8_t svorr[_n_s8]_z(svbool_t pg, svint8_t op1, int8_t op2);
```

### Description

Bitwise inclusive OR

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / OR

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
  "pg": {
    "register": "Pg"
  },
  "op1": {
    "register": "Zop1.B"
  },
  "op2": {
    "register": "Zop2.B[*]"
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

When result is in a different register from op2, this intrinsic can use:

```asm
MOVPRFX Zresult.B, Pg/Z, Zop1.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
ORR Zresult.B, Pg/M, Zresult.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ORR--vectors--predicated---Bitwise-inclusive-OR--predicated--

When result is in a different register from op1, this intrinsic can use:

```asm
MOVPRFX Zresult.B, Pg/Z, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
ORR Zresult.B, Pg/M, Zresult.B, Zop1.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ORR--vectors--predicated---Bitwise-inclusive-OR--predicated--

### Operation

Source operation ID: `SveOperation_svorr_n_s8_z`

**Operation**



Return a vector in which each active element *i* contains `op1[i] | op2`. Set the inactive elements of the result to zero.

## svorr[_n_u16]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svorr%5B_n_u16%5D_m

### Signature (source notation)

```c
svuint16_t svorr[_n_u16]_m(svbool_t pg, svuint16_t op1, uint16_t op2);
```

### Description

Bitwise inclusive OR

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / OR

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
  "op1": {
    "register": "Zop1.H|Ztied1.H"
  },
  "op2": {
    "register": "Zop2.H[*]"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.H|Ztied1.H": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
ORR Ztied1.H, Pg/M, Ztied1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ORR--vectors--predicated---Bitwise-inclusive-OR--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
ORR Zresult.H, Pg/M, Zresult.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ORR--vectors--predicated---Bitwise-inclusive-OR--predicated--

### Operation

Source operation ID: `SveOperation_svorr_n_s8_m`

**Operation**



Return a vector in which each active element *i* contains `op1[i] | op2`. Take the inactive elements of the result from the corresponding elements of `op1`.

## svorr[_n_u16]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svorr%5B_n_u16%5D_x

### Signature (source notation)

```c
svuint16_t svorr[_n_u16]_x(svbool_t pg, svuint16_t op1, uint16_t op2);
```

### Description

Bitwise inclusive OR

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / OR

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
  "op1": {
    "register": "Zop1.H|Ztied1.H"
  },
  "op2": {
    "register": "Zop2.H[*]|Ztied2.H[*]"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.H|Ztied1.H|Ztied2.H": "result"
  }
]
```

### Instruction mapping

When op2 is a logical immediate[1], this intrinsic can use:

```asm
ORR Ztied1.H, Ztied1.H, #op2  // [2]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ORR--immediate---Bitwise-inclusive-OR-with-immediate--unpredicated--

When result and op1 are in the same register, this intrinsic can use:

```asm
ORR Ztied1.H, Pg/M, Ztied1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ORR--vectors--predicated---Bitwise-inclusive-OR--predicated--

When result and op2 are in the same register, this intrinsic can use:

```asm
ORR Ztied2.H, Pg/M, Ztied2.H, Zop1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ORR--vectors--predicated---Bitwise-inclusive-OR--predicated--

The general implementation is:

```asm
ORR Zresult.D, Zop1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ORR--vectors--unpredicated---Bitwise-inclusive-OR--unpredicated--

### Operation

Source operation ID: `SveOperation_svorr_n_s8_x`

**Operation**



Return a vector in which each active element *i* contains `op1[i] | op2`. The inactive elements of the result have arbitrary, undefined values.



**[1]** This is true if op2 is filled by some replicated bitmask *b* for which either all 0s in *b* are consecutive or all 1s in *b* are consecutive.



**[2]** If instead `result` is in a different register from the inputs, the compiler can add a preceding [MOVPRFX (unpredicated)](https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--) instruction

## svorr[_n_u16]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svorr%5B_n_u16%5D_z

### Signature (source notation)

```c
svuint16_t svorr[_n_u16]_z(svbool_t pg, svuint16_t op1, uint16_t op2);
```

### Description

Bitwise inclusive OR

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / OR

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
  "op1": {
    "register": "Zop1.H"
  },
  "op2": {
    "register": "Zop2.H[*]"
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

When result is in a different register from op2, this intrinsic can use:

```asm
MOVPRFX Zresult.H, Pg/Z, Zop1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
ORR Zresult.H, Pg/M, Zresult.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ORR--vectors--predicated---Bitwise-inclusive-OR--predicated--

When result is in a different register from op1, this intrinsic can use:

```asm
MOVPRFX Zresult.H, Pg/Z, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
ORR Zresult.H, Pg/M, Zresult.H, Zop1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ORR--vectors--predicated---Bitwise-inclusive-OR--predicated--

### Operation

Source operation ID: `SveOperation_svorr_n_s8_z`

**Operation**



Return a vector in which each active element *i* contains `op1[i] | op2`. Set the inactive elements of the result to zero.

## svorr[_n_u32]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svorr%5B_n_u32%5D_m

### Signature (source notation)

```c
svuint32_t svorr[_n_u32]_m(svbool_t pg, svuint32_t op1, uint32_t op2);
```

### Description

Bitwise inclusive OR

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / OR

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
  "op1": {
    "register": "Zop1.S|Ztied1.S"
  },
  "op2": {
    "register": "Zop2.S[*]"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.S|Ztied1.S": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
ORR Ztied1.S, Pg/M, Ztied1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ORR--vectors--predicated---Bitwise-inclusive-OR--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
ORR Zresult.S, Pg/M, Zresult.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ORR--vectors--predicated---Bitwise-inclusive-OR--predicated--

### Operation

Source operation ID: `SveOperation_svorr_n_s8_m`

**Operation**



Return a vector in which each active element *i* contains `op1[i] | op2`. Take the inactive elements of the result from the corresponding elements of `op1`.

## svorr[_n_u32]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svorr%5B_n_u32%5D_x

### Signature (source notation)

```c
svuint32_t svorr[_n_u32]_x(svbool_t pg, svuint32_t op1, uint32_t op2);
```

### Description

Bitwise inclusive OR

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / OR

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
  "op1": {
    "register": "Zop1.S|Ztied1.S"
  },
  "op2": {
    "register": "Zop2.S[*]|Ztied2.S[*]"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.S|Ztied1.S|Ztied2.S": "result"
  }
]
```

### Instruction mapping

When op2 is a logical immediate[1], this intrinsic can use:

```asm
ORR Ztied1.S, Ztied1.S, #op2  // [2]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ORR--immediate---Bitwise-inclusive-OR-with-immediate--unpredicated--

When result and op1 are in the same register, this intrinsic can use:

```asm
ORR Ztied1.S, Pg/M, Ztied1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ORR--vectors--predicated---Bitwise-inclusive-OR--predicated--

When result and op2 are in the same register, this intrinsic can use:

```asm
ORR Ztied2.S, Pg/M, Ztied2.S, Zop1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ORR--vectors--predicated---Bitwise-inclusive-OR--predicated--

The general implementation is:

```asm
ORR Zresult.D, Zop1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ORR--vectors--unpredicated---Bitwise-inclusive-OR--unpredicated--

### Operation

Source operation ID: `SveOperation_svorr_n_s8_x`

**Operation**



Return a vector in which each active element *i* contains `op1[i] | op2`. The inactive elements of the result have arbitrary, undefined values.



**[1]** This is true if op2 is filled by some replicated bitmask *b* for which either all 0s in *b* are consecutive or all 1s in *b* are consecutive.



**[2]** If instead `result` is in a different register from the inputs, the compiler can add a preceding [MOVPRFX (unpredicated)](https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--) instruction

## svorr[_n_u32]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svorr%5B_n_u32%5D_z

### Signature (source notation)

```c
svuint32_t svorr[_n_u32]_z(svbool_t pg, svuint32_t op1, uint32_t op2);
```

### Description

Bitwise inclusive OR

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / OR

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
  "op1": {
    "register": "Zop1.S"
  },
  "op2": {
    "register": "Zop2.S[*]"
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

When result is in a different register from op2, this intrinsic can use:

```asm
MOVPRFX Zresult.S, Pg/Z, Zop1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
ORR Zresult.S, Pg/M, Zresult.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ORR--vectors--predicated---Bitwise-inclusive-OR--predicated--

When result is in a different register from op1, this intrinsic can use:

```asm
MOVPRFX Zresult.S, Pg/Z, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
ORR Zresult.S, Pg/M, Zresult.S, Zop1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ORR--vectors--predicated---Bitwise-inclusive-OR--predicated--

### Operation

Source operation ID: `SveOperation_svorr_n_s8_z`

**Operation**



Return a vector in which each active element *i* contains `op1[i] | op2`. Set the inactive elements of the result to zero.

## svorr[_n_u64]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svorr%5B_n_u64%5D_m

### Signature (source notation)

```c
svuint64_t svorr[_n_u64]_m(svbool_t pg, svuint64_t op1, uint64_t op2);
```

### Description

Bitwise inclusive OR

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / OR

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
  "op1": {
    "register": "Zop1.D|Ztied1.D"
  },
  "op2": {
    "register": "Zop2.D[*]"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.D|Ztied1.D": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
ORR Ztied1.D, Pg/M, Ztied1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ORR--vectors--predicated---Bitwise-inclusive-OR--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
ORR Zresult.D, Pg/M, Zresult.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ORR--vectors--predicated---Bitwise-inclusive-OR--predicated--

### Operation

Source operation ID: `SveOperation_svorr_n_s8_m`

**Operation**



Return a vector in which each active element *i* contains `op1[i] | op2`. Take the inactive elements of the result from the corresponding elements of `op1`.

## svorr[_n_u64]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svorr%5B_n_u64%5D_x

### Signature (source notation)

```c
svuint64_t svorr[_n_u64]_x(svbool_t pg, svuint64_t op1, uint64_t op2);
```

### Description

Bitwise inclusive OR

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / OR

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
  "op1": {
    "register": "Zop1.D|Ztied1.D"
  },
  "op2": {
    "register": "Zop2.D[*]|Ztied2.D[*]"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.D|Ztied1.D|Ztied2.D": "result"
  }
]
```

### Instruction mapping

When op2 is a logical immediate[1], this intrinsic can use:

```asm
ORR Ztied1.D, Ztied1.D, #op2  // [2]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ORR--immediate---Bitwise-inclusive-OR-with-immediate--unpredicated--

When result and op1 are in the same register, this intrinsic can use:

```asm
ORR Ztied1.D, Pg/M, Ztied1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ORR--vectors--predicated---Bitwise-inclusive-OR--predicated--

When result and op2 are in the same register, this intrinsic can use:

```asm
ORR Ztied2.D, Pg/M, Ztied2.D, Zop1.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ORR--vectors--predicated---Bitwise-inclusive-OR--predicated--

The general implementation is:

```asm
ORR Zresult.D, Zop1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ORR--vectors--unpredicated---Bitwise-inclusive-OR--unpredicated--

### Operation

Source operation ID: `SveOperation_svorr_n_s8_x`

**Operation**



Return a vector in which each active element *i* contains `op1[i] | op2`. The inactive elements of the result have arbitrary, undefined values.



**[1]** This is true if op2 is filled by some replicated bitmask *b* for which either all 0s in *b* are consecutive or all 1s in *b* are consecutive.



**[2]** If instead `result` is in a different register from the inputs, the compiler can add a preceding [MOVPRFX (unpredicated)](https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--) instruction

## svorr[_n_u64]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svorr%5B_n_u64%5D_z

### Signature (source notation)

```c
svuint64_t svorr[_n_u64]_z(svbool_t pg, svuint64_t op1, uint64_t op2);
```

### Description

Bitwise inclusive OR

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / OR

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
  "op1": {
    "register": "Zop1.D"
  },
  "op2": {
    "register": "Zop2.D[*]"
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

When result is in a different register from op2, this intrinsic can use:

```asm
MOVPRFX Zresult.D, Pg/Z, Zop1.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
ORR Zresult.D, Pg/M, Zresult.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ORR--vectors--predicated---Bitwise-inclusive-OR--predicated--

When result is in a different register from op1, this intrinsic can use:

```asm
MOVPRFX Zresult.D, Pg/Z, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
ORR Zresult.D, Pg/M, Zresult.D, Zop1.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ORR--vectors--predicated---Bitwise-inclusive-OR--predicated--

### Operation

Source operation ID: `SveOperation_svorr_n_s8_z`

**Operation**



Return a vector in which each active element *i* contains `op1[i] | op2`. Set the inactive elements of the result to zero.

## svorr[_n_u8]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svorr%5B_n_u8%5D_m

### Signature (source notation)

```c
svuint8_t svorr[_n_u8]_m(svbool_t pg, svuint8_t op1, uint8_t op2);
```

### Description

Bitwise inclusive OR

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / OR

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
  "pg": {
    "register": "Pg"
  },
  "op1": {
    "register": "Zop1.B|Ztied1.B"
  },
  "op2": {
    "register": "Zop2.B[*]"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.B|Ztied1.B": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
ORR Ztied1.B, Pg/M, Ztied1.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ORR--vectors--predicated---Bitwise-inclusive-OR--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
ORR Zresult.B, Pg/M, Zresult.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ORR--vectors--predicated---Bitwise-inclusive-OR--predicated--

### Operation

Source operation ID: `SveOperation_svorr_n_s8_m`

**Operation**



Return a vector in which each active element *i* contains `op1[i] | op2`. Take the inactive elements of the result from the corresponding elements of `op1`.

## svorr[_n_u8]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svorr%5B_n_u8%5D_x

### Signature (source notation)

```c
svuint8_t svorr[_n_u8]_x(svbool_t pg, svuint8_t op1, uint8_t op2);
```

### Description

Bitwise inclusive OR

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / OR

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
  "pg": {
    "register": "Pg"
  },
  "op1": {
    "register": "Zop1.B|Ztied1.B"
  },
  "op2": {
    "register": "Zop2.B[*]|Ztied2.B[*]"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.B|Ztied1.B|Ztied2.B": "result"
  }
]
```

### Instruction mapping

When op2 is a logical immediate[1], this intrinsic can use:

```asm
ORR Ztied1.B, Ztied1.B, #op2  // [2]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ORR--immediate---Bitwise-inclusive-OR-with-immediate--unpredicated--

When result and op1 are in the same register, this intrinsic can use:

```asm
ORR Ztied1.B, Pg/M, Ztied1.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ORR--vectors--predicated---Bitwise-inclusive-OR--predicated--

When result and op2 are in the same register, this intrinsic can use:

```asm
ORR Ztied2.B, Pg/M, Ztied2.B, Zop1.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ORR--vectors--predicated---Bitwise-inclusive-OR--predicated--

The general implementation is:

```asm
ORR Zresult.D, Zop1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ORR--vectors--unpredicated---Bitwise-inclusive-OR--unpredicated--

### Operation

Source operation ID: `SveOperation_svorr_n_s8_x`

**Operation**



Return a vector in which each active element *i* contains `op1[i] | op2`. The inactive elements of the result have arbitrary, undefined values.



**[1]** This is true if op2 is filled by some replicated bitmask *b* for which either all 0s in *b* are consecutive or all 1s in *b* are consecutive.



**[2]** If instead `result` is in a different register from the inputs, the compiler can add a preceding [MOVPRFX (unpredicated)](https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--) instruction

## svorr[_n_u8]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svorr%5B_n_u8%5D_z

### Signature (source notation)

```c
svuint8_t svorr[_n_u8]_z(svbool_t pg, svuint8_t op1, uint8_t op2);
```

### Description

Bitwise inclusive OR

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / OR

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
  "pg": {
    "register": "Pg"
  },
  "op1": {
    "register": "Zop1.B"
  },
  "op2": {
    "register": "Zop2.B[*]"
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

When result is in a different register from op2, this intrinsic can use:

```asm
MOVPRFX Zresult.B, Pg/Z, Zop1.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
ORR Zresult.B, Pg/M, Zresult.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ORR--vectors--predicated---Bitwise-inclusive-OR--predicated--

When result is in a different register from op1, this intrinsic can use:

```asm
MOVPRFX Zresult.B, Pg/Z, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
ORR Zresult.B, Pg/M, Zresult.B, Zop1.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ORR--vectors--predicated---Bitwise-inclusive-OR--predicated--

### Operation

Source operation ID: `SveOperation_svorr_n_s8_z`

**Operation**



Return a vector in which each active element *i* contains `op1[i] | op2`. Set the inactive elements of the result to zero.

## svorr[_s16]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svorr%5B_s16%5D_m

### Signature (source notation)

```c
svint16_t svorr[_s16]_m(svbool_t pg, svint16_t op1, svint16_t op2);
```

### Description

Bitwise inclusive OR

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / OR

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
  "op1": {
    "register": "Zop1.H|Ztied1.H"
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
    "Zresult.H|Ztied1.H": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
ORR Ztied1.H, Pg/M, Ztied1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ORR--vectors--predicated---Bitwise-inclusive-OR--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
ORR Zresult.H, Pg/M, Zresult.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ORR--vectors--predicated---Bitwise-inclusive-OR--predicated--

### Operation

Source operation ID: `SveOperation_svorr_s8_m`

**Operation**



Return a vector in which each active element *i* contains `op1[i] | op2[i]`. Take the inactive elements of the result from the corresponding elements of `op1`.

## svorr[_s16]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svorr%5B_s16%5D_x

### Signature (source notation)

```c
svint16_t svorr[_s16]_x(svbool_t pg, svint16_t op1, svint16_t op2);
```

### Description

Bitwise inclusive OR

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / OR

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
  "op1": {
    "register": "Zop1.H|Ztied1.H"
  },
  "op2": {
    "register": "Zop2.H|Ztied2.H"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.H|Ztied1.H|Ztied2.H": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic can use:

```asm
ORR Ztied1.H, Pg/M, Ztied1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ORR--vectors--predicated---Bitwise-inclusive-OR--predicated--

When result and op2 are in the same register, this intrinsic can use:

```asm
ORR Ztied2.H, Pg/M, Ztied2.H, Zop1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ORR--vectors--predicated---Bitwise-inclusive-OR--predicated--

This intrinsic compiles to:

```asm
ORR Zresult.D, Zop1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ORR--vectors--unpredicated---Bitwise-inclusive-OR--unpredicated--

### Operation

Source operation ID: `SveOperation_svorr_s8_x`

**Operation**



Return a vector in which each active element *i* contains `op1[i] | op2[i]`. The inactive elements of the result have arbitrary, undefined values.

## svorr[_s16]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svorr%5B_s16%5D_z

### Signature (source notation)

```c
svint16_t svorr[_s16]_z(svbool_t pg, svint16_t op1, svint16_t op2);
```

### Description

Bitwise inclusive OR

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / OR

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

When result is in a different register from op2, this intrinsic can use:

```asm
MOVPRFX Zresult.H, Pg/Z, Zop1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
ORR Zresult.H, Pg/M, Zresult.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ORR--vectors--predicated---Bitwise-inclusive-OR--predicated--

When result is in a different register from op1, this intrinsic can use:

```asm
MOVPRFX Zresult.H, Pg/Z, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
ORR Zresult.H, Pg/M, Zresult.H, Zop1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ORR--vectors--predicated---Bitwise-inclusive-OR--predicated--

### Operation

Source operation ID: `SveOperation_svorr_s8_z`

**Operation**



Return a vector in which each active element *i* contains `op1[i] | op2[i]`. Set the inactive elements of the result to zero.

## svorr[_s32]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svorr%5B_s32%5D_m

### Signature (source notation)

```c
svint32_t svorr[_s32]_m(svbool_t pg, svint32_t op1, svint32_t op2);
```

### Description

Bitwise inclusive OR

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / OR

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
  "op1": {
    "register": "Zop1.S|Ztied1.S"
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
    "Zresult.S|Ztied1.S": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
ORR Ztied1.S, Pg/M, Ztied1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ORR--vectors--predicated---Bitwise-inclusive-OR--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
ORR Zresult.S, Pg/M, Zresult.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ORR--vectors--predicated---Bitwise-inclusive-OR--predicated--

### Operation

Source operation ID: `SveOperation_svorr_s8_m`

**Operation**



Return a vector in which each active element *i* contains `op1[i] | op2[i]`. Take the inactive elements of the result from the corresponding elements of `op1`.

## svorr[_s32]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svorr%5B_s32%5D_x

### Signature (source notation)

```c
svint32_t svorr[_s32]_x(svbool_t pg, svint32_t op1, svint32_t op2);
```

### Description

Bitwise inclusive OR

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / OR

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
  "op1": {
    "register": "Zop1.S|Ztied1.S"
  },
  "op2": {
    "register": "Zop2.S|Ztied2.S"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.S|Ztied1.S|Ztied2.S": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic can use:

```asm
ORR Ztied1.S, Pg/M, Ztied1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ORR--vectors--predicated---Bitwise-inclusive-OR--predicated--

When result and op2 are in the same register, this intrinsic can use:

```asm
ORR Ztied2.S, Pg/M, Ztied2.S, Zop1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ORR--vectors--predicated---Bitwise-inclusive-OR--predicated--

This intrinsic compiles to:

```asm
ORR Zresult.D, Zop1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ORR--vectors--unpredicated---Bitwise-inclusive-OR--unpredicated--

### Operation

Source operation ID: `SveOperation_svorr_s8_x`

**Operation**



Return a vector in which each active element *i* contains `op1[i] | op2[i]`. The inactive elements of the result have arbitrary, undefined values.

## svorr[_s32]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svorr%5B_s32%5D_z

### Signature (source notation)

```c
svint32_t svorr[_s32]_z(svbool_t pg, svint32_t op1, svint32_t op2);
```

### Description

Bitwise inclusive OR

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / OR

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

When result is in a different register from op2, this intrinsic can use:

```asm
MOVPRFX Zresult.S, Pg/Z, Zop1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
ORR Zresult.S, Pg/M, Zresult.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ORR--vectors--predicated---Bitwise-inclusive-OR--predicated--

When result is in a different register from op1, this intrinsic can use:

```asm
MOVPRFX Zresult.S, Pg/Z, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
ORR Zresult.S, Pg/M, Zresult.S, Zop1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ORR--vectors--predicated---Bitwise-inclusive-OR--predicated--

### Operation

Source operation ID: `SveOperation_svorr_s8_z`

**Operation**



Return a vector in which each active element *i* contains `op1[i] | op2[i]`. Set the inactive elements of the result to zero.

## svorr[_s64]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svorr%5B_s64%5D_m

### Signature (source notation)

```c
svint64_t svorr[_s64]_m(svbool_t pg, svint64_t op1, svint64_t op2);
```

### Description

Bitwise inclusive OR

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / OR

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
  "op1": {
    "register": "Zop1.D|Ztied1.D"
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
    "Zresult.D|Ztied1.D": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
ORR Ztied1.D, Pg/M, Ztied1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ORR--vectors--predicated---Bitwise-inclusive-OR--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
ORR Zresult.D, Pg/M, Zresult.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ORR--vectors--predicated---Bitwise-inclusive-OR--predicated--

### Operation

Source operation ID: `SveOperation_svorr_s8_m`

**Operation**



Return a vector in which each active element *i* contains `op1[i] | op2[i]`. Take the inactive elements of the result from the corresponding elements of `op1`.

## svorr[_s64]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svorr%5B_s64%5D_x

### Signature (source notation)

```c
svint64_t svorr[_s64]_x(svbool_t pg, svint64_t op1, svint64_t op2);
```

### Description

Bitwise inclusive OR

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / OR

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
  "op1": {
    "register": "Zop1.D|Ztied1.D"
  },
  "op2": {
    "register": "Zop2.D|Ztied2.D"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.D|Ztied1.D|Ztied2.D": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic can use:

```asm
ORR Ztied1.D, Pg/M, Ztied1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ORR--vectors--predicated---Bitwise-inclusive-OR--predicated--

When result and op2 are in the same register, this intrinsic can use:

```asm
ORR Ztied2.D, Pg/M, Ztied2.D, Zop1.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ORR--vectors--predicated---Bitwise-inclusive-OR--predicated--

This intrinsic compiles to:

```asm
ORR Zresult.D, Zop1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ORR--vectors--unpredicated---Bitwise-inclusive-OR--unpredicated--

### Operation

Source operation ID: `SveOperation_svorr_s8_x`

**Operation**



Return a vector in which each active element *i* contains `op1[i] | op2[i]`. The inactive elements of the result have arbitrary, undefined values.

## svorr[_s64]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svorr%5B_s64%5D_z

### Signature (source notation)

```c
svint64_t svorr[_s64]_z(svbool_t pg, svint64_t op1, svint64_t op2);
```

### Description

Bitwise inclusive OR

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / OR

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

When result is in a different register from op2, this intrinsic can use:

```asm
MOVPRFX Zresult.D, Pg/Z, Zop1.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
ORR Zresult.D, Pg/M, Zresult.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ORR--vectors--predicated---Bitwise-inclusive-OR--predicated--

When result is in a different register from op1, this intrinsic can use:

```asm
MOVPRFX Zresult.D, Pg/Z, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
ORR Zresult.D, Pg/M, Zresult.D, Zop1.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ORR--vectors--predicated---Bitwise-inclusive-OR--predicated--

### Operation

Source operation ID: `SveOperation_svorr_s8_z`

**Operation**



Return a vector in which each active element *i* contains `op1[i] | op2[i]`. Set the inactive elements of the result to zero.

## svorr[_s8]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svorr%5B_s8%5D_m

### Signature (source notation)

```c
svint8_t svorr[_s8]_m(svbool_t pg, svint8_t op1, svint8_t op2);
```

### Description

Bitwise inclusive OR

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / OR

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
  "pg": {
    "register": "Pg"
  },
  "op1": {
    "register": "Zop1.B|Ztied1.B"
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
    "Zresult.B|Ztied1.B": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
ORR Ztied1.B, Pg/M, Ztied1.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ORR--vectors--predicated---Bitwise-inclusive-OR--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
ORR Zresult.B, Pg/M, Zresult.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ORR--vectors--predicated---Bitwise-inclusive-OR--predicated--

### Operation

Source operation ID: `SveOperation_svorr_s8_m`

**Operation**



Return a vector in which each active element *i* contains `op1[i] | op2[i]`. Take the inactive elements of the result from the corresponding elements of `op1`.

## svorr[_s8]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svorr%5B_s8%5D_x

### Signature (source notation)

```c
svint8_t svorr[_s8]_x(svbool_t pg, svint8_t op1, svint8_t op2);
```

### Description

Bitwise inclusive OR

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / OR

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
  "pg": {
    "register": "Pg"
  },
  "op1": {
    "register": "Zop1.B|Ztied1.B"
  },
  "op2": {
    "register": "Zop2.B|Ztied2.B"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.B|Ztied1.B|Ztied2.B": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic can use:

```asm
ORR Ztied1.B, Pg/M, Ztied1.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ORR--vectors--predicated---Bitwise-inclusive-OR--predicated--

When result and op2 are in the same register, this intrinsic can use:

```asm
ORR Ztied2.B, Pg/M, Ztied2.B, Zop1.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ORR--vectors--predicated---Bitwise-inclusive-OR--predicated--

This intrinsic compiles to:

```asm
ORR Zresult.D, Zop1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ORR--vectors--unpredicated---Bitwise-inclusive-OR--unpredicated--

### Operation

Source operation ID: `SveOperation_svorr_s8_x`

**Operation**



Return a vector in which each active element *i* contains `op1[i] | op2[i]`. The inactive elements of the result have arbitrary, undefined values.

## svorr[_s8]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svorr%5B_s8%5D_z

### Signature (source notation)

```c
svint8_t svorr[_s8]_z(svbool_t pg, svint8_t op1, svint8_t op2);
```

### Description

Bitwise inclusive OR

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / OR

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
  "pg": {
    "register": "Pg"
  },
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

When result is in a different register from op2, this intrinsic can use:

```asm
MOVPRFX Zresult.B, Pg/Z, Zop1.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
ORR Zresult.B, Pg/M, Zresult.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ORR--vectors--predicated---Bitwise-inclusive-OR--predicated--

When result is in a different register from op1, this intrinsic can use:

```asm
MOVPRFX Zresult.B, Pg/Z, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
ORR Zresult.B, Pg/M, Zresult.B, Zop1.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ORR--vectors--predicated---Bitwise-inclusive-OR--predicated--

### Operation

Source operation ID: `SveOperation_svorr_s8_z`

**Operation**



Return a vector in which each active element *i* contains `op1[i] | op2[i]`. Set the inactive elements of the result to zero.

## svorr[_u16]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svorr%5B_u16%5D_m

### Signature (source notation)

```c
svuint16_t svorr[_u16]_m(svbool_t pg, svuint16_t op1, svuint16_t op2);
```

### Description

Bitwise inclusive OR

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / OR

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
  "op1": {
    "register": "Zop1.H|Ztied1.H"
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
    "Zresult.H|Ztied1.H": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
ORR Ztied1.H, Pg/M, Ztied1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ORR--vectors--predicated---Bitwise-inclusive-OR--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
ORR Zresult.H, Pg/M, Zresult.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ORR--vectors--predicated---Bitwise-inclusive-OR--predicated--

### Operation

Source operation ID: `SveOperation_svorr_s8_m`

**Operation**



Return a vector in which each active element *i* contains `op1[i] | op2[i]`. Take the inactive elements of the result from the corresponding elements of `op1`.

## svorr[_u16]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svorr%5B_u16%5D_x

### Signature (source notation)

```c
svuint16_t svorr[_u16]_x(svbool_t pg, svuint16_t op1, svuint16_t op2);
```

### Description

Bitwise inclusive OR

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / OR

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
  "op1": {
    "register": "Zop1.H|Ztied1.H"
  },
  "op2": {
    "register": "Zop2.H|Ztied2.H"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.H|Ztied1.H|Ztied2.H": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic can use:

```asm
ORR Ztied1.H, Pg/M, Ztied1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ORR--vectors--predicated---Bitwise-inclusive-OR--predicated--

When result and op2 are in the same register, this intrinsic can use:

```asm
ORR Ztied2.H, Pg/M, Ztied2.H, Zop1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ORR--vectors--predicated---Bitwise-inclusive-OR--predicated--

This intrinsic compiles to:

```asm
ORR Zresult.D, Zop1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ORR--vectors--unpredicated---Bitwise-inclusive-OR--unpredicated--

### Operation

Source operation ID: `SveOperation_svorr_s8_x`

**Operation**



Return a vector in which each active element *i* contains `op1[i] | op2[i]`. The inactive elements of the result have arbitrary, undefined values.

## svorr[_u16]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svorr%5B_u16%5D_z

### Signature (source notation)

```c
svuint16_t svorr[_u16]_z(svbool_t pg, svuint16_t op1, svuint16_t op2);
```

### Description

Bitwise inclusive OR

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / OR

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

When result is in a different register from op2, this intrinsic can use:

```asm
MOVPRFX Zresult.H, Pg/Z, Zop1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
ORR Zresult.H, Pg/M, Zresult.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ORR--vectors--predicated---Bitwise-inclusive-OR--predicated--

When result is in a different register from op1, this intrinsic can use:

```asm
MOVPRFX Zresult.H, Pg/Z, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
ORR Zresult.H, Pg/M, Zresult.H, Zop1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ORR--vectors--predicated---Bitwise-inclusive-OR--predicated--

### Operation

Source operation ID: `SveOperation_svorr_s8_z`

**Operation**



Return a vector in which each active element *i* contains `op1[i] | op2[i]`. Set the inactive elements of the result to zero.

## svorr[_u32]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svorr%5B_u32%5D_m

### Signature (source notation)

```c
svuint32_t svorr[_u32]_m(svbool_t pg, svuint32_t op1, svuint32_t op2);
```

### Description

Bitwise inclusive OR

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / OR

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
  "op1": {
    "register": "Zop1.S|Ztied1.S"
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
    "Zresult.S|Ztied1.S": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
ORR Ztied1.S, Pg/M, Ztied1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ORR--vectors--predicated---Bitwise-inclusive-OR--predicated--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
ORR Zresult.S, Pg/M, Zresult.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ORR--vectors--predicated---Bitwise-inclusive-OR--predicated--

### Operation

Source operation ID: `SveOperation_svorr_s8_m`

**Operation**



Return a vector in which each active element *i* contains `op1[i] | op2[i]`. Take the inactive elements of the result from the corresponding elements of `op1`.

## svorr[_u32]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svorr%5B_u32%5D_x

### Signature (source notation)

```c
svuint32_t svorr[_u32]_x(svbool_t pg, svuint32_t op1, svuint32_t op2);
```

### Description

Bitwise inclusive OR

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Logical / OR

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
  "op1": {
    "register": "Zop1.S|Ztied1.S"
  },
  "op2": {
    "register": "Zop2.S|Ztied2.S"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.S|Ztied1.S|Ztied2.S": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic can use:

```asm
ORR Ztied1.S, Pg/M, Ztied1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ORR--vectors--predicated---Bitwise-inclusive-OR--predicated--

When result and op2 are in the same register, this intrinsic can use:

```asm
ORR Ztied2.S, Pg/M, Ztied2.S, Zop1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ORR--vectors--predicated---Bitwise-inclusive-OR--predicated--

This intrinsic compiles to:

```asm
ORR Zresult.D, Zop1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/ORR--vectors--unpredicated---Bitwise-inclusive-OR--unpredicated--

### Operation

Source operation ID: `SveOperation_svorr_s8_x`

**Operation**



Return a vector in which each active element *i* contains `op1[i] | op2[i]`. The inactive elements of the result have arbitrary, undefined values.

