[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCCreateCMAttenCharRsp.md)

[CAPL Functions](../../CAPLfunctions.md) » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [SLAC Test Functions](../CAPLFunctionsSmartChargingOverview.md#SLACtest) » [Shared Functions](../CAPLFunctionsSmartChargingOverview.md#SLACtest) » SCC_CreateCM_Atten_Char_Rsp

# SCC_CreateCM_Atten_Char_Rsp

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE  •  CANoe4SW DE

## Function Syntax

```c
void SCC_CreateCM_Atten_Char_Rsp ( byte RunId[], 
byte SourceMac[], byte TargetMac[], 
byte SourceAddress[] )
```

## Description

Creates a **CM_Atten_Char.Rsp** message for sending.

## Parameters

- **RunId**: Random Run Identifier of sender (8 byte).
- **SourceMac**: Source address of the Ethernet packet.
- **TargetMac**: Destination address of the Ethernet packet.
- **SourceAddress**: MAC Address of the PEV which initiates the SLAC process.

### Additional Parameters

- **Index 0**
  - **Name**: ApplicationType
  - **Type**: dword
  - **Description**:
    - 0x00 = PEV-EVSE Association
    - 0x01-0xFF = Reserved

- **Index 1**
  - **Name**: SecurityType
  - **Type**: dword
  - **Description**:
    - 0x00 = No Security
    - 0x01 = Public Key Signature
    - 0x02-0xFF = Reserved

- **Index 2**
  - **Name**: Result
  - **Type**: dword
  - **Description**: 0x00 = Success

- **Index 3**
  - **Name**: SourceId
  - **Type**: byte[]
  - **Description**: 17 byte ID

- **Index 4**
  - **Name**: RespId
  - **Type**: byte[]
  - **Description**: 17 byte ID

## Return Values

—

## Example

—

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
