# SME / Vector arithmetic / Multiply-accumulate / Multiply-accumulate — Part 5

## svmsb[_u64]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmsb%5B_u64%5D_z

### Signature (source notation)

```c
svuint64_t svmsb[_u64]_z(svbool_t pg, svuint64_t op1, svuint64_t op2, svuint64_t op3);
```

### Description

Multiply-subtract, multiplicand first

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Multiply-accumulate

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
    "Zresult.D": "result"
  }
]
```

### Instruction mapping

When result is in a different register from op2 and op3, this intrinsic can use:

```asm
MOVPRFX Zresult.D, Pg/Z, Zop1.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
MSB Zresult.D, Pg/M, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MSB--Multiply-subtract-vectors--predicated---writing-multiplicand--Zdn---Za---Zdn---Zm--

When result is in a different register from op1 and op3, this intrinsic can use:

```asm
MOVPRFX Zresult.D, Pg/Z, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
MSB Zresult.D, Pg/M, Zop1.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MSB--Multiply-subtract-vectors--predicated---writing-multiplicand--Zdn---Za---Zdn---Zm--

When result is in a different register from op1 and op2, this intrinsic can use:

```asm
MOVPRFX Zresult.D, Pg/Z, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
MLS Zresult.D, Pg/M, Zop1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MLS--vectors---Multiply-subtract-vectors--predicated---writing-addend--Zda---Zda---Zn---Zm--

### Operation

Source operation ID: `SveOperation_svmsb_u8_z`

**Operation**



Return a vector in which each active element *i* contains the value:



```text
op3[i] - op1[i] * op2[i]
```



Set the inactive elements of the result to zero.

## svmsb[_u8]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmsb%5B_u8%5D_m

### Signature (source notation)

```c
svuint8_t svmsb[_u8]_m(svbool_t pg, svuint8_t op1, svuint8_t op2, svuint8_t op3);
```

### Description

Multiply-subtract, multiplicand first

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Multiply-accumulate

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
    "register": "Zop2.B"
  },
  "op3": {
    "register": "Zop3.B"
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
MSB Ztied1.B, Pg/M, Zop2.B, Zop3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MSB--Multiply-subtract-vectors--predicated---writing-multiplicand--Zdn---Za---Zdn---Zm--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
MSB Zresult.B, Pg/M, Zop2.B, Zop3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MSB--Multiply-subtract-vectors--predicated---writing-multiplicand--Zdn---Za---Zdn---Zm--

### Operation

Source operation ID: `SveOperation_svmsb_u8_m`

**Operation**



Return a vector in which each active element *i* contains the value:



```text
op3[i] - op1[i] * op2[i]
```



Take the inactive elements of the result from the corresponding elements of `op1`.

## svmsb[_u8]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmsb%5B_u8%5D_x

### Signature (source notation)

```c
svuint8_t svmsb[_u8]_x(svbool_t pg, svuint8_t op1, svuint8_t op2, svuint8_t op3);
```

### Description

Multiply-subtract, multiplicand first

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Multiply-accumulate

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
    "register": "Zop2.B|Ztied2.B"
  },
  "op3": {
    "register": "Zop3.B|Ztied3.B"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.B|Ztied1.B|Ztied2.B|Ztied3.B": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
MSB Ztied1.B, Pg/M, Zop2.B, Zop3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MSB--Multiply-subtract-vectors--predicated---writing-multiplicand--Zdn---Za---Zdn---Zm--

When result and op2 are in the same register, this intrinsic compiles to:

```asm
MSB Ztied2.B, Pg/M, Zop1.B, Zop3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MSB--Multiply-subtract-vectors--predicated---writing-multiplicand--Zdn---Za---Zdn---Zm--

When result and op3 are in the same register, this intrinsic compiles to:

```asm
MLS Ztied3.B, Pg/M, Zop1.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MLS--vectors---Multiply-subtract-vectors--predicated---writing-addend--Zda---Zda---Zn---Zm--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
MSB Zresult.B, Pg/M, Zop2.B, Zop3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MSB--Multiply-subtract-vectors--predicated---writing-multiplicand--Zdn---Za---Zdn---Zm--

### Operation

Source operation ID: `SveOperation_svmsb_u8_x`

**Operation**



Return a vector in which each active element *i* contains the value:



```text
op3[i] - op1[i] * op2[i]
```



The inactive elements of the result have arbitrary, undefined values.

## svmsb[_u8]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmsb%5B_u8%5D_z

### Signature (source notation)

```c
svuint8_t svmsb[_u8]_z(svbool_t pg, svuint8_t op1, svuint8_t op2, svuint8_t op3);
```

### Description

Multiply-subtract, multiplicand first

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Multiply-accumulate

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
    "register": "Zop2.B"
  },
  "op3": {
    "register": "Zop3.B"
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

When result is in a different register from op2 and op3, this intrinsic can use:

```asm
MOVPRFX Zresult.B, Pg/Z, Zop1.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
MSB Zresult.B, Pg/M, Zop2.B, Zop3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MSB--Multiply-subtract-vectors--predicated---writing-multiplicand--Zdn---Za---Zdn---Zm--

When result is in a different register from op1 and op3, this intrinsic can use:

```asm
MOVPRFX Zresult.B, Pg/Z, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
MSB Zresult.B, Pg/M, Zop1.B, Zop3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MSB--Multiply-subtract-vectors--predicated---writing-multiplicand--Zdn---Za---Zdn---Zm--

When result is in a different register from op1 and op2, this intrinsic can use:

```asm
MOVPRFX Zresult.B, Pg/Z, Zop3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
MLS Zresult.B, Pg/M, Zop1.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MLS--vectors---Multiply-subtract-vectors--predicated---writing-addend--Zda---Zda---Zn---Zm--

### Operation

Source operation ID: `SveOperation_svmsb_u8_z`

**Operation**



Return a vector in which each active element *i* contains the value:



```text
op3[i] - op1[i] * op2[i]
```



Set the inactive elements of the result to zero.

