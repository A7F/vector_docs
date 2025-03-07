[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILControlWait.md)

**CAPL Functions** » **ISO11783** » **ISO11783 Interaction Layer** » Iso11783IL_ControlWait

# Iso11783IL_ControlWait

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long Iso11783IL_ControlWait();
```

## Description

Sending messages is suspended. Setting of signal is not possible.

Call [Iso11783IL_ControlResume](CAPLfunctionIso11783ILControlResume.md) to activate sending again.

## Parameters

—

## Return Values

0 on success or [error code](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

```plaintext
on key 'w'
{
    Iso11783IL_ControlWait();
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)