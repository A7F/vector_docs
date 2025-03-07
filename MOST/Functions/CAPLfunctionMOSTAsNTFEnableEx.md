[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/Functions/CAPLfunctionMOSTAsNTFEnableEx.md)

[CAPL Functions](../../CAPLfunctions.md) » [MOST](../CAPLfunctionsMOSTOverview.md) » mostAsNtfEnableEx, mostAsNtfDisableEx

# mostAsNtfEnableEx, mostAsNtfDisableEx

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```
long mostAsNtfEnableEx(long fblockID, long instID);
long mostAsNtfDisableEx(long fblockID, long instID);
```

## Description

`mostAsNtfEnableEx()` enables the notification service for the function block.

`mostAsNtfDisableEx()` disables the notification service. The notification matrix is thereby deleted.

## Parameters

- **fblockID**: Function block ID
- **instID**: Instance ID

## Return Values

—

## Example

—

[mostApRegisterEx](CAPLfunctionMOSTApRegisterEx.md) • [mostAsNtfEnable, mostAsNtfDisable](CAPLfunctionMOSTAsNTFEnable.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)