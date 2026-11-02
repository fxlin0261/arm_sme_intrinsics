# SME / Vector arithmetic / Logarithm — Part 1

## svlogb[_f16]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svlogb%5B_f16%5D_m

### Signature (source notation)

```c
svint16_t svlogb[_f16]_m(svint16_t inactive, svbool_t pg, svfloat16_t op);
```

### Description

Base 2 logarithm as integer

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Logarithm

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
    "register": "Zinactive.H|Ztied.H"
  },
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
    "Zresult.H|Ztied.H": "result"
  }
]
```

### Instruction mapping

When result and inactive are in the same register, this intrinsic compiles to:

```asm
FLOGB Ztied.H, Pg/M, Zop.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FLOGB--Floating-point-base-2-logarithm-as-integer-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zinactive
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FLOGB Zresult.H, Pg/M, Zop.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FLOGB--Floating-point-base-2-logarithm-as-integer-

### Operation

Source operation ID: `SveOperation_svlogb_f16_m`

**Operation**



For each active element *i*:




- If `op[i]` is a NaN or zero, set element *i* of the result to the minimum signed value.
- If `op[i]` is infinite, set element *i* of the result to the maximum signed value.
- Otherwise, set element *i* of the result to the base 2 logarithm of `op[i]`, rounding down.



Take the inactive elements of the result from the corresponding elements of `inactive`.



**Exceptions**



Active signaling and quiet NaNs both trigger an IEEE Invalid exception. Active zeros also trigger an IEEE Invalid exception.

## svlogb[_f16]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svlogb%5B_f16%5D_x

### Signature (source notation)

```c
svint16_t svlogb[_f16]_x(svbool_t pg, svfloat16_t op);
```

### Description

Base 2 logarithm as integer

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Logarithm

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
    "register": "Zop.H|Ztied.H"
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

When result and op are in the same register, this intrinsic compiles to:

```asm
FLOGB Ztied.H, Pg/M, Ztied.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FLOGB--Floating-point-base-2-logarithm-as-integer-

When result and op are in different registers, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FLOGB Zresult.H, Pg/M, Zop.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FLOGB--Floating-point-base-2-logarithm-as-integer-

### Operation

Source operation ID: `SveOperation_svlogb_f16_x`

**Operation**



For each active element *i*:




- If `op[i]` is a NaN or zero, set element *i* of the result to the minimum signed value.
- If `op[i]` is infinite, set element *i* of the result to the maximum signed value.
- Otherwise, set element *i* of the result to the base 2 logarithm of `op[i]`, rounding down.



The inactive elements of the result have arbitrary, undefined values.



**Exceptions**



Active signaling and quiet NaNs both trigger an IEEE Invalid exception. Active zeros also trigger an IEEE Invalid exception.

## svlogb[_f16]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svlogb%5B_f16%5D_z

### Signature (source notation)

```c
svint16_t svlogb[_f16]_z(svbool_t pg, svfloat16_t op);
```

### Description

Base 2 logarithm as integer

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Logarithm

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
    "register": "Zop.H"
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

This intrinsic compiles to the following instructions, or functionally equivalent instructions:

```asm
MOVPRFX Zresult.H, Pg/Z, Zop.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
FLOGB Zresult.H, Pg/M, Zop.H  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FLOGB--Floating-point-base-2-logarithm-as-integer-

### Operation

Source operation ID: `SveOperation_svlogb_f16_z`

**Operation**



For each active element *i*:




- If `op[i]` is a NaN or zero, set element *i* of the result to the minimum signed value.
- If `op[i]` is infinite, set element *i* of the result to the maximum signed value.
- Otherwise, set element *i* of the result to the base 2 logarithm of `op[i]`, rounding down.



Set the inactive elements of the result to zero.



**Exceptions**



Active signaling and quiet NaNs both trigger an IEEE Invalid exception. Active zeros also trigger an IEEE Invalid exception.



**[1]** Note that `result` must be in a different register from `op`

## svlogb[_f32]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svlogb%5B_f32%5D_m

### Signature (source notation)

```c
svint32_t svlogb[_f32]_m(svint32_t inactive, svbool_t pg, svfloat32_t op);
```

### Description

Base 2 logarithm as integer

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Logarithm

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
    "register": "Zinactive.S|Ztied.S"
  },
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
    "Zresult.S|Ztied.S": "result"
  }
]
```

### Instruction mapping

When result and inactive are in the same register, this intrinsic compiles to:

```asm
FLOGB Ztied.S, Pg/M, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FLOGB--Floating-point-base-2-logarithm-as-integer-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zinactive
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FLOGB Zresult.S, Pg/M, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FLOGB--Floating-point-base-2-logarithm-as-integer-

### Operation

Source operation ID: `SveOperation_svlogb_f16_m`

**Operation**



For each active element *i*:




- If `op[i]` is a NaN or zero, set element *i* of the result to the minimum signed value.
- If `op[i]` is infinite, set element *i* of the result to the maximum signed value.
- Otherwise, set element *i* of the result to the base 2 logarithm of `op[i]`, rounding down.



Take the inactive elements of the result from the corresponding elements of `inactive`.



**Exceptions**



Active signaling and quiet NaNs both trigger an IEEE Invalid exception. Active zeros also trigger an IEEE Invalid exception.

## svlogb[_f32]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svlogb%5B_f32%5D_x

### Signature (source notation)

```c
svint32_t svlogb[_f32]_x(svbool_t pg, svfloat32_t op);
```

### Description

Base 2 logarithm as integer

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Logarithm

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
    "register": "Zop.S|Ztied.S"
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

When result and op are in the same register, this intrinsic compiles to:

```asm
FLOGB Ztied.S, Pg/M, Ztied.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FLOGB--Floating-point-base-2-logarithm-as-integer-

When result and op are in different registers, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FLOGB Zresult.S, Pg/M, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FLOGB--Floating-point-base-2-logarithm-as-integer-

### Operation

Source operation ID: `SveOperation_svlogb_f16_x`

**Operation**



For each active element *i*:




- If `op[i]` is a NaN or zero, set element *i* of the result to the minimum signed value.
- If `op[i]` is infinite, set element *i* of the result to the maximum signed value.
- Otherwise, set element *i* of the result to the base 2 logarithm of `op[i]`, rounding down.



The inactive elements of the result have arbitrary, undefined values.



**Exceptions**



Active signaling and quiet NaNs both trigger an IEEE Invalid exception. Active zeros also trigger an IEEE Invalid exception.

## svlogb[_f32]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svlogb%5B_f32%5D_z

### Signature (source notation)

```c
svint32_t svlogb[_f32]_z(svbool_t pg, svfloat32_t op);
```

### Description

Base 2 logarithm as integer

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Logarithm

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
    "register": "Zop.S"
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

This intrinsic compiles to the following instructions, or functionally equivalent instructions:

```asm
MOVPRFX Zresult.S, Pg/Z, Zop.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
FLOGB Zresult.S, Pg/M, Zop.S  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FLOGB--Floating-point-base-2-logarithm-as-integer-

### Operation

Source operation ID: `SveOperation_svlogb_f16_z`

**Operation**



For each active element *i*:




- If `op[i]` is a NaN or zero, set element *i* of the result to the minimum signed value.
- If `op[i]` is infinite, set element *i* of the result to the maximum signed value.
- Otherwise, set element *i* of the result to the base 2 logarithm of `op[i]`, rounding down.



Set the inactive elements of the result to zero.



**Exceptions**



Active signaling and quiet NaNs both trigger an IEEE Invalid exception. Active zeros also trigger an IEEE Invalid exception.



**[1]** Note that `result` must be in a different register from `op`

## svlogb[_f64]_m

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svlogb%5B_f64%5D_m

### Signature (source notation)

```c
svint64_t svlogb[_f64]_m(svint64_t inactive, svbool_t pg, svfloat64_t op);
```

### Description

Base 2 logarithm as integer

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Logarithm

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
    "register": "Zinactive.D|Ztied.D"
  },
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
    "Zresult.D|Ztied.D": "result"
  }
]
```

### Instruction mapping

When result and inactive are in the same register, this intrinsic compiles to:

```asm
FLOGB Ztied.D, Pg/M, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FLOGB--Floating-point-base-2-logarithm-as-integer-

When result is in a different register from the inputs, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zinactive
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FLOGB Zresult.D, Pg/M, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FLOGB--Floating-point-base-2-logarithm-as-integer-

### Operation

Source operation ID: `SveOperation_svlogb_f16_m`

**Operation**



For each active element *i*:




- If `op[i]` is a NaN or zero, set element *i* of the result to the minimum signed value.
- If `op[i]` is infinite, set element *i* of the result to the maximum signed value.
- Otherwise, set element *i* of the result to the base 2 logarithm of `op[i]`, rounding down.



Take the inactive elements of the result from the corresponding elements of `inactive`.



**Exceptions**



Active signaling and quiet NaNs both trigger an IEEE Invalid exception. Active zeros also trigger an IEEE Invalid exception.

## svlogb[_f64]_x

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svlogb%5B_f64%5D_x

### Signature (source notation)

```c
svint64_t svlogb[_f64]_x(svbool_t pg, svfloat64_t op);
```

### Description

Base 2 logarithm as integer

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Logarithm

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
    "register": "Zop.D|Ztied.D"
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

When result and op are in the same register, this intrinsic compiles to:

```asm
FLOGB Ztied.D, Pg/M, Ztied.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FLOGB--Floating-point-base-2-logarithm-as-integer-

When result and op are in different registers, this intrinsic compiles to:

```asm
MOVPRFX Zresult, Zop
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--unpredicated---Move-prefix--unpredicated--

```asm
FLOGB Zresult.D, Pg/M, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FLOGB--Floating-point-base-2-logarithm-as-integer-

### Operation

Source operation ID: `SveOperation_svlogb_f16_x`

**Operation**



For each active element *i*:




- If `op[i]` is a NaN or zero, set element *i* of the result to the minimum signed value.
- If `op[i]` is infinite, set element *i* of the result to the maximum signed value.
- Otherwise, set element *i* of the result to the base 2 logarithm of `op[i]`, rounding down.



The inactive elements of the result have arbitrary, undefined values.



**Exceptions**



Active signaling and quiet NaNs both trigger an IEEE Invalid exception. Active zeros also trigger an IEEE Invalid exception.

## svlogb[_f64]_z

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svlogb%5B_f64%5D_z

### Signature (source notation)

```c
svint64_t svlogb[_f64]_z(svbool_t pg, svfloat64_t op);
```

### Description

Base 2 logarithm as integer

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Vector arithmetic / Logarithm

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
    "register": "Zop.D"
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

This intrinsic compiles to the following instructions, or functionally equivalent instructions:

```asm
MOVPRFX Zresult.D, Pg/Z, Zop.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/MOVPRFX--predicated---Move-prefix--predicated--

```asm
FLOGB Zresult.D, Pg/M, Zop.D  // [1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/FLOGB--Floating-point-base-2-logarithm-as-integer-

### Operation

Source operation ID: `SveOperation_svlogb_f16_z`

**Operation**



For each active element *i*:




- If `op[i]` is a NaN or zero, set element *i* of the result to the minimum signed value.
- If `op[i]` is infinite, set element *i* of the result to the maximum signed value.
- Otherwise, set element *i* of the result to the base 2 logarithm of `op[i]`, rounding down.



Set the inactive elements of the result to zero.



**Exceptions**



Active signaling and quiet NaNs both trigger an IEEE Invalid exception. Active zeros also trigger an IEEE Invalid exception.



**[1]** Note that `result` must be in a different register from `op`

