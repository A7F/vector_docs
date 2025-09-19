[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/Functions/CAPLfunctionJ1939CalculateCrcOfSDM.md)

**CAPL Functions** » **J1939** » **Function Overview** » **J1939CalculateCrcOfSDM**

# J1939CalculateCrcOfSDM

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
dword J1939CalculateCrcOfSDM(qword sdmPayload)
```

## Description

Calculates CRC for payload of a Safety Data Message according to [SAE J1939-76](../../../CANoeCANalyzer/J1939/j1939basics/j1939FunctionalSafety.md)

## Parameters

- **sdmPayload**: Payload of a Safety Data Message.

## Return Values

Calculated CRC

## Example

—

[J1939FillSHM](CAPLfunctionJ1939FillSHM.md) • [J1939ParseSHM](CAPLfunctionJ1939ParseSHM.md)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
