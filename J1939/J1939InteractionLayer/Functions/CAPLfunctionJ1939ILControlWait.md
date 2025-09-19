[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/J1939InteractionLayer/Functions/CAPLfunctionJ1939ILControlWait.md)

**CAPL Functions** » [J1939](../../CAPLfunctionsJ1939StartPage.md) » [J1939 IL](../CAPLfunctionsJ1939ILOverview.md) » J1939ILControlWait

# J1939ILControlWait

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long J1939ILControlWait(); // form 1`
- `long J1939ILControlWait(dbNode node); // form 2`

## Description

Sending messages is suspended. Setting of signal is not possible. Call [J1939ILControlResume](CAPLfunctionJ1939ILControlResume.md) to activate sending again.

## Parameters

- **node**: Simulation node to apply the function

## Return Values

0 on success or [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

```plaintext
on key 'w'
{
    J1939ILControlWait();
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
