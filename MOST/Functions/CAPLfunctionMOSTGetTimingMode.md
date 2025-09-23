[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/Functions/CAPLfunctionMOSTGetTimingMode.md)

[CAPL Functions](../../CAPLfunctions.md) » [MOST](../CAPLfunctionsMOSTOverview.md) » mostGetTimingMode

# mostGetTimingMode

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```
long mostGetTimingMode(long channel);
```

## Description

Returns the Timing Mode of the MOST hardware.

## Parameters

- **channel**: Channel of the connected interface.

## Return Values

- **0**: Timing Slave
- **1**: Timing Master
- **\<0**: See [error codes](../CAPLfunctionsMOSTErrorCodes.md)

If the bypass is closed this function returns the mode that would have been set if the bypass were opened (see [mostSetAllBypass](CAPLfunctionMOSTSetAllBypass.md)).

## Example

—

[mostGetChannel](CAPLfunctionMOSTGetChannel.md) • [mostSetTimingMode](CAPLfunctionMOSTSetTimingMode.md) • [OnMostTimingMode](../EventProcedures/CAPLfunctionOnMOSTTimingMode.md)
