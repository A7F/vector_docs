# MediaCreateMediaType

**Valid for**: CANoe DE • CANoe4SW DE

## Function Syntax

```
dword MediaCreateMediaType ();
```

## Description

Creates an empty media type. After usage use [MediaReleaseMediaType](CAPLfunctionMediaReleaseMediaType.md) to release the media type.

## Parameters

—

## Return Values

- **0**: The function failed. Call [MediaGetLastError](CAPLfunctionMediaGetLastError.md) to get a more specific error code.
- **≠0**: Media type handle

## Example

—

[See Also](javascript:void(0);)
