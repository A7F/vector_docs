[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILpdddelete.md)

**CAPL Functions** » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Interaction Layer](../CAPLfunctionsISOILOverview.md) » Iso11783IL_PDDDelete

# Iso11783IL_PDDDelete

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long Iso11783IL_PDDDelete( ); // form 1
long Iso11783IL_PDDDelete( dbNode implement ); // form 2
```

## Description

Deletes the process data directory and disconnects from the Task Controller.

## Parameters

- **implement**: Simulation node to apply the function.

## Return Values

- **0**: process data directory has been deleted successfully
- **< 0**: an error has occurred

## Example

```plaintext
Iso11783IL_PDDDelete( );
```

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
