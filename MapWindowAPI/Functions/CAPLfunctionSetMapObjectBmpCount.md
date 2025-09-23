# SetMapObjectBmpCount

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
long SetMapObjectBmpCount( long handle, long bitmapCount );
```

## Description

Sets the number of bitmaps in a multi bitmap file of a map object.

## Parameters

- **handle**: Reference of the map object
- **bitmapCount**: Number of available bitmaps in a multi bitmap file (default: 1)

## Return Values

- **0**: Success
- **≠0**: The set went wrong.

## Example

See example of C2xSetMapObjectBmpFilePath.
