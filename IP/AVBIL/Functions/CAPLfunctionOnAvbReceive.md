[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/AVBIL/Functions/CAPLfunctionOnAvbReceive.md)

**CAPL Functions** » [Ethernet](../../CAPLEthernetStartPage.md) » [AVB IL](../CAPLfunctionsAVBILOverview.md) » OnAvbReceive

# OnAvbReceive

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `void OnAvbReceive(dword listenerHandle, dword result, int buffer[], dword length); // form 1`
- `void OnAvbReceive(dword listenerHandle, dword result, long buffer[], dword length); // form 2`
- `void OnAvbReceive(dword listenerHandle, dword result, byte buffer[], dword length); // form 3`

## Description

This callback is dispatched when an asynchronous receive operation on a Listener completes.

## Parameters

- **listenerHandle**: The Listener handle.
- **result**: The specific result code of the operation. If the operation completed successfully the value is zero. Otherwise the value is non-zero.
- **buffer**: The buffer into which the data was stored.
- **size**: The length of the received data.

## Return Values

—

## Example

—

[See Also](javascript:void(0);)
