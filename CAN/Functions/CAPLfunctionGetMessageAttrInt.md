[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CAN/Functions/CAPLfunctionGetMessageAttrInt.md)

**CAPL Functions** » [CAN](../CAPLfunctionsCANOverview.md) » getMessageAttrInt

# getMessageAttrInt

**Valid for**: CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

**Note**: This function finds the value of the message attribute in the database again with each call. If the message is already known when the CAPL program is being written, the attribute should be found directly by its selector syntax (`<Message variable>.<Attribute name>` e.g. `absData.msgCycleTime`).

## Function Syntax

```plaintext
long GetMessageAttrInt(message canMessage, char attributeName[]);
long GetMessageAttrInt(pg parameterGroup, char attributeName[]);
```

## Description

Gets the value of a message attribute from the database.

A user-defined attribute with the name specified in the parameter, and of the Integer type, must be defined in the database. If no such attribute is defined, the function returns 0. If no attribute value is assigned to the message in the database, the default value of the attribute definition is returned.

## Parameters

- **canMessage**: Message variable
- **attributeName**: Attribute name

## Return Values

Value of the attribute (or default value) from the database.

## Example

This example outputs the value of the message attribute **GenMsgCycleTime** in the Write Window when the message is received.

The attribute name must be written as defined in the database. You can find the attribute name in the attribute window of the database.

```plaintext
on message *
{
    long cycleTimeValue1;
    long cycleTimeValue2;
    cycleTimeValue1 = getMessageAttrInt(this, "GenMsgCycleTime");
    write("CycleTime of message id %x = %d", this.id, cycleTimeValue1);
    message EngineData gMsgEngineData;
    cycleTimeValue2 = getMessageAttrInt(gMsgEngineData, "GenMsgCycleTime");
    write("CycleTime of message id %x = %d", this.id, cycleTimeValue2);
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)