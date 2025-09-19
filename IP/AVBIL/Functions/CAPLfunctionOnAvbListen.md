[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/AVBIL/Functions/CAPLfunctionOnAvbListen.md)

**CAPL Functions** » **Ethernet** » **AVB IL** » **OnAvbListen**

# OnAvbListen

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
void OnAvbListen(dword listenerHandle, dword result);
```

## Description

This callback is dispatched when a connection request for the specified Listener is received.

## Parameters

- **listenerHandle**: The Listener handle.
- **result**: The specific result code of the operation. If the operation completed successfully the value is zero. Otherwise the value is non-zero.

## Return Values

—

## Example

—

[See Also](javascript:void(0);)

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
