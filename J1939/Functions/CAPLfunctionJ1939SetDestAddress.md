[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/Functions/CAPLfunctionJ1939SetDestAddress.md)

**CAPL Functions** » **J1939** » **Function Overview** » **J1939SetDestAddress**

# J1939SetDestAddress

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
void J1939SetDestAddress (pg* aPG, dword destinationAddress);
```

## Description

Sets the [PDU specific](../../../CANoeCANalyzer/J1939/j1939basics/j1939PGandPGN.md) field of a parameter group or CAN ID. For PDU1 messages this is the destination address.

## Parameters

- **aPG**: Destination address of this parameter group is set.
- **destinationAddress**: New destination address (PDU1 Format) or PDU Specific field (PDU2 Format). A value bigger than 255 is truncated.

## Return Values

—

## Example

—

[J1939 General Functions](../CAPLfunctionsJ1939Overview.md#General)

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
