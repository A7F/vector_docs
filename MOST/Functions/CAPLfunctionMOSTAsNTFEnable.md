[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/Functions/CAPLfunctionMOSTAsNTFEnable.md)

**CAPL Functions** » [MOST](../CAPLfunctionsMOSTOverview.md) » mostAsNtfEnable, mostAsNtfDisable

# mostAsNtfEnable, mostAsNtfDisable

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

- `long mostAsNtfEnable();`
- `long mostAsNtfDisable();`

## Description

`mostAsNtfEnable()` enables the notification service for the function block. The function block must be assigned to the CAPL program via [mostApRegister(fblockID, instIDDefault)](CAPLfunctionMOSTApRegister.md) or the [database](../../../CANoeCANalyzer/MOST/MOSTSimulationDatabase.md).

`mostAsNtfDisable()` disables the notification service. The notification matrix is thereby deleted.

## Parameters

—

## Return Values

—

## Example

—

[mostApIsRegistered](CAPLfunctionMOSTApIsRegistered.md) • [mostAsNtfEnableEx, mostAsNtfDisableEx](CAPLfunctionMOSTAsNTFEnableEx.md) • [mostApplicationNode](CAPLfunctionMOSTApplicationNode.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
