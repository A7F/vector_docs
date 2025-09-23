# Iso11783OPChangeListItem

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long Iso11783OPChangeListItem( dword ecuHandle, dword inputID, dword index, dword itemID );
```

## Description

The function changes an item in an input list object. A **Change List Item** command is sent to the Virtual Terminal.

## Parameters

- **ecuHandle**: Handle of the ECU (must be created with [Iso11783CreateECU](CAPLfunctionIso11783CreateECU.md))
- **inputID**: Object ID of the input list object
- **index**: Index of the item
- **itemID**: Object ID which is set to the index position

## Return Values

0 or [error code](../CAPLfunctionsISONLErrorCodes.md)

## Example

```plaintext
Iso11783OPChangeListItem( handle, 1200, 1, 1250 );
```
