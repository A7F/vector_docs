# isStdId, isExtId

**Valid for**: CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

- `long isStdId(dword id);`
- `long isStdId(message m);`
- `long isExtId(dword id);`
- `long isExtId(message m);`

## Description

Checks parameter for [extended identifier](../../../CANoeCANalyzer/General/CANExtendedIdentifier.md) (29 bit) or standard identifier (11 Bit).

## Parameters

- **message**: Variable of type message
- **id**: Id part of a message

## Return Values

1 if check was successful, else 0

## Example

```plaintext
...
if(isExtId(this))
    write("extended identifier");
else
    write("standard identifier");
or
std = isStdId(m100.id);
```
