[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/LIN/Functions/CAPLfunctionLINSetBreakLength.md)

[CAPL Functions](../../CAPLfunctions.md) » [LIN](../CAPLfunctionsLINOverview.md) » linSetBreakLength

# linSetBreakLength

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

## Function Syntax

```
dword linSetBreakLength(dword syncBreakLen, dword syncDelLen); // form 1
dword linSetBreakLength(float syncBreakLen, float syncDelLen); // form 2
```

## Description

With this function, it is possible to change the length of break/synch symbol parts, particularly the length of its synch break (dominant bits) and its synch delimiter (recessive bits).

The version using float parameters allows setting the break and delimiter lengths in increments of 1/16th bits, but the unit still is bit times (i.e., `linSetBreakLength(14.5, 2.5)` will set a break length of 14 8/16th bit times and a delimiter length of 2 8/16th bit times). Note that setting non-integer break and delimiter lengths is not supported by every hardware.

**Note**: When LIN hardware is not in Master mode, calling this function will have no effect.

## Parameters

- **syncBreakLen**: Synch break length in bit times.
  - Default value: 18
  - Value range: 10..30

- **syncDelLen**: Synch delimiter length in bit times.
  - Default value: 2
  - Value range: 1..30

- **Values required for a LIN compliant header**:
  - `syncBreakLength >= 13`
  - `syncDelimiterLength >= 1`

## Return Values

On success, a value unequal to zero, otherwise zero.

## Example

—

[linSetValidBreakLimits](CAPLfunctionLINSetValidBreakLimits.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
