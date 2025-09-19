# mostAsFsEnableEx, mostAsFsDisableEx

[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/Functions/CAPLfunctionMOSTAsFsEnableExMOSTAsFsDisableEx.md)

**CAPL Functions** » [MOST](../CAPLfunctionsMOSTOverview.md) » mostAsFsEnableEx, mostAsFsDisableEx

**Valid for**: CANoe DE

## Function Syntax

- `long mostAsFsEnableEx(long fblockId, long instId);`
- `long mostAsFsDisableEx(long fblockId, long instId);`

## Description

`mostAsFsEnableEx()` makes the function service available for a function block. Furthermore, `mostAsFsEnableEx()` enables the functions `<FktIDs>`, `<Notification>`, and `<NotificationCheck>` of the given function block for the notification service.

`mostAsFsDisableEx()` disables the function service for a function block.

## Parameters

- **fblockId**: Function block ID
- **instId**: Instance ID

## Return Values

See [error codes](../CAPLfunctionsMOSTErrorCodes.md).

## Example

—

[mostAsFsFunctionEnableEx](CAPLfunctionMOSTAsFsFunctionEnableEx.md) • [mostAsFsEnable](CAPLfunctionMOSTAsFsEnableMOSTAsFsDisable.md)

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
