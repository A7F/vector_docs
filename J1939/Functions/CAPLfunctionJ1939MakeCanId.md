[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/Functions/CAPLfunctionJ1939MakeCanId.md)

**CAPL Functions** » [J1939](../CAPLfunctionsJ1939StartPage.md) » [Function Overview](../CAPLfunctionsJ1939Overview.md) » J1939MakeCanId

# J1939MakeCanId

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
dword J1939MakeCanId (byte priority, dword pgn, byte destinationAddress, byte sourceAddress, byte setExtendedBit);
```

## Description

Assembles a CAN ID of a [parameter group](../../../CANoeCANalyzer/J1939/j1939basics/j1939PGandPGN.md) (PG) from source/destination address, parameter group number (PGN) and priority.

For a PGN of PDU Format 2, the parameter destination address is ignored.

The parameter **setExtendedBit** defines whether the most significant bit of the resulting CAN ID is set (see [CAN Extended Identifier](../../../CANoeCANalyzer/General/CANExtendedIdentifier.md)).

## Parameters

- **priority**: Priority of the PG.
- **pgn**: Parameter group number (PGN) of the PG.
- **destinationAddress**: Destination address of the PG.
- **sourceAddress**: Source address of the PG.
- **setExtendedBit**: Defines whether the most significant bit of the resulting CAN ID is set.

## Return Values

—

## Example

—

[J1939 General Functions](../CAPLfunctionsJ1939Overview.md#General)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
