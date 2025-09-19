[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/Functions/CAPLfunctionJ1939GetDestAddress.md)

**CAPL Functions** » [J1939](../CAPLfunctionsJ1939StartPage.md) » [Function Overview](../CAPLfunctionsJ1939Overview.md) » J1939GetDestAddress

# J1939GetDestAddress

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `dword J1939GetDestAddress (pg* aPG); // form 1`
- `dword J1939GetDestAddress (dword canId); // form 2`

## Description

Returns the value of the [PDU specific](../../../CANoeCANalyzer/J1939/j1939basics/j1939PGandPGN.md) field of a parameter group or CAN ID. For PDU1 messages this is the destination address.

## Parameters

- **aPG**: The function returns the destination address of this parameter group.
- **canId**: The function returns the destination address of this CAN ID.

## Return Values

- **0..255**: Destination address (PDU1 Format) / PDU Specific field (PDU2 Format).

## Example

See [J1939GetSourceAddress](CAPLfunctionJ1939GetSourceAddress.md).

[J1939 General Functions](../CAPLfunctionsJ1939Overview.md#General)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
