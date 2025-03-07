[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestWaitForDiagResponse.md)

[CAPL Functions](../../CAPLfunctions.md) » [Diagnostics](../../Diagnostics/CAPLfunctionsDiagnosticsOverview.md) » TestWaitForDiagResponse

# TestWaitForDiagResponse

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

**Note**  
This function can only be called within a test module!

## Function Syntax

```plaintext
long TestWaitForDiagResponse (diagRequest request, dword timeout); // form 1
long TestWaitForDiagResponse (dword timeout); // form 2
```

## Description

Waits for the arrival of the response to the given request.

**Note**  
Please note that in case no response is received, it depends on the transport layer settings (e.g. P2 timing) whether the function returns with a timeout or an internal error.  
Before calling the function `TestWaitForDiagResponse`, make sure the request has already completely been sent using the function `TestWaitForDiagRequestSent()`.  
If the request was created using raw data (e.g. by using the CAPL functions [DiagSetPrimitiveData](../../Diagnostics/Functions/CAPLfunctionDiagGetPrimitiveData.md) or [DiagSetParameterRaw](../../Diagnostics/Functions/CAPLfunctionDiagSetParameterRaw.md)), the built-in diagnostic channel cannot determine whether the **Suppress Positive Response Message Indication Bit** (SPRMIB) is set or not. In this case, **TestWaitForDiagResponse** will expect a response even if the SPRMIB in the given request was set to **1**. To avoid this behavior, it is necessary to use the CAPL function [diagSetSuppressResp](../../Diagnostics/Functions/CAPLfunctionDiagGetSuppressRespDiagSetSuppressResp.md) in order to set the SPRMIB explicitly in the request.

The function will return immediately after a positive or negative response - other than "responsePending" - was received within the configured protocol (P2/P2*) timings.

Intermediate "responsePending" NRCs from the target ECU will automatically prolong the wait timer of the tester in P2* increments until maximally <timeout> [ms]. If by then no response has been received from the ECU target, the function will return with value =0 (timeout reached).

In case the tester node implements a "[CAPL callback interface for diagnostics](../../Diagnostics/CAPLfunctionsDiagnosticsConnectionCommunicationLayer.md#CAPLCallbackInterface)" (CCI), but has no further provisions to handle NRCs on its own right, the behavior is equivalent to the one described above (automated "responsePending" handling).

If the tester implements a CCI and handles "responsePending" messages by itself - calling [DiagSetP2Extended(-1)](../../Diagnostics/Functions/CAPLfunctionDiagGetP2ExtendedDiagSetP2Extended.md) beforehand on the CCI - then this function will also treat "responsePending" as a regular negative response code and will return immediately after having received such a negative response.

**Note**  
Using the syntax with **diagRequest** object (form 1), the check on **P2** or **P2 extended** does not take into account, whether the response fits to the request or not.  
If a response (whether fitting or not) was received within **P2** or **P2 extended**, the TP timings are treated as correct by the function and the further evaluation is executed on diagnostic layer.  
If **P2** or **P2 extended** is violated, the function returns with a negative return value, i.e. the timeout parameter value gets irrelevant and it doesn't matter if a fitting response was received during the timeout or not.  
The diagnostic layer gets only responses for fitting requests, i.e.:
- in case of the syntax without **diagRequest** object (form 2) all responses
- in case of the syntax with **diagRequest** object (form 1) only responses that fit to the request

Therefore, the function waits until the timeout, which was passed as a parameter, when it receives an unfitting response.

## Parameters

- **request**: Sent request
- **timeout [ms]**: Maximum time that should be waited [ms]. Transmission of 0: no timeout controlling.

## Return Values

- **< 0**: An internal error occurred, e.g. a protocol error or a faulty configuration of the diagnostic layer.
- **0**: The timeout was reached, i.e. the event of interest did not occur within the specified time.
- **1**: The event occurred.

## Example

[Using Diagnostics Functions in Test Cases](../../Diagnostics/CAPLfunctionsDiagnosticsUsingFunctionTestCase.md)

[Test Feature Set CAPL Functions](../CAPLfunctionsTFSOverview.md) • [TestJoinDiagResponseFromEcu](CAPLfunctionTestJoinDiagResponseFromEcu.md)

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)