# SME / Vector arithmetic / Multiply-accumulate / Multiply-accumulate and widen — Part 1

## svbfmlalb[_f32]

ISA classification: SME + FEAT_BF16

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svbfmlalb%5B_f32%5D

### Signature (source notation)

```c
svfloat32_t svbfmlalb[_f32](svfloat32_t op1, svbfloat16_t op2, svbfloat16_t op3);
```

### Description

BFloat16 multiply-add long to single-precision (bottom)

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Multiply-accumulate and widen

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
BFMLALB Ztied1.S, Zop2.H, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BFMLALB--vectors---BFloat16-multiply-add-long-to-single-precision--bottom--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
BFMLALB Zresult.S, Zop2.H, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BFMLALB--vectors---BFloat16-multiply-add-long-to-single-precision--bottom--

### Operation

Source operation ID: `SveOperation_svbfmlalb_f32`

**Operation**



Return a vector in which element *i* contains:



```text
op1[i] + (float)op2[i * 2] * (float)op3[i * 2]
```



The multiplication and addition are fused, with no intermediate rounding after the multiplication.



**Exceptions**



Signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not. Multiplying an infinity by zero also triggers an IEEE Invalid exception, as does adding +∞ and -∞ together.

## svbfmlalb[_n_f32]

ISA classification: SME + FEAT_BF16

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svbfmlalb%5B_n_f32%5D

### Signature (source notation)

```c
svfloat32_t svbfmlalb[_n_f32](svfloat32_t op1, svbfloat16_t op2, bfloat16_t op3);
```

### Description

BFloat16 multiply-add long to single-precision (bottom)

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Multiply-accumulate and widen

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
BFMLALB Ztied1.S, Zop2.H, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BFMLALB--vectors---BFloat16-multiply-add-long-to-single-precision--bottom--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
BFMLALB Zresult.S, Zop2.H, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BFMLALB--vectors---BFloat16-multiply-add-long-to-single-precision--bottom--

### Operation

Source operation ID: `SveOperation_svbfmlalb_n_f32`

**Operation**



Return a vector in which element *i* contains:



```text
op1[i] + (float)op2[i * 2] * (float)op3
```



The multiplication and addition are fused, with no intermediate rounding after the multiplication.



**Exceptions**



Signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not. Multiplying an infinity by zero also triggers an IEEE Invalid exception, as does adding +∞ and -∞ together.

## svbfmlalb_lane[_f32]

ISA classification: SME + FEAT_BF16

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svbfmlalb_lane%5B_f32%5D

### Signature (source notation)

```c
svfloat32_t svbfmlalb_lane[_f32](svfloat32_t op1, svbfloat16_t op2, svbfloat16_t op3, uint64_t imm_index);
```

### Description

BFloat16 multiply-add long to single-precision (bottom)

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Multiply-accumulate and widen

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
    "maximum": 7
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
BFMLALB Ztied1.S, Zop2.H, Zop3.H[imm_index]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BFMLALB--indexed---BFloat16-multiply-add-long-to-single-precision--bottom--indexed--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
BFMLALB Zresult.S, Zop2.H, Zop3.H[imm_index]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BFMLALB--indexed---BFloat16-multiply-add-long-to-single-precision--bottom--indexed--

### Operation

Source operation ID: `SveOperation_svbfmlalb_lane_f32`

**Operation**



Return a vector in which element *i* contains:



```text
op1[i] + (float)op2[i * 2] * (float)op3[base + imm_index]
```



where `op3[base]` is the first element in the same 128-bit quadword as `op3[i * 2]`.



The multiplication and addition are fused, with no intermediate rounding after the multiplication.



**Exceptions**



Signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not. Multiplying an infinity by zero also triggers an IEEE Invalid exception, as does adding +∞ and -∞ together.

## svbfmlalt[_f32]

ISA classification: SME + FEAT_BF16

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svbfmlalt%5B_f32%5D

### Signature (source notation)

```c
svfloat32_t svbfmlalt[_f32](svfloat32_t op1, svbfloat16_t op2, svbfloat16_t op3);
```

### Description

BFloat16 multiply-add long to single-precision (top)

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Multiply-accumulate and widen

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
BFMLALT Ztied1.S, Zop2.H, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BFMLALT--vectors---BFloat16-multiply-add-long-to-single-precision--top--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
BFMLALT Zresult.S, Zop2.H, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BFMLALT--vectors---BFloat16-multiply-add-long-to-single-precision--top--

### Operation

Source operation ID: `SveOperation_svbfmlalt_f32`

**Operation**



Return a vector in which element *i* contains:



```text
op1[i] + (float)op2[i * 2 + 1] * (float)op3[i * 2 + 1]
```



The multiplication and addition are fused, with no intermediate rounding after the multiplication.



**Exceptions**



Signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not. Multiplying an infinity by zero also triggers an IEEE Invalid exception, as does adding +∞ and -∞ together.

## svbfmlalt[_n_f32]

ISA classification: SME + FEAT_BF16

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svbfmlalt%5B_n_f32%5D

### Signature (source notation)

```c
svfloat32_t svbfmlalt[_n_f32](svfloat32_t op1, svbfloat16_t op2, bfloat16_t op3);
```

### Description

BFloat16 multiply-add long to single-precision (top)

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Multiply-accumulate and widen

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
BFMLALT Ztied1.S, Zop2.H, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BFMLALT--vectors---BFloat16-multiply-add-long-to-single-precision--top--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
BFMLALT Zresult.S, Zop2.H, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BFMLALT--vectors---BFloat16-multiply-add-long-to-single-precision--top--

### Operation

Source operation ID: `SveOperation_svbfmlalt_n_f32`

**Operation**



Return a vector in which element *i* contains:



```text
op1[i] + (float)op2[i * 2 + 1] * (float)op3
```



The multiplication and addition are fused, with no intermediate rounding after the multiplication.



**Exceptions**



Signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not. Multiplying an infinity by zero also triggers an IEEE Invalid exception, as does adding +∞ and -∞ together.

## svbfmlalt_lane[_f32]

ISA classification: SME + FEAT_BF16

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svbfmlalt_lane%5B_f32%5D

### Signature (source notation)

```c
svfloat32_t svbfmlalt_lane[_f32](svfloat32_t op1, svbfloat16_t op2, svbfloat16_t op3, uint64_t imm_index);
```

### Description

BFloat16 multiply-add long to single-precision (top)

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Multiply-accumulate and widen

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
    "maximum": 7
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
BFMLALT Ztied1.S, Zop2.H, Zop3.H[imm_index]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BFMLALT--indexed---BFloat16-multiply-add-long-to-single-precision--top--indexed--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
BFMLALT Zresult.S, Zop2.H, Zop3.H[imm_index]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/BFMLALT--indexed---BFloat16-multiply-add-long-to-single-precision--top--indexed--

### Operation

Source operation ID: `SveOperation_svbfmlalt_lane_f32`

**Operation**



Return a vector in which element *i* contains:



```text
op1[i] + (float)op2[i * 2 + 1] * (float)op3[base + imm_index]
```



where `op3[base]` is the first element in the same 128-bit quadword as `op3[i * 2]`.



The multiplication and addition are fused, with no intermediate rounding after the multiplication.



**Exceptions**



Signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not. Multiplying an infinity by zero also triggers an IEEE Invalid exception, as does adding +∞ and -∞ together.

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

## svmlalb[_f32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmlalb%5B_f32%5D

### Signature (source notation)

```c
svfloat32_t svmlalb[_f32](svfloat32_t op1, svfloat16_t op2, svfloat16_t op3);
```

### Description

Multiply-add long (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Multiply-accumulate and widen

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
FMLALB Ztied1.S, Zop2.H, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMLALB--vectors--FP16-to-FP32---Half-precision-multiply-add-long-to-single-precision--bottom--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FMLALB Zresult.S, Zop2.H, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMLALB--vectors--FP16-to-FP32---Half-precision-multiply-add-long-to-single-precision--bottom--

### Operation

Source operation ID: `SveOperation_svmlalb_f32`

**Operation**



Return a vector in which each element *i* contains:



```text
op1[i] + (float32_t)op2[i * 2] * (float32_t)op3[i * 2]
```



The multiplication and addition are fused, with no intermediate rounding after the multiplication.



**Exceptions**



Signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not. Multiplying an infinity by zero also triggers an IEEE Invalid exception, as does adding +∞ and -∞ together.

## svmlalb[_n_f32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmlalb%5B_n_f32%5D

### Signature (source notation)

```c
svfloat32_t svmlalb[_n_f32](svfloat32_t op1, svfloat16_t op2, float16_t op3);
```

### Description

Multiply-add long (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Multiply-accumulate and widen

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
FMLALB Ztied1.S, Zop2.H, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMLALB--vectors--FP16-to-FP32---Half-precision-multiply-add-long-to-single-precision--bottom--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FMLALB Zresult.S, Zop2.H, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMLALB--vectors--FP16-to-FP32---Half-precision-multiply-add-long-to-single-precision--bottom--

### Operation

Source operation ID: `SveOperation_svmlalb_n_f32`

**Operation**



Return a vector in which each element *i* contains:



```text
op1[i] + (float32_t)op2[i * 2] * (float32_t)op3
```



The multiplication and addition are fused, with no intermediate rounding after the multiplication.



**Exceptions**



Signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not. Multiplying an infinity by zero also triggers an IEEE Invalid exception, as does adding +∞ and -∞ together.

## svmlalb[_n_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmlalb%5B_n_s16%5D

### Signature (source notation)

```c
svint16_t svmlalb[_n_s16](svint16_t op1, svint8_t op2, int8_t op3);
```

### Description

Multiply-add long (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Multiply-accumulate and widen

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
    "Zresult.H|Ztied1.H": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
SMLALB Ztied1.H, Zop2.B, Zop3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SMLALB--vectors---Signed-multiply-add-long-to-accumulator--bottom--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SMLALB Zresult.H, Zop2.B, Zop3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SMLALB--vectors---Signed-multiply-add-long-to-accumulator--bottom--

### Operation

Source operation ID: `SveOperation_svmlalb_n_s16`

**Operation**



Return a vector in which each element *i* contains:



```text
op1[i] + (int16_t)op2[i * 2] * (int16_t)op3
```



The operation uses modulo arithmetic.  The behavior is therefore defined for all inputs; unlike C, there is no undefined behavior for signed overflow.

## svmlalb[_n_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmlalb%5B_n_s32%5D

### Signature (source notation)

```c
svint32_t svmlalb[_n_s32](svint32_t op1, svint16_t op2, int16_t op3);
```

### Description

Multiply-add long (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Multiply-accumulate and widen

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
SMLALB Ztied1.S, Zop2.H, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SMLALB--vectors---Signed-multiply-add-long-to-accumulator--bottom--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SMLALB Zresult.S, Zop2.H, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SMLALB--vectors---Signed-multiply-add-long-to-accumulator--bottom--

### Operation

Source operation ID: `SveOperation_svmlalb_n_s32`

**Operation**



Return a vector in which each element *i* contains:



```text
op1[i] + (int32_t)op2[i * 2] * (int32_t)op3
```



The operation uses modulo arithmetic.  The behavior is therefore defined for all inputs; unlike C, there is no undefined behavior for signed overflow.

## svmlalb[_n_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmlalb%5B_n_s64%5D

### Signature (source notation)

```c
svint64_t svmlalb[_n_s64](svint64_t op1, svint32_t op2, int32_t op3);
```

### Description

Multiply-add long (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Multiply-accumulate and widen

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
    "register": "Zop2.S"
  },
  "op3": {
    "register": "Zop3.S[*]"
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
SMLALB Ztied1.D, Zop2.S, Zop3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SMLALB--vectors---Signed-multiply-add-long-to-accumulator--bottom--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SMLALB Zresult.D, Zop2.S, Zop3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SMLALB--vectors---Signed-multiply-add-long-to-accumulator--bottom--

### Operation

Source operation ID: `SveOperation_svmlalb_n_s64`

**Operation**



Return a vector in which each element *i* contains:



```text
op1[i] + (int64_t)op2[i * 2] * (int64_t)op3
```



The operation uses modulo arithmetic.  The behavior is therefore defined for all inputs; unlike C, there is no undefined behavior for signed overflow.

## svmlalb[_n_u16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmlalb%5B_n_u16%5D

### Signature (source notation)

```c
svuint16_t svmlalb[_n_u16](svuint16_t op1, svuint8_t op2, uint8_t op3);
```

### Description

Multiply-add long (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Multiply-accumulate and widen

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
    "register": "Zop1.H|Ztied1.H"
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
    "Zresult.H|Ztied1.H": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
UMLALB Ztied1.H, Zop2.B, Zop3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UMLALB--vectors---Unsigned-multiply-add-long-to-accumulator--bottom--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
UMLALB Zresult.H, Zop2.B, Zop3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UMLALB--vectors---Unsigned-multiply-add-long-to-accumulator--bottom--

### Operation

Source operation ID: `SveOperation_svmlalb_n_u16`

**Operation**



Return a vector in which each element *i* contains:



```text
op1[i] + (uint16_t)op2[i * 2] * (uint16_t)op3
```

## svmlalb[_n_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmlalb%5B_n_u32%5D

### Signature (source notation)

```c
svuint32_t svmlalb[_n_u32](svuint32_t op1, svuint16_t op2, uint16_t op3);
```

### Description

Multiply-add long (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Multiply-accumulate and widen

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
UMLALB Ztied1.S, Zop2.H, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UMLALB--vectors---Unsigned-multiply-add-long-to-accumulator--bottom--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
UMLALB Zresult.S, Zop2.H, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UMLALB--vectors---Unsigned-multiply-add-long-to-accumulator--bottom--

### Operation

Source operation ID: `SveOperation_svmlalb_n_u32`

**Operation**



Return a vector in which each element *i* contains:



```text
op1[i] + (uint32_t)op2[i * 2] * (uint32_t)op3
```

## svmlalb[_n_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmlalb%5B_n_u64%5D

### Signature (source notation)

```c
svuint64_t svmlalb[_n_u64](svuint64_t op1, svuint32_t op2, uint32_t op3);
```

### Description

Multiply-add long (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Multiply-accumulate and widen

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
    "register": "Zop2.S"
  },
  "op3": {
    "register": "Zop3.S[*]"
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
UMLALB Ztied1.D, Zop2.S, Zop3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UMLALB--vectors---Unsigned-multiply-add-long-to-accumulator--bottom--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
UMLALB Zresult.D, Zop2.S, Zop3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UMLALB--vectors---Unsigned-multiply-add-long-to-accumulator--bottom--

### Operation

Source operation ID: `SveOperation_svmlalb_n_u64`

**Operation**



Return a vector in which each element *i* contains:



```text
op1[i] + (uint64_t)op2[i * 2] * (uint64_t)op3
```

## svmlalb[_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmlalb%5B_s16%5D

### Signature (source notation)

```c
svint16_t svmlalb[_s16](svint16_t op1, svint8_t op2, svint8_t op3);
```

### Description

Multiply-add long (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Multiply-accumulate and widen

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
    "Zresult.H|Ztied1.H": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
SMLALB Ztied1.H, Zop2.B, Zop3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SMLALB--vectors---Signed-multiply-add-long-to-accumulator--bottom--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SMLALB Zresult.H, Zop2.B, Zop3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SMLALB--vectors---Signed-multiply-add-long-to-accumulator--bottom--

### Operation

Source operation ID: `SveOperation_svmlalb_s16`

**Operation**



Return a vector in which each element *i* contains:



```text
op1[i] + (int16_t)op2[i * 2] * (int16_t)op3[i * 2]
```



The operation uses modulo arithmetic.  The behavior is therefore defined for all inputs; unlike C, there is no undefined behavior for signed overflow.

## svmlalb[_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmlalb%5B_s32%5D

### Signature (source notation)

```c
svint32_t svmlalb[_s32](svint32_t op1, svint16_t op2, svint16_t op3);
```

### Description

Multiply-add long (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Multiply-accumulate and widen

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
SMLALB Ztied1.S, Zop2.H, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SMLALB--vectors---Signed-multiply-add-long-to-accumulator--bottom--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SMLALB Zresult.S, Zop2.H, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SMLALB--vectors---Signed-multiply-add-long-to-accumulator--bottom--

### Operation

Source operation ID: `SveOperation_svmlalb_s32`

**Operation**



Return a vector in which each element *i* contains:



```text
op1[i] + (int32_t)op2[i * 2] * (int32_t)op3[i * 2]
```



The operation uses modulo arithmetic.  The behavior is therefore defined for all inputs; unlike C, there is no undefined behavior for signed overflow.

## svmlalb[_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmlalb%5B_s64%5D

### Signature (source notation)

```c
svint64_t svmlalb[_s64](svint64_t op1, svint32_t op2, svint32_t op3);
```

### Description

Multiply-add long (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Multiply-accumulate and widen

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
    "Zresult.D|Ztied1.D": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
SMLALB Ztied1.D, Zop2.S, Zop3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SMLALB--vectors---Signed-multiply-add-long-to-accumulator--bottom--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SMLALB Zresult.D, Zop2.S, Zop3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SMLALB--vectors---Signed-multiply-add-long-to-accumulator--bottom--

### Operation

Source operation ID: `SveOperation_svmlalb_s64`

**Operation**



Return a vector in which each element *i* contains:



```text
op1[i] + (int64_t)op2[i * 2] * (int64_t)op3[i * 2]
```



The operation uses modulo arithmetic.  The behavior is therefore defined for all inputs; unlike C, there is no undefined behavior for signed overflow.

## svmlalb[_u16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmlalb%5B_u16%5D

### Signature (source notation)

```c
svuint16_t svmlalb[_u16](svuint16_t op1, svuint8_t op2, svuint8_t op3);
```

### Description

Multiply-add long (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Multiply-accumulate and widen

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
    "register": "Zop1.H|Ztied1.H"
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
    "Zresult.H|Ztied1.H": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
UMLALB Ztied1.H, Zop2.B, Zop3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UMLALB--vectors---Unsigned-multiply-add-long-to-accumulator--bottom--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
UMLALB Zresult.H, Zop2.B, Zop3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UMLALB--vectors---Unsigned-multiply-add-long-to-accumulator--bottom--

### Operation

Source operation ID: `SveOperation_svmlalb_u16`

**Operation**



Return a vector in which each element *i* contains:



```text
op1[i] + (uint16_t)op2[i * 2] * (uint16_t)op3[i * 2]
```

## svmlalb[_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmlalb%5B_u32%5D

### Signature (source notation)

```c
svuint32_t svmlalb[_u32](svuint32_t op1, svuint16_t op2, svuint16_t op3);
```

### Description

Multiply-add long (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Multiply-accumulate and widen

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
UMLALB Ztied1.S, Zop2.H, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UMLALB--vectors---Unsigned-multiply-add-long-to-accumulator--bottom--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
UMLALB Zresult.S, Zop2.H, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UMLALB--vectors---Unsigned-multiply-add-long-to-accumulator--bottom--

### Operation

Source operation ID: `SveOperation_svmlalb_u32`

**Operation**



Return a vector in which each element *i* contains:



```text
op1[i] + (uint32_t)op2[i * 2] * (uint32_t)op3[i * 2]
```

## svmlalb[_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmlalb%5B_u64%5D

### Signature (source notation)

```c
svuint64_t svmlalb[_u64](svuint64_t op1, svuint32_t op2, svuint32_t op3);
```

### Description

Multiply-add long (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Multiply-accumulate and widen

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
    "Zresult.D|Ztied1.D": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
UMLALB Ztied1.D, Zop2.S, Zop3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UMLALB--vectors---Unsigned-multiply-add-long-to-accumulator--bottom--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
UMLALB Zresult.D, Zop2.S, Zop3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UMLALB--vectors---Unsigned-multiply-add-long-to-accumulator--bottom--

### Operation

Source operation ID: `SveOperation_svmlalb_u64`

**Operation**



Return a vector in which each element *i* contains:



```text
op1[i] + (uint64_t)op2[i * 2] * (uint64_t)op3[i * 2]
```

## svmlalb_lane[_f32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmlalb_lane%5B_f32%5D

### Signature (source notation)

```c
svfloat32_t svmlalb_lane[_f32](svfloat32_t op1, svfloat16_t op2, svfloat16_t op3, uint64_t imm_index);
```

### Description

Multiply-add long (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Multiply-accumulate and widen

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
    "maximum": 7
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
FMLALB Ztied1.S, Zop2.H, Zop3.H[imm_index]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMLALB--indexed--FP16-to-FP32---Half-precision-multiply-add-long-to-single-precision--bottom--indexed--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FMLALB Zresult.S, Zop2.H, Zop3.H[imm_index]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMLALB--indexed--FP16-to-FP32---Half-precision-multiply-add-long-to-single-precision--bottom--indexed--

### Operation

Source operation ID: `SveOperation_svmlalb_lane_f32`

**Operation**



Return a vector in which each element *i* contains:



```text
op1[i] + (float32_t)op2[i * 2] * (float32_t)op3[base + imm_index]
```



where `op3[base]` is the first element in the same 128-bit quadword as `op3[i * 2]`.



The multiplication and addition are fused, with no intermediate rounding after the multiplication.



**Exceptions**



Signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not. Multiplying an infinity by zero also triggers an IEEE Invalid exception, as does adding +∞ and -∞ together.

## svmlalb_lane[_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmlalb_lane%5B_s32%5D

### Signature (source notation)

```c
svint32_t svmlalb_lane[_s32](svint32_t op1, svint16_t op2, svint16_t op3, uint64_t imm_index);
```

### Description

Multiply-add long (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Multiply-accumulate and widen

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
    "register": "Zop2.H"
  },
  "op3": {
    "register": "Zop3.H"
  },
  "imm_index": {
    "minimum": 0,
    "maximum": 7
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
SMLALB Ztied1.S, Zop2.H, Zop3.H[imm_index]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SMLALB--indexed---Signed-multiply-add-long-to-accumulator--bottom--indexed--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SMLALB Zresult.S, Zop2.H, Zop3.H[imm_index]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SMLALB--indexed---Signed-multiply-add-long-to-accumulator--bottom--indexed--

### Operation

Source operation ID: `SveOperation_svmlalb_lane_s32`

**Operation**



Return a vector in which each element *i* contains:



```text
op1[i] + (int32_t)op2[i * 2] * (int32_t)op3[base + imm_index]
```



where `op3[base]` is the first element in the same 128-bit quadword as `op3[i * 2]`.



The operation uses modulo arithmetic.  The behavior is therefore defined for all inputs; unlike C, there is no undefined behavior for signed overflow.

## svmlalb_lane[_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmlalb_lane%5B_s64%5D

### Signature (source notation)

```c
svint64_t svmlalb_lane[_s64](svint64_t op1, svint32_t op2, svint32_t op3, uint64_t imm_index);
```

### Description

Multiply-add long (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Multiply-accumulate and widen

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
    "register": "Zop2.S"
  },
  "op3": {
    "register": "Zop3.S"
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
    "Zresult.D|Ztied1.D": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
SMLALB Ztied1.D, Zop2.S, Zop3.S[imm_index]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SMLALB--indexed---Signed-multiply-add-long-to-accumulator--bottom--indexed--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SMLALB Zresult.D, Zop2.S, Zop3.S[imm_index]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SMLALB--indexed---Signed-multiply-add-long-to-accumulator--bottom--indexed--

### Operation

Source operation ID: `SveOperation_svmlalb_lane_s64`

**Operation**



Return a vector in which each element *i* contains:



```text
op1[i] + (int64_t)op2[i * 2] * (int64_t)op3[base + imm_index]
```



where `op3[base]` is the first element in the same 128-bit quadword as `op3[i * 2]`.



The operation uses modulo arithmetic.  The behavior is therefore defined for all inputs; unlike C, there is no undefined behavior for signed overflow.

## svmlalb_lane[_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmlalb_lane%5B_u32%5D

### Signature (source notation)

```c
svuint32_t svmlalb_lane[_u32](svuint32_t op1, svuint16_t op2, svuint16_t op3, uint64_t imm_index);
```

### Description

Multiply-add long (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Multiply-accumulate and widen

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
    "register": "Zop2.H"
  },
  "op3": {
    "register": "Zop3.H"
  },
  "imm_index": {
    "minimum": 0,
    "maximum": 7
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
UMLALB Ztied1.S, Zop2.H, Zop3.H[imm_index]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UMLALB--indexed---Unsigned-multiply-add-long-to-accumulator--bottom--indexed--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
UMLALB Zresult.S, Zop2.H, Zop3.H[imm_index]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UMLALB--indexed---Unsigned-multiply-add-long-to-accumulator--bottom--indexed--

### Operation

Source operation ID: `SveOperation_svmlalb_lane_u32`

**Operation**



Return a vector in which each element *i* contains:



```text
op1[i] + (uint32_t)op2[i * 2] * (uint32_t)op3[base + imm_index]
```



where `op3[base]` is the first element in the same 128-bit quadword as `op3[i * 2]`.

## svmlalb_lane[_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmlalb_lane%5B_u64%5D

### Signature (source notation)

```c
svuint64_t svmlalb_lane[_u64](svuint64_t op1, svuint32_t op2, svuint32_t op3, uint64_t imm_index);
```

### Description

Multiply-add long (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Multiply-accumulate and widen

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
    "register": "Zop2.S"
  },
  "op3": {
    "register": "Zop3.S"
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
    "Zresult.D|Ztied1.D": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
UMLALB Ztied1.D, Zop2.S, Zop3.S[imm_index]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UMLALB--indexed---Unsigned-multiply-add-long-to-accumulator--bottom--indexed--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
UMLALB Zresult.D, Zop2.S, Zop3.S[imm_index]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UMLALB--indexed---Unsigned-multiply-add-long-to-accumulator--bottom--indexed--

### Operation

Source operation ID: `SveOperation_svmlalb_lane_u64`

**Operation**



Return a vector in which each element *i* contains:



```text
op1[i] + (uint64_t)op2[i * 2] * (uint64_t)op3[base + imm_index]
```



where `op3[base]` is the first element in the same 128-bit quadword as `op3[i * 2]`.

## svmlalt[_f32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmlalt%5B_f32%5D

### Signature (source notation)

```c
svfloat32_t svmlalt[_f32](svfloat32_t op1, svfloat16_t op2, svfloat16_t op3);
```

### Description

Multiply-add long (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Multiply-accumulate and widen

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
FMLALT Ztied1.S, Zop2.H, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMLALT--vectors--FP16-to-FP32---Half-precision-multiply-add-long-to-single-precision--top--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FMLALT Zresult.S, Zop2.H, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMLALT--vectors--FP16-to-FP32---Half-precision-multiply-add-long-to-single-precision--top--

### Operation

Source operation ID: `SveOperation_svmlalt_f32`

**Operation**



Return a vector in which each element *i* contains:



```text
op1[i] + (float32_t)op2[i * 2 + 1] * (float32_t)op3[i * 2 + 1]
```



The multiplication and addition are fused, with no intermediate rounding after the multiplication.



**Exceptions**



Signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not. Multiplying an infinity by zero also triggers an IEEE Invalid exception, as does adding +∞ and -∞ together.

## svmlalt[_n_f32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmlalt%5B_n_f32%5D

### Signature (source notation)

```c
svfloat32_t svmlalt[_n_f32](svfloat32_t op1, svfloat16_t op2, float16_t op3);
```

### Description

Multiply-add long (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Multiply-accumulate and widen

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
FMLALT Ztied1.S, Zop2.H, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMLALT--vectors--FP16-to-FP32---Half-precision-multiply-add-long-to-single-precision--top--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FMLALT Zresult.S, Zop2.H, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMLALT--vectors--FP16-to-FP32---Half-precision-multiply-add-long-to-single-precision--top--

### Operation

Source operation ID: `SveOperation_svmlalt_n_f32`

**Operation**



Return a vector in which each element *i* contains:



```text
op1[i] + (float32_t)op2[i * 2 + 1] * (float32_t)op3
```



The multiplication and addition are fused, with no intermediate rounding after the multiplication.



**Exceptions**



Signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not. Multiplying an infinity by zero also triggers an IEEE Invalid exception, as does adding +∞ and -∞ together.

## svmlalt[_n_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmlalt%5B_n_s16%5D

### Signature (source notation)

```c
svint16_t svmlalt[_n_s16](svint16_t op1, svint8_t op2, int8_t op3);
```

### Description

Multiply-add long (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Multiply-accumulate and widen

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
    "Zresult.H|Ztied1.H": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
SMLALT Ztied1.H, Zop2.B, Zop3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SMLALT--vectors---Signed-multiply-add-long-to-accumulator--top--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SMLALT Zresult.H, Zop2.B, Zop3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SMLALT--vectors---Signed-multiply-add-long-to-accumulator--top--

### Operation

Source operation ID: `SveOperation_svmlalt_n_s16`

**Operation**



Return a vector in which each element *i* contains:



```text
op1[i] + (int16_t)op2[i * 2 + 1] * (int16_t)op3
```



The operation uses modulo arithmetic.  The behavior is therefore defined for all inputs; unlike C, there is no undefined behavior for signed overflow.

## svmlalt[_n_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmlalt%5B_n_s32%5D

### Signature (source notation)

```c
svint32_t svmlalt[_n_s32](svint32_t op1, svint16_t op2, int16_t op3);
```

### Description

Multiply-add long (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Multiply-accumulate and widen

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
SMLALT Ztied1.S, Zop2.H, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SMLALT--vectors---Signed-multiply-add-long-to-accumulator--top--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SMLALT Zresult.S, Zop2.H, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SMLALT--vectors---Signed-multiply-add-long-to-accumulator--top--

### Operation

Source operation ID: `SveOperation_svmlalt_n_s32`

**Operation**



Return a vector in which each element *i* contains:



```text
op1[i] + (int32_t)op2[i * 2 + 1] * (int32_t)op3
```



The operation uses modulo arithmetic.  The behavior is therefore defined for all inputs; unlike C, there is no undefined behavior for signed overflow.

## svmlalt[_n_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmlalt%5B_n_s64%5D

### Signature (source notation)

```c
svint64_t svmlalt[_n_s64](svint64_t op1, svint32_t op2, int32_t op3);
```

### Description

Multiply-add long (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Multiply-accumulate and widen

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
    "register": "Zop2.S"
  },
  "op3": {
    "register": "Zop3.S[*]"
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
SMLALT Ztied1.D, Zop2.S, Zop3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SMLALT--vectors---Signed-multiply-add-long-to-accumulator--top--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SMLALT Zresult.D, Zop2.S, Zop3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SMLALT--vectors---Signed-multiply-add-long-to-accumulator--top--

### Operation

Source operation ID: `SveOperation_svmlalt_n_s64`

**Operation**



Return a vector in which each element *i* contains:



```text
op1[i] + (int64_t)op2[i * 2 + 1] * (int64_t)op3
```



The operation uses modulo arithmetic.  The behavior is therefore defined for all inputs; unlike C, there is no undefined behavior for signed overflow.

## svmlalt[_n_u16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmlalt%5B_n_u16%5D

### Signature (source notation)

```c
svuint16_t svmlalt[_n_u16](svuint16_t op1, svuint8_t op2, uint8_t op3);
```

### Description

Multiply-add long (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Multiply-accumulate and widen

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
    "register": "Zop1.H|Ztied1.H"
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
    "Zresult.H|Ztied1.H": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
UMLALT Ztied1.H, Zop2.B, Zop3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UMLALT--vectors---Unsigned-multiply-add-long-to-accumulator--top--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
UMLALT Zresult.H, Zop2.B, Zop3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UMLALT--vectors---Unsigned-multiply-add-long-to-accumulator--top--

### Operation

Source operation ID: `SveOperation_svmlalt_n_u16`

**Operation**



Return a vector in which each element *i* contains:



```text
op1[i] + (uint16_t)op2[i * 2 + 1] * (uint16_t)op3
```

## svmlalt[_n_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmlalt%5B_n_u32%5D

### Signature (source notation)

```c
svuint32_t svmlalt[_n_u32](svuint32_t op1, svuint16_t op2, uint16_t op3);
```

### Description

Multiply-add long (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Multiply-accumulate and widen

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
UMLALT Ztied1.S, Zop2.H, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UMLALT--vectors---Unsigned-multiply-add-long-to-accumulator--top--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
UMLALT Zresult.S, Zop2.H, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UMLALT--vectors---Unsigned-multiply-add-long-to-accumulator--top--

### Operation

Source operation ID: `SveOperation_svmlalt_n_u32`

**Operation**



Return a vector in which each element *i* contains:



```text
op1[i] + (uint32_t)op2[i * 2 + 1] * (uint32_t)op3
```

## svmlalt[_n_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmlalt%5B_n_u64%5D

### Signature (source notation)

```c
svuint64_t svmlalt[_n_u64](svuint64_t op1, svuint32_t op2, uint32_t op3);
```

### Description

Multiply-add long (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Multiply-accumulate and widen

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
    "register": "Zop2.S"
  },
  "op3": {
    "register": "Zop3.S[*]"
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
UMLALT Ztied1.D, Zop2.S, Zop3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UMLALT--vectors---Unsigned-multiply-add-long-to-accumulator--top--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
UMLALT Zresult.D, Zop2.S, Zop3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UMLALT--vectors---Unsigned-multiply-add-long-to-accumulator--top--

### Operation

Source operation ID: `SveOperation_svmlalt_n_u64`

**Operation**



Return a vector in which each element *i* contains:



```text
op1[i] + (uint64_t)op2[i * 2 + 1] * (uint64_t)op3
```

## svmlalt[_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmlalt%5B_s16%5D

### Signature (source notation)

```c
svint16_t svmlalt[_s16](svint16_t op1, svint8_t op2, svint8_t op3);
```

### Description

Multiply-add long (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Multiply-accumulate and widen

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
    "Zresult.H|Ztied1.H": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
SMLALT Ztied1.H, Zop2.B, Zop3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SMLALT--vectors---Signed-multiply-add-long-to-accumulator--top--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SMLALT Zresult.H, Zop2.B, Zop3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SMLALT--vectors---Signed-multiply-add-long-to-accumulator--top--

### Operation

Source operation ID: `SveOperation_svmlalt_s16`

**Operation**



Return a vector in which each element *i* contains:



```text
op1[i] + (int16_t)op2[i * 2 + 1] * (int16_t)op3[i * 2 + 1]
```



The operation uses modulo arithmetic.  The behavior is therefore defined for all inputs; unlike C, there is no undefined behavior for signed overflow.

## svmlalt[_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmlalt%5B_s32%5D

### Signature (source notation)

```c
svint32_t svmlalt[_s32](svint32_t op1, svint16_t op2, svint16_t op3);
```

### Description

Multiply-add long (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Multiply-accumulate and widen

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
SMLALT Ztied1.S, Zop2.H, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SMLALT--vectors---Signed-multiply-add-long-to-accumulator--top--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SMLALT Zresult.S, Zop2.H, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SMLALT--vectors---Signed-multiply-add-long-to-accumulator--top--

### Operation

Source operation ID: `SveOperation_svmlalt_s32`

**Operation**



Return a vector in which each element *i* contains:



```text
op1[i] + (int32_t)op2[i * 2 + 1] * (int32_t)op3[i * 2 + 1]
```



The operation uses modulo arithmetic.  The behavior is therefore defined for all inputs; unlike C, there is no undefined behavior for signed overflow.

## svmlalt[_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmlalt%5B_s64%5D

### Signature (source notation)

```c
svint64_t svmlalt[_s64](svint64_t op1, svint32_t op2, svint32_t op3);
```

### Description

Multiply-add long (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Multiply-accumulate and widen

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
    "Zresult.D|Ztied1.D": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
SMLALT Ztied1.D, Zop2.S, Zop3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SMLALT--vectors---Signed-multiply-add-long-to-accumulator--top--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SMLALT Zresult.D, Zop2.S, Zop3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SMLALT--vectors---Signed-multiply-add-long-to-accumulator--top--

### Operation

Source operation ID: `SveOperation_svmlalt_s64`

**Operation**



Return a vector in which each element *i* contains:



```text
op1[i] + (int64_t)op2[i * 2 + 1] * (int64_t)op3[i * 2 + 1]
```



The operation uses modulo arithmetic.  The behavior is therefore defined for all inputs; unlike C, there is no undefined behavior for signed overflow.

## svmlalt[_u16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmlalt%5B_u16%5D

### Signature (source notation)

```c
svuint16_t svmlalt[_u16](svuint16_t op1, svuint8_t op2, svuint8_t op3);
```

### Description

Multiply-add long (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Multiply-accumulate and widen

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
    "register": "Zop1.H|Ztied1.H"
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
    "Zresult.H|Ztied1.H": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
UMLALT Ztied1.H, Zop2.B, Zop3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UMLALT--vectors---Unsigned-multiply-add-long-to-accumulator--top--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
UMLALT Zresult.H, Zop2.B, Zop3.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UMLALT--vectors---Unsigned-multiply-add-long-to-accumulator--top--

### Operation

Source operation ID: `SveOperation_svmlalt_u16`

**Operation**



Return a vector in which each element *i* contains:



```text
op1[i] + (uint16_t)op2[i * 2 + 1] * (uint16_t)op3[i * 2 + 1]
```

## svmlalt[_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmlalt%5B_u32%5D

### Signature (source notation)

```c
svuint32_t svmlalt[_u32](svuint32_t op1, svuint16_t op2, svuint16_t op3);
```

### Description

Multiply-add long (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Multiply-accumulate and widen

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
UMLALT Ztied1.S, Zop2.H, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UMLALT--vectors---Unsigned-multiply-add-long-to-accumulator--top--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
UMLALT Zresult.S, Zop2.H, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UMLALT--vectors---Unsigned-multiply-add-long-to-accumulator--top--

### Operation

Source operation ID: `SveOperation_svmlalt_u32`

**Operation**



Return a vector in which each element *i* contains:



```text
op1[i] + (uint32_t)op2[i * 2 + 1] * (uint32_t)op3[i * 2 + 1]
```

## svmlalt[_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmlalt%5B_u64%5D

### Signature (source notation)

```c
svuint64_t svmlalt[_u64](svuint64_t op1, svuint32_t op2, svuint32_t op3);
```

### Description

Multiply-add long (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Multiply-accumulate and widen

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
    "Zresult.D|Ztied1.D": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
UMLALT Ztied1.D, Zop2.S, Zop3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UMLALT--vectors---Unsigned-multiply-add-long-to-accumulator--top--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
UMLALT Zresult.D, Zop2.S, Zop3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UMLALT--vectors---Unsigned-multiply-add-long-to-accumulator--top--

### Operation

Source operation ID: `SveOperation_svmlalt_u64`

**Operation**



Return a vector in which each element *i* contains:



```text
op1[i] + (uint64_t)op2[i * 2 + 1] * (uint64_t)op3[i * 2 + 1]
```

## svmlalt_lane[_f32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmlalt_lane%5B_f32%5D

### Signature (source notation)

```c
svfloat32_t svmlalt_lane[_f32](svfloat32_t op1, svfloat16_t op2, svfloat16_t op3, uint64_t imm_index);
```

### Description

Multiply-add long (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Multiply-accumulate and widen

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
    "maximum": 7
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
FMLALT Ztied1.S, Zop2.H, Zop3.H[imm_index]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMLALT--indexed--FP16-to-FP32---Half-precision-multiply-add-long-to-single-precision--top--indexed--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FMLALT Zresult.S, Zop2.H, Zop3.H[imm_index]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMLALT--indexed--FP16-to-FP32---Half-precision-multiply-add-long-to-single-precision--top--indexed--

### Operation

Source operation ID: `SveOperation_svmlalt_lane_f32`

**Operation**



Return a vector in which each element *i* contains:



```text
op1[i] + (float32_t)op2[i * 2 + 1] * (float32_t)op3[base + imm_index]
```



where `op3[base]` is the first element in the same 128-bit quadword as `op3[i * 2]`.



The multiplication and addition are fused, with no intermediate rounding after the multiplication.



**Exceptions**



Signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not. Multiplying an infinity by zero also triggers an IEEE Invalid exception, as does adding +∞ and -∞ together.

## svmlalt_lane[_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmlalt_lane%5B_s32%5D

### Signature (source notation)

```c
svint32_t svmlalt_lane[_s32](svint32_t op1, svint16_t op2, svint16_t op3, uint64_t imm_index);
```

### Description

Multiply-add long (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Multiply-accumulate and widen

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
    "register": "Zop2.H"
  },
  "op3": {
    "register": "Zop3.H"
  },
  "imm_index": {
    "minimum": 0,
    "maximum": 7
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
SMLALT Ztied1.S, Zop2.H, Zop3.H[imm_index]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SMLALT--indexed---Signed-multiply-add-long-to-accumulator--top--indexed--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SMLALT Zresult.S, Zop2.H, Zop3.H[imm_index]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SMLALT--indexed---Signed-multiply-add-long-to-accumulator--top--indexed--

### Operation

Source operation ID: `SveOperation_svmlalt_lane_s32`

**Operation**



Return a vector in which each element *i* contains:



```text
op1[i] + (int32_t)op2[i * 2 + 1] * (int32_t)op3[base + imm_index]
```



where `op3[base]` is the first element in the same 128-bit quadword as `op3[i * 2]`.



The operation uses modulo arithmetic.  The behavior is therefore defined for all inputs; unlike C, there is no undefined behavior for signed overflow.

## svmlalt_lane[_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmlalt_lane%5B_s64%5D

### Signature (source notation)

```c
svint64_t svmlalt_lane[_s64](svint64_t op1, svint32_t op2, svint32_t op3, uint64_t imm_index);
```

### Description

Multiply-add long (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Multiply-accumulate and widen

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
    "register": "Zop2.S"
  },
  "op3": {
    "register": "Zop3.S"
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
    "Zresult.D|Ztied1.D": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
SMLALT Ztied1.D, Zop2.S, Zop3.S[imm_index]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SMLALT--indexed---Signed-multiply-add-long-to-accumulator--top--indexed--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
SMLALT Zresult.D, Zop2.S, Zop3.S[imm_index]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/SMLALT--indexed---Signed-multiply-add-long-to-accumulator--top--indexed--

### Operation

Source operation ID: `SveOperation_svmlalt_lane_s64`

**Operation**



Return a vector in which each element *i* contains:



```text
op1[i] + (int64_t)op2[i * 2 + 1] * (int64_t)op3[base + imm_index]
```



where `op3[base]` is the first element in the same 128-bit quadword as `op3[i * 2]`.



The operation uses modulo arithmetic.  The behavior is therefore defined for all inputs; unlike C, there is no undefined behavior for signed overflow.

## svmlalt_lane[_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmlalt_lane%5B_u32%5D

### Signature (source notation)

```c
svuint32_t svmlalt_lane[_u32](svuint32_t op1, svuint16_t op2, svuint16_t op3, uint64_t imm_index);
```

### Description

Multiply-add long (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Multiply-accumulate and widen

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
    "register": "Zop2.H"
  },
  "op3": {
    "register": "Zop3.H"
  },
  "imm_index": {
    "minimum": 0,
    "maximum": 7
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
UMLALT Ztied1.S, Zop2.H, Zop3.H[imm_index]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UMLALT--indexed---Unsigned-multiply-add-long-to-accumulator--top--indexed--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
UMLALT Zresult.S, Zop2.H, Zop3.H[imm_index]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UMLALT--indexed---Unsigned-multiply-add-long-to-accumulator--top--indexed--

### Operation

Source operation ID: `SveOperation_svmlalt_lane_u32`

**Operation**



Return a vector in which each element *i* contains:



```text
op1[i] + (uint32_t)op2[i * 2 + 1] * (uint32_t)op3[base + imm_index]
```



where `op3[base]` is the first element in the same 128-bit quadword as `op3[i * 2]`.

## svmlalt_lane[_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmlalt_lane%5B_u64%5D

### Signature (source notation)

```c
svuint64_t svmlalt_lane[_u64](svuint64_t op1, svuint32_t op2, svuint32_t op3, uint64_t imm_index);
```

### Description

Multiply-add long (top)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Multiply-accumulate and widen

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
    "register": "Zop2.S"
  },
  "op3": {
    "register": "Zop3.S"
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
    "Zresult.D|Ztied1.D": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
UMLALT Ztied1.D, Zop2.S, Zop3.S[imm_index]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UMLALT--indexed---Unsigned-multiply-add-long-to-accumulator--top--indexed--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
UMLALT Zresult.D, Zop2.S, Zop3.S[imm_index]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/UMLALT--indexed---Unsigned-multiply-add-long-to-accumulator--top--indexed--

### Operation

Source operation ID: `SveOperation_svmlalt_lane_u64`

**Operation**



Return a vector in which each element *i* contains:



```text
op1[i] + (uint64_t)op2[i * 2 + 1] * (uint64_t)op3[base + imm_index]
```



where `op3[base]` is the first element in the same 128-bit quadword as `op3[i * 2]`.

## svmlslb[_f32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmlslb%5B_f32%5D

### Signature (source notation)

```c
svfloat32_t svmlslb[_f32](svfloat32_t op1, svfloat16_t op2, svfloat16_t op3);
```

### Description

Multiply-subtract long (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Multiply-accumulate and widen

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
FMLSLB Ztied1.S, Zop2.H, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMLSLB--vectors---Half-precision-multiply-subtract-long-from-single-precision--bottom--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FMLSLB Zresult.S, Zop2.H, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMLSLB--vectors---Half-precision-multiply-subtract-long-from-single-precision--bottom--

### Operation

Source operation ID: `SveOperation_svmlslb_f32`

**Operation**



Return a vector in which each element *i* contains:



```text
op1[i] - (float32_t)op2[i * 2] * (float32_t)op3[i * 2]
```



The multiplication and subtraction are fused, with no intermediate rounding after the multiplication.



**Exceptions**



Signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not. Multiplying an infinity by zero also triggers an IEEE Invalid exception, as does subtracting an infinity from itself.

## svmlslb[_n_f32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmlslb%5B_n_f32%5D

### Signature (source notation)

```c
svfloat32_t svmlslb[_n_f32](svfloat32_t op1, svfloat16_t op2, float16_t op3);
```

### Description

Multiply-subtract long (bottom)

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Multiply-accumulate and widen

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
FMLSLB Ztied1.S, Zop2.H, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMLSLB--vectors---Half-precision-multiply-subtract-long-from-single-precision--bottom--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FMLSLB Zresult.S, Zop2.H, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMLSLB--vectors---Half-precision-multiply-subtract-long-from-single-precision--bottom--

### Operation

Source operation ID: `SveOperation_svmlslb_n_f32`

**Operation**



Return a vector in which each element *i* contains:



```text
op1[i] - (float32_t)op2[i * 2] * (float32_t)op3
```



The multiplication and subtraction are fused, with no intermediate rounding after the multiplication.



**Exceptions**



Signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not. Multiplying an infinity by zero also triggers an IEEE Invalid exception, as does subtracting an infinity from itself.

