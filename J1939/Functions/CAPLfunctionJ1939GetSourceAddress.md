[J1939GetSourceAddress](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/Functions/CAPLfunctionJ1939GetSourceAddress.md)

**CAPL Functions** » [J1939](../CAPLfunctionsJ1939StartPage.md) » [Function Overview](../CAPLfunctionsJ1939Overview.md) » J1939GetSourceAddress

# J1939GetSourceAddress

**Valid for**: [CANoe DE](../../../Shared/FeatureAvailability.md) • CANoe4SW DE

## Function Syntax

```plaintext
dword J1939GetSourceAddress (pg* aPG); // form 1
dword J1939GetSourceAddress (dword canId); // form 2
```

## Description

Returns the [source address](../../../CANoeCANalyzer/J1939/j1939basics/j1939PGandPGN.md) of a parameter group or CAN ID.

## Parameters

- **aPG**: The function returns the source address of this parameter group.
- **canId**: The function returns the source address of this CAN ID.

## Return Values

- **0..255**: Source address.

## Example

```plaintext
void MessageIsReceived(dword canId)
{
  write("Receive message with sa %u, da %u, priority %u and data page %u",
    J1939GetPGN(
      J1939GetSourceAddress(canId),
      J1939GetDestAddress(canId),
      J1939GetPrio(canId),
      J1939GetDatapage(canId)
    );
}
```

[J1939 General Functions](../CAPLfunctionsJ1939Overview.md#General)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
