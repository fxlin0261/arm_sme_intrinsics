# SME / Vector manipulation / Set all lanes to the same value — Part 1

## svdup[_n]_bf16

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdup%5B_n%5D_bf16

### Signature (source notation)

```c
svbfloat16_t svdup[_n]_bf16(bfloat16_t op);
```

### Description

Broadcast a scalar value

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Set all lanes to the same value

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
  "op": {
    "register": "Hop|Wop"
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

When bitcast(op) is in range[1], this intrinsic can use:

```asm
DUP Zresult.H, #op
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/DUP--immediate---Broadcast-signed-immediate-to-vector-elements--unpredicated--

When op is an FP immediate[2], this intrinsic can use:

```asm
FDUP Zresult.H, #op
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FDUP--Broadcast-8-bit-floating-point-immediate-to-vector-elements--unpredicated--

When op is in a GP register, the general implementation is:

```asm
DUP Zresult.H, Wop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/DUP--scalar---Broadcast-general-purpose-register-to-vector-elements--unpredicated--

When op is in an FP register, the general implementation is:

```asm
DUP Zresult.H, Zop.H[0]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/DUP--indexed---Broadcast-indexed-element-to-vector--unpredicated--

### Operation

Source operation ID: `SveOperation_svdup_n_bf16`

**Operation**



Return a vector in which each element *i* contains `op`.



**[1]** This is true if the value is in the range [-128, 127] or is a multiple of 256 in the range [-32768, 32512]



**[2]** This is true if op is a floating-point immediate value expressable as ±n×2r, where n and r are integers such that 16 ≤ n ≤ 31 and -7 ≤ r ≤ 0.  In other words, this instruction requires op to have a normalized binary floating-point encoding with a sign bit, a 3-bit exponent, and a 4-bit fractional part.

## svdup[_n]_bf16_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdup%5B_n%5D_bf16_m

### Signature (source notation)

```c
svbfloat16_t svdup[_n]_bf16_m(svbfloat16_t inactive, svbool_t pg, bfloat16_t op);
```

### Description

Broadcast a scalar value

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Set all lanes to the same value

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
  "inactive": {
    "register": "Ztied.H"
  },
  "pg": {
    "register": "Pg"
  },
  "op": {
    "register": "Hop|Wop"
  }
}
```

### Result mapping

```json
[
  {
    "Ztied.H": "result"
  }
]
```

### Instruction mapping

When bitcast(op) is in range[1], this intrinsic can use:

```asm
CPY Ztied.H, Pg/M, #bitcast<int16_t>(op)  // [3]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CPY--immediate--merging---Copy-signed-integer-immediate-to-vector-elements--merging--

When op is an FP immediate[2], this intrinsic can use:

```asm
FCPY Ztied.H, Pg/M, #op  // [3]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCPY--Copy-8-bit-floating-point-immediate-to-vector-elements--predicated--

When op is in a GP register, the general implementation is:

```asm
CPY Ztied.H, Pg/M, Wop  // [3]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CPY--scalar---Copy-general-purpose-register-to-vector-elements--predicated--

When op is in an FP register, the general implementation is:

```asm
CPY Ztied.H, Pg/M, Hop  // [3]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CPY--SIMD-FP-scalar---Copy-SIMD-FP-scalar-register-to-vector-elements--predicated--

### Operation

Source operation ID: `SveOperation_svdup_n_bf16_m`

**Operation**



Return a vector in which each active element *i* contains `op`. Take the inactive elements of the result from the corresponding elements of `inactive`.



**[1]** This is true if the value is in the range [-128, 127] or is a multiple of 256 in the range [-32768, 32512]



**[2]** This is true if op is a floating-point immediate value expressable as ±n×2r, where n and r are integers such that 16 ≤ n ≤ 31 and -7 ≤ r ≤ 0.  In other words, this instruction requires op to have a normalized binary floating-point encoding with a sign bit, a 3-bit exponent, and a 4-bit fractional part.



**[3]** If instead `result` is in a different register from the inputs, the compiler can add a preceding [MOVPRFX (unpredicated)](https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--) instruction

## svdup[_n]_bf16_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdup%5B_n%5D_bf16_x

### Signature (source notation)

```c
svbfloat16_t svdup[_n]_bf16_x(svbool_t pg, bfloat16_t op);
```

### Description

Broadcast a scalar value

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Set all lanes to the same value

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
  "op": {
    "register": "Hop|Wop"
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

When bitcast(op) is in range[1], this intrinsic can use:

```asm
CPY Zresult.H, Pg/Z, #bitcast<int16_t>(op)
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CPY--immediate--merging---Copy-signed-integer-immediate-to-vector-elements--merging--

…or, alternatively:

```asm
DUP Zresult.H, #op
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/DUP--immediate---Broadcast-signed-immediate-to-vector-elements--unpredicated--

When op is an FP immediate[2], this intrinsic can use:

```asm
FCPY Zresult.H, Pg/M, #op
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCPY--Copy-8-bit-floating-point-immediate-to-vector-elements--predicated--

…or, alternatively:

```asm
FDUP Zresult.H, #op
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FDUP--Broadcast-8-bit-floating-point-immediate-to-vector-elements--unpredicated--

When op is in a GP register, the general implementation is:

```asm
DUP Zresult.H, Wop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/DUP--scalar---Broadcast-general-purpose-register-to-vector-elements--unpredicated--

When op is in an FP register, the general implementation is:

```asm
DUP Zresult.H, Zop.H[0]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/DUP--indexed---Broadcast-indexed-element-to-vector--unpredicated--

### Operation

Source operation ID: `SveOperation_svdup_n_bf16_x`

**Operation**



Return a vector in which each active element *i* contains `op`. The inactive elements of the result have arbitrary, undefined values.



**[1]** This is true if the value is in the range [-128, 127] or is a multiple of 256 in the range [-32768, 32512]



**[2]** This is true if op is a floating-point immediate value expressable as ±n×2r, where n and r are integers such that 16 ≤ n ≤ 31 and -7 ≤ r ≤ 0.  In other words, this instruction requires op to have a normalized binary floating-point encoding with a sign bit, a 3-bit exponent, and a 4-bit fractional part.

## svdup[_n]_bf16_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdup%5B_n%5D_bf16_z

### Signature (source notation)

```c
svbfloat16_t svdup[_n]_bf16_z(svbool_t pg, bfloat16_t op);
```

### Description

Broadcast a scalar value

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Set all lanes to the same value

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
  "op": {
    "register": "Hop|Wop"
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

When bitcast(op) is in range[1], this intrinsic can use:

```asm
CPY Zresult.H, Pg/Z, #bitcast<int16_t>(op)
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CPY--immediate--merging---Copy-signed-integer-immediate-to-vector-elements--merging--

When op is an FP immediate[2], this intrinsic can use:

```asm
DUP Zresult.H, #0
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/DUP--immediate---Broadcast-signed-immediate-to-vector-elements--unpredicated--

```asm
FCPY Zresult.H, Pg/M, #op
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCPY--Copy-8-bit-floating-point-immediate-to-vector-elements--predicated--

When op is in a GP register, the general implementation is:

```asm
DUP Zresult.H, #0
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/DUP--immediate---Broadcast-signed-immediate-to-vector-elements--unpredicated--

```asm
CPY Zresult.H, Pg/M, Wop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CPY--scalar---Copy-general-purpose-register-to-vector-elements--predicated--

When op is in an FP register and result is in a different register from op, this intrinsic can use:

```asm
MOVPRFX Zresult.H, Pg/Z, Zop.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
CPY Zresult.H, Pg/M, Hop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CPY--SIMD-FP-scalar---Copy-SIMD-FP-scalar-register-to-vector-elements--predicated--

### Operation

Source operation ID: `SveOperation_svdup_n_bf16_z`

**Operation**



Return a vector in which each active element *i* contains `op`. Set the inactive elements of the result to zero.



**[1]** This is true if the value is in the range [-128, 127] or is a multiple of 256 in the range [-32768, 32512]



**[2]** This is true if op is a floating-point immediate value expressable as ±n×2r, where n and r are integers such that 16 ≤ n ≤ 31 and -7 ≤ r ≤ 0.  In other words, this instruction requires op to have a normalized binary floating-point encoding with a sign bit, a 3-bit exponent, and a 4-bit fractional part.

## svdup[_n]_f16

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdup%5B_n%5D_f16

### Signature (source notation)

```c
svfloat16_t svdup[_n]_f16(float16_t op);
```

### Description

Broadcast a scalar value

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Set all lanes to the same value

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
  "op": {
    "register": "Hop|Wop"
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

When bitcast(op) is in range[1], this intrinsic can use:

```asm
DUP Zresult.H, #op
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/DUP--immediate---Broadcast-signed-immediate-to-vector-elements--unpredicated--

When op is an FP immediate[2], this intrinsic can use:

```asm
FDUP Zresult.H, #op
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FDUP--Broadcast-8-bit-floating-point-immediate-to-vector-elements--unpredicated--

When op is in a GP register, the general implementation is:

```asm
DUP Zresult.H, Wop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/DUP--scalar---Broadcast-general-purpose-register-to-vector-elements--unpredicated--

When op is in an FP register, the general implementation is:

```asm
DUP Zresult.H, Zop.H[0]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/DUP--indexed---Broadcast-indexed-element-to-vector--unpredicated--

### Operation

Source operation ID: `SveOperation_svdup_n_bf16`

**Operation**



Return a vector in which each element *i* contains `op`.



**[1]** This is true if the value is in the range [-128, 127] or is a multiple of 256 in the range [-32768, 32512]



**[2]** This is true if op is a floating-point immediate value expressable as ±n×2r, where n and r are integers such that 16 ≤ n ≤ 31 and -7 ≤ r ≤ 0.  In other words, this instruction requires op to have a normalized binary floating-point encoding with a sign bit, a 3-bit exponent, and a 4-bit fractional part.

## svdup[_n]_f16_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdup%5B_n%5D_f16_m

### Signature (source notation)

```c
svfloat16_t svdup[_n]_f16_m(svfloat16_t inactive, svbool_t pg, float16_t op);
```

### Description

Broadcast a scalar value

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Set all lanes to the same value

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
  "inactive": {
    "register": "Ztied.H"
  },
  "pg": {
    "register": "Pg"
  },
  "op": {
    "register": "Hop|Wop"
  }
}
```

### Result mapping

```json
[
  {
    "Ztied.H": "result"
  }
]
```

### Instruction mapping

When bitcast(op) is in range[1], this intrinsic can use:

```asm
CPY Ztied.H, Pg/M, #bitcast<int16_t>(op)  // [3]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CPY--immediate--merging---Copy-signed-integer-immediate-to-vector-elements--merging--

When op is an FP immediate[2], this intrinsic can use:

```asm
FCPY Ztied.H, Pg/M, #op  // [3]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCPY--Copy-8-bit-floating-point-immediate-to-vector-elements--predicated--

When op is in a GP register, the general implementation is:

```asm
CPY Ztied.H, Pg/M, Wop  // [3]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CPY--scalar---Copy-general-purpose-register-to-vector-elements--predicated--

When op is in an FP register, the general implementation is:

```asm
CPY Ztied.H, Pg/M, Hop  // [3]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CPY--SIMD-FP-scalar---Copy-SIMD-FP-scalar-register-to-vector-elements--predicated--

### Operation

Source operation ID: `SveOperation_svdup_n_bf16_m`

**Operation**



Return a vector in which each active element *i* contains `op`. Take the inactive elements of the result from the corresponding elements of `inactive`.



**[1]** This is true if the value is in the range [-128, 127] or is a multiple of 256 in the range [-32768, 32512]



**[2]** This is true if op is a floating-point immediate value expressable as ±n×2r, where n and r are integers such that 16 ≤ n ≤ 31 and -7 ≤ r ≤ 0.  In other words, this instruction requires op to have a normalized binary floating-point encoding with a sign bit, a 3-bit exponent, and a 4-bit fractional part.



**[3]** If instead `result` is in a different register from the inputs, the compiler can add a preceding [MOVPRFX (unpredicated)](https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--) instruction

## svdup[_n]_f16_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdup%5B_n%5D_f16_x

### Signature (source notation)

```c
svfloat16_t svdup[_n]_f16_x(svbool_t pg, float16_t op);
```

### Description

Broadcast a scalar value

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Set all lanes to the same value

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
  "op": {
    "register": "Hop|Wop"
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

When bitcast(op) is in range[1], this intrinsic can use:

```asm
CPY Zresult.H, Pg/Z, #bitcast<int16_t>(op)
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CPY--immediate--merging---Copy-signed-integer-immediate-to-vector-elements--merging--

When bitcast(op) is in range[1] and pg is all-true, this intrinsic can use:

```asm
DUP Zresult.H, #op
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/DUP--immediate---Broadcast-signed-immediate-to-vector-elements--unpredicated--

When op is an FP immediate[2], this intrinsic can use:

```asm
FCPY Zresult.H, Pg/M, #op
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCPY--Copy-8-bit-floating-point-immediate-to-vector-elements--predicated--

When op is an FP immediate[2] and pg is all-true, this intrinsic can use:

```asm
FDUP Zresult.H, #op
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FDUP--Broadcast-8-bit-floating-point-immediate-to-vector-elements--unpredicated--

When pg is all-true and op is in a GP register, this intrinsic can use:

```asm
DUP Zresult.H, Wop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/DUP--scalar---Broadcast-general-purpose-register-to-vector-elements--unpredicated--

When pg is all-true and op is in an FP register, this intrinsic can use:

```asm
DUP Zresult.H, Zop.H[0]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/DUP--indexed---Broadcast-indexed-element-to-vector--unpredicated--

### Operation

Source operation ID: `SveOperation_svdup_n_bf16_x`

**Operation**



Return a vector in which each active element *i* contains `op`. The inactive elements of the result have arbitrary, undefined values.



**[1]** This is true if the value is in the range [-128, 127] or is a multiple of 256 in the range [-32768, 32512]



**[2]** This is true if op is a floating-point immediate value expressable as ±n×2r, where n and r are integers such that 16 ≤ n ≤ 31 and -7 ≤ r ≤ 0.  In other words, this instruction requires op to have a normalized binary floating-point encoding with a sign bit, a 3-bit exponent, and a 4-bit fractional part.

## svdup[_n]_f16_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdup%5B_n%5D_f16_z

### Signature (source notation)

```c
svfloat16_t svdup[_n]_f16_z(svbool_t pg, float16_t op);
```

### Description

Broadcast a scalar value

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Set all lanes to the same value

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
  "op": {
    "register": "Hop|Wop"
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

When bitcast(op) is in range[1], this intrinsic can use:

```asm
CPY Zresult.H, Pg/Z, #bitcast<int16_t>(op)
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CPY--immediate--merging---Copy-signed-integer-immediate-to-vector-elements--merging--

When op is an FP immediate[2], this intrinsic can use:

```asm
DUP Zresult.H, #0
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/DUP--immediate---Broadcast-signed-immediate-to-vector-elements--unpredicated--

```asm
FCPY Zresult.H, Pg/M, #op
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCPY--Copy-8-bit-floating-point-immediate-to-vector-elements--predicated--

When op is in a GP register, the general implementation is:

```asm
DUP Zresult.H, #0
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/DUP--immediate---Broadcast-signed-immediate-to-vector-elements--unpredicated--

```asm
CPY Zresult.H, Pg/M, Wop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CPY--scalar---Copy-general-purpose-register-to-vector-elements--predicated--

When op is in an FP register and result is in a different register from op, this intrinsic can use:

```asm
MOVPRFX Zresult.H, Pg/Z, Zop.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
CPY Zresult.H, Pg/M, Hop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CPY--SIMD-FP-scalar---Copy-SIMD-FP-scalar-register-to-vector-elements--predicated--

### Operation

Source operation ID: `SveOperation_svdup_n_bf16_z`

**Operation**



Return a vector in which each active element *i* contains `op`. Set the inactive elements of the result to zero.



**[1]** This is true if the value is in the range [-128, 127] or is a multiple of 256 in the range [-32768, 32512]



**[2]** This is true if op is a floating-point immediate value expressable as ±n×2r, where n and r are integers such that 16 ≤ n ≤ 31 and -7 ≤ r ≤ 0.  In other words, this instruction requires op to have a normalized binary floating-point encoding with a sign bit, a 3-bit exponent, and a 4-bit fractional part.

## svdup[_n]_f32

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdup%5B_n%5D_f32

### Signature (source notation)

```c
svfloat32_t svdup[_n]_f32(float32_t op);
```

### Description

Broadcast a scalar value

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Set all lanes to the same value

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
  "op": {
    "register": "Sop|Wop"
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

When bitcast(op) is in range[1], this intrinsic can use:

```asm
DUP Zresult.S, #op
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/DUP--immediate---Broadcast-signed-immediate-to-vector-elements--unpredicated--

When op is an FP immediate[2], this intrinsic can use:

```asm
FDUP Zresult.S, #op
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FDUP--Broadcast-8-bit-floating-point-immediate-to-vector-elements--unpredicated--

When op is in a GP register, the general implementation is:

```asm
DUP Zresult.S, Wop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/DUP--scalar---Broadcast-general-purpose-register-to-vector-elements--unpredicated--

When op is in an FP register, the general implementation is:

```asm
DUP Zresult.S, Zop.S[0]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/DUP--indexed---Broadcast-indexed-element-to-vector--unpredicated--

### Operation

Source operation ID: `SveOperation_svdup_n_bf16`

**Operation**



Return a vector in which each element *i* contains `op`.



**[1]** This is true if the value is in the range [-128, 127] or is a multiple of 256 in the range [-32768, 32512]



**[2]** This is true if op is a floating-point immediate value expressable as ±n×2r, where n and r are integers such that 16 ≤ n ≤ 31 and -7 ≤ r ≤ 0.  In other words, this instruction requires op to have a normalized binary floating-point encoding with a sign bit, a 3-bit exponent, and a 4-bit fractional part.

## svdup[_n]_f32_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdup%5B_n%5D_f32_m

### Signature (source notation)

```c
svfloat32_t svdup[_n]_f32_m(svfloat32_t inactive, svbool_t pg, float32_t op);
```

### Description

Broadcast a scalar value

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Set all lanes to the same value

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
  "inactive": {
    "register": "Ztied.S"
  },
  "pg": {
    "register": "Pg"
  },
  "op": {
    "register": "Sop|Wop"
  }
}
```

### Result mapping

```json
[
  {
    "Ztied.S": "result"
  }
]
```

### Instruction mapping

When bitcast(op) is in range[1], this intrinsic can use:

```asm
CPY Ztied.S, Pg/M, #bitcast<int32_t>(op)  // [3]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CPY--immediate--merging---Copy-signed-integer-immediate-to-vector-elements--merging--

When op is an FP immediate[2], this intrinsic can use:

```asm
FCPY Ztied.S, Pg/M, #op  // [3]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCPY--Copy-8-bit-floating-point-immediate-to-vector-elements--predicated--

When op is in a GP register, the general implementation is:

```asm
CPY Ztied.S, Pg/M, Wop  // [3]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CPY--scalar---Copy-general-purpose-register-to-vector-elements--predicated--

When op is in an FP register, the general implementation is:

```asm
CPY Ztied.S, Pg/M, Sop  // [3]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CPY--SIMD-FP-scalar---Copy-SIMD-FP-scalar-register-to-vector-elements--predicated--

### Operation

Source operation ID: `SveOperation_svdup_n_bf16_m`

**Operation**



Return a vector in which each active element *i* contains `op`. Take the inactive elements of the result from the corresponding elements of `inactive`.



**[1]** This is true if the value is in the range [-128, 127] or is a multiple of 256 in the range [-32768, 32512]



**[2]** This is true if op is a floating-point immediate value expressable as ±n×2r, where n and r are integers such that 16 ≤ n ≤ 31 and -7 ≤ r ≤ 0.  In other words, this instruction requires op to have a normalized binary floating-point encoding with a sign bit, a 3-bit exponent, and a 4-bit fractional part.



**[3]** If instead `result` is in a different register from the inputs, the compiler can add a preceding [MOVPRFX (unpredicated)](https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--) instruction

## svdup[_n]_f32_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdup%5B_n%5D_f32_x

### Signature (source notation)

```c
svfloat32_t svdup[_n]_f32_x(svbool_t pg, float32_t op);
```

### Description

Broadcast a scalar value

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Set all lanes to the same value

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
  "op": {
    "register": "Sop|Wop"
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

When bitcast(op) is in range[1], this intrinsic can use:

```asm
CPY Zresult.S, Pg/Z, #bitcast<int32_t>(op)
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CPY--immediate--merging---Copy-signed-integer-immediate-to-vector-elements--merging--

When bitcast(op) is in range[1] and pg is all-true, this intrinsic can use:

```asm
DUP Zresult.S, #op
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/DUP--immediate---Broadcast-signed-immediate-to-vector-elements--unpredicated--

When op is an FP immediate[2], this intrinsic can use:

```asm
FCPY Zresult.S, Pg/M, #op
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCPY--Copy-8-bit-floating-point-immediate-to-vector-elements--predicated--

When op is an FP immediate[2] and pg is all-true, this intrinsic can use:

```asm
FDUP Zresult.S, #op
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FDUP--Broadcast-8-bit-floating-point-immediate-to-vector-elements--unpredicated--

When pg is all-true and op is in a GP register, this intrinsic can use:

```asm
DUP Zresult.S, Wop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/DUP--scalar---Broadcast-general-purpose-register-to-vector-elements--unpredicated--

When pg is all-true and op is in an FP register, this intrinsic can use:

```asm
DUP Zresult.S, Zop.S[0]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/DUP--indexed---Broadcast-indexed-element-to-vector--unpredicated--

### Operation

Source operation ID: `SveOperation_svdup_n_bf16_x`

**Operation**



Return a vector in which each active element *i* contains `op`. The inactive elements of the result have arbitrary, undefined values.



**[1]** This is true if the value is in the range [-128, 127] or is a multiple of 256 in the range [-32768, 32512]



**[2]** This is true if op is a floating-point immediate value expressable as ±n×2r, where n and r are integers such that 16 ≤ n ≤ 31 and -7 ≤ r ≤ 0.  In other words, this instruction requires op to have a normalized binary floating-point encoding with a sign bit, a 3-bit exponent, and a 4-bit fractional part.

## svdup[_n]_f32_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdup%5B_n%5D_f32_z

### Signature (source notation)

```c
svfloat32_t svdup[_n]_f32_z(svbool_t pg, float32_t op);
```

### Description

Broadcast a scalar value

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Set all lanes to the same value

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
  "op": {
    "register": "Sop|Wop"
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

When bitcast(op) is in range[1], this intrinsic can use:

```asm
CPY Zresult.S, Pg/Z, #bitcast<int32_t>(op)
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CPY--immediate--merging---Copy-signed-integer-immediate-to-vector-elements--merging--

When op is an FP immediate[2], this intrinsic can use:

```asm
DUP Zresult.S, #0
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/DUP--immediate---Broadcast-signed-immediate-to-vector-elements--unpredicated--

```asm
FCPY Zresult.S, Pg/M, #op
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCPY--Copy-8-bit-floating-point-immediate-to-vector-elements--predicated--

When op is in a GP register, the general implementation is:

```asm
DUP Zresult.S, #0
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/DUP--immediate---Broadcast-signed-immediate-to-vector-elements--unpredicated--

```asm
CPY Zresult.S, Pg/M, Wop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CPY--scalar---Copy-general-purpose-register-to-vector-elements--predicated--

When op is in an FP register and result is in a different register from op, this intrinsic can use:

```asm
MOVPRFX Zresult.S, Pg/Z, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
CPY Zresult.S, Pg/M, Sop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CPY--SIMD-FP-scalar---Copy-SIMD-FP-scalar-register-to-vector-elements--predicated--

### Operation

Source operation ID: `SveOperation_svdup_n_bf16_z`

**Operation**



Return a vector in which each active element *i* contains `op`. Set the inactive elements of the result to zero.



**[1]** This is true if the value is in the range [-128, 127] or is a multiple of 256 in the range [-32768, 32512]



**[2]** This is true if op is a floating-point immediate value expressable as ±n×2r, where n and r are integers such that 16 ≤ n ≤ 31 and -7 ≤ r ≤ 0.  In other words, this instruction requires op to have a normalized binary floating-point encoding with a sign bit, a 3-bit exponent, and a 4-bit fractional part.

## svdup[_n]_f64

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdup%5B_n%5D_f64

### Signature (source notation)

```c
svfloat64_t svdup[_n]_f64(float64_t op);
```

### Description

Broadcast a scalar value

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Set all lanes to the same value

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
  "op": {
    "register": "Dop|Xop"
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

When bitcast(op) is in range[1], this intrinsic can use:

```asm
DUP Zresult.D, #op
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/DUP--immediate---Broadcast-signed-immediate-to-vector-elements--unpredicated--

When op is an FP immediate[2], this intrinsic can use:

```asm
FDUP Zresult.D, #op
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FDUP--Broadcast-8-bit-floating-point-immediate-to-vector-elements--unpredicated--

When op is in a GP register, the general implementation is:

```asm
DUP Zresult.D, Xop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/DUP--scalar---Broadcast-general-purpose-register-to-vector-elements--unpredicated--

When op is in an FP register, the general implementation is:

```asm
DUP Zresult.D, Zop.D[0]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/DUP--indexed---Broadcast-indexed-element-to-vector--unpredicated--

### Operation

Source operation ID: `SveOperation_svdup_n_bf16`

**Operation**



Return a vector in which each element *i* contains `op`.



**[1]** This is true if the value is in the range [-128, 127] or is a multiple of 256 in the range [-32768, 32512]



**[2]** This is true if op is a floating-point immediate value expressable as ±n×2r, where n and r are integers such that 16 ≤ n ≤ 31 and -7 ≤ r ≤ 0.  In other words, this instruction requires op to have a normalized binary floating-point encoding with a sign bit, a 3-bit exponent, and a 4-bit fractional part.

## svdup[_n]_f64_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdup%5B_n%5D_f64_m

### Signature (source notation)

```c
svfloat64_t svdup[_n]_f64_m(svfloat64_t inactive, svbool_t pg, float64_t op);
```

### Description

Broadcast a scalar value

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Set all lanes to the same value

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
  "inactive": {
    "register": "Ztied.D"
  },
  "pg": {
    "register": "Pg"
  },
  "op": {
    "register": "Dop|Xop"
  }
}
```

### Result mapping

```json
[
  {
    "Ztied.D": "result"
  }
]
```

### Instruction mapping

When bitcast(op) is in range[1], this intrinsic can use:

```asm
CPY Ztied.D, Pg/M, #bitcast<int64_t>(op)  // [3]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CPY--immediate--merging---Copy-signed-integer-immediate-to-vector-elements--merging--

When op is an FP immediate[2], this intrinsic can use:

```asm
FCPY Ztied.D, Pg/M, #op  // [3]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCPY--Copy-8-bit-floating-point-immediate-to-vector-elements--predicated--

When op is in a GP register, the general implementation is:

```asm
CPY Ztied.D, Pg/M, Xop  // [3]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CPY--scalar---Copy-general-purpose-register-to-vector-elements--predicated--

When op is in an FP register, the general implementation is:

```asm
CPY Ztied.D, Pg/M, Dop  // [3]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CPY--SIMD-FP-scalar---Copy-SIMD-FP-scalar-register-to-vector-elements--predicated--

### Operation

Source operation ID: `SveOperation_svdup_n_bf16_m`

**Operation**



Return a vector in which each active element *i* contains `op`. Take the inactive elements of the result from the corresponding elements of `inactive`.



**[1]** This is true if the value is in the range [-128, 127] or is a multiple of 256 in the range [-32768, 32512]



**[2]** This is true if op is a floating-point immediate value expressable as ±n×2r, where n and r are integers such that 16 ≤ n ≤ 31 and -7 ≤ r ≤ 0.  In other words, this instruction requires op to have a normalized binary floating-point encoding with a sign bit, a 3-bit exponent, and a 4-bit fractional part.



**[3]** If instead `result` is in a different register from the inputs, the compiler can add a preceding [MOVPRFX (unpredicated)](https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--) instruction

## svdup[_n]_f64_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdup%5B_n%5D_f64_x

### Signature (source notation)

```c
svfloat64_t svdup[_n]_f64_x(svbool_t pg, float64_t op);
```

### Description

Broadcast a scalar value

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Set all lanes to the same value

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
  "op": {
    "register": "Dop|Xop"
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

When bitcast(op) is in range[1], this intrinsic can use:

```asm
CPY Zresult.D, Pg/Z, #bitcast<int64_t>(op)
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CPY--immediate--merging---Copy-signed-integer-immediate-to-vector-elements--merging--

When bitcast(op) is in range[1] and pg is all-true, this intrinsic can use:

```asm
DUP Zresult.D, #op
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/DUP--immediate---Broadcast-signed-immediate-to-vector-elements--unpredicated--

When op is an FP immediate[2], this intrinsic can use:

```asm
FCPY Zresult.D, Pg/M, #op
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCPY--Copy-8-bit-floating-point-immediate-to-vector-elements--predicated--

When op is an FP immediate[2] and pg is all-true, this intrinsic can use:

```asm
FDUP Zresult.D, #op
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FDUP--Broadcast-8-bit-floating-point-immediate-to-vector-elements--unpredicated--

When pg is all-true and op is in a GP register, this intrinsic can use:

```asm
DUP Zresult.D, Xop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/DUP--scalar---Broadcast-general-purpose-register-to-vector-elements--unpredicated--

When pg is all-true and op is in an FP register, this intrinsic can use:

```asm
DUP Zresult.D, Zop.D[0]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/DUP--indexed---Broadcast-indexed-element-to-vector--unpredicated--

### Operation

Source operation ID: `SveOperation_svdup_n_bf16_x`

**Operation**



Return a vector in which each active element *i* contains `op`. The inactive elements of the result have arbitrary, undefined values.



**[1]** This is true if the value is in the range [-128, 127] or is a multiple of 256 in the range [-32768, 32512]



**[2]** This is true if op is a floating-point immediate value expressable as ±n×2r, where n and r are integers such that 16 ≤ n ≤ 31 and -7 ≤ r ≤ 0.  In other words, this instruction requires op to have a normalized binary floating-point encoding with a sign bit, a 3-bit exponent, and a 4-bit fractional part.

## svdup[_n]_f64_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdup%5B_n%5D_f64_z

### Signature (source notation)

```c
svfloat64_t svdup[_n]_f64_z(svbool_t pg, float64_t op);
```

### Description

Broadcast a scalar value

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Set all lanes to the same value

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
  "op": {
    "register": "Dop|Xop"
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

When bitcast(op) is in range[1], this intrinsic can use:

```asm
CPY Zresult.D, Pg/Z, #bitcast<int64_t>(op)
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CPY--immediate--merging---Copy-signed-integer-immediate-to-vector-elements--merging--

When op is an FP immediate[2], this intrinsic can use:

```asm
DUP Zresult.D, #0
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/DUP--immediate---Broadcast-signed-immediate-to-vector-elements--unpredicated--

```asm
FCPY Zresult.D, Pg/M, #op
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCPY--Copy-8-bit-floating-point-immediate-to-vector-elements--predicated--

When op is in a GP register, the general implementation is:

```asm
DUP Zresult.D, #0
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/DUP--immediate---Broadcast-signed-immediate-to-vector-elements--unpredicated--

```asm
CPY Zresult.D, Pg/M, Xop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CPY--scalar---Copy-general-purpose-register-to-vector-elements--predicated--

When op is in an FP register and result is in a different register from op, this intrinsic can use:

```asm
MOVPRFX Zresult.D, Pg/Z, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
CPY Zresult.D, Pg/M, Dop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CPY--SIMD-FP-scalar---Copy-SIMD-FP-scalar-register-to-vector-elements--predicated--

### Operation

Source operation ID: `SveOperation_svdup_n_bf16_z`

**Operation**



Return a vector in which each active element *i* contains `op`. Set the inactive elements of the result to zero.



**[1]** This is true if the value is in the range [-128, 127] or is a multiple of 256 in the range [-32768, 32512]



**[2]** This is true if op is a floating-point immediate value expressable as ±n×2r, where n and r are integers such that 16 ≤ n ≤ 31 and -7 ≤ r ≤ 0.  In other words, this instruction requires op to have a normalized binary floating-point encoding with a sign bit, a 3-bit exponent, and a 4-bit fractional part.

## svdup[_n]_s16

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdup%5B_n%5D_s16

### Signature (source notation)

```c
svint16_t svdup[_n]_s16(int16_t op);
```

### Description

Broadcast a scalar value

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Set all lanes to the same value

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
  "op": {
    "register": "Hop|Wop"
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

When op is in range[1], this intrinsic can use:

```asm
DUP Zresult.H, #op
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/DUP--immediate---Broadcast-signed-immediate-to-vector-elements--unpredicated--

When op is an FP immediate[2], this intrinsic can use:

```asm
FDUP Zresult.H, #op
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FDUP--Broadcast-8-bit-floating-point-immediate-to-vector-elements--unpredicated--

When op is a logical immediate[3], this intrinsic can use:

```asm
DUPM Zresult.H, #op
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/DUPM--Broadcast-logical-bitmask-immediate-to-vector--unpredicated--

When op is in a GP register, the general implementation is:

```asm
DUP Zresult.H, Wop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/DUP--scalar---Broadcast-general-purpose-register-to-vector-elements--unpredicated--

When op is in an FP register, the general implementation is:

```asm
DUP Zresult.H, Zop.H[0]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/DUP--indexed---Broadcast-indexed-element-to-vector--unpredicated--

### Operation

Source operation ID: `SveOperation_svdup_n_s16`

**Operation**



Return a vector in which each element *i* contains `op`.



**[1]** This is true if the value is in the range [-128, 127] or is a multiple of 256 in the range [-32768, 32512]



**[2]** This is true if op is a floating-point immediate value expressable as ±n×2r, where n and r are integers such that 16 ≤ n ≤ 31 and -7 ≤ r ≤ 0.  In other words, this instruction requires op to have a normalized binary floating-point encoding with a sign bit, a 3-bit exponent, and a 4-bit fractional part.



**[3]** This is true if op is filled by some replicated bitmask *b* for which either all 0s in *b* are consecutive or all 1s in *b* are consecutive.

## svdup[_n]_s16_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdup%5B_n%5D_s16_m

### Signature (source notation)

```c
svint16_t svdup[_n]_s16_m(svint16_t inactive, svbool_t pg, int16_t op);
```

### Description

Broadcast a scalar value

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Set all lanes to the same value

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
  "inactive": {
    "register": "Ztied.H"
  },
  "pg": {
    "register": "Pg"
  },
  "op": {
    "register": "Hop|Wop"
  }
}
```

### Result mapping

```json
[
  {
    "Ztied.H": "result"
  }
]
```

### Instruction mapping

When op is in range[1], this intrinsic can use:

```asm
CPY Ztied.H, Pg/M, #op  // [3]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CPY--immediate--merging---Copy-signed-integer-immediate-to-vector-elements--merging--

When op is an FP immediate[2], this intrinsic can use:

```asm
FCPY Ztied.H, Pg/M, #op  // [3]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCPY--Copy-8-bit-floating-point-immediate-to-vector-elements--predicated--

When op is in a GP register, the general implementation is:

```asm
CPY Ztied.H, Pg/M, Wop  // [3]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CPY--scalar---Copy-general-purpose-register-to-vector-elements--predicated--

When op is in an FP register, the general implementation is:

```asm
CPY Ztied.H, Pg/M, Hop  // [3]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CPY--SIMD-FP-scalar---Copy-SIMD-FP-scalar-register-to-vector-elements--predicated--

### Operation

Source operation ID: `SveOperation_svdup_n_bf16_m`

**Operation**



Return a vector in which each active element *i* contains `op`. Take the inactive elements of the result from the corresponding elements of `inactive`.



**[1]** This is true if the value is in the range [-128, 127] or is a multiple of 256 in the range [-32768, 32512]



**[2]** This is true if op is a floating-point immediate value expressable as ±n×2r, where n and r are integers such that 16 ≤ n ≤ 31 and -7 ≤ r ≤ 0.  In other words, this instruction requires op to have a normalized binary floating-point encoding with a sign bit, a 3-bit exponent, and a 4-bit fractional part.



**[3]** If instead `result` is in a different register from the inputs, the compiler can add a preceding [MOVPRFX (unpredicated)](https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--) instruction

## svdup[_n]_s16_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdup%5B_n%5D_s16_x

### Signature (source notation)

```c
svint16_t svdup[_n]_s16_x(svbool_t pg, int16_t op);
```

### Description

Broadcast a scalar value

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Set all lanes to the same value

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
  "op": {
    "register": "Hop|Wop"
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

When op is in range[1], this intrinsic can use:

```asm
CPY Zresult.H, Pg/Z, #op
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CPY--immediate--merging---Copy-signed-integer-immediate-to-vector-elements--merging--

…or, alternatively:

```asm
DUP Zresult.H, #op
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/DUP--immediate---Broadcast-signed-immediate-to-vector-elements--unpredicated--

When op is an FP immediate[2], this intrinsic can use:

```asm
FCPY Zresult.H, Pg/M, #op
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCPY--Copy-8-bit-floating-point-immediate-to-vector-elements--predicated--

…or, alternatively:

```asm
FDUP Zresult.H, #op
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FDUP--Broadcast-8-bit-floating-point-immediate-to-vector-elements--unpredicated--

When op is a logical immediate[3], this intrinsic can use:

```asm
DUPM Zresult.H, #op
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/DUPM--Broadcast-logical-bitmask-immediate-to-vector--unpredicated--

When op is in a GP register, the general implementation is:

```asm
DUP Zresult.H, Wop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/DUP--scalar---Broadcast-general-purpose-register-to-vector-elements--unpredicated--

When op is in an FP register, the general implementation is:

```asm
DUP Zresult.H, Zop.H[0]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/DUP--indexed---Broadcast-indexed-element-to-vector--unpredicated--

### Operation

Source operation ID: `SveOperation_svdup_n_s16_x`

**Operation**



Return a vector in which each active element *i* contains `op`. The inactive elements of the result have arbitrary, undefined values.



**[1]** This is true if the value is in the range [-128, 127] or is a multiple of 256 in the range [-32768, 32512]



**[2]** This is true if op is a floating-point immediate value expressable as ±n×2r, where n and r are integers such that 16 ≤ n ≤ 31 and -7 ≤ r ≤ 0.  In other words, this instruction requires op to have a normalized binary floating-point encoding with a sign bit, a 3-bit exponent, and a 4-bit fractional part.



**[3]** This is true if op is filled by some replicated bitmask *b* for which either all 0s in *b* are consecutive or all 1s in *b* are consecutive.

## svdup[_n]_s16_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdup%5B_n%5D_s16_z

### Signature (source notation)

```c
svint16_t svdup[_n]_s16_z(svbool_t pg, int16_t op);
```

### Description

Broadcast a scalar value

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Set all lanes to the same value

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
  "op": {
    "register": "Hop|Wop"
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

When op is in range[1], this intrinsic can use:

```asm
CPY Zresult.H, Pg/Z, #op
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CPY--immediate--merging---Copy-signed-integer-immediate-to-vector-elements--merging--

When op is an FP immediate[2], this intrinsic can use:

```asm
DUP Zresult.H, #0
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/DUP--immediate---Broadcast-signed-immediate-to-vector-elements--unpredicated--

```asm
FCPY Zresult.H, Pg/M, #op
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCPY--Copy-8-bit-floating-point-immediate-to-vector-elements--predicated--

When op is in a GP register, the general implementation is:

```asm
DUP Zresult.H, #0
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/DUP--immediate---Broadcast-signed-immediate-to-vector-elements--unpredicated--

```asm
CPY Zresult.H, Pg/M, Wop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CPY--scalar---Copy-general-purpose-register-to-vector-elements--predicated--

When op is in an FP register and result is in a different register from op, this intrinsic can use:

```asm
MOVPRFX Zresult.H, Pg/Z, Zop.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
CPY Zresult.H, Pg/M, Hop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CPY--SIMD-FP-scalar---Copy-SIMD-FP-scalar-register-to-vector-elements--predicated--

### Operation

Source operation ID: `SveOperation_svdup_n_bf16_z`

**Operation**



Return a vector in which each active element *i* contains `op`. Set the inactive elements of the result to zero.



**[1]** This is true if the value is in the range [-128, 127] or is a multiple of 256 in the range [-32768, 32512]



**[2]** This is true if op is a floating-point immediate value expressable as ±n×2r, where n and r are integers such that 16 ≤ n ≤ 31 and -7 ≤ r ≤ 0.  In other words, this instruction requires op to have a normalized binary floating-point encoding with a sign bit, a 3-bit exponent, and a 4-bit fractional part.

## svdup[_n]_s32

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdup%5B_n%5D_s32

### Signature (source notation)

```c
svint32_t svdup[_n]_s32(int32_t op);
```

### Description

Broadcast a scalar value

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Set all lanes to the same value

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
  "op": {
    "register": "Sop|Wop"
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

When op is in range[1], this intrinsic can use:

```asm
DUP Zresult.S, #op
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/DUP--immediate---Broadcast-signed-immediate-to-vector-elements--unpredicated--

When op is an FP immediate[2], this intrinsic can use:

```asm
FDUP Zresult.S, #op
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FDUP--Broadcast-8-bit-floating-point-immediate-to-vector-elements--unpredicated--

When op is a logical immediate[3], this intrinsic can use:

```asm
DUPM Zresult.S, #op
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/DUPM--Broadcast-logical-bitmask-immediate-to-vector--unpredicated--

When op is in a GP register, the general implementation is:

```asm
DUP Zresult.S, Wop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/DUP--scalar---Broadcast-general-purpose-register-to-vector-elements--unpredicated--

When op is in an FP register, the general implementation is:

```asm
DUP Zresult.S, Zop.S[0]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/DUP--indexed---Broadcast-indexed-element-to-vector--unpredicated--

### Operation

Source operation ID: `SveOperation_svdup_n_s16`

**Operation**



Return a vector in which each element *i* contains `op`.



**[1]** This is true if the value is in the range [-128, 127] or is a multiple of 256 in the range [-32768, 32512]



**[2]** This is true if op is a floating-point immediate value expressable as ±n×2r, where n and r are integers such that 16 ≤ n ≤ 31 and -7 ≤ r ≤ 0.  In other words, this instruction requires op to have a normalized binary floating-point encoding with a sign bit, a 3-bit exponent, and a 4-bit fractional part.



**[3]** This is true if op is filled by some replicated bitmask *b* for which either all 0s in *b* are consecutive or all 1s in *b* are consecutive.

## svdup[_n]_s32_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdup%5B_n%5D_s32_m

### Signature (source notation)

```c
svint32_t svdup[_n]_s32_m(svint32_t inactive, svbool_t pg, int32_t op);
```

### Description

Broadcast a scalar value

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Set all lanes to the same value

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
  "inactive": {
    "register": "Ztied.S"
  },
  "pg": {
    "register": "Pg"
  },
  "op": {
    "register": "Sop|Wop"
  }
}
```

### Result mapping

```json
[
  {
    "Ztied.S": "result"
  }
]
```

### Instruction mapping

When op is in range[1], this intrinsic can use:

```asm
CPY Ztied.S, Pg/M, #op  // [3]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CPY--immediate--merging---Copy-signed-integer-immediate-to-vector-elements--merging--

When op is an FP immediate[2], this intrinsic can use:

```asm
FCPY Ztied.S, Pg/M, #op  // [3]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCPY--Copy-8-bit-floating-point-immediate-to-vector-elements--predicated--

When op is in a GP register, the general implementation is:

```asm
CPY Ztied.S, Pg/M, Wop  // [3]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CPY--scalar---Copy-general-purpose-register-to-vector-elements--predicated--

When op is in an FP register, the general implementation is:

```asm
CPY Ztied.S, Pg/M, Sop  // [3]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CPY--SIMD-FP-scalar---Copy-SIMD-FP-scalar-register-to-vector-elements--predicated--

### Operation

Source operation ID: `SveOperation_svdup_n_bf16_m`

**Operation**



Return a vector in which each active element *i* contains `op`. Take the inactive elements of the result from the corresponding elements of `inactive`.



**[1]** This is true if the value is in the range [-128, 127] or is a multiple of 256 in the range [-32768, 32512]



**[2]** This is true if op is a floating-point immediate value expressable as ±n×2r, where n and r are integers such that 16 ≤ n ≤ 31 and -7 ≤ r ≤ 0.  In other words, this instruction requires op to have a normalized binary floating-point encoding with a sign bit, a 3-bit exponent, and a 4-bit fractional part.



**[3]** If instead `result` is in a different register from the inputs, the compiler can add a preceding [MOVPRFX (unpredicated)](https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--) instruction

## svdup[_n]_s32_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdup%5B_n%5D_s32_x

### Signature (source notation)

```c
svint32_t svdup[_n]_s32_x(svbool_t pg, int32_t op);
```

### Description

Broadcast a scalar value

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Set all lanes to the same value

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
  "op": {
    "register": "Sop|Wop"
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

When op is in range[1], this intrinsic can use:

```asm
CPY Zresult.S, Pg/Z, #op
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CPY--immediate--merging---Copy-signed-integer-immediate-to-vector-elements--merging--

…or, alternatively:

```asm
DUP Zresult.S, #op
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/DUP--immediate---Broadcast-signed-immediate-to-vector-elements--unpredicated--

When op is an FP immediate[2], this intrinsic can use:

```asm
FCPY Zresult.S, Pg/M, #op
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCPY--Copy-8-bit-floating-point-immediate-to-vector-elements--predicated--

…or, alternatively:

```asm
FDUP Zresult.S, #op
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FDUP--Broadcast-8-bit-floating-point-immediate-to-vector-elements--unpredicated--

When op is a logical immediate[3], this intrinsic can use:

```asm
DUPM Zresult.S, #op
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/DUPM--Broadcast-logical-bitmask-immediate-to-vector--unpredicated--

When op is in a GP register, the general implementation is:

```asm
DUP Zresult.S, Wop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/DUP--scalar---Broadcast-general-purpose-register-to-vector-elements--unpredicated--

When op is in an FP register, the general implementation is:

```asm
DUP Zresult.S, Zop.S[0]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/DUP--indexed---Broadcast-indexed-element-to-vector--unpredicated--

### Operation

Source operation ID: `SveOperation_svdup_n_s16_x`

**Operation**



Return a vector in which each active element *i* contains `op`. The inactive elements of the result have arbitrary, undefined values.



**[1]** This is true if the value is in the range [-128, 127] or is a multiple of 256 in the range [-32768, 32512]



**[2]** This is true if op is a floating-point immediate value expressable as ±n×2r, where n and r are integers such that 16 ≤ n ≤ 31 and -7 ≤ r ≤ 0.  In other words, this instruction requires op to have a normalized binary floating-point encoding with a sign bit, a 3-bit exponent, and a 4-bit fractional part.



**[3]** This is true if op is filled by some replicated bitmask *b* for which either all 0s in *b* are consecutive or all 1s in *b* are consecutive.

## svdup[_n]_s32_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdup%5B_n%5D_s32_z

### Signature (source notation)

```c
svint32_t svdup[_n]_s32_z(svbool_t pg, int32_t op);
```

### Description

Broadcast a scalar value

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Set all lanes to the same value

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
  "op": {
    "register": "Sop|Wop"
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

When op is in range[1], this intrinsic can use:

```asm
CPY Zresult.S, Pg/Z, #op
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CPY--immediate--merging---Copy-signed-integer-immediate-to-vector-elements--merging--

When op is an FP immediate[2], this intrinsic can use:

```asm
DUP Zresult.S, #0
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/DUP--immediate---Broadcast-signed-immediate-to-vector-elements--unpredicated--

```asm
FCPY Zresult.S, Pg/M, #op
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCPY--Copy-8-bit-floating-point-immediate-to-vector-elements--predicated--

When op is in a GP register, the general implementation is:

```asm
DUP Zresult.S, #0
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/DUP--immediate---Broadcast-signed-immediate-to-vector-elements--unpredicated--

```asm
CPY Zresult.S, Pg/M, Wop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CPY--scalar---Copy-general-purpose-register-to-vector-elements--predicated--

When op is in an FP register and result is in a different register from op, this intrinsic can use:

```asm
MOVPRFX Zresult.S, Pg/Z, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
CPY Zresult.S, Pg/M, Sop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CPY--SIMD-FP-scalar---Copy-SIMD-FP-scalar-register-to-vector-elements--predicated--

### Operation

Source operation ID: `SveOperation_svdup_n_bf16_z`

**Operation**



Return a vector in which each active element *i* contains `op`. Set the inactive elements of the result to zero.



**[1]** This is true if the value is in the range [-128, 127] or is a multiple of 256 in the range [-32768, 32512]



**[2]** This is true if op is a floating-point immediate value expressable as ±n×2r, where n and r are integers such that 16 ≤ n ≤ 31 and -7 ≤ r ≤ 0.  In other words, this instruction requires op to have a normalized binary floating-point encoding with a sign bit, a 3-bit exponent, and a 4-bit fractional part.

## svdup[_n]_s64

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdup%5B_n%5D_s64

### Signature (source notation)

```c
svint64_t svdup[_n]_s64(int64_t op);
```

### Description

Broadcast a scalar value

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Set all lanes to the same value

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
  "op": {
    "register": "Dop|Xop"
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

When op is in range[1], this intrinsic can use:

```asm
DUP Zresult.D, #op
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/DUP--immediate---Broadcast-signed-immediate-to-vector-elements--unpredicated--

When op is an FP immediate[2], this intrinsic can use:

```asm
FDUP Zresult.D, #op
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FDUP--Broadcast-8-bit-floating-point-immediate-to-vector-elements--unpredicated--

When op is a logical immediate[3], this intrinsic can use:

```asm
DUPM Zresult.D, #op
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/DUPM--Broadcast-logical-bitmask-immediate-to-vector--unpredicated--

When op is in a GP register, the general implementation is:

```asm
DUP Zresult.D, Xop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/DUP--scalar---Broadcast-general-purpose-register-to-vector-elements--unpredicated--

When op is in an FP register, the general implementation is:

```asm
DUP Zresult.D, Zop.D[0]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/DUP--indexed---Broadcast-indexed-element-to-vector--unpredicated--

### Operation

Source operation ID: `SveOperation_svdup_n_s16`

**Operation**



Return a vector in which each element *i* contains `op`.



**[1]** This is true if the value is in the range [-128, 127] or is a multiple of 256 in the range [-32768, 32512]



**[2]** This is true if op is a floating-point immediate value expressable as ±n×2r, where n and r are integers such that 16 ≤ n ≤ 31 and -7 ≤ r ≤ 0.  In other words, this instruction requires op to have a normalized binary floating-point encoding with a sign bit, a 3-bit exponent, and a 4-bit fractional part.



**[3]** This is true if op is filled by some replicated bitmask *b* for which either all 0s in *b* are consecutive or all 1s in *b* are consecutive.

## svdup[_n]_s64_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdup%5B_n%5D_s64_m

### Signature (source notation)

```c
svint64_t svdup[_n]_s64_m(svint64_t inactive, svbool_t pg, int64_t op);
```

### Description

Broadcast a scalar value

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Set all lanes to the same value

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
  "inactive": {
    "register": "Ztied.D"
  },
  "pg": {
    "register": "Pg"
  },
  "op": {
    "register": "Dop|Xop"
  }
}
```

### Result mapping

```json
[
  {
    "Ztied.D": "result"
  }
]
```

### Instruction mapping

When op is in range[1], this intrinsic can use:

```asm
CPY Ztied.D, Pg/M, #op  // [3]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CPY--immediate--merging---Copy-signed-integer-immediate-to-vector-elements--merging--

When op is an FP immediate[2], this intrinsic can use:

```asm
FCPY Ztied.D, Pg/M, #op  // [3]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCPY--Copy-8-bit-floating-point-immediate-to-vector-elements--predicated--

When op is in a GP register, the general implementation is:

```asm
CPY Ztied.D, Pg/M, Xop  // [3]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CPY--scalar---Copy-general-purpose-register-to-vector-elements--predicated--

When op is in an FP register, the general implementation is:

```asm
CPY Ztied.D, Pg/M, Dop  // [3]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CPY--SIMD-FP-scalar---Copy-SIMD-FP-scalar-register-to-vector-elements--predicated--

### Operation

Source operation ID: `SveOperation_svdup_n_bf16_m`

**Operation**



Return a vector in which each active element *i* contains `op`. Take the inactive elements of the result from the corresponding elements of `inactive`.



**[1]** This is true if the value is in the range [-128, 127] or is a multiple of 256 in the range [-32768, 32512]



**[2]** This is true if op is a floating-point immediate value expressable as ±n×2r, where n and r are integers such that 16 ≤ n ≤ 31 and -7 ≤ r ≤ 0.  In other words, this instruction requires op to have a normalized binary floating-point encoding with a sign bit, a 3-bit exponent, and a 4-bit fractional part.



**[3]** If instead `result` is in a different register from the inputs, the compiler can add a preceding [MOVPRFX (unpredicated)](https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--) instruction

## svdup[_n]_s64_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdup%5B_n%5D_s64_x

### Signature (source notation)

```c
svint64_t svdup[_n]_s64_x(svbool_t pg, int64_t op);
```

### Description

Broadcast a scalar value

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Set all lanes to the same value

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
  "op": {
    "register": "Dop|Xop"
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

When op is in range[1], this intrinsic can use:

```asm
CPY Zresult.D, Pg/Z, #op
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CPY--immediate--merging---Copy-signed-integer-immediate-to-vector-elements--merging--

…or, alternatively:

```asm
DUP Zresult.D, #op
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/DUP--immediate---Broadcast-signed-immediate-to-vector-elements--unpredicated--

When op is an FP immediate[2], this intrinsic can use:

```asm
FCPY Zresult.D, Pg/M, #op
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCPY--Copy-8-bit-floating-point-immediate-to-vector-elements--predicated--

…or, alternatively:

```asm
FDUP Zresult.D, #op
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FDUP--Broadcast-8-bit-floating-point-immediate-to-vector-elements--unpredicated--

When op is a logical immediate[3], this intrinsic can use:

```asm
DUPM Zresult.D, #op
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/DUPM--Broadcast-logical-bitmask-immediate-to-vector--unpredicated--

When op is in a GP register, the general implementation is:

```asm
DUP Zresult.D, Xop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/DUP--scalar---Broadcast-general-purpose-register-to-vector-elements--unpredicated--

When op is in an FP register, the general implementation is:

```asm
DUP Zresult.D, Zop.D[0]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/DUP--indexed---Broadcast-indexed-element-to-vector--unpredicated--

### Operation

Source operation ID: `SveOperation_svdup_n_s16_x`

**Operation**



Return a vector in which each active element *i* contains `op`. The inactive elements of the result have arbitrary, undefined values.



**[1]** This is true if the value is in the range [-128, 127] or is a multiple of 256 in the range [-32768, 32512]



**[2]** This is true if op is a floating-point immediate value expressable as ±n×2r, where n and r are integers such that 16 ≤ n ≤ 31 and -7 ≤ r ≤ 0.  In other words, this instruction requires op to have a normalized binary floating-point encoding with a sign bit, a 3-bit exponent, and a 4-bit fractional part.



**[3]** This is true if op is filled by some replicated bitmask *b* for which either all 0s in *b* are consecutive or all 1s in *b* are consecutive.

## svdup[_n]_s64_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdup%5B_n%5D_s64_z

### Signature (source notation)

```c
svint64_t svdup[_n]_s64_z(svbool_t pg, int64_t op);
```

### Description

Broadcast a scalar value

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Set all lanes to the same value

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
  "op": {
    "register": "Dop|Xop"
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

When op is in range[1], this intrinsic can use:

```asm
CPY Zresult.D, Pg/Z, #op
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CPY--immediate--merging---Copy-signed-integer-immediate-to-vector-elements--merging--

When op is an FP immediate[2], this intrinsic can use:

```asm
DUP Zresult.D, #0
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/DUP--immediate---Broadcast-signed-immediate-to-vector-elements--unpredicated--

```asm
FCPY Zresult.D, Pg/M, #op
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCPY--Copy-8-bit-floating-point-immediate-to-vector-elements--predicated--

When op is in a GP register, the general implementation is:

```asm
DUP Zresult.D, #0
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/DUP--immediate---Broadcast-signed-immediate-to-vector-elements--unpredicated--

```asm
CPY Zresult.D, Pg/M, Xop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CPY--scalar---Copy-general-purpose-register-to-vector-elements--predicated--

When op is in an FP register and result is in a different register from op, this intrinsic can use:

```asm
MOVPRFX Zresult.D, Pg/Z, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
CPY Zresult.D, Pg/M, Dop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CPY--SIMD-FP-scalar---Copy-SIMD-FP-scalar-register-to-vector-elements--predicated--

### Operation

Source operation ID: `SveOperation_svdup_n_bf16_z`

**Operation**



Return a vector in which each active element *i* contains `op`. Set the inactive elements of the result to zero.



**[1]** This is true if the value is in the range [-128, 127] or is a multiple of 256 in the range [-32768, 32512]



**[2]** This is true if op is a floating-point immediate value expressable as ±n×2r, where n and r are integers such that 16 ≤ n ≤ 31 and -7 ≤ r ≤ 0.  In other words, this instruction requires op to have a normalized binary floating-point encoding with a sign bit, a 3-bit exponent, and a 4-bit fractional part.

## svdup[_n]_s8

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdup%5B_n%5D_s8

### Signature (source notation)

```c
svint8_t svdup[_n]_s8(int8_t op);
```

### Description

Broadcast a scalar value

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Set all lanes to the same value

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
  "op": {
    "register": "Bop|Wop"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.B": "result"
  }
]
```

### Instruction mapping

When op is constant, this intrinsic can use:

```asm
DUP Zresult.B, #op
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/DUP--immediate---Broadcast-signed-immediate-to-vector-elements--unpredicated--

When op is an FP immediate[1], this intrinsic can use:

```asm
FDUP Zresult.B, #op
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FDUP--Broadcast-8-bit-floating-point-immediate-to-vector-elements--unpredicated--

When op is a logical immediate[2], this intrinsic can use:

```asm
DUPM Zresult.B, #op
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/DUPM--Broadcast-logical-bitmask-immediate-to-vector--unpredicated--

When op is in a GP register, the general implementation is:

```asm
DUP Zresult.B, Wop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/DUP--scalar---Broadcast-general-purpose-register-to-vector-elements--unpredicated--

When op is in an FP register, the general implementation is:

```asm
DUP Zresult.B, Zop.B[0]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/DUP--indexed---Broadcast-indexed-element-to-vector--unpredicated--

### Operation

Source operation ID: `SveOperation_svdup_n_s8`

**Operation**



Return a vector in which each element *i* contains `op`.



**[1]** This is true if op is a floating-point immediate value expressable as ±n×2r, where n and r are integers such that 16 ≤ n ≤ 31 and -7 ≤ r ≤ 0.  In other words, this instruction requires op to have a normalized binary floating-point encoding with a sign bit, a 3-bit exponent, and a 4-bit fractional part.



**[2]** This is true if op is filled by some replicated bitmask *b* for which either all 0s in *b* are consecutive or all 1s in *b* are consecutive.

## svdup[_n]_s8_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdup%5B_n%5D_s8_m

### Signature (source notation)

```c
svint8_t svdup[_n]_s8_m(svint8_t inactive, svbool_t pg, int8_t op);
```

### Description

Broadcast a scalar value

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Set all lanes to the same value

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
  "inactive": {
    "register": "Ztied.B"
  },
  "pg": {
    "register": "Pg"
  },
  "op": {
    "register": "Bop|Wop"
  }
}
```

### Result mapping

```json
[
  {
    "Ztied.B": "result"
  }
]
```

### Instruction mapping

When op is constant, this intrinsic can use:

```asm
CPY Ztied.B, Pg/M, #op  // [2]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CPY--immediate--merging---Copy-signed-integer-immediate-to-vector-elements--merging--

When op is an FP immediate[1], this intrinsic can use:

```asm
FCPY Ztied.B, Pg/M, #op  // [2]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCPY--Copy-8-bit-floating-point-immediate-to-vector-elements--predicated--

When op is in a GP register, the general implementation is:

```asm
CPY Ztied.B, Pg/M, Wop  // [2]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CPY--scalar---Copy-general-purpose-register-to-vector-elements--predicated--

When op is in an FP register, the general implementation is:

```asm
CPY Ztied.B, Pg/M, Bop  // [2]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CPY--SIMD-FP-scalar---Copy-SIMD-FP-scalar-register-to-vector-elements--predicated--

### Operation

Source operation ID: `SveOperation_svdup_n_s8_m`

**Operation**



Return a vector in which each active element *i* contains `op`. Take the inactive elements of the result from the corresponding elements of `inactive`.



**[1]** This is true if op is a floating-point immediate value expressable as ±n×2r, where n and r are integers such that 16 ≤ n ≤ 31 and -7 ≤ r ≤ 0.  In other words, this instruction requires op to have a normalized binary floating-point encoding with a sign bit, a 3-bit exponent, and a 4-bit fractional part.



**[2]** If instead `result` is in a different register from the inputs, the compiler can add a preceding [MOVPRFX (unpredicated)](https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--) instruction

## svdup[_n]_s8_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdup%5B_n%5D_s8_x

### Signature (source notation)

```c
svint8_t svdup[_n]_s8_x(svbool_t pg, int8_t op);
```

### Description

Broadcast a scalar value

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Set all lanes to the same value

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
  "op": {
    "register": "Bop|Wop"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.B": "result"
  }
]
```

### Instruction mapping

When op is constant, this intrinsic can use:

```asm
CPY Zresult.B, Pg/Z, #op
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CPY--immediate--merging---Copy-signed-integer-immediate-to-vector-elements--merging--

…or, alternatively:

```asm
DUP Zresult.B, #op
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/DUP--immediate---Broadcast-signed-immediate-to-vector-elements--unpredicated--

When op is an FP immediate[1], this intrinsic can use:

```asm
FCPY Zresult.B, Pg/M, #op
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCPY--Copy-8-bit-floating-point-immediate-to-vector-elements--predicated--

…or, alternatively:

```asm
FDUP Zresult.B, #op
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FDUP--Broadcast-8-bit-floating-point-immediate-to-vector-elements--unpredicated--

When op is a logical immediate[2], this intrinsic can use:

```asm
DUPM Zresult.B, #op
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/DUPM--Broadcast-logical-bitmask-immediate-to-vector--unpredicated--

When op is in a GP register, the general implementation is:

```asm
DUP Zresult.B, Wop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/DUP--scalar---Broadcast-general-purpose-register-to-vector-elements--unpredicated--

When op is in an FP register, the general implementation is:

```asm
DUP Zresult.B, Zop.B[0]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/DUP--indexed---Broadcast-indexed-element-to-vector--unpredicated--

### Operation

Source operation ID: `SveOperation_svdup_n_s8_x`

**Operation**



Return a vector in which each active element *i* contains `op`. The inactive elements of the result have arbitrary, undefined values.



**[1]** This is true if op is a floating-point immediate value expressable as ±n×2r, where n and r are integers such that 16 ≤ n ≤ 31 and -7 ≤ r ≤ 0.  In other words, this instruction requires op to have a normalized binary floating-point encoding with a sign bit, a 3-bit exponent, and a 4-bit fractional part.



**[2]** This is true if op is filled by some replicated bitmask *b* for which either all 0s in *b* are consecutive or all 1s in *b* are consecutive.

## svdup[_n]_s8_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdup%5B_n%5D_s8_z

### Signature (source notation)

```c
svint8_t svdup[_n]_s8_z(svbool_t pg, int8_t op);
```

### Description

Broadcast a scalar value

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Set all lanes to the same value

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
  "op": {
    "register": "Bop|Wop"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.B": "result"
  }
]
```

### Instruction mapping

When op is constant, this intrinsic can use:

```asm
CPY Zresult.B, Pg/Z, #op
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CPY--immediate--merging---Copy-signed-integer-immediate-to-vector-elements--merging--

When op is an FP immediate[1], this intrinsic can use:

```asm
DUP Zresult.B, #0
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/DUP--immediate---Broadcast-signed-immediate-to-vector-elements--unpredicated--

```asm
FCPY Zresult.B, Pg/M, #op
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCPY--Copy-8-bit-floating-point-immediate-to-vector-elements--predicated--

When op is in a GP register, the general implementation is:

```asm
DUP Zresult.B, #0
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/DUP--immediate---Broadcast-signed-immediate-to-vector-elements--unpredicated--

```asm
CPY Zresult.B, Pg/M, Wop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CPY--scalar---Copy-general-purpose-register-to-vector-elements--predicated--

When op is in an FP register and result is in a different register from op, this intrinsic can use:

```asm
MOVPRFX Zresult.B, Pg/Z, Zop.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
CPY Zresult.B, Pg/M, Bop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CPY--SIMD-FP-scalar---Copy-SIMD-FP-scalar-register-to-vector-elements--predicated--

### Operation

Source operation ID: `SveOperation_svdup_n_s8_z`

**Operation**



Return a vector in which each active element *i* contains `op`. Set the inactive elements of the result to zero.



**[1]** This is true if op is a floating-point immediate value expressable as ±n×2r, where n and r are integers such that 16 ≤ n ≤ 31 and -7 ≤ r ≤ 0.  In other words, this instruction requires op to have a normalized binary floating-point encoding with a sign bit, a 3-bit exponent, and a 4-bit fractional part.

## svdup[_n]_u16

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdup%5B_n%5D_u16

### Signature (source notation)

```c
svuint16_t svdup[_n]_u16(uint16_t op);
```

### Description

Broadcast a scalar value

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Set all lanes to the same value

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
  "op": {
    "register": "Hop|Wop"
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

When (int16_t)op is in range[1], this intrinsic can use:

```asm
DUP Zresult.H, #op
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/DUP--immediate---Broadcast-signed-immediate-to-vector-elements--unpredicated--

When op is an FP immediate[2], this intrinsic can use:

```asm
FDUP Zresult.H, #op
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FDUP--Broadcast-8-bit-floating-point-immediate-to-vector-elements--unpredicated--

When op is a logical immediate[3], this intrinsic can use:

```asm
DUPM Zresult.H, #op
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/DUPM--Broadcast-logical-bitmask-immediate-to-vector--unpredicated--

When op is in a GP register, the general implementation is:

```asm
DUP Zresult.H, Wop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/DUP--scalar---Broadcast-general-purpose-register-to-vector-elements--unpredicated--

When op is in an FP register, the general implementation is:

```asm
DUP Zresult.H, Zop.H[0]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/DUP--indexed---Broadcast-indexed-element-to-vector--unpredicated--

### Operation

Source operation ID: `SveOperation_svdup_n_s16`

**Operation**



Return a vector in which each element *i* contains `op`.



**[1]** This is true if the value is in the range [-128, 127] or is a multiple of 256 in the range [-32768, 32512]



**[2]** This is true if op is a floating-point immediate value expressable as ±n×2r, where n and r are integers such that 16 ≤ n ≤ 31 and -7 ≤ r ≤ 0.  In other words, this instruction requires op to have a normalized binary floating-point encoding with a sign bit, a 3-bit exponent, and a 4-bit fractional part.



**[3]** This is true if op is filled by some replicated bitmask *b* for which either all 0s in *b* are consecutive or all 1s in *b* are consecutive.

## svdup[_n]_u16_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdup%5B_n%5D_u16_m

### Signature (source notation)

```c
svuint16_t svdup[_n]_u16_m(svuint16_t inactive, svbool_t pg, uint16_t op);
```

### Description

Broadcast a scalar value

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Set all lanes to the same value

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
  "inactive": {
    "register": "Ztied.H"
  },
  "pg": {
    "register": "Pg"
  },
  "op": {
    "register": "Hop|Wop"
  }
}
```

### Result mapping

```json
[
  {
    "Ztied.H": "result"
  }
]
```

### Instruction mapping

When (int16_t)op is in range[1], this intrinsic can use:

```asm
CPY Ztied.H, Pg/M, #(int16_t)op  // [3]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CPY--immediate--merging---Copy-signed-integer-immediate-to-vector-elements--merging--

When op is an FP immediate[2], this intrinsic can use:

```asm
FCPY Ztied.H, Pg/M, #op  // [3]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCPY--Copy-8-bit-floating-point-immediate-to-vector-elements--predicated--

When op is in a GP register, the general implementation is:

```asm
CPY Ztied.H, Pg/M, Wop  // [3]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CPY--scalar---Copy-general-purpose-register-to-vector-elements--predicated--

When op is in an FP register, the general implementation is:

```asm
CPY Ztied.H, Pg/M, Hop  // [3]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CPY--SIMD-FP-scalar---Copy-SIMD-FP-scalar-register-to-vector-elements--predicated--

### Operation

Source operation ID: `SveOperation_svdup_n_bf16_m`

**Operation**



Return a vector in which each active element *i* contains `op`. Take the inactive elements of the result from the corresponding elements of `inactive`.



**[1]** This is true if the value is in the range [-128, 127] or is a multiple of 256 in the range [-32768, 32512]



**[2]** This is true if op is a floating-point immediate value expressable as ±n×2r, where n and r are integers such that 16 ≤ n ≤ 31 and -7 ≤ r ≤ 0.  In other words, this instruction requires op to have a normalized binary floating-point encoding with a sign bit, a 3-bit exponent, and a 4-bit fractional part.



**[3]** If instead `result` is in a different register from the inputs, the compiler can add a preceding [MOVPRFX (unpredicated)](https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--) instruction

## svdup[_n]_u16_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdup%5B_n%5D_u16_x

### Signature (source notation)

```c
svuint16_t svdup[_n]_u16_x(svbool_t pg, uint16_t op);
```

### Description

Broadcast a scalar value

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Set all lanes to the same value

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
  "op": {
    "register": "Hop|Wop"
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

When (int16_t)op is in range[1], this intrinsic can use:

```asm
CPY Zresult.H, Pg/Z, #(int16_t)op
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CPY--immediate--merging---Copy-signed-integer-immediate-to-vector-elements--merging--

…or, alternatively:

```asm
DUP Zresult.H, #op
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/DUP--immediate---Broadcast-signed-immediate-to-vector-elements--unpredicated--

When op is an FP immediate[2], this intrinsic can use:

```asm
FCPY Zresult.H, Pg/M, #op
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCPY--Copy-8-bit-floating-point-immediate-to-vector-elements--predicated--

…or, alternatively:

```asm
FDUP Zresult.H, #op
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FDUP--Broadcast-8-bit-floating-point-immediate-to-vector-elements--unpredicated--

When op is a logical immediate[3], this intrinsic can use:

```asm
DUPM Zresult.H, #op
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/DUPM--Broadcast-logical-bitmask-immediate-to-vector--unpredicated--

When op is in a GP register, the general implementation is:

```asm
DUP Zresult.H, Wop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/DUP--scalar---Broadcast-general-purpose-register-to-vector-elements--unpredicated--

When op is in an FP register, the general implementation is:

```asm
DUP Zresult.H, Zop.H[0]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/DUP--indexed---Broadcast-indexed-element-to-vector--unpredicated--

### Operation

Source operation ID: `SveOperation_svdup_n_s16_x`

**Operation**



Return a vector in which each active element *i* contains `op`. The inactive elements of the result have arbitrary, undefined values.



**[1]** This is true if the value is in the range [-128, 127] or is a multiple of 256 in the range [-32768, 32512]



**[2]** This is true if op is a floating-point immediate value expressable as ±n×2r, where n and r are integers such that 16 ≤ n ≤ 31 and -7 ≤ r ≤ 0.  In other words, this instruction requires op to have a normalized binary floating-point encoding with a sign bit, a 3-bit exponent, and a 4-bit fractional part.



**[3]** This is true if op is filled by some replicated bitmask *b* for which either all 0s in *b* are consecutive or all 1s in *b* are consecutive.

## svdup[_n]_u16_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdup%5B_n%5D_u16_z

### Signature (source notation)

```c
svuint16_t svdup[_n]_u16_z(svbool_t pg, uint16_t op);
```

### Description

Broadcast a scalar value

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Set all lanes to the same value

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
  "op": {
    "register": "Hop|Wop"
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

When (int16_t)op is in range[1], this intrinsic can use:

```asm
CPY Zresult.H, Pg/Z, #(int16_t)op
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CPY--immediate--merging---Copy-signed-integer-immediate-to-vector-elements--merging--

When op is an FP immediate[2], this intrinsic can use:

```asm
DUP Zresult.H, #0
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/DUP--immediate---Broadcast-signed-immediate-to-vector-elements--unpredicated--

```asm
FCPY Zresult.H, Pg/M, #op
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCPY--Copy-8-bit-floating-point-immediate-to-vector-elements--predicated--

When op is in a GP register, the general implementation is:

```asm
DUP Zresult.H, #0
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/DUP--immediate---Broadcast-signed-immediate-to-vector-elements--unpredicated--

```asm
CPY Zresult.H, Pg/M, Wop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CPY--scalar---Copy-general-purpose-register-to-vector-elements--predicated--

When op is in an FP register and result is in a different register from op, this intrinsic can use:

```asm
MOVPRFX Zresult.H, Pg/Z, Zop.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
CPY Zresult.H, Pg/M, Hop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CPY--SIMD-FP-scalar---Copy-SIMD-FP-scalar-register-to-vector-elements--predicated--

### Operation

Source operation ID: `SveOperation_svdup_n_bf16_z`

**Operation**



Return a vector in which each active element *i* contains `op`. Set the inactive elements of the result to zero.



**[1]** This is true if the value is in the range [-128, 127] or is a multiple of 256 in the range [-32768, 32512]



**[2]** This is true if op is a floating-point immediate value expressable as ±n×2r, where n and r are integers such that 16 ≤ n ≤ 31 and -7 ≤ r ≤ 0.  In other words, this instruction requires op to have a normalized binary floating-point encoding with a sign bit, a 3-bit exponent, and a 4-bit fractional part.

## svdup[_n]_u32

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdup%5B_n%5D_u32

### Signature (source notation)

```c
svuint32_t svdup[_n]_u32(uint32_t op);
```

### Description

Broadcast a scalar value

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Set all lanes to the same value

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
  "op": {
    "register": "Sop|Wop"
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

When (int32_t)op is in range[1], this intrinsic can use:

```asm
DUP Zresult.S, #op
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/DUP--immediate---Broadcast-signed-immediate-to-vector-elements--unpredicated--

When op is an FP immediate[2], this intrinsic can use:

```asm
FDUP Zresult.S, #op
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FDUP--Broadcast-8-bit-floating-point-immediate-to-vector-elements--unpredicated--

When op is a logical immediate[3], this intrinsic can use:

```asm
DUPM Zresult.S, #op
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/DUPM--Broadcast-logical-bitmask-immediate-to-vector--unpredicated--

When op is in a GP register, the general implementation is:

```asm
DUP Zresult.S, Wop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/DUP--scalar---Broadcast-general-purpose-register-to-vector-elements--unpredicated--

When op is in an FP register, the general implementation is:

```asm
DUP Zresult.S, Zop.S[0]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/DUP--indexed---Broadcast-indexed-element-to-vector--unpredicated--

### Operation

Source operation ID: `SveOperation_svdup_n_s16`

**Operation**



Return a vector in which each element *i* contains `op`.



**[1]** This is true if the value is in the range [-128, 127] or is a multiple of 256 in the range [-32768, 32512]



**[2]** This is true if op is a floating-point immediate value expressable as ±n×2r, where n and r are integers such that 16 ≤ n ≤ 31 and -7 ≤ r ≤ 0.  In other words, this instruction requires op to have a normalized binary floating-point encoding with a sign bit, a 3-bit exponent, and a 4-bit fractional part.



**[3]** This is true if op is filled by some replicated bitmask *b* for which either all 0s in *b* are consecutive or all 1s in *b* are consecutive.

## svdup[_n]_u32_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdup%5B_n%5D_u32_m

### Signature (source notation)

```c
svuint32_t svdup[_n]_u32_m(svuint32_t inactive, svbool_t pg, uint32_t op);
```

### Description

Broadcast a scalar value

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Set all lanes to the same value

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
  "inactive": {
    "register": "Ztied.S"
  },
  "pg": {
    "register": "Pg"
  },
  "op": {
    "register": "Sop|Wop"
  }
}
```

### Result mapping

```json
[
  {
    "Ztied.S": "result"
  }
]
```

### Instruction mapping

When (int32_t)op is in range[1], this intrinsic can use:

```asm
CPY Ztied.S, Pg/M, #(int32_t)op  // [3]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CPY--immediate--merging---Copy-signed-integer-immediate-to-vector-elements--merging--

When op is an FP immediate[2], this intrinsic can use:

```asm
FCPY Ztied.S, Pg/M, #op  // [3]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCPY--Copy-8-bit-floating-point-immediate-to-vector-elements--predicated--

When op is in a GP register, the general implementation is:

```asm
CPY Ztied.S, Pg/M, Wop  // [3]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CPY--scalar---Copy-general-purpose-register-to-vector-elements--predicated--

When op is in an FP register, the general implementation is:

```asm
CPY Ztied.S, Pg/M, Sop  // [3]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CPY--SIMD-FP-scalar---Copy-SIMD-FP-scalar-register-to-vector-elements--predicated--

### Operation

Source operation ID: `SveOperation_svdup_n_bf16_m`

**Operation**



Return a vector in which each active element *i* contains `op`. Take the inactive elements of the result from the corresponding elements of `inactive`.



**[1]** This is true if the value is in the range [-128, 127] or is a multiple of 256 in the range [-32768, 32512]



**[2]** This is true if op is a floating-point immediate value expressable as ±n×2r, where n and r are integers such that 16 ≤ n ≤ 31 and -7 ≤ r ≤ 0.  In other words, this instruction requires op to have a normalized binary floating-point encoding with a sign bit, a 3-bit exponent, and a 4-bit fractional part.



**[3]** If instead `result` is in a different register from the inputs, the compiler can add a preceding [MOVPRFX (unpredicated)](https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--) instruction

## svdup[_n]_u32_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdup%5B_n%5D_u32_x

### Signature (source notation)

```c
svuint32_t svdup[_n]_u32_x(svbool_t pg, uint32_t op);
```

### Description

Broadcast a scalar value

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Set all lanes to the same value

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
  "op": {
    "register": "Sop|Wop"
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

When (int32_t)op is in range[1], this intrinsic can use:

```asm
CPY Zresult.S, Pg/Z, #(int32_t)op
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CPY--immediate--merging---Copy-signed-integer-immediate-to-vector-elements--merging--

…or, alternatively:

```asm
DUP Zresult.S, #op
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/DUP--immediate---Broadcast-signed-immediate-to-vector-elements--unpredicated--

When op is an FP immediate[2], this intrinsic can use:

```asm
FCPY Zresult.S, Pg/M, #op
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCPY--Copy-8-bit-floating-point-immediate-to-vector-elements--predicated--

…or, alternatively:

```asm
FDUP Zresult.S, #op
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FDUP--Broadcast-8-bit-floating-point-immediate-to-vector-elements--unpredicated--

When op is a logical immediate[3], this intrinsic can use:

```asm
DUPM Zresult.S, #op
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/DUPM--Broadcast-logical-bitmask-immediate-to-vector--unpredicated--

When op is in a GP register, the general implementation is:

```asm
DUP Zresult.S, Wop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/DUP--scalar---Broadcast-general-purpose-register-to-vector-elements--unpredicated--

When op is in an FP register, the general implementation is:

```asm
DUP Zresult.S, Zop.S[0]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/DUP--indexed---Broadcast-indexed-element-to-vector--unpredicated--

### Operation

Source operation ID: `SveOperation_svdup_n_s16_x`

**Operation**



Return a vector in which each active element *i* contains `op`. The inactive elements of the result have arbitrary, undefined values.



**[1]** This is true if the value is in the range [-128, 127] or is a multiple of 256 in the range [-32768, 32512]



**[2]** This is true if op is a floating-point immediate value expressable as ±n×2r, where n and r are integers such that 16 ≤ n ≤ 31 and -7 ≤ r ≤ 0.  In other words, this instruction requires op to have a normalized binary floating-point encoding with a sign bit, a 3-bit exponent, and a 4-bit fractional part.



**[3]** This is true if op is filled by some replicated bitmask *b* for which either all 0s in *b* are consecutive or all 1s in *b* are consecutive.

## svdup[_n]_u32_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdup%5B_n%5D_u32_z

### Signature (source notation)

```c
svuint32_t svdup[_n]_u32_z(svbool_t pg, uint32_t op);
```

### Description

Broadcast a scalar value

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Set all lanes to the same value

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
  "op": {
    "register": "Sop|Wop"
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

When (int32_t)op is in range[1], this intrinsic can use:

```asm
CPY Zresult.S, Pg/Z, #(int32_t)op
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CPY--immediate--merging---Copy-signed-integer-immediate-to-vector-elements--merging--

When op is an FP immediate[2], this intrinsic can use:

```asm
DUP Zresult.S, #0
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/DUP--immediate---Broadcast-signed-immediate-to-vector-elements--unpredicated--

```asm
FCPY Zresult.S, Pg/M, #op
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCPY--Copy-8-bit-floating-point-immediate-to-vector-elements--predicated--

When op is in a GP register, the general implementation is:

```asm
DUP Zresult.S, #0
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/DUP--immediate---Broadcast-signed-immediate-to-vector-elements--unpredicated--

```asm
CPY Zresult.S, Pg/M, Wop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CPY--scalar---Copy-general-purpose-register-to-vector-elements--predicated--

When op is in an FP register and result is in a different register from op, this intrinsic can use:

```asm
MOVPRFX Zresult.S, Pg/Z, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
CPY Zresult.S, Pg/M, Sop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CPY--SIMD-FP-scalar---Copy-SIMD-FP-scalar-register-to-vector-elements--predicated--

### Operation

Source operation ID: `SveOperation_svdup_n_bf16_z`

**Operation**



Return a vector in which each active element *i* contains `op`. Set the inactive elements of the result to zero.



**[1]** This is true if the value is in the range [-128, 127] or is a multiple of 256 in the range [-32768, 32512]



**[2]** This is true if op is a floating-point immediate value expressable as ±n×2r, where n and r are integers such that 16 ≤ n ≤ 31 and -7 ≤ r ≤ 0.  In other words, this instruction requires op to have a normalized binary floating-point encoding with a sign bit, a 3-bit exponent, and a 4-bit fractional part.

## svdup[_n]_u64

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdup%5B_n%5D_u64

### Signature (source notation)

```c
svuint64_t svdup[_n]_u64(uint64_t op);
```

### Description

Broadcast a scalar value

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Set all lanes to the same value

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
  "op": {
    "register": "Dop|Xop"
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

When (int64_t)op is in range[1], this intrinsic can use:

```asm
DUP Zresult.D, #op
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/DUP--immediate---Broadcast-signed-immediate-to-vector-elements--unpredicated--

When op is an FP immediate[2], this intrinsic can use:

```asm
FDUP Zresult.D, #op
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FDUP--Broadcast-8-bit-floating-point-immediate-to-vector-elements--unpredicated--

When op is a logical immediate[3], this intrinsic can use:

```asm
DUPM Zresult.D, #op
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/DUPM--Broadcast-logical-bitmask-immediate-to-vector--unpredicated--

When op is in a GP register, the general implementation is:

```asm
DUP Zresult.D, Xop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/DUP--scalar---Broadcast-general-purpose-register-to-vector-elements--unpredicated--

When op is in an FP register, the general implementation is:

```asm
DUP Zresult.D, Zop.D[0]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/DUP--indexed---Broadcast-indexed-element-to-vector--unpredicated--

### Operation

Source operation ID: `SveOperation_svdup_n_s16`

**Operation**



Return a vector in which each element *i* contains `op`.



**[1]** This is true if the value is in the range [-128, 127] or is a multiple of 256 in the range [-32768, 32512]



**[2]** This is true if op is a floating-point immediate value expressable as ±n×2r, where n and r are integers such that 16 ≤ n ≤ 31 and -7 ≤ r ≤ 0.  In other words, this instruction requires op to have a normalized binary floating-point encoding with a sign bit, a 3-bit exponent, and a 4-bit fractional part.



**[3]** This is true if op is filled by some replicated bitmask *b* for which either all 0s in *b* are consecutive or all 1s in *b* are consecutive.

## svdup[_n]_u64_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdup%5B_n%5D_u64_m

### Signature (source notation)

```c
svuint64_t svdup[_n]_u64_m(svuint64_t inactive, svbool_t pg, uint64_t op);
```

### Description

Broadcast a scalar value

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Set all lanes to the same value

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
  "inactive": {
    "register": "Ztied.D"
  },
  "pg": {
    "register": "Pg"
  },
  "op": {
    "register": "Dop|Xop"
  }
}
```

### Result mapping

```json
[
  {
    "Ztied.D": "result"
  }
]
```

### Instruction mapping

When (int64_t)op is in range[1], this intrinsic can use:

```asm
CPY Ztied.D, Pg/M, #(int64_t)op  // [3]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CPY--immediate--merging---Copy-signed-integer-immediate-to-vector-elements--merging--

When op is an FP immediate[2], this intrinsic can use:

```asm
FCPY Ztied.D, Pg/M, #op  // [3]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCPY--Copy-8-bit-floating-point-immediate-to-vector-elements--predicated--

When op is in a GP register, the general implementation is:

```asm
CPY Ztied.D, Pg/M, Xop  // [3]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CPY--scalar---Copy-general-purpose-register-to-vector-elements--predicated--

When op is in an FP register, the general implementation is:

```asm
CPY Ztied.D, Pg/M, Dop  // [3]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CPY--SIMD-FP-scalar---Copy-SIMD-FP-scalar-register-to-vector-elements--predicated--

### Operation

Source operation ID: `SveOperation_svdup_n_bf16_m`

**Operation**



Return a vector in which each active element *i* contains `op`. Take the inactive elements of the result from the corresponding elements of `inactive`.



**[1]** This is true if the value is in the range [-128, 127] or is a multiple of 256 in the range [-32768, 32512]



**[2]** This is true if op is a floating-point immediate value expressable as ±n×2r, where n and r are integers such that 16 ≤ n ≤ 31 and -7 ≤ r ≤ 0.  In other words, this instruction requires op to have a normalized binary floating-point encoding with a sign bit, a 3-bit exponent, and a 4-bit fractional part.



**[3]** If instead `result` is in a different register from the inputs, the compiler can add a preceding [MOVPRFX (unpredicated)](https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--) instruction

## svdup[_n]_u64_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdup%5B_n%5D_u64_x

### Signature (source notation)

```c
svuint64_t svdup[_n]_u64_x(svbool_t pg, uint64_t op);
```

### Description

Broadcast a scalar value

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Set all lanes to the same value

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
  "op": {
    "register": "Dop|Xop"
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

When (int64_t)op is in range[1], this intrinsic can use:

```asm
CPY Zresult.D, Pg/Z, #(int64_t)op
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CPY--immediate--merging---Copy-signed-integer-immediate-to-vector-elements--merging--

…or, alternatively:

```asm
DUP Zresult.D, #op
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/DUP--immediate---Broadcast-signed-immediate-to-vector-elements--unpredicated--

When op is an FP immediate[2], this intrinsic can use:

```asm
FCPY Zresult.D, Pg/M, #op
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCPY--Copy-8-bit-floating-point-immediate-to-vector-elements--predicated--

…or, alternatively:

```asm
FDUP Zresult.D, #op
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FDUP--Broadcast-8-bit-floating-point-immediate-to-vector-elements--unpredicated--

When op is a logical immediate[3], this intrinsic can use:

```asm
DUPM Zresult.D, #op
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/DUPM--Broadcast-logical-bitmask-immediate-to-vector--unpredicated--

When op is in a GP register, the general implementation is:

```asm
DUP Zresult.D, Xop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/DUP--scalar---Broadcast-general-purpose-register-to-vector-elements--unpredicated--

When op is in an FP register, the general implementation is:

```asm
DUP Zresult.D, Zop.D[0]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/DUP--indexed---Broadcast-indexed-element-to-vector--unpredicated--

### Operation

Source operation ID: `SveOperation_svdup_n_s16_x`

**Operation**



Return a vector in which each active element *i* contains `op`. The inactive elements of the result have arbitrary, undefined values.



**[1]** This is true if the value is in the range [-128, 127] or is a multiple of 256 in the range [-32768, 32512]



**[2]** This is true if op is a floating-point immediate value expressable as ±n×2r, where n and r are integers such that 16 ≤ n ≤ 31 and -7 ≤ r ≤ 0.  In other words, this instruction requires op to have a normalized binary floating-point encoding with a sign bit, a 3-bit exponent, and a 4-bit fractional part.



**[3]** This is true if op is filled by some replicated bitmask *b* for which either all 0s in *b* are consecutive or all 1s in *b* are consecutive.

## svdup[_n]_u64_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdup%5B_n%5D_u64_z

### Signature (source notation)

```c
svuint64_t svdup[_n]_u64_z(svbool_t pg, uint64_t op);
```

### Description

Broadcast a scalar value

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Set all lanes to the same value

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
  "op": {
    "register": "Dop|Xop"
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

When (int64_t)op is in range[1], this intrinsic can use:

```asm
CPY Zresult.D, Pg/Z, #(int64_t)op
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CPY--immediate--merging---Copy-signed-integer-immediate-to-vector-elements--merging--

When op is an FP immediate[2], this intrinsic can use:

```asm
DUP Zresult.D, #0
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/DUP--immediate---Broadcast-signed-immediate-to-vector-elements--unpredicated--

```asm
FCPY Zresult.D, Pg/M, #op
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCPY--Copy-8-bit-floating-point-immediate-to-vector-elements--predicated--

When op is in a GP register, the general implementation is:

```asm
DUP Zresult.D, #0
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/DUP--immediate---Broadcast-signed-immediate-to-vector-elements--unpredicated--

```asm
CPY Zresult.D, Pg/M, Xop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CPY--scalar---Copy-general-purpose-register-to-vector-elements--predicated--

When op is in an FP register and result is in a different register from op, this intrinsic can use:

```asm
MOVPRFX Zresult.D, Pg/Z, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
CPY Zresult.D, Pg/M, Dop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CPY--SIMD-FP-scalar---Copy-SIMD-FP-scalar-register-to-vector-elements--predicated--

### Operation

Source operation ID: `SveOperation_svdup_n_bf16_z`

**Operation**



Return a vector in which each active element *i* contains `op`. Set the inactive elements of the result to zero.



**[1]** This is true if the value is in the range [-128, 127] or is a multiple of 256 in the range [-32768, 32512]



**[2]** This is true if op is a floating-point immediate value expressable as ±n×2r, where n and r are integers such that 16 ≤ n ≤ 31 and -7 ≤ r ≤ 0.  In other words, this instruction requires op to have a normalized binary floating-point encoding with a sign bit, a 3-bit exponent, and a 4-bit fractional part.

## svdup[_n]_u8

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdup%5B_n%5D_u8

### Signature (source notation)

```c
svuint8_t svdup[_n]_u8(uint8_t op);
```

### Description

Broadcast a scalar value

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Set all lanes to the same value

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
  "op": {
    "register": "Bop|Wop"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.B": "result"
  }
]
```

### Instruction mapping

When op is constant, this intrinsic can use:

```asm
DUP Zresult.B, #op
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/DUP--immediate---Broadcast-signed-immediate-to-vector-elements--unpredicated--

When op is an FP immediate[1], this intrinsic can use:

```asm
FDUP Zresult.B, #op
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FDUP--Broadcast-8-bit-floating-point-immediate-to-vector-elements--unpredicated--

When op is a logical immediate[2], this intrinsic can use:

```asm
DUPM Zresult.B, #op
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/DUPM--Broadcast-logical-bitmask-immediate-to-vector--unpredicated--

When op is in a GP register, the general implementation is:

```asm
DUP Zresult.B, Wop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/DUP--scalar---Broadcast-general-purpose-register-to-vector-elements--unpredicated--

When op is in an FP register, the general implementation is:

```asm
DUP Zresult.B, Zop.B[0]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/DUP--indexed---Broadcast-indexed-element-to-vector--unpredicated--

### Operation

Source operation ID: `SveOperation_svdup_n_s8`

**Operation**



Return a vector in which each element *i* contains `op`.



**[1]** This is true if op is a floating-point immediate value expressable as ±n×2r, where n and r are integers such that 16 ≤ n ≤ 31 and -7 ≤ r ≤ 0.  In other words, this instruction requires op to have a normalized binary floating-point encoding with a sign bit, a 3-bit exponent, and a 4-bit fractional part.



**[2]** This is true if op is filled by some replicated bitmask *b* for which either all 0s in *b* are consecutive or all 1s in *b* are consecutive.

## svdup[_n]_u8_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdup%5B_n%5D_u8_m

### Signature (source notation)

```c
svuint8_t svdup[_n]_u8_m(svuint8_t inactive, svbool_t pg, uint8_t op);
```

### Description

Broadcast a scalar value

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Set all lanes to the same value

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
  "inactive": {
    "register": "Ztied.B"
  },
  "pg": {
    "register": "Pg"
  },
  "op": {
    "register": "Bop|Wop"
  }
}
```

### Result mapping

```json
[
  {
    "Ztied.B": "result"
  }
]
```

### Instruction mapping

When op is constant, this intrinsic can use:

```asm
CPY Ztied.B, Pg/M, #(int8_t)op  // [2]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CPY--immediate--merging---Copy-signed-integer-immediate-to-vector-elements--merging--

When op is an FP immediate[1], this intrinsic can use:

```asm
FCPY Ztied.B, Pg/M, #op  // [2]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCPY--Copy-8-bit-floating-point-immediate-to-vector-elements--predicated--

When op is in a GP register, the general implementation is:

```asm
CPY Ztied.B, Pg/M, Wop  // [2]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CPY--scalar---Copy-general-purpose-register-to-vector-elements--predicated--

When op is in an FP register, the general implementation is:

```asm
CPY Ztied.B, Pg/M, Bop  // [2]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CPY--SIMD-FP-scalar---Copy-SIMD-FP-scalar-register-to-vector-elements--predicated--

### Operation

Source operation ID: `SveOperation_svdup_n_s8_m`

**Operation**



Return a vector in which each active element *i* contains `op`. Take the inactive elements of the result from the corresponding elements of `inactive`.



**[1]** This is true if op is a floating-point immediate value expressable as ±n×2r, where n and r are integers such that 16 ≤ n ≤ 31 and -7 ≤ r ≤ 0.  In other words, this instruction requires op to have a normalized binary floating-point encoding with a sign bit, a 3-bit exponent, and a 4-bit fractional part.



**[2]** If instead `result` is in a different register from the inputs, the compiler can add a preceding [MOVPRFX (unpredicated)](https://developer.arm.com/documentation/ddi0602/latest/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--) instruction

## svdup[_n]_u8_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdup%5B_n%5D_u8_x

### Signature (source notation)

```c
svuint8_t svdup[_n]_u8_x(svbool_t pg, uint8_t op);
```

### Description

Broadcast a scalar value

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Set all lanes to the same value

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
  "op": {
    "register": "Bop|Wop"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.B": "result"
  }
]
```

### Instruction mapping

When op is constant, this intrinsic can use:

```asm
CPY Zresult.B, Pg/Z, #(int8_t)op
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CPY--immediate--merging---Copy-signed-integer-immediate-to-vector-elements--merging--

…or, alternatively:

```asm
DUP Zresult.B, #op
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/DUP--immediate---Broadcast-signed-immediate-to-vector-elements--unpredicated--

When op is an FP immediate[1], this intrinsic can use:

```asm
FCPY Zresult.B, Pg/M, #op
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCPY--Copy-8-bit-floating-point-immediate-to-vector-elements--predicated--

…or, alternatively:

```asm
FDUP Zresult.B, #op
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FDUP--Broadcast-8-bit-floating-point-immediate-to-vector-elements--unpredicated--

When op is a logical immediate[2], this intrinsic can use:

```asm
DUPM Zresult.B, #op
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/DUPM--Broadcast-logical-bitmask-immediate-to-vector--unpredicated--

When op is in a GP register, the general implementation is:

```asm
DUP Zresult.B, Wop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/DUP--scalar---Broadcast-general-purpose-register-to-vector-elements--unpredicated--

When op is in an FP register, the general implementation is:

```asm
DUP Zresult.B, Zop.B[0]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/DUP--indexed---Broadcast-indexed-element-to-vector--unpredicated--

### Operation

Source operation ID: `SveOperation_svdup_n_s8_x`

**Operation**



Return a vector in which each active element *i* contains `op`. The inactive elements of the result have arbitrary, undefined values.



**[1]** This is true if op is a floating-point immediate value expressable as ±n×2r, where n and r are integers such that 16 ≤ n ≤ 31 and -7 ≤ r ≤ 0.  In other words, this instruction requires op to have a normalized binary floating-point encoding with a sign bit, a 3-bit exponent, and a 4-bit fractional part.



**[2]** This is true if op is filled by some replicated bitmask *b* for which either all 0s in *b* are consecutive or all 1s in *b* are consecutive.

## svdup[_n]_u8_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdup%5B_n%5D_u8_z

### Signature (source notation)

```c
svuint8_t svdup[_n]_u8_z(svbool_t pg, uint8_t op);
```

### Description

Broadcast a scalar value

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Set all lanes to the same value

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
  "op": {
    "register": "Bop|Wop"
  }
}
```

### Result mapping

```json
[
  {
    "Zresult.B": "result"
  }
]
```

### Instruction mapping

When op is constant, this intrinsic can use:

```asm
CPY Zresult.B, Pg/Z, #(int8_t)op
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CPY--immediate--merging---Copy-signed-integer-immediate-to-vector-elements--merging--

When op is an FP immediate[1], this intrinsic can use:

```asm
DUP Zresult.B, #0
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/DUP--immediate---Broadcast-signed-immediate-to-vector-elements--unpredicated--

```asm
FCPY Zresult.B, Pg/M, #op
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FCPY--Copy-8-bit-floating-point-immediate-to-vector-elements--predicated--

When op is in a GP register, the general implementation is:

```asm
DUP Zresult.B, #0
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/DUP--immediate---Broadcast-signed-immediate-to-vector-elements--unpredicated--

```asm
CPY Zresult.B, Pg/M, Wop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CPY--scalar---Copy-general-purpose-register-to-vector-elements--predicated--

When op is in an FP register and result is in a different register from op, this intrinsic can use:

```asm
MOVPRFX Zresult.B, Pg/Z, Zop.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
CPY Zresult.B, Pg/M, Bop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CPY--SIMD-FP-scalar---Copy-SIMD-FP-scalar-register-to-vector-elements--predicated--

### Operation

Source operation ID: `SveOperation_svdup_n_s8_z`

**Operation**



Return a vector in which each active element *i* contains `op`. Set the inactive elements of the result to zero.



**[1]** This is true if op is a floating-point immediate value expressable as ±n×2r, where n and r are integers such that 16 ≤ n ≤ 31 and -7 ≤ r ≤ 0.  In other words, this instruction requires op to have a normalized binary floating-point encoding with a sign bit, a 3-bit exponent, and a 4-bit fractional part.

## svdup_lane[_bf16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdup_lane%5B_bf16%5D

### Signature (source notation)

```c
svbfloat16_t svdup_lane[_bf16](svbfloat16_t data, uint16_t index);
```

### Description

Broadcast a scalar value

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Set all lanes to the same value

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
  "data": {
    "register": "Zdata.H"
  },
  "index": {
    "register": "Zindex.H[*]"
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

When index is in the range [0, 31], this intrinsic can use:

```asm
DUP Zresult.H, Zdata.H[index]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/DUP--indexed---Broadcast-indexed-element-to-vector--unpredicated--

The general implementation is:

```asm
TBL Zresult.H, Zdata.H, Zindex.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/TBL--Programmable-table-lookup-in-one-or-two-vector-table--zeroing--

### Operation

Source operation ID: `SveOperation_svdup_lane_bf16`

**Operation**



If `index` is less than the number of elements in `data`, return a vector in which every element contains `data[index]`.  Return an all-zeros vector otherwise.

## svdup_lane[_f16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdup_lane%5B_f16%5D

### Signature (source notation)

```c
svfloat16_t svdup_lane[_f16](svfloat16_t data, uint16_t index);
```

### Description

Broadcast a scalar value

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector manipulation / Set all lanes to the same value

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
  "data": {
    "register": "Zdata.H"
  },
  "index": {
    "register": "Zindex.H[*]"
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

When index is in the range [0, 31], this intrinsic can use:

```asm
DUP Zresult.H, Zdata.H[index]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/DUP--indexed---Broadcast-indexed-element-to-vector--unpredicated--

The general implementation is:

```asm
TBL Zresult.H, Zdata.H, Zindex.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/TBL--Programmable-table-lookup-in-one-or-two-vector-table--zeroing--

### Operation

Source operation ID: `SveOperation_svdup_lane_bf16`

**Operation**



If `index` is less than the number of elements in `data`, return a vector in which every element contains `data[index]`.  Return an all-zeros vector otherwise.

