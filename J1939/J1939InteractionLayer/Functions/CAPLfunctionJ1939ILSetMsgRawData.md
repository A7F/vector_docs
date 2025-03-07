[J1939ILSetMsgRawData](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/J1939InteractionLayer/Functions/CAPLfunctionJ1939ILSetMsgRawData.md)

**CAPL Functions** » [J1939](../../CAPLfunctionsJ1939StartPage.md) » [J1939 IL](../CAPLfunctionsJ1939ILOverview.md) » J1939ILSetMsgRawData

# J1939ILSetMsgRawData

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long J1939ILSetMsgRawData(dbMsg msg, long dataSize, byte data[] ); // form 1`
- `long J1939ILSetMsgRawData(dbNode node, dbMsg msg, long dataSize, byte data[] ); // form 2`
- `long J1939ILSetMsgRawData(dbMsg msg, long dataSize, char data[] ); // form 3`
- `long J1939ILSetMsgRawData(dbNode node, dbMsg msg, long dataSize, char data[] ); // form 4`
- `long J1939ILSetMsgRawData(dbMsg msg, pg * pgData ); // form 5`
- `long J1939ILSetMsgRawData(dbNode node, dbMsg msg, pg * pgData ); // form 6`

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
  J1939ILSetMsgRawData( ECUID, elCount(data), data );
}
```

© Vector Informatik GmbH

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)