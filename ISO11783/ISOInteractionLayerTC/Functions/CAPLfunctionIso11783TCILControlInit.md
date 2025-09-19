[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerTC/Functions/CAPLfunctionIso11783TCILControlInit.md)

**CAPL Functions** » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [Task Controller Interaction Layer (TC IL)](../CAPLfunctionsISOILTCOverview.md) » TCIL_ControlInit

# TCIL_ControlInit

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long TCIL_ControlInit(); // form 1
long TCIL_ControlInit(dbNode tc); // form 2
```

## Description

This function can only be used in **on preStart**, to suppress the auto-start function of the IL.

## Parameters

- **tc**: TC simulation node to apply the function.

## Return Values

- **0**: Function has been executed successfully
- **< 0**: An error has occurred, see [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

Example form 1

```plaintext
on preStart
{
    TCIL_ControlInit();
}
```

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
