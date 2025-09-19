[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerVT/Functions/CAPLfunctionIso11783VTILSetMsgRawData.md)

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [Virtual Terminal Interaction Layer (VT IL)](../CAPLfunctionsISOILVTOverview.md) » VTIL_SetMsgRawData

# VTIL_SetMsgRawData

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long VTIL_SetMsgRawData( dbMsg msg, long dataSize, byte data[] ); // form 1
long VTIL_SetMsgRawData( dbNode vt,  dbMsg msg, long dataSize, char data[] ); // form 2
```

## Description

Sets the data bytes of the message. The length of the parameter group is adjusted to size of parameter **dataSize**.

## Parameters

- **msg**: message name from database, must be assigned to the node as Tx message
- **dataSize**: number of data bytes
- **data**: data bytes
- **pgData**: data and DLC are taken from this parameter group
- **vt**: VT simulation node to apply the function

## Return Values

- **0**: Function has been executed successfully
- **< 0**: An error has occurred, see [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

Example form 1

```plaintext
void SendPointingEvent(word x, word y, byte touchState)
{
  char buf[8];
  buf[0] = 0x02; // Pointing Event
  buf[1] = x & 0xFF;
  buf[2] = (x >> 8) & 0xFF;
  buf[3] = y & 0xFF;
  buf[4] = (y >> 8) & 0xFF;
  buf[5] = touchState;
  buf[6] = 0xFF;
  buf[7] = 0xFF;
  VTIL_SetMsgRawData(VT12_VT, elCount(buf), buf);
  VTIL_SetMsgEvent(VT12_VT);
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
