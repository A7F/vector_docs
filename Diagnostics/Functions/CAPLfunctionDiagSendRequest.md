# diagSendRequest

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

**Note**  
This function is called asynchronously. Therefore, it may happen, that even when the function returns with no error code, not the entire request may have been sent (e.g. especially when trying to send long messages with First Frame, Flow Control Frame and several Consecutive Frames) or that the request is not sent at all (e.g. if an error on a lower communication layer occurs). To make sure that the request has been sent completely, it is necessary to wait with [testWaitForDiagRequestSent](../../Test/Functions/CAPLfunctionTestWaitForDiagRequestSent.md) in test modules. To make sure that the request could be sent as expected in network nodes, you need to check that the [on diagRequestSent](../EventProcedures/CAPLfunctionOnDiagRequestSent.md) handler is called within the expected **timeframe**. When using the CAPL Callback Interface (CCI), it is additionally necessary to indicate errors from lower communication layers to the diagnostic layer with [diag_ErrorInd](CAPLfunctionDiagErrorInd.md).

## Function Syntax

```
long diagSendRequest (diagRequest obj)
```

## Method Syntax

[Method](../../../Shared/CAPL/General/ClassesAndObjects.md) Syntax

```
diagRequest::SendRequest()
```

## Description

Sends the request object to the ECU. If no connection has been established prior to calling `diagSendRequest`, a new connection attempt is started by internally calling the equivalent of [diagConnectChannel](CAPLfunctionDiagConnectChannel.md). Once the connection is established, the request is sent. The request will not be sent if (before the request could be sent) the channel has been closed, or if an error was reported.

Note: If [diagConnectChannel](CAPLfunctionDiagConnectChannel.md) was called before, use [testWaitForDiagChannelConnected](../../Test/Functions/CAPLfunctionTestWaitForDiagChannelConnected.md) to await the establishment of the channel before calling `diagSendRequest`.

## Parameters

- **obj**: Diagnostics object

## Return Values

[Error code](../CAPLfunctionsDiagnosticsErrorCode.md)

## Example

See [diagGenerateKeyFromSeed](CAPLfunctionDiagGenerateKeyFromSeed.md)
