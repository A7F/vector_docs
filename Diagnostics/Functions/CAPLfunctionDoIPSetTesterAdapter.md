[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Diagnostics/Functions/CAPLfunctionDoIPSetTesterAdapter.md)

**CAPL Functions** » **Diagnostics** » **DoIP_SetTesterAdapter**

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

© Vector Informatik GmbH  
**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)