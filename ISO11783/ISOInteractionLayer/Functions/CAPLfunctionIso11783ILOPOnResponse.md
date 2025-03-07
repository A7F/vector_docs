[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILOPOnResponse.md)

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Interaction Layer](../CAPLfunctionsISOILOverview.md) » Iso11783IL_OPOnResponse

# Iso11783IL_OPOnResponse (Callback)

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```c
void Iso11783IL_OPOnResponse( pg VTtoECU response );
```

## Description

The function is called by the node layer, if a response from the Virtual Terminal is received. If a response is **not** received, the callback function [Iso11783IL_OPOnError](CAPLfunctionIso11783ILOpOnError.md) is called.

## Parameters

- **response**: Parameter group containing the answer of the Virtual Terminal

## Return Values

—

## Example

```c
void Iso11783IL_OPOnResponse( pg VTtoECU response )
{
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)