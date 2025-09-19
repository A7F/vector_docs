[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestWaitForDiagRequestSent.md)

[CAPL Functions](../../CAPLfunctions.md) » [Diagnostics](../../Diagnostics/CAPLfunctionsDiagnosticsOverview.md) » TestWaitForDiagRequestSent

# TestWaitForDiagRequestSent

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

**Note**  
This function can only be called within a test module!

## Function Syntax

```
long TestWaitForDiagRequestSent (diagRequest request, dword timeout);
```

## Description

Waits until the previously sent request has been sent to the ECU.  
This might be triggered by a call of the function [Diag_DataCon()](../../Diagnostics/Functions/CAPLfunctionDiagDataCon.md) at the CAPL Callback Interface.

## Parameters

- **request**: Sent request
- **timeout [ms]**: Maximum time that should be waited [ms]. Transmission of 0: no timeout controlling.

## Return Values

- **< 0**: An internal error occurred, e.g. a faulty configuration of the Diagnostic Layer.
- **0**: The timeout was reached, i.e. the event of interest did not occur within the specified time.
- **1**: The event occurred.

## Example

```plaintext
DiagRequest SerialNumber_Read req;
long result;

DiagSetTarget("Door");
req.SendRequest();
// waits until request is completely sent
if (TestWaitForDiagRequestSent(req, 2000) == 1)
  TestStepPass("Request was sent successfully!");
else
  TestStepFail("Request could not be sent!");
TestWaitForDiagResponse(req, 2000);
```

[Test Feature Set CAPL Functions](../CAPLfunctionsTFSOverview.md)

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
