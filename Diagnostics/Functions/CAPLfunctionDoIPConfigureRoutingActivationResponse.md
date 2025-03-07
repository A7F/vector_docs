[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Diagnostics/Functions/CAPLfunctionDoIPConfigureRoutingActivationResponse.md)

**CAPL Functions** » [Diagnostics](../CAPLfunctionsDiagnosticsOverview.md) » DoIP_ConfigureRoutingActivationResponse

# DoIP_ConfigureRoutingActivationResponse

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

**Note**  
The following DoIP CAPL function is only available with the modeling library **DoIP.dll** and eventually an appropriate implementation of the CAPL Callback Interface. Information about the DoIP DLL and the CAPL Callback Interface you find here:

- [DoIP CAPL Introduction](../CAPLDiagnosticDoIP.md)
- [AN-IND-1-012_CAPL_Callback_Interface.pdf](javascript:startDemoLoader('AN-IND-1-012_CAPL_Callback_Interface.pdf'))
- [AN-IND-1-026_DoIP_in_CANoe.pdf](javascript:startDemoLoader('AN-IND-1-026_DoIP_in_CANoe.pdf'))

## Function Syntax

```c
void DoIP_ConfigureRoutingActivationResponse(dword valueReserved);
```

## Description

Configures the routing activation response message sent by the vehicle simulation on the reception of a routing activation request message.

## Parameters

- **valueReserved**: The value of the reserved field in the message. ISO 13400 specifies a default value of 0x00000000.

## Return Values

—

## Example

```c
// Set the reserved field in the routing activation response message to 0x12345678
DoIP_ConfigureRoutingActivationResponse(0x12345678);
```

[DoIP_SetRoutingActivationOEMSpecific](CAPLfunctionDoIPSetRoutingActivationOEMSpecific.md) • [_DoIP_RoutingActivationRequest](CAPLfunctionDoIPRoutingActivationRequest.md)

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)