[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILOPChangeChildLocation.md)

**CAPL Functions** » **ISO11783** » **ISO11783 Interaction Layer** » Iso11783IL_OPChangeChildLocation

# Iso11783IL_OPChangeChildLocation

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long Iso11783IL_OPChangeChildLocation( dword parentID, dword objectID, long dx, long dy ); // form 1
long Iso11783IL_OPChangeChildLocation( dbNode implement, dword parentID, dword objectID, long dx, long dy ); // form 2
```

## Description

The function moves an object. The object is moved relative inside the parent object. A **Change Child Location** command is sent to the Virtual Terminal.

## Parameters

- **parentID**: Parent object
- **objectID**: Object ID of the object which should be moved
- **dx**: Move X position relative by this value [pixel]
- **dy**: Move Y position relative by this value [pixel]
- **implement**: Simulation node to apply the function.

## Return Values

- **0**: Function has been executed successfully
- **< 0**: An error has occurred, see [error codes](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

```plaintext
// move object 5 pixels to the right
Iso11783IL_OPChangeChildLocation( 1000, 1200, 5, 0 );
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)