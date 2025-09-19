[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/Functions/CAPLfunctionMOSTAsFsEnableMOSTAsFsDisable.md)

**CAPL Functions** » [MOST](../CAPLfunctionsMOSTOverview.md) » mostAsFsEnable, mostAsFsDisable

# mostAsFsEnable, mostAsFsDisable

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

- `long mostAsFsEnable();`
- `long mostAsFsDisable();`

## Description

`mostAsFsEnable()` makes the function service available for the function block. The function block must be assigned to the CAPL program via [mostApRegister(fblockID, instIDDefault)](CAPLfunctionMOSTApRegister.md) or the [database](../../../CANoeCANalyzer/MOST/MOSTSimulationDatabase.md). Furthermore, `mostAsFsEnable()` enables the functions `<FktIDs>`, `<Notification>` and `<NotificationCheck>` of the function block for the notification service.

`mostAsFsDisable()` disables the function service.

## Parameters

—

## Return Values

See [error codes](../CAPLfunctionsMOSTErrorCodes.md)

## Example

—

[mostAsFsEnableEx](CAPLfunctionMOSTAsFsEnableExMOSTAsFsDisableEx.md) • [mostAsFsFunctionEnable](CAPLfunctionMOSTAsFsFunctionEnable.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
