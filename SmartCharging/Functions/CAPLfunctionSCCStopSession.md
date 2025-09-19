[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCStopSession.md)

## SCC_StopSession

**CAPL Functions** » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [V2G Simulation Control](../CAPLFunctionsSmartChargingOverview.md#V2GSimControl) » [EVSE Functions](../CAPLFunctionsSmartChargingOverview.md#V2GSimControlEVSE) » SCC_StopSession

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE •  CANoe4SW DE

### Function Syntax

```plaintext
long SCC_StopSession ( dword CloseTcpConnection ) // form 1
long SCC_StopSession ( dword CloseTcpConnection, dword CloseDataLink ) // form 2
```

### Description

The function stops a connection immediately. If it is used within a message callback, a response to the message is not sent.

### Parameters

- **CloseTcpConnection**: If 1, an additional TCP close is executed
- **CloseDataLink**: If 1, an additional data link close via CM_SetKey.Req is executed. This is the default behavior for CloseTcpConnection == 1

### Return Values

- **0**: Not successful
- **1**: Successful

### Example

—

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
