[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionGetPDUsTPTCPSrcPort.md)

[CAPL Functions](../../CAPLfunctions.md) » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » GetPDUsTPTCPSrcPort

# GetPDUsTPTCPSrcPort

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
long GetPDUsTPTCPSrcPort(this, dword &tcpSourcePort);
```

## Description

This function can only be used within a [on PDU](../EventProcedures/CAPLfunctionOnPDU.md) handler. If the PDU was received via TCP, with this function the TCP source address can be requested.

## Parameters

- **this**: Handle to the currently handled (received) PDU object.
- **tcpDestinationPort**: TCP source port.

## Return Values

- **0**: Data access successful.
- **-1**: Wrong bus system.
- **-2**: The requested information was not available. Most probably the PDU was not received by a TCP layer.
- **-3**: The PDU object is invalid.
- **-4**: PDU is not of RX type.
- **-5**: Parameter too small (e.g. array has too less bytes)
- **-6**: Message or PDU is not available (any more)

## Example

```plaintext
on PDU engineDataPDU
{
  dword srcAddr, dstAddr, srcPort, dstPort;
  char srcAddrAsString[16], dstAddrAsString[16];

  if (GetPDUsTPIPv4SrcAddr(this, srcAddr)==0
      && GetPDUsTPIPv4DstAddr(this, dstAddr)==0)
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

[GetPDUsTPIPv4DstAddr](CAPLfunctionGetPDUsTPIPv4DstAddr.md) • [GetPDUsTPIPv4SrcAddr](CAPLfunctionGetPDUsTPIPv4SrcAddr.md) • [GetPDUsTPIPv6DstAddr](CAPLfunctionGetPDUsTPIPv6DstAddr.md) • [GetPDUsTPIPv6SrcAddr](CAPLfunctionGetPDUsTPIPv6SrcAddr.md) • [GetPDUsTPTCPDstPort](CAPLfunctionGetPDUsTPTCPDstPort.md) • [GetPDUsTPUDPDstPort](CAPLfunctionGetPDUsTPUDPDstPort.md) • [GetPDUsTPUDPSrcPort](CAPLfunctionGetPDUsTPUDPSrcPort.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)