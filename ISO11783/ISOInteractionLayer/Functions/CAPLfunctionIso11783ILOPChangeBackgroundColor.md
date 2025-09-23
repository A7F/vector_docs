[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILOPChangeBackgroundColor.md)

**CAPL Functions** » **ISO11783** » **ISO11783 Interaction Layer** » **Iso11783IL_OPChangeBackgroundColor**

# Iso11783IL_OPChangeBackgroundColor

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long Iso11783IL_OPChangeBackgroundColor( dword objectID, dword color ); // form 1
long Iso11783IL_OPChangeBackgroundColor( dbNode implement, dword objectID, dword color ); // form 2
```

## Description

This function changes the background color of an object. The **Change Background Color** command is sent to the Virtual Terminal.

## Parameters

- **objectID**: Object ID of the object, which should change the background color
- **color**: Color index
- **implement**: Simulation node to apply the function.

## Return Values

- **0**: Function has been executed successfully
- **< 0**: An error has occurred, see [error codes](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

```plaintext
Iso11783IL_OPChangeBackgroundColor( 1200, 5 );
```
