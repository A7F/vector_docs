[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/Functions/CAPLfunctionJ1939ConvertMessageToPg.md)

[CAPL Functions](../../CAPLfunctions.md) » [J1939](../CAPLfunctionsJ1939StartPage.md) » [Function Overview](../CAPLfunctionsJ1939Overview.md) » J1939ConvertMessageToPg

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

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
