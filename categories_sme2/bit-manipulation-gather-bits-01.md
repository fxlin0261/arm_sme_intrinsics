# SME2 / Bit manipulation / Gather bits — Part 1

## svbext[_n_u16]

ISA classification: SME2 + FEAT_SSVE_BitPerm

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svbext%5B_n_u16%5D

### Signature (source notation)

```c
svuint16_t svbext[_n_u16](svuint16_t op1, uint16_t op2);
```

### Description

Gather lower bits from positions selected by bitmask

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Bit manipulation / Gather bits

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME,FEAT_SSVE_BitPerm
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

This intrinsic compiles to the following instruction:

```asm
BEXT Zresult.H, Zop1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BEXT--Gather-lower-bits-from-positions-selected-by-bitmask-

### Operation

Source operation ID: `SveOperation_svbext_n_u8`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- For each bit position *j*, extract bit *j* from `op1[i]` if bit *j* of `op2` is nonzero.
- Collect the extracted bits together into the low-order bits of an element, preserving the order of the extracted bits.
- Fill any remaining higher-order bits of the element with zero.



For example, if `op2` is 0xaa and `op1[i]` contains the bits *mnopqrst* (with *t* being the lsb), then element *i* of the result will contain the zero extension of *moqs*.

## svbext[_n_u32]

ISA classification: SME2 + FEAT_SSVE_BitPerm

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svbext%5B_n_u32%5D

### Signature (source notation)

```c
svuint32_t svbext[_n_u32](svuint32_t op1, uint32_t op2);
```

### Description

Gather lower bits from positions selected by bitmask

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Bit manipulation / Gather bits

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME,FEAT_SSVE_BitPerm
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
    "Zresult.S": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
BEXT Zresult.S, Zop1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BEXT--Gather-lower-bits-from-positions-selected-by-bitmask-

### Operation

Source operation ID: `SveOperation_svbext_n_u8`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- For each bit position *j*, extract bit *j* from `op1[i]` if bit *j* of `op2` is nonzero.
- Collect the extracted bits together into the low-order bits of an element, preserving the order of the extracted bits.
- Fill any remaining higher-order bits of the element with zero.



For example, if `op2` is 0xaa and `op1[i]` contains the bits *mnopqrst* (with *t* being the lsb), then element *i* of the result will contain the zero extension of *moqs*.

## svbext[_n_u64]

ISA classification: SME2 + FEAT_SSVE_BitPerm

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svbext%5B_n_u64%5D

### Signature (source notation)

```c
svuint64_t svbext[_n_u64](svuint64_t op1, uint64_t op2);
```

### Description

Gather lower bits from positions selected by bitmask

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Bit manipulation / Gather bits

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME,FEAT_SSVE_BitPerm
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
    "Zresult.D": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
BEXT Zresult.D, Zop1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BEXT--Gather-lower-bits-from-positions-selected-by-bitmask-

### Operation

Source operation ID: `SveOperation_svbext_n_u8`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- For each bit position *j*, extract bit *j* from `op1[i]` if bit *j* of `op2` is nonzero.
- Collect the extracted bits together into the low-order bits of an element, preserving the order of the extracted bits.
- Fill any remaining higher-order bits of the element with zero.



For example, if `op2` is 0xaa and `op1[i]` contains the bits *mnopqrst* (with *t* being the lsb), then element *i* of the result will contain the zero extension of *moqs*.

## svbext[_n_u8]

ISA classification: SME2 + FEAT_SSVE_BitPerm

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svbext%5B_n_u8%5D

### Signature (source notation)

```c
svuint8_t svbext[_n_u8](svuint8_t op1, uint8_t op2);
```

### Description

Gather lower bits from positions selected by bitmask

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Bit manipulation / Gather bits

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME,FEAT_SSVE_BitPerm
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
BEXT Zresult.B, Zop1.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BEXT--Gather-lower-bits-from-positions-selected-by-bitmask-

### Operation

Source operation ID: `SveOperation_svbext_n_u8`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- For each bit position *j*, extract bit *j* from `op1[i]` if bit *j* of `op2` is nonzero.
- Collect the extracted bits together into the low-order bits of an element, preserving the order of the extracted bits.
- Fill any remaining higher-order bits of the element with zero.



For example, if `op2` is 0xaa and `op1[i]` contains the bits *mnopqrst* (with *t* being the lsb), then element *i* of the result will contain the zero extension of *moqs*.

## svbext[_u16]

ISA classification: SME2 + FEAT_SSVE_BitPerm

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svbext%5B_u16%5D

### Signature (source notation)

```c
svuint16_t svbext[_u16](svuint16_t op1, svuint16_t op2);
```

### Description

Gather lower bits from positions selected by bitmask

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Bit manipulation / Gather bits

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME,FEAT_SSVE_BitPerm
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

This intrinsic compiles to the following instruction:

```asm
BEXT Zresult.H, Zop1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BEXT--Gather-lower-bits-from-positions-selected-by-bitmask-

### Operation

Source operation ID: `SveOperation_svbext_u8`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- For each bit position *j*, extract bit *j* from `op1[i]` if bit *j* of `op2[i]` is nonzero.
- Collect the extracted bits together into the low-order bits of an element, preserving the order of the extracted bits.
- Fill any remaining higher-order bits of the element with zero.



For example, if `op2[i]` is 0xaa and `op1[i]` contains the bits *mnopqrst* (with *t* being the lsb), then element *i* of the result will contain the zero extension of *moqs*.

## svbext[_u32]

ISA classification: SME2 + FEAT_SSVE_BitPerm

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svbext%5B_u32%5D

### Signature (source notation)

```c
svuint32_t svbext[_u32](svuint32_t op1, svuint32_t op2);
```

### Description

Gather lower bits from positions selected by bitmask

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Bit manipulation / Gather bits

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME,FEAT_SSVE_BitPerm
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
    "Zresult.S": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
BEXT Zresult.S, Zop1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BEXT--Gather-lower-bits-from-positions-selected-by-bitmask-

### Operation

Source operation ID: `SveOperation_svbext_u8`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- For each bit position *j*, extract bit *j* from `op1[i]` if bit *j* of `op2[i]` is nonzero.
- Collect the extracted bits together into the low-order bits of an element, preserving the order of the extracted bits.
- Fill any remaining higher-order bits of the element with zero.



For example, if `op2[i]` is 0xaa and `op1[i]` contains the bits *mnopqrst* (with *t* being the lsb), then element *i* of the result will contain the zero extension of *moqs*.

## svbext[_u64]

ISA classification: SME2 + FEAT_SSVE_BitPerm

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svbext%5B_u64%5D

### Signature (source notation)

```c
svuint64_t svbext[_u64](svuint64_t op1, svuint64_t op2);
```

### Description

Gather lower bits from positions selected by bitmask

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Bit manipulation / Gather bits

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME,FEAT_SSVE_BitPerm
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
BEXT Zresult.D, Zop1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BEXT--Gather-lower-bits-from-positions-selected-by-bitmask-

### Operation

Source operation ID: `SveOperation_svbext_u8`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- For each bit position *j*, extract bit *j* from `op1[i]` if bit *j* of `op2[i]` is nonzero.
- Collect the extracted bits together into the low-order bits of an element, preserving the order of the extracted bits.
- Fill any remaining higher-order bits of the element with zero.



For example, if `op2[i]` is 0xaa and `op1[i]` contains the bits *mnopqrst* (with *t* being the lsb), then element *i* of the result will contain the zero extension of *moqs*.

## svbext[_u8]

ISA classification: SME2 + FEAT_SSVE_BitPerm

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svbext%5B_u8%5D

### Signature (source notation)

```c
svuint8_t svbext[_u8](svuint8_t op1, svuint8_t op2);
```

### Description

Gather lower bits from positions selected by bitmask

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Bit manipulation / Gather bits

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME,FEAT_SSVE_BitPerm
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
BEXT Zresult.B, Zop1.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BEXT--Gather-lower-bits-from-positions-selected-by-bitmask-

### Operation

Source operation ID: `SveOperation_svbext_u8`

**Operation**



Return a vector in which each element *i* contains the result of the following procedure:




- For each bit position *j*, extract bit *j* from `op1[i]` if bit *j* of `op2[i]` is nonzero.
- Collect the extracted bits together into the low-order bits of an element, preserving the order of the extracted bits.
- Fill any remaining higher-order bits of the element with zero.



For example, if `op2[i]` is 0xaa and `op1[i]` contains the bits *mnopqrst* (with *t* being the lsb), then element *i* of the result will contain the zero extension of *moqs*.

