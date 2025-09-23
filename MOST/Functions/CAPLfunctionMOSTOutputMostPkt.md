[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/Functions/CAPLfunctionMOSTOutputMostPkt.md)

**CAPL Functions** » [MOST](../CAPLfunctionsMOSTOverview.md) » outputMostPkt

# outputMostPkt

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```
outputMostPkt(long channel, long destadr, long pktdatalen, BYTE pktdata[]);
```

## Description

Sends out packets over the asynchronous MOST channel.

## Parameters

- **channel**: Channel number
- **destadr**: Destination address
- **pktdatalen**: Number of bytes to be sent.
  - MOST25/MOST50: 0 < pktdatalen ≤ 1014
  - MOST150: 0 < pktdatalen ≤ 1524
- **pktdata[]**: Useful data

## Return Values

See [error codes](../CAPLfunctionsMOSTErrorCodes.md)

## Example

—

[output](CAPLfunctionMOSToutput.md) • [outputMostPktThis](CAPLfunctionMOSTOutputMostPktThis.md)
