[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCCreateCMSLACMatchReq.md)

**CAPL Functions** » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [SLAC Test Functions](../CAPLFunctionsSmartChargingOverview.md#SLACtest) » [Shared Functions](../CAPLFunctionsSmartChargingOverview.md#SLACtest) » SCC_CreateCM_SLAC_Match_Req

# SCC_CreateCM_SLAC_Match_Req

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
void SCC_CreateCM_SLAC_Match_Req ( byte RunId[], byte SourceMac[], byte TargetMac[], byte PEVMacAddress[], byte EVSEMacAddress[] )
```

## Description

Creates a **CM_SLAC_Match.Req** message for sending.

## Parameters

- **RunId**: Random Run Identifier of sender (8 byte).
- **SourceMac**: Source address of the Ethernet packet.
- **TargetMac**: Destination address of the Ethernet packet.
- **PEVMacAddress**: MAC Address of the PEV.
- **EVSEMacAddress**: MAC Address of the EVSE.

### Additional Parameters

1. **ApplicationType**: `dword`
   - 0x00 = PEV-EVSE Association
   - 0x01-0xFF = Reserved

2. **SecurityType**: `dword`
   - 0x00 = No Security
   - 0x01 = Public Key Signature
   - 0x02-0xFF = Reserved

3. **MVFLength**: `dword`
   - Length of the match variable field.

4. **PEVID**: `byte[]`
   - 17 byte ID

5. **EVSEID**: `byte[]`
   - 17 byte ID

6. **Reserved field**: `byte[]`
   - 8 byte

## Return Values

—

## Example

—
