[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/AVBIL/Functions/CAPLfunctionOnAvbSend.md)

**CAPL Functions** » **Ethernet** » **AVB IL** » **OnAvbSend**

# OnAvbSend

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `void OnAvbSend(dword talkerHandle, dword result, int buffer[], dword length); // form 1`
- `void OnAvbSend(dword talkerHandle, dword result, long buffer[], dword length); // form 2`
- `void OnAvbSend(dword talkerHandle, dword result, qword buffer[], dword length); // form 3`
- `void OnAvbSend(dword talkerHandle, dword result, byte buffer[], dword length); // form 4`

## Description

This callback is dispatched when an asynchronous send operation on a Talker completes.

## Parameters

- **talkerHandle**: The Talker handle.
- **result**: The specific result code of the operation. If the operation completed successfully the value is zero. Otherwise the value is non-zero.
- **buffer**: The buffer provided with the send operation.
- **size**: The number of elements sent.

## Return Values

—

## Example

—

[See Also](javascript:void(0);)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)