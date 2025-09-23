# SetMapObjectPosition

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
long SetMapObjectPosition( long handle, float latitude1, float longitude1 ); // form 1
long SetMapObjectPosition( long handle, float latitude1, float longitude1, float latitude2, float longitude2 ); // form 2
```

## Description

Sets the GPS position of a map object either for one (form 1) or two (form 2) points.

- In case of map object type **square**, **rectangle**, **ellipse**, **cross**, **triangle**, and **bitmap** the position of the center is set.
- In case of a **text** object the position of the left upper edge is set.
- In case of a **line** two positions need to be set (form 2).

## Parameters

- **handle**: Reference of the map object.
- **latitude1**: First latitude value of the map object to be drawn.
- **longitude1**: First longitude value of the map object to be drawn.
- **latitude2**: Second latitude value of the map object to be drawn (needed for drawing lines).
- **longitude2**: Second longitude value of the map object to be drawn (needed for drawing lines).

## Return Values

- **0**: Success
- **≠0**: The set went wrong.

## Example

See [Map Window API example](../CAPLfunctionMapWindowAPI.md).
