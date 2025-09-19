[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/Functions/CAPLfunctionJ1939GetContainedPGAssuranceData.md)

**CAPL Functions** » **J1939** » **Function Overview** » **J1939GetContainedPGAssuranceData**

# J1939GetContainedPGAssuranceData

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
long J1939GetContainedPGAssuranceData(message multiPG, byte index, qword assuranceData);
```

## Description

Returns the assurance data of a Contained-PG (C-PG) at the specified index of a [J1939-22 Multi-PG](../../../CANoeCANalyzer/J1939/J1939CANfd/1939CANfd.md).

## Parameters

- **multiPG**: A J1939-22 Multi-PG message
- **index**: Index of the C-PG within the Multi-PG
- **assuranceData**: Returns the assurance data of the C-PG

## Return Values

- **>0**: Length in bytes of assurance data
- **0**: C-PG contains no assurance data
- **-1**: Message is no J1939-22 Multi-PG message
- **-2**: Index is invalid

## Example

See [J1939GetNumberOfContainedPGs](CAPLfunctionJ1939GetNumberOfContainedPGs.md).

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
