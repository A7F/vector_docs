[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/Methods/CAPLfunctionPDUCount.md)

[CAPL Functions](../../CAPLfunctions.md) » [Ethernet](../CAPLEthernetStartPage.md) » [Function Overview](../CAPLfunctionsIPOverview.md) » ethernetPacket::PDUCount

# ethernetPacket::PDUCount

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Method Syntax

`long ethernetPacket.PDUCount();`

## Description

Returns the number of all PDUs in this message.

## Parameters

—

## Return Values

- **>=0**: number of all PDUs in this packet.
- **-1**: Wrong bus system.
- **-2**: This frame does not support accessing PDUs.
- **-3**: The PDU object is invalid.
- **-4**: PDU is not of RX type.
- **-5**: Parameter too small (e.g. array has too less bytes)
- **-6**: Message or PDU is not available (any more)
- **-7**: PDU index out of bound. Use selector PDUCount() to determine the number of PDUs.

## Example

```plaintext
ethernetPacket packet;
pdu* aPDU;

if(packet.PDUCount()>0)
{
  write("second pdu starts at %d bytes", packet.PDUOffset(1));
  packet.GetPDU(1, aPDU);
  write("pdu longheader: %d, %s", aPDU.LongHeaderID, aPDU.fullQualifiedName);
}
```

[See Also](javascript:void(0);)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
