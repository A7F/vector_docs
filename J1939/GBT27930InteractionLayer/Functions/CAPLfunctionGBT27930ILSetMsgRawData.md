[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/GBT27930InteractionLayer/Functions/CAPLfunctionGBT27930ILSetMsgRawData.md)

**CAPL Functions** » **J1939** » **GB/T 27930 IL** » **GBT27930IL_SetMsgRawData**

# GBT27930IL_SetMsgRawData

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long GBT27930IL_SetMsgRawData(dbMsg msg, long dataSize, byte data[] ); // form 1`
- `long GBT27930IL_SetMsgRawData(dbNode node, dbMsg msg, long dataSize, byte data[] ); // form 2`
- `long GBT27930IL_SetMsgRawData(dbMsg msg, long dataSize, char data[] ); // form 3`
- `long GBT27930IL_SetMsgRawData(dbNode node, dbMsg msg, long dataSize, char data[] ); // form 4`
- `long GBT27930IL_SetMsgRawData(dbMsg msg, pg * pgData ); // form 5`
- `long GBT27930IL_SetMsgRawData(dbNode node, dbMsg msg, pg * pgData ); // form 6`

## Description

Sets the data bytes of the message. The length of the parameter group is adjusted to size of parameter `dataSize`.

## Parameters

- **msg**: message name from database, must be assigned to the node as [Tx message](../../../../CANoeCANalyzer/J1939/j1939IL/j1939ILConfigureDB.md)
- **dataSize**: number of data bytes
- **data**: data bytes
- **pgData**: data and DLC are taken from this parameter group
- **node**: Simulation node to apply the function

## Return Values

- **0**: success
- **< 0**: [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

```plaintext
on key 't'
{
  char data[10] = "TPMS*V1.0*";
  GBT27930IL_SetMsgRawData( ECUID, elCount(data), data );
}
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
