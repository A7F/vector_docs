[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Diagnostics/Functions/CAPLfunctionDiagErrorInd.md)

**CAPL Functions** » **Diagnostics** » **diag_ErrorInd**

# diag_ErrorInd

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

- `void diag_ErrorInd (long error);` // form 1
- `void diag_ErrorInd (char target[], long error);` // form 2

## Description

Reports errors to the diagnostic layer.

This function is typically called within a transport layer callback. The transport layer uses it to report errors to the diagnostic layer.

If, for example, [testWaitForDiagResponse](../../Test/Functions/CAPLfunctionTestWaitForDiagResponse.md) is used in a test module to wait for receipt of a response and `Diag_ErrorInd` reports an error, the test function returns an error and stops waiting.

## Parameters

- **error**: Error number. This number is valid only in the context of the concrete transport protocol implementation used. It is recommended to forward error numbers reported by the protocol layer. For example, the OSEKTL API for the ISO TP on CAN implementation found in OSEK_TP.DLL reports errors in the callback function `OSEKTL_ErrorInd`. The error number reported here can simply be forwarded to the diagnostic layer:

  ```c
  OSEKTL_ErrorInd(int error) {
      diag_ErrorInd(error);
  }
  ```

- **target**: Qualifier of the ECU for which there was a communication error.

## Return Values

[Error code](../CAPLfunctionsDiagnosticsErrorCode.md)

## Example

See [DoIP_ErrorInd](CAPLfunctionDoIPErrorInd.md)

[Communication Layer Connection / Reference Implementations](../CAPLfunctionsDiagnosticsConnectionCommunicationLayer.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)