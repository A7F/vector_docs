# GetCANMessage

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long GetCANMessage(this, message * msg);
```

## Description

This function can only be called inside of an **on PDU** handler. The function will return in its second parameter the CAN (or CAN-FD) frame, the PDU was contained.

## Parameters

- **this**: Handle to the currently handled (received) PDU object.
- **msg**: Reference to a [message object](../../CAN/CAPLfunctionMessageSelectors.md) that will contain the overall received message data and information.

## Return Values

- **0**: Data access successful.
- **-1**: Wrong bus system; CAN message is not available.
- **-2**: Message does not support this info.
- **-3**: The PDU object is invalid.
- **-4**: PDU is not of Rx type.
- **-5**: Parameter too small (e.g. array has too less bytes)
- **-6**: Message or PDU is not available (any more)

## Example

```plaintext
on PDU PDU_A
{
  message * aMsg_01;
  long result;
  result = GetCANMessage(this, aMsg_01); // PDU is assumed to be sent on CAN
  if (result == 0)
  {
    write("Received PDU 'PDU_A' in message with CAN ID %lu", aMsg_01.ID);
  }
  else
  {
    write("Error accessing PDU!");
  }
}
```

[on PDU](../EventProcedures/CAPLfunctionOnPDU.md) • [GetFrFrame](CAPLfunctionGetFrFrame.md) • [GetEthernetPacket](CAPLfunctionGetEthernetPacket.md) • [GetPDUsTPIPv6SrcAddr](CAPLfunctionGetPDUsTPIPv6SrcAddr.md) • [GetPDUsTPIPv6DstAddr](CAPLfunctionGetPDUsTPIPv6DstAddr.md) • [GetPDUsTPIPv4SrcAddr](CAPLfunctionGetPDUsTPIPv4SrcAddr.md) • [GetPDUsTPIPv4DstAddr](CAPLfunctionGetPDUsTPIPv4DstAddr.md) • [GetPDUsTPUDPSrcPort](CAPLfunctionGetPDUsTPUDPSrcPort.md) • [GetPDUsTPUDPDstPort](CAPLfunctionGetPDUsTPUDPDstPort.md) • [GetPDUsTPTCPSrcPort](CAPLfunctionGetPDUsTPTCPSrcPort.md) • [GetPDUsTPTCPDstPort](CAPLfunctionGetPDUsTPTCPDstPort.md)
