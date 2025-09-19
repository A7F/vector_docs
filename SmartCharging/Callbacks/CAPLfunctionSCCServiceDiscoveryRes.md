[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Callbacks/CAPLfunctionSCCServiceDiscoveryRes.md)

[CAPL Functions](../../CAPLfunctions.md) » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [EV Callback Functions](../CAPLFunctionsSmartChargingOverview.md#CallbackEV) » SCC_ServiceDiscoveryRes

# SCC_ServiceDiscoveryRes

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE •  CANoe4SW DE

**Note**  
The element **ChargeService**, which is not part of the service list, is contained in the ServiceCount and referenced using index 0.

## Function Syntax

```plaintext
void SCC_ServiceDiscoveryRes ( byte SessionID[], long ResponseCode, long ServiceCount )
```

## Description

The callback is called as soon as a Service Discovery Response is received.

Further details that are transmitted in this request can be queried with the following functions:

- [SCC_GetServiceData](../Functions/CAPLfunctionSCCGetServiceData.md)
- [SCC_GetPaymentOptions](../Functions/CAPLfunctionSCCGetPaymentOptions.md)
- [SCC_GetEnergyTransferType](../Functions/CAPLfunctionSCCGetEnergyTransferType.md) (DIN 70121)
- [SCC_GetEnergyTransferMode Count](../Functions/CAPLfunctionSCCGetEnergyTransferModeCount.md) (ISO 15118)
- [SCC_GetEnergyTransferMode](../Functions/CAPLfunctionSCCGetEnergyTransferMode.md) (ISO 15118)
- [SCC_GetResponseCodeString](../Functions/CAPLfunctionSCCGetResponseCodeString.md)

## Parameters

- **SessionID**: 8-byte long SessionID of SCC connection, range: 0 – 0xFF FF FF FF FF FF FF FF.
- **ResponseCode**: 1 if **OK**, 0 if **FAILED**.
- **ServiceCount**: Number of ServiceTags or Services transmitted.

## Return Values

—

## Example

—

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
