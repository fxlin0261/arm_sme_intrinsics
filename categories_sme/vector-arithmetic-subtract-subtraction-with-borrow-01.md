# SME / Vector arithmetic / Subtract / Subtraction with borrow — Part 1

## svsbclb[_n_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsbclb%5B_n_u32%5D

### Signature (source notation)

```c
svuint32_t svsbclb[_n_u32](svuint32_t op1, svuint32_t op2, uint32_t op3);
```

### Description

Subtract with borrow long (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Subtract / Subtraction with borrow

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
    "register": "Zop1.S|Ztied1.S"
  },
  "op2": {
    "register": "Zop2.S"
  },
  "op3": {
    "register": "Zop3.S[*]"
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
SBCLB Ztied1.S, Zop2.S, Zop3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SBCLB--Subtract-with-carry-long--bottom--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SBCLB Zresult.S, Zop2.S, Zop3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SBCLB--Subtract-with-carry-long--bottom--

### Operation

Source operation ID: `SveOperation_svsbclb_n_u32`

**Operation**



For each even element index *i*, zero extend the following values to twice the width and add them together:




- `op1[i]`
- `~op2[i]`
- `op3 & 1`



Return a vector in which element *i* contains the low half of the result and in which element *i* + 1 contains the high half of the result.  The high half of the result is either 0 or 1 and acts a borrow.



Thus the low half of the result will be `op1[i] - op2[i]` when `op3 & 1` is one and `op1[i] - op2[i] - 1` when `op3 & 1` is zero.

## svsbclb[_n_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsbclb%5B_n_u64%5D

### Signature (source notation)

```c
svuint64_t svsbclb[_n_u64](svuint64_t op1, svuint64_t op2, uint64_t op3);
```

### Description

Subtract with borrow long (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Subtract / Subtraction with borrow

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
    "register": "Zop1.D|Ztied1.D"
  },
  "op2": {
    "register": "Zop2.D"
  },
  "op3": {
    "register": "Zop3.D[*]"
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
SBCLB Ztied1.D, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SBCLB--Subtract-with-carry-long--bottom--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SBCLB Zresult.D, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SBCLB--Subtract-with-carry-long--bottom--

### Operation

Source operation ID: `SveOperation_svsbclb_n_u32`

**Operation**



For each even element index *i*, zero extend the following values to twice the width and add them together:




- `op1[i]`
- `~op2[i]`
- `op3 & 1`



Return a vector in which element *i* contains the low half of the result and in which element *i* + 1 contains the high half of the result.  The high half of the result is either 0 or 1 and acts a borrow.



Thus the low half of the result will be `op1[i] - op2[i]` when `op3 & 1` is one and `op1[i] - op2[i] - 1` when `op3 & 1` is zero.

## svsbclb[_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsbclb%5B_u32%5D

### Signature (source notation)

```c
svuint32_t svsbclb[_u32](svuint32_t op1, svuint32_t op2, svuint32_t op3);
```

### Description

Subtract with borrow long (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Subtract / Subtraction with borrow

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
    "register": "Zop1.S|Ztied1.S"
  },
  "op2": {
    "register": "Zop2.S"
  },
  "op3": {
    "register": "Zop3.S"
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
SBCLB Ztied1.S, Zop2.S, Zop3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SBCLB--Subtract-with-carry-long--bottom--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SBCLB Zresult.S, Zop2.S, Zop3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SBCLB--Subtract-with-carry-long--bottom--

### Operation

Source operation ID: `SveOperation_svsbclb_u32`

**Operation**



For each even element index *i*, zero extend the following values to twice the width and add them together:




- `op1[i]`
- `~op2[i]`
- `op3[i + 1] & 1`



Return a vector in which element *i* contains the low half of the result and in which element *i* + 1 contains the high half of the result.  The high half of the result is either 0 or 1 and acts a borrow.



Thus the low half of the result will be `op1[i] - op2[i]` when `op3[i + 1] & 1` is one and `op1[i] - op2[i] - 1` when `op3[i + 1] & 1` is zero.

## svsbclb[_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsbclb%5B_u64%5D

### Signature (source notation)

```c
svuint64_t svsbclb[_u64](svuint64_t op1, svuint64_t op2, svuint64_t op3);
```

### Description

Subtract with borrow long (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Subtract / Subtraction with borrow

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
    "register": "Zop1.D|Ztied1.D"
  },
  "op2": {
    "register": "Zop2.D"
  },
  "op3": {
    "register": "Zop3.D"
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
SBCLB Ztied1.D, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SBCLB--Subtract-with-carry-long--bottom--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SBCLB Zresult.D, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SBCLB--Subtract-with-carry-long--bottom--

### Operation

Source operation ID: `SveOperation_svsbclb_u32`

**Operation**



For each even element index *i*, zero extend the following values to twice the width and add them together:




- `op1[i]`
- `~op2[i]`
- `op3[i + 1] & 1`



Return a vector in which element *i* contains the low half of the result and in which element *i* + 1 contains the high half of the result.  The high half of the result is either 0 or 1 and acts a borrow.



Thus the low half of the result will be `op1[i] - op2[i]` when `op3[i + 1] & 1` is one and `op1[i] - op2[i] - 1` when `op3[i + 1] & 1` is zero.

## svsbclt[_n_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsbclt%5B_n_u32%5D

### Signature (source notation)

```c
svuint32_t svsbclt[_n_u32](svuint32_t op1, svuint32_t op2, uint32_t op3);
```

### Description

Subtract with borrow long (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Subtract / Subtraction with borrow

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
    "register": "Zop1.S|Ztied1.S"
  },
  "op2": {
    "register": "Zop2.S"
  },
  "op3": {
    "register": "Zop3.S[*]"
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
SBCLT Ztied1.S, Zop2.S, Zop3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SBCLT--Subtract-with-carry-long--top--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SBCLT Zresult.S, Zop2.S, Zop3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SBCLT--Subtract-with-carry-long--top--

### Operation

Source operation ID: `SveOperation_svsbclt_n_u32`

**Operation**



For each even element index *i*, zero extend the following values to twice the width and add them together:




- `op1[i]`
- `~op2[i + 1]`
- `op3 & 1`



Return a vector in which element *i* contains the low half of the result and in which element *i* + 1 contains the high half of the result.  The high half of the result is either 0 or 1 and acts a borrow.



Thus the low half of the result will be `op1[i] - op2[i + 1]` when `op3 & 1` is one and `op1[i] - op2[i + 1] - 1` when `op3 & 1` is zero.

## svsbclt[_n_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsbclt%5B_n_u64%5D

### Signature (source notation)

```c
svuint64_t svsbclt[_n_u64](svuint64_t op1, svuint64_t op2, uint64_t op3);
```

### Description

Subtract with borrow long (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Subtract / Subtraction with borrow

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
    "register": "Zop1.D|Ztied1.D"
  },
  "op2": {
    "register": "Zop2.D"
  },
  "op3": {
    "register": "Zop3.D[*]"
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
SBCLT Ztied1.D, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SBCLT--Subtract-with-carry-long--top--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SBCLT Zresult.D, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SBCLT--Subtract-with-carry-long--top--

### Operation

Source operation ID: `SveOperation_svsbclt_n_u32`

**Operation**



For each even element index *i*, zero extend the following values to twice the width and add them together:




- `op1[i]`
- `~op2[i + 1]`
- `op3 & 1`



Return a vector in which element *i* contains the low half of the result and in which element *i* + 1 contains the high half of the result.  The high half of the result is either 0 or 1 and acts a borrow.



Thus the low half of the result will be `op1[i] - op2[i + 1]` when `op3 & 1` is one and `op1[i] - op2[i + 1] - 1` when `op3 & 1` is zero.

## svsbclt[_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsbclt%5B_u32%5D

### Signature (source notation)

```c
svuint32_t svsbclt[_u32](svuint32_t op1, svuint32_t op2, svuint32_t op3);
```

### Description

Subtract with borrow long (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Subtract / Subtraction with borrow

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
    "register": "Zop1.S|Ztied1.S"
  },
  "op2": {
    "register": "Zop2.S"
  },
  "op3": {
    "register": "Zop3.S"
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
SBCLT Ztied1.S, Zop2.S, Zop3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SBCLT--Subtract-with-carry-long--top--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SBCLT Zresult.S, Zop2.S, Zop3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SBCLT--Subtract-with-carry-long--top--

### Operation

Source operation ID: `SveOperation_svsbclt_u32`

**Operation**



For each even element index *i*, zero extend the following values to twice the width and add them together:




- `op1[i]`
- `~op2[i + 1]`
- `op3[i + 1] & 1`



Return a vector in which element *i* contains the low half of the result and in which element *i* + 1 contains the high half of the result.  The high half of the result is either 0 or 1 and acts a borrow.



Thus the low half of the result will be `op1[i] - op2[i + 1]` when `op3[i + 1] & 1` is one and `op1[i] - op2[i + 1] - 1` when `op3[i + 1] & 1` is zero.

## svsbclt[_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsbclt%5B_u64%5D

### Signature (source notation)

```c
svuint64_t svsbclt[_u64](svuint64_t op1, svuint64_t op2, svuint64_t op3);
```

### Description

Subtract with borrow long (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Subtract / Subtraction with borrow

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
    "register": "Zop1.D|Ztied1.D"
  },
  "op2": {
    "register": "Zop2.D"
  },
  "op3": {
    "register": "Zop3.D"
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
SBCLT Ztied1.D, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SBCLT--Subtract-with-carry-long--top--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SBCLT Zresult.D, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SBCLT--Subtract-with-carry-long--top--

### Operation

Source operation ID: `SveOperation_svsbclt_u32`

**Operation**



For each even element index *i*, zero extend the following values to twice the width and add them together:




- `op1[i]`
- `~op2[i + 1]`
- `op3[i + 1] & 1`



Return a vector in which element *i* contains the low half of the result and in which element *i* + 1 contains the high half of the result.  The high half of the result is either 0 or 1 and acts a borrow.



Thus the low half of the result will be `op1[i] - op2[i + 1]` when `op3[i + 1] & 1` is one and `op1[i] - op2[i + 1] - 1` when `op3[i + 1] & 1` is zero.

