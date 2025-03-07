[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/AVBIL/Functions/CAPLfunctionAvbReceive.md)

**CAPL Functions** » **Ethernet** » **AVB IL** » **AvbReceive**

# AvbReceive

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `dword AvbReceive(dword listenerHandle, int buffer[], dword& length, char onReceiveCallback[]); // form 1`
- `dword AvbReceive(dword listenerHandle, long buffer[], dword& length, char onReceiveCallback[]); // form 2`
- `dword AvbReceive(dword listenerHandle, byte buffer[], dword& length, char onReceiveCallback[]); // form 3`

## Description

The function receives data into the specified buffer.

If the receive operation completes immediately the function returns the number of received elements in the length parameter and the passed CAPL callback [OnAvbReceive](CAPLfunctionOnAvbReceive.md) will not be called.

If the receive operation does not complete immediately the operation is performed asynchronously and the function will return 460609.

In this case the CAPL callback [OnAvbReceive](CAPLfunctionOnAvbReceive.md) will be called on completion (successful or not).

## Parameters

- **listenerHandle**: The Listener handle.
- **buffer**: The buffer used to store the incoming data.
- **length**: The length of the data buffer.
- **onReceiveCallback**: The name of the CAPL callback function (see OnAvbReceive).

## Return Values

- **0**: The function completed successfully.
- **460609**: The operation is pending and will be completed later.
- **Any other value**: Other [Error code](../CAPLfunctionsAVBILErrorCode.md)

## Example

—

[See Also](javascript:void(0);)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)