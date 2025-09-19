[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/Functions/CAPLfunctionJ1939SetDatapage.md)

**CAPL Functions** » [J1939](../CAPLfunctionsJ1939StartPage.md) » [Function Overview](../CAPLfunctionsJ1939Overview.md) » J1939SetDatapage

# J1939SetDatapage

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
void J1939SetDatapage (pg* aPG, dword dataPage);
```

## Description

Sets the [data page](../../../CANoeCANalyzer/J1939/j1939basics/j1939PGandPGN.md) of a parameter group.

## Parameters

- **aPG**: Data page of this parameter group is set.
- **dataPage**: New data page. A value bigger than 1 is truncated.

## Return Values

—

## Example

—

[J1939 General Functions](../CAPLfunctionsJ1939Overview.md#General)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
