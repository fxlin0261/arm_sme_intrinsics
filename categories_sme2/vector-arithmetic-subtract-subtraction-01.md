# SME2 / Vector arithmetic / Subtract / Subtraction — Part 1

## svsub[_bf16]_m

ISA classification: SME2 + FEAT_SVE_B16B16

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsub%5B_bf16%5D_m

### Signature (source notation)

```c
svbfloat16_t svsub[_bf16]_m(svbool_t pg, svbfloat16_t zdn, svbfloat16_t zm);
```

### Description

BFloat16 subtract (predicated)

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Subtract / Subtraction

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2,FEAT_SVE_B16B16
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
  "pg": {
    "register": "Preg1"
  },
  "zdn": {
    "register": "Zreg1.H"
  },
  "zm": {
    "register": "Zreg2.H"
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
BFSUB Zreg1.H, Preg1/M, Zreg1.H, Zreg2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/BFSUB--predicated---BFloat16-subtract--predicated--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svsub[_bf16]_x

ISA classification: SME2 + FEAT_SVE_B16B16

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsub%5B_bf16%5D_x

### Signature (source notation)

```c
svbfloat16_t svsub[_bf16]_x(svbool_t pg, svbfloat16_t zdn, svbfloat16_t zm);
```

### Description

BFloat16 subtract (predicated)

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Subtract / Subtraction

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2,FEAT_SVE_B16B16
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
  "pg": {
    "register": "Preg1"
  },
  "zdn": {
    "register": "Zreg1.H"
  },
  "zm": {
    "register": "Zreg2.H"
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
BFSUB Zreg1.H, Preg1/M, Zreg1.H, Zreg2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/BFSUB--predicated---BFloat16-subtract--predicated--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svsub[_bf16]_z

ISA classification: SME2 + FEAT_SVE_B16B16

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsub%5B_bf16%5D_z

### Signature (source notation)

```c
svbfloat16_t svsub[_bf16]_z(svbool_t pg, svbfloat16_t zdn, svbfloat16_t zm);
```

### Description

BFloat16 subtract (predicated)

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Subtract / Subtraction

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2,FEAT_SVE_B16B16
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
  "pg": {
    "register": "Preg1"
  },
  "zdn": {
    "register": "Zreg1.H"
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
    "Zreg1.H": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
MOVI Vreg2.2D, #0000000000000000
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SIMD-FP-Instructions/MOVI--Move-immediate--vector--

```asm
SEL Zreg1.H, Preg1, Zreg1.H, Zreg2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/SEL--vectors---Conditionally-select-elements-from-two-vectors-

```asm
BFSUB Zreg1.H, Preg1/M, Zreg1.H, Zreg3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/BFSUB--predicated---BFloat16-subtract--predicated--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svsub[_n_bf16]_m

ISA classification: SME2 + FEAT_SVE_B16B16

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsub%5B_n_bf16%5D_m

### Signature (source notation)

```c
svbfloat16_t svsub[_n_bf16]_m(svbool_t pg, svbfloat16_t zdn, bfloat16_t zm);
```

### Description

BFloat16 subtract (predicated)

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Subtract / Subtraction

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2,FEAT_SVE_B16B16
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
  "pg": {
    "register": "Preg1"
  },
  "zdn": {
    "register": "Zreg2.H"
  },
  "zm": {
    "register": "Hreg1"
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
MOV Zreg1.H, Hreg1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/MOV--SIMD-FP-scalar--unpredicated---Move-indexed-element-or-SIMD-FP-scalar-to-vector--unpredicated---an-alias-of-DUP--indexed--

```asm
BFSUB Zreg2.H, Preg1/M, Zreg2.H, Zreg1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/BFSUB--predicated---BFloat16-subtract--predicated--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svsub[_n_bf16]_x

ISA classification: SME2 + FEAT_SVE_B16B16

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsub%5B_n_bf16%5D_x

### Signature (source notation)

```c
svbfloat16_t svsub[_n_bf16]_x(svbool_t pg, svbfloat16_t zdn, bfloat16_t zm);
```

### Description

BFloat16 subtract (predicated)

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Subtract / Subtraction

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2,FEAT_SVE_B16B16
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
  "pg": {
    "register": "Preg1"
  },
  "zdn": {
    "register": "Zreg2.H"
  },
  "zm": {
    "register": "Hreg1"
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
MOV Zreg1.H, Hreg1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/MOV--SIMD-FP-scalar--unpredicated---Move-indexed-element-or-SIMD-FP-scalar-to-vector--unpredicated---an-alias-of-DUP--indexed--

```asm
BFSUB Zreg2.H, Preg1/M, Zreg2.H, Zreg1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/BFSUB--predicated---BFloat16-subtract--predicated--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svsub[_n_bf16]_z

ISA classification: SME2 + FEAT_SVE_B16B16

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svsub%5B_n_bf16%5D_z

### Signature (source notation)

```c
svbfloat16_t svsub[_n_bf16]_z(svbool_t pg, svbfloat16_t zdn, bfloat16_t zm);
```

### Description

BFloat16 subtract (predicated)

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Subtract / Subtraction

- SME attributes: Not specified by source.

### Required streaming features

This intrinsic requires the following [ architecture features](https://developer.arm.com/documentation/109697/) to be run in streaming mode and appear in streaming functions (functions marked with the __arm_streaming attribute).

Source feature expression (verbatim):

```text
FEAT_SME2,FEAT_SVE_B16B16
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
  "pg": {
    "register": "Preg1"
  },
  "zdn": {
    "register": "Zreg2.H"
  },
  "zm": {
    "register": "Hreg1"
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
MOVI Vreg3.2D, #0000000000000000
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SIMD-FP-Instructions/MOVI--Move-immediate--vector--

```asm
MOV Zreg1.H, Hreg1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/MOV--SIMD-FP-scalar--unpredicated---Move-indexed-element-or-SIMD-FP-scalar-to-vector--unpredicated---an-alias-of-DUP--indexed--

```asm
SEL Zreg2.H, Preg1, Zreg2.H, Zreg3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/SEL--vectors---Conditionally-select-elements-from-two-vectors-

```asm
BFSUB Zreg2.H, Preg1/M, Zreg2.H, Zreg1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/BFSUB--predicated---BFloat16-subtract--predicated--

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

