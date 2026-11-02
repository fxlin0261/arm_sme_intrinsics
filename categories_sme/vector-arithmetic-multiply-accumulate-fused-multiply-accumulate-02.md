# SME / Vector arithmetic / Multiply-accumulate / Fused multiply-accumulate — Part 2

## svmls[_n_f16]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmls%5B_n_f16%5D_z

### Signature (source notation)

```c
svfloat16_t svmls[_n_f16]_z(svbool_t pg, svfloat16_t op1, svfloat16_t op2, float16_t op3);
```

### Description

Multiply-subtract, minuend first

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Fused multiply-accumulate

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
  "op1": {
    "register": "Zop1.H"
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
    "Zresult.H": "result"
  }
]
```

### Instruction mapping

When result is in a different register from op2 and op3, this intrinsic can use:

```asm
MOVPRFX Zresult.H, Pg/Z, Zop1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
FMLS Zresult.H, Pg/M, Zop2.H, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMLS--vectors---Floating-point-fused-multiply-subtract-vectors--predicated---writing-addend--Zda---Zda----Zn---Zm--

When result is in a different register from op3 and op1, this intrinsic can use:

```asm
MOVPRFX Zresult.H, Pg/Z, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
FMSB Zresult.H, Pg/M, Zop3.H, Zop1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMSB--Floating-point-fused-multiply-subtract-vectors--predicated---writing-multiplicand--Zdn---Za----Zdn---Zm--

When result is in a different register from op2 and op1, this intrinsic can use:

```asm
MOVPRFX Zresult.H, Pg/Z, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
FMSB Zresult.H, Pg/M, Zop2.H, Zop1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMSB--Floating-point-fused-multiply-subtract-vectors--predicated---writing-multiplicand--Zdn---Za----Zdn---Zm--

### Operation

Source operation ID: `SveOperation_svmls_n_f16_z`

**Operation**



Return a vector in which each active element *i* contains the value:



```text
op1[i] - op2[i] * op3
```



Set the inactive elements of the result to zero.



The multiplication and subtraction are fused, with no intermediate rounding after the multiplication.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not. Multiplying an infinity by zero also triggers an IEEE Invalid exception, as does subtracting an infinity from itself.

## svmls[_n_f32]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmls%5B_n_f32%5D_m

### Signature (source notation)

```c
svfloat32_t svmls[_n_f32]_m(svbool_t pg, svfloat32_t op1, svfloat32_t op2, float32_t op3);
```

### Description

Multiply-subtract, minuend first

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Fused multiply-accumulate

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
  "op1": {
    "register": "Zop1.S|Ztied1.S"
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
    "Zresult.S|Ztied1.S": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
FMLS Ztied1.S, Pg/M, Zop2.S, Zop3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMLS--vectors---Floating-point-fused-multiply-subtract-vectors--predicated---writing-addend--Zda---Zda----Zn---Zm--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FMLS Zresult.S, Pg/M, Zop2.S, Zop3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMLS--vectors---Floating-point-fused-multiply-subtract-vectors--predicated---writing-addend--Zda---Zda----Zn---Zm--

### Operation

Source operation ID: `SveOperation_svmls_n_f16_m`

**Operation**



Return a vector in which each active element *i* contains the value:



```text
op1[i] - op2[i] * op3
```



Take the inactive elements of the result from the corresponding elements of `op1`.



The multiplication and subtraction are fused, with no intermediate rounding after the multiplication.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not. Multiplying an infinity by zero also triggers an IEEE Invalid exception, as does subtracting an infinity from itself.

## svmls[_n_f32]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmls%5B_n_f32%5D_x

### Signature (source notation)

```c
svfloat32_t svmls[_n_f32]_x(svbool_t pg, svfloat32_t op1, svfloat32_t op2, float32_t op3);
```

### Description

Multiply-subtract, minuend first

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Fused multiply-accumulate

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
  "op1": {
    "register": "Zop1.S|Ztied1.S"
  },
  "op2": {
    "register": "Zop2.S|Ztied2.S"
  },
  "op3": {
    "register": "Zop3.S[*]|Ztied3.S[*]"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.S|Ztied1.S|Ztied2.S|Ztied3.S": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
FMLS Ztied1.S, Pg/M, Zop2.S, Zop3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMLS--vectors---Floating-point-fused-multiply-subtract-vectors--predicated---writing-addend--Zda---Zda----Zn---Zm--

When result and op2 are in the same register, this intrinsic compiles to:

```asm
FMSB Ztied2.S, Pg/M, Zop3.S, Zop1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMSB--Floating-point-fused-multiply-subtract-vectors--predicated---writing-multiplicand--Zdn---Za----Zdn---Zm--

When result and op3 are in the same register, this intrinsic compiles to:

```asm
FMSB Ztied3.S, Pg/M, Zop2.S, Zop1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMSB--Floating-point-fused-multiply-subtract-vectors--predicated---writing-multiplicand--Zdn---Za----Zdn---Zm--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FMLS Zresult.S, Pg/M, Zop2.S, Zop3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMLS--vectors---Floating-point-fused-multiply-subtract-vectors--predicated---writing-addend--Zda---Zda----Zn---Zm--

### Operation

Source operation ID: `SveOperation_svmls_n_f16_x`

**Operation**



Return a vector in which each active element *i* contains the value:



```text
op1[i] - op2[i] * op3
```



The inactive elements of the result have arbitrary, undefined values.



The multiplication and subtraction are fused, with no intermediate rounding after the multiplication.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not. Multiplying an infinity by zero also triggers an IEEE Invalid exception, as does subtracting an infinity from itself.

## svmls[_n_f32]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmls%5B_n_f32%5D_z

### Signature (source notation)

```c
svfloat32_t svmls[_n_f32]_z(svbool_t pg, svfloat32_t op1, svfloat32_t op2, float32_t op3);
```

### Description

Multiply-subtract, minuend first

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Fused multiply-accumulate

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
  "op1": {
    "register": "Zop1.S"
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
    "Zresult.S": "result"
  }
]
```

### Instruction mapping

When result is in a different register from op2 and op3, this intrinsic can use:

```asm
MOVPRFX Zresult.S, Pg/Z, Zop1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
FMLS Zresult.S, Pg/M, Zop2.S, Zop3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMLS--vectors---Floating-point-fused-multiply-subtract-vectors--predicated---writing-addend--Zda---Zda----Zn---Zm--

When result is in a different register from op3 and op1, this intrinsic can use:

```asm
MOVPRFX Zresult.S, Pg/Z, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
FMSB Zresult.S, Pg/M, Zop3.S, Zop1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMSB--Floating-point-fused-multiply-subtract-vectors--predicated---writing-multiplicand--Zdn---Za----Zdn---Zm--

When result is in a different register from op2 and op1, this intrinsic can use:

```asm
MOVPRFX Zresult.S, Pg/Z, Zop3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
FMSB Zresult.S, Pg/M, Zop2.S, Zop1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMSB--Floating-point-fused-multiply-subtract-vectors--predicated---writing-multiplicand--Zdn---Za----Zdn---Zm--

### Operation

Source operation ID: `SveOperation_svmls_n_f16_z`

**Operation**



Return a vector in which each active element *i* contains the value:



```text
op1[i] - op2[i] * op3
```



Set the inactive elements of the result to zero.



The multiplication and subtraction are fused, with no intermediate rounding after the multiplication.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not. Multiplying an infinity by zero also triggers an IEEE Invalid exception, as does subtracting an infinity from itself.

## svmls[_n_f64]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmls%5B_n_f64%5D_m

### Signature (source notation)

```c
svfloat64_t svmls[_n_f64]_m(svbool_t pg, svfloat64_t op1, svfloat64_t op2, float64_t op3);
```

### Description

Multiply-subtract, minuend first

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Fused multiply-accumulate

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
  "op1": {
    "register": "Zop1.D|Ztied1.D"
  },
  "op2": {
    "register": "Zop2.D"
  },
  "op3": {
    "register": "Zop3.D[*]"
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
FMLS Ztied1.D, Pg/M, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMLS--vectors---Floating-point-fused-multiply-subtract-vectors--predicated---writing-addend--Zda---Zda----Zn---Zm--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FMLS Zresult.D, Pg/M, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMLS--vectors---Floating-point-fused-multiply-subtract-vectors--predicated---writing-addend--Zda---Zda----Zn---Zm--

### Operation

Source operation ID: `SveOperation_svmls_n_f16_m`

**Operation**



Return a vector in which each active element *i* contains the value:



```text
op1[i] - op2[i] * op3
```



Take the inactive elements of the result from the corresponding elements of `op1`.



The multiplication and subtraction are fused, with no intermediate rounding after the multiplication.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not. Multiplying an infinity by zero also triggers an IEEE Invalid exception, as does subtracting an infinity from itself.

## svmls[_n_f64]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmls%5B_n_f64%5D_x

### Signature (source notation)

```c
svfloat64_t svmls[_n_f64]_x(svbool_t pg, svfloat64_t op1, svfloat64_t op2, float64_t op3);
```

### Description

Multiply-subtract, minuend first

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Fused multiply-accumulate

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
  "op1": {
    "register": "Zop1.D|Ztied1.D"
  },
  "op2": {
    "register": "Zop2.D|Ztied2.D"
  },
  "op3": {
    "register": "Zop3.D[*]|Ztied3.D[*]"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.D|Ztied1.D|Ztied2.D|Ztied3.D": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
FMLS Ztied1.D, Pg/M, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMLS--vectors---Floating-point-fused-multiply-subtract-vectors--predicated---writing-addend--Zda---Zda----Zn---Zm--

When result and op2 are in the same register, this intrinsic compiles to:

```asm
FMSB Ztied2.D, Pg/M, Zop3.D, Zop1.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMSB--Floating-point-fused-multiply-subtract-vectors--predicated---writing-multiplicand--Zdn---Za----Zdn---Zm--

When result and op3 are in the same register, this intrinsic compiles to:

```asm
FMSB Ztied3.D, Pg/M, Zop2.D, Zop1.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMSB--Floating-point-fused-multiply-subtract-vectors--predicated---writing-multiplicand--Zdn---Za----Zdn---Zm--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FMLS Zresult.D, Pg/M, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMLS--vectors---Floating-point-fused-multiply-subtract-vectors--predicated---writing-addend--Zda---Zda----Zn---Zm--

### Operation

Source operation ID: `SveOperation_svmls_n_f16_x`

**Operation**



Return a vector in which each active element *i* contains the value:



```text
op1[i] - op2[i] * op3
```



The inactive elements of the result have arbitrary, undefined values.



The multiplication and subtraction are fused, with no intermediate rounding after the multiplication.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not. Multiplying an infinity by zero also triggers an IEEE Invalid exception, as does subtracting an infinity from itself.

## svmls[_n_f64]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmls%5B_n_f64%5D_z

### Signature (source notation)

```c
svfloat64_t svmls[_n_f64]_z(svbool_t pg, svfloat64_t op1, svfloat64_t op2, float64_t op3);
```

### Description

Multiply-subtract, minuend first

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Fused multiply-accumulate

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
  "op1": {
    "register": "Zop1.D"
  },
  "op2": {
    "register": "Zop2.D"
  },
  "op3": {
    "register": "Zop3.D[*]"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.D": "result"
  }
]
```

### Instruction mapping

When result is in a different register from op2 and op3, this intrinsic can use:

```asm
MOVPRFX Zresult.D, Pg/Z, Zop1.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
FMLS Zresult.D, Pg/M, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMLS--vectors---Floating-point-fused-multiply-subtract-vectors--predicated---writing-addend--Zda---Zda----Zn---Zm--

When result is in a different register from op3 and op1, this intrinsic can use:

```asm
MOVPRFX Zresult.D, Pg/Z, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
FMSB Zresult.D, Pg/M, Zop3.D, Zop1.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMSB--Floating-point-fused-multiply-subtract-vectors--predicated---writing-multiplicand--Zdn---Za----Zdn---Zm--

When result is in a different register from op2 and op1, this intrinsic can use:

```asm
MOVPRFX Zresult.D, Pg/Z, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
FMSB Zresult.D, Pg/M, Zop2.D, Zop1.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMSB--Floating-point-fused-multiply-subtract-vectors--predicated---writing-multiplicand--Zdn---Za----Zdn---Zm--

### Operation

Source operation ID: `SveOperation_svmls_n_f16_z`

**Operation**



Return a vector in which each active element *i* contains the value:



```text
op1[i] - op2[i] * op3
```



Set the inactive elements of the result to zero.



The multiplication and subtraction are fused, with no intermediate rounding after the multiplication.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not. Multiplying an infinity by zero also triggers an IEEE Invalid exception, as does subtracting an infinity from itself.

## svmls_lane[_f16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmls_lane%5B_f16%5D

### Signature (source notation)

```c
svfloat16_t svmls_lane[_f16](svfloat16_t op1, svfloat16_t op2, svfloat16_t op3, uint64_t imm_index);
```

### Description

Multiply-subtract, minuend first

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Fused multiply-accumulate

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
    "maximum": 7
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
FMLS Ztied1.H, Zop2.H, Zop3.H[imm_index]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMLS--indexed---Floating-point-fused-multiply-subtract-by-indexed-elements--Zda---Zda----Zn---Zm-indexed---

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FMLS Zresult.H, Zop2.H, Zop3.H[imm_index]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMLS--indexed---Floating-point-fused-multiply-subtract-by-indexed-elements--Zda---Zda----Zn---Zm-indexed---

### Operation

Source operation ID: `SveOperation_svmls_lane_f16`

**Operation**



Return a vector in which each element *i* contains the value:



```text
op1[i] - op2[i] * op3[base + imm_index]
```



where *base* is the index of the first element in the same 128-bit quadword as *i*.



The multiplication and subtraction are fused, with no intermediate rounding after the multiplication.



**Exceptions**



Signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not. Multiplying an infinity by zero also triggers an IEEE Invalid exception, as does subtracting an infinity from itself.

## svmls_lane[_f32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmls_lane%5B_f32%5D

### Signature (source notation)

```c
svfloat32_t svmls_lane[_f32](svfloat32_t op1, svfloat32_t op2, svfloat32_t op3, uint64_t imm_index);
```

### Description

Multiply-subtract, minuend first

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Fused multiply-accumulate

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
    "Zresult.S|Ztied1.S": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
FMLS Ztied1.S, Zop2.S, Zop3.S[imm_index]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMLS--indexed---Floating-point-fused-multiply-subtract-by-indexed-elements--Zda---Zda----Zn---Zm-indexed---

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FMLS Zresult.S, Zop2.S, Zop3.S[imm_index]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMLS--indexed---Floating-point-fused-multiply-subtract-by-indexed-elements--Zda---Zda----Zn---Zm-indexed---

### Operation

Source operation ID: `SveOperation_svmls_lane_f16`

**Operation**



Return a vector in which each element *i* contains the value:



```text
op1[i] - op2[i] * op3[base + imm_index]
```



where *base* is the index of the first element in the same 128-bit quadword as *i*.



The multiplication and subtraction are fused, with no intermediate rounding after the multiplication.



**Exceptions**



Signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not. Multiplying an infinity by zero also triggers an IEEE Invalid exception, as does subtracting an infinity from itself.

## svmls_lane[_f64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmls_lane%5B_f64%5D

### Signature (source notation)

```c
svfloat64_t svmls_lane[_f64](svfloat64_t op1, svfloat64_t op2, svfloat64_t op3, uint64_t imm_index);
```

### Description

Multiply-subtract, minuend first

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Fused multiply-accumulate

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
    "register": "Zop1.D|Ztied1.D"
  },
  "op2": {
    "register": "Zop2.D"
  },
  "op3": {
    "register": "Zop3.D"
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
FMLS Ztied1.D, Zop2.D, Zop3.D[imm_index]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMLS--indexed---Floating-point-fused-multiply-subtract-by-indexed-elements--Zda---Zda----Zn---Zm-indexed---

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FMLS Zresult.D, Zop2.D, Zop3.D[imm_index]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMLS--indexed---Floating-point-fused-multiply-subtract-by-indexed-elements--Zda---Zda----Zn---Zm-indexed---

### Operation

Source operation ID: `SveOperation_svmls_lane_f16`

**Operation**



Return a vector in which each element *i* contains the value:



```text
op1[i] - op2[i] * op3[base + imm_index]
```



where *base* is the index of the first element in the same 128-bit quadword as *i*.



The multiplication and subtraction are fused, with no intermediate rounding after the multiplication.



**Exceptions**



Signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not. Multiplying an infinity by zero also triggers an IEEE Invalid exception, as does subtracting an infinity from itself.

## svmsb[_f16]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmsb%5B_f16%5D_m

### Signature (source notation)

```c
svfloat16_t svmsb[_f16]_m(svbool_t pg, svfloat16_t op1, svfloat16_t op2, svfloat16_t op3);
```

### Description

Multiply-subtract, multiplicand first

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Fused multiply-accumulate

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
FMSB Ztied1.H, Pg/M, Zop2.H, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMSB--Floating-point-fused-multiply-subtract-vectors--predicated---writing-multiplicand--Zdn---Za----Zdn---Zm--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FMSB Zresult.H, Pg/M, Zop2.H, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMSB--Floating-point-fused-multiply-subtract-vectors--predicated---writing-multiplicand--Zdn---Za----Zdn---Zm--

### Operation

Source operation ID: `SveOperation_svmsb_f16_m`

**Operation**



Return a vector in which each active element *i* contains the value:



```text
op3[i] - op1[i] * op2[i]
```



Take the inactive elements of the result from the corresponding elements of `op1`.



The multiplication and subtraction are fused, with no intermediate rounding after the multiplication.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not. Multiplying an infinity by zero also triggers an IEEE Invalid exception, as does subtracting an infinity from itself.

## svmsb[_f16]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmsb%5B_f16%5D_x

### Signature (source notation)

```c
svfloat16_t svmsb[_f16]_x(svbool_t pg, svfloat16_t op1, svfloat16_t op2, svfloat16_t op3);
```

### Description

Multiply-subtract, multiplicand first

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Fused multiply-accumulate

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
  "op1": {
    "register": "Zop1.H|Ztied1.H"
  },
  "op2": {
    "register": "Zop2.H|Ztied2.H"
  },
  "op3": {
    "register": "Zop3.H|Ztied3.H"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.H|Ztied1.H|Ztied2.H|Ztied3.H": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
FMSB Ztied1.H, Pg/M, Zop2.H, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMSB--Floating-point-fused-multiply-subtract-vectors--predicated---writing-multiplicand--Zdn---Za----Zdn---Zm--

When result and op2 are in the same register, this intrinsic compiles to:

```asm
FMSB Ztied2.H, Pg/M, Zop1.H, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMSB--Floating-point-fused-multiply-subtract-vectors--predicated---writing-multiplicand--Zdn---Za----Zdn---Zm--

When result and op3 are in the same register, this intrinsic compiles to:

```asm
FMLS Ztied3.H, Pg/M, Zop1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMLS--vectors---Floating-point-fused-multiply-subtract-vectors--predicated---writing-addend--Zda---Zda----Zn---Zm--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FMSB Zresult.H, Pg/M, Zop2.H, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMSB--Floating-point-fused-multiply-subtract-vectors--predicated---writing-multiplicand--Zdn---Za----Zdn---Zm--

### Operation

Source operation ID: `SveOperation_svmsb_f16_x`

**Operation**



Return a vector in which each active element *i* contains the value:



```text
op3[i] - op1[i] * op2[i]
```



The inactive elements of the result have arbitrary, undefined values.



The multiplication and subtraction are fused, with no intermediate rounding after the multiplication.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not. Multiplying an infinity by zero also triggers an IEEE Invalid exception, as does subtracting an infinity from itself.

## svmsb[_f16]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmsb%5B_f16%5D_z

### Signature (source notation)

```c
svfloat16_t svmsb[_f16]_z(svbool_t pg, svfloat16_t op1, svfloat16_t op2, svfloat16_t op3);
```

### Description

Multiply-subtract, multiplicand first

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Fused multiply-accumulate

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
  "op1": {
    "register": "Zop1.H"
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
    "Zresult.H": "result"
  }
]
```

### Instruction mapping

When result is in a different register from op2 and op3, this intrinsic can use:

```asm
MOVPRFX Zresult.H, Pg/Z, Zop1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
FMSB Zresult.H, Pg/M, Zop2.H, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMSB--Floating-point-fused-multiply-subtract-vectors--predicated---writing-multiplicand--Zdn---Za----Zdn---Zm--

When result is in a different register from op1 and op3, this intrinsic can use:

```asm
MOVPRFX Zresult.H, Pg/Z, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
FMSB Zresult.H, Pg/M, Zop1.H, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMSB--Floating-point-fused-multiply-subtract-vectors--predicated---writing-multiplicand--Zdn---Za----Zdn---Zm--

When result is in a different register from op1 and op2, this intrinsic can use:

```asm
MOVPRFX Zresult.H, Pg/Z, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
FMLS Zresult.H, Pg/M, Zop1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMLS--vectors---Floating-point-fused-multiply-subtract-vectors--predicated---writing-addend--Zda---Zda----Zn---Zm--

### Operation

Source operation ID: `SveOperation_svmsb_f16_z`

**Operation**



Return a vector in which each active element *i* contains the value:



```text
op3[i] - op1[i] * op2[i]
```



Set the inactive elements of the result to zero.



The multiplication and subtraction are fused, with no intermediate rounding after the multiplication.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not. Multiplying an infinity by zero also triggers an IEEE Invalid exception, as does subtracting an infinity from itself.

## svmsb[_f32]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmsb%5B_f32%5D_m

### Signature (source notation)

```c
svfloat32_t svmsb[_f32]_m(svbool_t pg, svfloat32_t op1, svfloat32_t op2, svfloat32_t op3);
```

### Description

Multiply-subtract, multiplicand first

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Fused multiply-accumulate

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
FMSB Ztied1.S, Pg/M, Zop2.S, Zop3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMSB--Floating-point-fused-multiply-subtract-vectors--predicated---writing-multiplicand--Zdn---Za----Zdn---Zm--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FMSB Zresult.S, Pg/M, Zop2.S, Zop3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMSB--Floating-point-fused-multiply-subtract-vectors--predicated---writing-multiplicand--Zdn---Za----Zdn---Zm--

### Operation

Source operation ID: `SveOperation_svmsb_f16_m`

**Operation**



Return a vector in which each active element *i* contains the value:



```text
op3[i] - op1[i] * op2[i]
```



Take the inactive elements of the result from the corresponding elements of `op1`.



The multiplication and subtraction are fused, with no intermediate rounding after the multiplication.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not. Multiplying an infinity by zero also triggers an IEEE Invalid exception, as does subtracting an infinity from itself.

## svmsb[_f32]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmsb%5B_f32%5D_x

### Signature (source notation)

```c
svfloat32_t svmsb[_f32]_x(svbool_t pg, svfloat32_t op1, svfloat32_t op2, svfloat32_t op3);
```

### Description

Multiply-subtract, multiplicand first

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Fused multiply-accumulate

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
  "op1": {
    "register": "Zop1.S|Ztied1.S"
  },
  "op2": {
    "register": "Zop2.S|Ztied2.S"
  },
  "op3": {
    "register": "Zop3.S|Ztied3.S"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.S|Ztied1.S|Ztied2.S|Ztied3.S": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
FMSB Ztied1.S, Pg/M, Zop2.S, Zop3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMSB--Floating-point-fused-multiply-subtract-vectors--predicated---writing-multiplicand--Zdn---Za----Zdn---Zm--

When result and op2 are in the same register, this intrinsic compiles to:

```asm
FMSB Ztied2.S, Pg/M, Zop1.S, Zop3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMSB--Floating-point-fused-multiply-subtract-vectors--predicated---writing-multiplicand--Zdn---Za----Zdn---Zm--

When result and op3 are in the same register, this intrinsic compiles to:

```asm
FMLS Ztied3.S, Pg/M, Zop1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMLS--vectors---Floating-point-fused-multiply-subtract-vectors--predicated---writing-addend--Zda---Zda----Zn---Zm--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FMSB Zresult.S, Pg/M, Zop2.S, Zop3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMSB--Floating-point-fused-multiply-subtract-vectors--predicated---writing-multiplicand--Zdn---Za----Zdn---Zm--

### Operation

Source operation ID: `SveOperation_svmsb_f16_x`

**Operation**



Return a vector in which each active element *i* contains the value:



```text
op3[i] - op1[i] * op2[i]
```



The inactive elements of the result have arbitrary, undefined values.



The multiplication and subtraction are fused, with no intermediate rounding after the multiplication.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not. Multiplying an infinity by zero also triggers an IEEE Invalid exception, as does subtracting an infinity from itself.

## svmsb[_f32]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmsb%5B_f32%5D_z

### Signature (source notation)

```c
svfloat32_t svmsb[_f32]_z(svbool_t pg, svfloat32_t op1, svfloat32_t op2, svfloat32_t op3);
```

### Description

Multiply-subtract, multiplicand first

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Fused multiply-accumulate

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
  "op1": {
    "register": "Zop1.S"
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
    "Zresult.S": "result"
  }
]
```

### Instruction mapping

When result is in a different register from op2 and op3, this intrinsic can use:

```asm
MOVPRFX Zresult.S, Pg/Z, Zop1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
FMSB Zresult.S, Pg/M, Zop2.S, Zop3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMSB--Floating-point-fused-multiply-subtract-vectors--predicated---writing-multiplicand--Zdn---Za----Zdn---Zm--

When result is in a different register from op1 and op3, this intrinsic can use:

```asm
MOVPRFX Zresult.S, Pg/Z, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
FMSB Zresult.S, Pg/M, Zop1.S, Zop3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMSB--Floating-point-fused-multiply-subtract-vectors--predicated---writing-multiplicand--Zdn---Za----Zdn---Zm--

When result is in a different register from op1 and op2, this intrinsic can use:

```asm
MOVPRFX Zresult.S, Pg/Z, Zop3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
FMLS Zresult.S, Pg/M, Zop1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMLS--vectors---Floating-point-fused-multiply-subtract-vectors--predicated---writing-addend--Zda---Zda----Zn---Zm--

### Operation

Source operation ID: `SveOperation_svmsb_f16_z`

**Operation**



Return a vector in which each active element *i* contains the value:



```text
op3[i] - op1[i] * op2[i]
```



Set the inactive elements of the result to zero.



The multiplication and subtraction are fused, with no intermediate rounding after the multiplication.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not. Multiplying an infinity by zero also triggers an IEEE Invalid exception, as does subtracting an infinity from itself.

## svmsb[_f64]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmsb%5B_f64%5D_m

### Signature (source notation)

```c
svfloat64_t svmsb[_f64]_m(svbool_t pg, svfloat64_t op1, svfloat64_t op2, svfloat64_t op3);
```

### Description

Multiply-subtract, multiplicand first

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Fused multiply-accumulate

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
FMSB Ztied1.D, Pg/M, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMSB--Floating-point-fused-multiply-subtract-vectors--predicated---writing-multiplicand--Zdn---Za----Zdn---Zm--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FMSB Zresult.D, Pg/M, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMSB--Floating-point-fused-multiply-subtract-vectors--predicated---writing-multiplicand--Zdn---Za----Zdn---Zm--

### Operation

Source operation ID: `SveOperation_svmsb_f16_m`

**Operation**



Return a vector in which each active element *i* contains the value:



```text
op3[i] - op1[i] * op2[i]
```



Take the inactive elements of the result from the corresponding elements of `op1`.



The multiplication and subtraction are fused, with no intermediate rounding after the multiplication.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not. Multiplying an infinity by zero also triggers an IEEE Invalid exception, as does subtracting an infinity from itself.

## svmsb[_f64]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmsb%5B_f64%5D_x

### Signature (source notation)

```c
svfloat64_t svmsb[_f64]_x(svbool_t pg, svfloat64_t op1, svfloat64_t op2, svfloat64_t op3);
```

### Description

Multiply-subtract, multiplicand first

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Fused multiply-accumulate

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
  "op1": {
    "register": "Zop1.D|Ztied1.D"
  },
  "op2": {
    "register": "Zop2.D|Ztied2.D"
  },
  "op3": {
    "register": "Zop3.D|Ztied3.D"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.D|Ztied1.D|Ztied2.D|Ztied3.D": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
FMSB Ztied1.D, Pg/M, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMSB--Floating-point-fused-multiply-subtract-vectors--predicated---writing-multiplicand--Zdn---Za----Zdn---Zm--

When result and op2 are in the same register, this intrinsic compiles to:

```asm
FMSB Ztied2.D, Pg/M, Zop1.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMSB--Floating-point-fused-multiply-subtract-vectors--predicated---writing-multiplicand--Zdn---Za----Zdn---Zm--

When result and op3 are in the same register, this intrinsic compiles to:

```asm
FMLS Ztied3.D, Pg/M, Zop1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMLS--vectors---Floating-point-fused-multiply-subtract-vectors--predicated---writing-addend--Zda---Zda----Zn---Zm--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FMSB Zresult.D, Pg/M, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMSB--Floating-point-fused-multiply-subtract-vectors--predicated---writing-multiplicand--Zdn---Za----Zdn---Zm--

### Operation

Source operation ID: `SveOperation_svmsb_f16_x`

**Operation**



Return a vector in which each active element *i* contains the value:



```text
op3[i] - op1[i] * op2[i]
```



The inactive elements of the result have arbitrary, undefined values.



The multiplication and subtraction are fused, with no intermediate rounding after the multiplication.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not. Multiplying an infinity by zero also triggers an IEEE Invalid exception, as does subtracting an infinity from itself.

## svmsb[_f64]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmsb%5B_f64%5D_z

### Signature (source notation)

```c
svfloat64_t svmsb[_f64]_z(svbool_t pg, svfloat64_t op1, svfloat64_t op2, svfloat64_t op3);
```

### Description

Multiply-subtract, multiplicand first

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Fused multiply-accumulate

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
  "op1": {
    "register": "Zop1.D"
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
    "Zresult.D": "result"
  }
]
```

### Instruction mapping

When result is in a different register from op2 and op3, this intrinsic can use:

```asm
MOVPRFX Zresult.D, Pg/Z, Zop1.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
FMSB Zresult.D, Pg/M, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMSB--Floating-point-fused-multiply-subtract-vectors--predicated---writing-multiplicand--Zdn---Za----Zdn---Zm--

When result is in a different register from op1 and op3, this intrinsic can use:

```asm
MOVPRFX Zresult.D, Pg/Z, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
FMSB Zresult.D, Pg/M, Zop1.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMSB--Floating-point-fused-multiply-subtract-vectors--predicated---writing-multiplicand--Zdn---Za----Zdn---Zm--

When result is in a different register from op1 and op2, this intrinsic can use:

```asm
MOVPRFX Zresult.D, Pg/Z, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
FMLS Zresult.D, Pg/M, Zop1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMLS--vectors---Floating-point-fused-multiply-subtract-vectors--predicated---writing-addend--Zda---Zda----Zn---Zm--

### Operation

Source operation ID: `SveOperation_svmsb_f16_z`

**Operation**



Return a vector in which each active element *i* contains the value:



```text
op3[i] - op1[i] * op2[i]
```



Set the inactive elements of the result to zero.



The multiplication and subtraction are fused, with no intermediate rounding after the multiplication.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not. Multiplying an infinity by zero also triggers an IEEE Invalid exception, as does subtracting an infinity from itself.

## svmsb[_n_f16]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmsb%5B_n_f16%5D_m

### Signature (source notation)

```c
svfloat16_t svmsb[_n_f16]_m(svbool_t pg, svfloat16_t op1, svfloat16_t op2, float16_t op3);
```

### Description

Multiply-subtract, multiplicand first

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Fused multiply-accumulate

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
  "op1": {
    "register": "Zop1.H|Ztied1.H"
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
    "Zresult.H|Ztied1.H": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
FMSB Ztied1.H, Pg/M, Zop2.H, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMSB--Floating-point-fused-multiply-subtract-vectors--predicated---writing-multiplicand--Zdn---Za----Zdn---Zm--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FMSB Zresult.H, Pg/M, Zop2.H, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMSB--Floating-point-fused-multiply-subtract-vectors--predicated---writing-multiplicand--Zdn---Za----Zdn---Zm--

### Operation

Source operation ID: `SveOperation_svmsb_n_f16_m`

**Operation**



Return a vector in which each active element *i* contains the value:



```text
op3 - op1[i] * op2[i]
```



Take the inactive elements of the result from the corresponding elements of `op1`.



The multiplication and subtraction are fused, with no intermediate rounding after the multiplication.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not. Multiplying an infinity by zero also triggers an IEEE Invalid exception, as does subtracting an infinity from itself.

## svmsb[_n_f16]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmsb%5B_n_f16%5D_x

### Signature (source notation)

```c
svfloat16_t svmsb[_n_f16]_x(svbool_t pg, svfloat16_t op1, svfloat16_t op2, float16_t op3);
```

### Description

Multiply-subtract, multiplicand first

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Fused multiply-accumulate

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
  "op1": {
    "register": "Zop1.H|Ztied1.H"
  },
  "op2": {
    "register": "Zop2.H|Ztied2.H"
  },
  "op3": {
    "register": "Zop3.H[*]|Ztied3.H[*]"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.H|Ztied1.H|Ztied2.H|Ztied3.H": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
FMSB Ztied1.H, Pg/M, Zop2.H, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMSB--Floating-point-fused-multiply-subtract-vectors--predicated---writing-multiplicand--Zdn---Za----Zdn---Zm--

When result and op2 are in the same register, this intrinsic compiles to:

```asm
FMSB Ztied2.H, Pg/M, Zop1.H, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMSB--Floating-point-fused-multiply-subtract-vectors--predicated---writing-multiplicand--Zdn---Za----Zdn---Zm--

When result and op3 are in the same register, this intrinsic compiles to:

```asm
FMLS Ztied3.H, Pg/M, Zop1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMLS--vectors---Floating-point-fused-multiply-subtract-vectors--predicated---writing-addend--Zda---Zda----Zn---Zm--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FMSB Zresult.H, Pg/M, Zop2.H, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMSB--Floating-point-fused-multiply-subtract-vectors--predicated---writing-multiplicand--Zdn---Za----Zdn---Zm--

### Operation

Source operation ID: `SveOperation_svmsb_n_f16_x`

**Operation**



Return a vector in which each active element *i* contains the value:



```text
op3 - op1[i] * op2[i]
```



The inactive elements of the result have arbitrary, undefined values.



The multiplication and subtraction are fused, with no intermediate rounding after the multiplication.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not. Multiplying an infinity by zero also triggers an IEEE Invalid exception, as does subtracting an infinity from itself.

## svmsb[_n_f16]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmsb%5B_n_f16%5D_z

### Signature (source notation)

```c
svfloat16_t svmsb[_n_f16]_z(svbool_t pg, svfloat16_t op1, svfloat16_t op2, float16_t op3);
```

### Description

Multiply-subtract, multiplicand first

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Fused multiply-accumulate

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
  "op1": {
    "register": "Zop1.H"
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
    "Zresult.H": "result"
  }
]
```

### Instruction mapping

When result is in a different register from op2 and op3, this intrinsic can use:

```asm
MOVPRFX Zresult.H, Pg/Z, Zop1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
FMSB Zresult.H, Pg/M, Zop2.H, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMSB--Floating-point-fused-multiply-subtract-vectors--predicated---writing-multiplicand--Zdn---Za----Zdn---Zm--

When result is in a different register from op1 and op3, this intrinsic can use:

```asm
MOVPRFX Zresult.H, Pg/Z, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
FMSB Zresult.H, Pg/M, Zop1.H, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMSB--Floating-point-fused-multiply-subtract-vectors--predicated---writing-multiplicand--Zdn---Za----Zdn---Zm--

When result is in a different register from op1 and op2, this intrinsic can use:

```asm
MOVPRFX Zresult.H, Pg/Z, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
FMLS Zresult.H, Pg/M, Zop1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMLS--vectors---Floating-point-fused-multiply-subtract-vectors--predicated---writing-addend--Zda---Zda----Zn---Zm--

### Operation

Source operation ID: `SveOperation_svmsb_n_f16_z`

**Operation**



Return a vector in which each active element *i* contains the value:



```text
op3 - op1[i] * op2[i]
```



Set the inactive elements of the result to zero.



The multiplication and subtraction are fused, with no intermediate rounding after the multiplication.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not. Multiplying an infinity by zero also triggers an IEEE Invalid exception, as does subtracting an infinity from itself.

## svmsb[_n_f32]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmsb%5B_n_f32%5D_m

### Signature (source notation)

```c
svfloat32_t svmsb[_n_f32]_m(svbool_t pg, svfloat32_t op1, svfloat32_t op2, float32_t op3);
```

### Description

Multiply-subtract, multiplicand first

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Fused multiply-accumulate

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
  "op1": {
    "register": "Zop1.S|Ztied1.S"
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
    "Zresult.S|Ztied1.S": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
FMSB Ztied1.S, Pg/M, Zop2.S, Zop3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMSB--Floating-point-fused-multiply-subtract-vectors--predicated---writing-multiplicand--Zdn---Za----Zdn---Zm--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FMSB Zresult.S, Pg/M, Zop2.S, Zop3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMSB--Floating-point-fused-multiply-subtract-vectors--predicated---writing-multiplicand--Zdn---Za----Zdn---Zm--

### Operation

Source operation ID: `SveOperation_svmsb_n_f16_m`

**Operation**



Return a vector in which each active element *i* contains the value:



```text
op3 - op1[i] * op2[i]
```



Take the inactive elements of the result from the corresponding elements of `op1`.



The multiplication and subtraction are fused, with no intermediate rounding after the multiplication.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not. Multiplying an infinity by zero also triggers an IEEE Invalid exception, as does subtracting an infinity from itself.

## svmsb[_n_f32]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmsb%5B_n_f32%5D_x

### Signature (source notation)

```c
svfloat32_t svmsb[_n_f32]_x(svbool_t pg, svfloat32_t op1, svfloat32_t op2, float32_t op3);
```

### Description

Multiply-subtract, multiplicand first

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Fused multiply-accumulate

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
  "op1": {
    "register": "Zop1.S|Ztied1.S"
  },
  "op2": {
    "register": "Zop2.S|Ztied2.S"
  },
  "op3": {
    "register": "Zop3.S[*]|Ztied3.S[*]"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.S|Ztied1.S|Ztied2.S|Ztied3.S": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
FMSB Ztied1.S, Pg/M, Zop2.S, Zop3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMSB--Floating-point-fused-multiply-subtract-vectors--predicated---writing-multiplicand--Zdn---Za----Zdn---Zm--

When result and op2 are in the same register, this intrinsic compiles to:

```asm
FMSB Ztied2.S, Pg/M, Zop1.S, Zop3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMSB--Floating-point-fused-multiply-subtract-vectors--predicated---writing-multiplicand--Zdn---Za----Zdn---Zm--

When result and op3 are in the same register, this intrinsic compiles to:

```asm
FMLS Ztied3.S, Pg/M, Zop1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMLS--vectors---Floating-point-fused-multiply-subtract-vectors--predicated---writing-addend--Zda---Zda----Zn---Zm--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FMSB Zresult.S, Pg/M, Zop2.S, Zop3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMSB--Floating-point-fused-multiply-subtract-vectors--predicated---writing-multiplicand--Zdn---Za----Zdn---Zm--

### Operation

Source operation ID: `SveOperation_svmsb_n_f16_x`

**Operation**



Return a vector in which each active element *i* contains the value:



```text
op3 - op1[i] * op2[i]
```



The inactive elements of the result have arbitrary, undefined values.



The multiplication and subtraction are fused, with no intermediate rounding after the multiplication.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not. Multiplying an infinity by zero also triggers an IEEE Invalid exception, as does subtracting an infinity from itself.

## svmsb[_n_f32]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmsb%5B_n_f32%5D_z

### Signature (source notation)

```c
svfloat32_t svmsb[_n_f32]_z(svbool_t pg, svfloat32_t op1, svfloat32_t op2, float32_t op3);
```

### Description

Multiply-subtract, multiplicand first

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Fused multiply-accumulate

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
  "op1": {
    "register": "Zop1.S"
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
    "Zresult.S": "result"
  }
]
```

### Instruction mapping

When result is in a different register from op2 and op3, this intrinsic can use:

```asm
MOVPRFX Zresult.S, Pg/Z, Zop1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
FMSB Zresult.S, Pg/M, Zop2.S, Zop3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMSB--Floating-point-fused-multiply-subtract-vectors--predicated---writing-multiplicand--Zdn---Za----Zdn---Zm--

When result is in a different register from op1 and op3, this intrinsic can use:

```asm
MOVPRFX Zresult.S, Pg/Z, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
FMSB Zresult.S, Pg/M, Zop1.S, Zop3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMSB--Floating-point-fused-multiply-subtract-vectors--predicated---writing-multiplicand--Zdn---Za----Zdn---Zm--

When result is in a different register from op1 and op2, this intrinsic can use:

```asm
MOVPRFX Zresult.S, Pg/Z, Zop3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
FMLS Zresult.S, Pg/M, Zop1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMLS--vectors---Floating-point-fused-multiply-subtract-vectors--predicated---writing-addend--Zda---Zda----Zn---Zm--

### Operation

Source operation ID: `SveOperation_svmsb_n_f16_z`

**Operation**



Return a vector in which each active element *i* contains the value:



```text
op3 - op1[i] * op2[i]
```



Set the inactive elements of the result to zero.



The multiplication and subtraction are fused, with no intermediate rounding after the multiplication.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not. Multiplying an infinity by zero also triggers an IEEE Invalid exception, as does subtracting an infinity from itself.

## svmsb[_n_f64]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmsb%5B_n_f64%5D_m

### Signature (source notation)

```c
svfloat64_t svmsb[_n_f64]_m(svbool_t pg, svfloat64_t op1, svfloat64_t op2, float64_t op3);
```

### Description

Multiply-subtract, multiplicand first

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Fused multiply-accumulate

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
  "op1": {
    "register": "Zop1.D|Ztied1.D"
  },
  "op2": {
    "register": "Zop2.D"
  },
  "op3": {
    "register": "Zop3.D[*]"
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
FMSB Ztied1.D, Pg/M, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMSB--Floating-point-fused-multiply-subtract-vectors--predicated---writing-multiplicand--Zdn---Za----Zdn---Zm--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FMSB Zresult.D, Pg/M, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMSB--Floating-point-fused-multiply-subtract-vectors--predicated---writing-multiplicand--Zdn---Za----Zdn---Zm--

### Operation

Source operation ID: `SveOperation_svmsb_n_f16_m`

**Operation**



Return a vector in which each active element *i* contains the value:



```text
op3 - op1[i] * op2[i]
```



Take the inactive elements of the result from the corresponding elements of `op1`.



The multiplication and subtraction are fused, with no intermediate rounding after the multiplication.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not. Multiplying an infinity by zero also triggers an IEEE Invalid exception, as does subtracting an infinity from itself.

## svmsb[_n_f64]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmsb%5B_n_f64%5D_x

### Signature (source notation)

```c
svfloat64_t svmsb[_n_f64]_x(svbool_t pg, svfloat64_t op1, svfloat64_t op2, float64_t op3);
```

### Description

Multiply-subtract, multiplicand first

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Fused multiply-accumulate

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
  "op1": {
    "register": "Zop1.D|Ztied1.D"
  },
  "op2": {
    "register": "Zop2.D|Ztied2.D"
  },
  "op3": {
    "register": "Zop3.D[*]|Ztied3.D[*]"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.D|Ztied1.D|Ztied2.D|Ztied3.D": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
FMSB Ztied1.D, Pg/M, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMSB--Floating-point-fused-multiply-subtract-vectors--predicated---writing-multiplicand--Zdn---Za----Zdn---Zm--

When result and op2 are in the same register, this intrinsic compiles to:

```asm
FMSB Ztied2.D, Pg/M, Zop1.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMSB--Floating-point-fused-multiply-subtract-vectors--predicated---writing-multiplicand--Zdn---Za----Zdn---Zm--

When result and op3 are in the same register, this intrinsic compiles to:

```asm
FMLS Ztied3.D, Pg/M, Zop1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMLS--vectors---Floating-point-fused-multiply-subtract-vectors--predicated---writing-addend--Zda---Zda----Zn---Zm--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FMSB Zresult.D, Pg/M, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMSB--Floating-point-fused-multiply-subtract-vectors--predicated---writing-multiplicand--Zdn---Za----Zdn---Zm--

### Operation

Source operation ID: `SveOperation_svmsb_n_f16_x`

**Operation**



Return a vector in which each active element *i* contains the value:



```text
op3 - op1[i] * op2[i]
```



The inactive elements of the result have arbitrary, undefined values.



The multiplication and subtraction are fused, with no intermediate rounding after the multiplication.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not. Multiplying an infinity by zero also triggers an IEEE Invalid exception, as does subtracting an infinity from itself.

## svmsb[_n_f64]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svmsb%5B_n_f64%5D_z

### Signature (source notation)

```c
svfloat64_t svmsb[_n_f64]_z(svbool_t pg, svfloat64_t op1, svfloat64_t op2, float64_t op3);
```

### Description

Multiply-subtract, multiplicand first

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Fused multiply-accumulate

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
  "op1": {
    "register": "Zop1.D"
  },
  "op2": {
    "register": "Zop2.D"
  },
  "op3": {
    "register": "Zop3.D[*]"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.D": "result"
  }
]
```

### Instruction mapping

When result is in a different register from op2 and op3, this intrinsic can use:

```asm
MOVPRFX Zresult.D, Pg/Z, Zop1.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
FMSB Zresult.D, Pg/M, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMSB--Floating-point-fused-multiply-subtract-vectors--predicated---writing-multiplicand--Zdn---Za----Zdn---Zm--

When result is in a different register from op1 and op3, this intrinsic can use:

```asm
MOVPRFX Zresult.D, Pg/Z, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
FMSB Zresult.D, Pg/M, Zop1.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMSB--Floating-point-fused-multiply-subtract-vectors--predicated---writing-multiplicand--Zdn---Za----Zdn---Zm--

When result is in a different register from op1 and op2, this intrinsic can use:

```asm
MOVPRFX Zresult.D, Pg/Z, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
FMLS Zresult.D, Pg/M, Zop1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FMLS--vectors---Floating-point-fused-multiply-subtract-vectors--predicated---writing-addend--Zda---Zda----Zn---Zm--

### Operation

Source operation ID: `SveOperation_svmsb_n_f16_z`

**Operation**



Return a vector in which each active element *i* contains the value:



```text
op3 - op1[i] * op2[i]
```



Set the inactive elements of the result to zero.



The multiplication and subtraction are fused, with no intermediate rounding after the multiplication.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not. Multiplying an infinity by zero also triggers an IEEE Invalid exception, as does subtracting an infinity from itself.

## svnmad[_f16]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svnmad%5B_f16%5D_m

### Signature (source notation)

```c
svfloat16_t svnmad[_f16]_m(svbool_t pg, svfloat16_t op1, svfloat16_t op2, svfloat16_t op3);
```

### Description

Negated multiply-add, multiplicand first

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Fused multiply-accumulate

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
FNMAD Ztied1.H, Pg/M, Zop2.H, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FNMAD--Floating-point-negated-fused-multiply-add-vectors--predicated---writing-multiplicand--Zdn----Za----Zdn---Zm--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FNMAD Zresult.H, Pg/M, Zop2.H, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FNMAD--Floating-point-negated-fused-multiply-add-vectors--predicated---writing-multiplicand--Zdn----Za----Zdn---Zm--

### Operation

Source operation ID: `SveOperation_svnmad_f16_m`

**Operation**



Return a vector in which each active element *i* contains the value:



```text
-(op3[i] + op1[i] * op2[i])
```



Take the inactive elements of the result from the corresponding elements of `op1`.



The multiplication and addition are fused, with no intermediate rounding after the multiplication.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not. Multiplying an infinity by zero also triggers an IEEE Invalid exception, as does adding +∞ and -∞ together.

## svnmad[_f16]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svnmad%5B_f16%5D_x

### Signature (source notation)

```c
svfloat16_t svnmad[_f16]_x(svbool_t pg, svfloat16_t op1, svfloat16_t op2, svfloat16_t op3);
```

### Description

Negated multiply-add, multiplicand first

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Fused multiply-accumulate

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
  "op1": {
    "register": "Zop1.H|Ztied1.H"
  },
  "op2": {
    "register": "Zop2.H|Ztied2.H"
  },
  "op3": {
    "register": "Zop3.H|Ztied3.H"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.H|Ztied1.H|Ztied2.H|Ztied3.H": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
FNMAD Ztied1.H, Pg/M, Zop2.H, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FNMAD--Floating-point-negated-fused-multiply-add-vectors--predicated---writing-multiplicand--Zdn----Za----Zdn---Zm--

When result and op2 are in the same register, this intrinsic compiles to:

```asm
FNMAD Ztied2.H, Pg/M, Zop1.H, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FNMAD--Floating-point-negated-fused-multiply-add-vectors--predicated---writing-multiplicand--Zdn----Za----Zdn---Zm--

When result and op3 are in the same register, this intrinsic compiles to:

```asm
FNMLA Ztied3.H, Pg/M, Zop1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FNMLA--Floating-point-negated-fused-multiply-add-vectors--predicated---writing-addend--Zda----Zda----Zn---Zm--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FNMAD Zresult.H, Pg/M, Zop2.H, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FNMAD--Floating-point-negated-fused-multiply-add-vectors--predicated---writing-multiplicand--Zdn----Za----Zdn---Zm--

### Operation

Source operation ID: `SveOperation_svnmad_f16_x`

**Operation**



Return a vector in which each active element *i* contains the value:



```text
-(op3[i] + op1[i] * op2[i])
```



The inactive elements of the result have arbitrary, undefined values.



The multiplication and addition are fused, with no intermediate rounding after the multiplication.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not. Multiplying an infinity by zero also triggers an IEEE Invalid exception, as does adding +∞ and -∞ together.

## svnmad[_f16]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svnmad%5B_f16%5D_z

### Signature (source notation)

```c
svfloat16_t svnmad[_f16]_z(svbool_t pg, svfloat16_t op1, svfloat16_t op2, svfloat16_t op3);
```

### Description

Negated multiply-add, multiplicand first

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Fused multiply-accumulate

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
  "op1": {
    "register": "Zop1.H"
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
    "Zresult.H": "result"
  }
]
```

### Instruction mapping

When result is in a different register from op2 and op3, this intrinsic can use:

```asm
MOVPRFX Zresult.H, Pg/Z, Zop1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
FNMAD Zresult.H, Pg/M, Zop2.H, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FNMAD--Floating-point-negated-fused-multiply-add-vectors--predicated---writing-multiplicand--Zdn----Za----Zdn---Zm--

When result is in a different register from op1 and op3, this intrinsic can use:

```asm
MOVPRFX Zresult.H, Pg/Z, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
FNMAD Zresult.H, Pg/M, Zop1.H, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FNMAD--Floating-point-negated-fused-multiply-add-vectors--predicated---writing-multiplicand--Zdn----Za----Zdn---Zm--

When result is in a different register from op1 and op2, this intrinsic can use:

```asm
MOVPRFX Zresult.H, Pg/Z, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
FNMLA Zresult.H, Pg/M, Zop1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FNMLA--Floating-point-negated-fused-multiply-add-vectors--predicated---writing-addend--Zda----Zda----Zn---Zm--

### Operation

Source operation ID: `SveOperation_svnmad_f16_z`

**Operation**



Return a vector in which each active element *i* contains the value:



```text
-(op3[i] + op1[i] * op2[i])
```



Set the inactive elements of the result to zero.



The multiplication and addition are fused, with no intermediate rounding after the multiplication.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not. Multiplying an infinity by zero also triggers an IEEE Invalid exception, as does adding +∞ and -∞ together.

## svnmad[_f32]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svnmad%5B_f32%5D_m

### Signature (source notation)

```c
svfloat32_t svnmad[_f32]_m(svbool_t pg, svfloat32_t op1, svfloat32_t op2, svfloat32_t op3);
```

### Description

Negated multiply-add, multiplicand first

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Fused multiply-accumulate

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
FNMAD Ztied1.S, Pg/M, Zop2.S, Zop3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FNMAD--Floating-point-negated-fused-multiply-add-vectors--predicated---writing-multiplicand--Zdn----Za----Zdn---Zm--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FNMAD Zresult.S, Pg/M, Zop2.S, Zop3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FNMAD--Floating-point-negated-fused-multiply-add-vectors--predicated---writing-multiplicand--Zdn----Za----Zdn---Zm--

### Operation

Source operation ID: `SveOperation_svnmad_f16_m`

**Operation**



Return a vector in which each active element *i* contains the value:



```text
-(op3[i] + op1[i] * op2[i])
```



Take the inactive elements of the result from the corresponding elements of `op1`.



The multiplication and addition are fused, with no intermediate rounding after the multiplication.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not. Multiplying an infinity by zero also triggers an IEEE Invalid exception, as does adding +∞ and -∞ together.

## svnmad[_f32]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svnmad%5B_f32%5D_x

### Signature (source notation)

```c
svfloat32_t svnmad[_f32]_x(svbool_t pg, svfloat32_t op1, svfloat32_t op2, svfloat32_t op3);
```

### Description

Negated multiply-add, multiplicand first

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Fused multiply-accumulate

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
  "op1": {
    "register": "Zop1.S|Ztied1.S"
  },
  "op2": {
    "register": "Zop2.S|Ztied2.S"
  },
  "op3": {
    "register": "Zop3.S|Ztied3.S"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.S|Ztied1.S|Ztied2.S|Ztied3.S": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
FNMAD Ztied1.S, Pg/M, Zop2.S, Zop3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FNMAD--Floating-point-negated-fused-multiply-add-vectors--predicated---writing-multiplicand--Zdn----Za----Zdn---Zm--

When result and op2 are in the same register, this intrinsic compiles to:

```asm
FNMAD Ztied2.S, Pg/M, Zop1.S, Zop3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FNMAD--Floating-point-negated-fused-multiply-add-vectors--predicated---writing-multiplicand--Zdn----Za----Zdn---Zm--

When result and op3 are in the same register, this intrinsic compiles to:

```asm
FNMLA Ztied3.S, Pg/M, Zop1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FNMLA--Floating-point-negated-fused-multiply-add-vectors--predicated---writing-addend--Zda----Zda----Zn---Zm--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FNMAD Zresult.S, Pg/M, Zop2.S, Zop3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FNMAD--Floating-point-negated-fused-multiply-add-vectors--predicated---writing-multiplicand--Zdn----Za----Zdn---Zm--

### Operation

Source operation ID: `SveOperation_svnmad_f16_x`

**Operation**



Return a vector in which each active element *i* contains the value:



```text
-(op3[i] + op1[i] * op2[i])
```



The inactive elements of the result have arbitrary, undefined values.



The multiplication and addition are fused, with no intermediate rounding after the multiplication.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not. Multiplying an infinity by zero also triggers an IEEE Invalid exception, as does adding +∞ and -∞ together.

## svnmad[_f32]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svnmad%5B_f32%5D_z

### Signature (source notation)

```c
svfloat32_t svnmad[_f32]_z(svbool_t pg, svfloat32_t op1, svfloat32_t op2, svfloat32_t op3);
```

### Description

Negated multiply-add, multiplicand first

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Fused multiply-accumulate

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
  "op1": {
    "register": "Zop1.S"
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
    "Zresult.S": "result"
  }
]
```

### Instruction mapping

When result is in a different register from op2 and op3, this intrinsic can use:

```asm
MOVPRFX Zresult.S, Pg/Z, Zop1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
FNMAD Zresult.S, Pg/M, Zop2.S, Zop3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FNMAD--Floating-point-negated-fused-multiply-add-vectors--predicated---writing-multiplicand--Zdn----Za----Zdn---Zm--

When result is in a different register from op1 and op3, this intrinsic can use:

```asm
MOVPRFX Zresult.S, Pg/Z, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
FNMAD Zresult.S, Pg/M, Zop1.S, Zop3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FNMAD--Floating-point-negated-fused-multiply-add-vectors--predicated---writing-multiplicand--Zdn----Za----Zdn---Zm--

When result is in a different register from op1 and op2, this intrinsic can use:

```asm
MOVPRFX Zresult.S, Pg/Z, Zop3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
FNMLA Zresult.S, Pg/M, Zop1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FNMLA--Floating-point-negated-fused-multiply-add-vectors--predicated---writing-addend--Zda----Zda----Zn---Zm--

### Operation

Source operation ID: `SveOperation_svnmad_f16_z`

**Operation**



Return a vector in which each active element *i* contains the value:



```text
-(op3[i] + op1[i] * op2[i])
```



Set the inactive elements of the result to zero.



The multiplication and addition are fused, with no intermediate rounding after the multiplication.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not. Multiplying an infinity by zero also triggers an IEEE Invalid exception, as does adding +∞ and -∞ together.

## svnmad[_f64]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svnmad%5B_f64%5D_m

### Signature (source notation)

```c
svfloat64_t svnmad[_f64]_m(svbool_t pg, svfloat64_t op1, svfloat64_t op2, svfloat64_t op3);
```

### Description

Negated multiply-add, multiplicand first

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Fused multiply-accumulate

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
FNMAD Ztied1.D, Pg/M, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FNMAD--Floating-point-negated-fused-multiply-add-vectors--predicated---writing-multiplicand--Zdn----Za----Zdn---Zm--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FNMAD Zresult.D, Pg/M, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FNMAD--Floating-point-negated-fused-multiply-add-vectors--predicated---writing-multiplicand--Zdn----Za----Zdn---Zm--

### Operation

Source operation ID: `SveOperation_svnmad_f16_m`

**Operation**



Return a vector in which each active element *i* contains the value:



```text
-(op3[i] + op1[i] * op2[i])
```



Take the inactive elements of the result from the corresponding elements of `op1`.



The multiplication and addition are fused, with no intermediate rounding after the multiplication.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not. Multiplying an infinity by zero also triggers an IEEE Invalid exception, as does adding +∞ and -∞ together.

## svnmad[_f64]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svnmad%5B_f64%5D_x

### Signature (source notation)

```c
svfloat64_t svnmad[_f64]_x(svbool_t pg, svfloat64_t op1, svfloat64_t op2, svfloat64_t op3);
```

### Description

Negated multiply-add, multiplicand first

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Fused multiply-accumulate

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
  "op1": {
    "register": "Zop1.D|Ztied1.D"
  },
  "op2": {
    "register": "Zop2.D|Ztied2.D"
  },
  "op3": {
    "register": "Zop3.D|Ztied3.D"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.D|Ztied1.D|Ztied2.D|Ztied3.D": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
FNMAD Ztied1.D, Pg/M, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FNMAD--Floating-point-negated-fused-multiply-add-vectors--predicated---writing-multiplicand--Zdn----Za----Zdn---Zm--

When result and op2 are in the same register, this intrinsic compiles to:

```asm
FNMAD Ztied2.D, Pg/M, Zop1.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FNMAD--Floating-point-negated-fused-multiply-add-vectors--predicated---writing-multiplicand--Zdn----Za----Zdn---Zm--

When result and op3 are in the same register, this intrinsic compiles to:

```asm
FNMLA Ztied3.D, Pg/M, Zop1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FNMLA--Floating-point-negated-fused-multiply-add-vectors--predicated---writing-addend--Zda----Zda----Zn---Zm--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FNMAD Zresult.D, Pg/M, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FNMAD--Floating-point-negated-fused-multiply-add-vectors--predicated---writing-multiplicand--Zdn----Za----Zdn---Zm--

### Operation

Source operation ID: `SveOperation_svnmad_f16_x`

**Operation**



Return a vector in which each active element *i* contains the value:



```text
-(op3[i] + op1[i] * op2[i])
```



The inactive elements of the result have arbitrary, undefined values.



The multiplication and addition are fused, with no intermediate rounding after the multiplication.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not. Multiplying an infinity by zero also triggers an IEEE Invalid exception, as does adding +∞ and -∞ together.

## svnmad[_f64]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svnmad%5B_f64%5D_z

### Signature (source notation)

```c
svfloat64_t svnmad[_f64]_z(svbool_t pg, svfloat64_t op1, svfloat64_t op2, svfloat64_t op3);
```

### Description

Negated multiply-add, multiplicand first

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Fused multiply-accumulate

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
  "op1": {
    "register": "Zop1.D"
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
    "Zresult.D": "result"
  }
]
```

### Instruction mapping

When result is in a different register from op2 and op3, this intrinsic can use:

```asm
MOVPRFX Zresult.D, Pg/Z, Zop1.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
FNMAD Zresult.D, Pg/M, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FNMAD--Floating-point-negated-fused-multiply-add-vectors--predicated---writing-multiplicand--Zdn----Za----Zdn---Zm--

When result is in a different register from op1 and op3, this intrinsic can use:

```asm
MOVPRFX Zresult.D, Pg/Z, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
FNMAD Zresult.D, Pg/M, Zop1.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FNMAD--Floating-point-negated-fused-multiply-add-vectors--predicated---writing-multiplicand--Zdn----Za----Zdn---Zm--

When result is in a different register from op1 and op2, this intrinsic can use:

```asm
MOVPRFX Zresult.D, Pg/Z, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
FNMLA Zresult.D, Pg/M, Zop1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FNMLA--Floating-point-negated-fused-multiply-add-vectors--predicated---writing-addend--Zda----Zda----Zn---Zm--

### Operation

Source operation ID: `SveOperation_svnmad_f16_z`

**Operation**



Return a vector in which each active element *i* contains the value:



```text
-(op3[i] + op1[i] * op2[i])
```



Set the inactive elements of the result to zero.



The multiplication and addition are fused, with no intermediate rounding after the multiplication.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not. Multiplying an infinity by zero also triggers an IEEE Invalid exception, as does adding +∞ and -∞ together.

## svnmad[_n_f16]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svnmad%5B_n_f16%5D_m

### Signature (source notation)

```c
svfloat16_t svnmad[_n_f16]_m(svbool_t pg, svfloat16_t op1, svfloat16_t op2, float16_t op3);
```

### Description

Negated multiply-add, multiplicand first

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Fused multiply-accumulate

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
  "op1": {
    "register": "Zop1.H|Ztied1.H"
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
    "Zresult.H|Ztied1.H": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
FNMAD Ztied1.H, Pg/M, Zop2.H, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FNMAD--Floating-point-negated-fused-multiply-add-vectors--predicated---writing-multiplicand--Zdn----Za----Zdn---Zm--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FNMAD Zresult.H, Pg/M, Zop2.H, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FNMAD--Floating-point-negated-fused-multiply-add-vectors--predicated---writing-multiplicand--Zdn----Za----Zdn---Zm--

### Operation

Source operation ID: `SveOperation_svnmad_n_f16_m`

**Operation**



Return a vector in which each active element *i* contains the value:



```text
-(op3 + op1[i] * op2[i])
```



Take the inactive elements of the result from the corresponding elements of `op1`.



The multiplication and addition are fused, with no intermediate rounding after the multiplication.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not. Multiplying an infinity by zero also triggers an IEEE Invalid exception, as does adding +∞ and -∞ together.

## svnmad[_n_f16]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svnmad%5B_n_f16%5D_x

### Signature (source notation)

```c
svfloat16_t svnmad[_n_f16]_x(svbool_t pg, svfloat16_t op1, svfloat16_t op2, float16_t op3);
```

### Description

Negated multiply-add, multiplicand first

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Fused multiply-accumulate

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
  "op1": {
    "register": "Zop1.H|Ztied1.H"
  },
  "op2": {
    "register": "Zop2.H|Ztied2.H"
  },
  "op3": {
    "register": "Zop3.H[*]|Ztied3.H[*]"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.H|Ztied1.H|Ztied2.H|Ztied3.H": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
FNMAD Ztied1.H, Pg/M, Zop2.H, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FNMAD--Floating-point-negated-fused-multiply-add-vectors--predicated---writing-multiplicand--Zdn----Za----Zdn---Zm--

When result and op2 are in the same register, this intrinsic compiles to:

```asm
FNMAD Ztied2.H, Pg/M, Zop1.H, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FNMAD--Floating-point-negated-fused-multiply-add-vectors--predicated---writing-multiplicand--Zdn----Za----Zdn---Zm--

When result and op3 are in the same register, this intrinsic compiles to:

```asm
FNMLA Ztied3.H, Pg/M, Zop1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FNMLA--Floating-point-negated-fused-multiply-add-vectors--predicated---writing-addend--Zda----Zda----Zn---Zm--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FNMAD Zresult.H, Pg/M, Zop2.H, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FNMAD--Floating-point-negated-fused-multiply-add-vectors--predicated---writing-multiplicand--Zdn----Za----Zdn---Zm--

### Operation

Source operation ID: `SveOperation_svnmad_n_f16_x`

**Operation**



Return a vector in which each active element *i* contains the value:



```text
-(op3 + op1[i] * op2[i])
```



The inactive elements of the result have arbitrary, undefined values.



The multiplication and addition are fused, with no intermediate rounding after the multiplication.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not. Multiplying an infinity by zero also triggers an IEEE Invalid exception, as does adding +∞ and -∞ together.

## svnmad[_n_f16]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svnmad%5B_n_f16%5D_z

### Signature (source notation)

```c
svfloat16_t svnmad[_n_f16]_z(svbool_t pg, svfloat16_t op1, svfloat16_t op2, float16_t op3);
```

### Description

Negated multiply-add, multiplicand first

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Fused multiply-accumulate

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
  "op1": {
    "register": "Zop1.H"
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
    "Zresult.H": "result"
  }
]
```

### Instruction mapping

When result is in a different register from op2 and op3, this intrinsic can use:

```asm
MOVPRFX Zresult.H, Pg/Z, Zop1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
FNMAD Zresult.H, Pg/M, Zop2.H, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FNMAD--Floating-point-negated-fused-multiply-add-vectors--predicated---writing-multiplicand--Zdn----Za----Zdn---Zm--

When result is in a different register from op1 and op3, this intrinsic can use:

```asm
MOVPRFX Zresult.H, Pg/Z, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
FNMAD Zresult.H, Pg/M, Zop1.H, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FNMAD--Floating-point-negated-fused-multiply-add-vectors--predicated---writing-multiplicand--Zdn----Za----Zdn---Zm--

When result is in a different register from op1 and op2, this intrinsic can use:

```asm
MOVPRFX Zresult.H, Pg/Z, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
FNMLA Zresult.H, Pg/M, Zop1.H, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FNMLA--Floating-point-negated-fused-multiply-add-vectors--predicated---writing-addend--Zda----Zda----Zn---Zm--

### Operation

Source operation ID: `SveOperation_svnmad_n_f16_z`

**Operation**



Return a vector in which each active element *i* contains the value:



```text
-(op3 + op1[i] * op2[i])
```



Set the inactive elements of the result to zero.



The multiplication and addition are fused, with no intermediate rounding after the multiplication.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not. Multiplying an infinity by zero also triggers an IEEE Invalid exception, as does adding +∞ and -∞ together.

## svnmad[_n_f32]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svnmad%5B_n_f32%5D_m

### Signature (source notation)

```c
svfloat32_t svnmad[_n_f32]_m(svbool_t pg, svfloat32_t op1, svfloat32_t op2, float32_t op3);
```

### Description

Negated multiply-add, multiplicand first

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Fused multiply-accumulate

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
  "op1": {
    "register": "Zop1.S|Ztied1.S"
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
    "Zresult.S|Ztied1.S": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
FNMAD Ztied1.S, Pg/M, Zop2.S, Zop3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FNMAD--Floating-point-negated-fused-multiply-add-vectors--predicated---writing-multiplicand--Zdn----Za----Zdn---Zm--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FNMAD Zresult.S, Pg/M, Zop2.S, Zop3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FNMAD--Floating-point-negated-fused-multiply-add-vectors--predicated---writing-multiplicand--Zdn----Za----Zdn---Zm--

### Operation

Source operation ID: `SveOperation_svnmad_n_f16_m`

**Operation**



Return a vector in which each active element *i* contains the value:



```text
-(op3 + op1[i] * op2[i])
```



Take the inactive elements of the result from the corresponding elements of `op1`.



The multiplication and addition are fused, with no intermediate rounding after the multiplication.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not. Multiplying an infinity by zero also triggers an IEEE Invalid exception, as does adding +∞ and -∞ together.

## svnmad[_n_f32]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svnmad%5B_n_f32%5D_x

### Signature (source notation)

```c
svfloat32_t svnmad[_n_f32]_x(svbool_t pg, svfloat32_t op1, svfloat32_t op2, float32_t op3);
```

### Description

Negated multiply-add, multiplicand first

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Fused multiply-accumulate

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
  "op1": {
    "register": "Zop1.S|Ztied1.S"
  },
  "op2": {
    "register": "Zop2.S|Ztied2.S"
  },
  "op3": {
    "register": "Zop3.S[*]|Ztied3.S[*]"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.S|Ztied1.S|Ztied2.S|Ztied3.S": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
FNMAD Ztied1.S, Pg/M, Zop2.S, Zop3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FNMAD--Floating-point-negated-fused-multiply-add-vectors--predicated---writing-multiplicand--Zdn----Za----Zdn---Zm--

When result and op2 are in the same register, this intrinsic compiles to:

```asm
FNMAD Ztied2.S, Pg/M, Zop1.S, Zop3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FNMAD--Floating-point-negated-fused-multiply-add-vectors--predicated---writing-multiplicand--Zdn----Za----Zdn---Zm--

When result and op3 are in the same register, this intrinsic compiles to:

```asm
FNMLA Ztied3.S, Pg/M, Zop1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FNMLA--Floating-point-negated-fused-multiply-add-vectors--predicated---writing-addend--Zda----Zda----Zn---Zm--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FNMAD Zresult.S, Pg/M, Zop2.S, Zop3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FNMAD--Floating-point-negated-fused-multiply-add-vectors--predicated---writing-multiplicand--Zdn----Za----Zdn---Zm--

### Operation

Source operation ID: `SveOperation_svnmad_n_f16_x`

**Operation**



Return a vector in which each active element *i* contains the value:



```text
-(op3 + op1[i] * op2[i])
```



The inactive elements of the result have arbitrary, undefined values.



The multiplication and addition are fused, with no intermediate rounding after the multiplication.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not. Multiplying an infinity by zero also triggers an IEEE Invalid exception, as does adding +∞ and -∞ together.

## svnmad[_n_f32]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svnmad%5B_n_f32%5D_z

### Signature (source notation)

```c
svfloat32_t svnmad[_n_f32]_z(svbool_t pg, svfloat32_t op1, svfloat32_t op2, float32_t op3);
```

### Description

Negated multiply-add, multiplicand first

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Fused multiply-accumulate

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
  "op1": {
    "register": "Zop1.S"
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
    "Zresult.S": "result"
  }
]
```

### Instruction mapping

When result is in a different register from op2 and op3, this intrinsic can use:

```asm
MOVPRFX Zresult.S, Pg/Z, Zop1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
FNMAD Zresult.S, Pg/M, Zop2.S, Zop3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FNMAD--Floating-point-negated-fused-multiply-add-vectors--predicated---writing-multiplicand--Zdn----Za----Zdn---Zm--

When result is in a different register from op1 and op3, this intrinsic can use:

```asm
MOVPRFX Zresult.S, Pg/Z, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
FNMAD Zresult.S, Pg/M, Zop1.S, Zop3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FNMAD--Floating-point-negated-fused-multiply-add-vectors--predicated---writing-multiplicand--Zdn----Za----Zdn---Zm--

When result is in a different register from op1 and op2, this intrinsic can use:

```asm
MOVPRFX Zresult.S, Pg/Z, Zop3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
FNMLA Zresult.S, Pg/M, Zop1.S, Zop2.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FNMLA--Floating-point-negated-fused-multiply-add-vectors--predicated---writing-addend--Zda----Zda----Zn---Zm--

### Operation

Source operation ID: `SveOperation_svnmad_n_f16_z`

**Operation**



Return a vector in which each active element *i* contains the value:



```text
-(op3 + op1[i] * op2[i])
```



Set the inactive elements of the result to zero.



The multiplication and addition are fused, with no intermediate rounding after the multiplication.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not. Multiplying an infinity by zero also triggers an IEEE Invalid exception, as does adding +∞ and -∞ together.

## svnmad[_n_f64]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svnmad%5B_n_f64%5D_m

### Signature (source notation)

```c
svfloat64_t svnmad[_n_f64]_m(svbool_t pg, svfloat64_t op1, svfloat64_t op2, float64_t op3);
```

### Description

Negated multiply-add, multiplicand first

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Fused multiply-accumulate

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
  "op1": {
    "register": "Zop1.D|Ztied1.D"
  },
  "op2": {
    "register": "Zop2.D"
  },
  "op3": {
    "register": "Zop3.D[*]"
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
FNMAD Ztied1.D, Pg/M, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FNMAD--Floating-point-negated-fused-multiply-add-vectors--predicated---writing-multiplicand--Zdn----Za----Zdn---Zm--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FNMAD Zresult.D, Pg/M, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FNMAD--Floating-point-negated-fused-multiply-add-vectors--predicated---writing-multiplicand--Zdn----Za----Zdn---Zm--

### Operation

Source operation ID: `SveOperation_svnmad_n_f16_m`

**Operation**



Return a vector in which each active element *i* contains the value:



```text
-(op3 + op1[i] * op2[i])
```



Take the inactive elements of the result from the corresponding elements of `op1`.



The multiplication and addition are fused, with no intermediate rounding after the multiplication.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not. Multiplying an infinity by zero also triggers an IEEE Invalid exception, as does adding +∞ and -∞ together.

## svnmad[_n_f64]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svnmad%5B_n_f64%5D_x

### Signature (source notation)

```c
svfloat64_t svnmad[_n_f64]_x(svbool_t pg, svfloat64_t op1, svfloat64_t op2, float64_t op3);
```

### Description

Negated multiply-add, multiplicand first

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Fused multiply-accumulate

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
  "op1": {
    "register": "Zop1.D|Ztied1.D"
  },
  "op2": {
    "register": "Zop2.D|Ztied2.D"
  },
  "op3": {
    "register": "Zop3.D[*]|Ztied3.D[*]"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.D|Ztied1.D|Ztied2.D|Ztied3.D": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
FNMAD Ztied1.D, Pg/M, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FNMAD--Floating-point-negated-fused-multiply-add-vectors--predicated---writing-multiplicand--Zdn----Za----Zdn---Zm--

When result and op2 are in the same register, this intrinsic compiles to:

```asm
FNMAD Ztied2.D, Pg/M, Zop1.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FNMAD--Floating-point-negated-fused-multiply-add-vectors--predicated---writing-multiplicand--Zdn----Za----Zdn---Zm--

When result and op3 are in the same register, this intrinsic compiles to:

```asm
FNMLA Ztied3.D, Pg/M, Zop1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FNMLA--Floating-point-negated-fused-multiply-add-vectors--predicated---writing-addend--Zda----Zda----Zn---Zm--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FNMAD Zresult.D, Pg/M, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FNMAD--Floating-point-negated-fused-multiply-add-vectors--predicated---writing-multiplicand--Zdn----Za----Zdn---Zm--

### Operation

Source operation ID: `SveOperation_svnmad_n_f16_x`

**Operation**



Return a vector in which each active element *i* contains the value:



```text
-(op3 + op1[i] * op2[i])
```



The inactive elements of the result have arbitrary, undefined values.



The multiplication and addition are fused, with no intermediate rounding after the multiplication.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not. Multiplying an infinity by zero also triggers an IEEE Invalid exception, as does adding +∞ and -∞ together.

## svnmad[_n_f64]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svnmad%5B_n_f64%5D_z

### Signature (source notation)

```c
svfloat64_t svnmad[_n_f64]_z(svbool_t pg, svfloat64_t op1, svfloat64_t op2, float64_t op3);
```

### Description

Negated multiply-add, multiplicand first

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Fused multiply-accumulate

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
  "op1": {
    "register": "Zop1.D"
  },
  "op2": {
    "register": "Zop2.D"
  },
  "op3": {
    "register": "Zop3.D[*]"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.D": "result"
  }
]
```

### Instruction mapping

When result is in a different register from op2 and op3, this intrinsic can use:

```asm
MOVPRFX Zresult.D, Pg/Z, Zop1.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
FNMAD Zresult.D, Pg/M, Zop2.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FNMAD--Floating-point-negated-fused-multiply-add-vectors--predicated---writing-multiplicand--Zdn----Za----Zdn---Zm--

When result is in a different register from op1 and op3, this intrinsic can use:

```asm
MOVPRFX Zresult.D, Pg/Z, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
FNMAD Zresult.D, Pg/M, Zop1.D, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FNMAD--Floating-point-negated-fused-multiply-add-vectors--predicated---writing-multiplicand--Zdn----Za----Zdn---Zm--

When result is in a different register from op1 and op2, this intrinsic can use:

```asm
MOVPRFX Zresult.D, Pg/Z, Zop3.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
FNMLA Zresult.D, Pg/M, Zop1.D, Zop2.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FNMLA--Floating-point-negated-fused-multiply-add-vectors--predicated---writing-addend--Zda----Zda----Zn---Zm--

### Operation

Source operation ID: `SveOperation_svnmad_n_f16_z`

**Operation**



Return a vector in which each active element *i* contains the value:



```text
-(op3 + op1[i] * op2[i])
```



Set the inactive elements of the result to zero.



The multiplication and addition are fused, with no intermediate rounding after the multiplication.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not. Multiplying an infinity by zero also triggers an IEEE Invalid exception, as does adding +∞ and -∞ together.

## svnmla[_f16]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svnmla%5B_f16%5D_m

### Signature (source notation)

```c
svfloat16_t svnmla[_f16]_m(svbool_t pg, svfloat16_t op1, svfloat16_t op2, svfloat16_t op3);
```

### Description

Negated multiply-add, addend first

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Fused multiply-accumulate

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
FNMLA Ztied1.H, Pg/M, Zop2.H, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FNMLA--Floating-point-negated-fused-multiply-add-vectors--predicated---writing-addend--Zda----Zda----Zn---Zm--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FNMLA Zresult.H, Pg/M, Zop2.H, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FNMLA--Floating-point-negated-fused-multiply-add-vectors--predicated---writing-addend--Zda----Zda----Zn---Zm--

### Operation

Source operation ID: `SveOperation_svnmla_f16_m`

**Operation**



Return a vector in which each active element *i* contains the value:



```text
-(op1[i] + op2[i] * op3[i])
```



Take the inactive elements of the result from the corresponding elements of `op1`.



The multiplication and addition are fused, with no intermediate rounding after the multiplication.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not. Multiplying an infinity by zero also triggers an IEEE Invalid exception, as does adding +∞ and -∞ together.

## svnmla[_f16]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svnmla%5B_f16%5D_x

### Signature (source notation)

```c
svfloat16_t svnmla[_f16]_x(svbool_t pg, svfloat16_t op1, svfloat16_t op2, svfloat16_t op3);
```

### Description

Negated multiply-add, addend first

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Fused multiply-accumulate

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
  "op1": {
    "register": "Zop1.H|Ztied1.H"
  },
  "op2": {
    "register": "Zop2.H|Ztied2.H"
  },
  "op3": {
    "register": "Zop3.H|Ztied3.H"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.H|Ztied1.H|Ztied2.H|Ztied3.H": "result"
  }
]
```

### Instruction mapping

When result and op1 are in the same register, this intrinsic compiles to:

```asm
FNMLA Ztied1.H, Pg/M, Zop2.H, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FNMLA--Floating-point-negated-fused-multiply-add-vectors--predicated---writing-addend--Zda----Zda----Zn---Zm--

When result and op2 are in the same register, this intrinsic compiles to:

```asm
FNMAD Ztied2.H, Pg/M, Zop3.H, Zop1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FNMAD--Floating-point-negated-fused-multiply-add-vectors--predicated---writing-multiplicand--Zdn----Za----Zdn---Zm--

When result and op3 are in the same register, this intrinsic compiles to:

```asm
FNMAD Ztied3.H, Pg/M, Zop2.H, Zop1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FNMAD--Floating-point-negated-fused-multiply-add-vectors--predicated---writing-multiplicand--Zdn----Za----Zdn---Zm--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FNMLA Zresult.H, Pg/M, Zop2.H, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FNMLA--Floating-point-negated-fused-multiply-add-vectors--predicated---writing-addend--Zda----Zda----Zn---Zm--

### Operation

Source operation ID: `SveOperation_svnmla_f16_x`

**Operation**



Return a vector in which each active element *i* contains the value:



```text
-(op1[i] + op2[i] * op3[i])
```



The inactive elements of the result have arbitrary, undefined values.



The multiplication and addition are fused, with no intermediate rounding after the multiplication.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not. Multiplying an infinity by zero also triggers an IEEE Invalid exception, as does adding +∞ and -∞ together.

## svnmla[_f16]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svnmla%5B_f16%5D_z

### Signature (source notation)

```c
svfloat16_t svnmla[_f16]_z(svbool_t pg, svfloat16_t op1, svfloat16_t op2, svfloat16_t op3);
```

### Description

Negated multiply-add, addend first

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Fused multiply-accumulate

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
  "op1": {
    "register": "Zop1.H"
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
    "Zresult.H": "result"
  }
]
```

### Instruction mapping

When result is in a different register from op2 and op3, this intrinsic can use:

```asm
MOVPRFX Zresult.H, Pg/Z, Zop1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
FNMLA Zresult.H, Pg/M, Zop2.H, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FNMLA--Floating-point-negated-fused-multiply-add-vectors--predicated---writing-addend--Zda----Zda----Zn---Zm--

When result is in a different register from op3 and op1, this intrinsic can use:

```asm
MOVPRFX Zresult.H, Pg/Z, Zop2.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
FNMAD Zresult.H, Pg/M, Zop3.H, Zop1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FNMAD--Floating-point-negated-fused-multiply-add-vectors--predicated---writing-multiplicand--Zdn----Za----Zdn---Zm--

When result is in a different register from op2 and op1, this intrinsic can use:

```asm
MOVPRFX Zresult.H, Pg/Z, Zop3.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
FNMAD Zresult.H, Pg/M, Zop2.H, Zop1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FNMAD--Floating-point-negated-fused-multiply-add-vectors--predicated---writing-multiplicand--Zdn----Za----Zdn---Zm--

### Operation

Source operation ID: `SveOperation_svnmla_f16_z`

**Operation**



Return a vector in which each active element *i* contains the value:



```text
-(op1[i] + op2[i] * op3[i])
```



Set the inactive elements of the result to zero.



The multiplication and addition are fused, with no intermediate rounding after the multiplication.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not. Multiplying an infinity by zero also triggers an IEEE Invalid exception, as does adding +∞ and -∞ together.

## svnmla[_f32]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svnmla%5B_f32%5D_m

### Signature (source notation)

```c
svfloat32_t svnmla[_f32]_m(svbool_t pg, svfloat32_t op1, svfloat32_t op2, svfloat32_t op3);
```

### Description

Negated multiply-add, addend first

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector arithmetic / Multiply-accumulate / Fused multiply-accumulate

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
FNMLA Ztied1.S, Pg/M, Zop2.S, Zop3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FNMLA--Floating-point-negated-fused-multiply-add-vectors--predicated---writing-addend--Zda----Zda----Zn---Zm--

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FNMLA Zresult.S, Pg/M, Zop2.S, Zop3.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FNMLA--Floating-point-negated-fused-multiply-add-vectors--predicated---writing-addend--Zda----Zda----Zn---Zm--

### Operation

Source operation ID: `SveOperation_svnmla_f16_m`

**Operation**



Return a vector in which each active element *i* contains the value:



```text
-(op1[i] + op2[i] * op3[i])
```



Take the inactive elements of the result from the corresponding elements of `op1`.



The multiplication and addition are fused, with no intermediate rounding after the multiplication.



**Exceptions**



Active signaling NaNs trigger an IEEE Invalid exception but quiet NaNs do not. Multiplying an infinity by zero also triggers an IEEE Invalid exception, as does adding +∞ and -∞ together.

