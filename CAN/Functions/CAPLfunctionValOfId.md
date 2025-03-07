[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CAN/Functions/CAPLfunctionValOfId.md)

[CAPL Functions](../../CAPLfunctions.md) » [CAN](../CAPLfunctionsCANOverview.md) » valOfId

# valOfId

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```
long valOfId(dword id);
long valOfId(message m);
```

## Description

Returns the value of a message identifier independent of its type.

Identifier as long value.

## Parameters

- **message**: Variable of the type message.
- **id**: Id portion of a message.

## Return Values

Identifier as long value.

## Example

```plaintext
on message *
{
    long x;
    x = valOfId(this);
    write("Received Identifier: %d", x);
    output(this);
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)