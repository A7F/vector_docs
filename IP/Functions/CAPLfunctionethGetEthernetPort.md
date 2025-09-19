[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/Functions/CAPLfunctionethGetEthernetPort.md)

[CAPL Functions](../../CAPLfunctions.md) » [Ethernet](../CAPLEthernetStartPage.md) » [Function Overview](../CAPLfunctionsIPOverview.md) » ethGetEthernetPort

# ethGetEthernetPort

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

`ethernetPort ethGetEthernetPort(long Channel);`

## Description

Gets the Ethernet port for the current simulation node. The channel needs to be specified and can be used for gateway nodes to differentiate between the ports on different networks.

## Parameters

- **Channel**: Application channel, i.e. Eth 1.

## Return Values

Ethernet port

## Example

```plaintext
on start
{
  ethernetport ownPort;
  ownPort = ethGetEthernetPort(1);
  // ... do something with ownPort
}
```

[lookupEthernetPort](CAPLfunctionLookupEthernetPort.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
