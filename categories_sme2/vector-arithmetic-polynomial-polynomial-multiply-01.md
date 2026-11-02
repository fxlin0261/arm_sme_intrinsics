# SME2 / Vector arithmetic / Polynomial / Polynomial multiply — Part 1

## svpmlal_pair[_n_u64_x2]

ISA classification: SME2 + FEAT_SVE_AES2, FEAT_SSVE_AES

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svpmlal_pair%5B_n_u64_x2%5D

### Signature (source notation)

```c
svuint64x2_t svpmlal_pair[_n_u64_x2](svuint64x2_t zda, svuint64_t zn, uint64_t zm);
```

### Description

Multi-vector polynomial multiply long and accumulate

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Polynomial / Polynomial multiply

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME,FEAT_SVE_AES2,FEAT_SSVE_AES
```

### Return type metadata

```json
{
  "return_base_type": "uint64",
  "element_bit_size": "64",
  "value": "svuint64x2_t"
}
```

### Argument preparation and constraints

```json
{
  "zda": {
    "Z multi-vector": "{ Zreg2.Q, Zreg3.Q }"
  },
  "zn": {
    "register": "Zreg4.D"
  },
  "zm": {
    "register": "Xreg1"
  }
}
```

### Result mapping

```json
[
  {
    "{ Zreg2.Q, Zreg3.Q }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
MOV Zreg1.D, Xreg1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/MOV--scalar--unpredicated---Move-general-purpose-register-to-vector-elements--unpredicated---an-alias-of-DUP--scalar--

```asm
PMLAL { Zreg2.Q, Zreg3.Q }, Zreg4.D, Zreg1.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/PMLAL--Multi-vector-polynomial-multiply-long-and-accumulate-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svpmlal_pair[_u64_x2]

ISA classification: SME2 + FEAT_SVE_AES2, FEAT_SSVE_AES

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svpmlal_pair%5B_u64_x2%5D

### Signature (source notation)

```c
svuint64x2_t svpmlal_pair[_u64_x2](svuint64x2_t zda, svuint64_t zn, svuint64_t zm);
```

### Description

Multi-vector polynomial multiply long and accumulate

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Polynomial / Polynomial multiply

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME,FEAT_SVE_AES2,FEAT_SSVE_AES
```

### Return type metadata

```json
{
  "return_base_type": "uint64",
  "element_bit_size": "64",
  "value": "svuint64x2_t"
}
```

### Argument preparation and constraints

```json
{
  "zda": {
    "Z multi-vector": "{ Zreg1.Q, Zreg2.Q }"
  },
  "zn": {
    "register": "Zreg3.D"
  },
  "zm": {
    "register": "Zreg4.D"
  }
}
```

### Result mapping

```json
[
  {
    "{ Zreg1.Q, Zreg2.Q }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
PMLAL { Zreg1.Q, Zreg2.Q }, Zreg3.D, Zreg4.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/PMLAL--Multi-vector-polynomial-multiply-long-and-accumulate-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svpmull_pair[_n_u64_x2]

ISA classification: SME2 + FEAT_SVE_AES2, FEAT_SSVE_AES

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svpmull_pair%5B_n_u64_x2%5D

### Signature (source notation)

```c
svuint64x2_t svpmull_pair[_n_u64_x2](svuint64_t zn, uint64_t zm);
```

### Description

Multi-vector polynomial multiply long

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Polynomial / Polynomial multiply

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME,FEAT_SVE_AES2,FEAT_SSVE_AES
```

### Return type metadata

```json
{
  "return_base_type": "uint64",
  "element_bit_size": "64",
  "value": "svuint64x2_t"
}
```

### Argument preparation and constraints

```json
{
  "zn": {
    "register": "Zreg3.D"
  },
  "zm": {
    "register": "Xreg1"
  }
}
```

### Result mapping

```json
[
  {
    "{ Zreg2.Q, Zreg1.Q }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
MOV Zreg4.D, Xreg1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/MOV--scalar--unpredicated---Move-general-purpose-register-to-vector-elements--unpredicated---an-alias-of-DUP--scalar--

```asm
PMULL { Zreg2.Q, Zreg1.Q }, Zreg3.D, Zreg4.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/PMULL--Multi-vector-polynomial-multiply-long-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svpmull_pair[_u64_x2]

ISA classification: SME2 + FEAT_SVE_AES2, FEAT_SSVE_AES

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svpmull_pair%5B_u64_x2%5D

### Signature (source notation)

```c
svuint64x2_t svpmull_pair[_u64_x2](svuint64_t zn, svuint64_t zm);
```

### Description

Multi-vector polynomial multiply long

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Polynomial / Polynomial multiply

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME,FEAT_SVE_AES2,FEAT_SSVE_AES
```

### Return type metadata

```json
{
  "return_base_type": "uint64",
  "element_bit_size": "64",
  "value": "svuint64x2_t"
}
```

### Argument preparation and constraints

```json
{
  "zn": {
    "register": "Zreg3.D"
  },
  "zm": {
    "register": "Zreg4.D"
  }
}
```

### Result mapping

```json
[
  {
    "{ Zreg1.Q, Zreg2.Q }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
PMULL { Zreg1.Q, Zreg2.Q }, Zreg3.D, Zreg4.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/PMULL--Multi-vector-polynomial-multiply-long-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svpmullb_pair[_n_u64]

ISA classification: SME2 + FEAT_SSVE_AES

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svpmullb_pair%5B_n_u64%5D

### Signature (source notation)

```c
svuint64_t svpmullb_pair[_n_u64](svuint64_t op1, uint64_t op2);
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
FEAT_SME,FEAT_SSVE_AES
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
    "Zresult.Q": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
PMULLB Zresult.Q, Zop1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/PMULLB--Polynomial-multiply-long--bottom--

### Operation

Source operation ID: `SveOperation_svpmullb_pair_n_u8`

**Operation**



For each even-indexed (“bottom”) element *i*, treat `op1[i]` and `op2` as polynomials over GF(2) and compute their product.  Return a vector in which element *i* contains the low half of the result and in which element *i* + 1 contains the high half of the result.

## svpmullb_pair[_u64]

ISA classification: SME2 + FEAT_SSVE_AES

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svpmullb_pair%5B_u64%5D

### Signature (source notation)

```c
svuint64_t svpmullb_pair[_u64](svuint64_t op1, svuint64_t op2);
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
FEAT_SME,FEAT_SSVE_AES
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
    "Zresult.Q": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
PMULLB Zresult.Q, Zop1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/PMULLB--Polynomial-multiply-long--bottom--

### Operation

Source operation ID: `SveOperation_svpmullb_pair_u8`

**Operation**



For each even-indexed (“bottom”) element *i*, treat `op1[i]` and `op2[i]` as polynomials over GF(2) and compute their product.  Return a vector in which element *i* contains the low half of the result and in which element *i* + 1 contains the high half of the result.

## svpmullt_pair[_n_u64]

ISA classification: SME2 + FEAT_SSVE_AES

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svpmullt_pair%5B_n_u64%5D

### Signature (source notation)

```c
svuint64_t svpmullt_pair[_n_u64](svuint64_t op1, uint64_t op2);
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
FEAT_SME,FEAT_SSVE_AES
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
    "Zresult.Q": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
PMULLT Zresult.Q, Zop1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/PMULLT--Polynomial-multiply-long--top--

### Operation

Source operation ID: `SveOperation_svpmullt_pair_n_u8`

**Operation**



For each odd-indexed (“top”) element *i*, treat `op1[i]` and `op2` as polynomials over GF(2) and compute their product.  Return a vector in which element *i* - 1 contains the low half of the result and in which element *i* contains the high half of the result.

## svpmullt_pair[_u64]

ISA classification: SME2 + FEAT_SSVE_AES

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svpmullt_pair%5B_u64%5D

### Signature (source notation)

```c
svuint64_t svpmullt_pair[_u64](svuint64_t op1, svuint64_t op2);
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
FEAT_SME,FEAT_SSVE_AES
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
    "Zresult.Q": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
PMULLT Zresult.Q, Zop1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/PMULLT--Polynomial-multiply-long--top--

### Operation

Source operation ID: `SveOperation_svpmullt_pair_u8`

**Operation**



For each odd-indexed (“top”) element *i*, treat `op1[i]` and `op2[i]` as polynomials over GF(2) and compute their product.  Return a vector in which element *i* - 1 contains the low half of the result and in which element *i* contains the high half of the result.

