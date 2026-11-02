# SME / Vector arithmetic / Multiply-accumulate / Multiply-accumulate — Part 3

## svmla_lane[_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmla_lane%5B_u32%5D

### Signature (source notation)

```c
svuint32_t svmla_lane[_u32](svuint32_t op1, svuint32_t op2, svuint32_t op3, uint64_t imm_index);
```

### Description

Multiply-add, addend first

### Availability

- ISA categories: SME and SME2, SVE2

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
  },
  "imm_index": {
    "minimum": 0,
    "maximum": 3
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
MLA Ztied1.S, Zop2.S, Zop3.S[imm_index]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MLA--indexed---Multiply-add-to-accumulator--indexed--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
MLA Zresult.S, Zop2.S, Zop3.S[imm_index]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MLA--indexed---Multiply-add-to-accumulator--indexed--

### Operation

Source operation ID: `SveOperation_svmla_lane_u16`

**Operation**



Return a vector in which each element *i* contains the value:



```text
op1[i] + op2[i] * op3[base + imm_index]
```



where *base* is the index of the first element in the same 128-bit quadword as *i*.

## svmla_lane[_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmla_lane%5B_u64%5D

### Signature (source notation)

```c
svuint64_t svmla_lane[_u64](svuint64_t op1, svuint64_t op2, svuint64_t op3, uint64_t imm_index);
```

### Description

Multiply-add, addend first

### Availability

- ISA categories: SME and SME2, SVE2

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
  "op1": {
    "register": "Zop1.D|Ztied1.D"
  },
  "op2": {
    "register": "Zop2.D"
  },
  "op3": {
    "register": "Zop3.D"
  },
  "imm_index": {
    "minimum": 0,
    "maximum": 1
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
MLA Ztied1.D, Zop2.D, Zop3.D[imm_index]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MLA--indexed---Multiply-add-to-accumulator--indexed--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
MLA Zresult.D, Zop2.D, Zop3.D[imm_index]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MLA--indexed---Multiply-add-to-accumulator--indexed--

### Operation

Source operation ID: `SveOperation_svmla_lane_u16`

**Operation**



Return a vector in which each element *i* contains the value:



```text
op1[i] + op2[i] * op3[base + imm_index]
```



where *base* is the index of the first element in the same 128-bit quadword as *i*.

## svmls[_n_s16]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmls%5B_n_s16%5D_m

### Signature (source notation)

```c
svint16_t svmls[_n_s16]_m(svbool_t pg, svint16_t op1, svint16_t op2, int16_t op3);
```

### Description

Multiply-subtract, minuend first

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
  },
  "op3": {
    "register": "Zop3.H[*]"
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
MLS Ztied1.H, Pg/M, Zop2.H, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MLS--vectors---Multiply-subtract-vectors--predicated---writing-addend--Zda---Zda---Zn---Zm--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
MLS Zresult.H, Pg/M, Zop2.H, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MLS--vectors---Multiply-subtract-vectors--predicated---writing-addend--Zda---Zda---Zn---Zm--

### Operation

Source operation ID: `SveOperation_svmls_n_s8_m`

**Operation**



Return a vector in which each active element *i* contains the value:



```text
op1[i] - op2[i] * op3
```



Take the inactive elements of the result from the corresponding elements of `op1`.



The operation uses modulo arithmetic.  The behavior is therefore defined for all inputs; unlike C, there is no undefined behavior for signed overflow.

## svmls[_n_s16]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmls%5B_n_s16%5D_x

### Signature (source notation)

```c
svint16_t svmls[_n_s16]_x(svbool_t pg, svint16_t op1, svint16_t op2, int16_t op3);
```

### Description

Multiply-subtract, minuend first

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
  },
  "op3": {
    "register": "Zop3.H[*]|Ztied3.H[*]"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.H|Ztied1.H|Ztied2.H|Ztied3.H": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
MLS Ztied1.H, Pg/M, Zop2.H, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MLS--vectors---Multiply-subtract-vectors--predicated---writing-addend--Zda---Zda---Zn---Zm--

When result and op2 are in the same register, this intrinsic compiles to:

```asm
MSB Ztied2.H, Pg/M, Zop3.H, Zop1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MSB--Multiply-subtract-vectors--predicated---writing-multiplicand--Zdn---Za---Zdn---Zm--

When result and op3 are in the same register, this intrinsic compiles to:

```asm
MSB Ztied3.H, Pg/M, Zop2.H, Zop1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MSB--Multiply-subtract-vectors--predicated---writing-multiplicand--Zdn---Za---Zdn---Zm--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
MLS Zresult.H, Pg/M, Zop2.H, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MLS--vectors---Multiply-subtract-vectors--predicated---writing-addend--Zda---Zda---Zn---Zm--

### Operation

Source operation ID: `SveOperation_svmls_n_s8_x`

**Operation**



Return a vector in which each active element *i* contains the value:



```text
op1[i] - op2[i] * op3
```



The inactive elements of the result have arbitrary, undefined values.



The operation uses modulo arithmetic.  The behavior is therefore defined for all inputs; unlike C, there is no undefined behavior for signed overflow.

## svmls[_n_s16]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmls%5B_n_s16%5D_z

### Signature (source notation)

```c
svint16_t svmls[_n_s16]_z(svbool_t pg, svint16_t op1, svint16_t op2, int16_t op3);
```

### Description

Multiply-subtract, minuend first

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
  },
  "op3": {
    "register": "Zop3.H[*]"
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

When result is in a different register from op2 and op3, this intrinsic can use:

```asm
MOVPRFX Zresult.H, Pg/Z, Zop1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
MLS Zresult.H, Pg/M, Zop2.H, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MLS--vectors---Multiply-subtract-vectors--predicated---writing-addend--Zda---Zda---Zn---Zm--

When result is in a different register from op3 and op1, this intrinsic can use:

```asm
MOVPRFX Zresult.H, Pg/Z, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
MSB Zresult.H, Pg/M, Zop3.H, Zop1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MSB--Multiply-subtract-vectors--predicated---writing-multiplicand--Zdn---Za---Zdn---Zm--

When result is in a different register from op2 and op1, this intrinsic can use:

```asm
MOVPRFX Zresult.H, Pg/Z, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
MSB Zresult.H, Pg/M, Zop2.H, Zop1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MSB--Multiply-subtract-vectors--predicated---writing-multiplicand--Zdn---Za---Zdn---Zm--

### Operation

Source operation ID: `SveOperation_svmls_n_s8_z`

**Operation**



Return a vector in which each active element *i* contains the value:



```text
op1[i] - op2[i] * op3
```



Set the inactive elements of the result to zero.



The operation uses modulo arithmetic.  The behavior is therefore defined for all inputs; unlike C, there is no undefined behavior for signed overflow.

## svmls[_n_s32]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmls%5B_n_s32%5D_m

### Signature (source notation)

```c
svint32_t svmls[_n_s32]_m(svbool_t pg, svint32_t op1, svint32_t op2, int32_t op3);
```

### Description

Multiply-subtract, minuend first

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
MLS Ztied1.S, Pg/M, Zop2.S, Zop3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MLS--vectors---Multiply-subtract-vectors--predicated---writing-addend--Zda---Zda---Zn---Zm--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
MLS Zresult.S, Pg/M, Zop2.S, Zop3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MLS--vectors---Multiply-subtract-vectors--predicated---writing-addend--Zda---Zda---Zn---Zm--

### Operation

Source operation ID: `SveOperation_svmls_n_s8_m`

**Operation**



Return a vector in which each active element *i* contains the value:



```text
op1[i] - op2[i] * op3
```



Take the inactive elements of the result from the corresponding elements of `op1`.



The operation uses modulo arithmetic.  The behavior is therefore defined for all inputs; unlike C, there is no undefined behavior for signed overflow.

## svmls[_n_s32]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmls%5B_n_s32%5D_x

### Signature (source notation)

```c
svint32_t svmls[_n_s32]_x(svbool_t pg, svint32_t op1, svint32_t op2, int32_t op3);
```

### Description

Multiply-subtract, minuend first

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
  },
  "op3": {
    "register": "Zop3.S[*]|Ztied3.S[*]"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.S|Ztied1.S|Ztied2.S|Ztied3.S": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
MLS Ztied1.S, Pg/M, Zop2.S, Zop3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MLS--vectors---Multiply-subtract-vectors--predicated---writing-addend--Zda---Zda---Zn---Zm--

When result and op2 are in the same register, this intrinsic compiles to:

```asm
MSB Ztied2.S, Pg/M, Zop3.S, Zop1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MSB--Multiply-subtract-vectors--predicated---writing-multiplicand--Zdn---Za---Zdn---Zm--

When result and op3 are in the same register, this intrinsic compiles to:

```asm
MSB Ztied3.S, Pg/M, Zop2.S, Zop1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MSB--Multiply-subtract-vectors--predicated---writing-multiplicand--Zdn---Za---Zdn---Zm--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
MLS Zresult.S, Pg/M, Zop2.S, Zop3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MLS--vectors---Multiply-subtract-vectors--predicated---writing-addend--Zda---Zda---Zn---Zm--

### Operation

Source operation ID: `SveOperation_svmls_n_s8_x`

**Operation**



Return a vector in which each active element *i* contains the value:



```text
op1[i] - op2[i] * op3
```



The inactive elements of the result have arbitrary, undefined values.



The operation uses modulo arithmetic.  The behavior is therefore defined for all inputs; unlike C, there is no undefined behavior for signed overflow.

## svmls[_n_s32]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmls%5B_n_s32%5D_z

### Signature (source notation)

```c
svint32_t svmls[_n_s32]_z(svbool_t pg, svint32_t op1, svint32_t op2, int32_t op3);
```

### Description

Multiply-subtract, minuend first

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
    "Zresult.S": "result"
  }
]
```

### Instruction mapping

When result is in a different register from op2 and op3, this intrinsic can use:

```asm
MOVPRFX Zresult.S, Pg/Z, Zop1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
MLS Zresult.S, Pg/M, Zop2.S, Zop3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MLS--vectors---Multiply-subtract-vectors--predicated---writing-addend--Zda---Zda---Zn---Zm--

When result is in a different register from op3 and op1, this intrinsic can use:

```asm
MOVPRFX Zresult.S, Pg/Z, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
MSB Zresult.S, Pg/M, Zop3.S, Zop1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MSB--Multiply-subtract-vectors--predicated---writing-multiplicand--Zdn---Za---Zdn---Zm--

When result is in a different register from op2 and op1, this intrinsic can use:

```asm
MOVPRFX Zresult.S, Pg/Z, Zop3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
MSB Zresult.S, Pg/M, Zop2.S, Zop1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MSB--Multiply-subtract-vectors--predicated---writing-multiplicand--Zdn---Za---Zdn---Zm--

### Operation

Source operation ID: `SveOperation_svmls_n_s8_z`

**Operation**



Return a vector in which each active element *i* contains the value:



```text
op1[i] - op2[i] * op3
```



Set the inactive elements of the result to zero.



The operation uses modulo arithmetic.  The behavior is therefore defined for all inputs; unlike C, there is no undefined behavior for signed overflow.

## svmls[_n_s64]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmls%5B_n_s64%5D_m

### Signature (source notation)

```c
svint64_t svmls[_n_s64]_m(svbool_t pg, svint64_t op1, svint64_t op2, int64_t op3);
```

### Description

Multiply-subtract, minuend first

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
MLS Ztied1.D, Pg/M, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MLS--vectors---Multiply-subtract-vectors--predicated---writing-addend--Zda---Zda---Zn---Zm--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
MLS Zresult.D, Pg/M, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MLS--vectors---Multiply-subtract-vectors--predicated---writing-addend--Zda---Zda---Zn---Zm--

### Operation

Source operation ID: `SveOperation_svmls_n_s8_m`

**Operation**



Return a vector in which each active element *i* contains the value:



```text
op1[i] - op2[i] * op3
```



Take the inactive elements of the result from the corresponding elements of `op1`.



The operation uses modulo arithmetic.  The behavior is therefore defined for all inputs; unlike C, there is no undefined behavior for signed overflow.

## svmls[_n_s64]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmls%5B_n_s64%5D_x

### Signature (source notation)

```c
svint64_t svmls[_n_s64]_x(svbool_t pg, svint64_t op1, svint64_t op2, int64_t op3);
```

### Description

Multiply-subtract, minuend first

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
  },
  "op3": {
    "register": "Zop3.D[*]|Ztied3.D[*]"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.D|Ztied1.D|Ztied2.D|Ztied3.D": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
MLS Ztied1.D, Pg/M, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MLS--vectors---Multiply-subtract-vectors--predicated---writing-addend--Zda---Zda---Zn---Zm--

When result and op2 are in the same register, this intrinsic compiles to:

```asm
MSB Ztied2.D, Pg/M, Zop3.D, Zop1.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MSB--Multiply-subtract-vectors--predicated---writing-multiplicand--Zdn---Za---Zdn---Zm--

When result and op3 are in the same register, this intrinsic compiles to:

```asm
MSB Ztied3.D, Pg/M, Zop2.D, Zop1.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MSB--Multiply-subtract-vectors--predicated---writing-multiplicand--Zdn---Za---Zdn---Zm--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
MLS Zresult.D, Pg/M, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MLS--vectors---Multiply-subtract-vectors--predicated---writing-addend--Zda---Zda---Zn---Zm--

### Operation

Source operation ID: `SveOperation_svmls_n_s8_x`

**Operation**



Return a vector in which each active element *i* contains the value:



```text
op1[i] - op2[i] * op3
```



The inactive elements of the result have arbitrary, undefined values.



The operation uses modulo arithmetic.  The behavior is therefore defined for all inputs; unlike C, there is no undefined behavior for signed overflow.

## svmls[_n_s64]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmls%5B_n_s64%5D_z

### Signature (source notation)

```c
svint64_t svmls[_n_s64]_z(svbool_t pg, svint64_t op1, svint64_t op2, int64_t op3);
```

### Description

Multiply-subtract, minuend first

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
MLS Zresult.D, Pg/M, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MLS--vectors---Multiply-subtract-vectors--predicated---writing-addend--Zda---Zda---Zn---Zm--

When result is in a different register from op3 and op1, this intrinsic can use:

```asm
MOVPRFX Zresult.D, Pg/Z, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
MSB Zresult.D, Pg/M, Zop3.D, Zop1.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MSB--Multiply-subtract-vectors--predicated---writing-multiplicand--Zdn---Za---Zdn---Zm--

When result is in a different register from op2 and op1, this intrinsic can use:

```asm
MOVPRFX Zresult.D, Pg/Z, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
MSB Zresult.D, Pg/M, Zop2.D, Zop1.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MSB--Multiply-subtract-vectors--predicated---writing-multiplicand--Zdn---Za---Zdn---Zm--

### Operation

Source operation ID: `SveOperation_svmls_n_s8_z`

**Operation**



Return a vector in which each active element *i* contains the value:



```text
op1[i] - op2[i] * op3
```



Set the inactive elements of the result to zero.



The operation uses modulo arithmetic.  The behavior is therefore defined for all inputs; unlike C, there is no undefined behavior for signed overflow.

## svmls[_n_s8]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmls%5B_n_s8%5D_m

### Signature (source notation)

```c
svint8_t svmls[_n_s8]_m(svbool_t pg, svint8_t op1, svint8_t op2, int8_t op3);
```

### Description

Multiply-subtract, minuend first

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
  },
  "op3": {
    "register": "Zop3.B[*]"
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
MLS Ztied1.B, Pg/M, Zop2.B, Zop3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MLS--vectors---Multiply-subtract-vectors--predicated---writing-addend--Zda---Zda---Zn---Zm--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
MLS Zresult.B, Pg/M, Zop2.B, Zop3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MLS--vectors---Multiply-subtract-vectors--predicated---writing-addend--Zda---Zda---Zn---Zm--

### Operation

Source operation ID: `SveOperation_svmls_n_s8_m`

**Operation**



Return a vector in which each active element *i* contains the value:



```text
op1[i] - op2[i] * op3
```



Take the inactive elements of the result from the corresponding elements of `op1`.



The operation uses modulo arithmetic.  The behavior is therefore defined for all inputs; unlike C, there is no undefined behavior for signed overflow.

## svmls[_n_s8]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmls%5B_n_s8%5D_x

### Signature (source notation)

```c
svint8_t svmls[_n_s8]_x(svbool_t pg, svint8_t op1, svint8_t op2, int8_t op3);
```

### Description

Multiply-subtract, minuend first

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
  },
  "op3": {
    "register": "Zop3.B[*]|Ztied3.B[*]"
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
MLS Ztied1.B, Pg/M, Zop2.B, Zop3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MLS--vectors---Multiply-subtract-vectors--predicated---writing-addend--Zda---Zda---Zn---Zm--

When result and op2 are in the same register, this intrinsic compiles to:

```asm
MSB Ztied2.B, Pg/M, Zop3.B, Zop1.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MSB--Multiply-subtract-vectors--predicated---writing-multiplicand--Zdn---Za---Zdn---Zm--

When result and op3 are in the same register, this intrinsic compiles to:

```asm
MSB Ztied3.B, Pg/M, Zop2.B, Zop1.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MSB--Multiply-subtract-vectors--predicated---writing-multiplicand--Zdn---Za---Zdn---Zm--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
MLS Zresult.B, Pg/M, Zop2.B, Zop3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MLS--vectors---Multiply-subtract-vectors--predicated---writing-addend--Zda---Zda---Zn---Zm--

### Operation

Source operation ID: `SveOperation_svmls_n_s8_x`

**Operation**



Return a vector in which each active element *i* contains the value:



```text
op1[i] - op2[i] * op3
```



The inactive elements of the result have arbitrary, undefined values.



The operation uses modulo arithmetic.  The behavior is therefore defined for all inputs; unlike C, there is no undefined behavior for signed overflow.

## svmls[_n_s8]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmls%5B_n_s8%5D_z

### Signature (source notation)

```c
svint8_t svmls[_n_s8]_z(svbool_t pg, svint8_t op1, svint8_t op2, int8_t op3);
```

### Description

Multiply-subtract, minuend first

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
  },
  "op3": {
    "register": "Zop3.B[*]"
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
MLS Zresult.B, Pg/M, Zop2.B, Zop3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MLS--vectors---Multiply-subtract-vectors--predicated---writing-addend--Zda---Zda---Zn---Zm--

When result is in a different register from op3 and op1, this intrinsic can use:

```asm
MOVPRFX Zresult.B, Pg/Z, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
MSB Zresult.B, Pg/M, Zop3.B, Zop1.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MSB--Multiply-subtract-vectors--predicated---writing-multiplicand--Zdn---Za---Zdn---Zm--

When result is in a different register from op2 and op1, this intrinsic can use:

```asm
MOVPRFX Zresult.B, Pg/Z, Zop3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
MSB Zresult.B, Pg/M, Zop2.B, Zop1.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MSB--Multiply-subtract-vectors--predicated---writing-multiplicand--Zdn---Za---Zdn---Zm--

### Operation

Source operation ID: `SveOperation_svmls_n_s8_z`

**Operation**



Return a vector in which each active element *i* contains the value:



```text
op1[i] - op2[i] * op3
```



Set the inactive elements of the result to zero.



The operation uses modulo arithmetic.  The behavior is therefore defined for all inputs; unlike C, there is no undefined behavior for signed overflow.

## svmls[_n_u16]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmls%5B_n_u16%5D_m

### Signature (source notation)

```c
svuint16_t svmls[_n_u16]_m(svbool_t pg, svuint16_t op1, svuint16_t op2, uint16_t op3);
```

### Description

Multiply-subtract, minuend first

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
  },
  "op3": {
    "register": "Zop3.H[*]"
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
MLS Ztied1.H, Pg/M, Zop2.H, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MLS--vectors---Multiply-subtract-vectors--predicated---writing-addend--Zda---Zda---Zn---Zm--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
MLS Zresult.H, Pg/M, Zop2.H, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MLS--vectors---Multiply-subtract-vectors--predicated---writing-addend--Zda---Zda---Zn---Zm--

### Operation

Source operation ID: `SveOperation_svmls_n_u8_m`

**Operation**



Return a vector in which each active element *i* contains the value:



```text
op1[i] - op2[i] * op3
```



Take the inactive elements of the result from the corresponding elements of `op1`.

## svmls[_n_u16]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmls%5B_n_u16%5D_x

### Signature (source notation)

```c
svuint16_t svmls[_n_u16]_x(svbool_t pg, svuint16_t op1, svuint16_t op2, uint16_t op3);
```

### Description

Multiply-subtract, minuend first

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
  },
  "op3": {
    "register": "Zop3.H[*]|Ztied3.H[*]"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.H|Ztied1.H|Ztied2.H|Ztied3.H": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
MLS Ztied1.H, Pg/M, Zop2.H, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MLS--vectors---Multiply-subtract-vectors--predicated---writing-addend--Zda---Zda---Zn---Zm--

When result and op2 are in the same register, this intrinsic compiles to:

```asm
MSB Ztied2.H, Pg/M, Zop3.H, Zop1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MSB--Multiply-subtract-vectors--predicated---writing-multiplicand--Zdn---Za---Zdn---Zm--

When result and op3 are in the same register, this intrinsic compiles to:

```asm
MSB Ztied3.H, Pg/M, Zop2.H, Zop1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MSB--Multiply-subtract-vectors--predicated---writing-multiplicand--Zdn---Za---Zdn---Zm--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
MLS Zresult.H, Pg/M, Zop2.H, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MLS--vectors---Multiply-subtract-vectors--predicated---writing-addend--Zda---Zda---Zn---Zm--

### Operation

Source operation ID: `SveOperation_svmls_n_u8_x`

**Operation**



Return a vector in which each active element *i* contains the value:



```text
op1[i] - op2[i] * op3
```



The inactive elements of the result have arbitrary, undefined values.

## svmls[_n_u16]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmls%5B_n_u16%5D_z

### Signature (source notation)

```c
svuint16_t svmls[_n_u16]_z(svbool_t pg, svuint16_t op1, svuint16_t op2, uint16_t op3);
```

### Description

Multiply-subtract, minuend first

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
  },
  "op3": {
    "register": "Zop3.H[*]"
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

When result is in a different register from op2 and op3, this intrinsic can use:

```asm
MOVPRFX Zresult.H, Pg/Z, Zop1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
MLS Zresult.H, Pg/M, Zop2.H, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MLS--vectors---Multiply-subtract-vectors--predicated---writing-addend--Zda---Zda---Zn---Zm--

When result is in a different register from op3 and op1, this intrinsic can use:

```asm
MOVPRFX Zresult.H, Pg/Z, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
MSB Zresult.H, Pg/M, Zop3.H, Zop1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MSB--Multiply-subtract-vectors--predicated---writing-multiplicand--Zdn---Za---Zdn---Zm--

When result is in a different register from op2 and op1, this intrinsic can use:

```asm
MOVPRFX Zresult.H, Pg/Z, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
MSB Zresult.H, Pg/M, Zop2.H, Zop1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MSB--Multiply-subtract-vectors--predicated---writing-multiplicand--Zdn---Za---Zdn---Zm--

### Operation

Source operation ID: `SveOperation_svmls_n_u8_z`

**Operation**



Return a vector in which each active element *i* contains the value:



```text
op1[i] - op2[i] * op3
```



Set the inactive elements of the result to zero.

## svmls[_n_u32]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmls%5B_n_u32%5D_m

### Signature (source notation)

```c
svuint32_t svmls[_n_u32]_m(svbool_t pg, svuint32_t op1, svuint32_t op2, uint32_t op3);
```

### Description

Multiply-subtract, minuend first

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
MLS Ztied1.S, Pg/M, Zop2.S, Zop3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MLS--vectors---Multiply-subtract-vectors--predicated---writing-addend--Zda---Zda---Zn---Zm--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
MLS Zresult.S, Pg/M, Zop2.S, Zop3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MLS--vectors---Multiply-subtract-vectors--predicated---writing-addend--Zda---Zda---Zn---Zm--

### Operation

Source operation ID: `SveOperation_svmls_n_u8_m`

**Operation**



Return a vector in which each active element *i* contains the value:



```text
op1[i] - op2[i] * op3
```



Take the inactive elements of the result from the corresponding elements of `op1`.

## svmls[_n_u32]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmls%5B_n_u32%5D_x

### Signature (source notation)

```c
svuint32_t svmls[_n_u32]_x(svbool_t pg, svuint32_t op1, svuint32_t op2, uint32_t op3);
```

### Description

Multiply-subtract, minuend first

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
  },
  "op3": {
    "register": "Zop3.S[*]|Ztied3.S[*]"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.S|Ztied1.S|Ztied2.S|Ztied3.S": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
MLS Ztied1.S, Pg/M, Zop2.S, Zop3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MLS--vectors---Multiply-subtract-vectors--predicated---writing-addend--Zda---Zda---Zn---Zm--

When result and op2 are in the same register, this intrinsic compiles to:

```asm
MSB Ztied2.S, Pg/M, Zop3.S, Zop1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MSB--Multiply-subtract-vectors--predicated---writing-multiplicand--Zdn---Za---Zdn---Zm--

When result and op3 are in the same register, this intrinsic compiles to:

```asm
MSB Ztied3.S, Pg/M, Zop2.S, Zop1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MSB--Multiply-subtract-vectors--predicated---writing-multiplicand--Zdn---Za---Zdn---Zm--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
MLS Zresult.S, Pg/M, Zop2.S, Zop3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MLS--vectors---Multiply-subtract-vectors--predicated---writing-addend--Zda---Zda---Zn---Zm--

### Operation

Source operation ID: `SveOperation_svmls_n_u8_x`

**Operation**



Return a vector in which each active element *i* contains the value:



```text
op1[i] - op2[i] * op3
```



The inactive elements of the result have arbitrary, undefined values.

## svmls[_n_u32]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmls%5B_n_u32%5D_z

### Signature (source notation)

```c
svuint32_t svmls[_n_u32]_z(svbool_t pg, svuint32_t op1, svuint32_t op2, uint32_t op3);
```

### Description

Multiply-subtract, minuend first

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
    "Zresult.S": "result"
  }
]
```

### Instruction mapping

When result is in a different register from op2 and op3, this intrinsic can use:

```asm
MOVPRFX Zresult.S, Pg/Z, Zop1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
MLS Zresult.S, Pg/M, Zop2.S, Zop3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MLS--vectors---Multiply-subtract-vectors--predicated---writing-addend--Zda---Zda---Zn---Zm--

When result is in a different register from op3 and op1, this intrinsic can use:

```asm
MOVPRFX Zresult.S, Pg/Z, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
MSB Zresult.S, Pg/M, Zop3.S, Zop1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MSB--Multiply-subtract-vectors--predicated---writing-multiplicand--Zdn---Za---Zdn---Zm--

When result is in a different register from op2 and op1, this intrinsic can use:

```asm
MOVPRFX Zresult.S, Pg/Z, Zop3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
MSB Zresult.S, Pg/M, Zop2.S, Zop1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MSB--Multiply-subtract-vectors--predicated---writing-multiplicand--Zdn---Za---Zdn---Zm--

### Operation

Source operation ID: `SveOperation_svmls_n_u8_z`

**Operation**



Return a vector in which each active element *i* contains the value:



```text
op1[i] - op2[i] * op3
```



Set the inactive elements of the result to zero.

## svmls[_n_u64]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmls%5B_n_u64%5D_m

### Signature (source notation)

```c
svuint64_t svmls[_n_u64]_m(svbool_t pg, svuint64_t op1, svuint64_t op2, uint64_t op3);
```

### Description

Multiply-subtract, minuend first

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
MLS Ztied1.D, Pg/M, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MLS--vectors---Multiply-subtract-vectors--predicated---writing-addend--Zda---Zda---Zn---Zm--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
MLS Zresult.D, Pg/M, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MLS--vectors---Multiply-subtract-vectors--predicated---writing-addend--Zda---Zda---Zn---Zm--

### Operation

Source operation ID: `SveOperation_svmls_n_u8_m`

**Operation**



Return a vector in which each active element *i* contains the value:



```text
op1[i] - op2[i] * op3
```



Take the inactive elements of the result from the corresponding elements of `op1`.

## svmls[_n_u64]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmls%5B_n_u64%5D_x

### Signature (source notation)

```c
svuint64_t svmls[_n_u64]_x(svbool_t pg, svuint64_t op1, svuint64_t op2, uint64_t op3);
```

### Description

Multiply-subtract, minuend first

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
    "register": "Zop1.D|Ztied1.D"
  },
  "op2": {
    "register": "Zop2.D|Ztied2.D"
  },
  "op3": {
    "register": "Zop3.D[*]|Ztied3.D[*]"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.D|Ztied1.D|Ztied2.D|Ztied3.D": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
MLS Ztied1.D, Pg/M, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MLS--vectors---Multiply-subtract-vectors--predicated---writing-addend--Zda---Zda---Zn---Zm--

When result and op2 are in the same register, this intrinsic compiles to:

```asm
MSB Ztied2.D, Pg/M, Zop3.D, Zop1.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MSB--Multiply-subtract-vectors--predicated---writing-multiplicand--Zdn---Za---Zdn---Zm--

When result and op3 are in the same register, this intrinsic compiles to:

```asm
MSB Ztied3.D, Pg/M, Zop2.D, Zop1.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MSB--Multiply-subtract-vectors--predicated---writing-multiplicand--Zdn---Za---Zdn---Zm--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
MLS Zresult.D, Pg/M, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MLS--vectors---Multiply-subtract-vectors--predicated---writing-addend--Zda---Zda---Zn---Zm--

### Operation

Source operation ID: `SveOperation_svmls_n_u8_x`

**Operation**



Return a vector in which each active element *i* contains the value:



```text
op1[i] - op2[i] * op3
```



The inactive elements of the result have arbitrary, undefined values.

## svmls[_n_u64]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmls%5B_n_u64%5D_z

### Signature (source notation)

```c
svuint64_t svmls[_n_u64]_z(svbool_t pg, svuint64_t op1, svuint64_t op2, uint64_t op3);
```

### Description

Multiply-subtract, minuend first

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
    "register": "Zop3.D[*]"
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
MLS Zresult.D, Pg/M, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MLS--vectors---Multiply-subtract-vectors--predicated---writing-addend--Zda---Zda---Zn---Zm--

When result is in a different register from op3 and op1, this intrinsic can use:

```asm
MOVPRFX Zresult.D, Pg/Z, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
MSB Zresult.D, Pg/M, Zop3.D, Zop1.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MSB--Multiply-subtract-vectors--predicated---writing-multiplicand--Zdn---Za---Zdn---Zm--

When result is in a different register from op2 and op1, this intrinsic can use:

```asm
MOVPRFX Zresult.D, Pg/Z, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
MSB Zresult.D, Pg/M, Zop2.D, Zop1.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MSB--Multiply-subtract-vectors--predicated---writing-multiplicand--Zdn---Za---Zdn---Zm--

### Operation

Source operation ID: `SveOperation_svmls_n_u8_z`

**Operation**



Return a vector in which each active element *i* contains the value:



```text
op1[i] - op2[i] * op3
```



Set the inactive elements of the result to zero.

## svmls[_n_u8]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmls%5B_n_u8%5D_m

### Signature (source notation)

```c
svuint8_t svmls[_n_u8]_m(svbool_t pg, svuint8_t op1, svuint8_t op2, uint8_t op3);
```

### Description

Multiply-subtract, minuend first

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
    "register": "Zop3.B[*]"
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
MLS Ztied1.B, Pg/M, Zop2.B, Zop3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MLS--vectors---Multiply-subtract-vectors--predicated---writing-addend--Zda---Zda---Zn---Zm--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
MLS Zresult.B, Pg/M, Zop2.B, Zop3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MLS--vectors---Multiply-subtract-vectors--predicated---writing-addend--Zda---Zda---Zn---Zm--

### Operation

Source operation ID: `SveOperation_svmls_n_u8_m`

**Operation**



Return a vector in which each active element *i* contains the value:



```text
op1[i] - op2[i] * op3
```



Take the inactive elements of the result from the corresponding elements of `op1`.

## svmls[_n_u8]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmls%5B_n_u8%5D_x

### Signature (source notation)

```c
svuint8_t svmls[_n_u8]_x(svbool_t pg, svuint8_t op1, svuint8_t op2, uint8_t op3);
```

### Description

Multiply-subtract, minuend first

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
    "register": "Zop3.B[*]|Ztied3.B[*]"
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
MLS Ztied1.B, Pg/M, Zop2.B, Zop3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MLS--vectors---Multiply-subtract-vectors--predicated---writing-addend--Zda---Zda---Zn---Zm--

When result and op2 are in the same register, this intrinsic compiles to:

```asm
MSB Ztied2.B, Pg/M, Zop3.B, Zop1.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MSB--Multiply-subtract-vectors--predicated---writing-multiplicand--Zdn---Za---Zdn---Zm--

When result and op3 are in the same register, this intrinsic compiles to:

```asm
MSB Ztied3.B, Pg/M, Zop2.B, Zop1.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MSB--Multiply-subtract-vectors--predicated---writing-multiplicand--Zdn---Za---Zdn---Zm--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
MLS Zresult.B, Pg/M, Zop2.B, Zop3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MLS--vectors---Multiply-subtract-vectors--predicated---writing-addend--Zda---Zda---Zn---Zm--

### Operation

Source operation ID: `SveOperation_svmls_n_u8_x`

**Operation**



Return a vector in which each active element *i* contains the value:



```text
op1[i] - op2[i] * op3
```



The inactive elements of the result have arbitrary, undefined values.

## svmls[_n_u8]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmls%5B_n_u8%5D_z

### Signature (source notation)

```c
svuint8_t svmls[_n_u8]_z(svbool_t pg, svuint8_t op1, svuint8_t op2, uint8_t op3);
```

### Description

Multiply-subtract, minuend first

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
    "register": "Zop3.B[*]"
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
MLS Zresult.B, Pg/M, Zop2.B, Zop3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MLS--vectors---Multiply-subtract-vectors--predicated---writing-addend--Zda---Zda---Zn---Zm--

When result is in a different register from op3 and op1, this intrinsic can use:

```asm
MOVPRFX Zresult.B, Pg/Z, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
MSB Zresult.B, Pg/M, Zop3.B, Zop1.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MSB--Multiply-subtract-vectors--predicated---writing-multiplicand--Zdn---Za---Zdn---Zm--

When result is in a different register from op2 and op1, this intrinsic can use:

```asm
MOVPRFX Zresult.B, Pg/Z, Zop3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
MSB Zresult.B, Pg/M, Zop2.B, Zop1.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MSB--Multiply-subtract-vectors--predicated---writing-multiplicand--Zdn---Za---Zdn---Zm--

### Operation

Source operation ID: `SveOperation_svmls_n_u8_z`

**Operation**



Return a vector in which each active element *i* contains the value:



```text
op1[i] - op2[i] * op3
```



Set the inactive elements of the result to zero.

## svmls[_s16]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmls%5B_s16%5D_m

### Signature (source notation)

```c
svint16_t svmls[_s16]_m(svbool_t pg, svint16_t op1, svint16_t op2, svint16_t op3);
```

### Description

Multiply-subtract, minuend first

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
  },
  "op3": {
    "register": "Zop3.H"
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
MLS Ztied1.H, Pg/M, Zop2.H, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MLS--vectors---Multiply-subtract-vectors--predicated---writing-addend--Zda---Zda---Zn---Zm--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
MLS Zresult.H, Pg/M, Zop2.H, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MLS--vectors---Multiply-subtract-vectors--predicated---writing-addend--Zda---Zda---Zn---Zm--

### Operation

Source operation ID: `SveOperation_svmls_s8_m`

**Operation**



Return a vector in which each active element *i* contains the value:



```text
op1[i] - op2[i] * op3[i]
```



Take the inactive elements of the result from the corresponding elements of `op1`.



The operation uses modulo arithmetic.  The behavior is therefore defined for all inputs; unlike C, there is no undefined behavior for signed overflow.

## svmls[_s16]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmls%5B_s16%5D_x

### Signature (source notation)

```c
svint16_t svmls[_s16]_x(svbool_t pg, svint16_t op1, svint16_t op2, svint16_t op3);
```

### Description

Multiply-subtract, minuend first

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
  },
  "op3": {
    "register": "Zop3.H|Ztied3.H"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.H|Ztied1.H|Ztied2.H|Ztied3.H": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
MLS Ztied1.H, Pg/M, Zop2.H, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MLS--vectors---Multiply-subtract-vectors--predicated---writing-addend--Zda---Zda---Zn---Zm--

When result and op2 are in the same register, this intrinsic compiles to:

```asm
MSB Ztied2.H, Pg/M, Zop3.H, Zop1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MSB--Multiply-subtract-vectors--predicated---writing-multiplicand--Zdn---Za---Zdn---Zm--

When result and op3 are in the same register, this intrinsic compiles to:

```asm
MSB Ztied3.H, Pg/M, Zop2.H, Zop1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MSB--Multiply-subtract-vectors--predicated---writing-multiplicand--Zdn---Za---Zdn---Zm--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
MLS Zresult.H, Pg/M, Zop2.H, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MLS--vectors---Multiply-subtract-vectors--predicated---writing-addend--Zda---Zda---Zn---Zm--

### Operation

Source operation ID: `SveOperation_svmls_s8_x`

**Operation**



Return a vector in which each active element *i* contains the value:



```text
op1[i] - op2[i] * op3[i]
```



The inactive elements of the result have arbitrary, undefined values.



The operation uses modulo arithmetic.  The behavior is therefore defined for all inputs; unlike C, there is no undefined behavior for signed overflow.

## svmls[_s16]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmls%5B_s16%5D_z

### Signature (source notation)

```c
svint16_t svmls[_s16]_z(svbool_t pg, svint16_t op1, svint16_t op2, svint16_t op3);
```

### Description

Multiply-subtract, minuend first

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
  },
  "op3": {
    "register": "Zop3.H"
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

When result is in a different register from op2 and op3, this intrinsic can use:

```asm
MOVPRFX Zresult.H, Pg/Z, Zop1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
MLS Zresult.H, Pg/M, Zop2.H, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MLS--vectors---Multiply-subtract-vectors--predicated---writing-addend--Zda---Zda---Zn---Zm--

When result is in a different register from op3 and op1, this intrinsic can use:

```asm
MOVPRFX Zresult.H, Pg/Z, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
MSB Zresult.H, Pg/M, Zop3.H, Zop1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MSB--Multiply-subtract-vectors--predicated---writing-multiplicand--Zdn---Za---Zdn---Zm--

When result is in a different register from op2 and op1, this intrinsic can use:

```asm
MOVPRFX Zresult.H, Pg/Z, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
MSB Zresult.H, Pg/M, Zop2.H, Zop1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MSB--Multiply-subtract-vectors--predicated---writing-multiplicand--Zdn---Za---Zdn---Zm--

### Operation

Source operation ID: `SveOperation_svmls_s8_z`

**Operation**



Return a vector in which each active element *i* contains the value:



```text
op1[i] - op2[i] * op3[i]
```



Set the inactive elements of the result to zero.



The operation uses modulo arithmetic.  The behavior is therefore defined for all inputs; unlike C, there is no undefined behavior for signed overflow.

## svmls[_s32]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmls%5B_s32%5D_m

### Signature (source notation)

```c
svint32_t svmls[_s32]_m(svbool_t pg, svint32_t op1, svint32_t op2, svint32_t op3);
```

### Description

Multiply-subtract, minuend first

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
MLS Ztied1.S, Pg/M, Zop2.S, Zop3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MLS--vectors---Multiply-subtract-vectors--predicated---writing-addend--Zda---Zda---Zn---Zm--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
MLS Zresult.S, Pg/M, Zop2.S, Zop3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MLS--vectors---Multiply-subtract-vectors--predicated---writing-addend--Zda---Zda---Zn---Zm--

### Operation

Source operation ID: `SveOperation_svmls_s8_m`

**Operation**



Return a vector in which each active element *i* contains the value:



```text
op1[i] - op2[i] * op3[i]
```



Take the inactive elements of the result from the corresponding elements of `op1`.



The operation uses modulo arithmetic.  The behavior is therefore defined for all inputs; unlike C, there is no undefined behavior for signed overflow.

## svmls[_s32]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmls%5B_s32%5D_x

### Signature (source notation)

```c
svint32_t svmls[_s32]_x(svbool_t pg, svint32_t op1, svint32_t op2, svint32_t op3);
```

### Description

Multiply-subtract, minuend first

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
  },
  "op3": {
    "register": "Zop3.S|Ztied3.S"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.S|Ztied1.S|Ztied2.S|Ztied3.S": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
MLS Ztied1.S, Pg/M, Zop2.S, Zop3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MLS--vectors---Multiply-subtract-vectors--predicated---writing-addend--Zda---Zda---Zn---Zm--

When result and op2 are in the same register, this intrinsic compiles to:

```asm
MSB Ztied2.S, Pg/M, Zop3.S, Zop1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MSB--Multiply-subtract-vectors--predicated---writing-multiplicand--Zdn---Za---Zdn---Zm--

When result and op3 are in the same register, this intrinsic compiles to:

```asm
MSB Ztied3.S, Pg/M, Zop2.S, Zop1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MSB--Multiply-subtract-vectors--predicated---writing-multiplicand--Zdn---Za---Zdn---Zm--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
MLS Zresult.S, Pg/M, Zop2.S, Zop3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MLS--vectors---Multiply-subtract-vectors--predicated---writing-addend--Zda---Zda---Zn---Zm--

### Operation

Source operation ID: `SveOperation_svmls_s8_x`

**Operation**



Return a vector in which each active element *i* contains the value:



```text
op1[i] - op2[i] * op3[i]
```



The inactive elements of the result have arbitrary, undefined values.



The operation uses modulo arithmetic.  The behavior is therefore defined for all inputs; unlike C, there is no undefined behavior for signed overflow.

## svmls[_s32]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmls%5B_s32%5D_z

### Signature (source notation)

```c
svint32_t svmls[_s32]_z(svbool_t pg, svint32_t op1, svint32_t op2, svint32_t op3);
```

### Description

Multiply-subtract, minuend first

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
    "Zresult.S": "result"
  }
]
```

### Instruction mapping

When result is in a different register from op2 and op3, this intrinsic can use:

```asm
MOVPRFX Zresult.S, Pg/Z, Zop1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
MLS Zresult.S, Pg/M, Zop2.S, Zop3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MLS--vectors---Multiply-subtract-vectors--predicated---writing-addend--Zda---Zda---Zn---Zm--

When result is in a different register from op3 and op1, this intrinsic can use:

```asm
MOVPRFX Zresult.S, Pg/Z, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
MSB Zresult.S, Pg/M, Zop3.S, Zop1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MSB--Multiply-subtract-vectors--predicated---writing-multiplicand--Zdn---Za---Zdn---Zm--

When result is in a different register from op2 and op1, this intrinsic can use:

```asm
MOVPRFX Zresult.S, Pg/Z, Zop3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
MSB Zresult.S, Pg/M, Zop2.S, Zop1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MSB--Multiply-subtract-vectors--predicated---writing-multiplicand--Zdn---Za---Zdn---Zm--

### Operation

Source operation ID: `SveOperation_svmls_s8_z`

**Operation**



Return a vector in which each active element *i* contains the value:



```text
op1[i] - op2[i] * op3[i]
```



Set the inactive elements of the result to zero.



The operation uses modulo arithmetic.  The behavior is therefore defined for all inputs; unlike C, there is no undefined behavior for signed overflow.

## svmls[_s64]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmls%5B_s64%5D_m

### Signature (source notation)

```c
svint64_t svmls[_s64]_m(svbool_t pg, svint64_t op1, svint64_t op2, svint64_t op3);
```

### Description

Multiply-subtract, minuend first

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
MLS Ztied1.D, Pg/M, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MLS--vectors---Multiply-subtract-vectors--predicated---writing-addend--Zda---Zda---Zn---Zm--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
MLS Zresult.D, Pg/M, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MLS--vectors---Multiply-subtract-vectors--predicated---writing-addend--Zda---Zda---Zn---Zm--

### Operation

Source operation ID: `SveOperation_svmls_s8_m`

**Operation**



Return a vector in which each active element *i* contains the value:



```text
op1[i] - op2[i] * op3[i]
```



Take the inactive elements of the result from the corresponding elements of `op1`.



The operation uses modulo arithmetic.  The behavior is therefore defined for all inputs; unlike C, there is no undefined behavior for signed overflow.

## svmls[_s64]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmls%5B_s64%5D_x

### Signature (source notation)

```c
svint64_t svmls[_s64]_x(svbool_t pg, svint64_t op1, svint64_t op2, svint64_t op3);
```

### Description

Multiply-subtract, minuend first

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
  },
  "op3": {
    "register": "Zop3.D|Ztied3.D"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.D|Ztied1.D|Ztied2.D|Ztied3.D": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
MLS Ztied1.D, Pg/M, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MLS--vectors---Multiply-subtract-vectors--predicated---writing-addend--Zda---Zda---Zn---Zm--

When result and op2 are in the same register, this intrinsic compiles to:

```asm
MSB Ztied2.D, Pg/M, Zop3.D, Zop1.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MSB--Multiply-subtract-vectors--predicated---writing-multiplicand--Zdn---Za---Zdn---Zm--

When result and op3 are in the same register, this intrinsic compiles to:

```asm
MSB Ztied3.D, Pg/M, Zop2.D, Zop1.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MSB--Multiply-subtract-vectors--predicated---writing-multiplicand--Zdn---Za---Zdn---Zm--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
MLS Zresult.D, Pg/M, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MLS--vectors---Multiply-subtract-vectors--predicated---writing-addend--Zda---Zda---Zn---Zm--

### Operation

Source operation ID: `SveOperation_svmls_s8_x`

**Operation**



Return a vector in which each active element *i* contains the value:



```text
op1[i] - op2[i] * op3[i]
```



The inactive elements of the result have arbitrary, undefined values.



The operation uses modulo arithmetic.  The behavior is therefore defined for all inputs; unlike C, there is no undefined behavior for signed overflow.

## svmls[_s64]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmls%5B_s64%5D_z

### Signature (source notation)

```c
svint64_t svmls[_s64]_z(svbool_t pg, svint64_t op1, svint64_t op2, svint64_t op3);
```

### Description

Multiply-subtract, minuend first

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
MLS Zresult.D, Pg/M, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MLS--vectors---Multiply-subtract-vectors--predicated---writing-addend--Zda---Zda---Zn---Zm--

When result is in a different register from op3 and op1, this intrinsic can use:

```asm
MOVPRFX Zresult.D, Pg/Z, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
MSB Zresult.D, Pg/M, Zop3.D, Zop1.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MSB--Multiply-subtract-vectors--predicated---writing-multiplicand--Zdn---Za---Zdn---Zm--

When result is in a different register from op2 and op1, this intrinsic can use:

```asm
MOVPRFX Zresult.D, Pg/Z, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
MSB Zresult.D, Pg/M, Zop2.D, Zop1.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MSB--Multiply-subtract-vectors--predicated---writing-multiplicand--Zdn---Za---Zdn---Zm--

### Operation

Source operation ID: `SveOperation_svmls_s8_z`

**Operation**



Return a vector in which each active element *i* contains the value:



```text
op1[i] - op2[i] * op3[i]
```



Set the inactive elements of the result to zero.



The operation uses modulo arithmetic.  The behavior is therefore defined for all inputs; unlike C, there is no undefined behavior for signed overflow.

## svmls[_s8]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmls%5B_s8%5D_m

### Signature (source notation)

```c
svint8_t svmls[_s8]_m(svbool_t pg, svint8_t op1, svint8_t op2, svint8_t op3);
```

### Description

Multiply-subtract, minuend first

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
MLS Ztied1.B, Pg/M, Zop2.B, Zop3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MLS--vectors---Multiply-subtract-vectors--predicated---writing-addend--Zda---Zda---Zn---Zm--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
MLS Zresult.B, Pg/M, Zop2.B, Zop3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MLS--vectors---Multiply-subtract-vectors--predicated---writing-addend--Zda---Zda---Zn---Zm--

### Operation

Source operation ID: `SveOperation_svmls_s8_m`

**Operation**



Return a vector in which each active element *i* contains the value:



```text
op1[i] - op2[i] * op3[i]
```



Take the inactive elements of the result from the corresponding elements of `op1`.



The operation uses modulo arithmetic.  The behavior is therefore defined for all inputs; unlike C, there is no undefined behavior for signed overflow.

## svmls[_s8]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmls%5B_s8%5D_x

### Signature (source notation)

```c
svint8_t svmls[_s8]_x(svbool_t pg, svint8_t op1, svint8_t op2, svint8_t op3);
```

### Description

Multiply-subtract, minuend first

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
MLS Ztied1.B, Pg/M, Zop2.B, Zop3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MLS--vectors---Multiply-subtract-vectors--predicated---writing-addend--Zda---Zda---Zn---Zm--

When result and op2 are in the same register, this intrinsic compiles to:

```asm
MSB Ztied2.B, Pg/M, Zop3.B, Zop1.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MSB--Multiply-subtract-vectors--predicated---writing-multiplicand--Zdn---Za---Zdn---Zm--

When result and op3 are in the same register, this intrinsic compiles to:

```asm
MSB Ztied3.B, Pg/M, Zop2.B, Zop1.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MSB--Multiply-subtract-vectors--predicated---writing-multiplicand--Zdn---Za---Zdn---Zm--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
MLS Zresult.B, Pg/M, Zop2.B, Zop3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MLS--vectors---Multiply-subtract-vectors--predicated---writing-addend--Zda---Zda---Zn---Zm--

### Operation

Source operation ID: `SveOperation_svmls_s8_x`

**Operation**



Return a vector in which each active element *i* contains the value:



```text
op1[i] - op2[i] * op3[i]
```



The inactive elements of the result have arbitrary, undefined values.



The operation uses modulo arithmetic.  The behavior is therefore defined for all inputs; unlike C, there is no undefined behavior for signed overflow.

## svmls[_s8]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmls%5B_s8%5D_z

### Signature (source notation)

```c
svint8_t svmls[_s8]_z(svbool_t pg, svint8_t op1, svint8_t op2, svint8_t op3);
```

### Description

Multiply-subtract, minuend first

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
MLS Zresult.B, Pg/M, Zop2.B, Zop3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MLS--vectors---Multiply-subtract-vectors--predicated---writing-addend--Zda---Zda---Zn---Zm--

When result is in a different register from op3 and op1, this intrinsic can use:

```asm
MOVPRFX Zresult.B, Pg/Z, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
MSB Zresult.B, Pg/M, Zop3.B, Zop1.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MSB--Multiply-subtract-vectors--predicated---writing-multiplicand--Zdn---Za---Zdn---Zm--

When result is in a different register from op2 and op1, this intrinsic can use:

```asm
MOVPRFX Zresult.B, Pg/Z, Zop3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
MSB Zresult.B, Pg/M, Zop2.B, Zop1.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MSB--Multiply-subtract-vectors--predicated---writing-multiplicand--Zdn---Za---Zdn---Zm--

### Operation

Source operation ID: `SveOperation_svmls_s8_z`

**Operation**



Return a vector in which each active element *i* contains the value:



```text
op1[i] - op2[i] * op3[i]
```



Set the inactive elements of the result to zero.



The operation uses modulo arithmetic.  The behavior is therefore defined for all inputs; unlike C, there is no undefined behavior for signed overflow.

## svmls[_u16]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmls%5B_u16%5D_m

### Signature (source notation)

```c
svuint16_t svmls[_u16]_m(svbool_t pg, svuint16_t op1, svuint16_t op2, svuint16_t op3);
```

### Description

Multiply-subtract, minuend first

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
  },
  "op3": {
    "register": "Zop3.H"
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
MLS Ztied1.H, Pg/M, Zop2.H, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MLS--vectors---Multiply-subtract-vectors--predicated---writing-addend--Zda---Zda---Zn---Zm--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
MLS Zresult.H, Pg/M, Zop2.H, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MLS--vectors---Multiply-subtract-vectors--predicated---writing-addend--Zda---Zda---Zn---Zm--

### Operation

Source operation ID: `SveOperation_svmls_u8_m`

**Operation**



Return a vector in which each active element *i* contains the value:



```text
op1[i] - op2[i] * op3[i]
```



Take the inactive elements of the result from the corresponding elements of `op1`.

## svmls[_u16]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmls%5B_u16%5D_x

### Signature (source notation)

```c
svuint16_t svmls[_u16]_x(svbool_t pg, svuint16_t op1, svuint16_t op2, svuint16_t op3);
```

### Description

Multiply-subtract, minuend first

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
  },
  "op3": {
    "register": "Zop3.H|Ztied3.H"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.H|Ztied1.H|Ztied2.H|Ztied3.H": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
MLS Ztied1.H, Pg/M, Zop2.H, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MLS--vectors---Multiply-subtract-vectors--predicated---writing-addend--Zda---Zda---Zn---Zm--

When result and op2 are in the same register, this intrinsic compiles to:

```asm
MSB Ztied2.H, Pg/M, Zop3.H, Zop1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MSB--Multiply-subtract-vectors--predicated---writing-multiplicand--Zdn---Za---Zdn---Zm--

When result and op3 are in the same register, this intrinsic compiles to:

```asm
MSB Ztied3.H, Pg/M, Zop2.H, Zop1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MSB--Multiply-subtract-vectors--predicated---writing-multiplicand--Zdn---Za---Zdn---Zm--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
MLS Zresult.H, Pg/M, Zop2.H, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MLS--vectors---Multiply-subtract-vectors--predicated---writing-addend--Zda---Zda---Zn---Zm--

### Operation

Source operation ID: `SveOperation_svmls_u8_x`

**Operation**



Return a vector in which each active element *i* contains the value:



```text
op1[i] - op2[i] * op3[i]
```



The inactive elements of the result have arbitrary, undefined values.

## svmls[_u16]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmls%5B_u16%5D_z

### Signature (source notation)

```c
svuint16_t svmls[_u16]_z(svbool_t pg, svuint16_t op1, svuint16_t op2, svuint16_t op3);
```

### Description

Multiply-subtract, minuend first

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
  },
  "op3": {
    "register": "Zop3.H"
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

When result is in a different register from op2 and op3, this intrinsic can use:

```asm
MOVPRFX Zresult.H, Pg/Z, Zop1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
MLS Zresult.H, Pg/M, Zop2.H, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MLS--vectors---Multiply-subtract-vectors--predicated---writing-addend--Zda---Zda---Zn---Zm--

When result is in a different register from op3 and op1, this intrinsic can use:

```asm
MOVPRFX Zresult.H, Pg/Z, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
MSB Zresult.H, Pg/M, Zop3.H, Zop1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MSB--Multiply-subtract-vectors--predicated---writing-multiplicand--Zdn---Za---Zdn---Zm--

When result is in a different register from op2 and op1, this intrinsic can use:

```asm
MOVPRFX Zresult.H, Pg/Z, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
MSB Zresult.H, Pg/M, Zop2.H, Zop1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MSB--Multiply-subtract-vectors--predicated---writing-multiplicand--Zdn---Za---Zdn---Zm--

### Operation

Source operation ID: `SveOperation_svmls_u8_z`

**Operation**



Return a vector in which each active element *i* contains the value:



```text
op1[i] - op2[i] * op3[i]
```



Set the inactive elements of the result to zero.

## svmls[_u32]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmls%5B_u32%5D_m

### Signature (source notation)

```c
svuint32_t svmls[_u32]_m(svbool_t pg, svuint32_t op1, svuint32_t op2, svuint32_t op3);
```

### Description

Multiply-subtract, minuend first

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
MLS Ztied1.S, Pg/M, Zop2.S, Zop3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MLS--vectors---Multiply-subtract-vectors--predicated---writing-addend--Zda---Zda---Zn---Zm--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
MLS Zresult.S, Pg/M, Zop2.S, Zop3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MLS--vectors---Multiply-subtract-vectors--predicated---writing-addend--Zda---Zda---Zn---Zm--

### Operation

Source operation ID: `SveOperation_svmls_u8_m`

**Operation**



Return a vector in which each active element *i* contains the value:



```text
op1[i] - op2[i] * op3[i]
```



Take the inactive elements of the result from the corresponding elements of `op1`.

## svmls[_u32]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmls%5B_u32%5D_x

### Signature (source notation)

```c
svuint32_t svmls[_u32]_x(svbool_t pg, svuint32_t op1, svuint32_t op2, svuint32_t op3);
```

### Description

Multiply-subtract, minuend first

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
  },
  "op3": {
    "register": "Zop3.S|Ztied3.S"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.S|Ztied1.S|Ztied2.S|Ztied3.S": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
MLS Ztied1.S, Pg/M, Zop2.S, Zop3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MLS--vectors---Multiply-subtract-vectors--predicated---writing-addend--Zda---Zda---Zn---Zm--

When result and op2 are in the same register, this intrinsic compiles to:

```asm
MSB Ztied2.S, Pg/M, Zop3.S, Zop1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MSB--Multiply-subtract-vectors--predicated---writing-multiplicand--Zdn---Za---Zdn---Zm--

When result and op3 are in the same register, this intrinsic compiles to:

```asm
MSB Ztied3.S, Pg/M, Zop2.S, Zop1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MSB--Multiply-subtract-vectors--predicated---writing-multiplicand--Zdn---Za---Zdn---Zm--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
MLS Zresult.S, Pg/M, Zop2.S, Zop3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MLS--vectors---Multiply-subtract-vectors--predicated---writing-addend--Zda---Zda---Zn---Zm--

### Operation

Source operation ID: `SveOperation_svmls_u8_x`

**Operation**



Return a vector in which each active element *i* contains the value:



```text
op1[i] - op2[i] * op3[i]
```



The inactive elements of the result have arbitrary, undefined values.

## svmls[_u32]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmls%5B_u32%5D_z

### Signature (source notation)

```c
svuint32_t svmls[_u32]_z(svbool_t pg, svuint32_t op1, svuint32_t op2, svuint32_t op3);
```

### Description

Multiply-subtract, minuend first

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
    "Zresult.S": "result"
  }
]
```

### Instruction mapping

When result is in a different register from op2 and op3, this intrinsic can use:

```asm
MOVPRFX Zresult.S, Pg/Z, Zop1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
MLS Zresult.S, Pg/M, Zop2.S, Zop3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MLS--vectors---Multiply-subtract-vectors--predicated---writing-addend--Zda---Zda---Zn---Zm--

When result is in a different register from op3 and op1, this intrinsic can use:

```asm
MOVPRFX Zresult.S, Pg/Z, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
MSB Zresult.S, Pg/M, Zop3.S, Zop1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MSB--Multiply-subtract-vectors--predicated---writing-multiplicand--Zdn---Za---Zdn---Zm--

When result is in a different register from op2 and op1, this intrinsic can use:

```asm
MOVPRFX Zresult.S, Pg/Z, Zop3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
MSB Zresult.S, Pg/M, Zop2.S, Zop1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MSB--Multiply-subtract-vectors--predicated---writing-multiplicand--Zdn---Za---Zdn---Zm--

### Operation

Source operation ID: `SveOperation_svmls_u8_z`

**Operation**



Return a vector in which each active element *i* contains the value:



```text
op1[i] - op2[i] * op3[i]
```



Set the inactive elements of the result to zero.

## svmls[_u64]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmls%5B_u64%5D_m

### Signature (source notation)

```c
svuint64_t svmls[_u64]_m(svbool_t pg, svuint64_t op1, svuint64_t op2, svuint64_t op3);
```

### Description

Multiply-subtract, minuend first

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
MLS Ztied1.D, Pg/M, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MLS--vectors---Multiply-subtract-vectors--predicated---writing-addend--Zda---Zda---Zn---Zm--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
MLS Zresult.D, Pg/M, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MLS--vectors---Multiply-subtract-vectors--predicated---writing-addend--Zda---Zda---Zn---Zm--

### Operation

Source operation ID: `SveOperation_svmls_u8_m`

**Operation**



Return a vector in which each active element *i* contains the value:



```text
op1[i] - op2[i] * op3[i]
```



Take the inactive elements of the result from the corresponding elements of `op1`.

## svmls[_u64]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmls%5B_u64%5D_x

### Signature (source notation)

```c
svuint64_t svmls[_u64]_x(svbool_t pg, svuint64_t op1, svuint64_t op2, svuint64_t op3);
```

### Description

Multiply-subtract, minuend first

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
    "register": "Zop1.D|Ztied1.D"
  },
  "op2": {
    "register": "Zop2.D|Ztied2.D"
  },
  "op3": {
    "register": "Zop3.D|Ztied3.D"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.D|Ztied1.D|Ztied2.D|Ztied3.D": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
MLS Ztied1.D, Pg/M, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MLS--vectors---Multiply-subtract-vectors--predicated---writing-addend--Zda---Zda---Zn---Zm--

When result and op2 are in the same register, this intrinsic compiles to:

```asm
MSB Ztied2.D, Pg/M, Zop3.D, Zop1.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MSB--Multiply-subtract-vectors--predicated---writing-multiplicand--Zdn---Za---Zdn---Zm--

When result and op3 are in the same register, this intrinsic compiles to:

```asm
MSB Ztied3.D, Pg/M, Zop2.D, Zop1.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MSB--Multiply-subtract-vectors--predicated---writing-multiplicand--Zdn---Za---Zdn---Zm--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
MLS Zresult.D, Pg/M, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MLS--vectors---Multiply-subtract-vectors--predicated---writing-addend--Zda---Zda---Zn---Zm--

### Operation

Source operation ID: `SveOperation_svmls_u8_x`

**Operation**



Return a vector in which each active element *i* contains the value:



```text
op1[i] - op2[i] * op3[i]
```



The inactive elements of the result have arbitrary, undefined values.

## svmls[_u64]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmls%5B_u64%5D_z

### Signature (source notation)

```c
svuint64_t svmls[_u64]_z(svbool_t pg, svuint64_t op1, svuint64_t op2, svuint64_t op3);
```

### Description

Multiply-subtract, minuend first

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
MLS Zresult.D, Pg/M, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MLS--vectors---Multiply-subtract-vectors--predicated---writing-addend--Zda---Zda---Zn---Zm--

When result is in a different register from op3 and op1, this intrinsic can use:

```asm
MOVPRFX Zresult.D, Pg/Z, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
MSB Zresult.D, Pg/M, Zop3.D, Zop1.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MSB--Multiply-subtract-vectors--predicated---writing-multiplicand--Zdn---Za---Zdn---Zm--

When result is in a different register from op2 and op1, this intrinsic can use:

```asm
MOVPRFX Zresult.D, Pg/Z, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
MSB Zresult.D, Pg/M, Zop2.D, Zop1.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MSB--Multiply-subtract-vectors--predicated---writing-multiplicand--Zdn---Za---Zdn---Zm--

### Operation

Source operation ID: `SveOperation_svmls_u8_z`

**Operation**



Return a vector in which each active element *i* contains the value:



```text
op1[i] - op2[i] * op3[i]
```



Set the inactive elements of the result to zero.

## svmls[_u8]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmls%5B_u8%5D_m

### Signature (source notation)

```c
svuint8_t svmls[_u8]_m(svbool_t pg, svuint8_t op1, svuint8_t op2, svuint8_t op3);
```

### Description

Multiply-subtract, minuend first

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
MLS Ztied1.B, Pg/M, Zop2.B, Zop3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MLS--vectors---Multiply-subtract-vectors--predicated---writing-addend--Zda---Zda---Zn---Zm--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
MLS Zresult.B, Pg/M, Zop2.B, Zop3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MLS--vectors---Multiply-subtract-vectors--predicated---writing-addend--Zda---Zda---Zn---Zm--

### Operation

Source operation ID: `SveOperation_svmls_u8_m`

**Operation**



Return a vector in which each active element *i* contains the value:



```text
op1[i] - op2[i] * op3[i]
```



Take the inactive elements of the result from the corresponding elements of `op1`.

## svmls[_u8]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmls%5B_u8%5D_x

### Signature (source notation)

```c
svuint8_t svmls[_u8]_x(svbool_t pg, svuint8_t op1, svuint8_t op2, svuint8_t op3);
```

### Description

Multiply-subtract, minuend first

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
MLS Ztied1.B, Pg/M, Zop2.B, Zop3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MLS--vectors---Multiply-subtract-vectors--predicated---writing-addend--Zda---Zda---Zn---Zm--

When result and op2 are in the same register, this intrinsic compiles to:

```asm
MSB Ztied2.B, Pg/M, Zop3.B, Zop1.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MSB--Multiply-subtract-vectors--predicated---writing-multiplicand--Zdn---Za---Zdn---Zm--

When result and op3 are in the same register, this intrinsic compiles to:

```asm
MSB Ztied3.B, Pg/M, Zop2.B, Zop1.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MSB--Multiply-subtract-vectors--predicated---writing-multiplicand--Zdn---Za---Zdn---Zm--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
MLS Zresult.B, Pg/M, Zop2.B, Zop3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MLS--vectors---Multiply-subtract-vectors--predicated---writing-addend--Zda---Zda---Zn---Zm--

### Operation

Source operation ID: `SveOperation_svmls_u8_x`

**Operation**



Return a vector in which each active element *i* contains the value:



```text
op1[i] - op2[i] * op3[i]
```



The inactive elements of the result have arbitrary, undefined values.

## svmls[_u8]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmls%5B_u8%5D_z

### Signature (source notation)

```c
svuint8_t svmls[_u8]_z(svbool_t pg, svuint8_t op1, svuint8_t op2, svuint8_t op3);
```

### Description

Multiply-subtract, minuend first

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
MLS Zresult.B, Pg/M, Zop2.B, Zop3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MLS--vectors---Multiply-subtract-vectors--predicated---writing-addend--Zda---Zda---Zn---Zm--

When result is in a different register from op3 and op1, this intrinsic can use:

```asm
MOVPRFX Zresult.B, Pg/Z, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
MSB Zresult.B, Pg/M, Zop3.B, Zop1.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MSB--Multiply-subtract-vectors--predicated---writing-multiplicand--Zdn---Za---Zdn---Zm--

When result is in a different register from op2 and op1, this intrinsic can use:

```asm
MOVPRFX Zresult.B, Pg/Z, Zop3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
MSB Zresult.B, Pg/M, Zop2.B, Zop1.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MSB--Multiply-subtract-vectors--predicated---writing-multiplicand--Zdn---Za---Zdn---Zm--

### Operation

Source operation ID: `SveOperation_svmls_u8_z`

**Operation**



Return a vector in which each active element *i* contains the value:



```text
op1[i] - op2[i] * op3[i]
```



Set the inactive elements of the result to zero.

