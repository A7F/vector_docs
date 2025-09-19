[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/Methods/CAPLfunctionIsAvailable.md)

[CAPL Functions](../../CAPLfunctions.md) » [Ethernet](../CAPLEthernetStartPage.md) » [Function Overview](../CAPLfunctionsIPOverview.md) » ethernetPacket::IsAvailable

# ethernetPacket::IsAvailable

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Method Syntax

byte [ethernetPacket](../Objects/CAPLfunctionEthernetPacket.md).IsAvailable(char protocol[], char field[]);

## Description

Checks whether the protocol and the **protocol** field are present in the Ethernet packet.

## Parameters

- **protocol**: Name of the [protocol](../../../CANoeCANalyzer/Ethernet/Protocols/Protocol.md).
- **field**: Name of the field.

## Return Values

- **1**: Protocol and protocol field are available in the Ethernet packet
- **0**: Protocol and protocol field are not available in the Ethernet packet

## Example

```plaintext
on ethernetPacket *
{
  if(this.IsAvailable("icmpv4", "echo.identifier"))
  {
    Write("Protocol field icmpv4.echo.identifier is available");
  }
}
```

[See Also](javascript:void(0);)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
