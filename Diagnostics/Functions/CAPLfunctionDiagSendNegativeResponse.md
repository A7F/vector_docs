# diagSendNegativeResponse

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

**Note**  
This function is called asynchronously. Therefore, it may happen, that even when the function returns with no error code, not the entire response may have been sent (e.g. especially when trying to send long messages with First Frame, Flow Control Frame and several Consecutive Frames) or that the response is not sent at all (e.g. if an error on a lower communication layer occurs).

## Function Syntax

```
long diagSendNegativeResponse (diagResponse obj, DWORD code)
long diagSendNegativeResponse (diagRequest obj, DWORD code)
```

## Method Syntax

[Method](../../../Shared/CAPL/General/ClassesAndObjects.md) Syntax

```
diagResponse::SendNegativeResponse (DWORD code)
diagRequest::SendNegativeResponse (DWORD code)
```

## Description

Sends a negative response to the tester, whereby the specified value is transmitted as error code.

## Parameters

- **obj**: Diagnostics object
- **code**: Error code.

## Return Values

[Error code](../CAPLfunctionsDiagnosticsErrorCode.md)

## Example

```plaintext
on diagRequest FaultMemory::FaultMemory::ReportByStatusMask
{
  // Send neg response with code 0x78 (requestCorrectlyReceived-ResponsePending)
  DiagSendNegativeResponse(this, 0x78);
  // Optionally set a timer to respond with a positive response later
  setTimer(posReq, 1);
  // pos resp after 1s
}
```
