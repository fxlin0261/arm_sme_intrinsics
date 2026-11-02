# SME / Vector arithmetic / Dot product — Part 1

## svbfdot[_f32]

ISA classification: SME + FEAT_BF16

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svbfdot%5B_f32%5D

### Signature (source notation)

```c
svfloat32_t svbfdot[_f32](svfloat32_t op1, svbfloat16_t op2, svbfloat16_t op3);
```

### Description

BFloat16 dot product

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Dot product

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME,FEAT_BF16
```

### Return type metadata

```json
{
  "return_base_type": "float",
  "element_bit_size": "32",
  "value": "svfloat32_t"
}
```

### Argument preparation and constraints

```json
{
  "op1": {
    "register": "Zop1.S|Ztied1.S"
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
    "Zresult.S|Ztied1.S": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
BFDOT Ztied1.S, Zop2.H, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BFDOT--vectors---BFloat16-dot-product-to-single-precision-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
BFDOT Zresult.S, Zop2.H, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BFDOT--vectors---BFloat16-dot-product-to-single-precision-

### Operation

Source operation ID: `SveOperation_svbfdot_f32`

**Operation**



Return a vector in which element *i* contains:



```text
op2[i * 2] * op3[i * 2]
+ op2[i * 2 + 1] * op3[i * 2 + 1]
+ op1[i]
```



**Exceptions**



The arithmetic ignores the FPCR and does not raise any exceptions; see [BFDOT (vectors)](https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/BFDOT--vectors---BFloat16-floating-point-dot-product-) for details.

## svbfdot[_n_f32]

ISA classification: SME + FEAT_BF16

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svbfdot%5B_n_f32%5D

### Signature (source notation)

```c
svfloat32_t svbfdot[_n_f32](svfloat32_t op1, svbfloat16_t op2, bfloat16_t op3);
```

### Description

BFloat16 dot product

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Dot product

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME,FEAT_BF16
```

### Return type metadata

```json
{
  "return_base_type": "float",
  "element_bit_size": "32",
  "value": "svfloat32_t"
}
```

### Argument preparation and constraints

```json
{
  "op1": {
    "register": "Zop1.S|Ztied1.S"
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
    "Zresult.S|Ztied1.S": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
BFDOT Ztied1.S, Zop2.H, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BFDOT--vectors---BFloat16-dot-product-to-single-precision-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
BFDOT Zresult.S, Zop2.H, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BFDOT--vectors---BFloat16-dot-product-to-single-precision-

### Operation

Source operation ID: `SveOperation_svbfdot_n_f32`

**Operation**



Return a vector in which element *i* contains:



```text
op2[i * 2] * op3
+ op2[i * 2 + 1] * op3
+ op1[i]
```



**Exceptions**



The arithmetic ignores the FPCR and does not raise any exceptions; see [BFDOT (vectors)](https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/BFDOT--vectors---BFloat16-floating-point-dot-product-) for details.

## svbfdot_lane[_f32]

ISA classification: SME + FEAT_BF16

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svbfdot_lane%5B_f32%5D

### Signature (source notation)

```c
svfloat32_t svbfdot_lane[_f32](svfloat32_t op1, svbfloat16_t op2, svbfloat16_t op3, uint64_t imm_index);
```

### Description

BFloat16 dot product

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Dot product

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME,FEAT_BF16
```

### Return type metadata

```json
{
  "return_base_type": "float",
  "element_bit_size": "32",
  "value": "svfloat32_t"
}
```

### Argument preparation and constraints

```json
{
  "op1": {
    "register": "Zop1.S|Ztied1.S"
  },
  "op2": {
    "register": "Zop2.H"
  },
  "op3": {
    "register": "Zop3.H"
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
BFDOT Ztied1.S, Zop2.H, Zop3.H[imm_index]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BFDOT--indexed---BFloat16-indexed-dot-product-to-single-precision-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
BFDOT Zresult.S, Zop2.H, Zop3.H[imm_index]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BFDOT--indexed---BFloat16-indexed-dot-product-to-single-precision-

### Operation

Source operation ID: `SveOperation_svbfdot_lane_f32`

**Operation**



Return a vector in which element *i* contains:



```text
op2[i * 2] * op3[base + imm_index * 2]
+ op2[i * 2 + 1] * op3[base + imm_index * 2 + 1]
+ op1[i]
```



where `op3[base]` is the first element in the same 128-bit quadword as `op3[i * 2]`.



**Exceptions**



The arithmetic ignores the FPCR and does not raise any exceptions; see [BFDOT (vectors)](https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/BFDOT--vectors---BFloat16-floating-point-dot-product-) for details.

## svdot[_f32_f16]

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdot%5B_f32_f16%5D

### Signature (source notation)

```c
svfloat32_t svdot[_f32_f16](svfloat32_t zda, svfloat16_t zn, svfloat16_t zm);
```

### Description

Half-precision dot product to single-precision

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Dot product

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p1)|FEAT_SME2
```

### Return type metadata

```json
{
  "return_base_type": "float32",
  "element_bit_size": "32",
  "value": "svfloat32_t"
}
```

### Argument preparation and constraints

```json
{
  "zda": {
    "register": "Zreg1.S"
  },
  "zn": {
    "register": "Zreg2.H"
  },
  "zm": {
    "register": "Zreg3.H"
  }
}
```

### Result mapping

```json
[
  {
    "Zreg1.S": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
FDOT Zreg1.S, Zreg2.H, Zreg3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FDOT--2-way--vectors--FP16-to-FP32---Half-precision-dot-product-to-single-precision-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svdot[_n_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdot%5B_n_s32%5D

### Signature (source notation)

```c
svint32_t svdot[_n_s32](svint32_t op1, svint8_t op2, int8_t op3);
```

### Description

Dot product

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Dot product

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
  "op1": {
    "register": "Zop1.S|Ztied1.S"
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
    "Zresult.S|Ztied1.S": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
SDOT Ztied1.S, Zop2.B, Zop3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SDOT--2-way--vectors---Signed-integer-dot-product-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SDOT Zresult.S, Zop2.B, Zop3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SDOT--2-way--vectors---Signed-integer-dot-product-

### Operation

Source operation ID: `SveOperation_svdot_n_s32`

**Operation**



Return a vector in which the value of element *i* contains:



```text
(int32_t)op2[i * 4 + 0] * (int32_t)op3
+ (int32_t)op2[i * 4 + 1] * (int32_t)op3
+ (int32_t)op2[i * 4 + 2] * (int32_t)op3
+ (int32_t)op2[i * 4 + 3] * (int32_t)op3
+ op1[i]
```



The operation uses modulo arithmetic.  The behavior is therefore defined for all inputs; unlike C, there is no undefined behavior for signed overflow.

## svdot[_n_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdot%5B_n_s64%5D

### Signature (source notation)

```c
svint64_t svdot[_n_s64](svint64_t op1, svint16_t op2, int16_t op3);
```

### Description

Dot product

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Dot product

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
  "op1": {
    "register": "Zop1.D|Ztied1.D"
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
    "Zresult.D|Ztied1.D": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
SDOT Ztied1.D, Zop2.H, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SDOT--2-way--vectors---Signed-integer-dot-product-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SDOT Zresult.D, Zop2.H, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SDOT--2-way--vectors---Signed-integer-dot-product-

### Operation

Source operation ID: `SveOperation_svdot_n_s64`

**Operation**



Return a vector in which the value of element *i* contains:



```text
(int64_t)op2[i * 4 + 0] * (int64_t)op3
+ (int64_t)op2[i * 4 + 1] * (int64_t)op3
+ (int64_t)op2[i * 4 + 2] * (int64_t)op3
+ (int64_t)op2[i * 4 + 3] * (int64_t)op3
+ op1[i]
```



The operation uses modulo arithmetic.  The behavior is therefore defined for all inputs; unlike C, there is no undefined behavior for signed overflow.

## svdot[_n_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdot%5B_n_u32%5D

### Signature (source notation)

```c
svuint32_t svdot[_n_u32](svuint32_t op1, svuint8_t op2, uint8_t op3);
```

### Description

Dot product

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Dot product

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
    "Zresult.S|Ztied1.S": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
UDOT Ztied1.S, Zop2.B, Zop3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UDOT--4-way--vectors---Unsigned-integer-dot-product-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
UDOT Zresult.S, Zop2.B, Zop3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UDOT--4-way--vectors---Unsigned-integer-dot-product-

### Operation

Source operation ID: `SveOperation_svdot_n_u32`

**Operation**



Return a vector in which the value of element *i* contains:



```text
(uint32_t)op2[i * 4 + 0] * (uint32_t)op3
+ (uint32_t)op2[i * 4 + 1] * (uint32_t)op3
+ (uint32_t)op2[i * 4 + 2] * (uint32_t)op3
+ (uint32_t)op2[i * 4 + 3] * (uint32_t)op3
+ op1[i]
```

## svdot[_n_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdot%5B_n_u64%5D

### Signature (source notation)

```c
svuint64_t svdot[_n_u64](svuint64_t op1, svuint16_t op2, uint16_t op3);
```

### Description

Dot product

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Dot product

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
    "Zresult.D|Ztied1.D": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
UDOT Ztied1.D, Zop2.H, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UDOT--4-way--vectors---Unsigned-integer-dot-product-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
UDOT Zresult.D, Zop2.H, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UDOT--4-way--vectors---Unsigned-integer-dot-product-

### Operation

Source operation ID: `SveOperation_svdot_n_u64`

**Operation**



Return a vector in which the value of element *i* contains:



```text
(uint64_t)op2[i * 4 + 0] * (uint64_t)op3
+ (uint64_t)op2[i * 4 + 1] * (uint64_t)op3
+ (uint64_t)op2[i * 4 + 2] * (uint64_t)op3
+ (uint64_t)op2[i * 4 + 3] * (uint64_t)op3
+ op1[i]
```

## svdot[_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdot%5B_s32%5D

### Signature (source notation)

```c
svint32_t svdot[_s32](svint32_t op1, svint8_t op2, svint8_t op3);
```

### Description

Dot product

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Dot product

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
  "op1": {
    "register": "Zop1.S|Ztied1.S"
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
    "Zresult.S|Ztied1.S": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
SDOT Ztied1.S, Zop2.B, Zop3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SDOT--2-way--vectors---Signed-integer-dot-product-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SDOT Zresult.S, Zop2.B, Zop3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SDOT--2-way--vectors---Signed-integer-dot-product-

### Operation

Source operation ID: `SveOperation_svdot_s32`

**Operation**



Return a vector in which the value of element *i* contains:



```text
(int32_t)op2[i * 4 + 0] * (int32_t)op3[i * 4 + 0]
+ (int32_t)op2[i * 4 + 1] * (int32_t)op3[i * 4 + 1]
+ (int32_t)op2[i * 4 + 2] * (int32_t)op3[i * 4 + 2]
+ (int32_t)op2[i * 4 + 3] * (int32_t)op3[i * 4 + 3]
+ op1[i]
```



The operation uses modulo arithmetic.  The behavior is therefore defined for all inputs; unlike C, there is no undefined behavior for signed overflow.

## svdot[_s32_s16]

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdot%5B_s32_s16%5D

### Signature (source notation)

```c
svint32_t svdot[_s32_s16](svint32_t zda, svint16_t zn, svint16_t zm);
```

### Description

Signed integer dot product

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Dot product

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p1)|FEAT_SME2
```

### Return type metadata

```json
{
  "return_base_type": "int32",
  "element_bit_size": "32",
  "value": "svint32_t"
}
```

### Argument preparation and constraints

```json
{
  "zda": {
    "register": "Zreg1.S"
  },
  "zn": {
    "register": "Zreg2.H"
  },
  "zm": {
    "register": "Zreg3.H"
  }
}
```

### Result mapping

```json
[
  {
    "Zreg1.S": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
SDOT Zreg1.S, Zreg2.H, Zreg3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SDOT--2-way--vectors---Signed-integer-dot-product-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svdot[_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdot%5B_s64%5D

### Signature (source notation)

```c
svint64_t svdot[_s64](svint64_t op1, svint16_t op2, svint16_t op3);
```

### Description

Dot product

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Dot product

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
  "op1": {
    "register": "Zop1.D|Ztied1.D"
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
    "Zresult.D|Ztied1.D": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
SDOT Ztied1.D, Zop2.H, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SDOT--2-way--vectors---Signed-integer-dot-product-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SDOT Zresult.D, Zop2.H, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SDOT--2-way--vectors---Signed-integer-dot-product-

### Operation

Source operation ID: `SveOperation_svdot_s64`

**Operation**



Return a vector in which the value of element *i* contains:



```text
(int64_t)op2[i * 4 + 0] * (int64_t)op3[i * 4 + 0]
+ (int64_t)op2[i * 4 + 1] * (int64_t)op3[i * 4 + 1]
+ (int64_t)op2[i * 4 + 2] * (int64_t)op3[i * 4 + 2]
+ (int64_t)op2[i * 4 + 3] * (int64_t)op3[i * 4 + 3]
+ op1[i]
```



The operation uses modulo arithmetic.  The behavior is therefore defined for all inputs; unlike C, there is no undefined behavior for signed overflow.

## svdot[_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdot%5B_u32%5D

### Signature (source notation)

```c
svuint32_t svdot[_u32](svuint32_t op1, svuint8_t op2, svuint8_t op3);
```

### Description

Dot product

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Dot product

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
    "Zresult.S|Ztied1.S": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
UDOT Ztied1.S, Zop2.B, Zop3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UDOT--4-way--vectors---Unsigned-integer-dot-product-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
UDOT Zresult.S, Zop2.B, Zop3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UDOT--4-way--vectors---Unsigned-integer-dot-product-

### Operation

Source operation ID: `SveOperation_svdot_u32`

**Operation**



Return a vector in which the value of element *i* contains:



```text
(uint32_t)op2[i * 4 + 0] * (uint32_t)op3[i * 4 + 0]
+ (uint32_t)op2[i * 4 + 1] * (uint32_t)op3[i * 4 + 1]
+ (uint32_t)op2[i * 4 + 2] * (uint32_t)op3[i * 4 + 2]
+ (uint32_t)op2[i * 4 + 3] * (uint32_t)op3[i * 4 + 3]
+ op1[i]
```

## svdot[_u32_u16]

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdot%5B_u32_u16%5D

### Signature (source notation)

```c
svuint32_t svdot[_u32_u16](svuint32_t zda, svuint16_t zn, svuint16_t zm);
```

### Description

Unsigned integer dot product

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Dot product

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p1)|FEAT_SME2
```

### Return type metadata

```json
{
  "return_base_type": "uint32",
  "element_bit_size": "32",
  "value": "svuint32_t"
}
```

### Argument preparation and constraints

```json
{
  "zda": {
    "register": "Zreg1.S"
  },
  "zn": {
    "register": "Zreg2.H"
  },
  "zm": {
    "register": "Zreg3.H"
  }
}
```

### Result mapping

```json
[
  {
    "Zreg1.S": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
UDOT Zreg1.S, Zreg2.H, Zreg3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UDOT--2-way--vectors---Unsigned-integer-dot-product-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svdot[_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdot%5B_u64%5D

### Signature (source notation)

```c
svuint64_t svdot[_u64](svuint64_t op1, svuint16_t op2, svuint16_t op3);
```

### Description

Dot product

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Dot product

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
    "Zresult.D|Ztied1.D": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
UDOT Ztied1.D, Zop2.H, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UDOT--4-way--vectors---Unsigned-integer-dot-product-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
UDOT Zresult.D, Zop2.H, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UDOT--4-way--vectors---Unsigned-integer-dot-product-

### Operation

Source operation ID: `SveOperation_svdot_u64`

**Operation**



Return a vector in which the value of element *i* contains:



```text
(uint64_t)op2[i * 4 + 0] * (uint64_t)op3[i * 4 + 0]
+ (uint64_t)op2[i * 4 + 1] * (uint64_t)op3[i * 4 + 1]
+ (uint64_t)op2[i * 4 + 2] * (uint64_t)op3[i * 4 + 2]
+ (uint64_t)op2[i * 4 + 3] * (uint64_t)op3[i * 4 + 3]
+ op1[i]
```

## svdot_lane[_f32_f16]

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdot_lane%5B_f32_f16%5D

### Signature (source notation)

```c
svfloat32_t svdot_lane[_f32_f16](svfloat32_t zda, svfloat16_t zn, svfloat16_t zm, uint64_t imm_idx);
```

### Description

Half-precision indexed dot product to single-precision

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Dot product

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p1)|FEAT_SME2
```

### Return type metadata

```json
{
  "return_base_type": "float32",
  "element_bit_size": "32",
  "value": "svfloat32_t"
}
```

### Argument preparation and constraints

```json
{
  "zda": {
    "register": "Zreg1.S"
  },
  "zn": {
    "register": "Zreg2.H"
  },
  "zm": {
    "register": "Zreg3.H"
  },
  "imm_idx": {
    "immediate": "imm1"
  }
}
```

### Result mapping

```json
[
  {
    "Zreg1.S": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
FDOT Zreg1.S, Zreg2.H, Zreg3.H[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FDOT--2-way--indexed--FP16-to-FP32---Half-precision-indexed-dot-product-to-single-precision-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svdot_lane[_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdot_lane%5B_s32%5D

### Signature (source notation)

```c
svint32_t svdot_lane[_s32](svint32_t op1, svint8_t op2, svint8_t op3, uint64_t imm_index);
```

### Description

Dot product

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Dot product

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
  "op1": {
    "register": "Zop1.S|Ztied1.S"
  },
  "op2": {
    "register": "Zop2.B"
  },
  "op3": {
    "register": "Zop3.B"
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
SDOT Ztied1.S, Zop2.B, Zop3.B[imm_index]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SDOT--2-way--indexed---Signed-integer-indexed-dot-product-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SDOT Zresult.S, Zop2.B, Zop3.B[imm_index]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SDOT--2-way--indexed---Signed-integer-indexed-dot-product-

### Operation

Source operation ID: `SveOperation_svdot_lane_s32`

**Operation**



Return a vector in which the value of element *i* contains:



```text
(int32_t)op2[i * 4 + 0] * (int32_t)op3[base + imm_index * 4 + 0]
+ (int32_t)op2[i * 4 + 1] * (int32_t)op3[base + imm_index * 4 + 1]
+ (int32_t)op2[i * 4 + 2] * (int32_t)op3[base + imm_index * 4 + 2]
+ (int32_t)op2[i * 4 + 3] * (int32_t)op3[base + imm_index * 4 + 3]
+ op1[i]
```



where `op3[base]` is the first element in the same 128-bit quadword as `op3[i * 4]`.



The operation uses modulo arithmetic.  The behavior is therefore defined for all inputs; unlike C, there is no undefined behavior for signed overflow.

## svdot_lane[_s32_s16]

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdot_lane%5B_s32_s16%5D

### Signature (source notation)

```c
svint32_t svdot_lane[_s32_s16](svint32_t zda, svint16_t zn, svint16_t zm, uint64_t imm_idx);
```

### Description

Signed integer indexed dot product

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Dot product

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p1)|FEAT_SME2
```

### Return type metadata

```json
{
  "return_base_type": "int32",
  "element_bit_size": "32",
  "value": "svint32_t"
}
```

### Argument preparation and constraints

```json
{
  "zda": {
    "register": "Zreg1.S"
  },
  "zn": {
    "register": "Zreg2.H"
  },
  "zm": {
    "register": "Zreg3.H"
  },
  "imm_idx": {
    "immediate": "imm1"
  }
}
```

### Result mapping

```json
[
  {
    "Zreg1.S": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
SDOT Zreg1.S, Zreg2.H, Zreg3.H[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SDOT--2-way--indexed---Signed-integer-indexed-dot-product-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svdot_lane[_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdot_lane%5B_s64%5D

### Signature (source notation)

```c
svint64_t svdot_lane[_s64](svint64_t op1, svint16_t op2, svint16_t op3, uint64_t imm_index);
```

### Description

Dot product

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Dot product

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
  "op1": {
    "register": "Zop1.D|Ztied1.D"
  },
  "op2": {
    "register": "Zop2.H"
  },
  "op3": {
    "register": "Zop3.H"
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
SDOT Ztied1.D, Zop2.H, Zop3.H[imm_index]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SDOT--2-way--indexed---Signed-integer-indexed-dot-product-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SDOT Zresult.D, Zop2.H, Zop3.H[imm_index]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SDOT--2-way--indexed---Signed-integer-indexed-dot-product-

### Operation

Source operation ID: `SveOperation_svdot_lane_s64`

**Operation**



Return a vector in which the value of element *i* contains:



```text
(int64_t)op2[i * 4 + 0] * (int64_t)op3[base + imm_index * 4 + 0]
+ (int64_t)op2[i * 4 + 1] * (int64_t)op3[base + imm_index * 4 + 1]
+ (int64_t)op2[i * 4 + 2] * (int64_t)op3[base + imm_index * 4 + 2]
+ (int64_t)op2[i * 4 + 3] * (int64_t)op3[base + imm_index * 4 + 3]
+ op1[i]
```



where `op3[base]` is the first element in the same 128-bit quadword as `op3[i * 4]`.



The operation uses modulo arithmetic.  The behavior is therefore defined for all inputs; unlike C, there is no undefined behavior for signed overflow.

## svdot_lane[_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdot_lane%5B_u32%5D

### Signature (source notation)

```c
svuint32_t svdot_lane[_u32](svuint32_t op1, svuint8_t op2, svuint8_t op3, uint64_t imm_index);
```

### Description

Dot product

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Dot product

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
    "register": "Zop2.B"
  },
  "op3": {
    "register": "Zop3.B"
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
UDOT Ztied1.S, Zop2.B, Zop3.B[imm_index]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UDOT--4-way--indexed---Unsigned-integer-indexed-dot-product-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
UDOT Zresult.S, Zop2.B, Zop3.B[imm_index]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UDOT--4-way--indexed---Unsigned-integer-indexed-dot-product-

### Operation

Source operation ID: `SveOperation_svdot_lane_u32`

**Operation**



Return a vector in which the value of element *i* contains:



```text
(uint32_t)op2[i * 4 + 0] * (uint32_t)op3[base + imm_index * 4 + 0]
+ (uint32_t)op2[i * 4 + 1] * (uint32_t)op3[base + imm_index * 4 + 1]
+ (uint32_t)op2[i * 4 + 2] * (uint32_t)op3[base + imm_index * 4 + 2]
+ (uint32_t)op2[i * 4 + 3] * (uint32_t)op3[base + imm_index * 4 + 3]
+ op1[i]
```



where `op3[base]` is the first element in the same 128-bit quadword as `op3[i * 4]`.

## svdot_lane[_u32_u16]

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdot_lane%5B_u32_u16%5D

### Signature (source notation)

```c
svuint32_t svdot_lane[_u32_u16](svuint32_t zda, svuint16_t zn, svuint16_t zm, uint64_t imm_idx);
```

### Description

Unsigned integer indexed dot product

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Dot product

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p1)|FEAT_SME2
```

### Return type metadata

```json
{
  "return_base_type": "uint32",
  "element_bit_size": "32",
  "value": "svuint32_t"
}
```

### Argument preparation and constraints

```json
{
  "zda": {
    "register": "Zreg1.S"
  },
  "zn": {
    "register": "Zreg2.H"
  },
  "zm": {
    "register": "Zreg3.H"
  },
  "imm_idx": {
    "immediate": "imm1"
  }
}
```

### Result mapping

```json
[
  {
    "Zreg1.S": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
UDOT Zreg1.S, Zreg2.H, Zreg3.H[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UDOT--2-way--indexed---Unsigned-integer-indexed-dot-product-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svdot_lane[_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdot_lane%5B_u64%5D

### Signature (source notation)

```c
svuint64_t svdot_lane[_u64](svuint64_t op1, svuint16_t op2, svuint16_t op3, uint64_t imm_index);
```

### Description

Dot product

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Dot product

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
    "register": "Zop2.H"
  },
  "op3": {
    "register": "Zop3.H"
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
UDOT Ztied1.D, Zop2.H, Zop3.H[imm_index]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UDOT--4-way--indexed---Unsigned-integer-indexed-dot-product-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
UDOT Zresult.D, Zop2.H, Zop3.H[imm_index]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UDOT--4-way--indexed---Unsigned-integer-indexed-dot-product-

### Operation

Source operation ID: `SveOperation_svdot_lane_u64`

**Operation**



Return a vector in which the value of element *i* contains:



```text
(uint64_t)op2[i * 4 + 0] * (uint64_t)op3[base + imm_index * 4 + 0]
+ (uint64_t)op2[i * 4 + 1] * (uint64_t)op3[base + imm_index * 4 + 1]
+ (uint64_t)op2[i * 4 + 2] * (uint64_t)op3[base + imm_index * 4 + 2]
+ (uint64_t)op2[i * 4 + 3] * (uint64_t)op3[base + imm_index * 4 + 3]
+ op1[i]
```



where `op3[base]` is the first element in the same 128-bit quadword as `op3[i * 4]`.

## svsudot[_n_s32]

ISA classification: SME + FEAT_I8MM

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsudot%5B_n_s32%5D

### Signature (source notation)

```c
svint32_t svsudot[_n_s32](svint32_t op1, svint8_t op2, uint8_t op3);
```

### Description

Dot product (signed × unsigned)

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Dot product

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME,FEAT_I8MM
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
  "op1": {
    "register": "Zop1.S|Ztied1.S"
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
    "Zresult.S|Ztied1.S": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
USDOT Ztied1.S, Zop3.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/USDOT--vectors---Unsigned-by-signed-8-bit-integer-dot-product-to-32-bit-integer-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
USDOT Zresult.S, Zop3.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/USDOT--vectors---Unsigned-by-signed-8-bit-integer-dot-product-to-32-bit-integer-

### Operation

Source operation ID: `SveOperation_svdot_n_s32`

**Operation**



Return a vector in which the value of element *i* contains:



```text
(int32_t)op2[i * 4 + 0] * (int32_t)op3
+ (int32_t)op2[i * 4 + 1] * (int32_t)op3
+ (int32_t)op2[i * 4 + 2] * (int32_t)op3
+ (int32_t)op2[i * 4 + 3] * (int32_t)op3
+ op1[i]
```



The operation uses modulo arithmetic.  The behavior is therefore defined for all inputs; unlike C, there is no undefined behavior for signed overflow.

## svsudot[_s32]

ISA classification: SME + FEAT_I8MM

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsudot%5B_s32%5D

### Signature (source notation)

```c
svint32_t svsudot[_s32](svint32_t op1, svint8_t op2, svuint8_t op3);
```

### Description

Dot product (signed × unsigned)

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Dot product

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME,FEAT_I8MM
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
  "op1": {
    "register": "Zop1.S|Ztied1.S"
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
    "Zresult.S|Ztied1.S": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
USDOT Ztied1.S, Zop3.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/USDOT--vectors---Unsigned-by-signed-8-bit-integer-dot-product-to-32-bit-integer-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
USDOT Zresult.S, Zop3.B, Zop2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/USDOT--vectors---Unsigned-by-signed-8-bit-integer-dot-product-to-32-bit-integer-

### Operation

Source operation ID: `SveOperation_svdot_s32`

**Operation**



Return a vector in which the value of element *i* contains:



```text
(int32_t)op2[i * 4 + 0] * (int32_t)op3[i * 4 + 0]
+ (int32_t)op2[i * 4 + 1] * (int32_t)op3[i * 4 + 1]
+ (int32_t)op2[i * 4 + 2] * (int32_t)op3[i * 4 + 2]
+ (int32_t)op2[i * 4 + 3] * (int32_t)op3[i * 4 + 3]
+ op1[i]
```



The operation uses modulo arithmetic.  The behavior is therefore defined for all inputs; unlike C, there is no undefined behavior for signed overflow.

## svsudot_lane[_s32]

ISA classification: SME + FEAT_I8MM

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsudot_lane%5B_s32%5D

### Signature (source notation)

```c
svint32_t svsudot_lane[_s32](svint32_t op1, svint8_t op2, svuint8_t op3, uint64_t imm_index);
```

### Description

Dot product (signed × unsigned)

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Dot product

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME,FEAT_I8MM
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
  "op1": {
    "register": "Zop1.S|Ztied1.S"
  },
  "op2": {
    "register": "Zop2.B"
  },
  "op3": {
    "register": "Zop3.B"
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
SUDOT Ztied1.S, Zop2.B, Zop3.B[imm_index]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SUDOT--Signed-by-unsigned-8-bit-integer-indexed-dot-product-to-32-bit-integer-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SUDOT Zresult.S, Zop2.B, Zop3.B[imm_index]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SUDOT--Signed-by-unsigned-8-bit-integer-indexed-dot-product-to-32-bit-integer-

### Operation

Source operation ID: `SveOperation_svdot_lane_s32`

**Operation**



Return a vector in which the value of element *i* contains:



```text
(int32_t)op2[i * 4 + 0] * (int32_t)op3[base + imm_index * 4 + 0]
+ (int32_t)op2[i * 4 + 1] * (int32_t)op3[base + imm_index * 4 + 1]
+ (int32_t)op2[i * 4 + 2] * (int32_t)op3[base + imm_index * 4 + 2]
+ (int32_t)op2[i * 4 + 3] * (int32_t)op3[base + imm_index * 4 + 3]
+ op1[i]
```



where `op3[base]` is the first element in the same 128-bit quadword as `op3[i * 4]`.



The operation uses modulo arithmetic.  The behavior is therefore defined for all inputs; unlike C, there is no undefined behavior for signed overflow.

## svusdot[_n_s32]

ISA classification: SME + FEAT_I8MM

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svusdot%5B_n_s32%5D

### Signature (source notation)

```c
svint32_t svusdot[_n_s32](svint32_t op1, svuint8_t op2, int8_t op3);
```

### Description

Dot product (unsigned × signed)

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Dot product

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME,FEAT_I8MM
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
  "op1": {
    "register": "Zop1.S|Ztied1.S"
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
    "Zresult.S|Ztied1.S": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
USDOT Ztied1.S, Zop2.B, Zop3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/USDOT--vectors---Unsigned-by-signed-8-bit-integer-dot-product-to-32-bit-integer-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
USDOT Zresult.S, Zop2.B, Zop3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/USDOT--vectors---Unsigned-by-signed-8-bit-integer-dot-product-to-32-bit-integer-

### Operation

Source operation ID: `SveOperation_svdot_n_s32`

**Operation**



Return a vector in which the value of element *i* contains:



```text
(int32_t)op2[i * 4 + 0] * (int32_t)op3
+ (int32_t)op2[i * 4 + 1] * (int32_t)op3
+ (int32_t)op2[i * 4 + 2] * (int32_t)op3
+ (int32_t)op2[i * 4 + 3] * (int32_t)op3
+ op1[i]
```



The operation uses modulo arithmetic.  The behavior is therefore defined for all inputs; unlike C, there is no undefined behavior for signed overflow.

## svusdot[_s32]

ISA classification: SME + FEAT_I8MM

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svusdot%5B_s32%5D

### Signature (source notation)

```c
svint32_t svusdot[_s32](svint32_t op1, svuint8_t op2, svint8_t op3);
```

### Description

Dot product (unsigned × signed)

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Dot product

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME,FEAT_I8MM
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
  "op1": {
    "register": "Zop1.S|Ztied1.S"
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
    "Zresult.S|Ztied1.S": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
USDOT Ztied1.S, Zop2.B, Zop3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/USDOT--vectors---Unsigned-by-signed-8-bit-integer-dot-product-to-32-bit-integer-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
USDOT Zresult.S, Zop2.B, Zop3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/USDOT--vectors---Unsigned-by-signed-8-bit-integer-dot-product-to-32-bit-integer-

### Operation

Source operation ID: `SveOperation_svdot_s32`

**Operation**



Return a vector in which the value of element *i* contains:



```text
(int32_t)op2[i * 4 + 0] * (int32_t)op3[i * 4 + 0]
+ (int32_t)op2[i * 4 + 1] * (int32_t)op3[i * 4 + 1]
+ (int32_t)op2[i * 4 + 2] * (int32_t)op3[i * 4 + 2]
+ (int32_t)op2[i * 4 + 3] * (int32_t)op3[i * 4 + 3]
+ op1[i]
```



The operation uses modulo arithmetic.  The behavior is therefore defined for all inputs; unlike C, there is no undefined behavior for signed overflow.

## svusdot_lane[_s32]

ISA classification: SME + FEAT_I8MM

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svusdot_lane%5B_s32%5D

### Signature (source notation)

```c
svint32_t svusdot_lane[_s32](svint32_t op1, svuint8_t op2, svint8_t op3, uint64_t imm_index);
```

### Description

Dot product (unsigned × signed)

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Dot product

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME,FEAT_I8MM
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
  "op1": {
    "register": "Zop1.S|Ztied1.S"
  },
  "op2": {
    "register": "Zop2.B"
  },
  "op3": {
    "register": "Zop3.B"
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
USDOT Ztied1.S, Zop2.B, Zop3.B[imm_index]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/USDOT--indexed---Unsigned-by-signed-8-bit-integer-indexed-dot-product-to-32-bit-integer-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
USDOT Zresult.S, Zop2.B, Zop3.B[imm_index]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/USDOT--indexed---Unsigned-by-signed-8-bit-integer-indexed-dot-product-to-32-bit-integer-

### Operation

Source operation ID: `SveOperation_svdot_lane_s32`

**Operation**



Return a vector in which the value of element *i* contains:



```text
(int32_t)op2[i * 4 + 0] * (int32_t)op3[base + imm_index * 4 + 0]
+ (int32_t)op2[i * 4 + 1] * (int32_t)op3[base + imm_index * 4 + 1]
+ (int32_t)op2[i * 4 + 2] * (int32_t)op3[base + imm_index * 4 + 2]
+ (int32_t)op2[i * 4 + 3] * (int32_t)op3[base + imm_index * 4 + 3]
+ op1[i]
```



where `op3[base]` is the first element in the same 128-bit quadword as `op3[i * 4]`.



The operation uses modulo arithmetic.  The behavior is therefore defined for all inputs; unlike C, there is no undefined behavior for signed overflow.

