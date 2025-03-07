[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Diagnostics/Functions/CAPLfunctionDiagSendResponse.md)

[CAPL Functions](../../CAPLfunctions.md) » [Diagnostics](../CAPLfunctionsDiagnosticsOverview.md) » diagSendResponse, diagSendPositiveResponse

# diagSendResponse, diagSendPositiveResponse

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

**Note**  
This function is called asynchronously. Therefore, it may happen, that even when the function returns with no error code, not the entire response may have been sent (e.g. especially when trying to send long messages with First Frame, Flow Control Frame and several Consecutive Frames) or that the response is not sent at all (e.g. if an error on a lower communication layer occurs).

## Function Syntax

```plaintext
long diagSendResponse (diagResponse obj)
long diagSendPositiveResponse (diagResponse obj)
```

## Method Syntax

[Method](../../../Shared/CAPL/General/ClassesAndObjects.md) Syntax

```plaintext
diagResponse::SendResponse ()
diagResponse::SendPositiveResponse()
```

## Description

Sends the response object back to the tester. Can only be called in the ECU simulation.

## Parameters

- **obj**: Diagnostics object

## Return Values

[Error code](../CAPLfunctionsDiagnosticsErrorCode.md)

## Example

See [on diagRequest](../EventProcedures/CAPLfunctionOnDiagRequest.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)