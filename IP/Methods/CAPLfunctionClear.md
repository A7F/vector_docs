[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/Methods/CAPLfunctionClear.md)

# ethernetPacket::Clear

[CAPL Functions](../../CAPLfunctions.md) » [Ethernet](../CAPLEthernetStartPage.md) » [Function Overview](../CAPLfunctionsIPOverview.md) » ethernetPacket::Clear

**Valid for:** CANoe DE • CANoe4SW DE

## Method Syntax

[Method](../../../Shared/CAPL/General/ClassesAndObjects.md) Syntax

```plaintext
void ethernetPacket.Clear();
```

## Description

Clears data and resets length.

## Parameters

—

## Return Values

—

## Example

```plaintext
ethernetPacket pkt;

// prepare packet for first output
pkt.ipv6.Init();
pkt.udp.Init();
pkt.udp.SetData( 0, "Hello", 5 );
pkt.CompletePacket();
output( pkt );

// clear the packet
pkt.Clear();

// prepare packet for second output with different
// protocols and data than with first output above

pkt.tcp.Init();
pkt.CompletePacket();
output( pkt );
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)