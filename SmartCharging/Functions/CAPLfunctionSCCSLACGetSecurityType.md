[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCSLACGetSecurityType.md)

## SCC_SLAC_GetSecurityType

[CAPL Functions](../../CAPLfunctions.md) » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [SLAC Data Queries](../CAPLFunctionsSmartChargingOverview.md#SLACSim) » [Shared Functions](../CAPLFunctionsSmartChargingOverview.md#SLACSim) » SCC_SLAC_GetSecurityType

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

### Note

- This function can be called only within the assigned callback. The function is used to query the details of a request.
- `<InvalidValueSigned>` and/or `<InvalidValueUnsigned>` can be defined in the XML configuration.
  - These are returned if an optional numeric message parameter was queried by this function but not found.
  - See [Configuration of Vehicle SCC Nodes](../../../CANoeCANalyzer/SmartCharging/SCProcedures/SCCConfigurationVehicleSCCNodes.md) or [Configuration of Chargepoint SCC Nodes](../../../CANoeCANalyzer/SmartCharging/SCProcedures/SCConfigurationChargePointSCCNodes.md).

## Function Syntax

```plaintext
long SCC_SLAC_GetSecurityType ( )
```

## Description

Queries the security type.

## Parameters

—

## Return Values

- **0x00**: No Security (mandatory)
- **0x01**: Public Key Signature
- **0x02-0xFF**: Reserved

## Example

—

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
