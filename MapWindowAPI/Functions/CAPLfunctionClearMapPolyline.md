# ClearMapPolyline

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
long ClearMapPolyline( long handle );
```

## Description

Clears all points of a map polyline object. Please note that [DrawMapObject](CAPLfunctionDrawMapObject.md) has to be called afterwards in order to visualize the changes in the Map Window.

## Parameters

- **handle**: Reference of the map object.

## Return Values

- **0**: Success
- **≠0**: The clear went wrong.

## Example

—
