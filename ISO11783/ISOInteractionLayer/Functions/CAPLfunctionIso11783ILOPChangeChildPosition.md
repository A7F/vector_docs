[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILOPChangeChildPosition.md)

**CAPL Functions** » **ISO11783** » **ISO11783 Interaction Layer** » **Iso11783IL_OPChangeChildPosition**

# Iso11783IL_OPChangeChildPosition

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long Iso11783IL_OPChangeChildPosition( dword parentID, dword objectID, long x, long y ); // form 1
long Iso11783IL_OPChangeChildPosition( dbNode implement, dword parentID, dword objectID, long x, long y ); // form 2
```

## Description

The function changes the absolute position of an object inside its parent object. A **Change Child Position** command is sent to the Virtual Terminal.

## Parameters

- **parentID**: Parent object
- **objectID**: Object which should change its position
- **x**: Absolute X Position inside the parent object
- **y**: Absolute Y Position inside the parent object
- **implement**: Simulation node to apply the function.

## Return Values

- **0**: Function has been executed successfully
- **< 0**: An error has occurred, see [error codes](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

```plaintext
Iso11783IL_OPChangeChildPosition( 1000, 1200, 10, 10 );
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)