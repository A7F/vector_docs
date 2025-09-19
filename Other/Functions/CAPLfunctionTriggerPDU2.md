[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionTriggerPDU2.md)

**CAPL Functions** » **General** » **Function Overview** » **TriggerPDU2**

# TriggerPDU2

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long triggerPDU2(pdu PDUObject, dword DestBusContext, char[] DBName, char[] TXNode, char[] PDUName, dword ShortHeaderID, dword LongHeaderID, dword Flags, dword PayloadLen);
```

## Description

This function forwards a received PDU to another Network. The destination PDU can be changed. For gateway applications this function can be useful.

## Parameters

- **PDUObject**: PDU object to be transmitted.
- **DestBusContext**: Bus context of the destination network where the PDU is to be sent.
- **DBName**: Name of the cluster in the database.
- **TXNode**: Name of the transmitter node, can be used with an empty string also.
- **PDUName**: Name of the PDU to be transmitted.
- **ShortHeaderID**: ID of the PDU to be transmitted. 0 means not configured.
- **LongHeaderID**: ID of the PDU to be transmitted. 0 means not configured.
- **Flags**: Reserved, 0 means not configured.
- **PayloadLen**: Length of Payload in Byte.

## Return Values

- **result=-6**: Triggering of PDU failed.
- **result=-5**: PDU Tx node server not present.
- **result=-4**: Measurement not running.
- **result=-3**: Channels not different or destination channel invalid.
- **result=-2**: PDU object invalid.
- **result=-1**: Any name parameter invalid (null).
- **result=0**: Success.

## Example

```plaintext
variables
{
  dword dstBusContext;
}
on preStart
{
  dstBusContext = GetBusNameContext("GWout");
  write("GWout = %d", dstBusContext);
  write("GWin  = %d", GetBusNameContext("GWin"));
}
on PDU msgchannel1.*
{
  long result;
  pdu * out;

  if((this.MsgChannel == 1) && (this.BusType == 1 /* CAN */))
  {
    result = TriggerPDU2(this, dstBusContext, "BODY3" /* DBName */, "" /* TXNode */, this.Name /* PDUName */, this.ShortHeaderID, this.LongHeaderID, 0, this.PduLength);
    writeLineEx(-3, 1, "Trigger (bridge) PDU '%s' onto bus (Channel %d, BusType %d) returned %d.", this.Name (dstBusContext & 0xFFFF), (dstBusContext >> 16), result);
  }
}
```

[triggerPDU](CAPLfunctionTriggerPDU.md) • [GetBusNameContext](CAPLfunctionGetBusNameContext.md)

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) • [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
