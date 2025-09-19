[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Callbacks/CAPLfunctionSCCServiceDetailReq.md)

**CAPL Functions** » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [EVSE Callback Functions](../CAPLFunctionsSmartChargingOverview.md#CallbackEVSE) » **SCC_ServiceDetailReq**

# SCC_ServiceDetailReq

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
void SCC_ServiceDetailReq ( byte SessionID[], dword ServiceId )
```

## Description

The callback is called as soon as a Service Detail Request is received.

## Parameters

- **SessionID**: 8-byte long SessionID of SCC connection, range: 0 – 0xFF FF FF FF FF FF FF FF.
- **ServiceId**: ID of the requested service (16 bit unsigned number).

## Return Values

—

## Example

—

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
