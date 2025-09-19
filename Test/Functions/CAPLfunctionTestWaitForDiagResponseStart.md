[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestWaitForDiagResponseStart.md)

[CAPL Functions](../../CAPLfunctions.md) » [Diagnostics](../../Diagnostics/CAPLfunctionsDiagnosticsOverview.md) » TestWaitForDiagResponseStart

# TestWaitForDiagResponseStart

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

**Note**  
This function can only be called within a test module!

## Function Syntax

```plaintext
long TestWaitForDiagResponseStart (diagRequest request, dword timeout);
long TestWaitForDiagResponseStart (dword timeout);
```

## Description

Waits for the arrival of the response to a sent request, e.g. the so-called "First Frame" in ISO TP transmissions. One way this function might be triggered is by `Diag_FirstFrameInd()` at the CAPL Callback Interface, but only if this has been implemented suitably. When other protocols or interfaces are used this call might be omitted. Then the function rolls back after the response has been fully received.

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
// waits for the start of the response reception
if (TestWaitForDiagResponseStart(req, 2000) == 1)
    TestStepPass("Starting response reception!!");
else
    TestStepFail("No response!");
TestWaitForDiagResponse(req, 2000);
```

[Test Feature Set CAPL Functions](../CAPLfunctionsTFSOverview.md)

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
