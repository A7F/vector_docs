[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Callbacks/CAPLfunctionSCCServiceDetailRes.md)

## SCC_ServiceDetailRes

[CAPL Functions](../../CAPLfunctions.md) » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [EV Callback Functions](../CAPLFunctionsSmartChargingOverview.md#CallbackEV) » SCC_ServiceDetailRes

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE  •  CANoe4SW DE

### Function Syntax

```plaintext
void SCC_ServiceDetailRes ( byte SessionID[], 
long ResponseCode, dword ServiceID, 
long ParameterSetCount )
```

### Description

The callback is called as soon as a Service Detail Response is received.

Further details that are transmitted in this request can be queried with the following functions:

- [SCC_GetServiceParameterSetData](../Functions/CAPLfunctionSCCGetServiceParameterSetData.md)
- [SCC_GetServiceParameterData](../Functions/CAPLfunctionSCCGetServiceParameterData.md)
- [SCC_GetServiceParameterNumericalValue](../Functions/CAPLfunctionSCCGetServiceParameterNumericalValue.md)
- [SCC_GetServiceParameterPhysicalValue](../Functions/CAPLfunctionSCCGetServiceParameterPhysicalValue.md)
- [SCC_GetServiceParameterStringValue](../Functions/CAPLfunctionSCCGetServiceParameterStringValue.md)
- [SCC_GetResponseCodeString](../Functions/CAPLfunctionSCCGetResponseCodeString.md)

### Parameters

- **SessionID**: 8-byte long SessionID of SCC connection, range: 0 – 0xFF FF FF FF FF FF FF FF.
- **ResponseCode**: 1 if **OK**, 0 if **FAILED**.
- **ServiceId**: ID of the requested service (16 bit unsigned number).
- **ParameterSetCount**: Number of transmitted parameter sets.

### Return Values

—

### Example

—

© Vector Informatik GmbH

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)