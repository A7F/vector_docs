# J1939ConvertPgToMessage

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
void J1939ConvertPgToMessage(message* target, pg* source);
```

## Description

Converts a J1939 parameter group (PG) to a CAN message.

This function copies all possible selectors as well as data up to 64 bytes. Data beyond 64 bytes will be cut off.

## Parameters

- **target**: Target CAN frame.
- **source**: Source parameter group.

## Return Values

—

## Example

```c
variables
{
  message * msgArray[100];
}

void StorePgInArray(byte index, pg * source)
{
  if (index >= 100) return;

  J1939ConvertPgToMessage(msgArray[index], source);
}
```

[J1939ConvertMessageToPg](CAPLfunctionJ1939ConvertMessageToPg.md)
