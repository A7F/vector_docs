[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILOPSelectActiveWorkingSet.md)

**CAPL Functions** » **ISO11783** » **ISO11783 Interaction Layer** » Iso11783IL_OPSelectActiveWorkingSet

# Iso11783IL_OPSelectActiveWorkingSet

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long Iso11783IL_OPSelectActiveWorkingSet( dword workingSetAddress ); // form 1
long Iso11783IL_OPSelectActiveWorkingSet( dbNode implement, dword workingSetAddress ); // form 2
```

## Description

Sends a **Select Active Working Set** command to the Virtual Terminal to select a new active Working Set. The necessary device name for this command is determined by means of parameter **workingSetAddress**.

## Parameters

- **implement**: Simulation node to apply the function.
- **workingSetAddress**: Address of the new active Working Set, 0..253.

## Return Values

- **0**: function has been executed successfully
- **< 0**: an error has occurred, see [error codes](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

—

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)