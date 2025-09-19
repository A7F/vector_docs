[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCCreateCMSetKeyCnf.md)

[CAPL Functions](../../CAPLfunctions.md) » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [SLAC Test Functions](../CAPLFunctionsSmartChargingOverview.md#SLACtest) » [Shared Functions](../CAPLFunctionsSmartChargingOverview.md#SLACtest) » SCC_CreateCM_Set_Key_Cnf

# SCC_CreateCM_Set_Key_Cnf

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE  •  CANoe4SW DE

**Note**  
The **Result** code representation (0x01="Success"/0x00="Failure") is according to the Qualcomm specification, which has also been adopted by other PLC-chip manufacturers.

## Function Syntax

```c
void SCC_CreateCM_Set_Key_Cnf ( byte SourceMac[], byte TargetMac[], dword Result )
```

## Description

Creates a **CM_Set_Key.Cnf** message for sending.

## Parameters

- **SourceMac**: Source address of the Ethernet packet.
- **TargetMac**: Destination address of the Ethernet packet.
- **Result**: Result code:
  - 0x00 = failure
  - 0x01 = success
  - 0x02-0xFF = reserved

### Additional Parameters

- **Index 0**: MyNonce, `byte[]`, 4 byte random number.
- **Index 1**: YourNonce, `byte[]`, Last received nonce (4 byte).
- **Index 2**: PID, `dword`, Protocol ID.
- **Index 3**: PRN, `byte[]`, Protocol Run Number (2 byte).
- **Index 4**: PMN, `dword`, Protocol Message Number.
- **Index 5**: CCoCapability, `dword`, STA’s CCo Capability.

## Return Values

—

## Example

—

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
