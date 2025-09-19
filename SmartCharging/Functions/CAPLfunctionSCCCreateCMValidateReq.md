[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCCreateCMValidateReq.md)

**CAPL Functions** » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [SLAC Test Functions](../CAPLFunctionsSmartChargingOverview.md#SLACtest) » [Shared Functions](../CAPLFunctionsSmartChargingOverview.md#SLACtest) » SCC_CreateCM_Validate_Req

# SCC_CreateCM_Validate_Req

[Valid for: CANoe DE](../../../Shared/FeatureAvailability.md) • CANoe4SW DE

## Function Syntax

```plaintext
void SCC_CreateCM_Validate_Req 
( byte SourceMac[], byte TargetMac[], 
dword ListenTimer )
```

## Description

Creates a **CM_Validate.Req** message for sending.

## Parameters

- **SourceMac**: Source address of the Ethernet packet.
- **TargetMac**: Destination address of the Ethernet packet.
- **ListenTimer**: Time duration while the EVSE shall listen to BCB-toggles:
  - 0x00 = 100 ms
  - 0x01 = 200 ms

### Additional Parameters

1. **SignalType** (dword):
   - 0x00 = PEV S2 toggles on CPLT line
   - 0x01-0xFF = Reserved

2. **Result** (dword):
   - 0x00 = Not Ready
   - 0x01 = Ready
   - 0x02 = Success
   - 0x03 = Failure
   - 0x04 = Not Required
   - 0x05-0xFF = Reserved

## Return Values

—

## Example

—

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
