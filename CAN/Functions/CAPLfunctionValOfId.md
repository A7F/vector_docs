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
