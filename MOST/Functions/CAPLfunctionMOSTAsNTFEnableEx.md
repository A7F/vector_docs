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
