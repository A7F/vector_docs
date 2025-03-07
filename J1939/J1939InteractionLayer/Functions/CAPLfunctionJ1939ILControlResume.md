[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/J1939InteractionLayer/Functions/CAPLfunctionJ1939ILControlResume.md)

[CAPL Functions](../../../CAPLfunctions.md) » [J1939](../../CAPLfunctionsJ1939StartPage.md) » [J1939 IL](../CAPLfunctionsJ1939ILOverview.md) » J1939ILControlResume

# J1939ILControlResume

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long J1939ILControlResume(); // form 1
long J1939ILControlResume(dbNode node); // form 2
```

## Description

After suspending the J1939 IL with [J1939ILControlWait](CAPLfunctionJ1939ILControlWait.md), this function restarts the IL. The J1939 IL starts sending cyclic messages again.

## Parameters

- **node**: Simulation node to apply the function

## Return Values

0 on success or [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

```plaintext
on key 'r'
{
    J1939ILControlResume();
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)