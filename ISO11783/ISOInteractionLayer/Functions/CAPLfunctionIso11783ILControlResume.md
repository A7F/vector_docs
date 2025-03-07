[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILControlResume.md)

**CAPL Functions** » **ISO11783** » **ISO11783 Interaction Layer** » Iso11783IL_ControlResume

# Iso11783IL_ControlResume

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long Iso11783IL_ControlResume();
```

## Description

After suspending the ISO11783 IL with [Iso11783IL_ControlWait](CAPLfunctionIso11783ILControlWait.md), this function restarts the IL. The ISO11783 IL starts sending cyclic messages again.

## Parameters

—

## Return Values

0 on success or [error code](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

```plaintext
on key 'r'
{
    Iso11783IL_ControlResume();
}
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)