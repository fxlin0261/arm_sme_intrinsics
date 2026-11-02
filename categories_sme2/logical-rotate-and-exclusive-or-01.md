# SME2 / Logical / Rotate and exclusive OR — Part 1

## svrax1[_s64]

ISA classification: SME2.1 + FEAT_SVE_SHA3

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrax1%5B_s64%5D

### Signature (source notation)

```c
svint64_t svrax1[_s64](svint64_t op1, svint64_t op2);
```

### Description

Bitwise rotate left by 1 and exclusive OR

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Logical / Rotate and exclusive OR

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2p1,FEAT_SVE_SHA3
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

This intrinsic compiles to the following instruction:

```asm
RAX1 Zresult.D, Zop1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/RAX1--Bitwise-rotate-left-by-1-and-exclusive-OR-

### Operation

Source operation ID: `SveOperation_svrax1_s64`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Rotate `op2[i]` left by one bit.
- Exclusive-OR the result with `op1[i]`.

## svrax1[_u64]

ISA classification: SME2.1 + FEAT_SVE_SHA3

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svrax1%5B_u64%5D

### Signature (source notation)

```c
svuint64_t svrax1[_u64](svuint64_t op1, svuint64_t op2);
```

### Description

Bitwise rotate left by 1 and exclusive OR

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Logical / Rotate and exclusive OR

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2p1,FEAT_SVE_SHA3
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
    "Zresult.D": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
RAX1 Zresult.D, Zop1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/RAX1--Bitwise-rotate-left-by-1-and-exclusive-OR-

### Operation

Source operation ID: `SveOperation_svrax1_s64`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- Rotate `op2[i]` left by one bit.
- Exclusive-OR the result with `op1[i]`.

