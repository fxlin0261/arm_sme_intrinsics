# SME / Complex arithmetic / Saturating complex addition — Part 1

## svqcadd[_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqcadd%5B_s16%5D

### Signature (source notation)

```c
svint16_t svqcadd[_s16](svint16_t op1, svint16_t op2, uint64_t imm_rotation);
```

### Description

Saturating complex add with rotate

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Complex arithmetic / Saturating complex addition

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
SQCADD Ztied1.H, Ztied1.H, Zop2.H, #imm_rotation
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQCADD--Saturating-complex-integer-add-with-rotate-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SQCADD Zresult.H, Zresult.H, Zop2.H, #imm_rotation
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQCADD--Saturating-complex-integer-add-with-rotate-

### Operation

Source operation ID: `SveOperation_svqcadd_s8`

**Operation**



The arguments and result contain complex values as pairs of real and imaginary components, with the real components in even-indexed elements and the imaginary components in odd-indexed elements.



If *r* is the index of a real component and *i* is the index of the corresponding imaginary component, return a vector *res* in which each element is given by:

`imm_rotation` == 90

```text
res[r] = SatSub(op1[r], op2[i]);
res[i] = SatAdd(op1[i], op2[r]);
```

`imm_rotation` == 270

```text
res[r] = SatAdd(op1[r], op2[i]);
res[i] = SatSub(op1[i], op2[r]);
```



where `SatAdd` represents saturating addition and where `SatSub` represents saturating subtraction.

## svqcadd[_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqcadd%5B_s32%5D

### Signature (source notation)

```c
svint32_t svqcadd[_s32](svint32_t op1, svint32_t op2, uint64_t imm_rotation);
```

### Description

Saturating complex add with rotate

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Complex arithmetic / Saturating complex addition

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
SQCADD Ztied1.S, Ztied1.S, Zop2.S, #imm_rotation
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQCADD--Saturating-complex-integer-add-with-rotate-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SQCADD Zresult.S, Zresult.S, Zop2.S, #imm_rotation
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQCADD--Saturating-complex-integer-add-with-rotate-

### Operation

Source operation ID: `SveOperation_svqcadd_s8`

**Operation**



The arguments and result contain complex values as pairs of real and imaginary components, with the real components in even-indexed elements and the imaginary components in odd-indexed elements.



If *r* is the index of a real component and *i* is the index of the corresponding imaginary component, return a vector *res* in which each element is given by:

`imm_rotation` == 90

```text
res[r] = SatSub(op1[r], op2[i]);
res[i] = SatAdd(op1[i], op2[r]);
```

`imm_rotation` == 270

```text
res[r] = SatAdd(op1[r], op2[i]);
res[i] = SatSub(op1[i], op2[r]);
```



where `SatAdd` represents saturating addition and where `SatSub` represents saturating subtraction.

## svqcadd[_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqcadd%5B_s64%5D

### Signature (source notation)

```c
svint64_t svqcadd[_s64](svint64_t op1, svint64_t op2, uint64_t imm_rotation);
```

### Description

Saturating complex add with rotate

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Complex arithmetic / Saturating complex addition

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
SQCADD Ztied1.D, Ztied1.D, Zop2.D, #imm_rotation
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQCADD--Saturating-complex-integer-add-with-rotate-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SQCADD Zresult.D, Zresult.D, Zop2.D, #imm_rotation
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQCADD--Saturating-complex-integer-add-with-rotate-

### Operation

Source operation ID: `SveOperation_svqcadd_s8`

**Operation**



The arguments and result contain complex values as pairs of real and imaginary components, with the real components in even-indexed elements and the imaginary components in odd-indexed elements.



If *r* is the index of a real component and *i* is the index of the corresponding imaginary component, return a vector *res* in which each element is given by:

`imm_rotation` == 90

```text
res[r] = SatSub(op1[r], op2[i]);
res[i] = SatAdd(op1[i], op2[r]);
```

`imm_rotation` == 270

```text
res[r] = SatAdd(op1[r], op2[i]);
res[i] = SatSub(op1[i], op2[r]);
```



where `SatAdd` represents saturating addition and where `SatSub` represents saturating subtraction.

## svqcadd[_s8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svqcadd%5B_s8%5D

### Signature (source notation)

```c
svint8_t svqcadd[_s8](svint8_t op1, svint8_t op2, uint64_t imm_rotation);
```

### Description

Saturating complex add with rotate

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Complex arithmetic / Saturating complex addition

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
SQCADD Ztied1.B, Ztied1.B, Zop2.B, #imm_rotation
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQCADD--Saturating-complex-integer-add-with-rotate-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SQCADD Zresult.B, Zresult.B, Zop2.B, #imm_rotation
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SQCADD--Saturating-complex-integer-add-with-rotate-

### Operation

Source operation ID: `SveOperation_svqcadd_s8`

**Operation**



The arguments and result contain complex values as pairs of real and imaginary components, with the real components in even-indexed elements and the imaginary components in odd-indexed elements.



If *r* is the index of a real component and *i* is the index of the corresponding imaginary component, return a vector *res* in which each element is given by:

`imm_rotation` == 90

```text
res[r] = SatSub(op1[r], op2[i]);
res[i] = SatAdd(op1[i], op2[r]);
```

`imm_rotation` == 270

```text
res[r] = SatAdd(op1[r], op2[i]);
res[i] = SatSub(op1[i], op2[r]);
```



where `SatAdd` represents saturating addition and where `SatSub` represents saturating subtraction.

