[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCCreateCMSLACParmCnf.md)

**CAPL Functions** » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [SLAC Test Functions](../CAPLFunctionsSmartChargingOverview.md#SLACtest) » [Shared Functions](../CAPLFunctionsSmartChargingOverview.md#SLACtest) » SCC_CreateCM_SLAC_Parm_Cnf

# SCC_CreateCM_SLAC_Parm_Cnf

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
void SCC_CreateCM_SLAC_Parm_Cnf ( byte RunId[], byte SourceMac[], byte TargetMac[], dword NumSounds, dword TimeOut, byte ForwardingSTA[] )
```

## Description

Creates a **CM_SLAC_Parm.Cnf** message for sending.

## Parameters

- **RunId**: Random Run Identifier of sender (8 byte).
- **SourceMac**: Source address of the Ethernet packet.
- **TargetMac**: Destination address of the Ethernet packet.
- **NumSounds**: Number of M-Sounds to be transmitted.
- **TimeOut**: Timeout for transmission of M-Sounds in multiples of 100ms.
- **ForwardingSTA**: MAC address where the measurement results shall be sent to.

### Additional Parameters

| Index | Name          | Type   | Description                              |
|-------|---------------|--------|------------------------------------------|
| 0     | RespType      | dword  | 0x00 = HLE of the STA, 0x01 = Another GP STA, 0x02-0xFF = Reserved |
| 1     | MSoundTarget  | byte[] | Target MAC address for M-Sounds          |
| 2     | ApplicationType | dword | 0x00 = PEV-EVSE Association, 0x01-0xFF = Reserved |
| 3     | SecurityType  | dword  | 0x00 = No Security, 0x01 = Public Key Signature, 0x02-0xFF = Reserved |

## Return Values

—

## Example

—
