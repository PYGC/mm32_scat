# MM32_SCT

MM32 Scatter Files for Keil µVision at Link Phase (for armlink).

## Scatter File

A scatter file contains one or more load regions. Each load region can contain one or more execution regions.

### Arm Compiler 5

```scat
#!armcc -E
```

### Arm Compiler for Embedded 6

```scat
#!armclang -E --target=arm-arm-none-eabi -mcpu=cortex-m3 -xc
```

### Description

The option `-E` makes armclang only execute the preprocessor step. See [-E](https://developer.arm.com/documentation/101754/0617/armclang-Reference/armclang-Command-line-Options/-E)

The mandatory option `--target` specifies the target state, either AArch32 state, as shown in this example, or AArch64 state. `aarch64-arm-none-eabi` or `arm-arm-none-eabi`. `aarch64-arm-none-eabi`, generates A64 instructions for `AArch64` state. Implies `-march=armv8-a` unless `-mcpu` or `-march` is specified. `arm-arm-none-eabi`, generates A32/T32 instructions for `AArch32` state. Must be used in conjunction with `-march` (to target an architecture) or `-mcpu` (to target a processor).

The option `-mcpu` specifies a processor, Cortex-M3 in this example. Alternatively, you can use -march to specify an architecture. See [-mcpu](https://developer.arm.com/documentation/101754/0617/armclang-Reference/armclang-Command-line-Options/-mcpu) and [-march](https://developer.arm.com/documentation/101754/0617/armclang-Reference/armclang-Command-line-Options/-march)

The option `-x` specifies the source language. `-xc` is c language. See [-x](https://developer.arm.com/documentation/101754/0617/armclang-Reference/armclang-Command-line-Options/-x--armclang-)

See [Preprocessing a scatter file when linking with armlink](https://developer.arm.com/documentation/100068/0617/Migrating-from-armcc-to-armclang/Preprocessing-a-scatter-file-when-linking-with-armlink).

## Usage

`Project` -> `Options for 'XXXX'` -> `Linker` -> `Scatter File` -> `...` (File Picker) to open *.scat.
