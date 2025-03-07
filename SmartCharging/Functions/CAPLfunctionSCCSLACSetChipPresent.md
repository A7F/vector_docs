[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCSLACSetChipPresent.md)

### SCC_SLAC_SetChipPresent

[CAPL Functions](../../CAPLfunctions.md) » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [SLAC Simulation](../CAPLFunctionsSmartChargingOverview.md#SLACSim) » [EVSE Functions](../CAPLFunctionsSmartChargingOverview.md#SLACSim) » SCC_SLAC_SetChipPresent

#### Valid for:  
CANoe DE • CANoe4SW DE

#### Function Syntax

```
long SCC_SLAC_SetChipPresent ( dword ChipPresent )
```

#### Description

Configures the SLAC protocol to run with a real HomePlug Green PHY chip, or without it. This toggles the sending of artificial attenuation data.

**Note**: This function overrides the configuration parameter `<SLAC_ChipPresent>`. The supplied EV / EVSE configurations for VT8770 are already configured to use a real chip - there is no need to adapt these.

#### Parameters

- **ChipPresent**: 1 to disable chip simulation, 0 to enable chip simulation.

#### Return Values

- **0**: Not successful
- **1**: Successful

#### Example

—

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)