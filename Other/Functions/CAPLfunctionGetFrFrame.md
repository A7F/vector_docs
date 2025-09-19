[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionGetFrFrame.md)

[CAPL Functions](../../CAPLfunctions.md) » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » GetFrFrame

# GetFrFrame

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long GetFrFrame(this, FrFrame * frame);
```

## Description

This function can only be called inside of an **on PDU** handler. The function will return in its second parameter the FlexRay frame, the PDU was contained.

## Parameters

- **this**: Handle to the currently handled (received) PDU object.
- **packet**: Reference to a [FlexRay Frame object](../../FlexRay/Objects/CAPLfunctionFRFrame.md) that will contain the overall received packet data and information.

## Return Values

- **0**: Data access successful.
- **-1**: Wrong bus system; FlexRay frame is not available.
- **-2**: Frame does not support this info.
- **-3**: The PDU object is invalid.
- **-4**: PDU is not of Rx type.
- **-5**: Parameter too small (e.g. array has too less bytes)
- **-6**: Frame or PDU is not available (any more)

## Example

```plaintext
on PDU PDU_C
{
  FrFrame (1,0,1) aFrFrame_01;
  long result;
  result = GetFrFrame(this, aFrFrame_01); // PDU is assumed to be sent on FlexRay
  if (result == 0)
  {
    write("Received PDU 'PDU_C' in FlexRay Slot %lu", aFrFrame_01.FR_SlotID);
  }
  else
  {
    write("Error accessing PDU!");
  }
}
```

[on PDU](../EventProcedures/CAPLfunctionOnPDU.md) • [GetCANMessage](CAPLfunctionGetCANMessage.md) • [GetEthernetPacket](CAPLfunctionGetEthernetPacket.md) • [GetPDUsTPIPv6SrcAddr](CAPLfunctionGetPDUsTPIPv6SrcAddr.md) • [GetPDUsTPIPv6DstAddr](CAPLfunctionGetPDUsTPIPv6DstAddr.md) • [GetPDUsTPIPv4SrcAddr](CAPLfunctionGetPDUsTPIPv4SrcAddr.md) • [GetPDUsTPIPv4DstAddr](CAPLfunctionGetPDUsTPIPv4DstAddr.md) • [GetPDUsTPUDPSrcPort](CAPLfunctionGetPDUsTPUDPSrcPort.md) • [GetPDUsTPUDPDstPort](CAPLfunctionGetPDUsTPUDPDstPort.md) • [GetPDUsTPTCPSrcPort](CAPLfunctionGetPDUsTPTCPSrcPort.md) • [GetPDUsTPTCPDstPort](CAPLfunctionGetPDUsTPTCPDstPort.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) • [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
