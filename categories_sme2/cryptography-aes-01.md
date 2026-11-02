# SME2 / Cryptography / AES — Part 1

## svaesd[_u8]

ISA classification: SME2 + FEAT_SSVE_AES

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svaesd%5B_u8%5D

### Signature (source notation)

```c
svuint8_t svaesd[_u8](svuint8_t op1, svuint8_t op2);
```

### Description

AES single round decryption

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Cryptography / AES

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
  "element_bit_size": "8",
  "value": "svuint8_t"
}
```

### Argument preparation and constraints

```json
{
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
    "Ztied1.B|Ztied2.B": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
AESD Ztied1.B, Ztied1.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/AESD--vectors---AES-single-round-decryption-

When result and op2 are in the same register, this intrinsic compiles to:

```asm
AESD Ztied2.B, Ztied2.B, Zop1.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/AESD--vectors---AES-single-round-decryption-

### Operation

Source operation ID: `SveOperation_svaesd_u8`

**Operation**



This function maps directly to the [AESD](https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/AESD--AES-single-round-decryption-) instruction; see there for a detailed description.

## svaesd_lane[_u8_x2]

ISA classification: SME2 + FEAT_SVE_AES2, FEAT_SSVE_AES

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svaesd_lane%5B_u8_x2%5D

### Signature (source notation)

```c
svuint8x2_t svaesd_lane[_u8_x2](svuint8x2_t zdn, svuint8_t zm, uint64_t index);
```

### Description

Multi-vector AES single round decryption

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Cryptography / AES

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
  "return_base_type": "uint8",
  "element_bit_size": "8",
  "value": "svuint8x2_t"
}
```

### Argument preparation and constraints

```json
{
  "zdn": {
    "Z multi-vector": "{ Zreg1.B, Zreg2.B }"
  },
  "zm": {
    "register": "Zreg3.Q"
  },
  "index": {
    "immediate": "imm1"
  }
}
```

### Result mapping

```json
[
  {
    "{ Zreg1.B, Zreg2.B }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
AESD { Zreg1.B, Zreg2.B }, { Zreg1.B, Zreg2.B }, Zreg3.Q[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/AESD--indexed---Multi-vector-AES-single-round-decryption-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svaesd_lane[_u8_x4]

ISA classification: SME2 + FEAT_SVE_AES2, FEAT_SSVE_AES

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svaesd_lane%5B_u8_x4%5D

### Signature (source notation)

```c
svuint8x4_t svaesd_lane[_u8_x4](svuint8x4_t zdn, svuint8_t zm, uint64_t index);
```

### Description

Multi-vector AES single round decryption

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Cryptography / AES

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
  "return_base_type": "uint8",
  "element_bit_size": "8",
  "value": "svuint8x4_t"
}
```

### Argument preparation and constraints

```json
{
  "zdn": {
    "Z multi-vector": "{ Zreg1.B - Zreg2.B }"
  },
  "zm": {
    "register": "Zreg3.Q"
  },
  "index": {
    "immediate": "imm1"
  }
}
```

### Result mapping

```json
[
  {
    "{ Zreg1.B - Zreg2.B }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
AESD { Zreg1.B - Zreg2.B }, { Zreg1.B - Zreg2.B }, Zreg3.Q[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/AESD--indexed---Multi-vector-AES-single-round-decryption-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svaesdimc_lane[_u8_x2]

ISA classification: SME2 + FEAT_SVE_AES2, FEAT_SSVE_AES

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svaesdimc_lane%5B_u8_x2%5D

### Signature (source notation)

```c
svuint8x2_t svaesdimc_lane[_u8_x2](svuint8x2_t zdn, svuint8_t zm, uint64_t index);
```

### Description

Multi-vector AES single round decryption and inverse mix columns

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Cryptography / AES

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
  "return_base_type": "uint8",
  "element_bit_size": "8",
  "value": "svuint8x2_t"
}
```

### Argument preparation and constraints

```json
{
  "zdn": {
    "Z multi-vector": "{ Zreg1.B, Zreg2.B }"
  },
  "zm": {
    "register": "Zreg3.Q"
  },
  "index": {
    "immediate": "imm1"
  }
}
```

### Result mapping

```json
[
  {
    "{ Zreg1.B, Zreg2.B }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
AESDIMC { Zreg1.B, Zreg2.B }, { Zreg1.B, Zreg2.B }, Zreg3.Q[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/AESDIMC--Multi-vector-AES-single-round-decryption-and-inverse-mix-columns-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svaesdimc_lane[_u8_x4]

ISA classification: SME2 + FEAT_SVE_AES2, FEAT_SSVE_AES

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svaesdimc_lane%5B_u8_x4%5D

### Signature (source notation)

```c
svuint8x4_t svaesdimc_lane[_u8_x4](svuint8x4_t zdn, svuint8_t zm, uint64_t index);
```

### Description

Multi-vector AES single round decryption and inverse mix columns

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Cryptography / AES

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
  "return_base_type": "uint8",
  "element_bit_size": "8",
  "value": "svuint8x4_t"
}
```

### Argument preparation and constraints

```json
{
  "zdn": {
    "Z multi-vector": "{ Zreg1.B - Zreg2.B }"
  },
  "zm": {
    "register": "Zreg3.Q"
  },
  "index": {
    "immediate": "imm1"
  }
}
```

### Result mapping

```json
[
  {
    "{ Zreg1.B - Zreg2.B }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
AESDIMC { Zreg1.B - Zreg2.B }, { Zreg1.B - Zreg2.B }, Zreg3.Q[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/AESDIMC--Multi-vector-AES-single-round-decryption-and-inverse-mix-columns-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svaese[_u8]

ISA classification: SME2 + FEAT_SSVE_AES

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svaese%5B_u8%5D

### Signature (source notation)

```c
svuint8_t svaese[_u8](svuint8_t op1, svuint8_t op2);
```

### Description

AES single round encryption

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Cryptography / AES

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
  "element_bit_size": "8",
  "value": "svuint8_t"
}
```

### Argument preparation and constraints

```json
{
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
    "Ztied1.B|Ztied2.B": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
AESE Ztied1.B, Ztied1.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/AESE--vectors---AES-single-round-encryption-

When result and op2 are in the same register, this intrinsic compiles to:

```asm
AESE Ztied2.B, Ztied2.B, Zop1.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/AESE--vectors---AES-single-round-encryption-

### Operation

Source operation ID: `SveOperation_svaese_u8`

**Operation**



This function maps directly to the [AESE](https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/AESE--AES-single-round-encryption-) instruction; see there for a detailed description.

## svaese_lane[_u8_x2]

ISA classification: SME2 + FEAT_SVE_AES2, FEAT_SSVE_AES

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svaese_lane%5B_u8_x2%5D

### Signature (source notation)

```c
svuint8x2_t svaese_lane[_u8_x2](svuint8x2_t zdn, svuint8_t zm, uint64_t index);
```

### Description

Multi-vector AES single round encryption

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Cryptography / AES

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
  "return_base_type": "uint8",
  "element_bit_size": "8",
  "value": "svuint8x2_t"
}
```

### Argument preparation and constraints

```json
{
  "zdn": {
    "Z multi-vector": "{ Zreg1.B, Zreg2.B }"
  },
  "zm": {
    "register": "Zreg3.Q"
  },
  "index": {
    "immediate": "imm1"
  }
}
```

### Result mapping

```json
[
  {
    "{ Zreg1.B, Zreg2.B }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
AESE { Zreg1.B, Zreg2.B }, { Zreg1.B, Zreg2.B }, Zreg3.Q[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/AESE--indexed---Multi-vector-AES-single-round-encryption-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svaese_lane[_u8_x4]

ISA classification: SME2 + FEAT_SVE_AES2, FEAT_SSVE_AES

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svaese_lane%5B_u8_x4%5D

### Signature (source notation)

```c
svuint8x4_t svaese_lane[_u8_x4](svuint8x4_t zdn, svuint8_t zm, uint64_t index);
```

### Description

Multi-vector AES single round encryption

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Cryptography / AES

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
  "return_base_type": "uint8",
  "element_bit_size": "8",
  "value": "svuint8x4_t"
}
```

### Argument preparation and constraints

```json
{
  "zdn": {
    "Z multi-vector": "{ Zreg1.B - Zreg2.B }"
  },
  "zm": {
    "register": "Zreg3.Q"
  },
  "index": {
    "immediate": "imm1"
  }
}
```

### Result mapping

```json
[
  {
    "{ Zreg1.B - Zreg2.B }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
AESE { Zreg1.B - Zreg2.B }, { Zreg1.B - Zreg2.B }, Zreg3.Q[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/AESE--indexed---Multi-vector-AES-single-round-encryption-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svaesemc_lane[_u8_x2]

ISA classification: SME2 + FEAT_SVE_AES2, FEAT_SSVE_AES

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svaesemc_lane%5B_u8_x2%5D

### Signature (source notation)

```c
svuint8x2_t svaesemc_lane[_u8_x2](svuint8x2_t zdn, svuint8_t zm, uint64_t index);
```

### Description

Multi-vector AES single round encryption and mix columns

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Cryptography / AES

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
  "return_base_type": "uint8",
  "element_bit_size": "8",
  "value": "svuint8x2_t"
}
```

### Argument preparation and constraints

```json
{
  "zdn": {
    "Z multi-vector": "{ Zreg1.B, Zreg2.B }"
  },
  "zm": {
    "register": "Zreg3.Q"
  },
  "index": {
    "immediate": "imm1"
  }
}
```

### Result mapping

```json
[
  {
    "{ Zreg1.B, Zreg2.B }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
AESEMC { Zreg1.B, Zreg2.B }, { Zreg1.B, Zreg2.B }, Zreg3.Q[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/AESEMC--Multi-vector-AES-single-round-encryption-and-mix-columns-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svaesemc_lane[_u8_x4]

ISA classification: SME2 + FEAT_SVE_AES2, FEAT_SSVE_AES

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svaesemc_lane%5B_u8_x4%5D

### Signature (source notation)

```c
svuint8x4_t svaesemc_lane[_u8_x4](svuint8x4_t zdn, svuint8_t zm, uint64_t index);
```

### Description

Multi-vector AES single round encryption and mix columns

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Cryptography / AES

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
  "return_base_type": "uint8",
  "element_bit_size": "8",
  "value": "svuint8x4_t"
}
```

### Argument preparation and constraints

```json
{
  "zdn": {
    "Z multi-vector": "{ Zreg1.B - Zreg2.B }"
  },
  "zm": {
    "register": "Zreg3.Q"
  },
  "index": {
    "immediate": "imm1"
  }
}
```

### Result mapping

```json
[
  {
    "{ Zreg1.B - Zreg2.B }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
AESEMC { Zreg1.B - Zreg2.B }, { Zreg1.B - Zreg2.B }, Zreg3.Q[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/AESEMC--Multi-vector-AES-single-round-encryption-and-mix-columns-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svaesimc[_u8]

ISA classification: SME2 + FEAT_SSVE_AES

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svaesimc%5B_u8%5D

### Signature (source notation)

```c
svuint8_t svaesimc[_u8](svuint8_t op);
```

### Description

AES inverse mix columns

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Cryptography / AES

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
  "element_bit_size": "8",
  "value": "svuint8_t"
}
```

### Argument preparation and constraints

```json
{
  "op": {
    "register": "Ztied.B"
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
AESIMC Ztied.B, Ztied.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/AESIMC--AES-inverse-mix-columns-

### Operation

Source operation ID: `SveOperation_svaesimc_u8`

**Operation**



This function maps directly to the [AESIMC](https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/AESIMC--AES-inverse-mix-columns-) instruction; see there for a detailed description.

## svaesmc[_u8]

ISA classification: SME2 + FEAT_SSVE_AES

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svaesmc%5B_u8%5D

### Signature (source notation)

```c
svuint8_t svaesmc[_u8](svuint8_t op);
```

### Description

AES mix columns

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Cryptography / AES

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
  "element_bit_size": "8",
  "value": "svuint8_t"
}
```

### Argument preparation and constraints

```json
{
  "op": {
    "register": "Ztied.B"
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
AESMC Ztied.B, Ztied.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/AESMC--AES-mix-columns-

### Operation

Source operation ID: `SveOperation_svaesmc_u8`

**Operation**



This function maps directly to the [AESMC](https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/AESMC--AES-mix-columns-) instruction; see there for a detailed description.

