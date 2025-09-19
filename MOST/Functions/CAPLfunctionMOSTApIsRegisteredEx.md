[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/Functions/CAPLfunctionMOSTApIsRegisteredEx.md)

[CAPL Functions](../../CAPLfunctions.md) » [MOST](../CAPLfunctionsMOSTOverview.md) » mostApIsRegisteredEx

# mostApIsRegisteredEx

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
long mostApIsRegisteredEx(long fblockID, long instID);
```

## Description

This function can be used to poll whether the function block with functional address {fblockID, instID} is entered in the [Local FBlockList](../../../CANoeCANalyzer/MOST/MOSTSimulationApplicationSocketLocalFBlockList.md).

## Parameters

- **fblockID**: Function block identifier to be queried.
- **instID**: Instance identifier to be queried.

## Return Values

- **1**: Function block is registered.
- **0**: Function block is not registered.
- **<0**: See [error codes](../CAPLfunctionsMOSTErrorCodes.md).

## Example

—

[mostApRegisterEx](CAPLfunctionMOSTApRegisterEx.md) • [mostApUnregisterEx](CAPLfunctionMOSTApUnregisterEx.md) • [mostApIsRegistered](CAPLfunctionMOSTApIsRegistered.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
