[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerFS/Functions/CAPLfunctionIso11783FSILSetMsgRawData.md)

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [File Server Interaction Layer (FS IL)](../CAPLfunctionsISOILFSOverview.md) » FSIL_SetMsgRawData

# FSIL_SetMsgRawData

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long FSIL_SetMsgRawData( dbMsg msg, long dataSize, byte data[] ); // form 1
long FSIL_SetMsgRawData( dbNode fs,  dbMsg msg, long dataSize, char data[] ); // form 2
```

## Description

Sets the data bytes of the message. The length of the parameter group is adjusted to size of parameter **dataSize**.

## Parameters

- **msg**: message name from database, must be assigned to the node as Tx message
- **dataSize**: number of data bytes
- **data**: data bytes
- **pgData**: data and DLC are taken from this parameter group
- **fs**: FS simulation node to apply the function

## Return Values

- **0**: Function has been executed successfully
- **< 0**: An error has occurred, see [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

—

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)