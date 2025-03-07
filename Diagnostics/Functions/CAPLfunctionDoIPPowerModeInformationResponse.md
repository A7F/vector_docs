[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Diagnostics/Functions/CAPLfunctionDoIPPowerModeInformationResponse.md)

[CAPL Functions](../../CAPLfunctions.md) » [Diagnostics](../CAPLfunctionsDiagnosticsOverview.md) » _DoIP_PowerModeInformationResponse

# _DoIP_PowerModeInformationResponse

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

**Note**  
The following DoIP CAPL function is only available with the modeling library **DoIP.dll** and eventually an appropriate implementation of the CAPL Callback Interface. Information about the DoIP DLL and the CAPL Callback Interface you find here:

- [DoIP CAPL Introduction](../CAPLDiagnosticDoIP.md)
- [AN-IND-1-012_CAPL_Callback_Interface.pdf](javascript:startDemoLoader('AN-IND-1-012_CAPL_Callback_Interface.pdf'))
- [AN-IND-1-026_DoIP_in_CANoe.pdf](javascript:startDemoLoader('AN-IND-1-026_DoIP_in_CANoe.pdf'))

## Function Syntax

```plaintext
void _DoIP_PowerModeInformationResponse(char IPaddress[], BYTE value);
```

## Description

The tester received a response for a Power Mode Information Request. The vehicle's IP address is given as first argument, in text form.

## Parameters

- **IPaddress**: Address in text form, e.g. "169.254.32.1" (IPv4) or "2001::1" (IPv6).
- **value**: Power mode information returned by the vehicle.

## Return Values

—

## Example

See [DoIP_SendPowerModeInformationRequest](CAPLfunctionDoIPSendPowerModeInformationRequest.md)

[DoIP_SendPowerModeInformationRequest](CAPLfunctionDoIPSendPowerModeInformationRequest.md) • [DoIP_SetPowerModeInformation](CAPLfunctionDoIPSetPowerModeInformation.md)

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)