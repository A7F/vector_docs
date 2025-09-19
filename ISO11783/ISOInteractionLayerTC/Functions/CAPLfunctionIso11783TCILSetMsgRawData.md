[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerTC/Functions/CAPLfunctionIso11783TCILSetMsgRawData.md)

**CAPL Functions** » **ISO11783** » **Task Controller Interaction Layer (TC IL)** » **TCIL_SetMsgRawData**

# TCIL_SetMsgRawData

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long TCIL_SetMsgRawData( dbMsg msg, long dataSize, byte data[] ); // form 1`
- `long TCIL_SetMsgRawData( dbNode tc, dbMsg msg, long dataSize, char data[] ); // form 2`

## Description

Sets the data bytes of the message. The length of the parameter group is adjusted to size of parameter **dataSize**.

## Parameters

- **msg**: message name from database, must be assigned to the node as Tx message
- **dataSize**: number of data bytes
- **data**: data bytes
- **pgData**: data and DLC are taken from this parameter group
- **tc**: TC simulation node to apply the function

## Return Values

—

## Example

—

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
