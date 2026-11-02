# SME / Prefetch / Consecutive — Part 1

## svprfb

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svprfb

### Signature (source notation)

```c
void svprfb(svbool_t pg, const void *base, enum svprfop op);
```

### Description

Prefetch bytes

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Prefetch / Consecutive

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
  "value": "void"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Pg"
  },
  "base": {
    "register": "Xbase"
  }
}
```

### Result mapping

```json
[]
```

### Instruction mapping

When base has the form &array[index], this intrinsic can use:

```asm
PRFB op, Pg, [Xarray, Xindex]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/PRFB--scalar-plus-scalar---Contiguous-prefetch-bytes--scalar-index--

The general implementation is:

```asm
PRFB op, Pg, [Xbase, #0, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/PRFB--scalar-plus-immediate---Contiguous-prefetch-bytes--immediate-index--

### Operation

Source operation ID: `SveOperation_svprfb`

**Operation**



For each active element *i*, provide a prefetch hint for the 8-bit data at address:



```text
(uint8_t *)base + i
```

## svprfb_vnum

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svprfb_vnum

### Signature (source notation)

```c
void svprfb_vnum(svbool_t pg, const void *base, int64_t vnum, enum svprfop op);
```

### Description

Prefetch bytes

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Prefetch / Consecutive

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
  "value": "void"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Pg"
  },
  "base": {
    "register": "Xbase"
  },
  "vnum * svcntb()": {
    "register": "Xindex"
  }
}
```

### Result mapping

```json
[]
```

### Instruction mapping

When vnum is in the range [-32, 31], this intrinsic can use:

```asm
PRFB op, Pg, [Xbase, #vnum, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/PRFB--scalar-plus-immediate---Contiguous-prefetch-bytes--immediate-index--

The general implementation is:

```asm
PRFB op, Pg, [Xbase, Xindex]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/PRFB--scalar-plus-scalar---Contiguous-prefetch-bytes--scalar-index--

### Operation

Source operation ID: `SveOperation_svprfb_vnum`

**Operation**



For each active element *i*, provide a prefetch hint for the 8-bit data at address:



```text
(uint8_t *)base + n * vnum + i
```



where *n* is the number of 8-bit elements in a vector.

## svprfd

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svprfd

### Signature (source notation)

```c
void svprfd(svbool_t pg, const void *base, enum svprfop op);
```

### Description

Prefetch doublewords

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Prefetch / Consecutive

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
  "value": "void"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Pg"
  },
  "base": {
    "register": "Xbase"
  }
}
```

### Result mapping

```json
[]
```

### Instruction mapping

When base has the form &array[index], this intrinsic can use:

```asm
PRFD op, Pg, [Xarray, Xindex, LSL #3]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/PRFD--scalar-plus-scalar---Contiguous-prefetch-doublewords--scalar-index--

The general implementation is:

```asm
PRFD op, Pg, [Xbase, #0, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/PRFD--scalar-plus-immediate---Contiguous-prefetch-doublewords--immediate-index--

### Operation

Source operation ID: `SveOperation_svprfd`

**Operation**



For each active element *i*, provide a prefetch hint for the 64-bit data at address:



```text
(int64_t *)base + i
```

## svprfd_vnum

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svprfd_vnum

### Signature (source notation)

```c
void svprfd_vnum(svbool_t pg, const void *base, int64_t vnum, enum svprfop op);
```

### Description

Prefetch doublewords

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Prefetch / Consecutive

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
  "value": "void"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Pg"
  },
  "base": {
    "register": "Xbase"
  },
  "vnum * svcntd()": {
    "register": "Xindex"
  }
}
```

### Result mapping

```json
[]
```

### Instruction mapping

When vnum is in the range [-32, 31], this intrinsic can use:

```asm
PRFD op, Pg, [Xbase, #vnum, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/PRFD--scalar-plus-immediate---Contiguous-prefetch-doublewords--immediate-index--

The general implementation is:

```asm
PRFD op, Pg, [Xbase, Xindex, LSL #3]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/PRFD--scalar-plus-scalar---Contiguous-prefetch-doublewords--scalar-index--

### Operation

Source operation ID: `SveOperation_svprfd_vnum`

**Operation**



For each active element *i*, provide a prefetch hint for the 64-bit data at address:



```text
(int64_t *)base + n * vnum + i
```



where *n* is the number of 64-bit elements in a vector.

## svprfh

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svprfh

### Signature (source notation)

```c
void svprfh(svbool_t pg, const void *base, enum svprfop op);
```

### Description

Prefetch halfwords

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Prefetch / Consecutive

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
  "value": "void"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Pg"
  },
  "base": {
    "register": "Xbase"
  }
}
```

### Result mapping

```json
[]
```

### Instruction mapping

When base has the form &array[index], this intrinsic can use:

```asm
PRFH op, Pg, [Xarray, Xindex, LSL #1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/PRFH--scalar-plus-scalar---Contiguous-prefetch-halfwords--scalar-index--

The general implementation is:

```asm
PRFH op, Pg, [Xbase, #0, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/PRFH--scalar-plus-immediate---Contiguous-prefetch-halfwords--immediate-index--

### Operation

Source operation ID: `SveOperation_svprfh`

**Operation**



For each active element *i*, provide a prefetch hint for the 16-bit data at address:



```text
(uint16_t *)base + i
```

## svprfh_vnum

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svprfh_vnum

### Signature (source notation)

```c
void svprfh_vnum(svbool_t pg, const void *base, int64_t vnum, enum svprfop op);
```

### Description

Prefetch halfwords

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Prefetch / Consecutive

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
  "value": "void"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Pg"
  },
  "base": {
    "register": "Xbase"
  },
  "vnum * svcnth()": {
    "register": "Xindex"
  }
}
```

### Result mapping

```json
[]
```

### Instruction mapping

When vnum is in the range [-32, 31], this intrinsic can use:

```asm
PRFH op, Pg, [Xbase, #vnum, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/PRFH--scalar-plus-immediate---Contiguous-prefetch-halfwords--immediate-index--

The general implementation is:

```asm
PRFH op, Pg, [Xbase, Xindex, LSL #1]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/PRFH--scalar-plus-scalar---Contiguous-prefetch-halfwords--scalar-index--

### Operation

Source operation ID: `SveOperation_svprfh_vnum`

**Operation**



For each active element *i*, provide a prefetch hint for the 16-bit data at address:



```text
(uint16_t *)base + n * vnum + i
```



where *n* is the number of 16-bit elements in a vector.

## svprfw

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svprfw

### Signature (source notation)

```c
void svprfw(svbool_t pg, const void *base, enum svprfop op);
```

### Description

Prefetch words

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Prefetch / Consecutive

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
  "value": "void"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Pg"
  },
  "base": {
    "register": "Xbase"
  }
}
```

### Result mapping

```json
[]
```

### Instruction mapping

When base has the form &array[index], this intrinsic can use:

```asm
PRFW op, Pg, [Xarray, Xindex, LSL #2]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/PRFW--scalar-plus-scalar---Contiguous-prefetch-words--scalar-index--

The general implementation is:

```asm
PRFW op, Pg, [Xbase, #0, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/PRFW--scalar-plus-immediate---Contiguous-prefetch-words--immediate-index--

### Operation

Source operation ID: `SveOperation_svprfw`

**Operation**



For each active element *i*, provide a prefetch hint for the 32-bit data at address:



```text
(int32_t *)base + i
```

## svprfw_vnum

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svprfw_vnum

### Signature (source notation)

```c
void svprfw_vnum(svbool_t pg, const void *base, int64_t vnum, enum svprfop op);
```

### Description

Prefetch words

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Prefetch / Consecutive

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
  "value": "void"
}
```

### Argument preparation and constraints

```json
{
  "pg": {
    "register": "Pg"
  },
  "base": {
    "register": "Xbase"
  },
  "vnum * svcntw()": {
    "register": "Xindex"
  }
}
```

### Result mapping

```json
[]
```

### Instruction mapping

When vnum is in the range [-32, 31], this intrinsic can use:

```asm
PRFW op, Pg, [Xbase, #vnum, MUL VL]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/PRFW--scalar-plus-immediate---Contiguous-prefetch-words--immediate-index--

The general implementation is:

```asm
PRFW op, Pg, [Xbase, Xindex, LSL #2]
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/PRFW--scalar-plus-scalar---Contiguous-prefetch-words--scalar-index--

### Operation

Source operation ID: `SveOperation_svprfw_vnum`

**Operation**



For each active element *i*, provide a prefetch hint for the 32-bit data at address:



```text
(int32_t *)base + n * vnum + i
```



where *n* is the number of 32-bit elements in a vector.

