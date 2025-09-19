# DoIP_SetTesterAdapter

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

**Note**  
The following DoIP CAPL function is only available with the modeling library **DoIP.dll** and eventually an appropriate implementation of the CAPL Callback Interface. Information about the DoIP DLL and the CAPL Callback Interface you find here:

- [DoIP CAPL Introduction](../CAPLDiagnosticDoIP.md)
- [AN-IND-1-012_CAPL_Callback_Interface.pdf](javascript:startDemoLoader('AN-IND-1-012_CAPL_Callback_Interface.pdf'))
- [AN-IND-1-026_DoIP_in_CANoe.pdf](javascript:startDemoLoader('AN-IND-1-026_DoIP_in_CANoe.pdf'))

## Function Syntax

```cpp
void DoIP_SetTesterAdapter(char adapter[]);
```

## Description

Sets the network interface to be used by the DoIP layer. This function must be called in [on preStart](../../Other/EventProcedures/CAPLfunctionsEventproceduresMeasurementSystem.md).

## Parameters

- **adapter**: The name of the network adapter.

## Return Values

—

## Example

```cpp
// Set the network adapter
char buffer[256];
DiagGetCommParameter("DoIP.TESTER_Adapter", 0, buffer, elcount(buffer));
DoIP_SetTesterAdapter(buffer);
```

[DiagGetCommParameter](CAPLfunctionDiagGetCommParameter.md) • [DoIP_SetLocalIPaddress](CAPLfunctionDoIPSetLocalIPaddress.md)
