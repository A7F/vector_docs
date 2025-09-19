[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILOnCA.md)

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Interaction Layer](../CAPLfunctionsISOILOverview.md) » Iso11783IL_OnCA

# Iso11783IL_OnCA (Callback)

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long Iso11783IL_OnCA(long newAddress);
```

## Description

This callback function is called from the ISO11783 IL when a **Command Address** message is received. The assignment of the new address can be suppressed.

## Parameters

- **newAddress**
  - 0..253: new address that ECU can accept
  - 254: ECU has to go offline

## Return Values

- **1**: Accept the new address
- **0**: Don’t accept the new address

## Example

```plaintext
long Iso11783IL_OnCA(long address)
{
  if(address == 2)
    return 0; // don’t accept the address ‘2’
  else
    return 1;
}
```

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
