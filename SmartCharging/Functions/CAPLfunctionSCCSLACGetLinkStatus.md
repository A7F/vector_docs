[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCSLACGetLinkStatus.md)

[CAPL Functions](../../CAPLfunctions.md) » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [SLAC Simulation](../CAPLFunctionsSmartChargingOverview.md#SLACSim) » [Shared Functions](../CAPLFunctionsSmartChargingOverview.md#SLACSim) » **SCC_SLAC_GetLinkStatus**

# SCC_SLAC_GetLinkStatus

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE  •  CANoe4SW DE

**Note**

- `<InvalidValueSigned>` and / or `<InvalidValueUnsigned>` can be defined in the XML configuration.
- These are returned if an optional numeric message parameter was queried by this function but not found.
- See [Configuration of Vehicle SCC Nodes](../../../CANoeCANalyzer/SmartCharging/SCProcedures/SCCConfigurationVehicleSCCNodes.md) or [Configuration of Chargepoint SCC Nodes](../../../CANoeCANalyzer/SmartCharging/SCProcedures/SCConfigurationChargePointSCCNodes.md).

## Function Syntax

```
long SCC_SLAC_GetLinkStatus ()
```

## Description

This function retrieves the internally stored link status of the HomePlug Green PHY chip.

## Parameters

—

## Return Values

- **0**: No link available.
- **1**: Link is available.
- **2**: Link status is unknown (chip is not responding).

## Example

—

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)