[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/Functions/CAPLfunctionMOSTApUnregister.md)

[CAPL Functions](../../CAPLfunctions.md) » [MOST](../CAPLfunctionsMOSTOverview.md) » mostApUnregister

# mostApUnregister

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

## Function Syntax

```plaintext
long mostApUnregister();
```

## Description

`mostApUnregister()` removes the function block assigned to the CAPL node by CANdb or [mostApRegister(fblockID, instIDDefault)](CAPLfunctionMOSTApRegister.md) from the [Local FBlockList](../../../CANoeCANalyzer/MOST/MOSTSimulationApplicationSocketLocalFBlockList.md).

In network status 'ConfigOk' the device's NetBlock reports the new Local FBlockList to the NetworkMaster.

## Parameters

—

## Return Values

See [error codes](../CAPLfunctionsMOSTErrorCodes.md)

## Example

—

[mostApRegister](CAPLfunctionMOSTApRegister.md) • [mostApUnregisterEx](CAPLfunctionMOSTApUnregisterEx.md)
