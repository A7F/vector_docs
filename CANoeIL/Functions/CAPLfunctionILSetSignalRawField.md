[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CANoeIL/Functions/CAPLfunctionILSetSignalRawField.md)

## ILSetSignalRawField

[CAPL Functions](../../CAPLfunctions.md) » [CANoe IL](../CAPLfunctionsCANoeILOverview.md) » ILSetSignalRawField

**Valid for**: CANoe DE • CANoe4SW DE

**Note**  
The function does not work with multiplex messages.

### Function Syntax

```plaintext
long ILSetSignalRawField (dbSignal sig, const char *pData, long aDataLen)
```

### Description

Sets the transferred signal to the provided value. Use for integer signals > 32 bit.

### Parameters

- **sig**: Signal that should be set. Specify as follows 'Message::Signal'.
- **pData**: Byte array, which contains the raw data.
- **aDataLen**: Length of the byte array.

### Return Values

- **0**: No error.
- **-1**: Momentary state of the IL does not permit this query.
- **-50**: Nodelayer is inactive — possibly deactivated in the node’s configuration dialog.
- **-100**: Signal or message was not found in the database or is not mapped to this node.
- **-101**: The maximum possible value range was exceeded (no sending on the bus).
- **-103**: Invalid value was passed.

### Example

—

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)