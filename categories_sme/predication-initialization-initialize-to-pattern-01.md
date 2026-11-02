# SME / Predication / Initialization / Initialize to pattern — Part 1

## svpfalse[_b]

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svpfalse%5B_b%5D

### Signature (source notation)

```c
svbool_t svpfalse[_b]();
```

### Description

Set all predicate elements to false

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Predication / Initialization / Initialize to pattern

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
{}
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
PFALSE Presult.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/PFALSE--Set-all-predicate-elements-to-false-

### Operation

Source operation ID: `SveOperation_svpfalse_b`

**Operation**



Return a predicate in which every element is false (zero).

## svpfalse_c

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svpfalse_c

### Signature (source notation)

```c
svcount_t svpfalse_c();
```

### Description

Set all predicate elements to false

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Initialization / Initialize to pattern

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
  "return_base_type": "count",
  "element_bit_size": "32",
  "value": "svcount_t"
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
    "Preg1.B": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
PFALSE Preg1.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/PFALSE--Set-all-predicate-elements-to-false-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svptrue_b16

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svptrue_b16

### Signature (source notation)

```c
svbool_t svptrue_b16();
```

### Description

Set predicate elements to true

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Predication / Initialization / Initialize to pattern

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
{}
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
PTRUE Presult.H, ALL
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/PTRUE--predicate---Initialize-predicate-from-named-constraint-

### Operation

Source operation ID: `SveOperation_svptrue_b16`

**Operation**



Return a predicate in which every element is true (one). Only the lowest bit of each element is set; the upper bits are always zero.

## svptrue_b32

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svptrue_b32

### Signature (source notation)

```c
svbool_t svptrue_b32();
```

### Description

Set predicate elements to true

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Predication / Initialization / Initialize to pattern

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
{}
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
PTRUE Presult.S, ALL
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/PTRUE--predicate---Initialize-predicate-from-named-constraint-

### Operation

Source operation ID: `SveOperation_svptrue_b16`

**Operation**



Return a predicate in which every element is true (one). Only the lowest bit of each element is set; the upper bits are always zero.

## svptrue_b64

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svptrue_b64

### Signature (source notation)

```c
svbool_t svptrue_b64();
```

### Description

Set predicate elements to true

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Predication / Initialization / Initialize to pattern

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
{}
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
PTRUE Presult.D, ALL
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/PTRUE--predicate---Initialize-predicate-from-named-constraint-

### Operation

Source operation ID: `SveOperation_svptrue_b16`

**Operation**



Return a predicate in which every element is true (one). Only the lowest bit of each element is set; the upper bits are always zero.

## svptrue_b8

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svptrue_b8

### Signature (source notation)

```c
svbool_t svptrue_b8();
```

### Description

Set predicate elements to true

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Predication / Initialization / Initialize to pattern

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
{}
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
PTRUE Presult.B, ALL
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/PTRUE--predicate---Initialize-predicate-from-named-constraint-

### Operation

Source operation ID: `SveOperation_svptrue_b8`

**Operation**



Return a predicate in which every element is true (one).

## svptrue_c16

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svptrue_c16

### Signature (source notation)

```c
svcount_t svptrue_c16();
```

### Description

Initialize predicate-as-counter to all active

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Initialization / Initialize to pattern

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
  "return_base_type": "count",
  "element_bit_size": "16",
  "value": "svcount_t"
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
    "PNreg1.H": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
PTRUE PNreg1.H
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/PTRUE--predicate-as-counter---Initialize-predicate-as-counter-to-all-active-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svptrue_c32

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svptrue_c32

### Signature (source notation)

```c
svcount_t svptrue_c32();
```

### Description

Initialize predicate-as-counter to all active

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Initialization / Initialize to pattern

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
  "return_base_type": "count",
  "element_bit_size": "32",
  "value": "svcount_t"
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
    "PNreg1.S": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
PTRUE PNreg1.S
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/PTRUE--predicate-as-counter---Initialize-predicate-as-counter-to-all-active-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svptrue_c64

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svptrue_c64

### Signature (source notation)

```c
svcount_t svptrue_c64();
```

### Description

Initialize predicate-as-counter to all active

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Initialization / Initialize to pattern

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
  "return_base_type": "count",
  "element_bit_size": "64",
  "value": "svcount_t"
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
    "PNreg1.D": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
PTRUE PNreg1.D
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/PTRUE--predicate-as-counter---Initialize-predicate-as-counter-to-all-active-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svptrue_c8

ISA classification: SME + FEAT_SVE2p1 OR SME2

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svptrue_c8

### Signature (source notation)

```c
svcount_t svptrue_c8();
```

### Description

Initialize predicate-as-counter to all active

### Availability

- ISA categories: SME and SME2, SVE2

- Architectures: A64

- Instruction group: Predication / Initialization / Initialize to pattern

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
  "return_base_type": "count",
  "element_bit_size": "8",
  "value": "svcount_t"
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
    "PNreg1.B": "result"
  }
]
```

### Instruction mapping

This intrinsic compiles to an instruction sequence that is semantically equivalent to:

```asm
PTRUE PNreg1.B
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/PTRUE--predicate-as-counter---Initialize-predicate-as-counter-to-all-active-

### Operation

No separate operation text/pseudocode supplied by source; see description and instruction references above.

## svptrue_pat_b16

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svptrue_pat_b16

### Signature (source notation)

```c
svbool_t svptrue_pat_b16(enum svpattern pattern);
```

### Description

Set predicate elements to true

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Predication / Initialization / Initialize to pattern

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
{}
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
PTRUE Presult.H, pattern
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/PTRUE--predicate---Initialize-predicate-from-named-constraint-

### Operation

Source operation ID: `SveOperation_svptrue_pat_b16`

**Operation**



Return a predicate that makes every element in vector pattern `pattern` active and makes all other elements inactive.  Return an all-false predicate if the current vector length does not support `pattern`.



Only the lowest bit of each element is ever set; the upper bits are always zero.

## svptrue_pat_b32

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svptrue_pat_b32

### Signature (source notation)

```c
svbool_t svptrue_pat_b32(enum svpattern pattern);
```

### Description

Set predicate elements to true

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Predication / Initialization / Initialize to pattern

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
{}
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
PTRUE Presult.S, pattern
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/PTRUE--predicate---Initialize-predicate-from-named-constraint-

### Operation

Source operation ID: `SveOperation_svptrue_pat_b16`

**Operation**



Return a predicate that makes every element in vector pattern `pattern` active and makes all other elements inactive.  Return an all-false predicate if the current vector length does not support `pattern`.



Only the lowest bit of each element is ever set; the upper bits are always zero.

## svptrue_pat_b64

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svptrue_pat_b64

### Signature (source notation)

```c
svbool_t svptrue_pat_b64(enum svpattern pattern);
```

### Description

Set predicate elements to true

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Predication / Initialization / Initialize to pattern

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
{}
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
PTRUE Presult.D, pattern
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/PTRUE--predicate---Initialize-predicate-from-named-constraint-

### Operation

Source operation ID: `SveOperation_svptrue_pat_b16`

**Operation**



Return a predicate that makes every element in vector pattern `pattern` active and makes all other elements inactive.  Return an all-false predicate if the current vector length does not support `pattern`.



Only the lowest bit of each element is ever set; the upper bits are always zero.

## svptrue_pat_b8

ISA classification: SME

Source: https://developer.arm.com/architectures/instruction-sets/intrinsics/svptrue_pat_b8

### Signature (source notation)

```c
svbool_t svptrue_pat_b8(enum svpattern pattern);
```

### Description

Set predicate elements to true

### Availability

- ISA categories: SME and SME2, SVE

- Architectures: A64

- Instruction group: Predication / Initialization / Initialize to pattern

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
{}
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
PTRUE Presult.B, pattern
```

Instruction reference: https://developer.arm.com/documentation/ddi0602/2025-06/SVE-Instructions/PTRUE--predicate---Initialize-predicate-from-named-constraint-

### Operation

Source operation ID: `SveOperation_svptrue_pat_b8`

**Operation**



Return a predicate that makes every element in vector pattern `pattern` active and makes all other elements inactive.  Return an all-false predicate if the current vector length does not support `pattern`.

