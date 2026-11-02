# SME / Vector arithmetic / Across vector arithmetic / Minimum across vector — Part 1

## svminqv[_f16]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svminqv%5B_f16%5D

### Signature (source notation)

```c
float16x8_t svminqv[_f16](svbool_t pg, svfloat16_t zn);
```

### Description

Floating-point minimum recursive reduction of quadword vector segments

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Across vector arithmetic / Minimum across vector

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
  "return_base_type": "float16x8_t",
  "element_bit_size": "16",
  "value": "float16x8_t"
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
FMINQV Vreg1.8H, Preg1, Zreg1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/FMINQV--Floating-point-minimum-recursive-reduction-of-quadword-vector-segments-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svminqv[_f32]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svminqv%5B_f32%5D

### Signature (source notation)

```c
float32x4_t svminqv[_f32](svbool_t pg, svfloat32_t zn);
```

### Description

Floating-point minimum recursive reduction of quadword vector segments

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Across vector arithmetic / Minimum across vector

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
  "return_base_type": "float32x4_t",
  "element_bit_size": "32",
  "value": "float32x4_t"
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
FMINQV Vreg1.4S, Preg1, Zreg1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/FMINQV--Floating-point-minimum-recursive-reduction-of-quadword-vector-segments-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svminqv[_f64]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svminqv%5B_f64%5D

### Signature (source notation)

```c
float64x2_t svminqv[_f64](svbool_t pg, svfloat64_t zn);
```

### Description

Floating-point minimum recursive reduction of quadword vector segments

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Across vector arithmetic / Minimum across vector

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
  "return_base_type": "float64x2_t",
  "element_bit_size": "64",
  "value": "float64x2_t"
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
FMINQV Vreg1.2D, Preg1, Zreg1.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/FMINQV--Floating-point-minimum-recursive-reduction-of-quadword-vector-segments-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svminqv[_s16]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svminqv%5B_s16%5D

### Signature (source notation)

```c
int16x8_t svminqv[_s16](svbool_t pg, svint16_t zn);
```

### Description

Signed minimum reduction of quadword vector segments

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Across vector arithmetic / Minimum across vector

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
SMINQV Vreg1.8H, Preg1, Zreg1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/SMINQV--Signed-minimum-reduction-of-quadword-vector-segments-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svminqv[_s32]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svminqv%5B_s32%5D

### Signature (source notation)

```c
int32x4_t svminqv[_s32](svbool_t pg, svint32_t zn);
```

### Description

Signed minimum reduction of quadword vector segments

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Across vector arithmetic / Minimum across vector

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
SMINQV Vreg1.4S, Preg1, Zreg1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/SMINQV--Signed-minimum-reduction-of-quadword-vector-segments-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svminqv[_s64]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svminqv%5B_s64%5D

### Signature (source notation)

```c
int64x2_t svminqv[_s64](svbool_t pg, svint64_t zn);
```

### Description

Signed minimum reduction of quadword vector segments

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Across vector arithmetic / Minimum across vector

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
SMINQV Vreg1.2D, Preg1, Zreg1.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/SMINQV--Signed-minimum-reduction-of-quadword-vector-segments-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svminqv[_s8]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svminqv%5B_s8%5D

### Signature (source notation)

```c
int8x16_t svminqv[_s8](svbool_t pg, svint8_t zn);
```

### Description

Signed minimum reduction of quadword vector segments

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Across vector arithmetic / Minimum across vector

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
SMINQV Vreg1.16B, Preg1, Zreg1.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/SMINQV--Signed-minimum-reduction-of-quadword-vector-segments-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svminqv[_u16]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svminqv%5B_u16%5D

### Signature (source notation)

```c
uint16x8_t svminqv[_u16](svbool_t pg, svuint16_t zn);
```

### Description

Unsigned minimum reduction of quadword vector segments

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Across vector arithmetic / Minimum across vector

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
UMINQV Vreg1.8H, Preg1, Zreg1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/UMINQV--Unsigned-minimum-reduction-of-quadword-vector-segments-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svminqv[_u32]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svminqv%5B_u32%5D

### Signature (source notation)

```c
uint32x4_t svminqv[_u32](svbool_t pg, svuint32_t zn);
```

### Description

Unsigned minimum reduction of quadword vector segments

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Across vector arithmetic / Minimum across vector

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
UMINQV Vreg1.4S, Preg1, Zreg1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/UMINQV--Unsigned-minimum-reduction-of-quadword-vector-segments-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svminqv[_u64]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svminqv%5B_u64%5D

### Signature (source notation)

```c
uint64x2_t svminqv[_u64](svbool_t pg, svuint64_t zn);
```

### Description

Unsigned minimum reduction of quadword vector segments

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Across vector arithmetic / Minimum across vector

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
UMINQV Vreg1.2D, Preg1, Zreg1.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/UMINQV--Unsigned-minimum-reduction-of-quadword-vector-segments-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svminqv[_u8]

ISA classification: SME + FEAT_SVE2p1 OR SME2.1

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svminqv%5B_u8%5D

### Signature (source notation)

```c
uint8x16_t svminqv[_u8](svbool_t pg, svuint8_t zn);
```

### Description

Unsigned minimum reduction of quadword vector segments

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Across vector arithmetic / Minimum across vector

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
UMINQV Vreg1.16B, Preg1, Zreg1.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/UMINQV--Unsigned-minimum-reduction-of-quadword-vector-segments-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svminv[_f16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svminv%5B_f16%5D

### Signature (source notation)

```c
float16_t svminv[_f16](svbool_t pg, svfloat16_t op);
```

### Description

Minimum reduction to scalar

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Across vector arithmetic / Minimum across vector

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
  "value": "float16_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Pg"
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
    "Hresult": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
FMINV Hresult, Pg, Zop.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMINV--Floating-point-minimum-recursive-reduction-to-scalar-

### Operation

Source operation ID: `SveOperation_svminv_f16`

**Operation**



Return:




- ∞ if no elements are active;
- a NaN if any active element of `op` is a NaN; or
- the minimum active element of `op` otherwise.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.

## svminv[_f32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svminv%5B_f32%5D

### Signature (source notation)

```c
float32_t svminv[_f32](svbool_t pg, svfloat32_t op);
```

### Description

Minimum reduction to scalar

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Across vector arithmetic / Minimum across vector

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
  "value": "float32_t"
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
    "Sresult": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
FMINV Sresult, Pg, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMINV--Floating-point-minimum-recursive-reduction-to-scalar-

### Operation

Source operation ID: `SveOperation_svminv_f16`

**Operation**



Return:




- ∞ if no elements are active;
- a NaN if any active element of `op` is a NaN; or
- the minimum active element of `op` otherwise.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.

## svminv[_f64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svminv%5B_f64%5D

### Signature (source notation)

```c
float64_t svminv[_f64](svbool_t pg, svfloat64_t op);
```

### Description

Minimum reduction to scalar

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Across vector arithmetic / Minimum across vector

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
  "value": "float64_t"
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
    "Dresult": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
FMINV Dresult, Pg, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMINV--Floating-point-minimum-recursive-reduction-to-scalar-

### Operation

Source operation ID: `SveOperation_svminv_f16`

**Operation**



Return:




- ∞ if no elements are active;
- a NaN if any active element of `op` is a NaN; or
- the minimum active element of `op` otherwise.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not.

## svminv[_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svminv%5B_s16%5D

### Signature (source notation)

```c
int16_t svminv[_s16](svbool_t pg, svint16_t op);
```

### Description

Minimum reduction to scalar

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Across vector arithmetic / Minimum across vector

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
  "value": "int16_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Pg"
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
    "Hresult": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
SMINV Hresult, Pg, Zop.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SMINV--Signed-minimum-reduction-to-scalar-

### Operation

Source operation ID: `SveOperation_svminv_s8`

**Operation**



Return the minimum active element of `op`, or the maximum representable value if no elements are active.

## svminv[_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svminv%5B_s32%5D

### Signature (source notation)

```c
int32_t svminv[_s32](svbool_t pg, svint32_t op);
```

### Description

Minimum reduction to scalar

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Across vector arithmetic / Minimum across vector

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
  "value": "int32_t"
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
    "Sresult": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
SMINV Sresult, Pg, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SMINV--Signed-minimum-reduction-to-scalar-

### Operation

Source operation ID: `SveOperation_svminv_s8`

**Operation**



Return the minimum active element of `op`, or the maximum representable value if no elements are active.

## svminv[_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svminv%5B_s64%5D

### Signature (source notation)

```c
int64_t svminv[_s64](svbool_t pg, svint64_t op);
```

### Description

Minimum reduction to scalar

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Across vector arithmetic / Minimum across vector

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
  "value": "int64_t"
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
    "Dresult": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
SMINV Dresult, Pg, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SMINV--Signed-minimum-reduction-to-scalar-

### Operation

Source operation ID: `SveOperation_svminv_s8`

**Operation**



Return the minimum active element of `op`, or the maximum representable value if no elements are active.

## svminv[_s8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svminv%5B_s8%5D

### Signature (source notation)

```c
int8_t svminv[_s8](svbool_t pg, svint8_t op);
```

### Description

Minimum reduction to scalar

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Across vector arithmetic / Minimum across vector

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
  "value": "int8_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Pg"
  },
  "op": {
    "register": "Zop.B"
  }
}
```

### Result mapping

```json
[
  {
    "Bresult": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
SMINV Bresult, Pg, Zop.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SMINV--Signed-minimum-reduction-to-scalar-

### Operation

Source operation ID: `SveOperation_svminv_s8`

**Operation**



Return the minimum active element of `op`, or the maximum representable value if no elements are active.

## svminv[_u16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svminv%5B_u16%5D

### Signature (source notation)

```c
uint16_t svminv[_u16](svbool_t pg, svuint16_t op);
```

### Description

Minimum reduction to scalar

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Across vector arithmetic / Minimum across vector

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
  "value": "uint16_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Pg"
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
    "Hresult": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
UMINV Hresult, Pg, Zop.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UMINV--Unsigned-minimum-reduction-to-scalar-

### Operation

Source operation ID: `SveOperation_svminv_s8`

**Operation**



Return the minimum active element of `op`, or the maximum representable value if no elements are active.

## svminv[_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svminv%5B_u32%5D

### Signature (source notation)

```c
uint32_t svminv[_u32](svbool_t pg, svuint32_t op);
```

### Description

Minimum reduction to scalar

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Across vector arithmetic / Minimum across vector

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
  "value": "uint32_t"
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
    "Sresult": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
UMINV Sresult, Pg, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UMINV--Unsigned-minimum-reduction-to-scalar-

### Operation

Source operation ID: `SveOperation_svminv_s8`

**Operation**



Return the minimum active element of `op`, or the maximum representable value if no elements are active.

## svminv[_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svminv%5B_u64%5D

### Signature (source notation)

```c
uint64_t svminv[_u64](svbool_t pg, svuint64_t op);
```

### Description

Minimum reduction to scalar

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Across vector arithmetic / Minimum across vector

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
  "value": "uint64_t"
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
    "Dresult": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
UMINV Dresult, Pg, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UMINV--Unsigned-minimum-reduction-to-scalar-

### Operation

Source operation ID: `SveOperation_svminv_s8`

**Operation**



Return the minimum active element of `op`, or the maximum representable value if no elements are active.

## svminv[_u8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svminv%5B_u8%5D

### Signature (source notation)

```c
uint8_t svminv[_u8](svbool_t pg, svuint8_t op);
```

### Description

Minimum reduction to scalar

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Across vector arithmetic / Minimum across vector

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
  "value": "uint8_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Pg"
  },
  "op": {
    "register": "Zop.B"
  }
}
```

### Result mapping

```json
[
  {
    "Bresult": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
UMINV Bresult, Pg, Zop.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UMINV--Unsigned-minimum-reduction-to-scalar-

### Operation

Source operation ID: `SveOperation_svminv_s8`

**Operation**



Return the minimum active element of `op`, or the maximum representable value if no elements are active.

