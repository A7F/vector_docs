# a429SetParity

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
dword a429SetParity( a429word myA429word, int parity_value );
```

## Description

This function sets the selector [parity](../CAPLfunctionsA429Selectors.md) of an ARINC word. So you may change the mode of parity generation for every single ARINC word.

**Note:** This modifies the ARINC word attributes only. For transmission call the function [output](CAPLfunctionA429output.md).

## Parameters

- **myA429word**: ARINC word
- **parity_value**: hardware parity support
  - 0: use channel configuration (default)
  - 1: disable hardware parity support
  - 2: generate odd parity
  - 3: generate even parity

## Return Values

- **0**: selector is not adapted (value range exceeded)
- **1**: selector parity successfully set

## Example

—
