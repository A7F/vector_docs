# diagSetTimeoutHandler

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

## Function Syntax

```plaintext
long diagSetTimeoutHandler (diagRequest obj, char callbackName[])
long diagSetTimeoutHandler (char callbackName[])
```

## Method Syntax

[Method](../../../Shared/CAPL/General/ClassesAndObjects.md) Syntax

```plaintext
diagRequest::SetTimeoutHandler (char callbackName[])
```

## Description

Sets the timeout callback for a request, or default timeout callback function. This function will be called if no response arrives at the tester within the timeout specified with [diagSetTimeout](CAPLfunctionDiagSetTimeout.md).

## Parameters

- **obj**: Diagnostics object
- **callbackName**: Callback name

## Return Values

[Error code](../CAPLfunctionsDiagnosticsErrorCode.md)

## Example

```plaintext
on start
{
  diagSetTimeout (200); // Set timeout to 200 ms
  diagSetTimeoutHandler("Request_Timeout");
}

on key '1'
{
  DiagRequest SimECU.ReadDataByIdentifier_Process req;
  diagSendRequest(req);
}

void Request_Timeout()
{
  write("No response received within expected time frame!");
}
```
