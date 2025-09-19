[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILPDDOnIdentifyWorkingSet.md)

**CAPL Functions** » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Interaction Layer](../CAPLfunctionsISOILOverview.md) » Iso11783IL_PDDOnIdentifyWorkingSet

# Iso11783IL_PDDOnIdentifyWorkingSet

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long Iso11783IL_PDDOnIdentifyWorkingSet( );
```

## Description

The function is called by the ISO11783 Interaction Layer to determine if the interaction layer is responsible for sending of the Working Set Master message after the Task Controller starts to send his status messages.

If this callback function is not implemented or it returns the value 1, the Working Set Master message is sent by the ISO11783 Interaction Layer. The transmitted number of Working Set members is 1. If the return value of the function is 0, the ISO11783 Interaction Layer doesn’t send the Working Set Master message. Instead, the CAPL application sends the Working Set Master message.

## Parameters

—

## Return Values

- **1**: Working Set Master message is sent by the ISO11783 Interaction Layer
- **0**: Working Set Master message is sent by the CAPL application

## Example

```plaintext
LONG Iso11783IL_PDDOnIdentifyWorkingSet( )
{
  return 1;
}
```

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
