[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionGetEthernetPacket.md)

**CAPL Functions** » **General** » **Function Overview** » **GetEthernetPacket**

# GetEthernetPacket

[Valid for: CANoe DE](../../../Shared/FeatureAvailability.md) • CANoe4SW DE

## Function Syntax

```
long GetEthernetPacket(this, ethernetPacket packet);
```

## Description

This function can only be called inside of an **on PDU** handler. The function will return in its second parameter the Ethernet packet, the PDU was contained.

## Parameters

- **this**: Handle to the currently handled (received) PDU object.
- **packet**: Reference to an [Ethernet Packet object](../../IP/Objects/CAPLfunctionEthernetPacket.md) that will contain the overall received packet data and information.

## Return Values

- **0**: Data access successful.
- **-1**: Wrong bus system; Ethernet packet is not available.
- **-2**: Packet does not support this info.
- **-3**: The PDU object is invalid.
- **-4**: PDU is not of Rx type.
- **-5**: Parameter too small (e.g. array has too less bytes)
- **-6**: Packet or PDU is not available (any more)

## Example

```plaintext
on PDU PDU_B
{
  ethernetPacket aPacket_01;
  long result;
  result = GetEthernetPacket(this, aPacket_01); // PDU is assumed to be sent on ETH
  if (result == 0)
  {
    write("Received PDU 'PDU_B' in ETH packet with FCS %lu", aPacket_01.FCS);
  }
  else
  {
    write("Error accessing PDU!");
  }
}
```

**Related Links:**

- [on PDU](../EventProcedures/CAPLfunctionOnPDU.md)
- [GetFrFrame](CAPLfunctionGetFrFrame.md)
- [GetCANMessage](CAPLfunctionGetCANMessage.md)
- [GetPDUsTPIPv6SrcAddr](CAPLfunctionGetPDUsTPIPv6SrcAddr.md)
- [GetPDUsTPIPv6DstAddr](CAPLfunctionGetPDUsTPIPv6DstAddr.md)
- [GetPDUsTPIPv4SrcAddr](CAPLfunctionGetPDUsTPIPv4SrcAddr.md)
- [GetPDUsTPIPv4DstAddr](CAPLfunctionGetPDUsTPIPv4DstAddr.md)
- [GetPDUsTPUDPSrcPort](CAPLfunctionGetPDUsTPUDPSrcPort.md)
- [GetPDUsTPUDPDstPort](CAPLfunctionGetPDUsTPUDPDstPort.md)
- [GetPDUsTPTCPSrcPort](CAPLfunctionGetPDUsTPTCPSrcPort.md)
- [GetPDUsTPTCPDstPort](CAPLfunctionGetPDUsTPTCPDstPort.md)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)