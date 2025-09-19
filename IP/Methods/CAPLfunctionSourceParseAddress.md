[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/Methods/CAPLfunctionSourceParseAddress.md)

CAPL Functions » [Ethernet](../CAPLEthernetStartPage.md) » [Function Overview](../CAPLfunctionsIPOverview.md) » ethernetPacket::source::ParseAddress

# ethernetPacket::source::ParseAddress

**Valid for**: CANoe DE • CANoe4SW DE

## Method Syntax

- `long ethernetPacket.source.ParseAddress( char addressAsString[] ); // form 1`
- `long ethernetPacket.destination.ParseAddress( char addressAsString[] ); // form 2`

## Description

Sets the source or destination MAC address of an Ethernet packet with a string. The address must be given in this form: `02:00:00:12:34:AB`

## Parameters

- **addressAsString**: Address in text form of format MAC address.

## Example

```plaintext
ethernetPacket pkt;

pkt.source.ParseAddress( "02:00:00:00:00:01" );
pkt.destination.ParseAddress( "FF:FF:FF:FF:FF:FF" );
```

[See Also](javascript:void(0);)

---

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
