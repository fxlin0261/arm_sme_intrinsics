# SME / Predication / Initialization / Detect hazards — Part 1

## svwhilerw[_bf16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwhilerw%5B_bf16%5D

### Signature (source notation)

```c
svbool_t svwhilerw[_bf16](const bfloat16_t *op1, const bfloat16_t *op2);
```

### Description

While free of read-after-write conflicts

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Initialization / Detect hazards

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
  "return_base_type": "bool",
  "element_bit_size": "16",
  "value": "svbool_t"
}
```

### Argument preparation and constraints

```json
{
  "op1": {
    "register": "Xop1"
  },
  "op2": {
    "register": "Xop2"
  }
}
```

### Result mapping

```json
[
  {
    "Presult.H": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
WHILERW Presult.H, Xop1, Xop2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/WHILERW--While-free-of-read-after-write-conflicts-

### Operation

Source operation ID: `SveOperation_svwhilerw_bf16`

**Operation**



Consider a hypothetical loop:



```text
for (int i = 0; i < n; ++i) {
  op1[i] = …;
  … = op2[i];
}
```



and return a predicate in which element *j* is active if *j*+1 iterations of the loop could be performed in parallel without changing the dependencies between `op1` and `op2`. The first element of the result is always active.

## svwhilerw[_f16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwhilerw%5B_f16%5D

### Signature (source notation)

```c
svbool_t svwhilerw[_f16](const float16_t *op1, const float16_t *op2);
```

### Description

While free of read-after-write conflicts

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Initialization / Detect hazards

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
  "return_base_type": "bool",
  "element_bit_size": "16",
  "value": "svbool_t"
}
```

### Argument preparation and constraints

```json
{
  "op1": {
    "register": "Xop1"
  },
  "op2": {
    "register": "Xop2"
  }
}
```

### Result mapping

```json
[
  {
    "Presult.H": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
WHILERW Presult.H, Xop1, Xop2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/WHILERW--While-free-of-read-after-write-conflicts-

### Operation

Source operation ID: `SveOperation_svwhilerw_bf16`

**Operation**



Consider a hypothetical loop:



```text
for (int i = 0; i < n; ++i) {
  op1[i] = …;
  … = op2[i];
}
```



and return a predicate in which element *j* is active if *j*+1 iterations of the loop could be performed in parallel without changing the dependencies between `op1` and `op2`. The first element of the result is always active.

## svwhilerw[_f32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwhilerw%5B_f32%5D

### Signature (source notation)

```c
svbool_t svwhilerw[_f32](const float32_t *op1, const float32_t *op2);
```

### Description

While free of read-after-write conflicts

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Initialization / Detect hazards

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
  "return_base_type": "bool",
  "element_bit_size": "32",
  "value": "svbool_t"
}
```

### Argument preparation and constraints

```json
{
  "op1": {
    "register": "Xop1"
  },
  "op2": {
    "register": "Xop2"
  }
}
```

### Result mapping

```json
[
  {
    "Presult.S": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
WHILERW Presult.S, Xop1, Xop2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/WHILERW--While-free-of-read-after-write-conflicts-

### Operation

Source operation ID: `SveOperation_svwhilerw_bf16`

**Operation**



Consider a hypothetical loop:



```text
for (int i = 0; i < n; ++i) {
  op1[i] = …;
  … = op2[i];
}
```



and return a predicate in which element *j* is active if *j*+1 iterations of the loop could be performed in parallel without changing the dependencies between `op1` and `op2`. The first element of the result is always active.

## svwhilerw[_f64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwhilerw%5B_f64%5D

### Signature (source notation)

```c
svbool_t svwhilerw[_f64](const float64_t *op1, const float64_t *op2);
```

### Description

While free of read-after-write conflicts

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Initialization / Detect hazards

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
  "return_base_type": "bool",
  "element_bit_size": "64",
  "value": "svbool_t"
}
```

### Argument preparation and constraints

```json
{
  "op1": {
    "register": "Xop1"
  },
  "op2": {
    "register": "Xop2"
  }
}
```

### Result mapping

```json
[
  {
    "Presult.D": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
WHILERW Presult.D, Xop1, Xop2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/WHILERW--While-free-of-read-after-write-conflicts-

### Operation

Source operation ID: `SveOperation_svwhilerw_bf16`

**Operation**



Consider a hypothetical loop:



```text
for (int i = 0; i < n; ++i) {
  op1[i] = …;
  … = op2[i];
}
```



and return a predicate in which element *j* is active if *j*+1 iterations of the loop could be performed in parallel without changing the dependencies between `op1` and `op2`. The first element of the result is always active.

## svwhilerw[_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwhilerw%5B_s16%5D

### Signature (source notation)

```c
svbool_t svwhilerw[_s16](const int16_t *op1, const int16_t *op2);
```

### Description

While free of read-after-write conflicts

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Initialization / Detect hazards

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
  "return_base_type": "bool",
  "element_bit_size": "16",
  "value": "svbool_t"
}
```

### Argument preparation and constraints

```json
{
  "op1": {
    "register": "Xop1"
  },
  "op2": {
    "register": "Xop2"
  }
}
```

### Result mapping

```json
[
  {
    "Presult.H": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
WHILERW Presult.H, Xop1, Xop2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/WHILERW--While-free-of-read-after-write-conflicts-

### Operation

Source operation ID: `SveOperation_svwhilerw_bf16`

**Operation**



Consider a hypothetical loop:



```text
for (int i = 0; i < n; ++i) {
  op1[i] = …;
  … = op2[i];
}
```



and return a predicate in which element *j* is active if *j*+1 iterations of the loop could be performed in parallel without changing the dependencies between `op1` and `op2`. The first element of the result is always active.

## svwhilerw[_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwhilerw%5B_s32%5D

### Signature (source notation)

```c
svbool_t svwhilerw[_s32](const int32_t *op1, const int32_t *op2);
```

### Description

While free of read-after-write conflicts

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Initialization / Detect hazards

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
  "return_base_type": "bool",
  "element_bit_size": "32",
  "value": "svbool_t"
}
```

### Argument preparation and constraints

```json
{
  "op1": {
    "register": "Xop1"
  },
  "op2": {
    "register": "Xop2"
  }
}
```

### Result mapping

```json
[
  {
    "Presult.S": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
WHILERW Presult.S, Xop1, Xop2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/WHILERW--While-free-of-read-after-write-conflicts-

### Operation

Source operation ID: `SveOperation_svwhilerw_bf16`

**Operation**



Consider a hypothetical loop:



```text
for (int i = 0; i < n; ++i) {
  op1[i] = …;
  … = op2[i];
}
```



and return a predicate in which element *j* is active if *j*+1 iterations of the loop could be performed in parallel without changing the dependencies between `op1` and `op2`. The first element of the result is always active.

## svwhilerw[_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwhilerw%5B_s64%5D

### Signature (source notation)

```c
svbool_t svwhilerw[_s64](const int64_t *op1, const int64_t *op2);
```

### Description

While free of read-after-write conflicts

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Initialization / Detect hazards

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
  "return_base_type": "bool",
  "element_bit_size": "64",
  "value": "svbool_t"
}
```

### Argument preparation and constraints

```json
{
  "op1": {
    "register": "Xop1"
  },
  "op2": {
    "register": "Xop2"
  }
}
```

### Result mapping

```json
[
  {
    "Presult.D": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
WHILERW Presult.D, Xop1, Xop2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/WHILERW--While-free-of-read-after-write-conflicts-

### Operation

Source operation ID: `SveOperation_svwhilerw_bf16`

**Operation**



Consider a hypothetical loop:



```text
for (int i = 0; i < n; ++i) {
  op1[i] = …;
  … = op2[i];
}
```



and return a predicate in which element *j* is active if *j*+1 iterations of the loop could be performed in parallel without changing the dependencies between `op1` and `op2`. The first element of the result is always active.

## svwhilerw[_s8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwhilerw%5B_s8%5D

### Signature (source notation)

```c
svbool_t svwhilerw[_s8](const int8_t *op1, const int8_t *op2);
```

### Description

While free of read-after-write conflicts

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Initialization / Detect hazards

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
  "return_base_type": "bool",
  "element_bit_size": "8",
  "value": "svbool_t"
}
```

### Argument preparation and constraints

```json
{
  "op1": {
    "register": "Xop1"
  },
  "op2": {
    "register": "Xop2"
  }
}
```

### Result mapping

```json
[
  {
    "Presult.B": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
WHILERW Presult.B, Xop1, Xop2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/WHILERW--While-free-of-read-after-write-conflicts-

### Operation

Source operation ID: `SveOperation_svwhilerw_bf16`

**Operation**



Consider a hypothetical loop:



```text
for (int i = 0; i < n; ++i) {
  op1[i] = …;
  … = op2[i];
}
```



and return a predicate in which element *j* is active if *j*+1 iterations of the loop could be performed in parallel without changing the dependencies between `op1` and `op2`. The first element of the result is always active.

## svwhilerw[_u16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwhilerw%5B_u16%5D

### Signature (source notation)

```c
svbool_t svwhilerw[_u16](const uint16_t *op1, const uint16_t *op2);
```

### Description

While free of read-after-write conflicts

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Initialization / Detect hazards

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
  "return_base_type": "bool",
  "element_bit_size": "16",
  "value": "svbool_t"
}
```

### Argument preparation and constraints

```json
{
  "op1": {
    "register": "Xop1"
  },
  "op2": {
    "register": "Xop2"
  }
}
```

### Result mapping

```json
[
  {
    "Presult.H": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
WHILERW Presult.H, Xop1, Xop2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/WHILERW--While-free-of-read-after-write-conflicts-

### Operation

Source operation ID: `SveOperation_svwhilerw_bf16`

**Operation**



Consider a hypothetical loop:



```text
for (int i = 0; i < n; ++i) {
  op1[i] = …;
  … = op2[i];
}
```



and return a predicate in which element *j* is active if *j*+1 iterations of the loop could be performed in parallel without changing the dependencies between `op1` and `op2`. The first element of the result is always active.

## svwhilerw[_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwhilerw%5B_u32%5D

### Signature (source notation)

```c
svbool_t svwhilerw[_u32](const uint32_t *op1, const uint32_t *op2);
```

### Description

While free of read-after-write conflicts

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Initialization / Detect hazards

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
  "return_base_type": "bool",
  "element_bit_size": "32",
  "value": "svbool_t"
}
```

### Argument preparation and constraints

```json
{
  "op1": {
    "register": "Xop1"
  },
  "op2": {
    "register": "Xop2"
  }
}
```

### Result mapping

```json
[
  {
    "Presult.S": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
WHILERW Presult.S, Xop1, Xop2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/WHILERW--While-free-of-read-after-write-conflicts-

### Operation

Source operation ID: `SveOperation_svwhilerw_bf16`

**Operation**



Consider a hypothetical loop:



```text
for (int i = 0; i < n; ++i) {
  op1[i] = …;
  … = op2[i];
}
```



and return a predicate in which element *j* is active if *j*+1 iterations of the loop could be performed in parallel without changing the dependencies between `op1` and `op2`. The first element of the result is always active.

## svwhilerw[_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwhilerw%5B_u64%5D

### Signature (source notation)

```c
svbool_t svwhilerw[_u64](const uint64_t *op1, const uint64_t *op2);
```

### Description

While free of read-after-write conflicts

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Initialization / Detect hazards

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
  "return_base_type": "bool",
  "element_bit_size": "64",
  "value": "svbool_t"
}
```

### Argument preparation and constraints

```json
{
  "op1": {
    "register": "Xop1"
  },
  "op2": {
    "register": "Xop2"
  }
}
```

### Result mapping

```json
[
  {
    "Presult.D": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
WHILERW Presult.D, Xop1, Xop2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/WHILERW--While-free-of-read-after-write-conflicts-

### Operation

Source operation ID: `SveOperation_svwhilerw_bf16`

**Operation**



Consider a hypothetical loop:



```text
for (int i = 0; i < n; ++i) {
  op1[i] = …;
  … = op2[i];
}
```



and return a predicate in which element *j* is active if *j*+1 iterations of the loop could be performed in parallel without changing the dependencies between `op1` and `op2`. The first element of the result is always active.

## svwhilerw[_u8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwhilerw%5B_u8%5D

### Signature (source notation)

```c
svbool_t svwhilerw[_u8](const uint8_t *op1, const uint8_t *op2);
```

### Description

While free of read-after-write conflicts

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Initialization / Detect hazards

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
  "return_base_type": "bool",
  "element_bit_size": "8",
  "value": "svbool_t"
}
```

### Argument preparation and constraints

```json
{
  "op1": {
    "register": "Xop1"
  },
  "op2": {
    "register": "Xop2"
  }
}
```

### Result mapping

```json
[
  {
    "Presult.B": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
WHILERW Presult.B, Xop1, Xop2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/WHILERW--While-free-of-read-after-write-conflicts-

### Operation

Source operation ID: `SveOperation_svwhilerw_bf16`

**Operation**



Consider a hypothetical loop:



```text
for (int i = 0; i < n; ++i) {
  op1[i] = …;
  … = op2[i];
}
```



and return a predicate in which element *j* is active if *j*+1 iterations of the loop could be performed in parallel without changing the dependencies between `op1` and `op2`. The first element of the result is always active.

## svwhilewr[_bf16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwhilewr%5B_bf16%5D

### Signature (source notation)

```c
svbool_t svwhilewr[_bf16](const bfloat16_t *op1, const bfloat16_t *op2);
```

### Description

While free of write-after-read conflicts

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Initialization / Detect hazards

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
  "return_base_type": "bool",
  "element_bit_size": "16",
  "value": "svbool_t"
}
```

### Argument preparation and constraints

```json
{
  "op1": {
    "register": "Xop1"
  },
  "op2": {
    "register": "Xop2"
  }
}
```

### Result mapping

```json
[
  {
    "Presult.H": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
WHILEWR Presult.H, Xop1, Xop2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/WHILEWR--While-free-of-write-after-read-write-conflicts-

### Operation

Source operation ID: `SveOperation_svwhilewr_bf16`

**Operation**



Consider a hypothetical loop:



```text
for (int i = 0; i < n; ++i) {
  … = op1[i];
  op2[i] = …;
}
```



and return a predicate in which element *j* is active if *j*+1 iterations of the loop could be performed in parallel without changing the dependencies between `op1` and `op2`. The first element of the result is always active.

## svwhilewr[_f16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwhilewr%5B_f16%5D

### Signature (source notation)

```c
svbool_t svwhilewr[_f16](const float16_t *op1, const float16_t *op2);
```

### Description

While free of write-after-read conflicts

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Initialization / Detect hazards

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
  "return_base_type": "bool",
  "element_bit_size": "16",
  "value": "svbool_t"
}
```

### Argument preparation and constraints

```json
{
  "op1": {
    "register": "Xop1"
  },
  "op2": {
    "register": "Xop2"
  }
}
```

### Result mapping

```json
[
  {
    "Presult.H": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
WHILEWR Presult.H, Xop1, Xop2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/WHILEWR--While-free-of-write-after-read-write-conflicts-

### Operation

Source operation ID: `SveOperation_svwhilewr_bf16`

**Operation**



Consider a hypothetical loop:



```text
for (int i = 0; i < n; ++i) {
  … = op1[i];
  op2[i] = …;
}
```



and return a predicate in which element *j* is active if *j*+1 iterations of the loop could be performed in parallel without changing the dependencies between `op1` and `op2`. The first element of the result is always active.

## svwhilewr[_f32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwhilewr%5B_f32%5D

### Signature (source notation)

```c
svbool_t svwhilewr[_f32](const float32_t *op1, const float32_t *op2);
```

### Description

While free of write-after-read conflicts

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Initialization / Detect hazards

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
  "return_base_type": "bool",
  "element_bit_size": "32",
  "value": "svbool_t"
}
```

### Argument preparation and constraints

```json
{
  "op1": {
    "register": "Xop1"
  },
  "op2": {
    "register": "Xop2"
  }
}
```

### Result mapping

```json
[
  {
    "Presult.S": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
WHILEWR Presult.S, Xop1, Xop2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/WHILEWR--While-free-of-write-after-read-write-conflicts-

### Operation

Source operation ID: `SveOperation_svwhilewr_bf16`

**Operation**



Consider a hypothetical loop:



```text
for (int i = 0; i < n; ++i) {
  … = op1[i];
  op2[i] = …;
}
```



and return a predicate in which element *j* is active if *j*+1 iterations of the loop could be performed in parallel without changing the dependencies between `op1` and `op2`. The first element of the result is always active.

## svwhilewr[_f64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwhilewr%5B_f64%5D

### Signature (source notation)

```c
svbool_t svwhilewr[_f64](const float64_t *op1, const float64_t *op2);
```

### Description

While free of write-after-read conflicts

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Initialization / Detect hazards

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
  "return_base_type": "bool",
  "element_bit_size": "64",
  "value": "svbool_t"
}
```

### Argument preparation and constraints

```json
{
  "op1": {
    "register": "Xop1"
  },
  "op2": {
    "register": "Xop2"
  }
}
```

### Result mapping

```json
[
  {
    "Presult.D": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
WHILEWR Presult.D, Xop1, Xop2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/WHILEWR--While-free-of-write-after-read-write-conflicts-

### Operation

Source operation ID: `SveOperation_svwhilewr_bf16`

**Operation**



Consider a hypothetical loop:



```text
for (int i = 0; i < n; ++i) {
  … = op1[i];
  op2[i] = …;
}
```



and return a predicate in which element *j* is active if *j*+1 iterations of the loop could be performed in parallel without changing the dependencies between `op1` and `op2`. The first element of the result is always active.

## svwhilewr[_s16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwhilewr%5B_s16%5D

### Signature (source notation)

```c
svbool_t svwhilewr[_s16](const int16_t *op1, const int16_t *op2);
```

### Description

While free of write-after-read conflicts

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Initialization / Detect hazards

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
  "return_base_type": "bool",
  "element_bit_size": "16",
  "value": "svbool_t"
}
```

### Argument preparation and constraints

```json
{
  "op1": {
    "register": "Xop1"
  },
  "op2": {
    "register": "Xop2"
  }
}
```

### Result mapping

```json
[
  {
    "Presult.H": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
WHILEWR Presult.H, Xop1, Xop2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/WHILEWR--While-free-of-write-after-read-write-conflicts-

### Operation

Source operation ID: `SveOperation_svwhilewr_bf16`

**Operation**



Consider a hypothetical loop:



```text
for (int i = 0; i < n; ++i) {
  … = op1[i];
  op2[i] = …;
}
```



and return a predicate in which element *j* is active if *j*+1 iterations of the loop could be performed in parallel without changing the dependencies between `op1` and `op2`. The first element of the result is always active.

## svwhilewr[_s32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwhilewr%5B_s32%5D

### Signature (source notation)

```c
svbool_t svwhilewr[_s32](const int32_t *op1, const int32_t *op2);
```

### Description

While free of write-after-read conflicts

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Initialization / Detect hazards

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
  "return_base_type": "bool",
  "element_bit_size": "32",
  "value": "svbool_t"
}
```

### Argument preparation and constraints

```json
{
  "op1": {
    "register": "Xop1"
  },
  "op2": {
    "register": "Xop2"
  }
}
```

### Result mapping

```json
[
  {
    "Presult.S": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
WHILEWR Presult.S, Xop1, Xop2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/WHILEWR--While-free-of-write-after-read-write-conflicts-

### Operation

Source operation ID: `SveOperation_svwhilewr_bf16`

**Operation**



Consider a hypothetical loop:



```text
for (int i = 0; i < n; ++i) {
  … = op1[i];
  op2[i] = …;
}
```



and return a predicate in which element *j* is active if *j*+1 iterations of the loop could be performed in parallel without changing the dependencies between `op1` and `op2`. The first element of the result is always active.

## svwhilewr[_s64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwhilewr%5B_s64%5D

### Signature (source notation)

```c
svbool_t svwhilewr[_s64](const int64_t *op1, const int64_t *op2);
```

### Description

While free of write-after-read conflicts

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Initialization / Detect hazards

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
  "return_base_type": "bool",
  "element_bit_size": "64",
  "value": "svbool_t"
}
```

### Argument preparation and constraints

```json
{
  "op1": {
    "register": "Xop1"
  },
  "op2": {
    "register": "Xop2"
  }
}
```

### Result mapping

```json
[
  {
    "Presult.D": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
WHILEWR Presult.D, Xop1, Xop2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/WHILEWR--While-free-of-write-after-read-write-conflicts-

### Operation

Source operation ID: `SveOperation_svwhilewr_bf16`

**Operation**



Consider a hypothetical loop:



```text
for (int i = 0; i < n; ++i) {
  … = op1[i];
  op2[i] = …;
}
```



and return a predicate in which element *j* is active if *j*+1 iterations of the loop could be performed in parallel without changing the dependencies between `op1` and `op2`. The first element of the result is always active.

## svwhilewr[_s8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwhilewr%5B_s8%5D

### Signature (source notation)

```c
svbool_t svwhilewr[_s8](const int8_t *op1, const int8_t *op2);
```

### Description

While free of write-after-read conflicts

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Initialization / Detect hazards

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
  "return_base_type": "bool",
  "element_bit_size": "8",
  "value": "svbool_t"
}
```

### Argument preparation and constraints

```json
{
  "op1": {
    "register": "Xop1"
  },
  "op2": {
    "register": "Xop2"
  }
}
```

### Result mapping

```json
[
  {
    "Presult.B": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
WHILEWR Presult.B, Xop1, Xop2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/WHILEWR--While-free-of-write-after-read-write-conflicts-

### Operation

Source operation ID: `SveOperation_svwhilewr_bf16`

**Operation**



Consider a hypothetical loop:



```text
for (int i = 0; i < n; ++i) {
  … = op1[i];
  op2[i] = …;
}
```



and return a predicate in which element *j* is active if *j*+1 iterations of the loop could be performed in parallel without changing the dependencies between `op1` and `op2`. The first element of the result is always active.

## svwhilewr[_u16]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwhilewr%5B_u16%5D

### Signature (source notation)

```c
svbool_t svwhilewr[_u16](const uint16_t *op1, const uint16_t *op2);
```

### Description

While free of write-after-read conflicts

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Initialization / Detect hazards

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
  "return_base_type": "bool",
  "element_bit_size": "16",
  "value": "svbool_t"
}
```

### Argument preparation and constraints

```json
{
  "op1": {
    "register": "Xop1"
  },
  "op2": {
    "register": "Xop2"
  }
}
```

### Result mapping

```json
[
  {
    "Presult.H": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
WHILEWR Presult.H, Xop1, Xop2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/WHILEWR--While-free-of-write-after-read-write-conflicts-

### Operation

Source operation ID: `SveOperation_svwhilewr_bf16`

**Operation**



Consider a hypothetical loop:



```text
for (int i = 0; i < n; ++i) {
  … = op1[i];
  op2[i] = …;
}
```



and return a predicate in which element *j* is active if *j*+1 iterations of the loop could be performed in parallel without changing the dependencies between `op1` and `op2`. The first element of the result is always active.

## svwhilewr[_u32]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwhilewr%5B_u32%5D

### Signature (source notation)

```c
svbool_t svwhilewr[_u32](const uint32_t *op1, const uint32_t *op2);
```

### Description

While free of write-after-read conflicts

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Initialization / Detect hazards

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
  "return_base_type": "bool",
  "element_bit_size": "32",
  "value": "svbool_t"
}
```

### Argument preparation and constraints

```json
{
  "op1": {
    "register": "Xop1"
  },
  "op2": {
    "register": "Xop2"
  }
}
```

### Result mapping

```json
[
  {
    "Presult.S": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
WHILEWR Presult.S, Xop1, Xop2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/WHILEWR--While-free-of-write-after-read-write-conflicts-

### Operation

Source operation ID: `SveOperation_svwhilewr_bf16`

**Operation**



Consider a hypothetical loop:



```text
for (int i = 0; i < n; ++i) {
  … = op1[i];
  op2[i] = …;
}
```



and return a predicate in which element *j* is active if *j*+1 iterations of the loop could be performed in parallel without changing the dependencies between `op1` and `op2`. The first element of the result is always active.

## svwhilewr[_u64]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwhilewr%5B_u64%5D

### Signature (source notation)

```c
svbool_t svwhilewr[_u64](const uint64_t *op1, const uint64_t *op2);
```

### Description

While free of write-after-read conflicts

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Initialization / Detect hazards

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
  "return_base_type": "bool",
  "element_bit_size": "64",
  "value": "svbool_t"
}
```

### Argument preparation and constraints

```json
{
  "op1": {
    "register": "Xop1"
  },
  "op2": {
    "register": "Xop2"
  }
}
```

### Result mapping

```json
[
  {
    "Presult.D": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
WHILEWR Presult.D, Xop1, Xop2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/WHILEWR--While-free-of-write-after-read-write-conflicts-

### Operation

Source operation ID: `SveOperation_svwhilewr_bf16`

**Operation**



Consider a hypothetical loop:



```text
for (int i = 0; i < n; ++i) {
  … = op1[i];
  op2[i] = …;
}
```



and return a predicate in which element *j* is active if *j*+1 iterations of the loop could be performed in parallel without changing the dependencies between `op1` and `op2`. The first element of the result is always active.

## svwhilewr[_u8]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svwhilewr%5B_u8%5D

### Signature (source notation)

```c
svbool_t svwhilewr[_u8](const uint8_t *op1, const uint8_t *op2);
```

### Description

While free of write-after-read conflicts

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Initialization / Detect hazards

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
  "return_base_type": "bool",
  "element_bit_size": "8",
  "value": "svbool_t"
}
```

### Argument preparation and constraints

```json
{
  "op1": {
    "register": "Xop1"
  },
  "op2": {
    "register": "Xop2"
  }
}
```

### Result mapping

```json
[
  {
    "Presult.B": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to the following instruction:

```asm
WHILEWR Presult.B, Xop1, Xop2
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/WHILEWR--While-free-of-write-after-read-write-conflicts-

### Operation

Source operation ID: `SveOperation_svwhilewr_bf16`

**Operation**



Consider a hypothetical loop:



```text
for (int i = 0; i < n; ++i) {
  … = op1[i];
  op2[i] = …;
}
```



and return a predicate in which element *j* is active if *j*+1 iterations of the loop could be performed in parallel without changing the dependencies between `op1` and `op2`. The first element of the result is always active.

