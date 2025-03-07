[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/Methods/CAPLfunctionProtocolFieldIsAvailable.md)

[CAPL Functions](../../CAPLfunctions.md) » [Ethernet](../CAPLEthernetStartPage.md) » [Function Overview](../CAPLfunctionsIPOverview.md) » ethernetPacket::protocol::field::IsAvailable

# ethernetPacket::protocol::field::IsAvailable

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Method Syntax

long [ethernetPacket](../Objects/CAPLfunctionEthernetPacket.md).<[protocol](../../../CANoeCANalyzer/Ethernet/Protocols/Protocol.md)>.<field>.IsAvailable();

## Description

Returns if a protocol field is available in the Ethernet packet. This can be used, if the protocol contains optional fields or options.

## Parameters

—

## Return Values

- **1**: Protocol field is available
- **0**: Protocol field is not available

## Example

```plaintext
on ethernetPacket *
{
  if (this.udp.checksum.IsAvailable())
  {
    Write( "Protocol field udp.checksum is available and has value 0x%X", this.udp.checksum );
  }
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)