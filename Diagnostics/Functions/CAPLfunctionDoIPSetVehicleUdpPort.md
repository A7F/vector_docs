[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Diagnostics/Functions/CAPLfunctionDoIPSetVehicleUdpPort.md)

# DoIP_SetVehicleUdpPort

[CAPL Functions](../../CAPLfunctions.md) » [Diagnostics](../CAPLfunctionsDiagnosticsOverview.md) » DoIP_SetVehicleUdpPort

**Valid for:** CANoe DE

**Note:** The following DoIP CAPL function is only available with the modeling library **DoIP.dll** and eventually an appropriate implementation of the CAPL Callback Interface. Information about the DoIP DLL and the CAPL Callback Interface you find here:
- [DoIP CAPL Introduction](../CAPLDiagnosticDoIP.md)
- [AN-IND-1-012_CAPL_Callback_Interface.pdf](javascript:startDemoLoader('AN-IND-1-012_CAPL_Callback_Interface.pdf'))
- [AN-IND-1-026_DoIP_in_CANoe.pdf](javascript:startDemoLoader('AN-IND-1-026_DoIP_in_CANoe.pdf'))

## Function Syntax

```plaintext
void DoIP_SetVehicleUdpPort( dword port);
```

## Description

Sets the UDP port (UDP_VEHICLE_LOCAL) to be used by the DoIP layer.

This function must be called in [on preStart](../../Other/EventProcedures/CAPLfunctionsEventproceduresMeasurementSystem.md).

## Parameters

- **port**: The UDP_VEHICLE_LOCAL port of the DoIP layer.

## Return Values

—

## Example

```plaintext
dword port;
port = DiagGetCommParameter( "DoIP.VEHICLE_UDP_Data");
// Set the vehicle UDP port
DoIP_SetVehicleUdpPort( port);
```

[DiagGetCommParameter](CAPLfunctionDiagGetCommParameter.md)

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)