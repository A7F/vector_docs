[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILOPChangeListItem.md)

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Interaction Layer](../CAPLfunctionsISOILOverview.md) » Iso11783IL_OPChangeListItem

# Iso11783IL_OPChangeListItem

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long Iso11783IL_OPChangeListItem( dword inputID, dword index, dword itemID ); // form 1
long Iso11783IL_OPChangeListItem( dbNode implement, dword inputID, dword index, dword itemID ); // form 2
```

## Description

The function changes an item in an input list object. A **Change List Item** command is sent to the Virtual Terminal.

## Parameters

- **inputID**: Object ID of the input list object
- **index**: Index of the item
- **itemID**: Object ID which is set to the index position
- **implement**: Simulation node to apply the function.

## Return Values

- **0**: Function has been executed successfully
- **< 0**: An error has occurred, see [error codes](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

```plaintext
Iso11783IL_OPChangeListItem( 1200, 1, 1250 );
```
