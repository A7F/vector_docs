[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/LIN/Functions/CAPLfunctionLINSetValidBreakLimits.md)

[CAPL Functions](../../CAPLfunctions.md) » [LIN](../CAPLfunctionsLINOverview.md) » linSetValidBreakLimits

# linSetValidBreakLimits

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

## Function Syntax

```plaintext
dword linSetValidBreakLimits(dword breakMin16thBits, 
 dword breakMax16thBits, dword delMin16thBits, dword delMax16thBits);
```

## Description

Sets limits for the accepted sync break and delimiter lengths. Any sync break and delimiter outside of this range is considered invalid, resulting in a receive error. Note that this function does not change the current sync break and delimiter length sent by a simulated master. This function can also be called in slave mode to test an external master.

This function does not change the header length restrictions of 47.6 bit times for LIN 2.x and 49 bit times for LIN 1.x. This means that a header can still be invalid even if the modified sync break and delimiter limits are met.

## Parameters

- **breakMin16thBits**: The minimum legal sync break length, specified in units of 1/16th bit times.  
  Range: 152 (9.5 bit times) – 784 (49 bit times)

- **breakMax16thBits**: The maximum legal sync break length, specified in units of 1/16th bit times.  
  Range: 152 (9.5 bit times) – 784 (49 bit times), has to be greater than breakMin16thBits

- **delMin16thBits**: The minimum legal sync delimiter length, specified in units of 1/16th bit times.  
  Range: 1 – 784 (49 bit times)

- **delMax16thBits**: The maximum legal sync delimiter length, specified in units of 1/16th bit times.  
  Range: 1 – 784 (49 bit times), has to be greater than delMin16thBits

## Return Values

On success, a value unequal to zero, otherwise zero.

## Example

—

[linSetBreakLength](CAPLfunctionLINSetBreakLength.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)