# SME2 / Vector arithmetic / Multiply-accumulate / Multiply-accumulate and widen — Part 1

## svbfmlslb[_f32]

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svbfmlslb%5B_f32%5D

### Signature (source notation)

```c
svfloat32_t svbfmlslb[_f32](svfloat32_t zda, svbfloat16_t zn, svbfloat16_t zm);
```

### Description

BFloat16 multiply-subtract long from single-precision (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Multiply-accumulate and widen

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
BFMLSLB Zreg1.S, Zreg2.H, Zreg3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BFMLSLB--vectors---BFloat16-multiply-subtract-long-from-single-precision--bottom--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svbfmlslb_lane[_f32]

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svbfmlslb_lane%5B_f32%5D

### Signature (source notation)

```c
svfloat32_t svbfmlslb_lane[_f32](svfloat32_t zda, svbfloat16_t zn, svbfloat16_t zm, uint64_t imm_idx);
```

### Description

BFloat16 multiply-subtract long from single-precision (bottom, indexed)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Multiply-accumulate and widen

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
BFMLSLB Zreg1.S, Zreg2.H, Zreg3.H[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BFMLSLB--indexed---BFloat16-multiply-subtract-long-from-single-precision--bottom--indexed--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svbfmlslt[_f32]

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svbfmlslt%5B_f32%5D

### Signature (source notation)

```c
svfloat32_t svbfmlslt[_f32](svfloat32_t zda, svbfloat16_t zn, svbfloat16_t zm);
```

### Description

BFloat16 multiply-subtract long from single-precision (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Multiply-accumulate and widen

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
BFMLSLT Zreg1.S, Zreg2.H, Zreg3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BFMLSLT--vectors---BFloat16-multiply-subtract-long-from-single-precision--top--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svbfmlslt_lane[_f32]

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svbfmlslt_lane%5B_f32%5D

### Signature (source notation)

```c
svfloat32_t svbfmlslt_lane[_f32](svfloat32_t zda, svbfloat16_t zn, svbfloat16_t zm, uint64_t imm_idx);
```

### Description

BFloat16 multiply-subtract long from single-precision (top, indexed)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Multiply-accumulate and widen

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
BFMLSLT Zreg1.S, Zreg2.H, Zreg3.H[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BFMLSLT--indexed---BFloat16-multiply-subtract-long-from-single-precision--top--indexed--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmlalb[_f16_mf8]_fpm

ISA classification: SME2 + FEAT_SSVE_FP8FMA

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmlalb%5B_f16_mf8%5D_fpm

### Signature (source notation)

```c
svfloat16_t svmlalb[_f16_mf8]_fpm(svfloat16_t zda, svmfloat8_t zn, svmfloat8_t zm, fpm_t fpm);
```

### Description

8-bit floating-point multiply-add to half-precision (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Multiply-accumulate and widen

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME,FEAT_SSVE_FP8FMA
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
  "zda": {
    "register": "Zreg1.H"
  },
  "zn": {
    "register": "Zreg2.B"
  },
  "zm": {
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
FMLALB Zreg1.H, Zreg2.B, Zreg3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/FMLALB--vectors--FP8-to-FP16---8-bit-floating-point-multiply-add-to-half-precision--bottom--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmlalb[_n_f16_mf8]_fpm

ISA classification: SME2 + FEAT_SSVE_FP8FMA

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmlalb%5B_n_f16_mf8%5D_fpm

### Signature (source notation)

```c
svfloat16_t svmlalb[_n_f16_mf8]_fpm(svfloat16_t zda, svmfloat8_t zn, mfloat8_t zm, fpm_t fpm);
```

### Description

8-bit floating-point multiply-add to half-precision (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Multiply-accumulate and widen

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME,FEAT_SSVE_FP8FMA
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
  "zda": {
    "register": "Zreg2.H"
  },
  "zn": {
    "register": "Zreg3.B"
  },
  "zm": {
    "register": "Breg1"
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
    "Zreg2.H": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
MOV Zreg1.B, Breg1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/MOV--SIMD-FP-scalar--unpredicated---Move-indexed-element-or-SIMD-FP-scalar-to-vector--unpredicated---an-alias-of-DUP--indexed--

```asm
MSR FPMR, Xreg1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/Base-Instructions/MSR--register---Move-general-purpose-register-to-System-register-

```asm
FMLALB Zreg2.H, Zreg3.B, Zreg1.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/FMLALB--vectors--FP8-to-FP16---8-bit-floating-point-multiply-add-to-half-precision--bottom--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmlalb_lane[_f16_mf8]_fpm

ISA classification: SME2 + FEAT_SSVE_FP8FMA

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmlalb_lane%5B_f16_mf8%5D_fpm

### Signature (source notation)

```c
svfloat16_t svmlalb_lane[_f16_mf8]_fpm(svfloat16_t zda, svmfloat8_t zn, svmfloat8_t zm, uint64_t imm0_15, fpm_t fpm);
```

### Description

8-bit floating-point multiply-add by indexed element to half-precision (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Multiply-accumulate and widen

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME,FEAT_SSVE_FP8FMA
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
  "zda": {
    "register": "Zreg1.H"
  },
  "zn": {
    "register": "Zreg2.B"
  },
  "zm": {
    "register": "Zreg3.B"
  },
  "imm0_15": {
    "immediate": "imm1"
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
FMLALB Zreg1.H, Zreg2.B, Zreg3.B[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/FMLALB--indexed--FP8-to-FP16---8-bit-floating-point-multiply-add-by-indexed-element-to-half-precision--bottom--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmlallbb[_f32_mf8]_fpm

ISA classification: SME2 + FEAT_SSVE_FP8FMA

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmlallbb%5B_f32_mf8%5D_fpm

### Signature (source notation)

```c
svfloat32_t svmlallbb[_f32_mf8]_fpm(svfloat32_t zda, svmfloat8_t zn, svmfloat8_t zm, fpm_t fpm);
```

### Description

8-bit floating-point multiply-add to single-precision (bottom bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Multiply-accumulate and widen

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME,FEAT_SSVE_FP8FMA
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
    "register": "Zreg2.B"
  },
  "zm": {
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
    "Zreg1.S": "result"
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
FMLALLBB Zreg1.S, Zreg2.B, Zreg3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/FMLALLBB--vectors---8-bit-floating-point-multiply-add-to-single-precision--bottom-bottom--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmlallbb[_n_f32_mf8]_fpm

ISA classification: SME2 + FEAT_SSVE_FP8FMA

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmlallbb%5B_n_f32_mf8%5D_fpm

### Signature (source notation)

```c
svfloat32_t svmlallbb[_n_f32_mf8]_fpm(svfloat32_t zda, svmfloat8_t zn, mfloat8_t zm, fpm_t fpm);
```

### Description

8-bit floating-point multiply-add to single-precision (bottom bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Multiply-accumulate and widen

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME,FEAT_SSVE_FP8FMA
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
    "register": "Zreg2.S"
  },
  "zn": {
    "register": "Zreg3.B"
  },
  "zm": {
    "register": "Breg1"
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
    "Zreg2.S": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
MOV Zreg1.B, Breg1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/MOV--SIMD-FP-scalar--unpredicated---Move-indexed-element-or-SIMD-FP-scalar-to-vector--unpredicated---an-alias-of-DUP--indexed--

```asm
MSR FPMR, Xreg1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/Base-Instructions/MSR--register---Move-general-purpose-register-to-System-register-

```asm
FMLALLBB Zreg2.S, Zreg3.B, Zreg1.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/FMLALLBB--vectors---8-bit-floating-point-multiply-add-to-single-precision--bottom-bottom--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmlallbb_lane[_f32_mf8]_fpm

ISA classification: SME2 + FEAT_SSVE_FP8FMA

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmlallbb_lane%5B_f32_mf8%5D_fpm

### Signature (source notation)

```c
svfloat32_t svmlallbb_lane[_f32_mf8]_fpm(svfloat32_t zda, svmfloat8_t zn, svmfloat8_t zm, uint64_t imm0_15, fpm_t fpm);
```

### Description

8-bit floating-point multiply-add by indexed element to single-precision (bottom bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Multiply-accumulate and widen

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME,FEAT_SSVE_FP8FMA
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
    "register": "Zreg2.B"
  },
  "zm": {
    "register": "Zreg3.B"
  },
  "imm0_15": {
    "immediate": "imm1"
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
    "Zreg1.S": "result"
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
FMLALLBB Zreg1.S, Zreg2.B, Zreg3.B[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/FMLALLBB--indexed---8-bit-floating-point-multiply-add-by-indexed-element-to-single-precision--bottom-bottom--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmlallbt[_f32_mf8]_fpm

ISA classification: SME2 + FEAT_SSVE_FP8FMA

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmlallbt%5B_f32_mf8%5D_fpm

### Signature (source notation)

```c
svfloat32_t svmlallbt[_f32_mf8]_fpm(svfloat32_t zda, svmfloat8_t zn, svmfloat8_t zm, fpm_t fpm);
```

### Description

8-bit floating-point multiply-add to single-precision (bottom top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Multiply-accumulate and widen

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME,FEAT_SSVE_FP8FMA
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
    "register": "Zreg2.B"
  },
  "zm": {
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
    "Zreg1.S": "result"
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
FMLALLBT Zreg1.S, Zreg2.B, Zreg3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/FMLALLBT--vectors---8-bit-floating-point-multiply-add-to-single-precision--bottom-top--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmlallbt[_n_f32_mf8]_fpm

ISA classification: SME2 + FEAT_SSVE_FP8FMA

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmlallbt%5B_n_f32_mf8%5D_fpm

### Signature (source notation)

```c
svfloat32_t svmlallbt[_n_f32_mf8]_fpm(svfloat32_t zda, svmfloat8_t zn, mfloat8_t zm, fpm_t fpm);
```

### Description

8-bit floating-point multiply-add to single-precision (bottom top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Multiply-accumulate and widen

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME,FEAT_SSVE_FP8FMA
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
    "register": "Zreg2.S"
  },
  "zn": {
    "register": "Zreg3.B"
  },
  "zm": {
    "register": "Breg1"
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
    "Zreg2.S": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
MOV Zreg1.B, Breg1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/MOV--SIMD-FP-scalar--unpredicated---Move-indexed-element-or-SIMD-FP-scalar-to-vector--unpredicated---an-alias-of-DUP--indexed--

```asm
MSR FPMR, Xreg1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/Base-Instructions/MSR--register---Move-general-purpose-register-to-System-register-

```asm
FMLALLBT Zreg2.S, Zreg3.B, Zreg1.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/FMLALLBT--vectors---8-bit-floating-point-multiply-add-to-single-precision--bottom-top--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmlallbt_lane[_f32_mf8]_fpm

ISA classification: SME2 + FEAT_SSVE_FP8FMA

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmlallbt_lane%5B_f32_mf8%5D_fpm

### Signature (source notation)

```c
svfloat32_t svmlallbt_lane[_f32_mf8]_fpm(svfloat32_t zda, svmfloat8_t zn, svmfloat8_t zm, uint64_t imm0_15, fpm_t fpm);
```

### Description

8-bit floating-point multiply-add by indexed element to single-precision (bottom top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Multiply-accumulate and widen

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME,FEAT_SSVE_FP8FMA
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
    "register": "Zreg2.B"
  },
  "zm": {
    "register": "Zreg3.B"
  },
  "imm0_15": {
    "immediate": "imm1"
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
    "Zreg1.S": "result"
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
FMLALLBT Zreg1.S, Zreg2.B, Zreg3.B[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/FMLALLBT--indexed---8-bit-floating-point-multiply-add-by-indexed-element-to-single-precision--bottom-top--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmlalltb[_f32_mf8]_fpm

ISA classification: SME2 + FEAT_SSVE_FP8FMA

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmlalltb%5B_f32_mf8%5D_fpm

### Signature (source notation)

```c
svfloat32_t svmlalltb[_f32_mf8]_fpm(svfloat32_t zda, svmfloat8_t zn, svmfloat8_t zm, fpm_t fpm);
```

### Description

8-bit floating-point multiply-add to single-precision (top bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Multiply-accumulate and widen

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME,FEAT_SSVE_FP8FMA
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
    "register": "Zreg2.B"
  },
  "zm": {
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
    "Zreg1.S": "result"
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
FMLALLTB Zreg1.S, Zreg2.B, Zreg3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/FMLALLTB--vectors---8-bit-floating-point-multiply-add-to-single-precision--top-bottom--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmlalltb[_n_f32_mf8]_fpm

ISA classification: SME2 + FEAT_SSVE_FP8FMA

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmlalltb%5B_n_f32_mf8%5D_fpm

### Signature (source notation)

```c
svfloat32_t svmlalltb[_n_f32_mf8]_fpm(svfloat32_t zda, svmfloat8_t zn, mfloat8_t zm, fpm_t fpm);
```

### Description

8-bit floating-point multiply-add to single-precision (top bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Multiply-accumulate and widen

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME,FEAT_SSVE_FP8FMA
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
    "register": "Zreg2.S"
  },
  "zn": {
    "register": "Zreg3.B"
  },
  "zm": {
    "register": "Breg1"
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
    "Zreg2.S": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
MOV Zreg1.B, Breg1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/MOV--SIMD-FP-scalar--unpredicated---Move-indexed-element-or-SIMD-FP-scalar-to-vector--unpredicated---an-alias-of-DUP--indexed--

```asm
MSR FPMR, Xreg1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/Base-Instructions/MSR--register---Move-general-purpose-register-to-System-register-

```asm
FMLALLTB Zreg2.S, Zreg3.B, Zreg1.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/FMLALLTB--vectors---8-bit-floating-point-multiply-add-to-single-precision--top-bottom--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmlalltb_lane[_f32_mf8]_fpm

ISA classification: SME2 + FEAT_SSVE_FP8FMA

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmlalltb_lane%5B_f32_mf8%5D_fpm

### Signature (source notation)

```c
svfloat32_t svmlalltb_lane[_f32_mf8]_fpm(svfloat32_t zda, svmfloat8_t zn, svmfloat8_t zm, uint64_t imm0_15, fpm_t fpm);
```

### Description

8-bit floating-point multiply-add by indexed element to single-precision (top bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Multiply-accumulate and widen

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME,FEAT_SSVE_FP8FMA
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
    "register": "Zreg2.B"
  },
  "zm": {
    "register": "Zreg3.B"
  },
  "imm0_15": {
    "immediate": "imm1"
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
    "Zreg1.S": "result"
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
FMLALLTB Zreg1.S, Zreg2.B, Zreg3.B[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/FMLALLTB--indexed---8-bit-floating-point-multiply-add-by-indexed-element-to-single-precision--top-bottom--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmlalltt[_f32_mf8]_fpm

ISA classification: SME2 + FEAT_SSVE_FP8FMA

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmlalltt%5B_f32_mf8%5D_fpm

### Signature (source notation)

```c
svfloat32_t svmlalltt[_f32_mf8]_fpm(svfloat32_t zda, svmfloat8_t zn, svmfloat8_t zm, fpm_t fpm);
```

### Description

8-bit floating-point multiply-add to single-precision (top top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Multiply-accumulate and widen

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME,FEAT_SSVE_FP8FMA
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
    "register": "Zreg2.B"
  },
  "zm": {
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
    "Zreg1.S": "result"
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
FMLALLTT Zreg1.S, Zreg2.B, Zreg3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/FMLALLTT--vectors---8-bit-floating-point-multiply-add-to-single-precision--top-top--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmlalltt[_n_f32_mf8]_fpm

ISA classification: SME2 + FEAT_SSVE_FP8FMA

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmlalltt%5B_n_f32_mf8%5D_fpm

### Signature (source notation)

```c
svfloat32_t svmlalltt[_n_f32_mf8]_fpm(svfloat32_t zda, svmfloat8_t zn, mfloat8_t zm, fpm_t fpm);
```

### Description

8-bit floating-point multiply-add to single-precision (top top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Multiply-accumulate and widen

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME,FEAT_SSVE_FP8FMA
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
    "register": "Zreg2.S"
  },
  "zn": {
    "register": "Zreg3.B"
  },
  "zm": {
    "register": "Breg1"
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
    "Zreg2.S": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
MOV Zreg1.B, Breg1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/MOV--SIMD-FP-scalar--unpredicated---Move-indexed-element-or-SIMD-FP-scalar-to-vector--unpredicated---an-alias-of-DUP--indexed--

```asm
MSR FPMR, Xreg1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/Base-Instructions/MSR--register---Move-general-purpose-register-to-System-register-

```asm
FMLALLTT Zreg2.S, Zreg3.B, Zreg1.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/FMLALLTT--vectors---8-bit-floating-point-multiply-add-to-single-precision--top-top--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmlalltt_lane[_f32_mf8]_fpm

ISA classification: SME2 + FEAT_SSVE_FP8FMA

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmlalltt_lane%5B_f32_mf8%5D_fpm

### Signature (source notation)

```c
svfloat32_t svmlalltt_lane[_f32_mf8]_fpm(svfloat32_t zda, svmfloat8_t zn, svmfloat8_t zm, uint64_t imm0_15, fpm_t fpm);
```

### Description

8-bit floating-point multiply-add by indexed element to single-precision (top top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Multiply-accumulate and widen

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME,FEAT_SSVE_FP8FMA
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
    "register": "Zreg2.B"
  },
  "zm": {
    "register": "Zreg3.B"
  },
  "imm0_15": {
    "immediate": "imm1"
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
    "Zreg1.S": "result"
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
FMLALLTT Zreg1.S, Zreg2.B, Zreg3.B[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/FMLALLTT--indexed---8-bit-floating-point-multiply-add-by-indexed-element-to-single-precision--top-top--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmlalt[_f16_mf8]_fpm

ISA classification: SME2 + FEAT_SSVE_FP8FMA

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmlalt%5B_f16_mf8%5D_fpm

### Signature (source notation)

```c
svfloat16_t svmlalt[_f16_mf8]_fpm(svfloat16_t zda, svmfloat8_t zn, svmfloat8_t zm, fpm_t fpm);
```

### Description

8-bit floating-point multiply-add to half-precision (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Multiply-accumulate and widen

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME,FEAT_SSVE_FP8FMA
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
  "zda": {
    "register": "Zreg1.H"
  },
  "zn": {
    "register": "Zreg2.B"
  },
  "zm": {
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
FMLALT Zreg1.H, Zreg2.B, Zreg3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/FMLALT--vectors--FP8-to-FP16---8-bit-floating-point-multiply-add-to-half-precision--top--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmlalt[_n_f16_mf8]_fpm

ISA classification: SME2 + FEAT_SSVE_FP8FMA

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmlalt%5B_n_f16_mf8%5D_fpm

### Signature (source notation)

```c
svfloat16_t svmlalt[_n_f16_mf8]_fpm(svfloat16_t zda, svmfloat8_t zn, mfloat8_t zm, fpm_t fpm);
```

### Description

8-bit floating-point multiply-add to half-precision (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Multiply-accumulate and widen

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME,FEAT_SSVE_FP8FMA
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
  "zda": {
    "register": "Zreg2.H"
  },
  "zn": {
    "register": "Zreg3.B"
  },
  "zm": {
    "register": "Breg1"
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
    "Zreg2.H": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
MOV Zreg1.B, Breg1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/MOV--SIMD-FP-scalar--unpredicated---Move-indexed-element-or-SIMD-FP-scalar-to-vector--unpredicated---an-alias-of-DUP--indexed--

```asm
MSR FPMR, Xreg1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/Base-Instructions/MSR--register---Move-general-purpose-register-to-System-register-

```asm
FMLALT Zreg2.H, Zreg3.B, Zreg1.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/FMLALT--vectors--FP8-to-FP16---8-bit-floating-point-multiply-add-to-half-precision--top--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svmlalt_lane[_f16_mf8]_fpm

ISA classification: SME2 + FEAT_SSVE_FP8FMA

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmlalt_lane%5B_f16_mf8%5D_fpm

### Signature (source notation)

```c
svfloat16_t svmlalt_lane[_f16_mf8]_fpm(svfloat16_t zda, svmfloat8_t zn, svmfloat8_t zm, uint64_t imm0_15, fpm_t fpm);
```

### Description

8-bit floating-point multiply-add by indexed element to half-precision (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Multiply-accumulate and widen

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME,FEAT_SSVE_FP8FMA
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
  "zda": {
    "register": "Zreg1.H"
  },
  "zn": {
    "register": "Zreg2.B"
  },
  "zm": {
    "register": "Zreg3.B"
  },
  "imm0_15": {
    "immediate": "imm1"
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
FMLALT Zreg1.H, Zreg2.B, Zreg3.B[imm1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/FMLALT--indexed--FP8-to-FP16---8-bit-floating-point-multiply-add-by-indexed-element-to-half-precision--top--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

