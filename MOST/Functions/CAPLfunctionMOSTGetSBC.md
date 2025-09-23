[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/Functions/CAPLfunctionMOSTGetSBC.md)

**CAPL Functions** » [MOST](../CAPLfunctionsMOSTOverview.md) » mostGetSBC

# mostGetSBC

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```
long mostGetSBC (long channel);
```

## Description

This function returns the "Synchronous Bandwidth Control (SBC) Register" value of the MOST hardware chip connected to the channel.

## Parameters

- **channel**: Channel of the connected MOST hardware.

## Return Values

- **>= 0**: Current value of the SBC register
- **< 0**: See [error codes](../CAPLfunctionsMOSTErrorCodes.md)

## Example

—

[mostGetChannel](CAPLfunctionMOSTGetChannel.md) • [mostSetSBC](CAPLfunctionMOSTSetSBC.md) • [OnMostSBC](../EventProcedures/CAPLfunctionOnMOSTSBC.md)
