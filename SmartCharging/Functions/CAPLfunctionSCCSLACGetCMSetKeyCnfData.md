[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCSLACGetCMSetKeyCnfData.md)

**CAPL Functions** » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [SLAC Data Queries](../CAPLFunctionsSmartChargingOverview.md#SLACSim) » [Shared Functions](../CAPLFunctionsSmartChargingOverview.md#SLACSim) » **SCC_SLAC_GetCMSetKeyCnfData**

# SCC_SLAC_GetCMSetKeyCnfData

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Note
- This function can be called only within the assigned callback. The function is used to query the details of a request.
- `<InvalidValueSigned>` and/or `<InvalidValueUnsigned>` can be defined in the XML configuration.
  - These are returned if an optional numeric message parameter was queried by this function but not found.
  - See [Configuration of Vehicle SCC Nodes](../../../CANoeCANalyzer/SmartCharging/SCProcedures/SCCConfigurationVehicleSCCNodes.md) or [Configuration of Chargepoint SCC Nodes](../../../CANoeCANalyzer/SmartCharging/SCProcedures/SCConfigurationChargePointSCCNodes.md).

## Function Syntax

```plaintext
void SLAC_GetCMSetKeyCnfData ( dword& MyNonce, dword& YourNonce, dword& PID, dword& PRN, dword& PMN, dword& CCOCapability )
```

## Description

Gets the additional parameters of a **CM_Set_Key.Cnf** message, all at once, via references.

## Parameters

- **MyNonce**: Gets the random number that will be used to verify next message (usually 0) (via reference).
- **YourNonce**: Gets the last nonce received; used to verify this message (usually 0) (via reference).
- **PID**: Gets the protocol (usually 0x04) (via reference).
- **PRN**: Gets the protocol Run Number (usually 0) (via reference).
- **PMN**: Gets the protocol Message Number (usually 0) (via reference).
- **CCOCapability**: Gets the STA’s CCo capability (usually 0) (via reference).

## Return Values

—

## Example

—
