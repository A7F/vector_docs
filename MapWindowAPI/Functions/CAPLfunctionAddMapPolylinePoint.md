# AddMapPolylinePoint

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
long AddMapPolylinePoint( long handle, float latitude, float longitude );
```

## Description

Adds a point to a map polyline object. Please note that [DrawMapObject](CAPLfunctionDrawMapObject.md) has to be called afterwards in order to visualize the changes in the Map Window.

## Parameters

- **handle**: Reference of the map object.
- **latitude**: Latitude value of the point to add.
- **longitude**: Longitude value of the point to add.

## Return Values

- **0**: Success
- **≠0**: The add went wrong.

## Example

—
