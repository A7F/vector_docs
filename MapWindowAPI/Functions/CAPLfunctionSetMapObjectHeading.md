# SetMapObjectHeading

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
long SetMapObjectHeading( long handle, float rotation );
```

## Description

Sets the heading of a map object.

## Parameters

- **handle**: Reference of the map object.
- **rotation**: Current heading in degrees relating to north (0°..360°, default: 0°).

## Return Values

- **0**: Success
- **≠0**: The set went wrong.

## Example

See [Map Window API example](../CAPLfunctionMapWindowAPI.md).
