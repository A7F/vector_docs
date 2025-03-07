[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCCreateCMAttenCharInd.md)

[CAPL Functions](../../CAPLfunctions.md) » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [SLAC Test Functions](../CAPLFunctionsSmartChargingOverview.md#SLACtest) » [Shared Functions](../CAPLFunctionsSmartChargingOverview.md#SLACtest) » SCC_CreateCM_Atten_Char_Ind

# SCC_CreateCM_Atten_Char_Ind

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE  •  CANoe4SW DE

## Function Syntax

```c
void SCC_CreateCM_Atten_Char_Ind ( byte RunId[], 
byte SourceMac[], byte TargetMac[], 
byte SourceAddress[], dword NumSounds, 
dword NumGroups, byte AAG[] )
```

## Description

Creates a **CM_Atten_Char.Ind** message for sending.

## Parameters

- **RunId**: Random Run Identifier of sender (8 byte).
- **SourceMac**: Source address of the Ethernet packet.
- **TargetMac**: Destination address of the Ethernet packet.
- **SourceAddress**: MAC Address of the PEV which initiates the SLAC process.
- **NumSounds**: Number of M-Sounds used to generate the ATTEN_PROFILE.
- **NumGroups**: Number of attenuation groups.
- **AAG**: Average Attenuation Group (array length is indicated by the parameter **NumGroups**).

### Additional Parameters

| Index | Name           | Type   | Description                          |
|-------|----------------|--------|--------------------------------------|
| 0     | ApplicationType| dword  | 0x00 = PEV-EVSE Association, 0x01-0xFF = Reserved |
| 1     | SecurityType   | dword  | 0x00 = No Security, 0x01 = Public Key Signature, 0x02-0xFF = Reserved |
| 2     | SourceId       | byte[] | 17 byte ID                           |
| 3     | RespId         | byte[] | 17 byte ID                           |

## Return Values

—

## Example

—

© Vector Informatik GmbH

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)