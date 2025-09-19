[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionGetPDUsTPIPv6SrcAddr.md)

## GetPDUsTPIPv6SrcAddr

[CAPL Functions](../../CAPLfunctions.md) » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » GetPDUsTPIPv6SrcAddr

### Tool Availability
[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

### Function Syntax

```plaintext
long GetPDUsTPIPv6SrcAddr(this, byte IPv6SourceAddress[]);
```

### Description
This function can only be used within a [on PDU](../EventProcedures/CAPLfunctionOnPDU.md) handler. If the PDU was received via IPv6, with this function the IPv6 source address can be requested.

### Parameters
- **this**: Handle to the currently handled (received) PDU object.
- **IPv6SourceAddress**: IPv6 source address as 16 byte array.

### Return Values
- **0**: Data access successful.
- **-1**: Wrong bus system.
- **-2**: The requested information was not available. Most probably the PDU was not received by an IPv6 layer.
- **-3**: The PDU object is invalid.
- **-4**: PDU is not of RX type.
- **-5**: Parameter too small (e.g. array has too less bytes)
- **-6**: Message or PDU is not available (any more)

### Example

```plaintext
on PDU engineDataPDU
{
  dword srcPort, dstPort;
  byte srcAddr[16], dstAddr[16];
  char srcAddrAsString[40], dstAddrAsString[40];

  if (GetPDUsTPIPv6SrcAddr(this, srcAddr)==0
      && GetPDUsTPIPv6DstAddr(this, dstAddr)==0)
  {
    IpGetAddressAsString(srcAddr, srcAddrAsString, elcount(srcAddrAsString));
    IpGetAddressAsString(dstAddr, dstAddrAsString, elcount(dstAddrAsString));

    if(GetPDUsTPUDPSrcPort(this, srcPort)==0
       && GetPDUsTPUDPDstPort(this, dstPort)==0)
    {
      write("PDU received by UDP from %s:%u to %s:%u", srcAddrAsString, srcPort, dstAddrAsString, dstPort);
    }

    if (GetPDUsTPTCPSrcPort(this, srcPort)==0
        && GetPDUsTPTCPDstPort(this, dstPort)==0)
    {
      write("PDU received by TCP from %s:%u to %s:%u", srcAddrAsString, srcPort, dstAddrAsString, dstPort);
    }
  }
}
```

[GetPDUsTPIPv4DstAddr](CAPLfunctionGetPDUsTPIPv4DstAddr.md) • [GetPDUsTPIPv4SrcAddr](CAPLfunctionGetPDUsTPIPv4SrcAddr.md) • [GetPDUsTPIPv6DstAddr](CAPLfunctionGetPDUsTPIPv6DstAddr.md) • [GetPDUsTPTCPDstPort](CAPLfunctionGetPDUsTPTCPDstPort.md) • [GetPDUsTPTCPSrcPort](CAPLfunctionGetPDUsTPTCPSrcPort.md) • [GetPDUsTPUDPDstPort](CAPLfunctionGetPDUsTPUDPDstPort.md) • [GetPDUsTPUDPSrcPort](CAPLfunctionGetPDUsTPUDPSrcPort.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
