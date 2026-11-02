# SME2 / Data type conversion / Conversions — Part 1

## svcvt1_bf16[_mf8]_fpm

ISA classification: SME2 + FEAT_FP8

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvt1_bf16%5B_mf8%5D_fpm

### Signature (source notation)

```c
svbfloat16_t svcvt1_bf16[_mf8]_fpm(svmfloat8_t zn, fpm_t fpm);
```

### Description

8-bit floating-point convert to BFloat16

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Data type conversion / Conversions

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2,FEAT_FP8
```

### Return type metadata

```json
{
  "return_base_type": "bfloat16",
  "element_bit_size": "16",
  "value": "svbfloat16_t"
}
```

### Argument preparation and constraints

```json
{
  "zn": {
    "register": "Zreg2.B"
  },
  "fpm": {
    "register": "Xreg1"
  }
}
```

### Result mapping

```json
[
  {
    "Zreg1.H": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
MSR FPMR, Xreg1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/Base-Instructions/MSR--register---Move-general-purpose-register-to-System-register-

```asm
BF1CVT Zreg1.H, Zreg2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/BF1CVT--BF2CVT--8-bit-floating-point-convert-to-BFloat16-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svcvt1_bf16[_mf8]_x2_fpm

ISA classification: SME2 + FEAT_FP8

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvt1_bf16%5B_mf8%5D_x2_fpm

### Signature (source notation)

```c
svbfloat16x2_t svcvt1_bf16[_mf8]_x2_fpm(svmfloat8_t zn, fpm_t fpm)
    __arm_streaming;
```

### Description

Multi-vector 8-bit floating-point convert to BFloat16

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Data type conversion / Conversions

- SME attributes: `__arm_streaming`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2,FEAT_FP8
```

### Return type metadata

```json
{
  "return_base_type": "bfloat16",
  "element_bit_size": "16",
  "value": "svbfloat16x2_t"
}
```

### Argument preparation and constraints

```json
{
  "zn": {
    "register": "Zreg3.B"
  },
  "fpm": {
    "register": "Xreg1"
  }
}
```

### Result mapping

```json
[
  {
    "{ Zreg1.H, Zreg2.H }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
MSR FPMR, Xreg1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/Base-Instructions/MSR--register---Move-general-purpose-register-to-System-register-

```asm
BF1CVT { Zreg1.H, Zreg2.H }, Zreg3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/BF1CVT--BF2CVT--Multi-vector-8-bit-floating-point-convert-to-BFloat16-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svcvt1_f16[_mf8]_fpm

ISA classification: SME2 + FEAT_FP8

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvt1_f16%5B_mf8%5D_fpm

### Signature (source notation)

```c
svfloat16_t svcvt1_f16[_mf8]_fpm(svmfloat8_t zn, fpm_t fpm);
```

### Description

8-bit floating-point convert to half-precision

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Data type conversion / Conversions

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2,FEAT_FP8
```

### Return type metadata

```json
{
  "return_base_type": "float16",
  "element_bit_size": "16",
  "value": "svfloat16_t"
}
```

### Argument preparation and constraints

```json
{
  "zn": {
    "register": "Zreg2.B"
  },
  "fpm": {
    "register": "Xreg1"
  }
}
```

### Result mapping

```json
[
  {
    "Zreg1.H": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
MSR FPMR, Xreg1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/Base-Instructions/MSR--register---Move-general-purpose-register-to-System-register-

```asm
F1CVT Zreg1.H, Zreg2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/F1CVT--F2CVT--8-bit-floating-point-convert-to-half-precision-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svcvt1_f16[_mf8]_x2_fpm

ISA classification: SME2 + FEAT_FP8

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvt1_f16%5B_mf8%5D_x2_fpm

### Signature (source notation)

```c
svfloat16x2_t svcvt1_f16[_mf8]_x2_fpm(svmfloat8_t zn, fpm_t fpm)
    __arm_streaming;
```

### Description

Multi-vector 8-bit floating-point convert to half-precision

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Data type conversion / Conversions

- SME attributes: `__arm_streaming`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2,FEAT_FP8
```

### Return type metadata

```json
{
  "return_base_type": "float16",
  "element_bit_size": "16",
  "value": "svfloat16x2_t"
}
```

### Argument preparation and constraints

```json
{
  "zn": {
    "register": "Zreg3.B"
  },
  "fpm": {
    "register": "Xreg1"
  }
}
```

### Result mapping

```json
[
  {
    "{ Zreg1.H, Zreg2.H }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
MSR FPMR, Xreg1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/Base-Instructions/MSR--register---Move-general-purpose-register-to-System-register-

```asm
F1CVT { Zreg1.H, Zreg2.H }, Zreg3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/F1CVT--F2CVT--Multi-vector-8-bit-floating-point-convert-to-half-precision-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svcvt2_bf16[_mf8]_fpm

ISA classification: SME2 + FEAT_FP8

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvt2_bf16%5B_mf8%5D_fpm

### Signature (source notation)

```c
svbfloat16_t svcvt2_bf16[_mf8]_fpm(svmfloat8_t zn, fpm_t fpm);
```

### Description

8-bit floating-point convert to BFloat16

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Data type conversion / Conversions

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2,FEAT_FP8
```

### Return type metadata

```json
{
  "return_base_type": "bfloat16",
  "element_bit_size": "16",
  "value": "svbfloat16_t"
}
```

### Argument preparation and constraints

```json
{
  "zn": {
    "register": "Zreg2.B"
  },
  "fpm": {
    "register": "Xreg1"
  }
}
```

### Result mapping

```json
[
  {
    "Zreg1.H": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
MSR FPMR, Xreg1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/Base-Instructions/MSR--register---Move-general-purpose-register-to-System-register-

```asm
BF2CVT Zreg1.H, Zreg2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/BF1CVT--BF2CVT--8-bit-floating-point-convert-to-BFloat16-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svcvt2_bf16[_mf8]_x2_fpm

ISA classification: SME2 + FEAT_FP8

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvt2_bf16%5B_mf8%5D_x2_fpm

### Signature (source notation)

```c
svbfloat16x2_t svcvt2_bf16[_mf8]_x2_fpm(svmfloat8_t zn, fpm_t fpm)
    __arm_streaming;
```

### Description

Multi-vector 8-bit floating-point convert to BFloat16

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Data type conversion / Conversions

- SME attributes: `__arm_streaming`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2,FEAT_FP8
```

### Return type metadata

```json
{
  "return_base_type": "bfloat16",
  "element_bit_size": "16",
  "value": "svbfloat16x2_t"
}
```

### Argument preparation and constraints

```json
{
  "zn": {
    "register": "Zreg3.B"
  },
  "fpm": {
    "register": "Xreg1"
  }
}
```

### Result mapping

```json
[
  {
    "{ Zreg1.H, Zreg2.H }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
MSR FPMR, Xreg1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/Base-Instructions/MSR--register---Move-general-purpose-register-to-System-register-

```asm
BF2CVT { Zreg1.H, Zreg2.H }, Zreg3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/BF1CVT--BF2CVT--Multi-vector-8-bit-floating-point-convert-to-BFloat16-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svcvt2_f16[_mf8]_fpm

ISA classification: SME2 + FEAT_FP8

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvt2_f16%5B_mf8%5D_fpm

### Signature (source notation)

```c
svfloat16_t svcvt2_f16[_mf8]_fpm(svmfloat8_t zn, fpm_t fpm);
```

### Description

8-bit floating-point convert to half-precision

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Data type conversion / Conversions

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2,FEAT_FP8
```

### Return type metadata

```json
{
  "return_base_type": "float16",
  "element_bit_size": "16",
  "value": "svfloat16_t"
}
```

### Argument preparation and constraints

```json
{
  "zn": {
    "register": "Zreg2.B"
  },
  "fpm": {
    "register": "Xreg1"
  }
}
```

### Result mapping

```json
[
  {
    "Zreg1.H": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
MSR FPMR, Xreg1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/Base-Instructions/MSR--register---Move-general-purpose-register-to-System-register-

```asm
F2CVT Zreg1.H, Zreg2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/F1CVT--F2CVT--8-bit-floating-point-convert-to-half-precision-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svcvt2_f16[_mf8]_x2_fpm

ISA classification: SME2 + FEAT_FP8

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvt2_f16%5B_mf8%5D_x2_fpm

### Signature (source notation)

```c
svfloat16x2_t svcvt2_f16[_mf8]_x2_fpm(svmfloat8_t zn, fpm_t fpm)
    __arm_streaming;
```

### Description

Multi-vector 8-bit floating-point convert to half-precision

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Data type conversion / Conversions

- SME attributes: `__arm_streaming`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2,FEAT_FP8
```

### Return type metadata

```json
{
  "return_base_type": "float16",
  "element_bit_size": "16",
  "value": "svfloat16x2_t"
}
```

### Argument preparation and constraints

```json
{
  "zn": {
    "register": "Zreg3.B"
  },
  "fpm": {
    "register": "Xreg1"
  }
}
```

### Result mapping

```json
[
  {
    "{ Zreg1.H, Zreg2.H }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
MSR FPMR, Xreg1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/Base-Instructions/MSR--register---Move-general-purpose-register-to-System-register-

```asm
F2CVT { Zreg1.H, Zreg2.H }, Zreg3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/F1CVT--F2CVT--Multi-vector-8-bit-floating-point-convert-to-half-precision-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svcvt_bf16[_f32_x2]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvt_bf16%5B_f32_x2%5D

### Signature (source notation)

```c
svbfloat16_t svcvt_bf16[_f32_x2](svfloat32x2_t zn)
    __arm_streaming;
```

### Description

Multi-vector convert from single-precision to packed BFloat16 format

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Data type conversion / Conversions

- SME attributes: `__arm_streaming`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2
```

### Return type metadata

```json
{
  "return_base_type": "bfloat16",
  "element_bit_size": "16",
  "value": "svbfloat16_t"
}
```

### Argument preparation and constraints

```json
{
  "zn": {
    "Z multi-vector": "{ Zreg2.S, Zreg3.S }"
  }
}
```

### Result mapping

```json
[
  {
    "Zreg1.H": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
BFCVT Zreg1.H, { Zreg2.S, Zreg3.S }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/BFCVT--single-precision-to-BFloat16---Multi-vector-convert-from-single-precision-to-packed-BFloat16-format-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svcvt_f16[_f32_x2]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvt_f16%5B_f32_x2%5D

### Signature (source notation)

```c
svfloat16_t svcvt_f16[_f32_x2](svfloat32x2_t zn)
    __arm_streaming;
```

### Description

Multi-vector convert from single-precision to packed half-precision

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Data type conversion / Conversions

- SME attributes: `__arm_streaming`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2
```

### Return type metadata

```json
{
  "return_base_type": "float16",
  "element_bit_size": "16",
  "value": "svfloat16_t"
}
```

### Argument preparation and constraints

```json
{
  "zn": {
    "Z multi-vector": "{ Zreg2.S, Zreg3.S }"
  }
}
```

### Result mapping

```json
[
  {
    "Zreg1.H": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
FCVT Zreg1.H, { Zreg2.S, Zreg3.S }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/FCVT--narrowing--FP32-to-FP16---Multi-vector-convert-from-single-precision-to-packed-half-precision-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svcvt_f32[_f16_x2]

ISA classification: SME2 + FEAT_SME_F16F16

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvt_f32%5B_f16_x2%5D

### Signature (source notation)

```c
svfloat32x2_t svcvt_f32[_f16_x2](svfloat16_t zn)
    __arm_streaming;
```

### Description

Multi-vector half-precision convert to single-precision

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Data type conversion / Conversions

- SME attributes: `__arm_streaming`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME_F16F16
```

### Return type metadata

```json
{
  "return_base_type": "float32",
  "element_bit_size": "32",
  "value": "svfloat32x2_t"
}
```

### Argument preparation and constraints

```json
{
  "zn": {
    "register": "Zreg3.H"
  }
}
```

### Result mapping

```json
[
  {
    "{ Zreg1.S, Zreg2.S }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
FCVT { Zreg1.S, Zreg2.S }, Zreg3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/FCVT--widening---Multi-vector-half-precision-convert-to-single-precision-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svcvt_f32[_s32_x2]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvt_f32%5B_s32_x2%5D

### Signature (source notation)

```c
svfloat32x2_t svcvt_f32[_s32_x2](svint32x2_t zn)
    __arm_streaming;
```

### Description

Multi-vector signed integer convert to floating-point

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Data type conversion / Conversions

- SME attributes: `__arm_streaming`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2
```

### Return type metadata

```json
{
  "return_base_type": "float32",
  "element_bit_size": "32",
  "value": "svfloat32x2_t"
}
```

### Argument preparation and constraints

```json
{
  "zn": {
    "Z multi-vector": "{ Zreg3.S, Zreg4.S }"
  }
}
```

### Result mapping

```json
[
  {
    "{ Zreg1.S, Zreg2.S }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
SCVTF { Zreg1.S, Zreg2.S }, { Zreg3.S, Zreg4.S }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SCVTF--Multi-vector-signed-integer-convert-to-floating-point-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svcvt_f32[_s32_x4]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvt_f32%5B_s32_x4%5D

### Signature (source notation)

```c
svfloat32x4_t svcvt_f32[_s32_x4](svint32x4_t zn)
    __arm_streaming;
```

### Description

Multi-vector signed integer convert to floating-point

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Data type conversion / Conversions

- SME attributes: `__arm_streaming`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2
```

### Return type metadata

```json
{
  "return_base_type": "float32",
  "element_bit_size": "32",
  "value": "svfloat32x4_t"
}
```

### Argument preparation and constraints

```json
{
  "zn": {
    "Z multi-vector": "{ Zreg3.S - Zreg4.S }"
  }
}
```

### Result mapping

```json
[
  {
    "{ Zreg1.S - Zreg2.S }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
SCVTF { Zreg1.S - Zreg2.S }, { Zreg3.S - Zreg4.S }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/SCVTF--Multi-vector-signed-integer-convert-to-floating-point-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svcvt_f32[_u32_x2]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvt_f32%5B_u32_x2%5D

### Signature (source notation)

```c
svfloat32x2_t svcvt_f32[_u32_x2](svuint32x2_t zn)
    __arm_streaming;
```

### Description

Multi-vector unsigned integer convert to floating-point

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Data type conversion / Conversions

- SME attributes: `__arm_streaming`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2
```

### Return type metadata

```json
{
  "return_base_type": "float32",
  "element_bit_size": "32",
  "value": "svfloat32x2_t"
}
```

### Argument preparation and constraints

```json
{
  "zn": {
    "Z multi-vector": "{ Zreg3.S, Zreg4.S }"
  }
}
```

### Result mapping

```json
[
  {
    "{ Zreg1.S, Zreg2.S }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
UCVTF { Zreg1.S, Zreg2.S }, { Zreg3.S, Zreg4.S }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/UCVTF--Multi-vector-unsigned-integer-convert-to-floating-point-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svcvt_f32[_u32_x4]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvt_f32%5B_u32_x4%5D

### Signature (source notation)

```c
svfloat32x4_t svcvt_f32[_u32_x4](svuint32x4_t zn)
    __arm_streaming;
```

### Description

Multi-vector unsigned integer convert to floating-point

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Data type conversion / Conversions

- SME attributes: `__arm_streaming`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2
```

### Return type metadata

```json
{
  "return_base_type": "float32",
  "element_bit_size": "32",
  "value": "svfloat32x4_t"
}
```

### Argument preparation and constraints

```json
{
  "zn": {
    "Z multi-vector": "{ Zreg3.S - Zreg4.S }"
  }
}
```

### Result mapping

```json
[
  {
    "{ Zreg1.S - Zreg2.S }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
UCVTF { Zreg1.S - Zreg2.S }, { Zreg3.S - Zreg4.S }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/UCVTF--Multi-vector-unsigned-integer-convert-to-floating-point-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svcvt_mf8[_bf16_x2]_fpm

ISA classification: SME2 + FEAT_FP8

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvt_mf8%5B_bf16_x2%5D_fpm

### Signature (source notation)

```c
svmfloat8_t svcvt_mf8[_bf16_x2]_fpm(svbfloat16x2_t zn, fpm_t fpm)
    __arm_streaming;
```

### Description

Multi-vector BFloat16 convert to 8-bit floating-point

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Data type conversion / Conversions

- SME attributes: `__arm_streaming`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2,FEAT_FP8
```

### Return type metadata

```json
{
  "return_base_type": "mfloat8",
  "element_bit_size": "8",
  "value": "svmfloat8_t"
}
```

### Argument preparation and constraints

```json
{
  "zn": {
    "Z multi-vector": "{ Zreg2.H, Zreg3.H }"
  },
  "fpm": {
    "register": "Xreg1"
  }
}
```

### Result mapping

```json
[
  {
    "Zreg1.B": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
MSR FPMR, Xreg1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/Base-Instructions/MSR--register---Move-general-purpose-register-to-System-register-

```asm
BFCVT Zreg1.B, { Zreg2.H, Zreg3.H }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/BFCVT--BFloat16-to-8-bit-floating-point---Multi-vector-BFloat16-convert-to-8-bit-floating-point-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svcvt_mf8[_f16_x2]_fpm

ISA classification: SME2 + FEAT_FP8

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvt_mf8%5B_f16_x2%5D_fpm

### Signature (source notation)

```c
svmfloat8_t svcvt_mf8[_f16_x2]_fpm(svfloat16x2_t zn, fpm_t fpm)
    __arm_streaming;
```

### Description

Multi-vector half-precision convert to 8-bit floating-point

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Data type conversion / Conversions

- SME attributes: `__arm_streaming`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2,FEAT_FP8
```

### Return type metadata

```json
{
  "return_base_type": "mfloat8",
  "element_bit_size": "8",
  "value": "svmfloat8_t"
}
```

### Argument preparation and constraints

```json
{
  "zn": {
    "Z multi-vector": "{ Zreg2.H, Zreg3.H }"
  },
  "fpm": {
    "register": "Xreg1"
  }
}
```

### Result mapping

```json
[
  {
    "Zreg1.B": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
MSR FPMR, Xreg1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/Base-Instructions/MSR--register---Move-general-purpose-register-to-System-register-

```asm
FCVT Zreg1.B, { Zreg2.H, Zreg3.H }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/FCVT--narrowing--FP16-to-FP8---Multi-vector-half-precision-convert-to-8-bit-floating-point-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svcvt_mf8[_f32_x4]_fpm

ISA classification: SME2 + FEAT_FP8

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvt_mf8%5B_f32_x4%5D_fpm

### Signature (source notation)

```c
svmfloat8_t svcvt_mf8[_f32_x4]_fpm(svfloat32x4_t zn, fpm_t fpm)
    __arm_streaming;
```

### Description

Multi-vector single-precision convert to 8-bit floating-point

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Data type conversion / Conversions

- SME attributes: `__arm_streaming`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2,FEAT_FP8
```

### Return type metadata

```json
{
  "return_base_type": "mfloat8",
  "element_bit_size": "8",
  "value": "svmfloat8_t"
}
```

### Argument preparation and constraints

```json
{
  "zn": {
    "Z multi-vector": "{ Zreg2.S - Zreg3.S }"
  },
  "fpm": {
    "register": "Xreg1"
  }
}
```

### Result mapping

```json
[
  {
    "Zreg1.B": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
MSR FPMR, Xreg1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/Base-Instructions/MSR--register---Move-general-purpose-register-to-System-register-

```asm
FCVT Zreg1.B, { Zreg2.S - Zreg3.S }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/FCVT--narrowing--FP32-to-FP8---Multi-vector-single-precision-convert-to-8-bit-floating-point-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svcvt_s32[_f32_x2]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvt_s32%5B_f32_x2%5D

### Signature (source notation)

```c
svint32x2_t svcvt_s32[_f32_x2](svfloat32x2_t zn)
    __arm_streaming;
```

### Description

Multi-vector floating-point convert to signed integer, rounding toward zero

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Data type conversion / Conversions

- SME attributes: `__arm_streaming`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2
```

### Return type metadata

```json
{
  "return_base_type": "int32",
  "element_bit_size": "32",
  "value": "svint32x2_t"
}
```

### Argument preparation and constraints

```json
{
  "zn": {
    "Z multi-vector": "{ Zreg3.S, Zreg4.S }"
  }
}
```

### Result mapping

```json
[
  {
    "{ Zreg1.S, Zreg2.S }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
FCVTZS { Zreg1.S, Zreg2.S }, { Zreg3.S, Zreg4.S }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/FCVTZS--Multi-vector-floating-point-convert-to-signed-integer--rounding-toward-zero-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svcvt_s32[_f32_x4]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvt_s32%5B_f32_x4%5D

### Signature (source notation)

```c
svint32x4_t svcvt_s32[_f32_x4](svfloat32x4_t zn)
    __arm_streaming;
```

### Description

Multi-vector floating-point convert to signed integer, rounding toward zero

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Data type conversion / Conversions

- SME attributes: `__arm_streaming`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2
```

### Return type metadata

```json
{
  "return_base_type": "int32",
  "element_bit_size": "32",
  "value": "svint32x4_t"
}
```

### Argument preparation and constraints

```json
{
  "zn": {
    "Z multi-vector": "{ Zreg3.S - Zreg4.S }"
  }
}
```

### Result mapping

```json
[
  {
    "{ Zreg1.S - Zreg2.S }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
FCVTZS { Zreg1.S - Zreg2.S }, { Zreg3.S - Zreg4.S }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/FCVTZS--Multi-vector-floating-point-convert-to-signed-integer--rounding-toward-zero-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svcvt_u32[_f32_x2]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvt_u32%5B_f32_x2%5D

### Signature (source notation)

```c
svuint32x2_t svcvt_u32[_f32_x2](svfloat32x2_t zn)
    __arm_streaming;
```

### Description

Multi-vector floating-point convert to unsigned integer, rounding toward zero

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Data type conversion / Conversions

- SME attributes: `__arm_streaming`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2
```

### Return type metadata

```json
{
  "return_base_type": "uint32",
  "element_bit_size": "32",
  "value": "svuint32x2_t"
}
```

### Argument preparation and constraints

```json
{
  "zn": {
    "Z multi-vector": "{ Zreg3.S, Zreg4.S }"
  }
}
```

### Result mapping

```json
[
  {
    "{ Zreg1.S, Zreg2.S }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
FCVTZU { Zreg1.S, Zreg2.S }, { Zreg3.S, Zreg4.S }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/FCVTZU--Multi-vector-floating-point-convert-to-unsigned-integer--rounding-toward-zero-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svcvt_u32[_f32_x4]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvt_u32%5B_f32_x4%5D

### Signature (source notation)

```c
svuint32x4_t svcvt_u32[_f32_x4](svfloat32x4_t zn)
    __arm_streaming;
```

### Description

Multi-vector floating-point convert to unsigned integer, rounding toward zero

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Data type conversion / Conversions

- SME attributes: `__arm_streaming`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2
```

### Return type metadata

```json
{
  "return_base_type": "uint32",
  "element_bit_size": "32",
  "value": "svuint32x4_t"
}
```

### Argument preparation and constraints

```json
{
  "zn": {
    "Z multi-vector": "{ Zreg3.S - Zreg4.S }"
  }
}
```

### Result mapping

```json
[
  {
    "{ Zreg1.S - Zreg2.S }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
FCVTZU { Zreg1.S - Zreg2.S }, { Zreg3.S - Zreg4.S }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/FCVTZU--Multi-vector-floating-point-convert-to-unsigned-integer--rounding-toward-zero-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svcvtl1_bf16[_mf8]_x2_fpm

ISA classification: SME2 + FEAT_FP8

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvtl1_bf16%5B_mf8%5D_x2_fpm

### Signature (source notation)

```c
svbfloat16x2_t svcvtl1_bf16[_mf8]_x2_fpm(svmfloat8_t zn, fpm_t fpm)
    __arm_streaming;
```

### Description

Multi-vector 8-bit floating-point convert to deinterleaved BFloat16

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Data type conversion / Conversions

- SME attributes: `__arm_streaming`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2,FEAT_FP8
```

### Return type metadata

```json
{
  "return_base_type": "bfloat16",
  "element_bit_size": "16",
  "value": "svbfloat16x2_t"
}
```

### Argument preparation and constraints

```json
{
  "zn": {
    "register": "Zreg3.B"
  },
  "fpm": {
    "register": "Xreg1"
  }
}
```

### Result mapping

```json
[
  {
    "{ Zreg1.H, Zreg2.H }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
MSR FPMR, Xreg1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/Base-Instructions/MSR--register---Move-general-purpose-register-to-System-register-

```asm
BF1CVTL { Zreg1.H, Zreg2.H }, Zreg3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/BF1CVTL--BF2CVTL--Multi-vector-8-bit-floating-point-convert-to-deinterleaved-BFloat16-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svcvtl1_f16[_mf8]_x2_fpm

ISA classification: SME2 + FEAT_FP8

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvtl1_f16%5B_mf8%5D_x2_fpm

### Signature (source notation)

```c
svfloat16x2_t svcvtl1_f16[_mf8]_x2_fpm(svmfloat8_t zn, fpm_t fpm)
    __arm_streaming;
```

### Description

Multi-vector 8-bit floating-point convert to deinterleaved half-precision

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Data type conversion / Conversions

- SME attributes: `__arm_streaming`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2,FEAT_FP8
```

### Return type metadata

```json
{
  "return_base_type": "float16",
  "element_bit_size": "16",
  "value": "svfloat16x2_t"
}
```

### Argument preparation and constraints

```json
{
  "zn": {
    "register": "Zreg3.B"
  },
  "fpm": {
    "register": "Xreg1"
  }
}
```

### Result mapping

```json
[
  {
    "{ Zreg1.H, Zreg2.H }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
MSR FPMR, Xreg1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/Base-Instructions/MSR--register---Move-general-purpose-register-to-System-register-

```asm
F1CVTL { Zreg1.H, Zreg2.H }, Zreg3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/F1CVTL--F2CVTL--Multi-vector-8-bit-floating-point-convert-to-deinterleaved-half-precision-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svcvtl2_bf16[_mf8]_x2_fpm

ISA classification: SME2 + FEAT_FP8

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvtl2_bf16%5B_mf8%5D_x2_fpm

### Signature (source notation)

```c
svbfloat16x2_t svcvtl2_bf16[_mf8]_x2_fpm(svmfloat8_t zn, fpm_t fpm)
    __arm_streaming;
```

### Description

Multi-vector 8-bit floating-point convert to deinterleaved BFloat16

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Data type conversion / Conversions

- SME attributes: `__arm_streaming`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2,FEAT_FP8
```

### Return type metadata

```json
{
  "return_base_type": "bfloat16",
  "element_bit_size": "16",
  "value": "svbfloat16x2_t"
}
```

### Argument preparation and constraints

```json
{
  "zn": {
    "register": "Zreg3.B"
  },
  "fpm": {
    "register": "Xreg1"
  }
}
```

### Result mapping

```json
[
  {
    "{ Zreg1.H, Zreg2.H }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
MSR FPMR, Xreg1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/Base-Instructions/MSR--register---Move-general-purpose-register-to-System-register-

```asm
BF2CVTL { Zreg1.H, Zreg2.H }, Zreg3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/BF1CVTL--BF2CVTL--Multi-vector-8-bit-floating-point-convert-to-deinterleaved-BFloat16-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svcvtl2_f16[_mf8]_x2_fpm

ISA classification: SME2 + FEAT_FP8

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvtl2_f16%5B_mf8%5D_x2_fpm

### Signature (source notation)

```c
svfloat16x2_t svcvtl2_f16[_mf8]_x2_fpm(svmfloat8_t zn, fpm_t fpm)
    __arm_streaming;
```

### Description

Multi-vector 8-bit floating-point convert to deinterleaved half-precision

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Data type conversion / Conversions

- SME attributes: `__arm_streaming`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2,FEAT_FP8
```

### Return type metadata

```json
{
  "return_base_type": "float16",
  "element_bit_size": "16",
  "value": "svfloat16x2_t"
}
```

### Argument preparation and constraints

```json
{
  "zn": {
    "register": "Zreg3.B"
  },
  "fpm": {
    "register": "Xreg1"
  }
}
```

### Result mapping

```json
[
  {
    "{ Zreg1.H, Zreg2.H }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
MSR FPMR, Xreg1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/Base-Instructions/MSR--register---Move-general-purpose-register-to-System-register-

```asm
F2CVTL { Zreg1.H, Zreg2.H }, Zreg3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/F1CVTL--F2CVTL--Multi-vector-8-bit-floating-point-convert-to-deinterleaved-half-precision-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svcvtl_f32[_f16_x2]

ISA classification: SME2 + FEAT_SME_F16F16

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvtl_f32%5B_f16_x2%5D

### Signature (source notation)

```c
svfloat32x2_t svcvtl_f32[_f16_x2](svfloat16_t zn)
    __arm_streaming;
```

### Description

Multi-vector half-precision convert to deinterleaved single-precision

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Data type conversion / Conversions

- SME attributes: `__arm_streaming`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME_F16F16
```

### Return type metadata

```json
{
  "return_base_type": "float32",
  "element_bit_size": "32",
  "value": "svfloat32x2_t"
}
```

### Argument preparation and constraints

```json
{
  "zn": {
    "register": "Zreg3.H"
  }
}
```

### Result mapping

```json
[
  {
    "{ Zreg1.S, Zreg2.S }": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
FCVTL { Zreg1.S, Zreg2.S }, Zreg3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/FCVTL--Multi-vector-half-precision-convert-to-deinterleaved-single-precision-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svcvtlt1_bf16[_mf8]_fpm

ISA classification: SME2 + FEAT_FP8

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvtlt1_bf16%5B_mf8%5D_fpm

### Signature (source notation)

```c
svbfloat16_t svcvtlt1_bf16[_mf8]_fpm(svmfloat8_t zn, fpm_t fpm);
```

### Description

8-bit floating-point convert to BFloat16 (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Data type conversion / Conversions

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2,FEAT_FP8
```

### Return type metadata

```json
{
  "return_base_type": "bfloat16",
  "element_bit_size": "16",
  "value": "svbfloat16_t"
}
```

### Argument preparation and constraints

```json
{
  "zn": {
    "register": "Zreg2.B"
  },
  "fpm": {
    "register": "Xreg1"
  }
}
```

### Result mapping

```json
[
  {
    "Zreg1.H": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
MSR FPMR, Xreg1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/Base-Instructions/MSR--register---Move-general-purpose-register-to-System-register-

```asm
BF1CVTLT Zreg1.H, Zreg2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/BF1CVTLT--BF2CVTLT--8-bit-floating-point-convert-to-BFloat16--top--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svcvtlt1_f16[_mf8]_fpm

ISA classification: SME2 + FEAT_FP8

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvtlt1_f16%5B_mf8%5D_fpm

### Signature (source notation)

```c
svfloat16_t svcvtlt1_f16[_mf8]_fpm(svmfloat8_t zn, fpm_t fpm);
```

### Description

8-bit floating-point convert to half-precision (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Data type conversion / Conversions

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2,FEAT_FP8
```

### Return type metadata

```json
{
  "return_base_type": "float16",
  "element_bit_size": "16",
  "value": "svfloat16_t"
}
```

### Argument preparation and constraints

```json
{
  "zn": {
    "register": "Zreg2.B"
  },
  "fpm": {
    "register": "Xreg1"
  }
}
```

### Result mapping

```json
[
  {
    "Zreg1.H": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
MSR FPMR, Xreg1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/Base-Instructions/MSR--register---Move-general-purpose-register-to-System-register-

```asm
F1CVTLT Zreg1.H, Zreg2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/F1CVTLT--F2CVTLT--8-bit-floating-point-convert-to-half-precision--top--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svcvtlt2_bf16[_mf8]_fpm

ISA classification: SME2 + FEAT_FP8

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvtlt2_bf16%5B_mf8%5D_fpm

### Signature (source notation)

```c
svbfloat16_t svcvtlt2_bf16[_mf8]_fpm(svmfloat8_t zn, fpm_t fpm);
```

### Description

8-bit floating-point convert to BFloat16 (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Data type conversion / Conversions

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2,FEAT_FP8
```

### Return type metadata

```json
{
  "return_base_type": "bfloat16",
  "element_bit_size": "16",
  "value": "svbfloat16_t"
}
```

### Argument preparation and constraints

```json
{
  "zn": {
    "register": "Zreg2.B"
  },
  "fpm": {
    "register": "Xreg1"
  }
}
```

### Result mapping

```json
[
  {
    "Zreg1.H": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
MSR FPMR, Xreg1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/Base-Instructions/MSR--register---Move-general-purpose-register-to-System-register-

```asm
BF2CVTLT Zreg1.H, Zreg2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/BF1CVTLT--BF2CVTLT--8-bit-floating-point-convert-to-BFloat16--top--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svcvtlt2_f16[_mf8]_fpm

ISA classification: SME2 + FEAT_FP8

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvtlt2_f16%5B_mf8%5D_fpm

### Signature (source notation)

```c
svfloat16_t svcvtlt2_f16[_mf8]_fpm(svmfloat8_t zn, fpm_t fpm);
```

### Description

8-bit floating-point convert to half-precision (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Data type conversion / Conversions

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2,FEAT_FP8
```

### Return type metadata

```json
{
  "return_base_type": "float16",
  "element_bit_size": "16",
  "value": "svfloat16_t"
}
```

### Argument preparation and constraints

```json
{
  "zn": {
    "register": "Zreg2.B"
  },
  "fpm": {
    "register": "Xreg1"
  }
}
```

### Result mapping

```json
[
  {
    "Zreg1.H": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
MSR FPMR, Xreg1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/Base-Instructions/MSR--register---Move-general-purpose-register-to-System-register-

```asm
F2CVTLT Zreg1.H, Zreg2.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/F1CVTLT--F2CVTLT--8-bit-floating-point-convert-to-half-precision--top--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svcvtlt_f32[_f16]_z

ISA classification: SME + FEAT_SVE2p2 OR SME2.2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvtlt_f32%5B_f16%5D_z

### Signature (source notation)

```c
svfloat32_t svcvtlt_f32[_f16]_z(svbool_t pg, svfloat16_t op);
```

### Description

Floating-point widening convert (top, predicated)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Data type conversion / Conversions

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p2)|FEAT_SME2p2
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
  "pg": {
    "register": "Preg1"
  },
  "op": {
    "register": "Zreg2.H"
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
FCVTLT Zreg1.S, Preg1/Z, Zreg2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/FCVTLT--Floating-point-widening-convert--top--predicated--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svcvtlt_f64[_f32]_z

ISA classification: SME + FEAT_SVE2p2 OR SME2.2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvtlt_f64%5B_f32%5D_z

### Signature (source notation)

```c
svfloat64_t svcvtlt_f64[_f32]_z(svbool_t pg, svfloat32_t op);
```

### Description

Floating-point widening convert (top, predicated)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Data type conversion / Conversions

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p2)|FEAT_SME2p2
```

### Return type metadata

```json
{
  "return_base_type": "float64",
  "element_bit_size": "64",
  "value": "svfloat64_t"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Preg1"
  },
  "op": {
    "register": "Zreg2.S"
  }
}
```

### Result mapping

```json
[
  {
    "Zreg1.D": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
FCVTLT Zreg1.D, Preg1/Z, Zreg2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/FCVTLT--Floating-point-widening-convert--top--predicated--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svcvtn_bf16[_f32_x2]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvtn_bf16%5B_f32_x2%5D

### Signature (source notation)

```c
svbfloat16_t svcvtn_bf16[_f32_x2](svfloat32x2_t zn)
    __arm_streaming;
```

### Description

Multi-vector convert from single-precision to interleaved BFloat16 format

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Data type conversion / Conversions

- SME attributes: `__arm_streaming`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2
```

### Return type metadata

```json
{
  "return_base_type": "bfloat16",
  "element_bit_size": "16",
  "value": "svbfloat16_t"
}
```

### Argument preparation and constraints

```json
{
  "zn": {
    "Z multi-vector": "{ Zreg2.S, Zreg3.S }"
  }
}
```

### Result mapping

```json
[
  {
    "Zreg1.H": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
BFCVTN Zreg1.H, { Zreg2.S, Zreg3.S }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/BFCVTN--Multi-vector-convert-from-single-precision-to-interleaved-BFloat16-format-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svcvtn_f16[_f32_x2]

ISA classification: SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvtn_f16%5B_f32_x2%5D

### Signature (source notation)

```c
svfloat16_t svcvtn_f16[_f32_x2](svfloat32x2_t zn)
    __arm_streaming;
```

### Description

Multi-vector convert from single-precision to interleaved half-precision

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Data type conversion / Conversions

- SME attributes: `__arm_streaming`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2
```

### Return type metadata

```json
{
  "return_base_type": "float16",
  "element_bit_size": "16",
  "value": "svfloat16_t"
}
```

### Argument preparation and constraints

```json
{
  "zn": {
    "Z multi-vector": "{ Zreg2.S, Zreg3.S }"
  }
}
```

### Result mapping

```json
[
  {
    "Zreg1.H": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
FCVTN Zreg1.H, { Zreg2.S, Zreg3.S }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/FCVTN--FP32-to-FP16---Multi-vector-convert-from-single-precision-to-interleaved-half-precision-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svcvtn_mf8[_bf16_x2]_fpm

ISA classification: SME2 + FEAT_FP8

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvtn_mf8%5B_bf16_x2%5D_fpm

### Signature (source notation)

```c
svmfloat8_t svcvtn_mf8[_bf16_x2]_fpm(svbfloat16x2_t zn, fpm_t fpm);
```

### Description

BFloat16 convert to interleaved 8-bit floating-point

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Data type conversion / Conversions

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2,FEAT_FP8
```

### Return type metadata

```json
{
  "return_base_type": "mfloat8",
  "element_bit_size": "8",
  "value": "svmfloat8_t"
}
```

### Argument preparation and constraints

```json
{
  "zn": {
    "Z multi-vector": "{ Zreg2.H, Zreg3.H }"
  },
  "fpm": {
    "register": "Xreg1"
  }
}
```

### Result mapping

```json
[
  {
    "Zreg1.B": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
MSR FPMR, Xreg1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/Base-Instructions/MSR--register---Move-general-purpose-register-to-System-register-

```asm
BFCVTN Zreg1.B, { Zreg2.H, Zreg3.H }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/BFCVTN--BFloat16-convert-to-interleaved-8-bit-floating-point-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svcvtn_mf8[_f16_x2]_fpm

ISA classification: SME2 + FEAT_FP8

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvtn_mf8%5B_f16_x2%5D_fpm

### Signature (source notation)

```c
svmfloat8_t svcvtn_mf8[_f16_x2]_fpm(svfloat16x2_t zn, fpm_t fpm);
```

### Description

Half-precision convert to interleaved 8-bit floating-point

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Data type conversion / Conversions

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2,FEAT_FP8
```

### Return type metadata

```json
{
  "return_base_type": "mfloat8",
  "element_bit_size": "8",
  "value": "svmfloat8_t"
}
```

### Argument preparation and constraints

```json
{
  "zn": {
    "Z multi-vector": "{ Zreg2.H, Zreg3.H }"
  },
  "fpm": {
    "register": "Xreg1"
  }
}
```

### Result mapping

```json
[
  {
    "Zreg1.B": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
MSR FPMR, Xreg1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/Base-Instructions/MSR--register---Move-general-purpose-register-to-System-register-

```asm
FCVTN Zreg1.B, { Zreg2.H, Zreg3.H }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/FCVTN--Half-precision-convert-to-interleaved-8-bit-floating-point-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svcvtn_mf8[_f32_x4]_fpm

ISA classification: SME2 + FEAT_FP8

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvtn_mf8%5B_f32_x4%5D_fpm

### Signature (source notation)

```c
svmfloat8_t svcvtn_mf8[_f32_x4]_fpm(svfloat32x4_t zn, fpm_t fpm)
    __arm_streaming;
```

### Description

Multi-vector single-precision convert to interleaved 8-bit floating-point

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Data type conversion / Conversions

- SME attributes: `__arm_streaming`

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2,FEAT_FP8
```

### Return type metadata

```json
{
  "return_base_type": "mfloat8",
  "element_bit_size": "8",
  "value": "svmfloat8_t"
}
```

### Argument preparation and constraints

```json
{
  "zn": {
    "Z multi-vector": "{ Zreg2.S - Zreg3.S }"
  },
  "fpm": {
    "register": "Xreg1"
  }
}
```

### Result mapping

```json
[
  {
    "Zreg1.B": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
MSR FPMR, Xreg1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/Base-Instructions/MSR--register---Move-general-purpose-register-to-System-register-

```asm
FCVTN Zreg1.B, { Zreg2.S - Zreg3.S }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SME-Instructions/FCVTN--FP32-to-FP8---Multi-vector-single-precision-convert-to-interleaved-8-bit-floating-point-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svcvtnb_mf8[_f32_x2]_fpm

ISA classification: SME2 + FEAT_FP8

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvtnb_mf8%5B_f32_x2%5D_fpm

### Signature (source notation)

```c
svmfloat8_t svcvtnb_mf8[_f32_x2]_fpm(svfloat32x2_t zn, fpm_t fpm);
```

### Description

Single-precision convert to interleaved 8-bit floating-point (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Data type conversion / Conversions

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2,FEAT_FP8
```

### Return type metadata

```json
{
  "return_base_type": "mfloat8",
  "element_bit_size": "8",
  "value": "svmfloat8_t"
}
```

### Argument preparation and constraints

```json
{
  "zn": {
    "Z multi-vector": "{ Zreg2.S, Zreg3.S }"
  },
  "fpm": {
    "register": "Xreg1"
  }
}
```

### Result mapping

```json
[
  {
    "Zreg1.B": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
MSR FPMR, Xreg1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/Base-Instructions/MSR--register---Move-general-purpose-register-to-System-register-

```asm
FCVTNB Zreg1.B, { Zreg2.S, Zreg3.S }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/FCVTNB--Single-precision-convert-to-interleaved-8-bit-floating-point--bottom--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svcvtnt_bf16[_f32]_z

ISA classification: SME + FEAT_SVE2p2 OR SME2.2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvtnt_bf16%5B_f32%5D_z

### Signature (source notation)

```c
svbfloat16_t svcvtnt_bf16[_f32]_z(svbfloat16_t even, svbool_t pg, svfloat32_t op);
```

### Description

Single-precision convert to BFloat16 (top, predicated)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Data type conversion / Conversions

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p2)|FEAT_SME2p2
```

### Return type metadata

```json
{
  "return_base_type": "bfloat16",
  "element_bit_size": "16",
  "value": "svbfloat16_t"
}
```

### Argument preparation and constraints

```json
{
  "even": {
    "register": "Zreg1.H"
  },
  "pg": {
    "register": "Preg1"
  },
  "op": {
    "register": "Zreg2.S"
  }
}
```

### Result mapping

```json
[
  {
    "Zreg1.H": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
BFCVTNT Zreg1.H, Preg1/Z, Zreg2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/BFCVTNT--Single-precision-convert-to-BFloat16--top--predicated--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svcvtnt_f16[_f32]_z

ISA classification: SME + FEAT_SVE2p2 OR SME2.2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvtnt_f16%5B_f32%5D_z

### Signature (source notation)

```c
svfloat16_t svcvtnt_f16[_f32]_z(svfloat16_t even, svbool_t pg, svfloat32_t op);
```

### Description

Floating-point narrowing convert (top, predicated)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Data type conversion / Conversions

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p2)|FEAT_SME2p2
```

### Return type metadata

```json
{
  "return_base_type": "float16",
  "element_bit_size": "16",
  "value": "svfloat16_t"
}
```

### Argument preparation and constraints

```json
{
  "even": {
    "register": "Zreg1.H"
  },
  "pg": {
    "register": "Preg1"
  },
  "op": {
    "register": "Zreg2.S"
  }
}
```

### Result mapping

```json
[
  {
    "Zreg1.H": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
FCVTNT Zreg1.H, Preg1/Z, Zreg2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/FCVTNT--predicated---Floating-point-narrowing-convert--top--predicated--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svcvtnt_f32[_f64]_z

ISA classification: SME + FEAT_SVE2p2 OR SME2.2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvtnt_f32%5B_f64%5D_z

### Signature (source notation)

```c
svfloat32_t svcvtnt_f32[_f64]_z(svfloat32_t even, svbool_t pg, svfloat64_t op);
```

### Description

Floating-point narrowing convert (top, predicated)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Data type conversion / Conversions

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p2)|FEAT_SME2p2
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
  "even": {
    "register": "Zreg1.S"
  },
  "pg": {
    "register": "Preg1"
  },
  "op": {
    "register": "Zreg2.D"
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
FCVTNT Zreg1.S, Preg1/Z, Zreg2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/FCVTNT--predicated---Floating-point-narrowing-convert--top--predicated--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svcvtnt_mf8[_f32_x2]_fpm

ISA classification: SME2 + FEAT_FP8

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvtnt_mf8%5B_f32_x2%5D_fpm

### Signature (source notation)

```c
svmfloat8_t svcvtnt_mf8[_f32_x2]_fpm(svmfloat8_t zd, svfloat32x2_t zn, fpm_t fpm);
```

### Description

Single-precision convert to interleaved 8-bit floating-point (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Data type conversion / Conversions

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2,FEAT_FP8
```

### Return type metadata

```json
{
  "return_base_type": "mfloat8",
  "element_bit_size": "8",
  "value": "svmfloat8_t"
}
```

### Argument preparation and constraints

```json
{
  "zd": {
    "register": "Zreg1.B"
  },
  "zn": {
    "Z multi-vector": "{ Zreg2.S, Zreg3.S }"
  },
  "fpm": {
    "register": "Xreg1"
  }
}
```

### Result mapping

```json
[
  {
    "Zreg1.B": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
MSR FPMR, Xreg1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/Base-Instructions/MSR--register---Move-general-purpose-register-to-System-register-

```asm
FCVTNT Zreg1.B, { Zreg2.S, Zreg3.S }
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/FCVTNT--unpredicated---Single-precision-convert-to-interleaved-8-bit-floating-point--top--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svcvtxnt_f32[_f64]_z

ISA classification: SME + FEAT_SVE2p2 OR SME2.2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcvtxnt_f32%5B_f64%5D_z

### Signature (source notation)

```c
svfloat32_t svcvtxnt_f32[_f64]_z(svfloat32_t even, svbool_t pg, svfloat64_t op);
```

### Description

Double-precision convert to single-precision, rounding to odd (top, predicated)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Data type conversion / Conversions

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
(FEAT_SME,FEAT_SVE2p2)|FEAT_SME2p2
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
  "even": {
    "register": "Zreg1.S"
  },
  "pg": {
    "register": "Preg1"
  },
  "op": {
    "register": "Zreg2.D"
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
FCVTXNT Zreg1.S, Preg1/Z, Zreg2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/FCVTXNT--Double-precision-convert-to-single-precision--rounding-to-odd--top--predicated--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

