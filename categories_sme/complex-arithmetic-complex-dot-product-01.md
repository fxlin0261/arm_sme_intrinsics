# SME / Complex arithmetic / Complex dot product — Part 1

## svcdot[_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcdot%5B_s32%5D

### Signature (source notation)

```c
svint32_t svcdot[_s32](svint32_t op1, svint8_t op2, svint8_t op3, uint64_t imm_rotation);
```

### Description

Complex dot product

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Complex arithmetic / Complex dot product

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
CDOT Ztied1.S, Zop2.B, Zop3.B, #imm_rotation
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CDOT--vectors---Complex-integer-dot-product-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
CDOT Zresult.S, Zop2.B, Zop3.B, #imm_rotation
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CDOT--vectors---Complex-integer-dot-product-

### Operation

Source operation ID: `SveOperation_svcdot_s32`

**Operation**



`op2` and `op3` contain complex values as pairs of real and imaginary components, with the real components in even-indexed elements and the imaginary components in odd-indexed elements.  There are two complex values per element of `op1`, and per element of the result vector.



Return a vector in which the value of element *j* contains the result of the following procedure:




- If `imm_rotation` is 180 or 270, compute the conjugate of `op2` and use it in place of `op2` in the following step.
- 

Calculate the dot product of the complex values stored in:



```text
op2[j * 4 … j * 4 + 3]
```



and:



```text
op3[j * 4 … j * 4 + 3]
```


- If `imm_rotation` is 0 or 180, add the real component of the dot product to `op1[j]`, otherwise add the imaginary component of the dot product to `op1[j]`.



Element *j* of the result vector therefore contains the following:

`imm_rotation` == 0

```text
op1[j] + (int32_t)op2[r1] * (int32_t)op3[r1]
       - (int32_t)op2[i1] * (int32_t)op3[i1]
       + (int32_t)op2[r2] * (int32_t)op3[r2]
       - (int32_t)op2[i2] * (int32_t)op3[i2]
```

`imm_rotation` == 90

```text
op1[j] + (int32_t)op2[r1] * (int32_t)op3[i1]
       + (int32_t)op2[i1] * (int32_t)op3[r1]
       + (int32_t)op2[r2] * (int32_t)op3[i2]
       + (int32_t)op2[i2] * (int32_t)op3[r2]
```

`imm_rotation` == 180

```text
op1[j] + (int32_t)op2[r1] * (int32_t)op3[r1]
       + (int32_t)op2[i1] * (int32_t)op3[i1]
       + (int32_t)op2[r2] * (int32_t)op3[r2]
       + (int32_t)op2[i2] * (int32_t)op3[i2]
```

`imm_rotation` == 270

```text
op1[j] + (int32_t)op2[r1] * (int32_t)op3[i1]
       - (int32_t)op2[i1] * (int32_t)op3[r1]
       + (int32_t)op2[r2] * (int32_t)op3[i2]
       - (int32_t)op2[i2] * (int32_t)op3[r2]
```



where:




- `r1 = j * 4 + 0`
- `i1 = j * 4 + 1`
- `r2 = j * 4 + 2`
- `i2 = j * 4 + 3`



The operation uses modulo arithmetic.  The behavior is therefore defined for all inputs; unlike C, there is no undefined behavior for signed overflow.

## svcdot[_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcdot%5B_s64%5D

### Signature (source notation)

```c
svint64_t svcdot[_s64](svint64_t op1, svint16_t op2, svint16_t op3, uint64_t imm_rotation);
```

### Description

Complex dot product

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Complex arithmetic / Complex dot product

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
CDOT Ztied1.D, Zop2.H, Zop3.H, #imm_rotation
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CDOT--vectors---Complex-integer-dot-product-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
CDOT Zresult.D, Zop2.H, Zop3.H, #imm_rotation
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CDOT--vectors---Complex-integer-dot-product-

### Operation

Source operation ID: `SveOperation_svcdot_s64`

**Operation**



`op2` and `op3` contain complex values as pairs of real and imaginary components, with the real components in even-indexed elements and the imaginary components in odd-indexed elements.  There are two complex values per element of `op1`, and per element of the result vector.



Return a vector in which the value of element *j* contains the result of the following procedure:




- If `imm_rotation` is 180 or 270, compute the conjugate of `op2` and use it in place of `op2` in the following step.
- 

Calculate the dot product of the complex values stored in:



```text
op2[j * 4 … j * 4 + 3]
```



and:



```text
op3[j * 4 … j * 4 + 3]
```


- If `imm_rotation` is 0 or 180, add the real component of the dot product to `op1[j]`, otherwise add the imaginary component of the dot product to `op1[j]`.



Element *j* of the result vector therefore contains the following:

`imm_rotation` == 0

```text
op1[j] + (int64_t)op2[r1] * (int64_t)op3[r1]
       - (int64_t)op2[i1] * (int64_t)op3[i1]
       + (int64_t)op2[r2] * (int64_t)op3[r2]
       - (int64_t)op2[i2] * (int64_t)op3[i2]
```

`imm_rotation` == 90

```text
op1[j] + (int64_t)op2[r1] * (int64_t)op3[i1]
       + (int64_t)op2[i1] * (int64_t)op3[r1]
       + (int64_t)op2[r2] * (int64_t)op3[i2]
       + (int64_t)op2[i2] * (int64_t)op3[r2]
```

`imm_rotation` == 180

```text
op1[j] + (int64_t)op2[r1] * (int64_t)op3[r1]
       + (int64_t)op2[i1] * (int64_t)op3[i1]
       + (int64_t)op2[r2] * (int64_t)op3[r2]
       + (int64_t)op2[i2] * (int64_t)op3[i2]
```

`imm_rotation` == 270

```text
op1[j] + (int64_t)op2[r1] * (int64_t)op3[i1]
       - (int64_t)op2[i1] * (int64_t)op3[r1]
       + (int64_t)op2[r2] * (int64_t)op3[i2]
       - (int64_t)op2[i2] * (int64_t)op3[r2]
```



where:




- `r1 = j * 4 + 0`
- `i1 = j * 4 + 1`
- `r2 = j * 4 + 2`
- `i2 = j * 4 + 3`



The operation uses modulo arithmetic.  The behavior is therefore defined for all inputs; unlike C, there is no undefined behavior for signed overflow.

## svcdot_lane[_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcdot_lane%5B_s32%5D

### Signature (source notation)

```c
svint32_t svcdot_lane[_s32](svint32_t op1, svint8_t op2, svint8_t op3, uint64_t imm_index, uint64_t imm_rotation);
```

### Description

Complex dot product

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Complex arithmetic / Complex dot product

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
CDOT Ztied1.S, Zop2.B, Zop3.B[imm_index], #imm_rotation
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CDOT--indexed---Complex-integer-dot-product--indexed--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
CDOT Zresult.S, Zop2.B, Zop3.B[imm_index], #imm_rotation
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CDOT--indexed---Complex-integer-dot-product--indexed--

### Operation

Source operation ID: `SveOperation_svcdot_lane_s32`

**Operation**



`op2` and `op3` contain complex values as pairs of real and imaginary components, with the real components in even-indexed elements and the imaginary components in odd-indexed elements.  There are two complex values per element of `op1`, and per element of the result vector.



Return a vector in which the value of element *j* contains the result of the following procedure:




- If `imm_rotation` is 180 or 270, compute the conjugate of `op2` and use it in place of `op2` in the following step.
- 

Calculate the dot product of the complex values stored in:



```text
op2[j * 4 … j * 4 + 3]
```



and:



```text
op3[base + imm_index * 4 … base + imm_index * 4 + 3]
```



where *base* is the index of the first element in the same 128-bit quadword as `op3[j * 4]`.


- If `imm_rotation` is 0 or 180, add the real component of the dot product to `op1[j]`, otherwise add the imaginary component of the dot product to `op1[j]`.



Element *j* of the result vector therefore contains the following:

`imm_rotation` == 0

```text
op1[j] + (int32_t)op2[r1] * (int32_t)op3[base + imm_index * 4 + 0]
       - (int32_t)op2[i1] * (int32_t)op3[base + imm_index * 4 + 1]
       + (int32_t)op2[r2] * (int32_t)op3[base + imm_index * 4 + 2]
       - (int32_t)op2[i2] * (int32_t)op3[base + imm_index * 4 + 3]
```

`imm_rotation` == 90

```text
op1[j] + (int32_t)op2[r1] * (int32_t)op3[base + imm_index * 4 + 1]
       + (int32_t)op2[i1] * (int32_t)op3[base + imm_index * 4 + 0]
       + (int32_t)op2[r2] * (int32_t)op3[base + imm_index * 4 + 3]
       + (int32_t)op2[i2] * (int32_t)op3[base + imm_index * 4 + 2]
```

`imm_rotation` == 180

```text
op1[j] + (int32_t)op2[r1] * (int32_t)op3[base + imm_index * 4 + 0]
       + (int32_t)op2[i1] * (int32_t)op3[base + imm_index * 4 + 1]
       + (int32_t)op2[r2] * (int32_t)op3[base + imm_index * 4 + 2]
       + (int32_t)op2[i2] * (int32_t)op3[base + imm_index * 4 + 3]
```

`imm_rotation` == 270

```text
op1[j] + (int32_t)op2[r1] * (int32_t)op3[base + imm_index * 4 + 1]
       - (int32_t)op2[i1] * (int32_t)op3[base + imm_index * 4 + 0]
       + (int32_t)op2[r2] * (int32_t)op3[base + imm_index * 4 + 3]
       - (int32_t)op2[i2] * (int32_t)op3[base + imm_index * 4 + 2]
```



where:




- `r1 = j * 4 + 0`
- `i1 = j * 4 + 1`
- `r2 = j * 4 + 2`
- `i2 = j * 4 + 3`



The operation uses modulo arithmetic.  The behavior is therefore defined for all inputs; unlike C, there is no undefined behavior for signed overflow.

## svcdot_lane[_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcdot_lane%5B_s64%5D

### Signature (source notation)

```c
svint64_t svcdot_lane[_s64](svint64_t op1, svint16_t op2, svint16_t op3, uint64_t imm_index, uint64_t imm_rotation);
```

### Description

Complex dot product

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Complex arithmetic / Complex dot product

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
CDOT Ztied1.D, Zop2.H, Zop3.H[imm_index], #imm_rotation
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CDOT--indexed---Complex-integer-dot-product--indexed--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
CDOT Zresult.D, Zop2.H, Zop3.H[imm_index], #imm_rotation
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CDOT--indexed---Complex-integer-dot-product--indexed--

### Operation

Source operation ID: `SveOperation_svcdot_lane_s64`

**Operation**



`op2` and `op3` contain complex values as pairs of real and imaginary components, with the real components in even-indexed elements and the imaginary components in odd-indexed elements.  There are two complex values per element of `op1`, and per element of the result vector.



Return a vector in which the value of element *j* contains the result of the following procedure:




- If `imm_rotation` is 180 or 270, compute the conjugate of `op2` and use it in place of `op2` in the following step.
- 

Calculate the dot product of the complex values stored in:



```text
op2[j * 4 … j * 4 + 3]
```



and:



```text
op3[base + imm_index * 4 … base + imm_index * 4 + 3]
```



where *base* is the index of the first element in the same 128-bit quadword as `op3[j * 4]`.


- If `imm_rotation` is 0 or 180, add the real component of the dot product to `op1[j]`, otherwise add the imaginary component of the dot product to `op1[j]`.



Element *j* of the result vector therefore contains the following:

`imm_rotation` == 0

```text
op1[j] + (int64_t)op2[r1] * (int64_t)op3[base + imm_index * 4 + 0]
       - (int64_t)op2[i1] * (int64_t)op3[base + imm_index * 4 + 1]
       + (int64_t)op2[r2] * (int64_t)op3[base + imm_index * 4 + 2]
       - (int64_t)op2[i2] * (int64_t)op3[base + imm_index * 4 + 3]
```

`imm_rotation` == 90

```text
op1[j] + (int64_t)op2[r1] * (int64_t)op3[base + imm_index * 4 + 1]
       + (int64_t)op2[i1] * (int64_t)op3[base + imm_index * 4 + 0]
       + (int64_t)op2[r2] * (int64_t)op3[base + imm_index * 4 + 3]
       + (int64_t)op2[i2] * (int64_t)op3[base + imm_index * 4 + 2]
```

`imm_rotation` == 180

```text
op1[j] + (int64_t)op2[r1] * (int64_t)op3[base + imm_index * 4 + 0]
       + (int64_t)op2[i1] * (int64_t)op3[base + imm_index * 4 + 1]
       + (int64_t)op2[r2] * (int64_t)op3[base + imm_index * 4 + 2]
       + (int64_t)op2[i2] * (int64_t)op3[base + imm_index * 4 + 3]
```

`imm_rotation` == 270

```text
op1[j] + (int64_t)op2[r1] * (int64_t)op3[base + imm_index * 4 + 1]
       - (int64_t)op2[i1] * (int64_t)op3[base + imm_index * 4 + 0]
       + (int64_t)op2[r2] * (int64_t)op3[base + imm_index * 4 + 3]
       - (int64_t)op2[i2] * (int64_t)op3[base + imm_index * 4 + 2]
```



where:




- `r1 = j * 4 + 0`
- `i1 = j * 4 + 1`
- `r2 = j * 4 + 2`
- `i2 = j * 4 + 3`



The operation uses modulo arithmetic.  The behavior is therefore defined for all inputs; unlike C, there is no undefined behavior for signed overflow.

