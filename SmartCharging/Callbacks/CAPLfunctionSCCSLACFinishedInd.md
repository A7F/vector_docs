[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Callbacks/CAPLfunctionSCCSLACFinishedInd.md)

## SCC_SLACFinishedInd

[CAPL Functions](../../CAPLfunctions.md) » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [Shared Callback Functions](../CAPLFunctionsSmartChargingOverview.md#Callback) » SCC_SLACFinishedInd

**Valid for**:  CANoe DE • CANoe4SW DE

### Note

If you are not using a real HomePlug Green PHY chip, use [SCC_SLAC_SetLinkStatus(1)](../Functions/CAPLfunctionSCCSLACSetLinkStatus.md) during this callback to make the SECC Discovery start instantly.

### Function Syntax

```plaintext
void SCC_SLACFinishedInd ( dword Result )
```

### Description

The callback is called when a SLAC run has been completed. It marks the point in time when the SECC Discovery process can be started, if a match has been found and as soon as the link is established.

The vehicle can use the function [SCC_SLAC_GetAttenResults](../Functions/CAPLfunctionSCCSLACGetAttenResults.md) during this callback to get the measured attenuation values.

### Parameters

- **Result**: Result of the SLAC run (2 = PLC link established and interval for Amplitude Map Exchange elapsed, 1 = match, 0 = no match).

### Return Values

—

### Example

—

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)