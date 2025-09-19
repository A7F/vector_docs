[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/Functions/CAPLfunctionJ1939SetPrio.md)

[CAPL Functions](../../CAPLfunctions.md) » [J1939](../CAPLfunctionsJ1939StartPage.md) » [Function Overview](../CAPLfunctionsJ1939Overview.md) » J1939SetPrio

# J1939SetPrio

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
void J1939SetPrio (pg* aPG, dword priority);
```

## Description

Sets the [priority](../../../CANoeCANalyzer/J1939/j1939basics/j1939PGandPGN.md) of a parameter group or CAN ID.

## Parameters

- **aPG**: Priority of this parameter group is set.
- **priority**: New priority. A value bigger than 7 is truncated.

## Return Values

—

## Example

See [J1939GetSourceAddress](CAPLfunctionJ1939GetSourceAddress.md).

[J1939 General Functions](../CAPLfunctionsJ1939Overview.md#General)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
