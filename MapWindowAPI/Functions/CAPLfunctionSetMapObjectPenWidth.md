# SetMapObjectPenWidth

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
long SetMapObjectPenWidth( long handle, float penWidth );
```

## Description

Sets the pen width of a map object.

## Parameters

- **handle**: Reference of the map object.
- **penWidth**: Pen width for the map object to be drawn (default: 1).

## Return Values

- **0**: Success
- **≠0**: The set went wrong.

## Example

See [Map Window API example](../CAPLfunctionMapWindowAPI.md).
