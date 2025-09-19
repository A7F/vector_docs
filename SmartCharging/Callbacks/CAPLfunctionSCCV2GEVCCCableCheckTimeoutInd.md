[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Callbacks/CAPLfunctionSCCV2GEVCCCableCheckTimeoutInd.md)

**CAPL Functions** » **Smart Charging** » **SCC Modeling Libraries (Simulation Setup)** » **EV Callback Functions** » **SCC_V2G_EVCC_CableCheck_TimeoutInd**

# SCC_V2G_EVCC_CableCheck_TimeoutInd

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```
(void SCC_V2G_EVCC_CableCheck_TimeoutInd 
 byte SessionID[] )
```

## Description

The callback is called as soon as an V2G_EVCC_CableCheck_Timeout occurs.

## Parameters

- **SessionID**: 8-byte long SessionID of the SCC connection, range: 0 – 0xFF FF FF FF FF FF FF FF.

## Return Values

—

## Example

—

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
