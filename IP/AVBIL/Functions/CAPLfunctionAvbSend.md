[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/AVBIL/Functions/CAPLfunctionAvbSend.md)

**CAPL Functions** » **Ethernet** » **AVB IL** » **AvbSend**

# AvbSend

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `dword AvbSend(dword talkerHandle, int buffer[], dword& length, char onSendCallback[]); // form 1`
- `dword AvbSend(dword talkerHandle, long buffer[], dword& length, char onSendCallback[]); // form 2`
- `dword AvbSend(dword talkerHandle, qword buffer[], dword& length, char onSendCallback[]); // form 3`
- `dword AvbSend(dword talkerHandle, byte buffer[], dword& length, char onSendCallback[]); // form 4`

## Description

The function sends the data passed in the buffer. If the send operation completes immediately the function returns the number of sent elements in the length parameter and the passed CAPL callback [OnAvbSend](CAPLfunctionOnAvbSend.md) will not be called.

If the send operation does not complete immediately the operation is performed asynchronously and the function will return 460609.

In this case the CAPL callback [OnAvbSend](CAPLfunctionOnAvbSend.md) will be called on completion (successful or not).

No data should be written to the buffer until the send operation is complete to avoid corruption of the sent data.

## Parameters

- **talkerHandle**: The Talker handle.
- **buffer**: The buffer containing the data to be sent.
- **length**: The length of the data buffer.
- **onSendCallback**: The name of the CAPL callback function (see [OnAvbSend](CAPLfunctionOnAvbSend.md)).

## Return Values

- **0**: The function completed successfully.
- **460609**: The operation is pending and will be completed later.
- **Any other value**: Other [Error code](../CAPLfunctionsAVBILErrorCode.md)

## Example

—

[See Also](javascript:void(0);)
