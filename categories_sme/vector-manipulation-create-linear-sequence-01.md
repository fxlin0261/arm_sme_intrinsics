# SME / Vector manipulation / Create linear sequence — Part 1

## svindex_s16

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svindex_s16

### Signature (source notation)

```c
svint16_t svindex_s16(int16_t base, int16_t step);
```

### Description

Create linear series

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Create linear sequence

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
  "base": {
    "register": "Wbase"
  },
  "step": {
    "register": "Wstep"
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

When base and step are in the range [-16, 15], this intrinsic can use:

```asm
INDEX Zresult.H, #base, #step
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/INDEX--immediates---Create-index-starting-from-and-incremented-by-immediate-

When base is in the range [-16, 15], this intrinsic can use:

```asm
INDEX Zresult.H, #base, Wstep
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/INDEX--immediate--scalar---Create-index-starting-from-immediate-and-incremented-by-general-purpose-register-

When step is in the range [-16, 15], this intrinsic can use:

```asm
INDEX Zresult.H, Wbase, #step
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/INDEX--scalar--immediate---Create-index-starting-from-general-purpose-register-and-incremented-by-immediate-

The general implementation is:

```asm
INDEX Zresult.H, Wbase, Wstep
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/INDEX--scalars---Create-index-starting-from-and-incremented-by-general-purpose-register-

### Operation

Source operation ID: `SveOperation_svindex_s8`

**Operation**



Return a vector in which element *i* contains `base + i * step`.

## svindex_s32

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svindex_s32

### Signature (source notation)

```c
svint32_t svindex_s32(int32_t base, int32_t step);
```

### Description

Create linear series

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Create linear sequence

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
  "base": {
    "register": "Wbase"
  },
  "step": {
    "register": "Wstep"
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

When base and step are in the range [-16, 15], this intrinsic can use:

```asm
INDEX Zresult.S, #base, #step
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/INDEX--immediates---Create-index-starting-from-and-incremented-by-immediate-

When base is in the range [-16, 15], this intrinsic can use:

```asm
INDEX Zresult.S, #base, Wstep
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/INDEX--immediate--scalar---Create-index-starting-from-immediate-and-incremented-by-general-purpose-register-

When step is in the range [-16, 15], this intrinsic can use:

```asm
INDEX Zresult.S, Wbase, #step
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/INDEX--scalar--immediate---Create-index-starting-from-general-purpose-register-and-incremented-by-immediate-

The general implementation is:

```asm
INDEX Zresult.S, Wbase, Wstep
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/INDEX--scalars---Create-index-starting-from-and-incremented-by-general-purpose-register-

### Operation

Source operation ID: `SveOperation_svindex_s8`

**Operation**



Return a vector in which element *i* contains `base + i * step`.

## svindex_s64

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svindex_s64

### Signature (source notation)

```c
svint64_t svindex_s64(int64_t base, int64_t step);
```

### Description

Create linear series

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Create linear sequence

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
  "base": {
    "register": "Xbase"
  },
  "step": {
    "register": "Xstep"
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

When base and step are in the range [-16, 15], this intrinsic can use:

```asm
INDEX Zresult.D, #base, #step
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/INDEX--immediates---Create-index-starting-from-and-incremented-by-immediate-

When base is in the range [-16, 15], this intrinsic can use:

```asm
INDEX Zresult.D, #base, Xstep
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/INDEX--immediate--scalar---Create-index-starting-from-immediate-and-incremented-by-general-purpose-register-

When step is in the range [-16, 15], this intrinsic can use:

```asm
INDEX Zresult.D, Xbase, #step
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/INDEX--scalar--immediate---Create-index-starting-from-general-purpose-register-and-incremented-by-immediate-

The general implementation is:

```asm
INDEX Zresult.D, Xbase, Xstep
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/INDEX--scalars---Create-index-starting-from-and-incremented-by-general-purpose-register-

### Operation

Source operation ID: `SveOperation_svindex_s8`

**Operation**



Return a vector in which element *i* contains `base + i * step`.

## svindex_s8

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svindex_s8

### Signature (source notation)

```c
svint8_t svindex_s8(int8_t base, int8_t step);
```

### Description

Create linear series

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Create linear sequence

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
  "base": {
    "register": "Wbase"
  },
  "step": {
    "register": "Wstep"
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

When base and step are in the range [-16, 15], this intrinsic can use:

```asm
INDEX Zresult.B, #base, #step
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/INDEX--immediates---Create-index-starting-from-and-incremented-by-immediate-

When base is in the range [-16, 15], this intrinsic can use:

```asm
INDEX Zresult.B, #base, Wstep
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/INDEX--immediate--scalar---Create-index-starting-from-immediate-and-incremented-by-general-purpose-register-

When step is in the range [-16, 15], this intrinsic can use:

```asm
INDEX Zresult.B, Wbase, #step
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/INDEX--scalar--immediate---Create-index-starting-from-general-purpose-register-and-incremented-by-immediate-

The general implementation is:

```asm
INDEX Zresult.B, Wbase, Wstep
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/INDEX--scalars---Create-index-starting-from-and-incremented-by-general-purpose-register-

### Operation

Source operation ID: `SveOperation_svindex_s8`

**Operation**



Return a vector in which element *i* contains `base + i * step`.

## svindex_u16

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svindex_u16

### Signature (source notation)

```c
svuint16_t svindex_u16(uint16_t base, uint16_t step);
```

### Description

Create linear series

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Create linear sequence

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
  "base": {
    "register": "Wbase"
  },
  "step": {
    "register": "Wstep"
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

When (int16_t)base and (int16_t)step are in the range [-16, 15], this intrinsic can use:

```asm
INDEX Zresult.H, #base, #step
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/INDEX--immediates---Create-index-starting-from-and-incremented-by-immediate-

When (int16_t)base is in the range [-16, 15], this intrinsic can use:

```asm
INDEX Zresult.H, #base, Wstep
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/INDEX--immediate--scalar---Create-index-starting-from-immediate-and-incremented-by-general-purpose-register-

When (int16_t)step is in the range [-16, 15], this intrinsic can use:

```asm
INDEX Zresult.H, Wbase, #step
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/INDEX--scalar--immediate---Create-index-starting-from-general-purpose-register-and-incremented-by-immediate-

The general implementation is:

```asm
INDEX Zresult.H, Wbase, Wstep
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/INDEX--scalars---Create-index-starting-from-and-incremented-by-general-purpose-register-

### Operation

Source operation ID: `SveOperation_svindex_s8`

**Operation**



Return a vector in which element *i* contains `base + i * step`.

## svindex_u32

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svindex_u32

### Signature (source notation)

```c
svuint32_t svindex_u32(uint32_t base, uint32_t step);
```

### Description

Create linear series

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Create linear sequence

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
  "base": {
    "register": "Wbase"
  },
  "step": {
    "register": "Wstep"
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

When (int32_t)base and (int32_t)step are in the range [-16, 15], this intrinsic can use:

```asm
INDEX Zresult.S, #base, #step
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/INDEX--immediates---Create-index-starting-from-and-incremented-by-immediate-

When (int32_t)base is in the range [-16, 15], this intrinsic can use:

```asm
INDEX Zresult.S, #base, Wstep
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/INDEX--immediate--scalar---Create-index-starting-from-immediate-and-incremented-by-general-purpose-register-

When (int32_t)step is in the range [-16, 15], this intrinsic can use:

```asm
INDEX Zresult.S, Wbase, #step
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/INDEX--scalar--immediate---Create-index-starting-from-general-purpose-register-and-incremented-by-immediate-

The general implementation is:

```asm
INDEX Zresult.S, Wbase, Wstep
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/INDEX--scalars---Create-index-starting-from-and-incremented-by-general-purpose-register-

### Operation

Source operation ID: `SveOperation_svindex_s8`

**Operation**



Return a vector in which element *i* contains `base + i * step`.

## svindex_u64

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svindex_u64

### Signature (source notation)

```c
svuint64_t svindex_u64(uint64_t base, uint64_t step);
```

### Description

Create linear series

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Create linear sequence

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
  "base": {
    "register": "Xbase"
  },
  "step": {
    "register": "Xstep"
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

When (int64_t)base and (int64_t)step are in the range [-16, 15], this intrinsic can use:

```asm
INDEX Zresult.D, #base, #step
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/INDEX--immediates---Create-index-starting-from-and-incremented-by-immediate-

When (int64_t)base is in the range [-16, 15], this intrinsic can use:

```asm
INDEX Zresult.D, #base, Xstep
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/INDEX--immediate--scalar---Create-index-starting-from-immediate-and-incremented-by-general-purpose-register-

When (int64_t)step is in the range [-16, 15], this intrinsic can use:

```asm
INDEX Zresult.D, Xbase, #step
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/INDEX--scalar--immediate---Create-index-starting-from-general-purpose-register-and-incremented-by-immediate-

The general implementation is:

```asm
INDEX Zresult.D, Xbase, Xstep
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/INDEX--scalars---Create-index-starting-from-and-incremented-by-general-purpose-register-

### Operation

Source operation ID: `SveOperation_svindex_s8`

**Operation**



Return a vector in which element *i* contains `base + i * step`.

## svindex_u8

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svindex_u8

### Signature (source notation)

```c
svuint8_t svindex_u8(uint8_t base, uint8_t step);
```

### Description

Create linear series

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Create linear sequence

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
  "base": {
    "register": "Wbase"
  },
  "step": {
    "register": "Wstep"
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

When (int8_t)base and (int8_t)step are in the range [-16, 15], this intrinsic can use:

```asm
INDEX Zresult.B, #base, #step
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/INDEX--immediates---Create-index-starting-from-and-incremented-by-immediate-

When (int8_t)base is in the range [-16, 15], this intrinsic can use:

```asm
INDEX Zresult.B, #base, Wstep
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/INDEX--immediate--scalar---Create-index-starting-from-immediate-and-incremented-by-general-purpose-register-

When (int8_t)step is in the range [-16, 15], this intrinsic can use:

```asm
INDEX Zresult.B, Wbase, #step
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/INDEX--scalar--immediate---Create-index-starting-from-general-purpose-register-and-incremented-by-immediate-

The general implementation is:

```asm
INDEX Zresult.B, Wbase, Wstep
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/INDEX--scalars---Create-index-starting-from-and-incremented-by-general-purpose-register-

### Operation

Source operation ID: `SveOperation_svindex_s8`

**Operation**



Return a vector in which element *i* contains `base + i * step`.

