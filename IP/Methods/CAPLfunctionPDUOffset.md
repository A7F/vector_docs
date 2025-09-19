[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/Methods/CAPLfunctionPDUOffset.md)

[CAPL Functions](../../CAPLfunctions.md) » [Ethernet](../CAPLEthernetStartPage.md) » [Function Overview](../CAPLfunctionsIPOverview.md) » ethernetPacket::PDUOffset

# ethernetPacket::PDUOffset

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Method Syntax

```plaintext
long ethernetPacket.PDUOffset(long n);
```

## Description

Returns the byte offset of the start of the PDU with index **n** in the payload of the packet data.

## Parameters

- **n**: Index of the requested PDU. The first PDU has index n = 0, the last PDU has index n = PDUCount() - 1.

## Return Values

- **>=0**: offset of the requested PDU.
- **-1**: Wrong bus system.
- **-2**: This frame does not support accessing PDUs.
- **-3**: The PDU object is invalid.
- **-4**: PDU is not of RX type.
- **-5**: Parameter too small (e.g. array has too few bytes).
- **-6**: Message or PDU is not available (any more).
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
