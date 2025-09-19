[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/Functions/CAPLfunctionJ1939CheckMultiPG.md)

[CAPL Functions](../../CAPLfunctions.md) » [J1939](../CAPLfunctionsJ1939StartPage.md) » [Function Overview](../CAPLfunctionsJ1939Overview.md) » J1939CheckMultiPG

# J1939CheckMultiPG

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long J1939CheckMultiPG(message multiPG);
long J1939CheckMultiPG(message multiPG, char[] errorText);
```

## Description

Checks whether a [J1939-22 Multi-PG](../../../CANoeCANalyzer/J1939/J1939CANfd/1939CANfd.md) and its Contained-PGs (C-PGs) are consistent.

## Parameters

- **multiPG**: A J1939-22 Multi-PG message.
- **errorText**: Returns an error text if return value is < 0.

## Return Values

- **0**: Multi-PG is valid
- **-1**: Leading three bytes of Padding C-PG (TOS = 0) must be 0x00
- **-2**: Padding bytes 4-15 shall be set all to 0xAA or all to 0x00
- **-3**: Data length of Multi-PG is unnecessary big for the contained C-PGs
- **-4**: Multi-PG is using the D_PDU1 format (destination specific) and therefore must not contain PDU2 C-PGs
- **-5**: Not enough space for another C-PG. Expected padding bytes
- **-6**: C-PG is a A-PDU1 and therefore PDU Specific (PS) field of PGN must be 0x00
- **-7**: Length of C-PG exceeds Multi-PG
- **-8**: C-PGs do not fit into the Multi-PG
- **-9**: Length of C-PG exceeds maximum of 60 bytes
- **-10**: Assurance Data length exceeds length of C-PG
- **-11**: A Multi-PG shall not contain Address Claimed messages

## Example

```plaintext
void CheckMultiPG(message * multiPG)
{
  long result;
  char errorText[128];
  result = J1939CheckMultiPG(multiPG, errorText);
  if (result != 0)
  {
    writeEx(-3, 3, "Multi-PG is not consistent: %s", errorText);
  }
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
