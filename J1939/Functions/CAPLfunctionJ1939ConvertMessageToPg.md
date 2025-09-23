# J1939ConvertMessageToPg

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
void J1939ConvertMessageToPg(pg* target, message* source);
```

## Description

Converts a CAN message to a J1939 parameter group (PG). This function copies all possible selectors as well as data up to 64 bytes.

## Parameters

- **target**: Target parameter group.
- **source**: Source CAN frame.

## Return Values

—

## Example

```plaintext
variables
{
  message * msgArray[100];
}

void GetPgOfArray(byte index, pg * target)
{
  if (index >= 100) return;

  J1939ConvertMessageToPg(target, msgArray[index]);
}
```

[J1939ConvertPgToMessage](CAPLfunctionJ1939ConvertPgToMessage.md)
