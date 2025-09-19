[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/Functions/CAPLfunctionMOSTAsNTFFunctionEnableEx.md)

**CAPL Functions** » [MOST](../CAPLfunctionsMOSTOverview.md) » mostAsNtfFunctionEnableEx, mostAsNtfFunctionDisableEx, mostAsNtfFunctionIsEnabledEx

# mostAsNtfFunctionEnableEx, mostAsNtfFunctionDisableEx, mostAsNtfFunctionIsEnabledEx

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

- `long mostAsNtfFunctionEnableEx(long fblockID, long instID, long functionID, char cbSendStatus[]);`
- `long mostAsNtfFunctionDisableEx(long fblockID, long instID, long functionID);`
- `long mostAsNtfFunctionIsEnabledEx(long fblockID, long instID, long functionID);`

## Description

The behavior corresponds to the functions [mostAsNtfFunctionEnable, mostAsNtfFunctionDisable, mostAsNtfFunctionIsEnabled](CAPLfunctionMOSTAsNTFFunctionEnable.md). The functions ending with 'Ex' can also be used if the CAPL node is not assigned to a function block exclusively.

## Parameters

- **fblockID**: Function block ID
- **instID**: Instance ID
- **functionID**: Function ID or -1 for all functions of the function block from the database.
- **cbSendStatus[]**: Name of the CAPL function that generates and sends the status message. If `functionID=-1`, `cbSendStatus` designates the prefix of the CAPL send functions to be defined. If an empty character string is specified, the default prefix "SendStatus_" is used.

## Return Values

See [error codes](../CAPLfunctionsMOSTErrorCodes.md).

## Example

—

[mostApIsRegisteredEx](CAPLfunctionMOSTApIsRegisteredEx.md) • [mostAsNtfEnableEx, mostAsNtfDisableEx](CAPLfunctionMOSTAsNTFEnableEx.md) • [mostAsNtfFunctionEnable, mostAsNtfFunctionDisable, mostAsNtfFunctionIsEnabled](CAPLfunctionMOSTAsNTFFunctionEnable.md) • [mostAsNtfOutput](CAPLfunctionMOSTAsNTFOutput.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
