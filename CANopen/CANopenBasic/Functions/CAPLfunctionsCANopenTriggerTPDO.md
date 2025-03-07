[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CANopen/CANopenBasic/Functions/CAPLfunctionsCANopenTriggerTPDO.md)

**CAPL Functions** » [CANopen](../../CAPLfunctionsCANopenOverview.md) » [Basic Functions](../CAPLfunctionsCANopenBasicOverview.md) » CANopenTriggerTPDO

# CANopenTriggerTPDO

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe:lite DE • CANoe4SW DE

## Function Syntax

```plaintext
void CANopenTriggerTPDO(dword pdoNumber, dword[] errCode)
```

## Description

Triggers the immediate transmission of a TPDO.

## Parameters

- **pdoNumber**: Number of the transmit PDO.
- **errCode**: Error code buffer (is entered in index 0 of the field).
  - 1: Invalid call
  - 2: Wrong NMT state
  - 3: Wrong transmission type
  - 4: PDO inhibited (i.e. not sent because of inhibit time)
  - 5: Invalid PDO number
  - 6: PDO not found in the object dictionary
  - 7: No CANopen license
  - 8: No CAN channel

## Example

—

© Vector Informatik GmbH

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)