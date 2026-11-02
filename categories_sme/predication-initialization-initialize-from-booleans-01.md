# SME / Predication / Initialization / Initialize from booleans — Part 1

## svdup[_n]_b16

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdup%5B_n%5D_b16

### Signature (source notation)

```c
svbool_t svdup[_n]_b16(bool op);
```

### Description

Broadcast a scalar value

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Predication / Initialization / Initialize from booleans

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

Not supplied by source.

### Result mapping

Not supplied by source.

### Instruction mapping

Not supplied by source.

### Operation

Source operation ID: `SveOperation_svdup_n_b8`

**Operation**



Return a vector in which each element *i* contains `op`.

## svdup[_n]_b32

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdup%5B_n%5D_b32

### Signature (source notation)

```c
svbool_t svdup[_n]_b32(bool op);
```

### Description

Broadcast a scalar value

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Predication / Initialization / Initialize from booleans

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

Not supplied by source.

### Result mapping

Not supplied by source.

### Instruction mapping

Not supplied by source.

### Operation

Source operation ID: `SveOperation_svdup_n_b8`

**Operation**



Return a vector in which each element *i* contains `op`.

## svdup[_n]_b64

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdup%5B_n%5D_b64

### Signature (source notation)

```c
svbool_t svdup[_n]_b64(bool op);
```

### Description

Broadcast a scalar value

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Predication / Initialization / Initialize from booleans

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

Not supplied by source.

### Result mapping

Not supplied by source.

### Instruction mapping

Not supplied by source.

### Operation

Source operation ID: `SveOperation_svdup_n_b8`

**Operation**



Return a vector in which each element *i* contains `op`.

## svdup[_n]_b8

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdup%5B_n%5D_b8

### Signature (source notation)

```c
svbool_t svdup[_n]_b8(bool op);
```

### Description

Broadcast a scalar value

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Predication / Initialization / Initialize from booleans

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

Not supplied by source.

### Result mapping

Not supplied by source.

### Instruction mapping

Not supplied by source.

### Operation

Source operation ID: `SveOperation_svdup_n_b8`

**Operation**



Return a vector in which each element *i* contains `op`.

## svdupq[_n]_b16

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdupq%5B_n%5D_b16

### Signature (source notation)

```c
svbool_t svdupq[_n]_b16(bool x0, bool x1, bool x2, bool x3, bool x4, bool x5, bool x6, bool x7);
```

### Description

Broadcast a quadword of scalars

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Predication / Initialization / Initialize from booleans

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

Not supplied by source.

### Result mapping

Not supplied by source.

### Instruction mapping

Not supplied by source.

### Operation

Source operation ID: `SveOperation_svdupq_n_b16`

**Operation**



Return a predicate in which 2-bit element *i* contains `x[i%8]` (where `x[0]` refers to `x0`, and so on).

## svdupq[_n]_b32

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdupq%5B_n%5D_b32

### Signature (source notation)

```c
svbool_t svdupq[_n]_b32(bool x0, bool x1, bool x2, bool x3);
```

### Description

Broadcast a quadword of scalars

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Predication / Initialization / Initialize from booleans

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

Not supplied by source.

### Result mapping

Not supplied by source.

### Instruction mapping

Not supplied by source.

### Operation

Source operation ID: `SveOperation_svdupq_n_b32`

**Operation**



Return a predicate in which 4-bit element *i* contains `x[i%4]` (where `x[0]` refers to `x0`, and so on).

## svdupq[_n]_b64

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdupq%5B_n%5D_b64

### Signature (source notation)

```c
svbool_t svdupq[_n]_b64(bool x0, bool x1);
```

### Description

Broadcast a quadword of scalars

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Predication / Initialization / Initialize from booleans

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

Not supplied by source.

### Result mapping

Not supplied by source.

### Instruction mapping

Not supplied by source.

### Operation

Source operation ID: `SveOperation_svdupq_n_b64`

**Operation**



Return a predicate in which 8-bit element *i* contains `x[i%2]` (where `x[0]` refers to `x0`, and so on).

## svdupq[_n]_b8

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svdupq%5B_n%5D_b8

### Signature (source notation)

```c
svbool_t svdupq[_n]_b8(bool x0, bool x1, bool x2, bool x3, bool x4, bool x5, bool x6, bool x7, bool x8, bool x9, bool x10, bool x11, bool x12, bool x13, bool x14, bool x15);
```

### Description

Broadcast a quadword of scalars

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Predication / Initialization / Initialize from booleans

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

Not supplied by source.

### Result mapping

Not supplied by source.

### Instruction mapping

Not supplied by source.

### Operation

Source operation ID: `SveOperation_svdupq_n_b8`

**Operation**



Return a predicate in which element *i* contains `x[i%16]` (where `x[0]` refers to `x0`, and so on).

