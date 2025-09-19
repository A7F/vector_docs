# DoIP_SetTesterUdpPort

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

**Note**

The following DoIP CAPL function is only available with the modeling library **DoIP.dll** and eventually an appropriate implementation of the CAPL Callback Interface. Information about the DoIP DLL and the CAPL Callback Interface you find here:

- [DoIP CAPL Introduction](../CAPLDiagnosticDoIP.md)
- [AN-IND-1-012_CAPL_Callback_Interface.pdf](javascript:startDemoLoader('AN-IND-1-012_CAPL_Callback_Interface.pdf'))
- [AN-IND-1-026_DoIP_in_CANoe.pdf](javascript:startDemoLoader('AN-IND-1-026_DoIP_in_CANoe.pdf'))

## Function Syntax

```plaintext
void DoIP_SetTesterUdpPort( dword port);
```

## Description

Sets the UDP port (UDP_TEST_EQUIPMENT_LISTEN) to be used by the DoIP layer.

This function must be called in [on preStart](../../Other/EventProcedures/CAPLfunctionsEventproceduresMeasurementSystem.md).

## Parameters

- **port**: The UDP_TEST_EQUIPMENT_LISTEN port of the test equipment.

## Return Values

—

## Example

```plaintext
dword port;
port = DiagGetCommParameter( "DoIP.TESTER_UDP_Data");
// Set the tester UDP port
DoIPSetTesterUdpPort( port);
```

[DiagGetCommParameter](CAPLfunctionDiagGetCommParameter.md)
