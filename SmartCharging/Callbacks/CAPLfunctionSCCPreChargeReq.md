[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Callbacks/CAPLfunctionSCCPreChargeReq.md)

**CAPL Functions** » **Smart Charging** » **SCC Modeling Libraries (Simulation Setup)** » **EVSE Callback Functions** » **SCC_PreChargeReq**

# SCC_PreChargeReq

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
void SCC_PreChargeReq ( byte SessionID[], float TargetVoltage, float TargetCurrent )
```

## Description

The callback is called as soon as a PreCharge Request is received.

Further details that are transmitted in this request can be queried with the following functions:

- [GetDC_EVStatus](../Functions/CAPLfunctionSCCGetDCEVStatus.md)

## Parameters

- **SessionID**: 8-byte long SessionID of SCC connection, range: 0 – 0xFF FF FF FF FF FF FF FF
- **TargetVoltage**: Voltage demand
- **TargetCurrent**: Current demand

## Return Values

—

## Example

—

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
