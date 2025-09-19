# DoIP_SetVehicleAdapter

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

**Note**

The following DoIP CAPL function is only available with the modeling library **DoIP.dll** and eventually an appropriate implementation of the CAPL Callback Interface. Information about the DoIP DLL and the CAPL Callback Interface you find here:

- [DoIP CAPL Introduction](../CAPLDiagnosticDoIP.md)
- [AN-IND-1-012_CAPL_Callback_Interface.pdf](javascript:startDemoLoader('AN-IND-1-012_CAPL_Callback_Interface.pdf'))
- [AN-IND-1-026_DoIP_in_CANoe.pdf](javascript:startDemoLoader('AN-IND-1-026_DoIP_in_CANoe.pdf'))

## Function Syntax

```plaintext
void DoIP_SetVehicleAdapter( char adapter[])
```

## Description

Sets the network interface to be used by the DoIP layer.

This function must be called in [on preStart](../../Other/EventProcedures/CAPLfunctionsEventproceduresMeasurementSystem.md).

## Parameters

- **adapter**: The name of the network adapter.

## Return Values

—

## Example

```plaintext
// Set the network interface
char buffer[256];
DiagGetCommParameter( "DoIP.VEHICLE_Adapter", 0, buffer, elcount( buffer));
DoIP_SetVehicleAdapter( buffer);
```

[DiagGetCommParameter](CAPLfunctionDiagGetCommParameter.md) • [DoIP_SetLocalIPaddress](CAPLfunctionDoIPSetLocalIPaddress.md)
