[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILOPSaveAuxAssignment.md)

**CAPL Functions** » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Interaction Layer](../CAPLfunctionsISOILOverview.md) » Iso11783IL_OPSaveAuxAssignment

# Iso11783IL_OPSaveAuxAssignment

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long Iso11783IL_OPSaveAuxAssignment( char filename[] ); // form 1
long Iso11783IL_OPSaveAuxAssignment( dbNode implement, char filename[] ); // form 2
```

## Description

The function saves the current auxiliary input assignment as **Preferred Auxiliary Input Assignment** in an INI file.

With the function [Iso11783IL_OPLoadAuxAssignment](CAPLfunctionIso11783ILOPLoadAuxAssignment.md) the **Preferred Assignment** can be load and used again.

## Parameters

- **filename**: Filename of an INI file (*.ini)
- **implement**: Simulation node to apply the function.

## Return Values

- **0**: Function has been executed successfully
- **< 0**: An error has occurred, see [error codes](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

```plaintext
Iso11783IL_OPSaveAuxAssignment( "Sprayer.INI");
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
