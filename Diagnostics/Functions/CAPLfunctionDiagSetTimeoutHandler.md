[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Diagnostics/Functions/CAPLfunctionDiagSetTimeoutHandler.md)

[CAPL Functions](../../CAPLfunctions.md) » [Diagnostics](../CAPLfunctionsDiagnosticsOverview.md) » diagSetTimeoutHandler

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

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)