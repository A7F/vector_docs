[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/Functions/CAPLfunctionMOSTAsNTFFunctionEnable.md)

# mostAsNtfFunctionEnable, mostAsNtfFunctionDisable, mostAsNtfFunctionIsEnabled

[CAPL Functions](../../CAPLfunctions.md) » [MOST](../CAPLfunctionsMOSTOverview.md) » mostAsNtfFunctionEnable, mostAsNtfFunctionDisable, mostAsNtfFunctionIsEnabled

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

- `long mostAsNtfFunctionEnable(long functionID, char cbSendStatus[]);`
- `long mostAsNtfFunctionDisable(long functionID);`
- `long mostAsNtfFunctionIsEnabled(long functionID);`

## Description

`mostAsNtfFunctionEnable()` enables the notification service for a function. The notification service must be enabled with [mostAsNtfEnable()](CAPLfunctionMOSTAsNTFEnable.md) for the function block beforehand.

The service must have the name of a CAPL function that generates and sends the status message of the properties. This is necessary so that the service can send the current value of the properties with the FBlock.Notification.Set(SetFunction/SetAll) message to the client when registering a client (see MOST Specification 2.3 Section 2.3.12).

The CAPL function must be defined by the user and display the following signature:

- `long <FunctionName>(long destAdr)`
- or
- `long <FunctionName>(long destAdr, long fblockID, long instID, long functionID)`

The function must generate and send the status message to the destAdr address. If the status message could be sent, the function has to return the value 0. Otherwise, it must report it to the notification service with the return value -1. The service then sends an error message (FBlock.Function.Error(0x41)) to the client instead of the status message.

`mostAsNtfFunctionDisable()` disables the notification service for the function.

`mostAsNtfFunctionIsEnabled()` returns 1 if the notification service is enabled for the function.

**Database support:**

The special value functionID=-1 triggers the execution of the CAPL function for all MOST functions from the function catalog meeting the following criteria:

- The MOST function must be of the "Property" type.
- A function with the name cbSendStatus+`<MOST function name>` needs to be defined in the CAPL program to generate and send the status message.

## Parameters

- **functionID**: Function ID or -1 for all functions of the function block from the database.
- **cbSendStatus[]**: Name of the CAPL function that generates and sends the status message. If functionID=-1, cbSendStatus designates the prefix of the CAPL send functions to be defined. If an empty character string is specified, the default prefix "SendStatus_" is used.

**Note:** The name of the CAPL function is **case sensitive**!

## Return Values

See [error codes](../CAPLfunctionsMOSTErrorCodes.md)

## Example

—

[mostApRegister](CAPLfunctionMOSTApRegister.md) • [mostAsNtfEnable, mostAsNtfDisable](CAPLfunctionMOSTAsNTFEnable.md) • [mostAsNtfFunctionEnableEx, mostAsNtfFunctionDisableEx, mostAsNtfFunctionIsEnabledEx](CAPLfunctionMOSTAsNTFFunctionEnableEx.md) • [mostAsNtfOutput](CAPLfunctionMOSTAsNTFOutput.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
