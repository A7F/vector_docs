[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/Functions/CAPLfunctionJ1939ConvertPgToMessage.md)

**CAPL Functions** » [J1939](../CAPLfunctionsJ1939StartPage.md) » [Function Overview](../CAPLfunctionsJ1939Overview.md) » J1939ConvertPgToMessage

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

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)