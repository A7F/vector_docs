# SetMapObjectBmpIndex

**Valid for**: CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
long SetMapObjectBmpIndex( long handle, long bitmapIndex );
```

## Description

Sets the index of a bitmap in a multi bitmap file for a map object of the type bitmap which must be shown.

## Parameters

- **handle**: Reference of the map object.
- **bitmapIndex**: Index of the to be displayed bitmap in a multi bitmap file (default: 0).

## Return Values

- **0**: Success
- **≠0**: The set went wrong.

## Example

See example of C2xSetMapObjectBmpFilePath.
