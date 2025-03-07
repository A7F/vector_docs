[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/Functions/CAPLfunctionMOSTApIsAddressed.md)

[CAPL Functions](../../CAPLfunctions.md) » [MOST](../CAPLfunctionsMOSTOverview.md) » mostApIsAddressed

# mostApIsAddressed

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

- `long mostApIsAddressed(long fblockID, long instID); // form 1`
- `long mostApIsAddressed(mostAmsMessage * msgCommand); // form 2`

## Description

`mostApIsAddressed` checks whether the functional MOST address `{fblockID, instID}` matches the CAPL node function blocks assigned via [mostApRegister()](CAPLfunctionMOSTApRegister.md) or [mostApRegisterEx()](CAPLfunctionMOSTApRegisterEx.md). The functional address is permitted to contain wildcard symbols.

This function can be used to determine whether an incoming command message is destined for the CAPL node.

## Parameters

- **fblockID**: Function block identifier of the functional address.
- **instID**: Instance identifier of the functional address.
- **msgCommand**: Received command message containing the functional address.

## Return Values

- **1**: If a MOST application simulated by this CAPL node is addressed.
- **0**: Otherwise
- **<0**: See [error codes](../CAPLfunctionsMOSTErrorCodes.md)

## Example

—

[mostApRegister](CAPLfunctionMOSTApRegister.md) • [mostApRegisterEx](CAPLfunctionMOSTApRegisterEx.md) • [mostPrepareReport](CAPLfunctionMOSTPrepareReport.md) • [mostSendError](CAPLfunctionMOSTSendError.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)