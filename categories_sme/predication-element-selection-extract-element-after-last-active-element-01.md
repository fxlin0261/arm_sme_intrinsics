# SME / Predication / Element selection / Extract element after last active element — Part 1

## svclasta[_bf16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svclasta%5B_bf16%5D

### Signature (source notation)

```c
svbfloat16_t svclasta[_bf16](svbool_t pg, svbfloat16_t fallback, svbfloat16_t data);
```

### Description

Conditionally extract element after last

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Predication / Element selection / Extract element after last active element

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
CLASTA Ztied.H, Pg, Ztied.H, Zdata.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CLASTA--vectors---Conditionally-extract-element-after-last-to-vector-register-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zfallback
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
CLASTA Zresult.H, Pg, Zresult.H, Zdata.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CLASTA--vectors---Conditionally-extract-element-after-last-to-vector-register-

### Operation

Source operation ID: `SveOperation_svclasta_bf16`

**Operation**




- If no elements are active, return `fallback`.
- If the last element is active, duplicate and return `data[0]`.
- Otherwise, duplicate and return the element after the last active element of `data`.

## svclasta[_f16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svclasta%5B_f16%5D

### Signature (source notation)

```c
svfloat16_t svclasta[_f16](svbool_t pg, svfloat16_t fallback, svfloat16_t data);
```

### Description

Conditionally extract element after last

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Predication / Element selection / Extract element after last active element

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
CLASTA Ztied.H, Pg, Ztied.H, Zdata.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CLASTA--vectors---Conditionally-extract-element-after-last-to-vector-register-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zfallback
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
CLASTA Zresult.H, Pg, Zresult.H, Zdata.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CLASTA--vectors---Conditionally-extract-element-after-last-to-vector-register-

### Operation

Source operation ID: `SveOperation_svclasta_bf16`

**Operation**




- If no elements are active, return `fallback`.
- If the last element is active, duplicate and return `data[0]`.
- Otherwise, duplicate and return the element after the last active element of `data`.

## svclasta[_f32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svclasta%5B_f32%5D

### Signature (source notation)

```c
svfloat32_t svclasta[_f32](svbool_t pg, svfloat32_t fallback, svfloat32_t data);
```

### Description

Conditionally extract element after last

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Predication / Element selection / Extract element after last active element

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
CLASTA Ztied.S, Pg, Ztied.S, Zdata.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CLASTA--vectors---Conditionally-extract-element-after-last-to-vector-register-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zfallback
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
CLASTA Zresult.S, Pg, Zresult.S, Zdata.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CLASTA--vectors---Conditionally-extract-element-after-last-to-vector-register-

### Operation

Source operation ID: `SveOperation_svclasta_bf16`

**Operation**




- If no elements are active, return `fallback`.
- If the last element is active, duplicate and return `data[0]`.
- Otherwise, duplicate and return the element after the last active element of `data`.

## svclasta[_f64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svclasta%5B_f64%5D

### Signature (source notation)

```c
svfloat64_t svclasta[_f64](svbool_t pg, svfloat64_t fallback, svfloat64_t data);
```

### Description

Conditionally extract element after last

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Predication / Element selection / Extract element after last active element

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
CLASTA Ztied.D, Pg, Ztied.D, Zdata.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CLASTA--vectors---Conditionally-extract-element-after-last-to-vector-register-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zfallback
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
CLASTA Zresult.D, Pg, Zresult.D, Zdata.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CLASTA--vectors---Conditionally-extract-element-after-last-to-vector-register-

### Operation

Source operation ID: `SveOperation_svclasta_bf16`

**Operation**




- If no elements are active, return `fallback`.
- If the last element is active, duplicate and return `data[0]`.
- Otherwise, duplicate and return the element after the last active element of `data`.

## svclasta[_n_bf16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svclasta%5B_n_bf16%5D

### Signature (source notation)

```c
bfloat16_t svclasta[_n_bf16](svbool_t pg, bfloat16_t fallback, svbfloat16_t data);
```

### Description

Conditionally extract element after last

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Predication / Element selection / Extract element after last active element

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
CLASTA Wtied, Pg, Wtied, Zdata.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CLASTA--scalar---Conditionally-extract-element-after-last-to-general-purpose-register-

When result and fallback are in FP registers, this intrinsic compiles to:

```asm
CLASTA Htied, Pg, Htied, Zdata.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CLASTA--SIMD-FP-scalar---Conditionally-extract-element-after-last-to-SIMD-FP-scalar-register-

### Operation

Source operation ID: `SveOperation_svclasta_n_bf16`

**Operation**




- If no elements are active, return `fallback`.
- If the last element is active, return `data[0]`.
- Otherwise, return the element after the last active element of `data`.

## svclasta[_n_f16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svclasta%5B_n_f16%5D

### Signature (source notation)

```c
float16_t svclasta[_n_f16](svbool_t pg, float16_t fallback, svfloat16_t data);
```

### Description

Conditionally extract element after last

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Predication / Element selection / Extract element after last active element

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
CLASTA Wtied, Pg, Wtied, Zdata.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CLASTA--scalar---Conditionally-extract-element-after-last-to-general-purpose-register-

When result and fallback are in FP registers, this intrinsic compiles to:

```asm
CLASTA Htied, Pg, Htied, Zdata.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CLASTA--SIMD-FP-scalar---Conditionally-extract-element-after-last-to-SIMD-FP-scalar-register-

### Operation

Source operation ID: `SveOperation_svclasta_n_bf16`

**Operation**




- If no elements are active, return `fallback`.
- If the last element is active, return `data[0]`.
- Otherwise, return the element after the last active element of `data`.

## svclasta[_n_f32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svclasta%5B_n_f32%5D

### Signature (source notation)

```c
float32_t svclasta[_n_f32](svbool_t pg, float32_t fallback, svfloat32_t data);
```

### Description

Conditionally extract element after last

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Predication / Element selection / Extract element after last active element

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
CLASTA Wtied, Pg, Wtied, Zdata.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CLASTA--scalar---Conditionally-extract-element-after-last-to-general-purpose-register-

When result and fallback are in FP registers, this intrinsic compiles to:

```asm
CLASTA Stied, Pg, Stied, Zdata.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CLASTA--SIMD-FP-scalar---Conditionally-extract-element-after-last-to-SIMD-FP-scalar-register-

### Operation

Source operation ID: `SveOperation_svclasta_n_bf16`

**Operation**




- If no elements are active, return `fallback`.
- If the last element is active, return `data[0]`.
- Otherwise, return the element after the last active element of `data`.

## svclasta[_n_f64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svclasta%5B_n_f64%5D

### Signature (source notation)

```c
float64_t svclasta[_n_f64](svbool_t pg, float64_t fallback, svfloat64_t data);
```

### Description

Conditionally extract element after last

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Predication / Element selection / Extract element after last active element

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
CLASTA Xtied, Pg, Xtied, Zdata.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CLASTA--scalar---Conditionally-extract-element-after-last-to-general-purpose-register-

When result and fallback are in FP registers, this intrinsic compiles to:

```asm
CLASTA Dtied, Pg, Dtied, Zdata.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CLASTA--SIMD-FP-scalar---Conditionally-extract-element-after-last-to-SIMD-FP-scalar-register-

### Operation

Source operation ID: `SveOperation_svclasta_n_bf16`

**Operation**




- If no elements are active, return `fallback`.
- If the last element is active, return `data[0]`.
- Otherwise, return the element after the last active element of `data`.

## svclasta[_n_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svclasta%5B_n_s16%5D

### Signature (source notation)

```c
int16_t svclasta[_n_s16](svbool_t pg, int16_t fallback, svint16_t data);
```

### Description

Conditionally extract element after last

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Predication / Element selection / Extract element after last active element

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
CLASTA Wtied, Pg, Wtied, Zdata.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CLASTA--scalar---Conditionally-extract-element-after-last-to-general-purpose-register-

When result and fallback are in FP registers, this intrinsic compiles to:

```asm
CLASTA Htied, Pg, Htied, Zdata.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CLASTA--SIMD-FP-scalar---Conditionally-extract-element-after-last-to-SIMD-FP-scalar-register-

### Operation

Source operation ID: `SveOperation_svclasta_n_bf16`

**Operation**




- If no elements are active, return `fallback`.
- If the last element is active, return `data[0]`.
- Otherwise, return the element after the last active element of `data`.

## svclasta[_n_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svclasta%5B_n_s32%5D

### Signature (source notation)

```c
int32_t svclasta[_n_s32](svbool_t pg, int32_t fallback, svint32_t data);
```

### Description

Conditionally extract element after last

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Predication / Element selection / Extract element after last active element

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
CLASTA Wtied, Pg, Wtied, Zdata.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CLASTA--scalar---Conditionally-extract-element-after-last-to-general-purpose-register-

When result and fallback are in FP registers, this intrinsic compiles to:

```asm
CLASTA Stied, Pg, Stied, Zdata.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CLASTA--SIMD-FP-scalar---Conditionally-extract-element-after-last-to-SIMD-FP-scalar-register-

### Operation

Source operation ID: `SveOperation_svclasta_n_bf16`

**Operation**




- If no elements are active, return `fallback`.
- If the last element is active, return `data[0]`.
- Otherwise, return the element after the last active element of `data`.

## svclasta[_n_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svclasta%5B_n_s64%5D

### Signature (source notation)

```c
int64_t svclasta[_n_s64](svbool_t pg, int64_t fallback, svint64_t data);
```

### Description

Conditionally extract element after last

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Predication / Element selection / Extract element after last active element

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
CLASTA Xtied, Pg, Xtied, Zdata.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CLASTA--scalar---Conditionally-extract-element-after-last-to-general-purpose-register-

When result and fallback are in FP registers, this intrinsic compiles to:

```asm
CLASTA Dtied, Pg, Dtied, Zdata.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CLASTA--SIMD-FP-scalar---Conditionally-extract-element-after-last-to-SIMD-FP-scalar-register-

### Operation

Source operation ID: `SveOperation_svclasta_n_bf16`

**Operation**




- If no elements are active, return `fallback`.
- If the last element is active, return `data[0]`.
- Otherwise, return the element after the last active element of `data`.

## svclasta[_n_s8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svclasta%5B_n_s8%5D

### Signature (source notation)

```c
int8_t svclasta[_n_s8](svbool_t pg, int8_t fallback, svint8_t data);
```

### Description

Conditionally extract element after last

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Predication / Element selection / Extract element after last active element

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
CLASTA Wtied, Pg, Wtied, Zdata.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CLASTA--scalar---Conditionally-extract-element-after-last-to-general-purpose-register-

When result and fallback are in FP registers, this intrinsic compiles to:

```asm
CLASTA Btied, Pg, Btied, Zdata.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CLASTA--SIMD-FP-scalar---Conditionally-extract-element-after-last-to-SIMD-FP-scalar-register-

### Operation

Source operation ID: `SveOperation_svclasta_n_bf16`

**Operation**




- If no elements are active, return `fallback`.
- If the last element is active, return `data[0]`.
- Otherwise, return the element after the last active element of `data`.

## svclasta[_n_u16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svclasta%5B_n_u16%5D

### Signature (source notation)

```c
uint16_t svclasta[_n_u16](svbool_t pg, uint16_t fallback, svuint16_t data);
```

### Description

Conditionally extract element after last

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Predication / Element selection / Extract element after last active element

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
CLASTA Wtied, Pg, Wtied, Zdata.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CLASTA--scalar---Conditionally-extract-element-after-last-to-general-purpose-register-

When result and fallback are in FP registers, this intrinsic compiles to:

```asm
CLASTA Htied, Pg, Htied, Zdata.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CLASTA--SIMD-FP-scalar---Conditionally-extract-element-after-last-to-SIMD-FP-scalar-register-

### Operation

Source operation ID: `SveOperation_svclasta_n_bf16`

**Operation**




- If no elements are active, return `fallback`.
- If the last element is active, return `data[0]`.
- Otherwise, return the element after the last active element of `data`.

## svclasta[_n_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svclasta%5B_n_u32%5D

### Signature (source notation)

```c
uint32_t svclasta[_n_u32](svbool_t pg, uint32_t fallback, svuint32_t data);
```

### Description

Conditionally extract element after last

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Predication / Element selection / Extract element after last active element

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
CLASTA Wtied, Pg, Wtied, Zdata.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CLASTA--scalar---Conditionally-extract-element-after-last-to-general-purpose-register-

When result and fallback are in FP registers, this intrinsic compiles to:

```asm
CLASTA Stied, Pg, Stied, Zdata.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CLASTA--SIMD-FP-scalar---Conditionally-extract-element-after-last-to-SIMD-FP-scalar-register-

### Operation

Source operation ID: `SveOperation_svclasta_n_bf16`

**Operation**




- If no elements are active, return `fallback`.
- If the last element is active, return `data[0]`.
- Otherwise, return the element after the last active element of `data`.

## svclasta[_n_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svclasta%5B_n_u64%5D

### Signature (source notation)

```c
uint64_t svclasta[_n_u64](svbool_t pg, uint64_t fallback, svuint64_t data);
```

### Description

Conditionally extract element after last

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Predication / Element selection / Extract element after last active element

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
CLASTA Xtied, Pg, Xtied, Zdata.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CLASTA--scalar---Conditionally-extract-element-after-last-to-general-purpose-register-

When result and fallback are in FP registers, this intrinsic compiles to:

```asm
CLASTA Dtied, Pg, Dtied, Zdata.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CLASTA--SIMD-FP-scalar---Conditionally-extract-element-after-last-to-SIMD-FP-scalar-register-

### Operation

Source operation ID: `SveOperation_svclasta_n_bf16`

**Operation**




- If no elements are active, return `fallback`.
- If the last element is active, return `data[0]`.
- Otherwise, return the element after the last active element of `data`.

## svclasta[_n_u8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svclasta%5B_n_u8%5D

### Signature (source notation)

```c
uint8_t svclasta[_n_u8](svbool_t pg, uint8_t fallback, svuint8_t data);
```

### Description

Conditionally extract element after last

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Predication / Element selection / Extract element after last active element

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
CLASTA Wtied, Pg, Wtied, Zdata.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CLASTA--scalar---Conditionally-extract-element-after-last-to-general-purpose-register-

When result and fallback are in FP registers, this intrinsic compiles to:

```asm
CLASTA Btied, Pg, Btied, Zdata.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CLASTA--SIMD-FP-scalar---Conditionally-extract-element-after-last-to-SIMD-FP-scalar-register-

### Operation

Source operation ID: `SveOperation_svclasta_n_bf16`

**Operation**




- If no elements are active, return `fallback`.
- If the last element is active, return `data[0]`.
- Otherwise, return the element after the last active element of `data`.

## svclasta[_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svclasta%5B_s16%5D

### Signature (source notation)

```c
svint16_t svclasta[_s16](svbool_t pg, svint16_t fallback, svint16_t data);
```

### Description

Conditionally extract element after last

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Predication / Element selection / Extract element after last active element

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
CLASTA Ztied.H, Pg, Ztied.H, Zdata.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CLASTA--vectors---Conditionally-extract-element-after-last-to-vector-register-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zfallback
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
CLASTA Zresult.H, Pg, Zresult.H, Zdata.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CLASTA--vectors---Conditionally-extract-element-after-last-to-vector-register-

### Operation

Source operation ID: `SveOperation_svclasta_bf16`

**Operation**




- If no elements are active, return `fallback`.
- If the last element is active, duplicate and return `data[0]`.
- Otherwise, duplicate and return the element after the last active element of `data`.

## svclasta[_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svclasta%5B_s32%5D

### Signature (source notation)

```c
svint32_t svclasta[_s32](svbool_t pg, svint32_t fallback, svint32_t data);
```

### Description

Conditionally extract element after last

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Predication / Element selection / Extract element after last active element

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
CLASTA Ztied.S, Pg, Ztied.S, Zdata.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CLASTA--vectors---Conditionally-extract-element-after-last-to-vector-register-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zfallback
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
CLASTA Zresult.S, Pg, Zresult.S, Zdata.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CLASTA--vectors---Conditionally-extract-element-after-last-to-vector-register-

### Operation

Source operation ID: `SveOperation_svclasta_bf16`

**Operation**




- If no elements are active, return `fallback`.
- If the last element is active, duplicate and return `data[0]`.
- Otherwise, duplicate and return the element after the last active element of `data`.

## svclasta[_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svclasta%5B_s64%5D

### Signature (source notation)

```c
svint64_t svclasta[_s64](svbool_t pg, svint64_t fallback, svint64_t data);
```

### Description

Conditionally extract element after last

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Predication / Element selection / Extract element after last active element

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
CLASTA Ztied.D, Pg, Ztied.D, Zdata.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CLASTA--vectors---Conditionally-extract-element-after-last-to-vector-register-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zfallback
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
CLASTA Zresult.D, Pg, Zresult.D, Zdata.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CLASTA--vectors---Conditionally-extract-element-after-last-to-vector-register-

### Operation

Source operation ID: `SveOperation_svclasta_bf16`

**Operation**




- If no elements are active, return `fallback`.
- If the last element is active, duplicate and return `data[0]`.
- Otherwise, duplicate and return the element after the last active element of `data`.

## svclasta[_s8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svclasta%5B_s8%5D

### Signature (source notation)

```c
svint8_t svclasta[_s8](svbool_t pg, svint8_t fallback, svint8_t data);
```

### Description

Conditionally extract element after last

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Predication / Element selection / Extract element after last active element

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
CLASTA Ztied.B, Pg, Ztied.B, Zdata.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CLASTA--vectors---Conditionally-extract-element-after-last-to-vector-register-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zfallback
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
CLASTA Zresult.B, Pg, Zresult.B, Zdata.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CLASTA--vectors---Conditionally-extract-element-after-last-to-vector-register-

### Operation

Source operation ID: `SveOperation_svclasta_bf16`

**Operation**




- If no elements are active, return `fallback`.
- If the last element is active, duplicate and return `data[0]`.
- Otherwise, duplicate and return the element after the last active element of `data`.

## svclasta[_u16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svclasta%5B_u16%5D

### Signature (source notation)

```c
svuint16_t svclasta[_u16](svbool_t pg, svuint16_t fallback, svuint16_t data);
```

### Description

Conditionally extract element after last

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Predication / Element selection / Extract element after last active element

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
CLASTA Ztied.H, Pg, Ztied.H, Zdata.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CLASTA--vectors---Conditionally-extract-element-after-last-to-vector-register-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zfallback
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
CLASTA Zresult.H, Pg, Zresult.H, Zdata.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CLASTA--vectors---Conditionally-extract-element-after-last-to-vector-register-

### Operation

Source operation ID: `SveOperation_svclasta_bf16`

**Operation**




- If no elements are active, return `fallback`.
- If the last element is active, duplicate and return `data[0]`.
- Otherwise, duplicate and return the element after the last active element of `data`.

## svclasta[_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svclasta%5B_u32%5D

### Signature (source notation)

```c
svuint32_t svclasta[_u32](svbool_t pg, svuint32_t fallback, svuint32_t data);
```

### Description

Conditionally extract element after last

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Predication / Element selection / Extract element after last active element

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
CLASTA Ztied.S, Pg, Ztied.S, Zdata.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CLASTA--vectors---Conditionally-extract-element-after-last-to-vector-register-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zfallback
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
CLASTA Zresult.S, Pg, Zresult.S, Zdata.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CLASTA--vectors---Conditionally-extract-element-after-last-to-vector-register-

### Operation

Source operation ID: `SveOperation_svclasta_bf16`

**Operation**




- If no elements are active, return `fallback`.
- If the last element is active, duplicate and return `data[0]`.
- Otherwise, duplicate and return the element after the last active element of `data`.

## svclasta[_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svclasta%5B_u64%5D

### Signature (source notation)

```c
svuint64_t svclasta[_u64](svbool_t pg, svuint64_t fallback, svuint64_t data);
```

### Description

Conditionally extract element after last

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Predication / Element selection / Extract element after last active element

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
CLASTA Ztied.D, Pg, Ztied.D, Zdata.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CLASTA--vectors---Conditionally-extract-element-after-last-to-vector-register-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zfallback
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
CLASTA Zresult.D, Pg, Zresult.D, Zdata.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CLASTA--vectors---Conditionally-extract-element-after-last-to-vector-register-

### Operation

Source operation ID: `SveOperation_svclasta_bf16`

**Operation**




- If no elements are active, return `fallback`.
- If the last element is active, duplicate and return `data[0]`.
- Otherwise, duplicate and return the element after the last active element of `data`.

## svclasta[_u8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svclasta%5B_u8%5D

### Signature (source notation)

```c
svuint8_t svclasta[_u8](svbool_t pg, svuint8_t fallback, svuint8_t data);
```

### Description

Conditionally extract element after last

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Predication / Element selection / Extract element after last active element

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
CLASTA Ztied.B, Pg, Ztied.B, Zdata.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CLASTA--vectors---Conditionally-extract-element-after-last-to-vector-register-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zfallback
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
CLASTA Zresult.B, Pg, Zresult.B, Zdata.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CLASTA--vectors---Conditionally-extract-element-after-last-to-vector-register-

### Operation

Source operation ID: `SveOperation_svclasta_bf16`

**Operation**




- If no elements are active, return `fallback`.
- If the last element is active, duplicate and return `data[0]`.
- Otherwise, duplicate and return the element after the last active element of `data`.

## svlasta[_bf16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svlasta%5B_bf16%5D

### Signature (source notation)

```c
bfloat16_t svlasta[_bf16](svbool_t pg, svbfloat16_t op);
```

### Description

Extract element after last

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Predication / Element selection / Extract element after last active element

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
LASTA Wresult, Pg, Zop.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LASTA--scalar---Extract-element-after-last-to-general-purpose-register-

When result is in an FP register, this intrinsic compiles to:

```asm
LASTA Hresult, Pg, Zop.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LASTA--SIMD-FP-scalar---Extract-element-after-last-to-SIMD-FP-scalar-register-

### Operation

Source operation ID: `SveOperation_svlasta_bf16`

**Operation**




- If no elements are active, return `op[0]`.
- If the last element is active, return `op[0]`.
- Otherwise, return the element after the last active element of `op`.

## svlasta[_f16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svlasta%5B_f16%5D

### Signature (source notation)

```c
float16_t svlasta[_f16](svbool_t pg, svfloat16_t op);
```

### Description

Extract element after last

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Predication / Element selection / Extract element after last active element

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
LASTA Wresult, Pg, Zop.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LASTA--scalar---Extract-element-after-last-to-general-purpose-register-

When result is in an FP register, this intrinsic compiles to:

```asm
LASTA Hresult, Pg, Zop.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LASTA--SIMD-FP-scalar---Extract-element-after-last-to-SIMD-FP-scalar-register-

### Operation

Source operation ID: `SveOperation_svlasta_bf16`

**Operation**




- If no elements are active, return `op[0]`.
- If the last element is active, return `op[0]`.
- Otherwise, return the element after the last active element of `op`.

## svlasta[_f32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svlasta%5B_f32%5D

### Signature (source notation)

```c
float32_t svlasta[_f32](svbool_t pg, svfloat32_t op);
```

### Description

Extract element after last

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Predication / Element selection / Extract element after last active element

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
LASTA Wresult, Pg, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LASTA--scalar---Extract-element-after-last-to-general-purpose-register-

When result is in an FP register, this intrinsic compiles to:

```asm
LASTA Sresult, Pg, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LASTA--SIMD-FP-scalar---Extract-element-after-last-to-SIMD-FP-scalar-register-

### Operation

Source operation ID: `SveOperation_svlasta_bf16`

**Operation**




- If no elements are active, return `op[0]`.
- If the last element is active, return `op[0]`.
- Otherwise, return the element after the last active element of `op`.

## svlasta[_f64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svlasta%5B_f64%5D

### Signature (source notation)

```c
float64_t svlasta[_f64](svbool_t pg, svfloat64_t op);
```

### Description

Extract element after last

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Predication / Element selection / Extract element after last active element

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
LASTA Xresult, Pg, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LASTA--scalar---Extract-element-after-last-to-general-purpose-register-

When result is in an FP register, this intrinsic compiles to:

```asm
LASTA Dresult, Pg, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LASTA--SIMD-FP-scalar---Extract-element-after-last-to-SIMD-FP-scalar-register-

### Operation

Source operation ID: `SveOperation_svlasta_bf16`

**Operation**




- If no elements are active, return `op[0]`.
- If the last element is active, return `op[0]`.
- Otherwise, return the element after the last active element of `op`.

## svlasta[_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svlasta%5B_s16%5D

### Signature (source notation)

```c
int16_t svlasta[_s16](svbool_t pg, svint16_t op);
```

### Description

Extract element after last

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Predication / Element selection / Extract element after last active element

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
LASTA Wresult, Pg, Zop.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LASTA--scalar---Extract-element-after-last-to-general-purpose-register-

When result is in an FP register, this intrinsic compiles to:

```asm
LASTA Hresult, Pg, Zop.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LASTA--SIMD-FP-scalar---Extract-element-after-last-to-SIMD-FP-scalar-register-

### Operation

Source operation ID: `SveOperation_svlasta_bf16`

**Operation**




- If no elements are active, return `op[0]`.
- If the last element is active, return `op[0]`.
- Otherwise, return the element after the last active element of `op`.

## svlasta[_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svlasta%5B_s32%5D

### Signature (source notation)

```c
int32_t svlasta[_s32](svbool_t pg, svint32_t op);
```

### Description

Extract element after last

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Predication / Element selection / Extract element after last active element

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
LASTA Wresult, Pg, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LASTA--scalar---Extract-element-after-last-to-general-purpose-register-

When result is in an FP register, this intrinsic compiles to:

```asm
LASTA Sresult, Pg, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LASTA--SIMD-FP-scalar---Extract-element-after-last-to-SIMD-FP-scalar-register-

### Operation

Source operation ID: `SveOperation_svlasta_bf16`

**Operation**




- If no elements are active, return `op[0]`.
- If the last element is active, return `op[0]`.
- Otherwise, return the element after the last active element of `op`.

## svlasta[_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svlasta%5B_s64%5D

### Signature (source notation)

```c
int64_t svlasta[_s64](svbool_t pg, svint64_t op);
```

### Description

Extract element after last

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Predication / Element selection / Extract element after last active element

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
LASTA Xresult, Pg, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LASTA--scalar---Extract-element-after-last-to-general-purpose-register-

When result is in an FP register, this intrinsic compiles to:

```asm
LASTA Dresult, Pg, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LASTA--SIMD-FP-scalar---Extract-element-after-last-to-SIMD-FP-scalar-register-

### Operation

Source operation ID: `SveOperation_svlasta_bf16`

**Operation**




- If no elements are active, return `op[0]`.
- If the last element is active, return `op[0]`.
- Otherwise, return the element after the last active element of `op`.

## svlasta[_s8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svlasta%5B_s8%5D

### Signature (source notation)

```c
int8_t svlasta[_s8](svbool_t pg, svint8_t op);
```

### Description

Extract element after last

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Predication / Element selection / Extract element after last active element

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
LASTA Wresult, Pg, Zop.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LASTA--scalar---Extract-element-after-last-to-general-purpose-register-

When result is in an FP register, this intrinsic compiles to:

```asm
LASTA Bresult, Pg, Zop.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LASTA--SIMD-FP-scalar---Extract-element-after-last-to-SIMD-FP-scalar-register-

### Operation

Source operation ID: `SveOperation_svlasta_bf16`

**Operation**




- If no elements are active, return `op[0]`.
- If the last element is active, return `op[0]`.
- Otherwise, return the element after the last active element of `op`.

## svlasta[_u16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svlasta%5B_u16%5D

### Signature (source notation)

```c
uint16_t svlasta[_u16](svbool_t pg, svuint16_t op);
```

### Description

Extract element after last

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Predication / Element selection / Extract element after last active element

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
LASTA Wresult, Pg, Zop.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LASTA--scalar---Extract-element-after-last-to-general-purpose-register-

When result is in an FP register, this intrinsic compiles to:

```asm
LASTA Hresult, Pg, Zop.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LASTA--SIMD-FP-scalar---Extract-element-after-last-to-SIMD-FP-scalar-register-

### Operation

Source operation ID: `SveOperation_svlasta_bf16`

**Operation**




- If no elements are active, return `op[0]`.
- If the last element is active, return `op[0]`.
- Otherwise, return the element after the last active element of `op`.

## svlasta[_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svlasta%5B_u32%5D

### Signature (source notation)

```c
uint32_t svlasta[_u32](svbool_t pg, svuint32_t op);
```

### Description

Extract element after last

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Predication / Element selection / Extract element after last active element

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
LASTA Wresult, Pg, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LASTA--scalar---Extract-element-after-last-to-general-purpose-register-

When result is in an FP register, this intrinsic compiles to:

```asm
LASTA Sresult, Pg, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LASTA--SIMD-FP-scalar---Extract-element-after-last-to-SIMD-FP-scalar-register-

### Operation

Source operation ID: `SveOperation_svlasta_bf16`

**Operation**




- If no elements are active, return `op[0]`.
- If the last element is active, return `op[0]`.
- Otherwise, return the element after the last active element of `op`.

## svlasta[_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svlasta%5B_u64%5D

### Signature (source notation)

```c
uint64_t svlasta[_u64](svbool_t pg, svuint64_t op);
```

### Description

Extract element after last

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Predication / Element selection / Extract element after last active element

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
LASTA Xresult, Pg, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LASTA--scalar---Extract-element-after-last-to-general-purpose-register-

When result is in an FP register, this intrinsic compiles to:

```asm
LASTA Dresult, Pg, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LASTA--SIMD-FP-scalar---Extract-element-after-last-to-SIMD-FP-scalar-register-

### Operation

Source operation ID: `SveOperation_svlasta_bf16`

**Operation**




- If no elements are active, return `op[0]`.
- If the last element is active, return `op[0]`.
- Otherwise, return the element after the last active element of `op`.

## svlasta[_u8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svlasta%5B_u8%5D

### Signature (source notation)

```c
uint8_t svlasta[_u8](svbool_t pg, svuint8_t op);
```

### Description

Extract element after last

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Predication / Element selection / Extract element after last active element

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
LASTA Wresult, Pg, Zop.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LASTA--scalar---Extract-element-after-last-to-general-purpose-register-

When result is in an FP register, this intrinsic compiles to:

```asm
LASTA Bresult, Pg, Zop.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/LASTA--SIMD-FP-scalar---Extract-element-after-last-to-SIMD-FP-scalar-register-

### Operation

Source operation ID: `SveOperation_svlasta_bf16`

**Operation**




- If no elements are active, return `op[0]`.
- If the last element is active, return `op[0]`.
- Otherwise, return the element after the last active element of `op`.

