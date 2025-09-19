[J1939ILControlInit](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/J1939InteractionLayer/Functions/CAPLfunctionJ1939ILControlInit.md)

**Structure Path:** [CAPL Functions](../../../CAPLfunctions.md) » [J1939](../../CAPLfunctionsJ1939StartPage.md) » [J1939 IL](../CAPLfunctionsJ1939ILOverview.md) » J1939ILControlInit

# J1939ILControlInit

**Valid for:** CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long J1939ILControlInit(); // form 1
long J1939ILControlInit(dbNode node);  // form 2
```

## Description

This function can only be used in **on preStart**, to suppress the auto-start function of the IL.

## Parameters

- **node**: Simulation node to apply the function

## Return Values

0 on success or [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

```plaintext
on preStart
{
    J1939ILControlInit();
}
```

**Version:** CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
