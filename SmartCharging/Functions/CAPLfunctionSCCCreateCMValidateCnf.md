[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCCreateCMValidateCnf.md)

[CAPL Functions](../../CAPLfunctions.md) » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [SLAC Test Functions](../CAPLFunctionsSmartChargingOverview.md#SLACtest) » [Shared Functions](../CAPLFunctionsSmartChargingOverview.md#SLACtest) » SCC_CreateCM_Validate_Cnf

# SCC_CreateCM_Validate_Cnf

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE  •  CANoe4SW DE

## Function Syntax

```plaintext
void SCC_CreateCM_Validate_Cnf ( byte SourceMac[], byte TargetMac[], dword Result, dword ToggleNum )
```

## Description

Creates a **CM_Validate.Cnf** message for sending.

## Parameters

- **SourceMac**: Source address of the Ethernet packet.
- **TargetMac**: Destination address of the Ethernet packet.
- **Result**: Result code:
  - 0x00 = Not Ready
  - 0x01 = Ready
  - 0x02 = Success
  - 0x03 = Failure
  - 0x04 = Not Required
  - 0x05-0xFF = Reserved
- **ToggleNum**: Number of BC-edges detected by the EVSE.
- **Additional Parameters**:
  - **Index**: 0
  - **Name**: SignalType
  - **Type**: dword
  - **Description**:
    - 0x00 = PEV S2 toggles on CPLT line
    - 0x01-0xFF = Reserved

## Return Values

—

## Example

—

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
