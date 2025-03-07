[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Diagnostics/Functions/CAPLfunctionDoIPGetSetVehicleDiscoveryTimeout.md)

[CAPL Functions](../../CAPLfunctions.md) » [Diagnostics](../CAPLfunctionsDiagnosticsOverview.md) » DoIP_GetVehicleDiscoveryTimeout, DoIP_SetVehicleDiscoveryTimeout

# DoIP_GetVehicleDiscoveryTimeout, DoIP_SetVehicleDiscoveryTimeout

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

**Note**

The following DoIP CAPL function is only available with the modeling library **DoIP.dll** and eventually an appropriate implementation of the CAPL Callback Interface. Information about the DoIP DLL and the CAPL Callback Interface you find here:

- [DoIP CAPL Introduction](../CAPLDiagnosticDoIP.md)
- [AN-IND-1-012_CAPL_Callback_Interface.pdf](javascript:startDemoLoader('AN-IND-1-012_CAPL_Callback_Interface.pdf'))
- [AN-IND-1-026_DoIP_in_CANoe.pdf](javascript:startDemoLoader('AN-IND-1-026_DoIP_in_CANoe.pdf'))

## Function Syntax

```plaintext
void DoIP_SetVehicleDiscoveryTimeout(dword toVehicleDiscovery); // form 1
dword DoIP_GetVehicleDiscoveryTimeout(); // form 2
```

## Description

Sets or returns the timeout waiting for Vehicle Identification Response Messages after a Vehicle Identification Request was sent (in milliseconds).

## Parameters

- **toVehicleDiscovery**: Time in milliseconds [ms]

## Return Values

- **Form 1**: —
- **Form 2**: Timeout waiting for Vehicle Identification Response Messages

## Example

This value can also be configured in the DoIP.INI file.

```plaintext
// Wait longer than the standard suggests to detect more vehicles
DoIP_SetVehicleDiscoveryTimeout( 10000);
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)