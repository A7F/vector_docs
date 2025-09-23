[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/Functions/CAPLfunctionMOSTApIsRegistered.md)

[CAPL Functions](../../CAPLfunctions.md) » [MOST](../CAPLfunctionsMOSTOverview.md) » mostApIsRegistered

# mostApIsRegistered

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
long mostApIsRegistered();
```

## Description

This function can be used to poll whether the CAPL node is registered as a function block in the [Local FBlockList](../../../CANoeCANalyzer/MOST/MOSTSimulationApplicationSocketLocalFBlockList.md). The function block must be assigned to the CAPL program via [mostApRegister(fblockID, instIDDefault)](CAPLfunctionMOSTApRegister.md) or the [database](../../../CANoeCANalyzer/MOST/MOSTSimulationDatabase.md).

## Parameters

—

## Return Values

- **1**: Function block is registered
- **0**: Function block is not registered
- **\< 0**: See [error codes](../CAPLfunctionsMOSTErrorCodes.md)

## Example

—

[mostApRegister](CAPLfunctionMOSTApRegister.md) • [mostApUnregister](CAPLfunctionMOSTApUnregister.md) • [mostApGetInstId](CAPLfunctionMOSTApGetInstID.md) • [mostApGetFBlockId](CAPLfunctionMOSTApGetFBlockID.md) • [mostApIsRegisteredEx](CAPLfunctionMOSTApIsRegisteredEx.md)
