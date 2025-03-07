[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Diagnostics/Functions/CAPLfunctionDoIPSendPowerModeInformationRequest.md)

**CAPL Functions** » [Diagnostics](../CAPLfunctionsDiagnosticsOverview.md) » DoIP_SendPowerModeInformationRequest

# DoIP_SendPowerModeInformationRequest

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

**Note**  
The following DoIP CAPL function is only available with the modeling library **DoIP.dll** and eventually an appropriate implementation of the CAPL Callback Interface. Information about the DoIP DLL and the CAPL Callback Interface you find here:

- [DoIP CAPL Introduction](../CAPLDiagnosticDoIP.md)
- [AN-IND-1-012_CAPL_Callback_Interface.pdf](javascript:startDemoLoader('AN-IND-1-012_CAPL_Callback_Interface.pdf'))
- [AN-IND-1-026_DoIP_in_CANoe.pdf](javascript:startDemoLoader('AN-IND-1-026_DoIP_in_CANoe.pdf'))

## Function Syntax

```plaintext
void DoIP_SendPowerModeInformationRequest();
void DoIP_SendPowerModeInformationRequest(char IPaddress[]);
```

## Description

Sends power mode information request as limited broadcast or to the given address.

## Parameters

- **IPaddress**: Address to send to, i.e. not a limited broadcast. May be a directed broadcast address.

## Return Values

—

## Example

```plaintext
void _DoIP_PowerModeInformationResponse( char IPaddress[], BYTE value)
{
  write( "DoIP_PowerModeInformationResponse from '%s': %d", IPaddress, value);
  testSupplyTextEvent( cTE_PowerModeRespInd);
}
// Send a power mode information request and wait for the first response
Testcase TC_PowerMode()
{
  DoIP_SendPowerModeInformationRequest();
  testWaitForTextEvent( cTE_PowerModeRespInd, 500);
}
```

[_DoIP_PowerModeInformationResponse](CAPLfunctionDoIPPowerModeInformationResponse.md)

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)