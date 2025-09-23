[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILSetMsgRawData.md)

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Interaction Layer](../CAPLfunctionsISOILOverview.md) » Iso11783IL_SetMsgRawData

# Iso11783IL_SetMsgRawData

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

- `long Iso11783IL_SetMsgRawData( dbMsg msg, long dataSize, byte data[] );`
- `long Iso11783IL_SetMsgRawData( dbMsg msg, long dataSize, char data[] );`
- `long Iso11783IL_SetMsgRawData( dbMsg msg, pg * pgData );`

## Description

Sets the data bytes of the message. The length of the parameter group is adjusted to size of parameter **dataSize**.

## Parameters

- **msg**: message name from database, must be assigned to the node as Tx message
- **dataSize**: number of data bytes
- **data**: data bytes
- **pgData**: data and DLC are taken from this parameter group

## Return Values

- **0**: success
- **< 0**: [error code](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

```c
on key 't'
{
  char data[10] = "TPMS*V1.0*";
  Iso11783IL_SetMsgRawData( ECUID, elCount(data), data );
}
```
