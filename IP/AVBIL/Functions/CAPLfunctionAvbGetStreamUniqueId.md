[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/AVBIL/Functions/CAPLfunctionAvbGetStreamUniqueId.md)

**CAPL Functions** » **Ethernet** » **AVB IL** » AvbGetStreamUniqueId

# AvbGetStreamUniqueId

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
dword AvbGetStreamUniqueId(dword listenerOrTalkerHandle, dword& retStreamUniqueId);
```

## Description

The function retrieves the stream’s Unique Identifier (ID) of the Listener or Talker as part of the Stream Identifier (ID).

## Parameters

- **listenerOrTalkerHandle**: The handle of the Listener or Talker.
- **retStreamUniqueId**: The 16 bitstream Unique Identifier (ID) upon successful return of the function.

## Return Values

- **0**: The function completed successfully.
- **>0**: [Error code](../CAPLfunctionsAVBILErrorCode.md)

## Example

—

[See Also](javascript:void(0);)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
