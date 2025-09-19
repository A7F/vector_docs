[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/Functions/CAPLfunctionMOSTAsNTFOutput.md)

[CAPL Functions](../../CAPLfunctions.md) » [MOST](../CAPLfunctionsMOSTOverview.md) » mostAsNtfOutput

# mostAsNtfOutput

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

- `long mostAsNtfOutput(long destAdr, mostMessage msg); // form 1`
- `long mostAsNtfOutput(long destAdr, mostAmsMessage msg); // form 2`

## Description

- `destAdr != 0xFFFF`: The command sends the message to the stated address.
- `destAdr == 0xFFFF`: The message is sent to the address of all notification clients. The FBlockID, InstID and FunctionID values, which are needed to read the addresses from the notification matrix, are extracted from the message variable (msg).

## Parameters

- **destAdr**: Message destination address or 0xFFFF to send to all notification clients.
- **msg**: Message to be sent.

## Return Values

See [error codes](../CAPLfunctionsMOSTErrorCodes.md)

## Example

—

[mostAsNtfFunctionEnable, mostAsNtfFunctionDisable, mostAsNtfFunctionIsEnabled](CAPLfunctionMOSTAsNTFFunctionEnable.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
