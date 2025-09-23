# OnMapObjectClick

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

`OnMapObjectClick ( long handle );`

## Description

Function is called when a map object is clicked. It is only raised for map objects that are defined as selectable using the function [SetMapObjectSelectable](../Functions/CAPLfunctionSetMapObjectSelectable.md).

## Parameters

- **handle**: Handle of the map object.

## Return Values

- **0**: Success
- **≠0**: The set went wrong.

## Example

```plaintext
OnMapObjectClick(long handle)
{
  // refer to information of a map object here that was stored before for the corresponding handle
}
```
