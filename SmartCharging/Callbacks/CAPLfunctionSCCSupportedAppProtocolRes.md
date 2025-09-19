[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Callbacks/CAPLfunctionSCCSupportedAppProtocolRes.md)

**CAPL Functions** » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [EV Callback Functions](../CAPLFunctionsSmartChargingOverview.md#CallbackEV) » **SCC_SupportedAppProtocolRes**

# SCC_SupportedAppProtocolRes

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE  •  CANoe4SW DE

**Note**

- `<InvalidValueSigned>` and/or `<InvalidValueUnsigned>` can be defined in the XML configuration.
- These are returned if an optional numeric message parameter was queried by this function but not found.
- See [Configuration of Vehicle SCC Nodes](../../../CANoeCANalyzer/SmartCharging/SCProcedures/SCCConfigurationVehicleSCCNodes.md) or [Configuration of Chargepoint SCC Nodes](../../../CANoeCANalyzer/SmartCharging/SCProcedures/SCConfigurationChargePointSCCNodes.md).

## Function Syntax

```c
void SCC_SupportedAppProtocolRes(long ResponseCode, dword SchemaID)
```

## Description

The callback is called as soon as a Supported App Protocol Response is received. Further details that are transmitted in this request can be queried with the following function:

- [SCC_GetResponseCodeString](../Functions/CAPLfunctionSCCGetResponseCodeString.md)

## Parameters

- **ResponseCode**: 1 if **OK**, 0 if **FAILED**.
- **SchemaID**: The ID of the schema that was selected by the charge point.

## Return Values

—

## Example

—

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
