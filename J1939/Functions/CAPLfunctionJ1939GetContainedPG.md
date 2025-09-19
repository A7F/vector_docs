[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/Functions/CAPLfunctionJ1939GetContainedPG.md)

[CAPL Functions](../../CAPLfunctions.md) » [J1939](../CAPLfunctionsJ1939StartPage.md) » [Function Overview](../CAPLfunctionsJ1939Overview.md) » J1939GetContainedPG

# J1939GetContainedPG

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
long J1939GetContainedPG(message multiPG, byte index, pg cpg);
```

## Description

Returns a Contained PG (C-PG) at the specified index of a [J1939-22 Multi-PG](../../../CANoeCANalyzer/J1939/J1939CANfd/1939CANfd.md).

This function does not return the parameters of Padding C-PG (TOS = 0).

## Parameters

- **multiPG**: A J1939-22 Multi-PG message.
- **index**: Index of the C-PG within the Multi-PG.
- **cpg**: This PG is filled with data of the Contained PG (Parameter Group Number (PGN), type of service, trailer format, payload as well as source and destination address of the Multi-PG and priority of the Multi-PG.

## Return Values

- **0**: The function successfully determined the parameters
- **-1**: Message is not a J1939-22 Multi-PG message
- **-2**: Index is invalid

## Example

See [J1939GetNumberOfContainedPGs](CAPLfunctionJ1939GetNumberOfContainedPGs.md).

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
