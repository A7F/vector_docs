# DoIP_SetPowerModeInformation

[Feature availability for your product](../../../Shared/FeatureAvailability.md):  CANoe DE

**Note**

The following DoIP CAPL function is only available with the modeling library **DoIP.dll** and eventually an appropriate implementation of the CAPL Callback Interface. Information about the DoIP DLL and the CAPL Callback Interface you find here:

- [DoIP CAPL Introduction](../CAPLDiagnosticDoIP.md)
- [AN-IND-1-012_CAPL_Callback_Interface.pdf](javascript:startDemoLoader('AN-IND-1-012_CAPL_Callback_Interface.pdf'))
- [AN-IND-1-026_DoIP_in_CANoe.pdf](javascript:startDemoLoader('AN-IND-1-026_DoIP_in_CANoe.pdf'))

## Function Syntax

```plaintext
void DoIP_SetPowerModeInformation(long powerMode);
```

## Description

Sets the value returned automatically for a Power Mode Information Request.

## Parameters

- **powerMode**  
  -1: do not send a response for the request  
  0: not ready  
  1: ready  
  2: not supported (default)  
  Others: reserved

## Return Values

—

## Example

```plaintext
// The ECU simulation will return "ready" if the power mode is requested
DoIP_SetPowerModeInformation(1);
```

[DoIP_SendPowerModeInformationRequest](CAPLfunctionDoIPSendPowerModeInformationRequest.md)
