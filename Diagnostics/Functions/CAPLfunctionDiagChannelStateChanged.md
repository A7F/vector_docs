[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Diagnostics/Functions/CAPLfunctionDiagChannelStateChanged.md)

**CAPL Functions** » **Diagnostics** » _Diag_ChannelStateChanged

# _Diag_ChannelStateChanged

**Valid for**: CANoe DE

## Function Syntax

- `void _Diag_ChannelStateChanged(long newState); // form 1`
- `void _Diag_ChannelStateChanged(char target[], long newState); // form 2`

## Description

Callback function in a tester that is called every time the state of the diagnostic channel changes.

- Note: Form 1 requires a diagnostic target to be set, by calling [diagSetTarget](CAPLfunctionDiagSetTarget.md).
- Note: Only one of the two forms may be implemented at a time and the function name is case-sensitive.
- Note: In combination with the [CAPL Callback Interface (CCI)](../CAPLfunctionsDiagnosticsConnectionCommunicationLayer.md), only the states Closed and Connected are supported.

## Parameters

- **target**: Qualifier of the ECU whose communication channel’s state has changed.
- **newState**: New state of the channel.

  - `0`: Closed  
    Channel is not yet opened or already closed.
  - `1`: Opened  
    Channel is opened but no request has successfully been sent yet or the attempt to send a request failed.
  - `2`: Connected  
    Request was successfully sent but no response has been received yet or the expected response was missed.
  - `3`: Online  
    Request and response have successfully been sent and received.
  - `4`: ClosePending  
    Closing of the communication was requested but is still pending. State **Closed** will follow.
  - `5`: ConnectPending  
    Start of the communication was requested but is still pending, in case of success state **Connected** will follow, otherwise state **Opened**.

## Return Values

—

## Example

```c
_Diag_ChannelStateChanged(char target[], long newState)
{
  write("Channel state changed for target %s changed to %d”, target, newState);
  gCurrentChannelState = newState;
}
```

[diagCloseChannel](CAPLfunctionDiagCloseChannel.md) • [diagConnectChannel](CAPLfunctionDiagConnectChannel.md) • [diagDisconnectChannel](CAPLfunctionDiagDisconnectChannel.md) • [diagIsChannelConnected](CAPLfunctionDiagIsChannelConnected.md)

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)