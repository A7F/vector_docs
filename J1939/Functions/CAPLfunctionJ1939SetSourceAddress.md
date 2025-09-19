[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/Functions/CAPLfunctionJ1939SetSourceAddress.md)

**CAPL Functions** » [J1939](../CAPLfunctionsJ1939StartPage.md) » [Function Overview](../CAPLfunctionsJ1939Overview.md) » J1939SetSourceAddress

# J1939SetSourceAddress

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
void J1939SetSourceAddress (pg* aPG, dword sourceAddress);
```

## Description

Sets the [source address](../../../CANoeCANalyzer/J1939/j1939basics/j1939PGandPGN.md) of a parameter group.

## Parameters

- **aPG**: Source address of this parameter group is set.
- **sourceAddress**: New source address. A value bigger than 255 is truncated.

## Return Values

—

## Example

—

[J1939 General Functions](../CAPLfunctionsJ1939Overview.md#General)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
