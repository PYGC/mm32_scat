# MM32_SCAT

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

The option `-E` makes armclang only execute the preprocessor step.

The mandatory option `--target` specifies the target state, either AArch32 state, as shown in this example, or AArch64 state.

The option `-mcpu` specifies a processor, Cortex-M7 in this example. Alternatively, you can use -march to specify an architecture. See -mcpu or -march.

The option `-x` specifies the source language. `-xc` is c language

See [Preprocessing a scatter file when linking with armlink](https://developer.arm.com/documentation/100068/0617/Migrating-from-armcc-to-armclang/Preprocessing-a-scatter-file-when-linking-with-armlink).

## Usage

`Project` -> `Options for 'XXXX'` -> `Linker` -> `Scatter File` -> `...` (File Picker) to open *.scat.