[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/Functions/CAPLfunctionMOSTApRegisterEx.md)

[CAPL Functions](../../CAPLfunctions.md) » [MOST](../CAPLfunctionsMOSTOverview.md) » mostApRegisterEx

# mostApRegisterEx

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

## Function Syntax

```plaintext
long mostApRegisterEx(long fblockID, long instID);
```

## Description

`mostApRegisterEx()` registers the function block with the Application Socket using the functional address (fblockID, instID).

It has to be checked in advance, if the functional address already exists ([mostApIsRegisteredEx](CAPLfunctionMOSTApIsRegisteredEx.md)). If so, another instID has to be selected.

In network status 'ConfigOk' the device's NetBlock reports the new Local FBlockList to the NetworkMaster.

## Parameters

- **fblockID**: Function block identifier to be registered.
- **instID**: Instance identifier to be registered.

## Return Values

See [error codes](../CAPLfunctionsMOSTErrorCodes.md).

## Example

—

[mostApUnregisterEx](CAPLfunctionMOSTApUnregisterEx.md) • [mostApIsRegisteredEx](CAPLfunctionMOSTApIsRegisteredEx.md) • [mostApRegister](CAPLfunctionMOSTApRegister.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
