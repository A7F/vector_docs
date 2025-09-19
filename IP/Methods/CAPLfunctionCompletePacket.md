[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/Methods/CAPLfunctionCompletePacket.md)

# ethernetPacket::CompletePacket

[CAPL Functions](../../CAPLfunctions.md) » [Ethernet](../CAPLEthernetStartPage.md) » [Function Overview](../CAPLfunctionsIPOverview.md) » ethernetPacket::CompletePacket

**Valid for**: CANoe DE • CANoe4SW DE

## Method Syntax

[word ethernetPacket.CompletePacket();](../Objects/CAPLfunctionEthernetPacket.md)

## Description

Calculates the checksum and length field for all protocols contained in the packet. The protocols will be valid after calling this method and the packet can be sent.

## Parameters

—

## Return Values

- **0**: Success
- **-1**: Error

## Example

```plaintext
ethernetPacket pkt;

// initialize with IPv4 and UDP protocol
pkt.udp.Init();

// recalculate checksum and length fields of IPv4 and UDP
pkt.CompletePacket();

// send packet
output( pkt );
```

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
