[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/Functions/CAPLfunctionMOSTGetNPR.md)

[CAPL Functions](../../CAPLfunctions.md) » [MOST](../CAPLfunctionsMOSTOverview.md) » mostGetNPR

# mostGetNPR

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
long mostGetNPR (long channel);
```

## Description

This function returns the "Node Position Register (NPR)" value of the MOST hardware chip connected to the channel.

## Parameters

- **channel**: Channel of the connected MOST hardware.

## Return Values

- **\\\> 0**: NPR value
- **\<\= 0**: See [error codes](../CAPLfunctionsMOSTErrorCodes.md)

## Example

—

[mostGetChannel](CAPLfunctionMOSTGetChannel.md) • [mostGetNodeAdr, mostGetGroupAdr, mostGetAltPktAdr, mostGetNodePosAdr](CAPLfunctionMOSTGetNodeAdr.md) • [OnMostNPR](../EventProcedures/CAPLfunctionOnMOSTNPR.md)
