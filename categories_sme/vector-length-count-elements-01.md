# SME / Vector length / Count elements — Part 1

## svcntb

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcntb

### Signature (source notation)

```c
uint64_t svcntb();
```

### Description

Count the number of 8-bit elements in a vector

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector length / Count elements

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
{}
```

### Result mapping

```json
[
  {
    "Xresult": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
CNTB Xresult, ALL
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CNTB--CNTD--CNTH--CNTW--Set-scalar-to-multiple-of-predicate-constraint-element-count-

### Operation

Source operation ID: `SveOperation_svcntb`

**Operation**



Return the number of 8-bit elements in a full vector.



The underlying instruction takes a constant multiplier in the range [1, 16], which compilers can use to optimize multiplications of the function's return value.

## svcntb_pat

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcntb_pat

### Signature (source notation)

```c
uint64_t svcntb_pat(enum svpattern pattern);
```

### Description

Count the number of 8-bit elements in a vector

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector length / Count elements

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
{}
```

### Result mapping

```json
[
  {
    "Xresult": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
CNTB Xresult, pattern
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CNTB--CNTD--CNTH--CNTW--Set-scalar-to-multiple-of-predicate-constraint-element-count-

### Operation

Source operation ID: `SveOperation_svcntb_pat`

**Operation**



Return the number of 8-bit elements in pattern `pattern`.



The underlying instruction takes a constant multiplier in the range [1, 16], which compilers can use to optimize multiplications of the function's return value.

## svcntd

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcntd

### Signature (source notation)

```c
uint64_t svcntd();
```

### Description

Count the number of 64-bit elements in a vector

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector length / Count elements

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
{}
```

### Result mapping

```json
[
  {
    "Xresult": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
CNTD Xresult, ALL
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CNTB--CNTD--CNTH--CNTW--Set-scalar-to-multiple-of-predicate-constraint-element-count-

### Operation

Source operation ID: `SveOperation_svcntd`

**Operation**



Return the number of 64-bit elements in a full vector.



The underlying instruction takes a constant multiplier in the range [1, 16], which compilers can use to optimize multiplications of the function's return value.

## svcntd_pat

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcntd_pat

### Signature (source notation)

```c
uint64_t svcntd_pat(enum svpattern pattern);
```

### Description

Count the number of 64-bit elements in a vector

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector length / Count elements

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
{}
```

### Result mapping

```json
[
  {
    "Xresult": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
CNTD Xresult, pattern
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CNTB--CNTD--CNTH--CNTW--Set-scalar-to-multiple-of-predicate-constraint-element-count-

### Operation

Source operation ID: `SveOperation_svcntd_pat`

**Operation**



Return the number of 64-bit elements in pattern `pattern`.



The underlying instruction takes a constant multiplier in the range [1, 16], which compilers can use to optimize multiplications of the function's return value.

## svcnth

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcnth

### Signature (source notation)

```c
uint64_t svcnth();
```

### Description

Count the number of 16-bit elements in a vector

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector length / Count elements

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
{}
```

### Result mapping

```json
[
  {
    "Xresult": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
CNTH Xresult, ALL
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CNTB--CNTD--CNTH--CNTW--Set-scalar-to-multiple-of-predicate-constraint-element-count-

### Operation

Source operation ID: `SveOperation_svcnth`

**Operation**



Return the number of 16-bit elements in a full vector.



The underlying instruction takes a constant multiplier in the range [1, 16], which compilers can use to optimize multiplications of the function's return value.

## svcnth_pat

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcnth_pat

### Signature (source notation)

```c
uint64_t svcnth_pat(enum svpattern pattern);
```

### Description

Count the number of 16-bit elements in a vector

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector length / Count elements

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
{}
```

### Result mapping

```json
[
  {
    "Xresult": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
CNTH Xresult, pattern
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CNTB--CNTD--CNTH--CNTW--Set-scalar-to-multiple-of-predicate-constraint-element-count-

### Operation

Source operation ID: `SveOperation_svcnth_pat`

**Operation**



Return the number of 16-bit elements in pattern `pattern`.



The underlying instruction takes a constant multiplier in the range [1, 16], which compilers can use to optimize multiplications of the function's return value.

## svcntsb

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcntsb

### Signature (source notation)

```c
uint64_t svcntsb();
```

### Description

Read multiple of Streaming SVE vector register size to scalar register

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Vector length / Count elements

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
  "return_base_type": "uint64_t",
  "element_bit_size": "64",
  "value": "uint64_t"
}
```

### Argument preparation and constraints

```json
{}
```

### Result mapping

```json
[
  {
    "Xreg1": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
RDSVL Xreg1, #1
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/RDSVL--Read-multiple-of-Streaming-SVE-vector-register-size-to-scalar-register-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svcntsd

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcntsd

### Signature (source notation)

```c
uint64_t svcntsd();
```

### Description

Read multiple of Streaming SVE vector register size to scalar register

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Vector length / Count elements

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
  "return_base_type": "uint64_t",
  "element_bit_size": "64",
  "value": "uint64_t"
}
```

### Argument preparation and constraints

```json
{}
```

### Result mapping

```json
[
  {
    "Xreg1": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
RDSVL Xreg1, #8
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/RDSVL--Read-multiple-of-Streaming-SVE-vector-register-size-to-scalar-register-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svcntsh

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcntsh

### Signature (source notation)

```c
uint64_t svcntsh();
```

### Description

Read multiple of Streaming SVE vector register size to scalar register

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Vector length / Count elements

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
  "return_base_type": "uint64_t",
  "element_bit_size": "64",
  "value": "uint64_t"
}
```

### Argument preparation and constraints

```json
{}
```

### Result mapping

```json
[
  {
    "Xreg1": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
RDSVL Xreg1, #2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/RDSVL--Read-multiple-of-Streaming-SVE-vector-register-size-to-scalar-register-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svcntsw

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcntsw

### Signature (source notation)

```c
uint64_t svcntsw();
```

### Description

Read multiple of Streaming SVE vector register size to scalar register

### Availability

- ISA categories: SME and SME2

- Architectures: A64

- Instruction group: Vector length / Count elements

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
  "return_base_type": "uint64_t",
  "element_bit_size": "64",
  "value": "uint64_t"
}
```

### Argument preparation and constraints

```json
{}
```

### Result mapping

```json
[
  {
    "Xreg1": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
RDSVL Xreg1, #4
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SME-Instructions/RDSVL--Read-multiple-of-Streaming-SVE-vector-register-size-to-scalar-register-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svcntw

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcntw

### Signature (source notation)

```c
uint64_t svcntw();
```

### Description

Count the number of 32-bit elements in a vector

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector length / Count elements

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
{}
```

### Result mapping

```json
[
  {
    "Xresult": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
CNTW Xresult, ALL
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CNTB--CNTD--CNTH--CNTW--Set-scalar-to-multiple-of-predicate-constraint-element-count-

### Operation

Source operation ID: `SveOperation_svcntw`

**Operation**



Return the number of 32-bit elements in a full vector.



The underlying instruction takes a constant multiplier in the range [1, 16], which compilers can use to optimize multiplications of the function's return value.

## svcntw_pat

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svcntw_pat

### Signature (source notation)

```c
uint64_t svcntw_pat(enum svpattern pattern);
```

### Description

Count the number of 32-bit elements in a vector

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector length / Count elements

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
{}
```

### Result mapping

```json
[
  {
    "Xresult": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
CNTW Xresult, pattern
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CNTB--CNTD--CNTH--CNTW--Set-scalar-to-multiple-of-predicate-constraint-element-count-

### Operation

Source operation ID: `SveOperation_svcntw_pat`

**Operation**



Return the number of 32-bit elements in pattern `pattern`.



The underlying instruction takes a constant multiplier in the range [1, 16], which compilers can use to optimize multiplications of the function's return value.

## svlen[_bf16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svlen%5B_bf16%5D

### Signature (source notation)

```c
uint64_t svlen[_bf16](svbfloat16_t op);
```

### Description

Count the number of elements in a full vector

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector length / Count elements

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
{}
```

### Result mapping

```json
[
  {
    "Xresult": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
CNTH Xresult, ALL
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CNTB--CNTD--CNTH--CNTW--Set-scalar-to-multiple-of-predicate-constraint-element-count-

### Operation

Source operation ID: `SveOperation_svlen_bf16`

**Operation**



Return the number of elements in `op`.



The contents of `op` do not matter.  However, unlike `sizeof`, any side-effects involved in evaluating `op` still take place.



In practice only the overloaded form of `svlen` is useful. It is better to use one of the following functions instead of using `svlen` with an explicit type suffix:




- `svcntb`
- `svcnth`
- `svcntw`
- `svcntd`

## svlen[_f16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svlen%5B_f16%5D

### Signature (source notation)

```c
uint64_t svlen[_f16](svfloat16_t op);
```

### Description

Count the number of elements in a full vector

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector length / Count elements

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
{}
```

### Result mapping

```json
[
  {
    "Xresult": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
CNTH Xresult, ALL
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CNTB--CNTD--CNTH--CNTW--Set-scalar-to-multiple-of-predicate-constraint-element-count-

### Operation

Source operation ID: `SveOperation_svlen_bf16`

**Operation**



Return the number of elements in `op`.



The contents of `op` do not matter.  However, unlike `sizeof`, any side-effects involved in evaluating `op` still take place.



In practice only the overloaded form of `svlen` is useful. It is better to use one of the following functions instead of using `svlen` with an explicit type suffix:




- `svcntb`
- `svcnth`
- `svcntw`
- `svcntd`

## svlen[_f32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svlen%5B_f32%5D

### Signature (source notation)

```c
uint64_t svlen[_f32](svfloat32_t op);
```

### Description

Count the number of elements in a full vector

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector length / Count elements

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
{}
```

### Result mapping

```json
[
  {
    "Xresult": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
CNTW Xresult, ALL
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CNTB--CNTD--CNTH--CNTW--Set-scalar-to-multiple-of-predicate-constraint-element-count-

### Operation

Source operation ID: `SveOperation_svlen_bf16`

**Operation**



Return the number of elements in `op`.



The contents of `op` do not matter.  However, unlike `sizeof`, any side-effects involved in evaluating `op` still take place.



In practice only the overloaded form of `svlen` is useful. It is better to use one of the following functions instead of using `svlen` with an explicit type suffix:




- `svcntb`
- `svcnth`
- `svcntw`
- `svcntd`

## svlen[_f64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svlen%5B_f64%5D

### Signature (source notation)

```c
uint64_t svlen[_f64](svfloat64_t op);
```

### Description

Count the number of elements in a full vector

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector length / Count elements

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
{}
```

### Result mapping

```json
[
  {
    "Xresult": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
CNTD Xresult, ALL
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CNTB--CNTD--CNTH--CNTW--Set-scalar-to-multiple-of-predicate-constraint-element-count-

### Operation

Source operation ID: `SveOperation_svlen_bf16`

**Operation**



Return the number of elements in `op`.



The contents of `op` do not matter.  However, unlike `sizeof`, any side-effects involved in evaluating `op` still take place.



In practice only the overloaded form of `svlen` is useful. It is better to use one of the following functions instead of using `svlen` with an explicit type suffix:




- `svcntb`
- `svcnth`
- `svcntw`
- `svcntd`

## svlen[_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svlen%5B_s16%5D

### Signature (source notation)

```c
uint64_t svlen[_s16](svint16_t op);
```

### Description

Count the number of elements in a full vector

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector length / Count elements

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
{}
```

### Result mapping

```json
[
  {
    "Xresult": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
CNTH Xresult, ALL
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CNTB--CNTD--CNTH--CNTW--Set-scalar-to-multiple-of-predicate-constraint-element-count-

### Operation

Source operation ID: `SveOperation_svlen_bf16`

**Operation**



Return the number of elements in `op`.



The contents of `op` do not matter.  However, unlike `sizeof`, any side-effects involved in evaluating `op` still take place.



In practice only the overloaded form of `svlen` is useful. It is better to use one of the following functions instead of using `svlen` with an explicit type suffix:




- `svcntb`
- `svcnth`
- `svcntw`
- `svcntd`

## svlen[_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svlen%5B_s32%5D

### Signature (source notation)

```c
uint64_t svlen[_s32](svint32_t op);
```

### Description

Count the number of elements in a full vector

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector length / Count elements

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
{}
```

### Result mapping

```json
[
  {
    "Xresult": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
CNTW Xresult, ALL
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CNTB--CNTD--CNTH--CNTW--Set-scalar-to-multiple-of-predicate-constraint-element-count-

### Operation

Source operation ID: `SveOperation_svlen_bf16`

**Operation**



Return the number of elements in `op`.



The contents of `op` do not matter.  However, unlike `sizeof`, any side-effects involved in evaluating `op` still take place.



In practice only the overloaded form of `svlen` is useful. It is better to use one of the following functions instead of using `svlen` with an explicit type suffix:




- `svcntb`
- `svcnth`
- `svcntw`
- `svcntd`

## svlen[_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svlen%5B_s64%5D

### Signature (source notation)

```c
uint64_t svlen[_s64](svint64_t op);
```

### Description

Count the number of elements in a full vector

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector length / Count elements

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
{}
```

### Result mapping

```json
[
  {
    "Xresult": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
CNTD Xresult, ALL
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CNTB--CNTD--CNTH--CNTW--Set-scalar-to-multiple-of-predicate-constraint-element-count-

### Operation

Source operation ID: `SveOperation_svlen_bf16`

**Operation**



Return the number of elements in `op`.



The contents of `op` do not matter.  However, unlike `sizeof`, any side-effects involved in evaluating `op` still take place.



In practice only the overloaded form of `svlen` is useful. It is better to use one of the following functions instead of using `svlen` with an explicit type suffix:




- `svcntb`
- `svcnth`
- `svcntw`
- `svcntd`

## svlen[_s8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svlen%5B_s8%5D

### Signature (source notation)

```c
uint64_t svlen[_s8](svint8_t op);
```

### Description

Count the number of elements in a full vector

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector length / Count elements

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
{}
```

### Result mapping

```json
[
  {
    "Xresult": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
CNTB Xresult, ALL
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CNTB--CNTD--CNTH--CNTW--Set-scalar-to-multiple-of-predicate-constraint-element-count-

### Operation

Source operation ID: `SveOperation_svlen_bf16`

**Operation**



Return the number of elements in `op`.



The contents of `op` do not matter.  However, unlike `sizeof`, any side-effects involved in evaluating `op` still take place.



In practice only the overloaded form of `svlen` is useful. It is better to use one of the following functions instead of using `svlen` with an explicit type suffix:




- `svcntb`
- `svcnth`
- `svcntw`
- `svcntd`

## svlen[_u16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svlen%5B_u16%5D

### Signature (source notation)

```c
uint64_t svlen[_u16](svuint16_t op);
```

### Description

Count the number of elements in a full vector

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector length / Count elements

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
{}
```

### Result mapping

```json
[
  {
    "Xresult": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
CNTH Xresult, ALL
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CNTB--CNTD--CNTH--CNTW--Set-scalar-to-multiple-of-predicate-constraint-element-count-

### Operation

Source operation ID: `SveOperation_svlen_bf16`

**Operation**



Return the number of elements in `op`.



The contents of `op` do not matter.  However, unlike `sizeof`, any side-effects involved in evaluating `op` still take place.



In practice only the overloaded form of `svlen` is useful. It is better to use one of the following functions instead of using `svlen` with an explicit type suffix:




- `svcntb`
- `svcnth`
- `svcntw`
- `svcntd`

## svlen[_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svlen%5B_u32%5D

### Signature (source notation)

```c
uint64_t svlen[_u32](svuint32_t op);
```

### Description

Count the number of elements in a full vector

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector length / Count elements

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
{}
```

### Result mapping

```json
[
  {
    "Xresult": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
CNTW Xresult, ALL
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CNTB--CNTD--CNTH--CNTW--Set-scalar-to-multiple-of-predicate-constraint-element-count-

### Operation

Source operation ID: `SveOperation_svlen_bf16`

**Operation**



Return the number of elements in `op`.



The contents of `op` do not matter.  However, unlike `sizeof`, any side-effects involved in evaluating `op` still take place.



In practice only the overloaded form of `svlen` is useful. It is better to use one of the following functions instead of using `svlen` with an explicit type suffix:




- `svcntb`
- `svcnth`
- `svcntw`
- `svcntd`

## svlen[_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svlen%5B_u64%5D

### Signature (source notation)

```c
uint64_t svlen[_u64](svuint64_t op);
```

### Description

Count the number of elements in a full vector

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector length / Count elements

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
{}
```

### Result mapping

```json
[
  {
    "Xresult": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
CNTD Xresult, ALL
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CNTB--CNTD--CNTH--CNTW--Set-scalar-to-multiple-of-predicate-constraint-element-count-

### Operation

Source operation ID: `SveOperation_svlen_bf16`

**Operation**



Return the number of elements in `op`.



The contents of `op` do not matter.  However, unlike `sizeof`, any side-effects involved in evaluating `op` still take place.



In practice only the overloaded form of `svlen` is useful. It is better to use one of the following functions instead of using `svlen` with an explicit type suffix:




- `svcntb`
- `svcnth`
- `svcntw`
- `svcntd`

## svlen[_u8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svlen%5B_u8%5D

### Signature (source notation)

```c
uint64_t svlen[_u8](svuint8_t op);
```

### Description

Count the number of elements in a full vector

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Vector length / Count elements

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
{}
```

### Result mapping

```json
[
  {
    "Xresult": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
CNTB Xresult, ALL
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/CNTB--CNTD--CNTH--CNTW--Set-scalar-to-multiple-of-predicate-constraint-element-count-

### Operation

Source operation ID: `SveOperation_svlen_bf16`

**Operation**



Return the number of elements in `op`.



The contents of `op` do not matter.  However, unlike `sizeof`, any side-effects involved in evaluating `op` still take place.



In practice only the overloaded form of `svlen` is useful. It is better to use one of the following functions instead of using `svlen` with an explicit type suffix:




- `svcntb`
- `svcnth`
- `svcntw`
- `svcntd`

