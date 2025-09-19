[J1939GetPGN](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/Functions/CAPLfunctionJ1939GetPGN.md)

**CAPL Functions** » [J1939](../CAPLfunctionsJ1939StartPage.md) » [Function Overview](../CAPLfunctionsJ1939Overview.md) » J1939GetPGN

# J1939GetPGN

Valid for: CANoe DE • CANoe4SW DE

## Function Syntax

- `dword J1939GetPGN (pg* aPG); // form 1`
- `dword J1939GetPGN (dword canId); // form 2`

## Description

Returns the [parameter group number (PGN)](../../../CANoeCANalyzer/J1939/j1939basics/j1939PGandPGN.md) of a parameter group or CAN ID.

## Parameters

- **aPG**: The function returns the PGN of this parameter group.
- **canId**: The function returns the PGN of this CAN ID.

## Return Values

- **0..3FFFFh**: Parameter group number.

## Example

See [J1939GetSourceAddress](CAPLfunctionJ1939GetSourceAddress.md).

[J1939 General Functions](../CAPLfunctionsJ1939Overview.md#General)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
