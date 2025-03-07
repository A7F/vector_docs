[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Media/Functions/CAPLfunctionMediaCreateMediaType.md)

**CAPL Functions** » **Media API** » **MediaCreateMediaType**

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

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)