# SME / Predication / Element selection / Extract last active element — Part 1

## svclastb[_bf16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svclastb%5B_bf16%5D

### Signature (source notation)

```c
svbfloat16_t svclastb[_bf16](svbool_t pg, svbfloat16_t fallback, svbfloat16_t data);
```

### Description

Conditionally extract last element

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Predication / Element selection / Extract last active element

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
  "pg": {
    "register": "Pg"
  },
  "fallback": {
    "register": "Zfallback.H|Ztied.H"
  },
  "data": {
    "register": "Zdata.H"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.H|Ztied.H": "result"
  }
]
```

### Instruction mapping

When result and fallback are in the same register, this intrinsic compiles to:

```asm
CLASTB Ztied.H, Pg, Ztied.H, Zdata.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CLASTB--vectors---Conditionally-extract-last-element-to-vector-register-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zfallback
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
CLASTB Zresult.H, Pg, Zresult.H, Zdata.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CLASTB--vectors---Conditionally-extract-last-element-to-vector-register-

### Operation

Source operation ID: `SveOperation_svclastb_bf16`

**Operation**




- If no elements are active, return `fallback`.
- Otherwise, duplicate and return the last active element of `data`.

## svclastb[_f16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svclastb%5B_f16%5D

### Signature (source notation)

```c
svfloat16_t svclastb[_f16](svbool_t pg, svfloat16_t fallback, svfloat16_t data);
```

### Description

Conditionally extract last element

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Predication / Element selection / Extract last active element

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
  "pg": {
    "register": "Pg"
  },
  "fallback": {
    "register": "Zfallback.H|Ztied.H"
  },
  "data": {
    "register": "Zdata.H"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.H|Ztied.H": "result"
  }
]
```

### Instruction mapping

When result and fallback are in the same register, this intrinsic compiles to:

```asm
CLASTB Ztied.H, Pg, Ztied.H, Zdata.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CLASTB--vectors---Conditionally-extract-last-element-to-vector-register-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zfallback
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
CLASTB Zresult.H, Pg, Zresult.H, Zdata.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CLASTB--vectors---Conditionally-extract-last-element-to-vector-register-

### Operation

Source operation ID: `SveOperation_svclastb_bf16`

**Operation**




- If no elements are active, return `fallback`.
- Otherwise, duplicate and return the last active element of `data`.

## svclastb[_f32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svclastb%5B_f32%5D

### Signature (source notation)

```c
svfloat32_t svclastb[_f32](svbool_t pg, svfloat32_t fallback, svfloat32_t data);
```

### Description

Conditionally extract last element

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Predication / Element selection / Extract last active element

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
  "pg": {
    "register": "Pg"
  },
  "fallback": {
    "register": "Zfallback.S|Ztied.S"
  },
  "data": {
    "register": "Zdata.S"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.S|Ztied.S": "result"
  }
]
```

### Instruction mapping

When result and fallback are in the same register, this intrinsic compiles to:

```asm
CLASTB Ztied.S, Pg, Ztied.S, Zdata.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CLASTB--vectors---Conditionally-extract-last-element-to-vector-register-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zfallback
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
CLASTB Zresult.S, Pg, Zresult.S, Zdata.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CLASTB--vectors---Conditionally-extract-last-element-to-vector-register-

### Operation

Source operation ID: `SveOperation_svclastb_bf16`

**Operation**




- If no elements are active, return `fallback`.
- Otherwise, duplicate and return the last active element of `data`.

## svclastb[_f64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svclastb%5B_f64%5D

### Signature (source notation)

```c
svfloat64_t svclastb[_f64](svbool_t pg, svfloat64_t fallback, svfloat64_t data);
```

### Description

Conditionally extract last element

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Predication / Element selection / Extract last active element

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
  "pg": {
    "register": "Pg"
  },
  "fallback": {
    "register": "Zfallback.D|Ztied.D"
  },
  "data": {
    "register": "Zdata.D"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.D|Ztied.D": "result"
  }
]
```

### Instruction mapping

When result and fallback are in the same register, this intrinsic compiles to:

```asm
CLASTB Ztied.D, Pg, Ztied.D, Zdata.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CLASTB--vectors---Conditionally-extract-last-element-to-vector-register-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zfallback
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
CLASTB Zresult.D, Pg, Zresult.D, Zdata.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CLASTB--vectors---Conditionally-extract-last-element-to-vector-register-

### Operation

Source operation ID: `SveOperation_svclastb_bf16`

**Operation**




- If no elements are active, return `fallback`.
- Otherwise, duplicate and return the last active element of `data`.

## svclastb[_n_bf16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svclastb%5B_n_bf16%5D

### Signature (source notation)

```c
bfloat16_t svclastb[_n_bf16](svbool_t pg, bfloat16_t fallback, svbfloat16_t data);
```

### Description

Conditionally extract last element

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Predication / Element selection / Extract last active element

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
  "value": "bfloat16_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Pg"
  },
  "fallback": {
    "register": "Htied|Wtied"
  },
  "data": {
    "register": "Zdata.H"
  }
}
```

### Result mapping

```json
[
  {
    "Htied|Wtied": "result"
  }
]
```

### Instruction mapping

When result and fallback are in GP registers, this intrinsic compiles to:

```asm
CLASTB Wtied, Pg, Wtied, Zdata.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CLASTB--scalar---Conditionally-extract-last-element-to-general-purpose-register-

When result and fallback are in FP registers, this intrinsic compiles to:

```asm
CLASTB Htied, Pg, Htied, Zdata.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CLASTB--SIMD-FP-scalar---Conditionally-extract-last-element-to-SIMD-FP-scalar-register-

### Operation

Source operation ID: `SveOperation_svclastb_n_bf16`

**Operation**




- If no elements are active, return `fallback`.
- Otherwise, return the last active element of `data`.

## svclastb[_n_f16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svclastb%5B_n_f16%5D

### Signature (source notation)

```c
float16_t svclastb[_n_f16](svbool_t pg, float16_t fallback, svfloat16_t data);
```

### Description

Conditionally extract last element

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Predication / Element selection / Extract last active element

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
  "value": "float16_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Pg"
  },
  "fallback": {
    "register": "Htied|Wtied"
  },
  "data": {
    "register": "Zdata.H"
  }
}
```

### Result mapping

```json
[
  {
    "Htied|Wtied": "result"
  }
]
```

### Instruction mapping

When result and fallback are in GP registers, this intrinsic compiles to:

```asm
CLASTB Wtied, Pg, Wtied, Zdata.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CLASTB--scalar---Conditionally-extract-last-element-to-general-purpose-register-

When result and fallback are in FP registers, this intrinsic compiles to:

```asm
CLASTB Htied, Pg, Htied, Zdata.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CLASTB--SIMD-FP-scalar---Conditionally-extract-last-element-to-SIMD-FP-scalar-register-

### Operation

Source operation ID: `SveOperation_svclastb_n_bf16`

**Operation**




- If no elements are active, return `fallback`.
- Otherwise, return the last active element of `data`.

## svclastb[_n_f32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svclastb%5B_n_f32%5D

### Signature (source notation)

```c
float32_t svclastb[_n_f32](svbool_t pg, float32_t fallback, svfloat32_t data);
```

### Description

Conditionally extract last element

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Predication / Element selection / Extract last active element

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
  "value": "float32_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Pg"
  },
  "fallback": {
    "register": "Stied|Wtied"
  },
  "data": {
    "register": "Zdata.S"
  }
}
```

### Result mapping

```json
[
  {
    "Stied|Wtied": "result"
  }
]
```

### Instruction mapping

When result and fallback are in GP registers, this intrinsic compiles to:

```asm
CLASTB Wtied, Pg, Wtied, Zdata.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CLASTB--scalar---Conditionally-extract-last-element-to-general-purpose-register-

When result and fallback are in FP registers, this intrinsic compiles to:

```asm
CLASTB Stied, Pg, Stied, Zdata.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CLASTB--SIMD-FP-scalar---Conditionally-extract-last-element-to-SIMD-FP-scalar-register-

### Operation

Source operation ID: `SveOperation_svclastb_n_bf16`

**Operation**




- If no elements are active, return `fallback`.
- Otherwise, return the last active element of `data`.

## svclastb[_n_f64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svclastb%5B_n_f64%5D

### Signature (source notation)

```c
float64_t svclastb[_n_f64](svbool_t pg, float64_t fallback, svfloat64_t data);
```

### Description

Conditionally extract last element

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Predication / Element selection / Extract last active element

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
  "value": "float64_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Pg"
  },
  "fallback": {
    "register": "Dtied|Xtied"
  },
  "data": {
    "register": "Zdata.D"
  }
}
```

### Result mapping

```json
[
  {
    "Dtied|Xtied": "result"
  }
]
```

### Instruction mapping

When result and fallback are in GP registers, this intrinsic compiles to:

```asm
CLASTB Xtied, Pg, Xtied, Zdata.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CLASTB--scalar---Conditionally-extract-last-element-to-general-purpose-register-

When result and fallback are in FP registers, this intrinsic compiles to:

```asm
CLASTB Dtied, Pg, Dtied, Zdata.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CLASTB--SIMD-FP-scalar---Conditionally-extract-last-element-to-SIMD-FP-scalar-register-

### Operation

Source operation ID: `SveOperation_svclastb_n_bf16`

**Operation**




- If no elements are active, return `fallback`.
- Otherwise, return the last active element of `data`.

## svclastb[_n_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svclastb%5B_n_s16%5D

### Signature (source notation)

```c
int16_t svclastb[_n_s16](svbool_t pg, int16_t fallback, svint16_t data);
```

### Description

Conditionally extract last element

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Predication / Element selection / Extract last active element

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
  "value": "int16_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Pg"
  },
  "fallback": {
    "register": "Htied|Wtied"
  },
  "data": {
    "register": "Zdata.H"
  }
}
```

### Result mapping

```json
[
  {
    "Htied|Wtied": "result"
  }
]
```

### Instruction mapping

When result and fallback are in GP registers, this intrinsic compiles to:

```asm
CLASTB Wtied, Pg, Wtied, Zdata.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CLASTB--scalar---Conditionally-extract-last-element-to-general-purpose-register-

When result and fallback are in FP registers, this intrinsic compiles to:

```asm
CLASTB Htied, Pg, Htied, Zdata.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CLASTB--SIMD-FP-scalar---Conditionally-extract-last-element-to-SIMD-FP-scalar-register-

### Operation

Source operation ID: `SveOperation_svclastb_n_bf16`

**Operation**




- If no elements are active, return `fallback`.
- Otherwise, return the last active element of `data`.

## svclastb[_n_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svclastb%5B_n_s32%5D

### Signature (source notation)

```c
int32_t svclastb[_n_s32](svbool_t pg, int32_t fallback, svint32_t data);
```

### Description

Conditionally extract last element

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Predication / Element selection / Extract last active element

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
  "value": "int32_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Pg"
  },
  "fallback": {
    "register": "Stied|Wtied"
  },
  "data": {
    "register": "Zdata.S"
  }
}
```

### Result mapping

```json
[
  {
    "Stied|Wtied": "result"
  }
]
```

### Instruction mapping

When result and fallback are in GP registers, this intrinsic compiles to:

```asm
CLASTB Wtied, Pg, Wtied, Zdata.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CLASTB--scalar---Conditionally-extract-last-element-to-general-purpose-register-

When result and fallback are in FP registers, this intrinsic compiles to:

```asm
CLASTB Stied, Pg, Stied, Zdata.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CLASTB--SIMD-FP-scalar---Conditionally-extract-last-element-to-SIMD-FP-scalar-register-

### Operation

Source operation ID: `SveOperation_svclastb_n_bf16`

**Operation**




- If no elements are active, return `fallback`.
- Otherwise, return the last active element of `data`.

## svclastb[_n_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svclastb%5B_n_s64%5D

### Signature (source notation)

```c
int64_t svclastb[_n_s64](svbool_t pg, int64_t fallback, svint64_t data);
```

### Description

Conditionally extract last element

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Predication / Element selection / Extract last active element

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
  "value": "int64_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Pg"
  },
  "fallback": {
    "register": "Dtied|Xtied"
  },
  "data": {
    "register": "Zdata.D"
  }
}
```

### Result mapping

```json
[
  {
    "Dtied|Xtied": "result"
  }
]
```

### Instruction mapping

When result and fallback are in GP registers, this intrinsic compiles to:

```asm
CLASTB Xtied, Pg, Xtied, Zdata.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CLASTB--scalar---Conditionally-extract-last-element-to-general-purpose-register-

When result and fallback are in FP registers, this intrinsic compiles to:

```asm
CLASTB Dtied, Pg, Dtied, Zdata.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CLASTB--SIMD-FP-scalar---Conditionally-extract-last-element-to-SIMD-FP-scalar-register-

### Operation

Source operation ID: `SveOperation_svclastb_n_bf16`

**Operation**




- If no elements are active, return `fallback`.
- Otherwise, return the last active element of `data`.

## svclastb[_n_s8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svclastb%5B_n_s8%5D

### Signature (source notation)

```c
int8_t svclastb[_n_s8](svbool_t pg, int8_t fallback, svint8_t data);
```

### Description

Conditionally extract last element

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Predication / Element selection / Extract last active element

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
  "value": "int8_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Pg"
  },
  "fallback": {
    "register": "Btied|Wtied"
  },
  "data": {
    "register": "Zdata.B"
  }
}
```

### Result mapping

```json
[
  {
    "Btied|Wtied": "result"
  }
]
```

### Instruction mapping

When result and fallback are in GP registers, this intrinsic compiles to:

```asm
CLASTB Wtied, Pg, Wtied, Zdata.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CLASTB--scalar---Conditionally-extract-last-element-to-general-purpose-register-

When result and fallback are in FP registers, this intrinsic compiles to:

```asm
CLASTB Btied, Pg, Btied, Zdata.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CLASTB--SIMD-FP-scalar---Conditionally-extract-last-element-to-SIMD-FP-scalar-register-

### Operation

Source operation ID: `SveOperation_svclastb_n_bf16`

**Operation**




- If no elements are active, return `fallback`.
- Otherwise, return the last active element of `data`.

## svclastb[_n_u16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svclastb%5B_n_u16%5D

### Signature (source notation)

```c
uint16_t svclastb[_n_u16](svbool_t pg, uint16_t fallback, svuint16_t data);
```

### Description

Conditionally extract last element

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Predication / Element selection / Extract last active element

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
  "value": "uint16_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Pg"
  },
  "fallback": {
    "register": "Htied|Wtied"
  },
  "data": {
    "register": "Zdata.H"
  }
}
```

### Result mapping

```json
[
  {
    "Htied|Wtied": "result"
  }
]
```

### Instruction mapping

When result and fallback are in GP registers, this intrinsic compiles to:

```asm
CLASTB Wtied, Pg, Wtied, Zdata.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CLASTB--scalar---Conditionally-extract-last-element-to-general-purpose-register-

When result and fallback are in FP registers, this intrinsic compiles to:

```asm
CLASTB Htied, Pg, Htied, Zdata.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CLASTB--SIMD-FP-scalar---Conditionally-extract-last-element-to-SIMD-FP-scalar-register-

### Operation

Source operation ID: `SveOperation_svclastb_n_bf16`

**Operation**




- If no elements are active, return `fallback`.
- Otherwise, return the last active element of `data`.

## svclastb[_n_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svclastb%5B_n_u32%5D

### Signature (source notation)

```c
uint32_t svclastb[_n_u32](svbool_t pg, uint32_t fallback, svuint32_t data);
```

### Description

Conditionally extract last element

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Predication / Element selection / Extract last active element

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
  "value": "uint32_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Pg"
  },
  "fallback": {
    "register": "Stied|Wtied"
  },
  "data": {
    "register": "Zdata.S"
  }
}
```

### Result mapping

```json
[
  {
    "Stied|Wtied": "result"
  }
]
```

### Instruction mapping

When result and fallback are in GP registers, this intrinsic compiles to:

```asm
CLASTB Wtied, Pg, Wtied, Zdata.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CLASTB--scalar---Conditionally-extract-last-element-to-general-purpose-register-

When result and fallback are in FP registers, this intrinsic compiles to:

```asm
CLASTB Stied, Pg, Stied, Zdata.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CLASTB--SIMD-FP-scalar---Conditionally-extract-last-element-to-SIMD-FP-scalar-register-

### Operation

Source operation ID: `SveOperation_svclastb_n_bf16`

**Operation**




- If no elements are active, return `fallback`.
- Otherwise, return the last active element of `data`.

## svclastb[_n_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svclastb%5B_n_u64%5D

### Signature (source notation)

```c
uint64_t svclastb[_n_u64](svbool_t pg, uint64_t fallback, svuint64_t data);
```

### Description

Conditionally extract last element

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Predication / Element selection / Extract last active element

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
  "value": "uint64_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Pg"
  },
  "fallback": {
    "register": "Dtied|Xtied"
  },
  "data": {
    "register": "Zdata.D"
  }
}
```

### Result mapping

```json
[
  {
    "Dtied|Xtied": "result"
  }
]
```

### Instruction mapping

When result and fallback are in GP registers, this intrinsic compiles to:

```asm
CLASTB Xtied, Pg, Xtied, Zdata.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CLASTB--scalar---Conditionally-extract-last-element-to-general-purpose-register-

When result and fallback are in FP registers, this intrinsic compiles to:

```asm
CLASTB Dtied, Pg, Dtied, Zdata.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CLASTB--SIMD-FP-scalar---Conditionally-extract-last-element-to-SIMD-FP-scalar-register-

### Operation

Source operation ID: `SveOperation_svclastb_n_bf16`

**Operation**




- If no elements are active, return `fallback`.
- Otherwise, return the last active element of `data`.

## svclastb[_n_u8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svclastb%5B_n_u8%5D

### Signature (source notation)

```c
uint8_t svclastb[_n_u8](svbool_t pg, uint8_t fallback, svuint8_t data);
```

### Description

Conditionally extract last element

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Predication / Element selection / Extract last active element

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
  "value": "uint8_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Pg"
  },
  "fallback": {
    "register": "Btied|Wtied"
  },
  "data": {
    "register": "Zdata.B"
  }
}
```

### Result mapping

```json
[
  {
    "Btied|Wtied": "result"
  }
]
```

### Instruction mapping

When result and fallback are in GP registers, this intrinsic compiles to:

```asm
CLASTB Wtied, Pg, Wtied, Zdata.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CLASTB--scalar---Conditionally-extract-last-element-to-general-purpose-register-

When result and fallback are in FP registers, this intrinsic compiles to:

```asm
CLASTB Btied, Pg, Btied, Zdata.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CLASTB--SIMD-FP-scalar---Conditionally-extract-last-element-to-SIMD-FP-scalar-register-

### Operation

Source operation ID: `SveOperation_svclastb_n_bf16`

**Operation**




- If no elements are active, return `fallback`.
- Otherwise, return the last active element of `data`.

## svclastb[_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svclastb%5B_s16%5D

### Signature (source notation)

```c
svint16_t svclastb[_s16](svbool_t pg, svint16_t fallback, svint16_t data);
```

### Description

Conditionally extract last element

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Predication / Element selection / Extract last active element

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
  "fallback": {
    "register": "Zfallback.H|Ztied.H"
  },
  "data": {
    "register": "Zdata.H"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.H|Ztied.H": "result"
  }
]
```

### Instruction mapping

When result and fallback are in the same register, this intrinsic compiles to:

```asm
CLASTB Ztied.H, Pg, Ztied.H, Zdata.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CLASTB--vectors---Conditionally-extract-last-element-to-vector-register-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zfallback
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
CLASTB Zresult.H, Pg, Zresult.H, Zdata.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CLASTB--vectors---Conditionally-extract-last-element-to-vector-register-

### Operation

Source operation ID: `SveOperation_svclastb_bf16`

**Operation**




- If no elements are active, return `fallback`.
- Otherwise, duplicate and return the last active element of `data`.

## svclastb[_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svclastb%5B_s32%5D

### Signature (source notation)

```c
svint32_t svclastb[_s32](svbool_t pg, svint32_t fallback, svint32_t data);
```

### Description

Conditionally extract last element

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Predication / Element selection / Extract last active element

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
  "fallback": {
    "register": "Zfallback.S|Ztied.S"
  },
  "data": {
    "register": "Zdata.S"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.S|Ztied.S": "result"
  }
]
```

### Instruction mapping

When result and fallback are in the same register, this intrinsic compiles to:

```asm
CLASTB Ztied.S, Pg, Ztied.S, Zdata.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CLASTB--vectors---Conditionally-extract-last-element-to-vector-register-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zfallback
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
CLASTB Zresult.S, Pg, Zresult.S, Zdata.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CLASTB--vectors---Conditionally-extract-last-element-to-vector-register-

### Operation

Source operation ID: `SveOperation_svclastb_bf16`

**Operation**




- If no elements are active, return `fallback`.
- Otherwise, duplicate and return the last active element of `data`.

## svclastb[_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svclastb%5B_s64%5D

### Signature (source notation)

```c
svint64_t svclastb[_s64](svbool_t pg, svint64_t fallback, svint64_t data);
```

### Description

Conditionally extract last element

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Predication / Element selection / Extract last active element

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
  "fallback": {
    "register": "Zfallback.D|Ztied.D"
  },
  "data": {
    "register": "Zdata.D"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.D|Ztied.D": "result"
  }
]
```

### Instruction mapping

When result and fallback are in the same register, this intrinsic compiles to:

```asm
CLASTB Ztied.D, Pg, Ztied.D, Zdata.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CLASTB--vectors---Conditionally-extract-last-element-to-vector-register-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zfallback
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
CLASTB Zresult.D, Pg, Zresult.D, Zdata.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CLASTB--vectors---Conditionally-extract-last-element-to-vector-register-

### Operation

Source operation ID: `SveOperation_svclastb_bf16`

**Operation**




- If no elements are active, return `fallback`.
- Otherwise, duplicate and return the last active element of `data`.

## svclastb[_s8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svclastb%5B_s8%5D

### Signature (source notation)

```c
svint8_t svclastb[_s8](svbool_t pg, svint8_t fallback, svint8_t data);
```

### Description

Conditionally extract last element

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Predication / Element selection / Extract last active element

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
  "fallback": {
    "register": "Zfallback.B|Ztied.B"
  },
  "data": {
    "register": "Zdata.B"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.B|Ztied.B": "result"
  }
]
```

### Instruction mapping

When result and fallback are in the same register, this intrinsic compiles to:

```asm
CLASTB Ztied.B, Pg, Ztied.B, Zdata.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CLASTB--vectors---Conditionally-extract-last-element-to-vector-register-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zfallback
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
CLASTB Zresult.B, Pg, Zresult.B, Zdata.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CLASTB--vectors---Conditionally-extract-last-element-to-vector-register-

### Operation

Source operation ID: `SveOperation_svclastb_bf16`

**Operation**




- If no elements are active, return `fallback`.
- Otherwise, duplicate and return the last active element of `data`.

## svclastb[_u16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svclastb%5B_u16%5D

### Signature (source notation)

```c
svuint16_t svclastb[_u16](svbool_t pg, svuint16_t fallback, svuint16_t data);
```

### Description

Conditionally extract last element

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Predication / Element selection / Extract last active element

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
  "fallback": {
    "register": "Zfallback.H|Ztied.H"
  },
  "data": {
    "register": "Zdata.H"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.H|Ztied.H": "result"
  }
]
```

### Instruction mapping

When result and fallback are in the same register, this intrinsic compiles to:

```asm
CLASTB Ztied.H, Pg, Ztied.H, Zdata.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CLASTB--vectors---Conditionally-extract-last-element-to-vector-register-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zfallback
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
CLASTB Zresult.H, Pg, Zresult.H, Zdata.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CLASTB--vectors---Conditionally-extract-last-element-to-vector-register-

### Operation

Source operation ID: `SveOperation_svclastb_bf16`

**Operation**




- If no elements are active, return `fallback`.
- Otherwise, duplicate and return the last active element of `data`.

## svclastb[_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svclastb%5B_u32%5D

### Signature (source notation)

```c
svuint32_t svclastb[_u32](svbool_t pg, svuint32_t fallback, svuint32_t data);
```

### Description

Conditionally extract last element

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Predication / Element selection / Extract last active element

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
  "fallback": {
    "register": "Zfallback.S|Ztied.S"
  },
  "data": {
    "register": "Zdata.S"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.S|Ztied.S": "result"
  }
]
```

### Instruction mapping

When result and fallback are in the same register, this intrinsic compiles to:

```asm
CLASTB Ztied.S, Pg, Ztied.S, Zdata.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CLASTB--vectors---Conditionally-extract-last-element-to-vector-register-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zfallback
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
CLASTB Zresult.S, Pg, Zresult.S, Zdata.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CLASTB--vectors---Conditionally-extract-last-element-to-vector-register-

### Operation

Source operation ID: `SveOperation_svclastb_bf16`

**Operation**




- If no elements are active, return `fallback`.
- Otherwise, duplicate and return the last active element of `data`.

## svclastb[_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svclastb%5B_u64%5D

### Signature (source notation)

```c
svuint64_t svclastb[_u64](svbool_t pg, svuint64_t fallback, svuint64_t data);
```

### Description

Conditionally extract last element

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Predication / Element selection / Extract last active element

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
  "fallback": {
    "register": "Zfallback.D|Ztied.D"
  },
  "data": {
    "register": "Zdata.D"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.D|Ztied.D": "result"
  }
]
```

### Instruction mapping

When result and fallback are in the same register, this intrinsic compiles to:

```asm
CLASTB Ztied.D, Pg, Ztied.D, Zdata.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CLASTB--vectors---Conditionally-extract-last-element-to-vector-register-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zfallback
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
CLASTB Zresult.D, Pg, Zresult.D, Zdata.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CLASTB--vectors---Conditionally-extract-last-element-to-vector-register-

### Operation

Source operation ID: `SveOperation_svclastb_bf16`

**Operation**




- If no elements are active, return `fallback`.
- Otherwise, duplicate and return the last active element of `data`.

## svclastb[_u8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svclastb%5B_u8%5D

### Signature (source notation)

```c
svuint8_t svclastb[_u8](svbool_t pg, svuint8_t fallback, svuint8_t data);
```

### Description

Conditionally extract last element

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Predication / Element selection / Extract last active element

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
  "fallback": {
    "register": "Zfallback.B|Ztied.B"
  },
  "data": {
    "register": "Zdata.B"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.B|Ztied.B": "result"
  }
]
```

### Instruction mapping

When result and fallback are in the same register, this intrinsic compiles to:

```asm
CLASTB Ztied.B, Pg, Ztied.B, Zdata.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CLASTB--vectors---Conditionally-extract-last-element-to-vector-register-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zfallback
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
CLASTB Zresult.B, Pg, Zresult.B, Zdata.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CLASTB--vectors---Conditionally-extract-last-element-to-vector-register-

### Operation

Source operation ID: `SveOperation_svclastb_bf16`

**Operation**




- If no elements are active, return `fallback`.
- Otherwise, duplicate and return the last active element of `data`.

## svlastb[_bf16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svlastb%5B_bf16%5D

### Signature (source notation)

```c
bfloat16_t svlastb[_bf16](svbool_t pg, svbfloat16_t op);
```

### Description

Extract last element

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Predication / Element selection / Extract last active element

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
  "value": "bfloat16_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Pg"
  },
  "op": {
    "register": "Zop.H"
  }
}
```

### Result mapping

```json
[
  {
    "Hresult|Wresult": "result"
  }
]
```

### Instruction mapping

When result is in a GP register, this intrinsic compiles to:

```asm
LASTB Wresult, Pg, Zop.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LASTB--scalar---Extract-last-element-to-general-purpose-register-

When result is in an FP register, this intrinsic compiles to:

```asm
LASTB Hresult, Pg, Zop.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LASTB--SIMD-FP-scalar---Extract-last-element-to-SIMD-FP-scalar-register-

### Operation

Source operation ID: `SveOperation_svlastb_bf16`

**Operation**




- If no elements are active, return the last element of `op`.
- Otherwise, return the last active element of `op`.

## svlastb[_f16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svlastb%5B_f16%5D

### Signature (source notation)

```c
float16_t svlastb[_f16](svbool_t pg, svfloat16_t op);
```

### Description

Extract last element

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Predication / Element selection / Extract last active element

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
  "value": "float16_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Pg"
  },
  "op": {
    "register": "Zop.H"
  }
}
```

### Result mapping

```json
[
  {
    "Hresult|Wresult": "result"
  }
]
```

### Instruction mapping

When result is in a GP register, this intrinsic compiles to:

```asm
LASTB Wresult, Pg, Zop.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LASTB--scalar---Extract-last-element-to-general-purpose-register-

When result is in an FP register, this intrinsic compiles to:

```asm
LASTB Hresult, Pg, Zop.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LASTB--SIMD-FP-scalar---Extract-last-element-to-SIMD-FP-scalar-register-

### Operation

Source operation ID: `SveOperation_svlastb_bf16`

**Operation**




- If no elements are active, return the last element of `op`.
- Otherwise, return the last active element of `op`.

## svlastb[_f32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svlastb%5B_f32%5D

### Signature (source notation)

```c
float32_t svlastb[_f32](svbool_t pg, svfloat32_t op);
```

### Description

Extract last element

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Predication / Element selection / Extract last active element

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
  "value": "float32_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Pg"
  },
  "op": {
    "register": "Zop.S"
  }
}
```

### Result mapping

```json
[
  {
    "Sresult|Wresult": "result"
  }
]
```

### Instruction mapping

When result is in a GP register, this intrinsic compiles to:

```asm
LASTB Wresult, Pg, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LASTB--scalar---Extract-last-element-to-general-purpose-register-

When result is in an FP register, this intrinsic compiles to:

```asm
LASTB Sresult, Pg, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LASTB--SIMD-FP-scalar---Extract-last-element-to-SIMD-FP-scalar-register-

### Operation

Source operation ID: `SveOperation_svlastb_bf16`

**Operation**




- If no elements are active, return the last element of `op`.
- Otherwise, return the last active element of `op`.

## svlastb[_f64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svlastb%5B_f64%5D

### Signature (source notation)

```c
float64_t svlastb[_f64](svbool_t pg, svfloat64_t op);
```

### Description

Extract last element

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Predication / Element selection / Extract last active element

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
  "value": "float64_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Pg"
  },
  "op": {
    "register": "Zop.D"
  }
}
```

### Result mapping

```json
[
  {
    "Dresult|Xresult": "result"
  }
]
```

### Instruction mapping

When result is in a GP register, this intrinsic compiles to:

```asm
LASTB Xresult, Pg, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LASTB--scalar---Extract-last-element-to-general-purpose-register-

When result is in an FP register, this intrinsic compiles to:

```asm
LASTB Dresult, Pg, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LASTB--SIMD-FP-scalar---Extract-last-element-to-SIMD-FP-scalar-register-

### Operation

Source operation ID: `SveOperation_svlastb_bf16`

**Operation**




- If no elements are active, return the last element of `op`.
- Otherwise, return the last active element of `op`.

## svlastb[_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svlastb%5B_s16%5D

### Signature (source notation)

```c
int16_t svlastb[_s16](svbool_t pg, svint16_t op);
```

### Description

Extract last element

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Predication / Element selection / Extract last active element

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
  "value": "int16_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Pg"
  },
  "op": {
    "register": "Zop.H"
  }
}
```

### Result mapping

```json
[
  {
    "Hresult|Wresult": "result"
  }
]
```

### Instruction mapping

When result is in a GP register, this intrinsic compiles to:

```asm
LASTB Wresult, Pg, Zop.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LASTB--scalar---Extract-last-element-to-general-purpose-register-

When result is in an FP register, this intrinsic compiles to:

```asm
LASTB Hresult, Pg, Zop.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LASTB--SIMD-FP-scalar---Extract-last-element-to-SIMD-FP-scalar-register-

### Operation

Source operation ID: `SveOperation_svlastb_bf16`

**Operation**




- If no elements are active, return the last element of `op`.
- Otherwise, return the last active element of `op`.

## svlastb[_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svlastb%5B_s32%5D

### Signature (source notation)

```c
int32_t svlastb[_s32](svbool_t pg, svint32_t op);
```

### Description

Extract last element

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Predication / Element selection / Extract last active element

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
  "value": "int32_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Pg"
  },
  "op": {
    "register": "Zop.S"
  }
}
```

### Result mapping

```json
[
  {
    "Sresult|Wresult": "result"
  }
]
```

### Instruction mapping

When result is in a GP register, this intrinsic compiles to:

```asm
LASTB Wresult, Pg, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LASTB--scalar---Extract-last-element-to-general-purpose-register-

When result is in an FP register, this intrinsic compiles to:

```asm
LASTB Sresult, Pg, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LASTB--SIMD-FP-scalar---Extract-last-element-to-SIMD-FP-scalar-register-

### Operation

Source operation ID: `SveOperation_svlastb_bf16`

**Operation**




- If no elements are active, return the last element of `op`.
- Otherwise, return the last active element of `op`.

## svlastb[_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svlastb%5B_s64%5D

### Signature (source notation)

```c
int64_t svlastb[_s64](svbool_t pg, svint64_t op);
```

### Description

Extract last element

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Predication / Element selection / Extract last active element

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
  "value": "int64_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Pg"
  },
  "op": {
    "register": "Zop.D"
  }
}
```

### Result mapping

```json
[
  {
    "Dresult|Xresult": "result"
  }
]
```

### Instruction mapping

When result is in a GP register, this intrinsic compiles to:

```asm
LASTB Xresult, Pg, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LASTB--scalar---Extract-last-element-to-general-purpose-register-

When result is in an FP register, this intrinsic compiles to:

```asm
LASTB Dresult, Pg, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LASTB--SIMD-FP-scalar---Extract-last-element-to-SIMD-FP-scalar-register-

### Operation

Source operation ID: `SveOperation_svlastb_bf16`

**Operation**




- If no elements are active, return the last element of `op`.
- Otherwise, return the last active element of `op`.

## svlastb[_s8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svlastb%5B_s8%5D

### Signature (source notation)

```c
int8_t svlastb[_s8](svbool_t pg, svint8_t op);
```

### Description

Extract last element

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Predication / Element selection / Extract last active element

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
  "value": "int8_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Pg"
  },
  "op": {
    "register": "Zop.B"
  }
}
```

### Result mapping

```json
[
  {
    "Bresult|Wresult": "result"
  }
]
```

### Instruction mapping

When result is in a GP register, this intrinsic compiles to:

```asm
LASTB Wresult, Pg, Zop.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LASTB--scalar---Extract-last-element-to-general-purpose-register-

When result is in an FP register, this intrinsic compiles to:

```asm
LASTB Bresult, Pg, Zop.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LASTB--SIMD-FP-scalar---Extract-last-element-to-SIMD-FP-scalar-register-

### Operation

Source operation ID: `SveOperation_svlastb_bf16`

**Operation**




- If no elements are active, return the last element of `op`.
- Otherwise, return the last active element of `op`.

## svlastb[_u16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svlastb%5B_u16%5D

### Signature (source notation)

```c
uint16_t svlastb[_u16](svbool_t pg, svuint16_t op);
```

### Description

Extract last element

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Predication / Element selection / Extract last active element

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
  "value": "uint16_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Pg"
  },
  "op": {
    "register": "Zop.H"
  }
}
```

### Result mapping

```json
[
  {
    "Hresult|Wresult": "result"
  }
]
```

### Instruction mapping

When result is in a GP register, this intrinsic compiles to:

```asm
LASTB Wresult, Pg, Zop.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LASTB--scalar---Extract-last-element-to-general-purpose-register-

When result is in an FP register, this intrinsic compiles to:

```asm
LASTB Hresult, Pg, Zop.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LASTB--SIMD-FP-scalar---Extract-last-element-to-SIMD-FP-scalar-register-

### Operation

Source operation ID: `SveOperation_svlastb_bf16`

**Operation**




- If no elements are active, return the last element of `op`.
- Otherwise, return the last active element of `op`.

## svlastb[_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svlastb%5B_u32%5D

### Signature (source notation)

```c
uint32_t svlastb[_u32](svbool_t pg, svuint32_t op);
```

### Description

Extract last element

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Predication / Element selection / Extract last active element

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
  "value": "uint32_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Pg"
  },
  "op": {
    "register": "Zop.S"
  }
}
```

### Result mapping

```json
[
  {
    "Sresult|Wresult": "result"
  }
]
```

### Instruction mapping

When result is in a GP register, this intrinsic compiles to:

```asm
LASTB Wresult, Pg, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LASTB--scalar---Extract-last-element-to-general-purpose-register-

When result is in an FP register, this intrinsic compiles to:

```asm
LASTB Sresult, Pg, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LASTB--SIMD-FP-scalar---Extract-last-element-to-SIMD-FP-scalar-register-

### Operation

Source operation ID: `SveOperation_svlastb_bf16`

**Operation**




- If no elements are active, return the last element of `op`.
- Otherwise, return the last active element of `op`.

## svlastb[_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svlastb%5B_u64%5D

### Signature (source notation)

```c
uint64_t svlastb[_u64](svbool_t pg, svuint64_t op);
```

### Description

Extract last element

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Predication / Element selection / Extract last active element

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
  "value": "uint64_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Pg"
  },
  "op": {
    "register": "Zop.D"
  }
}
```

### Result mapping

```json
[
  {
    "Dresult|Xresult": "result"
  }
]
```

### Instruction mapping

When result is in a GP register, this intrinsic compiles to:

```asm
LASTB Xresult, Pg, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LASTB--scalar---Extract-last-element-to-general-purpose-register-

When result is in an FP register, this intrinsic compiles to:

```asm
LASTB Dresult, Pg, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LASTB--SIMD-FP-scalar---Extract-last-element-to-SIMD-FP-scalar-register-

### Operation

Source operation ID: `SveOperation_svlastb_bf16`

**Operation**




- If no elements are active, return the last element of `op`.
- Otherwise, return the last active element of `op`.

## svlastb[_u8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svlastb%5B_u8%5D

### Signature (source notation)

```c
uint8_t svlastb[_u8](svbool_t pg, svuint8_t op);
```

### Description

Extract last element

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Predication / Element selection / Extract last active element

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
  "value": "uint8_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Pg"
  },
  "op": {
    "register": "Zop.B"
  }
}
```

### Result mapping

```json
[
  {
    "Bresult|Wresult": "result"
  }
]
```

### Instruction mapping

When result is in a GP register, this intrinsic compiles to:

```asm
LASTB Wresult, Pg, Zop.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LASTB--scalar---Extract-last-element-to-general-purpose-register-

When result is in an FP register, this intrinsic compiles to:

```asm
LASTB Bresult, Pg, Zop.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LASTB--SIMD-FP-scalar---Extract-last-element-to-SIMD-FP-scalar-register-

### Operation

Source operation ID: `SveOperation_svlastb_bf16`

**Operation**




- If no elements are active, return the last element of `op`.
- Otherwise, return the last active element of `op`.

