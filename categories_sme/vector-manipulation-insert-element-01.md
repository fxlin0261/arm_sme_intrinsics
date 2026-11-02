# SME / Vector manipulation / Insert element — Part 1

## svinsr[_n_bf16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svinsr%5B_n_bf16%5D

### Signature (source notation)

```c
svbfloat16_t svinsr[_n_bf16](svbfloat16_t op1, bfloat16_t op2);
```

### Description

Insert scalar into shifted vector

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Insert element

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
  "return_base_type": "bfloat",
  "element_bit_size": "16",
  "value": "svbfloat16_t"
}
```

### Argument preparation and constraints

```json
{
  "op1": {
    "register": "Ztied1.H"
  },
  "op2": {
    "register": "Hop2|Wop2"
  }
}
```

### Result mapping

```json
[
  {
    "Ztied1.H": "result"
  }
]
```

### Instruction mapping

When op2 is in a GP register, this intrinsic compiles to:

```asm
INSR Ztied1.H, Wop2  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/INSR--scalar---Insert-general-purpose-register-in-shifted-vector-

When op2 is in an FP register, this intrinsic compiles to:

```asm
INSR Ztied1.H, Hop2  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/INSR--SIMD-FP-scalar---Insert-SIMD-FP-scalar-register-in-shifted-vector-

### Operation

Source operation ID: `SveOperation_svinsr_n_bf16`

**Operation**



Return a vector in which:




- Element 0 contains `op2`.
- For all *i* > 0, element *i* contains `op1[i - 1]`.



**[1]** If instead `result` is in a different register from the inputs, the compiler can add a preceding [MOVPRFX (unpredicated)](https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--) instruction

## svinsr[_n_f16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svinsr%5B_n_f16%5D

### Signature (source notation)

```c
svfloat16_t svinsr[_n_f16](svfloat16_t op1, float16_t op2);
```

### Description

Insert scalar into shifted vector

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Insert element

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
  "return_base_type": "float",
  "element_bit_size": "16",
  "value": "svfloat16_t"
}
```

### Argument preparation and constraints

```json
{
  "op1": {
    "register": "Ztied1.H"
  },
  "op2": {
    "register": "Hop2|Wop2"
  }
}
```

### Result mapping

```json
[
  {
    "Ztied1.H": "result"
  }
]
```

### Instruction mapping

When op2 is in a GP register, this intrinsic compiles to:

```asm
INSR Ztied1.H, Wop2  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/INSR--scalar---Insert-general-purpose-register-in-shifted-vector-

When op2 is in an FP register, this intrinsic compiles to:

```asm
INSR Ztied1.H, Hop2  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/INSR--SIMD-FP-scalar---Insert-SIMD-FP-scalar-register-in-shifted-vector-

### Operation

Source operation ID: `SveOperation_svinsr_n_bf16`

**Operation**



Return a vector in which:




- Element 0 contains `op2`.
- For all *i* > 0, element *i* contains `op1[i - 1]`.



**[1]** If instead `result` is in a different register from the inputs, the compiler can add a preceding [MOVPRFX (unpredicated)](https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--) instruction

## svinsr[_n_f32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svinsr%5B_n_f32%5D

### Signature (source notation)

```c
svfloat32_t svinsr[_n_f32](svfloat32_t op1, float32_t op2);
```

### Description

Insert scalar into shifted vector

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Insert element

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
  "return_base_type": "float",
  "element_bit_size": "32",
  "value": "svfloat32_t"
}
```

### Argument preparation and constraints

```json
{
  "op1": {
    "register": "Ztied1.S"
  },
  "op2": {
    "register": "Sop2|Wop2"
  }
}
```

### Result mapping

```json
[
  {
    "Ztied1.S": "result"
  }
]
```

### Instruction mapping

When op2 is in a GP register, this intrinsic compiles to:

```asm
INSR Ztied1.S, Wop2  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/INSR--scalar---Insert-general-purpose-register-in-shifted-vector-

When op2 is in an FP register, this intrinsic compiles to:

```asm
INSR Ztied1.S, Sop2  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/INSR--SIMD-FP-scalar---Insert-SIMD-FP-scalar-register-in-shifted-vector-

### Operation

Source operation ID: `SveOperation_svinsr_n_bf16`

**Operation**



Return a vector in which:




- Element 0 contains `op2`.
- For all *i* > 0, element *i* contains `op1[i - 1]`.



**[1]** If instead `result` is in a different register from the inputs, the compiler can add a preceding [MOVPRFX (unpredicated)](https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--) instruction

## svinsr[_n_f64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svinsr%5B_n_f64%5D

### Signature (source notation)

```c
svfloat64_t svinsr[_n_f64](svfloat64_t op1, float64_t op2);
```

### Description

Insert scalar into shifted vector

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Insert element

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
  "return_base_type": "float",
  "element_bit_size": "64",
  "value": "svfloat64_t"
}
```

### Argument preparation and constraints

```json
{
  "op1": {
    "register": "Ztied1.D"
  },
  "op2": {
    "register": "Dop2|Xop2"
  }
}
```

### Result mapping

```json
[
  {
    "Ztied1.D": "result"
  }
]
```

### Instruction mapping

When op2 is in a GP register, this intrinsic compiles to:

```asm
INSR Ztied1.D, Xop2  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/INSR--scalar---Insert-general-purpose-register-in-shifted-vector-

When op2 is in an FP register, this intrinsic compiles to:

```asm
INSR Ztied1.D, Dop2  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/INSR--SIMD-FP-scalar---Insert-SIMD-FP-scalar-register-in-shifted-vector-

### Operation

Source operation ID: `SveOperation_svinsr_n_bf16`

**Operation**



Return a vector in which:




- Element 0 contains `op2`.
- For all *i* > 0, element *i* contains `op1[i - 1]`.



**[1]** If instead `result` is in a different register from the inputs, the compiler can add a preceding [MOVPRFX (unpredicated)](https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--) instruction

## svinsr[_n_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svinsr%5B_n_s16%5D

### Signature (source notation)

```c
svint16_t svinsr[_n_s16](svint16_t op1, int16_t op2);
```

### Description

Insert scalar into shifted vector

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Insert element

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
    "register": "Ztied1.H"
  },
  "op2": {
    "register": "Hop2|Wop2"
  }
}
```

### Result mapping

```json
[
  {
    "Ztied1.H": "result"
  }
]
```

### Instruction mapping

When op2 is in a GP register, this intrinsic compiles to:

```asm
INSR Ztied1.H, Wop2  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/INSR--scalar---Insert-general-purpose-register-in-shifted-vector-

When op2 is in an FP register, this intrinsic compiles to:

```asm
INSR Ztied1.H, Hop2  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/INSR--SIMD-FP-scalar---Insert-SIMD-FP-scalar-register-in-shifted-vector-

### Operation

Source operation ID: `SveOperation_svinsr_n_bf16`

**Operation**



Return a vector in which:




- Element 0 contains `op2`.
- For all *i* > 0, element *i* contains `op1[i - 1]`.



**[1]** If instead `result` is in a different register from the inputs, the compiler can add a preceding [MOVPRFX (unpredicated)](https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--) instruction

## svinsr[_n_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svinsr%5B_n_s32%5D

### Signature (source notation)

```c
svint32_t svinsr[_n_s32](svint32_t op1, int32_t op2);
```

### Description

Insert scalar into shifted vector

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Insert element

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
    "register": "Ztied1.S"
  },
  "op2": {
    "register": "Sop2|Wop2"
  }
}
```

### Result mapping

```json
[
  {
    "Ztied1.S": "result"
  }
]
```

### Instruction mapping

When op2 is in a GP register, this intrinsic compiles to:

```asm
INSR Ztied1.S, Wop2  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/INSR--scalar---Insert-general-purpose-register-in-shifted-vector-

When op2 is in an FP register, this intrinsic compiles to:

```asm
INSR Ztied1.S, Sop2  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/INSR--SIMD-FP-scalar---Insert-SIMD-FP-scalar-register-in-shifted-vector-

### Operation

Source operation ID: `SveOperation_svinsr_n_bf16`

**Operation**



Return a vector in which:




- Element 0 contains `op2`.
- For all *i* > 0, element *i* contains `op1[i - 1]`.



**[1]** If instead `result` is in a different register from the inputs, the compiler can add a preceding [MOVPRFX (unpredicated)](https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--) instruction

## svinsr[_n_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svinsr%5B_n_s64%5D

### Signature (source notation)

```c
svint64_t svinsr[_n_s64](svint64_t op1, int64_t op2);
```

### Description

Insert scalar into shifted vector

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Insert element

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
    "register": "Ztied1.D"
  },
  "op2": {
    "register": "Dop2|Xop2"
  }
}
```

### Result mapping

```json
[
  {
    "Ztied1.D": "result"
  }
]
```

### Instruction mapping

When op2 is in a GP register, this intrinsic compiles to:

```asm
INSR Ztied1.D, Xop2  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/INSR--scalar---Insert-general-purpose-register-in-shifted-vector-

When op2 is in an FP register, this intrinsic compiles to:

```asm
INSR Ztied1.D, Dop2  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/INSR--SIMD-FP-scalar---Insert-SIMD-FP-scalar-register-in-shifted-vector-

### Operation

Source operation ID: `SveOperation_svinsr_n_bf16`

**Operation**



Return a vector in which:




- Element 0 contains `op2`.
- For all *i* > 0, element *i* contains `op1[i - 1]`.



**[1]** If instead `result` is in a different register from the inputs, the compiler can add a preceding [MOVPRFX (unpredicated)](https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--) instruction

## svinsr[_n_s8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svinsr%5B_n_s8%5D

### Signature (source notation)

```c
svint8_t svinsr[_n_s8](svint8_t op1, int8_t op2);
```

### Description

Insert scalar into shifted vector

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Insert element

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
    "register": "Ztied1.B"
  },
  "op2": {
    "register": "Bop2|Wop2"
  }
}
```

### Result mapping

```json
[
  {
    "Ztied1.B": "result"
  }
]
```

### Instruction mapping

When op2 is in a GP register, this intrinsic compiles to:

```asm
INSR Ztied1.B, Wop2  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/INSR--scalar---Insert-general-purpose-register-in-shifted-vector-

When op2 is in an FP register, this intrinsic compiles to:

```asm
INSR Ztied1.B, Bop2  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/INSR--SIMD-FP-scalar---Insert-SIMD-FP-scalar-register-in-shifted-vector-

### Operation

Source operation ID: `SveOperation_svinsr_n_bf16`

**Operation**



Return a vector in which:




- Element 0 contains `op2`.
- For all *i* > 0, element *i* contains `op1[i - 1]`.



**[1]** If instead `result` is in a different register from the inputs, the compiler can add a preceding [MOVPRFX (unpredicated)](https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--) instruction

## svinsr[_n_u16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svinsr%5B_n_u16%5D

### Signature (source notation)

```c
svuint16_t svinsr[_n_u16](svuint16_t op1, uint16_t op2);
```

### Description

Insert scalar into shifted vector

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Insert element

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
  "op1": {
    "register": "Ztied1.H"
  },
  "op2": {
    "register": "Hop2|Wop2"
  }
}
```

### Result mapping

```json
[
  {
    "Ztied1.H": "result"
  }
]
```

### Instruction mapping

When op2 is in a GP register, this intrinsic compiles to:

```asm
INSR Ztied1.H, Wop2  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/INSR--scalar---Insert-general-purpose-register-in-shifted-vector-

When op2 is in an FP register, this intrinsic compiles to:

```asm
INSR Ztied1.H, Hop2  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/INSR--SIMD-FP-scalar---Insert-SIMD-FP-scalar-register-in-shifted-vector-

### Operation

Source operation ID: `SveOperation_svinsr_n_bf16`

**Operation**



Return a vector in which:




- Element 0 contains `op2`.
- For all *i* > 0, element *i* contains `op1[i - 1]`.



**[1]** If instead `result` is in a different register from the inputs, the compiler can add a preceding [MOVPRFX (unpredicated)](https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--) instruction

## svinsr[_n_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svinsr%5B_n_u32%5D

### Signature (source notation)

```c
svuint32_t svinsr[_n_u32](svuint32_t op1, uint32_t op2);
```

### Description

Insert scalar into shifted vector

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Insert element

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
    "register": "Ztied1.S"
  },
  "op2": {
    "register": "Sop2|Wop2"
  }
}
```

### Result mapping

```json
[
  {
    "Ztied1.S": "result"
  }
]
```

### Instruction mapping

When op2 is in a GP register, this intrinsic compiles to:

```asm
INSR Ztied1.S, Wop2  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/INSR--scalar---Insert-general-purpose-register-in-shifted-vector-

When op2 is in an FP register, this intrinsic compiles to:

```asm
INSR Ztied1.S, Sop2  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/INSR--SIMD-FP-scalar---Insert-SIMD-FP-scalar-register-in-shifted-vector-

### Operation

Source operation ID: `SveOperation_svinsr_n_bf16`

**Operation**



Return a vector in which:




- Element 0 contains `op2`.
- For all *i* > 0, element *i* contains `op1[i - 1]`.



**[1]** If instead `result` is in a different register from the inputs, the compiler can add a preceding [MOVPRFX (unpredicated)](https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--) instruction

## svinsr[_n_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svinsr%5B_n_u64%5D

### Signature (source notation)

```c
svuint64_t svinsr[_n_u64](svuint64_t op1, uint64_t op2);
```

### Description

Insert scalar into shifted vector

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Insert element

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
    "register": "Ztied1.D"
  },
  "op2": {
    "register": "Dop2|Xop2"
  }
}
```

### Result mapping

```json
[
  {
    "Ztied1.D": "result"
  }
]
```

### Instruction mapping

When op2 is in a GP register, this intrinsic compiles to:

```asm
INSR Ztied1.D, Xop2  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/INSR--scalar---Insert-general-purpose-register-in-shifted-vector-

When op2 is in an FP register, this intrinsic compiles to:

```asm
INSR Ztied1.D, Dop2  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/INSR--SIMD-FP-scalar---Insert-SIMD-FP-scalar-register-in-shifted-vector-

### Operation

Source operation ID: `SveOperation_svinsr_n_bf16`

**Operation**



Return a vector in which:




- Element 0 contains `op2`.
- For all *i* > 0, element *i* contains `op1[i - 1]`.



**[1]** If instead `result` is in a different register from the inputs, the compiler can add a preceding [MOVPRFX (unpredicated)](https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--) instruction

## svinsr[_n_u8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svinsr%5B_n_u8%5D

### Signature (source notation)

```c
svuint8_t svinsr[_n_u8](svuint8_t op1, uint8_t op2);
```

### Description

Insert scalar into shifted vector

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Insert element

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
  "op1": {
    "register": "Ztied1.B"
  },
  "op2": {
    "register": "Bop2|Wop2"
  }
}
```

### Result mapping

```json
[
  {
    "Ztied1.B": "result"
  }
]
```

### Instruction mapping

When op2 is in a GP register, this intrinsic compiles to:

```asm
INSR Ztied1.B, Wop2  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/INSR--scalar---Insert-general-purpose-register-in-shifted-vector-

When op2 is in an FP register, this intrinsic compiles to:

```asm
INSR Ztied1.B, Bop2  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/INSR--SIMD-FP-scalar---Insert-SIMD-FP-scalar-register-in-shifted-vector-

### Operation

Source operation ID: `SveOperation_svinsr_n_bf16`

**Operation**



Return a vector in which:




- Element 0 contains `op2`.
- For all *i* > 0, element *i* contains `op1[i - 1]`.



**[1]** If instead `result` is in a different register from the inputs, the compiler can add a preceding [MOVPRFX (unpredicated)](https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--) instruction

