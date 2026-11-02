# SME / Vector arithmetic / Polynomial / Polynomial multiply — Part 1

## svpmul[_n_u8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svpmul%5B_n_u8%5D

### Signature (source notation)

```c
svuint8_t svpmul[_n_u8](svuint8_t op1, uint8_t op2);
```

### Description

Polynomial multiply

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Polynomial / Polynomial multiply

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

This intrinsic compiles to the following instruction:

```asm
PMUL Zresult.B, Zop1.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/PMUL--Polynomial-multiply--unpredicated--

### Operation

Source operation ID: `SveOperation_svpmul_n_u8`

**Operation**



For each element *i*, treat `op1[i]` and `op2` as polynomials over GF(2) and compute their product.  Return the low half of the product in element *i* of the result.

## svpmul[_u8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svpmul%5B_u8%5D

### Signature (source notation)

```c
svuint8_t svpmul[_u8](svuint8_t op1, svuint8_t op2);
```

### Description

Polynomial multiply

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Polynomial / Polynomial multiply

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

This intrinsic compiles to the following instruction:

```asm
PMUL Zresult.B, Zop1.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/PMUL--Polynomial-multiply--unpredicated--

### Operation

Source operation ID: `SveOperation_svpmul_u8`

**Operation**



For each element *i*, treat `op1[i]` and `op2[i]` as polynomials over GF(2) and compute their product.  Return the low half of the product in element *i* of the result.

## svpmullb[_n_u16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svpmullb%5B_n_u16%5D

### Signature (source notation)

```c
svuint16_t svpmullb[_n_u16](svuint8_t op1, uint8_t op2);
```

### Description

Polynomial multiply long (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Polynomial / Polynomial multiply

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
    "Zresult.H": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
PMULLB Zresult.H, Zop1.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/PMULLB--Polynomial-multiply-long--bottom--

### Operation

Source operation ID: `SveOperation_svpmullb_n_u16`

**Operation**



For each element *i*, treat `op1[i * 2]` and `op2` as polynomials over GF(2) and compute their product.  Return the double-width product in element *i* of the result.

## svpmullb[_n_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svpmullb%5B_n_u64%5D

### Signature (source notation)

```c
svuint64_t svpmullb[_n_u64](svuint32_t op1, uint32_t op2);
```

### Description

Polynomial multiply long (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Polynomial / Polynomial multiply

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
    "Zresult.D": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
PMULLB Zresult.D, Zop1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/PMULLB--Polynomial-multiply-long--bottom--

### Operation

Source operation ID: `SveOperation_svpmullb_n_u16`

**Operation**



For each element *i*, treat `op1[i * 2]` and `op2` as polynomials over GF(2) and compute their product.  Return the double-width product in element *i* of the result.

## svpmullb[_u16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svpmullb%5B_u16%5D

### Signature (source notation)

```c
svuint16_t svpmullb[_u16](svuint8_t op1, svuint8_t op2);
```

### Description

Polynomial multiply long (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Polynomial / Polynomial multiply

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
    "Zresult.H": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
PMULLB Zresult.H, Zop1.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/PMULLB--Polynomial-multiply-long--bottom--

### Operation

Source operation ID: `SveOperation_svpmullb_u16`

**Operation**



For each element *i*, treat `op1[i * 2]` and `op2[i * 2]` as polynomials over GF(2) and compute their product.  Return the double-width product in element *i* of the result.

## svpmullb[_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svpmullb%5B_u64%5D

### Signature (source notation)

```c
svuint64_t svpmullb[_u64](svuint32_t op1, svuint32_t op2);
```

### Description

Polynomial multiply long (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Polynomial / Polynomial multiply

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
    "Zresult.D": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
PMULLB Zresult.D, Zop1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/PMULLB--Polynomial-multiply-long--bottom--

### Operation

Source operation ID: `SveOperation_svpmullb_u16`

**Operation**



For each element *i*, treat `op1[i * 2]` and `op2[i * 2]` as polynomials over GF(2) and compute their product.  Return the double-width product in element *i* of the result.

## svpmullb_pair[_n_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svpmullb_pair%5B_n_u32%5D

### Signature (source notation)

```c
svuint32_t svpmullb_pair[_n_u32](svuint32_t op1, uint32_t op2);
```

### Description

Polynomial multiply long (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Polynomial / Polynomial multiply

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
    "Zresult.D": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
PMULLB Zresult.D, Zop1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/PMULLB--Polynomial-multiply-long--bottom--

### Operation

Source operation ID: `SveOperation_svpmullb_pair_n_u8`

**Operation**



For each even-indexed (“bottom”) element *i*, treat `op1[i]` and `op2` as polynomials over GF(2) and compute their product.  Return a vector in which element *i* contains the low half of the result and in which element *i* + 1 contains the high half of the result.

## svpmullb_pair[_n_u8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svpmullb_pair%5B_n_u8%5D

### Signature (source notation)

```c
svuint8_t svpmullb_pair[_n_u8](svuint8_t op1, uint8_t op2);
```

### Description

Polynomial multiply long (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Polynomial / Polynomial multiply

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
    "Zresult.H": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
PMULLB Zresult.H, Zop1.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/PMULLB--Polynomial-multiply-long--bottom--

### Operation

Source operation ID: `SveOperation_svpmullb_pair_n_u8`

**Operation**



For each even-indexed (“bottom”) element *i*, treat `op1[i]` and `op2` as polynomials over GF(2) and compute their product.  Return a vector in which element *i* contains the low half of the result and in which element *i* + 1 contains the high half of the result.

## svpmullb_pair[_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svpmullb_pair%5B_u32%5D

### Signature (source notation)

```c
svuint32_t svpmullb_pair[_u32](svuint32_t op1, svuint32_t op2);
```

### Description

Polynomial multiply long (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Polynomial / Polynomial multiply

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
    "Zresult.D": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
PMULLB Zresult.D, Zop1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/PMULLB--Polynomial-multiply-long--bottom--

### Operation

Source operation ID: `SveOperation_svpmullb_pair_u8`

**Operation**



For each even-indexed (“bottom”) element *i*, treat `op1[i]` and `op2[i]` as polynomials over GF(2) and compute their product.  Return a vector in which element *i* contains the low half of the result and in which element *i* + 1 contains the high half of the result.

## svpmullb_pair[_u8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svpmullb_pair%5B_u8%5D

### Signature (source notation)

```c
svuint8_t svpmullb_pair[_u8](svuint8_t op1, svuint8_t op2);
```

### Description

Polynomial multiply long (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Polynomial / Polynomial multiply

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
    "Zresult.H": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
PMULLB Zresult.H, Zop1.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/PMULLB--Polynomial-multiply-long--bottom--

### Operation

Source operation ID: `SveOperation_svpmullb_pair_u8`

**Operation**



For each even-indexed (“bottom”) element *i*, treat `op1[i]` and `op2[i]` as polynomials over GF(2) and compute their product.  Return a vector in which element *i* contains the low half of the result and in which element *i* + 1 contains the high half of the result.

## svpmullt[_n_u16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svpmullt%5B_n_u16%5D

### Signature (source notation)

```c
svuint16_t svpmullt[_n_u16](svuint8_t op1, uint8_t op2);
```

### Description

Polynomial multiply long (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Polynomial / Polynomial multiply

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
    "Zresult.H": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
PMULLT Zresult.H, Zop1.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/PMULLT--Polynomial-multiply-long--top--

### Operation

Source operation ID: `SveOperation_svpmullt_n_u16`

**Operation**



For each element *i*, treat `op1[i * 2 + 1]` and `op2` as polynomials over GF(2) and compute their product.  Return the double-width product in element *i* of the result.

## svpmullt[_n_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svpmullt%5B_n_u64%5D

### Signature (source notation)

```c
svuint64_t svpmullt[_n_u64](svuint32_t op1, uint32_t op2);
```

### Description

Polynomial multiply long (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Polynomial / Polynomial multiply

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
    "Zresult.D": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
PMULLT Zresult.D, Zop1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/PMULLT--Polynomial-multiply-long--top--

### Operation

Source operation ID: `SveOperation_svpmullt_n_u16`

**Operation**



For each element *i*, treat `op1[i * 2 + 1]` and `op2` as polynomials over GF(2) and compute their product.  Return the double-width product in element *i* of the result.

## svpmullt[_u16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svpmullt%5B_u16%5D

### Signature (source notation)

```c
svuint16_t svpmullt[_u16](svuint8_t op1, svuint8_t op2);
```

### Description

Polynomial multiply long (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Polynomial / Polynomial multiply

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
    "Zresult.H": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
PMULLT Zresult.H, Zop1.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/PMULLT--Polynomial-multiply-long--top--

### Operation

Source operation ID: `SveOperation_svpmullt_u16`

**Operation**



For each element *i*, treat `op1[i * 2 + 1]` and `op2[i * 2 + 1]` as polynomials over GF(2) and compute their product.  Return the double-width product in element *i* of the result.

## svpmullt[_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svpmullt%5B_u64%5D

### Signature (source notation)

```c
svuint64_t svpmullt[_u64](svuint32_t op1, svuint32_t op2);
```

### Description

Polynomial multiply long (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Polynomial / Polynomial multiply

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
    "Zresult.D": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
PMULLT Zresult.D, Zop1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/PMULLT--Polynomial-multiply-long--top--

### Operation

Source operation ID: `SveOperation_svpmullt_u16`

**Operation**



For each element *i*, treat `op1[i * 2 + 1]` and `op2[i * 2 + 1]` as polynomials over GF(2) and compute their product.  Return the double-width product in element *i* of the result.

## svpmullt_pair[_n_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svpmullt_pair%5B_n_u32%5D

### Signature (source notation)

```c
svuint32_t svpmullt_pair[_n_u32](svuint32_t op1, uint32_t op2);
```

### Description

Polynomial multiply long (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Polynomial / Polynomial multiply

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
    "Zresult.D": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
PMULLT Zresult.D, Zop1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/PMULLT--Polynomial-multiply-long--top--

### Operation

Source operation ID: `SveOperation_svpmullt_pair_n_u8`

**Operation**



For each odd-indexed (“top”) element *i*, treat `op1[i]` and `op2` as polynomials over GF(2) and compute their product.  Return a vector in which element *i* - 1 contains the low half of the result and in which element *i* contains the high half of the result.

## svpmullt_pair[_n_u8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svpmullt_pair%5B_n_u8%5D

### Signature (source notation)

```c
svuint8_t svpmullt_pair[_n_u8](svuint8_t op1, uint8_t op2);
```

### Description

Polynomial multiply long (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Polynomial / Polynomial multiply

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
    "Zresult.H": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
PMULLT Zresult.H, Zop1.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/PMULLT--Polynomial-multiply-long--top--

### Operation

Source operation ID: `SveOperation_svpmullt_pair_n_u8`

**Operation**



For each odd-indexed (“top”) element *i*, treat `op1[i]` and `op2` as polynomials over GF(2) and compute their product.  Return a vector in which element *i* - 1 contains the low half of the result and in which element *i* contains the high half of the result.

## svpmullt_pair[_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svpmullt_pair%5B_u32%5D

### Signature (source notation)

```c
svuint32_t svpmullt_pair[_u32](svuint32_t op1, svuint32_t op2);
```

### Description

Polynomial multiply long (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Polynomial / Polynomial multiply

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
    "Zresult.D": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
PMULLT Zresult.D, Zop1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/PMULLT--Polynomial-multiply-long--top--

### Operation

Source operation ID: `SveOperation_svpmullt_pair_u8`

**Operation**



For each odd-indexed (“top”) element *i*, treat `op1[i]` and `op2[i]` as polynomials over GF(2) and compute their product.  Return a vector in which element *i* - 1 contains the low half of the result and in which element *i* contains the high half of the result.

## svpmullt_pair[_u8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svpmullt_pair%5B_u8%5D

### Signature (source notation)

```c
svuint8_t svpmullt_pair[_u8](svuint8_t op1, svuint8_t op2);
```

### Description

Polynomial multiply long (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Polynomial / Polynomial multiply

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
    "Zresult.H": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
PMULLT Zresult.H, Zop1.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/PMULLT--Polynomial-multiply-long--top--

### Operation

Source operation ID: `SveOperation_svpmullt_pair_u8`

**Operation**



For each odd-indexed (“top”) element *i*, treat `op1[i]` and `op2[i]` as polynomials over GF(2) and compute their product.  Return a vector in which element *i* - 1 contains the low half of the result and in which element *i* contains the high half of the result.

