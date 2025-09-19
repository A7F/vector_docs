[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Callbacks/CAPLfunctionSCCPowerDeliveryReq.md)

[CAPL Functions](../../CAPLfunctions.md) » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [EVSE Callback Functions](../CAPLFunctionsSmartChargingOverview.md#CallbackEVSE) » SCC_PowerDeliveryReq

# SCC_PowerDeliveryReq

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE •  CANoe4SW DE

**Note**

- `<InvalidValueSigned>` and/or `<InvalidValueUnsigned>` can be defined in the XML configuration.
- These are returned if an optional numeric message parameter was queried by this function but not found.
- See [Configuration of Vehicle SCC Nodes](../../../CANoeCANalyzer/SmartCharging/SCProcedures/SCCConfigurationVehicleSCCNodes.md) or [Configuration of Chargepoint SCC Nodes](../../../CANoeCANalyzer/SmartCharging/SCProcedures/SCConfigurationChargePointSCCNodes.md).

## Function Syntax

```plaintext
void SCC_PowerDeliveryReq ( byte SessionId[], 
long ChargeProfileCount, long ChargeState, 
long ScheduleID)
```

## Description

The callback is called as soon as a Power Delivery Request is received.

With this request, the vehicle requests the charge point to switch on the current and to send the charging profile.

Further details that are transmitted in this request can be queried with the following functions:

- [SCC_GetChargingProfileData](../Functions/CAPLfunctionSCCGetChargingProfileData.md)
- [SCC_GetBulkChargingComplete](../Functions/CAPLfunctionSCCGetBulkChargingComplete.md) (DC)
- [SCC_GetChargingComplete](../Functions/CAPLfunctionSCCGetChargingComplete.md) (DC)

## Parameters

- **SessionID**: 8-byte long SessionID of SCC connection, range: 0 – 0xFF FF FF FF FF FF FF FF.
- **ChargingProfileCount**: Number of received charging profiles.
- **ChargeState**: 1 if start of charging is requested, 0 if stop of charging is requested, 2 if ReNegotiation is requested (only ISO 15118). Corresponds to **ReadyToChargeState** in DIN 70121.
- **ScheduleID**: ID of the chosen SAScheduleTuple.

## Return Values

—

## Example

—

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
