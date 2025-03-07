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

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)