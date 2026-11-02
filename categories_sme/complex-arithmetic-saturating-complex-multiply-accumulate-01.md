# SME / Complex arithmetic / Saturating complex multiply-accumulate — Part 1

## svqrdcmlah[_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqrdcmlah%5B_s16%5D

### Signature (source notation)

```c
svint16_t svqrdcmlah[_s16](svint16_t op1, svint16_t op2, svint16_t op3, uint64_t imm_rotation);
```

### Description

Saturating rounding doubling complex multiply-add high with rotate

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Complex arithmetic / Saturating complex multiply-accumulate

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
SQRDCMLAH Ztied1.H, Zop2.H, Zop3.H, #imm_rotation
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQRDCMLAH--vectors---Saturating-rounding-doubling-complex-integer-multiply-add-high-with-rotate-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SQRDCMLAH Zresult.H, Zop2.H, Zop3.H, #imm_rotation
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQRDCMLAH--vectors---Saturating-rounding-doubling-complex-integer-multiply-add-high-with-rotate-

### Operation

Source operation ID: `SveOperation_svqrdcmlah_s16`

**Operation**



The arguments and result contain complex values as pairs of real and imaginary components, with the real components in even-indexed elements and the imaginary components in odd-indexed elements.



If *r* is the index of a real component and *i* is the index of the corresponding imaginary component, return a vector *res* in which each element is given by:

`imm_rotation` == 0

```text
res[r] = AddOp(op1[r], op2[r], op3[r]);
res[i] = AddOp(op1[i], op2[r], op3[i]);
```

`imm_rotation` == 90

```text
res[r] = SubOp(op1[r], op2[i], op3[i]);
res[i] = AddOp(op1[i], op2[i], op3[r]);
```

`imm_rotation` == 180

```text
res[r] = SubOp(op1[r], op2[r], op3[r]);
res[i] = SubOp(op1[i], op2[r], op3[i]);
```

`imm_rotation` == 270

```text
res[r] = AddOp(op1[r], op2[i], op3[i]);
res[i] = SubOp(op1[i], op2[i], op3[r]);
```



The AddOp(*x*, *y*, *z*) and SubOp(*x*, *y*, *z*) functions above represent the result of the following procedure:




- Multiply *y* and *z*, without loss of precision.
- For SubOp only: negate the result, without loss of precision.
- Divide the result by 2 to the power 15, rounding to nearest with ties towards +∞.
- Add the result to *x*, without loss of precision.
- Saturate the result to the range of `int16_t`.



Thus:




- A full `op1 + op2 * op3` operation can be performed using an `imm_rotation` of 0 followed by an `imm_rotation` of 90.
- A full `op1 - op2 * op3` operation can be performed using an `imm_rotation` of 180 followed by an `imm_rotation` of 270.
- A full `op1 + conj(op2) * op3` operation can be performed using an `imm_rotation` of 0 followed by an `imm_rotation` of 270.
- A full `op1 - conj(op2) * op3` operation can be performed using an `imm_rotation` of 180 followed by an `imm_rotation` of 90.

## svqrdcmlah[_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqrdcmlah%5B_s32%5D

### Signature (source notation)

```c
svint32_t svqrdcmlah[_s32](svint32_t op1, svint32_t op2, svint32_t op3, uint64_t imm_rotation);
```

### Description

Saturating rounding doubling complex multiply-add high with rotate

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Complex arithmetic / Saturating complex multiply-accumulate

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
SQRDCMLAH Ztied1.S, Zop2.S, Zop3.S, #imm_rotation
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQRDCMLAH--vectors---Saturating-rounding-doubling-complex-integer-multiply-add-high-with-rotate-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SQRDCMLAH Zresult.S, Zop2.S, Zop3.S, #imm_rotation
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQRDCMLAH--vectors---Saturating-rounding-doubling-complex-integer-multiply-add-high-with-rotate-

### Operation

Source operation ID: `SveOperation_svqrdcmlah_s32`

**Operation**



The arguments and result contain complex values as pairs of real and imaginary components, with the real components in even-indexed elements and the imaginary components in odd-indexed elements.



If *r* is the index of a real component and *i* is the index of the corresponding imaginary component, return a vector *res* in which each element is given by:

`imm_rotation` == 0

```text
res[r] = AddOp(op1[r], op2[r], op3[r]);
res[i] = AddOp(op1[i], op2[r], op3[i]);
```

`imm_rotation` == 90

```text
res[r] = SubOp(op1[r], op2[i], op3[i]);
res[i] = AddOp(op1[i], op2[i], op3[r]);
```

`imm_rotation` == 180

```text
res[r] = SubOp(op1[r], op2[r], op3[r]);
res[i] = SubOp(op1[i], op2[r], op3[i]);
```

`imm_rotation` == 270

```text
res[r] = AddOp(op1[r], op2[i], op3[i]);
res[i] = SubOp(op1[i], op2[i], op3[r]);
```



The AddOp(*x*, *y*, *z*) and SubOp(*x*, *y*, *z*) functions above represent the result of the following procedure:




- Multiply *y* and *z*, without loss of precision.
- For SubOp only: negate the result, without loss of precision.
- Divide the result by 2 to the power 31, rounding to nearest with ties towards +∞.
- Add the result to *x*, without loss of precision.
- Saturate the result to the range of `int32_t`.



Thus:




- A full `op1 + op2 * op3` operation can be performed using an `imm_rotation` of 0 followed by an `imm_rotation` of 90.
- A full `op1 - op2 * op3` operation can be performed using an `imm_rotation` of 180 followed by an `imm_rotation` of 270.
- A full `op1 + conj(op2) * op3` operation can be performed using an `imm_rotation` of 0 followed by an `imm_rotation` of 270.
- A full `op1 - conj(op2) * op3` operation can be performed using an `imm_rotation` of 180 followed by an `imm_rotation` of 90.

## svqrdcmlah[_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqrdcmlah%5B_s64%5D

### Signature (source notation)

```c
svint64_t svqrdcmlah[_s64](svint64_t op1, svint64_t op2, svint64_t op3, uint64_t imm_rotation);
```

### Description

Saturating rounding doubling complex multiply-add high with rotate

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Complex arithmetic / Saturating complex multiply-accumulate

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
SQRDCMLAH Ztied1.D, Zop2.D, Zop3.D, #imm_rotation
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQRDCMLAH--vectors---Saturating-rounding-doubling-complex-integer-multiply-add-high-with-rotate-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SQRDCMLAH Zresult.D, Zop2.D, Zop3.D, #imm_rotation
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQRDCMLAH--vectors---Saturating-rounding-doubling-complex-integer-multiply-add-high-with-rotate-

### Operation

Source operation ID: `SveOperation_svqrdcmlah_s64`

**Operation**



The arguments and result contain complex values as pairs of real and imaginary components, with the real components in even-indexed elements and the imaginary components in odd-indexed elements.



If *r* is the index of a real component and *i* is the index of the corresponding imaginary component, return a vector *res* in which each element is given by:

`imm_rotation` == 0

```text
res[r] = AddOp(op1[r], op2[r], op3[r]);
res[i] = AddOp(op1[i], op2[r], op3[i]);
```

`imm_rotation` == 90

```text
res[r] = SubOp(op1[r], op2[i], op3[i]);
res[i] = AddOp(op1[i], op2[i], op3[r]);
```

`imm_rotation` == 180

```text
res[r] = SubOp(op1[r], op2[r], op3[r]);
res[i] = SubOp(op1[i], op2[r], op3[i]);
```

`imm_rotation` == 270

```text
res[r] = AddOp(op1[r], op2[i], op3[i]);
res[i] = SubOp(op1[i], op2[i], op3[r]);
```



The AddOp(*x*, *y*, *z*) and SubOp(*x*, *y*, *z*) functions above represent the result of the following procedure:




- Multiply *y* and *z*, without loss of precision.
- For SubOp only: negate the result, without loss of precision.
- Divide the result by 2 to the power 63, rounding to nearest with ties towards +∞.
- Add the result to *x*, without loss of precision.
- Saturate the result to the range of `int64_t`.



Thus:




- A full `op1 + op2 * op3` operation can be performed using an `imm_rotation` of 0 followed by an `imm_rotation` of 90.
- A full `op1 - op2 * op3` operation can be performed using an `imm_rotation` of 180 followed by an `imm_rotation` of 270.
- A full `op1 + conj(op2) * op3` operation can be performed using an `imm_rotation` of 0 followed by an `imm_rotation` of 270.
- A full `op1 - conj(op2) * op3` operation can be performed using an `imm_rotation` of 180 followed by an `imm_rotation` of 90.

## svqrdcmlah[_s8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqrdcmlah%5B_s8%5D

### Signature (source notation)

```c
svint8_t svqrdcmlah[_s8](svint8_t op1, svint8_t op2, svint8_t op3, uint64_t imm_rotation);
```

### Description

Saturating rounding doubling complex multiply-add high with rotate

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Complex arithmetic / Saturating complex multiply-accumulate

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
SQRDCMLAH Ztied1.B, Zop2.B, Zop3.B, #imm_rotation
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQRDCMLAH--vectors---Saturating-rounding-doubling-complex-integer-multiply-add-high-with-rotate-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SQRDCMLAH Zresult.B, Zop2.B, Zop3.B, #imm_rotation
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQRDCMLAH--vectors---Saturating-rounding-doubling-complex-integer-multiply-add-high-with-rotate-

### Operation

Source operation ID: `SveOperation_svqrdcmlah_s8`

**Operation**



The arguments and result contain complex values as pairs of real and imaginary components, with the real components in even-indexed elements and the imaginary components in odd-indexed elements.



If *r* is the index of a real component and *i* is the index of the corresponding imaginary component, return a vector *res* in which each element is given by:

`imm_rotation` == 0

```text
res[r] = AddOp(op1[r], op2[r], op3[r]);
res[i] = AddOp(op1[i], op2[r], op3[i]);
```

`imm_rotation` == 90

```text
res[r] = SubOp(op1[r], op2[i], op3[i]);
res[i] = AddOp(op1[i], op2[i], op3[r]);
```

`imm_rotation` == 180

```text
res[r] = SubOp(op1[r], op2[r], op3[r]);
res[i] = SubOp(op1[i], op2[r], op3[i]);
```

`imm_rotation` == 270

```text
res[r] = AddOp(op1[r], op2[i], op3[i]);
res[i] = SubOp(op1[i], op2[i], op3[r]);
```



The AddOp(*x*, *y*, *z*) and SubOp(*x*, *y*, *z*) functions above represent the result of the following procedure:




- Multiply *y* and *z*, without loss of precision.
- For SubOp only: negate the result, without loss of precision.
- Divide the result by 2 to the power 7, rounding to nearest with ties towards +∞.
- Add the result to *x*, without loss of precision.
- Saturate the result to the range of `int8_t`.



Thus:




- A full `op1 + op2 * op3` operation can be performed using an `imm_rotation` of 0 followed by an `imm_rotation` of 90.
- A full `op1 - op2 * op3` operation can be performed using an `imm_rotation` of 180 followed by an `imm_rotation` of 270.
- A full `op1 + conj(op2) * op3` operation can be performed using an `imm_rotation` of 0 followed by an `imm_rotation` of 270.
- A full `op1 - conj(op2) * op3` operation can be performed using an `imm_rotation` of 180 followed by an `imm_rotation` of 90.

## svqrdcmlah_lane[_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqrdcmlah_lane%5B_s16%5D

### Signature (source notation)

```c
svint16_t svqrdcmlah_lane[_s16](svint16_t op1, svint16_t op2, svint16_t op3, uint64_t imm_index, uint64_t imm_rotation);
```

### Description

Saturating rounding doubling complex multiply-add high with rotate

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Complex arithmetic / Saturating complex multiply-accumulate

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
  "op1": {
    "register": "Zop1.H|Ztied1.H"
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
    "Zresult.H|Ztied1.H": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
SQRDCMLAH Ztied1.H, Zop2.H, Zop3.H[imm_index], #imm_rotation
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQRDCMLAH--indexed---Saturating-rounding-doubling-complex-integer-multiply-add-high-with-rotate--indexed--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SQRDCMLAH Zresult.H, Zop2.H, Zop3.H[imm_index], #imm_rotation
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQRDCMLAH--indexed---Saturating-rounding-doubling-complex-integer-multiply-add-high-with-rotate--indexed--

### Operation

Source operation ID: `SveOperation_svqrdcmlah_lane_s16`

**Operation**



The arguments and result contain complex values as pairs of real and imaginary components, with the real components in even-indexed elements and the imaginary components in odd-indexed elements.



If *r* is the index of a real component and *i* is the index of the corresponding imaginary component, return a vector *res* in which each element is given by:

`imm_rotation` == 0

```text
res[r] = AddOp(op1[r], op2[r], op3[base + imm_index * 2]);
res[i] = AddOp(op1[i], op2[r], op3[base + imm_index * 2 + 1]);
```

`imm_rotation` == 90

```text
res[r] = SubOp(op1[r], op2[i], op3[base + imm_index * 2 + 1]);
res[i] = AddOp(op1[i], op2[i], op3[base + imm_index * 2]);
```

`imm_rotation` == 180

```text
res[r] = SubOp(op1[r], op2[r], op3[base + imm_index * 2]);
res[i] = SubOp(op1[i], op2[r], op3[base + imm_index * 2 + 1]);
```

`imm_rotation` == 270

```text
res[r] = AddOp(op1[r], op2[i], op3[base + imm_index * 2 + 1]);
res[i] = SubOp(op1[i], op2[i], op3[base + imm_index * 2]);
```



where *base* is the index of the first element in the same 128-bit quadword as *i*.  The AddOp(*x*, *y*, *z*) and SubOp(*x*, *y*, *z*) functions above represent the result of the following procedure:




- Multiply *y* and *z*, without loss of precision.
- For SubOp only: negate the result, without loss of precision.
- Divide the result by 2 to the power 15, rounding to nearest with ties towards +∞.
- Add the result to *x*, without loss of precision.
- Saturate the result to the range of `int16_t`.



Thus:




- A full `op1 + op2 * op3` operation can be performed using an `imm_rotation` of 0 followed by an `imm_rotation` of 90.
- A full `op1 - op2 * op3` operation can be performed using an `imm_rotation` of 180 followed by an `imm_rotation` of 270.
- A full `op1 + conj(op2) * op3` operation can be performed using an `imm_rotation` of 0 followed by an `imm_rotation` of 270.
- A full `op1 - conj(op2) * op3` operation can be performed using an `imm_rotation` of 180 followed by an `imm_rotation` of 90.

## svqrdcmlah_lane[_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqrdcmlah_lane%5B_s32%5D

### Signature (source notation)

```c
svint32_t svqrdcmlah_lane[_s32](svint32_t op1, svint32_t op2, svint32_t op3, uint64_t imm_index, uint64_t imm_rotation);
```

### Description

Saturating rounding doubling complex multiply-add high with rotate

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Complex arithmetic / Saturating complex multiply-accumulate

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
    "register": "Zop2.S"
  },
  "op3": {
    "register": "Zop3.S"
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
    "Zresult.S|Ztied1.S": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
SQRDCMLAH Ztied1.S, Zop2.S, Zop3.S[imm_index], #imm_rotation
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQRDCMLAH--indexed---Saturating-rounding-doubling-complex-integer-multiply-add-high-with-rotate--indexed--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SQRDCMLAH Zresult.S, Zop2.S, Zop3.S[imm_index], #imm_rotation
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQRDCMLAH--indexed---Saturating-rounding-doubling-complex-integer-multiply-add-high-with-rotate--indexed--

### Operation

Source operation ID: `SveOperation_svqrdcmlah_lane_s32`

**Operation**



The arguments and result contain complex values as pairs of real and imaginary components, with the real components in even-indexed elements and the imaginary components in odd-indexed elements.



If *r* is the index of a real component and *i* is the index of the corresponding imaginary component, return a vector *res* in which each element is given by:

`imm_rotation` == 0

```text
res[r] = AddOp(op1[r], op2[r], op3[base + imm_index * 2]);
res[i] = AddOp(op1[i], op2[r], op3[base + imm_index * 2 + 1]);
```

`imm_rotation` == 90

```text
res[r] = SubOp(op1[r], op2[i], op3[base + imm_index * 2 + 1]);
res[i] = AddOp(op1[i], op2[i], op3[base + imm_index * 2]);
```

`imm_rotation` == 180

```text
res[r] = SubOp(op1[r], op2[r], op3[base + imm_index * 2]);
res[i] = SubOp(op1[i], op2[r], op3[base + imm_index * 2 + 1]);
```

`imm_rotation` == 270

```text
res[r] = AddOp(op1[r], op2[i], op3[base + imm_index * 2 + 1]);
res[i] = SubOp(op1[i], op2[i], op3[base + imm_index * 2]);
```



where *base* is the index of the first element in the same 128-bit quadword as *i*.  The AddOp(*x*, *y*, *z*) and SubOp(*x*, *y*, *z*) functions above represent the result of the following procedure:




- Multiply *y* and *z*, without loss of precision.
- For SubOp only: negate the result, without loss of precision.
- Divide the result by 2 to the power 31, rounding to nearest with ties towards +∞.
- Add the result to *x*, without loss of precision.
- Saturate the result to the range of `int32_t`.



Thus:




- A full `op1 + op2 * op3` operation can be performed using an `imm_rotation` of 0 followed by an `imm_rotation` of 90.
- A full `op1 - op2 * op3` operation can be performed using an `imm_rotation` of 180 followed by an `imm_rotation` of 270.
- A full `op1 + conj(op2) * op3` operation can be performed using an `imm_rotation` of 0 followed by an `imm_rotation` of 270.
- A full `op1 - conj(op2) * op3` operation can be performed using an `imm_rotation` of 180 followed by an `imm_rotation` of 90.

